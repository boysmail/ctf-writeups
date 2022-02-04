I know that this is a begginer competition, so I decided to use it as a practise to writing writeups
##Challenges list

- [runme.py](#runmepy)
- [ncme](#ncme)
- [convertme.py](#convertmepy)
- [Codebook](#codebook)
- [fixme1.py](#fixme1py)
- [fixme2.py](#fixme2py)
- [PW Crack 1](#pw-crack-1)
- [Glitch Cat](#glitch-cat)
- [PW Crack 2](#pw-crack-2)
- [HashingJobApp](#hashingjobapp)
- [Serpentine](#serpentine)
- [PW Crack 3](#pw-crack-3)
- [PW Crack 4](#pw-crack-4)
- [PW Crack 5](#pw-crack-5)



# runme.py
#### Description
Run the runme.py script to get the flag. Download the script with your browser or with wget in the webshell.

[runme.py](picoctf2022mini-files/runme.py)
#### Solution
Run the script with Python, or just view it in notepad and get the flag.
```
$ python runme.py
```
Flag: ```picoCTF{run_s4n1ty_run}```

# ncme
#### Description
Connect to a remote computer using nc and get the flag. 
$ nc saturn.picoctf.net 57688
#### Solution
Use netcat to connect and get the flag
```
brooo@debian:~$ nc saturn.picoctf.net 57688
picoCTF{s4n1ty_c4t}
```
Flag: ```picoCTF{s4n1ty_c4t}```

# convertme.py
#### Description
Run the Python script and convert the given number from decimal to binary to get the flag.

[convertme.py](picoctf2022mini-files/convertme.py)
#### Solution
You can calculate the number and get the flag that way or you can cheat and view how flag decryption works as the code XOR's flag characters from line 16 with ```enkidu```
```
brooo@debian:~$ python convertme.py
If 86 is in decimal base, what is it in binary base?
Answer: 1010110
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_e2a58836}
```
Flag: ```picoCTF{4ll_y0ur_b4535_e2a58836}```

# Codebook
#### Description
Run the Python script code.py in the same directory as codebook.txt.

[code.py](picoctf2022mini-files/code.py)
[codebook.txt](picoctf2022mini-files/codebook.txt)
#### Solution
You can just place the files in same directory and run code.py, or cheat and see that flag is XORed with password ```chthonian``` from codebook.txt
```
brooo@debian:~$ python code.py
picoCTF{c0d3b00k_455157_8100c7c1}
```
Flag: ```picoCTF{c0d3b00k_455157_8100c7c1}```

# fixme1.py
#### Description
Fix the syntax error in this Python script to print the flag.

[fixme.py](picoctf2022mini-files/fixme1.py)
#### Solution
Run the script and look at the compiler error and remove the indent, or cheat and XOR the flag with ```enkidu```
```
brooo@debian:~$ fixme1.py
  File "fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
    ^
IndentationError: unexpected indent
```
```
brooo@debian:~$ fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_09ee727a}
```
Flag: ```picoCTF{1nd3nt1ty_cr1515_09ee727a}```

# fixme2.py
#### Description
Fix the syntax error in this Python script to print the flag.

[fixme.py](picoctf2022mini-files/fixme2.py)
#### Solution
Run the script and look at the compiler error and fix the syntax by adding ```=```, or cheat and XOR the flag with ```enkidu```
```
brooo@debian:~$ fixme2.py
  File "fixme1.py", line 22
    if flag = "":
            ^
SyntaxError: invalid syntax
```
```
brooo@debian:~$ fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
```
Flag: ```picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}```

# PW Crack 1
#### Description
Can you crack the password to get the flag? Download the password checker [here](picoctf2022mini-files/level1.py) and you'll need the encrypted [flag](picoctf2022mini-files/level1.flag.txt.enc) in the same directory too.

#### Solution
Find the check for user password on line 19 and enter it, can't cheat because the flag is XORed with the user password
```
brooo@debian:~$ python level1.py
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
```
Flag: ```picoCTF{545h_r1ng1ng_56891419}```

# Glitch Cat
#### Description
Our flag printing service has started glitching!

$ nc saturn.picoctf.net 52026
#### Solution
Connect and recive the string, you can try to convert the characters yourself or just put it in python compiler
```
brooo@debian:~$ nc saturn.picoctf.net 52026
'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x65) + chr(0x63) + chr(0x66) + chr(0x33) + chr(0x38) + chr(0x36) + chr(0x31) + '}'
```
```
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x65) + chr(0x63) + chr(0x66) + chr(0x33) + chr(0x38) + chr(0x36) + chr(0x31) + '}'
'picoCTF{gl17ch_m3_n07_becf3861}'
```
Flag: ```picoCTF{gl17ch_m3_n07_becf3861}```

# PW Crack 2
#### Description
Can you crack the password to get the flag? Download the password checker [here](picoctf2022mini-files/level2.py) and you'll need the encrypted [flag](picoctf2022mini-files/level2.flag.txt.enc) in the same directory too.

#### Solution
Almost same as the first one, now you need to decode the password first
```
>>> chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39)
'4ec9'
```
```
brooo@debian:~$ python level2.py
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}
```
Flag: ```picoCTF{tr45h_51ng1ng_9701e681}```

# HashingJobApp
#### Description
If you want to hash with the best, beat this test!
nc saturn.picoctf.net 65352

#### Solution
There is not time limit so you can manually hash the string 3 times or write an auto solver
```
Please md5 hash the text between quotes, excluding the quotes: 'Keanu Reeves'
Answer: 
4d2e1f8eabca061706aec58b21c2e199
4d2e1f8eabca061706aec58b21c2e199
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'my sixteenth birthday'
Answer: 
97a710ca19764e4bcdd09966d7a28859
97a710ca19764e4bcdd09966d7a28859
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'kilts'
Answer: 
64cb30b3223e083fa0a2dad43fae9a0e
64cb30b3223e083fa0a2dad43fae9a0e
Correct.
picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}
```
Flag: ```picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}```

# Serpentine
#### Description
Find the flag in the Python script!

[Serpentine.py](picoctf2022mini-files/serpentine.py)
#### Solution
Check the code to find print_flag() function and call it somewere in main
```
elif choice == 'b':
      print_flag()
```

Flag: ```picoCTF{7h3_r04d_l355_7r4v3l3d_8e47d128}```

# PW Crack 3
#### Description
Can you crack the password to get the flag? Download the password checker [here](picoctf2022mini-files/level3.py) and you'll need the encrypted [flag](picoctf2022mini-files/level3.flag.txt.enc) and the [hash](picoctf2022mini-files/level3.hash.bin) in the same directory too.
There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

#### Solution
You can manually check or write a script to simplify solving
[brute_level3.py](picoctf2022mini-files/brute_level3.py)
```python
import hashlib
pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"]
flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()

def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])

def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


for pw in pos_pw_list:
    user_hash = hash_pw(pw)
    if user_hash == correct_pw_hash:
        print(pw)
        decryption = str_xor(flag_enc.decode(), pw)
        print(decryption)
```
Password is ```1ea2```
Flag: ```picoCTF{m45h_fl1ng1ng_6f98a49f}```

# PW Crack 4
#### Description
Can you crack the password to get the flag? Download the password checker [here](picoctf2022mini-files/level4.py) and you'll need the encrypted [flag](picoctf2022mini-files/level4.flag.txt.enc) and the [hash](picoctf2022mini-files/level4.hash.bin) in the same directory too.
There are 100 potential passwords with 1 being correct. You can find these by examining the password checker script.

#### Solution
Same as PW crack 3 but now you can't manually check all the passwords
[brute_level4.py](picoctf2022mini-files/brute_level4.py)

Password is ```c2a8```

Flag: ```picoCTF{fl45h_5pr1ng1ng_89490f2d}```

# PW Crack 5
#### Description
Can you crack the password to get the flag? Download the password checker [here](picoctf2022mini-files/level5.py) and you'll need the encrypted [flag](picoctf2022mini-files/level5.flag.txt.enc) and the [hash](picoctf2022mini-files/level5.hash.bin) in the same directory too.
Here's a [dictionary](picoctf2022mini-files/dictionaty.txt) with all possible passwords based on the password conventions we've seen so far.

#### Solution
Same as PW crack 4 but now you need to read the dictionary from the file or 
[brute_level5.py](picoctf2022mini-files/brute_level4.py)

Password is ```f920```

Flag: ```picoCTF{h45h_sl1ng1ng_2f021ce9}```
