---
title: Datamodell för Microsoft 365 användningsanalyser
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 08c5307c-4a6b-4761-8410-a6c96725760f
description: 'Lär dig hur användningsanalyser ansluter till ett API och tillhandahåller månatliga trenden för användningen av olika Microsoft 365-tjänster.  '
ms.openlocfilehash: 877ad005e3ff7f7537247963fafcab5fb1ff6c74
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580756"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Datamodell för Microsoft 365 användningsanalyser

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Data för Microsoft 365 användningsanalystabeller

Microsoft 365 användningsanalyser ansluter till ett API som visar en flerdimensionell datamodell. DE API:er som Microsoft 365 användningsanalyser använder för att generera data kommer från olika, allmänt tillgängliga, Graph-API:er. Funktionen för Själva API:t för Microsoft 365 användningsanalyser är inte tillgänglig i allmänhet.
  
> [!NOTE]
> Mer information finns i Arbeta [med Microsoft 365 användningsrapporter i Microsoft Graph.](/graph/api/resources/report) 
  
Det här API:t innehåller information om månatliga trenden för användningen av de olika Microsoft 365-tjänsterna. Information om exakt vilka data som returneras av API:et finns i tabellen i följande avsnitt.
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Datatabeller som returneras av rapport-API:et för Microsoft 365

|**Tabellnamn**|**Informationen i tabellen**|**Datumintervall**|
|:-----|:-----|:-----|
|Klientorganisationens produktanvändning  <br/> |Innehåller månatliga summeringar av aktiverade, aktiva användare, kvarhållna användare månad för månad, första gången och ackumulerade aktiva användare.  <br/> |Innehåller sammanräknade månatliga data för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens produktaktivitet  <br/> |Innehåller månatliga summering av aktiviteter och antalet aktiva användare för olika aktiviteter i produkterna.  <br/> Se [definition av aktiv användare](active-user-in-usage-reports.md) om du vill ha information om aktiviteterna i en produkt som visas i den här datatabellen.  <br/> |Innehåller sammanräknade månatliga data för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens Office-licenser  <br/> |Innehåller information om hur många Microsoft Office-prenumerationer som användare tilldelats  <br/> |Innehåller information om status vid månadsslutet för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens postlådeanvändning  <br/> |Innehåller information om användarens postlåda, totalt antal postlådor och hur lagringsutrymme används.  <br/> |Innehåller information om status vid månadsslutet för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens klientanvändning  <br/> |Innehåller information om antalet användare som aktivt använder specifika klienter/enheter för att ansluta till Exchange Online, Skype för företag och Yammer.  <br/> |Innehåller sammanräknade månatliga data för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens användning av SharePoint Online  <br/> |Innehåller information om SharePoint-webbplatserna, vilket omfattar gruppwebbplatser, till exempel totalt antal webbplatser, antal dokument på webbplatsen, antal filer efter aktivitetstyp och använt lagringsutrymme.  <br/> |Innehåller information om status vid månadsslutet för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens användning av OneDrive för företag  <br/> |Innehåller information om OneDrive-kontona, till exempel antalet konton, antalet dokument i OneDrives, lagringsutrymme som används och antalet filer efter aktivitetstyp.  <br/> |Innehåller information om status vid månadsslutet för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens användning av Microsoft 365 Grupper  <br/> |Innehåller information om användning av Microsoft 365 Grupper, som postlåda, SharePoint och Yammer.  <br/> |Innehåller information om status vid månadsslutet för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens Office-aktiveringar  <br/> |Innehåller information om antalet aktiveringar för Office-prenumerationer, antalet aktiveringar per enhet (Android/iOS/Mac/PC), aktiveringar efter tjänstplan, till exempel Microsoft 365-appar för företag, Visio, Project.  <br/> |Innehåller information om status vid månadsslutet för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Användarens status  <br/> |Innehåller metadata om användare, inklusive användarens visningsnamn, produkter som tilldelats, plats, avdelning, titel och företag. Den här informationen handlar om användare som tilldelades en licens under den senaste fullständiga månaden. Varje användare är unikt representerad av ett användar-ID.  <br/> |Den här informationen handlar om användare som hade en tilldelad licens under den senaste fullständiga månaden.  <br/> |
|Användaraktivitet  <br/> |Innehåller information efter användarnivå om aktiviteter som utförts av licensierade användare.  <br/> Se [definition av aktiv användare](active-user-in-usage-reports.md) om du vill ha information om aktiviteterna i en produkt som visas i den här datatabellen.  <br/> |Den här informationen handlar om användare som utförde en aktivitet i någon av tjänsterna under den senaste fullständiga månaden.  <br/> |
   
