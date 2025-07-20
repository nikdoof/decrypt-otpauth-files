# decrypt-otpauth-files

This tool allows for decrypting the encrypted backups/account files created by [OTP Auth for iOS](http://cooperrs.de/otpauth.html).

If you find problems with the file format (in particular security related issues), do not hesitate and file an issue.

This is a fork of the original repository at [CooperRS/decrypt-otpauth-files](https://github.com/CooperRS/decrypt-otpauth-files) with a aim to get the script working out of the box with modern Python versions.

## Requirements

  - [Python 3.12](https://www.python.org/downloads/)
  - [uv](https://astral.sh/uv)
  - An encrypted OTP Auth backup/account file

## Usage

1. Clone repository

```
git clone https://github.com/CooperRS/decrypt-otpauth-files.git
cd decrypt-otpauth-files
```

2. Install dependencies

```shell-session
$ uv sync
```

3. Decrypt your OTP Auth file

```shell-session
# Decrypt a full backup file
$ uv run python decrypt_otpauth.py decrypt_backup --encrypted-otpauth-backup <path to your OTP Auth backup>
```

```shell-session
# Decrypt a single account export
$ uv run python decrypt_otpauth.py decrypt_account --encrypted-otpauth-account <path to your OTP Auth account>
```

## Demo

The project contains two OTP Auth exports for demo purposes:

* `backup.otpauthdb`: A complete OTP Auth backup
* `account.otpauth`: One account exported by OTP Auth

The password for both files is `abc123`.

![example gif](demo.gif)

## Credits

Inspired by [ewdurbin](https://github.com/ewdurbin) and his [evacuate_2STP](https://github.com/ewdurbin/evacuate_2stp) repo.
