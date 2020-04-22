---
title: Microsoft Managed Desktop-drift och övervakning
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6e543219bd6a7667febadcdc8f3cff6ab705b8d3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632019"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Desktop-drift och övervakning

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Förändringsledning

I ett tjänsteerbjudande flyttas ansvarsbalansen för sådant som maskinvaruunderhåll och säkerhetsuppdateringar till tjänsteleverantören (Microsoft) i stället för kunden (du). Du måste dock fortfarande se till att programvara från tredje part och anpassad programvara fortsätter att fungera som förväntat när uppdateringar distribueras.

För lokala produkter tar din organisation på sig allt ansvar för att hantera förändringar.

### <a name="balance-of-responsibility"></a>Ansvarsfördelning

Ansvar | Microsofts hanterade skrivbordstjänst | Microsoft 365-klientprogram | Lokala klienter och servrar | Tredje part och anpassad programvara
----- | ----- | ----- | ----- | -----
Tillhandahålla nya funktioner | Microsoft | Microsoft | Både | Kunden
Testa nya funktioner för kvalitetssäkring |  Microsoft | Microsoft | Både | Kunden
Kommunicera om nya funktioner | Både | Både | Både | Kunden
Integrera anpassad programvara | Både | Både | Kunden | Kunden
Installera säkerhetsuppdateringar | Microsoft | Microsoft | Kunden | Kunden
Underhåll systemprogramvara | Microsoft | Microsoft | Kunden | Kunden
Paket för distribution | Microsoft | Microsoft | Kunden | Kunden


### <a name="change-process-overview"></a>Översikt över ändringsprocessen

Här är en sammanfattning av hur ändringsprocessen delas mellan Microsoft och kunder. 



<table>
<tr><th></th><th><p>Microsofts roll:</p></th><th><p>Kundens roll:</p></th></tr>
<tr><td>Före en ändring</td><td><ul><li>Ställ in förväntningar på serviceändringar.</li><li>Meddela kunder 5 dagar i förväg för ändringar som kräver administratörsåtgärder.</li><li>För nödändringar, tillämpa en begränsning innan du meddelar.</li></ul></td><td><ul><li>Förstå vad som väntar för förändringar och kommunikation.</li><li>Läs Microsoft Managed Desktop Message Center regelbundet.</li><li>Granska och uppdatera interna ändringshanteringsprocesser.</li><li>Förstå och kontrollera efterlevnaden av Microsofts krav på hanterade skrivbord. </li><li>Bekräfta och godkänn, när det behövs.</li></ul></td></tr><tr><td>Under en förändring</td><td><ul><li>Släpp och distribuera månatliga säkerhets- och icke-säkerhetsuppdateringar för Windows 10- och Office 365-klienter.</li><li>Övervaka datasignaler och stödköer för påverkan.</li></ul></td><td><ul><li>Kontrollera Microsoft Managed Desktop Message Center och granska eventuell ytterligare information.</li><li>   Vidta alla nödvändiga åtgärder, om tillämpligt, och testprogram.</li><li>Om ett break/fix-scenario upplevs skapar du en supportbegäran.</li></ul></td></tr><tr><td>Efter en förändring</td><td><ul><li>Samla in feedback från kunder för att förbättra distributionen av framtida ändringar.</li><li>Övervaka datasignaler och stödköer för påverkan.</li></ul></td><td><ul><li>Arbeta med personer i organisationen för att anta ändringen.</li><li>   Granska förändrings- och implementeringshanteringsprocesser för möjligheter att öka effektiviteten.</li><li>Ge allmän feedback och specifik feedback i verktyget för administratörsfeedback.</li><li>Utbilda användarna så att de ger appspecifik feedback med hjälp av Windows Feedback Hub och Smile-knappen i Office-appar.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Ändra typer

Det finns flera typer av ändringar som görs i tjänsten regelbundet. Kommunikationskanalen för dessa ändringar och de åtgärder som kunderna ansvarar för varierar.

Alla ändringar har inte samma inverkan på användarna eller kräver åtgärder. Vissa är planerade och vissa oplanerade till sin natur (icke-säkerhetsuppdateringar och säkerhetsuppdateringar är vanligtvis inte planerade). Beroende på typ av ändring kan kommunikationskanalen variera. I följande tabell visas de typer av ändringar som du kan förvänta dig för tjänsten Microsoft Managed Desktop.

