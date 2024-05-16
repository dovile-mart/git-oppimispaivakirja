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
