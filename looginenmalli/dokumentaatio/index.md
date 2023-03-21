---
layout: "default"
description: ""
id: "dokumentaatio"
status: "Keskeneräinen"
---

# Loogisen tason rakennuskohteiden ja huoneistojen tietomalli

{:.no_toc}

{% include common/note.html content="Tietomallin dokumentaatio on toistaiseksi puutteellinen. Täydelliset luokkien, niiden attribuuttien ja assosiaatioden kuvaukset laaditaan mahdollisimman pian" %}

1.  {:toc}

## Yleistä

Loogisen tason Rakennuskohteiden ja huoneistojen tietomalli määrittelee yhteiset tietorakenteet, joita käytetään rakennusten, rakennelmien ja muiden rakennuskohteiden, sekä rakennusten sisältämien rakennettujen tilojen ja huoneistojen tietojen kuvaamiseen koneluettavassa rakenteisessa paikkatietomuodossa. Tietomallin luokkia tulee käyttää tietomallin [elinkaari](../elinkaarisaannot.html)- ja [laatusääntöjen](../laatusaannot.html) mukaisesti. Looginen tietomalli pyrkii olemaan mahdollisimman riippumaton tietystä toteutusteknologiasta tai tiedon fyysisestä esitystavasta (esim. relaatiotietokanta, tietyn ohjelmointikielen tietorakenteet, XML, JSON).

## Normatiiviset viittaukset

Seuraavat dokumentit ovat välttämättömiä tämän dokumentin täysipainoisessa soveltamisessa:

