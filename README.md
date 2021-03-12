# Interpoly-CTF-2021
Writeups on the challenges I solved in the Interpoly CTF (Lag and Crash) 2021
# Table of Contents
* [Misc](https://github.com/ZYChua02/Interpoly-CTF-2021#misc)
  * [Tedious? Or is it?](https://github.com/ZYChua02/Interpoly-CTF-2021#tedious-or-is-it)
* [Crypto](https://github.com/ZYChua02/Interpoly-CTF-2021#crypto)
  * [Nokia](https://github.com/ZYChua02/Interpoly-CTF-2021#nokia)
  * [Oink Oink](https://github.com/ZYChua02/Interpoly-CTF-2021#oink-oink)
  * [weak n insecure](https://github.com/ZYChua02/Interpoly-CTF-2021#weak-n-insecure)
* [Forensics](https://github.com/ZYChua02/Interpoly-CTF-2021#forensics)
  * [Do you believe in Aliens?](https://github.com/ZYChua02/Interpoly-CTF-2021#do-you-believe-in-aliens)
* [OSINT](https://github.com/ZYChua02/Interpoly-CTF-2021#osint)
  * [div0](https://github.com/ZYChua02/Interpoly-CTF-2021#div0)
* [Personal thoughts on the CTF](https://github.com/ZYChua02/Interpoly-CTF-2021#personal-thoughts-on-the-ctf)
# Misc
## Tedious? Or is it?
## Challenge Description
My friend pranked me and hide my secret in one these!
## Approach
We were given a zip file named tedious. I unzipped the file and inside a folder name 'QR' there are even more zip files, from 0.zip and 4255.zip
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/110916409-ba890c00-8353-11eb-964b-c13d037b2728.png)
</br>
</br>
I remember in a write up I read that when there are many files, the first thing is to look for anomalies (Date modified/Size), in this case I decided to sort the zip files by date modified and sure enough there is a anomally in 1337.zip
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/110916745-13f13b00-8354-11eb-97e4-74f70a54792d.png)
</br>
</br>
I tried to unzip 1337.zip but it was a not a zip file
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/110917105-7fd3a380-8354-11eb-9ad0-83623fcf2374.png)
</br>
</br>
I decided to put into the cyberchef to determine the file type, but saw that it is a QR code so I used the parse QR code function in cyberchef to retreive the flag
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/110925529-46079a80-835e-11eb-9228-a3dddbbb3819.png)
## The flag
`LNC{IS_THlS_TH3_R3AL_0N3?}`
# Crypto
## Nokia
## Challenge Description
Look at my indestructible keypad phone!
</br>
</br>
66 666 55 444 2 444 7777 7777 8 444 555 555 8 44 33 22 33 7777 8 0
</br>
</br>
PS Take note after decryption, the output is NOT in flag format LNC{}. The final flag entered should be in all caps eg LNC{THIS_IS_THE_FLAG}.
## Approach
I recognised as the keypad that was used in nokia phone in the 2000s so used dcode (Multi-Tap Phone) to get the plain text
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/110917914-7139bc00-8355-11eb-8b49-0fe8b2d9a53a.png)
## The flag
`LNC{NOKIAISSTILLTHEBEST}`
## Oink Oink
## Challenge Description
Oink Oink is the sound I make!
</br>
</br>
Take note after decryption, the output is NOT in flag format LNC{}. The final flag entered should be in all caps eg LNC{THIS_IS_THE_FLAG}.
## Approach
We were given this picture, which is the pigpen cipher
</br>
</br>
![oinkoink](https://user-images.githubusercontent.com/65858555/110918089-a9d99580-8355-11eb-90bd-1c038c07b2ad.jpeg)
</br>
</br>
I decoded it by hand and got THISMIGHTTAKEAWHILEBUTTHEFLAGISOINKOINKPIGISCUTE
## The flag
`LNC{OINKOINKPIGISCUTE}`
## weak n insecure
## Challenge Description
e = 65537 N = 21805564595370162889 cipher = 10421600892944111639
</br>
</br>
find the message :) the message should be a 10-digit long number remember to encapsulate the answer in the flag format LNC{xxxxxxxxxx}
## Approach
I was just reading W3rni0 writeup on NahamCon CTF 2020 where I came across on the Twinning which was a RSA Problem. The way it was solved and the fact that only n, e and the ciphertext was provided was similar hence I decided to use the apporach to tackle this challenge.
</br>
</br>
I went to factordb to get the values of p and q
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/110918929-abf02400-8356-11eb-9aa2-34d7444e27ce.png)
</br>
</br>
I decided I can make use of the script that was in the writeup so I modified the values to the one in the CTF
```python
from Crypto.Util.number import inverse


p = 2625556849
q = 8305119961
e = 65537
ct = 10421600892944111639
n = 21805564595370162889

phi = (p - 1) * (q - 1)
d = inverse(e,phi)
plain = pow(ct,d,n)
print(plain)
```
I ran the program and was able to get the 10-digit number
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/110919623-6f70f800-8357-11eb-995d-e5e98b887004.png)
</br>
</br>

## The flag
`LNC{5342585545}`
## Link to writeup I referenced to
https://github.com/W3rni0/NahamCon_CTF_2020#twinning
# Forensics
## Do you believe in Aliens?
## Challenge Description
I was just listening to my radio...until I caught a secret message sent from the great unknown!
</br>
</br>
Though I can't make sense of it...help?
## Approach
I put the file into sonic visualizer and added spectogrma to get the flag
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/110920200-1190e000-8358-11eb-8422-19be5419d4e0.png)
## The flag
`LNC{tr@sH_2iNt_It}`
# OSINT
## div0
## Challenge Description
Div0 is one of the co-organisers of the Lag n Crash CTF. I wonder what were they previously called.
## Approach
I just went to their website and scrolled down and found what they were previously called (underlined in blue)
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/110920852-d3e08700-8358-11eb-9b69-ed755e232cac.png)
## The flag
`LNC{Edgis}`
# Personal thoughts on the CTF
Honestly the CTF was more difficult than I thought considering it was only for teritiary students, but I learnt new things in this CTF. This includes the use of Sonic Visualizer to anlayse the spectogram in the wav file and reading other writeups to solve the RSA Problem (weak n insecure), which I had tried for a few hours. Riding Solo in this CTF definitely tested my skills to the fullest and there is a lot of room of improvement regarding my performance, but this CTF is a good starting point. Getting 43rd place out of 68 teams that were on the scoreboard was better than I expected.
