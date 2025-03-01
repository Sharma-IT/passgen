# `passgen`

![image](https://github.com/user-attachments/assets/4aa74a57-2a3b-41fb-b291-72a03a24c1c1)

Feature-rich and lightweight CLI password generator. This password generator provides a simple yet powerful command-line interface for generating strong and cryptographically randomised passwords. With it's focus on performance, security, and usability, this password generator enables anyone to conveniently and quickly create strong passwords whether or not they use a password manager.

## Table of Contents

1. [Features](#features)
2. [Minimum System Requirements](#minimum-system-requirements)
3. [Dependencies](#dependencies)
4. [Getting Started](#getting-started)
5. [Usage](#usage)
6. [Contributing](#contributing)
7. [Contact](#contact)
8. [License](#license)

## Features

- Lightweight and user-friendly CLI
- Performs many times faster than GUI-based alternatives
- Configurable maximum password length limit and password strength
- Password strength checking using zxcvbn
- Uses Python's `secrets` module for cryptographically secure password generation
- Does not require admin privileges
- Automatically logs generated passwords into a text file
- Copy generated passwords directly to clipboard
- Generates symmetric cryptographic key to encrypt and decrypt text file
- Opens text file using the operating system's default text editor
- Secure key storage using system keyring
- Configurable via JSON configuration file
- Wipe stored passwords or encryption keys
- Runs offline and makes no outgoing or incoming network connections
- Executable is only 8 MB in size
- Uses an average of 20 MB of RAM (and only for a second) when generating passwords
- Source code contains plenty of docstrings, is easily readable and editable

## Minimum System Requirements

- **Processor (CPU):** Intel Core Solo
- **Windows Operating System:** Microsoft Windows XP
- **macOS Operating System:** Mac OS X
- **Linux Operating System:** Ubuntu Oneiric Ocelot
- **Memory:** 500 MB RAM
- **Storage:** 1 GB (or 8 MB excl. neccessary OS files)

**NOTE:** Generating passwords with a character length of 16 or less will be instantaneous or take only a few seconds for most PCs, consuming an average of 15 to 20 MB of RAM during that time. However, generating passwords exceeding 16 characters may take over a minute and utilise more than 100 MB of RAM for a couple of seconds, though this is largely dependant on your PC's specifications. For example, testing on an M1 MacBook revealed that passwords with character lengths as long as 99999 could be generated in under a second.

## Dependencies

- [`python`](https://www.python.org/) - high-level, general-purpose programming language.
- [`cryptography`](https://cryptography.io/en/latest/) -  package which provides cryptographic recipes and primitives to Python developers.
- [`keyring`](https://pypi.org/project/keyring/) - cross-platform library for secure password and key storage.
- [`zxcvbn`](https://pypi.org/project/zxcvbn/) - realistic password strength estimation.
- [`pyperclip`](https://pypi.org/project/pyperclip/) - cross-platform clipboard module for Python.

## Getting Started

You can install the package directly from this repository:
```sh
pip install git+https://github.com/sharma-it/password-generator.git
```

Or clone and install locally:
```sh
git clone https://github.com/sharma-it/password-generator.git
cd password-generator
pip install -e .
```

After installation, you can use the tool from anywhere by running:
```sh
passgen -g p          # Generate a password interactively
passgen -g p -l 12    # Generate a 12-character password
passgen -g p -l 16 -c # Generate a 16-character password and copy to clipboard
passgen -g p -c       # Generate a password interactively and copy to clipboard
passgen -g k          # Generate an encryption key
passgen -h            # Show help
```

## Usage

The application uses a configuration file (`config.json`) to store settings like:
- Password file location
- Minimum and maximum password length (default: 8-64 characters)
- Minimum required password strength (0 - 4, default: 3)
- Key storage name

By default, the script stores generated passwords into a text file named `passwords.txt`. The encryption key is securely stored in your system's keyring as `password_generator_key`. All files are stored in the same directory as the script.

### Command-Line Arguments

| Argument | Description |
| -------- | ----------- |
| -g p, --generate p | Generate a new password |
| -l N, --length N | Generate password with length N (optional) |
| -c, --copy | Copy generated password to clipboard |
| -g k, --generate k | Generate new encryption key |
| -w t, --wipe t | Wipe the passwords file |
| -w k, --wipe k | Wipe the stored encryption key |
| -o, --open | Open the passwords file |
| -e, --encrypt | Encrypt the passwords file |
| -d, --decrypt | Decrypt the passwords file |
| -h, --help | Show help message |

## Contributing

Pull requests are welcomed. For major changes, please open an issue first to discuss what you would like to change.

## Contact

- [LinkedIn](https://www.linkedin.com/in/sharma-it/)
- [X](https://x.com/shubsharmatech)

## License

This project is licensed under the GPL 3.0 License - see the [LICENSE](LICENSE) file for details.