-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/" title="Rakennetun ympäristön yhteiset tietokomponentit" %}, versio 1.0
-   [ISO 639-2:1998 Codes for the representation of names of languages --- Part 2: Alpha-3 code](https://www.iso.org/standard/4767.html "ISO 639-2:1998 Codes for the representation of names of languages — Part 2: Alpha-3 code")
-   [ISO 8601-1:2019 Date and time --- Representations for information interchange --- Part 1: Basic rules](https://www.iso.org/standard/70907.html "ISO 8601-1:2019 Date and time — Representations for information interchange — Part 1: Basic rules")
-   [ISO 19103:2015 Geographic information --- Conceptual schema language](https://www.iso.org/standard/56734.html "ISO 19103:2015 Geographic information — Conceptual schema language")
-   [ISO 19107:2019 Geographic information --- Spatial schema](https://www.iso.org/standard/66175.html "ISO 19107:2019 Geographic information — Spatial schema")
-   [ISO 19108:2002 Geographic information --- Temporal schema](https://www.iso.org/standard/26013.html "ISO 19108:2002 Geographic information — Temporal schema")
-   [ISO 19109:2015 Geographic information --- Rules for application schema](https://www.iso.org/standard/59193.html "ISO 19109:2015 Geographic information — Rules for application schema")
-   [ISO 19505-2:ISO/IEC 19505-2:2012, Information technology --- Object Management Group Unified Modeling Language (OMG UML) --- Part 2: Superstructure](https://www.iso.org/standard/52854.html "ISO/IEC 19505-2:2012, Information technology — Object Management Group Unified Modeling Language (OMG UML) — Part 2: Superstructure")

## Standardienmukaisuus

Kuvattu tietomalli perustuu [ISO 19109](https://www.iso.org/standard/59193.html "ISO 19109:2015 Geographic information — Rules for application schema")-standardin yleinen kohdetietomalliin (General Feature Model, GFM), joka määrittelee rakennuspalikat paikkatiedon ISO-standardiperheen mukaisten sovellusskeemojen määrittelyyn. GFM kuvaa muun muassa metaluokat `FeatureType`, `AttributeType` ja `FeatureAssociationType`. Kaavatietomallissa kaikki tietokohteet, joilla on tunnus ja jotka voivat esiintyä erillään toisista kohteista on määritelty kohdetyypeinä (stereotyyppi `FeatureType`. Sellaiset tietokohteet, joilla ei ole omaa tunnusta ja jotka voivat esiintyä vain kohdetyyppien attribuuttien arvoina on määritelty [ISO 19103](https://www.iso.org/standard/56734.html "ISO 19103:2015 Geographic information — Conceptual schema language")-standardin `DataType`-stereotyypin avulla.

[ISO 19109](https://www.iso.org/standard/59193.html "ISO 19109:2015 Geographic information — Rules for application schema") -standardin lisäksi tietomalli perustuu muihin paikkatiedon ISO-standardeihin, joista keskeisimpiä ovat [ISO 19103](https://www.iso.org/standard/56734.html "ISO 19103:2015 Geographic information — Conceptual schema language") (UML-kielen käyttö paikkatietojen mallinnuksessa), [ISO 19107](https://www.iso.org/standard/66175.html "ISO 19107:2019 Geographic information — Spatial schema") (sijaintitiedon mallintaminen) ja [ISO 19108](https://www.iso.org/standard/26013.html "ISO 19108:2002 Geographic information — Temporal schema") (aikaan sidotun tiedon mallintaminen).

### Muulla määritellyt luokat ja tietotyypit

#### Rakennetun ympäristön yhteiset tietokomponentit

Malli perustuu {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/" title="Rakennetun ympäristön yhteiset tietokomponentit" %} -kirjaston määrittelyille. Tässä mallissa hyönnetään suoraan seuraavia kirjaston luokkia:

-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/#versioituobjekti" title="VersioituObjekti" %}
-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/#liiteasiakirja" title="Liiteasiakirja" %}
-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/#rakennetunympäristönkohde" title="RakennetunYmpäristönKohde" %}
-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/#osoite" title="Osoite" %}
-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/#kiinteistö" title="Kiinteistö" %}
-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/#toimija" title="Toimija" %}
-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/#hallinnollinenAlue" title="HallinnollinenAlue" %}
-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/#alueidenkäyttöjarakentamisasia" title="AlueidenkäyttöJaRakentamisasia" %}
-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/#suunnitelmanlaatija" title="SuunnitelmanLaatija" %}
-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/#suureenarvo" title="SuureenArvo" %}
-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/#suure" title="Suure" %}
-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/#koodiarvo" title="Koodiarvo" %}
-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/#numeerinenarvo" title="NumeerinenArvo" %}
-   {% include common/moduleLink.html moduleId="yhteisetkomponentit" path="looginenmalli/dokumentaatio/#abstraktiasiakirjanlaji" title="AbstraktiAsiakirjanLaji" %}

#### CharacterString {#characterstring}

Kuvaa yleisen merkkijonon, joka koostuu 0..\* merkistä, merkkijonon pituudesta, merkistökoodista ja maksimipituudesta. Määritelty rajapinta-tyyppisenä [ISO 19103](https://www.iso.org/standard/56734.html "ISO 19103:2015 Geographic information — Conceptual schema language")-standardissa.

#### LanguageString {#languagestring}

Kuvaa kielikohtaisen merkkijonon. Laajentaa [CharacterString](#characterstring)-rajapintaa lisäämällä siihen `language`-attribuutin, jonka arvo on `LanguageCode`-koodiston arvo. Kielikoodi voi [ISO 19103](https://www.iso.org/standard/56734.html "ISO 19103:2015 Geographic information — Conceptual schema language")-standardin määritelmän mukaan olla mikä tahansa ISO 639 -standardin osa.

#### Number {#number}

Kuvaa yleisen numeroarvon, joka voi olla kokonaisluku, desimaaliluku tai liukuluku. Määritelty rajapintana [ISO 19103](https://www.iso.org/standard/56734.html "ISO 19103:2015 Geographic information — Conceptual schema language")-standardissa.

#### Integer {#integer}

Laajentaa [Number](#number)-rajapintaa kuvaamaan numeron, joka on kokonaisluku ilman murto- tai desimaaliosaa. Määritelty rajapintana [ISO 19103](https://www.iso.org/standard/56734.html "ISO 19103:2015 Geographic information — Conceptual schema language")-standardissa.

#### Decimal {#decimal}

Laajentaa [Number](#number)-rajapintaa kuvaamaan numeron, joka on desimaaliluku. Decimal-rajapinnan toteuttava numero voidaan ilmaista virheettä yhden kymmenysosan tarkkuudella. Määritelty rajapintana [ISO 19103](https://www.iso.org/standard/56734.html "ISO 19103:2015 Geographic information — Conceptual schema language")-standardissa. Decimal-numeroita käytetään, kun desimaalien käsittelyn tulee olla tarkkaa, esim. rahaan liityvissä tehtävissä.

#### Real

Laajentaa [Number](#number)-rajapintaa kuvaamaan numeron, joka on tarkkudeltaan rajoitettu liukuluku. Real-rajapinnan numero voi ilmaista tarkasti vain luvut, jotka ovat 1/2:n (puolen) potensseja. Määritelty rajapintana [ISO 19103](https://www.iso.org/standard/56734.html "ISO 19103:2015 Geographic information — Conceptual schema language")-standardissa. Käytännössä esitystarkkuus riippuu numeron tallentamiseen varattujen bittien määrästä, esim. `float (32-bittinen)` (tarkkuus 7 desimaalia) ja `double (64-bittinen)` (tarkkuus 15 desimaalia).

#### Measure {#measure}

Mittattavan, numeerisen tiedon ja sen antamiseen käytetyn mittayksikön kuvaamiseen käytettävä yleiskäyttöinen tietorakenne. Määritelty [ISO 19103](https://www.iso.org/standard/56734.html "ISO 19103:2015 Geographic information — Conceptual schema language")-standardissa.

#### TM_Object {#tm_object}

Aikamääreiden yhteinen yläluokka, käytetään, mikäli arvo voi olla joko yksittäinen ajanhetki tai aikaväli. Määritelty luokkana [ISO 19108](https://www.iso.org/standard/26013.html "ISO 19108:2002 Geographic information — Temporal schema")-standardissa.

#### TM_Instant {#tm_instant}

Kuvaa yksittäisen ajanhetken 0-ulotteisena ajan geometriana, joka vastaa pistettä avaruudessa. Määritelty luokkana [ISO 19108](https://www.iso.org/standard/26013.html "ISO 19108:2002 Geographic information — Temporal schema")-standardissa. Aikapisteen arvo on määritelty `TM_Position`-luokalla yhdistelmänä [ISO 8601](https://www.iso.org/standard/70907.html "ISO 8601-1:2019 Date and time — Representations for information interchange — Part 1: Basic rules")-standin mukaisia päivämäärä- tai kellonaika-kenttiä tai näiden yhdistelmää, tai muuta `TM_TemporalPosition`-luokan avulla kuvattua aikapistettä. Viimeksi mainitun luokan attribuutti `indeterminatePosition` mahdollistaa ei-täsmällisen ajanhetken ilmaisemisen liittämällä mahdolliseen arvoon luokittelun tuntematon, nyt, ennen, jälkeen tai nimi.

#### TM_Period

Kuvaa aikavälin [TM_Instant](#tm_instant)-tyyppisten `begin`- ja `end`-attribuuttien avulla. Molemmat attribuutit ovat pakollisia, mutta voivat sisältää tuntemattoman arvon `indeterminatePosition = unknown` -attribuutin arvon avulla annettuna. Määritelty luokkana [ISO 19108](https://www.iso.org/standard/26013.html "ISO 19108:2002 Geographic information — Temporal schema")-standardissa.

#### URI

Määrittää merkkijonomuotoisen Uniform Resource Identifier (URI) -tunnuksen [ISO 19103](https://www.iso.org/standard/56734.html "ISO 19103:2015 Geographic information — Conceptual schema language")-standardissa. URIa voi käyttää joko pelkkänä tunnuksena tai resurssin paikantimena (Uniform Resource Locator, URL).

#### Geometry

Kaikkien geometria-tyyppien yhteinen rajapinta [ISO 19107](https://www.iso.org/standard/66175.html "ISO 19107:2019 Geographic information — Spatial schema")-standardissa. Tyypillisimpiä [ISO 19107](https://www.iso.org/standard/66175.html "ISO 19107:2019 Geographic information — Spatial schema")-standardin Geometry-rajapintaa laajentavia rajapintoja ovat `Point`, `Curve`, `Surface` ja `Solid` sekä `Collection`, jota käyttämällä voidaan kuvata geometriakokoelmia (multipoint, multicurve, multisurface, multisolid).

#### Point {#point}

Täsmälleen yhdestä pisteestä koostuva geometriatyyppi. Määritelty rajapintana [ISO 19107](https://www.iso.org/standard/66175.html "ISO 19107:2019 Geographic information — Spatial schema")-standardissa.

## Tietomallin yleispiirteet

## Rakennuskohteet

### Rakennuskohde {#rakennuskohde}

Englanninkielinen nimi: **building object**

Kuvaa käsitteen [Rakennuskohde](../../kasitemalli/#rakennuskohde), Stereotyyppi: FeatureType (kohdetyyppi)

Suunniteltujen tai toteutettujen rakentamis- tai purkamistoimenpiteiden kohde. Rakennuskohde voi olla rakennus, rakennelma, huoneisto tai erityistä toimintaa varten rakennettava alue (esim. pysäköintialue).

**Ominaisuudet**

| Nimi                             | Name       | Tyyppi                                                                | Kardinaliteetti | Kuvaus                                                                                                                                                                                                                             |
|---------------|---------------|---------------|---------------|---------------|
| RakennuskohteenTiedonLaji        |            | [RakennuskohteenTiedonLaji](#RakennuskohteenTiedonLaji)               | 1               |                                                                                                                                                                                                                                    |
| RakennuskohteenSijaintitiedot    |            | [Sijainti](#sijainti)                                                 | 0..\*           | paikka, jossa jokin sijaitsee                                                                                                                                                                                                      |
| kokonaisala                      | total area | [Integer](#integer)                                                   | 1               | Rakennuksen pinta-ala, johon lasketaan ulkomitoin kaikkien kerrosten, kellareiden ja lämpöeristettyjen ullakkohuoneiden pinta-alat. Pinta-alaan ei lasketa parvekkeita, katoksia eikä tiloja, joissa vapaa korkeus on alle 160 cm. |
| RakennuskohteenTiedonLähteenLaji |            | [RakennusKohteenTiedonLähteenLaji](#rakennuskohteentiedonlähteenlaji) | 1               |                                                                                                                                                                                                                                    |

**Assosiaatiot**

| Roolinimi          | Role name                  | Kohde                                           | Kardinaliteetti | Kuvaus                                                                                                                                |
|---------------|---------------|---------------|---------------|---------------|
| Rakennustietomalli | building information model | [RakennuksenTietomalli](#rakennuksentietomalli) | 1               | tietomalli, joka mahdollistaa rakennustietojen vaihdon, jakamisen ja käytön                                                           |
| paikka             | building site              | [Rakennuspaikka](#rakennuspaikka)               | 1               | Kiinteistö tai muu määritelty alue, joka rakentamisluvan yhteydessä osoitetaan rakennuksen tai muun rakennuskohteen sijaintipaikaksi. |
| Sijaintikiinteistö |                            | [Kiinteisto](#kiinteisto)                       | 1               | kiinteistörekisteriin merkitty maan tai vesialueen omistuksen yksikkö                                                                 |

### RakennusTaiSenOsa

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [RakennusTaiSenOSa](../../kasitemalli/#rakennustaisenosa), yleistää luokkia Rakennus, RakennuksenOsa, Rakennuskohde, Stereotyyppi: FeatureType (kohdetyyppi)

| Nimi                                | Name                            | Tyyppi                                                                      | Kardinaliteetti | Kuvaus                                                                                 |
|---------------|---------------|---------------|---------------|---------------|
| elinkaarenvaihe                     | life-cycle stage                | [RakennuksenElinkaarenVaihe](#rakennuksenelinkaarenvaihe)                   | 1               |                                                                                        |
| valmistumispäivämäärä               | completion date                 | date                                                                        | 0..1            |                                                                                        |
| suojelutapa                         |                                 | [Suojelutapa](#suojelutapa)                                                 | 0..1            |                                                                                        |
| kulttuurihistoriallinenMerkittävyys | culture-historical significance | [KulttuurihistoriallinenMerkittävyys](#kulttuurihistoriallinenmerkittävyys) | 1               | Tieto kohteen kulttuurihistoriallisesta merkittävyydestä.                              |
| materiaalitiedot                    |                                 | [Materiaalitiedot](#materiaalitiedot)                                       | 0..1            |                                                                                        |
| Energiatiedot                       |                                 | [Energiatiedot](#energiatiedot)                                             | 0..1            |                                                                                        |
| sisätilojenTiedot                   |                                 | [SisätilojenTiedot](#sisatilojentiedot)                                     | 0..1            |                                                                                        |
| talotekniikkatiedot                 |                                 | [Talotekniikkatiedot](#talotekniikkatiedot)                                 | 0..1            |                                                                                        |
| käyttötiedot                        |                                 | [Rakennuksenkäyttötiedot](#rakennuksenkäyttötiedot)                         | 0..1            |                                                                                        |
| varuste                             | equipment                       | [RakennuksenVaruste](#rakennuksenvaruste)                                   | 0..\*           | Rakennukseen, rakennelmaan tai huoneistoon kiinteästi asennettu järjestelmä tai laite. |

### Rakennus {#rakennus}

Englanninkielinen nimi: **building**

Kuvaa käsitteen [Rakennus](../../kasitemalli/#rakennus), tarkentaa luokkaa RakennusTaiSenOSa, Stereotyyppi: FeatureType (kohdetyyppi)

Omalla sisäänkäynnillä varustettu rakennuskohde, joka on erillinen, kiinteä tai tarkoitettu paikallaan pidettäväksi ja joka sisältää eri toimintoihin tarkoitettua katettua ja yleensä ulkoseinien tai muista rakennelmista erottavien seinien rajoittamaa tilaa.

**Ominaisuudet**

| Nimi                 | Name                          | Tyyppi                                      | Kardinaliteetti | Kuvaus                                                      |
|---------------|---------------|---------------|---------------|---------------|
| pysyväRAkennusTunnus | permanent building identifier | [CharacterString](#characterstring)         | 0..1            | Väestötietojärjestelmään tallennettu pysyvä rakennustunnus. |
| väliaikainenTunnus   | temporary identifier          | [CharacterString](#characterstring)         | 0..1            |                                                             |
| tilapäinen           |                               | boolean                                     | 1               |                                                             |
| purkamisenMääräaika  |                               | date                                        | 0..1            |                                                             |
| osittelu             |                               | [RakennuksenOsittelu](#rakennuksenosittelu) | 0..\*           |                                                             |
| KäyttöJaHuoltoOhje   |                               | [Liiteasiakirja](#liiteasiakirja)           | 0..1            |                                                             |

**Assosiaatiot**

| Roolinimi     | Rolename | Kohde          | Kardinaliteetti | Kuvaus                                                                           |
|---------------|---------------|---------------|---------------|---------------|
| hissi         | Lift     | Hissi          | 0..\*           |                                                                                  |
| sisäänkäynti  | entrance | Sisäänkäynti   | 0..\*           | Portaali kahden tilan välillä; sisätilasta sisätilaan tai ulkotilasta sisätilaan |
| sisältyväTila |          | RakennettuTila | 0..\*           |                                                                                  |

### RakennuksenOsa

Englanninkielinen nimi: **Building section**

Kuvaa käsitteen [RakennuksenOsa](../../kasitemalli/#rakennuksenosa),tarkentaa luokkaa RakennusTaiSenOsa, Stereotyyppi: FeatureType (kohdetyyppi)

Erillinen, kiinteä tai paikallaan pidettäväksi tarkoitettu, omalla sisäänkäynnillä varustettu kokonaisuuden osa, joka sisältää eri toimintoihin tarkoitettua katettua ja yleensä ulkoseinien tai muista rakennelmista erottavien seinien rajoittamaa tilaa. Kun rakennuksessa ei ole seiniä tai kattoa, sitä yleensä kutsutaan rakennelmaksi.

**Ominaisuudet**

| Nimi                  | Name                        | Tyyppi                              | Kardinaliteetti | Kuvaus                                                                                                                                                                                                  |
|---------------|---------------|---------------|---------------|---------------|
| RakennuksenOsanTunnus | building section identifier | [CharacterString](#characterstring) | 1               | Rakennuksen osalle määritetty rakennuksen osan tunnus. Kullakin rakennuksen osalla on erillinen rakennuksen osatunnus. Pysyvä rakennustunnus on jokaisella samaan rakennukseen liittyvällä osalla sama. |

**Assosiaatiot**

| Roolinimi | Rolename | Kohde                                       | Kardinaliteetti | Kuvaus |
|---------------|---------------|---------------|---------------|---------------|
| rakennus  | building | [Rakennus](#rakennus)                       | 1               |        |
| osa       |          | [RakennuksenOsittelu](#rakennuksenosittelu) | 1               |        |

### ErityistäToimintaaVartenRakennettavaAlue

Englanninkielinen nimi: **Area to be built for specific activities**

Kuvaa käsitteen [ErityistäToimintaaVartenRAkennettavaAlue](../../kasitemalli/#erityistatoimintaavartenrakennettavaalue),tarkentaa luokkaa Rakennuskohde, Stereotyyppi: FeatureType (kohdetyyppi)

Erityistä toimintaa varten rakennettava alue, esim. pysäköintialue

**Ominaisuudet**

| Nimi                  | Name                                             | Tyyppi                                                                                                  | Kardinaliteetti | Kuvaus                                                 |
|---------------|---------------|---------------|---------------|---------------|
| laji                  | type of area to be built for specific activities | [ErityistäToimintaaVartenRAkennettavanAlueenTyyppi](#erityistatoimintaavartenrakennettavanalueentyyppi) | 1               | Erityistä toimintaa varten rakennettavan alueen tyyppi |
| verkostoliittymä      | network connection                               | [Verkostoliittymä](#verkostoliittymä)                                                                   | 0..\*           |                                                        |
| varuste               | Equipment                                        | [rakennuksenVaruste](#rakennuksenvaruste)                                                               | 0..\*           |                                                        |
| valmistumispäivämäärä | completion date                                  | date                                                                                                    | 1               |                                                        |
| tilapäinen            | temporary                                        | boolean                                                                                                 | 1               |                                                        |
| purkamisenMääräaika   |                                                  | date                                                                                                    | 0..1            |                                                        |

### RakennelmaTaiSenOsa

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [RakennelmaTaiSenOSa](../../kasitemalli/#rakennelmataisenosa), yleistää [rakennelma](#rakennelma) ja [rakennelmanosa](#rakennelmanosa), tarkentaa rakennuskohde, Stereotyyppi: FeatureType (kohdetyyppi)

**Ominaisuudet**

| Nimi                                | Name                            | Tyyppi                                                                      | Kardinaliteetti | Kuvaus                                                                                 |
|---------------|---------------|---------------|---------------|---------------|
| elinkaarenVaihe                     | life-cycle stage                | [RakennuksenElinkaarenVaihe](#rakennuksenelinkaarenvaihe)                   | 1               |                                                                                        |
| valmistumispäivämäärä               | completion date                 | date                                                                        | 1               |                                                                                        |
| suojelutapa                         |                                 | [Suojelutapa](#suojelutapa)                                                 | 0..1            |                                                                                        |
| KulttuurihistoriallinenMerkittävyys | culture-historical significance | [KulttuurihistoriallinenMerkittävyys](#kulttuurihistoriallinenmerkittavyys) | 1               | Tieto kohteen kulttuurihistoriallisesta merkittävyydestä.                              |
| materiaalitiedot                    |                                 | [Materiaalitiedot](#materiaalitiedot)                                       | 0..1            |                                                                                        |
| energiatiedot                       |                                 | [Energiatiedot](#energiatiedot)                                             | 0..1            |                                                                                        |
| ulkokuorenTiedot                    |                                 | [UlkokuorenTiedot](#ulkokuorentiedot)                                       | 0..1            |                                                                                        |
| Talotekniikkatiedot                 |                                 | [Talotekniikkatiedot](#talotekniikkatiedot)                                 | 0..1            |                                                                                        |
| käyttötarkoitus                     | purpose of structure            | [Rakennelmankäyttötarkoitus](#rakennelmankayttotarkoitus)                   | 0..1            | Rakennelman käyttötarkoitus.                                                           |
| varuste                             | Equipment                       | [RakennuksenVaruste](#rakennuksenvaruste)                                   | 0..\*           | Rakennukseen, rakennelmaan tai huoneistoon kiinteästi asennettu järjestelmä tai laite. |

### Rakennelma {#rakennelma}

Englanninkielinen nimi: **structure**

Kuvaa käsitteen [Rakennelma](../../kasitemalli/#rakennelma), tarkentaa luokkaa RakennelmaTaiSenOSa, Stereotyyppi: FeatureType (kohdetyyppi)

Rakennuskohde, jota alueen rakennusvalvontaviranomainen ei sen käyttötarkoituksen, koon, muodon tai väliaikaisuuden vuoksi pidä rakennuksena

**Ominaisuudet**

| Nimi                 | Name                          | Tyyppi                              | Kardinaliteetti | Kuvaus                                                      |
|---------------|---------------|---------------|---------------|---------------|
| Pysyvärakennustunnus | permanent building identifier | [CharacterString](#characterstring) | 0..1            | Väestötietojärjestelmään tallennettu pysyvä rakennustunnus. |
| väliaikainenTunnus   | temporary identifier          | [CharacterString](#characterstring) | 0..1            |                                                             |
| tilapäinen           |                               | boolean                             | 1               |                                                             |
| purkamisenMääräaika  |                               | date                                | 0..1            |                                                             |

**Assosiaatiot**

| Roolinimi | Rolename | Kohde                             | Kardinaliteetti | Kuvaus                                                                                                                                               |
|---------------|---------------|---------------|---------------|---------------|
| osa       |          | [RakennelmanOsa](#rakennelmanosa) | 0..\*           | Osa rakennuskohteesta, jota alueen rakennusvalvontaviranomainen ei sen käyttötarkoituksen, koon, muodon tai väliaikaisuuden vuoksi pidä rakennuksena |

### RakennelmanOsa {#rakennelmanosa}

Englanninkielinen nimi: **Structure section**

Kuvaa käsitteen [RakennelmanOsa](../../kasitemalli/#rakennelmanosa), Stereotyyppi: FeatureType (kohdetyyppi)

Osa rakennuskohteesta, jota alueen rakennusvalvontaviranomainen ei sen käyttötarkoituksen, koon, muodon tai väliaikaisuuden vuoksi pidä rakennuksena.

**Assosiaatiot**

| Roolinimi | Rolename | Kohde                     | Kardinaliteetti | Kuvaus                                                                                                                                               |
|---------------|---------------|---------------|---------------|---------------|
| osa       | section  | [Rakennelma](#rakennelma) | 0..\*           | Osa rakennuskohteesta, jota alueen rakennusvalvontaviranomainen ei sen käyttötarkoituksen, koon, muodon tai väliaikaisuuden vuoksi pidä rakennuksena |

### Rakennustietomalli

Englanninkielinen nimi: **Building Information Model, BIM**

Kuvaa käsitteen [Rakennustietomalli](../../kasitemalli/#rakennustietomalli), Stereotyyppi: FeatureType (kohdetyyppi)

Kuvaus Rakenteinen, koneluettava kuvaus rakennuksen koostumisesta ja ominaisuuksista.

**Ominaisuudet**

| Nimi                            | Name                               | Tyyppi                                               | Kardinaliteetti | kuvaus |
|---------------|---------------|---------------|---------------|---------------|
| laji                            | type of building information model | [RakennustietomallinLaji](#rakennustietomallinlajit) | 1               |        |
| tiedosto                        |                                    | [Liiteasiakirja](#liiteasiakirja)                    | 1               |        |
| jalanjälkiprojektionNurkkapiste |                                    | [point](#point)                                      | 0..1            |        |

**Assosiaatiot**

| Roolinimi | Rolename        | Kohde                           | Kardinaliteetti | Kuvaus                                                                                                                                                                                                        |
|---------------|---------------|---------------|---------------|---------------|
| kohde     | Building object | [RakennusKohde](#rakennuskohde) | 1               | Suunniteltujen tai toteutettujen rakentamis- tai purkamistoimenpiteiden kohde. Rakennuskohde voi olla rakennus, rakennelma, huoneisto tai erityistä toimintaa varten rakennettava alue (esim. pysäköintialue) |

### Rakennussuunnitelma

Englanninkielinen nimi: **Construction plan**

Kuvaa käsitteen [Rakennussuunnitelma](../../kasitemalli/#rakennussuunnitelma), Stereotyyppi: FeatureType (kohdetyyppi)

Rakentamista koskeva suunnitelma, joka on perustana rakennettavan kohteen erityissuunnittelulle ja muulle suunnittelulle.

**Ominaisuudet**

| Nimi     | Name | Tyyppi                            | Kardinaliteetti | Kuvaus |
|----------|------|-----------------------------------|-----------------|--------|
| tiedosto |      | [Liiteasiakirja](#liiteasiakirja) | 1               |        |

**Assosiaatiot**

| Roolinimi        | Rolename        | Kohde                           | Kardinaliteetti | Kuvaus |
|---------------|---------------|---------------|---------------|---------------|
| suunniteltukohde | building object | [Rakennuskohde](#rakennuskohde) | 0..\*           |        |

### Erityissuunnitelma

Englanninkielinen nimi: **Special plan**

Kuvaa käsitteen [Erityissuunnitelma](../../kasitemalli/#erityissuunnitelma), Stereotyyppi: FeatureType (kohdetyyppi)

Rakentamista koskeva suunnitelma, joka laaditaan rakennussuunnitelman lisäksi silloin, kun rakennettavan kohteen ominaisuudet ja laajuus sitä edellyttävät.

**Ominaisuudet**

| Nimi     | Name        | Tyyppi                            | Kardinaliteetti | Kuvaus |
|-------------|-------------|--------------------|-------------|-------------|
| kuvaus   | description | [LanguageString](#languagestring) | 0..\*           |        |
| tiedosto |             | [Liiteasiakirja](#liiteasiakirja) | 1               |        |

**Assosiaatiot**

| Roolinimi        | Rolename        | Kohde                           | Kardinaliteetti | Kuvaus                                                                                                                                                                                                        |
|---------------|---------------|---------------|---------------|---------------|
| suunniteltukohde | building object | [Rakennuskohde](#rakennuskohde) | 0..\*           | Suunniteltujen tai toteutettujen rakentamis- tai purkamistoimenpiteiden kohde. Rakennuskohde voi olla rakennus, rakennelma, huoneisto tai erityistä toimintaa varten rakennettava alue (esim. pysäköintialue) |

### Rakennuspaikka {#rakennuspaikka}

Englanninkielinen nimi: **Building site**

Kuvaa käsitteen [Rakennuspaikka](../../kasitemalli/#rakennuspaikka), Stereotyyppi: FeatureType (kohdetyyppi)

Kiinteistö tai muu määritelty alue, joka rakentamisluvan yhteydessä osoitetaan rakennuksen tai muun rakennuskohteen sijaintipaikaksi.

**Ominaisuudet**

| Nimi                   | Name                          | Tyyppi                    | Kardinaliteetti | Kuvaus                   |
|---------------|---------------|---------------|---------------|---------------|
| pintaAla               | area                          | [decimal](#decimal)       | 0..1            | Rakennuspaikan pinta-ala |
| hulevedenkäsittelytapa | type of storm water treatment | [HulevedenKäsittelynLaji] | 0..1            |                          |

**Assosiaatiot**

| Roolinimi                | Rolename            | Kohde                                                   | Kardinaliteetti | Kuvaus                                                                                                                                                                                                                                                                           |
|---------------|---------------|---------------|---------------|---------------|
| rakentamistaOhjaavaKaava | Plan                | [Kaava](../kaavatiedot/#Kaava) (kaavatietomalli)        | 0..\*           |                                                                                                                                                                                                                                                                                  |
| kaavayksikkö             | Plan unit           | Kaavayksikkö (kaavatietomalli)                          | 0..\*           | Asema- tai ranta-asemakaavan pienin yksikkö. Käytännössä kaavayksiköt ovat kortteleita tai sen osia, tai vastaavasti yleisiä alueita tai sen osia. Kaavayksikkö voi olla esimerkiksi sitovan tonttijaon mukainen kaavatontti tai ohjeellisen tonttijaon mukainen rakennuspaikka. |
| rakennuspaikanOsoite     |                     | [Osoite](#osoite) yhteisetkomponentit                   | 0..\*           | sijaintipaikan osoittavien tietojen kokonaisuus                                                                                                                                                                                                                                  |
| toimenpide               | construction action | [RakennuskohteenToimenpide](#rakennuskohteentoimenpide) | 0..\*           | maankäyttöprosessi jossa määriteltyjen vaiheiden mukaisesti tuotetaan rakennuskohde                                                                                                                                                                                              |
| kohde                    | building object     | [rakennuskohde](#rakennuskohde)                         | 0..\*           |                                                                                                                                                                                                                                                                                  |

### RakennuskohteenOmistaja

Englanninkielinen nimi: **Building owner**

Kuvaa käsitteen [RakennuskohteenOmistaja](../../kasitemalli/#rakennuskohteenomistaja), Stereotyyppi: FeatureType (kohdetyyppi)

Rakennuskohteen omistajatieto.

**Ominaisuudet**

| Nimi                | Name                      | Tyyppi                                                          | Kardinaliteetti | Kuvaus                         |
|---------------|---------------|---------------|---------------|---------------|
| tunnuksetonOmistaja | owner without identifiers | [TunnuksettomanOmistajanTiedot](#tunnuksettomanomistajantiedot) | 0..1            |                                |
| omistajalaji        | owner type                | [omistajalaji](#omistajalaji)                                   |                 | rakennuskohteen omistajalaji   |
| omistuksenlaji      | ownership type            | [omistuksenlaji](#omistuksenlaji)                               |                 | rakennuskohteen omistuksenlaji |
| passiivinen         |                           | boolean                                                         |                 |                                |
| passivoinninSyy     |                           | [LanguageString](#languagestring)                               | 0..\*           |                                |

**Assosiaatiot**

| Roolinimi              | Rolename        | Kohde                               | Kardinaliteetti | Kuvaus           |
|---------------|---------------|---------------|---------------|---------------|
| tunnuksellinenOmistaja |                 | toimija (yhteiset tietokomponentit) | 0..1            | Liittyvä toimija |
| omistettuKohde         | building object | [RakennusKohde](#rakennuskohde)     | 0..\*           |                  |

### Hissi

Englanninkielinen nimi: **Lift**

Kuvaa käsitteen [Hissi](../../kasitemalli/#hissi), Stereotyyppi: FeatureType (kohdetyyppi)

**Ominaisuudet**

| Nimi            | Name                | Tyyppi                                                                                        | Kardinaliteetti | Kuvaus                                                               |
|---------------|---------------|---------------|---------------|---------------|
| laji            | type of lift        | [HissinLaji](#hissinlaji)                                                                     | 1               | Hissin laji                                                          |
| elinkaarenVaihe | life-cycle stage    | [RakennuksenToiminnallisenOsanElinkaarenVaihe](#rakennuksentoiminnallisenosanelinkaarenvaihe) | 1               |                                                                      |
| sisäpituus      | inside length       | [Measure](#measure)                                                                           | 0..1            | Hissikorin sisäpituus millimetreinä                                  |
| sisäleveys      | inside width        | [Measure](#measure)                                                                           | 0..1            | Hissikorin sisäleveys millimetreinä                                  |
| oviaukonLeveys  | door opening width  | [Measure](#measure)                                                                           | 0..1            | Oven kulkuaukon leveys millimetreinä                                 |
| oviaukonkorkeus | door opening height | [Measure](#measure)                                                                           | 0..1            | Oven kulkuaukon korkeus millimetreinä                                |
| henkilömäärä    | passenger capacity  | [integer](#integer)                                                                           | 0..1            | Henkilöiden lukumäärä.                                               |
| kantavuus       | load capacity       | [Measure](#measure)                                                                           | 0..1            | Rakenteen, rakennusosan, nostinlaitteen tms. kantavuus kilogrammoina |

### Sisäänkäynti

Englanninkielinen nimi: **Entrance**

Kuvaa käsitteen [Sisäänkäynti](../../kasitemalli/#sisaankaynti), Stereotyyppi: FeatureType (kohdetyyppi)

Portaali kahden tilan välillä; sisätilasta sisätilaan tai ulkotilasta sisätilaan.

**Ominaisuudet**

|                 |                     |                                                                                               |                 |                                                                                                             |
|---------------|---------------|---------------|---------------|---------------|
| Nimi            | Name                | Tyyppi                                                                                        | Kardinaliteetti | kuvaus                                                                                                      |
| laji            | type of entrance    | [SisäänkäynninTyyppi]                                                                         | 1               | Sisäänkäynnin käyttötarkoitusta tai -tapaa kuvaava tieto.                                                   |
| elinkaarenVaihe | life-cycle stage    | [RakennuksenToiminnallisenOsanElinkaarenVaihe](#rakennuksentoiminnallisenosanelinkaarenvaihe) | 1               |                                                                                                             |
| osoitetunnus    | address of entrance | [CharacterString](#characterstring)                                                           | 0..1            | Merkkiyhdistelmä, joka yksilöi sisäänkäynnin ja on kirjattu rakennusta koskeviin virallisiin asiakirjoihin. |
| esteetön        | accessible          | boolean                                                                                       | 0..1            |                                                                                                             |

### RakennuskohteenToimenpide {#rakennuskohteentoimenpide}

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [RakennuskohteenToimenpide](../../kasitemalli/#rakennuskohteentoimenpide), Stereotyyppi: FeatureType (kohdetyyppi)

Maankäyttöprosessi jossa määriteltyjen vaiheiden mukaisesti tuotetaan rakennuskohde.

**Ominaisuudet**

|                              |                             |                                                           |                 |                                                                 |
|---------------|---------------|---------------|---------------|---------------|
| Nimi                         | Name                        | Tyyppi                                                    | kardinaliteetti | kuvaus                                                          |
| toimenpiteenlaji             | type of construction action | [RakentamistoimenpiteenLaji](#rakentamistoimenpiteenlaji) | 0..1            |                                                                 |
| suunniteltuMuutos            |                             | [RakennuskohteenMuutos](#rakenuskohteenmuutos)            | 1..\*           |                                                                 |
| kuvaus                       | description of action       | [LanguageString](#languagestring)                         | 0..1            | Toimenpiteen tarkentava kuvaus                                  |
| arvioituValmistumisajankohta |                             | [TM_Object](#tm_object)                                   | 0..1            |                                                                 |
| muutosala                    | area undergoing changes     | [Measure](#measure)                                       | 0..1            | Muutostyön pinta-alatieto                                       |
| PurkamisenSyy                | reason for demolition       | [LanguageString](#languagestring)                         | 0..\*           | Rakennuksen purkamisen syy (ainoastaan purkamistoimenpiteelle). |
| perusparannus                | renovation                  | Boolean                                                   | 0..1            |                                                                 |
| korjausaste                  | renovation rate             | [integer](#integer)                                       | 0..1            | Korjausaste (%)                                                 |

**Assosiaatiot**

| Roolinimi       | Rolename       | Kohde                                                 | Kardinaliteetti | Kuvaus |
|---------------|---------------|---------------|---------------|---------------|
| Ilmastoselvitys | climate report | [ilmastoselvitys](#ilmastoselvitys-1)                 | 0..\*           |        |
| liittyväAsia    | land use case  | AlueidenkäyttöJaRakentamisasia (yhteiset komponentit) | 0..\*           |        |

### RakennuskohteenMuutos

Englanninkielinen nimi: **Change in building object**

Kuvaa käsitteen [Rakennuskohteenmuutos](../../kasitemalli/#rakennuskohteenmuutos), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

|                                       |                                        |                                           |                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|---------------|---------------|---------------|---------------|---------------|
| Nimi                                  | Name                                   | Tyyppi                                    | Kardinaliteetti | Kuvaus                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| tilavuudenMuutos                      | change in volume                       | [Measure](#measure)                       | 0..1            | Kirjataan, kuinka paljon rakennuksen tilavuus muuttuu rakentamistoimenpiteellä, johon hankkeen rakennus on liitetty. Muutos voi olla positiivinen tai negatiivinen.                                                                                                                                                                                                                                                                                                  |
| kerrosalanMuutos                      | change in gross floor area             | [Measure](#measure)                       | 0..1            | Kerrosten alat ulkoseinien ulkopinnan mukaan laskettuina sekä se kellarikerroksen tai ullakon ala, johon sijoitetaan tai voidaan näiden tilojen sijainnista, yhteyksistä, koosta, valoisuudesta ja muista ominaisuuksista päätellen sijoittaa rakennuksen pääasiallisen käyttötarkoituksen mukaisia tiloja. Kirjataan, kuinka paljon kerrosala muuttuu rakentamistoimenpiteellä, johon hankkeen rakennus on liitetty. Muutos voi olla positiivinen tai negatiivinen. |
| rakennusoikeudellisenKerrosalanMuutos | change in permitted building area      | [Measure](#measure)                       | 0..1            | Kerrosalasta huomioidaan ulkoseinien sisällä oleva pinta-ala ja ulkoseinistä vain se osa, joka on paksuudeltaan enintään 250 mm. Kirjataan, jos tieto muuttuu rakentamistoimenpiteellä, johon hankkeen rakennus on liitetty. Kirjataan, kuinka paljon rakennusoikeudellinen kerrosala muuttuu rakentamistoimenpiteellä, johon hankkeen rakennus on liitetty. Muutos voi olla positiivinen tai negatiivinen.                                                          |
| kokonaisalanMuutos                    | change in total area                   | [Measure](#measure)                       | 0..1            | Kaikkien kerrosten, kellareiden ja lämpöeristettyjen ullakoiden pinta-ala yhteensä ulkomitoin. Kokonaisalaan ei lasketa parvekkeita, katoksia eikä 160 cm:ä matalampia tiloja. Kirjataan, kuinka paljon kokonaisala muuttuu rakentamistoimenpiteellä, johon hankkeen rakennus on liitetty. Muutos voi olla positiivinen tai negatiivinen.                                                                                                                            |
| kellarialanMuutos                     | change in basement area                | [Measure](#measure)                       | 0..1            | Kellarin pinta-alan muutos rakentamistoimenpiteen yhteydessä                                                                                                                                                                                                                                                                                                                                                                                                         |
| kerrosluvunMuutos                     | change in number of storeys            | [Measure](#measure)                       | 0..1            | Rakennushankkeella kerrosluvun muuttuminen voi olla positiivinen tai negatiivinen.                                                                                                                                                                                                                                                                                                                                                                                   |
| huoneistonMuutos                      |                                        | [HuoneistonMuutos](#huoneistomuutos)      | 0..\*           | Kuvaa rakennuksen tiettyyn huoneistoon tehdyn muutoksen                                                                                                                                                                                                                                                                                                                                                                                                              |
| varustemuutos                         | change of equipment of building object | [RakennuksenVaruste](#rakennuksenvaruste) | 0..\*           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| kohdePoistuu                          |                                        | boolean                                   | 1               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

**Assosiaatiot**

| Roolinimi             | Rolename | Kohde                           | Kardinaliteetti | Kuvaus                                                                                      |
|---------------|---------------|---------------|---------------|---------------|
| kohdeMuutoksenJälkeen |          | [RakennusKohde](#rakennuskohde) | 0..\*           |                                                                                             |
| kohdeEnnenMuutosta    |          | [RakennusKohde](#rakennuskohde) | 0..\*           | Tiedot rakennuskohteesta tai -kohteista sellaisena kuin on tallennettu ennen tätä muutosta. |

### TunnuksettomanOmistajanTiedot {#tunnuksettomanomistajantiedot}

Englanninkielinen nimi: **Identifier data of owner without identifiers**

Kuvaa käsitteen [TunnuksettomanOmistajanTiedot](../../kasitemalli/#tunnuksettomanomistajantiedot), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi             | Name | Tyyppi                              | Kardinaliteetti | Kuvaus                                                    |
|---------------|---------------|---------------|---------------|---------------|
| osoite           |      | [CharacterString](#characterstring) | 1               | Tunnuksettoman omistajan kotimainen tai ulkomainen osoite |
| muuTunnistetieto |      | [CharacterString](#characterstring) | 0..1            |                                                           |
| nimi             |      | [CharacterString](#characterstring) | 0..1            |                                                           |

### RakennuksenOsittelu {#rakennuksenosittelu}

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [RakennuksenOsittelu](../../kasitemalli/#rakennuksenosittelu), Stereotyyppi: DataType (tietotyyppi)

| Nimi            | Name        | Tyyppi                            | Kardinaliteetti | Kuvaus |
|---------------|---------------|---------------|---------------|---------------|
| ositteluperuste |             | [RakennuksenOsittelunLaji]        | 1               |        |
| kuvaus          | description | [LanguageString](#languagestring) | 0..\*           |        |

### RakennuskohteenSijaintitiedot

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [RakennuskohteenSijaintitiedot](../../kasitemalli/#rakennuskohteensijaintitiedot), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi               | Name                   | Tyyppi                              | Kardinaliteetti | Kuvaus |
|---------------|---------------|---------------|---------------|---------------|
| äänestysaluenumero | voting district number | [CharacterString](#characterstring) | 0..1            |        |
| sijaintikeskipiste |                        | [point](#point)                     | 0..1            |        |

**Assosiaatiot**

| Nimi               | Name | Tyyppi                                         | Kardinaliteetti | Kuvaus |
|---------------|---------------|---------------|---------------|---------------|
| hallinnollinenAlue |      | HallinnollinenAlue (yhteiset tietokomponentit) | 0..\*           |        |
| kohteenOsoite      |      | Osoite (yhteiset tietokomponentit)             | 0..\*           |        |

### RakennuksenSisäänkäynti

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [RakennuksenSisäänkäynti](../../kasitemalli/#rakennuskohteensijaintitiedot),

**Ominaisuudet**

| Nimi         | Name    | Tyyppi  | Kardinaliteetti | Kuvaus |
|--------------|---------|---------|-----------------|--------|
| ensisijainen | primary | boolean |                 |        |

### RakennuksenVaruste {#rakennuksenvaruste}

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [RakennuksenVaruste](../../kasitemalli/#rakennuksenVaruste), Stereotyyppi: DataType (tietotyyppi)

Rakennukseen, rakennelmaan tai huoneistoon kiinteästi asennettu järjestelmä tai laite.

**Ominaisuudet**

| Nimi             | Name              | Tyyppi                     | Kardinaliteetti | Kuvaus                                                     |
|---------------|---------------|---------------|---------------|---------------|
| laji             | type of equipment | [RakennuksenVarusteenLaji] | 1               | Ylätason luokittelu, minkä tyyppisestä varusteesta on kyse |
| kuuluuKohteeseen |                   | boolean                    | 0..1            |                                                            |

### Materiaalitiedot {#materiaalitiedot}

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [Materiaalitiedot](../../kasitemalli/#materiaalitiedot), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi                                    | Name                | Tyyppi                             | Kardinaliteetti | Kuvaus                                                                                                                                                  |
|---------------|---------------|---------------|---------------|---------------|
| rakentamistapa                          | construction method | [Rakentamistapa]                   | 0..1            | Ilmoitetaan, onko rakennus rakennettu elementeistä vai tehty paikalla. Rakentamistapa määräytyy rakennuksen rungon pääasiallisen rakennustavan mukaan.  |
| kantavienrakenteidenRakennusaine        |                     | [KantavienRakenteidenRakennusaine] | 0..\*           | Kantavanrakenteen rakennusaine                                                                                                                          |
| julkisivumateriaali                     | facade material     | [Julkisivumateriaali]              | 0..\*           |                                                                                                                                                         |
| paloluokka                              | fire class          | [Paloluokka]                       | 0..1            | Rakennuksen paloluokka                                                                                                                                  |
| laajarunkoinenRakennus                  |                     | boolean                            | 1               | Laajarunkoisella rakennuksella tarkoitetaan rakennusta, jossa kantavan rungon jänneväli on pitkä (esim. varastohallit, kauppakeskukset, liikuntatilat). |
| uudelleenhyödynnettävänMateriaalinMäärä |                     | SuureenArvo                        | 0..\*           |                                                                                                                                                         |

#### KantavienRakenteidenRakennusaine

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [KantavienRakenteidenRAkennusaine](../../kasitemalli/#kantavienrakenteidenrakennusaine), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi         | Name    | Tyyppi                                   | Kardinaliteetti | Kuvaus                                 |
|---------------|---------------|---------------|---------------|---------------|
| laji         |         | [KantavienRakenteidenRakennusaineenlaji] | 1               | Kantavan rakenteen rakennusaineen laji |
| ensisijainen | primary | boolean                                  | 1               |                                        |

#### Julkisivumateriaali

Englanninkielinen nimi: **facade building material**

Kuvaa käsitteen [Julkisivumateriaali](../../kasitemalli/#julkisivumateriaali), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi         | Name                             | Tyyppi                      | Kardinaliteetti | Kuvaus                         |
|---------------|---------------|---------------|---------------|---------------|
| laji         | type of facade building material | JulksivunRakennusaineenLaji | 1               | Julkisivun rakennusaineen laji |
| ensisijainen | primary                          | boolean                     | 1               |                                |

### RakennuksenKäyttötiedot {#rakennuksenkäyttötiedot}

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [Rakennuksenkäyttötiedot](../../kasitemalli/#rakennuksenkayttotiedot), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi                     | Name               | Tyyppi                       | Kardinaliteetti | Kuvaus                                                                                                      |
|---------------|---------------|---------------|---------------|---------------|
| käyttöönottopäivämäärä   | commissioning date | date                         | 0..1            | Rakennuksen ensimmäisen käyttöönottokatselmuksen hyväksymisen päivä                                         |
| käytössäolo              |                    | [integer](#integer)          | 0..1            | Rakennuksen käytön tilanne. Rakennuksen käytössäolotieto päätellään mm. asumistietojen perusteella VTJ:ssä. |
| käyttötarkoitus          | purpose            | [RakennuksenKäyttötarkoitus] | 0..\*           | kuvaa rakennuksen osan pääasiallista käyttötarkoitusta voimassa olevan koodiston sallimin arvoin            |
| tavoitteellinenKäyttöikä |                    | [integer](#integer)          | 0..1            | Rakennuksen käyttöiän tavoite, joka rakennukselle on määritetty sitä suunniteltaessa. Annetaan vuosina.     |
| suunniteltukäyttäjämäärä |                    | [integer](#integer)          | 0..1            | Rakennuksen käyttäjien lukumäärä, joka rakennusta suunniteltaessa on määritelty.                            |

#### RakennuksenKäyttötarkoitus

Englanninkielinen nimi: **purpose**

Kuvaa käsitteen [Rakennuksenkäyttötarkoitus](../../kasitemalli/#rakennuksenkayttotarkoitus), Stereotyyppi: DataType (tietotyyppi)

Rakennuksen tai sen osan pääasiallinen käyttötarkoitus. Attribuutin arvo määräytyy Tilastokeskuksen Rakennusluokituksen mukaisesti.

**Ominaisuudet**

| Nimi         | Name | Tyyppi                 | Kardinaliteetti | Kuvaus                                                                                                                                                                                                                                                                                        |
|---------------|---------------|---------------|---------------|---------------|
| laji         |      | [Rakennusluokitus2018] | 1               | Rakennusluokitus luokittelee rakennuksia niiden pääasiallisen käyttötarkoituksen mukaan. Rakennuksen tilojen ja tilavaatimusten tulee olla sen käyttötarkoitusluokalle ominaisia. Luokituksen kohdeyksikkönä on rakennus, joka sisältää asumiseen tai muihin toimintoihin tarkoitettua tilaa. |
| ensisijainen |      | boolean                | 1               |                                                                                                                                                                                                                                                                                               |

### Energiatiedot {#energiatiedot}

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [Energiatiedot](../../kasitemalli/#energiatiedot), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi                                         | Name                     | Tyyppi                                | Kardinaliteetti | Kuvaus                                                                                           |
|---------------|---------------|---------------|---------------|---------------|
| energialuokka                                | energy rating            | [Energialuokka]                       | 0..1            | Rakennuksen energiatehokkuusdirektiivin mukainen energialuokka.                                  |
| laskennallinenEnergiatehokkuudenVertailuluku | energy efficiency rating | double                                | 0..1            |                                                                                                  |
| lämmitystapa                                 | heating method           | [Lämmitystapa]                        | 0..\*           | Lämmitystapa                                                                                     |
| lämmitysenergianLähde                        | heating energy source    | [LämmitysenergianLähde]               | 0..\*           | Lämmitysenergian lähde                                                                           |
| jäähdytystapa                                | cooling method           | [Jäähdytystapa]                       | 0..\*           | Jäähdytystapa                                                                                    |
| jäähdytysenergianLähde                       | cooling energy source    | [Jäähdytysenergianlähde]              | 0..\*           | Jäähdytysenergeian lähde                                                                         |
| sähköenrgianLähde                            | electrical energy source | [SähköenergianLähde]                  | 0..\*           | Sähköenergian lähde                                                                              |
| lämmitettyNettopintaAla                      | net heated area          | [Measure](#measure)                   | 0..1            | Rakennuksen lämmitetty pinta-ala mm. energiatodistusta ja hiilijalanjäljen vertailuarvoa varten. |
| lämmitettyTilavuus                           | heated volume            | [Measure](#measure)                   | 0..1            | Rakennuksen lämmitetty tilavuus mm. energiatodistusta ja hiilijalanjäljen vertailuarvoa varten.  |
| energiatodistus                              | energy certificate       | Liiteasiakirja (yhteiset komponentit) | 0..1            |                                                                                                  |
| laskennallinenOstoenergianKulutus            |                          | [EnergianKulutus]                     | 0..1            |                                                                                                  |

#### Lämmitystapa

Englanninkielinen nimi: **heating method**

Kuvaa käsitteen [Lämmitystapa](../../kasitemalli/#lammitystapa), Stereotyyppi: DataType (tietotyyppi)

Tarkoitetaan rakennuksen lämmittämisessä käytettyä lämmitystapaa.

**Ominaisuudet**

| Nimi         | Name                   | Tyyppi              | Kardinaliteetti | Kuvaus                                 |
|---------------|---------------|---------------|---------------|---------------|
| laji         | type of heating method | [LämmitystavanLaji] | 1               | Rakennuksen pääasiallinen lämmitystapa |
| ensisijainen | primary                | boolean             | 1               |                                        |

#### Jäähdytystapa

Englanninkielinen nimi: **cooling method**

Kuvaa käsitteen [Jäähdytystapa](../../kasitemalli/#jaahdytystapa), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi         | Name                   | Tyyppi               | Kardinaliteetti | Kuvaus              |
|---------------|---------------|---------------|---------------|---------------|
| laji         | type of cooling method | [jäähdytystavanLaji] | 1               | Jäähdytystavan laji |
| ensisijainen | primary                | boolean              | 1               |                     |

#### SähköenergianLähde

Englanninkielinen nimi: electrical energy source

Kuvaa käsitteen [SähköenergianLähde](../../kasitemalli/#sahkoenergianlahde), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi         | Name                             | Tyyppi                     | Kardinaliteetti | Kuvaus                    |
|---------------|---------------|---------------|---------------|---------------|
| laji         | type of electrical energy source | [sähköenergianLähteenLaji] | 1               | Sähköenergianlähteen laji |
| ensisijainen | primary                          | boolean                    | 1               |                           |

#### EnergianKulutus

Englanninkielinen nimi: **delivered energy**

Kuvaa käsitteen [Energiankulutus](../../kasitemalli/#energiankulutus), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi                 | Name                     | Tyyppi              | Kardinaliteetti | Kuvaus                   |
|---------------|---------------|---------------|---------------|---------------|
| laji                 | type of delivered energy | [OstoenergianLaji]  | 1               | Ostoenergianlähteen laji |
| energiamäärävuodessa |                          | [Measure](#measure) | 1               |                          |

#### JäähdytysenergianLähde

Englanninkielinen nimi: **cooling energy source**

Kuvaa käsitteen [JäähdytysenergianLähde](../../kasitemalli/#jaahdytysenergianlahde), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi         | Name                          | Tyyppi                         | Kardinaliteetti | Kuvaus                         |
|---------------|---------------|---------------|---------------|---------------|
| laji         | type of cooling energy source | [JäähdytysenergianLähteenLaji] | 1               | jäähdytysenergian lähteen laji |
| ensisijainen | primary                       | boolean                        | 1               |                                |

#### LämmitysenergianLähde

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [LämmitysenergianLähde](../../kasitemalli/#lammitysenergianlahde), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi         | Name | Tyyppi                        | Kardinaliteetti | Kuvaus                                                                         |
|---------------|---------------|---------------|---------------|---------------|
| laji         |      | [LämmitysenergianLähteenLaji] | 1               | Koodiston avulla ilmoitetaan rakennuksen pääasiallinen lämmitysenergian lähde. |
| ensisijainen |      | boolean                       | 1               |                                                                                |

### Talotekniikkatiedot {#talotekniikkatiedot}

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [Talotekniikkatiedot](../../kasitemalli/#talotekniikkatiedot), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi                   | Name | Tyyppi                     | Kardinaliteetti | Kuvaus |
|---------------|---------------|---------------|---------------|---------------|
| ilmanvaihtotapa        |      | [Ilmanvaihtotapa]          | 0..\*           |        |
| viemäröintitapa        |      | [JätevesienkäsittelynLaji] | 0..1            |        |
| talousvesi             |      | [TalousvedenLaji]          | 0..1            |        |
| Verkostoliittymä       |      | [VerkostoliittymänLaji]    | 0..\*           |        |
| hulevedenKäsittelytapa |      | [HulevedenKäsittelynLaji]  | 0..1            |        |

#### Ilmanvaihtotapa

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [Ilmanvaihtotapa](../../kasitemalli/#ilmanvaihtotapa), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi         | Name | Tyyppi                 | Kardinaliteetti | Kuvaus                                                           |
|---------------|---------------|---------------|---------------|---------------|
| laji         |      | [IlmanvaihtotavanLaji] | 1               | Koodistolla kuvataan rakennuksen ilmanvaihtotavan hallintatapaa. |
| ensisijainen |      | boolean                | 1               |                                                                  |

#### Verkostoliittymä {#verkostoliittymä}

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [Verkostoliittymä](../../kasitemalli/#verkostoliittyma), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi          | Name | Tyyppi                  | Kardinaliteetti | Kuvaus                                                    |
|---------------|---------------|---------------|---------------|---------------|
| laji          |      | [VerkostoliittymänLaji] | 1               | Koodistolla kuvataan rakennuksen verkostoliittymän lajia. |
| liitetty      |      | boolean                 | 1               |                                                           |
| liittymäpiste |      | [Geometry]              | 0..1            |                                                           |

### UlkokuorenTiedot {#ulkokuorentiedot}

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [ulkokuorenTiedot](../../kasitemalli/#ulkokuorentiedot), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi                            | Name | Tyyppi              | Kardinaliteetti | Kuvaus                                                                                                                                                                                                                                                                                                                     |
|---------------|---------------|---------------|---------------|---------------|
| kerrosluku                      |      | [integer](#integer) | 0..1            | Rakennuksen maanpäällisten kerrosten lukumäärä. Kerroslukuun lasketaan kaikki ne kokonaan tai pääasiallisesti maanpinnan yläpuolella olevat kerrokset (=ei kellarikerrokset), joissa on asuin- tai työ (toimi-) tiloja tai rakennuksen pääasiallisen käyttötarkoituksen mukaisia tiloja. Kerroslukuun ei lasketa ullakkoa. |
| korkeus                         |      | [Measure](#measure) | 0..1            | Absoluuttinen korkeus rakennuksen tai rakennuksen osan korkeimmasta kohdasta.                                                                                                                                                                                                                                              |
| lentoeste                       |      | boolean             | 1               | Tieto siitä, onko kohde lentoeste. Kohde tulee määritellä lentoesteeksi EUROCONTROL Terrain and Obstacle Data Manual Edition 2.1 -dokumentin perusteella (ISBN: 978-2-87497-079-5). Kohteen määrittelyyn lentoesteeksi vaikuttavat mm. kohteen etäisyys kiitoradasta, kohteen suhteellinen korkeus ja maanpinnan korkeus.  |
| muoto                           |      | [Geometry]          | 0..1            |                                                                                                                                                                                                                                                                                                                            |
| suhdeMaanpintaan                |      | SuhdeMaanpintaan    | 0..1            | Tieto siitä, missä rakennus sijaitsee suhteessa maan pintaan.                                                                                                                                                                                                                                                              |
| tilavuus                        |      | [Measure](#measure) | 0..1            | Rakennuksen tilavuus lasketaan sen tilan perusteella, jota rajoittavat ulkoseinien ulkopinnat, alapohjan alapinta ja yläpohjan yläpinta.                                                                                                                                                                                   |
| kerrosala                       |      | [Integer](#integer) | 0..1            | Kerrosten alat ulkoseinien ulkopinnan mukaan laskettuina sekä se kellarikerroksen tai ullakon ala, johon sijoitetaan tai voidaan näiden tilojen sijainnista, yhteyksistä, koosta, valoisuudesta ja muista ominaisuuksista päätellen sijoittaa rakennuksen pääasiallisen käyttötarkoituksen mukaisia tiloja.                |
| rakennusoikeudellinen kerrosala |      | [Measure](#measure) | 0..1            | Kerrosalasta huomioidaan ulkoseinien sisällä oleva pinta-ala ja ulkoseinistä vain se osa, joka on paksuudeltaan enintään 250 mm.                                                                                                                                                                                           |

### SisätilojenTiedot

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [SisätilojenTiedot](../../kasitemalli/#sisatilojentiedot), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi                         | Name | Tyyppi              | Kardinaliteetti | Kuvaus                                                                                                                                                                                                                                                                                          |
|---------------|---------------|---------------|---------------|---------------|
| huoneistoala                 |      | [Measure](#measure) | 0..1            | Ala, jota rajaavat toisaalta huoneistoa ympäröivien seinien, toisaalta huoneiston sisällä olevien kantavien seinien ja muiden rakennukselle välttämättömien rakennusosien huoneiston puoleiset pinnat. Pinta-alaan lasketaan mukaan vain se osa, jossa huonekorkeus ylittää 160 cm.             |
| väestösuojanHenkilömäärä     |      | [integer](#integer) | 0..1            |                                                                                                                                                                                                                                                                                                 |
| kellariala                   |      | [Measure](#measure) | 0..1            | Kellarikerrosten yhteenlaskettu pinta-ala. Kellarikerroksen pinta-ala on kellarikerrosta ympäröivien seinien ulkopintojen rajoittama ala. Mukaan ei lasketa 160 cm:ä matalampia tiloja. Kellarikerroksiksi luetaan kaikki kokonaan tai pääasiallisesti maanpinnan alapuolella olevat kerrokset. |
| kokoontumistilanHenkilömäärä |      | [integer](#integer) | 0..1            | Kokoontumistilaan hyväksyttävä enimmäishenkilömäärä                                                                                                                                                                                                                                             |

## Tilat ja huoneistot

### RakennettuTila

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [RakennettuTila](../../kasitemalli/#rakennettutila), Stereotyyppi: FeatureType (kohdetyyppi)

**Ominaisuudet**

| Nimi                         | Name | Tyyppi                               | Kardinaliteetti | Kuvaus |
|---------------|---------------|---------------|---------------|---------------|
| laji                         |      | [HuoneenTaiMuunTilanLaji]            | 0..1            |        |
| käyttötarkoitus              |      | [HuoneenTaiMuunTilanKäyttötarkoitus] | 0..1            |        |
| pysyväTilaTunnus             |      | [CharacterString](#characterstring)  | 0..1            |        |
| tilaryhmä                    |      | [CharacterString](#characterstring)  | 0..1            |        |
| kokoontumistilanHenkilömäärä |      | [Integer](#integer)                  | 0..1            |        |
| tilavuus                     |      | [Measure](#measure)                  | 0..1            |        |
| pohjapintaAla                |      | [Measure](#measure)                  | 0..1            |        |

**Assosiaatiot**

| Roolinimi     | Rolename | Kohde            | Kardinaliteetti | Kuvaus |
|---------------|----------|------------------|-----------------|--------|
| sisältyväTila |          | [RakennuksenOsa] | 0..\*           |        |

### Huoneisto

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [Huoneisto](../../kasitemalli/#huoneisto), Stereotyyppi: FeatureType (kohdetyyppi)

Rakennukseen liittyvä hallintakohde, jolla on oma välitön sisäänkäynti.

**Ominaisuudet**

| Nimi                   | Name | Tyyppi                                   | Kardinaliteetti | Kuvaus                                                                                                                                                                 |
|---------------|---------------|---------------|---------------|---------------|
| elinakaarenvaihe       |      | [HuoneistonElinkaarenVaihe]              | 1               |                                                                                                                                                                        |
| varuste                |      | [HuoneistonVaruste]                      | 0..\*           |                                                                                                                                                                        |
| pysyväHuoneistoTunnus  |      | [CharacterString](#characterstring)      | 0..1            | Pysyvä huoneistotunnus (VTJ-PHT) on jokaiselle huoneistolle ja uudisrakennushankkeen huoneistolle annettava 10-merkkinen tunnus                                        |
| osoiteHuoneistoTunnus  |      | [OsoiterakenteenMukainenHuoneistotunnus] | 0..1            |                                                                                                                                                                        |
| huoneistoLaji          |      | [Huoneistotyyppi]                        | 0..1            |                                                                                                                                                                        |
| huoneistoala           |      | [Measure](#measure)                      | 0..1            | Huoneistoa ympäröivien seinien sisäpintojen mukaan laskettu pinta-ala. Pinta-alaan lasketaan mukaan vain se osa, jossa huonekorkeus ylittää 160 cm.                    |
| huoneidenlukumäärä     |      | [integer](#integer)                      | 0..1            | Huoneeksi katsotaan rakennuksessa oleva tila, jota ympäröivät lattia, katto ja seinät. Huoneiden lukumäärään ei lasketa keittiötä.                                     |
| keittiötyyppi          |      | [keittiötyyppi]                          | 0..1            | Tieto siitä, minkälainen keittiö huoneistossa on.                                                                                                                      |
| käymälätyyppi          |      | [Käymälätyyppi]                          | 0..1            | Koodisto kertoo, minkä tyyppinen käymälä huoneessa on.                                                                                                                 |
| käyttöönottopäivämäärä |      | Date                                     | 0..1            | Päivämäärä, jolloin huoneisto on hyväksytty käyttöönotettavaksi viimeisimmän siihen tehdyn käyttöönottokatselmusta vaativan muutoksen jälkeen.                         |
| käyttöala              |      | [Measure](#measure)                      | 0..1            | Rakennuksen kokonaislaajuus, johon lasketaan bruttoalan lisäksi mukaan myös rakennetut, ei-maanvaraiset ulkotilat, kuten parvekkeet, luhtikäytävät, terassit ja kannet |

**Assosiaatiot**

| Roolinimi               | Rolename | Kohde                 | Kardinaliteetti | Kuvaus                                                                                                   |
|---------------|---------------|---------------|---------------|---------------|
| huone                   |          | [Huone]               | 0..\*           | rakennuksen tila, jonka pinta-ala, valoaukko ja huonekorkeus täyttävät laissa säädetyt minimivaatimukset |
| sisältäväRakennuksenOsa |          | [RakennuksenOsa]      | 0..\*           |                                                                                                          |
| Rakennus                |          | [Rakennus](#rakennus) | 1               |                                                                                                          |

### Huone

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [Huone](../../kasitemalli/#huone), Stereotyyppi: FeatureType (kohdetyyppi)

Rakennuksen tila, jonka pinta-ala, valoaukko ja huonekorkeus täyttävät laissa säädetyt minimivaatimukset.

**Ominaisuudet**

| Nimi       | Name | Tyyppi              | Kardinaliteetti | Kuvaus |
|------------|------|---------------------|-----------------|--------|
| asuinhuone |      | boolean             | 1               |        |
| huoneala   |      | [Measure](#measure) | 0..1            |        |

### OsoiterakenteenMukainenHuoneistoTunnus

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [OsoiterakenteenMukainenHuoneistoTunnus](../../kasitemalli/#osoiterakenteenmukainenhuoneistotunnus), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi        | Name | Tyyppi                              | Kardinaliteetti | Kuvaus                                                                                                                                                   |
|---------------|---------------|---------------|---------------|---------------|
| kirjainosa  |      | [characterString](#characterstring) | 1               | Useamman kuin yhden huoneiston käsittävässä rakennuksessa tai rakennuksissa sijaitsevien huoneistojen tunnuksiin kuuluva kirjain                         |
| jakokirjain |      | [characterString](#characterstring) | 0..1            | Kirjain, joka on lisätty huoneistotunnuksen numero-osaan silloin, kun alkuperäinen huoneisto on jaettu kahdeksi tai useammaksi erilliseksi huoneistoksi. |
| numeroOsa   |      | [integer](#integer)                 | 1               | Useamman kuin yhden huoneiston käsittävässä rakennuksessa sijaitsevan huoneiston tunnukseen kuuluva numero                                               |

### HuoneistonVaruste

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [HuoneistonVaruste](../../kasitemalli/#huoneistonvaruste), Stereotyyppi: FeatureType (kohdetyyppi)

**Ominaisuudet**

| Nimi              | Name | Tyyppi                    | Kardinaliteetti | Kuvaus |
|---------------|---------------|---------------|---------------|---------------|
| laji              |      | [HuoneistonVarusteenLaji] | 1               |        |
| kuuluuHuoneistoon |      | boolean                   | 0..1            |        |

## Ilmastoselvitys {#ilmastoselvitys}

### Ilmastoselvitys {#ilmastoselvitys-1}

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [Ilmastoselvitys](../../kasitemalli/#ilmastoselvitys), Stereotyyppi: FeatureType (kohdetyyppi)

Selvitys, jossa raportoidaan rakentamistoimenpiteen hiilijalanjälki ja hiilikädenjälki arvioituna rakennuksen koko elinkaaren ajalta, ja kohdistuen sekä rakennukseen tai sen osaan että rakennuspaikkaan.

**Ominaisuudet**

| Nimi                          | Name | Tyyppi                                       | Kardinaliteetti | Kuvaus                                                                                             |
|---------------|---------------|---------------|---------------|---------------|
| otsikko                       |      | [LanguageString](#languagestring)            | 0..\*           | Selvityksen otsikko                                                                                |
| kuvaus                        |      | [LanguageString](#languagestring)            | 0..\*           | Kohteen sisällöstä kertova tieto                                                                   |
| laatimispäivä                 |      | Date                                         |                 | Selvityksen laatimispäivämäärä                                                                     |
| kohteenVähähiilisyys          |      | [Rakennuskohdekohtaisetvähähiilisyystiedot]  | 1..\*           |                                                                                                    |
| paikanVähähiilisyys           |      | [RakennuspaikkakohtaisetVähähiilisyystiedot] |                 |                                                                                                    |
| käytetynArviointijaksonpituus |      | [Measure](#measure)                          |                 | ajanjakson pituus, jolle rakennuksen vähähiilisyyden arviointi tehdään, yksikkönä vuosi            |
| sovellettavatRajaArvot        |      | koodiarvo                                    | 0..\*           | Hiilijalanjäljen ja -kädenjäljen arvioinnissa sovellettujen raja-arvomääräysten tunnus koodistossa |
| käytetytLaskentaohjelmistot   |      | [LanguageString](#languagestring)            | 1..\*           | Ilmastoselvityksen hiilijalan- ja -kädenjäljen laskentaan käytetyn laskentaohjelmiston nimi        |

**Assosiaatiot**

| Roolinimi  | Rolename | Kohde                                                   | Kardinaliteetti | Kuvaus                                                                    |
|---------------|---------------|---------------|---------------|---------------|
| laatija    |          | SuunnitelmanLaatija (yhteiset komponentit)              | 1..\*           | laatija/laadinnan määritelmä                                              |
| kohde      |          | [RakennusTaiSenOsa]                                     | 1..\*           | Rakennuskohde, jonka rakentamista tai korjaamista ilmastoselvitys koskee. |
| toimenpide |          | [Rakennuskohteentoimenpide](#rakennuskohteentoimenpide) | 1               | Toimenpide, jonka ilmastovaikutuksia ilmastoselvitys koskee.              |

### Hiilijalanjälkitiedot

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [Hiilijalanjälkitiedot](../../kasitemalli/#hiilijalanjalkitiedot), Stereotyyppi: DataType (tietotyyppi)

Ilmastoselvitykseen kuuluvat, yhden rakentamistoimenpiteen arvioidut hiilijalanjälkitiedot rakennuksen elinkaarivaiheittain

**Ominaisuudet**

| Nimi                           | Name | Tyyppi                | Kardinaliteetti | Kuvaus                                                                |
|---------------|---------------|---------------|---------------|---------------|
| rajaArvostaPoikkeamisenPeruste |      | [PoikkeamisenPeruste] | 0..\*           | Syy hiilijalanjäljen arviointiin kuuluvien raja-arvojen ylittämiselle |
| osatekijä                      |      | SuureenArvo           | 0..\*           |                                                                       |

### Hiilikädenjälkitiedot

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [Hiilikädenjälkitiedot](../../kasitemalli/#hiilikadejalkitiedot), Stereotyyppi: DataType (tietotyyppi)

Ilmastoselvitykseen kuuluvat rakentamistoimenpidettä koskevat arvioidut hiilikädenjälkitiedot osatekijöittäin

**Ominaisuudet**

| Nimi                           | Name | Tyyppi                | Kardinaliteetti | Kuvaus                                                                       |
|---------------|---------------|---------------|---------------|---------------|
| rajaArvostaPoikkeamisenPeruste |      | [PoikkeamisenPeruste] | 0..\*           | Syy hiilikädenjäljen arvioinnille määriteltävien raja-arvojen ylittämiselle. |
| osatekijä                      |      | SuureenArvo           | 0..\*           |                                                                              |

### RakennuskohdekohtaisetVähähiilisyystiedot

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [RakennuskohdekohtaisetVähähiilisyystiedot](../../kasitemalli/#rakennuskohdekohtaisetvahahiilisyystiedot), Stereotyyppi: DataType (tietotyyppi)

Ilmastoselvityksen hiilijalan- ja kädenjälkitiedot yhtä rakennuskohdetta koskevilta osin.

**Ominaisuudet**

| Nimi                  | Name | Tyyppi                                                           | Kardinaliteetti | Kuvaus                                                                                           |
|---------------|---------------|---------------|---------------|---------------|
| käyttötarkoitusluokka |      | [RakennuksenKäyttötarkoitusluokkaEnergiatehokkuudenArvioinnissa] | 1               | Rakennuskohteen tai sen sen osan energiatehokkuden arviointiin käytettävä käyttötarkoitus        |
| hiilijalanjälki       |      | [Hiilikädenjälkitiedot]                                          | 1               | Ilmastoselvityksen hiilijalanjälkitiedot                                                         |
| hiilikädenjälki       |      | [Hiilikädenjälkitiedot]                                          | 1               | Ilmastoselvityksen hiilikädenjälkitiedot                                                         |
| lämmitettyNettoala    |      | [Measure](#measure)                                              | 1               | Rakennuksen lämmitetty pinta-ala mm. energiatodistusta ja hiilijalanjäljen vertailuarvoa varten. |

**Assosiaatio**

| Roolinimi | Rolename | Kohde               | Kardinaliteetti | Kuvaus                                      |
|---------------|---------------|---------------|---------------|---------------|
| kohde     |          | [RakennusTaiSenOsa] | 1               | Rakennuskohde, jota annetut tiedot koskevat |

### RakennuspaikkakohtaisetVähähiilisyystiedot

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [RakennuskohdekohtaisetVähähiilisyystiedot](../../kasitemalli/#rakennuskohdekohtaisetvahahiilisyystiedot), Stereotyyppi: DataType (tietotyyppi)

Ilmastoselvityksen hiilijalan- ja kädenjälkitiedot rakennuspaikkaan kohdistuvilta osin

**Ominaisuudet**

| Nimi            | Name | Tyyppi                  | Kardinaliteetti | Kuvaus                                   |
|---------------|---------------|---------------|---------------|---------------|
| hiilijalanjälki |      | [Hiilijalanjälkitiedot] | 1               | Ilmastoselvityksen hiilijalanjälkitiedot |
| hiilikädenjälki |      | [Hiilikädenjälkitiedot] | 1               | Ilmastoselvityksen hiilikädenjälkitiedot |

**Assosiaatiot**

| Roolinimi | Rolename | Kohde                             | Kardinaliteetti | Kuvaus                               |
|---------------|---------------|---------------|---------------|---------------|
| paikka    |          | [Rakennuspaikka](#rakennuspaikka) | 1               | Rakennuspaikka, jota tiedot koskevat |

### PoikkeamisenPeruste

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [PoikkeamisenPeruste](../../kasitemalli/#poikkeamisenperuste), Stereotyyppi: DataType (tietotyyppi)

Selite, joka kuvaa annetuista raja-arvoista poikkevien arvojen syytä.

**Ominaisuudet**

| Nimi        | Name | Tyyppi                                                    | Kardinaliteetti | Kuvaus                                         |
|---------------|---------------|---------------|---------------|---------------|
| perustelaji |      | [IlmastoselvityksenRajaArvoistapoikkeamisenPerusteenLaji] | 0..\*           | Luokitteluun perustuva syykoodi poikkeamiselle |
| selite      |      | [Measure](#measure)                                       | 0..\*           | Sanallinen selite poikkeamiselle               |

## Materiaaliseloste

### Materiaaliseloste

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [Materiaaliseloste](../../kasitemalli/#materiaaliseloste), Stereotyyppi: FeatureType (kohdetyyppi)

Selvitys, jossa raportoidaan rakentamistoimenpitessä käytettyjen materiaalien määrät rakennusosittain, materiaalilajeittain ja niiden alkuperän perusteella

**Ominaisuudet**

| Nimi                               | Name | Tyyppi                                                           | Kardinaliteetti | Kuvaus                                                                                                                                                     |
|---------------|---------------|---------------|---------------|---------------|
| otsikko                            |      | [LanguageString](#languagestring)                                | 0..\*           | Selvityksen otsikko                                                                                                                                        |
| kuvaus                             |      | [LanguageString](#languagestring)                                | 0..\*           | Kohteen sisällöstä kertova tieto                                                                                                                           |
| laatimispäivä                      |      | Date                                                             | 1               | selvityksen laatimispäivämäärä                                                                                                                             |
| toimenpidealueenLämmitettyNettoala |      | [Measure](#measure)                                              | 1               | rakentamistoimenpiteen kohdealueen lämmitettyjen kerrostasoalojen summa kerrostasoja ympäröivien ulkoseinien sisäpintojen mukaan laskettuna, neliömetreinä |
| rakennuksenKäyttötarkoitus         |      | [rakennuksenKäyttötarkoitusluokkaEnergiatehokkuudenArvioinnissa] | 1..\*           |                                                                                                                                                            |
| rakennuksenOsienMateriaalit        |      | [RakennuspaikkakohtaisetMateriaalimäärät]                        | 1..\*           | Rakennuksen materiaalimäärät rakennusosittain                                                                                                              |
| rakennuspaikanMateriaalit          |      | [RakennuspaikkakohtaisetMateriaalimäärät]                        | 1               | Rakennuspaikkaan kohdistuvien rakentamisen materiaalien määrät rakennusosittain                                                                            |
| materiaalilajinMäärä               |      | SuureenArvo                                                      | 0..\*           | Käytetyn materiaalinmäärä yhden materiaalilajin osalta                                                                                                     |
| vaarallistenAineidenMäärä          |      | [Measure](#measure)                                              |                 | Käytettävien tai käytettyjen vaarallisten aineiden kokonaismäärä niiden painon perusteella, pyöristettynä kokonaisiin kilogrammoihin.                      |
| uusiutuvanMateriaalinMäärä         |      | [Measure](#measure)                                              |                 | Käytettävien tai käytettyjen uusiutuvien materiaalien kokonaismäärä niiden painon perusteella, pyöristettynä kokonaisiin kilogrammoihin.                   |
| uusiutumattomanMateriaalinMäärä    |      | [Measure](#measure)                                              |                 | Käytettävien tai käytettyjen uusiutumattoman materiaalin kokonaismäärä niiden painon perusteella, pyöristettynä kokonaisiin kilogrammoihin.                |
| kierrätetynMateriaalinMäärä        |      | [Measure](#measure)                                              |                 | Käytettävien tai käytettyjen kierrätetyn materiaalin kokonaismäärä niiden painon perusteella, pyöristettynä kokonaisiin kilogrammoihin.                    |
| uudelleenkäytetynMateriaalinMäärä  |      | [Measure](#measure)                                              |                 | Käytettävien tai käytettyjen uudelleenkäytetyn materiaalin kokonaismäärä niiden painon perusteella, pyöristettynä kokonaisiin kilogrammoihin.              |

**Assosiaatiot**

| Roolinimi  | Rolename | Kohde                                                   | Kardinaliteetti | Kuvaus                                                                    |
|---------------|---------------|---------------|---------------|---------------|
| toimenpide |          | [RakennusKohteenToimenpide](#rakennuskohteentoimenpide) | 1               | Toimenpide, jonka ilmastovaikutuksia ilmastoselvitys koskee               |
| kohde      |          | [RakennusTaiSenOsa]                                     | 1..\*           | Rakennuskohde, jonka rakentamista tai korjaamista ilmastoselvitys koskee. |
| laatija    |          | SuunnitelmanLaatija yhteiset komponentit                | 1..\*           | laatija/laadinnan määritelmä                                              |

### RakennuspaikkakohtaisetMateriaalimäärät

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [RakennuspaikkakohtaisetMateriaalimäärät](../../kasitemalli/#rakennuspaikkakohtaisetmateriaalimaarat), Stereotyyppi: DataType (tietotyyppi)

Rakennuspaikkaan kohdistuvat rakentamistoimenpiteen materiaalimäärät rakennusosittain

**Ominaisuudet**

| Nimi              | Name | Tyyppi      | Kardinaliteetti | Kuvaus                                                |
|---------------|---------------|---------------|---------------|---------------|
| rakennusosanOsuus |      | SuureenArvo | 0..\*           | Yhden rakennusosan osuus materiaalin kokonaismäärästä |

**Assosiaatiot**

| Roolinimi | Rolename | Kohde                             | Kardinaliteetti | Kuvaus                                       |
|---------------|---------------|---------------|---------------|---------------|
| paikka    |          | [Rakennuspaikka](#rakennuspaikka) | 1               | Rakennuspaikka, jota annetut tiedot koskevat |

### RakennuskohdekohtaisetMateriaalimäärät

Englanninkielinen nimi: **käännös tähän**

Kuvaa käsitteen [RakennuskohdekohtaisetMateriaalimäärät](../../kasitemalli/#rakennuskohdekohtaisetmateriaalimaarat), Stereotyyppi: DataType (tietotyyppi)

**Ominaisuudet**

| Nimi              | Name | Tyyppi      | Kardinaliteetti | Kuvaus                                                |
|---------------|---------------|---------------|---------------|---------------|
| rakennusosanOsuus |      | SuureenArvo | 0..\*           | Yhden rakennusosan osuus materiaalin kokonaismäärästä |

: **Assosiaatiot**

| Roolinimi | Rolename | Kohde               | Kardinaliteetti | Kuvaus                                      |
|---------------|---------------|---------------|---------------|---------------|
| kohde     |          | [RakennusTaiSenOsa] | 1               | Rakennuskohde, jota annetut tiedot koskevat |

## Koodistot

### RakennuksenElinkaarenVaihe {#rakennuksenelinkaarenvaihe}

{% include common/codelistref.html registry="rakrek" id="rakelinvaih" name="Rakennuksen elinkaaren vaihe" %}

### Rakennusluokitus2018

{% include common/codelistref.html registry="jhs" id="rakennus_1\_20180712" name="Rakennusluokitus 2018" %}

### RakennelmanKäyttötarkoitus

{% include common/codelistref.html registry="rytj" id="RakennelmanKayttotarkoitus" name="Rakennelman käyttötarkoitus" %}

### RakentamistoimenpiteenLaji {#rakentamistoimenpiteenlaji}

{% include common/codelistref.html registry="rytj" id="Rakentamistoimenpide" name="Rakentamistoimenpide" %}

### RakennuksenVarusteenLaji

{% include common/codelistref.html registry="rytj" id="RakennusVaruste" name="Rakennuksen varusteet" %}

### Rakennustietomallinlaji

{% include common/codelistref.html registry="rytj" id="rakennuksentietomallinlaji" name="Rakennuksen tietomallin laji" %}

### RakennuskohteenTiedonLaji {#rakennuskohteentiedonlaji}

{% include common/codelistref.html registry="rytj" id="rakkohteen-tiedon-laji" name="Rakennuskohteen tiedon laji" %}

### RakennuskohteenTiedonLähteenLaji {#rakennuskohteentiedonlähteenlaji}

{% include common/codelistref.html registry="rytj" id="RakennuskohteenTiedonlahde" name="Rakennuskohteen tiedon lähde" %}

### Suojelutapa {#suojelutapa}

{% include common/codelistref.html registry="rytj" id="suojtapa" name="Suojelutapa" %}

### RakennuksenOsittelunLaji

{% include common/codelistref.html registry="rytj" id="rak-osittelun-laji" name="Rakennuksen osittelun laji" %}

### ErityistäToimintaaVartenRakennettavanAlueenTyyppi

{% include common/codelistref.html registry="rakrek" id="erityistatoimintaavartenrakennettavanalueentyyppi" name="Erityistä toimintaa varten rakennettavan alueen tyyppi" %}

### SuhdeMaanpintaan

{% include common/codelistref.html registry="rytj" id="Suhde_pintaan" name="Suhde maan pintaan" %}

### Omistajalaji {#omistajalaji}

{% include common/codelistref.html registry="rytj" id="Omistajalaji" name="Omistajalaji" %}

### OmistuksenLaji {#omistuksenlaji}

{% include common/codelistref.html registry="rytj" id="Omistuksenlaji" name="Omistuksen laji" %}

### KulttuurihistoriallinenMerkittävyys {#kulttuurihistoriallinenmerkittävyys}

{% include common/codelistref.html registry="rakrek" id="kulthistmer" name="Kulttuurihistoriallinen merkittävyys" %}

### LuvanvaraisenRakentamisenAsiakirjanLaji

Laajentaa luokkaa AbstraktiAsiakirjanLaji

Y-alustan koodisto puuttuu toistaiseksi

### KantavienRakenteidenRakennusaineenLaji

{% include common/codelistref.html registry="rytj" id="kantavanrakenteenrakennusaine" name="Kantavan rakenteen rakennusaine" %}

### Rakentamistapa

{% include common/codelistref.html registry="vtj" id="Rake_runkotapa" name="Rakentamistapa" %}

### IlmastoselvityksenHiilijalanjälkisuure

{% include common/codelistref.html registry="rytj" id="is-hiilijalanjalkisuure" name="Ilmastoselvityksen hiilijalanjälkisuure" %}

### IlmastoselvityksenHiilikädenjälkisuure

{% include common/codelistref.html registry="rytj" id="is-hiilikadenjalkisuure" name="Ilmastoselvityksen hiilikädenjälkisuure" %}

### JulkisivunRakennusaineenLaji

{% include common/codelistref.html registry="rytj" id="julkisivunrakennusaine" name="Julkisivun rakennusaineen laji" %}

### Paloluokka

{% include common/codelistref.html registry="rytj" id="Paloluokka" name="Paloluokka" %}

### RakennusosanMateriaalinMäärä

{% include common/codelistref.html registry="rytj" id="ms-rakennusosan-materiaalimaara" name="Rakennuksen rakennusosan materiaalin määrä" %}

### RakentamisessaKäytettävänMaterialilajinMäärä

{% include common/codelistref.html registry="rytj" id="ms-materiaalilajin-maara" name="Rakentamisessa käytettävän materiaalin määrä" %}

### IlmastoselvityksenRajaArvoistaPoikkeamisenPerusteenLaji

{% include common/codelistref.html registry="rytj" id="is-raja-arvoista-poikkeamisen-laji" name="Ilmastoselvityksen raja-arvoista poikkeamisen perusteen laji" %}

### RakennuksenKäyttötarkoitusluokkaEnergiatehokkuudenArvioinnissa

{% include common/codelistref.html registry="rytj" id="rak-kt-luokka-energiatehokkuus" name="Rakennuksen käyttötarkoitusluokka energiatehokkuuden arvionnissa" %}

### Energialuokka

{% include common/codelistref.html registry="rytj" id="Energialuokka" name="Energialuokka" %}

### LämmitystavanLaji

{% include common/codelistref.html registry="rytj" id="lammitystapa" name="Lämmitystavan laji" %}

### JäähdytystavanLaji

{% include common/codelistref.html registry="rytj" id="jaahdytystapa" name="Jäähdytystavan laji" %}

### SähköenergianLähteenLaji

{% include common/codelistref.html registry="rytj" id="sahkoenergianlahde" name="Sähköenergianlähteen laji" %}

### HulevedenKäsittelynLaji

{% include common/codelistref.html registry="rytj" id="hulevedenkasittely" name="Huleveden käsittelyn laji" %}

### JäähdytysenergianLähteenLaji

Y-alustan koodisto puuttuu toistaiseksi

### LämmitysenergianLähteenLaji

{% include common/codelistref.html registry="rytj" id="lammitysenergianlahde" name="Lämmitysenergianlähteen laji" %}

### OstoenergianLaji

{% include common/codelistref.html registry="rytj" id="ostoenergia" name="Ostoenergian laji" %}

### JätevesienKäsittelynLaji

{% include common/codelistref.html registry="rytj" id="jatevesienkasittely" name="Jätevesien käsittelyn laji" %}

### IlmanvaihtotavanLaji

{% include common/codelistref.html registry="rytj" id="ilmanvaihto" name="Ilmanvaihtotavan laji" %}

### VerkostoliittymänLaji

{% include common/codelistref.html registry="rytj" id="verkliit" name="Verkostoliittymän laji" %}

### TalousvedenLaji

{% include common/codelistref.html registry="rytj" id="talousvesi" name="Talousveden laji" %}

### SisäänkäynninTyyppi

{% include common/codelistref.html registry="rytj" id="sisaankaynti" name="Sisäänkäynnin tyyppi" %}

### HissinLaji {#hissinlaji}

{% include common/codelistref.html registry="rytj" id="hissi" name="Hissin laji" %}

### RakennuksenToiminnallisenOsanElinkaarenVaihe {#rakennuksentoiminnallisenosanelinkaarenvaihe}

{% include common/codelistref.html registry="rytj" id="rakennuksen-toim-osan-elinkaaren-vaihe" name="Rakennuksen toiminnallisen osan elinkaaren vaihe" %}

### HuoneenTaiMuunTilanKäyttötarkoitus

Y-alustan koodisto puuttuu toistaiseksi

### HuoneenTaiMuunTilanLaji

{% include common/codelistref.html registry="jhs" id="huonelaji" name="Huoneiden ja muiden tilojen lajit" %}

### Huoneistotyyppi

{% include common/codelistref.html registry="rytj" id="Huoneistotyyppi" name="Huoneistotyyppi" %}

### HuoneistonVarusteenLaji

{% include common/codelistref.html registry="rytj" id="HuoneistoVaruste" name="Huoneiston varusteet" %}

### HuoneistonElinkaarenVaihe

{% include common/codelistref.html registry="rytj" id="huon-elinkaaren-vaihe" name="Huoneiston elinkaaren vaihe" %}

### Keittiötyyppi

{% include common/codelistref.html registry="rytj" id="Keittiotyyppi" name="Keittiötyyppi" %}

### HuoneistonMuutoksenLaji

{% include common/codelistref.html registry="rytj" id="huoneistonmuutoksenlaji" name="Huoneiston muutoksen laji" %}

### Käymälätyyppi

{% include common/codelistref.html registry="rytj" id="kaymalatyyppi" name="Käymälätyyppi" %}
