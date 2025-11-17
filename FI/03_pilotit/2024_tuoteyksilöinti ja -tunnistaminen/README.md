# BETK: Tuoteyksilöinnin ja RFID-teknologian pilotoinnin loppuraportti (KESKEN)

**Tilauksesta suunniteltavat rakennustuotteet**  
>Julkaisija: Rakennusteollisuus ry\
>Julkaistu: 11.2.2025  
Versio: 1.0  
Status: Julkaistu

## Asiakirjan tiedot

<details> 
<Summary>Pilotointi työryhmä</Summary>

| **Nimi**            | **Organisaatio**     | **Rooli / kontribuutio**               |
|---------------------|----------------------|--------------------------------|
| Teemu Alaluusua     | Aalto-yliopisto      |Pääkirjoittaja (1st author)     |
| Tuomas Kekki        | Fira Oy              |Case 1: aineiston tuottaminen ja kerääminen    |
| Ville Retulainen    | Lujabetoni           |Case 1: aineiston tuottaminen ja kerääminen    |
| Janne Raitaniemi    | Riffid               |Case 1: RFID-laitetoimittaja   |
| Eetu Lahtinen       | Consolis Parma Oy    |Case 2: aineiston tuottaminen ja kerääminen    |
| Arto Nieminen       | NCC                  |Case 2: Työmaanyhteyshenkilö    |
| Juha Porkka         | NordicID             |Case 2: RFID-laitetoimittaja   |
</details>

<details> 
<Summary>Asiantuntijaryhmä</Summary>

| Nimi               | Organisaatio                   |
|--------------------|--------------------------------|
| Janne Kihula       | Rakennustuoteteollisuus RTT ry |
| Veijo Artoma       | Consolis Parma Oy              |
| Kari Turunen       | Lujabetoni Oy                  |
| Ville Retulainen   | Lujabetoni Oy                  |
| Markku Räisänen    | Betset Oy                      |
| Otto Alhava        | Fira Oy                        |
| Tuomas Kekki       | Fira Oy                        |
| Hannes Ilveskoski  | Fira Oy                        |
| Antti Pekkala      | Fira Oy                        |
| Ari Törrönen       | NCC Suomi Oy                   |
| Riku Laiho         | NCC Suomi Oy                   |
| Arto Nieminen      | NCC Suomi Oy                   |
| Janne Makkonen     | Consti                         |
| Ville Siikaoja     | YIT                            |
| Lassi Saari        | YIT                            |
| Klaus Turhanen     | RFID Lab Finland ry            |
| Janne Raitaniemi   | Riffid Oy                      |
| Juha Porkka        | Nordic ID Oyj                  |
| Sami Saari         | Rakennustieto Oy               |
| Teemu Rantanen     | Rakennustieto Oy               |
</details>


---

## Sisällys

