---
title: Threat Explorer och realtidsidentifieringar, nya till Threat Explorer, ändringar i Threat Explorer, ny i Office 365, Säkerhet, Molnsäkerhet, ny på säkerhet i ATP, nya ATP-funktioner
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: Lär dig mer om Explorer- och &amp; realtidsidentifieringar i Säkerhetsefterlevnadscenter.
ms.openlocfilehash: 3ddcaf4dc457ead7a203e00d71d0d18c23ee6557
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806805"
---
# <a name="threat-explorer-and-real-time-detections"></a>Threat Explorer och identifieringar i realtid

Om din organisation har [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) och du har de behörigheter som [krävs,](#required-licenses-and-permissions)har du antingen **Explorer** eller **realtidsidentifieringar** (tidigare *realtidsrapporter* – [se vad som är nytt!).](#new-features-in-threat-explorer-and-real-time-detections) Gå till **Threat-hantering**i Säkerhets& Compliance Center och välj sedan **Explorer** ELLER **realtidsidentifieringar**. 

|Med ATP Plan 2 ser du:  |Med ATP Plan 1 ser du:  |
|---------|---------|
|![Hot explorer](../../media/threatmgmt-explorer.png)      |![Identifiering i realtid](../../media/threatmgmt-realtimedetections.png)         |

Med Explorer (eller identifiering i realtid) har du en kraftfull rapport som gör det möjligt för ditt Security Operations-team att undersöka och svara på hot effektivt och effektivt. Rapporten liknar följande bild: 

![Gå till \> Utforskaren för hothantering](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Med den här rapporten kan du:
- [Se skadlig kod som har upptäckts av säkerhetsfunktioner i Office 365](#see-malware-detected-in-email-by-technology)
- [Visa data om url:er för nätfiske och klicka på dom](#view-data-about-phishing-urls-and-click-verdict)
- [Starta en automatiserad utrednings- och svarsprocess från en vy i Explorer](#start-automated-investigation-and-response) (endast ATP-plan 2)
- ... [Undersök skadlig e-post och mycket mer!](#more-ways-to-use-explorer-or-real-time-detections)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nya funktioner i Threat Explorer och identifiering i realtid

Tre nya funktioner läggs till threat explorer och identifieringi realtid:
- [Förhandsgranska e-postrubrik och ladda ner e-postkropp](#preview-email-header-and-download-email-body)
- [Tidslinje för e-post](#email-timeline)
- [Klicka på exporturl-klickdata](#export-url-click-data)

Dessa nya funktioner beskrivs nedan.

### <a name="preview-email-header-and-download-email-body"></a>Förhandsgranska e-postrubrik och ladda ner e-postkropp

Möjligheten att förhandsgranska ett e-posthuvud och ladda ned e-postkroppen är nya funktioner som finns i Threat Explorer. Administratörer kan analysera nedladdade rubriker/e-postmeddelanden för hot. Eftersom nedladdning av e-postmeddelanden kan riskera exponering av information, styrs den här processen av roller-baserad åtkomstkontroll (RBAC). En ny roll, *Förhandsgranska,* måste läggas till i en annan Office 365-rollgrupp (till exempel Säkerhetsåtgärder eller säkerhetsadministratör) för att ge möjlighet att hämta e-post och förhandsgranska rubriker i vyn för alla e-postmeddelanden.

Men Explorer (och identifiering i realtid) lägger också till nya nya fält som är utformade för att ge dig en mer komplett bild av var dina e-postmeddelanden landar. En del av målet med denna förändring är att göra jakt lättare för Security Ops människor, men nettoresultatet är att veta platsen för problem e-postmeddelanden på ett ögonkast.

Hur går det till? Leveransstatus är nu uppdelad i två kolumner:

- **Leveransåtgärd** - Vad är statusför det här e-postmeddelandet?
- **Leveransplats** - Var dirigerades det här e-postmeddelandet som ett resultat?

Leveransåtgärd är de åtgärder som vidtas på ett e-postmeddelande på grund av befintliga principer eller identifieringar. Här är de möjliga åtgärder som ett e-postmeddelande kan vidta:

|Levereras  |Skräppost  |Blockerade  |Ersatt  |
|---------|---------|---------|---------|
|E-post levererades till användarens inkorg eller en annan mapp, och användaren kan direkt komma åt den.    | E-post skickades till antingen användarens skräppostmapp eller borttagen mapp, och användaren har tillgång till e-postmeddelanden i dessa mappar.       | Alla e-postmeddelanden som är i karantän, som misslyckades eller har tagits bort och inte är tillgängliga för användaren.     | Alla e-postmeddelanden där skadliga bilagor ersattes av TXT-filer som anger att bilagorna var skadliga.     |

Och här är vad användaren kan se, och vad de inte kan:

|Tillgänglig för slutanvändare  |Otillgänglig för slutanvändare  |
|---------|---------|
|Levereras     | Blockerade        |
|Skräppost     | Ersatt        |

Leveransplatsen visar resultatet av principer och identifieringar som kör efterleverans. Den är kopplad till en leveransåtgärd. Det här fältet har lagts till för att ge insikt i de åtgärder som vidtagits när ett problemmeddelande hittas. Här är de möjliga värdena för leveransplats:

- **Inkorg eller mapp**: E-postmeddelandet är i inkorgen eller en mapp (enligt dina e-postregler).
- **Prem eller extern**: Postlådan finns inte i molnet utan är lokal.
- **Skräppostmapp:** E-postmeddelandet finns i mappen Skräppost för en användare.
- **Mappen Borttagna objekt:** E-postmeddelandet i mappen Borttaget för en användare.
- **Karantän**: E-postmeddelandet i karantän och finns inte i en användares postlåda.
- **Misslyckades**: E-postmeddelandet kunde inte nå postlådan.
- **Tappade:** E-postmeddelandet går vilse någonstans i e-postflödet.

### <a name="email-timeline"></a>Tidslinje för e-post

**E-posttidslinjen** är en annan ny Explorer-funktion som syftar till att göra jaktupplevelsen bättre för administratörer. Det skär ner på randomisering eftersom det finns mindre tid att kontrollera olika platser för att försöka förstå händelsen. När flera händelser inträffar vid eller nära, samtidigt i ett e-postmeddelande visas dessa händelser i en tidslinjevy. Faktum är att vissa händelser som inträffar efter leverans till din e-post kommer att fångas i kolumnen "Special action". Genom att kombinera informationen från tidslinjen för den posten med de särskilda åtgärder som vidtagits för postefterleverans en inblick i hur deras policyer fungerar, var posten slutligen dirigerades, och i vissa fall vad den slutliga bedömningen var.

Mer information om hur du undersöker skadliga e-postmeddelanden finns [i Hitta och undersöka skadlig e-post som levererades i Office 365](https://docs.microsoft.com/office365/securitycompliance/investigate-malicious-email-that-was-delivered).

### <a name="export-url-click-data"></a>Klicka på exporturl-klickdata

Dessutom kommer du nu att kunna exportera rapporter för URL-klick till Microsoft Excel för att visa både deras nätverksmeddelande-ID och deras Click Verdict, vilket gör uppgiften att förstå var webbadressen klickar på trafiken har sitt ursprung lättare. Så här fungerar det. Klicka igenom den här kedjan med hjälp av Threat Management i snabbstart för Office 365:

**Explorer** > **Visa Phish** > Klick Topp**webbadresser** > **eller URL Top Clicks** > Klicka på en post för att öppna URL**utfällbar**

När du klickar på en WEBBADRESS i listan visas en ny exportknapp på utfällbara panelen. Använd den här knappen om du vill flytta data till ett Excel-kalkylblad för enklare rapportering.

Du kan komma till samma plats i rapporten identifiering i realtid enligt följande:

**Explorer** > **Realtidsidentifieringar** > **Visa phish** > **webbadresser** > **toppadresser eller top clicks** > **Klicka på en post för att öppna URL-utfällbara** > navigera till fliken**Klick.**

> [!TIP]
> I nätverksmeddelande-ID mappas klicket tillbaka till specifika e-postmeddelanden när du söker igenom Utforskaren eller tillhörande verktyg från tredje part via Nätverksmeddelande-ID. Genom att söka igenom id-nätverkets meddelande visas det specifika e-postmeddelandet som är associerat med ett klickresultat. När export har, korrelera identifiering av Network Message ID gör för snabbare och mer kraftfull analys.

![tp_ExportClickResultAndNetworkID.png](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Se skadlig kod som upptäckts i e-post efter teknik

Anta att du vill se skadlig kod som har upptäckts i e-post, med Office 365-teknik. Det gör du genom att använda vyn [E-post > malware](threat-explorer-views.md#email--malware) i Explorer (eller identifiering i realtid).

1. Välj **Threat management** > **Explorer** (eller **identifieringar i realtid**i Security & Compliance Center ( )[https://protection.office.com](https://protection.office.com) (I det här exemplet används Explorer.)

2. Välj **E-postmalware** > **Malware**på **Visa-menyn** .<br/>![Visa meny för Utforskaren](../../media/ExplorerViewEmailMalwareMenu.png)<br/>

3. Klicka på **Avsändare**och välj sedan **Grundläggande** > **identifieringsteknik**.<br/>Din identifieringsteknik är nu tillgänglig som filter för rapporten.<br/>![Tekniker för identifiering av skadlig kod](../../media/ExplorerEmailMalwareDetectionTech.png)<br/> 

4. Välj ett alternativ och klicka sedan på **knappen Uppdatera** för att använda filtret.<br/>![Vald detektionsteknik](../../media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

Rapporten uppdateras för att visa de resultat som skadlig kod upptäckts i e-post med det teknikalternativ du valde. Härifrån kan du göra ytterligare analyser.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Visa data om url:er för nätfiske och klicka på dom

Anta att du vill se nätfiskeförsök via webbadresser i e-post, inklusive en lista över webbadresser som var tillåtna, blockerade och åsidosatta. Identifiera webbadresser som klickades kräver [ATP-säkra länkar](atp-safe-links.md) som ska konfigureras. Se till att du har ställt in [ATP Safe Links-principer](set-up-atp-safe-links-policies.md) för skydd av klicktid och loggning av klickdomsdomar från ATP-säkra länkar. 

Om du vill granska fasiga webbadresser i meddelanden och klick på webbadresser i facitmeddelanden använder du vyn [E-post > Phish](threat-explorer-views.md#email--phish) i Explorer (eller identifiering i realtid).

1. Välj **Threat management** > **Explorer** (eller **identifieringar i realtid**i Security & Compliance Center ( )[https://protection.office.com](https://protection.office.com) (I det här exemplet används Explorer.)

2. Välj **E-postphish** > **i** **Visa-menyn.**<br/>![Visa meny för Utforskaren](../../media/ExplorerViewEmailPhishMenu.png)<br/>

3. Klicka på **Avsändare**och välj sedan **webbadresser** > **Klicka dom**.

4. Markera ett eller flera alternativ, till exempel **Blockera och** **Blockera åsidosätts,** och klicka sedan på **knappen Uppdatera** som finns på samma rad som alternativen för att använda filtret. (Uppdatera inte webbläsarfönstret.)<br/>![Webbadresser och klickdomar](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

    Rapporten uppdateras för att visa två olika URL-tabeller på fliken URL under rapporten:

   - **De bästa webbadresserna** är webbadresserna i de meddelanden som du har filtrerat ned till och e-postleveransåtgärden räknas för varje URL. I den phish e-postvyn kommer den här listan vanligtvis att innehålla legitima webbadresser. Angripare inkluderar en blandning av bra och dåliga webbadresser i sina meddelanden för att försöka få dem levererade, men de kommer att göra de skadliga länkarna mer intressant för användaren att klicka. Tabellen med webbadresser sorteras efter totalt antal e-postmeddelanden (OBS: Den här kolumnen visas inte för att förenkla vyn).

   - **De bästa klicken** är webbadresserna för safe links som klickades, sorterade efter totalt antal klick (den här kolumnen visas inte heller för att förenkla vyn). Totalt antal per kolumn anger antalet antal säkra länkar klickdom för varje klickad webbadress. I den phish e-vyn, dessa är oftare misstänkta eller skadliga webbadresser, men kan innehålla rena webbadresser som finns i phish meddelanden. URL-klick på oförpackade länkar visas inte här.
   
   De två URL-tabellerna visar de bästa webbadresserna i nätfiskemeddelanden genom leveransåtgärder och leveransplatser, och de visar URL-klick som blockerades (eller besöktes trots en varning) så att du kan förstå vilka potentiella dåliga länkar som togs emot av användare och interagerade med användare. Härifrån kan du göra ytterligare analyser. Under diagrammet kan du till exempel se de bästa webbadresserna i e-postmeddelanden som har blockerats i organisationens miljö.
   
   ![Explorer-URL:er som har blockerats](../../media/ExplorerPhishClickVerdictURLs.png)
   
   Välj en URL för att visa mer detaljerad information. **I**dialogrutan utfällbar a-postmeddelanden tas filtreringen på e-postmeddelanden bort för att visa hela vyn av webbadressens exponering i din miljö. På så sätt kan du filtrera ned e-postmeddelanden i Explorer till de du är orolig för, hitta specifika webbadresser som är potentiella hot och sedan utöka din förståelse av URL-exponeringen i din miljö (via dialogrutan URL-information) utan att behöva lägga till URL-filter till själva Explorer-vyn.

## <a name="review-email-messages-reported-by-users"></a>Granska e-postmeddelanden som rapporterats av användare

Anta att du vill se e-postmeddelanden som användare i organisationen har rapporterat som skräppost, inte skräppost eller nätfiske med hjälp av [tillägget Rapportmeddelande för Outlook och Outlook på webben](enable-the-report-message-add-in.md). Det gör du genom att använda vyn [E-post > inlämningar](threat-explorer-views.md#email--submissions) i Explorer (eller identifiering i realtid).

1. Välj **Threat management** > **Explorer** (eller **identifieringar i realtid**i Security & Compliance Center ( )[https://protection.office.com](https://protection.office.com) (I det här exemplet används Explorer.)

2. Välj **E-postinlämningar** > **Submissions**på **Visa-menyn** .<br/>![Visa meny för Utforskaren](../../media/ExplorerViewMenuEmailUserReported.png)<br/>

3. Klicka på **Avsändare**och välj sedan **typ Grundläggande** > **rapport**.

4. Välj ett alternativ, till exempel **Phish,** och klicka sedan på **knappen Uppdatera.** <br/>![Användarrapporterade phish](../../media/EmailUserReportedReportType.png)<br/> 

Rapporten uppdateras för att visa data om e-postmeddelanden som personer i organisationen har rapporterat som ett nätfiskeförsök. Du kan använda den här informationen för att göra ytterligare analyser, och vid behov justera dina [ATP-policyer mot nätfiske](set-up-anti-phishing-policies.md).

## <a name="start-automated-investigation-and-response"></a>Starta automatiserad undersökning och svar

> [!NOTE]
> Automatiska undersöknings- och svarsfunktioner finns i **Office 365 ATP Plan 2** och Office **365 E5**.

(NY!) [Automatiserad utredning och svar](automated-investigation-response-office.md) kan spara din säkerhetsverksamhet team mycket tid och ansträngning för att undersöka och mildra cyberattacker. Förutom att konfigurera aviseringar som kan utlösa en säkerhetsspelbok kan du starta en automatisk utrednings- och svarsprocess från en vy i Explorer. 

Mer information om detta finns i [Exempel: En säkerhetsadministratör utlöser en undersökning från Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>Fler sätt att använda Explorer (eller identifieringi realtid)

Förutom de scenarier som beskrivs i den här artikeln har du många fler rapporteringsalternativ tillgängliga med Explorer (eller identifieringi realtid). 
- [Hitta och undersöka skadligt e-postmeddelande som levererades](investigate-malicious-email-that-was-delivered.md)
- [Visa skadliga filer som upptäckts i SharePoint Online, OneDrive och Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Få en översikt över vyerna i Threat Explorer (och identifieringi realtid)](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a>Obligatoriska licenser och behörigheter

Du måste ha [Office 365 ATP](office-365-atp.md) för att hämta Explorer- eller realtidsidentifieringar.
- Explorer ingår i Office 365 ATP Plan 2. 
- Rapporten identifiering i realtid ingår i Office 365 ATP Plan 1.
- Planera att tilldela licenser för alla användare som ska skyddas av Office 365 ATP. (Explorer- eller realtidsidentifieringar visar identifieringsdata för licensierade användare.)

Om du vill visa och använda Explorer- eller realtidsidentifieringar måste du ha rätt behörighet, till exempel de som beviljas en säkerhetsadministratör eller säkerhetsläsare. 

- För Security &amp; Compliance Center måste du ha en av följande roller tilldelad:
    - Organisationshantering
    - Säkerhetsadministratör (detta kan tilldelas i Administrationscentret[https://aad.portal.azure.com](https://aad.portal.azure.com)för Azure Active Directory ())
    - Säkerhetsläsare

- För Exchange Online måste du ha en av följande roller som[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)tilldelats i antingen Administrationscentret för Exchange ( ) eller med PowerShell-cmdlets (se [Exchange Online PowerShell):](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)
    - Organisationshantering
    - Organisationshantering för endast vy
    - Roll för endast visningsmottagare
    - Efterlevnadshantering

Mer information om roller och behörigheter finns i följande resurser:

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
- [Funktionsbehörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a>Vissa skillnader mellan Threat Explorer och identifieringar i realtid

 - Rapporten **identifiering i realtid** är tillgänglig i Office 365 ATP Plan 1, medan Threat **Explorer** är tillgängligt i Office 365 ATP Plan 2.
 - I rapporten identifiering **i realtid** kan du visa identifieringar i realtid. **Threat Explorer** gör detta också, men kan du också visa ytterligare information för en viss attack.
