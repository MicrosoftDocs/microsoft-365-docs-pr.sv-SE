---
title: Vad DLP-funktionerna (dataförlustskydd) söker efter
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
recommendations: false
description: Ta reda på vad DLP-funktionerna (dataförlustskydd) söker efter.
ms.openlocfilehash: 787abc1e7fb4c95392a76f7514ceffd3f7f4dda0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288101"
---
# <a name="what-the-dlp-functions-look-for"></a>Vad DLP-funktionerna letar efter

Principer för skydd mot dataförlust (DLP) kan använda typer av känslig information för att identifiera känsliga objekt. Kreditkortsnummer och EU-betalkortsnummer är exempel på typer av känslig information. Typer av känslig information letar efter specifika mönster. Med typer av känslig information verifieras data genom att de tittar på dess format, det är kontrollsummar och söker efter relevanta nyckelord eller annan information. En del av den här funktionen utförs av interna funktioner. Exempelvis använder typen Kreditkortsnummer känslig information en funktion för att leta efter datum som är formaterade som ett utgångsdatum. Detta hjälper till att bekräfta att ett nummer är ett kreditkortsnummer.

I den här artikeln förklaras vad de här funktionerna söker efter, för att hjälpa dig att förstå hur de fördefinierade typerna av känslig information fungerar. Mer information finns i Definitioner [av typen Känslig informationstyp](sensitive-information-type-entity-definitions.md)

## <a name="table-of-functions"></a>Tabell med funktioner

<br>

****

