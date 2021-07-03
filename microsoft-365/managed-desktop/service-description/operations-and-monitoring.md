---
title: Microsoft Hanterat skrivbord åtgärder och övervakning
description: Vem gör vad för olika ändringsprocesser
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: e8fc583feb0d1ae1fc4ec4aa970b9dc19ae46fd9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286903"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Hanterat skrivbord åtgärder och övervakning

<!-- Operations and monitoring: -->

## <a name="change-management"></a>Ändringshantering

Vid tjänster så ligger skiftar ansvaret för saker som underhåll av maskinvara och säkerhetsuppdateringar till tjänsteleverantören (Microsoft) i stället för kunden (du). Du måste dock fortfarande säkerställa att icke-Microsoft- och anpassad programvara fortsätter att fungera som förväntat när uppdateringar distribueras.

För lokala produkter har organisationen allt ansvar för ändringshantering.

### <a name="balance-of-responsibility"></a>Ansvarsfördelning

Ansvar | Microsoft Hanterat skrivbord tjänst | Microsoft 365 klientprogramvara | Lokala klienter och servrar | annan programvara än Microsoft och anpassad programvara
----- | ----- | ----- | ----- | -----
Tillhandahålla nya funktioner | Microsoft | Microsoft | Båda | Kund
Testa nya funktioner för kvalitetskontroll |  Microsoft | Microsoft | Båda | Kund
Kommunicera om nya funktioner | Båda | Båda | Båda | Kund
Integrera anpassad programvara | Båda | Båda | Kund | Kund
Tillämpa säkerhetsuppdateringar | Microsoft | Microsoft | Kund | Kund
Underhålla systemprogramvara | Microsoft | Microsoft | Kund | Kund
Paket för distribution | Microsoft | Microsoft | Kund | Kund

### <a name="change-process-overview"></a>Översikt över ändringsprocessen

Här är en sammanfattning av hur ändringsprocessen delas mellan Microsoft och kunder: 

<table>
<tr><th></th><th><p>Microsofts roll:</p></th><th><p>Kundens roll:</p></th></tr>
<tr><td>Före en ändring</td><td><ul><li>Ange förväntningar för tjänständringar.</li><li>Meddela kunder 5 dagar i förväg för ändringar som kräver åtgärder från administratören.</li><li>För akuta ändringar tillämpar du en minskning innan du meddelar.</li></ul></td><td><ul><li>Förstå vad du kan förvänta dig när det gäller ändringar och kommunikationer.</li><li>Läs Microsoft Hanterat skrivbord meddelandecentret regelbundet.</li><li>Granska och uppdatera interna processer för ändringshantering.</li><li>Förstå och kontrollera efterlevnad Microsoft Hanterat skrivbord krav. </li><li>Bekräfta och godkänn vid behov.</li></ul></td></tr><tr><td>Under en ändring</td><td><ul><li>Släppa och distribuera månatliga säkerhets- och icke-säkerhetsuppdateringar för Windows 10 och Office 365 klienter.</li><li>Övervaka datasignaler och stödköer för påverkan.</li></ul></td><td><ul><li>Kontrollera meddelandecentret Microsoft Hanterat skrivbord granska eventuell ytterligare information.</li><li>Vidta alla åtgärder som krävs, om tillämpligt, och testa program.</li><li>Skapa en supportbegäran om det är problem med avbrott/korrigering.</li></ul></td></tr><tr><td>Efter en ändring</td><td><ul><li>Samla in feedback från kunder för att förbättra framtida ändringar.</li><li>Övervaka datasignaler och stödköer för påverkan.</li></ul></td><td><ul><li>Arbeta med personer i din organisation för att införa ändringen.</li><li>Granska processer för ändrings- och införandehantering för att få effektivitet.</li><li>Ge allmän feedback och specifik feedback i administrationsverktyget för feedback.</li><li>Utbilda användare att ge specifik feedback med hjälp av Windows Feedbackhubben och uttrycksknappen i appen Office appen.</li></ul></td></tr>
<table> 

### <a name="change-types"></a>Ändra typer

Vi gör regelbundet flera olika ändringar av tjänsten. Kommunikationskanalen för ändringarna och de åtgärder som du ansvarar för varierar.

Alla ändringar påverkar inte användarna på samma sätt eller kräver åtgärder. Vissa är planerade och andra är oplanerade (uppdateringar som inte är säkerhetsuppdateringar och säkerhetsuppdateringar är normalt inte planerade). Beroende på typen av ändring kan kommunikationskanalen variera. I följande tabell visas de typer av ändringar som du kan förvänta dig Microsoft Hanterat skrivbord tjänsten.

