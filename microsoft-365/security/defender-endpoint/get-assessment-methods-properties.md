---
title: Exportera utvärderingsmetoder och egenskaper per enhet
description: Ger information om API:er som hämtar "Hantering av hot och säkerhetsrisker"-data. Det finns olika API-anrop för att få olika typer av data. I allmänhet innehåller varje API-anrop nödvändiga data för enheter i organisationen.
keywords: api, apis, exportutvärdering, per enhetsutvärdering, per maskinutvärdering, sårbarhetsutvärderingsrapport, enhet genom sårbarhetsanalys, enhetsproblemrapport, säker konfigurationsutvärdering, säker konfigurationsrapport, säkerhetsproblem för programvara, sårbarhetsrapport för programvara, sårbarhetsrapport efter maskin,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 3e5a91a33a4207daa30f1054f03655c846d297ec
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022444"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>Exportera utvärderingsmetoder och egenskaper per enhet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="api-description"></a>API-beskrivning

Tillhandahåller metod- och egenskapsinformation om API:er som hämtar Hantering av hot och säkerhetsrisker data per enhet. Det finns olika API-anrop för att få olika typer av data. I allmänhet innehåller varje API-anrop nödvändiga data för enheter i organisationen.

> [!Note]
>
> Om inget annat anges exporteras alla utvärderingsmetoder som **_listas för fullständig export_** **_och_** efter enhet (kallas även **_per enhet)._**

Du kan använda exportutvärderings-API:er för att hämta (exportera) olika typer av information:

