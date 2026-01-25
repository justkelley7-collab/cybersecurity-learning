"""
Simple Password Strength Checker
Evaluates passwords based on basic security rules.
"""

def check_password_strength(password):
    """
    Check password strength and return score with feedback.
    
    Args:
        password: String to evaluate
        
    Returns:
        Dictionary with strength level and feedback
    """
    score = 0
    feedback = []
    
    # Check if password exists
    if not password:
        return {"strength": "Invalid", "score": 0, "feedback": ["Password cannot be empty"]}
    
    # Check length
    length = len(password)
    if length < 8:
        feedback.append("Too short - use at least 8 characters")
    elif length < 12:
        score += 1
        feedback.append("Decent length")
    else:
        score += 2
        feedback.append("Good length")
    
    # Check for lowercase letters
    if any(c.islower() for c in password):
        score += 1
        feedback.append("Contains lowercase letters")
    else:
        feedback.append("Add lowercase letters")
    
    # Check for uppercase letters
    if any(c.isupper() for c in password):
        score += 1
        feedback.append("Contains uppercase letters")
    else:
        feedback.append("Add uppercase letters")
    
    # Check for numbers
    if any(c.isdigit() for c in password):
        score += 1
        feedback.append("Contains numbers")
    else:
        feedback.append("Add numbers")
    
    # Check for special characters
    special_chars = "!@#$%^&*(),.?\":{}|<>"
    if any(c in special_chars for c in password):
        score += 1
        feedback.append("Contains special characters")
    else:
        feedback.append("Add special characters (!@#$%)")
    
    # Check against common passwords
    common_passwords = ['password', '123456', 'qwerty', 'abc123', 'letmein']
    if password.lower() in common_passwords:
        score = 0
        feedback.append("WEAK: This is a common password!")
    
    # Determine strength level
    if score <= 2:
        strength = "Weak"
    elif score <= 4:
        strength = "Moderate"
    else:
        strength = "Strong"
    
    return {
        "strength": strength,
        "score": score,
        "feedback": feedback
    }


def main():
    """Run the password checker."""
    print("=" * 50)
    print("PASSWORD STRENGTH CHECKER")
    print("=" * 50)
    print("\nThis tool checks for:")
    print("• Minimum length (8+ characters)")
    print("• Uppercase and lowercase letters")
    print("• Numbers and special characters")
    print("• Common weak passwords")
    print("=" * 50)
    
    while True:
        print("\nEnter a password to check (or 'quit' to exit):")
        password = input("> ")
        
        if password.lower() == 'quit':
            print("\nGoodbye!")
            break
        
        # Evaluate the password
        result = check_password_strength(password)
        
        # Display results
        print("\n" + "-" * 50)
        print(f"Strength: {result['strength']}")
        print(f"Score: {result['score']}/6")
        print("\nFeedback:")
        for item in result['feedback']:
            print(f"  {item}")
        print("-" * 50)


# Run the program
if __name__ == "__main__":
    main()
