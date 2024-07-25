---
id: 193
title: 'Zautomatyzowane backupowanie plików'
date: '2008-02-26T20:09:31+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://blog.ludwikc.net/2008/02/26/zautomatyzowane-backupowanie-plikow/'
permalink: /zautomatyzowane-backupowanie-plikow/
dsq_thread_id:
    - '2171676518'
views:
    - '611'
bsb_share_transient_facebook:
    - '1605608386'
bsb_share_count_facebook:
    - '0'
bsb_share_transient_linkedin:
    - '1605608386'
bsb_share_count_linkedin:
    - '0'
categories:
    - Szuflandia
format: image
---

Stare słowiańskie przysłowie głosi, że

> Administratorzy dzielą się na dwie grupy: tych, którzy robią backupy i tych, którzy jeszcze nie robią backupów.

Kilka tygodni temu, w pewne piątkowe popołudnie zdarzyło mi się permanentnie uszkodzić tablicę partycji na głównym dysku mojego desktopu. Nie miałem kopii, a zabawa nie wskazywała na to, że coś może się uszkodzić. [Murphy](http://www.murphys-laws.com/murphy/murphy-computer.html) i tym razem się nie mylił i zawartość dysku odeszła w niepamięć.

Oczywiście robię backupy. Weekly, w każdy… piątkowy wieczór. Pech chciał, że w tym właśnie tygodniu rozpocząłem intensywną pracę nad kolejnym [uczelnianym](http://www.ox.ac.uk) assignmentem i kilka stron eseju… również odeszło w niepamięć.

  
Postanowiłem więc zmienić system backupowania z ręcznego na automatyczny, szczególnie jeśli pracuję z Windows (w Linuksie nie ma tego problemu, od czego jest przecież cron?).

Z pomocą przyszedł zatem bardzo przyjemny soft Louisa Cobiana (studenta szwedzkiego [Umeå University](http://www.umu.se/)) – [Cobian Backup](http://www.educ.umu.se/~cobian/cobianbackup.htm).

<div style="text-align:center">![Cobian Backup 8](http://personaldevelopment.pl/wp-content/uploads/2008/02/cobian11.png)</div>Program pozwala na zdefiniowanie backupowych tasków w dowolny sposób: co miesiąc, co tydzień, tylko w czwartki, tylko o 13 i 19 w piątki i wtorki, etc. Obsługa jest banalnie prosta – foldery, które mają być archiwizowane wystarczy przeciągnąć z eksploratora Windows do programu, podać namiary na nośnik na którym mają być zapisane i voila. Nośnik jest dowolny – połącznie FTP, SSH, dysk zewnętrzny, inna partycja – bez różnicy. Plusów jest więcej:

- 4 rodzaje backupów: 
    - full
    - incremental
    - differential
    - dummy
- kompresja – zip i sqx
- szyfrowanie – DES, RSA, Rijndael i Blowfish
- wyjątki – w każdym ze zdefiniowanych katalogów można wybrać pomijane pliki
- akcje przed- i pobackupowe – możliwość uruchomienia/zakończenia dowolnej usługi czy programu w dowolnym czasie
- przeprowadzanie backupu jako inny użytkownik
- limitowanie prędkości transferu (usługa działa w tle i jedynym sygnałem jest ikona w tray’u)
- logowanie akcji w plikach txt (z możliwością powiadamiania via e-mail)
- sprawdzanie CRC przesłanych plików
- masterpassword, żeby nikt *“przypadkiem”* nie anulował naszych kopii 🙂

Aktualnie stabilną wersją jest 8.4.0.202 Black Moon, udostępniona na Mozilla Public License. Louis pracuje nad 9 (codename Amanita), ale ta nie jest i nie będzie już *wolna*. 8 jednak taką jest i pozostanie (źródła do pobrania z [SourceForge](http://sourceforge.net/projects/cobianbackup)).

*Ask the Readers:* **Jakiego softu do backupowania swoich plików używacie?**