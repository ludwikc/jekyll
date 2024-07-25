---
id: 59
title: 'Kubuntu 6.10. Pierwsze spojrzenie'
date: '2006-10-29T02:13:25+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://blog.ludwikc.net/2006/10/29/kubuntu-610-pierwsze-spojrzenie/'
permalink: /kubuntu-610-pierwsze-spojrzenie/
tags:
    - ''
dsq_thread_id:
    - '2198767387'
views:
    - '502'
bsb_share_transient_facebook:
    - '1605982967'
bsb_share_count_facebook:
    - '0'
bsb_share_transient_linkedin:
    - '1605982968'
bsb_share_count_linkedin:
    - '0'
categories:
    - Szuflandia
format: image
---

![Kubuntu](http://personaldevelopment.pl/wp-content/uploads/2006/10/kubuntu11.gif)Jako, że nadal nie znalazłem czasu, żeby przejść na jakieś lekkie środowisko<sup>[\*](#wm)</sup>, a interfejs [GNOME](https://www.gnome.org/) jest wg mnie mało atrakcyjny, [pobrałem](http://www.kubuntu.org/getkubuntu) z sieci [Ubuntu](http://www.ubuntu.org/) z prefiksem [K](http://www.kubuntu.org/).

### Instalacja

Z premedytacją wybrałem opcję najbardziej typową dla newbies, czyli *zrób sobie miejsce na dysku i się zainstaluj*. Instalacja przebiegła bez problemów, choć (mimo braku większej uwagi) dopatrzyłem się kilku literówek (m.in. *Przzeglądanie plików* czy strefa czasowa *WarszawaL*).  
Miejsce zrobiło się bez problemów a w [Grubie](http://www.gnu.org/software/grub/) pojawiła się nowa pozycja.

### 10 minut w nowym systemie

Tytułem wstępu: To nie jest profesjonalna recenzja nowej wersji Ubuntu. Ot, moje przemyślenia, zgodnie z [disclaimerem](http://blog.ludwikc.net/about/).

Pierwsza uwaga: **+**: Logo podczas ładowania sytemu jest przyjaźniejsze i milsze dla oka. Szczególnie niewprawnego. Również pasek postępu jest ładniejszy. Ale tu pojawia się minus: nie mamy żadnej informacji o ładowanych modułach. Jesteśmy zostawieni na pastwę losu, dokładnie tak, jak od lat postępuje [konkurencja](http://www.microsoft.com). Oczywiście, dla początkujących użytkowników nie ma to znaczenia i nie przerażają komunikaty typu

> Connecting to ntp.ubuntulinux.com — <span style="color:red">Failed</span>

Zasadniczo jest to punkt do tyłu, choć Ubuntu z założenia jest przystosowane dla początkujących, więc pominę to w końcowej klasyfikacji. Z pewnością wielu takie rozwiązanie będzie odpowiadać.  
Cieszy również nowy, gładki ekran logowania.

Zaskakująca, po uruchomieniu managera okien, jest zawartość katalogu `/`. Otóż mamy w nim zaledwie 2 (słownie: dwa) katalogi: `/home` i `/media`. Włączenie wyświetlania plików ukrytych, oczywiście zwraca nam resztę zawartości, z plikiem `.hidden` w którym możemy definiować które katalogi maja być domyślnie ukrywane, i obrazem jadra. Oczywiście – rozwiązanie bardzo wygodne dla niedoświadczonych uzytkowników, z założeniem, że system ma działać, a nie chcemy się go uczyć. Sam przyznam, że przez jakiś czas korzystałem z Kubuntu. Z czystego lenistwa i wygody jaką oferuje ten system w momencie, kiedy nie ma się kilku wolnych godzin na konfigurację [Slackware](http://www.slackware.com) czy kilku wolnych dni na instalację [Gentoo](https://www.gentoo.org/).

[KDE](https://www.kde.org/) niestety nadal nie jest spolonizowane po instalacji. Oczywiście, można zrobić `apt-get upgrade`, ale skoro system jest zorientowany na *nowoprzybyłych*, winien jest zapewnić im możliwie komfortowe warunki na rozpoczęcie przygody z wolnymi systemami. Minus.

KLaptop został zastąpiony o wiele gorszym (zaznaczam, że korzystałem z systemu przez 10 minut!) PowerManagerem. Mając końcówkę baterii (która i tak wystarczyła na przeprowadzenie instalacji) po załadowaniu się systemu Bateria wskazywała pozostały czas 2:00<abbr title="godziny">h</abbr>, a po 4-5 minutach 1:00h. Bez zmian. Aż do momentu przejścia w stan wstrzymania. Również bez ostrzeżenia, znanego mi dotąd z Klaptopa.

### Podsumowanie

Podsumowania brak. Zbyt mało czasu spędziłem w tym systemie by go należycie ocenić. Moja opinia się jednak potwierdza. Ubuntu (z dowolnym prefiksem) jest systemem który jest definitywnie zorientowany na nowych, niedoświadczonych użytkowników, którzy chcą znaleźć alternatywę dla Windows<sup>™</sup>. Takiej inicjatywie należy zdecydowanie przyklasnąć. Ale trzeba też mieć nadzieję, że nie przeistoczy się w drugą [Mandrivę](http://www.mandriva.com/en/).  
Jest jednak jeszcze sporo do zrobienia, a najważniejszą rzeczą jaką powinni zająć się developerzy z [Canonical](http://www.canonical.com/) jest pełna lokalizacja systemu tuz po instalacji (bez aktualizowania!).

---

<sup><a name="wm">\*</a></sup> – moje typy to [fluxbox](http://fluxbox.sourceforge.net/) i [fvwm](http://www.fvwm.org/), z naciskiem na to drugie, bo jest *“mniej GTK”*. A może w [GNOME](https://www.gnome.org/) coś się zmieniło przez ostatnie 2 lata?

\[tags\]kubuntu, ubuntu, linux, first look, WM,\[/tags\]