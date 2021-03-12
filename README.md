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
![image](https://user-images.githubusercontent.com/65858555/110905362-52cbc480-8345-11eb-878f-84597f63356a.png)
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
## The flag
`LNC{IS_THlS_TH3_R3AL_0N3?}`


