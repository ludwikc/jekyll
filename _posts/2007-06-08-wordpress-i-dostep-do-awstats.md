---
id: 142
title: 'WordPress i dostęp do awstats'
date: '2007-06-08T10:34:58+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://blog.ludwikc.net/2007/06/08/wordpress-i-dostep-do-awstats/'
permalink: /wordpress-i-dostep-do-awstats/
dsq_thread_id:
    - '2280687889'
views:
    - '812'
bsb_share_transient_facebook:
    - '1605673636'
bsb_share_count_facebook:
    - '0'
bsb_share_transient_linkedin:
    - '1605673636'
bsb_share_count_linkedin:
    - '0'
categories:
    - Szuflandia
format: image
---

![Apache](http://personaldevelopment.pl/wp-content/uploads/2007/06/apache11.jpg)Do każdej domeny, podpietej do konta na dreamhost ([200 GB za parę gorszy](http://blog.ludwikc.net/2006/10/05/vouchery-dreamhost/)) instalowane są statystyki Analog. [Awstats](http://awstats.sourceforge.net/) jest perlowym skryptem, który oferuje statstyki szersze niż Analogowe. W wiki jest obszerny i przystępny [poradnik](http://wiki.dreamhost.com/AWStats_Installation) dot. instalacji skryptu.

Działa z marszu, jednak problem pojawia się w przypadku korzystania z `mod_rewrite`, a ten wykorzystuje wiele CMS’ów – między innymi WordPress. Temat wielokrotnie poruszany na wielu forach: *“Awstats – not accessible!!!”* Rozwiazanie jest proste i samo się nasuwa:

```
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteBase /
RewriteCond %{REQUEST_URI} ^/(awstats|stats|failed_auth.html)/?(.*)$ [NC]
RewriteRule ^.*$ - [L]
</IfModule> 
```

Dzięki wpisowi w `.htaccess` mamy dostęp zarówno do awstats jak i analog (umieszczanego w katalogu *domain.com/stats/*).  
Tylko jedna uwaga. Taka reguła musi być wykonana **przed** resztą reguł CMS’a. Inaczej dostęp do statystyk nie będzie nadal możliwy.

\[tags\]apache, awstats, wordpress, dreamhost\[/tags\]

Ku pamięci 🙂