Expandera avsnitten nedan om du vill se detaljerad information om varje datatabell.
  
### <a name="data-table---user-state"></a>Datatabell - användarens status

Den här tabellen innehåller information på användarnivå för alla användare som har en tilldelad licens under den sista fullständiga månaden. Dessa data hämtas från Azure Active Directory.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|UserId  <br/> |Unikt användar-ID som representerar en användare och som gör det möjligt att ansluta till andra datatabeller i datauppsättningen.  <br/> |
|Timeframe  <br/> |Månadsvärde som den här tabellen har data för.  <br/> |
|UPN  <br/> |UPN, användarens huvudnamn, identifierar användaren unikt så att denne kan ansluta till andra externa datakällor.  <br/> |
|DisplayName  <br/> |Användarens visningsnamn.  <br/> |
|IDType  <br/> |ID-typen anges till 1 om användaren är en Yammer-användare som ansluter med hjälp av sitt Yammer-ID eller 0 om han eller hon ansluter till Yammer med sitt Microsoft 365-ID.  <br/> Värdet är 1 för att representera att användaren ansluter till Yammer med sitt Yammer-ID och inte sitt Microsoft 365-ID  <br/> |
|HasLicenseEXO  <br/> |Värdet är Sant om användaren tilldelats en licens och är aktiverad för att använda Exchange.  <br/> |
|HasLicenseODB  <br/> |Värdet är Sant om användaren tilldelats en licens och är aktiverad för att använda OneDrive för företag.  <br/> |
|HasLicenseSPO  <br/> |Värdet är Sant om användaren tilldelats en licens och är aktiverad för att använda SharePoint Online.  <br/> |
|HasLicenseYAM  <br/> |Värdet är Sant om användaren tilldelats en licens och är aktiverad för att använda Yammer.  <br/> |
|HasLicenseSFB  <br/> |Värdet är Sant om användaren tilldelats en licens och är aktiverad för att använda Skype för företag.  <br/> |
|HasLicenseTeams  <br/> |Värdet är sant om användaren tilldelats en licens och är aktiverad för att använda Microsoft Teams.  <br/> |
|Company  <br/> |Företagsinformation som återges i Azure Active Directory för användaren.  <br/> |
|Department  <br/> |Avdelningsinformation som återges i Azure Active Directory för användaren.  <br/> |
|LocationCity  <br/> |Information om ort som återges i Azure Active Directory för användaren.  <br/> |
|LocationCountry  <br/> |Information om land som återges i Azure Active Directory för användaren.  <br/> |
|LocationState  <br/> |Information om region som återges i Azure Active Directory för användaren.  <br/> |
|LocationOffice  <br/> |Användarens kontor.  <br/> |
|Title  <br/> |Information om titel som återges i Azure Active Directory för användaren.  <br/> |
|Deleted  <br/> |Sant om användaren har tagits bort från Microsoft 365 under den senaste fullständiga månaden.  <br/> |
|DeletedDate  <br/> |Datum när användaren togs bort från Microsoft 365.  <br/> |
|YAM_State  <br/> |Användarens tillstånd i Yammer-systemet, kan vara aktiv, borttagna eller inaktiverade.  <br/> |
|YAM_ActivationDate  <br/> |Det datum då användaren angav statusen aktiv i Yammer.  <br/> |
|YAM_DeletionDate  <br/> |Det datum då användaren angav statusen borttagen i Yammer.  <br/> |
|YAM_SuspensionDate  <br/> |Det datum då användaren angav statusen inaktiverad i Yammer.  <br/> |
   
### <a name="data-table---user-activity"></a>Datatabell - användaraktivitet