|funktionsnamn|funktionsåtgärd|är en validerare|
|---|---|:---:|
|Func_Argentina_Unique_Tax_Key|identifierar och verifierar Argentinas unika skattenyckel|nej|
|Func_aba_routing|identifierar ABA-routningsnummer|ja|
|Func_alabama_drivers_license_number|identifierar Alabama-drivrutinens licensnummer|nej|
|Func_alaska_delaware_oregon_drivers_license_number|identifierar Alaska, Delaware, Oregon-drivrutinens registreringsnummer|nej|
|Func_alaska_drivers_license_number|identifierar Alaska-drivrutinens licensnummer|nej|
|Func_alberta_drivers_license_number|identifierar Alberta driver's license number|nej|
|Func_Argentina_Unique_Tax_Key|identifierar Argentinas unika skattenyckel|nej|
|Func_arizona_drivers_license_number|identifierar Arizona-drivrutinens licensnummer|nej|
|Func_arkansas_drivers_license_number|identifierar Arkansas-drivrutinens licensnummer|nej|
|Func_australian_business_number|identifierar Australiens företagsnummer|nej|
|Func_Australian_Company_Number|identifierar Australiens företagsnummer|nej|
|Func_australian_medical_account_number|identifierar Australiens medicinska kontonummer|nej|
|Func_australian_tax_file_number|identifierar Australiens skattefilnummer|ja|
|Func_austria_eu_ssn_or_equivalent|identifierar socialförsäkringsnumret för Österrike|nej|
|Func_austria_eu_tax_file_number|identifierar Österrikes skattefilnummer|nej|
|Func_Austria_Value_Added_Tax|identifierar Österrikes moms|nej|
|Func_belgium_national_number|identifierar belgiens nationella nummer|nej|
|Func_belgium_value_added_tax_number|identifierar Belgiens momsnummer|nej|
|Func_brazil_cnpj|identifierar brasiliens juridiska personnummer (CNPJ)|ja|
|Func_brazil_cpf|identifierar Brasiliens CPF|ja|
|Func_brazil_rg|identifierar Brasiliens RG|nej|
|Func_british_columbia_drivers_license_number|identifierar British Columbia driver's license number|nej|
|Func_bulgaria_eu_national_id_card|identifierar Bulgariens enhetliga civilnummer|nej|
|Func_california_drivers_license_number|identifierar Kaliforniens drivrutinsnummer|nej|
|Func_canadian_sin|identifierar Kanada sin|ja|
|Func_chile_id_card|identifierar Chile ID-kort|nej|
|Func_china_resident_id|identifierar boende ID i Kina|nej|
|Func_colorado_drivers_license_number|identifierar Colorado driver's license number|nej|
|Func_connecticut_drivers_license_number|identifierar Connecticut-drivrutinens licensnummer|nej|
|Func_credit_card|identifierar kreditkort|ja|
|Func_croatia_id_card|identifierar Kroatiens ID-kort|nej|
|Func_croatia_oib_number|identifierar Kroatiens OIB-nummer|nej|
|Func_cyprus_eu_tax_file_number|identifierar cyperns skattefilnummer|nej|
|Func_czech_id_card|identifierar tjeckiska ID-kort|nej|
|Func_czech_id_card_new_format|identifierar tjeckiska ID-kort i nytt format|nej|
|Func_dea_number|identifierar DEA-nummer|ja|
|Func_denmark_eu_tax_file_number|detects Danmark personal identification number|nej|
|Func_district_of_columbia_drivers_license_number|identifierar District of Columbia driver's license number|nej|
|Func_estonia_eu_national_id_card|identifierar Estland Personal Identification Code|nej|
|Func_eu_debit_card|identifierar EU-betalkort|nej|
|Func_finnish_national_id|identifierar finska nationella ID|nej|
|Func_florida_drivers_license_number|identifierar Florida-drivrutinens licensnummer|nej|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|identifierar Florida, Maryland, Michigan, Minnesota driver's license number|nej|
|Func_formatted_itin|identifierar formaterad US ITIN|ja|
|Func_fr_insee|identifierar Frankrike INSEE|nej|
|Func_fr_passport|identifierar Frankrike-pass|nej|
|Func_france_eu_tax_file_number|identifierar Frankrikes skattenummer|nej|
|Func_france_value_added_tax_number|detects France value added tax number|nej|
|Func_french_drivers_license|identifierar franska körkort|nej|
|Func_french_insee|identifierar franska INSEE|nej|
|Func_georgia_drivers_license_number|identifierar Georgias körkortsnummer|nej|
|Func_german_drivers_license|identifierar Tysklands körkort|nej|
|Func_german_passport|identifierar Tyskland-passet|nej|
|Func_german_passport_data|identifierar Tyskland-passet|nej|
|Func_germany_eu_tax_file_number|identifierar skattefilnumret för Tyskland|nej|
|Func_germany_value_added_tax_number|identifierar momsnumret för Tyskland|nej|
|Func_greece_eu_ssn|identifierar Grekland sin (AMKA)|nej|
|Func_hawaii_drivers_license_number|identifierar Hawaii-drivrutinens licensnummer|nej|
|Func_hong_kong_id_card|identifierar Hongkong-ID-kort|nej|
|Func_hungarian_value_added_tax_number|identifierar Ungerns momsnummer|nej|
|Func_hungary_eu_national_id_card|identifierar Ungerns personliga ID-nummer|nej|
|Func_hungary_eu_ssn_or_equivalent|identifierar Ungerns personnummer|nej|
|Func_hungary_eu_tax_file_number|identifierar Ungerns skattefilnummer|nej|
|Func_iban|identifierar IBAN|ja|
|Func_idaho_drivers_license_number|identifierar Idaho-drivrutinens licensnummer|nej|
|Func_illinois_drivers_license_number|identifierar Illinois driver's license number|nej|
|Func_india_aadhaar|identifierar Indien aadhaar|ja|
|Func_indiana_drivers_license_number|identifierar Indiana-drivrutinens licensnummer|nej|
|Func_iowa_drivers_license_number|identifierar Iowa-drivrutinens licensnummer|nej|
|Func_ireland_pps|identifierar Irland PPS|nej|
|Func_israeli_national_id_number|identifierar Israels nationella ID-nummer|nej|
|Func_italy_eu_national_id_card|identifierar italiens räkenskapskod|nej|
|Func_italy_value_added_tax_number|identifierar italiens momsnummer|nej|
|Func_japanese_my_number_corporate|identifierar Japan my number corporate|ja|
|Func_japanese_my_number_personal|identifierar min personliga japanska siffra|ja|
|Func_jp_bank_account|identifierar det japanska bankkontot|nej|
|Func_jp_bank_account_branch_code|identifierar banköverföringskod för japanska bankkontor|nej|
|Func_jp_drivers_license_number|identifierar Japans körkortsnummer|nej|
|Func_jp_passport|identifierar Japan-pass|nej|
|Func_jp_resident_registration_number|identifierar registreringsnumret för japaninvånare|nej|
|Func_jp_sin|identifierar Japan SIN|nej|
|Func_jp_sin_pre_1997|identifierar Japan sin före 1997|nej|
|Func_kansas_drivers_license_number|identifierar Kansas driver's license number|nej|
|Func_kentucky_drivers_license_number|identifierar Kentucky-drivrutinens licensnummer|nej|
|Func_kentucky_massachusetts_virginia_drivers_license_number|detects Kentucky, Massachusetts, Virginia driver's license number|nej|
|Func_latvia_eu_national_id_card|identifierar personlig kod för Lettland|nej|
|Func_lithuania_eu_tax_file_number|identifierar den personliga Litauen-koden|nej|
|Func_louisiana_drivers_license_number|identifierar Louisiana driver's license number|nej|
|Func_luxemburg_eu_tax_file_number|identifierar Luxemburgs nationella identifikationsnummer (naturliga personer)|nej|
|Func_luxemburg_eu_tax_file_number_non_natural|identifierar Luxemburgs nationella identifikationsnummer (icke-naturliga personer)|nej|
|Func_maine_drivers_license_number|identifierar Maine-drivrutinens licensnummer|nej|
|Func_manitoba_drivers_license_number|identifierar drivrutinsnumret för Manitoba|nej|
|Func_maryland_drivers_license_number|identifierar Maryland-drivrutinens licensnummer|nej|
|Func_massachusetts_drivers_license_number|identifierar Massachusetts driver's license number|nej|
|Func_mexico_population_registry_code|identifierar den mexikoa registerkoden för population|nej|
|Func_michigan_minnesota_drivers_license_number|detects Michigan, Minnesota driver's license number|nej|
|Func_minnesota_drivers_license_number|identifierar Minnesota-drivrutinens licensnummer|nej|
|Func_mississippi_oklahoma_drivers_license_number|identifierar Mississippi, Oklahoma-drivrutinens licensnummer|nej|
|Func_missouri_drivers_license_number|identifierar Missouri-drivrutinens licensnummer|nej|
|Func_montana_drivers_license_number|identifierar Montana-drivrutinens licensnummer|nej|
|Func_nebraska_drivers_license_number|identifierar Nebraska-drivrutinens licensnummer|nej|
|Func_netherlands_bsn|identifierar nederländska BSN|nej|
|Func_netherlands_eu_tax_file_number|identifierar det nederländska skattefilnumret|nej|
|Func_netherlands_value_added_tax_number|identifierar nederländska momsnummer|nej|
|Func_nevada_drivers_license_number|identifierar Nevada-drivrutinens licensnummer|nej|
|Func_new_brunswick_drivers_license_number|identifierar New Brunswick-drivrutinens licensnummer|nej|
|Func_new_hampshire_drivers_license_number|identifierar New Hampshire-drivrutinens licensnummer|nej|
|Func_new_jersey_drivers_license_number|identifierar drivrutinens licensnummer i New Jersey|nej|
|Func_new_mexico_drivers_license_number|identifierar New Mexico driver's license number|nej|
|Func_new_york_drivers_license_number|identifierar drivrutinsnumret för New York|nej|
|Func_new_zealand_bank_account_number|identifierar Nya Zeelands bankkontonummer|nej|
|Func_new_zealand_inland_revenue_number|identifierar Nya Zeelands inåtelsnummer|nej|
|Func_new_zealand_ministry_of_health_number|identifierar Nya Zeeland på hälsonummer|nej|
|Func_newfoundland_labrador_drivers_license_number|identifierar Newfoundland Labrador-drivrutinens licensnummer|nej|
|Func_newzealand_driver_license_number|identifierar Nya Zeeland-drivrutinslicensnummer|nej|
|Func_newzealand_social_welfare_number|identifierar Nya Zeelands sociala nätverk-nummer|nej|
|Func_north_carolina_drivers_license_number|identifierar North Carolina-drivrutinens licensnummer|nej|
|Func_north_dakota_drivers_license_number|identifierar North Dakota-drivrutinens licensnummer|nej|
|Func_norway_id_number|identifierar Norges ID-nummer|nej|
|Func_nova_scotia_drivers_license_number|identifierar Nova Scotia-drivrutinens licensnummer|nej|
|Func_ohio_drivers_license_number|identifierar Ohio-drivrutinens licensnummer|nej|
|Func_ontario_drivers_license_number|identifierar Ontario körkortsnummer|nej|
|Func_pennsylvania_drivers_license_number|identifierar Pennsylvania-drivrutinens licensnummer|nej|
|Func_pesel_identification_number|identifierar Polens National ID (PESEL)|nej|
|Func_poland_eu_tax_file_number|identifierar Polens skattefilnummer|nej|
|Func_polish_national_id|identifierar Polens identitetskort|nej|
|Func_polish_passport_number|upptäcker polska passnummer|nej|
|Func_polish_regon_number|identifierar polska REGON-nummer|nej|
|Func_portugal_eu_tax_file_number|identifierar Portugals skatteidentifieringsnummer|nej|
|Func_prince_edward_island_drivers_license_number|identifierar Prince Edward Island driver's license number|nej|
|Func_quebec_drivers_license_number|identifierar Quebecs körkortsnummer|nej|
|Func_randomized_formatted_ssn|identifierar slumpmässigt formaterade US SSN|ja|
|Func_randomized_unformatted_ssn|identifierar slumpmässigt oformaterade US SSN|ja|
|Func_rhode_island_drivers_license_number|identifierar Rhode Island driver's license number|nej|
|Func_romania_eu_national_id_card|identifierar Rumäniens personliga numeriska kod (CNP)|nej|
|Func_saskatchewan_drivers_license_number|identifierar Saskatchewan-drivrutinens licensnummer|nej|
|Func_slovakia_eu_national_id_card|identifierar personligt nummer för Slovakien|nej|
|Func_slovenia_eu_national_id_card|identifierar Sloveniens unika huvudpersonnummer|nej|
|Func_slovenia_eu_tax_file_number|identifierar Sloveniens skattenummer|nej|
|Func_south_africa_identification_number|identifierar Sydafrikas ID-nummer|ja|
|Func_south_carolina_drivers_license_number|identifierar South Carolina-drivrutinens licensnummer|nej|
|Func_south_dakota_drivers_license_number|identifierar South Dakota-drivrutinens licensnummer|nej|
|Func_south_korea_resident_number|identifierar sydkoreanska boendenummer|nej|
|Func_spain_eu_DL_and_NI_number_citizen|identifierar Spaniens DL- och NI-nummer för medborgare|nej|
|Func_spain_eu_DL_and_NI_number_foreigner|identifierar Spaniens DL- och NI-nummer foreigner|nej|
|Func_spain_eu_driver är s_license_number|identifierar Spaniens körkortsnummer|nej|
|Func_spain_eu_tax_file_number|identifierar spaniens skattefilnummer|nej|
|Func_spanish_social_security_number|identifierar det spanska personnumret|nej|
|Func_ssn|Funktion för att identifiera icke-slumpvis formaterade US SSN|ja|
|Func_sweden_eu_tax_file_number|identifierar skattefilnummer för Sverige|nej|
|Func_swedish_national_identifier|identifierar svenska nationella identifierare|ja|
|Func_swiss_social_security_number_ahv|identifierar det schweiziska personnumret AHV|nej|
|Func_taiwanese_national_id|identifierar taiwanesiska nationella ID|nej|
|Func_tennessee_drivers_license_number|identifierar Tennessee-drivrutinens licensnummer|nej|
|Func_texas_drivers_license_number|identifierar driver's license number i Texas|nej|
|Func_Thai_Citizen_Id|identifierar thailändska,id för medborgare|nej|
|Func_Turkish_National_Id|identifierar turkiska national-ID|ja|
|Func_uk_drivers_license|identifierar uk driver's license|nej|
|Func_uk_eu_tax_file_number|identifierar ett unikt taxpayer-nummer i Storbritannien|nej|
|Func_uk_nhs_number|identifierar UK NHS-nummer|ja|
|Func_uk_nino|identifierar brittisk NINO|nej|
|Func_unformatted_canadian_sin|identifierar oformaterad kanadensisk SIN|nej|
|Func_unformatted_itin|identifierar oformaterade amerikanska ITIN|ja|
|Func_unformatted_ssn|identifierar icke-slumpmässigt oformaterade US SSN|ja|
|Func_usa_uk_passport|identifierar USA- och Storbritannien-pass|ja|
|Func_utah_drivers_license_number|identifierar Utah-drivrutinens licensnummer|nej|
|Func_vermont_drivers_license_number|identifierar Vermont-drivrutinens licensnummer|nej|
|Func_virginia_drivers_license_number|identifierar Virginia driver's license number|nej|
|Func_washington_drivers_license_number|identifierar Washington Driver's license number|nej|
|Func_west_virginia_drivers_license_number|identifierar West Virginia-drivrutinens licensnummer|nej|
|Func_wisconsin_drivers_license_number|identifierar Wisconsin-drivrutinens licensnummer|nej|
|Func_wyoming_drivers_license_number|identifierar Wyoming-drivrutinens licensnummer|nej|
|

