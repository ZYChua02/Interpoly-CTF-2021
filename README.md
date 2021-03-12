# Interpoly-CTF-2021
Writeups on the challenges I solved in the Interpoly CTF (Lag and Crash) 2021

# Table of Contents
* Misc
  * Tedious? Or is it? 
* Crypto 
  * Nokia 
  * Oink Oink 
  * weak n insecure
* Forensics
  * Do you believe in Aliens
* OSINT
  * div0
* Personal thoughts on the CTF

# Misc
## Tedious? Or is it
## Challenge Description
My friend pranked me and hide my secret in one these!
## Approach
</br>
We were given a zip file named tedious. I unzipped the file and inside a folder name 'QR' there are even more zip files, from 0.zip and 4255.zip
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/110905132-f9fc2c00-8344-11eb-92d7-d17894b5a512.png)
</br>
</br>
I remember in a write up I read that when there are many files, the first thing is to look for anomalies (Date modified/Size), in this case I decided to sort the zip files by date modified and sure enough there is a anomally in 1337.zip
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/109409967-d85c8580-79d1-11eb-92db-b954e2ba7462.png)
</br>
</br>
I tried unzipping the file but it was not a zip file
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/110905482-80187280-8345-11eb-91f4-3397795639d4.png)
</br>
</br>
I decided to use cyberchef to determine the file type and found out that it was a QR code, so I decided to use the Parse QR code functionality in cyberchef to get the flag
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/110905798-06cd4f80-8346-11eb-96ab-217ee188a89e.png)
</br>
</br>
## The Flag
`LNC{IS_THlS_TH3_R3AL_0N3?}`
# Crypto
## Nokia
## Challenge Description
Look at my indestructible keypad phone!
</br>
66 666 55 444 2 444 7777 7777 8 444 555 555 8 44 33 22 33 7777 8 0
</br>
PS Take note after decryption, the output is NOT in flag format LNC{}. The final flag entered should be in all caps eg LNC{THIS_IS_THE_FLAG}.
## Approach
I knew that this was the numpad that was found in nokia phones so I proceeded to use dcode to do it and get the flag
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/110910840-d5a44d80-834c-11eb-8b34-c652b7ccafb2.png)
</br>
</br>
## The flag
`LNC{NOKIAISSTILLTHEBEST}'



