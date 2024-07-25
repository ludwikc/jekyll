---
id: 57
title: 'AdSense i WordPress. Bloguj z reklamami bez reklam!'
date: '2013-12-28T17:12:36+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://blog.ludwikc.net/?p=57'
permalink: '/?p=57'
tags:
    - ''
categories:
    - Szuflandia
---

Zasadniczo, blogi (jeśli mówimy o blogach technicznych, a nie *rósHoWyChh blOgAssKaCh*) dzielą się na dwie grupy

- blogi z reklamami – w mniejszym bądź większym stopniu wbudowanymi w treść (*patrz [Piotr Konieczny](http://blog.konieczny.be), [Tomasz Topa](http://tomasz.topa.pl)*)
- blogi bez reklam – tam, gdzie liczy się tylko treść (*patrz [Patrys](http://room-303.com/blog), [nbw](http://enbewu.net/blog)*)

Na moim blogu również pojawiły się ostatnio reklamy, ale teraz już *zniknęły*. [Zarobki z reklam](http://www.sprawnymarketing.pl/artykuly/urbanowicz-o-blogach/#comment-149) na moim blogu nie były wysokie, a jednak zmniejszały jego czytelność. Skoro jednak bloggerzy dzielą się na dwa obozy, tych którzy reklamy umieszczają i tych, których te reklamy drażnią, więc i czytelnicy na takie obozy muszą się [dzielić](http://www.sprawnymarketing.pl/artykuly/zarabianie-web20/).

### Blokada w przeglądarce

Oczywiście, [niektórzy](http://paweltkaczyk.midea.pl/498/#comment-6087) stosują [UserCSS](http://blog.konieczny.be/2006/08/21/czytaj-koniecznego-wygodniej/) czy [adBlock’i](http://mozillapl.org/katalogi_i_bazy/baza_dodatkow/rozszerzenia/inne/adblock_plus) do wyłączenia niechcianych reklam, ale to jednak wymaga pewnej wiedzy. Szaremu użytkownikowi nie przyjdzie do głowy możliwość zastosowania takich wybiegów.  
Poniżej (z dedykacją dla użytkowników [WordPress’a](http://wordpress.org)) najprostsze dostosowanie wyświetlania reklam do preferencji czytelnika.

### AdSense plugin

Do publikowania reklam na [swoim blogu](http://blog.ludwikc.net) używam wtyczki [AdSenseDeluxe](http://www.acmetech.com/blog/2005/07/26/adsense-deluxe-wordpress-plugin/). Jest bardzo wygodna i funkcjonalna. Po wrzuceniu jej w `/wp-content/plugins/`, na stronie opcji możemy zdefiniować dowolną ilość formatów reklam. Dzięki temu w zależności od ukladu wpisu jaki nam się buduje, możemy wstawić odpowiednie reklamy. Do wpisu, jak i szablonu, rzecz jasna. Ważną opcją jest dodawanie formatów reklam niezależnie od AdSense’owego UserID, co przy redagowaniu bloga przez kilku użytkowników pozwala na rozgraniczenie zarobków. Ot, każdy wstawia swoje.  
Również samo doklejanie reklam do wpisu jest maksymalnie uproszczone, bo sprowadza się do umieszczenia w jego treści komentarza `\<!--adsense-->`.

Co daje taki efekt:  
  
(nie widzisz reklam? czytaj [dalej…](#ukryj))

### Treść przede wszystkim

Jak napisałem wyżej, różni ludzie mają różne podejścia do prezentacji treści na swoich stronach/blogach (z zaznaczeniem, że to nad blogami właśnie chciałbym się zastanowić, bo komercyjne serwisy WWW, to zupełnie inna kwestia). Najbardziej optymalnym rozwiązaniem problemu dostosowania przedstawianej treści do preferencji czytelników jest nic innego jak **pozostawienie** im **wyboru**.

Stąd też moja propozycja: dajmy [możliwość klikania](http://www.sprawnymarketing.pl/artykuly/zarabianie-web20/) tym którzy chcą klikać, lecz nie zmuszajmy do tego tych, którzy tego nie chcą.

\[tags\]wordpress, blogs, adsense, advertisement, usability\[/tags\]