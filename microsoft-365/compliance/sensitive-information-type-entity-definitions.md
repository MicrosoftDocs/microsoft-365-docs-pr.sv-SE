---
title: Entitetsdefinitioner för typer av känslig information
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: I dataförlustskydd (DLP) i Säkerhetsefterlevnadscenter finns över 200 typer av känslig information som är färdiga att använda i &amp; DLP-principerna. Den här artikeln innehåller alla dessa typer av känslig information och visar vad en DLP-princip söker efter när den identifierar varje typ.
ms.openlocfilehash: ff976389e75e96d0a018d7c5379e2831313388dc
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730480"
---
# <a name="sensitive-information-type-entity-definitions"></a>Entitetsdefinitioner för typer av känslig information

I dataförlustskydd (DLP) i efterlevnadscentret finns många typer av känslig information som är färdiga att använda i DLP-principerna. Den här artikeln innehåller alla dessa typer av känslig information och visar vad en DLP-princip söker efter när den identifierar varje typ. Mer information om typer av känslig information finns i [Typer av känslig information](sensitive-information-type-learn-about.md)

## <a name="aba-routing-number"></a>ABA-routningsnummer

### <a name="format"></a>Format

Nio siffror som kan vara i ett formaterat eller oformaterat mönster

### <a name="pattern"></a>Mönster

- två siffror i områdena 00-12, 21-32, 61-72 eller 80
- två siffror
- Ett valfritt bindestreck
- fyra siffror
- Ett valfritt bindestreck
- en siffra


### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En princip har med medelhög säkerhet upptäckt den här typen av känslig information om, inom 300 tecken:
- Funktionen för Func_aba_routing hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_ABA_Routing hittas.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_aba_routing hittar innehåll som matchar mönstret.

```xml
    <!-- ABA Routing Number -->
    <Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_aba_routing" />
      </Pattern>
    </Entity>
```


### <a name="keywords"></a>Nyckelord

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba number
- aba #
- aba
- abarouting #
- abaroutingnumber
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bankrouting #
- bankroutingnumber
- routning #
- routningsnr
- routningsnummer
- routing transit number
- routning #
- RTN


## <a name="argentina-national-identity-dni-number"></a>Argentinas national identity (DNI) number

### <a name="format"></a>Format

Åtta siffror med eller utan punkter

### <a name="pattern"></a>Mönster

Åtta siffror:
- två siffror
- en valfri period
- tre siffror
- en valfri period
- tre siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_argentina_national_id hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_argentina_national_id hittas.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity Number 
- cedula 
- ratdula 
- dni 
- documento nacional de identidad 
- documento número 
- documento numero 
- registro nacional de las personas 
- rnp 
   
## <a name="argentina-unique-tax-identification-key-cuitcuil"></a>Argentinas unika skatteidentifieringsnyckel (CUIT/CUIL)

### <a name="format"></a>Format

Elva siffror med streck

### <a name="pattern"></a>Mönster

Elva siffror med ett streck:
- två siffror i 20, 23, 24, 27, 30, 33 eller 34
- ett bindestreck (-)
- åtta siffror
- ett bindestreck (-)
- en checksiffra

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar `Func_Argentina_Unique_Tax_Key` innehåll som matchar mönstret.
- Ett nyckelord `Keyword_Argentina_Unique_Tax_Key` från hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar `Func_Argentina_Unique_Tax_Key` innehåll som matchar mönstret.

```xml
    <!-- Argentina Unique Tax Identification Key (CUIT/CUIL) -->
      <Entity id="98da3da1-9199-4571-b7c4-b6522980b507" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
          <Match idRef="Keyword_Argentina_Unique_Tax_Key" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_argentina_unique_tax_key"></a>Keyword_Argentina_Unique_Tax_Key

- Dirigeringve Unica de Identificacion Tributaria
- CUIT
- unik kod för identifiering av person 
- Kodriska Única de Identificación Tributaria
- unik id-kod
- CUIL
- Unik skatteidentifieringsnyckel
- Unique Labour Identification Key
- Unik nyckel för id:t
- Unik id-kod för arbete
- Unik kod för arbetsidentifiering
- Unik arbetsidentifieringsnyckel
- Unik nyckel för arbetsidentifiering
- Unik kod för skatteidentifiering
- Unik nyckel för skatteidentifiering
- Unique Labor Identification Code
- Unik kod för Labor Identification
- Unique Labor Identification Key
- Unik nyckel för Labor Identification
- skatte-ID
- taxID #
- taxId
- taxidnumber
- tax number
- tax no
- skatt #
- skatt #
- taxpayer ID
- taxpayer number
- taxpayer no
- taxpayer #
- taxpayer #
- skatteidentitet
- tax identification
- Número de Identificación Fiscal
- número de contribuyente
   
   
## <a name="australia-bank-account-number"></a>Bankkontonummer för Australien

### <a name="format"></a>Format

Sex till tio siffror med eller utan ett bankkontornummer

### <a name="pattern"></a>Mönster

Kontonumret kan vara 6 till 10 siffror.

Bankkontor i Australien:
- tre siffror 
- ett bindestreck 
- tre siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_australia_bank_account_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_australia_bank_account_number hittas.
- Det reguljära uttrycket Regex_australia_bank_account_number_bsb hittar innehåll som matchar mönstret.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_australia_bank_account_number hittar innehåll som matchar mönstret.

- Ett nyckelord från Keyword_australia_bank_account_number hittas.

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_australia_bank_account_number"></a>Keyword_australia_bank_account_number

- swift bankkod
- brevkortsbank
- basvaluta
- USA-konto
- innehavarens adress
- bank address
- informationskonto
- fondöverföringar
- bankavgifter
- bankinformation
- bankinformation
- fullständiga namn
- han/hon

## <a name="australia-business-number"></a>Australiens företagsnummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen


### <a name="format"></a>Format

11 siffror med valfria avgränsare

### <a name="pattern"></a>Mönster

11 siffror med valfria avgränsare:

- två siffror
- Ett valfritt bindestreck eller blanksteg
- tre siffror
- Ett valfritt bindestreck eller blanksteg
- tre siffror
- Ett valfritt bindestreck eller blanksteg
- tre siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_australian_business_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_australian_business_number hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_australian_business_number hittar innehåll som matchar mönstret.

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Nyckelord

#### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- australia business no
- företagsnummer
- abn #
- businessid #
- företags-ID
- abn
- businessno #

## <a name="australia-company-number"></a>Australiens företagsnummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

Nio siffror med avgränsare

### <a name="pattern"></a>Mönster

Nio siffror med avgränsare:

- tre siffror
- ett blanksteg
- tre siffror
- ett blanksteg
- tre siffror


### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_Australian_Company_Number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_Australian_Company_Number hittas.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_Australian_Company_Number hittar innehåll som matchar mönstret.

```xml
      <!-- Australia Company Number -->
      <Entity id="b1fba4f7-7b3e-4bb9-8f9a-9366df604dbb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Australian_Company_Number" />
          <Match idRef="Keyword_Australian_Company_Number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_Australian_Company_Number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Nyckelord

#### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- kan
- australiensiska företagnr
- australiensiska företagnr #
- australiens företagsnummer
- australiensiska företag no
- australiensiska företag no #
- australiensiskt företagsnummer

## <a name="australia-drivers-license-number"></a>Australiens körkortsnummer

### <a name="format"></a>Format

nio bokstäver och siffror

### <a name="pattern"></a>Mönster

Nio bokstäver och siffror: 

- två siffror eller bokstäver (inte teckenkänsliga) 
- två siffror 
- Fem siffror eller bokstäver (inte teckenkänsliga)

ELLER

- En till två valfria bokstäver (inte teckenkänsliga) 
- fyra till nio siffror

ELLER

- nio siffror eller bokstäver (inte teckenkänsliga)

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_australia_drivers_license_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_australia_drivers_license_number hittas.
- Inget nyckelord från Keyword_australia_drivers_license_number_exclusions hittas.

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_australia_drivers_license_number"></a>Keyword_australia_drivers_license_number

- internationella biltillstånd
- Australian Automobile Association
- internationellt körtillstånd
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Licence
- Driver Licences
- DriversLic
- DriversLicence
- DriversLicences
- Drivers Lic
- Drivers Lics
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- Driver'Licence
- Driver'Licences
- Driver' Lic
- Driver' Lics
- Driver' Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's Licence
- Driver's Licences
- DriverLic #
- DriverLics #
- DriverLicence #
- DriverLicences #
- Driver Lic #
- Driver Lics #
- Driver Licence #
- Driver Licences #
- DriversLic #
- DriversLics #
- DriversLicence #
- DriversLicences #
- Drivers Lic #
- Drivers Lics #
- Drivers Licence #
- Drivers Licences #
- Driver'Lic #
- Driver'Lics #
- Driver'Licence #
- Driver'Licences #
- Driver' Lic #
- Driver' Lics #
- Driver' Licence #
- Driver' Licences #
- Driver'sLic #
- Driver'sLics #
- Driver'sLicence #
- Driver'sLicences #
- Driver's Lic #
- Driver's Lics #
- Driver's Licence #
- Driver's Licences # 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a>Keyword_australia_drivers_license_number_exclusions

- aaa
- DriverLicense
- DriverLicenses
- Driver License
- Driver Licenses
- DriversLicense
- DriversLicenses
- Drivers License
- Drivers Licenses
- Driver'License
- Driver'Licenses
- Driver' License
- Driver' Licenses
- Driver'sLicense
- Driver'sLicenses
- Driver's License
- Driver's Licenses
- DriverLicense #
- DriverLicenses #
- Driver License #
- Driver Licenses #
- DriversLicense #
- DriversLicenses #
- Drivers License #
- Drivers Licenses #
- Driver'License #
- Driver'Licenses #
- Driver' License #
- Driver' Licenses #
- Driver'sLicense #
- Driver'sLicenses #
- Driver's License #
- Driver's Licenses #
   
## <a name="australia-medical-account-number"></a>Australiens medicinska kontonummer

### <a name="format"></a>Format

10–11 siffror

### <a name="pattern"></a>Mönster

10–11 siffror:
- Den första siffran i intervallet 2–6
- Nio siffror är en kontrollsiffra
- Tionde siffran är problemets siffra
- Elfte siffran (valfritt) är det enskilda talet

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_australian_medical_account_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_Australia_Medical_Account_Number hittas.
- Kontrollsumman passeras.


```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- bankkontoinformation
- medicare payments
- amorteringskonto
- bank payments
- informationsgren
- kreditkortslån
- avdelning för personalavdelningen
- lokal tjänst
- medicare

   
## <a name="australia-passport-number"></a>Australien passnummer

### <a name="format"></a>Format

Åtta eller nio alfanumeriska tecken 

### <a name="pattern"></a>Mönster

- en bokstav (N, E, D, F, A, C, U, X) följt av 7 siffror eller
- 2 bokstäver (PA, PB, PC, PD, PE, PF, PU, PW, PX, PZ) följt av 7 siffror.

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära `Regex_australia_passport_number` uttrycket hittar innehåll som matchar mönstret.
- Ett nyckelord `Keyword_australia_passport_number` från hittas.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära `Regex_australia_passport_number` uttrycket hittar innehåll som matchar mönstret.

```xml
    <!-- Australia Passport Number -->
    <Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Match idRef="Keyword_australia_passport_number" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_australia_passport_number" />
      </Pattern>
    </Entity>  
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer
- passinformation
- det här är något som är av samma dag som det
- Commonwealth of australia
- department of sås
- national identity card
- resedokument
- utfärdar behörighet


## <a name="australia-tax-file-number"></a>Australiens skattenummer

### <a name="format"></a>Format

åtta till nio siffror

### <a name="pattern"></a>Mönster

Åtta till nio siffror visas vanligtvis med blanksteg enligt följande:
- tre siffror 
- ett valfritt blanksteg 
- tre siffror 
- ett valfritt blanksteg 
- Två till tre siffror där den sista siffran är en bård

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_australian_tax_file_number hittar innehåll som matchar mönstret.
- Inget nyckelord från Keyword_Australia_Tax_File_Number eller Keyword_number_exclusions hittas.
- Kontrollsumman passeras.

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- australiensiskt företagsnummer
- marginalskattesats
- medicare – exe
- portföljnummer
- service eller vana att ha
- undanhålla skatt
- enskild skatteåterresa
- tax file number
- tfn

## <a name="austria-drivers-license-number"></a>Österrikes körkortsnummer

### <a name="format"></a>Format

Åtta siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

åtta siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
  
- Det reguljära  `Regex_austria_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_austria_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Austria Driver's License Number -->
      <Entity id="682f18ce-44eb-482b-8198-2bcb96a0761e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_austria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver är s_license_number

- fuscheschein
- füscheschein
- Füschescheine
- Füscheinnummer
- Füscheinnummern

## <a name="austria-identity-card"></a>Österrike-identitetskort
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

En kombination av bokstäver, siffror och specialtecken med 24 tecken
  
### <a name="pattern"></a>Mönster

24 tecken:
  
-  22 bokstäver (inte versaler, siffror, omslag, snedstreck eller plustecken 
    
- Två bokstäver (inte teckenkänsliga), siffror, omslag, snedstreck, plustecken eller likhetstecken
    
### <a name="checksum"></a>Kontrollsumma

Ej tillämpligt
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
  
- Det reguljära  `Regex_austria_eu_national_id_card` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_austria_eu_national_id_card` från hittas. 
   
```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- identitetsnummer
- national id
- personalaus denskö, österreich

## <a name="austria-passport-number"></a>Österrike passnummer

### <a name="format"></a>Format

En bokstav följt av ett valfritt blanksteg och sju siffror
  
### <a name="pattern"></a>Mönster

En kombination av en bokstav, sju siffror och ett blanksteg:
  
- en bokstav (inte en ärendekänslig)
- ett blanksteg (valfritt)
- sju siffror
    
### <a name="checksum"></a>Kontrollsumma

ej tillämpligt
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_austria_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_austria_eu_passport_number` hittas. 
- Det reguljära `Regex_eu_passport_date1` uttrycket hittar datum i formatet DD.MM.YYYY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_austria_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_austria_eu_passport_number` hittas. 
    
```xml
      <!-- Austria Passport Number -->
      <Entity id="1c96ae4e-303b-447d-86c7-77113ac266bf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- reisepasse
- No-Reisepass 
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisessesse

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum

## <a name="austria-social-security-number"></a>Österrikes personnummer

### <a name="format"></a>Format

10 siffror i det angivna formatet
  
### <a name="pattern"></a>Mönster

10 siffror:
  
- Tre siffror som motsvarar ett serienummer 
- en checksiffra
- Sex siffror som motsvarar födelsedatumet (DDMMYY)
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_austria_eu_ssn_or_equivalent` innehåll som matchar mönstret. 
- ett nyckelord  `Keywords_austria_eu_ssn_or_equivalent` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_austria_eu_ssn_or_equivalent` innehåll som matchar mönstret. 
    
```xml
      <!-- Austria Social Security Number -->
      <Entity id="6896a906-86c9-4d19-a2da-6e43ccd19b7b" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_austria_eu_telephone_number" />
            <Match idRef="Keywords_austria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- österrike ssn
- ehic number
- ehic no
- insurance code
- insurancecode #
- insurance number (försäkringsnummer)
- insurance no
- denkkenka uppnummer
- denkkversicherung
- socialsecurityno
- socialsecurityno #
- social security no
- personnummer
- social security code
- sozialversicherungsnummer
- sozialversicherungsnummer #
- sofferle sicherheit kein
- solesicherheitkein #
- ssn #
- ssn
- versicherungscode
- versicherungsnummer
- zdravstveno zavarovanje

## <a name="austria-tax-identification-number"></a>Österrikes skatteidentifieringsnummer

### <a name="format"></a>Format

Nio siffror med valfritt bindestreck och snedstreck
  
### <a name="pattern"></a>Mönster

Nio siffror med valfritt bindestreck och snedstreck:
  
- två siffror
- Ett bindestreck (valfritt)
- tre siffror
- ett snedstreck (valfritt)
- fyra siffror
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_austria_eu_tax_file_number` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_austria_eu_tax_file_number` från hittas. 
    
En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_austria_eu_tax_file_number` innehåll som matchar mönstret. 
    
```xml
      <!-- Austria Tax Identification Number -->
      <Entity id="4fd58d22-af28-4451-b18a-6f722430a56d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- österreich
- st.nr.
- steuernummer
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #
- tax number
 
## <a name="austria-value-added-tax"></a>Moms i Österrike
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

Alfanumeriskt mönster med 11 tecken

### <a name="pattern"></a>Mönster

Alfanumeriskt mönster med 11 tecken:

- A eller a
- T eller t
- Valfritt blanksteg
- U eller u
- valfritt blanksteg
- två eller tre siffror
- valfritt blanksteg
- fyra siffror
- valfritt blanksteg
- en eller två siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_Austria_Value_Added_Tax hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_Austria_Value_Added_Tax hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_Austria_Value_Added_Tax hittar innehåll som matchar mönstret.

```xml
      <!-- Austria Value Added Tax -->
      <Entity id="b6a3eda2-c56c-4b69-a5f7-dca34db00f48" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
          <Match idRef="Keyword_Austria_Value_Added_Tax" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Nyckelord

#### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- momsregistreringsnummer
- moms #
- vat-nummer för vat vat
- momsnr.
- vatno #
- momsnummer
- vat för vat
- han/hon
- umsatzsteuernummer
- hannnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- momsregistreringsnummer
- atu-nummer
- användargränssnittsnummer


## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB-autentiseringsnyckel

### <a name="format"></a>Format

Strängen "DocumentDb" följt av de tecken och strängar som beskrivs i mönstret nedan.

### <a name="pattern"></a>Mönster

- Strängen "DocumentDb"
- Valfri kombination av 3–200 gemener eller versaler, siffror, symboler, specialtecken eller blanksteg
- En större än-symbol (>), ett likhetstecken (=), ett citattecken ("), eller en apostrof (')
- Valfri kombination av 86 gemener eller versaler, siffror, snedstreck (/) eller plustecken (+)
- Två likhetstecken (=)

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket CEP_Regex_AzureDocumentDBAuthKey hittar innehåll som matchar mönstret.
- Det reguljära uttrycket CEP_CommonExampleKeywords hittar inte innehåll som matchar mönstret.

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Tekniskt sett identifierar den här typen av känslig information dessa nyckelord med hjälp av ett reguljärt uttryck, inte en nyckelordslista.)

- contoso
- fabrikam
- northwind
- begränsat läge (sandbox)
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS-databasanslutningssträng och Azure SQL en anslutningssträng

### <a name="format"></a>Format

Strängen "Server", "server" eller "datakälla" följt av de tecken och strängar som beskrivs i mönstret nedan, inklusive strängen "cloudapp.azure.<!--no-hyperlink-->com" eller "cloudapp.azure.<!--no-hyperlink-->net" eller "database.windows.<!--no-hyperlink-->net" och strängen "Lösenord" eller "lösenord" eller "pwd".

### <a name="pattern"></a>Mönster

- strängen "Server", "server" eller "datakälla"
- noll till två blankstegstecken
- Ett likhetstecken (=)
- noll till två blankstegstecken
- valfri kombination av 1–200 gemener eller versaler, siffror, symboler, specialtecken eller blanksteg
- Strängen "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net" eller "database.windows.<!--no-hyperlink-->net"
- valfri kombination av 1–300 gemener eller versaler, siffror, symboler, specialtecken eller blanksteg
- strängen "Lösenord", "lösenord" eller "pwd"
- noll till två blankstegstecken
- Ett likhetstecken (=)
- noll till två blankstegstecken
- ett eller flera tecken som inte är semikolon (;), citattecken (") eller apostrof (')
- Semikolon (;), citattecken (") eller apostrof (')

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket CEP_Regex_AzureConnectionString hittar innehåll som matchar mönstret.
- Det reguljära uttrycket CEP_CommonExampleKeywords hittar inte innehåll som matchar mönstret.

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Tekniskt sett identifierar den här typen av känslig information dessa nyckelord med hjälp av ett reguljärt uttryck, inte en nyckelordslista.)

- contoso
- fabrikam
- northwind
- begränsat läge (sandbox)
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iot-connection-string"></a>Azure IoT-anslutningssträng

### <a name="format"></a>Format

Strängen "HostName" följt av de tecken och strängar som beskrivs i mönstret nedan, inklusive strängarna "azure-devices.<!--no-hyperlink-->net" och "SharedAccessKey".

### <a name="pattern"></a>Mönster

- strängen "HostName"
- noll till två blankstegstecken
- Ett likhetstecken (=)
- noll till två blankstegstecken
- valfri kombination av 1–200 gemener eller versaler, siffror, symboler, specialtecken eller blanksteg
- strängen "azure-devices.<!--no-hyperlink-->net"
- valfri kombination av 1–200 gemener eller versaler, siffror, symboler, specialtecken eller blanksteg
- strängen "SharedAccessKey"
- noll till två blankstegstecken
- Ett likhetstecken (=)
- noll till två blankstegstecken
- valfri kombination av 43 gemener eller versaler, siffror, snedstreck (/) eller plustecken (+)
- Ett likhetstecken (=)

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket CEP_Regex_AzureIoTConnectionString hittar innehåll som matchar mönstret.
- Det reguljära uttrycket CEP_CommonExampleKeywords hittar inte innehåll som matchar mönstret.

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Tekniskt sett identifierar den här typen av känslig information dessa nyckelord med hjälp av ett reguljärt uttryck, inte en nyckelordslista.)

- contoso
- fabrikam
- northwind
- begränsat läge (sandbox)
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-publish-setting-password"></a>Lösenord för Azure-publiceringsinställning

### <a name="format"></a>Format

Strängen "userpwd=" följt av en alfanumerisk sträng.

### <a name="pattern"></a>Mönster

- strängen "userpwd="
- valfri kombination av 60 gemener eller siffror
- ett citattecken (")

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket CEP_Regex_AzurePublishSettingPasswords hittar innehåll som matchar mönstret.
- Det reguljära uttrycket CEP_CommonExampleKeywords hittar inte innehåll som matchar mönstret.


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Tekniskt sett identifierar den här typen av känslig information dessa nyckelord med hjälp av ett reguljärt uttryck, inte en nyckelordslista.)

- contoso
- fabrikam
- northwind
- begränsat läge (sandbox)
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-redis-cache-connection-string"></a>Azure Redis-cacheanslutningssträng

### <a name="format"></a>Format

Strängen "redis.cache.windows.<!--no-hyperlink-->net" följt av de tecken och strängar som beskrivs i mönstret nedan, inklusive strängen "lösenord" eller "pwd".

### <a name="pattern"></a>Mönster

- strängen "redis.cache.windows.<!--no-hyperlink-->net"
- valfri kombination av 1–200 gemener eller versaler, siffror, symboler, specialtecken eller blanksteg
- strängen "lösenord" eller "pwd"
- noll till två blankstegstecken
- Ett likhetstecken (=)
- noll till två blankstegstecken
- valfri kombination av 43 tecken som är gemener eller versaler, siffror, snedstreck (/) eller plustecken (+)
- Ett likhetstecken (=)

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket CEP_Regex_AzureRedisCacheConnectionString hittar innehåll som matchar mönstret.
- Det reguljära uttrycket CEP_CommonExampleKeywords hittar inte innehåll som matchar mönstret.

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Tekniskt sett identifierar den här typen av känslig information dessa nyckelord med hjälp av ett reguljärt uttryck, inte en nyckelordslista.)

- contoso
- fabrikam
- northwind
- begränsat läge (sandbox)
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>Format

Strängen "sig" följt av de tecken och strängar som beskrivs i mönstret nedan.

### <a name="pattern"></a>Mönster

- strängen "sig"
- noll till två blankstegstecken
- Ett likhetstecken (=)
- noll till två blankstegstecken
- valfri kombination av 43–53 tecken som är gemener eller versaler, siffror eller procenttecken (%)
- strängen "%3d"
- alla tecken som inte är en bokstav med gemener eller versaler, siffror eller procenttecken (%)

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket CEP_Regex_AzureSAS hittar innehåll som matchar mönstret.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Azure Service Bus-anslutningssträng

### <a name="format"></a>Format

Strängen "EndPoint" följt av de tecken och strängar som beskrivs i mönstret nedan, inklusive strängarna "servicebus.windows.<!--no-hyperlink-->net" och "SharedAccesKey".

