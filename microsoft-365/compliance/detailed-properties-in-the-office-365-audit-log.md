---
title: Detaljerade egenskaper i granskningsloggen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: Den här artikeln innehåller beskrivningar av ytterligare egenskaper som ingår när du exporterar resultat för Office 365 i granskningsloggposten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69a34f4de948bc9533ef2872d94171134e50ffea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162238"
---
# <a name="detailed-properties-in-the-audit-log"></a>Detaljerade egenskaper i granskningsloggen

När du exporterar resultatet av en granskningsloggsökning från Säkerhets- och & efterlevnadscenter kan du ladda ned alla resultat som uppfyller dina sökvillkor. Det gör du genom att **välja Exportera resultat** Ladda ned alla \> **resultat** på sidan **Granskningsloggsökning.** Mer information finns i Söka [i granskningsloggen](search-the-audit-log-in-security-and-compliance.md).
  
 När du exporterar alla resultat för en granskningsloggsökning kopieras rådata från den enhetliga granskningsloggen till en CSV-fil (kommaavgränsade värden) som laddas ned till den lokala datorn. Den här filen innehåller ytterligare information från varje granskningspost i en kolumn med namnet **Information.** Den här kolumnen innehåller en flervärdesegenskap för flera egenskaper från granskningsloggposten. Var och en **av egenskapen: värdepar** i den här flervärdesegenskapen avgränsas med kommatecken. 
  
I följande tabell beskrivs de egenskaper som ingår (beroende på vilken tjänst som en händelse inträffar) i fleregenskapskolumnen **Information.** I **Office 365 tjänst som har den här egenskapskolumnen** anges tjänsten och typen av aktivitet (användare eller administratör) som innehåller egenskapen. Mer detaljerad information om dessa egenskaper eller om egenskaper som kanske inte finns med i det här avsnittet finns i [API-schema för hanteringsaktivitet.](/office/office-365-management-api/office-365-management-activity-api-schema)
  
> [!TIP]
> Du kan använda funktionen JSON-transformering i Power Query i Excel för att dela upp kolumnen **Information** i flera kolumner så att varje egenskap har en egen kolumn. Då kan du sortera och filtrera en eller flera av dessa egenskaper. Mer information om hur du gör det finns i [Exportera, konfigurera och visa granskningsloggposter](export-view-audit-log-records.md). 
  
