---
id: 1735
title: 'GoogleCo-op &#8211; Zbuduj własne Google'
date: '2006-10-28T03:34:58+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://blog.ludwikc.net/2006/10/28/googleco-op-zbuduj-wlasne-google/'
permalink: /googleco-op-zbuduj-wlasne-google/
tags:
    - ''
dsq_thread_id:
    - '2283168754'
views:
    - '574'
bsb_share_transient_facebook:
    - '1606064256'
bsb_share_count_facebook:
    - '0'
bsb_share_transient_linkedin:
    - '1606064256'
bsb_share_count_linkedin:
    - '0'
categories:
    - Szuflandia
format: image
---

![GoogleCo-op](http://personaldevelopment.pl/wp-content/uploads/2006/10/google_coop_sm.gif) Google Co-op to usługa, pozwalająca nie tylko na [zamieszczenie](http://services.google.com/searchcode2.html?accept=on#both) wyszukiwarki [Google](https://www.google.pl/?gfe_rd=cr&ei=RTVKVb60KNOv8weX0YGABg&gws_rd=ssl) wewnątrz własnej witryny, ale również wybór konkretnych witryn, które będą dla nas przeszukiwane.

## Coś wiecej niż “Znajdź na tej stronie”

Niemal każdy <abbr title="Content Management System">CMS</abbr> czy system blogowy ma dziś wbudowaną wyszukiwarkę. Jedne z nich są bardziej, inne mniej efektywne. Coraz częściej jednak spotyka się na [stronach](http://www.pedagog.uw.edu.pl/) czy [blogach](http://blog.konieczny.be/2006/10/20/oficjalny-blog-google-po-polsku/) wyszukiwarki Google, które pozwalają przeszukiwać zasoby całej sieci, badź tylko wybranej przez nas witryny:

<div style="text-align:center;border: 1px solid #eeeeee"><form action="http://www.google.com/search" method="GET">| [   ![Google](http://www.google.com/logos/Logo_40wht.gif)](http://www.google.com/) | <font size="-1">   Cała sieć Tylko ta witryna    </font> |
|---|---|

</form></div>To są rozwiązania znane od “lat”. Czym jest jednak [Google Co-op](https://cse.google.com/cse/)?

## Co-op: Twoje własne żródła danych

Przykład: [Planeta Google](http://planet-google.com/pl/), nad którą pieczę sprawuje [Piotr Konieczny](http://konieczny.be). “*Szukaj z Google*“. Dlaczego Google miałyby przeszukiwać całą sieć, skoro czytelnik serwisu (wiedząc, że blogi Planety są dobrane tak, by spełniały jego oczekiwania) może w prosty sposób użyć Google Co-op i sprawdzić co na dany temat piszą *mieszkańcy* planety? Dlatego właśnie w takich projektach znajdzie zastosowanie [GoogleCo-op](https://cse.google.com/cse/).

### Wybierz swoje miejsca w sieci

GoogleCo-op jest, najprościej rzecz ujmując, uszczupleniem wyników wyszukiwania do treści witryn, które samodzielnie wskażemy. Co więcej, URL patterns (opisane niżej) pozwalają nam na wybranie nie tylko adresu strony, której zawartość ma być przeszukiwana, ale również określonego wzoru wg którego będą one sortowane. Zastosowanie chociażby na przykładzie Planety Google. Po co nasza wyszukiwarka ma sprawdzać treść wszystkich wpisów [Łukasza Horodeckiego](http://www.golf-olszewka.pl/blog), skoro może szukać tylko wśród tych, które w nazwie maja string “*google*“?

### Nie ograniczaj się!

Ograniczenie wyników wyszukiwania do kilku/kilkunastu serwisów nie miałoby sensu, jeśli rozważamy użyteczność takiego rozwiązania. Wiedzą to też inżynierowie Google, którzy oddali nam do dyspozycji dwie możliwości doboru otrzymywanych wyników:

- Wyszukiwanie w sieci, ze szczególnym uwzględnieniem wskazanych przez nas witryn
- Wyszukiwanie wyłącznie pośród zdefiniowanych adresów

Dzięki temu jesteśmy w stanie dokładnie kontrolować to, co będzie zwracać wyszukiwarka. Zasoby całej sieci będą brane pod uwagę dopiero, gdy podana przez nas pula ulegnie wyczerpaniu. A zastosowanie ścisłego ograniczenia? Bardzo sensowne. Jeśli stworzymy Planetę Polskich Filharmonii, to możemy ograniczyć wyniki wyszukiwania frazy *“I Koncert skrzypcowy fis-moll op. 14 Henryka Wieniawskiego”* (polecam!) do repertuarów filharmonii z pominięciem jego recenzji.

### URL patterns

Żadna z opisanych wyżej technik nie miałaby zastosowania, gdyby nie wzorce <abbr title="Uniform Resource Locator">URL</abbr>. Poniżej fragment informacji na ten temat z [dokumentacji](http://google.com/coop/docs/cse/) produktu:

<div>| **Pattern** | **Zawiera** | **Nie zawiera** |
|---|---|---|
| www.y.com | www.y.com | y.com     www.y.com/stamps |
| www.y.com/\* | www.y.com    www.y.com/stamps | y.com |
| www.y.com/\*kites | www.y.com/kites.html    www.y.com/kites/page2.html    www.y.com/funwithkites.html | www.y.com    www.y.com/stamps |
| www.buy.com/product.asp   \*Category=Elec | www.buy.com/product.asp?   sku=2028283&amp;Category=Elec | www.buy.com    www.buy.com/stamps |
| www.y.com/\*kites\*fly | ww.y.com/kites/howto/fly.html    www.y.com/fly/howto/kites.html | www.y.com/kites/help.htm   www.y.com/help/fly.html |

</div>(Z wyraźnym zaznaczeniem, że dla definiowania adresów nie działają [wildcardy](http://www.digipedia.pl/def/449795737.html), co uniemożliwia hurtowe dodanie wszystkich subdomen danego serwisu)

W opisany wyżej sposób możemy równocześnie dodawać jak i wykluczać adresy poddawane przeszukiwaniu. Pozwala to na usunięcie tych wyników, które są bezwartościowe, choć wysoko usytuowane w rankingu Google.

### GoogleMarker, czyli jak być na bieżąco

Blogi, zarówno te wartościowe, jak i większych wartości nieprzedstawiające (z przewagą tych drugich), pojawiają się niemal co chwilę. Tak samo zmieniają się wyniki Google, czy adresy poszczególnych stron. GoogleMarker jest javascriptową zakładką, która pozwala na bieżąco dodawać i wykluczać adresy do naszych silników.

<div style="text-align: center;font-size:x-small">[![Google Marker in use](http://personaldevelopment.pl/wp-content/uploads/2006/10/marker.thumbnail.jpg)](http://personaldevelopment.pl/wp-content/uploads/2006/10/marker1.jpg "Google Marker in use")  
*Screen zapożyczony  
ze [stron dokumentacji](http://google.com/coop/docs/cse/)*</div>### Ważne opcje

#### Zarabiaj z GoogleCo-op

Konto Co-op, jest (do czego chyba jesteśmy już przyzwyczajeni) połączone z kontem [AdSense](http://adsense.google.com), na które będą automatycznie spływać fundusze za kliknięcia w reklamy, wyświetlane wśród naszych wyników.

#### Pimp your Co-op

Podobne brzmienie przybrał kiedyś [tytuł artykułu Piotra](http://blog.konieczny.be/2006/08/31/pimp-your-adsense-5-zlotych-rad/), jednak dotyczył wymienionego wyżej [AdSense](http://adsense.google.com). Skoro mówimy o personalizacji, niech będzie to personalizacja pełną parą. Teraz już nie tylko nagłówek strony czy tło pod znakiem Google jest zmienialne. Dzięki Co-op, możemy skonfigurować sposób wyświetlania wyników jeszcze dokładniej niż w AdSense, za pomocą konfiguratora [Look and Feel](http://google.com/coop/manage/cse/look)  
![Look and Fell - GoogleCo-op](http://personaldevelopment.pl/wp-content/uploads/2006/10/look_and_feel.png)

#### Audyt

Audyt z przymrużeniem oka ;). Co-op, oferuje 100 zaproszeń dla Twoich znajomych, którzy pomogą Ci w *redagowaniu* zawartości bazy URL’i. Każdą z tych propozycji możesz rozważyć i zaakceptować lub nie. Twoi znajomi również mogą korzystać z GoogleMakera.

### Tylko tyle?

Nie, ale to w zupełności wystarczy, żeby GoogleCo-op, stało się wszechobecnym narzędziem, które pozwoli na segregację treści, jakich szukają użytkownicy naszych serwisów. *Ordnung must sein!* 🙂

W następnym odcinku – GoogleFSS prosto z [GoogleLabs](http://labs.google.com/).

<ins>UPDATE:</ins> [Oficjalne ogłoszenie](http://googleblog.blogspot.com/2006/10/eureka-your-own-search-engine-has.html) na [blogu Google](http://googleblog.blogspot.com).

\[tags\]google, googlelabs, search, engines\[/tags\]