Den här tabellen innehåller information om alla användare som hade en aktivitet i någon av tjänster under den föregående månaden.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|UserID  <br/> |Unikt användar-ID som representerar en användare och som gör det möjligt att ansluta till andra datatabeller i datauppsättningen.  <br/> |
|IDType  <br/> |ID-typen anges till 1 om användaren är en Yammer-användare som ansluter med hjälp av sitt Yammer-ID eller 0 om han eller hon ansluter till Yammer med sitt Microsoft 365-ID.  <br/> Värdet är 1 för att representera att användaren ansluter till Yammer med sitt Yammer-ID och inte sitt Microsoft 365-ID  <br/> |
|Timeframe  <br/> |Månadsvärde som den här tabellen innehåller data för.  <br/> |
|EXO_EmailSent  <br/> |Antalet e-postmeddelanden som skickats.  <br/> |
|EXO_EmailReceived  <br/> |Antalet e-postmeddelanden som mottagits.  <br/> |
|EXO_EmailRead  <br/> |Antalet e-postmeddelanden som lästs som användaren utfört, det kan vara flera gånger som du läser ett redan läst e-postmeddelande eller ett e-postmeddelande som tagits emot tidigare.  <br/> |
|EXO_AppointmentCreated  <br/> |Antalet avtalade tider som skapats.  <br/> |
|EXO_MeetingAccepted  <br/> |Antalet möten som accepterats.  <br/> |
|EXO_MeetingCancelled  <br/> |Antalet möten som avbokats.  <br/> |
|EXO_MeetingDeclined  <br/> |Antalet möten som avböjts.  <br/> |
|EXO_MeetingSent  <br/> |Antalet möten som skickats.  <br/> |
|ODB_FileViewedModified  <br/> |Antalet filer som användaren interagerat med på en OneDrive för företag (till exempel skapat, uppdaterat, tagit bort, visat eller hämtat).  <br/> |
|ODB_FileSynched  <br/> |Antalet filer som användaren synkroniserat på ett OneDrive för företag.  <br/> |
|ODB_FileSharedInternally  <br/> |Antalet filer som användaren delat internt från ett OneDrive för företag eller med användare i grupper (som kan innehålla externa användare).  <br/> |
|ODB_FileSharedExternally  <br/> |Antalet filer som användaren delat externt från ett OneDrive för företag.  <br/> |
|ODB_AccessByOwner  <br/> |Antalet filer användaren interagerat med på sitt eget OneDrive för företag.  <br/> |
|ODB_AccessOthers  <br/> |Antalet filer användaren interagerat med på någon annan användares OneDrive för företag.  <br/> |
|SPO_GroupFileViewedModified  <br/> |Antalet filer som användaren interagerat med på någon webbplats för grupper.  <br/> |
|SPO_GroupFileSynched  <br/> |Antalet filer som användaren synkroniserat på någon webbplats för grupper.  <br/> |
|SPO_GroupFileSharedInternally  <br/> |Antalet filer som har delats med användare inom organisationen eller med användare i grupper (som kan innehålla externa användare).  <br/> |
|SPO_GroupFileSharedExternally  <br/> |Antalet filer som användaren delat externt på någon webbplats för grupper.  <br/> |
|SPO_GroupAccessByOwner  <br/> |Antalet filer som användaren interagerat med på en webbplats för grupper som han eller hon äger.  <br/> |
|SPO_GroupAccessByOthers  <br/> |Antalet filer som användaren interagerat med som finns på en webbplats för grupper som någon annan användare äger.  <br/> |
|SPO_OtherFileViewedModified  <br/> |Antalet filer som användaren interagerat med på någon annan webbplats.  <br/> |
|SPO_OtherFileSynched  <br/> |Antalet filer som användaren synkroniserat från någon annan webbplats.  <br/> |
|SPO_OtherFileSharedInternally  <br/> |Antalet filer som användaren delat internt på någon annan webbplats eller med användare i grupper (som kan innehålla externa användare). <br/> |
|SPO_OtherFileSharedExternally  <br/> |Antalet filer som användaren delat externt på någon annan webbplats.  <br/> |
|SPO_OtherAccessedByOwner  <br/> |Antalet webbplatser som användaren interagerat med på en annan webbplats som han eller hon äger.  <br/> |
|SPO_OtherAccessedByOthers  <br/> |Antalet webbplatser som användaren interagerat med som finns på en annan webbplats som någon annan användare äger.  <br/> |
|SPO_TeamFileViewedModified  <br/> |Antalet filer som användaren interagerat med på någon gruppwebbplats.  <br/> |
|SPO_TeamFileSynched  <br/> |Antalet filer som användaren synkroniserat från någon gruppwebbplats.  <br/> |
|SPO_TeamFileSharedInternally  <br/> |Antalet filer som användaren delat internt på någon gruppwebbplats eller med användare i grupper (som kan innehålla externa användare).  <br/> |
|SPO_TeamFileSharedExternally  <br/> |Antalet filer som användaren delat externt på någon gruppwebbplats.  <br/> |
|SPO_TeamAccessByOwner  <br/> |Antalet filer som användaren interagerat med på en gruppwebbplats som han eller hon äger.  <br/> |
|SPO_TeamAccessByOthers  <br/> |Antalet filer som användaren interagerat med som finns på en gruppwebbplats som någon annan användare äger.  <br/> |
|Teams_ChatMessages  <br/> |Antalet chattmeddelanden som skickats.  <br/> |
|Teams_ChannelMessage  <br/> |Antalet meddelanden som postats till kanaler.  <br/> |
|Teams_CallParticipate  <br/> |Antalet samtal som användaren har deltagit i.  <br/> |
|Teams_MeetingParticipate  <br/> |Antalet möten som användaren anslutit till.  <br/> |
|Teams_HasOtherAction  <br/> |Booleskt värde om användaren utfört andra åtgärder i Microsoft Teams.  <br/> |
|YAM_MessagePost  <br/> |Antalet Yammer-meddelanden som användaren publicerat.  <br/> |
|YAM_MessageLiked  <br/> |Antalet Yammer-meddelanden som användaren gillat.  <br/> |
|YAM_MessageRead  <br/> |Antalet Yammer-meddelanden som användaren läst.  <br/> |
|SFB_P2PSummary  <br/> |Antalet peer to peer-sessioner som användaren deltagit i.  <br/> |
|SFB_ConfOrgSummary  <br/> |Antalet konferenssessioner som användaren organiserat.  <br/> |
|SFB_ConfPartSummary  <br/> |Antalet konferenssessioner som användaren deltagit i.  <br/> |