|   | Funktioner | Uppdateringar som inte är säkerhetsuppdateringar | Säkerhet
--- | --- | --- | ---
**Ändringstyp** | - Funktionsuppdateringar<br>- Nya funktioner eller program<br>- Inaktuella funktioner | Snabbkorrigeringar för klientproblem | Säkerhetsuppdateringar
**Förhandsmeddelande** | Fem dagars förvarning för ändringar som kräver åtgärd | Nej, sådana ändringar inkluderas i den månatliga versionen | Nej, ändringar ingår i den månatliga versionen 
**Kommunikationskanal** | - Meddelandecenter<br>- E-postavisering | - Meddelandecenter<br>- E-postavisering | - Meddelandecenter<br>- E-postavisering
**Kräver åtgärder från global administratör** | Ibland | Sällan | Sällan 
**Typ av åtgärd** | Ändra inställningar | Informera användarna om ändringarna | Ändra administratörsinställningar  
**Kräver testning** | Kontrollera affärsprogram, inklusive tjänster för fjärråtkomst | Ibland – testa korrigeringen med processer eller anpassningar | Sällan 
**Exempel på förändring** | - Funktionsuppdateringar: IT-administratörsportalen för enklare inskickade supportinskick och granskning<br>- Nya funktioner eller program: Semi-Annual av en Windows 10 en funktionsuppdatering | Snabbkorrigeringar baserade på rapporterad kundbugg |

## <a name="standard-operating-procedures"></a>Standardoperativsystemets procedurer

Tjänsten Microsoft Hanterat skrivbord implementeras och drivs av Microsoft i din Microsoft-molninstans där du kan utföra andra administrativa aktiviteter. Microsoft är ensamt ansvarig Microsoft Hanterat skrivbord konfiguration, konfiguration och åtgärd.

För lokala produkter har organisationen allt ansvar för att hantera installation, konfiguration och drift.

