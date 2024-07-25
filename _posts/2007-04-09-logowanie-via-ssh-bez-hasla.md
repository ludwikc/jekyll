---
id: 123
title: 'Logowanie via SSH bez hasła'
date: '2007-04-09T17:55:26+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://blog.ludwikc.net/2007/04/09/logowanie-via-ssh-bez-hasla/'
permalink: /logowanie-via-ssh-bez-hasla/
dsq_thread_id:
    - '2195921965'
views:
    - '720'
bsb_share_transient_facebook:
    - '1605625102'
bsb_share_count_facebook:
    - '0'
bsb_share_transient_linkedin:
    - '1605625103'
bsb_share_count_linkedin:
    - '0'
categories:
    - Szuflandia
format: image
---

Nie, to nie będzie wpis informujący o tym, że logując się przez SSH nie trzeba za każdym razem wklepywać hasła.  
Mam kilka kont z dostępem do shella, a wykonywanie rutynowych czynności umożliwiających bezhasłowe logowanie (jak to zwykle z rutyną bywa) zaczęło mnie nudzić. Napisałem prosty skrypt, który na kształt kreatora wyda wszystkie niezbędne plecenia.

### HOWTO

Zakładam, że masz juz swój klucz publiczny. Jeśli nie – stwórz go, wydając w konsoli polecenie

```
ssh-keygen -t rsa
```

Generator zapyta o nazwe pliku i hasła. Możesz na wszystkie pytania odpowiedzieć Enterem, pozostawiając domyślne ustawienia.

Skrypt możesz zapisać na dysku kopiując jego treść z poniższej ramki. Dla wygody umieściłem go jednak na serwerze. Teraz wystarczy wpisać:

```
wget http://projects.ludwikc.net/passwordless_ssh
chmod +x passwordless_ssh
./passwordless_ssh
```

Po kolei:

1. nazwa użytkownika konta ssh
2. adres hosta
3. port serwera (dafault’owo 22)
4. hasło (2x)

Od tego momentu wystarczy wpisac w konsoli

```
./yourhostname.com
```

 żeby połączyć się z serwerem bez podawania hasła (oczywiście `ssh user@host` też będzie działać bez zarzutu!)

**Enjoy 🙂**

Treść dla zainteresowanych:  
`#!/bin/sh<br></br>cd $HOME<br></br>echo "Passwordless ssh (v. 0.6)"<br></br>echo "Enter your ssh username:"<br></br>read user<br></br>echo "Host (or ip):"<br></br>read host<br></br># Ports added in 0.4<br></br>echo "Enter ssh port: (press Enter if you don't know)"<br></br>read port<br></br>if port=NULL<br></br>then port=22<br></br>fi<br></br>echo "Wait for connection and type password for given username"<br></br>scp -P $port $HOME/.ssh/id_rsa.pub $user@$host:~/id_rsa-passwordless.pub<br></br>echo "Success: RSA key exported."<br></br>echo "Last with-password ssh login..."<br></br>ssh $user@$host -p $port "if [ -d $dotssh ]<br></br>then<br></br>        echo "Success: Directory $HOME/.ssh/ exists."<br></br>        else<br></br>                echo -e "There is no $HOME/.ssh/ directory." && mkdir $HOME/.ssh && echo "Success: Directory $HOME/.ssh has been created"<br></br>                fi &&<br></br>                cat ~/id_rsa-passwordless.pub >> .ssh/authorized_keys && rm id_rsa-passwordless.pub && chmod 700 ~/.ssh && chmod 600 ~/.ssh/authorized_keys && exit"<br></br>echo "Authorization successful!"<br></br># Added in 0.3 version - symlinks providing easier login<br></br>echo ""<br></br>if [ -d $HOME/.ssh/passwordless_login ]<br></br>then<br></br>echo "Directory $HOME/.ssh/passwordless_login has been created during last passwordless_ssh usage."<br></br>else<br></br>mkdir $HOME/.ssh/passwordless_login<br></br>fi<br></br>echo ssh $user@$host -p $port >> ~/.ssh/passwordless_login/$host<br></br>chmod +x ~/.ssh/passwordless_login/$host<br></br>ln -s ~/.ssh/passwordless_login/$host $host<br></br>echo "From now-on simply type ./$host, to log-in without password."<br></br>echo "Passwordless ssh by Ludwik C. Siadlak http://personaldevelopment.pl/). GPL Licence. Have a nice day!"<br></br>`

<ins datetime="2007-04-09T18:17:51+00:00">UPDATE:</ins> v. 0.4 – Możliwość wyboru portu innego niż 22.  
<ins datetime="2007-04-10T15:36:27+00:00">UPDATE:</ins> v. 0.5 – Powłoka zmieniona na `/bin/sh` dla kompatybilności z systemami \*BSD.  
<ins datetime="2007-04-11T11:18:05+00:00">UPDATE:</ins> v. 0.6 – Sprawdzanie katalogów (*dzięki Jojo!*) i domślny port połączenia. (Wersja *passwordless\_ssh-pl* została zastąpiona oryginalną *passwordless\_ssh*)  
\[tags\]linux, bash\[/tags\]