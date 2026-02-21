
### what is internet?

The internet is:

- **millions of computers**
    
- connected by **wires / fiber / wireless**
    
- following **common rules (protocols)**

![[Pasted image 20260203150845.png]]

>Networking means connecting two or more computers so they can exchange data.

![[Public-vs-Private-IP-Addresses-01-EN.webp]]

### SSH

>SSH lets you control another computer over the internet, securely, using the terminal.

![[Pasted image 20260203194329.png]]

### firewall

A firewall is a security guard for your computer or network.

![[Pasted image 20260203203351.png]]

![[Pasted image 20260203203538.png]]

> **SELinux is an extra security guard inside Linux that controls what programs are allowed to do.**

Even if:

- a user has permission
    
- a service is running
    
- a firewall allows traffic
    

 **SELinux can still say: NO.**

SELinux enforces **Mandatory Access Control (MAC)**.

Meaning:

- Rules are enforced by the system
    
- Users cannot bypass them
    
- Even root must obey
    

 This is different from normal Linux permissions.

![[Pasted image 20260203204846.png]]
![[Pasted image 20260203204918.png]]

![[Pasted image 20260203205021.png]]


**Command to check the net status**

```
ip a
```


#### `nslookup`

>`nslookup` is used to find the IP address of a domain name using DNS


> [!PDF|note] [[Navigating Linux.pdf#page=187&selection=47,6,47,30&color=note|Navigating Linux, p.165]]
> > Key-based Authentication

Key-based authentication means logging in to an SSH server without a password, using cryptographic keys instead.

### SSH Keys Generation

run these commands or you follow the instruction just click on this 

> [!PDF|red] [[Navigating Linux.pdf#page=188&selection=10,0,15,30&color=red|Navigating Linux, p.166]]
> > We need to use the ssh-keygen command to create a new public-private key pair.

```shell
ssh-keygen
```

> [!PDF|yellow] [[Navigating Linux.pdf#page=188&selection=42,0,58,7&color=yellow|Navigating Linux, p.166]]
> > There are multiple algorithms that can be used to generate a key pair. The most common ones are RSA, DSA, and ED25519. The ED25519 algorithm is the new default algorithm used by OpenSSH since it is shorter yet more secure than RSA. If you have an outdated version of OpenSSH, you might get the default RSA algorithm. To change the algorithm, you can use the -t flag along with the ssh-keygen command

but we will use the default one the secure one

