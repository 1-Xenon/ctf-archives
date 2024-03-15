## Challenge Description
![image](https://github.com/1-Xenon/ctf-archives/assets/110148117/41d98c1f-30de-4615-876a-82256cae47e7)

## Writeup
Opening up the text file, we see the following:
```https://1drv.ms/u/s!AgQjno_WN3iOjXe5ywVQ0zcjYiq5?e=cHDa33```

which redirects us to an .wav file. The very first thing I did was to listen to the contents of the file and in the first 5 seconds, I notice that something was off with the audio. I then downloaded the file and placed it into Audacity to review the audio.

![image](https://github.com/1-Xenon/ctf-archives/assets/110148117/112b3f32-c63b-449f-8667-b92c4bfed29d)

We can see that there is indeed something hidden within the first few seconds, upon expanding we find the following

![image](https://github.com/1-Xenon/ctf-archives/assets/110148117/c86128c2-9b75-4886-b778-cf5bafe7793c)

```LNC24{4ud10_5t3ng0``` so thats one part of the flag, cause obviously the bracket was not closed which then brings me to the next question, how am I supposed to get the second part of the flag?

I then went to research more about audio steganography and this is when I came across this term - Least Significant Bits (LSB). Messages could be hidden in the least significant bits of images/audio and this is one of the common steganography techniques that is used.

I then came across this <a href="https://github.com/ragibson/Steganography#WavSteg"> tool </a> which will assist me in getting the second part of the flag

![image](https://github.com/1-Xenon/ctf-archives/assets/110148117/a656160a-c795-4e38-9662-5d666cc06c0e)

Second part of the flag: ```_15_fun}```
```Flag: LNC24{4ud10_5t3ng0_15_fun}```
