phpLintBash
===========

# Usage
$ phpLint

- Will recursively lint all PHP files in default directory specified in script

$ ./phpLint [directory]

Lint all files recursively of specified directory

# Overview:
  
- Will return a pass / fail
- Will only pass if all files pass
- Any errors will be output in addition to the file they were found in

# Scope:
	- This is a syntax checker. It will not run methods and check for correct returns
	- It is not a static analysis tool. Code quality / specs are not enforced or searched for

# Caveats and Best Practice:
	- The nature of PHP's lint operation is to abort linting of a file once an error has been found, so...
		- If a file has multiple errors you will only be notified of the first error
		- Run until you're error-free
		- Although linting of the current file may have stopped due to a syntax error,
			linting of any remaining files in the queue will continue.

# Scripting / Deployment Usage:
	- This will return proper exit codes so it can be used for scripting deployments, etc.
		- Pass
			- Exit 0 (clean)
			- Output on stdin
		- Fail
			- Exit 1
			- Output on stderr

Requires: PHP
