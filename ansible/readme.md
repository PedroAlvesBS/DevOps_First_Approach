# This file is created to help in the setting up moment

## pam_pwquality.yml FILE

The password must be encrypted, so you must execute some steps before to just past it

If you wat to create generate a password using the linux you first has to install two packages

1. pwgen
2. mkpasswd

The first will generate the password and the second will encrypt it.

Just execute as follow

```
pass=`pwgen --secure --capitalize --numerals --symbols 12 1`
```

`--secure`, means the password will be generated randomly and is switable for machine password
`--capitalize`, will insert capitalized characters
`--numerals`, this parameters will let in consideration numerals
`--symbols` symbols will be used in the password
`12` is how many characters the password will have
`1` stands for how many password will be created

As the pass variable was created, we now execute the code below

```
echo $pass | mkpasswd --stdin --method=sha-512; echo $pass
```

we capture the password with `--stdin` as a good practice, and use as a encryption method `sha-512` 

The output will be the digest of hash function and the plain password

## authorized_keys.yml

Now it is necessary that you generate a ssh key pair to connect remotely through ssh protocol

if you are at a linux base host just type

```
ssh-keygen -t rsa -f ~/.ssh/<name-of-file> -C <name-of-file>
```

`-t` stands type of key pair 
`-f` it is the file location
`-C` it is a comment added to the key-pair generation

