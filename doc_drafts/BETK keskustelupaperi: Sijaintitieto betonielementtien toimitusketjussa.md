# BETK keskustelupaperi: Sijaintitieto betonielementtien toimitusketjussa


**Sijaintitieto suunnittelijan tietomallista toimitukseen**  
>Julkaisija: Rakennusteollisuus ry\
>Luonnos: 6.11.2025

<details>
<summary>Asiakirjan tiedot </summary>

| Selite                | Arvo                                                                |
|-----------------------|---------------------------------------------------------------------|
| Asiakirjan nimi       | BETK soveltamisohje: Sijaintieto betonielementtien toimitusketjussa |
| Asiakirjan päivämäärä | 3.7.2025                                                            |
| Asiakirjan versio     | 0.4                                                                 |
| Asiakirjan status     | Luonnos                                                             |

</details>

<details>
<summary>Asiakirjan laatijat </summary>

| Nimi             | Organisaatio                  |
|------------------|-------------------------------|
| Antti Pekkala    | Fira Oy                       |
| Teemu Anttila    | Ramboll                       |
| Janne Kihula     | Rakennustuoteteollisuus RTT   |
| Teemu Alaluusua  | Aalto-yliopisto               |
| Tom Partanen     | Consolis Parma Oy             |
| Eetu Lahtinen    | Consolis Parma Oy             |
| Satu Parikka     | Consolis Parma Oy             |
| Markku Räisänen  | Betset Oy                     |
| Jarkko Vitikainen| Sitowise Oy                   |
| Arto Nieminen    | NCC Oy                        |
| Riku Laiho       | NCC Oy                        |
| Antti Taskinen   | Fira Oy                       |
| Paula Valkonen   | Suutarinen / SBS Betoni Oy    |
| Kari Turunen     | Lujabetoni Oy                 |

</details>

<details>
<summary> Asiakirjan versio </summary>

| Versio  | Päivämäärä  | Tekijä  | Muutoskuvaus               |
|---------|-------------|---------|----------------------------|
| 0.1     | 21.5.2025   | anpekk  | Luonnos vaihe              |
| 0.2     | 30.5.2025   | anpekk  | Tekstiosuuksia täydennetty |
| 0.3     | 3.7.2025    | anpekk  | Tekstiosuuksia täydennetty |
| 0.4     | 6.11.2025   | TeAla   | Tekstiosuuksia täydennetty |

 </details>

 
## Sisällysluettelo

