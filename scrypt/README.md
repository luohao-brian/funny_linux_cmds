```
[root@hluo scrypt]# ls
hello  README.md  scrypt.sh

# Load scrypt function
[root@hluo scrypt]# . scrypt.sh

# encrypt hello script
[root@hluo scrypt]# scrypt hello
Enter the passphrase (maximum of 512 characters)
Please use a combination of upper and lower case letters and numbers.
Enter passphrase:
Enter passphrase:

Stdin was encrypted.

# an encrypted script was generated.
[root@hluo scrypt]# ls
hello  hello.scrypt  README.md  scrypt.sh

# got an error if password is not correct.
[root@hluo scrypt]# ./hello.scrypt
Enter passphrase:
SHA1 check failed
Stdin was NOT decrypted successfully.
/dev/fd/63:行1: 未预期的符号 `$'^\252\247s\251\303Q\260\355\347a'' 附近有语法错误

# script works as expected if password is correct.
[root@hluo scrypt]# ./hello.scrypt
Enter passphrase:
This is the fantastic Hello World. Try this: hello.scrypt [entity]

[root@hluo scrypt]# ./hello.scrypt world
Enter passphrase:
Hello, world!
```
