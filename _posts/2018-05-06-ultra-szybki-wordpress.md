---
id: 6865
title: 'Jak zbudować ultra-szybki blog?'
date: '2018-05-06T19:34:26+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'https://personaldevelopment.pl/?p=6865'
permalink: /ultra-szybki-wordpress/
ampforwp_custom_content_editor:
    - ''
ampforwp_custom_content_editor_checkbox:
    - null
ampforwp-amp-on-off:
    - default
ampforwp-redirection-on-off:
    - enable
bsb_share_transient_facebook:
    - '1605673754'
bsb_share_count_facebook:
    - '24'
bsb_share_transient_linkedin:
    - '1605673755'
bsb_share_count_linkedin:
    - '0'
csco_singular_layout:
    - default
csco_page_header_type:
    - default
image: /wp-content/uploads/2018/05/lightning-199651_1920.jpg
categories:
    - 'Budowanie wizerunku'
tags:
    - technologie
    - wizerunek
    - wordpress
---

Dawno nie publikowałem na tym blogu treści pisanej – tak fizycznie, palcami na klawiaturze. Pora to zmienić.

Blog siadlak.com przeszedł gruntowny remont – szczególnie pod maską, bo od strony karoserii możesz zobaczyć tylko kosmetyczne zmiany i różnice.

Ten tekst ma na celu pokazanie z jakich narzędzi, rozwiązań i dostawców usług korzystałem, aby ten blog uruchamiał się na Twoim urządzeniu tak szybko, jak miałeś/miałaś okazję zobaczyć podczas otwierania tego tekstu.

A zatem do dzieła.

## Założenia wstępne

### 1. Poziom techniczny artykułu.

Zakładam, że ten tekst będą czytały osoby ***względnie techniczne*** – czyli nie będę rozkładał na czynniki pierwsze dlaczego klauzula *@import* w CSS będzie istotnie spowalniać szybkość Twojej platformy, ale wyjaśnię szczegółowo czym jest *TTFB* i dlaczego warto badać ten wskaźnik.

### 2. Język techniczny

Bezpośrednio z założenia nr 1 wynika założenie nr 2, czyli nie będę silił się na używanie – niejednokrotnie kuriozalnych – polskich tłumaczeń powszechnie rozumianych terminów. <acronym title="Cascade Stylesheet">CSS</acronym> to CSS, bez rozwijania do *kaskadowych arkuszy stylów.* A już na pewno nie będziemy bawić się w rozwijanie <acronym title="Content Delivery Network">CDN</acronym> do – jak podaje wikipedia “*duży, rozproszony system dostarczania treści do wielu centrów danych i punktów wymiany ruchu w Internecie.*”

Skróty, które będą się pojawiać po raz pierwszy, będą podkreślone – <acronym title="To nie jest skrót, ale przynajmniej wiesz o co chodzi">o tak</acronym>. Oznacza to, że po najechaniu nań myszą, będziesz widzieć co dany skrót oznacza, a przez to będzie Ci łatwiej go sobie potem wygooglać.

### 3. Co dalej?

Jeśli po lekturze tego mini-przewodnika będziesz mieć jakieś pytania – zapraszam do sekcji komentarzy, od tego one są i jeśli nie ja, to pewnie inni Czytelnicy będą mogli pomóc Ci rozwiązać nurtujący Cię kłopot.

Jedziemy!

---

# Po pierwsze: Hosting

Mamy obecnie dwa rodzaje usług na rynku hostingowym. Piewszą jest shared hosting, czyli taki, na który możesz wrzucić wszystko. WordPressa, Joomlę, Moodle, Magento, czy stronę w czystym HTML, napisaną w Notatniku.

### Shared hosting

