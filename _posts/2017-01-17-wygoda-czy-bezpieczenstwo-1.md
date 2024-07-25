---
id: 5554
title: 'Jak (łatwo) wykraść Twoje dane z Google Chrome?'
date: '2017-01-17T13:42:52+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://siadlak.angrybytes.pl/?p=5554'
permalink: /wygoda-czy-bezpieczenstwo-1/
slide_template:
    - default
csco_post_featured:
    - ''
csco_singular_layout_page:
    - default
csco_featured_image_type:
    - default
views:
    - '936'
dsq_thread_id:
    - '5470088661'
bsb_share_transient_facebook:
    - '1605757026'
bsb_share_count_facebook:
    - '0'
bsb_share_transient_linkedin:
    - '1605757026'
bsb_share_count_linkedin:
    - '0'
image: /wp-content/uploads/2017/01/devastation-1848976_1920-1.jpg
categories:
    - 'Prywatność w Sieci'
tags:
    - bezpieczeństwo
    - rozwiązania
    - technologie
---

Dziś będzie nieco bardziej technicznie. Krótko i treściwie, bo rzecz dotyczy Twojego bezpieczeństwa. A dokładnie Twojej prywatności. A już zupełnie dokładnie Twojego adresu zamieszkania i numeru karty kredytowej.

\[alert type=”info\]Ten tekst otwiera serię publikacji o podstawach bezpieczeństwa IT. Te teksty generalnie skierowane są do osób niezwiązanych z branżą IT, ale ceniących sobie swoją prywatność i bezpieczeństwo. Jeśli chcesz otrzymywać powiadomienia o kolejnych częściach – [kliknij tutaj](http://personaldevelopment.pl/powiadomienia-o-nowych-publikacjach/). \[/alert\]

## Wygoda

Nowoczesne przeglądarki mają bardzo wygodną funkcję autouzupełniania adresów i zapamiętywania haseł. O hasłach pewnie jeszcze porozmawiamy, ale dziś interesuje mnie to, żeby **wiedzieć gdzie dokładnie mieszkasz**. Nawet jeśli wszystko co robię to pytam Cię o imię i email, czyli podstawowe – nieszczególnie tajne – dane, które podajesz przy subskrypcji [każdego newslettera](http://personaldevelopment.pl/powiadomienia-o-nowych-publikacjach/).

<figure aria-describedby="caption-attachment-5556" class="wp-caption alignright" id="attachment_5556" style="width: 300px">![](http://personaldevelopment.pl/wp-content/uploads/2017/01/autofill-1-stas-1-300x169.png)<figcaption class="wp-caption-text" id="caption-attachment-5556">Źródło: Google Analytics</figcaption></figure>Skoncentrujemy się tutaj na przeglądarce Chrome, z dwóch powodów. To jest **moja ulubiona przeglądarka** – dlatego opublikowałem już dwa teksty o wtyczkach rozszerzających jej możliwości: [5 najważniejszych wtyczek do Google Chrome](http://personaldevelopment.pl/5-najwazniejszych-wtyczek-google-chrome/) oraz [sequel tego artykułu](http://personaldevelopment.pl/5-kolejnych-najwazniejszych-wtyczek-google-chrome/). Istnieje też ponad pięćdziesięciopięcioprocentowe prawdopodobieństwo, że jest to też **Twoja ulubiona przeglądarka**. A to dlatego, że ponad 55% Czytelników siadlak.com używa właśnie Chrome odwiedzając tę stronę.

Wymieniony tutaj Google Chrome jak każdy z jej konkurentów oferuje funkcję zapamiętywania adresów. Ta funkcja uaktywnia się podczas wypełniania pierwszego formularza, w którym podajesz adres. Na przykład składając zamówienie w sklepie internetowym z dostawą do domu. Chrome zapamiętuje Twoje dane i trzyma je w swoich ustawieniach. O tak:

 ![](http://personaldevelopment.pl/wp-content/uploads/2017/01/autofill-1_new1-1-1.png)

Co więcej, jeśli robisz zakupy wybierając kartę płatniczą jako formę płatności, Twoja przeglądarka będzie chciała ułatwić Ci życie i numer karty również zapamięta:  
![](http://personaldevelopment.pl/wp-content/uploads/2017/01/autofill-1_new2-1-1.png)

## Bezpieczeństwo

Nie byłoby w tym nic szczególnego, gdyby nie fakt, że w bardzo prosty sposób można te dane ukraść. Fiński programista Viljami Kuosmanen [opublikował na swoim GitHubie](https://github.com/anttiviljami/browser-autofill-phishing) (repozytorium projektów programistycznych) prosty skrypt, który udowadnia niebezpieczeństwo korzystania z tej funkcji przeglądarki.

Skrypt jest niczym innym jak formularzem, który wypełniony przez użytkownika funkcją autouzupełniania, wpisuje **w widoczne pola** Twoje *imię* i *adres email*, ale posiada również pola ukryte – niewidoczne dla użytkownika, ale czytelne dla skryptu i **autouzupełniane przez przeglądarkę!**

Wygląda to dokładnie tak:

![](http://personaldevelopment.pl/wp-content/uploads/2017/01/autofill-1-demo-1-1.gif)

Jak widać powyżej, mimo tego, że użytkownik pozornie “*auto-uzupełnił*” **tylko** pola Imię i Email, to skrypt przechwycił **wszystkie** dane, które były wcześniej zapamiętane w przeglądarce, czyli

- Nazwa firmy, w której pracuje użytkownik
- Adres korespondencyjny – ulica **z numerem domu i mieszkania**(!), kod pocztowy, miasto, kraj
- Numer telefonu komórkowego

A nie przypominam sobie przecież, żeby ten formularz mówił, że będzie takie dane przechwytywał…

## Jak się chronić?

Zupełnie łatwo. Przejdź do ustawień Google Chrome wpisując <chrome://settings> w pasku adresu przeglądarki, przejdź do sekcji *Ustawienia ⇒ Hasła i formularze*  po czym **odznacz** opcję “Włącz funkcję autouzupełniania, aby wypełniać formularze jednym kliknięciem.”

![](http://personaldevelopment.pl/wp-content/uploads/2017/01/autofill-10-10-1-1.png)

Dla pewności, możesz wejść jeszcze w ustawienia i samego autouzupełniania i skasować wszystkie wartości, jakie dotychczas zapamiętała Twoja przeglądarka.  
![](http://personaldevelopment.pl/wp-content/uploads/2017/01/autofill-13-1-1.png)

## Wniosek?

Zasada jest prosta:

> Przyjmij, że **im <span style="text-decoration: underline;">wygodniejsze</span> jest rozwiązanie,** tym bardziej prawdopodobne jest, że **jest <span style="text-decoration: underline;">mało bezpieczne</span>.**

W następnej części porozmawiamy jednak o takim rozwiązaniu, które daje wygodę zapamiętywania haseł, a jednocześnie jest praktycznie nie-do-złamania.