## <a name="func_us_date"></a>Func_us_date

Func_us_date söker efter datum i vanliga amerikanskt format. De vanliga formaten är "månad/dag/år", "månad-dag-år" och "månad dag år ". Namnen eller förkortningarna på månader är inte fallkänsliga.

Exempel:

- 2 december 2016
- 2 december 2016
- dec 02 2016
- 12/2/2016
- 12/02/16
- 2 december 2016
- 12-2-16

Godkända månadsnamn:

- Engelska
  - Januari, Februari, Mars, April, Maj, Juni, Juli, Augusti, September, Oktober, November, December
  - Jan. Feb. Mar. Apr. May June July aug. September. Oct. Nov. Dec.

## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates söker efter datum i usa. format (och de flesta platser utanför USA), till exempel "dag/månad/år", "dag-månad-år" och "dag månad år". Namnen eller förkortningarna på månader är inte fallkänsliga.

Exempel:

- 2 december 2016
- 2 december 2016
- 2 december 16
- 2/12/2016
- 02/12/16
- 2/12-2016
- 2-12-16

Godkända månadsnamn:

- Engelska
  - Januari, Februari, Mars, April, Maj, Juni, Juli, Augusti, September, Oktober, November, December
  - Jan. Feb. Mar. Apr. May June July aug. September. Oct. Nov. Dec.
