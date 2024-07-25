---
id: 1733
title: 'Importuj załączniki GMail do GoogleDocs!'
date: '2006-10-23T01:02:26+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://blog.ludwikc.net/2006/10/23/importuj-zalaczniki-gmail-do-googledocs/'
permalink: /importuj-zalaczniki-gmail-do-googledocs/
tags:
    - ''
dsq_thread_id:
    - '2317660661'
views:
    - '520'
bsb_share_transient_facebook:
    - '1605989869'
bsb_share_count_facebook:
    - '0'
bsb_share_transient_linkedin:
    - '1605989869'
bsb_share_count_linkedin:
    - '0'
categories:
    - Szuflandia
format: image
---

![GoogleDocs](http://personaldevelopment.pl/wp-content/uploads/2006/10/googledocs11.png)Taki tytuł nosi [ostatni wpis](http://googlesystem.blogspot.com/2006/10/import-gmail-attachments-into-google.html) ma blogu [<abbr title="Google Operating System">GoogleOS</abbr>](http://googlesystem.blogspot.com/). Niestety. Import jako taki nie został dotąd wprowadzony, ale dzięki nowej funkcji możemy go sami “*zaimplementować*“. Dla mnie, wprowadzenie obsługi eksportu dokumentów do GoogleDocs powinno wyglądać tak (stąd opinia, że *nie został wprowadzony*):

![Export Google Docs](http://personaldevelopment.pl/wp-content/uploads/2006/10/gdocs.png)

## Nowa skrzynka na dokumenty

Google przygotowało dla każdego użytkownika [Gmail](http://gmail.com)/[GoogleDocs](https://docs.google.com/) dodatkową [skrzynkę pocztową](https://docs.google.com/?action=updoc) w której możemy gromadzić dokumenty. A właściwie nie gromadzić, ale bezpośrednio wstawiać je do naszego GoogleDocs.

## Eksport dotychczasowych załączników

![Google Search]()Możemy przesłać do GoogleDocs załączniki z poczty która juz znajduje się w naszej skrzynce. Wystarczy wyszukać takie właśnie przesyłki (jak na obrazku, lub po prostu – zapytaniem <kbd>(odt OR txt OR doc OR sxw OR rft) has:attachment </kbd>), a potem wybrane przesłać na [wskazany adres](https://docs.google.com/?action=updoc).

## Filtrowanie nowych załączników

O wiele łatwiejsze jest natomiast stworzenie dodatkowego filtra, który zautomatyzuje dodawanie nowych dokumentów do teczki GoogleDocs. Zasada działania jest identyczna, jak w przypadku powyżej. Filtr dla wiadomości zawierających <kbd>odt OR txt OR doc OR sxw OR rft</kbd> i załącznik. Potem forwardowanie wiadomości na [ten adres](https://docs.google.com/?action=updoc) i jesteśmy w domu. Prawie…

## Problem na dzień dobry

Instrukcja jest prosta. Sęk w tym, że nie działa. Wysłanie przesyłki, sformatowanej html’em bez przeszkód dodaje nam nowy dokument w GoogleDocs. Dostajemy też potwierdzającego maila z bezpośrednim linkiem do nowoutworzonego dokumentu (“*Just <abbr title="For Your Information">FYI</abbr>*.”). Jednak każde wysłanie załącznika (w tym po ustawieniu filtra) jest bezskuteczne. Proof:  
![GoogleDocs Error](http://personaldevelopment.pl/wp-content/uploads/2006/10/error.png)  
Wydaje mi się, że <del>oficjalne ogłoszenia</del><sup>\*</sup> wiarygodne ogłoszenia nie powinny dopuszczać się takich błędów. Za taki właśnie serwis jest postrzegany [GoogleOS](http://googlesystem.blogspot.com/). Wszystkie opisane tutaj funkcjonalności zostaną wprowadzone wkrótce, wobec czego pozostaje nam jedynie cieszyć się możliwością wysyłania dokumentów do GoogleDocs jako maili.

---

<sup>\*</sup> – Na dole strony znajduje się wyraźny disclaimer: > [Google Operating System](http://googlesystem.blogspot.com/) is a blog created by Ionut Alex. Chitu and **it’s not affiliated** with [Google Inc](https://www.google.pl/?gfe_rd=cr&ei=FzVKVZ2AMNCv8wfEjICYBw&gws_rd=ssl).

\[tags\]google, gmail, googledocs, google operating system\[/tags\]