> [!NOTE]
> Teams_HasOtherAction innebär att användaren anses vara aktiv men har ett nollvärde för chattmeddelanden, 1:1-samtal, kanalmeddelanden, totalt antal möten och möten organiserade.
   
### <a name="data-table---tenant-product-usage"></a>Datatabell - Klientorganisationens produktanvändning

Den här tabellen innehåller införandedata månad för månad för användare som vill aktivera, aktiva, gå tillbaka och använda första gången för de olika produkterna i Microsoft 365. Microsoft 365-värdena representerar aktiv användning i någon av produkterna.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|Produkt  <br/> |Namnet på produkter som användningsinformationen sammanfattas för. Microsoft 365-värdet i produktkolumnen representerar aktivitet i någon av produkterna  <br/> |
|Timeframe  <br/> |Månadsvärdet. Det kommer att finnas en rad per produkt per månad för de senaste tolv månaderna, inklusive delar av aktuell månad.  <br/> |
|EnabledUsers  <br/> |Antalet användare som är aktiverade för att använda produkten under tidsintervallet räknas fortfarande om en användare var aktiverad för en del av månaden.  <br/> |
|ActiveUsers  <br/> |Antalet användare som utförde en avsiktlig aktivitet i produkten under tidsperioden.  <br/> En användare räknas som aktiv för en produkt under en viss månad om han eller hon har utfört en nyckelaktivitet i produkten. Nyckelaktiviteter är tillgängliga i tabellen **Klientorganisationens produktaktivitet**.  <br/> |
|CumulativeActiveUsers  <br/> |Antalet användare som har aktiverats för att använda en produkt och som har använt produkten fram till månaden inom tidsperioden minst en gång sedan datainsamlingen påbörjades i det nya användningssystemet.  <br/> |
|MoMReturningUsers  <br/> |Antalet användare som är aktiva under månaden inom tidsperioden och som även var aktiva under den föregående månaden.  <br/> |
|FirstTimeUsers  <br/> |Antalet användare som blev aktiva inom tidsperioden för första gången sedan data samlades in i det nya användningssystemet.  <br/> En användare räknas som förstagångsanvändare under en viss månad, om vi identifierar hans eller hennes aktiviteter för första gången efter det att data börjat samlas in i det här nya rapporteringssystemet. När en användare väl har räknats som första gång, även om han eller hon sedan inte gör några aktiviteter på mycket länge, räknas han eller hon aldrig igen som förstaanvändare  <br/> |
|Content Date  <br/> |Om tidsperioden är aktuell månad representerar det här värdet det senaste datumet i den aktuella månaden för vilket det finns tillgängliga data.  <br/> Om tidsperioden är föregående månad representerar det här värdet det sista datumet i månaden inom tidsperioden.  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>Datatabell - Klientorganisationens produktaktivitet

