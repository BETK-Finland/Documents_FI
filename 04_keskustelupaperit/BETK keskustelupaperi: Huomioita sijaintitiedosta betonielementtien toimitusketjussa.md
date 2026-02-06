# BETK keskustelupaperi: Huomioita sijaintitiedosta betonielementtien toimitusketjussa


**Sijaintitieto suunnittelijan tietomallista toimitukseen**  
>Julkaisija: Rakennusteollisuus ry\
>Luonnos: 23.12.2025

<details>
<summary>Asiakirjan tiedot </summary>

| Selite                | Arvo                                                                |
|-----------------------|---------------------------------------------------------------------|
| Asiakirjan nimi       | BETK soveltamisohje: Sijaintieto betonielementtien toimitusketjussa |
| Asiakirjan päivämäärä | 23.12.2025                                                          |
| Asiakirjan versio     | 1.0                                                                 |
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
| 0.4     | 9.11.2025   | TeAla   | Tekstiosuuksia täydennetty |
| 1.0     | 23.12.2025  | TeAla   | Github-julkaisu			   |

 </details>

 
## Sisällysluettelo

1. [Tausta](#1-tausta)
2. [Keskustelupaperin tarkoitus ja rajaukset](#2-keskustelupaperin-tarkoitus-ja-rajaukset)
3. [Sijaintitietojen esittäminen tietomalleissa](#3-sijaintitietojen-esittäminen-tietomalleissa)
   - 3.1 [Koordinaatistot](#31-koordinaatistot)
     - 3.1.1 [Asiakkaan koordinaatisto](#311-asiakkaan-koordinaatisto)
     - 3.1.2 [Projektin koordinaatisto](#312-projektin-koordinaatisto)
     - 3.1.3 [Suunnittelijan koordinaatisto](#313-suunnittelijan-koordinaatisto)
   - 3.2 [Kerrostiedot IFC-mallissa](#32-kerrostiedot-ifc-mallissa)
   - 3.3 [Lohkotiedot IFC-mallissa](#33-lohkotiedot-ifc-mallissa)
4. [Toimialan näkökulma – koordinaatistosta kohti toimitusketjun sijaintitietoa](#4-toimialan-näkökulma--koordinaatistosta-kohti-toimitusketjun-sijaintitietoa)
   - 4.1 [Sijaintitietojen välitys sähköisissä hankinta- ja toimitussanomissa](#41-sijaintitietojen-välitys-sähköisissä-hankinta--ja-toimitussanomissa)
   - 4.2 [Toimitusketjun näkökulma: BEAst Label -esimerkki Ruotsista](#42-toimitusketjun-näkökulma-beast-label--esimerkki-ruotsista)
5. [Lyhenteet ja terminologia](#lyhenteet-ja-terminologia)
6. [Viittaukset](#viittaukset)



---
​ 
## 1 Tausta

Rakennushankkeiden tietomallit ovat vakiintuneet osaksi hankkeiden tarjouspyyntöjä, määrä- ja kustannuslaskentaa sekä toteutuksen suunnittelua. Suunnittelijoiden laatimia tietomalleja hyödyntävät rakennusliikkeet ja tuoteosatoimittajat laajasti hankinnan, tuotannon, logistiikan ja asennuksen suunnittelussa. Betonielementtirakentamisessa tietomallien merkitys korostuu erityisesti elementtien määrälaskennassa, ryhmittelyssä ja aikataulutuksessa.

Alalla yleisesti käytössä olevat mallinnusohjeet ja vakioidut tietokentät, kuten BEC2012-hankkeessa luodut käytännöt, ovat parantaneet tietomallien yhteentoimivuutta. Tästä huolimatta betonielementtien sijaintitietoon liittyvät tiedot, erityisesti lohko- ja kerrostiedot, ovat edelleen epäyhtenäisiä, puutteellisia tai tulkinnanvaraisia. Suunnittelumalleista saatava sijaintitieto ei sellaisenaan vastaa toimitusketjun eri vaiheiden tarpeita, eikä tieto siirry luotettavasti suunnittelusta tilaus-, toimitus- ja asennusprosessiin.

Käytännössä tämä tarkoittaa, että asennuslohkojaot, aikataulut ja toimitusten kohdistaminen muodostuvat usein työmaakohtaisesti erillisissä järjestelmissä tai manuaalisina tulkintoina. Toimitusketjun osapuolten välillä on käytössä monenlaisia ratkaisuja, mutta yhteisiä digitaalisia ja vakioituja käytäntöjä sijaintitiedon välittämiseen ei ole muodostunut. Tämä lisää tiedon päällekkäistä käsittelyä, virheriskiä ja heikentää toimitusketjun kokonaisohjattavuutta.

Sijaintitiedon haaste ei rajoitu pelkästään tietomallien sisäiseen rakenteeseen, vaan se korostuu erityisesti tilanteissa, joissa tieto tulisi yhdistää fyysisiin tuotteisiin ja toimituksiin. Kun betonielementti siirtyy suunnittelusta tuotantoon, kuljetukseen ja asennukseen, sen sijainti muuttuu käsitteellisestä tilasijainnista fyysiseksi kohdistustiedoksi, jonka tulee olla ymmärrettävä sekä ihmiselle että tietojärjestelmille.

Tämän vuoksi sijaintitiedon tarkastelussa on huomioitava sekä fyysinen, ihmisluettava ulottuvuus että digitaalinen, koneluettava ulottuvuus. Tiedon tulee olla tulkittavissa työmaalla esimerkiksi kollietiketeissä ja asennusohjeissa, mutta samalla sen on oltava rakenteellisessa muodossa, jotta se voidaan siirtää sähköisesti järjestelmien välillä ilman manuaalista uudelleenkirjausta. Tässä kokonaisuudessa betonielementtien sijaintitieto tunnistetaan keskeiseksi kehityskohteeksi, joka yhdistää tietomallit, tuoteyksilöinnin, toimitukset ja asennusprosessit toisiinsa.

<img width="2602" height="1945" alt="Kerrosten nimeäminen" src="https://github.com/user-attachments/assets/6a8460de-d368-4afd-932e-bee9b8927ab5" /><br> Kuva 1. Esimerkki yhdistelmämallin kerrostiedoista


 ---

## 2	Keskustelupaperin tarkoitus ja rajaukset
Tämä dokumentti on BETK-työryhmän keskustelupaperi, jonka tarkoituksena on jäsentää betonielementtien toimitusketjun kannalta keskeisiä sijaintitietoon liittyviä havaintoja, ongelmia ja kehityssuuntia. Paperi ei ole normi, standardi tai valmis ohje, vaan lähtökohta yhteiselle ymmärrykselle ja jatkokehitykselle.

Keskustelupaperi kytkeytyy Rakennusteollisuus RT:n käynnissä olevaan tuotetiedon ja toimitusketjujen digitalisaatiotyöhön, jossa tavoitteena on siirtyä manuaalisesta ja rakenteettomasta tiedonvaihdosta kohti rakenteellista, koneluettavaa ja toimitusketjun eri osapuolia palvelevaa tiedonhallintaa. Tässä kokonaisuudessa sijaintitieto muodostaa kriittisen rajapinnan tietomallien, fyysisten tuotteiden tunnistamisen sekä toimitus- ja tapahtumatiedon välillä.

Koska rakennettavien kohteiden sijaintitiedolla on eri käyttäjäryhmille erilaisia merkityksiä, käyttötarkoituksia ja tarkkuusvaatimuksia, tässä dokumentissa keskitytään rajatusti betonielementtien toimitusketjun näkökulmaan. Tarkastelun painopiste on suunnittelumalleissa esiintyvissä kerros- ja lohkotiedoissa, niiden tulkittavuudessa sekä mahdollisuuksissa liittää nämä tiedot fyysisiin toimituksiin ja digitaalisiin sanomiin. Laajempi sijaintitiedon standardointi, esimerkiksi koordinaattipohjaisessa tai monialaisessa kontekstissa, tunnistetaan tärkeäksi jatkotyön aiheeksi, mutta se ei ole tämän keskustelupaperin varsinainen tavoite.

Esimerkiksi rakennesuunnittelijalle lohkoa usein rajaavat rakenteelliset liikuntasaumat ja samaan aikaan elementtiasentajalle tärkeä tieto on mm. betonielementin asennuslohko. LVI-suunnittelija usein jakaa rakennuksen TATE-järjestelmien mukaisiin palvelualueisiin ja esim. TATE-toimitusketjun kannalta yksittäisen tilan yksilöinti on tärkeä sijaintitieto. Tämän takia tämä kirjoitus on ns. keskustelupaperi, jossa ei pyritä ratkaisemaan sijaintitietoa täydellisesti vaan keskittyen betonielementtien toimituksen kannalta tärkeisiin tietoihin ja niissä havaittuihin ongelmiin ja myös ehdotuksia näiden ratkaisemiseksi pohjoismaisella tasolla.

---

## 3	Sijaintitietojen esittäminen tietomalleissa
Rakennettujen kohteiden tietomalleissa sijaintitieto muodostaa keskeisen osan tuotetiedon ja prosessitiedon yhteentoimivuutta. IFC-standardin (*Industry Foundation Classes*) rakenteessa sijainti ja tilallinen organisointi määritellään kahden toisiaan täydentävän periaatteen kautta: ```placement``` (sijoittaminen) ja ```spatial organization``` (tilallinen rakenne).<br>

**Placement** kuvaa kohteen paikan suhteessa koordinaattijärjestelmään, toiseen objektiin tai paikalliseen referenssiin. IFC:n määritelmissä tämä toteutetaan luokan ```IfcObjectPlacement``` kautta, joka voi olla absoluuttinen (maailmankoordinatisto), suhteellinen (toiseen tuotteeseen) tai rajoitettu (esimerkiksi verkkoon tai lineaariseen kohteeseen sidottu). Paikallinen sijoitus määritellään ```IfcLocalPlacement```-luokalla, ja suuremmassa mittakaavassa georeferointi yhdistää mallin maantieteelliseen sijaintiin. Koordinaattiverkot (```IfcGrid```) mahdollistavat kohteiden sijoittamisen eri geometristen asetelmien mukaan, kuten suorakulmaisina, radiaalisina tai kolmiomaisina rakenteina.<br>

<img width="4163" height="1220" alt="Kuva13" src="https://github.com/user-attachments/assets/2a6df68b-4abe-4de2-8ec6-94be281ed721" /><br> Kuva x. Koordinaattiverkot (Domer & Bernadello, 2023)


**Spatial organization** puolestaan määrittää, miten rakennuksen tai muun rakenteen osat järjestyvät hierarkkisesti ja tilallisesti. Tämä voidaan esittää kahdella tavalla:<br>

**Spatial containment** – hierarkkinen tilarakenne ilman omaa geometriaa (esimerkiksi ```Site``` – ```Building``` – ```Storey``` – ```Space```), jota kuvataan luokalla ```IfcSpatialStructureElement```.<br>

**Spatial composition** – geometrisesti kuvattu tilallinen koostumus, kuten ```IfcSpatialZone```, joka kokoaa yhteen samankaltaisia tiloja tai toiminnallisia alueita.<br>

<img width="4450" height="2223" alt="Kuva12" src="https://github.com/user-attachments/assets/b5baed5d-4741-4d37-af71-6ab5e02f665f" />

<br> Kuva x. Rakennuksen tilayksiköt (Domer & Bernadello, 2023)[^1]

Rakennuksen tilahierarkia seuraa tyypillisesti rakennuksen suunnittelun ja rakentamisen logiikkaa: ```IfcProject``` toimii ylimpänä kontekstina, jonka alla sijaitsevat ```IfcSite```, ```IfcBuilding```, ```IfcBuildingStorey``` ja ```IfcSpace```. Näin muodostetaan yhtenäinen tietorakenne rakentamiskohteen informaatiomalliin (BIM), jonka avulla eri suunnittelualojen ja toimitusketjun toimijat voivat viitata samoihin tilallisiin ja paikallisiin konteksteihin mallissa (BIM).<br>

Lisäksi IFC tukee koostettuja elementtejä (```assemblies```), joiden avulla voidaan yhdistää useita rakennusosia (esim. palkki- ja runkorakenteita) yhdeksi loogiseksi kokonaisuudeksi ```IfcElementAssembly```-luokan kautta. Sijainti- ja tilatietojen yhteys varmistetaan relaatioiden, kuten ```IfcRelContainedInSpatialStructure``` ja ```IfcRelAggregates```, avulla, jolloin kohteiden keskinäiset suhteet säilyvät yksiselitteisinä tietomallissa.<br>

Sijaintitiedon mallintamisen standardoitu rakenne on keskeinen edellytys digitaalisten toimitusketjujen hallinnalle, koska se mahdollistaa sekä fyysisten tuotteiden että niihin liittyvien tapahtumien (esim. toimitukset, asennukset) liittämisen samaan kontekstiin. Yhtenäinen sijaintimäärittely tukee myös linkitetyn datan sovelluksia, joissa rakennustuotteiden yksilöivä tunniste voidaan yhdistää rakennuksen tilalliseen ja koordinaattipohjaiseen rakenteeseen.<br>

---

### 3.1	Koordinaatistot
Rakennushankkeissa käytettävistä koordinaatistoista käydään keskustelua käytännössä jokaisessa hankkeessa. Koordinaatistojen määrittely on tarpeen, koska hankkeen eri osapuolilla ja eri käyttötapauksilla on toisistaan poikkeavia vaatimuksia sijaintitiedolle. Tietomallien näkökulmasta keskeistä on, että projektin koordinaatisto on sovittu ja dokumentoitu, usein arkkitehdin toimesta, jotta aineistoa voidaan siirtää ja yhdistää luotettavasti hankkeen aikana.

Rakennushankkeissa on tyypillisesti käytössä kolme toisiaan täydentävää koordinaatistotyyppiä: asiakkaan koordinaatisto, projektin koordinaatisto ja suunnittelijan koordinaatisto.

#### 3.1.1 Asiakkaan koordinaatisto

Asiakkaan koordinaatisto perustuu tyypillisesti kaupungin tai kunnan käyttämään koordinaatistojärjestelmään. Asiakkaan koordinaatisto palvelee asiakkaan tarpeita ja mahdollistaa esimerkiksi suunnitelmien liittämisen laajempaan virtuaaliseen malliin. Projektin aikana rakennusvalvonta tai muu viranomainen voi edellyttää asiakkaan koordinaatiston käyttämistä.


<img width="416" height="335" alt="Asiakkaan koordinaatisto" src="https://github.com/user-attachments/assets/57adfd92-120f-4033-b764-86a7b755fa25" /> <br> Kuva 2. Asiakkaan koordinaatisto

#### 3.1.2 Projektin koordinaatisto

Projektin koordinaatisto on hankkeen osapuolten kesken sovittu koordinaatisto, jossa aineistoa siirretään projektin aikana. Projektin koordinaatisto palvelee tiedonsiirtoa eri suunnittelualojen ja eri suunnitteluvaiheiden välillä. Sen avulla eri suunnitteluajojen mallit voidaan yhdistää toisiinsa esimerkiksi suunnitelmien ristiriidattomuuden tarkastelua varten.

 <img width="530" height="335" alt="Projektin koordinaatisto" src="https://github.com/user-attachments/assets/204114d4-ebea-410f-a53f-c6dc935941b8" /><br> Kuva 3.Projektin koordinaatisto
 
#### 3.1.3 Suunnittelijan koordinaatisto

Suunnittelijan koordinaatisto on suunnittelijan omassa suunnittelutyössä käyttämä koordinaatisto. Se palvelee ensisijaisesti suunnittelijan työn sujuvuutta. Käytännössä suunnittelijan voi olla tarpeen asettaa origo tiettyyn pisteeseen tai kääntää kohdetta, jotta mallinnus ja näkymien käsittely on tarkoituksenmukaista.

Mikäli suunnittelijan ohjelmistossa ei ole mahdollista toteuttaa näitä ratkaisuja esimerkiksi näkymien avulla, voi suunnittelija käyttää projektin koordinaatistosta poikkeavaa koordinaatistoa omassa työssään.


<img width="384" height="335" alt="Suunnittelijan koordinaatisto" src="https://github.com/user-attachments/assets/acc2c361-8c3e-411d-bea7-6158deb8d653" /><br> Kuva 4.Suunnittelijan koordinaatisto<br>

### 3.2	Kerrostiedot IFC-mallissa
IFC-mallissa rakenneosat kuuluvat tiettyyn rakennukseen (```IfcBuilding```), lohkoon (osittainen ```IfcBuilding```) ja kerrokseen (```IfcBuildingStorey```). Rakennuksen lohko ei ole IFC-formaatissa vastaava käsite kuin rakennus ja kerros. IFC-formaatti mahdollistaa hierarkisuuden siten että, rakennus voi koostua useasta rakennuksesta, jotka voivat sisältää osittaisia rakennuksia, jotka ovat on tarkoitettu raken-nuksen lohkojen määrittelyyn. Useat eri suunnittelualojen mallinnusohjelmat perustuvat siihen, että mallia tehdään rakennuksittain ja kerroksittain. Nämä sijaintitiedot ovat tärkeitä asennusta ja valmistusta suunniteltaessa ja toteutuksessa. Ja usein myös jo tarjouslaskentavaiheessa kustannusten jaot-telua varten on tietomallien lohkojako tarpeellinen. 
Kerrostiedossa on havaittu haasteeksi mm. kerrostiedon puuttuminen, väärin syötetty kerrostiedot ja monenlaiset kirjoitustavat ja -virheet. 

<img width="197" height="246" alt="Kuva5" src="https://github.com/user-attachments/assets/4b8df90e-22ef-445d-ba3f-3e6135d2d7e0" /><br> Kuva 6. Esimerkki kuinka välilyönnit lisäävät kerroksia hankkeen tietomalliin

> [!TIP]
> **Ohjeita tietojen lisäämiseen hankkeissa:**
> * Rakennesuunnittelija lisää sovitun lohko- ja kerrosjaon tietomalliin.<br>
> * Lohko- ja kerrostiedot tarkistetaan ennen tietomallitoimituksia.<br>
> * Kerrostieto kirjoitetaan ilman ”.krs” tai muita tiedonsiirtoa sotkevia selitetekstejä, vain numeroita tai kirjaimia. Kerrostieto on IFC-mallissa kerrostietonimisessä tietokentässä (IfcBuildingStorey), joten arvo ei tarvitse selittävää tekstiä siitä, että tiedolla tarkoitetaan kerrosta.<br>
> * Kerroksen muodostavat kantavat ja ei-kantavat seinät ja pilarit niiden yläpuolinen välipohja. Usean kerrosten läpi menevät rakenteet (esim. pilarit) alimpaan kerrokseen, jossa ne asennetaan.<br>
> * Rakennemallissa kerroksina myös ”POHJARAKENTEET, PERUSTUKSET, ALAPOHJA, KELLARI”. Eli paalut ja anturarakenteet, sokkelit ja alapohjan rakenteet.<br>
> * Kerrokset nimet aina isolla kirjaimella, jotta ei tule eri tavalla kirjoitettuna. Esim. Kellari vs KELLARI.<br> 
> * Rakenteellinen pintalaatta nimetään saman kerrokseen kuin sen alapuoliset rakenteet.<br>
> * Yläpohjassa esim. ylimmän ontelolaattatason yläpuoliset vesikattorakenteet nimetään erikseen omaksi kerrokseksi, esim. YLÄPOHJA.<br>
 
<img width="385" height="159" alt="Kuva6" src="https://github.com/user-attachments/assets/7d6217e4-ef5a-44cf-adb9-c6b1322c298c" /><br>Kuva 7. Esimerkki kerrosten nimeämisestä

---

#### 3.3 Lohkotiedot IFC-mallissa
Rakennuksen lohkojako on keskeinen mutta luonteeltaan kontekstisidonnainen osa sijaintitietoa. Lohko ei ole yksiselitteinen tai pysyvä rakennuksen ominaisuus, vaan se muodostuu useiden suunnittelullisten, rakenteellisten ja tuotannollisten tekijöiden yhteisvaikutuksesta. Lohkojakoon vaikuttavat esimerkiksi palo-osastointi, rakennuksen toiminnallinen jäsentely, runkojärjestelmä, tekniset järjestelmät, perustamisolosuhteet, työvaiheiden ajoitus sekä tontin koko ja geometria. Näiden tekijöiden merkitys vaihtelee hanketyypin ja hankevaiheen mukaan, minkä vuoksi myös lohkotiedon käyttötarkoitukset muuttuvat hankkeen edetessä.

IFC-mallissa lohko ei ole samalla tavoin eksplisiittisesti määritelty tilallinen yksikkö kuin rakennus tai kerros. Käytännössä lohkot mallinnetaan usein osittaisina rakennuksina, rakennuksen alirakenteina tai ominaisuustietoina, jotka liitetään rakennusosiin. Tämä mahdollistaa lohkojaon esittämisen tietomallissa, mutta ei takaa lohkotiedon yhdenmukaista tulkintaa tai siirrettävyyttä eri järjestelmien välillä. Toimitusketjun näkökulmasta lohko toimii kuitenkin usein keskeisenä viittauspisteenä tuotannon suunnittelussa, toimitusten kohdistamisessa ja asennusjärjestyksen ohjauksessa.

Teollisissa ja logistisissa hallirakennuksissa lohkojako perustuu tyypillisesti rakennuksen toiminnallisiin tai rakenteellisiin kokonaisuuksiin. Rakennus jaetaan laajoihin päälohkoihin, joiden sisälle muodostuu edelleen useita asennuslohkoja. Näiden avulla betonielementtien valmistusta, toimituksia ja asennuksia voidaan vaiheistaa ja ajoittaa hallitusti.

<img width="642" height="289" alt="Kuva7" src="https://github.com/user-attachments/assets/01b3ef00-47f5-41a8-ac34-afaf78d2c2e6" /><br> Kuva 8. Logistiikka-halli lohkojako esimerkki

Asuinkerrostalokohteissa lohkojako perustuu usein liikuntasaumoihin ja rakennuksen rakenteelliseen jaotteluun. Näin muodostuvat lohkot jakautuvat edelleen porrashuoneiden mukaisiin kokonaisuuksiin. Tässä kontekstissa lohko toimii paitsi rakenteellisena myös aikataulullisena ja logistisena ohjausrakenteena betonielementtien toimitusketjussa.

<img width="583" height="260" alt="Kuva8" src="https://github.com/user-attachments/assets/13bfacc9-db06-435f-9720-62275f2f1c8f" /><br> Kuva 9. Asuinkerrostalon lohkojako esimerkki

Pienemmissä rakennuksissa, kuten pistetaloissa, erillinen lohkojako ei aina ole tarkoituksenmukainen. Tällöin porrashuone tai jopa yksittäinen huoneisto muodostaa käytännössä asennuslohkon, jonka ympärille elementtien toimitukset ja asennus ajoitetaan. Tämä osoittaa, että lohko ei ole universaali rakennuksen ominaisuus, vaan hankekohtainen abstrahointi, jonka tarpeellisuus ja tarkkuustaso vaihtelevat.

<img width="421" height="381" alt="Kuva9" src="https://github.com/user-attachments/assets/c1822aeb-8444-499b-a0b8-5cc13a73ec1d" /><br> Kuva 10. Pistetalo esimerkki

> [!TIP]
> **Huomio hankekäytännöistä:**
> 
> Lohko- ja kerrostiedon määrittely jää käytännössä usein rakennesuunnittelijan vastuulle, ja tietojen oikeellisuus tarkistetaan ennen tietomallien luovutusta. Samalla jää avoimeksi kysymys siitä, missä määrin lohkotiedon tulisi olla eksplisiittisesti määritelty myös hankkeissa, joissa lohkojako on rakenteellisesti yksinkertainen.<br>
> 
> Toimitusketjun näkökulmasta on perusteltua pohtia, tulisiko lohkojakotieto esittää järjestelmällisesti kaikissa kohteissa, myös tilanteissa joissa rakennus koostuu vain yhdestä porrashuoneesta tai joissa erillistä lohkojakoa ei muutoin koeta tarpeelliseksi. Tällöin lohko ei välttämättä kuvaa rakennuksen fyysistä jakautumista, vaan toimii loogisena viittauspisteenä, jonka avulla betonielementit voidaan kohdistaa, tunnistaa ja liittää toimitus- ja asennusprosessien tapahtumatietoon yhdenmukaisella tavalla.


---

## 4 Toimialan näkökulma – koordinaatistosta kohti toimitusketjun sijaintitietoa

Rakennusalan viimeaikaisissa kehityshankkeissa on tunnistettu, että tietomallien koordinaattitiedon nykyinen käyttö painottuu vahvasti suunnittelun ja viranomaisprosessien tarpeisiin, kun taas toimitusketjun operatiiviset käyttötapaukset jäävät heikosti tuetuiksi. Hankkeissa, kuten Rava3Pro- ja BETK-kokonaisuuksissa, koordinaattitietoon liittyviä vaatimuksia on täsmennetty erityisesti IFC-mallien validoinnin ja viranomaiskäytön näkökulmasta. Tästä huolimatta alalla ei ole vielä muodostunut yhtenäisiä ja laajasti sovellettuja käytäntöjä, joilla koordinaattipohjainen sijaintitieto kytkeytyisi systemaattisesti fyysisiin tuotteisiin ja toimitusketjun tapahtumiin.

Toimitusketjun näkökulmasta pelkkä geometrinen tai absoluuttinen sijainti ei ole riittävä. Keskeistä on sijaintitiedon kontekstualisointi siten, että se on tulkittavissa tuotannon, logistiikan ja asennuksen ohjausta varten. Tämä edellyttää siirtymää koordinaattikeskeisestä ajattelusta kohti tapahtuma- ja kohdepohjaista sijaintitietoa, jossa fyysiset tuotteet voidaan yksilöidä, paikantaa ja liittää ajallisiin sekä prosessuaalisiin tapahtumiin koko toimitusketjun läpi.

BETK-hankkeessa kehitetty lähestymistapa betonielementtien tuoteyksilöintiin ja -tunnistamiseen GS1 standardien avulla muodostaa keskeisen teknisen edellytyksen tälle siirtymälle. Yksilöivä tuotetunniste mahdollistaa fyysisen betonielementin kytkemisen digitaaliseen tapahtuma- ja sijaintitietoon esimerkiksi RFID-teknologian avulla. RFID-lukutapahtumat voivat tuottaa automaattisesti tietoa elementin sijainnista, siirtymistä ja käsittelyvaiheista, ja tämä tieto voidaan välittää edelleen toimitusketjun osapuolten välillä rakenteellisissa digitaalisissa sanomissa, kuten Peppol-pohjaisissa hankinta- ja toimitussanomissa.

Koordinaattitiedon välittäminen toimitusketjussa tarjoaa merkittäviä mahdollisuuksia, mutta samalla se paljastaa vakioinnin puutteen keskeiseksi rajoitteeksi. Ilman yhteisesti sovittuja tietorakenteita, semantiikkaa ja käyttötapoja koordinaattitieto jää helposti järjestelmäkohtaiseksi tai kontekstittomaksi. BETK-hankkeessa tietomalliin lisätty betonielementin painopisteen koordinaattitieto edustaa tarkoituksellisesti kevyttä ratkaisua tähän ongelmaan. Painopisteen koordinaatti ei pyri kuvaamaan koko elementin geometriaa, vaan toimii yksiselitteisenä ja laskennallisesti yksinkertaisena sijaintireferenssinä, joka voidaan hyödyntää tuotannon suunnittelussa, kuljetusten optimoinnissa, nostojen ohjauksessa ja asennusjärjestyksen hallinnassa.

<img width="642" height="211" alt="Kuva4" src="https://github.com/user-attachments/assets/a6dacf51-5744-4673-9c8b-0c5f8f0d53d5" /><br>Kuva 5. Kuorielementin painopisteen koordinaatit

Tämä lähestymistapa osoittaa, että toimitusketjun sijaintitiedon kehittäminen ei välttämättä edellytä laajoja muutoksia IFC-standardin rakenteisiin tai raskaita semanttisia laajennuksia. Sen sijaan vaikuttavia käyttötapauksia voidaan avata lisäämällä rajattuja, mutta merkityksellisiä sijaintiattribuutteja, jotka voidaan liittää yksilöityihin tuotteisiin ja välittää eteenpäin tapahtumatiedon yhteydessä. Näin sijaintitieto toimii linkkinä tietomallien, fyysisten tuotteiden ja toimitusketjun operatiivisten prosessien välillä.

---

### 4.1 Sijaintitietojen välitys sähköisissä hankinta-toimitus sanomissa

Toimitusketjun näkökulmasta keskeinen kysymys ei ole ainoastaan sijaintitiedon mallintaminen, vaan sen siirrettävyys järjestelmien välillä. Peppol-pohjaiset hankinta- ja toimitussanomat tarjoavat olemassa olevan infrastruktuurin, jossa sijaintitietoa voidaan välittää rakenteellisessa muodossa tilausten, toimitusten ja tapahtumien yhteydessä. Kun asennuslohko-, kerros- ja tilatiedot johdetaan tietomallista ja liitetään osaksi sanomaliikennettä, voidaan fyysisten toimitusten kohdistaminen tehdä johdonmukaisesti ilman manuaalista uudelleentulkintaa.

Alla esitetty esimerkkirakenne havainnollistaa, miten sijaintitietoa voidaan jäsentää hierarkkisesti sähköisissä hankinta- ja toimitussanomissa siten, että se tukee sekä tietomallipohjaista suunnittelua että toimitusketjun operatiivista ohjausta.

```yaml
Sijaintitiedot Peppol sanomissa:
<Rakennus>
<RAK-lohko>
<Kerros>
<Asennuslohko 1>
<Asennuslohko 2>
<Asennuslohko 3>
<Rappu>
<Tila>
<Tehtaan valupäivä>
<Toimituspäivä>
<Toimitusaika>
<Vaihtoehtoiset toimitusajat>

```
Koodi 1. esimerkki sijaintitietojen välittämisestä sähköisissä hankinta-toimitus sanomissa

---

### 4.2 Toimitusketjun näkökulma: BEAst Label -esimerkki Ruotsista
Ruotsalaisen rakennusteollisuuden tarpeisiin kehitetty BEAst Label on rakennusalan toimitusketjujen tueksi laadittu kollietikettistandardi, jonka tarkoituksena on yhdenmukaistaa tavaroiden ja materiaalien merkintä ja tunnistettavuus toimitusprosessin eri vaiheissa. Standardin tekninen tehtävä on mahdollistaa rakennusmateriaalien yksiselitteinen tunnistus, paikannus ja ohjattu käsittely työmaalla sekä tukea sähköistä tiedonvaihtoa toimitusketjun osapuolten välillä. BEAst Label perustuu GS1-järjestelmään ja sen SSCC-tunnuksiin (Serial Shipping Container Code) sekä hyödyntää GS1-128-, DataMatrix- ja QR-viivakoodeja, joita käytetään muun muassa kolli-ID:n, GPS-koordinaattien ja yhteystietojen koneelliseen lukuun.<br>

Standardin ydinperiaate on, että fyysinen etiketti ja sähköinen tiedonvaihto muodostavat yhdenmukaisen tietorakenteen. Etikettien tiedot tuotetaan automaattisesti BEAst Supply Material -standardin mukaisesta sähköisestä tilausviestistä (EDI), jossa määritellään toimituksen kohdetiedot kuten rakennus, porrashuone, kerros, huone ja purkupaikka. Tämän rakenteen ansiosta toimittajat voivat tulostaa kollikohtaiset etiketit samansisältöisinä eri toimituksissa ilman manuaalista tietojen syöttöä.<br>

BEAst Labelista on neljä eri versiota, jotka on suunniteltu erilaisiin käyttötarkoituksiin. Label A soveltuu lavatavaralle ja sisältää suurikokoiset kohdekentät, jotka helpottavat etäluettavuutta esimerkiksi trukin käytön yhteydessä. Label B on tarkoitettu muille pakkauksille ja alikolleille, ja se sisältää tarkemmat tiedot kollin sisällöstä. Label C toimii lisäluettelona tilanteissa, joissa tarvitaan enemmän tietokenttiä kuin Label B tarjoaa. Label D on tuote- tai artikkelikohtainen etiketti, joka täydentää valmistajan omaa merkintää ja mukautetaan tuotekohtaisesti.<br>

Etiketti sisältää sekä tekstimuotoisia tietoja että viivakoodeja, joita voidaan esittää yksiulotteisina (1D) tai kaksiulotteisina (2D) koodeina, kuten DataMatrix tai QR. Näin voidaan välittää suuri määrä tietoa kompaktissa muodossa ja varmistaa tiedon koneellinen luettavuus koko toimitusketjun läpi. BEAst Label tukee myös GPS-pohjaisten purkupaikkakoordinaattien ja yhteystietojen liittämistä etikettiin.<br>

Standardi käyttää applikointitunnistetta (AI) 90 erotuksena STE/STILL-kuljetusetiketin tunnisteesta (AI) 00, mikä mahdollistaa järjestelmien rinnakkaisen käytön samalla SSCC-tunnisteella. BEAst Labelia sovelletaan toimitusketjun eri vaiheissa materiaalien tunnistamiseen, sähköisten sanomien tietosisällön yhdistämiseen ja toimitusten kohdistamiseen työmaan sisäisiin loppukohteisiin.<br>

BEAst Label muodostaa teknisen rajapinnan fyysisen etiketin ja sähköisen tiedonhallinnan välillä. Sen avulla toimitusketjun tiedot voidaan esittää yhteismitallisesti eri järjestelmissä ja varmistaa, että tunnistetiedot säilyvät yhdenmukaisina koko materiaalivirran läpi rakennuslogistiikassa.

<img width="2693" height="2190" alt="Kuva14" src="https://github.com/user-attachments/assets/f1eea75b-1960-4119-8ee2-9cb33f9283cb" /><br> Kuva X. [BEAst Label](https://beast.se/standarder/beast-label/#) -kollietikettien hyödyntäminen materiaalitoimituksissa

	
	
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

​ 
[^1]:Domer & Bernadello, 2023, Interoperability: An introduction to IFC and buildingSmart standards integrating infrastructure modeling
​ 

​ 

​ 

​​ 
 