* [1 Esipuhe](#1-esipuhe)
* [2 Yleiskuvaus pilotista](#2-yleiskuvaus-pilotista)
  * [2.1 Betonielementtien tuoteyksilöinti (UPID)](#21-betonielementtien-tuoteyksilöinti-upid)
  * [2.2 UHF RFID-tunniste tiedonkantajana (AIDC) betonielementissä](#22-uhf-rfid-tunniste-tiedonkantajana-aidc-betonielementissä)
* [3 RFID-teknologian testaus toimitusketjussa](#3-rfid-teknologian-testaus-toimitusketjussa)
  * [3.1 Case 1](#31-case-1)
    * [3.1.1 Case 1: Osapuolet](#311-case-1-osapuolet)
    * [3.1.2 Case 1: RFID-tagien tiedot](#312-case-1-rfid-tagien-tiedot)
    * [3.1.3 Case 1: UHF RFID-lukijoiden tiedot](#313-case-1-uhf-rfid-lukijoiden-tiedot)
    * [3.1.4 Case 1: RFID-tunnisteiden sijoittaminen elementtiin](#314-case-1-rfid-tunnisteiden-sijoittaminen-elementtiin)
    * [3.1.5 Case 1: Kiinteän RFID-portin asemointi työmaalla](#315-case-1-kiinteän-rfid-portin-asemointi-työmaalla)
  * [3.2 Case 2](#32-case-2)
    * [3.2.1 Case 1: Osapuolet](#321-case-1-osapuolet)
    * [3.2.2 Case 2: RFID-tagien tiedot](#322-case-2-rfid-tagien-tiedot)
    * [3.2.3 Case 2: UHF RFID-lukijoiden tiedot](#323-case-2-uhf-rfid-lukijoiden-tiedot)
    * [3.2.4 Case 2: RFID-tunnisteiden sijoittaminen elementtiin](#324-case-2-rfid-tunnisteiden-sijoittaminen-elementtiin)
    * [3.2.5 Case 2: Kiinteän RFID-portin asemointi elementtitehtaalla](#325-case-2-kiinteän-rfid-portin-asemointi-elementtitehtaalla)
* [4 Tulokset](#4-tulokset)
  * [4.1 Case 1: RFID-tunnisteiden asennuksen ja lukutulosten analyysi](#41-case-1-rfid-tunnisteiden-asennuksen-ja-lukutulosten-analyysi)
  * [4.2 Case 2: RFID-tunnisteiden asennuksen ja lukutulosten analyysi](#42-case-2-rfid-tunnisteiden-asennuksen-ja-lukutulosten-analyysi)
* [5 Johtopäätökset](#5-johtopäätökset)
* [6 Liitteet](#6-liitteet)


---


## 1 Esipuhe

Tilauksesta suunniteltavien rakennustuotteiden (Engineer-to-Order, ETO) toimitusketjujen hallinta perustuu edelleen suurelta osin manuaaliseen tiedonvaihtoon ja suljetun toimintaympäristön integraatioratkaisuihin. Tämä rajoittaa tiedon siirrettävyyttä, hyödynnettävyyttä ja yhteentoimivuutta eri järjestelmien välillä. ETO-tuotantostrategian mukaisesti valmistettavien betonielementtien yksilöintiä ei ole aiemmin toteutettu tuoteyksilötasolla hyödyntämällä globaaleihin GS1-standardeihin perustuvaa yhtenäistä mallia, minkä seurauksena käytännöt ovat muodostuneet valmistajakohtaisiksi ja keskenään yhteensopimattomiksi. Tämä on vaikeuttanut toimitusketjun tietovirtojen digitalisointia, kokonaisuuden hallintaa sekä rajoittanut tiedon yhtenäistä hyödyntämistä eri osapuolten välillä.

Tämä raportti kokoaa tulokset tuoteyksilöinnin ja RFID-teknologian pilotista, joka toteutettiin osana Rakennusteollisuus RT:n tuotetiedon ja toimitusketjun digitalisoinnin kehityshanketta. Työn toimeenpanosta vastasi betonielementtitoimitusketju (BETK) -työryhmä, joka koostuu tilauksesta suunniteltavien rakennustuotteiden toimitusketjujen osapuolista sekä digitaalisen tiedonvaihdon asiantuntijoista.

Kehityshankkeen ensisijaisena tavoitteena on edistää rakennusalan tuotteiden toimitusketjujen siirtymistä manuaalisesta ja rakenteettomasta tiedonvaihdosta kohti täysin rakenteellista ja koneluettavaa tiedonhallintaa. Tavoitteen saavuttaminen edellyttää, että tilauksesta suunniteltavien tuotteiden valmistuksessa ja toimituksessa sovelletaan yhteisiä ja vakioituja menetelmiä tuotteiden yksilöintiin, tunnistamiseen ja tietosisältöjen jakamiseen. Näin voidaan parantaa tietojärjestelmien ja palveluiden yhteentoimivuutta, jonka puute on tällä hetkellä yksi merkittävimmistä esteistä rakennusteollisuuden digitalisaatiolle ja toimijoiden väliselle tiedonvaihdolle.

---

## 2 Yleiskuvaus pilotista

Tutkimuksen ensisijaisena tarkoituksena oli selvittää, missä määrin radioaaltotunnistukseen perustuva RFID-teknologia soveltuu vakioidun tuoteyksilöintitiedon kantamiseen ja lukemiseen betonielementtien toimitusketjussa. Tavoitteena oli lisäksi muodostaa perusteet GS1-standardeihin pohjautuvien ja eri toimijoiden yhteisesti hyödynnettävissä olevien tuoteyksilöinti- ja tunnistusmenetelmien käyttöönotolle rakennustuoteteollisuudessa. RFID-teknologiaa tarkasteltiin menetelmänä, joka mahdollistaa yksilöintitiedon liittämisen fyysiseen tuotteeseen ja sen systemaattisen keräämisen toimitusketjun eri vaiheiden aikana.

Tutkimus toteutettiin Proof of Concept -kokeiluna, jossa passiiviset UHF RFID -tunnisteet upotettiin betonielementteihin valmistusvaiheessa. Kokeilun tavoitteena oli arvioida tunnisteiden teknistä toimivuutta toimitusketjun eri osapuolten prosesseissa sekä tunnisteiden luettavuutta käytännön prosessi- ja käyttöympäristöissä. Luettavuudessa havaittavat vaihtelut muodostavat keskeisen kriteerin teknologian soveltuvuudelle rakenteellisten tuotteiden yksilöinnissä.

Teknisen toimivuuden arvioinnin ohella tarkasteltiin RFID-pohjaisen yksilöinnin käyttöönoton vaikutuksia toimitusketjun toimintaan. Teknologian integroiminen tuotantoon, logistiikkaan ja työmaaprosesseihin edellyttää muutoksia osapuolten toimintakäytännöissä, tiedonkeruun järjestelyissä ja prosessien välisessä koordinoinnissa. Näiden vaikutusten ymmärtäminen on keskeistä RFID-teknologian käyttöönoton kokonaisarvioinnissa, sillä organisatoriset ja prosessuaaliset tekijät määrittävät teknisen toimivuuden rinnalla ratkaisun todellisen soveltuvuuden.

Tutkimuksessa selvitettiin myös käyttöympäristön mahdollisia vaikutuksia passiivisten UHF RFID -tunnisteiden suorituskykyyn. Tarkastelussa huomioitiin betonin kosteuspitoisuus, materiaalikoostumus ja teräsvahvistusten läsnäolo sekä tunnisteen ja lukijan väliset sähkömagneettiset luentarajapinnat, joiden tunnetaan vaikuttavan antennin toimintakykyyn ja luentamatkaan. Lisäksi analysoitiin lukutapahtuman onnistumiseen vaikuttavia tekijöitä, kuten tunnisteen sijaintia ja orientaatiota betonin sisällä, RFID-lukujärjestelmän antennien sijoittelua suhteessa tunnisteeseen sekä ympäristön radiohäiriöitä. Näiden tekijöiden tunnistaminen on välttämätöntä arvioitaessa RFID-teknologian käyttökelpoisuutta betonielementtien toimitusketjun hallinnassa.

Tutkimuksen tuloksena luotiin lähtötaso tuleville toimintamalleille, joissa RFID-teknologiaa voidaan hyödyntää yhtenä tiedonkeruun ja tuoteyksilöinnin mahdollistavana ratkaisuna koko arvoverkon laajuudella. Tämä muodostaa perustan jatkokehitykselle, jossa tunnisteiden tekninen toimivuus ja järjestelmien yhteentoimivuus voidaan integroida osaksi digitaalista toimitusketjuarkkitehtuuria.

**Pilotoinnin toteutus**

Betonielementtien RFID-tunnisteteknologian pilotointi toteutettiin touko–marraskuun 2024 aikana kahdella kerrostalotyömaalla Helsingissä ja Tampereella. Testaus kattoi toimitusketjun vaiheet tuotevalmistuksesta työmaalla tapahtuvaan asennukseen asti. Toimitusketjun hallinnan näkökulmasta pilotointi rajattiin keskittymään tuoteyksilöinnin ja tunnistamisen menetelmiin (kuva 1). Tämä lähestymistapa muodosti perustan myöhemmin toteutettavalle toimitusketjun tapahtumatiedon jakamisen pilotoinnille.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/68ad12b2-839b-4beb-8800-ee0ef6edd3de" />

###### Kuva 1. Tuoteyksilöinnin ja RFID-tunnistusteknologian pilotointilaajuus toimitusketjun digitaalisen hallinnan näkökulmasta.

**Osallistujat ja yhteistyötahot**

Pilottiin osallistuivat betonielementtivalmistajat Parma Consolis Oy ja Lujabetoni Oy sekä rakennusyritykset Fira Rakennus Oy ja NCC Suomi Oy. RFID-teknologiaosaamista projektiin toivat Riffid Oy ja NordicID Oy. Lisäksi toteutuksessa olivat mukana Rakennusteollisuus RT, RFID Lab Finland Oy, Aalto-yliopisto ja GS1 Finland Oy.

### 2.1 Betonielementtien tuoteyksilöinti (UPID)
Tilauksesta suunniteltavien rakennustuotteiden toimitusketjuissa keskeinen haaste on, että tuotteet suunnitellaan ja valmistetaan yksilöllisesti tilausten perusteella. Tämä edellyttää tuoteyksilöinniltä laajaa, rakenteellisesti yhtenäistä tietosisältöä sekä tiedonkantajalta riittävää kapasiteettia yksilöintitiedon tallentamiseen.

BETK-työryhmässä tuoteyksilöinti päätettiin toteuttaa hyödyntämällä GS1-standardiperheen tunnisterakenteita. Menetelmä soveltuu erityisesti tilauksesta suunniteltaviin tuotteisiin, joissa hierarkkinen yksilöintimalli tukee tuotetiedon kohdistamista ja sen jäljitettävyyttä toimitusketjun eri osapuolten välillä.

Kuvassa 2 esitetään tilauksesta suunniteltavien betonielementtien tuoteyksilöinti GS1-standardiperheen mukaisten tunnisteiden ja sovellustunnusten perusteella. Kuvan yläosa kuvaa kolmitasoisen tuoteyksilöintimallin, jossa jokaisella tasolla tarkennetaan tuotteen yksilöintiä toimitusketjun tarpeisiin. Ensimmäinen taso on tuoteryhmätason tuoteyksilöinti, jossa käytettävä tunniste (MTO GTIN) määrittää valmistajan perustuotteen. Toinen taso on tuotevariaatiotason tuoteyksilöinti, jossa lisätunniste (MTO-varianttinumero) erottaa perustuotteen tilauskohtaisen variantin. Variantit voivat poiketa toisistaan esimerkiksi mitoiltaan, varustelultaan tai muista suunnittelua koskevista lähtötiedoista. Kolmas taso on tuoteyksilötason tuoteyksilöinti, jossa sarjanumero yhdistetään tuoteryhmätason tunnisteeseen ja varianttinumeroon. Tämä mahdollistaa saman variantin yksittäisten tuoteyksilöiden erottamisen toisistaan ja tukee tuotteen jäljitettävyyttä elementin koko elinkaaren ajan.

Kuvan keskiosassa esitetään ne GS1-sovellustunnukset, jotka muodostavat betonielementtien yksilöinnin minimitietosisällön. Pakollisia sovellustunnuksia ovat tuoteryhmätason tunniste (03), tuotevariaatiotason tunniste (242) ja tuoteyksilötason sarjanumero (21). Kuvassa esitetään lisäksi valinnaisia sovellustunnuksia, kuten elementtitunnus (91), GUID-tunniste (92) ja verkkotunnus (99), jotka mahdollistavat tuotteen liittämisen järjestelmäkohtaisiin tietoihin ja digitaalisiin tietorakenteisiin. Nämä lisätunnisteet parantavat tuotteen jäljitettävyyttä ja tukevat tietojen yhdistettävyyttä toimitusketjun eri osapuolten välillä.

Kuvan alaosa esittää yksilöintitiedon toteutusvaihtoehtoja käytännössä. Esitetyt tiedonkantajat ovat GS1 Digital Link -tunniste (2D-viivakoodi), GS1 DataMatrix (2D-viivakoodi) ja EPC/RFID-tunniste, jotka mahdollistavat tiedon liittämisen fyysiseen tuotteeseen ja tiedon lukemisen osana toimitusketjun prosesseja. Näiden tiedonkantajien avulla kuvassa esitetyt tunnisteet voidaan sijoittaa joko tuotteen pinnalle tai upottaa osaksi tuotetta, mikä mahdollistaa tuoteyksilöinnin teknisen käytettävyyden myös haastavissa työmaa- ja tuotanto-olosuhteissa.


<img width="2343" height="3541" alt="2025-10-13_Kuva1(fi)" src="https://github.com/user-attachments/assets/8b3d332d-0bfd-411d-b3ab-7927fceb5e97" />

###### Kuva 2. tilauksesta suunniteltavien betonielementtien tuoteyksilöinti ja tiedonkantajat

### 2.2 UHF RFID-tunniste tiedonkantajana (AIDC) betonielementissä
BETK-työryhmän tuoteyksilöintimäärittelyjen testaamiseksi päätettiin kokeilla betonielementtien tuotetunnistusta RFID-teknologiaan perustuvien tiedonkantajin kautta haastavimmassa mahdollisessa käyttötapauksessa. RFID-teknologia perustuu radiotaajuuksilla tapahtuvaan tiedonsiirtoon, jossa RFID-lukija lähettää radiosignaalin aktivoidakseen tunnisteen. Tunniste vastaa signaaliin heijastamalla siihen tallennetut tiedot takaisin lukijalle, joka edelleen välittää ne tietojärjestelmään.

<img width="3257" height="993" alt="2025-10-29_Kuva1" src="https://github.com/user-attachments/assets/6bbfae60-e3aa-461c-adf8-3e3bd9464714" />

###### Kuva 3. RFID-teknologian perusperiaate

RFID-järjestelmä ei edellytä suoraa näköyhteyttä ja mahdollistaa automaattisen sekä etäluettavan yksilöinnin. Tunnisteet luokitellaan passiivisiin, puolipassiivisiin ja aktiivisiin niiden virransyöttömekanismin perusteella. RFID-järjestelmät toimivat eri radiotaajuuksilla, joista yleisin on LF-taajuus (matala taajuus, 30–300 kHz), HF (korkea taajuus, 3–30 MHz) ja UHF (erittäin korkea taajuus, 300 MHz - 3 GHz).

Testissä käytettiin koteloituja metallipinnoille soveltuvia passiivisia EPC/RFID Gen2 UHF -tunnisteita, jotka valettiin betonielementtien sisään. Tunnisteen valinta perustui RFID-teknologia-asiantuntijoiden näkemykseen, jossa passiivisten UHF-tunnisteiden lukuetäisyys, kustannustehokkuus ja käyttöympäristön soveltuvuus olivat keskeisiä valintakriteerejä kyseiselle RFID-teknologialle. EPC Globalin Gen2-luokan passiivinen UHF-RFID teknologia on laajasti käytetty, joka toimii 840–960 MHz:n taajuuksilla alueellisista radiomääräyksistä riippuen. Se on kehitetty erityisesti logistiikkaverkoissa käytettäväksi, ja siinä on keskitytty useiden tunnisteiden nopeaan lukemiseen, hyvään lukuetäisyyteen ja alhaisiin kustannuksiin.

Tiedonkantajien osalta betonielementtien käyttöympäristön haasteena nähtiin betonin emäksisyyden, kosteuden, sekä raudoituksen vaikutukset RFID-tunnisteen toimintaan. RFID-teknologian testauksen tarve perustui aiempien tutkimus- ja kehityshankkeiden tuloksiin, jossa RFID-teknologian etuna nähtiin tiedonkantajan käyttöikä osana tuotetta, sekä automatisoidut lukutapahtumat ja niistä syntyvän tapahtumatiedon jakaminen toimitusketjun osapuolten välisissä prosesseissa.

---

## 3 RFID-teknologian testaus toimitusketjussa
RFID-teknologian toimivuutta betonielementtien sisään upotettuna tiedonkantajana testattiin kahdessa erillisessä rakennushankkeessa Helsingissä (Case 1) ja Tampereella (Case 2). Testaukseen osallistuivat kaksi pääurakoitsijaa, kaksi betonielementtivalmistajaa ja kaksi RFID-teknologiatoimittajaa. Testaus toteutettiin osana todellisia toimitusketjuja kunkin yrityksen omilla resursseilla ja ilman erillistä mock-up-vaihetta, jolloin tunnisteiden käyttöä voitiin tarkastella osana käynnissä olevaa tuotantoketjua ja ilman merkittäviä muutoksia vakiintuneisiin prosesseihin.

RFID-tunnisteet koodattiin etukäteen RFID-teknologiatoimittajien toimesta BETK-työryhmän tuoteyksilöintiohjeen mukaisesti. Tunnisteita luettiin ensisijaisesti käsikäyttöisillä lukijoilla, ja lisäksi hyödynnettiin automaattisia porttilukijoita, joiden avulla voitiin tarkastella lukumenetelmien soveltuvuutta toimitusketjun eri vaiheisiin sekä niiden yhteensopivuutta elementtien tavanomaisten käsittely- ja logistiikkaprosessien kanssa.

---

### 3.1 Case 1
Ensimmäisenä pilottikohteena toimi Fira Rakennus Oy:n asuinkerrostalokohde Helsingissä, johon Lujabetoni Oy valmisti ja toimitti väliseinäelementtejä. Testauslaajuus ensimmäisen pilotoinnin osalta oli kymmenen (10) väliseinäelementtiä. Toimitusketjussa testattiin RFID-tunnisteiden luentaa eri vaiheissa: elementtitehtaalla käsilukijoilla, työmaan elementtipurkupaikalla kiinteällä automaattisella lukuportilla sekä elementtiasennuksen jälkeisessä tarkastuksessa käsilukijalla.

#### 3.1.1 Case 1: Osapuolet

<table border="1" cellspacing="5" cellpadding="5">
<tbody>
  <tr>
        <td><strong>RFID-teknologia toimittaja:</strong></td>
        <td><code>Riffid Oy</code></td>
  </tr><tr>
        <td><strong>Valmistaja:</strong></td>
        <td><code>Lujabetoni Oy, Järvenpään betonielementtitehdas</code></td>
  </tr><tr>
        <td><strong>Vastaanottaja:</strong></td>
        <td><code>Fira Rakennus Oy, asuinkerrostalokohde Hexagon (Pasila, Helsinki)</code></td>
  </tr>
</tbody>
</table>

#### 3.1.2 Case 1: RFID-tagien tiedot

Ensimmäisessä tapaustutkimuksessa tarkasteltiin kahden erilaisen UHF-taajuusalueella toimivan RFID-tunnisteen soveltuvuutta betonituotteiden yksilölliseen tunnistamiseen ja tiedonsiirtoon. Molemmat testatut tunnisteet perustuivat Alien Technology Higgs3 -siruun, jossa on 512 bitin käyttäjämuisti ja 96/128 bitin EPC-tunniste. Näin ollen ne mahdollistavat sekä pysyvän yksilöintitiedon että rajallisen määrän tuotekohtaista lisädataa tallennettuna itse tunnisteeseen.

Ensimmäinen tunniste (RFID tunniste 1) oli ABS-muovikoteloitu, metallia kestävä hard tag, jonka mitat olivat 155 × 32 × 12 mm ja suojausluokka IP67. Tunniste suunniteltiin erityisesti ympäristöihin, joissa se altistuu kosteudelle, pölylle ja mekaaniselle rasitukselle, kuten betonivalujen yhteydessä tapahtuvassa upotuksessa. Tässä kokeessa tunnisteita oli käytössä yhteensä 15 kappaletta.

Toinen testattu tunniste (RFID tunniste 2) oli vastaavasti anti-metal-tyyppinen passiivinen tunniste, mutta rakenteeltaan pienempi ja matalaprofiilisempi (135 × 21 × 17 mm). Sen kotelointi oli IP68-suojattu, mikä tekee siitä täysin pöly- ja vesitiiviin. Tämä tunnistemalli soveltui erityisen hyvin kohteisiin, joissa tilaa oli rajoitetusti, mutta kestävyydeltä vaadittiin vastaavaa tasoa kuin suuremmassa mallissa. Myös tätä tunnistetyyppiä oli käytössä 15 kappaletta.

Molemmat tunnisteet toimivat passiivisina EPC Class 1 Gen 2 / ISO 18000-6C -standardin mukaisina R/W-tunnisteina taajuusalueella 860–920 MHz, mikä mahdollistaa yhteensopivuuden laajasti käytössä olevien UHF-lukijoiden kanssa. Tunnisteiden valinnassa painotettiin erityisesti testiympäristön vaatimusten mukaista kestävyyttä, luotettavaa luentaa metallipintojen läheisyydessä sekä tiedon pysyvyyttä tuotteen elinkaaren ajan.

<table border="1" cellspacing="5" cellpadding="5">
 <tbody>
  <tr>
    <td><strong>RFID tunniste</strong></td>
    <td><strong>Muisti</strong></td>
    <td><strong>Tyyppi</strong></td>
    <td><strong>Taajuus</strong></td>
    <td><strong>Kotelointi</strong></td>
    <td><strong>Määrä</strong></td>
  </tr><tr>
    <td><strong>RFID tunniste 1 </strong><br><img width="895" height="202" alt="tunniste2-removebg-preview" src="https://github.com/user-attachments/assets/bd892371-d7c1-4ec0-8a2f-aa1ab5d3bef6" /></td>
    <td>Alien Technology, Alien Higgs3 chip, 512bits User memory, 96/128bits EPC </td>
    <td>Passive R/W EPC Class 1 Gen 2/ISO 18000-6C</td>
    <td>UHF 860-920 MHz</td>
    <td>Anti metal ABS rfid hard tag Koko:155*32*12mm IP67 </td>
    <td>15 kpl</td>
  </tr>
  <tr>
    <td><strong>RFID tunniste 2</strong><br> <img width="831" height="168" alt="tunniste1" src="https://github.com/user-attachments/assets/7c8eeb0f-8367-4a52-adea-0a5d27d4d120" /></td>
    <td>Alien Technology, Alien Higgs3 chip, 512bits User memory, 96/128bits EPC </td>
    <td>Passive R/W EPC Class 1 Gen 2/ISO 18000-6C</td>
    <td>UHF 860-920 MHz</td>
    <td>Anti-Metal Passive Tag Plate, Koko:135*21* 17 mm IP68 </td>
    <td>15 kpl</td>
  </tr>
 </tbody>
</table>

#### 3.1.3 Case 1: UHF RFID-lukijoiden tiedot

Tapaustutkimuksessa hyödynnettiin neljää UHF RFID -lukulaitetta ja kahta antennia, joiden avulla voitiin kerätä ja lukea tunnistetietoja betonielementteihin upotetuista RFID-tageista eri toimitusketjun vaiheissa. Lukijat valittiin edustamaan sekä kannettavia että kiinteitä ratkaisuja, jotta voitiin testata järjestelmän toimivuutta tuotannosta työmaan vastaanottoon asti.

Elementtitehtaalla tunnistetietojen lukemiseen ja tallentamiseen tuotantovaiheessa käytettiin **Nordic ID EXA51E**- ja **Nordic ID Medea** -laitteita. Nämä toimivat käsikäyttöisinä UHF-lukijoina, jotka tukevat EPC Class 1 Gen 2 -standardia ja hyödyntävät Bluetooth-yhteyttä mobiilipäätteeseen. Laitteiden avulla luettiin valmiiden elementtien RFID-tunnisteet ja tallennettiin tiedot digitaaliseen tietokantaan.

Työmaalla asennuksen jälkeisessä tarkastuksessa käytettiin **LT-C9082**-lukijaa, joka toimii Android-pohjaisena kannettavana UHF-lukijana. Laitteessa on integroitu lukumoduuli, jonka avulla tunnistetiedot voidaan lukea ja tallentaa suoraan työmaaympäristössä ilman erillisiä päätelaitteita.

Elementtien vastaanotto- ja purkualueella työmaalla käytettiin **Impinj Speedway R220** -lukijaa, joka toimii teollisuustason UHF RFID -lukijana ja soveltuu jatkuvaan tiedonkeruuseen esimerkiksi porttiseurannoissa. Lukija mahdollistaa kuljetuksista purettujen elementtien automaattisen tunnistamisen ja tiedonsiirron. 
Kiinteän lukijan yhteydessä toimivat kaksi antennia, **Times-7 A5010** ja **BRA-08**, jotka hyödyntävät circular polarized -periaatetta mahdollistaen tunnisteiden luennan eri kulmista ja asennoista. Times-7 A5010 tarjoaa laajan keilakulman ja korkean kestävyyden, kun taas BRA-08 soveltuu tarkasti kohdennettuun luentaan rajoitetuissa tiloissa.

<table border="1" cellspacing="5" cellpadding="5">
 <tbody>
  <tr>
    <td><strong>Laite</strong></td>
    <td><strong>Tuotetiedot</strong></td>
    <td><strong>Valmistaja/tyyppi</strong></td>
    <td><strong>Käyttötarkoitus</strong></td>
    <td><strong>Määrä</strong></td>
  </tr><tr>
    <td><strong>Kannettava UHF RFID-lukija 1</strong><br><img width="500" height="500" alt="nordic-id-exa51e-acd-nur2-1w-uhf-2d-imager-wireless-charging-etsi" src="https://github.com/user-attachments/assets/05e66998-e47a-4fbb-9d9f-0239879c86df" /></td>
     <td>Kannettava UHF RFID-lukija</td>
     <td>Nordic ID EXA51E </td>
     <td>Elementtitehtaan lukutapahtumat </td>
     <td>1 kpl</td>
  </tr><tr>
     <td><strong>Kannettava UHF RFID-lukija 2</strong><br><img width="500" height="500" alt="Medea_UHF_RFID_Reader_from_Nordic_ID" src="https://github.com/user-attachments/assets/cfcbf999-af75-4f1d-b522-2409c55506ec" /></td>
     <td>Kannettava UHF RFID-lukija</td>
     <td>Nordic ID Medea</td>
     <td>Elementtitehtaan tapahtumat </td>
     <td>1 kpl</td>
  </tr><tr>
     <td><strong>Kannettava UHF RFID-lukija 3</strong><br><img width="500" height="500" alt="4G-5-7inch-with-Screen-Wireless-UHF-Reader-Writer-Scanners-Device-Asset-Identification-Readers-RFID-PDA-removebg-preview" src="https://github.com/user-attachments/assets/b2f96cf9-e888-43bf-92c1-91050ac37192" /></td>
     <td>Kannettava UHF RFID-lukija</td>
     <td>LT-C9082</td>
     <td>Työmaalla asennuksen jälkeinen tarkastus</td>
     <td>1 kpl</td>   
  </tr><tr>
     <td><strong>Kiinteä UHF RFID-lukija</strong><br><img width="408" height="408" alt="Impinj_R220-removebg-preview" src="https://github.com/user-attachments/assets/4c19dc8d-a54c-4c25-a66e-d9277f7a9370" /></td>
     <td>Kiinteä UHF RFID-lukija</td>
     <td>Impinj Speedway R220 UHF-lukija </td>
     <td>Elementin vastaanotto/kuorman purku työmaalla</td>
     <td>1 kpl</td>
  </tr><tr>
    <td><strong>Kiinteän UHF RFID-lukijan antenni 1</strong><br> <img width="293" height="300" alt="0001290_times-7-slimline-a5010-circular-polarized-antenna_300-removebg-preview" src="https://github.com/user-attachments/assets/cf5bbab7-1f75-4b81-851f-2868079f827b" /></td>
    <td>UHF-antenni</td>
    <td>UHF-antenni Times-7 A5010 (A5010)</td>
    <td>Elementin vastaanotto/kuorman purku työmaalla</td>
    <td>1 kpl</td>
  </tr><tr>
    <td><strong>Kiinteän UHF RFID-lukijan antenni 2</strong><br> <img width="300" height="200" alt="5bcfddc6b8170-removebg-preview" src="https://github.com/user-attachments/assets/95a4f4b7-2986-4798-bc5e-3c96fe02910a" /></td>
    <td>UHF-antenni</td>
    <td>UHF-antenni BRA-08</td>
    <td>Elementin vastaanotto/kuorman purku työmaalla</td>
    <td>1 kpl</td>
  </tr>
 </tbody>
</table>


#### 3.1.4 Case 1: RFID-tunnisteiden sijoittaminen elementtiin

RFID-tunnisteita asennettiin yhteensä kymmeneen väliseinäelementtiin, ja jokaiseen elementtiin sijoitettiin kolme tunnistetta. Tunnisteet integroitiin osaksi elementtiä valamalla ne rakenteeseen tuotannon yhteydessä. Asennuspaikat valittiin siten, että tunnisteet voitiin lukea sekä elementtitehtaalla että työmaalla elementtien tavanomaisten käsittelyprosessien yhteydessä. RFID-tunnisteiden sijoitus- ja suuntausperiaate on esitetty alla olevassa kuvassa.

Tunnisteista kaksi sijoitettiin elementin yläpintaan ja yksi elementin päätyyn. Yläpintaan sijoitettujen tunnisteiden antenni suunnattiin kohtisuoraan ylöspäin, kun taas päätyyn sijoitetun tunnisteen antenni suunnattiin elementin lyhyelle sivulle. Tunnisteiden orientaatio määritettiin siten, että antennin suunnalla oli optimaalinen yhteys lukijan suuntaan sekä elementtien varastoinnin että työmaalle toimituksen aikana.

<img width="960" height="874" alt="Case 1 orientaatio (FI)" src="https://github.com/user-attachments/assets/825ca439-71b2-4edc-a8f0-9225c03cafd1" />  <br> Kuva. Case 1: RFID tunnisteiden asennuspaikat

Ennen betonivalua tunnisteet kiinnitettiin raudoitukseen joko mekaanisesti kuparilangan tai vastaavien sidontamateriaalien avulla tai vaihtoehtoisesti painamalla tunniste suoraan tuoreeseen betonimassaan ilman erillisiä kiinnitystarvikkeita. Raudoitukseen kiinnittämistä käytettiin erityisesti silloin, kun haluttiin varmistaa tunnisteen pysyminen täsmällisessä asennossa valun aikana. Massaan painaminen soveltui tilanteisiin, joissa tunniste sijoitettiin valupinnan kautta ja sen asentoa voitiin hallita riittävällä tarkkuudella. Alla olevissa kuvissa on esitetty esimerkkejä käytetyistä kiinnitysmenetelmistä.

Betonivalun jälkeen tunnisteiden sijainti tarkastettiin visuaalisesti valupinnan läpi sekä suorittamalla alustavat luentatestit käsilukijalla. Tavoitteena oli varmistaa, että tunnisteet säilyttivät suunnitellun orientaationsa ja että betoniin upottaminen ei estänyt radiotaajuiseen etälukuun perustuvaa tiedonsiirtoa. Luentatestien avulla voitiin myös arvioida, millaisia vaikutuksia betonin kosteudella ja raudoituksella oli luentatulokseen.

<img width="1698" height="1135" alt="image" src="https://github.com/user-attachments/assets/e7887267-d9f6-422d-9e52-3f4f6de5bca0" /><br> Kuva. Case 1: RFID-tunnisteen asennus elementin yläpintaan

<img width="1698" height="1135" alt="image" src="https://github.com/user-attachments/assets/360a5248-be2d-47a5-a535-b0a5e94aea22" /><br> Kuva. Case 1: RFID-tunnisteen asennus elementin sivulle

#### 3.1.5 Case 1: Kiinteän RFID-portin asemointi työmaalla

Kiinteän RFID-portin asemointi toteutettiin työmaaolosuhteissa elementtien purkualueelle siten, että lukujärjestelmä mahdollistaisi automaattisen tapahtumatiedon keruun kuljetusten saapuessa ja purettaessa elementtitelineeseen. Portti muodostettiin kahdelle puolelle asennetuista UHF-antenneista, jotka sijoitettiin 9,2 metrin etäisyydelle toisistaan purkukaistan molemmille puolille. Molempien puolien UHF-antennit sijoitettiin 4,5 metrin korkeuteen, mahdollistaen tunnisteiden luennan myös korkeammalle kuormatuista betonielementeistä sekä ajoneuvojen yläosista. Tien puoleiselle reunalle asennettiin lisäksi toinen antenni 1,8 metrin korkeuteen, jonka tehtävänä oli varmistaa tunnisteiden luenta alemmilta tasoilta, kuten elementtien alaosista ja ajoneuvon lavan läheisyydestä. Antennit kiinnitettiin pystyrakenteisiin, jotka ankkuroitiin työmaan suojarakenteisiin ja julkisivuun. Lukulaitteet ja virransyöttö sijoitettiin sähkökotelointiin (IP-luokan suojaus) purkualueen laidalle, jossa ne yhdistettiin paikalliseen sähköverkkoon. Kaapelointi suojattiin mekaaniselta rasitukselta ja sijoitettiin aidan sisäpuolelle turvallisuuden ja käyttövarmuuden takaamiseksi.

<img width="1704" height="1658" alt="image" src="https://github.com/user-attachments/assets/2628e839-afaf-43a0-b97d-4cb80151208b" /><br> Kuva. Case 1: Kiinteän RFID-portin asemointi työmaalla

---

### 3.2 Case 2

#### 3.2.1 Case 1: Osapuolet

<table border="1" cellspacing="5" cellpadding="5">
<tbody>
  <tr>
        <td><strong>RFID-teknologia toimittaja:</strong></td>
        <td><code>Nordic ID Oy</code></td>
  </tr><tr>
        <td><strong>Valmistaja:</strong></td>
        <td><code>Parma Consolis Oy, Kangasalan betonielementtitehdas </code></td>
  </tr><tr>
        <td><strong>Vastaanottaja:</strong></td>
        <td><code>NCC Rakennus Oy, asuinkerrostalokohde TOAS Rauhaniemi 34, (Tampere) </code></td>
  </tr>
</tbody>
</table>


#### 3.2.2 Case 2: RFID-tagien tiedot

Toisessa RFID-tapaustutkimuksessa arvioitiin kahden Confidexin UHF RFID -tunnisteen teknistä soveltuvuutta betonituotteiden yksilöintiin. Molemmat tunnisteet ovat passiivisia EPC Class 1 Gen2 / ISO 18000-6C -standardin mukaisia ja suunniteltu vaativiin teollisuusympäristöihin, joissa vaaditaan mekaanista kestävyyttä, korkeaa luotettavuutta ja metallipintojen läheisyydessä toimivaa antennirakennetta.

Ensimmäinen tunnistetyyppi (Confidex Ironside Classic) perustuu UHF EPC Gen2 / ISO 18000-6C -protokollaan ja toimii taajuusalueella 865–928 MHz. Tunnisteessa käytetään Alien Higgs-3 -sukupolven sirua, jonka muistirakenne sisältää 128 tavua EPC-muistia, 512 tavua käyttäjämuistia (User Memory) ja 96 tavua TID-muistia (Tag Identifier). Nämä muistialueet mahdollistavat sekä yksilöivän EPC-tunnisteen tallennuksen että tuotekohtaisten metatietojen (esim. valmistuserä, valupäivä tai toimitusnumero) upottamisen tunnisteeseen. Fyysisesti tunniste on ABS-komposiittikuorinen, mitoiltaan 85 × 21 × 10 mm, ja se täyttää IP68-luokituksen pöly- ja vesitiiviyden osalta. Käyttölämpötila-alue (−35 °C – +85 °C) kattaa tyypilliset betonielementtiteollisuuden prosessilämpötilat sekä ulkovarastoinnin olosuhteet. Tunnistetta käytettiin kokeessa yhteensä 14 kappaletta

Toinen tutkittu malli (Confidex Survivor) on rakenteeltaan järeämpi ja varustettu NXP UCODE G2iM+ -piirillä, joka tarjoaa suuremman muistikapasiteetin: EPC 448 bittiä, User Memory 640 bittiä ja TID 96 bittiä. Tunniste toimii EU:n säädösten mukaisella taajuusalueella 865–869 MHz ja noudattaa samaa EPC Class 1 Gen2 / ISO 18000-6C -standardia. Fyysiset mitat (155 × 26 × 14,5 mm) mahdollistavat tehokkaamman antennin ja pidemmän lukuetäisyyden ja IP68-luokitus tekevät tunnisteesta mekaanisesti erittäin kestävän, ja sen kapselointi mahdollistaa upotuksen betonimassaan ilman sirun vaurioitumista. Käyttölämpötila-alue on identtinen Ironside-mallin kanssa, mutta Survivor-tunnisteen antennirakenne tarjoaa paremman säteilykuvion ja luentatehon, erityisesti metallipintojen läheisyydessä tai rakenteellisesti vaimennetuissa olosuhteissa. Tässä tutkimuksessa tunnisteita oli käytössä viisi kappaletta.

Teknisestä näkökulmasta Confidex Ironside soveltuu paremmin kompaktien tuotteiden ja lyhyiden lukuetäisyyksien sovelluksiin, kun taas Confidex Survivor tarjoaa pidemmän lukuetäisyyden ja korkeamman luotettavuuden vaativissa teollisuusympäristöissä. Molemmat tunnisteet tukevat EPCIS-yhteensopivaa tapahtumatiedonhallintaa, mikä mahdollistaa tunnistetietojen integroinnin digitaaliseen toimitusketjujärjestelmään.

<table border="1" cellspacing="5" cellpadding="5">
 <tbody>
  <tr>
    <td><strong>RFID tunniste</strong></td>
    <td><strong>Muisti</strong></td>
    <td><strong>Tyyppi</strong></td>
    <td><strong>Taajuus</strong></td>
    <td><strong>Kotelointi</strong></td>
    <td><strong>Määrä</strong></td>
  </tr><tr>
    <td><strong>RFID tunniste 1 <img width="400" alt="confidex-ironside-slim-370x273-removebg-preview" src="https://github.com/user-attachments/assets/c5d22a72-13aa-4fd6-ac55-6fc1bef1c32a" /></td>
    <td>Confidex ironside classic: EPC 128 bytes, RAM 512 bytes, TID 96 bytes </td>
    <td>Passiivinen</td>
    <td>Global 865-928MHz </td>
    <td>Koko: 85 x 21 x 10 mm. Operating temperature -35°C to +85°C / -31°F to +185°F Ambient temperature -35°C to +85°C /-31°F to +185°F IP classification IP68 </td>
    <td>14 kpl</td>
  </tr>
  <tr>
    <td><strong>RFID tunniste 2</strong><br> <img width="400" alt="Confidex-Survivor-removebg-preview" src="https://github.com/user-attachments/assets/3aee56d2-b062-43d5-9cd2-03ac9feb6112" /></td>
    <td>Confidex Confidex survivor: NXP UCODE G2iM+ Memory: EPC 448 bit; User 640 bit; TID 96 bit </td>
    <td>Passiivinen </td>
    <td>EU 865 - 869 MHz</td>
    <td>Koko: 155 x 26 x 14,5 mm. Operating temperature -35°C to +85°C / -31°F to +185°F Ambient temperature -35°C to +85°C /-31°F to +185°F IP classification IP68</td>
    <td>5 kpl</td>
  </tr>
 </tbody>
</table>


#### 3.2.3 Case 2: UHF RFID-lukijoiden tiedot

Toisessa tapaustutkimuksessa testattiin RFID-lukulaitteiden toimivuutta teollisen tuotannon ja työmaan rajapinnassa. Käytössä oli sekä kannettava että kiinteä UHF RFID -lukuratkaisu, jotka edustivat uudemman sukupolven laitekantaa.

Kannettava lukija oli Nordic ID HH85, ergonominen ja teollisuuskäyttöön suunniteltu päätelaite, jossa on suuri akku, integroitu antenni ja kosketusnäyttö. Lukijaa käytettiin rakennustyömaalla elementtien tunnistamiseen ja toimituserien seurantaan, erityisesti asennusvaiheen yhteydessä. Laite mahdollisti tiedon siirron suoraan pilvipalveluun, mikä paransi luentatietojen ajantasaisuutta ja vähensi manuaalista kirjaamista.

Kiinteänä lukijana toimi Nordic ID FR22 LTE, joka asennettiin betonielementtitehtaan tuotannon ja välivaraston väliseen pisteeseen. Lukija keräsi automaattisesti tunnistetietoja elementtien siirtyessä prosessin vaiheiden välillä. FR22-laitteeseen liitettiin neljä Nordic ID GA30 -antennia, jotka muodostivat laajan ja monisuuntaisen lukualueen mahdollistaen tunnisteiden luennan myös betonipinnan sisältä.

Kokonaisuutena laitteisto toimi luotettavasti, ja sen avulla voitiin todentaa automaattisen tunnistamisen soveltuvuus rakennustuotteiden tuotannon ja logistiikan digitaaliseen seurantaan.

<table border="1" cellspacing="5" cellpadding="5">
 <tbody>
  <tr>
    <td><strong>Laite</strong></td>
    <td><strong>Tuotetiedot</strong></td>
    <td><strong>Valmistaja/tyyppi</strong></td>
    <td><strong>Käyttötarkoitus</strong></td>
    <td><strong>Määrä</strong></td>
  </tr><tr>
    <td><strong>Kannettava UHF RFID-lukija 1</strong><br><img width="400" alt="nordic-id-hh85-acd-uhf-rfid-2d-imager-dual-band-wlan-a-b-g-n-ac-us-removebg-preview" src="https://github.com/user-attachments/assets/ceb05261-c5bd-4223-b637-6cf087bf7fe5" /></td>
    <td>Kannettava UHF RFID-lukija</td>
    <td>Nordic ID HH85</td>
    <td>Rakennustyömaalla RFID-tunnisteiden luenta</td>
    <td>1 kpl</td>
  </tr><tr> 
    <td><strong>Kiinteä UHF RFID-lukija</strong><br><img width="400" alt="NPI00002-1-removebg-preview" src="https://github.com/user-attachments/assets/679d4f37-324d-4424-8ef4-8a74ee9e74b5" /></td>
    <td>Kiinteä UHF RFID-lukija</td>
    <td>Nordic ID FR22 LTE UHF-lukija </td>
    <td>Betonielementtitehtaalla valmistuksen / välivaraston välisellä osuudella sijaitseva kiinteä piste</td>
    <td>1 kpl</td>
  </tr><tr> 
    <td><strong>UFH-antenni</strong> <br> <img width="800" alt="-nordic-id-rfid-antennas-removebg-preview" src="https://github.com/user-attachments/assets/22ea4aa2-a37f-4420-b7b5-c0ddd92d3f8b" /></td>
    <td>UHF-antenni</td>
    <td>UHF-antenni Nordic ID GA30</td>
    <td>Betonielementtitehtaalla valmistuksen / välivaraston välisellä osuudella sijaitseva kiinteä piste</td>
    <td>4 kpl</td>
  </tr>
  </body>
</table>

#### 3.2.4 Case 2: RFID-tunnisteiden sijoittaminen elementtiin

RFID-tunnisteiden sijoittaminen betonielementteihin toteutettiin suunnitelmallisesti siten, että tunnisteiden sijainti ja asennustapa voitiin määrittää joko ennalta sovittujen reunaehtojen mukaisesti tai elementtisuunnitelmia hyödyntäen. Tässä projektissa lähtökohtana oli, että RFID-tunnisteiden asemointi tehtiin elementtisuunnittelijan laatiman tasokuvan perusteella. Sijoituspaikat määriteltiin eri tavoin elementin geometrian ja käyttötarkoituksen mukaan, mutta yhtenä periaatteena oli suunnata tunnisteen lukusuunta elementin etupintaa kohti, jotta tunnistaminen olisi mahdollisimman luotettavaa elementin ollessa paikallaan tai varastoituna.

Käytännön toteutuksessa RFID-tunnisteita asennettiin yhteensä viiteentoista (15) väliseinäelementtiin. Jokainen elementti varustettiin yhdellä tai kahdella tunnisteella, jotka valettiin osaksi betonielementtiä. Asennusperiaate on havainnollistettu alla olevassa kuvassa. Lisättävät RFID-tagien paikka tiedot lisättiin erilliseen RFID-Tag asemointi suunnitelmaan. Lisättävät RFID-tagien paikka tiedot lisättiin erilliseen RFID-Tag asemointi suunnitelmaan. Lisäksi jokaisesta erilaisesta asennuksesta on oma detaljinsa, jotka viitattiin yksittäisille elementtitunnuksille ja tällöin suunnitelmat olivat tekijöiden käytössä.




<img width="962" height="875" alt="Case 2 orientaatio-F (FI)" src="https://github.com/user-attachments/assets/d0214a07-33bd-4098-a9f9-f99ea88142bd" /><br> Kuva. RFID tunnisteiden asennuspaikat

<img width="1051" height="1183" alt="image" src="https://github.com/user-attachments/assets/33a129f6-f66e-4af3-99dc-211eed56f1f3" /><br> Kuva. Case 2: tasokuva

<img width="1812" height="861" alt="image" src="https://github.com/user-attachments/assets/f3487c53-4059-4f89-b7ad-5aca2fd7b5d9" /><br> Kuva. RFID-tunnisteiden asennusvaihe



#### 3.2.5 Case 2: Kiinteän RFID-portin asemointi elementtitehtaalla

Kiinteän UHF RFID-portin asemointi suoritettiin elementtitehtaalla tuotantolinjan ja ulkovaraston väliselle kulkureitille. Tavoitteena oli testata RFID-järjestelmän toimintaa automatisoidussa tunnistuksessa, kun betonielementit siirtyvät valmistuksen jälkeen viimeistelyosastolta varastointialueelle.

RFID-lukujärjestelmä koostui Nordic ID FR22 LTE -lukulaitteesta ja neljästä Nordic ID GA30 -UHF-antenneista. Antennit asennettiin tuulikaapin sisäseinään pareittain pystysuunnassa siten, että ylempi antenni sijoitettiin noin 2 metrin ja alempi noin 1,0 metrin korkeudelle lattiapinnasta. Antennien sijoittelu perustui kenttämittauksiin, joiden perusteella haluttiin varmistaa luentapeitto sekä ajoneuvon lavalla olevien että lattiatason läheisyydessä sijaitsevien RFID-tunnisteiden osalta.

<img width="1231" height="1114" alt="image" src="https://github.com/user-attachments/assets/d41dac59-ec1f-4d4a-880a-f85d5cc13f5d" /><br> Kuva. Case 2: Kiinteän RFID-portin asemointi elementtitehtaalla


---
## 4 Tulokset

### 4.1 Case 1: RFID-tunnisteiden asennuksen ja lukutulosten analyysi

Kymmenen väliseinäelementtiä varustettiin kolmella RFID-tunnisteella. Päätyihin asennetut tunnisteet (@1L ja @1R) sijoitettiin noin metrin korkeudelle, ja yläpinnan tunniste (@2) valettiin elementin yläreunaan. Luenta tehtiin tehtaalla, työmaan vastaanotossa kiinteällä RFID-portilla sekä asennuksen jälkeen käsilukijalla.

Tulokset osoittivat, että päätysijoitus tuotti johdonmukaisimmin onnistuneita lukutapahtumia kaikissa vaiheissa. Päädyt luettiin toistuvasti 0,3–2,0 metrin etäisyydeltä ja RSSI-arvot vaihtelivat pääosin välillä 56–80. Tämä osoittaa, että tunnisteen orientaatio antenniin nähden oli näissä asennoissa suotuisampi, sillä tunnisteen kenttäsuunta vastasi lukijan polarisaatiotasoa ja säteilykuviota.

Yläpintaan sijoitettu tunniste oli selvästi haasteellisempi erityisesti silloin, kun elementti oli pystyasennossa ja lukija lattiatason korkeudella. Näissä tapauksissa tunnisteen antennirakenne oli näkymättömässä kulmassa lukijan säteilykenttään nähden, mikä heikensi vastaanotetun signaalin voimakkuutta ja johti usein epäonnistuneisiin lukuihin. Tunnisteen antenni oli suunnattu pääasiassa vaakatasoon, kun taas lukijan antenni säteili pääosin pystysuunnassa, jolloin niiden välinen kenttäorientaatio ei ollut optimaalinen. Tämä vaikutti erityisesti UHF-taajuusalueella, jossa polarisaation ja suuntaavuuden yhteensopivuus on keskeinen lukematkan kannalta.

Useissa tapauksissa onnistunut luenta yläpinnasta edellytti hyvin pientä etäisyyttä tai lukijan nostamista samaan tasoon tunnisteen kanssa. Asennuksen jälkeen yläpinnan tunniste saatiin luettua joissain kohteissa, mutta yleensä vain, kun lukija voitiin kohdistaa lähes suoraan tunnisteen antennin tasoon. Tämä vahvistaa käsitystä, että tunnisteen ja lukijan välisen kenttägeometrian yhteensopivuus on ratkaiseva tekijä lukutuloksen onnistumisessa.

Työmaalle asennettu kiinteä RFID-portti tuotti vain vähän havaintoja. Portti havaitsi yksittäisiä tunnisteita, mutta useimmista elementeistä lukutapahtuma puuttui. Tämä viittaa siihen, että antennien korkeus, suuntaus ja ajoneuvon pysähtymiskohta eivät muodostaneet riittävän kattavaa lukukenttää. Lisäksi portin antennit olivat kiinteässä pystyasennossa, kun taas kuljetettujen elementtien tunnisteet sijaitsivat vaihtelevissa kulmissa ja korkeuksissa suhteessa antennikenttään, mikä heikensi luennan toistettavuutta.

Kun luenta tehtiin käsilukijalla asennuksen jälkeen ja tunniste oli esteettömästi saavutettavissa, päätytunnisteet saatiin luettua luotettavasti. Tällöin lukija ja tunniste voitiin asettaa toisiaan kohti samansuuntaisesti, jolloin antennien välinen polarisaatio vastasi optimaalisesti ja signaalin voimakkuus kasvoi.

Tulosten perusteella vaihtelu lukutuloksissa johtui ensisijaisesti tunnisteen orientaatiosta suhteessa lukijan antenniin, näkymäkulmasta ja rakenteiden vaikutuksesta antennikenttään. Kun tunniste oli asennettu niin, että sen antenni oli suunnattu samaan tasoon lukijan säteilykuvion kanssa, lukemat olivat toistettavia ja signaalin voimakkuus pysyi korkeana. Sen sijaan poikittainen tai yläviistoinen orientaatio heikensi kentän kytkeytymistä ja johti epävakaisiin lukutuloksiin. Näin ollen päätysijoitus osoittautui teknisesti toimivimmaksi ratkaisuksi, kun taas kiinteän portin kokoonpano ja antennien suuntaus vaativat jatko-optimointia, jotta automaattinen luenta onnistuisi luotettavasti kaikille elementeille.

<img width="1697" height="1135" alt="image" src="https://github.com/user-attachments/assets/9152cc62-d324-4f8d-a5f9-2e1717403efa" />

<img width="1697" height="1135" alt="image" src="https://github.com/user-attachments/assets/b01c301a-0b3a-4598-aaa6-7e74c7ebb2dc" />


<details> 
<Summary>Case 1. Koontitulokset</Summary>
  <table border="1" cellspacing="5" cellpadding="5">
<tbody>
<tr><td colspan="8"><br><strong>1: RFID-piirin asennus valmistettavaan betonielementtiin </strong><br><br></td>
</tr><tr>
      <td><strong>Elem. tunnus</strong></td>
      <td><strong>Asennus päivämäärä</strong></td>
      <td><strong>Raud.- verkko</strong></td>
      <td><strong>Valu- tapa</strong></td>
      <td><strong>Valo- kuva</strong></td>
      <td><strong>RFID tag sijainti</strong></td>
      <td><strong>RFID tag id</strong></td>
      <td><strong>RFID-tunnisteen asennus</strong></td>  
</tr><tr>
      <td rowspan="3">V-21004</td>
      <td rowspan="3">2024-08-19</td>
      <td rowspan="3">Kyllä</td>
      <td rowspan="3">Vaaka</td>
      <td rowspan="3">Kyllä</td>
      <td>@2</td>
      <td>0015</td>
      <td>↑ Elementin yläpinta: RFID-tagin orientaatio pituussuunnassa sivun mukaisesti </td>
</tr><tr>
      <td>@1L</td>
      <td>0013</td>
      <td>← Elementin vasen reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti </td>
</tr><tr>
      <td>@1R</td>
      <td>0014</td>
      <td>→ Elementin oikea reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti </td>
</tr><tr>
</tr><tr>
      <td rowspan="3">V-21005</td>
      <td rowspan="3">2024-08-16</td>
      <td rowspan="3">Kyllä</td>
      <td rowspan="3">Vaaka</td>
      <td rowspan="3">Ei</td>
      <td>@2</td>
      <td>000F</td>
      <td>↑ Elementin yläpinta: RFID-tagin orientaatio pituussuunnassa sivun mukaisesti </td>
</tr><tr>
      <td>@1L</td>
      <td>000D</td>
      <td>← Elementin vasen reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus surrilangalla raudoitus verkkoon</td>
</tr><tr>
      <td>@1R</td>
      <td>000E</td>
      <td>→ Elementin oikea reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus surrilangalla raudoitus verkkoon</td>
</tr><tr>
</tr><tr>
      <td rowspan="3">V-21009</td>
      <td rowspan="3">2024-08-16</td>
      <td rowspan="3">Kyllä</td>
      <td rowspan="3">Vaaka</td>
      <td rowspan="3">Kyllä</td>
      <td>@2</td>
      <td>0018</td>
      <td>↑ Elementin yläpinta: RFID-tagin orientaatio pituussuunnassa sivun mukaisesti </td>
</tr><tr>
      <td>@1L</td>
      <td>0016</td>
      <td>← Elementin vasen reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus surrilangalla raudoitus verkkoon</td>
</tr><tr>
      <td>@1R</td>
      <td>0017</td>
      <td>→ Elementin oikea reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus surrilangalla raudoitus verkkoon</td>
</tr><tr>
</tr><tr>
      <td rowspan="3">V-21019</td>
      <td rowspan="3">2024-08-19</td>
      <td rowspan="3">Kyllä</td>
      <td rowspan="3">Vaaka</td>
      <td rowspan="3">Kyllä</td>
      <td>@2</td>
      <td>001E</td>
      <td>↑ Elementin yläpinta: RFID-tagin orientaatio pituussuunnassa sivun mukaisesti </td>
</tr><tr>
      <td>@1L</td>
      <td>001C</td>
      <td>← Elementin vasen reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti </td>
</tr><tr>
      <td>@1R</td>
      <td>001D</td>
      <td>→ Elementin oikea reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti </td>
</tr><tr>
</tr><tr>
      <td rowspan="3">V-21305</td>
      <td rowspan="3">2024-08-14</td>
      <td rowspan="3">Kyllä</td>
      <td rowspan="3">Vaaka</td>
      <td rowspan="3">Kyllä</td>
      <td>@2</td>
      <td>0009</td>
      <td>↑ Elementin yläpinta: RFID-tagin orientaatio pituussuunnassa sivun mukaisesti </td>
</tr><tr>
      <td>@1L</td>
      <td>0007</td>
      <td>← Elementin vasen reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus surrilangalla raudoitus verkkoon</td>
</tr><tr>
      <td>@1R</td>
      <td>0008</td>
      <td>→ Elementin oikea reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus surrilangalla raudoitus verkkoon</td>
</tr><tr>
</tr><tr>
      <td rowspan="3">V-2502</td>
      <td rowspan="3">2024-08-13</td>
      <td rowspan="3">Kyllä</td>
      <td rowspan="3">Vaaka</td>
      <td rowspan="3">Kyllä</td>
      <td>@2</td>
      <td>0019</td>
      <td>↑ Elementin yläpinta: RFID-tagin orientaatio pituussuunnassa sivun mukaisesti </td>
</tr><tr>
      <td>@1L</td>
      <td>001A</td>
      <td>← Elementin vasen reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus vaarnaan naulalla.</td>
</tr><tr>
      <td>@1R</td>
      <td>001B</td>
      <td>→ Elementin oikea reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus vaarnaan naulalla.</td>
</tr><tr>
</tr><tr>
      <td rowspan="3">V-2509</td>
      <td rowspan="3">2024-08-12</td>
      <td rowspan="3">Kyllä</td>
      <td rowspan="3">Vaaka</td>
      <td rowspan="3">Kyllä</td>
      <td>@2</td>
      <td>0006</td>
      <td>↑ Elementin yläpinta: RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennettu valun aikana</td>
</tr><tr>
      <td>@1L</td>
      <td>0004</td>
      <td>← Elementin vasen reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus vaarnaan naulalla.</td>
</tr><tr>
      <td>@1R</td>
      <td>0005</td>
      <td>→ Elementin oikea reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus vaarnaan naulalla.</td>
</tr><tr>
</tr><tr>
      <td rowspan="3">V-2802</td>
      <td rowspan="3">2024-08-13</td>
      <td rowspan="3">Kyllä</td>
      <td rowspan="3">Vaaka</td>
      <td rowspan="3">Kyllä</td>
      <td>@2</td>
      <td>0003</td>
      <td>↑ Elementin yläpinta: RFID-tagin orientaatio pituussuunnassa sivun mukaisesti </td>
</tr><tr>
      <td>@1L</td>
      <td>0001</td>
      <td>← Elementin vasen reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus vaarnaan naulalla.</td>
</tr><tr>
      <td>@1R</td>
      <td>0002</td>
      <td>→ Elementin oikea reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus vaarnaan naulalla.</td>
</tr><tr>
</tr><tr>
      <td rowspan="3">V-2803</td>
      <td rowspan="3">2024-08-14</td>
      <td rowspan="3">Kyllä</td>
      <td rowspan="3">Vaaka</td>
      <td rowspan="3">Kyllä</td>
      <td>@2</td>
      <td>0012</td>
      <td>↑ Elementin yläpinta: RFID-tagin orientaatio pituussuunnassa sivun mukaisesti </td>
</tr><tr>
      <td>@1L</td>
      <td>0010</td>
      <td>← Elementin vasen reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus surrilangalla raudoitus verkkoon.</td>
</tr><tr>
      <td>@1R</td>
      <td>0011</td>
      <td>→ Elementin oikea reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus surrilangalla raudoitus verkkoon.</td>
</tr><tr>
</tr><tr>
      <td rowspan="3">V-2909</td>
      <td rowspan="3">2024-08-15</td>
      <td rowspan="3">Kyllä</td>
      <td rowspan="3">Vaaka</td>
      <td rowspan="3">Kyllä</td>
      <td>@2</td>
      <td>000C</td>
      <td>↑ Elementin yläpinta: RFID-tagin orientaatio pituussuunnassa sivun mukaisesti </td>
</tr><tr>
      <td>@1L</td>
      <td>000A</td>
      <td>← Elementin vasen reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti. Asennus surrilangalla raudoitus verkkoon.</td>
</tr><tr>
      <td>@1R</td>
      <td>000B</td>
      <td>→ Elementin oikea reuna: asennettu 1 m korkeuteen. RFID-tagin orientaatio pituussuunnassa sivun mukaisesti.  Asennus surrilangalla raudoitus verkkoon.</td>
</tr>
</tbody>
</table>










<table border="1" cellspacing="5" cellpadding="5">
<tbody>
<tr><td colspan="8"><br><strong>2: RFID-piirin luenta valmistuksen jälkeen</strong><br><br></td>
<tr><td colspan="8">Luenta toteutettiin käsilukijalla. Huom! Luenta toteutettin välivarastoinnin yhteydessä.</td>
</tr><tr>
      <td><strong>Elem. tunnus</strong></td>
      <td><strong>RFID-tag sijainti</strong></td>
      <td><strong>RFID tag id:</strong></td>
      <td><strong>Luenta onnistui</strong></td>
      <td><strong>Luenta-ajankohta</strong></td>
      <td><strong>Luentaetäisyys (mm):</strong></td>
      <td><strong>RSSI</strong></td>
      <td><strong>Havainnot</strong></td>  
</tr><tr>
      <td rowspan="3">V-21004</td>
      <td>@2</td>
      <td>0015</td>
      <td>Ei</td>
      <td>2024-08-20T13:57</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut maanpinnan tasolta (elementti varastoitu pystyasennossa)</td>
</tr><tr>
      <td>@1L</td>
      <td>0013</td>
      <td>Kyllä</td>
      <td>2024-08-20T13:57</td>
      <td>1500</td>
      <td>80</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä.</td>
</tr><tr>
      <td>@1R</td>
      <td>0014</td>
      <td>Kyllä</td>
      <td>2024-08-20T13:57</td>
      <td>1500</td>
      <td>80</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä.</td>
</tr><tr>
      </tr><tr>
      <td rowspan="3">V-21005</td>
      <td>@2</td>
      <td>000F</td>
      <td>Ei</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut maanpinnan tasolta (elementti varastoitu pystyasennossa)</td>
</tr><tr>
      <td>@1L</td>
      <td>000D</td>
      <td>Kyllä</td>
      <td>2024-08-19T12:37</td>
      <td>1500</td>
      <td>80</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä.</td>
</tr><tr>
      <td>@1R</td>
      <td>000E</td>
      <td>Kyllä</td>
      <td>2024-08-19T12:38</td>
      <td>1000</td>
      <td>65</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä.</td>
</tr><tr>
      <td rowspan="3">V-21009</td>
      <td>@2</td>
      <td>0018</td>
      <td>Kyllä</td>
      <td>2024-08-19T12:47</td>
      <td>1000</td>
      <td>63</td>
      <td>Luenta toteutettiin elementin yläpinnan tasolta (elementti pystyasennossa) </td>
</tr><tr>
      <td>@1L</td>
      <td>0016</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td>Luentaa ei suoritettu</td>
</tr><tr>
      <td>@1R</td>
      <td>0017</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td>Luentaa ei suoritettu</td>
</tr><tr>
      <td rowspan="3">V-21019</td>
      <td>@2</td>
      <td>001E</td>
      <td>Ei</td>
      <td>2024-08-20T13:54</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut maanpinnan tasolta (elementti varastoitu pystyasennossa)</td>
</tr><tr>
      <td>@1L</td>
      <td>001C</td>
      <td>Kyllä</td>
      <td>2024-08-20T13:54</td>
      <td>1500</td>
      <td>59</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä.</td>
</tr><tr>
      <td>@1R</td>
      <td>001D</td>
      <td>Kyllä</td>
      <td>2024-08-20T13:54</td>
      <td>1000</td>
      <td>60</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä.</td>
</tr><tr>
      <td rowspan="3">V-21305</td>
      <td>@2</td>
      <td>0009</td>
      <td>Ei</td>
      <td>2024-08-15T10:04</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut maanpinnan tasolta (elementti varastoitu pystyasennossa)</td>
</tr><tr>
      <td>@1L</td>
      <td>0007</td>
      <td>Kyllä</td>
      <td>2024-08-15T10:04</td>
      <td>500</td>
      <td>71</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä.</td>
</tr><tr>
      <td>@1R</td>
      <td>0008</td>
      <td>Kyllä</td>
      <td>2024-08-15T10:04</td>
      <td>500</td>
      <td>73</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä.</td>
</tr><tr>
      <td rowspan="3">V-2502</td>
      <td>@2</td>
      <td>0019</td>
      <td>Kyllä</td>
      <td>2024-08-16T10:21</td>
      <td>1500</td>
      <td>74</td>
      <td>Luenta toteutettiin elementin yläpinnan tasolta (elementti pystyasennossa)</td>
</tr><tr>
      <td>@1L</td>
      <td>001A</td>
      <td>Kyllä</td>
      <td>2024-08-16T10:19</td>
      <td>1500</td>
      <td>78</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä. </td>
</tr><tr>
      <td>@1R</td>
      <td>001B</td>
      <td>Kyllä</td>
      <td>2024-08-16T10:25</td>
      <td>1000</td>
      <td>63</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä.</td>
</tr><tr>
      <td rowspan="3">V-2509</td>
      <td>@2</td>
      <td>0006</td>
      <td>Kyllä</td>
      <td>2024-08-15T12:55</td>
      <td>2000</td>
      <td>53</td>
      <td>Luenta toteutettiin elementin yläpinnan tasolta (elementti pystyasennossa)</td>
</tr><tr>
      <td>@1L</td>
      <td>0004</td>
      <td>Kyllä</td>
      <td>2024-08-15T12:55</td>
      <td>1000</td>
      <td>60</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä.</td>
</tr><tr>
      <td>@1R</td>
      <td>0005</td>
      <td>Kyllä</td>
      <td>2024-08-15T12:55</td>
      <td>1000</td>
      <td>57</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä.</td>
</tr><tr>
      <td rowspan="3">V-2802</td>
      <td>@2</td>
      <td>0003</td>
      <td>Kyllä</td>
      <td>2024-08-16T10:20</td>
      <td>1500</td>
      <td>71</td>
      <td>Luenta toteutettiin elementin yläpinnan tasolta (elementti pystyasennossa) </td>
</tr><tr>
      <td>@1L</td>
      <td>0001</td>
      <td>Kyllä</td>
      <td>2024-08-16T10:20</td>
      <td>1500</td>
      <td>80</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä.</td>
</tr><tr>
      <td>@1R</td>
      <td>0002</td>
      <td>Kyllä</td>
      <td>2024-08-16T10:17</td>
      <td>1000</td>
      <td>74</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä. </td>
</tr><tr>
      <td rowspan="3">V-2803</td>
      <td>@2</td>
      <td>0012</td>
      <td>Ei</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut maanpinnan tasolta (elementti varastoitu pystyasennossa) </td>
</tr><tr>
      <td>@1L</td>
      <td>0010</td>
      <td>Kyllä</td>
      <td>2024-08-16T10:28</td>
      <td>1000</td>
      <td>58</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä. </td>
</tr><tr>
      <td>@1R</td>
      <td>0011</td>
      <td>Kyllä</td>
      <td>2024-08-16T10:29</td>
      <td>1000</td>
      <td>57</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä. </td>
</tr><tr>
      <td rowspan="3">V-2909</td>
      <td>@2</td>
      <td>000C</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut maanpinnan tasolta (elementti varastoitu pystyasennossa) </td>
</tr><tr>
      <td>@1L</td>
      <td>000A</td>
      <td>Kyllä</td>
      <td>2024-08-16T10:01</td>
      <td>1000</td>
      <td>58</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä. </td>
</tr><tr>
      <td>@1R</td>
      <td>000B</td>
      <td>Kyllä</td>
      <td>2024-08-16T10:01</td>
      <td>1000</td>
      <td>56</td>
      <td>Elementti varastoitu pystyasennossa. Luettu elementin päädystä. </td>
</tr>
</tr>
</tbody>
</table>
















<table border="1" cellspacing="5" cellpadding="5">
<tbody>
<tr><td colspan="8"><br><strong>3: RFID-piirin luenta työmaalla vastaanoton yhteydessä</strong><br><br></td>
<tr><td colspan="8">Luenta toteutettiin työmaan elementinpurkupaikalle asennetulla kiinteällä portilla sekä satunnaisesti käsilukijalla.</td>
</tr><tr>
      <td><strong>Elem. tunnus</strong></td>
      <td><strong>RFID-tag sijainti:</strong></td>     
      <td><strong>RFID tag id:</strong></td>
      <td><strong>Luenta onnistui</strong></td>
      <td><strong>Luenta-ajankohta</strong></td>
      <td><strong>Luentaetäisyys (mm):</strong></td>
      <td><strong>RSSI</strong></td>
      <td><strong>Havainnot</strong></td>  
</tr><tr>
      <td rowspan="3">V-21004</td>
      <td>@2</td>
      <td>0015</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td>@1L</td>
      <td>0013</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td>@1R</td>
      <td>0014</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td rowspan="3">V-21005</td>
      <td>@2</td>
      <td>000F</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td>@1L</td>
      <td>000D</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td>@1R</td>
      <td>000E</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td rowspan="3">V-21009</td>
      <td>@2</td>
      <td>0018</td>
      <td>Kyllä</td>
      <td>2024-09-13T10:59 </td>
      <td> - </td>
      <td> - </td>
      <td>Elementti luettiin työmaan portilla kiinteällä RFID-lukijalla</td>
</tr><tr>
      <td>@1L</td>
      <td>0016</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td>@1R</td>
      <td>0017</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td rowspan="3">V-21019</td>
      <td>@2</td>
      <td>001E</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td>@1L</td>
      <td>001C</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td>@1R</td>
      <td>001D</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td rowspan="3">V-21305</td>
      <td>@2</td>
      <td>0009</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td>@1L</td>
      <td>0007</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td>@1R</td>
      <td>0008</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td rowspan="3">V-2502</td>
      <td>@2</td>
      <td>0019</td>
      <td>Kyllä</td>
      <td>2024-09-09T08:45</td>
      <td>1500</td>
      <td>77</td>
      <td>Luenta suoritettiin käsilukijalla viistosti elementtivakilta kurottaen elementin päälle. </td>
</tr><tr>
      <td>@1L</td>
      <td>001A</td>
      <td>Kyllä</td>
      <td>2024-09-09T08:45</td>
      <td>3000</td>
      <td>80</td>
      <td>Luenta suoritettiin varastointipaikalla noin 3000 mm etäisyydeltä elementin päädystä. </td>
</tr><tr>
      <td>@1R</td>
      <td>001B</td>
      <td>Kyllä</td>
      <td>2024-09-09T08:45</td>
      <td>500</td>
      <td>79</td>
      <td>Luenta suoritettiin käsilukijalla elementtivakilta alaviistoon noin 500 mm etäisyydeltä. </td>
</tr><tr>
      <td rowspan="3">V-2509</td>
      <td>@2</td>
      <td>0006</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td>@1L</td>
      <td>0004</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td>@1R</td>
      <td>0005</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td rowspan="3">V-2802</td>
      <td>@2</td>
      <td>0003</td>
      <td>Ei</td>
      <td>2024-09-02T10:25</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut käsilukijalla. </td>
</tr><tr>
      <td>@1L</td>
      <td>0001</td>
      <td>Kyllä</td>
      <td>2024-09-02T10:25 (kiinteän lukuaika?)</td>
      <td>500</td>
      <td>75</td>
      <td>Luenta suoritettiin noin 500 mm etäisyydeltä elementin ollessa varastoituna elementtivakissa. ELEMENTTI LUETTIIN MYÖS TYÖMAAN KIINTEÄLLÄ PORTILLA </td>
</tr><tr>
      <td>@1R</td>
      <td>0002</td>
      <td>Kyllä</td>
      <td>2024-09-02T10:25</td>
      <td>1000</td>
      <td>78</td>
      <td>Luenta suoritettiin noin 1000 mm etäisyydeltä elementin ollessa varastoituna elementtivakissa. </td>
</tr><tr>
      <td rowspan="3">V-2803</td>
      <td>@2</td>
      <td>0012</td>
      <td>Ei</td>
      <td>2024-08-16T10:28</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td>@1L</td>
      <td>0010</td>
      <td>Ei</td>
      <td>2024-08-16T10:28</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td>@1R</td>
      <td>0011</td>
      <td>Kyllä</td>
      <td>2024-08-16T10:28</td>
      <td>750</td>
      <td>57</td>
      <td>Elementin luenta suoritettiin noin 750 mm etäisyydeltä elementin ollessa varastoituna elementtivakissa. </td>
</tr><tr>
      <td rowspan="3">V-2909</td>
      <td>@2</td>
      <td>000C</td>
      <td>Ei</td>
      <td>2024-08-16T10:01</td>
      <td> - </td>
      <td> - </td>
      <td> - </td>
</tr><tr>
      <td>@1L</td>
      <td>000A</td>
      <td>Kyllä</td>
      <td>2024-08-16T10:01</td>
      <td>1000</td>
      <td>57</td>
      <td>Luenta suoritettiin noin 500 mm etäisyydeltä elementtivakissa.  </td>
</tr><tr>
      <td>@1R</td>
      <td>000B</td>
      <td>Kyllä</td>
      <td>2024-08-16T10:01</td>
      <td>1000</td>
      <td>56</td>
      <td>Luenta suoritettiin käsilukijalla noin 1500 mm etäisyydeltä elementin päädystä. </td>
</tr>
</tr>
</tbody>
</table>











<table border="1" cellspacing="5" cellpadding="5">
<tbody>
<tr><td colspan="9"><br><strong>4: RFID-piirin luenta työmaalla asennuksen jälkeen</strong><br><br></td>
<tr><td colspan="9">Luenta toteutettiin käsilukijalla.</td>
</tr><tr>
      <td><strong>Elem. tunnus</strong></td>
      <td><strong>Asennus-sijainti (kerros)</strong></td>
      <td><strong>RFID-tag sijainti:</strong></td>     
      <td><strong>RFID tag id:</strong></td>
      <td><strong>Luenta onnistui</strong></td>
      <td><strong>Luenta-ajankohta</strong></td>
      <td><strong>Luentaetäisyys (mm):</strong></td>
      <td><strong>RSSI</strong></td>
      <td><strong>Havainnot</strong></td>  
</tr><tr>
      <td rowspan="3">V-21004</td>
      <td rowspan="3">13</td>
      <td>@2</td>
      <td>0015</td>
      <td>Ei</td>
      <td>2024-10-16T12:56</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut käsilukijalla.</td>
</tr><tr>
      <td>@1L</td>
      <td>0013</td>
      <td>Kyllä</td>
      <td>2024-10-16T12:51</td>
      <td>1000</td>
      <td>71</td>
      <td>Luenta suoritettiin noin 1000mm etäisyydeltä elementistä, pystysaumat pumppaamatta.</td>
</tr><tr>
      <td>@1R</td>
      <td>0014</td>
      <td>Kyllä</td>
      <td>2024-10-16T12:54</td>
      <td>150</td>
      <td>72</td>
      <td>Luenta suoritettiin kohtisuoraan elementistä noin 150 mm etäisyydeltä (molemmin puolin elementtiä), pystysaumat pumppaamatta. </td>
</tr><tr>
      <td rowspan="3">V-21005</td>
      <td rowspan="3">13</td>
      <td>@2</td>
      <td>000F</td>
      <td>Ei</td>
      <td>2024-10-15T12:54</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut käsilukijalla asennuksen jälkeen. </td>
</tr><tr>
      <td>@1L</td>
      <td>000D</td>
      <td>Kyllä</td>
      <td>2024-10-15T12:48</td>
      <td>1000</td>
      <td>71</td>
      <td>Luenta suoritettiin kohtisuoraan elementtiin nähden noin 1000 mm etäisyydeltä. </td>
</tr><tr>
      <td>@1R</td>
      <td>000E</td>
      <td>Kyllä</td>
      <td>2024-10-15T12:55</td>
      <td>300</td>
      <td>76</td>
      <td>Luenta suoritettiin viistosti elementtiin nähden noin 300 mm etäisyydeltä, pystysaumat pumppaamatta. </td>
</tr><tr>
      <td rowspan="3">V-21009</td>
      <td rowspan="3">10</td>
      <td>@2</td>
      <td>0018</td>
      <td>Ei</td>
      <td>2024-10-02T14:21</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut työmaalla normaalilta seisontakorkeudelta. </td>
</tr><tr>
      <td>@1L</td>
      <td>0016</td>
      <td>Kyllä</td>
      <td>2024-10-02T14:21</td>
      <td>100</td>
      <td>56</td>
      <td>Luenta suoritettiin noin 100 mm etäisyydeltä, pystysaumat pumpattu. </td>
</tr><tr>
      <td>@1R</td>
      <td>0017</td>
      <td>Kyllä</td>
      <td>2024-10-02T14:21</td>
      <td>100</td>
      <td>59</td>
      <td>Luenta suoritettiin 100 mm etäisyydeltä elementistä, pystysaumat pumpattuna. </td>
</tr><tr>
      <td rowspan="3">V-21019</td>
      <td rowspan="3">11</td>
      <td>@2</td>
      <td>001E</td>
      <td>Ei</td>
      <td>2024-10-15T12:59</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut asennuksen jälkeen käsilukijalla. </td>
</tr><tr>
      <td>@1L</td>
      <td>001C</td>
      <td>Kyllä</td>
      <td>2024-10-15T12:59</td>
      <td>100</td>
      <td>58</td>
      <td>Luenta suoritettiin käsilukijalla noin 100 mm päästä kohtisuoraan elementtiin nähden, pystysaumat pumpattu. </td>
</tr><tr>
      <td>@1R</td>
      <td>001D</td>
      <td>Kyllä</td>
      <td>2024-10-15T12:59</td>
      <td>100</td>
      <td>65</td>
      <td>Luenta suoritettiin kohtisuoraan käsilukijalla noin 100 mm etäisyydeltä, pystysaumat pumpattu. </td>
</tr><tr>
      <td rowspan="3">V-21305</td>
      <td rowspan="3">13</td>
      <td>@2</td>
      <td>0009</td>
      <td>Ei</td>
      <td>2024-10-15T12:49</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut käsilukijalla asennuksen jälkeen. </td>
</tr><tr>
      <td>@1L</td>
      <td>0007</td>
      <td>Kyllä</td>
      <td>2024-10-15T12:47</td>
      <td>2000</td>
      <td>70</td>
      <td>Luenta suoritettiin käytävän puolelta viistosti noin 2000 mm etäisyydeltä elementistä, pystysaumat pumppaamatta. </td>
</tr><tr>
      <td>@1R</td>
      <td>0008</td>
      <td>Kyllä</td>
      <td>2024-10-15T12:49</td>
      <td>1000</td>
      <td>75</td>
      <td>Luenta suoritettiin noin 1000 mm etäisyydeltä kohtisuoraan elementtiin nähden, saumat pumppaamatta ja paljon holvitukia edessä. </td>
</tr><tr>
      <td rowspan="3">V-2502</td>
      <td rowspan="3">9</td>
      <td>@2</td>
      <td>0019</td>
      <td>Kyllä</td>
      <td>2024-09-18T12:45</td>
      <td>1000</td>
      <td>72</td>
      <td>Luenta suoritettiin alaviistosta noin 1000 mm etäisyydeltä, holvi valettu.</td>
</tr><tr>
      <td>@1L</td>
      <td>001A</td>
      <td>Kyllä</td>
      <td>2024-09-18T12:45</td>
      <td>3500</td>
      <td>70</td>
      <td>Luenta suoritettiin kohtisuoraan elementtiin nähden noin 3500 mm etäisyydeltä, pystysaumat pumppaamatta. </td>
</tr><tr>
      <td>@1R</td>
      <td>001B</td>
      <td>Kyllä</td>
      <td>2024-09-18T12:45</td>
      <td>2000</td>
      <td>69</td>
      <td>Luenta suoritettiin noin 2000 mm etäisyydeltä viistosti, pystysaumat pumppaamatta.</td>
</tr><tr>
      <td rowspan="3">V-2509</td>
      <td rowspan="3">6</td>
      <td>@2</td>
      <td>0006</td>
      <td>Kyllä</td>
      <td>2024-10-02T12:59</td>
      <td>300</td>
      <td>57</td>
      <td>Luenta tapahtui alaviistosta tikkaiden päältä noin 300 mm etäisyydeltä. Saumat pumpattu/valettu. </td>
</tr><tr>
      <td>@1L</td>
      <td>0004</td>
      <td>Kyllä</td>
      <td>2024-10-02T12:59</td>
      <td>500</td>
      <td>56</td>
      <td>Havainnot: Luenta suoritettu kohtisuoraan noin 500 mm etäisyydeltä. Elementtisaumat valettu/pumpattu. 2024-09-02: Luenta suoritettu myös elementin toiselta puolelta noin 50 mm etäisyydeltä. </td>
</tr><tr>
      <td>@1R</td>
      <td>0005</td>
      <td>Kyllä</td>
      <td>2024-10-02T12:59</td>
      <td>1000</td>
      <td>58</td>
      <td>Luettu kohtisuoraan noin 1000 mm etäisyydeltä. Elementtisaumat pumpattu/valettu. 2024-09-02: Luenta suoritettu myös elementin toiselta puolen noin 50 mm etäisyydeltä, RSSI 59. </td>
</tr><tr>
      <td rowspan="3">V-2802</td>
      <td rowspan="3">8</td>
      <td>@2</td>
      <td>0003</td>
      <td>Ei</td>
      <td>2024-09-09T08:57</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut, elementin keskellä hormi ja toisella puolella KPH-moduuli.</td>
</tr><tr>
      <td>@1L</td>
      <td>0001</td>
      <td>Kyllä</td>
      <td>2024-09-09T08:57</td>
      <td>2000</td>
      <td>77</td>
      <td>Luenta suoritettiin noin 2000 mm etäisyydeltä viistosti. Pystysaumat pumppaamatta.</td>
</tr><tr>
      <td>@1R</td>
      <td>0002</td>
      <td>Kyllä</td>
      <td>2024-09-09T08:57</td>
      <td>300</td>
      <td>77</td>
      <td>Luenta suoritettiin kohtisuoraan noin 300 mm etäisyydeltä elementistä. Pystysaumat pumppaamatta. </td>
</tr><tr>
      <td rowspan="3">V-2803</td>
      <td rowspan="3">8</td>
      <td>@2</td>
      <td>0012</td>
      <td>Ei</td>
      <td>2024-09-09T09:01</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut ainakaan ilman tikkaita, tikkaita ei ollut saatavilla. </td>
</tr><tr>
      <td>@1L</td>
      <td>0010</td>
      <td>Kyllä</td>
      <td>2024-09-09T09:01</td>
      <td>100</td>
      <td>59</td>
      <td>Luenta suoritettiin kohtisuoraan noin 100 mm etäisyydeltä, pystysaumat pumppaamatta. </td>
</tr><tr>
      <td>@1R</td>
      <td>0011</td>
      <td>Kyllä</td>
      <td>2024-09-09T09:01</td>
      <td>100</td>
      <td>57</td>
      <td>Luenta suoritettiin kohtisuoraan noin 100 mm etäisyydeltä, pystysaumat pumppaamatta. </td>
</tr><tr>
      <td rowspan="3">V-2909</td>
      <td rowspan="3">9</td>
      <td>@2</td>
      <td>000C</td>
      <td>Ei</td>
      <td>2024-09-18T12:39</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta ei onnistunut lattialta käsilukijalla. </td>
</tr><tr>
      <td>@1L</td>
      <td>000A</td>
      <td>Kyllä</td>
      <td>2024-09-18T12:39</td>
      <td>500</td>
      <td>58</td>
      <td>Luenta suoritettiin kohtisuoraan elementtiin nähden noin 500 mm etäisyydeltä, pystysaumat pumppaamatta. Luenta suoritettiin myös toiselta puolen elementtiä noin 500 mm etäisyydeltä.  </td>
</tr><tr>
      <td>@1R</td>
      <td>000B</td>
      <td>Kyllä</td>
      <td>2024-09-18T12:39</td>
      <td>1500; 100</td>
      <td>55; 63</td>
      <td>Luenta suoritettiin viistosti elementtiin nähden noin 1500 mm etäisyydeltä (RSSI 55), pystysaumat pumppaamatta. Toiselta puolen elementti noin 100 mm etäisyydeltä (RSSI 63). </td>
</tr>
</tr>
</tbody>
</table>
</details>

### 4.2 Case 2: RFID-tunnisteiden asennuksen ja lukutulosten analyysi

Toisessa tapauksessa käytettiin Confidex Ironside Classic- ja Confidex Survivor -tunnisteita. Kiinteä FR22-lukija antenneineen asennettiin tehtaalle tuulikaapin sisäpuolelle, jossa sillä seurattiin elementtien siirtymistä tuotannosta varastoon. Tässä aineistossa ei raportoitu vastaanoton porttilukuja, joten analyysi perustuu työmaan asennuksen jälkeisiin käsilukuihin.

Yläpintaan sijoitetut tunnisteet (@2L ja @2R) saatiin luettua useissa elementeissä vain 100–150 millimetrin etäisyydeltä, ja usein vasta, kun lukija voitiin nostaa yläreunan tasolle. Tämä toistui useilla elementeillä, kuten VG-1701, VG-1710 ja VG-1711. Reunatunnisteet (@1LF ja @1RF) tuottivat selvästi parempia tuloksia. Niitä saatiin luettua 300–750 millimetrin etäisyydeltä, ja RSSI-arvot olivat useissa tapauksissa 65–75.

Aineistossa esiintyi myös elementtejä, joista tunnisteita ei saatu luettua lainkaan, vaikka luenta toistettiin useita kertoja eri suunnista. Havaintojen perusteella epäonnistumiset johtuivat usein tunnisteen väärästä sijoituksesta tai varjostuksesta. Esimerkiksi elementillä VG-1702 tunniste oli asennettu väärälle puolelle, ja elementillä VG-1813 epäiltiin virheellistä asennussuuntaa. Näissä tapauksissa luenta ei onnistunut lainkaan, mikä osoittaa asennusdokumentoinnin ja koeluennan tärkeyden.

Tulokset osoittivat, että reunasijoitus noin 1,25–1,35 metrin korkeudelle on tässä ympäristössä toimivin ratkaisu. Yläpinnan tunniste soveltuu vain tilanteisiin, joissa luenta voidaan tehdä turvallisesti korotetulta työskentelytasolta. Kiinteän tehtaan portin toimintaa ei voitu arvioida vastaanoton näkökulmasta, koska porttilokidataa ei ollut käytettävissä.

Yhteenvetona voidaan todeta, että RFID-tunnisteet toimivat teknisesti betonielementeissä, mutta luennan toistettavuus riippuu tunnisteen sijainnista, antennien asemoinnista ja asennuksen laadusta. Kun tunniste sijoitetaan päätyyn noin metrin korkeudelle, antennit suunnataan kulkulinjan mukaisesti ja asennus varmistetaan koeluennalla, järjestelmä tuottaa toistettavia lukutuloksia myös haastavissa olosuhteissa. Ilman näitä toimenpiteitä luentatulokset jäävät satunnaisiksi ja porttiluentojen hyöty jää rajalliseksi.

<img width="1768" height="1024" alt="image" src="https://github.com/user-attachments/assets/a358c37c-4288-4b5a-93f7-0fad83ef4b03" />



<details> 
<Summary>Case 2. Koontitulokset</Summary>
<table border="1" cellspacing="5" cellpadding="5">
<tbody>
<tr><td colspan="8"><br><strong>1: RFID-piirin asennus valmistettavaan betonielementtiin </strong><br><br></td>
</tr><tr>
      <td><strong>Elem. tunnus</strong></td>
      <td><strong>Asennus päivämäärä</strong></td>
      <td><strong>Raud.- verkko</strong></td>
      <td><strong>Valu- tapa</strong></td>
      <td><strong>Valo- kuva</strong></td>
      <td><strong>RFID tag sijainti</strong></td>
      <td><strong>RFID tag id</strong></td>
      <td><strong>RFID-tunnisteen asennus</strong></td>  
</tr><tr>
      <td>VG-1701</td>
      <td>2024-10-15</td>
      <td>Kyllä</td>
      <td>Patterimuotti</td>
      <td>Kyllä</td>
      <td>@2L</td>
      <td>0015</td>
      <td>↑ Elementin yläpinta: Elementin päästä 1000 mm-1200 mm, vasensivu</td>
</tr><tr>
      <td>VG-1702</td>
      <td>2024-10-15</td>
      <td>Ei</td>
      <td>Patterimuotti</td>
      <td>Kyllä</td>
      <td>@1LF</td>
      <td>0008</td>
      <td>← Elementin vasen reuna: Korkeus 1250 mm-1350 mm</td>
</tr><tr>
      <td>VG-1707</td>
      <td>2024-10-15</td>
      <td>Kyllä</td>
      <td>Patterimuotti</td>
      <td>Kyllä</td>
      <td>@1LF</td>
      <td>0009</td>
      <td>← Elementin vasen reuna: Korkeus 1250 mm-1350 mm</td>
</tr><tr>
      <td>VG-1710</td>
      <td>2024-10-15</td>
      <td>Kyllä</td>
      <td>Patterimuotti</td>
      <td>Kyllä</td>
      <td>@2L</td>
      <td>0014</td>
      <td>↑ Elementin yläpinta: Elementin päästä 1000 mm-1200 mm, vasensivu</td>
</tr><tr>
      <td>VG-1711</td>
      <td>2024-10-15</td>
      <td>Kyllä</td>
      <td>Patterimuotti</td>
      <td>Kyllä</td>
      <td>@2L</td>
      <td>0013</td>
      <td>↑ Elementin yläpinta: Elementin päästä 1000 mm-1200 mm, vasensivu</td>
</tr><tr>
      <td>VG-1724</td>
      <td>2024-10-15</td>
      <td>Ei</td>
      <td>Patterimuotti</td>
      <td>Kyllä</td>
      <td>@1LF</td>
      <td>0007</td>
      <td>← Elementin vasen reuna: Korkeus 1250 mm-1350 mm</td>
</tr><tr>
      <td>VG-1802</td>
      <td>2024-10-25</td>
      <td>Ei</td>
      <td>Patterimuotti</td>
      <td>Kyllä</td>
      <td>@1</td>
      <td>0010</td>
      <td>↔ Elementin vasen tai oikea reuna: Korkeus 1250 mm-1350 mm </td>
</tr><tr>
      <td>VG-1807</td>
      <td>2024-10-25</td>
      <td>Kyllä</td>
      <td>Patterimuotti</td>
      <td>Kyllä</td>
      <td>@1</td>
      <td>0012</td>
      <td>↔ Elementin vasen tai oikea reuna: Korkeus 1250 mm-1350 mm </td>
</tr><tr>
      <td rowspan="2">VG-1812</td>
      <td rowspan="2">2024-10-25</td>
      <td rowspan="2">Ei</td>
      <td rowspan="2">Vaaka</td>
      <td rowspan="2">Kyllä</td>
      <td>@2L</td>
      <td>0001</td>
      <td>↑ Elementin yläpinta: Elementin päästä 1000 mm-1200 mm, vasensivu</td>
</tr><tr>
      <td>@1RF</td>
      <td>0016</td>
      <td>→ Elementin oikea reuna: Korkeus 1250 mm-1350 mm</td>
</tr><tr>
      <td rowspan="2">VG-1813</td>
      <td rowspan="2">2024-10-25</td>
      <td rowspan="2">Ei</td>
      <td rowspan="2">Vaaka</td>
      <td rowspan="2">Kyllä</td>
      <td>@2R</td>
      <td>0002</td>
      <td>↑ Elementin yläpinta: Elementin päästä 1000 mm-1200 mm, vasensivu</td>
</tr><tr>
      <td>@1RF</td>
      <td>0017</td>
      <td>→ Elementin oikea reuna: Korkeus 1250 mm-1350 mm. </td>
</tr><tr>
      <td rowspan="2">VG1816</td>
      <td rowspan="2">2024-10-25</td>
      <td rowspan="2">Ei</td>
      <td rowspan="2">Vaaka</td>
      <td rowspan="2">Kyllä</td>
      <td>@1LF</td>
      <td>0003</td>
      <td>← Elementin vasen reuna: Korkeus 1250 mm-1350 mm</td>
</tr><tr>
      <td>@1RF</td>
      <td>0018</td>
      <td>→ Elementin oikea reuna: Korkeus 1250 mm-1350 mm</td>
</tr><tr>
      <td>VG-1824</td>
      <td>2024-10-25</td>
      <td>Ei</td>
      <td>Patterimuotti</td>
      <td>Kyllä</td>
      <td>@1</td>
      <td>0011</td>
      <td>↔ Elementin vasen tai oikea reuna: Korkeus 1250 mm-1350 mm </td>
</tr><tr>
      <td rowspan="2">VG-1919</td>
      <td rowspan="2">2024-11-05</td>
      <td rowspan="2">Ei</td>
      <td rowspan="2">Patterimuotti</td>
      <td rowspan="2">Kyllä</td>
      <td>@1LF</td>
      <td>0004</td>
      <td>← Elementin vasen reuna: Korkeus 1250 mm-1350 mm</td>
</tr><tr>
      <td>@1RF</td>
      <td>0019</td>
      <td>→ Elementin oikea reuna: Korkeus 1250 mm-1350 mm</td>
</tr><tr>
      <td>VG-1920</td>
      <td>2024-11-05</td>
      <td>Ei</td>
      <td>Patterimuotti</td>
      <td>Kyllä</td>
      <td>@1LF</td>
      <td>0005</td>
      <td>← Elementin vasen reuna: Korkeus 1250 mm-1350 mm</td>
</tr><tr>
      <td>VG-1922</td>
      <td>2024-11-05</td>
      <td>Kyllä</td>
      <td>Patterimuotti</td>
      <td>Kyllä</td>
      <td>@1LF</td>
      <td>0006</td>
      <td>← Elementin vasen reuna: Korkeus 1250 mm-1350 mm</td>
</tr>
</tbody>
</table>


<table border="1" cellspacing="5" cellpadding="5">
<tbody>
<tr><td colspan="8"><br><strong>2: RFID-piirin luenta valmistuksen jälkeen</strong><br><br></td>
<tr><td colspan="8">Ei toteutettu</td>
</tr>
</tbody>
</table>


<table border="1" cellspacing="5" cellpadding="5">
<tbody>
<tr><td colspan="8"><br><strong>3: RFID-piirin luenta työmaalla vastaanoton yhteydessä</strong><br><br></td>
<tr><td colspan="8">Ei toteutettu</td>
</tr>
</tbody>
</table>




<table border="1" cellspacing="5" cellpadding="5">
<tbody>
<tr><td colspan="9"><br><strong>4: RFID-piirin luenta työmaalla asennuksen jälkeen</strong><br><br></td>
<tr><td colspan="9">Luenta toteutettiin käsilukijalla.</td>
</tr><tr>
      <td><strong>Elem. tunnus</strong></td>
      <td><strong>Asennus-sijainti (kerros)</strong></td>
      <td><strong>RFID-tag sijainti:</strong></td>     
      <td><strong>RFID tag id:</strong></td>
      <td><strong>Luenta onnistui</strong></td>
      <td><strong>Luenta-ajankohta</strong></td>
      <td><strong>Luentaetäisyys (mm):</strong></td>
      <td><strong>RSSI</strong></td>
      <td><strong>Havainnot</strong></td>  
</tr><tr>
      <td>VG-1701</td>
      <td>7</td>
      <td>@2L</td>
      <td>0015</td>
      <td>Kyllä</td>
      <td>2024-11-28T14:10 </td>
      <td>~125</td>
      <td>75</td>
      <td>Luenta suoritettiin 100–150 mm etäisyydeltä elementin yläreunasta ja onnistui molemmilta puolilta seinää. Kuitenkin yläpuolelta "lattian tasolta" ei luenta onnistunut kummaltakaan puolelta. Käyttäjä (176 cm) joutui kurkottamaan elementin yläreunaan saadakseen luennon onnistumaan. Luennassa tarvetta A-pukille. RFID-tunniste oli asennettu 1000–1200 mm etäisyydelle elementin oikealta puolelta. </td>
</tr><tr>
      <td>VG-1702</td>
      <td>7</td>
      <td>@1LF</td>
      <td>0008</td>
      <td>Kyllä</td>
      <td>2024-11-28T14:05</td>
      <td>600</td>
      <td>76</td>
      <td>Luenta suoritettiin noin 600 mm etäisyydeltä elementin pinnasta huoneistonpuolella. Myös käytävän puolella luettaessa laite pystyi löytämään tunnistimen, mutta laite oli seinänpinnan tuntumassa (50 mm). Lisäksi RFID-TUNNISTE oli asennettu väärin OIKEALLE puolelle elementtiä</td>
</tr><tr>
      <td>VG-1707</td>
      <td>7</td>
      <td>@1LF</td>
      <td>0009</td>
      <td>Kyllä</td>
      <td>2024-11-28T12:57</td>
      <td>750</td>
      <td>74</td>
      <td>Luenta suoritettiin noin 750 mm etäisyydeltä elementin pinnasta huoneistonpuolella. Myös käytävän puolella luettaessa laite pystyi löytämään tunnistimen, mutta laite oli seinänpinnan tuntumassa (50 mm).</td>
</tr><tr>
      <td>VG-1710</td>
      <td>7</td>
      <td>@2L</td>
      <td>0014</td>
      <td>Kyllä</td>
      <td>2024-11-28T14:21 </td>
      <td>~125</td>
      <td>75</td>
      <td>Luenta onnistui noin 100–150 mm etäisyydeltä elementin yläreunasta molemmilta puolilta, mutta yläpuolelta (lattian tasolta) ei kummaltakaan puolelta. Käyttäjän (176 cm) täytyi kurkottaa elementin yläreunaan, jotta luenta onnistui. Luennassa tarvetta A-pukille. RFID-tunniste oli asennettu 1000–1200 mm päähän elementin vasemmalta puolelta. </td>
</tr><tr>
      <td>VG-1711</td>
      <td>7</td>
      <td>@2L</td>
      <td>0013</td>
      <td>Kyllä</td>
      <td>2024-11-28T14:17</td>
      <td>~125</td>
      <td>73</td>
      <td>Luenta suoritettiin 100–150 mm etäisyydeltä elementin yläreunasta, elementin toiselta puolelta ei saatu onnistunutta lukutapahtumaa portaikon vuoksi. Porrasnousun puolelta päästiin lähemmäksi saumakohtaa, mutta lukeminen epäonnistui. Yläpuolisesta kerroksesta ei myöskään saatu luettua kummaltakaan puolelta. Käyttäjän (176 cm) oli kurkotettava elementin yläreunaan luennan onnistumiseksi. RFID-tunniste oli asennettu 1000–1200 mm etäisyydelle elementin oikealta puolelta. Luennassa tarvetta A-pukille. </td>
</tr><tr>
      <td>VG-1724</td>
      <td>7</td>
      <td>@1LF</td>
      <td>0007</td>
      <td>Ei</td>
      <td>2024-11-28T14:29</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta tehtiin useampaan kertaan molemmilta puolilta ja -sivuilta elementtiä, mutta RFID-TUNNISTEEN signaalia ei paikallistettu. </td>
</tr><tr>
      <td>VG-1802</td>
      <td>8</td>
      <td>@1</td>
      <td>0010</td>
      <td>Ei</td>
      <td>2024-11-28T12:56</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta tehtiin useampaan kertaan molemmilta puolilta ja -sivuilta elementtiä, mutta RFID-TUNNISTEEN signaalia ei paikallistettu. </td>
</tr><tr>
      <td>VG-1807</td>
      <td>8</td>
      <td>@1</td>
      <td>0012</td>
      <td>Ei</td>
      <td>2024-11-28T13:00</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta tehtiin useampaan kertaan molemmilta puolilta ja -sivuilta elementtiä, mutta RFID-TUNNISTEEN signaalia ei paikallistettu. </td>
</tr><tr>
      <td rowspan="2">VG-1812</td>
      <td rowspan="2">8</td>
      <td>@2L</td>
      <td>0001</td>
      <td>Kyllä</td>
      <td>2024-11-28T14:42</td>
      <td>~125</td>
      <td>53</td>
      <td>Luenta suoritettiin noin 100 mm-150 mm etäisyydeltä elementin yläreunasta huoneiston puolelta</td>
</tr><tr>
      <td>@1RF</td>
      <td>0016</td>
      <td>Kyllä</td>
      <td>2024-11-28T14:42</td>
      <td>600</td>
      <td>78</td>
      <td>Luenta onnistui 600 mm päästä. Seinän takan hissikuilu, josta ei mitattu arvoja</td>
</tr><tr>
      <td rowspan="2">VG-1813</td>
      <td rowspan="2">8</td>
      <td>@2L?</td>
      <td>0002</td>
      <td>Ei</td>
      <td>2024-11-28T12:39</td>
      <td> - </td>
      <td> - </td>
      <td>Tunnistinta ei löytynyt. RFID-tunnistin yritetty lukea vasemmasta yläreunasta. Epäilty, että tunnistin asennettu virheellisesti oikealle puolelle nostolenkin kohdalle.</td>
</tr><tr>
      <td>@1RF</td>
      <td>0017</td>
      <td>Kyllä</td>
      <td>2024-11-28T12:39</td>
      <td>600</td>
      <td>78</td>
      <td>Luenta onnistui 600 mm päästä. Seinän takan hissikuilu, josta ei mitattu arvoja</td>
</tr><tr>
      <td rowspan="2">VG1816</td>
      <td rowspan="2">8</td>
      <td>@1LF</td>
      <td>0003</td>
      <td>Kyllä</td>
      <td>2024-11-28T14:40</td>
      <td>600</td>
      <td>31</td>
      <td>Luenta onnistui 600 mm päästä</td>
</tr><tr>
      <td>@1RF</td>
      <td>0018</td>
      <td>Kyllä</td>
      <td>2024-11-28T14:40</td>
      <td>300</td>
      <td>54</td>
      <td>Luenta onnistui 300 mm päästä </td>
</tr><tr>
      <td>VG-1824</td>
      <td>8</td>
      <td>@1</td>
      <td>0011</td>
      <td>Ei</td>
      <td>2024-11-28T13:07</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta tehtiin useampaan kertaan molemmilta puolilta ja -sivuilta elementtiä, mutta RFID-TUNNISTEEN signaalia ei paikallistettu. </td>
</tr><tr>
      <td rowspan="2">VG-1919</td>
      <td rowspan="2">9</td>
      <td>@1LF</td>
      <td>0004</td>
      <td>Ei</td>
      <td>2024-11-28T13:30</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta tehtiin useampaan kertaan molemmilta puolilta ja -sivuilta elementtiä, mutta RFID-tunnistetta ei paikallistettu.</td>
</tr><tr>
      <td>@1RF</td>
      <td>0019</td>
      <td>Ei</td>
      <td>2024-11-28T13:30</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta tehtiin useampaan kertaan molemmilta puolilta ja -sivuilta elementtiä, mutta RFID-tunnistetta ei paikallistettu.</td>
</tr><tr>
      <td>VG-1920</td>
      <td>9</td>
      <td>@1LF</td>
      <td>0005</td>
      <td>Kyllä</td>
      <td>2024-11-28T13:15</td>
      <td>650</td>
      <td>77</td>
      <td>Luenta suoritettiin noin 650 mm etäisyydeltä elementin pinnasta huoneistonpuolelta.</td>
</tr><tr>
      <td>VG-1922</td>
      <td>9</td>
      <td>@1LF</td>
      <td>0006</td>
      <td>Ei</td>
      <td>2024-11-28T13:26</td>
      <td> - </td>
      <td> - </td>
      <td>Luenta tehtiin useampaan kertaan molemmilta puolilta ja -sivuilta elementtiä, mutta RFID-TUNNISTEEN signaalia ei paikallistettu.</td>
</tr>
</tbody>
</table>
</details>

---

## 5 Johtopäätökset

Tutkimuksen tavoitteena oli arvioida RFID-tunnisteiden toimivuutta erilaisissa asennus- ja käyttöympäristöissä sekä analysoida lukutulosten luotettavuutta ja käytettävyyttä. Tulokset osoittavat, että RFID-teknologian soveltaminen betonielementtien tunnistamiseen ja toimitusketjun tapahtumien seurantaan tarjoaa merkittävää potentiaalia tuotannon, logistiikan ja laadunhallinnan kehittämiseen. RFID-tunnisteiden käyttö betonielementeissä on teknisesti toteutettavissa, ja tunnisteet voivat säilyä luettavina myös vaativissa olosuhteissa.

Havaintojen perusteella teknologia soveltuu integroitavaksi osaksi digitaalista toimitusketjua, mutta käytännön toteutuksessa on edelleen ratkaistavia haasteita. Keskeisiä kehityskohteita ovat RFID-tunnisteiden sijoittelun ja asennustapojen optimointi sekä luentaprosessien yhdenmukaistaminen. Tutkimuksessa ilmeni poikkeamia tunnisteiden luettavuudessa, mikä saattaa johtua tunnisteiden virheellisistä asennuspaikoista tai niiden orientaatiosta betonielementissä suhteessa lukijaan. Tällaiset tekijät voivat heikentää signaalin kulkua ja estää luentatapahtumien tallentumisen. Nämä havainnot korostavat asennusprosessin huolellisuuden, dokumentoinnin ja laadunvarmistuksen keskeistä merkitystä RFID-teknologian onnistuneessa käyttöönotossa.

Koska tutkimuksen otanta oli rajallinen, tuloksia tulee pitää suuntaa-antavina. Kattavampi testaus eri elementtityypeillä, tuotantomenetelmillä ja käyttötilanteissa on tarpeen RFID-teknologian todellisten hyötyjen ja rajoitteiden luotettavaksi arvioimiseksi. Laajemmilla kokeilla voidaan lisäksi täsmentää teknologian soveltuvuutta rakennustuoteteollisuuden tapahtumatiedon hallintaan, jossa yksittäisten tuotteiden liikkeet ja tilamuutokset voidaan yhdistää digitaaliseen prosessitietoon reaaliaikaisesti ja läpinäkyvästi toimitusketjun eri osapuolten välillä.

---

## 6 Liitteet


![IMG_20240529_145019](https://github.com/user-attachments/assets/79e5dfcd-5d06-4290-ad4b-b5f3b755fd1c)


