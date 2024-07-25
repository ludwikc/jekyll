---
id: 145
title: 'Ratowanie Windows'
date: '2007-06-11T00:59:01+02:00'
author: 'Ludwik C. Siadlak'
layout: post
guid: 'http://blog.ludwikc.net/2007/06/11/windows-odzyskiwanie-mbr/'
permalink: /windows-odzyskiwanie-mbr/
dsq_thread_id:
    - '2179185988'
views:
    - '524'
bsb_share_transient_facebook:
    - '1605784383'
bsb_share_count_facebook:
    - '0'
bsb_share_transient_linkedin:
    - '1605784384'
bsb_share_count_linkedin:
    - '0'
categories:
    - Szuflandia
format: image
---

![Microsoft Windows](http://personaldevelopment.pl/wp-content/uploads/2007/06/ms-windows_logo_m11.jpg)Zdarzają się sytuacje, w których nie dość, że musisz skorzystać z oprogramowania napisanego dla Windows, to jeszcze sam system musisz po drodze *uratować*. Tworząc publikację DVD dla [Collegium Cantorum](http://collegiumcantorum.com), używam zamkniętego softu do obróbki video. Oczywiście większość partycji na 200GB dyskach działa na ext3, a NTFS, to raptem ~10% całości. Przy takiej zabawie potrzeba jednak trochę miejsca (tym bardziej, że publikacja będzie dwupłytowa, a zawarte na niej filmy mam nadzieję zamknąć w niecałych **8 godzinach**). Znalazłem na dysku trochę wolnego miejsca, niezajętego dotychczas przez żadną partycję – +/- 30GB. Powinno wystarczyć. *My Computer -&gt; Manage -&gt; Disk Management.* **Voila!** Oczywiście, przy okazji dodawania do projektu kolejnych plików \*.mpeg coś tam się zadziało i system zaczął się potwornie mulić (niestety, widać, że to nie Arch). No to restart…

###  A po restarcie 

```
GRUB loading...
Error 17.
```

Brzmi znajomo, nieprawdaż? W takiej sytuacji (czyli kiedy mieszają się partycje) odpala się pierwsze z brzegu LiveCD i reinstaluje GRUBa w MBR’ze. Teraz jednak jest 1:54, a priorytetowym zadaniem jest płytka DVD. Płytka obrabiana w Windows. Jak przywrócić dostęp do partycji NTFS, tak aby <del>system</del>Windows mógł wstać?

### Metoda “na barbarzyńcę”

Step-by-step HOWTO, czyli jak uruchomić Windowsa:  
Potrzebny jest tylko oryginalny nośnik instalacyjny (to **nie** jest żart! 😉 ) i klawiatura: po załadowaniu instalatora Windows interesuje nas literka “R” czyli System Recovery. Po zalogowaniu do konsoli (po podaniu hasła Administratora) nadpisujemy MBR:

```
C:WINDOWS> <b>fixmbr</b>
```

 a potem dla pewności dodajemy wpis do bootloadera:

```
C:WINDOWS> <b>bootcfg /rebuild</b>
```

 Na koniec jeszcze *reset, sil vous plait!*

Tym oto magicznym sposobem wyrzuciliśmy przyjaznego *GBURa* przez *Okno*. Przykre, ale skuteczne.

\[tags\]windows, mbr, recovery\[/tags\]