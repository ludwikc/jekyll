---
id: 5876
title: 'Wkurzający bug w Evernote'
date: '2017-04-27T09:10:41+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://siadlak.angrybytes.pl/?p=5876'
permalink: /wkurzajacy-bug-w-evernote/
slide_template:
    - default
views:
    - '339'
csco_post_featured:
    - ''
csco_singular_layout_page:
    - default
csco_featured_image_type:
    - default
dsq_thread_id:
    - '5763990443'
bsb_share_transient_facebook:
    - '1605598030'
bsb_share_count_facebook:
    - '0'
bsb_share_transient_linkedin:
    - '1605598030'
bsb_share_count_linkedin:
    - '0'
image: /wp-content/uploads/2017/04/weevil-564503_1920-1.jpg
categories:
    - Evernote
tags:
    - technologie
---

Jak na ECC przystało, aktualizuję Evernote przy każdej możliwej okazji – również do wersji *beta*, które mają to do siebie, że nie zawsze działają perfekcyjnie.

Ostatnia aktualizacja była jednak wersją finalną i publiczną. [Evernote w wersji 6.5](https://discussion.evernote.com/topic/105063-evernote-for-windows-65-ga-released/) m.in. przyspiesza synchronizację notatek pomiędzy urządzeniami.

Niestety, ta nowa funkcja powoduję koszmarnie irytujące zachowanie aplikacji dla Windows. Mianowicie – jeśli piszesz notatkę, w momencie kiedy w tle uruchamia się proces tej *przyspieszonej* synchronizacji, kursor tekstu przeskakuje z właściwej notatki do… pola tytułu.

W efekcie – kontynuujemy pisanie nie tam gdzie trzeba!

Evernote oczywiście wie już o tym problemie i pracują nad rozwiązaniem, natomiast ja spieszę z podpowiedzią jak sobie z tym sprawnie poradzić bez uciekania się do cofania wersji czy poddawania frustracji 🙂

![](http://personaldevelopment.pl/wp-content/uploads/2017/04/EN-tools-options-1-1.png)Otóż, w opcjach Evernote (*Tools -&gt; Options*) należy zmienić zachowanie Evernote w momencie otwierania nowej notatki. Domyślnie, aplikacja umieszcza kursor w polu tytułu i dokładnie to dzieje się, kiedy następuje proces synchronizacji: Evernote *myśli*, że pracujemy nad *nową* notatką (sugerując się datą ostatniej modyfikacji).

![](http://personaldevelopment.pl/wp-content/uploads/2017/04/EN-options-focus-1-1.png)

Odznaczenie tego pola przyniesie ze sobą dwie konsekwencje

1. podczas tworzenia nowej notatki nie trzeba wpisywać najpierw tytułu aby dopiero później przechodzić do jej właściwej treści
2. synchronizacja w tle nie będzie już doskwierać

Oczywiście jest to *bug*, więc programiści Evernote z pewnością rozwiążą tę kwestię przy kolejnej aktualizacji. To tymczasowe rozwiązanie jest jednak skuteczne i znacząco ogranicza ilość wulgaryzmów kierowanych pod adresem aplikacji, kiedy patrząc na klawiaturę nie zorientujesz się, że połowa Twojej notatki niespodziewanie znalazła się w jej tytule.