Kategorier | Microsoft | Kunden
--- | --- | ---
Nätverk (proxy, paketinspektion, VPN)  | Informera och planera med kunder för att minimera risken för företagsanvändare. | – skapa en supportbegäran och be om information om en planerad konfigurationsändring, inklusive konfigurationsinformation, omfattning, tidslinje och annan relevant information som Microsoft kan granska.<br>- Tillämpa endast en ändring när Microsoft Hanterat skrivbord åtgärder har gjort en bedömning och är informerad.
Tjänstkonton |– Implementera, lagra och hantera autentiseringsuppgifterna på ett säkert sätt.<br> – Kommunicera obehörig åtkomst eller användning av dessa autentiseringsuppgifter till ditt team med säkerhetsåtgärder. | – skapa en supportbegäran och be om information om en planerad konfigurationsändring, inklusive konfigurationsinformation, omfattning, tidslinje och annan relevant information som Microsoft kan granska.<br>- Tillämpa endast en ändring när Microsoft Hanterat skrivbord åtgärder har gjort en bedömning och är informerad.<br>- Tilldela inte princip-, multifaktorautentisering, villkorsstyrd åtkomst eller programdistribution till Microsoft Hanterat skrivbord-tjänstkonton.<br>- Återställ inte lösenordet eller använd autentiseringsuppgifterna.<br>– öppna en Sev C-supportbegäran för Microsoft Hanterat skrivbord Åtgärder om misstänkt aktivitet observeras i Intune- eller Azure-granskningsloggar som är relaterade till dessa tjänstkonton.
Enhetsgrupper | – Implementera och hantera medlemskap för enheter inom Microsoft Hanterat skrivbord grupper.<br>- Använd Microsoft Hanterat skrivbord för att hantera tilldelning och utgivning av konfiguration och uppdateringar på enheter. | – skapa en supportbegäran och be om information om en planerad konfigurationsändring, inklusive konfigurationsinformation, omfattning, tidslinje och annan relevant information som Microsoft kan granska.<br>- Tillämpa endast en ändring när Microsoft Hanterat skrivbord åtgärder har gjort en bedömning och är informerad.<br>- Inte ändra medlemskapet i någon Microsoft Hanterat skrivbord grupp.<br>- Använd endast grupperna för att tilldela företagscertifikat för tjänster som VPN, Windows Hello för företag eller e-postkryptering eller konfiguration Wi-Fi företagsprofil.<br>– Där samtidig hantering finns exkluderar du uttryckligen Microsoft Hanterat skrivbord grupper när du distribuerar Konfigurationshanteraren-klienten.
Principer | - Implementera och hantera Microsoft Hanterat skrivbord som styr konfigurationstillståndet för enheter i tjänsten.<br>- Distribuera uppdateringar till policy eller Windows stegvis med hjälp av enhetsgrupper.<br> – uttryckligen från att rikta Microsoft Hanterat skrivbord grupper. | – skapa en supportbegäran och be om information om en planerad konfigurationsändring, inklusive konfigurationsinformation, omfattning, tidslinje och annan relevant information som Microsoft kan granska.<br>- Tillämpa endast en ändring när Microsoft Hanterat skrivbord åtgärder har gjort en bedömning och är informerad.<br>– Inte redigera Microsoft Hanterat skrivbord tilldela principer till enheter eller användare som inte hanteras Microsoft Hanterat skrivbord tjänsten.
Microsoft Defender för Endpoint | Övervaka och undersöka enheter inom tjänstens Microsoft Hanterat skrivbord. | – skapa en supportbegäran och be om information om en planerad konfigurationsändring, inklusive konfigurationsinformation, omfattning, tidslinje och annan relevant information som Microsoft kan granska.<br>- Tillämpa endast en ändring när Microsoft Hanterat skrivbord åtgärder har gjort en bedömning och informeras
Microsoft Store för företag | Konfigurera och underhålla Windows Autopilot-profilen för Microsoft Hanterat skrivbord tjänsten. | – skapa en supportbegäran och be om information om en planerad konfigurationsändring, inklusive konfigurationsinformation, omfattning, tidslinje och annan relevant information som Microsoft kan granska.<br>- Tillämpa endast en ändring när Microsoft Hanterat skrivbord åtgärder har gjort en bedömning och är informerad.<br>– Inte ändra konfigurationen av Microsoft Hanterat skrivbord Windows Autopilot-profilen eller lägg till/ta bort tilldelade enheter.
Certifikat | | – Skapa en supportbegäran 60 dagar innan ett certifikat upphör att gälla och begär information om en planerad konfigurationsändring, inklusive konfigurationsinformation, omfattning, tidslinje och annan relevant information som Microsoft kan granska.<br>- Tillämpa endast en ändring när Microsoft Hanterat skrivbord åtgärder har gjort en bedömning och är informerad.<br>- Uppdatera alla certifikat som krävs för att konfigurera certifikatprofiler, VPN-profiler och Wi-Fi profiler.

## <a name="device-wipe-with-factory-reset"></a>Enhetsåterställning med fabriksåterställning

Teamet Microsoft Hanterat skrivbord Operations kan utföra en fabriksåterställning av enheter som registrerats i tjänsten vid behov. Återställning är användbart om du behöver ge en enhet till en annan anställd eller om en anställd lämnar företaget.

Det finns några krav:

- Din globala administratör måste skicka en servicebegäran.
- Ta med enhetens datornamn i begäran.
- Användarkontot måste vara i Azure AD innan vi återställer enheten.

Teamet för hanterade skrivbordsåtgärder gör följande:

- Leta upp enhetsnamnet i Intune
- Skicka kommandot för fabriksåterställning till enheten

> [!NOTE]
> Ta inte bort användarkontot från Azure AD innan enheten återställs. Om användaren inte finns i Azure AD kan Intune inte skicka kommandot för fabriksåterställning till enheten.

Enheten startar i "in användningsutrymmet" och alla förinstallerade program och inställningar kommer att tillämpas igen. Användaren av enheten måste ange den första installationsinformationen igen. 

När enheten har återställts kan du ge den till en annan person i organisationen. Ingen av de tidigare användarnas data eller företagsdata finns på enheten. Nästa användare går igenom samma process som den föregående personen gjorde med en ny Microsoft Hanterat skrivbord enhet.

BitLocker är en viktig komponent i datasäkerhet i den här processen. Med BitLocker-kryptering Microsoft Hanterat skrivbord enheter förblir data på enheten säkra även efter att enheten har fabriksåterställts. Data som fanns på enheten blir inte tillgängliga för nästa användare av enheten. Mer information finns i [Översikt över BitLocker.](/windows/security/information-protection/bitlocker/bitlocker-overview)

Mer information finns i [Fabriksåterställning av en enhet](/intune/remote-actions/devices-wipe#factory-reset-a-device).
