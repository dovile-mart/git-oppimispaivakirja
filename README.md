# Git-versionhallinta -kurssin oppimispäiväkirja (SOF011AS2A-3001)
Tekijä: Dovile Martinonyte

Tämä oppimispäiväkirja on luotu tehdessä harjoituksia, jotka liittyvät Git-versionhallinnan kurssiin. Kurssin tavoitteena oli oppia ja kerrata git-versionhallintajärjestelmän perusteita soveltamalla projektityössä. 

Minun kokemus jokaisesta osiosta on kuvattu alla: 
- Oppimispäiväkirjan [ensimmäisessä](#oppimispäiväkirja-paikallinen-git) osassa olen harjoitellut vi-editorin käyttöä sekä Git-versionhallinnan käyttöä pakallisesti. [Siirry päiväkirja 1:een](./paivakirja1.md).

 - [Toisessa](#oppimispäiväkirja-hajautettu-git) osassa harjoitelin hajautetun gitin käyttöä. [Siirry päiväkirja 2:een](./paivakirja2.md).
 
 - [Kolmannessa](#oppimispäiväkirja-git-projektissa) osassa harjoiteltu [projektin](https://github.com/dovile-mart/git-kurssi) kehittämistä virtuaalisen tiimikaverin (botin) kanssa. [Siirry päiväkirja 3:een](./paivakirja3.md).


# Oppimispäiväkirja: Paikallinen git

__Mitä uutta opin osiossa? Miten voisin hyödyntää oppimaani käytännössä?__

Tutustuin paremmin tiedostojen käsittelyyn ja niiden sisälön muokkaukseen käyttämällä pelkästään komentoja ja vi-editoria. Minulle entuudestaan tuntemattomat tai tosi harvoin käytetyt komennot olivat _reset, revert, diff, switch_. Tähän asti olen luonut turhaan paljon uusia haaroja ja käyttänyt _restore_. Tulevaisuudessa voisin aloittaa käyttämään enemmän talletuksia ja tarvittaessa _log_ ja _revert_ avulla palata takaisin, näin työskentely ja projektien historian hallinta olisi tehokkaampi. 

__Mikä osion tehtävissä oli vaikeaa ja mikä helppoa? Mikä auttoi minua oppimaan? Miten selvitin esteet, jotka vaikuttivat tehtävän suorittamiseen?__

Olen aiemmin käyttänyt Git:iä koulun projekteissa ja silloin ehkä en ole ottanut huomioon sen tarkemmin mitä versiohalinnassa tapahtuu. Olin keskittynyt enemmän projektien koodiin eikä siihen mitä versionhalinnassa tapahtuu.

Mielestäni vaikeita asioita ei ollut, kunhan jaksoin keskittyä siihen, mitä tein. Oli helppoa seurata ohjeita. Tein harjoituksia monta kertaa peräkkäin, mikä helpottaa muistamista. 
Oppimispäiväkirjan kloonaminen meni vähän sekaisin, kun en alussa hahmottanut, kummalla haaralla pitäisi tehdä muutoksia ja mihin lopullisesti paivakirja1.md tiedosto pitäisi tallentaa. 
Toinen asia, jonka olin tehnyt eri tavalla, oli käyttäjänimen ja sähköpostiosoitteen asettaminen. En halunnut asettaa globaallisti koulun tunnuksia ja huomasin vasta myöhemmin että alustetussa hakemistossa oli koulun tunnukset, mutta sen hakemiston sisällä olevissa muissa hakemistoissa oli aiemmin globaalisti asetetut tunnukset. Olisi ollut helpompaa, jos harjoitusten alussa olisi jonkinlainen "kartta", joka näyttää, miltä harjoitushakemisto tulisi näyttämään.

Esim.
```
- HARJOITUKSET
    - temp.log
    - HELLO   
        - index.html
        - styles.css
    - GIT-OPPIMISPAIVAKIRJA
        - paivakirja1.md
```

## Osiossa käyttämäni Git-komennot

| Komento | Kuvaus |
| --------| ------ |
| config --list | listaa kaikki asetukset |
| config user.email | user.email parametrin tarkistus |
| config user.name | user.name parametrin tarkistus |
| config user.name "_uusi nimi_" | parametrin asettaminen |
| config --list --global| globaalien parametrien lista |
| config -h | komentojen opastus |
| status | git-tilan tarkistus työhakemistossa |
| mkdir _uusiHakemisto_ | luo uuden hakemiston |
| touch _uusi.txt_ | luo uuden tiedoston |
| init | repon perustaminen hakemistoon |
| ls | listaa hakemiston sisältö |
| ls -l | listaa kaikki tiedostojen tiedot|
| ls -l -a | listaa myös piilotetut tiedot|
| clone | kloonaa etärepositorion |
| add _tiedosto.txt_ | lisää tiedoston **staged**-tilaan |
| add . | lisää kaikki **untracked** ja **modified** tiedostot |
| reset _tiedosto.txt_ | ennen committia poistaa sen **staged**-tilasta |
| restore _tiedosto.txt_ | palauttaa tiedoston siihen tilanteeseen missä se oli viimeisessä commitissa |
| commit -m "_viesti_"| tallennetaan muutokset lisäämällä kuvaava muutosten viesti |
| log | näyttää committien historia (q:lla pääsee pois vi-tilasta)|
| log --stat | näyttää yhteenvedon mitä muutoksia on committissa tehty |
| diff _tiedosto.txt_ | näyttää muutokset, jotka ovat tehty viimeisen commitin jälkeen |
| mv vanha.txt uusi.txt | tiedoston nimen muutos |
| mv _uusi.txt_ _uusiHakemisto_ | siirtää tiedoston toiseen hakemistoon |
| rm _tiedosto.txt_ | poistaa tiedoston |
| rm -f _tiedosto.txt_ | pakottaa poistamaan tiedoston, jos esim. on muutoksia, jotka eivät ole commitoittu|
| chechout _hash-tunniste_ | palataan commitin tilanteeseen (hash-merkkijono, 7 ensimmäistä merkkiä commitin numerosta riittää) |
| switch - | palataan nykyiseen tilaan |
|log -2 | näyttää kaksi viimesintä committia |
| revert _hash-tunniste_ | peruuttaa yhden commitin kerralla |
| branch _testing_ | uuden haaran luonti |
| branch | listaa olemassa olevat haarat |
| switch _testing_ | haaran vaihto |
| switch -c _haara_ | luo haaran ja samalla vaihtaa siihen |
| log --graph --all --oneline | listaa kaikkien haarojen commitit, kun projektissa on esim. kaksi haaraa ja molemmissa on talletuksia joita toisessa ei ole. |
|merge _haara_ | yhdistää toisen haaran muutoksia nykyiseen haaraan |

## Osiossa käyttämäni vi-komennot
| Komento | Kuvaus |
| --------| ------ |
| vi _tiedosto.txt_ | avaa tiedoston vi-editorille |
| a | insert-tila |
| SHIFT + ENTER | rivivaihto insert-tilassa |
| ESC | pääsee pois tilasta |
| o | uusi rivi |
| r | muuttaa merkin kursorin jälkeen |
| u | palauttaa aiemmat muutokset yksi kerralla |
| k | liikkuminen ylös|
| j | alas |
| l | oikealle |
| h | vasemmalle |
| D | poistaa kaiken kursorin oikealla puolella |
| cw | muuttaa kokonaisen sanan, kun kursori on sanan alussa|
| dd | poistaa kokonaisen rivin |
| x | yhden merkin poistaminen kursorin oikealta |
| :w | tallentaa ja jättää tiedoston auki |
|:q | lopettaa ilman tallentamista |
| :wq tai SHIFT+zz | tallentaa ja sulkee vi-editorin |

---

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
| branch -v | listaa paikalliset haarat ja näyttää viimeisimmän commitin |
| branch -r | listaa etärepositorion haarat |
| branch -r -v | listaa etärepositorion haarat ja näyttää viimeisimmän commitin |
| push origin --delete paivakirja-1 | poistaa etärepositorion haaran |
| switch paivakirja1 | vaihtaa haaran |
| switch -c paivakirja1 | luo uuden haaran ja vaihtaa siihen |
| checkout paivakirja3 | vaihtaa haaran |
| checkout paivakirja2 paivakirja3.md | ollessa paivakirja3-haarassa kopioi paivakirja3.md-tiedoston paivakirja2-haarasta |
| rm paivakirja3.md | tiedoston poisto (paivakirja2-haarasta) |
| remote rename | muuttaa etärepositorion nimen |
| remote rm | poistaa etärepositorion paikallisesta repositoriosta |
| fetch | hakee muutokset etärepositoriosta ja tallentaa ne paikallisesti |

---

# Oppimispäiväkirja: Git projektissa

__Mitä uutta opin osiossa? Miten voisin hyödyntää oppimaani käytännössä?__

Tässä osiossa opin eri työnkulkujen hyödyistä ja haasteista Git-versionhallinnassa keskitetyssä mallissa. Tulevaisuudessa voisin tutkia enenmmän integrointimanagerimallin asioita. Opin myös, kuinka tärkeää on käyttää hyviä käytäntöjä talletuskommenttien kirjoittamisessa, kuten lyhyet ja ytimekkäät otsikot sekä selkeät ja informatiiviset kuvaukset. Näitä tietoja voin hyödyntää omissa projekteissani parantaakseni yhteistyötä muiden kehittäjien kanssa ja varmistaakseni, että koodini on helposti ymmärrettävää ja hallittavaa.

---

__Millaiset talletuskommentit ovat mielestäsi hyödyllisiä muille projektin jäsenille? Tarkastele kurssilla laatimiasi talletuskommentteja ja arvioi niitä.__

Muille projektin jäsenille hyödylliset talletuskommentit pitäisi olla selkeitä ja informatiivisia. Ne voisivat sisältää lyhyen otsikon, joka tiivistää muutoksen pääkohdan. Lisäksi kommentit voisi sisältää pidemmän kuvauksen, joka selittäisi tehdyn muutoksen paremmin. Kurssilla laatimani talletuskommentit mielestäni olivat pääosin selkeitä. Arvio omista talletuskommenteistani:

#### _Hyvät esimerkit:_
```
git commit -m "Nappula poistettu ja kellonaika näkyy pysyvästi"
```
```
git commit -m "paivakirja3.md poistettu kopioimisen paivakirja3-haaraan jälkeen"
```

Nämä kommentit ovat lyhyitä, kuvaavia ja ne selittävät selkeästi, mitä muutoksia on tehty.

#### _Parannettavat esimerkit:_
```
git commit -m "Lisätty toiminnallisuus nappulaan"
```
Tämä kommentti olisin voinut tarkentaa kertomalla mikä toiminnallisuus on lisätty ja miksi.
```
git commit -m "Päiväkirja2 päivitetty"
```
Tässä kommenttissa olisin voinut kirjoittaa onko tietoa poistettu, lisätty vai kirjoitusvirheitä korjattu.

---

__Osallistut 3-4 hengen ohjelmistoprojektikurssille, ja olet saanut tehtäväksesi järjestää projektitiimin versionhallinnan. Kerro, miten tekisit sen. Laadi tiimiläisille lyhyt ohje, miten projektissa toimitaan.__

Projektin versionhallinnan järjestäminen:

- Repositoryn perustaminen: Luon projektin yhteisen Git-repositoryn GitHubiin ja varmistan, että kaikilla tiimin jäsenillä on luku- ja kirjoitusoikeudet.
- Haarojen hallinta: Sovimme käytännön, jossa jokainen kehittäjä tekee muutoksensa omassa kehityshaarassaan (esim. feature-ominaisuus) ja yhdistämme vain valmiit ja testatut muutokset päähaaraan (main).
- Onnistuneen yhdistämisen jälkeen väliaikaiset haarat poistetaan.
- Talletuskommentit: Käytämme yhteisiä talletuskommenttikäytäntöjä: lyhyt otsikko ja tarvittaessa pidempi kuvaus.
- Työnkulku:
1. Aluksi kloonaamme yhteisen repositoryn paikallisesti: ```git clone repon-osoite```
2. Uuden ominaisuuden kehityksen aikana luomme uuden haaran: ```git switch -c ominaisuus-haara```. Haaran nimi voisi sisältää esimerkiksi myös päivämäärän ```feature-15.5.24```.
3. Teemme muutokset paikallisesti ja talletamme ne: ```git commit -m "Lyhyt ja selkeä kuvaus muutoksesta"```
4. Ennen muutosten viemistä yhteiseen repositorioon, haemme muiden tekemät muutokset: ```git fetch origin```
5. Siirtyminen haettuun haaraan ja muutosten tarkastelu ```git switch origin/ominaisuus-haara```
6. Siirtyminen omaan haaraan ja muutosten yhdistäminen ```git switch ominaisuus-haara``` ```git merge origin/ominaisuus-haara```
7. Mahdollisten konfliktien ratkaisu: ```git add .``` ```git commit -m "Konflikti ratkaistu"``` 
Mikäli konflikti on monimutkainen tai vaattii laajempaa tarkastelua - kommunikointi tiimijäsenten kanssa.
8. Muutosten vienti GitHubiin:  ```git push origin ominaisuus-haara```
8. Teemme pull requestin GitHubissa ja tarkistamme toistemme muutokset ennen niiden yhdistämistä päähaaraan.
- Dokumentointi ja kommunikaatio: Pidämme huolta, että kaikki muutokset dokumentoidaan asianmukaisesti ja että kommunikoimme tiimin kesken aktiivisesti.

---

__Kommenttini opintojaksosta, esim. sisällöstä, materiaalista, työmäärästä, hyödyllisyydestä, työmäärästä. Mitä toivoisit olevan enemmän, mitä vähemmän?__

Opintojakso oli hyvin suunniteltu ja materiaali oli kattavaa. Sisällöt olivat hyödyllisiä ja auttoivat kertaamaan ja ymmärtämään paremmin Git-versionhallinnan periaatteita ja parhaita käytäntöjä. Työmäärä oli sopiva ja käytännön harjoitukset auttoivat sisäistämään teorian.
Kehityskohdat voisivat olla:
- Peruskäyttö-osuudessa olisi voinut olla myös tiedoston luontikomento: touch.
- Githubin sivun navigointia voisi kehittää esimerkiksi lisäämällä jokaisen sivun alapuolelle nappulan, joka veisi edelliseen/seuraavaan aiheeseen.

Kokonaisuudessaan mielestäni kurssi oli erittäin hyödyllinen ja hyvin toteutettu.