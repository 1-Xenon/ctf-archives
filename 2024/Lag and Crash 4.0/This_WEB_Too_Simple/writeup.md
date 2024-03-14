## Challenge Description
![image](https://github.com/1-Xenon/ctf-archives/assets/110148117/fe2db848-edca-400e-835d-c2f8e2540435)

## Writeup
Opening the challenge, I was greeted by the following web page
![image](https://github.com/1-Xenon/ctf-archives/assets/110148117/30f23816-1bbc-4338-8c18-82fa59289ad1)

I then clicked on the login button and was redirected to a login page
![image](https://github.com/1-Xenon/ctf-archives/assets/110148117/cd8fb094-70ac-45ce-96c0-38d2cae0f649)

Naturally when I first see input pages, I will try to test for SQL Injection and see if it works. The payload that I used for this page was ```test' OR 1=1 -- // ```
I then clicked on login and found that it had worked and the following message appeared:
```"Login Successful, This is your key: E9bYhRnW9P5QRtEdwsv15pJX"```

Hmm, a key. Wonder what that is for. This is the point where I was stuck for a while as I did not how I should be utilising this key to get the flag. I then remembered that I could use robots.txt to check if there are any other pages I could navigate to. I went to the file and found the following

![image](https://github.com/1-Xenon/ctf-archives/assets/110148117/51c13d55-f41f-45ec-8304-9f41d5d6d06a)

So there is an admin page that exists after all, I then navigated to the admin page and was greeted with the following
![image](https://github.com/1-Xenon/ctf-archives/assets/110148117/e2f5273a-1bb7-41d7-91b1-437b97a9e93a)

This was when I decided to inspect the cookies to see if the login that I had done initally had provided me with a cookie and I found the following:
![image](https://github.com/1-Xenon/ctf-archives/assets/110148117/9b2e3f0e-0a66-49c7-b2ca-a3740f297a11)

So there is a token assigned after the login was done, and by the looks and format of the token, it is a JWT token. I then head to jwt.io to throw the token value into the debugger to see what it returns me
![image](https://github.com/1-Xenon/ctf-archives/assets/110148117/cd647e84-1759-4cbf-b850-7cc5cc1be8b4)

This is when the key that we have received from the login comes in. For JWT Tokens, the last part of the token, or known as signature, requires a secret for verification. This is very important for this challenge as we can see that the role that the token assigned was non-admin and that the token expires immediately after it is created. This means that we will need to manipulate this token such that the token does not expire for a while and that we are assigned the admin role
![image](https://github.com/1-Xenon/ctf-archives/assets/110148117/68098b04-ac2c-4215-a3ed-f35e2391e217)

Now that we have our new token, we will replace it with the old one and then try to access the admin page again and tada, we got the flag now.
![image](https://github.com/1-Xenon/ctf-archives/assets/110148117/6f833aec-d363-41cb-b15b-4b277dc1f425)

```LNC24{5imp1e_Bu7_N0t_Simpl3}```