Den här tabellen innehåller månatliga summering av aktivitet och antalet aktiva användare för olika aktiviteter i produkterna.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|Timeframe  <br/> |Månadsvärdet. Det kommer att finnas en rad per produkt per månad för de senaste tolv månaderna, inklusive delar av aktuell månad.  <br/> |
|Produkt  <br/> |Namnet på produkten i Microsoft 365, för vilken det finns tillgängliga användningsdata.  <br/> |
|Aktivitet  <br/> |Namnet på aktiviteten i en produkt som används för att visa upp aktiv användning av produkten.  <br/> |
|ActivityCount  <br/> |Det här är det totala antalet åtgärder som räknas för varje aktivitet som utförs i produkten för alla aktiva användare.  <br/> **Obs!** För SharePoint Online- och OneDrive för företag-aktiviteter representerar det här värdet antalet specifika dokument som användarna interagerat med.      <br/> |
|ActiveUserCount  <br/> |Antalet användare som utfört aktiviteten i produkten.  <br/> |
|TotalDurationInMinute  <br/> |Varaktighet i minuter för alla aktiva användare som använt ljud- eller videosession i en tillämplig Skype för företag-aktivitet.  <br/> |
|Content Date  <br/> |Om tidsperioden är aktuell månad representerar det här värdet det senaste datumet i den aktuella månaden för vilket det finns tillgängliga data.  <br/> Om tidsperioden är föregående månad representerar det här värdet det sista datumet i månaden inom tidsperioden.  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>Datatabell - Klientorganisationens postlådeanvändning

Den här tabellen består av sammanfattningsdata för alla licensierade Exchange Online-användare som har en användarpostlåda. Den visar statusvärden vid slutet av månaden för alla användarpostlådor. Data i den här tabellen är inte additiva över flera månader. Senaste månadens data i den här tabellen representerar den senaste statusen.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|TotalMailboxes  <br/> |Antalet användarpostlådor för Microsoft 365-prenumerationen.  <br/> |
|IssueWarningQuota  <br/> |Totalkvot för att utfärda en varning för alla användares postlådor.  <br/> |
|ProhibitSendQuota  <br/> |Totalkvot för att förhindra sändning för alla användarpostlådor.  <br/> |
|ProhibitSendReceiveQuota  <br/> |Totalkvot för kvot för att förhindra sändning/mottagning för alla användarpostlådor.  <br/> |
|TotalItemBytes  <br/> |Mängden lagringsutrymme som används för alla användarpostlådor i byte.  <br/> |
|MailboxesNoWarning  <br/> |Antalet användarpostlådor som låg under gränsen för lagringsutrymmesvarning.  <br/> |
|MailboxesIssueWarning  <br/> |Antalet användarpostlådor för vilka det utfärdats en varning för lagringskvot.  <br/> |
|MailboxesExceedSendQuota  <br/> |Antalet användarpostlådor som har överskridit sändningskvoten.  <br/> |
|MailboxesExceedSendReceiveQuota  <br/> |Antalet användarpostlådor som har överskridit kvoten för skicka/ta emot.  <br/> |
|DeletedMailboxes  <br/> |Antalet användarpostlådor som tagits bort inom tidsperioden.  <br/> |
|Timeframe  <br/> |Månadsvärdet.  <br/> |
|Content Date  <br/> |Om tidsperioden är aktuell månad representerar det här värdet det senaste datumet i den aktuella månaden för vilket det finns tillgängliga data.  <br/> Om tidsperioden är föregående månad representerar det här värdet det sista datumet i månaden inom tidsperioden.  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>Datatabell - Klientorganisationens klientanvändning