1. [Tausta](#1-tausta)
3. [Kirjoituksen tarkoitus ja rajaukset](#2kirjoituksen-tarkoitus-ja-rajaukset)  
4. [Sijaintieto tietomallissa](#3sijaintieto-tietomallissa)  
   3.1 [Koordinaatistot](#31koordinaatistot)  
   3.2 [Sijaintitiedot tietomallissa](#32sijaintitiedot-tietomallissa)  
   &nbsp;&nbsp;&nbsp;&nbsp;3.2.1 [Kerrostiedot IFC-mallissa](#321kerrostiedot-ifc-mallissa)  
   &nbsp;&nbsp;&nbsp;&nbsp;3.2.2 [Lohkotiedot IFC-mallissa](#322lohkotiedot-ifc-mallissa)
6. [XXX](#4xxx)  
7. [Lyhenteet ja terminologia](#lyhenteet-ja-terminologia)  
8. [Viittaukset](#viittaukset)


​ 
## 1 Tausta

Tällä hetkellä rakennushankkeen tietomallit ovat yleinen osa hankkeen tarjouspyyntöjä ja niiden määrä- ja kustannuslaskentaa. Suunnittelijoiden tekemiä tietomalleja käyttävät rakennusliikkeet ja tuoteosatoimittajat mm. määrä- ja tarjouslaskennassa, hankkeen toteutuksen suunnittelussa ja aikatauluttamisessa jne. BEC2012-hankkeessa luodut vakioidut tietokentät, mallinnusohje ja mallinnustyökalut ovat alalla yleisesti käytössä. Betonielementtien lohko- ja kerrostiedot ovat myös tärkeä osa betonielementtien toimitusketjua ja luotettavan tiedon saaminen suunnittelijoiden tietomalleista on havaittu olevan iso ongelma. Työmaalla tehtävän asennuslohkojaon ja aikataulutiedon välittämisessä on käytössä monenlaisia ratkaisuja, eikä alalla ole tullut vakioituja digitaalisia ratkaisuja toimitusketjun osapuolten välille.


<img width="524" height="433" alt="image" src="https://github.com/user-attachments/assets/a07ce81f-f492-496f-8bf3-df2607f6af1a" /><br> Kuva 1. Esimerkki yhdistelmämallin kerrostiedoista



​ 

​ 
Tämä soveltamisohje on tehty osana Rakennusteollisuus RT:n tuotetiedon ja toimitusketjun digitali-soinnin kehityshanketta, BETK-työryhmän toimesta. Kehityshankkeen ensisijainen tavoite on edistää rakennusalan tuotteiden toimitusketjun hallinnan menetelmien siirtymistä manuaalisesta ja raken-teettomasta tiedonvaihdosta täysin rakenteelliseen ja koneluettavaan tiedonvaihtoon. 
Ohjetta täydentävät muut BETK-hankkeen soveltamisohjeet:
•	BETK Soveltamisohje_Tuoteyksilöinti ja -tunnistaminen[1]
•	Excel-taulukko muuttujista [2]
•	Soveltamisohje GS1 EPCIS (tapahtumatieto) käytöstä [syksyllä tehdään] [3]

## 2	Kirjoituksen tarkoitus ja rajaukset
Hankkeen rakennusosien sijaintitiedolle on monenlaisia käyttötarkoituksia ja vaadittava tarkkuusta-so vaihtelee tiedon käyttäjän mukaan. Esimerkiksi rakennesuunnittelijalle lohkoa usein rajaavat ra-kenteelliset liikuntasaumat ja samaan aikaan elementtiasentajalle tärkeä tieto on mm. betonielemen-tin asennuslohko. LVI-suunnittelija usein jakaa rakennuksen TATE-järjestelmien mukaisiin palvelu-alueisiin ja esim. TATE-toimitusketjun kannalta yksittäisen tilan yksilöinti on tärkeä sijaintitieto. Tä-män takia tämä kirjoitus on ns. keskustelupaperi, jossa ei pyritä ratkaisemaan sijaintitietoa täydelli-sesti vaan keskittyen betonielementtien toimituksen kannalta tärkeisiin tietoihin ja niissä havaittuihin ongelmiin ja myös ehdotuksia näiden ratkaisemiseksi. 

## 3	Sijaintieto tietomallissa
### 3.1	Koordinaatistot. 
Rakennushankkeen koordinaatistoista käydään keskustelua jokaisessa hankkeessa. Alla selventävät kuvat siitä minkälaisia koordinaatistoja hankkeissa on tarpeen määrittää erilaisia käyttötapauksia varten. Projektin koordinaatisto tulee dokumentoida usein arkkitehdin toimesta.
 
<img width="853" height="238" alt="image" src="https://github.com/user-attachments/assets/63b72224-b3f7-4e24-9a10-1512d224a4b2" /><br> Kuva 2.Asiakkaan koordinaatisto


Projektin koordinaatisto
 
<img width="820" height="208" alt="image" src="https://github.com/user-attachments/assets/844f3dbd-1425-4381-a7e7-37c272ae714a" /><br> Kuva 3.Projektin koordinaatisto





Suunnittelijan koordinaatisto

<img width="869" height="221" alt="image" src="https://github.com/user-attachments/assets/e3cb40e8-4f02-45c7-8c60-ae0b0603c0ea" /><br> Kuva 4.Suunnittelijan koordinaatisto


 
Rava3Pro-hankkeessa on ollut esillä vaatimuksia hankkeen tietomallien koordinaatti-tiedolle, mutta tätä ohjetta kirjotettaessa selkeitä vaatimuksia ei vielä ole tiedossa. BETK-hankkeessa on käyty kes-kustelua koordinaatti-  tiedon mahdollisuuksista ja haasteista.  BETK-hankkeessa luotu ja soveltamis-ohjeessa [1] kuvattu tapa yksilöidä elementti käyttäen GS1 GTIN-standardia mahdollistaa elementin tunnistamisen käyttäen RFID-teknologiaa. RFID-lukutapahtumissa on mahdollista saada mm. lukuta-pahtumista sijaintitietoa ja tietoa on mahdollista välittää toimitusketjun välillä Peppol-sanomilla. Koordinaattitiedon välittäminen tarjoaa erilaisia mahdollisuuksia mutta edellyttää alalta laajempaa vakiointia. BETK-hankkeessa tietomallin tietokenttiin lisättiin betonielementin  painopisteen koordi-naatit. Tämän toteuttaminen ei edellytä laajempaa vakiointia ja on esimerkkinä tulevaisuuden ratkai-suille ja käyttötapauksille. 


<img width="1004" height="258" alt="image" src="https://github.com/user-attachments/assets/5d92f857-183c-47ba-9935-a630dc00974f" /><br>Kuva 5. Kuorielementin painopisteen koordinaatit

### 3.2	Sijaintitiedot tietomallissa
#### 3.2.1	Kerrostiedot IFC-mallissa
IFC-mallissa rakenneosat kuuluvat tiettyyn rakennukseen (IfcBuilding), lohkoon (osittainen IfcBuil-ding) ja kerrokseen (IfcBuildingStorey). Rakennuksen lohko ei ole IFC-formaatissa vastaava käsite kuin rakennus ja kerros. IFC-formaatti mahdollistaa hierarkisuuden siten että, rakennus voi koostua useasta rakennuksesta, jotka voivat sisältää osittaisia rakennuksia, jotka ovat on tarkoitettu raken-nuksen lohkojen määrittelyyn. Useat eri suunnittelualojen mallinnusohjelmat perustuvat siihen, että mallia tehdään rakennuksittain ja kerroksittain. Nämä sijaintitiedot ovat tärkeitä asennusta ja valmis-tusta suunniteltaessa ja toteutuksessa. Ja usein myös jo tarjouslaskentavaiheessa kustannusten jaot-telua varten on tietomallien lohkojako tarpeellinen. 
Kerrostiedossa on havaittu haasteeksi mm. kerrostiedon puuttuminen, väärin syötetty kerrostiedot ja monenlaiset kirjoitustavat ja -virheet. 

<img width="308" height="384" alt="image" src="https://github.com/user-attachments/assets/0c04801c-1b8e-4946-a941-4d19218d149f" /><br> Kuva 6. Esimerkki kuinka välilyönnit lisäävät kerroksia hankkeen tietomalliin

Ohjeita tietojen lisäämiseen hankkeissa:
•	Rakennesuunnittelija lisää sovitun lohko- ja kerrosjaon tietomalliin. 
•	Lohko- ja kerrostiedot tarkistetaan ennen tietomallitoimituksia.
•	Kerrostieto kirjoitetaan ilman ”.krs” tai muita tiedonsiirtoa sotkevia selitetekstejä, vain nu-meroita. Kerrostieto on IFC-mallissa kerrostietonimisessä tietokentässä (IfcBuildingStorey) jo-ten arvo ei tarvitse selittävää tekstiä siitä, että tiedolla tarkoitetaan kerrosta.
•	Kerroksen muodostavat kantavat ja ei-kantavat seinät ja pilarit niiden yläpuolinen välipohja. Usean kerrosten läpi menevät rakenteet (esim. pilarit) alimpaan kerrokseen, jossa ne asenne-taan.
•	Rakennemallissa kerroksina myös ”POHJARAKENTEET, PERUSTUKSET, ALAPOHJA, KELLARI”. Eli paalut ja anturarakenteet, sokkelit ja alapohjan rakenteet. 
•	Kerrokset nimet aina isolla kirjaimella, jotta ei tule eri tavalla kirjoitettuna. Esim. Kellari vs KELLARI. 
•	Rakenteellinen pintalaatta nimetään saman kerrokseen kuin sen alapuoliset rakenteet. 
•	Yläpohjassa esim. ylimmän ontelolaattatason yläpuoliset vesikattorakenteet nimetään erik-seen omaksi kerrokseksi, esim. YLÄPOHJA. 
 
<img width="601" height="248" alt="image" src="https://github.com/user-attachments/assets/2ebf0f95-cd28-482b-ac64-19a99e008c11" /><br>Kuva 7. Esimerkki kerrosten nimeämisestä
	
#### 3.2.2	Lohkotiedot IFC-mallissa
Rakennuksen lohkojakoon vaikuttavat mm. palo-osastointi, toiminnot, runkojärjestelmä, tekniikka, maapinnan olosuhteen ja perustukset, työvaiheiden limitys, tontin koko ja muoto ja jne jne. Eli vai-kuttavia asioita on paljon ja lohkotietojen käyttötapaukset vaihtelevat hankkeen aikana. Alla muu-tamia esimerkkejä erityyppisistä rakennuksista.
Logistiikka-halli, joka jaettu lohkoihin A ja B ja niiden alla useampi asennuslohko A1, A2, B1 ja  B2 jne. 

 <img width="1004" height="452" alt="image" src="https://github.com/user-attachments/assets/f2d8ac55-0850-47a1-95fc-ba43b43d8ca9" /><br> Kuva 8. Logistiikka-halli lohkojako esimerkki









Asuinkerrostalo jossa liikuntasaumajaon kohdalta jaottelu lohkoihin A ja B ja niiden sisällä rappujen mukainen jaottelu. 

 <img width="911" height="407" alt="image" src="https://github.com/user-attachments/assets/71cb8876-9845-46fe-aa5e-4767749cd3c8" /><br> Kuva 9. Asuinkerrostalon lohkojako esimerkki

Pistetalo jossa ei ole tarpeen lohkojakoa tehdä. Rappu-tiedon lisäksi asennuslohkon muodostaa yksittäinen huoneisto ja sen sisältämät elementit.

 
<img width="658" height="595" alt="image" src="https://github.com/user-attachments/assets/f086b082-df95-44dd-9895-17c9f3121da8" /><br> Kuva 10. Pistetalo esimerkki


Ohjeita tietojen lisäämiseen hankkeissa:
•	Rakennesuunnittelija lisää tietomalliin sovitun lohko- ja kerrosjaon. 
•	Lohko- ja kerrostiedot tarkistetaan ennen tietomallitoimituksia.

Lohkojakotieto oltava aina vaikka vain yksi rappu talossa?

Peppol
Asennuslohkotieto tietomallista
Asennuslohkotieto tietomalliin
Asennussijainnit Peppol
 
<img width="511" height="531" alt="image" src="https://github.com/user-attachments/assets/a7507ad8-d45e-4eda-97de-235de943ae75" /><br> Kuva 11. 


## 4	XXX
Tähän vielä tarvittaessa jotain viisasta. 
Sijaintitiedot tietomallissa
Rakennus
Lohko
Purkupaikka
Kerros

## 5 Sijaintitiedot toimituksissa (case Ruotsi)

BEAst Label on ruotsalaisen BEAst AB:n kehittämä standardi rakennustyömaiden toimitusten kollietiketeille. Sen tekninen tarkoitus on mahdollistaa rakennusmateriaalien yksiselitteinen tunnistus, paikannus ja ohjattu käsittely työmaalla sekä tukea sähköistä tiedonvaihtoa toimitusketjun osapuolten välillä. Standardi perustuu GS1-järjestelmään ja sen SSCC-tunnuksiin (Serial Shipping Container Code) sekä GS1-128-, DataMatrix- ja QR-viivakoodeihin, joita käytetään kolli-ID:n, GPS-koordinaattien ja yhteystietojen koneelliseen lukuun.

Etikettien tiedot tuotetaan automaattisesti BEAst Supply Material -standardin mukaisesta sähköisestä tilausviestistä (EDI), jossa määritellään toimituksen kohdetiedot, kuten rakennuksen, kerroksen, huoneen ja purkupaikan osoittavat kentät. Näin varmistetaan, että toimittaja voi tulostaa kollikohtaiset etiketit yhdenmukaisella tietosisällöllä.

BEAst Label koostuu neljästä versiosta, joilla on eri käyttötarkoitukset. Label A on pääasiassa lavatavaralle, ja se sisältää suurella kirjasinkoolla tulostetut kohdekentät, jotta esimerkiksi trukin kuljettaja voi lukea ne etäältä. Label B on tarkoitettu muille kuin lavatavarapakkauksille ja alikolleille, ja se sisältää myös kollin sisällön. Label C toimii lisäsisältöluettelona tilanteissa, joissa Label B:n kentät eivät riitä. Label D on tuote- tai artikkelietiketti, joka täydentää valmistajan omaa merkintää ja sovitetaan tuotekohtaiseen muotoon.

Etikettien tietokenttien rakenne, fontit, tehosteet, linjapaksuudet ja mittasuhteet on määritelty tarkasti. Tekstin asettelu on optimoitu luettavuuden ja dynaamisen fonttikoon perusteella. BEAst Labelin fyysinen koko on yleensä 105×251 mm, mikä vastaa standardoitua STE/STILL-kuljetusetikettiä, jota käytetään rinnakkain kuljetusvaiheen tunnistamisessa. BEAst Labelin tunniste käyttää applikointitunnistetta (AI) 90, kun taas STE/STILL käyttää (AI) 00, mikä mahdollistaa järjestelmien välisen erottelun samalla SSCC-numerolla.

BEAst Label tukee GPS-pohjaisia purkupaikkakoordinaatteja, puhelinnumeroita ja EDI-yhteensopivaa tiedonvaihtoa, mikä mahdollistaa logistiikan hallinnan koko toimitusketjussa. Standardin avulla voidaan automatisoida materiaalivirtojen kohdistus, parantaa sisälogistiikan läpinäkyvyyttä ja vähentää virhetoimituksia sekä hukkatyötä työmailla. BEAst Label muodostaa siten keskeisen teknisen rajapinnan digitaalisen rakennuslogistiikan toteuttamisessa.
<img width="604" height="424" alt="image" src="https://github.com/user-attachments/assets/b90691a3-730f-44a7-90c6-ce82dc2bd869" />
<img width="604" height="534" alt="image" src="https://github.com/user-attachments/assets/704fb214-00fd-411d-b887-c8a49bd8aabf" />


<img width="279" height="666" alt="image" src="https://github.com/user-attachments/assets/52b9f808-d6ea-4cc7-83f9-c24459ba6f73" />
<img width="279" height="666" alt="image" src="https://github.com/user-attachments/assets/25af1586-4fbc-43cd-9e1d-cbaf84181947" />
<img width="575" height="253" alt="image" src="https://github.com/user-attachments/assets/3a194c20-fdad-4b97-8124-8c8ed8524ff1" />


<img width="1024" height="677" alt="image" src="https://github.com/user-attachments/assets/f708114e-c008-441c-ab6c-5c0b5dffc214" />

(BEAst Label)[https://beast.se/standarder/beast-label/#]
(BEAst Label-manual)[https://beast.se/wp-content/uploads/2018/10/BEAst-Label_Manual_v1-03.pdf]
	
	
## Lyhenteet ja terminologia

| Lyhenne / Käsite | Selite |
|------------------|---------|
| **Alkuperäisformaatti** | Mallinnusohjelman oma tallennusformaatti. Alan julkaisuissa käytetään tälle synonyyminä käsitteitä *natiivimalli* tai *natiiviformaatti*. |
| **BIM** | Tietomalli tai tietomallinnus, lyhenne englanninkielisestä käsitteestä *Building Information Modeling*. |
| **IFC** | Rakennusten mallinnuksessa käytetty tuotetietojen siirron kansainvälinen standardi, lyhenne englanninkielisestä käsitteestä *Industry Foundation Classes*. |
| **RFID** | *(Radio Frequency Identification)* – Tunnistus- ja tiedonkeruumenetelmä, jolla kohteet tunnistetaan automaattisesti, kerätään niitä koskevia tietoja ja syötetään ne suoraan tietojärjestelmiin (esim. viivakoodien tai RFID:n avulla). |
| **UDA** | Suunnitteluohjelmistoissa mallin objekteille talletettavaa liitännäistietoa (*metatietoa*), lyhenne englanninkielisestä käsitteestä *User Defined Attribute*. |
| **PropertySet** | Rakentamisalalla yleisesti käytetty termi ”Property Set”. Tässä dokumentissa käytetään termiä *Ominaisuusryhmä*, jotta se on helpommin ymmärrettävissä. Ominaisuusryhmien tarkka määrittäminen mahdollistaa ominaisuuksien ryhmittelyn ja selkeyttää tietorakennetta. |
| **Property** | Rakentamisalalla vakiintunut termi ”Property”. Tässä dokumentissa käytetään termiä *Ominaisuus*, jolla viitataan yksittäiseen määriteltyyn tietokenttään tai ominaisuuteen vakioidussa tietorakenteessa. |

	
	
	
	


## Viittaukset
Nykyisessä asiakirjassa ei ole lähteitä.


​ 

​ 

​ 

​ 

​ 

​​ 
 