|   | Funktionalitet |   Icke-säkerhetsuppdateringar |  Säkerhet
--- | --- | --- | ---
**Typ av ändring** | - Funktionsuppdateringar<br>- Nya funktioner eller applikationer<br>- Föråldrade funktioner | Snabbkorrigeringar för klienter för problem | Säkerhetskorrigeringar
**Varsel** | 5 dagars varsel för ändringar som kräver åtgärder |    Nej, dessa ingår i månadsversionen   | Nej, dessa ingår i månadsversionen 
**Kommunikationskanal** | - Meddelandecenter<br>- E-postvarning | - Meddelandecenter<br>- E-postvarning | - Meddelandecenter<br>- E-postvarning
**Kräver global administratörsåtgärd** | Ibland |  Sällan |    Sällan 
**Typ av åtgärd** | Ändra inställningar | Kommunicera ändringar till användare | Ändra administratörsinställningar     
**Kräver testning** | Kontrollera affärsprogram, inklusive fjärråtkomsttjänster |  Ibland - testa korrigeringen mot processer eller anpassningar |   Sällan 
**Exempel på förändring** | - Funktionsuppdateringar: IT Admin Portal förenklad support biljett inlämning och översyn<br>- Nya funktioner eller program: Halvårsvis lansering av en Windows 10-funktionsuppdatering | Snabbkorrigeringar baserat på kundrapporterade fel |  


## <a name="standard-operating-procedures"></a>Standardrutiner

Tjänsten Microsoft Managed Desktop implementeras och drivs av Microsoft i microsoft-molninstansen där du kan utföra andra administrativa aktiviteter. Microsoft är ensamt ansvarigt för Microsoft Managed Desktop-specifika installationer, konfiguration och drift. 

För lokala produkter tar din organisation på sig allt ansvar för att hantera installation och konfiguration och operativa aktiviteter.

