# Password Hacker

This Python script is designed to execute a brute-force attack on a server by attempting to login using a series of potential usernames and passwords. It operates by sending login attempts to the server, firstly to identify a valid username from a provided list, and subsequently to discover the corresponding password. The attack utilizes a timing attack vector for password discovery, assuming that the server's response time can hint at a correct password character.

## How It Works

1. **Username Discovery:** The script starts with trying to find a valid username from a given list (`logins.txt`). It sends login requests to the server with each username and a blank password. If the server responds indicating a wrong password, it implies that the username exists.
   
2. **Password Discovery:** Upon finding a valid username, the script attempts to guess the password. It appends characters one by one to the password field, measuring the server's response time for each attempt. A notably longer response time suggests a correct character guess, allowing the script to progressively construct the password.

## Requirements

- [Python 3](https://www.python.org/downloads/)

## Installation

This application is written in Python, so you'll need Python installed on your computer to run it. If you don't have Python installed, you can download it from [python.org](https://www.python.org/downloads/).

To install this project, clone the repository to your local machine:

```
git clone https://github.com/SonikSeven/password-hacker.git
```

## Usage

To use this script, you should have a file named `logins.txt` in the same directory as the script. This file should contain possible usernames, one per line.

Open the command line, navigate to the directory where the script is located and run it by providing the target IP address and port number:

```
python main.py [IP address] [Port]
```

For example:

```
python main.py 127.0.0.1 9090
```

## Disclaimer

This script is provided for educational purposes only. Performing brute-force attacks without explicit permission from the target is illegal and unethical. Use this script responsibly and only on servers you are authorized to test.

## License

This project is licensed under the [MIT License](LICENSE.txt).
