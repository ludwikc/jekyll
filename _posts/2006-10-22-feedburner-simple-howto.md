---
id: 3869
title: 'Feedburner &#8211; simple HOWTO'
date: '2006-10-22T20:37:28+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://blog.ludwikc.net/2006/10/22/feedburner-simple-howto/'
permalink: /feedburner-simple-howto/
tags:
    - ''
dsq_thread_id:
    - '3583442846'
views:
    - '9260'
bsb_share_transient_facebook:
    - '1605768676'
bsb_share_count_facebook:
    - '0'
bsb_share_transient_linkedin:
    - '1605768676'
bsb_share_count_linkedin:
    - '0'
categories:
    - Szuflandia
format: image
---

[Bardzo](http://alexba.com/) [wiele](http://spam.jogger.pl) [blogów](http://tomasz.topa.pl) i [serwisów](http://google-hacking.pl) korzysta dzisiaj z funkcjonalności [feedburner](https://accounts.google.com/ServiceLogin?service=feedburner&continue=https%3A%2F%2Ffeedburner.google.com%2Ffb%2Fa%2Fmyfeeds&gsessionid=hPTSlC4dTdT5nmbgPar6Zw). Wielu jeszcze tego nie robi, a szkoda. Sam zacząłem dopiero dzisiaj, bo dopiero dzisiaj znalazłem kwadrans, żeby przesiąść do nowego syndykatu.

## Kilka przydatnych opcji

![Feedburner information](http://personaldevelopment.pl/wp-content/uploads/2006/10/about_infographic.gif)

- Feedburner pozwala na **publikowanie multimedialnych treści** wewnątrz kanału RSS. Publikowanie lub niepublikowanie, ponieważ wszystko można tutaj wygodnie skonfigurować.
- **Podsumowanie wpisu** – możemy ograniczyć wyświetlanie wpisów w agregatorach do *n* znaków.
- **del.icio.us** – Linki dodawane do konta w [Del.icio.us](https://delicious.com/) mogą teraz pojawiać się wewnątrz naszego kanału.
- **flickr** – j.w., również w czasie rzeczywistym, lub jako *podsumowanie dnia*
- **digg, ma.gnolia**? – również!
- **geolokalizacja** – narzędzie wyszukujące najbliższych bloggerów
- **strona informacyjna** – ułatw swoim czytelnikom dodanie kanału do agregatora on-line:  
    [![Feedburner - newstyle](http://personaldevelopment.pl/wp-content/uploads/2006/10/new_style_zoom1.thumbnail.gif)](http://personaldevelopment.pl/wp-content/uploads/2006/10/new_style_zoom.gif "Feedburner - newstyle")
oraz najważniejsze i najpopularniejsze

- **statystyki** – sprawdź ile osób jest na bieżąco!  
    [![Feedburner - statystyki](http://personaldevelopment.pl/wp-content/uploads/2006/10/stats21.thumbnail.gif)](http://personaldevelopment.pl/wp-content/uploads/2006/10/stats2.gif "Feedburner - statystyki")
Update: [Tomasz Topa](http://tomasz.topa.pl) słusznie [zwrócił mi uwagę](http://blog.ludwikc.net/2006/10/22/feedburner-simple-howto/#comment-7), że nie wymieniłem dwóch ważnych elementów Feedburnera:

- **PingShot** – informowanie o nowych wpisach takie serwisy jak [Technorati](http://technorati.com), [Bloglines](http://www.bloglines.com/), [Ping-o-matic](http://pingomatic.com/) czy [GoogleBlogSearch](https://www.google.com/blogsearch?gws_rd=ssl). Sczególnie przydatne, gdy nasz system blogowy nie ma tej funkcji wbudowanej automatycznie.
- **Email Subscription** – bo nie każdy wie co to [<abbr title="Really Simple Syndication">RSS</abbr>](http://pl.wikipedia.org/wiki/Really_Simple_Syndication).

Systemów blogowych i <abbr title="Content Management System">CMS</abbr>‘ów jest wiele, a większość z nich obsługuje feedy <abbr title="Really Simple Syndication">RSS</abbr> czy Atom. Jak je zatem podmienić? Ten blog działa pod kontrolą silnika [WordPress](https://wordpress.org/) zatem na jego przykładzie omówię co zrobić, by w kilku krokach mieć dostęp do funkcjonalności Feedburner’a. Niemniej, poniżej znajdują się 2 metody. Druga z nich – owszem, nadaje się tylko dla WordPress’a. Jednak pierwszą można wykorzystać (z minimalnymi modyfikacjami wymagającymi jedynie odrobiny myślenia) w **każdym CMS’ie**.

## Feedburner HOWTO – part 1

Decydując się na oddanie się pod kontrolę Feedburnera musimy podmienić istniejące na naszej stronie kanały.

1. Rejestracji i tworzenia feedu nie warto opisywać. Standard.
2. **Aktualizacja nagłówka strony** – w przypadku <abbr title="Wordpress">WP</abbr> jest to plik *header.php*. należy zastąpić **wszystkie** nagłówki dotyczące kanałów RSS jak np. `<link rel="alternate" type="application/rss+xml" title="<i>moj blog</i> RSS Feed" href="http://blog.domain.tld/rss/" /><br></br>	<link rel="alternate" type="application/atom+xml" title="<i>moj blog</i> Atom Feed" href="http://blog.domain.tld/feed/atom/" /><br></br>	<link rel="alternate" type="application/rss+xml" title="<i>moj blog</i> RSS 2.0 Feed" href="http://blog.domain.tld/feed/" /><br></br>	<link rel="alternate" type="application/rss+xml" title="<i>moj blog</i> Comments RSS 2.0 Feed" href="http://blog.domain.tld/comments/feed/" /><br></br>	<link rel="alternate" type="application/rdf+xml" title="<i>moj blog</i> RSS 1.0" href="http://blog.domain.tld/feed/rdf/" /><br></br>	<link rel="alternate" type="text/xml" title="<i>moj blog</i> RSS 0.92 Feed" href="http://blog.domain.tld/feed/rss/" />`  
    takim:  
    `<link rel="alternate" type="application/rss+xml" title="RSS" href="http://feeds.feedburner.com/<i>moj_feed</i>" />`  
    Od tego momentu każdy nowy czytelnik będzie już subskrybował kanał dostarczany przez <abbr title="Feedburner">FB.  
    </abbr>
3. Dla obecnych już czytelników należy przygotować kilka zmian w pliku `.htaccess`.  
    Dla mojego bloga wygląda on tak:  
    `RewriteEngine On<br></br>RewriteBase /<br></br>RewriteRule ^archives/category/(.*)/(feed|rdf|rss|rss2|atom)/?$ /wp-feed.php?category_name=$1&feed=$2 [QSA]<br></br>RewriteRule ^archives/category/?(.*) /index.php?category_name=$1 [QSA]<br></br>RewriteRule ^archives/author/(.*)/(feed|rdf|rss|rss2|atom)/?$ /wp-feed.php?author_name=$1&feed=$2 [QSA]<br></br>RewriteRule ^archives/author/?(.*) /index.php?author_name=$1 [QSA]<br></br>RewriteRule ^archives/([0-9]{4})?/?([0-9]{1,2})?/?([0-9]{1,2})?/?([_0-9a-z-]+)?/?([0-9]+)?/?$ /index.php?year=$1&monthnum=$2&day=$3&name=$4&page=$5 [QSA]<br></br>RewriteRule ^archives/([0-9]{4})/([0-9]{1,2})/([0-9]{1,2})/([_0-9a-z-]+)/(feed|rdf|rss|rss2|atom)/?$ /wp-feed.php?year=$1&monthnum=$2&day=$3&name=$4&feed=$5 [QSA]<br></br>RewriteRule ^archives/([0-9]{4})/([0-9]{1,2})/([0-9]{1,2})/([_0-9a-z-]+)/trackback/?$ /wp-trackback.php?year=$1&monthnum=$2&day=$3&name=$4 [QSA]<br></br>RewriteRule ^comments/feed/?([_0-9a-z-]+)?/?$ /wp-feed.php?feed=$1&withcomments=1 [QSA]<br></br>RewriteCond %{HTTP_USER_AGENT} FeedBurner<br></br>RewriteRule ^feed/?([_0-9a-z-]+)?/?$ /wp-feed.php?feed=$1 [QSA]<br></br>RewriteCond %{HTTP_USER_AGENT} !FeedBurner<br></br>RewriteRule ^feed/?([_0-9a-z-]+)?/?$ http://feeds.feedburner.com/ludwikc/blog [R,L]<br></br>`  
    Z zaznaczeniem, że mój blog dziala we własnej domenie. Dla podkatalogu z blogiem należy przed każdym `/wp-...` oraz po `RewriteBase` podać ścieżkę `/blog`.   
    Taki zabieg pozwoli dotychczasowym subskrybentom zaktualizować feedy. Mój `.htaccess` [do pobrania](http://files.ludwikc.net/web/htaccess).
4. To wszystko. ```
    .htaccess
    ```
    
     z zasady jest aktywowany w czasie rzeczywistym.
5. A, tak. Zapomniałem dodać, że teraz próba otworzenia jakiegokolwiek postu kończy się **błędem 404**. Ale dto nie jest żaden problem. Nie zależnie od tego jaką metodę wyświetlania permalinków wybraliśmy należy udać się do [Options » Permalinks](http://personaldevelopment.pl/wp-login.php?redirect_to=http%3A%2F%2Fsiadlak.com%2Fwp-admin%2Foptions-permalink.php&reauth=1) i zaktualizować sposób ich wyświetlania.

## Feedburner HOWTO – part 2: WordPress plugin

 Metoda prostsza, do wykorzystania w WordPressie. Ściągamy [odpowiedni plugin](http://orderedlist.com/wordpress-plugins/feedburner-plugin/), instalujemy, aktywujemy. Działa. 🙂

## <a name="wykop">Social Linkin’ – Wykop.pl</a>

Mamy, wymienione wyżej, del.icio.us, digg. A co z naszym [wykopem](http://wykop.pl)? Też jest. Zgodnie z [API](https://accounts.google.com/ServiceLogin?service=feedburner&continue=https%3A%2F%2Ffeedburner.google.com%2Ffb%2Fa%2Fmyfeeds&gsessionid=NZGsnXLsWZpvNqfhZh-wtw) możemy Stworzyć własną FeedFlarę która pozwoli dodawać linki na [wykop.pl](http://wykop.pl) bezpośrednio z czytnika.   
Aby to zrobić należy podać w Personal FeedFlares adres pliku <abbr title="eXtensible Markup Language">xml</abbr>:   
`http://projects.ludwikc.net/xml/wykop.xml`  
![FeedFlare - wykop.pl](http://personaldevelopment.pl/wp-content/uploads/2006/10/flare.png)  
Co daje następujący efekt:  
![Wykop.pl - zastosowanie](http://personaldevelopment.pl/wp-content/uploads/2006/10/wykop.png)  
 [Sprawdź sam.](http://feeds.feedburner.com/ludwikc/blog)

\[tags\]feedburner, rss, wordpress, howto\[/tags\]