### <a name="pattern"></a>Mönster

- strängen "EndPoint"
- noll till två blankstegstecken
- Ett likhetstecken (=)
- noll till två blankstegstecken
- valfri kombination av 1–200 gemener eller versaler, siffror, symboler, specialtecken eller blanksteg
- strängen "servicebus.windows.<!--no-hyperlink-->net"
- valfri kombination av 1–200 gemener eller versaler, siffror, symboler, specialtecken eller blanksteg
- strängen "SharedAccessKey"
- noll till två blankstegstecken
- Ett likhetstecken (=)
- noll till två blankstegstecken
- valfri kombination av 43 tecken som är gemener eller versaler, siffror, snedstreck (/) eller plustecken (+)
- Ett likhetstecken (=)

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket CEP_Regex_AzureServiceBusConnectionString hittar innehåll som matchar mönstret.
- Det reguljära uttrycket CEP_CommonExampleKeywords hittar inte innehåll som matchar mönstret.

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Tekniskt sett identifierar den här typen av känslig information dessa nyckelord med hjälp av ett reguljärt uttryck, inte en nyckelordslista.)

- contoso
- fabrikam
- northwind
- begränsat läge (sandbox)
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key"></a>Azure Storage Account-nyckel

### <a name="format"></a>Format

Strängen "DefaultEndpointsProtocol" följt av de tecken och strängar som beskrivs i mönstret nedan, inklusive strängen "AccountKey".

### <a name="pattern"></a>Mönster

- strängen "DefaultEndpointsProtocol"
- noll till två blankstegstecken
- Ett likhetstecken (=)
- noll till två blankstegstecken
- valfri kombination av 1–200 gemener eller versaler, siffror, symboler, specialtecken eller blanksteg
- strängen "AccountKey"
- noll till två blankstegstecken
- Ett likhetstecken (=)
- noll till två blankstegstecken
- valfri kombination av 86 tecken som är gemener eller versaler, siffror, snedstreck (/) eller plustecken (+)
- två likhetstecken (=)

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket CEP_Regex_AzureStorageAccountKey hittar innehåll som matchar mönstret.
- Det reguljära CEP_AzureEmulatorStorageAccountFilter hittar inte innehåll som matchar mönstret.
- Det reguljära uttrycket CEP_CommonExampleKeywords hittar inte innehåll som matchar mönstret.

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="cep_azure_emulator_storage_account_filter"></a>CEP_azure_emulator_storage_account_filter

(Tekniskt sett identifierar den här typen av känslig information dessa nyckelord med hjälp av ett reguljärt uttryck, inte en nyckelordslista.)

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErPur4I6tq/K1SZFPTOtr/KBHBeksoGMGw==

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Tekniskt sett identifierar den här typen av känslig information dessa nyckelord med hjälp av ett reguljärt uttryck, inte en nyckelordslista.)

- contoso
- fabrikam
- northwind
- begränsat läge (sandbox)
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key-generic"></a>Azure Storage (allmän)

### <a name="format"></a>Format

Valfri kombination av 86 gemener eller versaler, siffror, snedstreck (/) eller plustecken (+), före eller efter tecknen som beskrivs i mönstret nedan.

### <a name="pattern"></a>Mönster