Den här tabellen innehåller sammanfattningsdata månad för månad om klienter som användarna använder för att ansluta till Exchange Online, Skype för företag och Yammer. Den här tabellen har ännu inte klientanvändningsdata för SharePoint Online och OneDrive för företag.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|Produkt  <br/> |Namnet på produkten i Microsoft 365, för vilken det finns tillgängliga användningsdata.  <br/> |
|ClientId  <br/> |Namnet på varje enhet som används för att ansluta till produkten.  <br/> |
|UserCount  <br/> |Antalet användare som använt de olika klienterna för de olika produkterna.  <br/> |
|Timeframe  <br/> |Månadsvärdet  <br/> |
|Content Date  <br/> |Om tidsperioden är aktuell månad representerar det här värdet det senaste datumet i den aktuella månaden för vilket det finns tillgängliga data.  <br/> Om tidsperioden är föregående månad representerar det här värdet det sista datumet i månaden inom tidsperioden.  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>Datatabell - Klientorganisationens användning av SharePoint Online

Den här tabellen består av sammanfattningsdata månad för månad om användning eller aktivitet för SharePoint Online-webbplatser. Det här gäller bara gruppwebbplatser och gruppwebbplatser. Statusen vid månadsslutet för SharePoint Online-webbplatser representeras i den här kolumnen, till exempel om en användare skapade fem dokument och använde 10 MB för total lagring, och sedan tog bort några filer och lade till fler filer så att i slutet av månadens tillstånd för filer är sju totalt som använder fem MB lagringsutrymme, är värdet som representeras i den här tabellen status vid månadsslutet. Den här tabellen är dold för att undvika dubblettantal av aggregeringar och används som källa för att skapa två referenstabeller.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|SiteType  <br/> |Typvärde för webbplats (valfri/team/grupp) (valfri motsvarar någon av följande två typer av webbplatser).  <br/> |
|TotalSites  <br/> |Antalet webbplatser som fanns vid tidsperiodens slut.  <br/> |
|DocumentCount  <br/> |Totalt antal dokument som fanns på webbplatsen vid tidsperiodens slut.  <br/> |
|Diplansed  <br/> |Total lagringskvot som används för alla webbplatserna vid tidsperiodens slut.  <br/> |
|ActivityType  <br/> |Antalet webbplatser som registrerade de olika typerna av filaktivitet (valfri/aktiva filer/delade filer EXT/INT/synkroniserade filer).  <br/> Representerar någon av filaktiviteten som utfördes.  <br/> |
|SitesWithOwnerActivities  <br/> |Antalet aktiva platser där webbplatsägaren utfört en viss filaktivitet på sina egna webbplatser. Du kan få webbplatsägaren från **PowerShell-kommandot get-sposite**. Det här är den person som ansvarar för webbplatsen.   <br/> |
|SitesWithNonOwnerActivities  <br/> |Antalet aktiva platser som summeras för månaden, där andra användare än webbplatsägaren utfört en viss filaktivitet på webbplatser. Du kan få webbplatsägaren från **PowerShell-kommandot get-sposite**. Det här är den person som ansvarar för webbplatsen. <br/> |
|ActivityTotalSites  <br/> |Antalet webbplatser där någon aktivitet registrerats inom tidsperioden. Om en webbplats hade aktivitet tidigare inom tidsperioden och sedan togs bort i slutet av tidsperioden skulle den fortfarande räknas in i totalen för den aktiva webbplatsen för den tidsperioden.  <br/> |
|Timeframe  <br/> |Den här kolumnen innehåller datumvärdet. Används som ett-till-många-samband för kalendertabellen.  <br/> |
|Content Date  <br/> |Om tidsperioden är aktuell månad representerar det här värdet det senaste datumet i den aktuella månaden för vilket det finns tillgängliga data.  <br/> Om tidsperioden är föregående månad representerar det här värdet det sista datumet i månaden inom tidsperioden.  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>Datatabell - klientorganisationens OneDrive-användning