- Dutch
  - januari, februari, maart, april, mei, juni, juli, augustus, September, ocktober, oktober, november, december
  - jan feb maart apr mei jun jul aug sep sep okt nov dec
- French
  - janvier, février, mars, avril, mai, juin juillet, aoèt, sepembre, octobre, novembre, décembre
  - janv. févr. mars avril mai juin juil. aoút september. okt. nov. déc.
- German
  - jänuar, februari, brandz, april, mai, juni juli, augusti, september, oktober, november, dezember
  - Jan./Jän. Feb. Zzz Apr. Mai Juni Juli aug. September. Okt. Nov. Dez.
- Italian
  - gennaio, febbraio, marzo, aprile, mkario, luglio, agosto, settembre, ottobre, novembre, dicembre
  - genn. feb feb mar. apr. förstoring. gixoo luglio ag. . ott. nov. dic.
- Portugisiska
  - janeiro, janeiroeiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
  - jan fev mar a mai jun jul sedan nov dez
- Spanish
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, sepiembre, octubre, noviembre, diciembre
  - enero feb. marzo agar. mayo jun. jul. sedan till september/set. okt. nov. dic.

## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (inaktuellt)

> [!NOTE]
> Den här funktionen är inaktuell eftersom den bara har stöd för portugisiska månadsnamn, som nu ingår i  `Func_eu_date` funktionen ovan.

