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