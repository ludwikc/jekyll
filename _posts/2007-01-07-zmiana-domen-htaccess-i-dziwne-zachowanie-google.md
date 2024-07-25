---
id: 111
title: 'Zmiana domen, .htaccess i dziwne zachowanie Google'
date: '2007-01-07T17:38:32+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://blog.ludwikc.net/2007/01/07/zmiana-domen-htaccess-i-dziwne-zachowanie-google/'
permalink: /zmiana-domen-htaccess-i-dziwne-zachowanie-google/
tags:
    - ''
dsq_thread_id:
    - '2205051126'
views:
    - '837'
bsb_share_transient_facebook:
    - '1605605989'
bsb_share_count_facebook:
    - '0'
bsb_share_transient_linkedin:
    - '1605605990'
bsb_share_count_linkedin:
    - '0'
categories:
    - Szuflandia
format: image
---

W związku z wygaśnięciem mojej umowy hostingowej z [SuperHost.pl](http://superhost.pl) (z [kilku powodów](/2006/08/06/czy-superhost.pl-plajtuje/)) i totalnej indolencji administratorów serwera domen [art.pl](http://art.pl) kupiłem nowe domeny dla [chóru](http://www.collegiumcantorum.com) i jego [dyrygenta](http://www.janusz.siadlak.pl) (a prywatnie mojego ojca 🙂 ). Po trzykrotnej konsultacji telefonicznej (ponieważ na mailowy kontakt z supportem liczyć **nie można** – otwarte tickety helpdesku są **zamykane** bez **żadnego** sygnału dla użytkownika) dowiedziałem się, że absolutnie nie ma możliwości przekierowywania domen \*.art.pl na inne bez wykupienia hostingu. Argumenty, że pozostaję ich klientem (mam tam kilka domen globalnych) niestety nie przekonały administratorów, którzy *nie dysponują odpowiednimi narzędziami do takich zabiegów*.

Cóż, nie pozostało mi nic innego, jak znaleźć [dobrą duszę](http://www.rajwedkarza.pl/), która posiadając konto w <abbr title="SuperHost.pl">SH</abbr> *przygarnie* te trzy domeny i ustawi im HTTP:301 na nowe.   
Wszystko gra. Przekierowania w `.htaccess` standardowe (przykład dla domeny [collegiumcantorum.art.pl](http://www.collegiumcantorum.com)):

```
Options +FollowSymLinks
RewriteEngine on
RewriteRule (.*) http://www.collegiumcantorum.com/ [R=301,L]
```

Po kilku dniach wyniki w Googlach prezentowały się następująco:

1. collegium-cantorum.bis.top.pl – nasza pierwsza domena
2. collegiumcantorum.art.pl
3. collegiumcantorum.com

Siadlak.pl też wylądowało tuż pod *art* a [mój blog](http://personaldevelopment.pl) (na który BTW przekierowałem domene ludwikc.art.pl) skoczył o jedną – dwie pozycje wyżej.

Niestety, dziś sytuacja się skomplikowała. Śledząc[ pozycję](https://www.google.pl/search?hl=pl&client=opera&rls=en&hs=WZa&q=collegium+cantorum&btnG=Szukaj&lr=&gfe_rd=cr&ei=WS9KVYrAOc6v8weF04CoCw&gws_rd=ssl) [strony chóru](http://www.collegiumcantorum.com) przy okazji zapytałem google o [mojego bloga](https://www.google.pl/search?hl=pl&client=opera&rls=en&hs=WZa&q=ludwikc&btnG=Szukaj&lr=&gfe_rd=cr&ei=GzJKVfq9GtOv8weX0YGABg&gws_rd=ssl). Niestety. Nie ma go w wynikach! Zamiast niego pojawiła się strona główna mojej domeny, [www.ludwikc.net](http://personaldevelopment.pl/), która dotąd była listowana w okolicach 5 miejsca.   
Zasadniczo mi to nie przeszkadza, bo na stronie głównej mam ustawione

```
<meta http-equiv="refresh" content="2;url=http://blog.ludwikc.net/" />
```

Problem pojawia się jednak przy zapytaniu [“siadlak”](https://www.google.pl/search?hl=pl&client=opera&rls=en&hs=WZa&q=siadlak&btnG=Szukaj&lr=&gfe_rd=cr&ei=Ti9KVdevEsev8wfsqYG4Bw&gws_rd=ssl). Strona [siadlak.pl](http://www.janusz.siadlak.pl), jeszcze wczoraj zajmująca zaszczytne 3 miejsce, zaraz po siadlak.art.pl, również została usunięta!  
Skąd takie zachowanie Google? Co je powoduje i jak temu zaradzić?

Może **Ty** wiesz, czytelniku?  
  
\[tags\]hosting, htaccess, google, seo\[/tags\]