Den här tabellen innehåller information om OneDrive-kontona, till exempel antalet konton, antalet dokument för alla OneDrive-konton, lagringsutrymme som används och antalet filer efter aktivitetstyp. Statusen vid månadsslutet för OneDrive för företag-konton som visas i den här tabellen. Om en användare till exempel skapade fem dokument som använde 10 MB lagringsutrymme och sedan tog bort några och lade till fler filer så att de i slutet av månaden har sju filer som använder Fem MB lagringsutrymme, representeras värdet vid slutet av månaden i den här tabellen i slutet av månaden.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|SiteType  <br/> |Värdet är "OneDrive".  <br/> |
|TotalSites  <br/> |Antalet OneDrive för företag-konton som finns i slutet av tidsperioden.  <br/> |
|DocumentCount  <br/> |Det totala antalet dokument som fanns i alla OneDrive för företag-konton i slutet av tidsperioden  <br/> |
|Diplansed  <br/> |Totalt lagringsutrymme som används för alla OneDrive-konton vid tidsperiodens slut.  <br/> |
|ActivityType  <br/> |Antalet konton som registrerade de olika typerna av filaktivitet (valfri/aktiva filer/delade filer EXT/INT/synkroniserade filer).  <br/> Valfri betyder att någon av filaktiviteterna utfördes  <br/> |
|SitesWithOwnerActivities  <br/> |Antalet aktiva OneDrive för företag-konton, där kontoinnehavaren utfört en viss filaktivitet på sitt eget konto.  <br/> |
|SitesWithNonOwnerActivities  <br/> |Antalet OneDrive för företag-konton där filaktivitet utförts av andra användare än kontoinnehavaren.  <br/> |
|ActivityTotalSites  <br/> |Antalet OneDrive för företag-konton som registrerat någon aktivitet under tidsperioden. Om ett OneDrive för företag-konto hade aktivitet tidigare under tidsperioden och sedan togs bort i slutet av tidsperioden skulle det fortfarande räknas som aktivt OneDrive för företag-konto för den tidsperioden.  <br/> |
|Timeframe  <br/> |Den här kolumnen innehåller datumvärdet. Används som ett-till-många-samband för kalendertabellen.  <br/> |
|Content Date  <br/> |Om tidsperioden är aktuell månad representerar det här värdet det senaste datumet i den aktuella månaden för vilket det finns tillgängliga data.  <br/> Om tidsperioden är föregående månad representerar det här värdet det sista datumet i månaden inom tidsperioden.  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>Datatabell – Klientorganisationens användning av Microsoft 365 Grupper

Den här tabellen innehåller information om hur Microsoft 365 Grupper används i hela organisationen.
  
****

