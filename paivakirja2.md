# Oppimispäiväkirja: Hajautettu git

__Mitä uutta opin osiossa? Miten voisin hyödyntää oppimaani käytännössä?__

Opin että voi muuttaa etärepositorion origin-nimen paikallisessa repositoriossa, ja että se ei ole varattu sana.
Tarkastellin myös etärepositoriota komentorivillä.
Olen tehnyt myös fetch-hakua ja sen tarkistusta paikallisesti (git checkout origin/master). Aiemmin olin aina vaan pullannut muutoksia ilman että tarkistin mitä muutoksia on tehty. 
Mielestäni jatkossa voisin käyttää fetch-komentoa sääännöllisesti, jotta tarkistaisin mitä muutoksia on tapahtunut etärepositoriossa ennen kuin yhdistän paikallisiin muutoksiin.
Olin vahingossa luonut paivakirja2-haaraan paivakirja3.md tiedoston pohjan, ja sen sain switch:illa kopioitu uutteen haaraan. Sen jälkeen poistin tiedoston paivakirja2:sta.

__Mikä osion tehtävissä oli vaikeaa ja mikä helppoa? Mikä auttoi minua oppimaan? Miten selvitin esteet, jotka vaikuttivat tehtävän suorittamiseen?__

Olin ymmärtänyt väärin mihin piti kloonata oppimispäiväkirjan tehtävänannon, joten meni paljon aikaa lukiessa teoriaa alusta ja etsiessä mikä meni pieleen. Lopuksi tarkistin Moodlen Loppupalautus-osiosta ja selvisi että hello ja oppimisäiväkirja pitäisi olla kaksi eri repositoriota.

## Osiossa käyttämäni Git-komennot

| Komento | Kuvaus |
| --------| ------ |
| clone _etärepositorion osoite_ | Repositorion kloonaaminen hakemistoon |
| init | Gitin alustus hakemistossa |
| branch -M master | luo tai päivittää master-nimisen päähaaran |
| remote add origin _etärepositorion osiote_ | lisää etärepositorion paikalliseen repositorioon |
| push -u origin master | vie muutokset etärepositorioon ja asettaa seuraamisen päähaaran master kanssa |
| push | vie nykyisen haaran muutokset sen oletusarvoiseen etähaaraan |
| push --all | vie kaikkien haarojen muutokset etärepositorion haaraan |
| branch paivakirja1 | luo uuden haaran |
| branch | listaa paikalliset haarat |
| branch -v | listaa etärepositorion haarat ja näyttää viimeisimman commitin |
| switch paivakirja1 | vaihtaa haaran |
| switch -c paivakirja1 | luo uuden haaran ja vaihtaa siihen |
| checkout paivakirja3 | vaihtaa haaran |
| checkout paivakirja2 paivakirja3.md | ollessa paivakirja3-haarassa kopioi paivakirja3.md-tiedoston paivakirja2-haarasta |
| rm paivakirja3.md | tiedoston poisto (paivakirja2-haarasta) |
| remote rename | muuttaa etärepositorion nimen |
| remote rm | poistaa etärepositorion paikallisesta repositoriosta |
| fetch | hakee muutokset etärepositoriosta ja tallentaa ne paikallisesti |