# BETK: Tuoteyksilöinnin ja RFID-teknologian pilotoinnin loppuraportti (KESKEN)

**Tilauksesta suunniteltavat rakennustuotteet**  
>Julkaisija: Rakennusteollisuus ry\
>Julkaistu: 11.2.2025  
Versio: 1.0  
Status: Julkaistu

## Asiakirjan tiedot
<details> 
<Summary>Pilotointi työryhmä</Summary>

| **Nimi**            | **Organisaatio**     | **Kontribuutio**               |
|---------------------|----------------------|--------------------------------|
| Teemu Alaluusua     | Aalto-yliopisto      |1st author                      |
| Tuomas Kekki        | Fira Oy              |aineiston kerääminen            |
| Eetu Lahtinen       | Consolis Parma Oy    |aineiston kerääminen            |
| Ville Retulainen    | Lujabetoni           |aineiston kerääminen            |
| Arto Nieminen       | NCC                  |Työmaayhteys                    |
| Janne Raitaniemi    | Riffid               |RFID-laite toimittaja           |
| Juha Porkka         | NordicID             |RFID-laite toimittaja           |
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
  * [2.1 Betonielementtien tuoteyksilöinti (UPID)](#21-betonielementtien-tuoteyksil%C3%B6inti-upid)

---


## 1 Esipuhe
Tämä tuoteyksilöinnin ja RFID-teknologian pilotoinnin loppuraportti on tehty osana Rakennusteollisuus RT:n tuotetiedon ja toimitusketjun digitalisoinnin kehityshanketta, betonielementtitoimitusketju (BETK) -työryhmän toimesta.  BETK-työryhmä koostuu tilauksesta suunniteltavien rakennustuotteiden toimitusketjujen eri vaiheiden osapuolista sekä digitaalisen tiedonvaihdon asiantuntijoista. 

Kehityshankkeen ensisijainen tavoite on edistää rakennusalan tuotteiden toimitusketjun hallinnan menetelmien siirtymistä manuaalisesta ja rakenteettomasta tiedonvaihdosta täysin rakenteelliseen ja koneluettavaan tiedonvaihtoon. Tavoitteen saavuttaminen edellyttää, että tilauksesta suunniteltavien tuotteiden valmistuksessa käytetään yhteisiä, vakioituja menetelmiä tuotteiden yksilöintiin, tunnistamiseen ja tietosisältöjen jakamiseen. Näin voidaan edistää tietojärjestelmien ja palveluiden yhteentoimivuutta, jonka puute on merkittävä este rakennusteollisuuden digitalisaatiolle ja eri toimijoiden väliselle yhteistyölle.  

## 2 Yleiskuvaus pilotista
Työn tarkoituksena oli selvittää ja todentaa konseptitodistuksen (engl. Proof of Concept, PoC) avulla RFID-teknologian toimivuutta vakioidun yksilöintitiedon kantamiseen betonielementtien toimitusketjussa ja luoda lähtökohdat yhteisen, avoimen, GS1 EPC -standardeja käyttävän RFID/EPC-pohjaisen järjestelmän käyttöönotolle. Tämä toteutettiin käyttämällä betonielementtien sisään valettuja passiivisia UHF RFID -tunnisteita. Hankkeen yhtenä tarkoituksena oli myös luoda tulevaisuuden toimintamalleja, joissa RFID-teknologiaa hyödynnetään tuotteiden tunnistamisessa koko arvoverkossa. Lisäksi tavoitteena oli havainnoida käyttöympäristön tuomia haasteita toimitusketjun hallinnan näkökulmasta. 

**Pilotoinnin toteutus**<br>
Betonielementtien RFID-tunnisteteknologian pilotointi toteutettiin touko–marraskuun 2024 aikana kahdella kerrostalotyömaalla Helsingissä ja Tampereella. Testaus kattoi toimitusketjun vaiheet tuotevalmistuksesta työmaalle asennukseen asti. Toimitusketjun hallinnan näkökulmasta pilotointi rajattiin keskittymään tuoteyksilöinnin ja -tunnistamisen menetelmiin (kuva 1). Tämä lähestymistapa loi perustan laajemmalle toimitusketjun tapahtumatiedon jakamisen testaamiselle, joka on suunniteltu toteutettavaksi myöhemmässä vaiheessa.  


<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/68ad12b2-839b-4beb-8800-ee0ef6edd3de" />

###### Kuva 1. Tuoteyksilöinnin ja RFID-tunnistusteknologian pilotointilaajuus toimitusketjun digitaalisen hallinnan näkökulmasta.

**Osallistujat ja yhteistyötahot**<br>
Pilotoinnissa olivat mukana betonielementtien tuotevalmistajat Parma Oy ja Lujabetoni Oy sekä rakennusyritykset Fira Rakennus Oy ja NCC Suomi Oy. RFID-teknologiaosaamista projektiin toivat Riffid Oy ja NordicId Oy. Lisäksi toteutukseen osallistuivat Rakennusteollisuus RT, RFID Lab Finland Oy, Aalto-yliopisto ja GS1 Finland Oy.

### 2.1 Betonielementtien tuoteyksilöinti (UPID)
Tilauksesta suunniteltavien rakennustuotteiden toimitusketjussa haasteena on, että valmistuslogiikan mukaisesti suunniteltavat ja valmistettavat tuotteet ovat yksilöitä, mikä edellyttää tuoteyksilöinnin osalta enemmän informaatiota ja käytettävältä tiedonkantajalta tallennustilaa.

BETK-työryhmässä päädyttiin hyödyntämään GS1-standardia ns. kolmella tuoteyksilöinnin tasolla (esitetty taulukossa 1). Tässä mallissa GTIN-koodilla yksilöidään tietyn valmistajan tietyntyyppinen perustuote. Made-to-Order variation -numeron avulla yksilöidään tämän perustuotteen tietty variantti ja lopulta sarjanumerolla yksilöidään perustuotteen saman variantin identtiset yksilöt. Tässä tapauksessa pelkkä GTIN ei siis yksilöi tiettyä tuotetta, vaan yleisen luokan mahdollisista tilauksen perusteella valmistettavista tuotteen variaatioista.

###### Taulukko 1. GS1-standardiperheen mukaiset tuoteyksilöinnin hierarkia tasot tarkempaan yksilöintiin
<table>
  <tr>
    <td colspan="2"><strong>Tuoteyksilöinnin tasot</strong></td>
  </tr><tr>
    <td><strong>Taso 1</strong><br>Tuoteryhmä/perustuote</td>
    <td>GTIN</td>
  </tr><tr>
    <td><strong>Taso 2</strong><br>Tuotevariaation taso</td>
    <td>GTIN + MTO Varianttinumero</td>
  </tr><tr>
    <td><strong>Taso 3</strong><br>Tuoteyksilön taso</td>
    <td>GTIN + (MTO Varianttinumero) + Sarjanumero (sGTIN)</td>
  </tr>
</table>

BETK-työryhmän määrittelemässä taulukossa 2 esitetään minimitietovaatimukset tilauksesta suunniteltavien (ETO) rakennustuotteiden yksilöintiin GS1-sovellustunnusten avulla. GS1-sovellustunnukset (Application Identi-fiers, AI) ovat rakenteellisia tietokenttiä, jotka mahdollistavat tuotteiden ja logististen yksiköiden yksiselitteisen tunnistamisen sekä tiedon hallinnan toimitusketjussa. Jokainen sovellustunnus määrittelee tietyn tyyppisen in-formaation, kuten tuotteen globaalin tunnisteen (GTIN), yksilöllisen sarjanumeron, tilauksesta suunnitellun tuot-teen (MTO) varianttinumeron tai muita kontekstikohtaisia lisätietoja, kuten elementtitunnuksen ja GUID-tunnisteen.


###### Taulukko 2. BETK-työryhmän määrittämät tiedonkantajaan sisällytettävät yksilöintitiedot betonielementtien osalta
<table>
  <tr>
    <td colspan="2"><strong>Minimitietovaatimukset tilauksesta suunniteltavien (ETO) rakennustuotteiden yksilöintiin</strong></td>
  </tr><tr>
    <td><strong>GS1 Sovellustunnukset (AI) </strong></td>
    <td><strong>Esimerkki</strong></td>
  </tr><tr>
    <td><strong>(01) GTIN-koodi</strong></td>
    <td><code>06400001000247</code></td>
  </tr><tr>
    <td><strong>(242) Made-To-Order (MTO) varianttinumero</strong></td>
    <td><code>123456</code></td>
  </tr><tr>
    <td><strong>(21) Sarjanumero</strong></td>
    <td><code>12345678910</code></td>
  </tr>
    <tr>
    <td colspan="2"><strong>Valinnaiset lisätiedot betonielementtien tapauksessa</strong></td>
  </tr><tr>
    <td><strong>GS1 Sovellustunnukset (AI) </strong></td>
    <td><strong>Esimerkki</strong></td>
  </tr><tr>
    <td><strong>(91) Elementtitunnus</strong></td>
    <td><code>V-1001</code></td>
  </tr><tr>
    <td><strong>(92) GUID</strong></td>
    <td><code>ba34cf17-0c4b-4c6f-9295-cae05aa74ad4 </code></td>
  </tr><tr>
    <td><strong>(99) Verkkotunnus</strong></td>
    <td><code>id.rt.fi </code></td>
    </tr>
</table>

### 2.2 UHF RFID-tunniste tiedonkantajana (AIDC) betonielementissä
BETK-työryhmän tuoteyksilöintimäärittelyjen testaamiseksi päätettiin kokeilla betonielementtien tuotetunnistusta RFID-teknologiaan perustuvien tiedonkantajin kautta haastavimmassa mahdollisessa käyttötapauksessa. RFID-teknologia perustuu radiotaajuuksilla tapahtuvaan tiedonsiirtoon, jossa RFID-lukija lähettää radiosignaalin aktivoidakseen tunnisteen. Tunniste vastaa signaaliin heijastamalla siihen tallennetut tiedot takaisin lukijalle, joka edelleen välittää ne tietojärjestelmään.

RFID-järjestelmä ei edellytä suoraa näköyhteyttä ja mahdollistaa automaattisen sekä etäluettavan yksilöinnin. Tunnisteet luokitellaan passiivisiin, puolipassiivisiin ja aktiivisiin niiden virransyöttömekanismin perusteella. RFID-järjestelmät toimivat eri radiotaajuuksilla, joista yleisin on LF-taajuus (matala taajuus, 30–300 kHz), HF (korkea taajuus, 3–30 MHz) ja UHF (erittäin korkea taajuus, 300 MHz - 3 GHz).

Testissä käytettiin koteloituja metallipinnoille soveltuvia passiivisia EPC/RFID Gen2 UHF -tunnisteita, jotka valettiin betonielementtien sisään. Tunnisteen valinta perustui RFID-teknologia-asiantuntijoiden näkemykseen, jossa passiivisten UHF-tunnisteiden lukuetäisyys, kustannustehokkuus ja käyttöympäristön soveltuvuus olivat keskeisiä valintakriteerejä kyseiselle RFID-teknologialle. EPC Globalin Gen2-luokan passiivinen UHF-RFID teknologia on laajasti käytetty, joka toimii 840–960 MHz:n taajuuksilla alueellisista radiomääräyksistä riippuen. Se on kehitetty erityisesti logistiikkaverkoissa käytettäväksi, ja siinä on keskitytty useiden tunnisteiden nopeaan lukemiseen, hy-vään lukuetäisyyteen ja alhaisiin kustannuksiin.

Tiedonkantajien osalta betonielementtien käyttöympäristön haasteena nähtiin betonin emäksisyyden, kosteuden, sekä raudoituksen vaikutukset RFID-tunnisteen toimintaan. RFID-teknologian testauksen tarve perustui aiempien tutkimus- ja kehityshankkeiden tuloksiin, jossa RFID-teknologian etuna nähtiin tiedonkantajan käyttöikä osana tuotetta, sekä automatisoidut lukutapahtumat ja niistä syntyvän tapahtumatiedon jakaminen toimitusketjun osapuolten välisissä prosesseissa.

## 3 RFID-teknologian testaus toimitusketjussa
RFID-teknologian toimivuutta betonielementtien sisään upotettuna tiedonkantajana testattiin kahdessa erillisessä rakennushankkeessa Helsingissä (Case 1) ja Tampereella (Case 2). Testaukseen osallistuivat kaksi eri pääurakoitsijaa, kaksi eri betonielementtivalmistajaa ja kaksi eri RFID-teknologiatoimittajaa. Testaus toteutettiin suoraan toimitettaviin betonielementteihin ilman erillistä mock-up-vaihetta. Tavoitteena oli arvioida RFID-tunnisteiden asennuksen vaikutusta tuotantoprosessiin ja testata niiden käyttöä toimivassa tuotantoketjussa mahdollisimman vähäisin häiriöin. Testauksessa hyödynnettiin valmiiksi koodattuja RFID-tunnisteita, joita luettiin enimmäkseen käsilukijoilla, mutta myös automaattisilla porttilukijoilla.
### 3.1 Case 1
Ensimmäisenä pilottikohteena toimi Fira Rakennus Oy:n asuinkerrostalokohde Helsingissä, johon Lujabetoni Oy valmisti ja toimitti väliseinäelementtejä. Testauslaajuus ensimmäisen pilotoinnin osalta oli kymmenen (10) väliseinäelementtiä. Toimitusketjussa testattiin RFID-tunnisteiden luentaa eri vaiheissa: elementtitehtaalla käsilukijoilla, työmaan elementtipurkupaikalla kiinteällä automaattisella lukuportilla sekä elementtiasennuksen jälkeisessä tarkastuksessa käsilukijalla.

#### 3.1.1 Käytetty RFID-teknologia

###### Taulukko 3. Case 1: Hyödynnetty RFID-teknologia

<table border="1" cellspacing="5" cellpadding="5">
<tbody>
  <tr>
    <td colspan="2"><strong>1. Osapuolet</strong></td>
  </tr><tr>
        <td>RFID-teknologia toimittaja:</td>
        <td><code>Riffid Oy</code></td>
  </tr><tr>
        <td>Valmistaja:</td>
        <td><code>Lujabetoni Oy, Järvenpään betonielementtitehdas</code></td>
  </tr><tr>
        <td>Vastaanottaja:</td>
        <td><code>Fira Rakennus Oy, asuinkerrostalokohde Hexagon (Pasila, Helsinki)</code></td>
  </tr>
</tbody>
</table>




##### 2. Testikokonaisuudessa käytettyjen RFID-tagien tiedot

##### RFID tunniste 1
<img width="895" height="202" alt="tunniste2-removebg-preview" src="https://github.com/user-attachments/assets/bd892371-d7c1-4ec0-8a2f-aa1ab5d3bef6" />

<table>
 <tbody>
  <tr>
    <td><strong>Muisti</strong></td>
    <td><strong>Tyyppi</strong></td>
    <td><strong>Taajuus</strong></td>
    <td><strong>Kotelointi</strong></td>
    <td><strong>Määrä</strong></td>
  </tr><tr>
    <td>Alien Technology, Alien Higgs3 chip, 512bits User memory, 96/128bits EPC </td>
    <td>Passive R/W EPC Class 1 Gen 2/ISO 18000-6C</td>
    <td>UHF 860-920 MHz</td>
    <td>Anti metal ABS rfid hard tag Koko:155*32*12mm IP67 </td>
    <td>15 kpl</td>
  </tr>
 </tbody>
</table>
  



<table border="1" cellspacing="5" cellpadding="5">
<tbody>
  <tr>
    <td colspan = "4"><strong>2. Testikokonaisuudessa käytettyjen RFID-tagien tiedot</strong></td>
  </tr><tr>
    <td colspan = "5"> <img width="895" height="202" alt="tunniste2-removebg-preview" src="https://github.com/user-attachments/assets/bd892371-d7c1-4ec0-8a2f-aa1ab5d3bef6" /><br> <strong>Kuva 1.</strong></td>   
  </tr><tr>
    <td><strong>Muisti</strong></td>
    <td><strong>Tyyppi</strong></td>
    <td><strong>Taajuus</strong></td>
    <td><strong>Kotelointi</strong></td>
    <td><strong>Määrä</strong></td>
  </tr><tr>
    <td>Alien Technology, Alien Higgs3 chip, 512bits User memory, 96/128bits EPC </td>
    <td>Passive R/W EPC Class 1 Gen 2/ISO 18000-6C</td>
    <td>UHF 860-920 MHz</td>
    <td>Anti metal ABS rfid hard tag Koko:155*32*12mm IP67 </td>
    <td>15 kpl</td>
   </tr><tr>
    <td colspan = "5"><img width="831" height="168" alt="tunniste1" src="https://github.com/user-attachments/assets/7c8eeb0f-8367-4a52-adea-0a5d27d4d120" /><br> <strong>Kuva 2.</strong></td>   
  </tr><tr>
    <td><strong>Muisti</strong></td>
    <td><strong>Tyyppi</strong></td>
    <td><strong>Taajuus</strong></td>
    <td><strong>Kotelointi</strong></td>
    <td><strong>Määrä</strong></td>
  </tr><tr>
    <td>Alien Technology, Alien Higgs3 chip, 512bits User memory, 96/128bits EPC </td>
    <td>Passive R/W EPC Class 1 Gen 2/ISO 18000-6C</td>
    <td>UHF 860-920 MHz</td>
    <td>Anti-Metal Passive Tag Plate, Koko:135*21* 17 mm IP68 </td>
    <td>15 kpl</td>
  </tr>
</tbody>
</table>





<table border="1" cellspacing="5" cellpadding="5">
<tbody>
  <tr>
    <td colspan = "4"><strong>2. Testikokonaisuudessa käytettyjen RFID-tagien tiedot</strong></td>
  </tr><tr>
    <td><strong>Muisti</strong></td>
    <td><strong>Tyyppi</strong></td>
    <td><strong>Taajuus</strong></td>
    <td><strong>Kotelointi</strong></td>
    <td><strong>Määrä</strong></td>
  </tr><tr>
    <td>Alien Technology, Alien Higgs3 chip, 512bits User memory, 96/128bits EPC </td>
    <td>Passive R/W EPC Class 1 Gen 2/ISO 18000-6C</td>
    <td>UHF 860-920 MHz</td>
    <td>Anti metal ABS rfid hard tag Koko:155*32*12mm IP67 </td>
    <td>15 kpl</td>
  </tr><tr>
    <td colspan = "5"> <img width="895" height="202" alt="tunniste2-removebg-preview" src="https://github.com/user-attachments/assets/bd892371-d7c1-4ec0-8a2f-aa1ab5d3bef6" /><br> <strong>Kuva 1.</strong>

</td>   
  </tr><tr>
    <td><strong>Muisti</strong></td>
    <td><strong>Tyyppi</strong></td>
    <td><strong>Taajuus</strong></td>
    <td><strong>Kotelointi</strong></td>
    <td><strong>Määrä</strong></td>
  </tr><tr>
    <td>Alien Technology, Alien Higgs3 chip, 512bits User memory, 96/128bits EPC </td>
    <td>Passive R/W EPC Class 1 Gen 2/ISO 18000-6C</td>
    <td>UHF 860-920 MHz</td>
    <td>Anti-Metal Passive Tag Plate, Koko:135*21* 17 mm IP68 </td>
    <td>15 kpl</td>
   </tr><tr>
    <td colspan = "5"><img width="831" height="168" alt="tunniste1" src="https://github.com/user-attachments/assets/7c8eeb0f-8367-4a52-adea-0a5d27d4d120" /><br> <strong>Kuva 2.</strong>
</td>   
  </tr>
</tbody>
</table>



<table border="1" cellspacing="5" cellpadding="5">
  <body>
    <tr>
      <td colspan = "4"><strong>3. Testikokonaisuudessa käytettyjen RFID-lukijoiden tiedot</strong></td>
    </tr><tr>
      <td><strong>Laite</strong></td>
      <td><strong>Valmistaja/tyyppi</strong></td>
      <td><strong>Käyttötarkoitus</strong></td>
      <td><strong>Määrä</strong></td>
    </tr><tr>
      <td rowspan = "3"></td>
      <td></td>
      <td></td>
      <td>1 kpl</td>
    </tr><tr>
      <td></td>
      <td></td>
      <td>1 kpl</td>
    </tr><tr>
      <td></td>
      <td></td>
      <td>1 kpl</td>
    </tr><tr>
      <td rowspan = "3"></td>
      <td></td>
      <td></td>
      <td>1 kpl</td>
    </tr><tr>
      <td></td>
      <td></td>
      <td>1 kpl</td>
    </tr><tr>
      <td></td>
      <td></td>
      <td>1 kpl</td>
    </tr><tr>
      <td colspan = "4"><strong>3. RFID-tunnisteiden sijoittaminen elementtiin</strong></td>
    </tr><tr>
      <td colspan = "4">RFID-tunnisteita asennettiin yhteensä kymmeneen (10) väliseinäelementtiin, joista jokaiseen sijoitettiin kolme RFID-tunnistetta. Betonielementin sisälle valetut RFID-tunnisteiden asennussijaintien periaate on esitetty alla olevassa kuvassa, jossa RFID-tunniste on lisätty elementtien molempiin päihin sekä elementin yläpintaan.</td>
    </tr><tr>
      <td colspan = "4"></td>
    </tr>
  </body>
</table>


#### 3.1.2 Case 1: RFID-tunnisteiden asennuksen ja lukutulosten analyysi

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

### 3.2 Case 2

#### 3.2.1 Käytetty RFID-teknologia

###### Taulukko 3. Case 2: Hyödynnetty RFID-teknologia

<table border="1" cellspacing="5" cellpadding="5">
<tbody>
  <tr>
    <td colspan="2"><strong>1. Osapuolet</strong></td>
  </tr><tr>
        <td>RFID-teknologia toimittaja:</td>
        <td><code></code></td>
  </tr><tr>
        <td>Valmistaja:</td>
        <td><code></code></td>
  </tr><tr>
        <td>Vastaanottaja:</td>
        <td><code></code></td>
  </tr>
</tbody>
</table>

<table border="1" cellspacing="5" cellpadding="5">
<tbody>
  <tr>
    <td colspan = "4"><strong>2. Testikokonaisuudessa käytettyjen RFID-tagien tiedot</strong></td>
  </tr><tr>
    <td><strong>Muisti</strong></td>
    <td><strong>Tyyppi</strong></td>
    <td><strong>Taajuus</strong></td>
    <td><strong>Kotelointi</strong></td>
    <td><strong>Määrä</strong></td>
  </tr><tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr><tr>
    <td><strong>Kuva 1.</strong></td>
    <td colspan = "4"> <img width="400" height="408" alt="confidex-ironside-slim-370x273-removebg-preview" src="https://github.com/user-attachments/assets/c5d22a72-13aa-4fd6-ac55-6fc1bef1c32a" />

</td>   
  </tr><tr>
    <td><strong>Muisti</strong></td>
    <td><strong>Tyyppi</strong></td>
    <td><strong>Taajuus</strong></td>
    <td><strong>Kotelointi</strong></td>
    <td><strong>Määrä</strong></td>
  </tr><tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
   </tr><tr>
    <td><strong>Kuva 2.</strong></td>
    <td colspan = "4"> <img width="400" height="400" alt="Confidex-Survivor-removebg-preview" src="https://github.com/user-attachments/assets/3aee56d2-b062-43d5-9cd2-03ac9feb6112" />
</td>     
  </tr>
</tbody>
</table>



<table border="1" cellspacing="5" cellpadding="5">
  <body>
    <tr>
      <td colspan = "4"><strong>3. Testikokonaisuudessa käytettyjen RFID-lukijoiden tiedot</strong></td>
    </tr><tr>
      <td><strong>Laite</strong></td>
      <td><strong>Valmistaja/tyyppi</strong></td>
      <td><strong>Käyttötarkoitus</strong></td>
      <td><strong>Määrä</strong></td>
    </tr><tr>
      <td rowspan = "3"></td>
      <td></td>
      <td></td>
      <td>1 kpl</td>
    </tr><tr>
      <td></td>
      <td></td>
      <td>1 kpl</td>
    </tr><tr>
      <td></td>
      <td></td>
      <td>1 kpl</td>
    </tr><tr>
      <td rowspan = "3"></td>
      <td></td>
      <td></td>
      <td>1 kpl</td>
    </tr><tr>
      <td></td>
      <td></td>
      <td>1 kpl</td>
    </tr><tr>
      <td></td>
      <td></td>
      <td>1 kpl</td>
    </tr><tr>
      <td colspan = "4"><strong>3. RFID-tunnisteiden sijoittaminen elementtiin</strong></td>
    </tr><tr>
      <td colspan = "4"></td>
    </tr><tr>
      <td colspan = "4"></td>
    </tr>
  </body>
</table>

#### 3.2.2 Case 2: RFID-tunnisteiden asennuksen ja lukutulosten analyysi

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

## 4 Johtopäätökset

RFID-teknologian soveltaminen betonielementtien yksilöintiin ja toimitusketjun tapahtumien seurantaan osoittaa merkittävää potentiaalia tuotantoprosessien ja logistiikan hallinnan parantamisessa. Tämän tutkimuksen tarkoituksena oli analysoida RFID-tunnisteiden toimivuutta eri asennus- ja käyttöympäristöissä sekä arvioida lukutulosten luotettavuutta ja käytettävyyttä. 

Ei voida poissulkea mahdollisuutta, että ne rfid elementit jotka ei löytyneet betonielementit olisi asennettu vääriin sijainteihin 

suppea otanta, jonka vuoksi kattavammalle testaukselle on tarvetta RFID-teknologian todellisten hyötyjen mittaamisessa.  

## 5 Liitteet
