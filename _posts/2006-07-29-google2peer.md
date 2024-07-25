---
id: 1719
title: Google2Peer
date: '2006-07-29T01:42:43+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://blog.ludwikc.net/2006/08/10/google2peer/'
permalink: /google2peer/
tags:
    - 'google p2p mp3 e-books hacking'
dsq_thread_id:
    - '2809989840'
views:
    - '664'
bsb_share_transient_facebook:
    - '1605900671'
bsb_share_count_facebook:
    - '0'
bsb_share_transient_linkedin:
    - '1605900672'
bsb_share_count_linkedin:
    - '0'
categories:
    - Szuflandia
format: image
---

![Google Hacking](http://personaldevelopment.pl/wp-content/uploads/2006/11/google_hacking.gif)W myśl początku [ostatniego wpisu](http://blog.ludwikc.net/2006/07/26/o-beniaminie-slow-kilka/) na temat programu [Beniamin](http://www.beniamin.pl) w którym napomknąłem o produkcie G2P, postanowiłem owy temat rozszerzyć. Nie jest to temat na cały elaborat, ale krótkie i zwięzłe wyjaśnienie zasad działania, które pozwolą nam dowolnie modyfikować zapytanie do własnych celów. Otóż:

Zasada działania skryptu G2P jest bardzo prosta. Wyszukuję on listingi katalogów zawierających dane wyrażenie – w zależności od naszego wyboru: tytułu e-booka lub nazwy zespołu / utworu. Zapytanie kierowane do Google jest bardzo proste, a jak pisze sam autor: “Napisane po to, żebym nie musiał wklepywać go w wyszukiwarke za każdym razem.” Treść zapytania przy poszukiwaniu muzyki [Mozarta](http://pl.wikipedia.org/wiki/Wolfgang_Amadeusz_Mozart) wyglada tak:

> `intitle:index.of "mp3" +"Mozart" -htm -html -php -asp "Last Modified"`

. Skrypt zwraca wszystkie strony generowane automatycznie przez serwer – bez \*.html, \*.php i innych które wymienimy po minusie. Samo `index.of`i `Last modified` również wskazuje na poszukiwanie takich listingów.  
Zapytanie dotyczące wynajdowania w sieci [e-booków](http://en.wikipedia.org/wiki/E-book) jest juz nieco bardziej zaawansowane:

> `-inurl:htm -inurl:html intitle:"index of" +("/ebooks"|"/book") +(chm|pdf|zip) +"for dummies" "Last Modified"`

A to przez to, że musimy skłonić wyszukiwarkę do odnalezienia stron zawierających rozszerzenia plików wielu typów: w tym przypadku to zarówno `*.chm` jak `*.pdf` i `*.zip`. Rzecz jasna strony które są odnajdywane przez skrypt nie zawsze są tymi których poszukujemy, ale mając do dyspozycji treść zapytań – możemy je sami w dowolny sposób modyfikować.

W związku z powyższym: [Enjoy!](http://g2p.org/)