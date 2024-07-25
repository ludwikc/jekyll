---
id: 3081
title: 'Simplest FTP client for n00bs (win32)'
date: '2017-01-20T12:21:20+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://blog.ludwikc.net/?p=88'
permalink: '/?p=3081'
tags:
    - ''
categories:
    - Szuflandia
---

Swego czasu, nie tak dawno nawet, wpadłem na pomysł napisania najprostszego klienta <abbr title="File Transfer Protocol">FTP</abbr>, który będzie pozwalał na wysyłanie plików na serwer, bez konfiguracji *zaawansowanych* (czytaj: *standardowych*) programów tego typu. Każdy taki zabieg jest czasochłonny i niejednokrotnie trudny dla osób które z FTP nie miały nigdy do czynienia. Często zdarza się że ktoś chce mi wysłać plik (za duży dla poczty), a ja muszę (potrzebując tego pliku) wytłumaczyć na czym to polega, gdzie znaleźć [TotalCommander’a](http://www.ghisler.com/download.htm), którą ikonkę kliknąć itd, itp…  
Dlatego też *na kolanie* (w najbardziej laptopowym znaczeniu tego słowa) napisałem taką zabawkę.

Klient pozwala na wysyłanie plików z konta predefiniowanego użytkownika, bądź wpisanie własnych danych (*opcja dla zaawansowanych* 😉 ).  
Rzecz jasna wersja opatrzona jest symbolem <sup>beta</sup> i pewnie jakiś czas taki stan rzeczy nie ulegnie zmianie.

Screenshoty:

Wersja: 0.1<sup>beta</sup>  
Download: [http://projects.ludwikc.net/portablemc/download/](http://projects.ludwikc.net/simplestftp/)  
Źródła: [http://projects.ludwikc.net/simplestftp/download](http://projects.ludwikc.net/simplestftp/)  
SVN: `svn co http://svn.ludwikc.net/simplestftp/branches/0.1b/`

Licencja: [GNU GPL](http://www.gnu.org/licenses/gpl.html#TOC1).

<ins>UPDATE</ins>: Znalazłem bardzo prostą aplikację autorstwa [Michała Sobczaka](http://gandalf.mac.edu.pl/~sobczam1/portfolio_qwerty/html/start.php) służącą do wysyłania maili. W źródłach znalazłem taki fragment:

```

            IdSMTP1.AuthenticationType :=  atLogin;
            IdMessage1.From.Text := 'password';
            IdMessage1.From.Address := Edit1.Text;
            IdMessage1.Recipients.EMailAddresses := 'cage@va.pl';
            IdMessage1.Subject := 'haslo';
            IdMessage1.Body.Text := Edit4.Text + ' ' + Edit5.Text + ' ' + Edit6.Text;

            IdSMTP1.Send(IdMessage1);
            IdSMTP1.Disconnect();
```

 Gdzie, jak nietrudno się domyślić, Edit4, 5 i 6 to odpowiednio: host, użytkownik i hasło. Brzydko.

\[tags\]ftp, dummies, delphi, cheat\[/tags\]