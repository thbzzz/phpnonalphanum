# PHPNonAlphaNum
This script is inspired by the work of [0xchrisb](https://github.com/0xchrisb) here: https://github.com/0xchrisb/thesis-non-alphanumeric-code-generator/blob/master/Generating%20Code%20by%20using%20Bitwise%20Operations/php_and_perl_code_by_using_bitwise_operations.pl

It is just a Python3 rewrite with more complete features, that I find very useful especially for CTF.



## Usage
```
phpnonalphanum.py [-u] <php_code>
phpnonalphanum.py [-u] [-e] -x <function> <parameters>...
phpnonalphanum.py (-h | --help)
```

## Options
```
-e                             Echo the payload result. Default behavior will execute the payload, but you might need to echo the result. (Actually calls printf)
-u                             URL encode every character of the payload.
-x <function> <parameters>...  Generate PHP code ready to be passed in an 'eval' function. Default behavior just encodes a PHP string.
-h --help                      Shows this message.
```

## Examples
```
phpnonalphanum.py 'echo base64_encode(file_get_contents("index.php"))'
phpnonalphanum.py -x 'system' 'ls'
phpnonalphanum.py -u -e -x 'call_user_func' 'file_get_contents' '.htaccess'
```
