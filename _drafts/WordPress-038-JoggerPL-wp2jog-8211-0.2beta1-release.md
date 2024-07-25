---
id: 102
title: 'WordPress &#038; JoggerPL: wp2jog &#8211; 0.2beta1 release'
date: '2013-12-28T17:12:35+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://blog.ludwikc.net/?p=102'
permalink: '/?p=102'
tags:
    - ''
categories:
    - Szuflandia
---

[wp2jog](http://projects.ludwikc.net/wp2jog/). Wtyczka do [WordPressa](http://wordpress.org), pozwalająca jego użytkownikom pozostać w kontakcie ze społecznością [JoggerPL](http://jogger.pl).

### Dlaczego?

Z wielu powodów. Jogger jest zamknięty i w wielu kwestiach upośledzony (czytaj: pozbawiony wielu niezbędnych funkcjonalności). Dlaczego i jakich? Pisało już o tym parę osób, dlatego nie będę się powtarzał. Zapraszam do lektury (linki poniżej).

Społeczność zgromadzona Joggera to w znacznej mierze informatycy i ludzie, którzy mają do powiedzenia coś, co warto z uwagą przeczytać. Część z nich opuściła już ten system, często na rzecz WordPressa właśnie. Część z nich nadal się jednak wacha, ponieważ sporo osób trafia na interesujące wpisy prosto ze strony głównej Joggera, a przechodząc na inny system pozbawiłoby się kontaktu z tymi właśnie ludźmi.

Sam, od czasu do czasu napiszę coś na [swoim joggerze](http://jogger.ludwikc.net), który traktuję właśnie jako panel dyskusyjny z tą społecznością.  
Po to właśnie napisałem tą wtyczkę. Co robi? Wykorzystuje [Class.Jabber.PHP](http://cjphp.netflint.net/), aby przechwycić nowy wpis na blogu działającym pod kontrolą WordPressa i przesłać ją na adres Joggera.

Aby uniknąć dublowania wpisów (bo jaki jest sens prowadzenia dwóch blogów jednocześnie?) wp2jog dodaje do joggera wpis pod takim samym tytułem jak na WP, a w treści umieszcza link:

> Na moim <a title="http://adres-bloga.wordpress">blogu</a> pojawił się nowy wpis pt. “Tytuł\_wpisu”. <a title="http://adres-bloga.wordpress/wpis">Czytaj dalej…»</a>

Wszystko można oczywiście dostosować do swoich potrzeb w pliku `wp2jog/wp2jog.php`.

<http://project.ludwikc.net/wp2jog/downloads/wp2jog-0.2b1.tar.bz2>  
<http://project.ludwikc.net/wp2jog/downloads/wp2jog-0.2b1.zip>  
`svn co http://svn.ludwikc.net/wp2jog/branches/0.3 wp2jog-dev`  
(user: `jogger` pass: `wordpress`)

Licencja: [GPL](http://www.fsf.org/licensing/licenses/gpl.html). (Dlaczego? Przeczytaj podtytuł tego bloga).

Instrukcja obsługi:

1. Upload do katalogu `/wp-content/plugins/`
2. W opcjach (Opcje » wp2jog) należy podać swój JID, hasło oraz JID prowadzonego joggera.

To jest wersja 0.2beta1. Spełnia tylko podstawowe funkcje, opisane powyżej.

### Lista TODO

Jako, że adres strony wp2jog przekierowywany jest właśnie tutaj, dopóki nie zostanie wypuszczona stabilna i funkcjonalna wersja, poniżej znajduje się lista todo i roadmap. Funkcji, jakie dziś można zaimplementować wtyczce jest niewiele, ponieważ niewielka jest funkcjonalność samego Joggera, a dodatkowo nie zostało upublicznione żadne API systemu.

- Obsługa tematów (wkrótce)
- Dostosowywanie wpisu wysyłanego na joggera na stroni opcji
- Pobieranie JID’a z adresu joggera (nie dotyczy joggerów prowadzonych we własnej domenie)
- Opcja wyboru poziomu na jaki ma być dodawany wpis, wyświetlana w trakcie dodawania wpisu
- Wybór – czy wpis ma być dodany czy nie

O Joggerze napisali:  
<http://diary.e-gandalf.net/2006/03/05/jogger-story/>  
<http://private.hell.to/jogger-vulgaris/>  
<http://riddle.jogger.pl/id/156967>