# Password Generator

A simple and customizable password generator script written in Python.

## Markdown
```python
import random
import stringa
import time
from random import choice


custom_mod = input("Do you want use custom character (Y/N)---->").strip().lower()


def password_generator(legnth = 12, use_upper=True, use_lower=True,
                       use_digits=True, use_symbol=True, custom_character=''):

    if custom_character.strip():
        char_pool = custom_character
    else :
        char_pool = ''
        if use_upper:
            char_pool += string.ascii_uppercase
        if use_lower:
            char_pool += string.ascii_lowercase
        if use_symbol:
            char_pool += string.punctuation
        if use_digits:
            char_pool += string.digits
    if not char_pool :
        raise ValueError("Error --> you should choice one character !!!")

    final_password=''.join(random.choice(char_pool) for _ in range(legnth))
    return final_password

legnth = int(input("Choice Your Legnth Password (EXAM = 12) --->"))


if custom_mod.lower() == 'y':

    custom_character = input("Enter Your character --->").strip()
    final_password = password_generator(legnth, custom_character=custom_character)

    print("\n your password generate === ", final_password)

elif custom_mod == 'n':

    print("\n OK you want use ATUO Genarate")
    big_char = input("Do You Want Use BIG Word (Y/N)---->")
    low_char =  input("Do You Want Use SMALL Word (Y/N)---->")
    sym_char = input("Do You Want Use SYMBOL (Y/N)---->")
    dig_char = input("Do You Want Use DIGITS (Y/N) ")

    if big_char.lower() == 'y':
        use_upper = True
    else:
        use_upper = False

    if low_char.lower() == 'y':
        use_lower = True
    else:
        use_lower = False

    if sym_char.lower() == 'y':
        use_symbol = True
    else:
        use_symbol = False

    if dig_char.lower() == 'y':
        use_digits = True
    else:
        use_digits = False

    final_password = password_generator(
        legnth=legnth,
        use_upper=use_upper,
        use_lower=use_lower,
        use_digits=use_digits,
        use_symbol=use_symbol
    )

    print("\n your password generate === ", final_password)
```
## Features

- Generate passwords with custom length
- Choose to include uppercase letters, lowercase letters, digits, and symbols
- Option to generate password from a custom set of characters
- Easy-to-use interactive command line interface

## Requirements

- Python 3.x

## Usage

Run the script and follow the interactive prompts:

```bash
python pass_gen.py
