#!/bin/bash 

: '

Author: Jubin Joseph
Version: 1.0 
Description: Password Validation Script

'

echo "Enter your password for testing: "
read password # User input for password for validation

Length=${#password} #Length of password input is saved in variable 

if (( $Length<8 )) #if statement to check length of inputted password
then 
	echo "Password is too short. Validation failed!" 
	exit 1
elif [[ $password =~ [a-z] && $password =~ [A-Z] && $password =~ [0-9] ]];
then
	echo "Password matches all criteria. Validation Passed!"
else
	echo "Password doesn't match all criteria. Validation Failed!"
	exit 1
fi 
exit 0