|**Egenskap**|**Beskrivning**|**Microsoft 365 tjänst som har den här egenskapen**|
|:-----|:-----|:-----|
|Aktör|Användaren eller tjänstkontot som utförde åtgärden.|Azure Active Directory|
|AddOnName|Namnet på ett tillägg som har lagts till, tagits bort eller uppdaterats i ett team. Typen av tillägg i Microsoft Teams är en robot, en koppling eller en flik.|Microsoft Teams|
|AddOnType|Typen av tillägg som har lagts till, tagits bort eller uppdaterats i ett team. Följande värden anger typ av tillägg.  <br/> **1** – Anger en robot.<br/> **2** – Anger en koppling.<br/> **3** – Anger en flik.|Microsoft Teams|
|AzureActiveDirectoryEventType|Typen av Azure Active Directory händelse. Följande värden anger händelsetypen.  <br/> **0** – Anger en kontoinloggningshändelse.<br/> **1** – Anger en Azure-programsäkerhetshändelse.|Azure Active Directory|
|ChannelGuid|ID för en Microsoft Teams kanal. Teamet som kanalen finns i identifieras med egenskaperna **TeamName** och **TeamGuid.**|Microsoft Teams|
|ChannelName|Namnet på en Microsoft Teams kanal. Teamet som kanalen finns i identifieras med egenskaperna **TeamName** och **TeamGuid.**|Microsoft Teams|
|Klient|Klientenheten, enhetens OS och enhetens webbläsare som används för inloggningshändelsen (till exempel Nokia Lumia 920; Windows Phone 8; IE Mobile 11).|Azure Active Directory|
|ClientInfoString|Information om den e-postklient som användes för att utföra åtgärden, till exempel en webbläsarversion, en Outlook-version och information om mobila enheter|Exchange (postlådeaktivitet)|
|ClientIP|IP-adressen för den enhet som användes när aktiviteten loggades. IP-adressen visas i IPv4- eller IPv6-adressformat.<br/><br/> För vissa tjänster kan värdet som visas i den här egenskapen vara IP-adressen för ett betrott program (till exempel Office på webben-appar) som ringer till tjänsten för en användares räkning och inte IP-adressen för den enhet som används av personen som utförde aktiviteten. <br/><br/>För administratörsaktivitet (eller aktivitet som utförs av ett systemkonto) för Azure Active Directory-relaterade händelser loggas inte IP-adressen och värdet för egenskapen ClientIP är `null` . |Azure Active Directory, Exchange, SharePoint|
|CreationTime|Datum och tid i UTC (Coordinated Universal Time) när användaren utförde aktiviteten.|Alla|
|DestinationFileExtension|Filtillägg för en fil som kopieras eller flyttas. Den här egenskapen visas endast för användaraktiviteterna FileCopied och FileMoved.|SharePoint|
|DestinationFileName|Namnet på filen kopieras eller flyttas. Den här egenskapen visas endast för åtgärderna FileCopied och FileMoved.|SharePoint|
|DestinationRelativeUrl|URL:en för målmappen dit en fil kopieras eller flyttas. Kombinationen av värdena för egenskapen **SiteURL,** **DestinationRelativeURL** och **DestinationFileName** är samma som värdet för egenskapen **ObjectID,** som är den fullständiga sökvägen för filen som kopierades. Den här egenskapen visas endast för användaraktiviteterna FileCopied och FileMoved.|SharePoint|
|EventSource|Identifierar att en händelse inträffade i SharePoint. Möjliga värden är **SharePoint** **ObjectModel.**|SharePoint|
|ExternalAccess|För Exchange av administratörsaktivitet anges om cmdleten körts av en användare i organisationen, av Microsofts datacenterpersonal eller ett tjänstekonto på ett datacenter eller av en delegerad administratör. Värdet **False anger** att cmdleten körts av någon i din organisation. Värdet **True anger** att cmdleten körts av datacenterpersonal, ett tjänstekonto på ett datacenter eller en delegerad administratör.  <br/> För Exchange postlådeaktivitet anges om en postlåda har åtkomst till en användare utanför organisationen.|Exchange|
|ExtendedProperties|Utökade egenskaper för en Azure Active Directory händelse.|Azure Active Directory|
|ID|ID för rapportposten. ID:t identifierar den unika rapportposten.|Alla|
|InternalLogonType|Reserverad för intern användning.|Exchange (postlådeaktivitet)|
|ItemType|Typen av objekt som har åtkomst till eller ändrats. Bland de möjliga **värdena** finns File , **Folder**, **Web**, **Site**, **Tenant** och **DocumentLibrary.**|SharePoint|
|LoginStatus|Identifierar inloggningsfel som kan ha inträffat.|Azure Active Directory|
|LogonType|Typen av åtkomst för postlådan. Följande värden anger vilken typ av användare som kom åt postlådan.  <br/><br/> **0** – Anger en postlådas ägare.<br/> **1** – Anger en administratör.<br/> **2** – Anger ett ombud. <br/>**3** – Anger transporttjänsten i Microsoft-datacentret.<br/> **4** – Anger ett tjänstkonto i Microsoft-datacentret. <br/>**6** – Anger en delegerad administratör.|Exchange (postlådeaktivitet)|
|MailboxGuid|Det Exchange GUID för postlådan som kom åt.|Exchange (postlådeaktivitet)|
|MailboxOwnerUPN|E-postadressen till den person som äger postlådan som koms åt.|Exchange (postlådeaktivitet)|
|Medlemmar|En lista med användare som har lagts till eller tagits bort från ett team. Följande värden anger vilken rolltyp som tilldelats till användaren.  <br/><br/> **1** – Anger ägarrollen.<br/> **2** – Anger medlemsrollen.<br/> **3** – Anger gästrollen. <br/><br/>Egenskapen Medlemmar innehåller även namnet på organisationen och medlemmens e-postadress.|Microsoft Teams|
|ModifiedProperties (Name, NewValue, OldValue)|Egenskapen ingår för administratörshändelser, till exempel att lägga till en användare som medlem i administratörsgruppen för en webbplats eller en webbplatssamling. Egenskapen innehåller namnet på egenskapen som har ändrats (till exempel gruppen Webbplatsadministratör), det nya värdet för den ändrade egenskapen (till exempel användaren som har lagts till som webbplatsadministratör och det tidigare värdet för det ändrade objektet.|Alla (administratörsaktivitet)|
|ObjectId|Namnet Exchange objektet som ändrades av cmdleten, för administratörens granskningsloggning.  <br/> För SharePoint aktiviteten är den fullständiga URL-sökvägen för filen eller mappen som används av en användare.  <br/> För Azure AD-aktivitet – namnet på användarkontot som ändrades.|Alla|
|Åtgärd|Namnet på användar- eller administratörsaktiviteten. Värdet för den här egenskapen motsvarar värdet som valdes i **listrutan** Aktiviteter. Om **Visa resultat för alla aktiviteter** markerades innehåller rapporten poster för alla användar- och administratörsaktiviteter för alla tjänster. En beskrivning av åtgärder/aktiviteter som loggas i granskningsloggen finns på fliken Granskade aktiviteter i Sök i granskningsloggen [i Office 365](search-the-audit-log-in-security-and-compliance.md).   <br/> För Exchange administratörsaktivitet identifierar den här egenskapen namnet på cmdleten som körts.|Alla|
|OrganizationId|GUID för din organisation.|Alla|
|Sökväg|Namnet på postlådemappen där meddelandet som koms åt finns. Den här egenskapen identifierar också mappen som ett meddelande skapas i eller kopieras/flyttas till.|Exchange (postlådeaktivitet)|
|Parametrar|För Exchange av administratörsaktivitet anger namn och värde för alla parametrar som har använts med cmdleten som identifieras i egenskapen Åtgärd.|Exchange (administratörsaktivitet)|
|RecordType|Typen av åtgärd som anges av posten. Den här egenskapen anger tjänsten eller funktionen som åtgärden utlöstes i. En lista över posttyper och deras motsvarande ENUM-värde (som är värdet som visas i egenskapen **RecordType** i en granskningspost) finns i Posttyp för [granskningslogg.](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)| 
|ResultStatus|Anger om åtgärden (som anges i **egenskapen Åtgärd)** lyckades eller inte.  <br/> För Exchange administratörsaktivitet är värdet antingen **Sant** (lyckades) eller **Falskt** (misslyckades).|Alla  <br/>|
|SecurityComplianceCenterEventType|Anger att aktiviteten var en säkerhets- & händelsen Compliance Center. Alla aktiviteter & Säkerhets- och efterlevnadscenter har värdet **0** för den här egenskapen.|Säkerhets- och efterlevnadscenter|
|SharingType|Typen av delningsbehörigheter som har tilldelats användaren som resursen har delats med. Den här användaren identifieras i **UserSharedWith-egenskapen.**|SharePoint|
|Webbplats|GUID för webbplatsen där filen eller mappen som används av användaren finns.|SharePoint|
|SiteUrl|URL-adressen till webbplatsen där filen eller mappen som används av användaren finns.|SharePoint|
|SourceFileExtension|Filtillägget för filen som användaren hade åtkomst till. Den här egenskapen är tom om objektet som koms åt är en mapp.|SharePoint|
|SourceFileName|Namnet på filen eller mappen som används av användaren.|SharePoint|
|SourceRelativeUrl|URL-adressen till mappen som innehåller filen som används av användaren. Kombinationen av värdena för egenskapen **SiteURL,** **SourceRelativeURL** och **SourceFileName** är samma som värdet för egenskapen **ObjectID,** som är den fullständiga sökvägen för filen som används av användaren.|SharePoint|
|Ämne|Ämnesraden i meddelandet som koms åt.|Exchange (postlådeaktivitet)|
|TabType| Typen av flik som lagts till, tagits bort eller uppdaterats i ett team. Möjliga värden för den här egenskapen är:  <br/><br/> **Excel –** en Excel.  <br/> **Tillägg** – Alla appar från första part och tredje part. som Klassschema, VSTS och Formulär.  <br/> **Anteckningar** – OneNote fliken.  <br/> **Pdfpin** – en PDF-flik.  <br/> **Powerbi** – en Power BI fliken.  <br/> **Powerpointpin** – en PowerPoint flik.  <br/> **Sharepointfiles** – SharePoint fil.  <br/> **Webbsida** – en fäst webbplatsflik.  <br/> **Wiki-flik** – en wiki-flik.  <br/> **Wordpin** – fliken Word.|Microsoft Teams|
|Mål|Användaren som åtgärden (identifierad i **Operation-egenskapen)** utfördes på. Om till exempel en gästanvändare läggs till i SharePoint eller ett Microsoft Team anges den användaren i den här egenskapen.|Azure Active Directory|
|TeamGuid|ID för ett team i Microsoft Teams.|Microsoft Teams|
|TeamName|Namnet på ett team i Microsoft Teams.|Microsoft Teams|
|UserAgent|Information om användarens webbläsare. Den här informationen tillhandahålls av webbläsaren.|SharePoint|
|UserDomain|Identitetsinformation om klientorganisationen för användaren (aktören) som utförde åtgärden.|Azure Active Directory|
|UserId|Användaren som utförde åtgärden (anges i **operation-egenskapen)** som resulterade i att posten loggades. Granskningsposter för aktivitet som utförs av systemkonton (till exempel SHAREPOINT\system eller NT AUTHORITY\SYSTEM) ingår också i granskningsloggen. Ett annat vanligt värde för egenskapen UserId är app@sharepoint. Det här anger att användaren som utförde aktiviteten var ett program som har rätt behörighet i SharePoint för att utföra åtgärder som gäller hela organisationen (till exempel söka på en SharePoint-webbplats eller ett OneDrive-konto) åt en användare, administratör eller tjänst. Mer information finns i [Användaren app\@sharepoint i granskningsposter](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records). |Alla|
|UserKey|Ett alternativt ID för användaren som identifieras i **UserID-egenskapen.** Den här egenskapen fylls till exempel i med ETT PUID (Unikt Passport-ID) för händelser som utförs av användare i SharePoint. Den här egenskapen kan också ange samma värde som egenskapen **UserID** för händelser som inträffar i andra tjänster och händelser som utförs av systemkonton.|Alla|
|UserSharedWith|Användaren som en resurs delades med. Den här egenskapen ingår om värdet för egenskapen **Operation** är **SharingSet.** Den här användaren visas också i **kolumnen Delas** med i rapporten.|SharePoint|
|UserType|Typen av användare som utförde åtgärden. Följande värden anger användartypen. <br/> <br/> **0** – En vanlig användare. <br/>**2** – En administratör i Microsoft 365 organisation. <sup>1</sup> <br/>**3** – En Microsoft-datacenteradministratör eller ett datacentersystemkonto. <br/>**4** – Ett systemkonto. <br/>**5** – Ett program. <br/>**6** – En tjänsts huvudnamn.<br/>**7** – En anpassad princip.<br/>**8** – En systemprincip.|Alla|
|Version|Anger versionsnumret för aktiviteten (identifieras av **egenskapen Operation)** som har loggats.|Alla|
|Arbetsbelastning|Den Microsoft 365 tjänst där aktiviteten inträffade.|Alla|
||||

> [!NOTE]
><sup>1</sup> för Azure Active Directory-relaterade händelser används inte värdet för en administratör i en granskningspost. Granskningsposter för aktiviteter som utförs av administratörer anger att en vanlig användare (till exempel **UserType: 0**) utförde aktiviteten. Egenskapen **UserID** identifierar den person (vanlig användare eller administratör) som utförde aktiviteten.<br/>

Egenskaperna som beskrivs ovan visas också när du klickar på **Mer information när** du visar information om en viss händelse.
  
![Klicka på Mer information om du vill se detaljerade egenskaper för granskningsloggens händelsepost](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)