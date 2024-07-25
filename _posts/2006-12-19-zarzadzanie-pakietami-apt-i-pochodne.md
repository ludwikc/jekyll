---
id: 109
title: 'Zarządzanie pakietami (apt i pochodne)'
date: '2006-12-19T13:23:21+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://blog.ludwikc.net/2006/12/19/zarzadzanie-pakietami-apt-i-pochodne/'
permalink: /zarzadzanie-pakietami-apt-i-pochodne/
tags:
    - ''
dsq_thread_id:
    - '2178595405'
views:
    - '791'
bsb_share_transient_facebook:
    - '1605570696'
bsb_share_count_facebook:
    - '0'
bsb_share_transient_linkedin:
    - '1605570696'
bsb_share_count_linkedin:
    - '0'
categories:
    - Szuflandia
format: image
---

![Linux](http://personaldevelopment.pl/wp-content/uploads/2006/12/linux-tux11.jpg)Swego czasu prowadziłem prezentację z zakresu użytkowania Debianowego systemu zarządzania pakietami jakim jest apt-get. Oto ona.

W poniższej prezentacji postaram się przybliżyć działanie programu *apt* – jednego z najpopularniejszych managerów pakietów jakim dysponuje środowisko OpenSource. *apt* (z ang. *Advanced Packaging Tool*) jest domyślnym zarządcą pakietów w systemie Ubuntu Linux. Dzięki niemu, wydajac jedną komendę jesteśmy w stanie zainstalować każdy z 20 tysięcy(!) programów dostępnych w repozytoriach Ubuntu.

| <div id="toctitle">## Spis treści  </div>- [<span class="tocnumber">1</span> <span class="toctext">Wstęp</span>](#Wst.C4.99p)     - [<span class="tocnumber">1.1</span> <span class="toctext">Pakiety (paczki)</span>](#Pakiety_.28paczki.29)     - [<span class="tocnumber">1.2</span> <span class="toctext">Repozytoria</span>](#Repozytoria)     - [<span class="tocnumber">1.3</span> <span class="toctext">Zależności</span>](#Zale.C5.BCno.C5.9Bci)     - [<span class="tocnumber">1.4</span> <span class="toctext">dpkg</span>](#dpkg) - [<span class="tocnumber">2</span> <span class="toctext">apt a apt-get</span>](#apt_a_apt-get)     - [<span class="tocnumber">2.1</span> <span class="toctext">Konfiguracja apt’a</span>](#Konfiguracja_apt.27a)         - [<span class="tocnumber">2.1.1</span> <span class="toctext">sources.list</span>](#sources.list)     - [<span class="tocnumber">2.2</span> <span class="toctext">Użytkowanie</span>](#U.C5.BCytkowanie)         - [<span class="tocnumber">2.2.1</span> <span class="toctext">Aktualizacja</span>](#Aktualizacja)         - [<span class="tocnumber">2.2.2</span> <span class="toctext">Instalacja</span>](#Instalacja)         - [<span class="tocnumber">2.2.3</span> <span class="toctext">Usuwanie</span>](#Usuwanie)         - [<span class="tocnumber">2.2.4</span> <span class="toctext">Dodatkowe opcje</span>](#Dodatkowe_opcje)     - [<span class="tocnumber">2.3</span> <span class="toctext">Inne możliwości</span>](#Inne_mo.C5.BCliwo.C5.9Bci)         - [<span class="tocnumber">2.3.1</span> <span class="toctext">apt-cache</span>](#apt-cache)             - [<span class="tocnumber">2.3.1.1</span> <span class="toctext">Informacje o pakiecie</span>](#Informacje_o_pakiecie)             - [<span class="tocnumber">2.3.1.2</span> <span class="toctext">Statystyki repozytoriów</span>](#Statystyki_repozytori.C3.B3w)             - [<span class="tocnumber">2.3.1.3</span> <span class="toctext">Podsumowanie</span>](#Podsumowanie)             - [<span class="tocnumber">2.3.1.4</span> <span class="toctext">Zależności</span>](#Zale.C5.BCno.C5.9Bci_2)             - [<span class="tocnumber">2.3.1.5</span> <span class="toctext">Wyszukiwanie</span>](#Wyszukiwanie)     - [<span class="tocnumber">2.4</span> <span class="toctext">Aktualizacja systemu UbuntuLinux</span>](#Aktualizacja_systemu_UbuntuLinux) |
|---|

<a name="Wst.C4.99p"></a>

#  Wstęp 

Apt jest nakładką na zarządce pakietów *dpkg*, do korzystania z którego ze względu na szerokie zastosowania *apt*`a nie jesteśmy praktycznie wcale zobowiązani korzystać. Dzięki repozytoriom, w którym znajduje się jak wspomniałem wyżej ok. 20 000 różnych programów możemy założyć z dużą dozą prawdopodobieństwa, że program jaki nas interesuje będzie się znajdował w jedym z nich.

<a name="Pakiety_.28paczki.29"></a>

##  Pakiety (paczki) 

Najprościej rzecz ujmując pakiet to skompilowany i spakowany program, którego instalacja trwa kilka sekund. Zasadniczo cała opracja polega na pobraniu źródeł programu przez danego developera, skonfigurowaniu go, skompilowaniu (które jest procesem o wiele dłuzszym) na własnym komputerze oraz spakowaniu tak przygotowanego programu w paczkę. Tak przygotowany pakiet jest oczywiście sprawdzany przez opiekunów danego projektu, dzięki czemu jest wolny od błędów.  
Większość systemów korzysta (jeśli w ogóle) z jednego z dwóch typów pakietów:

- **deb** – pakiety opracowane przez twórów Debiana. Wykorzystuje je m.in. Ubuntu.
- **rpm** – system paczek opracowany dla RedHata. Wykorzystywany przez Fedorę, Mandrivę, Auroksa i wiele innych.
- **tgz** –

<a name="Repozytoria"></a>

##  Repozytoria 

Repozytoria to serwery, na których gromadzone są pakiety. Dodanie danego repozytorium do pliku *sources.list* pozwala nam ściągnąć każdy ze znajdujących się w nim programów. Do czynienia mamy z repozytoriami oficjalnymi (markowanymi przez Ubuntu), oraz nieoficjalnymi (repozytoria poszczególnych programów bądź grup developerskich, jak również osób które mają dostęp do szybkich i pojemnych serwerów na których udostępniają wybrane programy).  
Ponadto w jednym repozytorium mogą (i często właśnie tak jest) znajdować się pakiety dla różnych wersji danej dystrybucji. I tak dla Ubuntu mamy w oficjalnych repozytoriach pakiety oznaczone “horay”, “breezy”, oraz “dapper” – odpowiednio dla wersji 5.04, 5.10 oraz 6.06.  
Trzecia “zmienna” jaka jest istotna do zdefiniowania repozytorium przez plik *sources.list* to sekcje. Pakiety zostały posortowane w pewne działy, dzięki którym łatwiej jest je zidentyfikować. Dla Debiana są to m. in. *stable, main, contrib* oraz *non-free* (z zaznaczeniem, że *non-free* oznacza *niewolne* a nie jak mogłoby się zdawać *niedarmowe* – znajdują się tam takie programy jak np. wirtualna maszyna Java),a w Ubuntu *main, restricted, universe* oraz *multiverse* To od nas zależy które sekcje wybierzemy. Więcej informacji n/t sekcji znajduje się poniżej, w rozdziale *sources.list*.

<a name="Zale.C5.BCno.C5.9Bci"></a>

##  Zależności 

W programach pisanych na systemy rodziny Windows® każdy stanowi jednolitą całość. Program to nie jeden plik, ale cały zestaw plików, bibliotek i modułów. Takie biblioteki. Każda firma musi rzecz jasna napisać własne, bo źródła innych nie są wolne, nie ma do nich dostępu. 3 firmy piszą 3 biblioteki. W każdej z nich programiści popełniają błędy, bo nikt nie jest idealny. Ale każdy skupia się na swojej bibliotece i bez pomocy innych, obiektywnych programistów czy testerów nie jest w stanie odkryć wszystkich błędów jakie popełnił podczas pisania. W środowisku OpenSource jest odwrotnie. Programiści, pisząc swoje programy wykorzystują biblioteki które są wolnodostępne. Te biblioteki są współdzielone między równymi programami. Takie biblioteki czy nawet programy które wykorzystuje konkretna aplikacja, są nazywane zależnościami. Dzięki temu np. program Gimp (linuksowy odpowiednik Adobe® Photoshop™) zajmuje… 2,7 MiB!  
Każda biblioteka jest współtworzona przez wielu programistów, którzy dodają własne poprawki i ulepszenia z każdą kolejną wersja.  
Dzięki temu biblioteki takie są coraz szybsze, sprawniejsze, pozbawione błędów i bardziej funkcjonalne.

<a name="dpkg"></a>

##  dpkg 

Jak nadmieniłem – *apt*, który jest nakładką na program *dpkg* jest na tyle funkcjonalny, że praktycznie uwalnia nas od korzystania z samego *dpkg*. Jeśli zajdzie taka potrzeba – opiszę szczegółowo wykorzystanie tego programu.

<a name="apt_a_apt-get"></a>

#  apt a apt-get 

*apt* sam w sobie jest nadal w fazie rozwoju i implementacji. Równolegle rozpoczęto rozwój modułu *apt* oznaczonego *apt-get*. Nim też będziemy się zajmować, ponieważ podręcznik programu *apt* wygląda tak:

```
NAME
       apt - Advanced Package Tool

SYNOPSIS
       apt

DESCRIPTION
       APT  is  a  management system for software packages.  It is still under
       development; the snazzy front ends are not yet available.  In the mean‐
       time, please see <b>apt-get(8)</b>.

OPTIONS
       None.

FILES
       None.

SEE ALSO
       apt-cache(8), apt-get(8), apt.conf(5), sources.list(5)

```

<a name="Konfiguracja_apt.27a"></a>

##  Konfiguracja apt’a 

Konfiguracja programu odbywa się za pomocą pliku */etc/apt/sources.list* o którym wspomniałem na początku. To jedyny plik który musimy wyedytować aby zmienić konfigurację *apt*

<a name="sources.list"></a>

###  sources.list 

Na początek chciałbym przedstawić swój plik *sources.list*. Można go śmiało zapisać w katalogu */ect/apt* (pakiety dotyczą ubuntu oraz kubuntu). Do tego można użyć komendy:

`sudo mv ~/sources.list /etc/apt/sources.list<br></br>`

Z założeniem, że zapisaliśmy nowy plik o treści, która znajduje się poniżej w katalogu domowym.

```
deb <a class="external free" href="http://pl.archive.ubuntu.com/ubuntu/" rel="nofollow" title="http://pl.archive.ubuntu.com/ubuntu">http://pl.archive.ubuntu.com/ubuntu</a> dapper main restricted
deb-src <a class="external free" href="http://pl.archive.ubuntu.com/ubuntu/" rel="nofollow" title="http://pl.archive.ubuntu.com/ubuntu">http://pl.archive.ubuntu.com/ubuntu</a> dapper main restricted

deb <a class="external free" href="http://pl.archive.ubuntu.com/ubuntu/" rel="nofollow" title="http://pl.archive.ubuntu.com/ubuntu">http://pl.archive.ubuntu.com/ubuntu</a> dapper-updates main restricted
deb-src <a class="external free" href="http://pl.archive.ubuntu.com/ubuntu/" rel="nofollow" title="http://pl.archive.ubuntu.com/ubuntu">http://pl.archive.ubuntu.com/ubuntu</a> dapper-updates main restricted

deb <a class="external free" href="http://security.ubuntu.com/ubuntu/" rel="nofollow" title="http://security.ubuntu.com/ubuntu">http://security.ubuntu.com/ubuntu</a> dapper-security main restricted
deb-src <a class="external free" href="http://security.ubuntu.com/ubuntu/" rel="nofollow" title="http://security.ubuntu.com/ubuntu">http://security.ubuntu.com/ubuntu</a> dapper-security main restricted

deb <a class="external free" href="http://security.ubuntu.com/ubuntu/" rel="nofollow" title="http://security.ubuntu.com/ubuntu">http://security.ubuntu.com/ubuntu</a> dapper-security universe
deb-src <a class="external free" href="http://security.ubuntu.com/ubuntu/" rel="nofollow" title="http://security.ubuntu.com/ubuntu">http://security.ubuntu.com/ubuntu</a> dapper-security universe

deb <a class="external free" href="http://archive.ubuntu.com/ubuntu/" rel="nofollow" title="http://archive.ubuntu.com/ubuntu">http://archive.ubuntu.com/ubuntu</a> dapper universe multiverse
deb-src <a class="external free" href="http://archive.ubuntu.com/ubuntu/" rel="nofollow" title="http://archive.ubuntu.com/ubuntu">http://archive.ubuntu.com/ubuntu</a> dapper universe multiverse

deb <a class="external free" href="http://archive.ubuntu.com/ubuntu/" rel="nofollow" title="http://archive.ubuntu.com/ubuntu">http://archive.ubuntu.com/ubuntu</a> dapper-backports main restricted universe multiverse
deb-src <a class="external free" href="http://archive.ubuntu.com/ubuntu/" rel="nofollow" title="http://archive.ubuntu.com/ubuntu">http://archive.ubuntu.com/ubuntu</a> dapper-backports main restricted universe multiverse

deb <a class="external free" href="http://www.kubuntu.org/packages/kde-latest" rel="nofollow" title="http://kubuntu.org/packages/kde-latest">http://kubuntu.org/packages/kde-latest</a> dapper main
deb <a class="external free" href="http://www.kubuntu.org/packages/amarok-latest" rel="nofollow" title="http://kubuntu.org/packages/amarok-latest">http://kubuntu.org/packages/amarok-latest</a> dapper main
deb <a class="external free" href="http://www.kubuntu.org/packages/koffice-latest" rel="nofollow" title="http://kubuntu.org/packages/koffice-latest">http://kubuntu.org/packages/koffice-latest</a> dapper main
deb <a class="external free" href="http://packages.freecontrib.org/ubuntu/plf" rel="nofollow" title="http://packages.freecontrib.org/ubuntu/plf">http://packages.freecontrib.org/ubuntu/plf</a> dapper free non-free
deb-src <a class="external free" href="http://packages.freecontrib.org/ubuntu/plf" rel="nofollow" title="http://packages.freecontrib.org/ubuntu/plf">http://packages.freecontrib.org/ubuntu/plf</a> dapper free non-free

deb <a class="external free" href="http://wine.budgetdedicated.com/apt" rel="nofollow" title="http://wine.budgetdedicated.com/apt">http://wine.budgetdedicated.com/apt</a> dapper main
deb-src <a class="external free" href="http://wine.budgetdedicated.com/apt" rel="nofollow" title="http://wine.budgetdedicated.com/apt">http://wine.budgetdedicated.com/apt</a> dapper main

deb <a class="external free" href="http://xgl.compiz.info/" rel="nofollow" title="http://xgl.compiz.info/">http://xgl.compiz.info/</a> dapper main
deb-src <a class="external free" href="http://xgl.compiz.info/" rel="nofollow" title="http://xgl.compiz.info/">http://xgl.compiz.info/</a> dapper main

deb <a class="external free" href="http://www.beerorkid.com/404.html" rel="nofollow" title="http://www.beerorkid.com/compiz/">http://www.beerorkid.com/compiz/</a> dapper main

deb <a class="external free" href="http://mirror2.ubuntulinux.nl/" rel="nofollow" title="http://mirror2.ubuntulinux.nl/">http://mirror2.ubuntulinux.nl/</a> dapper-seveas all
deb <a class="external free" href="http://antesis.freecontrib.org/mirrors/ubuntu/plf/" rel="nofollow" title="http://antesis.freecontrib.org/mirrors/ubuntu/plf/">http://antesis.freecontrib.org/mirrors/ubuntu/plf/</a> dapper free non-free

deb <a class="external free" href="http://www.kadu.im/download/binary/ubuntu/repo" rel="nofollow" title="http://www.kadu.net/download/binary/ubuntu/repo">http://www.kadu.net/download/binary/ubuntu/repo</a> dapper main
deb-src <a class="external free" href="http://www.kadu.im/download/binary/ubuntu/repo" rel="nofollow" title="http://www.kadu.net/download/binary/ubuntu/repo">http://www.kadu.net/download/binary/ubuntu/repo</a> dapper main

deb <a class="external free" href="http://morgoth.free.fr/ubuntu" rel="nofollow" title="http://morgoth.free.fr/ubuntu">http://morgoth.free.fr/ubuntu</a> dapper-backports main
deb-src <a class="external free" href="http://morgoth.free.fr/ubuntu" rel="nofollow" title="http://morgoth.free.fr/ubuntu">http://morgoth.free.fr/ubuntu</a> dapper-backports main

deb <a class="external free" href="http://deb.svx.pl" rel="nofollow" title="http://deb.svx.pl">http://deb.svx.pl</a> dapper main universe multiverse
deb-src <a class="external free" href="http://deb.svx.pl" rel="nofollow" title="http://deb.svx.pl">http://deb.svx.pl</a> dapper main universe multiverse

```

Plik zamieściłem również na serwerze – jest dostępny do pobrania pod adresem [http://files.ludwikc.net/trash/linux/sources.list](http://files.ludwikc.net/trash/linux/sources.list "http://files.ludwikc.net/trash/linux/sources.list"). Więcej repozytoriów można znaleźć w [tym wątku](http://forum.ubuntu.pl/viewtopic.php?t=120&highlight=gpg+sources.list "http://forum.ubuntu.pl/viewtopic.php?t=120&highlight=gpg+sources.list") na [forum ubuntu.pl](http://ubuntu.pl/forum/ "http://forum.ubuntu.pl/").

W powyższym przykładzie podane są jedynie repozytoria oparte o protokół http. Należy jednak pamiętać, że program *apt-get* świetnie radzi sobie również z protokołami ftp czy ssh!

Wprawdzie więcej na temat tego pliku wiedzieć nam nie trzeba, ale należy się słowo komentarza. Pierwsza “kolumna” zaznacza jakiego typu jest pakiet. *deb* to paczki skompilowane, a *deb-src* to źródła tychże. Po adresie serwera repozytoriów należy koniecznie podać wersję systemu (p. niżej), a następnie sekcję poprzez sekcję należy rozumieć grupy pakietów, które są dobierane wg tabeli:

|  | **Wolne oprogramowanie** | **Zamknięte oprogramowanie** |
|---|---|---|
| **Wspierane** | *main* | *restricted* |
| **Niewspierane** | *universe* | *multiverse* |

Dzięki takiemu podziałowi możemy dokładnie wybrać pakiety z których będziemy korzystać. Przykładowo ograniczając plikowi *sources.list* dostęp do repozytoriów do sekcji main i universe mamy 100% pewność, że nasz system jest w 100% OpenSource i w 100% legalny.

Przyjęto następującą metodę podawania wersji systemu:

| Wersja | Nazwa | Tłumaczenie | Skrót |
|---|---|---|---|
| 4.10 | Warty Warthog | Piegowaty Guziec | warthog |
| 5.04 | Hoary Hedgehog | Sędziwy Jeż | horay |
| 5.10 | Breezy Badger | Serdeczny Borsuk | breezy |
| 6.06 | Dapper Drake | Wytworny Kaczor | dapper |
| 6.10 | Edgy Eft | Przebiegła Traszka | edgy |

Owy skrót jest bardzo ważny, ponieważ wraz z kolejnymi wersjami systemu mogą np. zmienić się pewne elementy systemu lub ich położenie, którego podanie jest wymagane do prawidłowego przeprowadzenia procesu instalacji.

<a name="U.C5.BCytkowanie"></a>

##  Użytkowanie 

Polecenie apt-get jest dostępne jedynie z konta roota lub dla uprawnionych użytkowników poprzez sudo. Zdecydowanie najczęściej wykorzystywanymi poleceniami programu jest komenda *install, remove* oraz *update*.

<a name="Aktualizacja"></a>

###  Aktualizacja 

Polecenie służy do aktualizacji repozytoriów, po zamianie zawartości pliku *sources.list*. . Sprawdzana jest lista repozytoriów, możliwość połączenia się z nimi oraz klucze gpg.

<a name="Instalacja"></a>

###  Instalacja 

Instalacja oprogramowania w systemie Ubuntu jest najprostszą z możliwych. Sprowadza się ona do wydania jednego polecenia:

```
apt-get install <i>nazwa_pakietu</i>
```

W ten sposób mamy dostęp do wspomnianych wyżej **dwudziestu tysięcy** pakietów.

*apt-get* za każdym razem wyświetla informację o pakietach jakie są wymagane, aktualizowane oraz sugerowane (te ostatnie nie zostaną pobrane jednak twórcy programu lub paczki zaznaczyli, że te są pomocne w użytkowaniu, choć nie są wymagane do prawidłowego funkcjonowania aplikacji).

```
root@ludwikc-desktop:/home/ludwikc# <b>apt-get install gaim</b>
Czytanie list pakietów... Gotowe
Budowanie drzewa zależności... Gotowe
Zostaną zainstalowane następujące dodatkowe pakiety:
  gaim-data libgtkspell0 liblaunchpad-integration0
Sugerowane pakiety:
  gnome-panel evolution-data-server libzephyr3
Zostaną zainstalowane następujące NOWE pakiety:
  gaim gaim-data libgtkspell0 liblaunchpad-integration0
0 aktualizowanych, 4 nowo instalowanych, 0 usuwanych i 45 nieaktualizowanych.
Konieczne pobranie 1473kB archiwów.
Po rozpakowaniu zostanie dodatkowo użyte 13,0MB miejsca na dysku.
Czy chcesz kontynuować [T/n]? <b>n</b>
Przerwane.
root@ludwikc-desktop:/home/ludwikc#
```

Na koniec podsumowania zostaje wyświetlone potwierdzenie chęci przeprowadzenia instalacji, na które trzeba odpowiedzieć klawiszem ***t*** lub ***n***. Pytanie to jest wyświetlane jednak tylko w przypadku, gdy oprócz żądanego pakietu wymagane jest pobranie zależności badź aktualizacji innych pakietów. W momencie gdy wybieramy aplikację, która takowych nie wymaga instalacja przebiega automatycznie do samego końca.

```
root@ludwikc-desktop:/home/ludwikc# apt-get install wmfishtime
Czytanie list pakietów... Gotowe
Budowanie drzewa zależności... Gotowe
Zostaną zainstalowane następujące NOWE pakiety:
  wmfishtime
0 aktualizowanych, 1 nowo instalowanych, 0 usuwanych i 45 nieaktualizowanych.
Konieczne pobranie 16,5kB archiwów.
Po rozpakowaniu zostanie dodatkowo użyte 102kB miejsca na dysku.
Pob: 1 <a class="external free" href="http://archive.ubuntu.com" rel="nofollow" title="http://archive.ubuntu.com">http://archive.ubuntu.com</a> dapper/universe wmfishtime 1:1.24-4 [16,5kB]
Pobrano 16,5kB w 5s (2941B/s)
Zaznaczenie poprzednio niezaznaczonego pakietu wmfishtime.
(Odczytywanie bazy danych ... 85526 plików i katalogów obecnie zainstalowanych.)
Rozpakowanie wmfishtime (z .../wmfishtime_1%3a1.24-4_i386.deb) ...
Konfigurowanie wmfishtime (1.24-4) ...
root@ludwikc-desktop:/home/ludwikc#
```

Od tego momentu program *wmfishtime* jest dostępny w systemie. Bardzo proszę o przyznanie racji osobom, które utrzymują, że instalacja oprogramowania pod linuksem jest **trudna** 🙂

<div class="editsection" style="float:right;margin-left:5px">[[edytuj](http://personaldevelopment.pl/?title=Zarz%C4%85dzanie_pakietami&action=edit&section=12 "Edytuj sekcję: Usuwanie")]</div><a name="Usuwanie"></a>

###  Usuwanie 

Proszę też takim osobom zaznaczyć, że odinstalowywanie jest **jeszcze trudniejsze**. Oto przykład:

```
root@ludwikc-desktop:/home/ludwikc# <b>apt-get remove wmfishtime</b>
Czytanie list pakietów... Gotowe
Budowanie drzewa zależności... Gotowe
Następujące pakiety zostaną USUNIĘTE:
  wmfishtime
0 aktualizowanych, 0 nowo instalowanych, 1 usuwanych i 45 nieaktualizowanych.
Konieczne pobranie 0B archiwów.
Po rozpakowaniu zostanie zwolnione 102kB miejsca na dysku.
Czy chcesz kontynuować [T/n]? <b>T</b>
(Odczytywanie bazy danych ... 85536 plików i katalogów obecnie zainstalowanych.)
Usuwanie wmfishtime ...
root@ludwikc-desktop:/home/ludwikc#
```

I po pakiecie…  
Ważna informacja: zależności **nie są** usuwane wraz z pakietem, nawet jeśli są wykorzystywane tylko przez usuwany pakiet! Jeśli chcemy usunąć zależności, musimy byc **pewni**, że nie są one wykorzystywane przez inne pakiety. Do usunięcia takich pakietów (a właściwie ich odnalezienia) przydaje sie narzędzie *deborphan*. Jak je znaleźć? Patrz *apt-cache* 🙂

<a name="Dodatkowe_opcje"></a>

###  Dodatkowe opcje 

Każde z poleceń ma dodatkowe opcje. np.

- ***-d*** – tylko pobranie pliku, bez instalacji

```
root@ludwikc-desktop:/home/ludwikc# <b>apt-get -d install wmfishtime</b>
Czytanie list pakietów... Gotowe
Budowanie drzewa zależności... Gotowe
Zostaną zainstalowane następujące NOWE pakiety:
  wmfishtime
0 aktualizowanych, 1 nowo instalowanych, 0 usuwanych i 45 nieaktualizowanych.
Konieczne pobranie 16,5kB archiwów.
Po rozpakowaniu zostanie dodatkowo użyte 102kB miejsca na dysku.

<i>Ukończono pobieranie w trybie samego pobierania</i>
root@ludwikc-desktop:/home/ludwikc#
```

- ***-s*** – symulacja instalacji

```
root@ludwikc-desktop:/home/ludwikc# apt-get -s install wmfishtime
Czytanie list pakietów... Gotowe
Budowanie drzewa zależności... Gotowe
Zostaną zainstalowane następujące NOWE pakiety:
  wmfishtime
0 aktualizowanych, 1 nowo instalowanych, 0 usuwanych i 45 nieaktualizowanych.
Inst wmfishtime (1:1.24-4 Ubuntu:6.06/dapper)
Conf wmfishtime (1:1.24-4 Ubuntu:6.06/dapper)
root@ludwikc-desktop:/home/ludwikc#
```

Dwie ostatnie linijki (*Inst* – instalacja, *Conf* – konfiguracja) potwierdzają, że instalacja przebiegnie bez błędów.

- ***–reinstall*** – usunięcie i ponowna instalacja pakietu znajdującego się juz w systemie.

<a name="Inne_mo.C5.BCliwo.C5.9Bci"></a>

##  Inne możliwości 

<a name="apt-cache"></a>

###  apt-cache 

Oprócz *apt-get* program apt posiada więcej wbudowanych funkcji, jaknp. bardzo przydatne *apt-cache* (czyt. *apt-kesz*), ktore na podstawie wykonanego wcześniej *apt-gaet update* pozwala na odczytywanie z pamięci takich informacji jak np. podsumowanie pakietu lub wyszukiwanie go spośród listy repozytoriów.

<a name="Informacje_o_pakiecie"></a>

####  Informacje o pakiecie 

Na przykładzie programu GRUB:

```
root@ludwikc-desktop:/home/ludwikc# <b>apt-cache show grub</b>
Package: grub
Priority: optional
Section: admin
Installed-Size: 748
Maintainer: Grub Maintainers <pkg-grub-devel@lists.alioth.debian.org>
Architecture: i386
Version: 0.97-1ubuntu9
Depends: libc6 (>= 2.3.4-1), libncurses5 (>= 5.4-5)
Suggests: grub-doc, grubconf
Filename: pool/main/g/grub/grub_0.97-1ubuntu9_i386.deb
Size: 362200
MD5sum: b331cdd615a96933db0dc34042cb0964
Description: GRand Unified Bootloader
 GRUB is a GPLed bootloader intended to unify bootloading across x86
 operating systems.  In addition to loading the Linux kernel,
 it implements the Multiboot standard, which allows for flexible loading
 of multiple boot images (needed for modular kernels such as the GNU Hurd).
Bugs: <a class="external free" href="mailto:ubuntu-users@lists.ubuntu.com" rel="nofollow" title="mailto:ubuntu-users@lists.ubuntu.com">mailto:ubuntu-users@lists.ubuntu.com</a>
Origin: Ubuntu

root@ludwikc-desktop:/home/ludwikc#
```

W kolejności wiersze oznaczają:

- nazwę pakietu
- priorytet
- sekcję
- rozmiar po zainstalowaniu
- właściciela pakietu
- architekurę pod jaką został zoptymalizowany
- wersję
- zależności
- pliki zalecane do instalacji
- ścieżkę na serwerze repozytorium
- rozmiar paczki
- sumę MD5
- opis pakietu
- adres pod którym można zgłaszać błędy
- system, pod jaki został przygotowany dany pakiet

<a name="Statystyki_repozytori.C3.B3w"></a>

####  Statystyki repozytoriów 

Pocecenie *apt-cache stats* pozwala na przejrzenie statystyk naszych repozytoriów:

```
root@ludwikc-desktop:/home/ludwikc# apt-cache stats
Liczba nazw pakietów : 24259 (970k)
  Zwykłych pakietów: 18854
  Czysto wirtualnych pakietów: 358
  Pojedynczych pakietów wirtualnych: 1047
  Mieszanych pakietów wirtualnych: 201
  Brakujących: 3799
W sumie różnych wersji: 20974 (1007k)
W sumie zależności: 149842 (4196k)
W sumie zależności wersja/plik: 22137 (354k)
W sumie mapowań zapewnień: 3543 (70,9k)
W sumie dopasowanych napisów: 174 (2246)
Sumaryczny rozmiar obszaru zależności od wersji: 679k
Sumaryczny rozmiar niewykorzystanego miejsca: 92,2k
Całkowity rozmiar: 6692k
root@ludwikc-desktop:/home/ludwikc#
```

W nawiasach podano podano liczbę tzw. pakietów wirtualnych. Ich powstanie wiązało się z tym, że dany pakiet był znany pod różnymi nazwami, więc aby uniknąć problemów z ich wyszukiwaniem postanowiono utworzyć “aliasy”, które są dzisiaj pakietami wirtualnymi.

<a name="Podsumowanie"></a>

####  Podsumowanie 

Możemy przejrzeć krótkie podsumowanie plików znajdujących się w repozytoriach. Służy do tego polecenie

```
apt-cache dump
```

(czyt. *damp*).  
***Uwaga:*** Wcześniej wyświetliliśmy ilość pakietów znajdujacych się w repozytoriach. Wykonanie polecenia *dump* może być czasochłonne, a do tego nie bedziemy w stanie wszystkoiego odczytać. W związku z tym trzy podpowiedzi:

Jeśli chcemy wyświetlać listę “stronami” (lista jest **bardzo** długa!) należy polecenie *dump* wpuścić w potok *less*

```
apt-cache dump | less
```

Zapisanie listy w pliku odbywa się poprzez polecenie

```
apt-cache dump >> mojalista.txt
```

Możemy też w dowolnym momencie przerwać wykonywanie polecenia poprzez uzycie skrótu klawiaturowego

```
<i>Ctrl+C</i>
```

(Skrót ten działa zawsze w konsoli, niezależnie od wykonywanego polecenia!)

<div class="editsection" style="float:right;margin-left:5px">[[edytuj](http://personaldevelopment.pl/?title=Zarz%C4%85dzanie_pakietami&action=edit&section=19 "Edytuj sekcję: Zależności")]</div><a name="Zale.C5.BCno.C5.9Bci_2"></a>

####  Zależności 

Sprawdzenie zależności umożliwia polecenie *depends*

```
apt-cache depends <i>nazwa pakietu</i>
```

<a name="Wyszukiwanie"></a>

####  Wyszukiwanie 

*apt-cache* ma dwie funkcje wyszukiwania. Pierwszą jest poszukiwanie wyrażenia w całości podsumowania pliku, a druga to sprawdzanie początków nazw paczek

```
apt-cache search <i>wyrażenie</i>
```

Należy jednak zwrocić uwagę, że to polecenie poszukuje ciągu znaków “*wyrażenie*” we **wszystkich** polach informacji o danym pakiecie, dlatego w komunikacie zwrotnym mogą znaleźć się paczki pozornie zupełnie z poszukiwanym ciągiem znaków nie związane. Daje nam ono jednak szanse na odnalezie programów związanych z danym tematem, np: *usenet* (czyt. *juznet*) – czyli grupami dyskusyjnymi.

```
apt-cache pkgnames <i>począt</i>
```

To polecenie wyszukuje nazwy pakietów wg ciągu znaków podanego jako argument polecenia. Przykładowe *począt* może stanowić ciąg dla wyszukiwania *początek-nazwy-pakietu* lub *początkowe-nauczanie* ale **nie** *nauczanie-początkowe*!

<a name="Aktualizacja_systemu_UbuntuLinux"></a>

##  Aktualizacja systemu UbuntuLinux 

Dzięki programowi *apt* możemy bezboleśnie, w kilku krokach przeprowadzić aktualizacje całego systemu. Sprowadza się to do wydania kolejno komend:

```
apt-get update
apt-get upgrade
apt-get dist-upgrade
```

Całość trwa jakiś czas, ponieważ z reguły potrzebne jest pobranie bardzo wielu pakietów. Mój rekord aktualizacji Ubunutu (z wersji *breezy* do *dapper*) to 10 godzin, bez używania płytki CD. Przy używaniu płyty czas ten skraca się do godziny.  
Ze wszystkim można sobie poradzić i do wszystkiego mamy wolny dostęp – możemy aktualizować system przez godzinę lub 10. Wszystko zależy od nas.  
A jak mówi dewiza jednego z linuksowych portali: ***Przywróć radość użytkowaniu komputerów. Używaj Linuksa!***

\[tags\]ubuntu, linux, apt, howto\[/tags\]