- noll till ett av symbolen större än (>), apostrof ('), likhetstecken (=), citattecken (") eller nummertecken (#)
- valfri kombination av 86 tecken som är gemener eller versaler, siffror, snedstreck (/) eller plustecken (+)
- två likhetstecken (=)

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket CEP_Regex_AzureStorageAccountKeyGeneric hittar innehåll som matchar mönstret.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>Belgiens licensnummer

### <a name="format"></a>Format

10 siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

10 siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_belgium_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från `Keywords_eu_driver's_license_number` eller `Keywords_belgium_eu_driver's_license_number` hittas.
    
```xml
      <!-- Belgium Driver's License Number -->
      <Entity id="d89fd329-9324-433c-b687-2c37bd5166f3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_belgium_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord


#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver är s_license_number

- rijbewijs
- rijbewijsnummer
- füscheschein
- füscheinnummer
- füescheinnummer
- fuscheschein
- fueschein
- fuscheinnummer
- fuescheinnummer
- permis de conduire
- numéro permis conduire


## <a name="belgium-national-number"></a>Belgiens nationalnummer

### <a name="format"></a>Format

11 siffror plus valfria avgränsare

### <a name="pattern"></a>Mönster

11 siffror plus avgränsare:
- Sex siffror och två valfria punkter i formatet YY. MM.DD för födelsedatum 
- En valfri avgränsare från punkt, streck, blanksteg 
- Tre siffror i följd (udda för män, även för kvinnor) 
- En valfri avgränsare från punkt, streck, blanksteg 
- två kontrollsiffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_belgium_national_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_belgium_national_number hittas.
- Kontrollsumman passeras.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_belgium_national_number hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<!-- Belgium National Number -->
       <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_national_number" />
          <Match idRef="Keyword_belgium_national_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_belgium_national_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasting aantal
- bnn #
- bnn
- carte d'identité
- identifiant national
- identifiantnational #
- identificatie
- identification
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- identitet
- var och en
- national number
- national register
- nationalnumber #
- nationalnumber
- nif #
- nif
- numéro d'assuré
- numéro de registre national
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro national
- numéronational #
- personligt ID-nummer
- personalaus en
- personalidnumber #
- registratie
- registrering
- registrationsnumme
- registrierung
- personnummer
- ssn #
- ssn
- steuernummer
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #

## <a name="belgium-passport-number"></a>Belgien passnummer

### <a name="format"></a>Format

Två bokstäver följt av sex siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

Två bokstäver och följt av sex siffror
  
### <a name="checksum"></a>Kontrollsumma

ej tillämpligt
  
### <a name="definition"></a>Definition

 En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_belgium_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_belgium_eu_passport_number` hittas. 
- Det reguljära `Regex_eu_passport_date2` uttrycket hittar datum i formatet DD MM YY eller ett nyckelord från eller `Keywords_eu_passport_date` `Keywords_belgium_eu_passport_number` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_belgium_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_belgium_eu_passport_number` hittas. 

```xml
      <!-- Belgium Passport Number -->
      <Entity id="d7b1315b-21ca-4774-a32a-596010ff78fd" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
            <Match idRef="Keywords_belgium_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- Passeport carte
- Passeport livre
- Pass-Nr
- Passnummer
- reisepass kein

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum

## <a name="belgium-value-added-tax-number"></a>Nummer för moms för belgien
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

Alfanumeriskt mönster med 12 tecken

### <a name="pattern"></a>Mönster

Alfanumeriskt mönster med 12 tecken:

- a bokstaven B eller b
- ett bokstaven E eller e
- en siffra 0
- en siffra mellan 1 och 9
- En valfri punkt eller ett bindestreck eller blanksteg
- fyra siffror
- En valfri punkt eller ett bindestreck eller blanksteg
- fyra siffror


### <a name="checksum"></a>Kontrollsumma

Ja


### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_belgium_value_added_tax_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_belgium_value_added_tax_number hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_belgium_value_added_tax_number hittar innehåll som matchar mönstret.

```xml
      <!-- Belgium Value Added Tax Number -->
      <Entity id="85b5b3c3-f2de-4ae8-ac46-fd3cb38bf9ed" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
          <Match idRef="Keywords_belgium_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
        </Pattern>
      </Entity>
    </Version>
```
### <a name="keywords"></a>Nyckelord

#### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- nº tva
- momsregistreringsnummer
- momsnr
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- han/hon
- han/hon #
- moms #


## <a name="brazil-cpf-number"></a>Brasiliens CPF-nummer

### <a name="format"></a>Format

11 siffror som innehåller en bediff och kan formateras eller vara oformaterade

### <a name="pattern"></a>Mönster

Formaterat:
- tre siffror
- en punkt
- tre siffror
- en punkt
- tre siffror
- ett bindestreck
- två siffror som anger siffror

Oformaterat:
- 11 siffror där de två sista siffrorna är kontrollsiffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_brazil_cpf hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_brazil_cpf hittas.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_brazil_cpf hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- Identifiering
- Registrering
- Intäkter
- Cadastro de Pessoas Físicas 
- Imposto 
- Identificação 
- Inscrição 
- Receita 

   
## <a name="brazil-legal-entity-number-cnpj"></a>Brasiliens juridiska enhetsnummer (CNPJ)

### <a name="format"></a>Format

14 siffror som innehåller ett registreringsnummer, branchnummer och kontrollera siffror, plus avgränsare

### <a name="pattern"></a>Mönster

14 siffror plus avgränsare:

- två siffror 
- en punkt 
- tre siffror 
- en punkt 
- tre siffror (de åtta första siffrorna är registreringsnumret) 
- ett snedstreck 
- fyrsiffrigt branchnummer 
- ett bindestreck 
- två siffror som anger siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_brazil_cnpj hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_brazil_cnpj hittas.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_brazil_cnpj hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ 
- CNPJ/MF 
- CNPJ-MF 
- National Registry of Legal Entities 
- Taxpayers Registry 
- Juridisk person 
- Juridiska enheter 
- Registreringsstatus 
- Business 
- Company
- CNPJ 
- Cadastro Nacional da Pessoa Jurídica 
- Cadastro Geral de Contribuintes 
- CGC 
- Pessoa jurídica 
- Pessoas jurídicas 
- Situação cadasua 
- Inscrição 
- Anstresa 

   
## <a name="brazil-national-identification-card-rg"></a>Brasiliens national identification card (RG)

### <a name="format"></a>Format

Registro Geral (gammalt format): Nio siffror

Registro de Identidade (RIC) (nytt format): 11 siffror

### <a name="pattern"></a>Mönster

Registro Geral (gammalt format):
- två siffror 
- en punkt 
- tre siffror 
- en punkt 
- tre siffror 
- ett bindestreck 
- en siffra som är en biffrig siffra

Registro de Identidade (RIC) (nytt format):
- 10 siffror 
- ett bindestreck 
- en siffra som är en biffrig siffra

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_brazil_rg hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_brazil_rg hittas.
- Kontrollsumman passeras.


```xml
      <!-- Brazil National ID Card (RG) -->
      <Entity id="486de900-db70-41b3-a886-abdf25af119c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_brazil_rg" />
          <Match idRef="Keyword_brazil_rg" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Sådär de identidade
- identitetskort
- national id 
- número de rregistro
- registro de Iidentidade 
- registro geral
- RG (det här nyckelordet är fallkänsligt) 
- RIC (det här nyckelordet är fallkänsligt) 


## <a name="bulgaria-drivers-license-number"></a>Bulgariens körkortsnummer

### <a name="format"></a>Format

Nio siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

nio siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_bulgaria_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_bulgaria_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Bulgaria Driver's License Number -->
      <Entity id="66d39258-94c2-43b2-804b-aa312258e54b" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>    
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver är s_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>Bulgariens enhetliga civilnummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

10 siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

10 siffror utan blanksteg och avgränsare
  
- Sex siffror som motsvarar födelsedatumet (AMMDD) 
- två siffror som motsvarar födelsedatumet
- en siffra som motsvarar kön: En jämn siffra för man och en udda siffra för kvinna
- en checksiffra

### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_bulgaria_eu_national_id_card` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_bulgaria_eu_national_id_card` från hittas. 

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_bulgaria_eu_national_id_card` innehåll som matchar mönstret. 
    
```xml
      <!-- Bulgaria Uniform Civil Number -->
      <Entity id="100d58b1-0a35-4fb1-aa89-e4a86fb53fcc" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_bulgaria_eu_telephone_number" />
            <Match idRef="Keywords_bulgaria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- bnn #
- bnn
- bucn #
- bucn
- edinenhdanski nomer
- egn #
- egn
- identification number
- national id
- national number
- nationalnumber #
- nationalnumber
- personligt ID
- personligt nej
- personligt nummer
- personalidnumber #
- personnummer
- ssn #
- ssn
- uniform civil id
- Uniform civil no
- enhetligt civilnummer
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- unikt unika nummer
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ id
- униформ графдански id
- униформ граждански не
- униформ граждански номер
- униформграфданскиid #
- униформгражданскине. #


## <a name="bulgaria-passport-number"></a>Bulgarien passnummer

### <a name="format"></a>Format

Nio siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

nio siffror 
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_bulgaria_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_bulgaria_eu_passport_number` hittas. 
- Det reguljära `Regex_eu_passport_date1` uttrycket hittar datum i formatet DD.MM.YYYY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_bulgaria_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_bulgaria_eu_passport_number` hittas. 

```xml
      <!-- Bulgaria Passport Number -->
      <Entity id="f7172b82-c588-4216-845e-4e54e397f29a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- паспорт No

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum

## <a name="canada-bank-account-number"></a>Bankkontonummer för Kanada

### <a name="format"></a>Format

7 eller 12 siffror

### <a name="pattern"></a>Mönster

Ett bankkontonummer i Kanada har 7 eller 12 siffror.

Ett bankkontotransitnummer för Kanada är:
- fem siffror 
- ett bindestreck 
- tre siffror ELLER
- en nolla "0" 
- åtta siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_canada_bank_account_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_canada_bank_account_number hittas.
- Det reguljära uttrycket Regex_canada_bank_account_transit_number hittar innehåll som matchar mönstret.

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_canada_bank_account_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_canada_bank_account_number hittas.

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_canada_bank_account_number"></a>Keyword_canada_bank_account_number

- canada savings
- canada revenue agency
- kanadensiskt finansiellt institution
- formulär för direktinsättning
- kanadensiskt invånare
- juridisk representant
- notary public
- oaths
- förmån för barnvård
- allmän barnvård
- kanada för barnskatt
- förmån med inkomstskatt
- taxa
- social insurance number
- återbetalning av inkomstskatt
- förmån för barnskatt
- betalningar
- institution number
- insättningsbegäran
- bankinformation
- direktinsättning

   
## <a name="canada-drivers-license-number"></a>Kanadas körkortsnummer

### <a name="format"></a>Format

Varierar per provins

### <a name="pattern"></a>Mönster

Olika mönster täcker Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec och Saskatchewan

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_[province_name]_drivers_license_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_[province_name]_drivers_license_name hittas.
- Ett nyckelord från Keyword_canada_drivers_license hittas.

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_[province_name]_drivers_license_name

- Provinsförkortningen, till exempel AB
- Namnet på provinsen, till exempel Alberta

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- DL
- DLS
- CDL
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- Driver Licence
- Driver Licences
- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- Driver'License
- Driver'Licenses
- Driver'Licence
- Driver'Licences
- Driver' Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver' Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's License
- Driver's Licenses
- Driver's Licence
- Driver's Licences
- Permis de Conduire
- id
- ids
- idcard-nummer
- idcard-nummer
- idcard #
- idcard-#s
- idcard-kort
- idcard-kort
- idcard
- identification number
- identification numbers
- identification #
- identification #s
- identification card
- identification cards
- identification 
- DL #
- DLS # 
- CDL # 
- CDLS # 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- DriverLicence # 
- DriverLicences # 
- Driver Lic #
- Driver Lics # 
- Driver License # 
- Driver Licenses # 
- Driver License # 
- Driver Licences # 
- DriversLic # 
- DriversLics # 
- DriversLicense # 
- DriversLicenses # 
- DriversLicence # 
- DriversLicences # 
- Drivers Lic # 
- Drivers Lics # 
- Drivers License # 
- Drivers Licenses # 
- Drivers Licence # 
- Drivers Licences # 
- Driver'Lic # 
- Driver'Lics # 
- Driver'License # 
- Driver'Licenses # 
- Driver'Licence # 
- Driver'Licences # 
- Driver' Lic # 
- Driver' Lics # 
- Driver' License # 
- Driver' Licenses # 
- Driver' Licence # 
- Driver' Licences # 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver'sLicence # 
- Driver'sLicences # 
- Driver's Lic # 
- Driver's Lics # 
- Driver's License # 
- Driver's Licenses # 
- Driver's Licence # 
- Driver's Licences # 
- Permis de Conduire # 
- id # 
- ids # 
- idcard-kort # 
- idcard-kort # 
- idcard # 
- identification card # 
- identification cards # 
- identification # 

   
## <a name="canada-health-service-number"></a>Kanadas hälsotjänstnummer

### <a name="format"></a>Format

 10 siffror

### <a name="pattern"></a>Mönster

10 siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_canada_health_service_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_canada_health_service_number hittas.

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- personligt hälsonummer
- patientinformation
- hälsotjänster
- specialtjänster
- bil misstag
- patient sjukhus
- ska vara
- kompensation för anställda
- funktionshinder

      
## <a name="canada-passport-number"></a>Kanada passnummer

### <a name="format"></a>Format

Två versaler följt av sex siffror

### <a name="pattern"></a>Mönster

Två versaler följt av sex siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_canada_passport_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_canada_passport_number eller Keyword_passport hittas.

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_canada_passport_number"></a>Keyword_canada_passport_number

- kanadensiskt klipp
- kanadensiskt pass
- passport-program
- passfoton
- certified translator
- kanadensiska invånare
- bearbetningstider
- förnyelseprogram

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Pass #
- Pass #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °

   
## <a name="canada-personal-health-identification-number-phin"></a>Canada Personal Health Identification Number (PHIN)

### <a name="format"></a>Format

nio siffror

### <a name="pattern"></a>Mönster

nio siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_canada_phin hittar innehåll som matchar mönstret.
- Minst två nyckelord från Keyword_canada_phin eller Keyword_canada_provinces hittas.

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_canada_phin"></a>Keyword_canada_phin

- social insurance number
- hälsoinformation agera
- information om inkomstskatt
- manitoba health
- hälsoregistrering
- köp som köpts tidigare
- förmånsberättigande
- personlig hälsa
- fullmakt
- registreringsnummer
- personligt hälsonummer
- hänvisning till, hänvisning
- professional
- patienthänvisning
- hälso- och hälsocenter

#### <a name="keyword_canada_provinces"></a>Keyword_canada_provinces

- Nunavut
- Quebec
- Northwest Territories
- Ontario
- British Columbia
- Alberta
- Saskatchewan
- Manitoba
- Yukon
- Newfoundland och Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- Kanada

   
## <a name="canada-social-insurance-number"></a>Kanadas socialförsäkringsnummer

### <a name="format"></a>Format

Nio siffror med valfria bindestreck eller blanksteg

### <a name="pattern"></a>Mönster

Formaterat:
- tre siffror 
- Ett bindestreck eller blanksteg 
- tre siffror 
- Ett bindestreck eller blanksteg 
- tre siffror

Oformaterad: nio siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_canadian_sin hittar innehåll som matchar mönstret.
- Minst två av följande kombinationer:
    - Ett nyckelord från Keyword_sin hittas.
    - Ett nyckelord från Keyword_sin_collaborative hittas.
    - Funktionen Func_eu_date hittar ett datum i rätt datumformat.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_unformatted_canadian_sin hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_sin hittas.
- Kontrollsumman passeras.

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_sin"></a>Keyword_sin

- sin 
- social insurance 
- numero d'assurance sociale 
- sins 
- ssn 
- ssns 
- social security 
- numero d'assurance social 
- national identification number 
- national id 
- sin # 
- soc ins 
- sociala ins 

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- driver's license 
- drivers license 
- driver's licence 
- drivers licence 
- DOB 
- Birthdate 
- Födelsedag 
- Födelsedatum 

   
## <a name="chile-identity-card-number"></a>Chiles identitetskortsnummer

### <a name="format"></a>Format

sju till åtta siffror plus avgränsare en kontrollerad siffra eller bokstav

### <a name="pattern"></a>Mönster

sju till åtta siffror plus avgränsare:
- En till två siffror 
- en valfri period 
- tre siffror 
- en valfri period 
- tre siffror 
- ett streck 
- en siffra eller bokstav (inte en teckenkänslig) som är en kontrollsiffra

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_chile_id_card hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_chile_id_card hittas.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_chile_id_card hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- ratdula de identidad
- identificación
- national identification
- national identification number
- national id
- número de identificación nacional
- rol único nacional
- rol único tributario
- RUN
- RUT
- tarjeta de identificación
- Rol Unico Nacional
- Rol Unico Tributario
- RUN #
- RUT #
- nationaluniqueroleID #
- nacional identidad
- número identificación
- identidad número
- numero identificacion
- identidad numero
- Chilenska identitetsnr.
- Chilenska identitetsnummer
- Chilenska identitet #
- Unikt skatteregister
- Unik Tributary-roll
- Unik skatteroll
- Unikt Tributary-nummer
- Unique National Number
- Unique National Role
- National unique role
- Chile identity no.
- Chile-identitetsnummer
- Chile-identitet #

   
## <a name="china-resident-identity-card-prc-number"></a>Inhörande identitetskort (Folkrepubliken Kina) i Kina

### <a name="format"></a>Format

18 siffror

### <a name="pattern"></a>Mönster

18 siffror:
- Sex siffror som är en adresskod 
- Åtta siffror i formuläret YYYYMMDD, som är födelsedatumet 
- tre siffror som är en orderkod 
- en siffra som är en biffrig siffra

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_china_resident_id hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_china_resident_id hittas.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_china_resident_id hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

### <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- Insvarande identitetskort 
- Folkrepubliken Kina 
- National Identification Card 
- 身份证 
- 居民 身份证 
- 居民身份证 
- 鉴定 
- 身分證 
- 居民 身份證
- 鑑定 

   
## <a name="credit-card-number"></a>Kreditkortsnummer

### <a name="format"></a>Format

14 till 16 siffror som kan vara formaterade eller oformaterade (ddddddddddd) och som måste passera Luhn-testet.

### <a name="pattern"></a>Mönster

Komplext och robust mönster som identifierar kort från alla större varumärken över hela världen, inklusive Visa, MasterCard, Discover Card, JCB, American Express, presentkort och betalkort.

### <a name="checksum"></a>Kontrollsumma

Ja, Luhn-kontrollsumma

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_credit_card hittar innehåll som matchar mönstret.
- Något av följande är sant:
    - Ett nyckelord från Keyword_cc_verification hittas.
    - Ett nyckelord från Keyword_cc_name hittas.
    - Funktionen Func_expiration_date hittar ett datum i rätt datumformat.
- Kontrollsumman passeras.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_credit_card hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- kortverifiering
- id-nummer för kort
- cvn
- cid
- cvc2
- cvv2
- fästblock
- säkerhetskod
- säkerhetsnummer
- säkerhetsnr
- utfärdandenummer
- problemnr
- cryptogramm
- numéro de sécurité
- numero de securite
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- cod. sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- cod. seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód. segurança
- cod. seguranca
- cod. segurança
- cód. seguranca
- cód segurança
- cod seguranca
- cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- data scad
- fecha de expiracion
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- data de expiração
- data de expiracao
- data em que expira
- validade
- valor
- vencimento
- transaktion
- transaktionsnummer
- referensnummer
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- american express
- americanexpress
- americano sådd
- Visa
- mastercard
- master card
- mc
- mastercards
- master cards
- diner's Club
- diners club
- diners besser
- upptäck
- discover card
- discovercard
- discover cards
- JCB
- Brand Smart
- japansk kortbyrå
- carte blanche
- carteblanche
- kreditkort
- kopia #
- kopia#:
- utgångsdatum
- exp datum
- utgångsdatum
- date d'expiration
- date d'exp
- datum förfallodag
- bankkort
- bankkort
- kortnummer
- kortnum
- kortnummer
- kortnummer
- kortnummer
- kreditkort
- kreditkort
- kreditkort
- ccn
- kort innehavare
- kortinnehavare
- kort innehavare
- kortinnehavare
- de olika korten
- degcard
- de olika korten
- degcards
- betalkort
- betalkort
- betalkort
- betalkort
- bank kort
- bankkort
- bank kort
- bankkort
- enroute
- en route
- korttyp
- Cardmember Acct
- kortmedlemskonto
- Cardno
- Företagskort
- Företagskort
- Typ av kort
- kortkontonummer
- kortmedlemskonto
- Cardmember Acct.
- kortnr
- kortnr
- kortnummer
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kreditkarte
- karte
- karteninhaber
- karteninhabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- carta di credito
- carta credito
- n. carta
- n carta
- nr. carta
- nr carta
- numero carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- Nej. de tarjeta
- no de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta no
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número do cartão
- numero do cartão
- número do cartao
- numero do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº do cartão
- nº do cartao
- nº. do cartão
- no do cartão
- no do cartao
- Nej. do cartão
- Nej. do cartao
- クレジットカード番号
- クレジットカードナンバー
- クレジットカード＃
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード＃
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- Visaカード
- Visa カード
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード


## <a name="croatia-drivers-license-number"></a>Kroatiens körkortsnummer

### <a name="format"></a>Format

Åtta siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

åtta siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
  
- Det reguljära  `Regex_croatia_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från `Keywords_eu_driver's_license_number` eller `Keywords_croatia_eu_driver's_license_number` hittas. 

```xml
      <!-- Croatia Driver's License Number -->
      <Entity id="005b3ef1-47dd-4e68-bb02-c6db484d00f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_croatia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver är s_license_number

- vozačka dozvola
- vozačke dozvole


## <a name="croatia-identity-card-number"></a>Kroatiens identitetskortsnummer
Den här typen av känslig information ingår i den nationella identifieringstypen (EU). Det är tillgängligt som en fristående typ av känslig information.

### <a name="format"></a>Format

nio siffror

### <a name="pattern"></a>Mönster

nio siffror i följd

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_croatia_id_card hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_croatia_id_card hittas.

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj gra iana
- master master number
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- personal identification number
- porezni broj
- porezni identifikacijski broj
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #


## <a name="croatia-passport-number"></a>Kroatien passnummer

### <a name="format"></a>Format

Nio siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

nio siffror 
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_croatia_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_croatia_eu_passport_number` hittas. 
- Det reguljära `Regex_eu_passport_date1` uttrycket hittar datum i formatet DD.MM.YYYY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_croatia_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_croatia_eu_passport_number` hittas. 
    
```xml
      <!-- Croatia Passport Number -->
      <Entity id="7d7a729d-32d8-4204-8d01-d5e6a6c25581" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- br. Putovnice
- br putovnice
   
## <a name="croatia-personal-identification-oib-number"></a>Kroatiens id-nummer (OIB)

### <a name="format"></a>Format

11 siffror

### <a name="pattern"></a>Mönster

11 siffror:
- 10 siffror 
- slutsiffra är en kontrollsiffra

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_croatia_oib_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_croatia_eu_tax_file_number hittas.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_croatia_oib_number hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
      <!-- Croatia Personal Identification (OIB) Number -->
      <Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_oib_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_oib_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- majstorski broj gra iana
- master master number
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- personal identification number
- porezni broj
- porezni identifikacijski broj
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #

## <a name="cyprus-drivers-license-number"></a>Licensnummer för cyperns drivrutiner

### <a name="format"></a>Format

12 siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

12 siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_cyprus_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_cyprus_eu_driver's_license_number` hittas.

```xml
      <!-- Cyprus Driver's License Number -->
      <Entity id="356fa104-f9ac-4aff-a0e4-2e6e65ea06c4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver är s_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>Identitetskort för Cypern
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

10 siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

10 siffror 
  
### <a name="checksum"></a>Kontrollsumma

ej tillämpligt
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_cyprus_eu_national_id_card` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_cyprus_eu_national_id_card` från hittas. 
    
```xml 
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- ID-kortnummer
- Identitetskortsnummer
- kimlik karti
- national identification number
- personligt ID-nummer
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>Cypern passnummer

### <a name="format"></a>Format

en bokstav följt av 6–8 siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

en bokstav följt av sex till åtta siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_cyprus_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_cyprus_eu_passport_number` hittas. 
- Det reguljära `Regex_cyprus_eu_passport_date` uttrycket hittar datum i formatet DD/MM/YYY eller ett nyckelord från `Keywords_cyprus_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_cyprus_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_cyprus_eu_passport_number` hittas.  
    
```xml
      <!-- Cyprus Passport Number -->
      <Entity id="9193e2e8-7f8c-43c1-a274-ac40d651936f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_cyprus_eu_passport_date" />
            <Match idRef="Keywords_cyprus_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο #
- διαβατήριο
- αριθμός διαβατηρίου
- Pasaport Kimliği
- pasaport nuısı
- Pasaport no.
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- går ut
- utfärdat den


## <a name="cyprus-tax-identification-number"></a>Skatteidentifieringsnummer för Cypern
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

Åtta siffror och en bokstav i det angivna mönstret
  
### <a name="pattern"></a>Mönster

Åtta siffror och en bokstav:
  
- a "0" eller "9"
- sju siffror
- en bokstav (inte en ärendekänslig)
    
### <a name="checksum"></a>Kontrollsumma

ej tillämpligt
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_cyprus_eu_tax_file_number` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_cyprus_eu_tax_file_number` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_cyprus_eu_tax_file_number` innehåll som matchar mönstret. 
    
```xml
      <!-- Cyprus Tax Identification Number -->
      <Entity id="40e64bd9-55f3-4a09-9bd6-1db18dced9dd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- tax id
- tax identification code
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tic #
- tic
- tin-id
- tin no
- tin #
- vergi kimlik kodu
- vergi kimlik nuısı
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>Tjeckiska körkortsnummer

### <a name="format"></a>Format

Två bokstäver följt av sex siffror
  
### <a name="pattern"></a>Mönster

Åtta bokstäver och siffror:
  
- bokstaven "E" (inte den är det.
- en bokstav
- ett blanksteg (valfritt)
- sex siffror

### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_czech_republic_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_czech_republic_eu_driver's_license_number` hittas. 

```xml
      <Entity id="86b40d3b-d8ea-4c36-aab0-ef9416a6769c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver är s_license_number

- čidičskú prúkaz
- čidičské prčka upptaget
- číslo čidičského prčkazu
- čísla čidičskách prčkazí


## <a name="czech-passport-number"></a>Tjeckiska passnummer

### <a name="format"></a>Format

Åtta siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

Åtta siffror utan blanksteg eller avgränsare
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_czech_republic_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_czech_republic_eu_passport_number` hittas. 
- Det reguljära `Regex_eu_passport_date1` uttrycket hittar datum i formatet DD.MM.YYYY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_czech_republic_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_czech_republic_eu_passport_number` hittas. 
    
```xml
      <!-- Czech Republic Passport Number -->
      <Entity id="7bcd8ce8-5e92-4bbe-bc92-fa669f0369fa" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- cestovní pas
- číslo pasu
- cestovní pasu
- passeport no
- čísla pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="czech-personal-identity-number"></a>Tjeckiska personnummer

### <a name="format"></a>Format

Nio siffror med valfritt snedstreck (gammalt format) 10 siffror med valfritt snedstreck (nytt format)

### <a name="pattern"></a>Mönster

Nio siffror (gammalt format):
- Sex siffror som representerar födelsedatum
- ett valfritt snedstreck
- tre siffror

10 siffror (nytt format):
- Sex siffror som representerar födelsedatum
- ett valfritt snedstreck 
- fyra siffror där sista siffran är en bård

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:

- Funktionen för Func_czech_id_card hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_czech_id_card hittas.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:

- Funktionen Func_czech_id_card_new_format hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<!-- Czech Personal Identity Number -->
      <!-- Czech Personal Identity Number -->
      <Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_id_card" />
          <Match idRef="Keyword_czech_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.3000.000">
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Func_czech_id_card_new_format" />
          </Pattern>
        </Version>
      </Entity>
```
### <a name="keywords"></a>Nyckelord

#### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- födelsedatum
- tjeckien id
- czechidno #
- daňové číslo
- identifikační číslo
- identity no
- identitetsnummer
- identityno #
- identityno
- insurance number (försäkringsnummer)
- national identification number
- nationalnumber #
- national number
- osobní číslo
- personalidnumber #
- personligt ID-nummer
- personal identification number
- personligt nummer
- pid #
- pid
- pojištšní číslo
- rč
- janne cislo
- né číslo
- ssn
- ssn #
- personnummer
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #
- unikt ID-nummer


## <a name="denmark-drivers-license-number"></a>Danmarks körkortsnummer

### <a name="format"></a>Format

Åtta siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

åtta siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_denmark_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_denmark_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Denmark Driver's License Number -->
      <Entity id="98a95812-6203-451a-a220-d39870ebef0e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_denmark_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver är s_license_number

- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>Danmark passnummer

### <a name="format"></a>Format

Nio siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

nio siffror 
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_denmark_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_denmark_eu_passport_number` hittas. 
- Det reguljära `Regex_eu_passport_date2` uttrycket hittar datum i formatet DD MM YY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_denmark_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_denmark_eu_passport_number` hittas. 
    
```xml
      <!-- Denmark Passport Number -->
      <Entity id="25e8c47e-e6fe-4884-a211-74898f8c0196" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n°
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="denmark-personal-identification-number"></a>Danmarks personliga ID-nummer

### <a name="format"></a>Format

10 siffror som innehåller ett bindestreck

### <a name="pattern"></a>Mönster

10 siffror:
- Sex siffror i formatet DDMMYY, som är födelsedatumet 
- ett bindestreck 
- fyra siffror där den sista siffran är en bård

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Func_denmark_eu_tax_file_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_denmark_id hittas.
- Kontrollsumman passeras.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Func_denmark_eu_tax_file_number hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<!-- Denmark Personal Identification Number -->
      <!-- Denmark Personal Identification Number -->
      <Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keyword_denmark_id" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- civilt registreringssystem
- cpr
- cpr #
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- hälsokort
- hälsoförsäkringskortsnummer
- hälsoförsäkringsnummer
- identification number
- identifikationsnummer
- identifikationsnummer #
- identitetsnummer
- denkkenka uppnummer
- nationalid #
- nationalnumber #
- national number
- personalidnumber #
- personalidentityno #
- personligt ID-nummer
- personnummer
- personnummer #
- reiseichkenversicherungskartenummer
- rejsesygesikringskort
- ssn
- ssn #
- skat-ID
- skat kode
- skat nummer
- skattenummer
- personnummer
- diversehedsforsikringskort
- diversehedsforsikringsnummer
- diverseedskort
- diverseedskortnummer
- stavelse
- sygesikringkortnummer
- skattekod
- reseförsäkringskort
- uniqueidentityno #
- tax number
- skatteregistreringsnummer
- tax id
- tax identification number
- taxid #
- räknare #
- tax no
- taxno #
- räknare
- tax identification no
- tin #
- taxidno #
- taxidnumber #
- tax no #
- tin-id
- tin no
- cpr.nr
- cprnr
- cprnummer
- personnr
- personregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer


## <a name="drug-enforcement-agency-dea-number"></a>Dea-nummer

### <a name="format"></a>Format

Två bokstäver följt av sju siffror

### <a name="pattern"></a>Mönster

Mönster måste omfatta alla följande:
- en bokstav (inte den här uppsättning möjliga bokstäver) från den här uppsättningen möjliga bokstäver: abcdefghjklmnprstux, som är en registrantkod 
- en bokstav (inte fallkänslig), som är den första bokstaven i registrantens efternamn eller siffran "9"
- sju siffror, den sista är bårdsiffran

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_dea_number hittar innehåll som matchar mönstret.
- Ett nyckelord `Keyword_dea_number` från hittas
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_dea_number hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
    <!-- DEA Number -->
    <Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_dea_number" />
      </Pattern>
      <Version minEngineVersion="15.20.1207.000" maxEngineVersion="15.20.3134.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
        </Pattern>
      </Version>
      <Version minEngineVersion="15.20.3135.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
          <Match idRef="Keyword_dea_number" />
        </Pattern>
      </Version>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_dea_number"></a>Keyword_dea_number

- dea
- dea #
- efterlevnadsadministration
- tvingande agentur


## <a name="estonia-drivers-license-number"></a>Estlands körkortsnummer

### <a name="format"></a>Format

Två bokstäver följt av sex siffror
  
### <a name="pattern"></a>Mönster

Två bokstäver och sex siffror:
  
- bokstäverna "ET" (inte case-sensitive) 
- sex siffror
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_estonia_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_estonia_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Estonia Driver's License Number -->
      <Entity id="51da8171-da70-4cc1-9d65-055a59ca4f83" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_estonia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver är s_license_number

-- permis de conduire
- juubade numbrid
- junéoa-nummer
- juubauba


## <a name="estonia-personal-identification-code"></a>Estland – personidentifieringskod
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

11 siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

11 siffror:
  
- en siffra som motsvarar sex och ett sekel (udda nummer man, jämn kvinna; 1–2: 19:e talet; 3–4: 20:e talet; 5–6: 2000)
- Sex siffror som motsvarar födelsedatumet (DSMMMDD)
- Tre siffror som motsvarar ett serienummer som separerar personer som föds samma datum
- en checksiffra
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_estonia_eu_national_id_card` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_estonia_eu_national_id_card` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_estonia_eu_national_id_card` innehåll som matchar mönstret. 
    
```xml
      <!-- Estonia Personal Identification Code -->
      <Entity id="bfb26de6-dad5-4d48-ab72-4789cdd0654c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_estonia_eu_telephone_number" />
            <Match idRef="Keywords_estonia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- id-kaart
- ik
- isikkood #
- isikkood
- maksu id
- maksukohustuslase identifitseerimisnumber
- maksunumber
- national identification number
- national number
- personlig kod
- personligt ID-nummer
- personal identification code
- personal identification number
- personalidnumber #
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #


## <a name="estonia-passport-number"></a>Estland passnummer

### <a name="format"></a>Format

en bokstav följt av sju siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

en bokstav följt av sju siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_estonia_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_estonia_eu_passport_number` hittas. 
- Det reguljära `Regex_eu_passport_date1` uttrycket hittar datum i formatet DD.MM.YYYY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_estonia_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_estonia_eu_passport_number` hittas. 
    
```xml
      <!-- Estonia Passport Number -->
      <Entity id="61f7073a-509e-425b-a754-bc01bb5d5b8c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku passi number passinumbrid document number document document no dokumendi nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="eu-debit-card-number"></a>BETALKORTSNUMMER (EU)

### <a name="format"></a>Format

16 siffror

### <a name="pattern"></a>Mönster

Komplext och robust mönster

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_eu_debit_card hittar innehåll som matchar mönstret.
- Minst ett av följande stämmer:
    - Ett nyckelord från Keyword_eu_debit_card hittas.
    - Ett nyckelord från Keyword_card_terms_dict hittas.
    - Ett nyckelord från Keyword_card_security_terms_dict hittas.
    - Ett nyckelord från Keyword_card_expiration_terms_dict hittas.
    - Funktionen Func_expiration_date hittar ett datum i rätt datumformat.
- Kontrollsumman passeras.

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- kontonummer 
- kortnummer 
- kortnr 
- säkerhetsnummer 
- kopia # 

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr 
- acct num 
- acct no 
- american express 
- americanexpress 
- americano sådd 
- amex 
- bank kort 
- bank kort 
- atm kaart 
- bankkort 
- bankkort 
- atmkaart 
- atmkaarten 
- bancontact 
- bankkort 
- bankkaart 
- kort innehavare 
- kort innehavare 
- kortnum 
- kortnummer 
- kortnummer 
- korttyp 
- cardano numerico 
- kortinnehavare 
- kortinnehavare 
- kortnummer 
- kortnummer 
- carta några 
- carta credito 
- carta di credito 
- cartao de credito 
- cartao de crédito 
- cartao de debito 
- cartao de débito 
- carte bancaire 
- carte blanche 
- carte bleue 
- carte de credit 
- carte de crédit 
- carte di credito 
- carteblanche 
- cartão de credito 
- cartão de crédito 
- cartão de debito 
- cartão de débito 
- cb 
- ccn 
- de olika korten 
- de olika korten 
- degcard
- degcards 
- chekaart 
- cirrus 
- cirrus-edc-maestro 
- controlekaart 
- controlekaarten 
- kreditkort 
- kreditkort 
- kreditkort 
- kreditkort 
- debetkaart 
- debetkaarten 
- betalkort 
- betalkort 
- betalkort 
- betalkort 
- debito automatico 
- diners club 
- diners besser 
- upptäck 
- discover card 
- discover cards 
- discovercard 
- discovercards 
- débito automático
- edc 
- eigentümername 
- europeiskt bankkort 
- hoofdkaart 
- hoofdkaarten 
- in vi andra 
- japansk kortbyrå 
- japanse kaartdienst 
- jcb 
- kaart 
- kaart num 
- kaartaantal 
- kaartaantallen 
- kaarthouder 
- kaarthouder 
- karte  
- karteninhaber 
- karteninhabers
- kartennr 
- kartennummer 
- kreditkarte 
- kreditkarten-nummer 
- kreditkarteninhaber 
- kreditkarteninstitut 
- kreditkartennummer 
- kreditkartentyp 
- maestro 
- master card 
- master cards 
- mastercard 
- mastercards 
- mc 
- cash 
- n carta 
- carta 
- no de tarjeta 
- no do cartao 
- no do cartão 
- Nej. de tarjeta 
- Nej. do cartao 
- Nej. do cartão 
- nr carta 
- nr. carta 
- numeri di scheda 
- numero carta 
- numero de cartao 
- numero de carte 
- numero de cartão 
- numero de tarjeta
- numero della carta 
- numero di carta 
- numero di scheda 
- numero do cartao 
- numero do cartão 
- numéro de carte 
- nº carta 
- nº de carte 
- nº de la carte 
- nº de tarjeta 
- nº do cartao 
- nº do cartão 
- nº. do cartão 
- número de cartao 
- número de cartão 
- número de tarjeta 
- número do cartao 
- scheda dell'assegno 
- scheda dell'atmosfera 
- scheda dell'atmosfera 
- scheda della banca 
- scheda di controllo 
- scheda di debito 
- scheda matrice 
- schede dell'atmosfera 
- schede di controllo 
- schede di debito 
- schede matrici 
- scoprono la scheda 
- scoprono le schede 
- solo 
- supporti di scheda 
- supporto di scheda 
- växla 
- tarjeta atm 
- tarjeta credito 
- tarjeta de atm 
- tarjeta de credito 
- tarjeta de debito 
- tarjeta debito 
- tarjeta no
- tarjetahabiente 
- tipo della scheda 
- ufficio giapponese della 
- scheda 
- v pay 
- v-pay 
- visa 
- visa plus 
- visa electron 
- visto 
- var och en 
- vpay   

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- id-nummer för kort
- kortverifiering 
- cardi la verifica 
- cid 
- cod seg 
- cod seguranca 
- cod segurança 
- cod sicurezza 
- cod. seg 
- cod. seguranca 
- cod. segurança 
- cod. sicurezza 
- codice di sicurezza 
- codice di verifica 
- codigo 
- codigo de seguranca 
- codigo de segurança 
- crittogramma 
- cryptogram 
- cryptogramm 
- cv2 
- cvc 
- cvc2 
- cvn 
- cvv 
- cvv2 
- cód seguranca 
- cód segurança 
- cód. seguranca 
- cód. segurança 
- código 
- código de seguranca 
- código de segurança 
- de kaart controle 
- geeft nr uit 
- problemnr 
- utfärdandenummer 
- kaartidentificatienummer 
- kreditkartenprufnummer 
- kreditkartenprüfnummer 
- kwestieaantal 
- Nej. dell'edizione 
- Nej. di sicurezza 
- numero de securite 
- numero de verificacao 
- numero dell'edizione 
- numero di identificazione della 
- scheda 
- numero di sicurezza 
- numero van veiligheid 
- numéro de sécurité 
- nº autorizzazione 
- número de verificação 
- perno il blocco 
- fästblock 
- prufziffer 
- prüfziffer 
- säkerhetskod 
- säkerhetsnr 
- säkerhetsnummer 
- sicherheits kode 
- sicherheitscode 
- sicherheitsnummer 
- speldblok 
- veiligheid nr 
- veiligheidsaantal 
- veiligheidscode 
- veiligheidsnummer 
- verfalldatum 

#### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

- ablauf 
- data de expiracao 
- data de expiração 
- data del exp 
- data di exp 
- data di scadenza 
- data em que expira 
- data scad 
- data scadenza 
- date de validité 
- datum afloop 
- datum van exp 
- de afloop 
- espira 
- espira 
- exp datum 
- exp datum 
- utgång 
- utgå 
- förfaller 
- utgång 
- fecha de expiracion 
- fecha de venc 
- gultig bis 
- gultigkeitsdatum 
- gültig bis 
- gültigkeitsdatum 
- la scadenza 
- scadenza 
- valable 
- validade 
- valido hasta 
- valor 
- venc 
- vencimento 
- vencimiento 
- verloopt 
- vervaldag 
- vervaldatum 
- vto 
- válido hasta 


## <a name="eu-drivers-license-number"></a>EU:s körkortsnummer

De här enheterna finns i EU:s licensnummer och är typer av känslig information.

- [Österrike](#austria-drivers-license-number) 
- [Belgien](#belgium-drivers-license-number)
- [Bulgarien](#bulgaria-drivers-license-number)
- [Kroatien](#croatia-drivers-license-number)
- [Cypern](#cyprus-drivers-license-number)
- [Czech](#czech-drivers-license-number)
- [Danmark](#denmark-drivers-license-number)
- [Estland](#estonia-drivers-license-number)
- [Finland](#finland-drivers-license-number)
- [Frankrike](#france-drivers-license-number) 
- [Tyskland](#germany-drivers-license-number)
- [Grekland](#greece-drivers-license-number)
- [Ungern](#hungary-drivers-license-number)
- [Irland](#ireland-drivers-license-number)
- [Italien](#italy-drivers-license-number)
- [Lettland](#latvia-drivers-license-number)
- [Litauen](#lithuania-drivers-license-number)
- [Luxemburg](#luxemburg-drivers-license-number)
- [Malta](#malta-drivers-license-number)
- [Nederländerna](#netherlands-drivers-license-number)
- [Polen](#poland-drivers-license-number) 
- [Portugal](#portugal-drivers-license-number)
- [Rumänien](#romania-drivers-license-number)
- [Slovakien](#slovakia-drivers-license-number)
- [Slovenien](#slovenia-drivers-license-number)
- [Spanien](#spain-drivers-license-number)
- [Sverige](#sweden-drivers-license-number)
- [Storbritannien](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>NATIONELLA IDENTIFIKATIONSNUMMER (EU)

Enheterna finns i EU:s National Identification Number och är typer av känslig information.

- [Österrike](#austria-identity-card)
- [Belgien](#belgium-national-number)
- [Bulgarien](#bulgaria-uniform-civil-number)
- [Kroatien](#croatia-identity-card-number)
- [Cypern](#cyprus-identity-card)
- [Czech](#czech-personal-identity-number)
- [Danmark](#denmark-personal-identification-number)
- [Estland](#estonia-personal-identification-code)
- [Finland](#finland-national-id)
- [Frankrike](#france-national-id-card-cni)
- [Tyskland](#germany-identity-card-number)
- [Grekland](#greece-national-id-card)
- [Ungern](#hungary-personal-identification-number)
- [Irland](#ireland-personal-public-service-pps-number)
- [Italien](#italy-fiscal-code)
- [Lettland](#latvia-personal-code)
- [Litauen](#lithuania-personal-code)
- [Luxemburg](#luxemburg-national-identification-number-natural-persons)
- [Malta](#malta-identity-card-number)
- [Nederländerna](#netherlands-citizens-service-bsn-number)
- [Polen](#poland-national-id-pesel)
- [Portugal](#portugal-citizen-card-number)
- [Rumänien](#romania-personal-numeric-code-cnp)
- [Slovakien](#slovakia-personal-number)
- [Slovenien](#slovenia-unique-master-citizen-number)
- [Spanien](#spain-dni)
- [Storbritannien](#uk-national-insurance-number-nino)                                        


## <a name="eu-passport-number"></a>EU-passnummer 

Dessa enheter finns i EU:s passnummer och är typer av känslig information. De här enheterna finns i EU:s passnummerpaket.

- [Österrike](#austria-passport-number)
- [Belgien](#belgium-passport-number)
- [Bulgarien](#bulgaria-passport-number)
- [Kroatien](#croatia-passport-number)
- [Cypern](#cyprus-passport-number)
- [Czech](#czech-passport-number)
- [Danmark](#denmark-passport-number)
- [Estland](#estonia-passport-number)
- [Finland](#finland-passport-number)
- [Frankrike](#france-passport-number)
- [Tyskland](#germany-passport-number)
- [Grekland](#greece-passport-number)
- [Ungern](#hungary-passport-number)
- [Irland](#ireland-passport-number)
- [Italien](#italy-passport-number)
- [Lettland](#latvia-passport-number)
- [Litauen](#lithuania-passport-number)
- [Luxemburg](#luxemburg-passport-number)
- [Malta](#malta-passport-number)
- [Nederländerna](#netherlands-passport-number)
- [Polen](#poland-passport-number)
- [Portugal](#portugal-passport-number)
- [Rumänien](#romania-passport-number)
- [Slovakien](#slovakia-passport-number)
- [Slovenien](#slovenia-passport-number)
- [Spanien](#spain-passport-number)
- [Sverige](#sweden-passport-number)
- [Storbritannien](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>EU:s personnummer eller motsvarande identifikation

Dessa enheter i EU:s personnummer eller motsvarande identifiering och är typer av känslig information.

- [Österrike](#austria-social-security-number)
- [Belgien](#belgium-national-number)
- [Kroatien](#croatia-personal-identification-oib-number)
- [Czech](#czech-personal-identity-number)
- [Danmark](#denmark-personal-identification-number)
- [Finland](#finland-national-id)
- [Frankrike](#france-social-security-number-insee)
- [Tyskland](#germany-identity-card-number)
- [Grekland](#greece-national-id-card)
- [Ungern](#hungary-social-security-number-taj)
- [Portugal](#portugal-citizen-card-number)
- [Spanien](#spain-social-security-number-ssn)
- [Sverige](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>EU:s skatteidentifieringsnummer

Enheterna finns i typen Skatteidentifieringsnummer för känslig information inom EU.

- [Österrike](#austria-tax-identification-number)
- [Belgien](#belgium-national-number)
- [Bulgarien](#bulgaria-uniform-civil-number)
- [Kroatien](#croatia-identity-card-number)
- [Cypern](#cyprus-tax-identification-number)
- [Czech](#czech-personal-identity-number)
- [Danmark](#denmark-personal-identification-number)
- [Estland](#estonia-personal-identification-code)
- [Finland](#finland-national-id)
- [Frankrike](#france-tax-identification-number)
- [Tyskland](#germany-tax-identification-number)
- [Grekland](#greece-tax-identification-number)
- [Ungern](#hungary-tax-identification-number)
- [Irland](#ireland-personal-public-service-pps-number)
- [Italien](#italy-fiscal-code)
- [Lettland](#latvia-personal-code)
- [Litauen](#lithuania-personal-code)
- [Luxemburg](#luxemburg-national-identification-number-non-natural-persons)
- [Malta](#malta-tax-identification-number)
- [Nederländerna](#netherlands-tax-identification-number)
- [Polen](#poland-tax-identification-number)
- [Portugal](#portugal-tax-identification-number)
- [Rumänien](#romania-personal-numeric-code-cnp)
- [Slovakien](#slovakia-personal-number)
- [Slovenien](#slovenia-tax-identification-number)
- [Spanien](#spain-tax-identification-number)
- [Sverige](#sweden-tax-identification-number)
- [Storbritannien](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>Finlands körkortsnummer

### <a name="format"></a>Format

10 siffror som innehåller ett bindestreck
  
### <a name="pattern"></a>Mönster

10 siffror som innehåller ett bindestreck:
  
- sex siffror 
- ett bindestreck
- tre siffror 
- en siffra eller bokstav
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_finland_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_finland_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Finland Driver's License Number -->
      <Entity id="bb3b27a3-79bd-4ac4-81a7-f9fca3c7d1a7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_finland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver är s_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- kuljettaja lic.
- körkort
- körkortnummer
- lic.
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>Finlands hälsoförsäkringsnummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

20-siffrigt nummer

### <a name="pattern"></a>Mönster

20-siffrigt nummer:

- 10 siffror – 8024680246
- Ett valfritt blanksteg eller bindestreck
- 10 siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Regex-Regex_Finland_European_Health_Insurance_Number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_Finland_European_Health_Insurance_Number hittas.

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Nyckelord

#### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ehic #
- ehic
- finlandehicnumber #
- finska denskort
- hälsokort
- hälsoförsäkringskort
- hälsoförsäkringsnummer
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- den här nummern
- denskort
- suomen sairausvakuutuskortti
- etteveyskortti


## <a name="finland-national-id"></a>Finlands national-ID

### <a name="format"></a>Format

Sex siffror plus ett tecken som anger ett sekel plus tre siffror plus en bård

### <a name="pattern"></a>Mönster

Mönster måste omfatta alla följande:
- Sex siffror i formatet DDMMYY, som är ett födelsedatum 
- talmarkör (antingen '-', '+' eller 'a') 
- tresiffrigt id-nummer 
- En siffra eller bokstav (tecken insensitiv) som är en kontrollsiffra

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- funktionen som Func_finnish_national_id hittar innehåll som matchar mönstret
- ett nyckelord från Keyword_finnish_national_id hittas
- kontrollsumma passeras

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- funktionen som Func_finnish_national_id hittar innehåll som matchar mönstret
- kontrollsumma passeras

```xml
      <!-- Finnish National ID-->
      <Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finnish_national_id" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

- ainutlaatuinen henkilöktaintainen tunnus
- henkilöktainen tunnus
- henkilötunaki
- henkilötunningsnumero #
- henkilötunningsnumero
- hetu
- id no
- id-nummer
- identification number
- identiteette numero
- identitetsnummer
- idnumber
- kansallinen henkilötunaki
- kansallisen henkilökortin
- national id card
- national id no.
- personligt ID
- personlig identitetskod
- personalidnumber #
- personbeteckning
- personnummer
- personnummer
- sosiaaliturvatunano
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunano


## <a name="finland-passport-number"></a>Finland passnummer

Den här typen av känslig information är tillgänglig i typen KÄNSLIG informationstyp EU Passport Number och är tillgänglig som en fristående typ av känslig information.

### <a name="format"></a>Format
kombination av nio bokstäver och siffror

### <a name="pattern"></a>Mönster
kombination av nio bokstäver och siffror:
- Två bokstäver (inte versaler och teckenkänsliga) 
- sju siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära `Regex_finland_passport_number` uttrycket hittar innehåll som matchar mönstret.
- Ett nyckelord från `Keywords_eu_passport_number` eller `Keyword_finland_passport_number` hittas.
- Det reguljära `Regex_eu_passport_date1` uttrycket hittar datum i formatet DD.MM.YYYY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära `Regex_finland_passport_number` uttrycket hittar innehåll som matchar mönstret.
- Ett nyckelord från `Keywords_eu_passport_number` eller `Keyword_finland_passport_number` hittas.

```xml
      <!-- Finland Passport Number -->
      <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomaénen passi
- passin numero
- passin numero. #
- passin numero #
- passin numero.
- passi #
- passi-nummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum

## <a name="france-drivers-license-number"></a>Frankrikes körkortsnummer

Den här typen av känslig information är tillgänglig i EU-drivrutinens licensnummerkänsliga informationstyp och är tillgänglig som en fristående typ av känslig information.

### <a name="format"></a>Format

12 siffror

### <a name="pattern"></a>Mönster

12 siffror med validering för rabatt på liknande mönster som franska telefonnummer

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- funktionen Func_french_drivers_license hittar innehåll som matchar mönstret.
- ett nyckelord från Keyword_french_drivers_license hittas.

```xml
    <!-- France Driver's License Number -->
    <Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Match idRef="Keyword_french_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer
- permis de conduire
- licensnummer
- licensnummer
- licensnummer
- licensnummer
- numéros de licence


## <a name="france-health-insurance-number"></a>Frankrikes hälsoförsäkringsnummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

21-siffrigt nummer

### <a name="pattern"></a>Mönster

21-siffrigt nummer:

- 10 siffror
- ett valfritt blanksteg
- 10 siffror
- ett valfritt blanksteg
- en siffra


### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- regex-Regex_France_Health_Insurance_Number hittar innehåll som matchar mönstret.
- ett nyckelord från Keyword_France_Health_Insurance_Number hittas.

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Nyckelord

#### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- insurance card
- carte vitale
- carte d'assuré social


## <a name="france-national-id-card-cni"></a>France national id card (CNI)

### <a name="format"></a>Format

12 siffror

### <a name="pattern"></a>Mönster

12 siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_france_cni hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_france_eu_national_id_card hittas.

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- kortnummer
- carte nationale d'identité
- carte nationale d'idenite no
- cni #
- cni
- compte bancaire
- national identification number
- national identity
- nationalidno #
- numéro d'assurance malakit
- numéro de carte vitale

   
## <a name="france-passport-number"></a>Frankrike passnummer
Den här typen av känslig information är tillgänglig i typen Känslig information av EU-passnummer. Det är tillgängligt som en fristående typ av känslig information.

### <a name="format"></a>Format

Nio siffror och bokstäver

### <a name="pattern"></a>Mönster

Nio siffror och bokstäver:
- två siffror 
- Två bokstäver (inte versaler och teckenkänsliga) 
- fem siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar `Func_fr_passport` innehåll som matchar mönstret.
- Ett nyckelord från `Keywords_eu_passport_number` eller `Keywords_france_eu_passport_number` hittas.
- Det reguljära `Regex_eu_passport_date3` uttrycket hittar datum i formatet DD MM YYYY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar `Func_fr_passport` innehåll som matchar mönstret.
- Ett nyckelord från `Keywords_eu_passport_number` eller `Keywords_france_eu_passport_number` hittas.


```xml
    <!-- France Passport Number -->
    <Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_france_eu_passport_number"></a>Keywords_france_eu_passport_number

- numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passeport français
- passeport livre
- passeport carte
- numéro passeport
- passeport n°
- n° du passeport
- n° passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="france-social-security-number-insee"></a>Frankrikes personnummer (INSEE)

### <a name="format"></a>Format

15 siffror

### <a name="pattern"></a>Mönster

Måste matcha ett av två mönster:
- 13 siffror följt av ett blanksteg följt av två siffror<br/>
eller
- 15 siffror i följd

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar `Func_french_insee` innehåll som matchar mönstret.
- Ett nyckelord från Keyword_fr_insee hittas.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_french_insee eller Func_fr_insee hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
    <!-- France INSEE -->
    <Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Keyword_fr_insee" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- code sécu
- d'identité nationale
- insee
- fssn #
- le numéro d'identification nationale
- le code de la sécurité sociale
- national id
- national identification
- no d'identité
- Nej. d'identité
- numéro d'assurance
- numéro d'identité
- numero d'identite
- numéro de sécu
- numéro de sécurité sociale
- no d'identite
- Nej. d'identite
- ssn
- ssn #
- sécurité sociale
- securité sociale
- securite sociale
- socialsecuritynumber
- personnummer
- social security code
- social insurance number


## <a name="france-tax-identification-number"></a>Frankrikes skattenummer

### <a name="format"></a>Format

13 siffror
  
### <a name="pattern"></a>Mönster

13 siffror
  
- En siffra som måste vara 0, 1, 2 eller 3
- En siffra
- Ett blanksteg (valfritt)
- Två siffror 
- Ett blanksteg (valfritt)
- Tre siffror 
- Ett blanksteg (valfritt)
- Tre siffror 
- Ett blanksteg (valfritt)
- Tre kontrollsiffror 

  
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_france_eu_tax_file_number` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_france_eu_tax_file_number` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_france_eu_tax_file_number` innehåll som matchar mönstret. 
    
```xml
      <!-- France Tax Identification Number (numéro SPI.) -->
      <Entity id="ed59e77e-171d-442c-9ec1-88e2ebcb5b0a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_france_eu_telephone_number" />
            <Match idRef="Keywords_france_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- numéro d'identification fiscale
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #


## <a name="france-value-added-tax-number"></a>Värdeskattenummer för Frankrike
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

Alfanumeriskt mönster med 13 tecken

### <a name="pattern"></a>Mönster

13 tecken för alfanumeriskt mönster:

- två bokstäver – FR (teckenkänsligt)
- Ett valfritt blanksteg eller bindestreck
- två bokstäver eller siffror
- Ett valfritt blanksteg, punkt, bindestreck eller kommatecken
- tre siffror
- Ett valfritt blanksteg, punkt, bindestreck eller kommatecken
- tre siffror
- Ett valfritt blanksteg, punkt, bindestreck eller kommatecken
- tre siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_france_value_added_tax_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_france_value_added_tax_number hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_france_value_added_tax_number hittar innehåll som matchar mönstret.

```xml
      <!-- France Value Added Tax Number -->
      <Entity id="949121e6-ad9f-4379-8731-710342baea78" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_value_added_tax_number" />
          <Match idRef="Keywords_france_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Nyckelord

#### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- momsregistreringsnummer
- momsnr
- moms #
- moms
- siren identification no numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n° tva
- numéro de tva
- numéro d'identification siren


## <a name="germany-drivers-license-number"></a>Tysklands körkortsnummer

Den här typen av känslig information ingår i EU:s typ av licensnummer för känslig information. Det är tillgängligt som en fristående typ av känslig information.

### <a name="format"></a>Format

kombination av 11 siffror och bokstäver

### <a name="pattern"></a>Mönster

11 siffror och bokstäver (inte teckenkänsliga):
- en siffra eller bokstav 
- två siffror 
- Sex siffror eller bokstäver 
- en siffra 
- en siffra eller bokstav

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_german_drivers_license hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_german_drivers_license_number hittas.
- Kontrollsumman passeras.

```xml
    <!-- German Driver's License Number -->
    <Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Match idRef="Keyword_german_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- ausstelelssdatum
- ausstelellsort
- ausstellende beellede
- ausstellende behorde
- ausstellende behoerde
- füscheschein
- fuscheschein
- fueschein
- füscheinnummer
- fuscheinnummer
- fuescheinnummer
- füscheschein- 
- fuschein- 
- fueschein- 
- füscheinnummernr
- fuscheinnummernr
- fuescheinnummernr
- füscheinnummerklasse
- fuscheinnummerklasse
- fuescheinnummerklasse
- nr-füscheschein
- nr-fuschein
- nr-fueschein
- no-füscheschein
- no-fuscheschein
- no-fuescheschein
- n-füscheschein
- n-fuschein
- n-fueschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dlno


## <a name="germany-identity-card-number"></a>Identitetskortsnummer i Tyskland

### <a name="format"></a>Format

sedan 1 november 2010: nio bokstäver och siffror

från 1 april 1987 till 31 oktober 2010: 10 siffror

### <a name="pattern"></a>Mönster

sedan 1 november 2010:
- en bokstav (inte en ärendekänslig) 
- åtta siffror

från den 1 april 1987 till den 31 oktober 2010:
- 10 siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_germany_id_card hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_germany_id_card hittas.

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- aus denisys
- gpid
- identification
- identifikation
- identifizierungsnummer
- identitetskort
- identitetsnummer
- id-nummer
- personligt ID
- personalaus en
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>Tyskland passnummer

Den här typen av känslig information ingår i typen Känslig information i EU Passport Number och är tillgänglig som en fristående typ av känslig information.

### <a name="format"></a>Format

10 siffror eller bokstäver

### <a name="pattern"></a>Mönster

Mönster måste omfatta alla följande:
- det första tecknet är en siffra eller en bokstav från denna uppsättning (C, F, G, H, J, K) 
- tre siffror 
- Fem siffror eller bokstäver från denna uppsättning (C, -H, J-N, P, R, T, V-Z) 
- en siffra

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_german_passport hittar innehåll som matchar mönstret.
- Ett nyckelord från `Keyword_german_passport` eller `Keywords_eu_passport_number_common` hittas.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_german_passport_data hittar innehåll som matchar mönstret.
- Ett nyckelord från `Keyword_german_passport` eller `Keywords_eu_passport_number_common` hittas.
- Kontrollsumman passeras.

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepasse
- reisepassnummer
- No-Reisepass 
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisessesse
- passeport no.
- passeport no

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer


## <a name="germany-tax-identification-number"></a>Tysklands skatteidentifieringsnummer

### <a name="format"></a>Format

11 siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

11 siffror
  
- Två siffror 
- Ett valfritt blanksteg
- Tre siffror 
- Ett valfritt blanksteg
- Tre siffror 
- Ett valfritt blanksteg
- Två siffror
- en checksiffra
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_germany_eu_tax_file_number` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_germany_eu_tax_file_number` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_germany_eu_tax_file_number` innehåll som matchar mönstret. 
    
```xml
      <!-- Germany Tax Identification Number -->
      <Entity id="43316a89-9880-40cf-b980-04bc7eefcec5" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

- identifikationsnummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #
- zinn #
- zinn
- zinnnummer


## <a name="germany-value-added-tax-number"></a>Momsnummer för Tyskland
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

Alfanumeriskt mönster med 11 tecken

### <a name="pattern"></a>Mönster

Alfanumeriskt mönster med 11 tecken:

- a bokstaven D eller d
- ett bokstaven E eller e
- ett valfritt blanksteg
- tre siffror
- Ett valfritt blanksteg eller kommatecken
- tre siffror
- Ett valfritt blanksteg eller kommatecken
- tre siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_germany_value_added_tax_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_germany_value_added_tax_number hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_germany_value_added_tax_number hittar innehåll som matchar mönstret.

```xml
      <!-- Germany Value Added Tax Number -->
      <Entity id="db177eb2-8811-4842-bffc-128c14aa219f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
          <Match idRef="Keywords_germany_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Nyckelord

#### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- momsregistreringsnummer
- momsnr
- moms #
- vat# mehrwertsteuer
- han/hon
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>Greklands körkortsnummer

Den här typen av känslig information ingår i EU-drivrutinens typ av licensnummerkänslig information och är tillgänglig som en fristående typ av känslig information.

### <a name="format"></a>Format

Nio siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

nio siffror 
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_greece_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_greece_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Greece Driver's License Number -->
      <Entity id="7a2200b5-aacf-4e3c-ab36-136d3e68b7da" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_greece_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver är s_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


## <a name="greece-national-id-card"></a>Greklands nationella ID-kort

### <a name="format"></a>Format

Kombination av 7–8 bokstäver och siffror plus ett streck

### <a name="pattern"></a>Mönster

Sju bokstäver och siffror (gammalt format):
- En bokstav (valfri bokstav i det grekiska alfabetet) 
- Ett streck 
- Sex siffror

Åtta bokstäver och siffror (nytt format):
- Två bokstäver med versaler både i det grekiska och det latinska alfabetet (ABEZHIKMNOPTYX) 
- Ett streck 
- Sex siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_greece_id_card hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_greece_id_card hittas.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_greece_id_card hittar innehåll som matchar mönstret.

```xml
      <!-- Greece National ID Card -->
      <Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_id_card" />
          <Match idRef="Keyword_greece_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- grekiska id
- grekiska national id
- grekiska personliga ID-kort
- grekiska police id
- identitetskort
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>Greklands passnummer

### <a name="format"></a>Format

Två bokstäver följt av sju siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

Två bokstäver följt av sju siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_greece_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_greece_eu_passport_number` hittas. 
- Det reguljära uttrycket hittar datum i `Regex_greece_eu_passport_date` formatet DD MMM YY (Exempel - 28 augusti 19) eller ett `Keywords_greece_eu_passport_date` nyckelord från hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_greece_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_greece_eu_passport_number` hittas. 
    
```xml
      <!-- Greece Passport Number -->
      <Entity id="7e65eb47-cdf9-4f52-8f90-2a27d5ee67e3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_greece_eu_passport_date" />
            <Match idRef="Keywords_greece_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a>Greklands social securitynummer (AMKA)
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

Elva siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

- 6 siffror som födelsedatum YYMMDD
- 4 siffror
- en kontrollsiffra
  
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_greece_eu_ssn` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_greece_eu_ssn_or_equivalent` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_greece_eu_ssn` innehåll som matchar mönstret. 

```xml
      <!-- Greece Social Security Number (AMKA) -->
      <Entity id="e39b03f4-50ea-41ae-af7a-a4b9539596ad" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_greece_eu_ssn" />
          <Match idRef="Keywords_greece_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_greece_eu_ssn" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_greece_eu_ssn_or_equivalent"></a>Keywords_greece_eu_ssn_or_equivalent

- ssn
- ssn #
- social security no
- socialsecurityno #
- personnummer
- amka
- e.Kr.m.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>Greklands skatteidentifieringsnummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

Nio siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

Nio siffror
  
### <a name="checksum"></a>Kontrollsumma

Ej tillämpligt
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
  
- Det reguljära  `Regex_greece_eu_tax_file_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_greece_eu_tax_file_number` från hittas. 
    
```xml
      <!-- Greek Tax Identification Number -->
      <Entity id="15a54a5a-53d4-4080-ad43-a2a4fe1d3bf7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- afm #
- afm
- aμ|aμ αμμμμμì ì μ
- aμ
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- skatteregisternr
- skatteregisternummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- taxregistryno #
- tin-id
- tin no
- tin #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>Hongkong identitetskort (HKID) nummer

### <a name="format"></a>Format

Kombination av 8–9 bokstäver och siffror samt valfria parenteser runt det sista tecknet

### <a name="pattern"></a>Mönster

Kombination av 8–9 bokstäver:
- 1–2 bokstäver (inte teckenkänsliga) 
- Sex siffror 
- Det sista tecknet (valfri siffra eller bokstaven A), som är en kontrollsiffra och som kan omges av parenteser.

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_hong_kong_id_card hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_hong_kong_id_card hittas.
- Kontrollsumman passeras.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_hong_kong_id_card hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- Hong Kong-identitetskort
- HKIDC
- id card
- identitetskort
- hk-identitetskort
- hong kong id
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証

   
## <a name="hungary-drivers-license-number"></a>Ungerns körkortsnummer

### <a name="format"></a>Format

Två bokstäver följt av sex siffror
  
### <a name="pattern"></a>Mönster

Två bokstäver och sex siffror:
  
- Två bokstäver (inte versaler och teckenkänsliga) 
- Sex siffror
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
  
- Det reguljära  `Regex_hungary_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_hungary_eu_driver's_license_number` hittas. 
    
```xml
      <Entity id="9d31c46b-6e6b-444c-aeb1-6dd7e604bb24" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_hungary_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver är s_license_number

- vezetoi engedely
- vezetõi engedély
- vezetõi engedélyek


## <a name="hungary-personal-identification-number"></a>Ungerns personliga ID-nummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

11 siffror
  
### <a name="pattern"></a>Mönster

11 siffror:
  
- En siffra som motsvarar kön (1-man, 2-kvinna, andra siffror är också möjliga för människor som föddes före 1900 eller för att människor med dubbel kön) 
- Sex siffror som motsvarar födelsedatum (AMMDD)
- Tre siffror som motsvarar ett serienummer
- En kontrollsiffra
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
  
- Funktionen hittar  `Func_hungary_eu_national_id_card` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_hungary_eu_national_id_card` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
  
- Funktionen hittar  `Func_hungary_eu_national_id_card` innehåll som matchar mönstret. 
    
```xml
      <!-- Hungary Personal Identification Number -->
      <Entity id="7b5cc218-7046-47d9-80c9-f325b50896ca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- id-nummer
- identification number
- sz ig
- sz. ig.
- sz.ig.
- személyazonosító igamévány
- személyi igaávány


## <a name="hungary-passport-number"></a>Ungern passnummer

### <a name="format"></a>Format

Två bokstäver följt av sex eller sju siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

Två bokstäver följt av sex eller sju siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_hungary_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_hungary_eu_passport_number` hittas. 
- Det reguljära uttrycket hittar datum i `Regex_hungary_eu_passport_date` formatet DD MMM/MMM YY (Exempel - 01 MÁR/MAR 12) eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_hungary_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_hungary_eu_passport_number` hittas. 
    
```xml
      <!-- Hungary Passport Number -->
      <Entity id="5b483910-9aa7-4c99-9917-f4001464bda7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_hungary_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útleúl száma
- Útlevelek száma
- útleúl szám

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="hungary-social-security-number-taj"></a>Ungerns social security number (TAJ)

### <a name="format"></a>Format

Nio siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

Nio siffror
  
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
  
- Funktionen hittar  `Func_hungary_eu_ssn_or_equivalent` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_hungary_eu_ssn_or_equivalent` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
  
- Funktionen hittar  `Func_hungary_eu_ssn_or_equivalent` innehåll som matchar mönstret. 
    
```xml
      <!-- Hungarian Social Security Number (TAJ) -->
      <Entity id="0de78315-9537-47f5-95ab-b3e77eba3993" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- ungerska personnummer
- personnummer
- socialsecuritynumber #
- hssn #
- socialsecuritynno
- hssn
- tad
- tad #
- ssn
- ssn #
- social security no
- áfa
- közösségi adószám
- általádiagnos forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>Ungerns skatteidentifieringsnummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

10 siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

10 siffror:
  
- En siffra som måste vara "8" 
- Åtta siffror
- En kontrollsiffra
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
  
- Funktionen hittar  `Func_hungary_eu_tax_file_number` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_hungary_eu_tax_file_number` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
  
- Funktionen hittar  `Func_hungary_eu_tax_file_number` innehåll som matchar mönstret. 
    
```xml
      <!-- Hungary Tax Identification Number -->
      <Entity id="ede42eb4-59d9-49eb-9603-d7853fbda91d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
- adószám
- ungerska tin
- hungatiantin #
- skattemyndigheten nej
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #
- momsregistreringsnummer


## <a name="hungary-value-added-tax-number"></a>Nummer för moms i Ungern
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

10 tecken för alfanumeriskt mönster

### <a name="pattern"></a>Mönster

10 tecken för alfanumeriskt mönster:

- två bokstäver – HU eller hu
- valfritt blanksteg
- åtta siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:

- Funktionen Func_hungarian_value_added_tax_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_hungarian_value_added_tax_number hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:

- Funktionen Func_hungarian_value_added_tax_number hittar innehåll som matchar mönstret.

```xml
      <!-- Hungarian Value Added Tax Number -->
      <Entity id="976349a0-683b-477a-90f8-ff0a220d5592" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
          <Match idRef="Keywords_hungarian_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- moms
- momsnummer
- moms #
- vatno #
- ungerskavatno #
- tax no.
- value added tax áfa
- közösségi adószám
- általádiagnos forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a>Indiens permanenta kontonummer (PAN)

### <a name="format"></a>Format

10 bokstäver eller siffror

### <a name="pattern"></a>Mönster

10 bokstäver eller siffror:
- Tre bokstäver (inte teckenkänsliga) 
- En bokstav i C, P, H, F, A, T, B, L, J, G (inte ärendekänsligt)
- En bokstav
- Fyra siffror 
- En bokstav med en alfabetisk kontrollsiffra

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_india_permanent_account_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_india_permanent_account_number hittas.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_india_permanent_account_number hittar innehåll som matchar mönstret.


```xml
      <!-- India Permanent Account Number -->
      <Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_india_permanent_account_number" />
          <Match idRef="Keyword_india_permanent_account_number" />
        </Pattern>
        <Version minEngineVersion="15.20.3520.000">
          <Pattern confidenceLevel="65">
            <IdMatch idRef="Regex_india_permanent_account_number" />
          </Pattern>
        </Version>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent kontonummer 
- PAN 
   
## <a name="india-unique-identification-aadhaar-number"></a>Indiens unika ID-nummer (Aadhaar)

### <a name="format"></a>Format

12 siffror som innehåller valfria blanksteg eller streck

### <a name="pattern"></a>Mönster

12 siffror:
- En siffra som inte är 0 eller 1
- Tre siffror 
- Ett blanksteg eller streck (valfritt) 
- Fyra siffror 
- Ett blanksteg eller streck (valfritt) 
- Den sista siffran, som är kontrollsiffran

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_india_aadhaar hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_india_aadhar hittas.
- Kontrollsumman passeras.
- 
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:

- Funktionen för Func_india_aadhaar hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>Nyckelord
   
#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- aadhaar
- aadhar
- aadhar #
- uid
- आधार
- uidai
   
## <a name="indonesia-identity-card-ktp-number"></a>Indonesia Identity Card-nummer (KTP)

### <a name="format"></a>Format

16 siffror med valfria punkter

### <a name="pattern"></a>Mönster

16 siffror:
- Tvåsiffrig provinskod 
- En punkt (valfritt) 
- Tvåsiffrig regency eller ortkod 
- Tvåsiffrig underpriskod 
- En punkt (valfritt) 
- Sex siffror i formatet DDMMYY, som är födelsedatumet 
- En punkt (valfritt) 
- Fyra siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:

- Det reguljära uttrycket Regex_indonesia_id_card hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_indonesia_id_card hittas.

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
</Entity>
```

### <a name="keywords"></a>Nyckelord
   
#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## <a name="international-banking-account-number-iban"></a>Nummer för internationella banktjänster (IBAN)

### <a name="format"></a>Format

Landskod (två bokstäver) plus kontrollera siffror (två siffror) plus bban-nummer (upp till 30 tecken)

### <a name="pattern"></a>Mönster

Mönster måste omfatta alla följande:

- Landskod med två bokstäver
- Två kontrollsiffror (följt av ett valfritt blanksteg) 
- 1–7 grupper med fyra bokstäver eller siffror (kan avgränsas med blanksteg)
- 1–3 bokstäver eller siffror

Formatet skiljer sig åt mellan olika länder. IBAN-typen för känslig information omfattar dessa 60 länder:

ad, ae, al, at, az, ba, be, bg, ch, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mt, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk , sm, tn, tr, vg

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:

- Funktionen Func_iban hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

Inga

   
## <a name="international-classification-of-diseases-icd-10-cm"></a>Internationell klassificering av den internationella klassificeringen (ICD-10-CM)

### <a name="format"></a>Format

Ordlista

### <a name="pattern"></a>Mönster

Nyckelord

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Ett nyckelord från Dictionary_icd_10_updated hittas.
- Ett nyckelord från Dictionary_icd_10_codes hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Ett nyckelord från Dictionary_icd_10_ har uppdaterats hittas.

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

### <a name="keywords"></a>Nyckelord

Valfri term från nyckelordsordlistan i Dictionary_icd_10_updated, som baseras på den internationella klassificeringen av den internationella klassificeringen, den tionde revisionen, den kliniskt [modifieringen (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). Den här typen söker bara efter termen, inte för försäkringskoderna.

Valfri term från nyckelordsordlistan i Dictionary_icd_10_codes, som baseras på den internationella klassificeringen av ärevisionen, tionde revision, klinisk ändring [(ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). Den här typen söker bara efter försäkringskoder, inte beskrivningen.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Internationell klassificering av den internationella klassificeringen (ICD-9-CM)

### <a name="format"></a>Format

Ordlista

### <a name="pattern"></a>Mönster

Nyckelord

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Ett nyckelord från Dictionary_icd_9_updated hittas.
- Ett nyckelord från Dictionary_icd_9_codes hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Ett nyckelord från Dictionary_icd_9_updated hittas.

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

Valfri term från nyckelordsordlistan i Dictionary_icd_9_updated, som baseras på den internationella klassificeringen av det här ordet, den nionde revisionen, den kliniskt [modifieringen (ICD-9-CM).](https://go.microsoft.com/fwlink/?linkid=852605) Den här typen söker bara efter termen, inte för försäkringskoderna.

Valfri term från Dictionary_icd_9_codes ordlistan, som baseras på den internationella klassificeringen av ärevisionen, den nionde revisionen, den kliniskt [modifieringen (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). Den här typen söker bara efter försäkringskoder, inte beskrivningen.

## <a name="ip-address"></a>IP-adress

### <a name="format"></a>Format

#### <a name="ipv4"></a>IPv4:
Komplext mönster som konton för formaterade (punkter) och oformaterade (inga perioder) versioner av IPv4-adresser

#### <a name="ipv6"></a>IPv6:
Komplext mönster som står för formaterade IPv6-tal (som innehåller kolon)

### <a name="pattern"></a>Mönster

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

För IPv6 har en DLP-princip med hög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_ipv6_address hittar innehåll som matchar mönstret.
- Inget nyckelord från Keyword_ipaddress hittas.

För IPv4 har en DLP-princip med hög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_ipv4_address hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_ipaddress hittas.

För IPv6 har en DLP-princip med hög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_ipv6_address hittar innehåll som matchar mönstret.
- Inget nyckelord från Keyword_ipaddress hittas.

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (det här nyckelordet är det här är det ärendekänsliga)
- ip-adress 
- ip-adresser
- internetprotokoll
- IP-כתובת 

## <a name="ireland-drivers-license-number"></a>Irlands körkortsnummer

### <a name="format"></a>Format

Sex siffror följt av fyra bokstäver
  
### <a name="pattern"></a>Mönster

Sex siffror och fyra bokstäver:
  
- Sex siffror
- Fyra bokstäver (inte teckenkänsliga)
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
  
- Det reguljära  `Regex_ireland_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_ireland_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Ireland Driver's License Number -->
      <Entity id="e01bccd9-eb4d-414f-ace1-e9b6a4c4a2ca" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_ireland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver är s_license_number

- ceadúnas tiomána
- ceadúnais tiomána

## <a name="ireland-passport-number"></a>Irland, passnummer

### <a name="format"></a>Format

Två bokstäver eller siffror följt av sju siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

Två bokstäver eller siffror följt av sju siffror:
  
- Två siffror eller bokstäver (inte teckenkänsliga)
- Sju siffror
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_ireland_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_ireland_eu_passport_number` hittas. 
- Det reguljära uttrycket hittar datum i formatet `Regex_ireland_eu_passport_date` DD MMM/MMM YYYY (Exempel - 01 BEA/MAJ 1988) eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_ireland_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_ireland_eu_passport_number` hittas.
    
```xml
      <!-- Ireland Passport Number -->
      <Entity id="a2130f27-9ee2-4103-84f9-a6b1ee7d0cbf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_ireland_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasanna
- uimhir pas
- uimhir phas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="ireland-personal-public-service-pps-number"></a>PpS-nummer (Personal Public Service) för Irland

### <a name="format"></a>Format

Gammalt format (till 31 december 2012):
- sju siffror följt av 1–2 bokstäver 

Nytt format (1 januari 2013 och senare):
- sju siffror följt av två bokstäver

### <a name="pattern"></a>Mönster

Gammalt format (till 31 december 2012):
- sju siffror 
- En till två bokstäver (inte teckenkänsligt) 

Nytt format (1 januari 2013 och senare):
- sju siffror 
- En bokstav (inte en teckenkänslig) som är en alfabetisk kontrollsiffra 
- En valfri bokstav i cellområdet A-I eller "W"

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_ireland_pps hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_ireland_eu_national_id_card hittas.
- Kontrollsumman passeras.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_ireland_pps hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
      <!-- Ireland Personal Public Service (PPS) Number -->
      <Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_pps" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_ireland_pps" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- klientidentitetstjänst
- identification number
- personligt ID-nummer
- personligt offentligt servicenummer
- personlig tjänstnr
- phearsanta seirbhíse poiblí
- pps no
- pps-tal
- pps num
- pps-tjänstnr
- ppsn
- ppsno #
- ppsno
- psp
- public service no
- publicserviceno #
- publicserviceno
- intäkts- och socialförsäkringsnummer
- rsi no
- rsi-nummer
- rsin
- seirbhís aitheantais-klienten
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #


## <a name="israel-bank-account-number"></a>Bankkontonummer för Israel

### <a name="format"></a>Format

13 siffror

### <a name="pattern"></a>Mönster

Formaterat:
- två siffror 
- ett streck 
- tre siffror 
- ett streck 
- åtta siffror

Oformaterat:
- 13 siffror i följd

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_israel_bank_account_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_israel_bank_account_number hittas.

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Bankkontonummer 
- Bankkonto 
- Kontonummer 
- מספר חשבון בנק 
   
## <a name="israel-national-identification-number"></a>Israels national identification number

### <a name="format"></a>Format

nio siffror

### <a name="pattern"></a>Mönster

nio siffror i följd

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_israeli_national_id_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_Israel_National_ID hittas.
- Kontrollsumman passeras.

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

-   מספר זהות
-   מספר זיה וי
-   מספר זיהוי ישר אלי      
-   זהותישר אלית
-   هو ية اسرائيل ية عدد
-   هوية إسرائ يلية
-   رقم الهوية
-   عدد هوية فريدة من نوعها
-   idnumber #
-   id-nummer
-   identity no        
-   identitynumber #
-   identitetsnummer
-   israeliskaidentitynumber       
-   personligt ID
-   unikt ID  

   
## <a name="italy-drivers-license-number"></a>Italiens körkortsnummer

Den här typen av känslig information ingår i EU-drivrutinens typ av licensnummerkänslig information och är tillgänglig som en fristående typ av känslig information.

### <a name="format"></a>Format

en kombination av 10 bokstäver och siffror

### <a name="pattern"></a>Mönster

en kombination av 10 bokstäver och siffror:
- en bokstav (inte en ärendekänslig) 
- bokstaven "A" eller "V" (inte ärendekänsligt) 
- sju siffror
- en bokstav (inte en ärendekänslig)

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära `Regex_italy_drivers_license_number` uttrycket hittar innehåll som matchar mönstret.
- Ett nyckelord från `Keywords_eu_driver's_license_number` eller `Keyword_italy_drivers_license_number` hittas.

```xml
    <!-- Italy Driver's license Number -->
    <Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keyword_italy_drivers_license_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente
- patente di guida 
- patente guida
- patenti di guida
- patenti guida


## <a name="italy-fiscal-code"></a>Italiens räkenskapskod
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

En kombination av bokstäver och siffror på 16 tecken i det angivna mönstret
  
### <a name="pattern"></a>Mönster

En kombination av 16 tecken och siffror:
- Tre bokstäver som motsvarar de tre första konsonanterna i familjenamnet
- Tre bokstäver som motsvarar den första, tredje och fjärde konsonanterna i förnamnet
- två siffror som motsvarar de sista siffrorna i födelsedatumet
- en bokstav som motsvarar bokstaven för födelsedatumet – bokstäver används i alfabetisk ordning, men bara bokstäverna A till E, H, L, M, P, R till T används (så januari är A och oktober är R)
- Två siffror som motsvarar dagen i månaden – för att skilja på kön läggs 40 till för kvinnor
- fyra siffror som motsvarar den specifika areakoden för den valuta som personen är föds på (landskoder används för externa länder)
- en paritetssiffra
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_italy_eu_national_id_card` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_italy_eu_national_id_card` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_italy_eu_national_id_card` innehåll som matchar mönstret. 
    
```xml
      <!-- Italy Fiscal Code -->
      <Entity id="4cd79172-8da9-4ff5-9188-98b1e7e2eca6" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- codice fiscal
- codice fiscale
- codice id personale
- codice personale
- räkenskapskod
- numero certificificific personale
- numero di identificazione fiscale
- numero id personale
- numero personale
- personligt certifikatnummer
- personlig kod
- personlig ID-kod
- personligt ID-nummer
- personalcodeno #
- skattekod
- tax id
- tax identification no
- tax identification number
- skatteidentitetsnummer
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #


## <a name="italy-passport-number"></a>Italien passnummer

### <a name="format"></a>Format

två bokstäver eller siffror följt av sju siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

Två bokstäver eller siffror följt av sju siffror:
  
- två siffror eller bokstäver (inte teckenkänsliga)
- sju siffror
    
### <a name="checksum"></a>Kontrollsumma

ej tillämpligt
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_italy_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_italy_eu_passport_number` hittas. 
- Det reguljära uttrycket hittar datum i formatet `Regex_italy_eu_passport_date` DD MMM/MMM YYYY (Exempel - 01 GEN/JAN 1988) eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_italy_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_italy_eu_passport_number` hittas. 
    
```xml
      <!-- Italy Passport Number -->
      <Entity id="39811019-4750-445f-b26d-4c0e6c431544" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_italy_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- passeport italien

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="italy-value-added-tax-number"></a>Momsnummer i Italien
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

13 tecken för alfanumeriska mönster med valfria avgränsare

### <a name="pattern"></a>Mönster

13 tecken med alfanumeriska mönster med valfria avgränsare:

- I eller i
- T eller t
- Valfritt blanksteg, punkt, bindestreck eller kommatecken
- 11 siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_italy_value_added_tax_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_italy_value_added_tax_number hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_italy_value_added_tax_number hittar innehåll som matchar mönstret.

```xml
      <!-- Italy Value Added Tax -->
      <Entity id="26a8cc07-2283-4a2a-ab1d-4ab643c4c67f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
          <Match idRef="Keywords_italy_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- momsregistreringsnummer
- momsnr
- moms #
- iva
- iva #


## <a name="japan-bank-account-number"></a>Bankkontonummer för Japan

### <a name="format"></a>Format

sju eller åtta siffror

### <a name="pattern"></a>Mönster

bankkontonummer:
- sju eller åtta siffror
- bankkontokontorskod:
- fyra siffror 
- Blanksteg eller streck (valfritt) 
- tre siffror

Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_jp_bank_account hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_jp_bank_account hittas.
- Något av följande är sant:
- Funktionen för Func_jp_bank_account_branch_code hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_jp_bank_branch_code hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_jp_bank_account hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_jp_bank_account hittas.

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_jp_bank_account"></a>Keyword_jp_bank_account

- Checking Account Number 
- Checking Account 
- Checking Account # 
- Checking Acct Number 
- Checking Acct # 
- Checking Acct No. 
- Checking Account No. 
- Bankkontonummer 
- Bankkonto 
- Bankkonto # 
- Bank Acct Number 
- Bank Acct # 
- Bank Acct No. 
- Bank Account No. 
- Savings Account Number 
- Savings Account 
- Savings Account # 
- Savings Acct Number 
- Savings Acct # 
- Savings Acct No. 
- Savings Account No. 
- Debit Account Number 
- Debit Account 
- Debit Account # 
- Debit Acct Number 
- Debit Acct # 
- Debit Acct No. 
- Debit Account No. 
- 口座番号
- 銀行口座
- 銀行口座番号
- 総合口座
- 普通預金口座
- 普通口座
- 当座預金口座
- 当座口座
- 預金口座
- 振替口座
- 銀行
- バンク

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

- 支店番号
- 支店コード
- 店番号

## <a name="japan-drivers-license-number"></a>Japans körkortsnummer

### <a name="format"></a>Format

12 siffror

### <a name="pattern"></a>Mönster

12 siffror i följd

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_jp_drivers_license_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_jp_drivers_license_number hittas.

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- driverlicense
- driverslicense
- driver'slicense
- driverslicenses
- driver'slicenses
- driverlicenses
- dl #
- dls #
- lic #
- lics #
- 運転免許証
- 運転免許
- 免許証
- 免許
- 運転免許証番号
- 運転免許番号
- 免許証番号
- 免許番号
- 運転免許証ナンバー
- 運転免許ナンバー
- 免許証ナンバー
- 運転免許証nr
- 運転免許no
- 免許証nr
- 免許no
- 運転経歴証明書番号
- 運転経歴証明書
- 運転免許証No.
- 運転免許Nr.
- 免許証No.
- 免許No.
- 運転免許証 #
- 運転免許 #
- 免許証 #
- 免許 #


## <a name="japan-my-number---corporate"></a>Japan, mitt nummer – företag
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

13-siffrigt nummer

### <a name="pattern"></a>Mönster

13-siffrigt nummer:

- en siffra från en till nio
- 12 siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_japanese_my_number_corporate hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_japanese_my_number_corporate hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_japanese_my_number_corporate hittar innehåll som matchar mönstret.

```xml
      <!-- Japanese My Number – Corporate -->
      <Entity id="9e0eaf79-ff20-4ffb-b3e4-e7368d5db6ff" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
          <Match idRef="Keywords_japanese_my_number_corporate" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_japan_my_number_corporate"></a>Keyword_japan_my_number_corporate

- företagsnummer
- マイナンバー
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 法人番号
- 指定通知書


## <a name="japan-my-number---personal"></a>Japan, mitt nummer – privat
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

12-siffrigt nummer

### <a name="pattern"></a>Mönster

12-siffrigt nummer:

- fyra siffror
- Ett valfritt blanksteg, punkt eller bindestreck
- fyra siffror
- Ett valfritt blanksteg, punkt eller bindestreck
- fyra siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_japanese_my_number_personal hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_japanese_my_number_personal hittas.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_japanese_my_number_personal hittar innehåll som matchar mönstret.

```xml
      <!-- Japanese My Number – Personal -->
      <Entity id="98da8e66-7299-4ebd-9f82-c871ab37d3ef" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_personal" />
          <Match idRef="Keywords_japanese_my_number_personal" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_japanese_my_number_personal" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- mitt nummer
- マイナンバー
- 個人番号
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 通知カード

   
## <a name="japan-passport-number"></a>Japan passport number

### <a name="format"></a>Format

Två bokstäver följt av sju siffror

### <a name="pattern"></a>Mönster

Två bokstäver (inte teckenkänsliga) följt av sju siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_jp_passport hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_jp_passport hittas.

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- Pass
- Passport Number
- Passport No.
- Pass #
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート #
- パスポートNo.
- 旅券番号
- 旅券番号＃
- 旅券番号♯
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>Japan residence card number

### <a name="format"></a>Format

12 bokstäver och siffror

### <a name="pattern"></a>Mönster

12 bokstäver och siffror:
- Två bokstäver (inte versaler och teckenkänsliga)
- åtta siffror 
- Två bokstäver (inte versaler och teckenkänsliga)

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_jp_residence_card_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_jp_residence_card_number hittas.

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- Residence card number
- Residence card no
- Residence card #
- 在留カード番号
- 在留カード
- 在留番号

## <a name="japan-resident-registration-number"></a>Registreringsnummer för boende i Japan

### <a name="format"></a>Format

11 siffror

### <a name="pattern"></a>Mönster

11 siffror i följd

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_jp_resident_registration_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_jp_resident_registration_number hittas.

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Invånarregistreringsnummer
- Boendes grundläggande registernummer 
- Registreringsnr för boende. 
- Resident Register No. 
- Residents Basic Registry No. 
- Basic Resident Register No. 
- 外国人登録証明書番号
- 証明書番号
- 登録番号
- 外国人登録証

   
## <a name="japan-social-insurance-number-sin"></a>Japan social insurance number (SIN)

### <a name="format"></a>Format

7-12 siffror

### <a name="pattern"></a>Mönster

7-12 siffror:
- fyra siffror 
- Ett bindestreck (valfritt) 
- sex siffror ELLER
- 7–12 siffror i följd

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_jp_sin hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_jp_sin hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_jp_sin_pre_1997 hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_jp_sin hittas.

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No. 
- Social Insurance Num 
- Social Insurance Number 
- 健康保険被保険者番号
- 健保番号
- 基礎年金番号
- 雇用保険被保険者番号
- 雇用保険番号
- 保険証番号
- 社会保険番号
- 社出保険No.
- 社会保険
- 介護保険
- 介護保険被保険者番号
- 健康保険被保険者整理番号
- 雇用保険被保険者整理番号
- 厚生年金
- 厚生年金被保険者整理番号


## <a name="latvia-drivers-license-number"></a>Lettiska körkortsnummer

### <a name="format"></a>Format

Tre bokstäver följt av sex siffror
  
### <a name="pattern"></a>Mönster

tre bokstäver och sex siffror:
  
- Tre bokstäver (inte versaler och teckenkänsliga) 
- sex siffror
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_latvia_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_latvia_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Latvia Driver's License Number -->
      <Entity id="ec996de0-30f2-46b1-b192-4d2ff8805fa7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_latvia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver är s_license_number

- autovadītāja apliecība
- autovadītāja apliecības
- vadītāja apliecība

## <a name="latvia-personal-code"></a>Personlig kod för Lettland

### <a name="format"></a>Format

11 siffror och ett valfritt bindestreck
  
### <a name="pattern"></a>Mönster

Gammalt format

11 siffror och ett bindestreck:
  
- Sex siffror som motsvarar födelsedatumet (DDMMYY) 
- ett bindestreck
- en siffra som motsvarar födelsedatumet ("0" för 19:e talet, "1" för 20:e talet och "2" för 2000-talet)
- fyra siffror, slumpmässigt genererade

Nytt format

11 siffror

- Två siffror "32"
- Nio siffror
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen eller  `Func_latvia_eu_national_id_card` regex hittar `Regex_latvia_eu_national_id_card_new_format` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_latvia_eu_national_id_card` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen eller  `Func_latvia_eu_national_id_card` regex hittar `Regex_latvia_eu_national_id_card_new_format` innehåll som matchar mönstret. 
    
```xml
      <!-- Latvia Personal Code -->
      <Entity id="03fcf763-27c2-49ed-9422-2641c6c895c9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- administrativt nummer
- alvas nē
- födelsedatum
- telefonnummer för medborgare
- civilnummer
- Elektronisk statistiska nummer
- elektroniskt nummer
- räkenskapskod
- användarnummer för sjukvård
- id #
- id-kod
- identification number
- identifikācijas numurs
- id-number
- enskilt nummer
- latvija alva
- nacionā uppringnings-id
- national id
- national identifying number
- national identity number
- national insurance number
- national register number
- nodokfara numurs
- nodokau id
- nodokāu identifikācija numurs
- personligt certifikatnummer
- personlig kod
- personlig ID-kod
- personligt ID-nummer
- personal identification code
- personlig identifierare
- personnummer
- personligt nummer
- personlig numerisk kod
- personalcodeno #
- personas kods
- identifieringskod för population
- public service number
- registreringsnummer
- intäktsnummer
- social insurance number
- personnummer
- delstatsskattekod
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #
- dens nummer

## <a name="latvia-passport-number"></a>Lettiska passnummer

### <a name="format"></a>Format

två bokstäver eller siffror följt av sju siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

Två bokstäver eller siffror följt av sju siffror:
  
- två siffror eller bokstäver (inte teckenkänsliga)
- sju siffror
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_latvia_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_latvia_eu_passport_number` hittas. 
- Det reguljära `Regex_eu_passport_date1` uttrycket hittar datum i formatet DD.MM.YYYY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_latvia_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_latvia_eu_passport_number` hittas. 
    
```xml
      <!-- Latvia Passport Number -->
      <Entity id="23ae25ec-cc28-421b-b77a-3054eadf1ede" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- pases numuri
- pases nr
- passeport no
- n° du Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="lithuania-drivers-license-number"></a>Litauens körkortsnummer

### <a name="format"></a>Format

Åtta siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

åtta siffror 
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_lithuania_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_lithuania_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Lithuania Driver's License Number -->
      <Entity id="86f7628b-e0f4-4dc3-9fbc-e4300e4c7d78" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver är s_license_number

- vairuotojo pažymymjimas
- vairuotojo panotymjijimo numeris
- vairuotojo panotymjijimo numeriai

## <a name="lithuania-personal-code"></a>Personlig kod för Litauen
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

11 siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

11 siffror utan blanksteg och avgränsare:
  
- en siffra (1–6) som motsvarar personens kön och födelsedatumet
- Sex siffror som motsvarar födelsedatum (AMMDD) 
- Tre siffror som motsvarar serienumret för födelsedatumet
- en checksiffra
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_lithuania_eu_tax_file_number` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_lithuania_eu_tax_file_number` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_lithuania_eu_tax_file_number` innehåll som matchar mönstret. 
    
```xml
      <!-- Lithuania Personal Code -->
      <Entity id="cd6d3786-8ec3-4524-a2cf-1e0095379171" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_lithuania_eu_telephone_number" />
            <Match idRef="Keywords_lithuania_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- asmeninis skaitmeninis kodas
- asmens kodas
- servicenummer för servicenr, service, service,
- mokesčičič id
- mokesčió identifikavimas numeris
- mokesčió identifikavimo numeris
- mokesčič numeris
- national identification number
- personlig kod
- personlig numerisk kod
- piliečio paslaugos numeris
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- unikt ID-nummer
- unikt identitetsnummer
- uniqueidentityno #

## <a name="lithuania-passport-number"></a>Litauen passnummer

### <a name="format"></a>Format

åtta siffror eller bokstäver utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

åtta siffror eller bokstäver (inte teckenkänsliga)
  
### <a name="checksum"></a>Kontrollsumma

ej tillämpligt
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_lithuania_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_lithuania_eu_passport_number` hittas. 
- Det reguljära `Regex_eu_passport_date3` uttrycket hittar datum i formatet DD MM YYYY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_lithuania_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_lithuania_eu_passport_number` hittas. 
    
```xml
      <!-- Lithuania Passport Number -->
      <Entity id="1b79900f-047b-4c3f-846f-7d73b5534bce" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso numeris
- paso numeriai
- paso nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="luxemburg-drivers-license-number"></a>Luxemburgs körkortsnummer

### <a name="format"></a>Format

Sex siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

sex siffror 
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_luxemburg_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_luxemburg_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Luxemburg Driver's License Number -->
      <Entity id="89daf717-1544-4860-9a2e-fc9166dd8852" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver är s_license_number

- farélaubnis
- Füüüschäin

## <a name="luxemburg-national-identification-number-natural-persons"></a>Luxemburgs national identification number (natural persons)
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

13 siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

13 siffror:
  
- 11 siffror 
- två kontrollsiffror
    
### <a name="checksum"></a>Kontrollsumma

ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_luxemburg_eu_tax_file_number` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_luxemburg_eu_national_id_card` från hittas. 

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_luxemburg_eu_tax_file_number` innehåll som matchar mönstret. 


```xml
      <!-- Luxemburg National Identification Number (Natural persons) -->
      <Entity id="aaf661ed-29ec-426d-8bf9-880cad298ebb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- eindeutige id
- eindeutige id-nummer
- eindeutigeid #
- id personnelle
- idpersonnelle #
- idpersonnelle
- enskild kod
- enskilt id
- enskild legitimation
- enskild identitet
- numéro d'identification personnel
- personligt ID
- personlig legitimation
- personlig identitet
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- unikt ID
- unik identitet
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>Luxemburg-passnummer

### <a name="format"></a>Format

åtta siffror eller bokstäver utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

åtta siffror eller bokstäver (inte teckenkänsliga)
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_luxemburg_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_luxemburg_eu_passport_number` hittas. 
- Det reguljära `Regex_eu_passport_date3` uttrycket hittar datum i formatet DD MM YYYY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_luxemburg_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_luxemburg_eu_passport_number` hittas. 
    
```xml
      <!-- Luxemburg Passport Number -->
      <Entity id="81d5c027-bed9-4421-91a0-3b2e55b3eb85" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- aus uppsnummer
- luxembourg pass
- luxembourg passeport
- luxembourg-pass
- no de passeport
- no-reisepass
- nr-reisepass
- numéro de passeport
- pass net
- pass nr
- passnummer
- passeport nombre
- reisessesse
- reisepass-nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>Luxemburgs national identification number (icke-naturliga personer)

### <a name="format"></a>Format

11 siffror
  
### <a name="pattern"></a>Mönster

11 siffror
  
- två siffror
- ett valfritt blanksteg 
- tre siffror 
- ett valfritt blanksteg
- tre siffror 
- ett valfritt blanksteg
- två siffror
- en checksiffra
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_luxemburg_eu_tax_file_number_non_natural` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_luxemburg_eu_tax_file_number` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_luxemburg_eu_tax_file_number_non_natural` innehåll som matchar mönstret. 
    
```xml
      <!-- Luxemburg National Identification Number (Non-natural persons) -->
      <Entity id="84bffa3a-d805-4788-a613-b1e4df3804cf" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- carte de sécurité sociale
- étain non
- étain #
- identifiant d'impôt
- luxembourg tax identifikatiounsnummer
- numéro d'étain
- numéro d'identification fiscal luxembourgeois
- numéro d'identification fiscale
- social security
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausvägs
- steier-id
- steier identifikatiounsnummer
- steiernummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #
- zinn #
- zinn
- zinnznznz


## <a name="malaysia-identification-card-number"></a>Malaysia identification card number

### <a name="format"></a>Format

12 siffror med valfria bindestreck

### <a name="pattern"></a>Mönster

12 siffror:
- Sex siffror i formatet YYMMDD, som är födelsedatumet 
- Ett streck (valfritt) 
- plats-av-födelsedatum med två bokstäver 
- Ett streck (valfritt) 
- tre slumpmässiga siffror 
- ensiffrig kön-kod

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_malaysia_id_card_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_malaysia_id_card_number hittas.

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord
   
#### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- digitalt programkort
- i/c
- i/c nej
- ic
- ic no
- id card
- identification Card
- identitetskort
- k/p
- k/p nej
- han eller hon akuan diri
- vari aplikasi digital
- pengenalan malaysia
- kp
- kp no
- mykad
- mykas
- mykid
- mypr
- mytentera
- malaysia identity card
- malaysian identitetskort
- nric
- personal identification card

## <a name="malta-drivers-license-number"></a>Maltas körkortsnummer

### <a name="format"></a>Format

Kombination av två tecken och sex siffror i det angivna mönstret
  
### <a name="pattern"></a>Mönster

kombination av två tecken och sex siffror:
  
- Två tecken (siffror eller bokstäver, inte teckenkänsliga)
- ett blanksteg (valfritt)
- tre siffror
- ett blanksteg (valfritt)
- tre siffror
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_malta_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_malta_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Malta Driver's License Number -->
      <Entity id="a3bdaa4a-8371-4735-8fa5-56ee0fb4afc4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_malta_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver är s_license_number

- liizenzja tas-faqan
- liizenzji tas-faqq


## <a name="malta-identity-card-number"></a>Malta-identitetskortsnummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

sju siffror följt av en bokstav
  
### <a name="pattern"></a>Mönster

sju siffror följt av en bokstav:
  
- sju siffror 
- en bokstav i "M, G, A, P, L, H, B, Z" (ärendekänsligt)
    
### <a name="checksum"></a>Kontrollsumma

Ej tillämpligt
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_malta_eu_national_id_card` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_malta_eu_national_id_card` från hittas. 
    
En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_malta_eu_national_id_card` uttrycket hittar innehåll som matchar mönstret. 
    
```xml
      <!-- Malta Identity Card Number -->
      <Entity id="854b36b3-a388-4ac8-a4ec-677c2b5e4356" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- servicenummer för servicenr, service, service,
- id tat-taxxa
- identifika numru tal-biljett
- kodilisi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taë-ëittadin
- numru tat-taxxa
- personlig numerisk kod
- unikt ID-nummer
- unikt identitetsnummer
- uniqueidentityno #


## <a name="malta-passport-number"></a>Malta passnummer

### <a name="format"></a>Format

sju siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

sju siffror 
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_malta_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_malta_eu_passport_number` hittas. 
- Ett nyckelord `Keywords_eu_passport_date` från hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_malta_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_malta_eu_passport_number` hittas. 
    
```xml
      <!-- Malta Passport Number -->
      <Entity id="b2b21198-48f9-4d13-b2a5-03969bff0fb8" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
          <Match idRef="Keywords_eu_passport_date" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="malta-tax-identification-number"></a>Maltas skatteidentifieringsnummer

### <a name="format"></a>Format

För Maltesiska:
- sju siffror och en bokstav i det angivna mönstret
  
Non-Denesiska ochesiska enheter:
- nio siffror
  
### <a name="pattern"></a>Mönster

Esiska: sju siffror och en bokstav
  
- sju siffror 
- en bokstav (inte en ärendekänslig)
    
Non-Denesiska och enheter av senesiska: nio siffror
  
- nio siffror 
    
### <a name="checksum"></a>Kontrollsumma

Ej tillämpligt
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Regex eller  `Regex_malta_eu_tax_file_number`  hittar innehåll som matchar `Regex_malta_eu_tax_file_number_non_maltese_national` mönstret. 
- Ett nyckelord  `Keywords_malta_eu_tax_file_number` från hittas. 
    
En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Regex eller  `Regex_malta_eu_tax_file_number` hittar innehåll som matchar `Regex_malta_eu_tax_file_number_non_maltese_national` mönstret. 
    
```xml
      <!-- Malta Tax ID Number -->
      <Entity id="ec830c63-65f4-45d0-9d8c-910dc8334b20" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- servicenummer för servicenr, service, service,
- id tat-taxxa
- identifika numru tal-biljett
- kodilisi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taë-ëittadin
- numru tat-taxxa
- personlig numerisk kod
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #
- unikt ID-nummer
- unikt identitetsnummer
- uniqueidentityno #


## <a name="medicare-beneficiary-identifier-mbi-card"></a>MBI-kort (Identifier Identifier)

### <a name="format"></a>Format

eleven character alphanumeric pattern
  
### <a name="pattern"></a>Mönster

- en siffra mellan 1 och 9
- en bokstav utom S, L, O, I, B, Z
- en siffra eller bokstav utom S, L, O, I, B, Z
- en siffra
- ett valfritt bindestreck
- en bokstav utom S, L, O, I, B, Z
- en siffra eller bokstav utom S, L, O, I, B, Z
- en siffra
- ett valfritt bindestreck
- två bokstäver utom S, L, O, I, B, Z
- två siffror
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_mbi_card` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord  `Keyword_mbi_card` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_mbi_card` uttrycket hittar innehåll som matchar mönstret. 
    
```xml
    <!-- Medicare Beneficiary Identifier (MBI) card -->
      <Entity id="f753a286-f5cc-47e6-a592-4be25fd02591" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_mbi_card" />
          <Match idRef="Keyword_mbi_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_mbi_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_mbi_card"></a>Keyword_mbi_card

- mbi
- mbi #
- medicare-mottagare #
- medicare identifier
- medicare mottagarnr
- medicare mottagarnummer
- medicare-mottagare #


## <a name="mexico-unique-population-registry-code-curp"></a>Mexico Unique Population Registry Code (CURP)

### <a name="format"></a>Format

18 tecken för alfanumeriskt mönster
  
### <a name="pattern"></a>Mönster

- fyra bokstäver (inkänsliga versaler)
- Sex siffror som anger ett giltigt datum
- en bokstav – H/h eller M/m
- Två bokstäver som anger en giltig statuskod i Mexico
- tre bokstäver
- en bokstav eller en siffra
- en siffra
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_mexico_population_registry_code` innehåll som matchar mönstret. 
- Ett nyckelord  `Keyword_mexico_population_registry_code` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_mexico_population_registry_code` innehåll som matchar mönstret. 
    
```xml
    <!-- Mexico Unique Population Registry Code (CURP) -->
      <Entity id="e905ad4d-5a74-406d-bf36-b1efca798af4" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_mexico_population_registry_code" />
          <Match idRef="Keyword_mexico_population_registry_code" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_mexico_population_registry_code" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_mexico_population_registry_code"></a>Keyword_mexico_population_registry_code

- Kodriska Única de Registro de Población
- Puffve Unica de Registro de Poblacion
- Registerkod för unik population 
- unik populationskod
- CURP
- Personligt ID
- Unikt ID
- personalid
- personalidnumber
- uniqueidkey
- uniqueidnumber
- úve única
- vakve unica
- personal Identidad
- personal Identidad Ochve
- PeruaveÚnica
- nicanica
- personalIdentidad


## <a name="netherlands-citizens-service-bsn-number"></a>Nederländska medborgares servicenummer (BSN)

### <a name="format"></a>Format

Åtta eller nio siffror som innehåller valfria blanksteg

### <a name="pattern"></a>Mönster

åtta-nio siffror:
- tre siffror 
- ett blanksteg (valfritt) 
- tre siffror 
- ett blanksteg (valfritt) 
- två-tre siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_netherlands_bsn hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_netherlands_bsn hittas.
- Kontrollsumman passeras.

```xml
      <!-- Netherlands Citizen's Service (BSN) Number -->
      <Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_bsn" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card
  
- bsn #
- bsn
- servicenummer
- servicenummer för servicenr, service, service,
- personnummer
- personligt nummer
- personlig numerisk kod
- personrelaterat nummer
- persoonlijk nummer
- persoonlijke numerieke-kod
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- social-fiscal number
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- unikt ID-nummer
- unikt identitetsnummer
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>Nederländska körkortsnummer

### <a name="format"></a>Format

tio siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

tio siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_netherlands_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_netherlands_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Netherlands Driver's License Number -->
      <Entity id="6247fbea-ab80-4be5-8233-308b7c031401" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
            </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver är s_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewijzen
- rijbewijs nummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>Nederländska passnummer

### <a name="format"></a>Format

Nio bokstäver eller siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

nio bokstäver eller siffror
  
### <a name="checksum"></a>Kontrollsumma

ej tillämpligt
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_netherlands_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_netherlands_eu_passport_number` hittas. 
- Det reguljära uttrycket hittar datum i formatet `Regex_netherlands_eu_passport_date` DD MMM/MMM YYYY (Exempel - 26 MAA/MAR 2012)

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_netherlands_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_netherlands_eu_passport_number` hittas. 
    
```xml
      <!-- Netherlands Passport Number -->
      <Entity id="61786727-bafd-45f6-94d9-888d815e228e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Regex_netherlands_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoort nummer
- paspoortnummers
- paspoortnummer
- paspoort nr

## <a name="netherlands-tax-identification-number"></a>Nederländska skatteidentifieringsnummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

Nio siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

nio siffror 
  
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_netherlands_eu_tax_file_number` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_netherlands_eu_tax_file_number` från hittas. 
    
En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_netherlands_eu_tax_file_number` innehåll som matchar mönstret. 
    
```xml
      <!-- Netherlands Tax Identification Number -->
      <Entity id="01f42a64-eba7-4892-a67b-398237e4ade2" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- han/hon nummer
- den här skatteidentifieringen
- hulandes impuesto id number
- hulandes impuesto identification
- identificatienummer belasting
- identificatienummer van belasting
- impuesto identification number
- impuesto-nummer
- nederlands belasting id nummer
- nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- nederlandse belasting identificatie
- nederländska skatteidentifiering
- Netherlands skatteidentifiering
- nederländska tin
- netherlands tin
- tax id
- tax identification no
- tax identification number
- tax identification tal
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- tax tal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #


## <a name="netherlands-value-added-tax-number"></a>Nederländska momsnummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

14 tecken för alfanumeriskt mönster

### <a name="pattern"></a>Mönster

Alfanumeriskt mönster med 14 tecken:

- N eller n
- L eller l
- Valfritt blanksteg, punkt eller bindestreck
- nio siffror
- Valfritt blanksteg, punkt eller bindestreck
- B eller b
- två siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_netherlands_value_added_tax_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_netherlands_value_added_tax_number hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_netherlands_value_added_tax_number hittar innehåll som matchar mönstret.

```xml
      <!-- Netherlands Value Added Tax Number -->
      <Entity id="4f320d9b-4972-41ae-b337-88d499bb1ade" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
          <Match idRef="Keywords_netherlands_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- momsregistreringsnummer
- momsnr
- moms #
- wearde tafoege tax getal
- ú númer
- y.y.y.


## <a name="new-zealand-bank-account-number"></a>Bankkontonummer för Nya Zeeland
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

14-siffrigt till 16-siffrigt mönster med valfri avgränsare

### <a name="pattern"></a>Mönster

14-siffrigt till 16-siffrigt mönster med valfri avgränsare:

- två siffror
- Ett valfritt bindestreck eller blanksteg
- tre till fyra siffror
- Ett valfritt bindestreck eller blanksteg
- sju siffror
- Ett valfritt bindestreck eller blanksteg
- Två till tre siffror
- Ett bindestreck eller blanksteg för alternativ

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_new_zealand_bank_account_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_new_zealand_bank_account_number hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_new_zealand_bank_account_number hittar innehåll som matchar mönstret.

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zFealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- kontonummer
- bankkonto
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>New Zealand driver's license number
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

åtta tecken för alfanumeriskt mönster

### <a name="pattern"></a>Mönster

åtta tecken för alfanumeriskt mönster

- två bokstäver 
- sex siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_newzealand_driver_license_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_newzealand_driver_license_number hittas.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_newzealand_driver_license_number hittar innehåll som matchar mönstret.

```xml
      <!-- New Zealand Driver License Number -->
      <Entity id="1924b377-d287-49c9-a737-cfe7a8a2615a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
          <Match idRef="Keywords_newzealand_driver_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_new_zealand_drivers_license_number"></a>Keyword_new_zealand_drivers_license_number

- driverlicence
- driverlicences
- driver lic
- driver licence
- driver licences
- driverslic
- driverslicence
- driverslicences
- drivers lic
- drivers lics
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's licence
- driver's licences
- driverlic #
- driverlics #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver licence #
- driver licences #
- driverslic #
- driverslics #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's licence #
- driver's licences #
- internationellt körtillstånd
- internationella biltillstånd
- nz automobile association
- new zealand automobile association


## <a name="new-zealand-inland-revenue-number"></a>Inåtland i Nya Zeeland
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

Åtta eller nio siffror med valfria avgränsare

### <a name="pattern"></a>Mönster

Åtta eller nio siffror med valfria avgränsare

- två eller tre siffror
- Ett valfritt blanksteg eller bindestreck
- tre siffror
- Ett valfritt blanksteg eller bindestreck
- tre siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_new_zealand_inland_revenue_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_new_zealand_inland_revenue_number hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_new_zealand_inland_revenue_number hittar innehåll som matchar mönstret.

```xml
      <!-- New Zealand Inland Revenue Number -->
      <Entity id="dd0fe2bc-7bcf-455f-bac1-83b1e3eb25fd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
          <Match idRef="Keywords_new_zealand_inland_revenue_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- ird no.
- ird no #
- nz ird
- nya Zeeland
- ird nummer
- inåt landsnummer


## <a name="new-zealand-ministry-of-health-number"></a>Nya Zeeland med hälsonummer

### <a name="format"></a>Format

tre bokstäver, ett blanksteg (valfritt) och fyra siffror

### <a name="pattern"></a>Mönster

- Tre bokstäver (inte ärendekänsliga) förutom "I" och "O"
- ett blanksteg (valfritt) 
- fyra siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_new_zealand_ministry_of_health_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_nz_terms hittas.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_new_zealand_ministry_of_health_number hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
    <!-- New Zealand Health Number -->
    <Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
          <Match idRef="Keyword_nz_terms" />
      </Pattern>
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
       </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI
- Nya Zeeland
- Hälsa
- behandling
- National Health Index Number
- nhi-nummer
- nhi no.
- NHI #
- National Health Index No.
- National Health Index Id
- National Health Index #

## <a name="new-zealand-social-welfare-number"></a>Nya Zeelands sociala nummer

Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

nio siffror

### <a name="pattern"></a>Mönster

nio siffror

- tre siffror
- Ett valfritt bindestreck
- tre siffror
- Ett valfritt bindestreck
- tre siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_newzealand_social_welfare_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_newzealand_social_welfare_number hittas.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_newzealand_social_welfare_number hittar innehåll som matchar mönstret.

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- sociala medier #
- sociala medier #
- socialen No.
- social social social en-nummer
- swn #

   
## <a name="norway-identification-number"></a>Id-nummer för Norge

### <a name="format"></a>Format

11 siffror

### <a name="pattern"></a>Mönster

11 siffror:
- Sex siffror i formatet DDMMYY som är födelsedatumet 
- tresiffrigt enskilt nummer 
- två kontrollsiffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_norway_id_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_norway_id_number hittas.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_norway_id_numbe hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Personnummer
- Norska (ID-nummer)
- ID-nummer
- Identifiering
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-identification-number"></a>Philippines unified multi-purpose identification number

### <a name="format"></a>Format

12 siffror avgränsade med bindestreck

### <a name="pattern"></a>Mönster

12 siffror:
- fyra siffror 
- ett bindestreck 
- sju siffror 
- ett bindestreck 
- en siffra

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_philippines_unified_id hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_philippines_id hittas.

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord
   
#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Enhetligt flerfunktions-ID 
- UMID 
- Identitetskort 
- Pinag-isang Multi-Layunin-ID

## <a name="poland-drivers-license-number"></a>Polens körkortsnummer

### <a name="format"></a>Format

14 siffror med två snedstreck
  
### <a name="pattern"></a>Mönster

14 siffror och två snedstreck:
  
- fem siffror 
- ett snedstreck
- två siffror
- ett snedstreck
- sju siffror
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_poland_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_poland_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Poland Driver's License Number -->
      <Entity id="24d51f99-ee9e-4060-a077-cae58cab1ee4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_poland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver är s_license_number

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>Polens identitetskort

### <a name="format"></a>Format

tre bokstäver och sex siffror

### <a name="pattern"></a>Mönster

Tre bokstäver (inte teckenkänsliga) följt av sex siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_polish_national_id hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_polish_national_id_passport_number hittas.
- Kontrollsumman passeras.

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Dowód osobisty
- Numer dowodu osobistego
- Wa i numer dowodu osobistego
- Wa i nr dowodu osobistego
- Wa i nr dowodu to isamoxoci
- Dowód Toósamoòci
- dow. os.

   
## <a name="poland-national-id-pesel"></a>Polens national-ID (PESEL)

### <a name="format"></a>Format

11 siffror

### <a name="pattern"></a>Mönster

- Sex siffror som representerar födelsedatum i formatet YYMMDD
- fyra siffror
- en checksiffra

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_pesel_identification_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_pesel_identification_number hittas.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_pesel_identification_number hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
      <!-- Poland National ID (PESEL) -->
      <Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_pesel_identification_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- dowód osobisty
- dowódosobisty
- niepowtarzalny numer
- niepowtarzalnynumer
- nr.-pesel
- nr-pesel
- numer identyfikacyjny
- pesel
- tociesamoóci narodowej

   
## <a name="poland-passport-number"></a>Polen passnummer
Den här typen av känslig information ingår i typen Känslig information i EU Passport Number. Det är tillgängligt som en fristående typ av känslig information.

### <a name="format"></a>Format

Två bokstäver och sju siffror

### <a name="pattern"></a>Mönster

Två bokstäver (inte teckenkänsliga) följt av sju siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar `Func_polish_passport_number_v2` innehåll som matchar mönstret.
- Kontrollsumman passeras.
- Ett nyckelord från `Keywords_eu_passport_number` eller `Keyword_polish_national_passport_number` hittas.
- Ett nyckelord `Keywords_eu_passport_date` från hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar `Func_polish_passport_number_v2` innehåll som matchar mönstret.
- Kontrollsumman passeras.
- Ett nyckelord från `Keywords_eu_passport_number` eller `Keyword_polish_national_passport_number` hittas.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar `Func_polish_passport_number_v2` innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
      <!-- Poland Passport Number -->
      <Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_passport_number_v2" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keyword_polish_national_passport_number"></a>Keyword_polish_national_passport_number

- numer paszportu
- numery paszportów
- numery paszportowe
- nr paszportu
- nr. paszportu
- nr paszportów
- n° passeport
- passeport n°

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="poland-regon-number"></a>PolenS REGON-nummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

9- eller 14-siffrigt nummer

### <a name="pattern"></a>Mönster

Nio eller fyrsiffriga siffror:

- nio siffror eller 
- nio siffror
- bindestreck
- fem siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_polish_regon_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_polish_regon_number hittas.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_polish_regon_number hittar innehåll som matchar mönstret.

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Nyckelord

#### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- regon-id
- statistiskt tal
- statistiskt id
- statistiskt nej
- regonnummer
- regonid #
- regonno #
- företags-ID
- companyid #
- companyidno #
- numer densty denny
- numeru regon
- numerstatystynikny #
- numeruregon #


## <a name="poland-tax-identification-number"></a>Polens skatteidentifieringsnummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

11 siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

11 siffror
  
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_poland_eu_tax_file_number` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_poland_eu_tax_file_number` från hittas. 
    
  
```xml
      <!-- Poland Tax Identification Number -->
      <Entity id="1ff28b4d-40f2-49e9-b677-9606a88e2bca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- nip #
- nip
- numer identyfikacji podatüej
- numeridentyfikacjipodatpodatej #
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #
- momsregistreringsnummer #
- momsregistreringsnummer
- momsnr
- momsregistreringsnummer
- vatid #
- vatid
- vatno #
   

## <a name="portugal-citizen-card-number"></a>Portugal med kreditkortsnummer

### <a name="format"></a>Format

åtta siffror

### <a name="pattern"></a>Mönster

åtta siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_portugal_citizen_card hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_portugal_citizen_card hittas.

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- bilhete de identidade
- cartão de cidadão
- kreditkort
- dokumentnummer
- documento de identificação
- id-nummer
- identification no
- identification number
- identitetskortnr
- Identitetskortsnummer
- national id card
- nic
- número bi de portugal
- número de identificação civil
- número de identificação fiscal
- número do documento
- portugal bi number


## <a name="portugal-drivers-license-number"></a>Portugals körkortsnummer

### <a name="format"></a>Format

två mönster – två bokstäver följt av 5–8 siffror med specialtecken
  
### <a name="pattern"></a>Mönster

Mönster 1: Två bokstäver följt av 5/6 med specialtecken:
- Två bokstäver (inte versaler och teckenkänsliga)
- Ett bindestreck
- Fem eller sex siffror
- Ett blanksteg
- En siffra

Mönster 2: En bokstav följt av 6/8 siffror med specialtecken:
- En bokstav (inte en ärendekänslig)
- Ett bindestreck
- Sex eller åtta siffror
- Ett blanksteg
- En siffra

    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_portugal_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_portugal_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Portugal Driver's License Number -->
      <Entity id="977f1e5a-2c33-4bcc-b516-95bb275cff23" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_portugal_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver är s_license_number

- carteira de motorista
- carteira motorista
- carteira de habilitação
- carteira habilitação
- número de licença
- número licença
- permissão de condução
- permissão condução
- Licença condução Portugal
- carta de condução

## <a name="portugal-passport-number"></a>Portugal passnummer

### <a name="format"></a>Format

en bokstav följt av sex siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

en bokstav följt av sex siffror:
  
- en bokstav (inte en ärendekänslig)
- sex siffror
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_portugal_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_portugal_eu_passport_number` hittas. 
- Det reguljära `Regex_eu_passport_date1` uttrycket hittar datum i formatet DD.MM.YYYY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_portugal_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_portugal_eu_passport_number` hittas.
    
```xml
      <!-- Portugal Passport Number -->
      <Entity id="080a52fd-a7bc-431e-b54d-51f08f59db11" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- portugisiska pass
- portuguese passeport
- portugisiska passaporte
- passaporte nº
- passeport nº
- números de passaporte
- portugisiska pass
- número passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="portugal-tax-identification-number"></a>Portugals skatteidentifieringsnummer

### <a name="format"></a>Format

Nio siffror med valfria blanksteg
  
### <a name="pattern"></a>Mönster

- tre siffror
- ett valfritt blanksteg
- tre siffror
- ett valfritt blanksteg
- tre siffror
  
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_portugal_eu_tax_file_number` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_portugal_eu_tax_file_number` från hittas. 
    
En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_portugal_eu_tax_file_number` innehåll som matchar mönstret. 
    
```xml
      <!-- Portugal Tax Identification Number -->
      <Entity id="65372402-3131-4f1e-9983-4439841d1f15" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

- cpf #
- cpf
- nif #
- nif
- número de identificação fisca
- numero fiscal
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #


## <a name="romania-drivers-license-number"></a>Rumäniens körkortsnummer

### <a name="format"></a>Format

ett tecken följt av åtta siffror
  
### <a name="pattern"></a>Mönster

ett tecken följt av åtta siffror:
- en bokstav (inte en teckenkänslig) eller en siffra 
- åtta siffror
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_romania_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_romania_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Romania Driver's License Number -->
      <Entity id="b5511ace-2fd8-4ae4-b6fc-c7c6e4689e3c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_romania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver är s_license_number

- permis de som beter sig som en 10-åring
- permisului de-detrare
- permisului-härdare
- permisele de-detserare
- permisele-härdare
- permis-2013

## <a name="romania-personal-numeric-code-cnp"></a>Rumäniens personliga numeriska kod (CNP)
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

13 siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

- en siffra från 1–9
- Sex siffror som representerar födelsedatum (DSMMMDD)
- två siffror, som kan vara 01-52 eller 99
- fyra siffror

### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_romania_eu_national_id_card` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_romania_eu_national_id_card` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_romania_eu_national_id_card` innehåll som matchar mönstret. 
    
```xml
      <!-- Romania Personal Numerical Code (CNP) -->
      <Entity id="eb5fa399-fe28-4c67-8188-d63a616ed89c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- cnp #
- cnp
- cod identificare personal
- cod numeric personal
- cod unic identificare
- codnumericpersonal #
- codul fiscal nr.
- identificarea fiscalista nr #
- id-ul taxei
- insurance number (försäkringsnummer)
- insurancenumber #
- national id #
- national id
- national identification number
- numør identificare personal
- num ør identitate
- numør personal unic
- numøridentitate #
- numøridentitate
- numørpersonalunic #
- numørpersonalunic
- numøru de identificare fiscalista
- numørul de identificare fiscalista
- personlig numerisk kod
- fäst #
- fäst
- tax file no
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #
- unikt ID-nummer
- unikt identitetsnummer
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>Rumänien, passnummer

### <a name="format"></a>Format

Åtta eller nio siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

Åtta eller nio siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_romania_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_romania_eu_passport_number` hittas. 
- Det reguljära uttrycket hittar datum i `Regex_romania_eu_passport_date` formatet DD MMM/MMM YY (Exempel- 01 FEB/10 FEB) eller ett nyckelord `Keywords_eu_passport_date` från hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_romania_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_romania_eu_passport_number` hittas. 
    
```xml
      <!-- Romania Passport Number -->
      <Entity id="5d31b90c-7fe2-4a76-a14b-767b8fd19d6c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_romania_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numşrul paşaportului numarul pasaportului numerele paşaportului Paşaport nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="russia-passport-number-domestic"></a>Ryssland passnummer inrikes
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

10-siffrigt nummer

### <a name="pattern"></a>Mönster

10-siffrigt nummer:

- två siffror
- Ett valfritt blanksteg eller bindestreck
- två siffror
- ett valfritt blanksteg
- sex siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Regex-Regex_Russian_Passport_Number_Domestic hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_Russian_Passport_Number hittas.

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

- passnummer
- passport no
- pass #
- passport id
- passportno #
- passportnumber #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>Ryssland passnummer internationellt
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

niosiffrigt nummer

### <a name="pattern"></a>Mönster

niosiffriga nummer:

- två siffror
- Ett valfritt blanksteg eller bindestreck
- sju siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Regex-Regex_Russian_Passport_Number_International hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_Russian_Passport_Number hittas.

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- passnummer
- passport no
- pass #
- passport id
- passportno #
- passportnumber #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="saudi-arabia-national-id"></a>Saudiarabiens national-ID

### <a name="format"></a>Format

10 siffror

### <a name="pattern"></a>Mönster

10 siffror i följd

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_saudi_arabia_national_id hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_saudi_arabia_national_id hittas.

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- ID-kort 
- Jag kortnummer 
- ID-nummer 
- الوطنية الهوية بطاقة رقم 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>Nummer till Singapore national registration identity card (NRIC)

### <a name="format"></a>Format

nio bokstäver och siffror

### <a name="pattern"></a>Mönster

- Nio bokstäver och siffror:
- bokstaven "F", "G", "S" eller "T" (inte ärendekänsligt) 
- sju siffror 
- en alfabetisk kontrollsiffra

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_singapore_nric hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_singapore_nric hittas.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_singapore_nric hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord
   
#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- National Registration Identity Card 
- Identitetskortsnummer 
- NRIC 
- IC 
- Foreign Identification Number 
- FIN 
- 身份证 
- 身份證 

## <a name="slovakia-drivers-license-number"></a>Slovakiens körkortsnummer

### <a name="format"></a>Format

ett tecken följt av sju siffror
  
### <a name="pattern"></a>Mönster

ett tecken följt av sju siffror
  
- en bokstav (inte en teckenkänslig) eller en siffra
- sju siffror 
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_slovakia_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_slovakia_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Slovakia Driver's License Number -->
      <Entity id="14240c22-b6de-4ce5-a90b-137f74252513" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver är s_license_number

- vodičskč prezzz
- vodičské prepé
- vodičského prezu
- vodičskčch prezenzov

## <a name="slovakia-personal-number"></a>Personligt nummer för Slovakien
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

nio eller tio siffror som innehåller valfritt omslag
  
### <a name="pattern"></a>Mönster

- Sex siffror som representerar födelsedatum
- valfritt snedstreck (/)
- tre siffror
- en valfri kontrollsiffra
  
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_slovakia_eu_national_id_card` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_slovakia_eu_national_id_card` från hittas. 
    
En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_slovakia_eu_national_id_card` innehåll som matchar mönstret. 
    
```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- födelsedatum
- číslo národnej identifikačnej karty
- číslo občianského prezuzu
- daňové číslo
- id-nummer
- identification no
- identification number
- identifikačná karta č
- identifikačné číslo
- identitetskortnr
- Identitetskortsnummer
- národná identifikačná značka č
- national number
- nationalnumber #
- nemzeti személyazonosító igaávány
- personalidnumber #
- rč
- janne cislo
- né číslo
- personnummer
- ssn #
- ssn
- személyi igaénvány szám
- személyi igaénvány száma
- személyigavezvány szám
- tax file no
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #

## <a name="slovakia-passport-number"></a>Slovakiens passnummer

### <a name="format"></a>Format

en siffra eller bokstav följt av sju siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

en siffra eller bokstav (inte en teckenkänslig) följt av sju siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_slovakia_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_slovakia_eu_passport_number` hittas. 
- Det reguljära `Regex_eu_passport_date1` uttrycket hittar datum i formatet DD.MM.YYYY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_slovakia_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_slovakia_eu_passport_number` hittas. 
    
```xml
      <!-- Slovakia Passport Number -->
      <Entity id="238e1f08-d80e-4793-af33-9b57918335b7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo pasu
- čísla pasov
- pas č.
- Passeport n°
- n° Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="slovenia-drivers-license-number"></a>Sloveniens körkortsnummer

### <a name="format"></a>Format

Nio siffror utan blanksteg och avgränsare
  
### <a name="pattern"></a>Mönster

nio siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_slovenia_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_slovenia_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Slovenia Driver's License Number -->
      <Entity id="d5bc089a-f2ee-433d-a6b1-5c253051d6f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver är s_license_number

- vozniško dovoljenje
- vozniška številka-licens
- vozniških dovoljenj
- številka vozniškega dovoljenja
- številke vozniških dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>Slovenska unik master number
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

13 siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

13 siffror i det angivna mönstret:
  
- sju siffror som motsvarar födelsedatumet (DDMMLLL) där "LLL" motsvarar de tre sista siffrorna i födelsedatumet 
- två siffror som motsvarar födelsedatumet "50"
- Tre siffror som motsvarar en kombination av kön och serienummer för personer som föds på samma dag (000-499 för man och 500-999 för kvinna)
- en checksiffra
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_slovenia_eu_national_id_card` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_slovenia_eu_national_id_card` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_slovenia_eu_national_id_card` innehåll som matchar mönstret. 
    
```xml
      <!-- Slovenia Unique Master Citizen Number -->
      <Entity id="68948b27-803d-41e4-adf1-13e05eb541bb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena številka glavnega dršavljana
- emšo
- enotna maticna številka obcana
- id card
- identification number
- identifikacijska številka
- identitetskort
- nacionalna id
- nacionalni potni-lista
- national id
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- personlig kod
- personligt nummer
- personlig numerisk kod
- številka dršavljana
- unikt telefonnummer för medborgare
- unikt ID-nummer
- unikt identitetsnummer
- unikt huvudpersonnummer
- unikt registreringsnummer
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>Slovenska passnummer

### <a name="format"></a>Format

Två bokstäver följt av sju siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

Två bokstäver följt av sju siffror:
  
- bokstaven "P"
- en versal
- sju siffror
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_slovenia_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_slovenia_eu_passport_number` hittas. 
- Det reguljära `Regex_eu_passport_date1` uttrycket hittar datum i formatet DD.MM.YYYY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_slovenia_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_slovenia_eu_passport_number` hittas. 
    
```xml
      <!-- Slovenia Passport Number -->
      <Entity id="235b7976-7bbe-4df5-bb40-08678e749d1a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavckti
- potnilista #
- datum rojstva
- potnilista
- številke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="slovenia-tax-identification-number"></a>Slovenska skatteidentifieringsnummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

Åtta siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

- en siffra från 1–9
- sex siffror
- en checksiffra
  
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_slovenia_eu_tax_file_number` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_slovenia_eu_tax_file_number` från hittas. 
    
En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_slovenia_eu_tax_file_number` innehåll som matchar mönstret. 
    
```xml
      <!-- Slovenia Tax Identification Number -->
      <Entity id="e47b071e-c352-4d70-8241-8c215ad65505" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
          <Match idRef="Keywords_slovenia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
- tax file no
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #


## <a name="south-africa-identification-number"></a>South Africa identification number

### <a name="format"></a>Format

13 siffror som kan innehålla blanksteg

### <a name="pattern"></a>Mönster

13 siffror:
- Sex siffror i formatet YYMMDD, som är födelsedatumet 
- fyra siffror 
- en ensiffrig indikator 
- siffran "8" eller "9" 
- en siffra, som är en kontrollsummasiffra

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_south_africa_identification_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_south_africa_identification_number hittas.
- Kontrollsumman passeras.

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord
   
#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Identitetskort
- ID
- Identifiering 
   
## <a name="south-korea-resident-registration-number"></a>Registreringsnummer för sydkoreanska invånare

### <a name="format"></a>Format

13 siffror som innehåller ett bindestreck

### <a name="pattern"></a>Mönster

13 siffror:
- Sex siffror i formatet YYMMDD, som är födelsedatumet 
- ett bindestreck 
- en siffra som bestäms av talet och kön 
- fyrsiffrig födelsedatumskod 
- en siffra som används för att särskilja personer som de föregående siffrorna är identiska för 
- en kontrollsiffra.

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_south_korea_resident_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_south_korea_resident_number hittas.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_south_korea_resident_number hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord
   
#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- National ID card 
- Medborgares registreringsnummer 
- Jumin deungnok beonho 
- RRN 
- 주민등록번호

## <a name="spain-drivers-license-number"></a>Spaniens körkortsnummer

### <a name="format"></a>Format

Åtta siffror följt av ett tecken
  
### <a name="pattern"></a>Mönster

Åtta siffror följt av ett tecken:
  
- åtta siffror 
- en siffra eller bokstav (inte en teckenkänslig)
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen eller  `Func_spain_eu_DL_and_NI_number_citizen` hittar innehåll som matchar `Func_spain_eu_DL_and_NI_number_foreigner` mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_spain_eu_driver's_license_number` hittas. 

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen eller  `Func_spain_eu_DL_and_NI_number_citizen` hittar innehåll som matchar `Func_spain_eu_DL_and_NI_number_foreigner` mönstret. 
    
```xml
      <!-- Spain Driver's License Number -->
      <Entity id="d5a82922-b501-4f40-8868-341321146aa2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver är s_license_number

- permiso de guación
- permiso ención
- licencia de memoarir
- licencia-härdarna
- permiso-uppserer
- permiso de en-
- permisos de memoarir
- permisos-enkärer
- carnet-memoarer
- carnet de memoarir
- licencia de manejo
- licencia manejo

## <a name="spain-dni"></a>Spanien DNI
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

Åtta siffror följt av ett tecken
  
### <a name="pattern"></a>Mönster

sju siffror följt av ett tecken
  
- åtta siffror
- Ett valfritt blanksteg eller bindestreck
- en bkryssbokstav (inte fallkänslig)
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen eller  `Func_spain_eu_DL_and_NI_number_citizen` hittar innehåll som matchar `Func_spain_eu_DL_and_NI_number_foreigner` mönstret. 
- Ett nyckelord  `Keywords_spain_eu_national_id_card"` från hittas. 

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen eller  `Func_spain_eu_DL_and_NI_number_citizen` hittar innehåll som matchar `Func_spain_eu_DL_and_NI_number_foreigner` mönstret. 

    
```xml
      <!-- Spain DNI -->
      <Entity id="8e6251b9-47b4-40e8-a42b-0f80876be192" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- dni #
- dni
- dninúmero #
- documento nacional de identidad
- identidad único
- identidadúnico #
- insurance number (försäkringsnummer)
- national identification number
- national identity
- nationalid #
- nationalidno #
- nie #
- nie
- nienúmero #
- número de identificación
- número nacional identidad
- personal identification number
- personlig identitet, inte
- unikt identitetsnummer
- uniqueid #

## <a name="spain-passport-number"></a>Spanien passnummer

### <a name="format"></a>Format

En kombination av åtta eller nio tecken med bokstäver och siffror utan blanksteg eller avgränsare
  
### <a name="pattern"></a>Mönster

En kombination av åtta eller nio tecken med bokstäver och siffror:
  
- två siffror eller bokstäver 
- en siffra eller bokstav (valfritt)
- sex siffror
    
### <a name="checksum"></a>Kontrollsumma

Ej tillämpligt
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_spain_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_spain_eu_passport_number` hittas. 
- Det reguljära `Regex_spain_eu_passport_date` uttrycket hittar datum i formatet DD-MM-YYYY eller ett nyckelord från `Keywords_eu_passport_date` hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_spain_eu_passport_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_passport_number` eller `Keywords_spain_eu_passport_number` hittas.
    
```xml
      <!-- Spain Passport Number -->
      <Entity id="d17a57de-9fa5-4e9f-85d3-85c26d89686e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_spain_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- españa pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte no
- Passeport n°
- n° Passeport
- pasaporte no.
- pasaporte n°
- spanien pass

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="spain-social-security-number-ssn"></a>Spaniens personnummer (SSN)


### <a name="format"></a>Format

11–12 siffror

### <a name="pattern"></a>Mönster

11–12 siffror:
- två siffror 
- ett snedstreck (valfritt) 
- sju till åtta siffror 
- ett snedstreck (valfritt) 
- två siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_spanish_social_security_number hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.
- - Ett nyckelord  `Keywords_spain_eu_ssn_or_equivalent` från hittas. 

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_spanish_social_security_number hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
    <!-- Spain SSN -->
    <Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" >
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spanish_social_security_number" />
          <Match idRef="Keywords_spain_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spanish_social_security_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- ssn
- ssn #
- socialsecurityno
- social security no
- personnummer
- número de la seguridad social

## <a name="spain-tax-identification-number"></a>Skatteidentifieringsnummer för Spanien
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

sju eller åtta siffror och en eller två bokstäver i det angivna mönstret
  
### <a name="pattern"></a>Mönster

Spanska naturliga personer med ett Spanien National Identity Card:
  
- åtta siffror 
- en versaler (gemener och versaler) 
    
Non-resident Sstraards utan ett Spain National Identity Card
  
- en versaler "L" (gemener/versaler) (gemener/VERSALER) (gemener och versaler) (gemener/VERSALER)
- sju siffror
- en versaler (gemener och versaler) 
    
Invånare som är under 14 år utan spaniens nationalidentitetskort:
  
- en versal "K" (gemener/versaler) (gemener och versaler) (gemener och versaler)
- sju siffror 
- en versaler (gemener och versaler)
    
Foreigners with a Foreigner's Identification Number
  
- en versal som är "X", "Y" eller "Z" (gemener och versaler) 
- sju siffror
- en versaler (gemener och versaler) 
    
Foreigners without a Foreigner's Identification Number
  
- en versal som är "M" (gemener/versaler) (gemener och versaler) (gemener och versaler) 
- sju siffror
- en versaler (gemener och versaler) 
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen eller  `Func_spain_eu_tax_file_number` hittar innehåll som matchar `Func_spain_eu_DL_and_NI_number_citizen` mönstret. 
- Ett nyckelord  `Keywords_spain_eu_tax_file_number` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen eller  `Func_spain_eu_tax_file_number` hittar innehåll som matchar `Func_spain_eu_DL_and_NI_number_citizen` mönstret. 
    
```xml
      <!-- Spain Tax Identification Number -->
      <Entity id="10f0d113-b0e1-47dc-872a-a4f45b9376a3" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- cif
- cifid #
- cifnúmero #
- número de contribuyente
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- tax file no
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #


## <a name="sql-server-connection-string"></a>SQL Server en anslutningssträng

### <a name="format"></a>Format

Strängen "Användar-ID", "Användar-ID", "uid" eller "UserId" följt av de tecken och strängar som beskrivs i mönstret nedan.

### <a name="pattern"></a>Mönster

- strängen "Användar-ID", "Användar-ID", "uid" eller "UserId"
- valfri kombination av 1–200 gemener eller versaler, siffror, symboler, specialtecken eller blanksteg
- strängen "Lösenord" eller "pwd" där "pwd" inte föregås av en gemener
- Ett likhetstecken (=)
- alla tecken som inte är ett dollartecken ($), procenttecken (%) större än symbol (>), symbol (@), citattecken ("), semikolon (;), vänster klammerparentes([) eller vänster klammerparentes ({)
- valfri kombination av 7–128 tecken som inte är ett semikolon (;), snedstreck (/) eller citattecken (")
- Semikolon (;) eller citattecken (")

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket CEP_Regex_SQLServerConnectionString hittar innehåll som matchar mönstret.
- Ett nyckelord CEP_GlobalFilter hittades inte.
- Det reguljära uttrycket CEP_PasswordPlaceHolder hittar inte innehåll som matchar mönstret.
- Det reguljära uttrycket CEP_CommonExampleKeywords hittar inte innehåll som matchar mönstret.

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- some-password
- någotlösenord
- secretPassword
- exempel

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

(Tekniskt sett identifierar den här typen av känslig information dessa nyckelord med hjälp av ett reguljärt uttryck, inte en nyckelordslista.)

- Lösenord eller pwd följt av 0-2 blanksteg, ett likhetstecken (=), 0-2 blanksteg och en asterisk (*) -ELLER-
- Lösenord eller pwd följt av:
    - Likhetstecken (=)
    - Mindre än-symbol (<)
    - En kombination av 1–200 tecken som är versaler eller gemener, siffror, asterisk (*), bindestreck (-), understrykning (_) eller blanksteg
    - Större än-symbol (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Tekniskt sett identifierar den här typen av känslig information dessa nyckelord med hjälp av ett reguljärt uttryck, inte en nyckelordslista.)

- contoso
- fabrikam
- northwind
- begränsat läge (sandbox)
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="sweden-drivers-license-number"></a>Sverigedrivrutinens licensnummer

### <a name="format"></a>Format

tio siffror som innehåller ett bindestreck
  
### <a name="pattern"></a>Mönster

tio siffror som innehåller ett bindestreck:
  
- sex siffror 
- ett bindestreck
- fyra siffror
    
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära  `Regex_sweden_eu_driver's_license_number` uttrycket hittar innehåll som matchar mönstret. 
- Ett nyckelord från  `Keywords_eu_driver's_license_number` eller `Keywords_sweden_eu_driver's_license_number` hittas. 
    
```xml
      <!-- Sweden Driver's License Number -->
      <Entity id="70088720-90dd-47f5-805e-5525f3567391" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_sweden_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver är s_license_number

- ajokortti
- permis de som beter sig som en 10-åring
- ajokortin numero
- kuljettajat lic.
- drivere lic.
- körkort
- numolurul permisului de det finns en 10-åring
-  שאָפער דערלויבעניש נומער
- lic.
-  דריווערס דערלויבעניש
- körkortsnummer

## <a name="sweden-national-id"></a>National ID för Sverige

### <a name="format"></a>Format

10 eller 12 siffror och en valfri avgränsare

### <a name="pattern"></a>Mönster

10 eller 12 siffror och en valfri avgränsare:
- två siffror (valfritt) 
- Sex siffror i datumformat YYMMDD 
- avgränsare av "-" eller "+" (valfritt)
- fyra siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar `Func_swedish_national_identifier` innehåll som matchar mönstret.
- Ett nyckelord `Keywords_swedish_national_identifier` från hittas
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar `Func_swedish_national_identifier` innehåll som matchar mönstret.
- Kontrollsumman passeras.


```xml
    <!-- Sweden National ID -->
    <Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
        <Match idRef="Keywords_swedish_national_identifier" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_swedish_national_identifier" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- id no
- id-nummer
- id #
- identification no
- identification number
- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- identitetsdokument
- identity no
- identitetsnummer
- id-nummer
- personligt ID
- personnummer #
- personnummer
- skatteidentifikationsnummer
   
## <a name="sweden-passport-number"></a>Sverige passnummer

### <a name="format"></a>Format

åtta siffror

### <a name="pattern"></a>Mönster

åtta siffror i följd

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- det reguljära uttrycket Regex_sweden_passport_number hittar innehåll som matchar mönstret.
- ett nyckelord från `Keywords_eu_passport_number` eller `Keyword_sweden_passport` hittas.
- det reguljära uttrycket hittar ett datum i formatet `Regex_sweden_eu_passport_date` DD MMM/MMM YY (01 JAN/JAN 12) eller ett `Keywords_eu_passport_date` nyckelord från hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- det reguljära uttrycket Regex_sweden_passport_number hittar innehåll som matchar mönstret.
- ett nyckelord från `Keywords_eu_passport_number` eller `Keyword_sweden_passport` hittas.


```xml
    <!-- Sweden Passport Number -->
    <Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_sweden_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord
   
#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- registreringskort för registrering av registrering av registreringsnummer
- G3 bearbetningsavgifter
- flera inmatningar
- Numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passnummer
- pass nr
- visa visa för visa
- y. visas
- enskild post
- sverige pass
- visakrav
- visa processing
- visatyp

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- utfärdandedatum
- utgångsdatum


## <a name="sweden-tax-identification-number"></a>Skatteidentifieringsnummer i Sverige
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

10 siffror och en symbol i det angivna mönstret
  
### <a name="pattern"></a>Mönster

10 siffror och en symbol:
  
- Sex siffror som motsvarar födelsedatumet (AMMDD) 
- ett plustecken eller minustecken
- Tre siffror som gör ID-numret unikt där: 
  - för nummer som utfärdats före 1990, den sjunde och åttonde siffran identifiera födelsedatum eller foreign-born people
  - Siffran i den nionde positionen anger kön med antingen udda för man eller till och med för kvinna
- en checksiffra
    
### <a name="checksum"></a>Kontrollsumma

Ja
  
### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_sweden_eu_tax_file_number` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_sweden_eu_tax_file_number` från hittas. 
    
En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_sweden_eu_tax_file_number` innehåll som matchar mönstret. 
    
```xml
      <!-- Sweden Tax Identification Number -->
      <Entity id="139acba0-a5bc-4fbb-876d-f7a493ae8a40" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_sweden_eu_telephone_number" />
            <Match idRef="Keywords_sweden_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- personligt ID-nummer
- personnummer
- skatt id nummer
- skatt identifikation
- 855 000 000 0
- sverige tin
- skattefil
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- tax number
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #


## <a name="swift-code"></a>SWIFT-kod

### <a name="format"></a>Format

fyra bokstäver följt av 5–31 bokstäver eller siffror

### <a name="pattern"></a>Mönster

fyra bokstäver följt av 5–31 bokstäver eller siffror:
- bankkod på fyra bokstäver (inte ärendekänsligt) 
- ett valfritt blanksteg 
- 4–28 bokstäver eller siffror (BBAN (Basic Bank Account Number)) 
- ett valfritt blanksteg 
- en till tre bokstäver eller siffror (resten av BBAN)

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_swift hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_swift hittas.

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord
   
#### <a name="keyword_swift"></a>Keyword_swift

- internationella standardiseringsorganisationen 9362
- iso 9362
- iso9362
- swift #
- swiftkod
- swiftnummer
- swiftroutingsnummer
- swift-kod
- swift-nummer #
- swift-routningsnummer
- bic-nummer
- bic-kod
- bic-bic #
- bic-bic #
- bank identifier code
- Organisation internationale de normalisation 9362
- rapide #
- code SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- # <a name="bic"></a>BIC
- code identificateur de banque
- SWIFTコード
- SWIFT番号
- BIC番号
- BICコード
- SWIFT コード
- SWIFT-番号
- BIC-番号
- BIC-コード
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>Schweiz SSN AHV-nummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

13-siffrigt nummer

### <a name="pattern"></a>Mönster

13-siffrigt nummer:

- tre siffror – 756
- en valfri punkt
- fyra siffror
- en valfri punkt
- fyra siffror
- en valfri punkt
- två siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_swiss_social_security_number_ahv hittar innehåll som matchar mönstret.
- Ett nyckelord från Keywords_swiss_social_security_number_ahv hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_swiss_social_security_number_ahv hittar innehåll som matchar mönstret.

```xml
      <!-- Swiss SSN AHV Number -->
      <Entity id="277cfa4b-6eaa-4a1b-9492-099dec849971" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
          <Match idRef="Keywords_swiss_social_security_number_ahv" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ahv
- ssn
- pid
- insurance number (försäkringsnummer)
- personalidno #
- personnummer
- personligt ID-nummer
- personal identification no.
- insuranceno #
- uniqueidno #
- unikt ID-nummer.
- avs-nummer
- personlig identitet, ingen versicherungsnummer
- identifikationsnummer
- zigartige identit utsämta niyo
- sozialversicherungsnummer
- identification personnelle id
- numéro de sécurité sociale

   
## <a name="taiwan-national-identification-number"></a>Taiwans national identification number

### <a name="format"></a>Format

en bokstav (på engelska) följt av nio siffror

### <a name="pattern"></a>Mönster

en bokstav (på engelska) följt av nio siffror:
- en bokstav (på engelska, inte den där den är det. 
- siffran "1" eller "2" 
- åtta siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_taiwanese_national_id hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_taiwanese_national_id hittas.
- Kontrollsumman passeras.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_taiwanese_national_id hittar innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
       <Pattern confidenceLevel="75">
         <IdMatch idRef="Func_taiwanese_national_id" />
       </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_taiwan_national_id"></a>Keyword_taiwan_national_id

- 身份證字號 
- 身份證 
- 身份證號碼 
- 身份證號 
- 身分證字號 
- 身分證 
- 身分證號碼 
- 身份證號 
- 身分證統一編號 
- 國民身分證統一編號 
- 簽名 
- 蓋章 
- 簽名或蓋章 
- 簽章   
   
## <a name="taiwan-passport-number"></a>Taiwan passport number

### <a name="format"></a>Format

- biometrisk passnummer: nio siffror
- icke-biometrisk passnummer: nio siffror

### <a name="pattern"></a>Mönster
biometrisk pass nummer:
- tecknet "3" 
- åtta siffror

icke-biometrisk passnummer:
- nio siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_taiwan_passport hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_taiwan_passport hittas.

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- ROC-passnummer 
- Passnummer 
- Passport no 
- Passport Num 
- Pass # 
- 护照 
- 中華民國護照 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>Taiwan-intjänat certifikat (ARC/TARC) nummer

### <a name="format"></a>Format

10 bokstäver och siffror

### <a name="pattern"></a>Mönster

10 bokstäver och siffror:
- Två bokstäver (inte versaler och teckenkänsliga) 
- åtta siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_taiwan_resident_certificate hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_taiwan_resident_certificate hittas.

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_taiwan_resident_certificate"></a>Keyword_taiwan_resident_certificate

- Inebonnat certifikat 
- Intreifit certifikat 
- Resident Cert. 
- ID-kort 
- Alien Resident Certificate 
- ARC 
- Taiwan Area Resident Certificate 
- TARC 
- 居留證 
- 外僑居留證 
- 台灣地區居留證 

## <a name="thai-population-identification-code"></a>Identifieringskod för thailändska

### <a name="format"></a>Format

13 siffror

### <a name="pattern"></a>Mönster

13 siffror:
- första siffran är inte noll eller nio 
- 12 siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_Thai_Citizen_Id hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_Thai_Citizen_Id hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_Thai_Citizen_Id hittar innehåll som matchar mönstret.

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_thai_citizen_id"></a>Keyword_thai_citizen_Id

- ID-nummer
- Id-nummer
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
  
## <a name="turkish-national-identification-number"></a>Turkiska national identification number

### <a name="format"></a>Format

11 siffror

### <a name="pattern"></a>Mönster

11 siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_Turkish_National_Id hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_Turkish_National_Id hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_Turkish_National_Id hittar innehåll som matchar mönstret.

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_turkish_national_id"></a>Keyword_turkish_national_id

- TC Kimlik No
- TC Kimlik nuısı
- Vatandaşlık nuısı
- Vatandaşlık no

## <a name="uk-drivers-license-number"></a>Storbritannien driver's license number

### <a name="format"></a>Format

Kombination av 18 bokstäver och siffror i det angivna formatet

### <a name="pattern"></a>Mönster

18 bokstäver och siffror:
- Fem bokstäver (inte ärendekänsliga) eller siffran "9" i stället för en bokstav. 
- En siffra.
- Fem siffror i datumformatet MMDDY för födelsedatumet. Det sjunde tecknet ökas med 50 om drivrutinen är kvinna. för prov, 51 till 62 i stället för 01 till 12.
- Två bokstäver (inte teckenkänsliga) eller siffran "9" i stället för en bokstav. 
- Fem siffror.

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar `Func_uk_drivers_license` innehåll som matchar mönstret.
- Ett nyckelord `Keywords_eu_driver's_license_number` från hittas.
- Kontrollsumman passeras.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar `Func_uk_drivers_license` innehåll som matchar mönstret.
- Kontrollsumman passeras.

```xml
    <!-- U.K. Driver's License Number -->
    <Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75" relaxProximity="true" >
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_drivers_license" />
          <Match idRef="Keywords_eu_driver's_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_uk_drivers_license" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver är s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- billicens 
- billicens
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- driver's licen
- kör lic
- kör licens
- billicenser
- billicens
- billicenser
- biltillstånd
- dl no
- dlno
- dl-nummer

   
## <a name="uk-electoral-roll-number"></a>Storbritannien nummer för att samla, rulla ut, 75

### <a name="format"></a>Format

två bokstäver följt av 1–4 siffror

### <a name="pattern"></a>Mönster

Två bokstäver (inte teckenkänsliga) följt av 1–4 siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_uk_electoral hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_uk_electoral hittas.

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- mötesmöte 
- formulär för att skapa en 20 
- register över registrering av registrer 
- roll för underse

   
## <a name="uk-national-health-service-number"></a>Storbritannien national health service number

### <a name="format"></a>Format

10–17 siffror avgränsade med blanksteg

### <a name="pattern"></a>Mönster

10–17 siffror:
- antingen 3 eller 10 siffror 
- ett blanksteg 
- tre siffror 
- ett blanksteg 
- fyra siffror

### <a name="checksum"></a>Kontrollsumma

Ja

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_uk_nhs_number hittar innehåll som matchar mönstret.
- Något av följande är sant:
    - Ett nyckelord från Keyword_uk_nhs_number hittas.
    - Ett nyckelord från Keyword_uk_nhs_number1 hittas.
    - Ett nyckelord från Keyword_uk_nhs_number_dob hittas.
- Kontrollsumman passeras.

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord
   
#### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- national health service 
- nhs 
- hälsotjänstutfärdare 
- hälsoutfärdare

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient-ID 
- patientidentifiering 
- patientnr 
- patientnummer

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- GP 
- DOB 
- D.O.B 
- Födelsedatum 
- Födelsedatum 
   
## <a name="uk-national-insurance-number-nino"></a>Storbritannien national insurance number (NINO)
Den här typen av känslig information ingår i den nationella identifieringstypen (EU). Det är tillgängligt som en fristående typ av känslig information.

### <a name="format"></a>Format

Sju tecken eller nio tecken avgränsade med blanksteg eller streck

### <a name="pattern"></a>Mönster

två möjliga mönster:

- två bokstäver (giltiga NINOs använder bara vissa tecken i det här prefixet, som det här mönstret verifierar, inte de är det.
- sex siffror
- antingen "A", "B", "C" eller "D" (t.ex. prefixet tillåts bara vissa tecken i suffixet, inte teckenkänsliga)

ELLER

- två bokstäver
- blanksteg eller streck
- två siffror
- blanksteg eller streck
- två siffror
- blanksteg eller streck
- två siffror
- blanksteg eller streck
- antingen "A", "B", "C" eller "D"

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_uk_nino hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_uk_nino hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_uk_nino hittar innehåll som matchar mönstret.

```xml
    <!-- U.K. NINO -->
    <Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Match idRef="Keyword_uk_nino" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number
- national insurance contributions
- protection act
- insurance
- personnummer
- insurance application
- medical application
- social insurance
- medical attention
- social security
- great britain
- NI-nummer
- NI No.
- NI #
- NI #
- insurance #
- insurancenumber
- national en #
- national den 10:e

    
## <a name="uk-unique-taxpayer-reference-number"></a>Storbritannien Unique Taxpayer-referensnummer
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

10 siffror utan blanksteg och avgränsare
 
  
### <a name="pattern"></a>Mönster

10 siffror
  
### <a name="checksum"></a>Kontrollsumma

Nej
  
### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen hittar  `Func_uk_eu_tax_file_number` innehåll som matchar mönstret. 
- Ett nyckelord  `Keywords_uk_eu_tax_file_number` från hittas. 
    
```xml
      <!-- U.K. Unique Taxpayer Reference Number -->
      <Entity id="ad4a8116-0db8-439a-b545-6d967642f0ec" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- tax number
- skattefil
- tax id
- tax identification no
- tax identification number
- tax no #
- tax no
- skatteregistreringsnummer
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- räknare #
- räknare
- tin-id
- tin no
- tin #

## <a name="us-bank-account-number"></a>U.S. bank account number

### <a name="format"></a>Format

6-17 siffror

### <a name="pattern"></a>Mönster

6–17 siffror i följd

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_usa_bank_account_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_usa_Bank_Account hittas.

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_usa_bank_account"></a>Keyword_usa_Bank_Account

- Checking Account Number 
- Checking Account 
- Checking Account # 
- Checking Acct Number 
- Checking Acct # 
- Checking Acct No. 
- Checking Account No. 
- Bankkontonummer 
- Bankkonto # 
- Bank Acct Number 
- Bank Acct # 
- Bank Acct No. 
- Bank Account No. 
- Savings Account Number 
- Savings Account. 
- Savings Account # 
- Savings Acct Number 
- Savings Acct # 
- Savings Acct No. 
- Savings Account No. 
- Debit Account Number 
- Debit Account 
- Debit Account # 
- Debit Acct Number 
- Debit Acct # 
- Debit Acct No. 
- Debit Account No. 

## <a name="us-drivers-license-number"></a>U.S. driver's license number

### <a name="format"></a>Format

Beror på delstat

### <a name="pattern"></a>Mönster

beror på delstat – till exempel New York:
- Nio siffror med formatet sss sss sss matchar.
- Nio siffror med ssssssssss matchar inte.

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_new_york_drivers_license_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_[state_name]_drivers_license_name hittas.
- Ett nyckelord från Keyword_us_drivers_license hittas.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_new_york_drivers_license_number hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_[state_name]_drivers_license_name hittas.
- Ett nyckelord från Keyword_us_drivers_license_abbreviations hittas.
- Inget nyckelord från Keyword_us_drivers_license hittas.

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- DL 
- DLS 
- CDL 
- CDLS 
- ID 
- IDs 
- DL # 
- DLS # 
- CDL # 
- CDLS # 
- ID #
- IDs # 
- ID-nummer 
- ID-nummer 
- LIC 
- LIC # 

#### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- DriverLic 
- DriverLics 
- DriverLicense 
- DriverLicenses 
- Driver Lic 
- Driver Lics 
- Driver License 
- Driver Licenses 
- DriversLic 
- DriversLics 
- DriversLicense 
- DriversLicenses 
- Drivers Lic 
- Drivers Lics 
- Drivers License 
- Drivers Licenses 
- Driver'Lic 
- Driver'Lics 
- Driver'License 
- Driver'Licenses 
- Driver' Lic 
- Driver' Lics 
- Driver' License 
- Driver' Licenses
- Driver'sLic 
- Driver'sLics 
- Driver'sLicense 
- Driver'sLicenses 
- Driver's Lic 
- Driver's Lics 
- Driver's License 
- Driver's Licenses 
- identification number 
- identification numbers 
- identification # 
- id card 
- id cards 
- identification card 
- identification cards 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- Driver Lic # 
- Driver Lics # 
- Driver License # 
- Driver Licenses # 
- DriversLic # 
- DriversLics # 
- DriversLicense # 
- DriversLicenses # 
- Drivers Lic # 
- Drivers Lics # 
- Drivers License # 
- Drivers Licenses # 
- Driver'Lic # 
- Driver'Lics # 
- Driver'License # 
- Driver'Licenses # 
- Driver' Lic # 
- Driver' Lics # 
- Driver' License # 
- Driver' Licenses # 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver's Lic # 
- Driver's Lics # 
- Driver's License # 
- Driver's Licenses # 
- id card # 
- id cards # 
- identification card # 
- identification cards # 


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_[state_name]_drivers_license_name

- delstatsförkortning (t.ex. "NY") 
- delstatsnamn (till exempel "New York")

## <a name="us-individual-taxpayer-identification-number-itin"></a>U.S. individual taxpayer identification number (ITIN)

### <a name="format"></a>Format

Nio siffror som börjar med "9" och innehåller "7" eller "8" som fjärde siffra, alternativt formaterade med blanksteg eller streck

### <a name="pattern"></a>Mönster

formaterat:
- siffran "9" 
- två siffror 
- blanksteg eller streck 
- a "7" eller "8" 
- en siffra 
- blanksteg eller streck 
- fyra siffror

oformaterad:
- siffran "9" 
- två siffror 
- a "7" eller "8" 
- fem siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_formatted_itin hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_itin hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_unformatted_itin hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_itin hittas.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_formatted_itin eller Func_unformatted_itin hittar innehåll som matchar mönstret.

```xml
    <!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
    <Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_formatted_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_unformatted_itin" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_itin"></a>Keyword_itin

- taxpayer 
- tax id 
- tax identification 
- itin 
- i.t.i.n.
- ssn 
- tin 
- social security 
- tax payer 
- itins 
- taxid 
- individual taxpayer 


## <a name="us-social-security-number-ssn"></a>U.S. social security number (SSN)

### <a name="format"></a>Format

nio siffror, som kan vara i ett formaterat eller oformaterat mönster

> [!NOTE]
> Om det har utfärdats före mitten av 2011 har SSN stark formatering där vissa delar av numret måste faller inom vissa intervall för att vara giltigt (men det finns ingen kontrollsumma).

### <a name="pattern"></a>Mönster

fyra funktioner söker efter SSN i fyra olika mönster:
- Func_ssn söker efter SSN med stark formatering före 2011 som är formaterade med streck eller blanksteg (s-ss-s eller s)
- Func_unformatted_ssn söker efter SSN med stark formatering före 2011 som är oformaterade som nio siffror i följd (sss)
- Func_randomized_formatted_ssn söker efter SSN efter 2011 som är formaterade med streck eller blanksteg (s-ss-s eller s s)
- Func_randomized_unformatted_ssn söker efter SSN efter 2011 som är oformaterade som nio siffror i följd (ss)

### <a name="checksum"></a>Kontrollsumma

Nej


### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_ssn hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_ssn hittas.

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_unformatted_ssn hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_ssn hittas.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen Func_randomized_formatted_ssn hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_ssn hittas.

En DLP-princip har låg konfidens för att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_randomized_unformatted_ssn hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_ssn hittas.


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_ssn"></a>Keyword_ssn

- SSA-nummer
- personnummer
- social security #
- social security #
- social security no
- Social Security #
- Soc Sec
- SSN
- SSNS
- SSN #
- SS #
- SSID
   
## <a name="us--uk-passport-number"></a>U.S. / Storbritannien passnummer

### <a name="format"></a>Format

nio siffror

### <a name="pattern"></a>Mönster

nio siffror i följd

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har hög säkerhet att den har upptäckt den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_usa_uk_passport hittar innehåll som matchar mönstret.
- Ett nyckelord från `Keywords_eu_passport_number` eller `Keywords_uk_eu_passport_number` hittas.
- Ett nyckelord `Keywords_eu_passport_date` från hittas

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Funktionen för Func_usa_uk_passport hittar innehåll som matchar mönstret.
- Ett nyckelord från `Keywords_eu_passport_number` eller `Keywords_uk_eu_passport_number` hittas.

```xml
    <!-- U.S. / U.K. Passport Number -->
    <Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
       <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- pass #
- pass #
- passportid
- pass
- passportno
- passport no
- passportnumber
- passnummer
- passportnumbers
- passnummer

#### <a name="keywords_uk_eu_passport_number"></a>Keywords_uk_eu_passport_number

- brittisk pass 
- uk passport 


## <a name="ukraine-passport-domestic"></a>Ukrainas pass inrikes
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

nio siffror

### <a name="pattern"></a>Mönster

nio siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Regex-Regex_Ukraine_Passport_Domestic hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_Ukraine_Passport_Domestic hittas.

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- ukraina-pass
- passnummer
- passport no
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>Ukraina passport international
Den här typen av känslig information kan bara användas i:
- principer för dataförlustskydd
- policyer för kommunikationsefterlevnad
- informationsstyrning
- hantering av arkivhandlingar
- Säkerhet för Microsoft-molnappen

### <a name="format"></a>Format

Alfanumeriskt mönster med åtta tecken

### <a name="pattern"></a>Mönster

Alfanumeriskt mönster med åtta tecken:
- två bokstäver eller siffror
- sex siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Regex-Regex_Ukraine_Passport_International hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_Ukraine_Passport_International hittas.

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- ukraina-pass
- passnummer
- passport no
- паспорт України
- номер паспорта
