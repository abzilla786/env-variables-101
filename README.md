# Environment Variables in bash

this class is on Environment Variables


### what is an Environment Variable

Variable is like a box, you can put things inside and give it a name.

For us an Environment is a system where code runs. Usually at least 3 environments exist:
- development
- testing
- production

**Environment** Variable are variable that exist on said environments and are interpolated from the environments and NOT from the code.

**Environment Variables exist in the machine NOT the code**

This is great for things:
- risk reduction
- things that you don't want to have in your code!
- like access keys!
- like AWS_SECRET keys
- similar to SSH keys, THEY NEVER GO IN THE CODE!

Allows us to keep them secret and they don't end up on github where some wanna be hacker is going to find them and mine bitcoin.

you can create variables in the terminal such as:
```
MY_VAR=GOODYEAARRRR
```

to view them you can use the command:
```
$echo MY_VAR
```
this will print GOOODDYEAAARRRRR as thats whats stored in the variable.

you can also set MY_VAR to run code/ functions
so if you input:
```
MY_VAR=$(pwd)
```
so now is we run:
```
echo $MY_VAR
```
it will run the PWD command which will show you your current location.

if you close your terminal it will close the entire session and the variables will not be stored under persistent status.

this is because in bash variables are stored on a session by session basis however there are ways to create persistent variable that will stay even if you close your session.

### bash CHILD process, and exporting
to create a child process we can
```
touch example_bash.sh
```
and use atom to edit it.

once open if we add in two simple lines and save it:

echo 'My process'

echo $MY_VAR

now to run the file we will use the command
```
./example_bash.sh
```
however we will get an error as we will need to give it the right permissions.

we can do this by running the command:
```
chmod 777 example_bash.sh
```
so now if we run the previous command we will se in our terminal My process being printed.

if we create a new variable will a value under the same name, such as:
```
MY_VAR=AMAZING
```
and run the command for our file again we will see nothing is going to change and only My process will be displayed.

to change this we can simply use
```
export MY_VAR=AMAZING
```
and what this will do is export the command as a temporary file so that when you run the ./example_bash.sh command again you will see both values displayed.

to create permanent variables outside of the file we have created we can go into our ~ directory and edit the file .zshrc

over there we can write a line for our variable such as:

```
export MY_VAR=YELLOOWWWWWMELLOWWW
```
so that when we close our terminal and run our file again it will display My process along with the new variable we have created as it is now outside of the session dependent limits.