- [1. Exportera utvärdering av säkra konfigurationer](#1-export-secure-configurations-assessment)

- [2. Exportera utvärdering av programvara för lager](#2-export-software-inventory-assessment)

- [3. Utvärdering av eventuella säkerhetsproblem med programvara](#3-export-software-vulnerabilities-assessment)

API:er som motsvarar exportinformationstyperna beskrivs i avsnitten 1, 2 och 3.

För varje metod finns det olika API-anrop för att få olika typer av data. Eftersom mängden data kan vara stor kan den hämtas på två sätt:

- **JSON-svar**  API:t hämtar alla data i organisationen som JSON-svar. Den här metoden är bäst _för små organisationer med mindre än 100 K-enheter._ Svaret är paginerat, så du kan använda \@ odata.nextLink-fältet från svaret för att hämta nästa resultat.

- **via filer** Med den här API-lösningen kan du hämta stora mängder data snabbare och mer tillförlitligt. Därför rekommenderas det för stora organisationer med fler än 100 K-enheter. Detta API hämtar alla data i organisationen som nedladdningsfiler. Svaret innehåller URL:er för att ladda ned alla data från Azure-lagring. Med det här API:t kan du ladda ned alla dina data Azure-lagring enligt följande:

  - Anropa API:t för att få en lista med hämtningsadresser med alla dina organisationsdata.

  - Ladda ned alla filer med hjälp av URL:er för nedladdning och bearbeta dina data som du vill.

Data som samlas in (med hjälp av _Antingen JSON-svar_ eller _via_ filer ) är den aktuella ögonblicksbilden av den aktuella statusen, och innehåller inte historiska data. För att kunna samla in historiska data måste kunderna spara data i sina egna datalagringar.

## <a name="1-export-secure-configurations-assessment"></a>1. Exportera utvärdering av säkra konfigurationer

Returnerar alla konfigurationer och deras status per enhet.

### <a name="11-methods"></a>1.1 Metoder

Metod | Datatyp | Beskrivning
:---|:---|:---
Exportera säker konfigurationsutvärdering **(JSON-svar)** | Säker konfiguration efter enhetssamling. Mer information: [1.2 Egenskaper (JSON-svar)](#12-properties-json-response) | Returnerar en tabell med en post för varje unik kombination av DeviceId, ConfigurationId. API:t hämtar alla data i organisationen som JSON-svar. Den här metoden är bäst för små organisationer med mindre än 100 K-enheter. Svaret är paginerat, så du kan använda fältet @odata.nextLink från svaret för att hämta nästa resultat.
Exportera utvärdering av säker konfiguration **(via filer)** | Säker konfiguration efter enhetssamling. Mer information: [1.3 Egenskaper (via filer)](#13-properties-via-files) | Returnerar en tabell med en post för varje unik kombination av DeviceId, ConfigurationId. Med den här API-lösningen kan du hämta stora mängder data snabbare och mer tillförlitligt. Därför rekommenderas det för stora organisationer med fler än 100 K-enheter. Detta API hämtar alla data i organisationen som nedladdningsfiler. Svaret innehåller URL:er för att ladda ned alla data från Azure-lagring. Med detta API kan du ladda ned alla data från Azure-lagring enligt följande: 1.  Anropa API:t för att få en lista med hämtningsadresser med alla dina organisationsdata. 2.  Ladda ned alla filer med hjälp av URL:er för nedladdning och bearbeta dina data som du vill.

### <a name="12-properties-json-response"></a>1.2 Egenskaper (JSON-svar)

Egenskap (ID) | Datatyp | Beskrivning
:---|:---|:---
ConfigurationCategory | sträng | Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller
ConfigurationId | sträng | Unikt ID för en viss konfiguration
ConfigurationImpact | sträng | Klassificerad inverkan av konfigurationen på det övergripande konfigurationsresultatet (1–10)
ConfigurationName | sträng | Visningsnamn för konfigurationen
ConfigurationSubcategory | sträng | Underkategori eller undergrupp som konfigurationen tillhör. I många fall beskrivs specifika funktioner.
DeviceId | sträng | Unikt ID för enheten i tjänsten.
DeviceName | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten.
IsApplicable | bool | Anger om konfigurationen eller principen är tillämplig
IsCompliet | bool | Anger om konfigurationen eller principen är korrekt konfigurerad
IsExpectedUserImpact | bool | Anger om det kommer att finnas någon påverkan på användaren om konfigurationen ska användas
OSPlatform | sträng | Operativsystemets plattform som körs på enheten. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. Mer information finns i Operativsystem och plattformar som stöds av TVM.
RbacGroupName | sträng | Den rollbaserade åtkomstkontrollgruppen (RBAC). Om enheten inte är tilldelad till någon RBAC-grupp kommer värdet att vara "Ej tilldelat". Om organisationen inte innehåller några RBAC-grupper blir värdet "Ingen".
RekommendationReference | sträng | En referens till det rekommendations-ID som hör till den här programvaran.
Tidsstämpel | sträng | Senaste gången konfigurationen sågs på enheten

### <a name="13-properties-via-files"></a>1.3 Egenskaper (via filer)

Egenskap (ID) | Datatyp | Beskrivning
:---|:---|:---
Exportera filer | \[matrissträng\] | En lista med hämtnings-URL:er för filer som innehåller den aktuella ögonblicksbilden av organisationen.
GeneratedTime | sträng | Tidpunkten då exporten skapades.

## <a name="2-export-software-inventory-assessment"></a>2. Exportera utvärdering av programvara för lager

Returnerar alla installerade program och deras information på varje enhet.

### <a name="21-methods"></a>2.1 Metoder

Metod | Datatyp | Beskrivning
:---|:---|:---
Exportera utvärdering av programvaruinventering **(JSON-svar)** | Inventering av programvara efter enhetssamling. Se: [2.2 Egenskaper (JSON-svar)](#22-properties-json-response) | Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName och SoftwareVersion. API:t hämtar alla data i organisationen som JSON-svar. Den här metoden är bäst för små organisationer med mindre än 100 K-enheter. Svaret är paginerat, så du kan använda fältet @odata.nextLink från svaret för att hämta nästa resultat.
Exportera utvärdering av programvaruinventering **(via filer)** | Inventering av programvara efter enhetsfiler. Mer information: [2.3 Egenskaper (via filer)](#23-properties-via-files) | Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName och SoftwareVersion. Med den här API-lösningen kan du hämta stora mängder data snabbare och mer tillförlitligt. Därför rekommenderas det för stora organisationer med fler än 100 K-enheter. Detta API hämtar alla data i organisationen som nedladdningsfiler. Svaret innehåller URL:er för att ladda ned alla data från Azure-lagring. Med detta API kan du ladda ned alla data från Azure-lagring enligt följande: 1.  Anropa API:t för att få en lista med hämtningsadresser med alla dina organisationsdata. 2.  Ladda ned alla filer med hjälp av URL:er för nedladdning och bearbeta dina data som du vill.

### <a name="22-properties-json-response"></a>2.2 Egenskaper (JSON-svar)

Egenskap (ID) | Datatyp | Beskrivning
:---|:---|:---
DeviceId | sträng | Unikt ID för enheten i tjänsten.
DeviceName | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten.
DiskPaths | Matris[sträng]  | Disk bevis för att produkten är installerad på enheten.
EndOfSupportDate | sträng | Datumet då supporten för den här programvaran har eller kommer att upphöra.
EndOfSupportStatus | sträng | Supportstatusen avslutas. Kan innehålla följande möjliga värden: Ingen, EOS-version, Kommande EOS-version, EOS-programvara, kommande EOS-programvara.
ID | sträng | Unikt ID för posten.
NumberOfWeaknesses | int|Antal svagheter på den här programvaran på den här enheten
OSPlatform | sträng | Operativsystemets plattform som körs på enheten. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. Mer information finns i Operativsystem och plattformar som stöds av TVM.
RbacGroupName | sträng | Den rollbaserade åtkomstkontrollgruppen (RBAC). Om enheten inte är tilldelad till någon RBAC-grupp kommer värdet att vara "Ej tilldelat". Om organisationen inte innehåller några RBAC-grupper blir värdet "Ingen".
RegistryPaths | Matris[sträng] | Register bevis för att produkten är installerad på enheten.
SoftwareFirstSeenTimestamp | sträng | Första gången programvaran sågs på enheten.
SoftwareName | sträng | Namnet på programvaruprodukten.
SoftwareVendor | sträng | Namnet på programvaruleverantören.
SoftwareVersion | sträng | Versionsnummer för programvaran.

### <a name="23-properties-via-files"></a>2.3 Egenskaper (via filer)

Egenskap (ID) | Datatyp | Beskrivning
:---|:---|:---
Exportera filer | \[matrissträng\] | En lista med hämtnings-URL:er för filer som innehåller den aktuella ögonblicksbilden av organisationen.
GeneratedTime | sträng | Tidpunkten då exporten skapades.

## <a name="3-export-software-vulnerabilities-assessment"></a>3. Utvärdering av eventuella säkerhetsproblem med programvara

Returnerar alla kända säkerhetsproblem på en enhet och deras information för alla enheter.

### <a name="31-methods"></a>3.1 Metoder

Metod | Datatyp | Beskrivning
:---|:---|:---
Exportera utvärdering av säkerhetsproblem för **programvara (JSON-svar)** | Undersökningssamling Se: [3.2 Egenskaper (JSON-svar)](#32-properties-json-response) | Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. API:t hämtar alla data i organisationen som JSON-svar. Den här metoden är bäst för små organisationer med mindre än 100 K-enheter. Svaret är paginerat, så du kan använda fältet @odata.nextLink från svaret för att hämta nästa resultat.
Utvärdering av export av säkerhetsproblem **för programvara (via filer)** | Undersökningsentitet Se: [3.3 Egenskaper (via filer)](#33-properties-via-files) | Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. Med den här API-lösningen kan du hämta stora mängder data snabbare och mer tillförlitligt. Därför rekommenderas det för stora organisationer med fler än 100 K-enheter. Detta API hämtar alla data i organisationen som nedladdningsfiler. Svaret innehåller URL:er för att ladda ned alla data från Azure-lagring. Med detta API kan du ladda ned alla data från Azure-lagring enligt följande: 1.  Anropa API:t för att få en lista med hämtningsadresser med alla dina organisationsdata. 2.  Ladda ned alla filer med hjälp av URL:er för nedladdning och bearbeta dina data som du vill.
**Delta vid utvärdering** av säkerhetsproblem i exportprogramvara **(JSON-svar)** | Undersökningssamling Se: [3.4 Properties Delta export (JSON-svar)](#34-properties-delta-export-json-response) | Returnerar en tabell med en post för varje unik kombination av: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId och EventTimestamp. <br><br> API:t hämtar data i organisationen som JSON-svar. Svaret är paginerat, så du kan använda fältet @odata.nextLink från svaret för att hämta nästa resultat. Till skillnad från sårbarhetsbedömningen för hela programvaran (JSON-svar), som används för att erhålla en hel ögonblicksbild av säkerhetsproblem i programvarans bedömning av organisationen per enhet, används deltaexport-OData API-anropet för att bara hämta ändringar som har skett mellan ett valt datum och dagens datum (delta-API-anropet). I stället för att få en fullständig export med en stor mängd data varje gång får du bara specifik information om nya, korrigerade och uppdaterade svagheter. Deltaexport av OData API-anrop kan också användas för att beräkna olika KPI:er, till exempel "hur många säkerhetsproblem har åtgärdats?" eller "hur många nya säkerhetsproblem lades till i organisationen?"  <br><br> Eftersom deltaexporten av OData API-anropet för svagheter i programvaran returnerar data endast för ett måldatum betraktas det inte som en _fullständig export._

### <a name="32-properties-json-response"></a>3.2 Egenskaper (JSON-svar)

Egenskap (ID) | Datatyp | Beskrivning
:---|:---|:---
CveId | sträng | Unikt ID tilldelat till säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE).
CvssScore | sträng | CVSS-poäng för CVE.
DeviceId | sträng | Unikt ID för enheten i tjänsten.
DeviceName | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten.
DiskPaths | \[Matrissträng\] | Disk bevis för att produkten är installerad på enheten.
ExploitabilityLevel | sträng | Sårbarhetsnivån för detta sårbarhet (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | sträng | Första gången CVE för den här produkten sågs på enheten.
ID | sträng | Unikt ID för posten.
LastSeenTimestamp | sträng | Senaste gången CVE sågs på enheten.
OSPlatform | sträng | Operativsystemets plattform som körs på enheten. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. Mer information finns i Operativsystem och plattformar som stöds av TVM.
RbacGroupName | sträng | Den rollbaserade åtkomstkontrollgruppen (RBAC). Om enheten inte är tilldelad till någon RBAC-grupp kommer värdet att vara "Ej tilldelat". Om organisationen inte innehåller några RBAC-grupper blir värdet "Ingen".
RekommendationReference | sträng | En referens till det rekommendations-ID som hör till den här programvaran.
RecommendedSecurityUpdate | sträng | Namn eller beskrivning av säkerhetsuppdateringen som tillhandahålls av programvaruleverantören för att hantera problemet.
RecommendedSecurityUpdateId | sträng | Identifierare för tillämpliga säkerhetsuppdateringar eller identifierare för motsvarande vägledning eller kunskapsbas (KB) artiklar
Matrissträng för \[ registersökvägar\] | Register bevis för att produkten är installerad på enheten.
SoftwareName | sträng | Namnet på programvaruprodukten.
SoftwareVendor | sträng | Namnet på programvaruleverantören.
SoftwareVersion | sträng | Versionsnummer för programvaran.
VulnerabilitySeverityLevel | sträng | Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer som påverkas av hotbilden.

### <a name="33-properties-via-files"></a>3.3 Egenskaper (via filer)

Egenskap (ID) | Datatyp | Beskrivning
:---|:---|:---
Exportera filer | \[matrissträng\]  | En lista med hämtnings-URL:er för filer som innehåller den aktuella ögonblicksbilden av organisationen.
GeneratedTime | sträng | Tidpunkten då exporten skapades.

### <a name="34-properties-delta-export-json-response"></a>3.4 Egenskaper (deltaexport-JSON-svar)

Egenskap (ID) | Datatyp | Beskrivning
:---|:---|:---
CveId | sträng | Unikt ID tilldelat till säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE).
CvssScore | sträng | CVSS-poäng för CVE.
DeviceId | sträng | Unikt ID för enheten i tjänsten.
DeviceName | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten.
DiskPaths | Matris[sträng] | Disk bevis för att produkten är installerad på enheten.
EventTimestamp | Sträng | Tidpunkten då deltahändelsen hittades.
ExploitabilityLevel | sträng | Sårbarhetsnivån för detta sårbarhet (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | sträng | Första gången CVE för den här produkten sågs på enheten.
ID | sträng | Unikt ID för posten.  
LastSeenTimestamp | sträng | Senaste gången CVE sågs på enheten.
OSPlatform | sträng | Operativsystemets plattform som körs på enheten. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. Mer information finns i Operativsystem och plattformar som stöds av TVM.
RbacGroupName | sträng | Den rollbaserade åtkomstkontrollgruppen (RBAC). Om enheten inte är tilldelad till någon RBAC-grupp kommer värdet att vara "Ej tilldelat". Om organisationen inte innehåller några RBAC-grupper blir värdet "Ingen".
RekommendationReference | sträng | En referens till det rekommendations-ID som hör till den här programvaran.
RecommendedSecurityUpdate  | sträng | Namn eller beskrivning av säkerhetsuppdateringen som tillhandahålls av programvaruleverantören för att hantera problemet.
RecommendedSecurityUpdateId  | sträng | Identifierare för tillämpliga säkerhetsuppdateringar eller identifierare för motsvarande vägledning eller kunskapsbas (KB) artiklar
RegistryPaths  | Matris[sträng] | Register bevis för att produkten är installerad på enheten.
SoftwareName | sträng | Namnet på programvaruprodukten.
SoftwareVendor | sträng | Namnet på programvaruleverantören.
SoftwareVersion | sträng | Versionsnummer för programvaran.
Status | Sträng | **Ny**   (för en ny säkerhetsrisk som introducerades på en enhet).  **Åtgärdat**   (för ett sårbarhetssproblem som inte finns längre på enheten, vilket innebär att det har åtgärdats). **Uppdaterad**   (för en sårbarhet på en enhet som har ändrats. De möjliga ändringarna är: CVSS-poäng, sårbarhetsnivå, allvarlighetsnivå, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).
VulnerabilitySeverityLevel | sträng | Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer som påverkas av hotbilden.

## <a name="see-also"></a>Se även

- [Exportera utvärdering av säker konfiguration per enhet](get-assessment-secure-config.md)

- [Exportera utvärdering av programvaruinventering per enhet](get-assessment-software-inventory.md)

- [Exportera bedömningar av säkerhetsproblem för programvara per enhet](get-assessment-software-vulnerabilities.md)

Andra relaterade

- [Riskbaserade hot & hantering av säkerhetsrisker](next-gen-threat-and-vuln-mgt.md)

- [Svagheter i organisationen](tvm-weaknesses.md)
