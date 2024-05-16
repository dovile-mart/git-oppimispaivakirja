# Oppimispäiväkirja: Hajautettu git

__Mitä uutta opin osiossa? Miten voisin hyödyntää oppimaani käytännössä?__

Opin että voi muuttaa etärepositorion origin-nimen paikallisessa repositoriossa, ja että se ei ole varattu sana.
Tarkastellin myös etärepositoriota komentorivillä.
Olen tehnyt myös fetch-hakua ja sen tarkistusta paikallisesti (git checkout origin/master). Aiemmin olin aina vaan pullannut muutoksia ilman että tarkistin mitä muutoksia on tehty. 
Mielestäni jatkossa voisin käyttää fetch-komentoa sääännöllisesti, jotta tarkistaisin mitä muutoksia on tapahtunut etärepositoriossa ennen kuin yhdistän paikallisiin muutoksiin.

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
| branch paivakirja1 | luo uuden haaran |
| branch | listaa paikalliset haarat |
| branch -v | listaa etärepositorion haarat |
| switch paivakirja1 | vaihtaa haaran |
| remote rename | muuttaa etärepositorion nimen |
| remote rm | poistaa etärepositorion paikallisesta repositoriosta |