|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|TimeFrame  <br/> |Månadsvärdet. Det kommer att finnas en rad per produkt per månad för de senaste 12 månaderna, inklusive del av aktuell månad.  <br/> |
|GroupType  <br/> |Typ av grupp (privat/offentlig/alla).  <br/> |
|TotalGroups  <br/> |Antalet grupper i varje grupptyp.  <br/> |
|ActiveGroups  <br/> |Antalet aktiva grupper.  <br/> |
|MBX_TotalGroups  <br/> |Antalet postlådegrupper.  <br/> |
|MBX_ActiveGroups  <br/> |Antalet aktiva postlådegrupper.  <br/> |
|MBX_TotalActivities  <br/> |Antalet postlådeaktiviteter.  <br/> |
|MBX_TotalItems  <br/> |Antalet postlådeobjekt.  <br/> |
|MBX_StorageUsed  <br/> |Mängden använt lagringsutrymme.  <br/> |
|SPO_TotalGroups  <br/> |Antalet SharePoint-grupper.  <br/> |
|SPO_ActiveGroups  <br/> |Antalet aktiva SharePoint-grupper.  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |Antalet SharePoint-grupper som har filåtkomstaktiviteter.  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |Antalet SharePoint-grupper som har filsynkronerade aktiviteter.  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |Antalet SharePoint-grupper som har delade aktiviteter internt eller med grupper (som kan omfatta externa användare).  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |Antalet SharePoint-grupper som har externdelningsaktiviteter.  <br/> |
|SPO_TotalActivities  <br/> |Antalet SharePoint-aktiviteter.  <br/> |
|SPO_FileAccessedActivities  <br/> |Antalet SharePoint filåtkomstaktiviteter.  <br/> |
|SPO_FileSyncedActivities  <br/> |Antalet SharePoint filsynkroniseringsaktiviteter.  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |Antalet SharePoint fildelningsaktiviteter internt eller med grupper (som kan innehålla externa medlemmar).  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |Antalet SharePoint externfildelningsaktiviteter.  <br/> |
|SPO_TotalFiles  <br/> |Antalet SharePoint-filer.  <br/> |
|SPO_ActiveFiles  <br/> |Antalet aktiva SharePoint-filer.  <br/> |
|SPO_StorageUsed  <br/> |Mängden SharePoint-lagring som använts.  <br/> |
|YAM_TotalGroups  <br/> |Antalet Yammer-grupper.  <br/> |
|YAM_ActiveGroups  <br/> |Antalet aktiva Yammer-grupper.  <br/> |
|YAM_LikedActiveGroups  <br/> |Antalet Yammer-grupper som har gillaaktiviteter.  <br/> |
|YAM_PostedActiveGroups  <br/> |Antalet Yammer-grupper som har inläggsaktiviteter.  <br/> |
|YAM_ReadActiveGroups  <br/> |Antalet Yammer-grupper som har läsningsaktiviteter.  <br/> |
|YAM_TotalActivities  <br/> |Antalet Yammer-aktiviteter.  <br/> |
|YAM_LikedActivities  <br/> |Antalet Yammer-gillaaktiviteter.  <br/> |
|YAM_PostedActivties  <br/> |Antalet Yammer-inläggsaktiviteter.  <br/> |
|YAM_ReadActivites  <br/> |Antalet Yammer-läsningsaktiviteter.  <br/> |
   
### <a name="data-table---tenant-office-activation"></a>Datatabell - Klientorganisationens Office-aktiveringar

Tabellen innehåller information om antalet aktiveringar av Office-prenumerationer för alla tjänstplaner, till exempel Microsoft 365-program för företag, Visio och Project. Här finns även information om antalet aktiveringar per enhet (Android/iOS/Mac/PC).
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|ServicePlanName  <br/> |Lista med värden för namn på tjänstplaner och antalet aktiveringar efter enheter, som i kolumnerna nedan.  <br/> |
|TotalEnabled  <br/> |Antalet användare som är aktiverade per tjänstplansnamn i slutet av tidsperioden.  <br/> |
|TotalActivatedUsers  <br/> |Antalet användare som har aktiverat de olika tjänstplanerna i slutet av tidsperioden.  <br/> |
|AndroidCount  <br/> |Antalet aktiveringar per tjänstplan för Android-enhet i slutet av tidsperioden.  <br/> |
|iOSCount  <br/> |Antalet aktiveringar per tjänstplan för iOS-enhet i slutet av tidsperioden.  <br/> |
|MacCount  <br/> |Antalet aktiveringar per tjänstplan för MAC-enhet i slutet av tidsperioden.  <br/> |
|PcCount  <br/> |Antalet aktiveringar per tjänstplan för PC-enhet i slutet av tidsperioden.  <br/> |
|WinRtCount  <br/> |Antalet aktiveringar per tjänstplan för Windows Mobile-enhet i slutet av tidsperioden.  <br/> |
|Timeframe  <br/> |Den här kolumnen innehåller datumvärdet. Används som ett-till-många-samband för kalendertabellen.  <br/> |
|Content Date  <br/> |Om tidsperioden är aktuell månad representerar det här värdet det senaste datumet i den aktuella månaden för vilket det finns tillgängliga data.  <br/> Om tidsperioden är föregående månad representerar det här värdet det sista datumet i månaden inom tidsperioden.  <br/> |
