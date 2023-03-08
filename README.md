# onelinevalidation
onelinevalidation It is a simple library in the Python language that performs validate in an easy and simple way

## Installation

* From PyPi
```
python pip install onelinevalidation
````

## Examples

```python

In default sanitize = True
in validate_form
and custom_validate
This is to prevent a Cross-site Scripting vulnerability
For more https://owasp.org/www-community/attacks/xss/


from onelinevalidation import validate_form


userData = {"username": "amr123", "email": "amr.@aol.com", "password": "123Ab#"}
print(validate_form(userData))
-------------------------
{'username': 'Invalid username should be like this abc_123 or abc. abc', 
'email': 'This email address is not valid', 
'password': 'The password length must be at least 8 uppercase, lowercase letters, numbers, symbols like @aA123#*'
}


## If you want more control use custom_validate 

from onelinevalidation import custom_validate


pattrens = [
	"[a-zA-Z]+[_.]+[a-zA-Z0-9]+", 
	"[a-zA-Z0-9_-]+[@](aol|gmail|yahoo|outlook)+(.com)+",
	"^(?=.*?[A-Z])(?=.*?[a-z])(?=.*?[0-9])(?=.*?[#?!@$%^&*-]).{8,}$"
]


messages = [
	"Invalid username should be like this abc_123 or abc. abc",
	"This email address is not valid",
	"The password length must be at least 8 uppercase, lowercase letters, numbers, symbols like @aA123#*"
]

print(custom_validate(userData, pattrens, messages))

```
