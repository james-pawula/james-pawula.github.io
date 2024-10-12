---
layout: post
title: 'John the Ripper: A Powerful Password Cracking Tool'
date: 2024-10-09 09:16 -0800
categories: [tutorials, john the ripper] 
tags: [tutorials, john the ripper]
---

**John the Ripper: A Powerful Password Cracking Tool**
=====================================

John the Ripper is a popular, free, and open-source password cracking tool that can automatically detect password hash types and supports a wide range of password hash types, including DES, MD5, and SHA. It's a powerful tool that can be used for both ethical and unethical purposes, so it's essential to use it responsibly and with permission.

### What is John the Ripper?

John the Ripper is an offline password cracking tool that was developed in 1996 by Openwall Project. It's notable for supporting a diversity of password formats. It's included in the default repositories for many Linux distributions, including Debian and Ubuntu, and installed by default in most penetration testing distributions, including Kali and BlackArch.

### How to Install John the Ripper on Windows and Linux

#### Installing on Windows

To install John the Ripper on Windows, you can download the executable file from the official website and follow the installation instructions.

#### Installing on Linux

To install John the Ripper on Linux, you can use the package manager for your distribution. For example, on Ubuntu or Debian, you can use the following command:
```shell
sudo apt-get install john
```

## How to Use John the Ripper
John the Ripper has several modes to crack passwords, including single crack mode, wordlist mode, and incremental mode. Here are some examples of how to use John the Ripper:
```shell
    john
```

#### Cracking a SHA Hash
<p>To crack a SHA256 hash using John the Ripper, you can use the following command:</p>
```shell
john --format=Raw-SHA256 --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
```

##### Cracking an MD5 Hash
To crack an MD5 hash using John the Ripper, you can use the following command:
```shell
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
```

#### Cracking a Password Using a Wordlist
To crack a password using a wordlist, you can use the following command:
```shell
john --wordlist=/usr/share/wordlists/rockyou.txt passwordfile
```

### Incremental Mode
In Incremental Mode, John tries all possible character combinations as passwords. This process can be time-consuming if the password is too long or if alphanumeric characters and symbols comprise the password.

You won’t use this Mode unless you don’t have any other options. Typically, a combination of social engineering attacks and Wordlist Mode will help you uncover most passwords.

The syntax for Incremental Mode is:
```shell
john --incremental --incremental-charcount=N --format=FORMAT passwords_to_crack.txt

john -inc --incremental-charcount=N --format=FORMAT passwords_to_crack.txt
```

## How To Crack a Zip Using John the Ripper 
To crack a password-protected ZIP file, we first get the hash of the ZIP file’s password:
```shell
zip2john file.zip > zip.hashes
```

This command gets the hash from the ZIP file and stores it in the zip.hashes file.

Now you can crack the hash with John:

john zip.hashes # Single Crack Mode

```shell
john --wordlist=rockyou zip.hashes # Using the RockYou wordlist
``` 

#### Helpful Commands
<table> <tr> <th>Flag</th> <th>Description</th> </tr> <tr> <td>--show FILE</td> <td>Show cracked passwords based on hashes from FILE</td> </tr> <tr> <td>--rules, -ru</td> <td>Enable word-mangling rules to teach John the Ripper how to generate passwords</td> </tr> <tr> <td>--status</td> <td>Print the status of an interrupted or running session</td> </tr> <tr> <td>--session=NAME</td> <td>Give a new John the Ripper session a NAME, to which John will form the session file name NAME.rec; useful for running multiple instances of John in parallel or to be able to recover later a session other than the last one you interrupt</td> </tr> <tr> <td>--restore[=NAME]</td> <td>Continue an interrupted cracking session, reading state information from the specified session file or the default session at the file path $JOHN/john.rec</td> </tr> <tr> <td>--save-memory=LEVEL</td> <td>Enable memory saving at LEVEL 1, 2, or 3. Level 1 tells John not to waste memory on login names, and may speed things up. Levels 2 and 3 reduce John’s use of performance optimizations involving large lookup tables and thus may impact performance negatively.</td> </tr> <tr> <td>--test[=TIME]</td> <td>Run tests (and benchmarks, unless TIME is explicitly 0), each spanning TIME seconds</td> </tr> <tr> <td>&</td> <td>Run the command in the background (only applies to Kali Linux and other Unix-based operating systems)</td> </tr> <tr> <td>--format=NAME</td> <td>Specify the hash type for John the Ripper to detect</td> </tr> <tr> <td>--list=formats, --list=subformats</td> <td>Reveal the hash types John the Ripper supports</td> </tr> <tr> <td>--single, -si</td> <td>Enable Single Crack Mode</td> </tr> <tr> <td>--wordlist=FILE, -w=FILE</td> <td>Enable Wordlist Mode, specifying a Wordlist (dictionary attack)</td> </tr> <tr> <td>--incremental, -inc</td> <td>Enable Incremental Mode</td> </tr> </table>

#### Resources

<ul>
  <li><a href="https://www.freecodecamp.org/news/crack-passwords-using-john -the-ripper-pentesting-tutorial/">How to Crack Passwords using John the Ripper – Pentesting Tutorial</a></li> 
  <li><a href="https://www.openwall.com/john/doc/FAQ.shtml">John the Ripper - Frequently Asked Questions (FAQ)</a></li>
  <li><a href="https://www.openwall.com/john/">John the Ripper - Official Website</a></li>
  <li><a href="https://www.openwall.com/john/doc/EXAMPLES.shtml">John the Ripper - Examples and Documentation</a></li> 
  </ul>

  