Mam taki hosting na [Dreamhost](https://go.siadlak.com/dreamhost50) – korzystam z ich usług od 12 lat i spisują się doskonale, zważywszy na stosunek jakości do ceny. Od lat hosting w Dreamhost kosztuje $120/rok. Można tę cenę obniżyć o $50, jeśli zarejestrujesz się [z tego linka](https://go.siadlak.com/dreamhost50) (nie ma za co, to standardowy program Dreamhost). W tym masz nielimitowaną przestrzeń dyskową, nielimitowany transfer, nielimitowaną ilość skrzynek pocztowych i nielimitowaną ilość domen, którą możesz podpiąć. A i **darmową domenę** w cenie Do tego, po rejstracji, masz 97 dni na rezygnację z usługi więc nie ma się czego obawiać. Zdążysz wszystko przetestować i sprawdzić jak śmiga.

W pewnym momencie stwierdziłem, że zamiast mieć wszystkie serwery w datacenters rozsianych po USA, może lepiej byłoby mieć coś, do czego można dostać się krótszą drogą. Wybór padł na Zenbox, z którego byłem (jak wszyscy) bardzo zadowolony na samym początku jego działania. Niestety, z czasem jego jakość zaczęła spadać…  
i spadać… i spadać… Historię mojego rozwodu z zenbox.pl opiszę innym razem, jako case study obsługi klienta i powoływanie się na zapisy “małym druczkiem”, bo przecież “to że napisaliśmy *nielimitowany*, wcale nie oznacza, że *nielimitowany*!”, prawda? Ale to temat na inny post.

Problem w tym, że jak sobie o tym pomyślisz – jeden serwer (niezależnie od dostawcy), milion innych użytkowników, różne aplikacje, różne wymagania, różne rzeczy – to to nie jest optymalne środowisko pracy dla Twojej platformy, która ma być przecież *ultra szybka*.

Dlatego jest alternatywna opcja

### Managed (WordPress) hosting

Są firmy, które specjalizują się w hostowaniu WordPressa. To mogą być konkretne, profilowane usługi w ramach popularnych dostawców – tak jak wymieniony wyżej Dreamhost, który markuje swoją usługę jako [DreamPress](http://mbsy.co/dreamhost/27501362) (tu niestety nie mam dla Ciebie standardowej zniżki).

Są też firmy, które zajmują się wyłącznie tym i niczym więcej. Tak działa np. [wp-engine](https://wpengine.com/plans/) czy [pagely](https://pagely.com/plans-pricing/).

Oczywiście jako, że jest to usługa specjalistyczna, wszystko jest zarządzane i zoptymalizowane pod konkretne wymagania WordPressa, to nie dość, że jest mnóstwo limitów – jak ilość instancji WordPressa, przestrzeń dyskowa czy miesięczny transfer danych, to ceny takiego hostingu są odpowiednio wyższe. Dużo wyższe. I tak, te wymienione wyżej oferują podstawowe pakiety za:

- Dreamhost: ponad $200/rok
- WP-Engine: $420/rok
- Pagely: $300/…miesiąc!

Więc ceny mówią same za siebie. Ale tak jak ustaliliśmy wcześniej – dostajemy platformę, która zbudowana jest w konkretnym celu, zamiast być *one-size, uni-sex,* czyli wszystko na jedno kopyto.

[![](https://personaldevelopment.pl/wp-content/uploads/2018/05/aff-angrybytes-e1525630022333.png)](https://go.siadlak.com/hosting-wordpress)No to co wybrałem? Ano żadne z powyższych. [Krzysiek Kotkowicz](https://twitter.com/lancaster) prowadzi firmę [AngryBytes](https://go.siadlak.com/hosting-wordpress), gdzie zajmuje się administrowaniem serwerami, ale również… tak! [Hostowaniem WordPressa](https://go.siadlak.com/hosting-wordpress)!

Ponieważ hostuje się u niego [kilku](http://opydo.pl) [naprawdę](http://busemprzezswiat.pl) [lubianych](http://amalenstwo.pl) przeze mnie blogerów, postanowiłem dołączyć do tego zacnego grona.

A, ważne: w AngryBytes zarządzany hosting **kosztuje raptem $50/rok** ([199zł](https://go.siadlak.com/hosting-wordpress)) a efekty – jak widać na załączonym obrazku. Mniam!

<div class="content-block block-bg block-bg-inverse block-border-all" style="text-align: center;"><span style="color: #ffffff;"><span style="text-decoration: underline;">UPDATE:</span> zaraz po opublikowaniu tego wpisu Szef Wszystkich Szefów w AngryBytes przygotował kod na **wszystkie pakiety zarządzanego WordPressa:**</span>

<span style="color: #ffffff;">-10% z kodem</span> <span style="color: #053355;">**ODLUDWIKA** </span>

</div><div>(Komentarz do powyższej aktualizacji: to jest obsługa klienta, nie? :))) )</div># Po drugie: CDN

Problem z hostingiem – nawet super szybkim i zlokalizowanym blisko nas – jest taki, że to jest tylko jeden serwer. I o ile nowe treści – pisane przez nas teksty, dodawane przez Czytelników komentarze – powinny być z niego serwowane, o tyle zdjęcia, stałe elementy layoutu, ikonki, emotki, skrypty, etc – to zajmuje strasznie dużo czasu i transferu.

A użytkownik, który musi czekać na załadowanie się strony to nie jest zadowolony użytkownik.

Dlatego wymyślono CDN – Content Delivery Network, czyli w największym uogólnieniu sieć serwerów, która będzie dostarczać statyczne treści, z których składa się Twój blog. Co więcej, jako, że jest to *sieć*, to te serwery są rozsiane po świecie i dlatego bardzo szybko prześlą te obrazki, skrypty, ikonki prosto do przeglądarki Czytelnika.

Najpopularniejszym rozwiązaniem tego typu jest [CloudFlare](https://www.cloudflare.com/), które pewnie zdarzyło Ci się już kiedyś gdzieś widzieć. Ja sam korzystam z [KeyCDN](https://go.siadlak.com/keycdn) ze względu na dużo korzystniejszy (jak na moje potrzeby) cennik i ekstremalną łatwość w konfiguracji. **Całość zajęła mi z 15 minut**, w tym zaparzenie sobie świeżej kawy z niezmielonych wcześniej ziaren.

Poważnie, to jest temat, którego (mam wrażenie) wielu samodzielnych blogerów się boi a całość sprowadza się do:

1. Rejestracji [z tego linka](https://go.siadlak.com/keycdn) (dostaniesz z niego [250GB](https://go.siadlak.com/keycdn) bezpłatnego ruchu do przetestowania usługi)[![](https://personaldevelopment.pl/wp-content/uploads/2018/05/aff-keycdn-e1525630053954.png)](https://go.siadlak.com/keycdn)
2. Wybraniu swojej nazwy
3. Zainstalowaniu wtyczki [*CDN Enabler*](https://wordpress.org/plugins/cdn-enabler/)
4. Podaniu w niej swojej i klucza dostępu
5. Voilà, nie ma nawet punktu piątego!

Czyli mamy już szybki hosting + CDN, który będzie dostarczał to co statyczne. Tylko co jest statyczne?

# Po trzecie: Minifikacja

Uwielbiam to słowo. Nie wiem czemu, ale po prostu jest… nie mam innego określenia niż to, z którego nader często korzysta [moja małżonka](http://siadlak.ae): *słodziaszne*!

Żarty na bok. Jeśli masz te statyczne treści, to z reguły jest ich od groma. Czyli developer piszący theme/template/layout (zwał jak zwał) Twojego WordPressa, użył kilku plików CSS, każdy z pluginów powołuje się pewnie na jakąś bibliotekę JS, a co za tym idzie cały proces wydłuża się w nieskończoność.

Minifikacja kodu polega na tym, aby pozbyć się redundantnych, zbędnych linii kodu. Nie tylko tych, które się powtarzają, ale też absolutnie wszystkich spacji, tabulatorów itp. A najlepiej, zamiast mieć to wszystko w pięćdziesięciu plikach, zróbmy z tego jeden plik. Wiadomo – ściągnięcie jednego większego będzie łatwiejsze dla przeglądarki, niż ściągnięcie 50 mikroskopijnych pliczków, z których połowa jest do niczego.

Tutaj również mamy różne wtyczki – najintensywniej testowałem dwie: [Fast Velocity Minify](https://wordpress.org/plugins/fast-velocity-minify/) i [Autooptimize](https://wordpress.org/plugins/autoptimize). Finalnie wybrałem tę drugą, bo lepiej współpracuje z kolejnym punktem programu.

***Protip***: Wyszukiwarki cenią sobie kolejność w jakiej serwowane są jej treści. Warto więc podpytać developera lub jakiegoś eksperta, którego mamy pod ręką aby przygotował nam tzw *Critical CSS* czyli te najbardziej niezbędne zapisy stylu naszej strony, które pozwolą na uzyskanie czytelności zanim załaduje się wszystko inne. To temat nieco bardziej zaawansowany – nieszczególnie trudny w pojęciu, ale wymagający osobnego tekstu, żeby tutaj się nie rozdrabniać – jeśli chcesz, żebym to opisał – daj znać w komentarzach na dole.

# Po czwarte: Cache

Ogólnie jest tak, że mamy silnik napisany w PHP. Otwarcie strony powoduje zaciągniecie danych z bazy MySQL. Magia serwera się dzieje, procesory szaleją, a WordPress spina treść Twoich artykułów, ze zdjęciami, które do niego uploadowałeś, z elementami menu, które tak skrzętnie poukładałaś i w efekcie wypluwa gotową stronę.

Czyli jakby to rozpisać na kroki, to mamy ich :

1. \[Ty, do swojej przeglądarki\] Poproszę o stronę https://personaldevelopment.pl
2. \[Serwer AngryBytes\]: Już przygotowuję, czekaj.
3. \[Ty\]: Czekam
4. \[Serwer AngryBytes\]: OK, trzymaj
5. \[Ty\]: OK, ściągam

Niestety, ten trzeci krok jest dla Czytelnika najbardziej frustrujący, bo w zależności od złożoności Twojej strony i wydajności serwera (który z reguły nie spodziewa się, że ktoś go zapyta o przygotowanie jakiejś strony, bo po co), może on trwać długo.

Bardzo długo.

Zobacz:

![](https://personaldevelopment.pl/wp-content/uploads/2018/05/ttfb-1-800x397.png)

Ten wskaźnik (nazywany <acronym title="Time To First Byte">TTFB</acronym>, czyli *czasem do pierwszego bajta danych*) mówi o tym jak długo serwerowi zajmuje złożenie wszystkiego *do kupy* i wysłanie sensownej treści do Twojej przeglądarki. To zależy od wielu czynników – od tego ile masz treści na stronie, ile obrazków, ile różnych widgetów, karuzeli zdjęć z instagrama, etc.

A co by było gdybyśmy mogli powiedzieć WordPressowi *“hej ziomek, te artykuły są już napisane i opublikowane, weź mi je przygotuj w formie gotowej dla klienta, zebyś nie musiał ich montować od zera za każdym razem, co?”*

No i jak tak powiemy, to dzieje się magia, bo serwer jest przygotowany na Twoją żądzę czytania tekstów z bloga.

Jest oczywiście mnóstwo wtyczek do tego ([WP Super Cache](https://wordpress.org/plugins/wp-super-cache/), [Fastest Cache](https://wordpress.org/plugins/wp-fastest-cache/), etc). Ja wybrałem [Cache Enabler,](https://wordpress.org/plugins/cache-enabler/) bo zamiast tworzyć cały ten cache lokalnie, wrzuca go od razu na [naszego CDNa](https://go.siadlak.com/keycdn).

Efekt? o taki:

![](https://personaldevelopment.pl/wp-content/uploads/2018/05/ttfb-ok-800x268.png)

Całkowity czas oczekiwania na odpowiedź strony spadł z prawie 2,70 sekundy do 0,06 sekundy, czyli <span style="text-decoration: underline;">o **98% krócej!!!**</span>

# Po piąte: Test, test, test

Jest kilka narzędzi, sprawdzających techniczną jakość naszej strony:

<figure aria-describedby="caption-attachment-6870" class="wp-caption alignright" id="attachment_6870" style="width: 259px">![PageSpeed Insights dla siadlak.com](https://personaldevelopment.pl/wp-content/uploads/2018/05/pagespeed-99-e1525629511582.png)<figcaption class="wp-caption-text" id="caption-attachment-6870">PageSpeed Insights dla siadlak.com</figcaption></figure>Jest googlowy [PageSpeed Insight](https://developers.google.com/speed/pagespeed/insights/).

Jest [Pingdom Tools,](https://tools.pingdom.com/) z którego pochodzą screeny w poprzedniej sekcji.

Jest [Webpage Test](https://www.webpagetest.org/):

<figure aria-describedby="caption-attachment-6871" class="wp-caption alignleft" id="attachment_6871" style="width: 335px">![Webpage Test dla siadlak.com](https://personaldevelopment.pl/wp-content/uploads/2018/05/webpagetest.png)<figcaption class="wp-caption-text" id="caption-attachment-6871">Webpage Test dla siadlak.com</figcaption></figure>Moim ulubionym jest jednak [GTMetrix](https://gtmetrix.com/), który zbiera to wszystko w całość i pozwala wyświetlić na jednej stronie – z różnych miejsc na świecie z różnych przeglądarek na różnych systemach operacyjnych:

![](https://personaldevelopment.pl/wp-content/uploads/2018/05/gtmetrix-ludwikc-1160x533.png)

# Po szóste: dla kogo to robisz?

Na sam koniec, kiedy wiesz już doskonale jak sprawić, aby Twoja platforma była szybsza i łatwiejsza w odbiorze niż 90% wszystkich stron w internecie, chciałbym zostawić Cię z jedną myślą:

Wskaźniki wskaźnikami. Psychologia użytkownika internetu – owszem, jest ważna. Ale jeśli będziesz serwować świetną treść, to nawet jeśli nie będzie ona hostowana na najlepszej, najszybszej i najczytelniejszej platformie świata to i tak będzie OK. Bo słowa *“dobra treść obroni się sama“,* nie są puste.

Może powinienem to napisać na samym początku, ale założyłem, że masz świetną treść i wartość, z której mogą czerpać Twoi Czytelnicy, Widzowie i Słuchacze. I dlatego tu jesteś. Zostawię Cię z przykładem trzech fenomenalnych ludzi – blogerów, vlogerów, podcasterów, którzy mają fantastyczne wyniki biznesowe i brandingowe, ich strony są odwiedzane przez tysiące, dziesiątki bądź setki tysięcy użytkowników miesięcznie **mimo**, że ich platformy nie są doskonałe:

Mirek Burnejko i jego [trzypoziomy.pl](http://trzypoziomy.pl):

<figure aria-describedby="caption-attachment-6875" class="wp-caption alignnone" id="attachment_6875" style="width: 400px">![trzypoziomy.pl](https://personaldevelopment.pl/wp-content/uploads/2018/05/gtmetrix-miroburn-e1525631136569.png)<figcaption class="wp-caption-text" id="caption-attachment-6875">trzypoziomy.pl</figcaption></figure>Michał Szafrański i jego [finansowyninja.pl](http://finansowyninja.pl):

<figure aria-describedby="caption-attachment-6873" class="wp-caption alignnone" id="attachment_6873" style="width: 400px">![finansowyninja.pl](https://personaldevelopment.pl/wp-content/uploads/2018/05/2018-05-06_16-29-43-e1525631059788.png)<figcaption class="wp-caption-text" id="caption-attachment-6873">finansowyninja.pl</figcaption></figure>Bartek Popiel i jego [liczysiewynik.pl](http://liczysiewynik.pl):

<figure aria-describedby="caption-attachment-6874" class="wp-caption alignnone" id="attachment_6874" style="width: 400px">![liczysiewynik.pl](https://personaldevelopment.pl/wp-content/uploads/2018/05/gtmetrix-bartekpopiel-e1525631088418.png)<figcaption class="wp-caption-text" id="caption-attachment-6874">liczysiewynik.pl</figcaption></figure>Powyższe przykłady wskazują jednoznacznie: dobry kontent obroni się sam. Choćby nie wiem co!