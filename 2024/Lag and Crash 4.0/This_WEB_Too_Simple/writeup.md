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