Med den här funktionen söker du efter ett datum i det format som används ofta på portugisiska. Formatet för den här funktionen är detsamma som  `Func_eu_date` , och det skiljer sig bara på det språk som används.

Exempel:

- 2 Dez 2016
- 02 dez 2016
- 2 Dez 16
- 2/12/2016
- 02/12/16
- 2-Dez-2016
- 2-12-16

Godkända månadsnamn:

- Portugisiska
  - janeiro, janeiroeiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
  - jan fev mar a mai jun jul sedan nov dez

## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (inaktuellt)

> [!NOTE]
> Den här funktionen är inaktuell eftersom den bara har stöd för nederländska månadsnamn, som nu ingår i  `Func_eu_date` funktionen ovan.

Med den här funktionen söker du efter ett datum i det format som används ofta på nederländska. Formatet för den här funktionen är detsamma som  `Func_eu_date` , och det skiljer sig bara på det språk som används.

Exempel:

- 2 Mei 2016
- 02 mei 2016
- 2 Mei 16
- 2/12/2016
- 02/12/16
- 2-Mei-2016
- 2-12-16

Godkända månadsnamn:

- Dutch
  - januari, februari, maart, april, mei, juni, juli, augustus, September, ocktober, oktober, november, december
  - jan feb maart apr mei jun jul aug sep sep ut okt nov dec

## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date letar efter datum i format som ofta används av kreditkort och betalkort. Den här funktionen matchar datum i formatet "månad/år", "månad-år", "[månadsnamn] år" och "[månadsförkortning] år". Namnen eller förkortningarna på månader är inte fallkänsliga.

Exempel:

- MM/YY - t.ex. 11/01 eller 1/11
- MM/YYYY - t.ex. 2011-01-01 eller 1/2011
- MM-YY - till exempel 01-22 eller 1-11
- MM-YYYY - till exempel 01-2000 eller 1-2000

Följande format stöder YY eller YYYY:

- Månad-YYYY -- exempelvis jan-2010 eller januari-2010 eller jan-10 eller januari-10
- Månad YYYY - till exempel 'januari 2010' eller 'jan 2010' eller 'januari 10' eller 'jan 10'
- MånadYYY - till exempel 'januari2010' eller 'jan2010' eller 'januari10' eller 'jan10'
- Månad/YYY - exempelvis januari/2010 eller jan/2010 eller januari/10 eller jan/10

Godkända månadsnamn:

- Engelska
  - Januari, Februari, Mars, April, Maj, Juni, Juli, Augusti, September, Oktober, November, December
  - Jan feb apr maj juni juli augusti september nov dec

## <a name="func_us_address"></a>Func_us_address

Func_us_address efter ett amerikanskt postnummer följt av ett giltigt postnummer. Postnumret måste vara ett av de korrekta postnummer som är kopplade till namnet eller förkortningen i USA. Usa:s delstatnamn och postnummer kan inte avgränsas med skiljetecken eller bokstäver.

Exempel:

- Washington 98052
- Washington 98052-9998
- WA 98052
- WA 98052-9998