Kategorier |    Microsoft kommer att | Kunden kommer att
--- | --- | ---
Nätverk (proxy, paketinspektion, VPN)  | Ge råd och planera med kunder för att minimera riskerna för företagsanvändare. | - Skapa en supportbegäran som begär information för en planerad konfigurationsändring, inklusive konfigurationsinformation, omfattning, tidslinje och annan relevant information för Microsoft att granska.<br>- Tillämpa endast en ändring när Microsoft Managed Desktop Operations har utvärderat och rekommenderat.
Tjänstkonton |- Implementera, säkert lagra och hantera autentiseringsuppgifterna.<br> - Meddela obehörig åtkomst eller användning av dessa autentiseringsuppgifter till ditt säkerhetsoperationsteam. | - Skapa en supportbegäran som begär information för en planerad konfigurationsändring, inklusive konfigurationsinformation, omfattning, tidslinje och annan relevant information för Microsoft att granska.<br>- Tillämpa endast en ändring när Microsoft Managed Desktop Operations har utvärderat och rekommenderat.<br>- Inte tilldela princip, multifaktorautentisering, villkorlig åtkomst eller programdistribution till Microsoft Managed Desktop Service-konton.<br>- Inte återställa lösenordet eller använda autentiseringsuppgifterna.<br>- Öppna en Sev C-supportbegäran till Microsoft Managed Desktop Operations om misstänkt aktivitet observeras i Intune- eller Azure-granskningsloggar, relaterade till dessa tjänstkonton.
Enhetsgrupper | - Implementera och hantera medlemskap i enheter i Microsoft Managed Desktop-grupper.<br>- Använd Microsoft Managed Desktop-grupperna för att hantera tilldelning och utgivning av konfiguration och uppdateringar till enheter. | - Skapa en supportbegäran som begär information för en planerad konfigurationsändring, inklusive konfigurationsinformation, omfattning, tidslinje och annan relevant information för Microsoft att granska.<br>- Tillämpa endast en ändring när Microsoft Managed Desktop Operations har utvärderat och rekommenderat.<br>- Inte ändra medlemskap i någon Microsoft Managed Desktop grupp.<br>- Använd endast grupperna för att tilldela företagscertifikat för tjänster som VPN, Windows Hello for Business eller e-postkryptering eller konfiguration av företagswi-fi-profil.<br>- Där samhantering finns utesluter du uttryckligen alla Microsoft Managed Desktop-grupper när Configuration Manager-klienten distribueras.
Politik |  - Implementera och hantera Microsoft Managed Desktop-principer som styr konfigurationstillståndet för enheter inom tjänsten.<br>- Distribuera uppdateringar, till princip eller Windows, stegvis med hjälp av enhetsgrupper.<br> - Uttryckligen utesluta inriktning icke-Microsoft Managed Desktop grupper. | - Skapa en supportbegäran som begär information för en planerad konfigurationsändring, inklusive konfigurationsinformation, omfattning, tidslinje och annan relevant information för Microsoft att granska.<br>- Tillämpa endast en ändring när Microsoft Managed Desktop Operations har utvärderat och rekommenderat.<br>- Inte redigera eller tilldela Microsoft Managed Desktop-principer till enheter eller användare som inte hanteras av Tjänsten Microsoft Managed Desktop.
Microsoft Defender Avancerat skydd   | Övervaka och undersöka enheter inom ramen för Microsoft Managed Desktop-tjänsten. | - Skapa en supportbegäran som begär information för en planerad konfigurationsändring, inklusive konfigurationsinformation, omfattning, tidslinje och annan relevant information för Microsoft att granska.<br>- Tillämpa endast en ändring när Microsoft Managed Desktop Operations har bedömt och rekommenderat
Microsoft Store för företag |  Konfigurera och underhåll Windows Autopilot-profilen för Tjänsten Microsoft Managed Desktop. | - Skapa en supportbegäran som begär information för en planerad konfigurationsändring, inklusive konfigurationsinformation, omfattning, tidslinje och annan relevant information för Microsoft att granska.<br>- Tillämpa endast en ändring när Microsoft Managed Desktop Operations har utvärderat och rekommenderat.<br>- Inte ändra konfigurationen av Microsoft Managed Desktop Windows Autopilot-profilen eller lägga till/ta bort tilldelade enheter.
Certifikat | | - Skapa en supportbegäran 60 dagar innan ett certifikat löper ut och begär information om en planerad konfigurationsändring, inklusive konfigurationsinformation, omfattning, tidslinje och annan relevant information för Microsoft att granska.<br>- Tillämpa endast en ändring när Microsoft Managed Desktop Operations har utvärderat och rekommenderat.<br>- Uppdatera alla certifikat som krävs för att konfigurera certifikatprofiler, VPN-profiler och Wi-Fi-profiler.




## <a name="device-wipe-with-factory-reset"></a>Enhetsrensning med fabriksåterställning

Microsoft Managed Desktop Operations Team kan utföra en fabriksåterställning av enheter som är registrerade i tjänsten när det behövs. Detta är användbart om du behöver ge en enhet till en annan anställd, eller om en anställd lämnar företaget. 

Det finns några krav:

- Den globala administratören måste skicka en tjänstbegäran.
- Inkludera enhetens datornamn i begäran.
- Användarkontot måste finnas i Azure AD innan vi återställer enheten.

Managed Desktop Operations-teamet gör följande:

- Slå upp enhetsnamnet i Intune
- Skicka kommandot fabriksåterställning till enheten

>[!NOTE]
>Ta inte bort användarkontot från Azure AD innan enheten återställs. Om användaren inte finns i Azure AD kan Intune inte skicka kommandot fabriksåterställning till enheten. 

Enheten startar i "out of box-upplevelsen" och alla förinstallerade program och inställningar kommer att tillämpas igen. Användaren av enheten måste ange inledande installationsinformation igen. 

När enheten har återställts kan du ge den till en annan person i organisationen. Ingen av den tidigare användarens data eller företagsdata kommer att finnas på enheten. Nästa användare kommer att gå igenom samma process som den tidigare personen gjorde med en ny Microsoft Managed Desktop-enhet.

BitLocker är en viktig komponent för datasäkerhet i den här processen. Med BitLocker-kryptering på Microsoft Managed Desktop-enheter förblir data på enheten säkra även efter att enheten har fabriksåterställts. Data som fanns på enheten kommer inte att vara tillgängliga för nästa användare av enheten. Mer information finns i [BitLocker översikt](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).

Mer information finns i [Fabriksåterställning av en enhet](https://docs.microsoft.com/intune/remote-actions/devices-wipe#factory-reset-a-device). 