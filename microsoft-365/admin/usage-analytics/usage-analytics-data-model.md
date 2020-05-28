---
title: Datamodell för Microsoft 365 användningsanalyser
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 'Lär dig hur användningsanalys ansluter till ett API och ger månatliga trend för användning av olika Microsoft 365-tjänster.  '
ms.openlocfilehash: 6b0b005e6e07e52731a84490a6df7c9ead614321
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402052"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Datamodell för Microsoft 365 användningsanalyser

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Data för Microsoft 365 användningsanalystabeller

Microsoft 365 användningsanalyser ansluter till ett API som visar en flerdimensionell datamodell. API:erna är i förhandsversion och kan nås på `https://reports.office.com/pbi/v1.0/\<tenantid\>` (ersätt \<tenant id\> med klient-GUID). 
  
> [!NOTE]
> Mer information finns i [Arbeta med Användningsrapporter för Microsoft 365 i Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=864336). 
  
Det här API:et innehåller information om den månatliga trenden för användning av de olika Microsoft 365-tjänsterna. Information om exakt vilka data som returneras av API:et finns i tabellen i följande avsnitt.
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Datatabeller som returneras av Microsoft 365 Reporting API

|**Tabellnamn**|**Informationen i tabellen**|**Datumintervall**|
|:-----|:-----|:-----|
|Klientorganisationens produktanvändning  <br/> |Innehåller månatliga summeringar av antalet aktiverade, aktiva användare, antalet kvarhållna användare månad för månad, förstagångsanvändare och det ackumulerade antalet aktiva användare.  <br/> |Innehåller sammanräknade månatliga data för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens produktaktivitet  <br/> |Innehåller månatliga summeringar av aktivitet och antalet aktiva användare för olika aktiviteter i produkterna.  <br/> Se [definition av aktiv användare](active-user-in-usage-reports.md) om du vill ha information om aktiviteterna i en produkt som visas i den här datatabellen.  <br/> |Innehåller sammanräknade månatliga data för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens Office-licenser  <br/> |Innehåller information om hur många Microsoft Office-prenumerationer som användare tilldelats  <br/> |Innehåller information om status vid månadsslutet för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens postlådeanvändning  <br/> |Innehåller information om användarens postlåda, till exempel totalt antal meddelanden i postlådan och lagringsanvändningen.  <br/> |Innehåller information om status vid månadsslutet för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens klientanvändning  <br/> |Innehåller information om antalet användare som aktivt använder specifika klienter/enheter för att ansluta till Exchange Online, Skype för företag och Yammer.  <br/> |Innehåller sammanräknade månatliga data för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens användning av SharePoint Online  <br/> |Innehåller information om SharePoint-webbplatserna, vilket omfattar gruppwebbplatser, till exempel totalt antal webbplatser, antal dokument på webbplatsen, antal filer efter aktivitetstyp och använt lagringsutrymme.  <br/> |Innehåller information om status vid månadsslutet för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens användning av OneDrive för företag  <br/> |Innehåller information om OneDrive-kontona, till exempel antalet konton, antalet dokument i OneDrives, lagringsutrymme som används och antalet filer efter aktivitetstyp.  <br/> |Innehåller information om status vid månadsslutet för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Användning av Microsoft 365-grupper för klient  <br/> |Innehåller data om användning av Microsoft 365-grupper, inklusive postlåda, SharePoint och Yammer.  <br/> |Innehåller information om status vid månadsslutet för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Klientorganisationens Office-aktiveringar  <br/> |Innehåller data om antalet Office-prenumerationsaktiveringar, antal aktiveringar per enhet (Android/iOS/Mac/PC), aktiveringar per serviceplan, till exempel Microsoft 365 Apps för företag, Visio, Project.  <br/> |Innehåller information om status vid månadsslutet för en rullande tolvmånadersperiod som omfattar delar av innevarande månad.  <br/> |
|Användarens status  <br/> |Innehåller metadata om användare, inklusive användarens visningsnamn, produkter som tilldelats, plats, avdelning, titel och företag. Den här informationen handlar om användare som tilldelades en licens under den senaste fullständiga månaden. Alla användare är unikt representerade av ett användar-ID.  <br/> |Den här informationen handlar om användare som hade en tilldelad licens under den senaste fullständiga månaden.  <br/> |
|Användaraktivitet  <br/> |Innehåller information efter användarnivå om aktiviteter som utförts av licensierade användare.  <br/> Se [definition av aktiv användare](active-user-in-usage-reports.md) om du vill ha information om aktiviteterna i en produkt som visas i den här datatabellen.  <br/> |Den här informationen handlar om användare som utförde en aktivitet i någon av tjänsterna under den senaste fullständiga månaden.  <br/> |
   
Expandera avsnitten nedan om du vill se detaljerad information om varje datatabell.
  
### <a name="data-table---user-state"></a>Datatabell - användarens status

Den här tabellen innehåller information efter användarnivå för alla användare som har en tilldelad licens under den sista fullständiga månaden. Dessa data hämtas från Azure Active Directory.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|Userid  <br/> |Unikt användar-ID som representerar en användare och som gör det möjligt att ansluta till andra datatabeller i datauppsättningen.  <br/> |
|Timeframe  <br/> |Månadsvärde som den här tabellen har data för.  <br/> |
|UPN  <br/> |UPN, användarens huvudnamn, identifierar användaren unikt så att denne kan ansluta till andra externa datakällor.  <br/> |
|Displayname  <br/> |Användarens visningsnamn.  <br/> |
|IDType  <br/> |Id-typ är inställd på 1 om användaren är en Yammer-användare som ansluter med hjälp av sitt Yammer-ID eller 0 om de ansluter till Yammer med hjälp av sitt Microsoft 365-ID.  <br/> Värdet är 1 för att representera att dessa användare ansluter till Yammer med sitt Yammer-id och inte deras Microsoft 365-id  <br/> |
|HarLicenseEXO  <br/> |Värdet är Sant om användaren tilldelats en licens och är aktiverad för att använda Exchange.  <br/> |
|HarLicenseODB  <br/> |Värdet är Sant om användaren tilldelats en licens och är aktiverad för att använda OneDrive för företag.  <br/> |
|HasLicenseSPO  <br/> |Värdet är Sant om användaren tilldelats en licens och är aktiverad för att använda SharePoint Online.  <br/> |
|HarLicenseYAM  <br/> |Värdet är Sant om användaren tilldelats en licens och är aktiverad för att använda Yammer.  <br/> |
|HasLicenseSFB  <br/> |Värdet är Sant om användaren tilldelats en licens och är aktiverad för att använda Skype för företag.  <br/> |
|HasLicenseTeams  <br/> |Värdet är sant om användaren tilldelats en licens och är aktiverad för att använda Microsoft Teams.  <br/> |
|Company  <br/> |Företagsinformation som återges i Azure Active Directory för användaren.  <br/> |
|Department  <br/> |Avdelningsinformation som återges i Azure Active Directory för användaren.  <br/> |
|PlatsStad  <br/> |Information om ort som återges i Azure Active Directory för användaren.  <br/> |
|PlatsLand  <br/> |Information om land som återges i Azure Active Directory för användaren.  <br/> |
|PlatsTillstånd  <br/> |Information om region som återges i Azure Active Directory för användaren.  <br/> |
|PlatsOffice  <br/> |Användarens kontor.  <br/> |
|Title  <br/> |Information om titel som återges i Azure Active Directory för användaren.  <br/> |
|Deleted  <br/> |Sant om användaren har tagits bort från Microsoft 365 under den senaste hela månaden.  <br/> |
|DeletedDate  <br/> |Datum då användaren togs bort från Microsoft 365.  <br/> |
|YAM_State  <br/> |Statusvärden för användaren i Yammer-systemet, kan vara aktiv, borttagen eller inaktiverad.  <br/> |
|YAM_ActivationDate  <br/> |Det datum då användaren angav statusen aktiv i Yammer.  <br/> |
|YAM_DeletionDate  <br/> |Det datum då användaren angav statusen borttagen i Yammer.  <br/> |
|YAM_SuspensionDate  <br/> |Det datum då användaren angav statusen inaktiverad i Yammer.  <br/> |
   
### <a name="data-table---user-activity"></a>Datatabell - användaraktivitet

Den här tabellen innehåller information om alla användare som hade en aktivitet i någon av tjänster under den föregående månaden.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|Userid  <br/> |Unikt användar-ID som representerar en användare och som gör det möjligt att ansluta till andra datatabeller i datauppsättningen.  <br/> |
|IDType  <br/> |Id-typ är inställd på 1 om användaren är en Yammer-användare som ansluter med hjälp av sitt Yammer-ID eller 0 om de ansluter till Yammer med hjälp av sitt Microsoft 365-ID.  <br/> Värdet är 1 för att representera att dessa användare ansluter till Yammer med sitt Yammer-id och inte deras Microsoft 365-id  <br/> |
|Timeframe  <br/> |Månadsvärde som den här tabellen innehåller data för.  <br/> |
|EXO_EmailSent  <br/> |Antalet e-postmeddelanden som skickats.  <br/> |
|EXO_EmailReceived  <br/> |Antalet e-postmeddelanden som mottagits.  <br/> |
|EXO_EmailRead  <br/> |Antalet gånger som aktiviteten att läsa mottagna e-postmeddelanden utförs (avser både antalet gånger användaren läser redan lästa e-postmeddelanden och e-postmeddelanden som användaren fått tidigare).  <br/> |
|EXO_AppointmentCreated  <br/> |Antalet avtalade tider som skapats.  <br/> |
|EXO_MeetingAccepted  <br/> |Antalet möten som accepterats.  <br/> |
|EXO_MeetingCancelled  <br/> |Antalet möten som avbokats.  <br/> |
|EXO_MeetingDeclined  <br/> |Antalet möten som avböjts.  <br/> |
|EXO_MeetingSent  <br/> |Antalet möten som skickats.  <br/> |
|ODB_FileViewedModified  <br/> |Antalet filer som användaren interagerat med på en OneDrive för företag (till exempel skapat, uppdaterat, tagit bort, visat eller hämtat).  <br/> |
|ODB_FileSynched  <br/> |Antalet filer som användaren synkroniserat på ett OneDrive för företag.  <br/> |
|ODB_FileSharedInternally  <br/> |Antal filer som användaren har delat internt från en OneDrive för företag eller med användare inom grupper (som kan omfatta externa användare).  <br/> |
|ODB_FileSharedExternally  <br/> |Antalet filer som användaren delat externt från ett OneDrive för företag.  <br/> |
|ODB_AccessByOwner  <br/> |Antalet filer användaren interagerat med på sitt eget OneDrive för företag.  <br/> |
|ODB_AccessOthers  <br/> |Antalet filer användaren interagerat med på någon annan användares OneDrive för företag.  <br/> |
|SPO_GroupFileViewedModified  <br/> |Antalet filer som användaren interagerat med på någon webbplats för grupper.  <br/> |
|SPO_GroupFileSynched  <br/> |Antalet filer som användaren synkroniserat på någon webbplats för grupper.  <br/> |
|SPO_GroupFileSharedInternally  <br/> |Antalet filer som har delats med användare inom organisationen eller med användare inom grupper (som kan inkludera externa användare).  <br/> |
|SPO_GroupFileSharedExternally  <br/> |Antalet filer som användaren delat externt på någon webbplats för grupper.  <br/> |
|SPO_GroupAccessByOwner  <br/> |Antalet filer som användaren interagerat med på en webbplats för grupper som han eller hon äger.  <br/> |
|SPO_GroupAccessByOthers  <br/> |Antalet filer som användaren interagerat med som finns på en webbplats för grupper som någon annan användare äger.  <br/> |
|SPO_OtherFileViewedModified  <br/> |Antalet filer som användaren interagerat med på någon annan webbplats.  <br/> |
|SPO_OtherFileSynched  <br/> |Antalet filer som användaren synkroniserat från någon annan webbplats.  <br/> |
|SPO_OtherFileSharedInternally  <br/> |Antal filer som användaren har delat internt från någon annan webbplats eller med användare inom grupper (som kan inkludera externa användare). <br/> |
|SPO_OtherFileSharedExternally  <br/> |Antalet filer som användaren delat externt på någon annan webbplats.  <br/> |
|SPO_OtherAccessedByOwner  <br/> |Antalet webbplatser som användaren interagerat med på en annan webbplats som han eller hon äger.  <br/> |
|SPO_OtherAccessedByOthers  <br/> |Antalet webbplatser som användaren interagerat med som finns på en annan webbplats som någon annan användare äger.  <br/> |
|SPO_TeamFileViewedModified  <br/> |Antalet filer som användaren interagerat med på någon gruppwebbplats.  <br/> |
|SPO_TeamFileSynched  <br/> |Antalet filer som användaren synkroniserat från någon gruppwebbplats.  <br/> |
|SPO_TeamFileSharedInternally  <br/> |Antal filer som användaren har delat internt från en gruppwebbplats eller med användare inom grupper (som kan inkludera externa användare).  <br/> |
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
   
### <a name="data-table---tenant-product-usage"></a>Datatabell - Klientorganisationens produktanvändning

Den här tabellen innehåller månad för månadsanvändningsdata när det gäller aktivera, aktiva, återkommande och första gången användare för varje produkt inom Microsoft 365. Microsoft 365-värdet representerar aktiv användning i någon av produkterna.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|Produkt  <br/> |Namnet på produkter som användningsinformationen sammanfattas för. Microsoft 365-värdet i produktkolumnen representerar aktivitet i någon av produkterna  <br/> |
|Timeframe  <br/> |Månadsvärdet. Det kommer att finnas en rad per produkt per månad för de senaste tolv månaderna, inklusive delar av aktuell månad.  <br/> |
|Aktiveradeanvändare  <br/> |Antalet användare som är aktiverade för att använda produkten under tidsperioden. Om en användare var aktiverad för en del av månaden räknas han eller hon fortfarande.  <br/> |
|ActiveUsers  <br/> |Antalet användare som utförde en avsiktlig aktivitet i produkten under tidsperioden.  <br/> En användare räknas som aktiv för en produkt under en viss månad om han eller hon har utfört en nyckelaktivitet i produkten. Nyckelaktiviteter är tillgängliga i tabellen **Klientorganisationens produktaktivitet**.  <br/> |
|Kumulativa Aktivaanvändare  <br/> |Antalet användare som har aktiverats för att använda en produkt och som har använt produkten fram till månaden inom tidsperioden minst en gång sedan datainsamlingen påbörjades i det nya användningssystemet.  <br/> |
|MoMReturningAnvändare  <br/> |Antalet användare som är aktiva under månaden inom tidsperioden och som även var aktiva under den föregående månaden.  <br/> |
|FirstTimeUsers  <br/> |Antalet användare som blev aktiva inom tidsperioden för första gången sedan data samlades in i det nya användningssystemet.  <br/> En användare räknas som förstagångsanvändare under en viss månad, om vi identifierar hans eller hennes aktiviteter för första gången efter det att data börjat samlas in i det här nya rapporteringssystemet. En gång räknat som en första gången användare, även om denna användare har en stor lucka i sin verksamhet de aldrig kommer att räknas igen som en första gången användare  <br/> |
|Content Date  <br/> |Om tidsperioden är aktuell månad representerar det här värdet det senaste datumet i den aktuella månaden för vilket det finns tillgängliga data.  <br/> Om tidsperioden är föregående månad representerar det här värdet det sista datumet i månaden inom tidsperioden.  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>Datatabell - Klientorganisationens produktaktivitet

Den här tabellen innehåller månatliga summeringar av aktivitet och antalet aktiva användare för olika aktiviteter i produkterna.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|Timeframe  <br/> |Månadsvärdet. Det kommer att finnas en rad per produkt per månad för de senaste tolv månaderna, inklusive delar av aktuell månad.  <br/> |
|Produkt  <br/> |Namnet på den produkt inom Microsoft 365 för vilken användningsdata är tillgängliga.  <br/> |
|Aktivitet  <br/> |Namnet på aktiviteten i en produkt som används för att visa upp aktiv användning av produkten.  <br/> |
|Aktivitetskonto  <br/> |Det här är det totala antalet åtgärder som räknas för varje aktivitet som utförs i produkten för alla aktiva användare.  <br/> **Obs!** För SharePoint Online- och OneDrive för företag-aktiviteter representerar det här värdet antalet specifika dokument som användarna interagerat med.      <br/> |
|ActiveUserCount  <br/> |Antalet användare som utfört aktiviteten i produkten.  <br/> |
|TotaltUnderyreminute  <br/> |Varaktighet i minuter för alla aktiva användare som använt ljud- eller videosession i en tillämplig Skype för företag-aktivitet.  <br/> |
|Content Date  <br/> |Om tidsperioden är aktuell månad representerar det här värdet det senaste datumet i den aktuella månaden för vilket det finns tillgängliga data.  <br/> Om tidsperioden är föregående månad representerar det här värdet det sista datumet i månaden inom tidsperioden.  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>Datatabell - Klientorganisationens postlådeanvändning

Den här tabellen består av sammanfattningsdata för alla licensierade Exchange Online-användare som har en användarpostlåda. Den visar statusvärden vid slutet av månaden för alla användarpostlådor. Data i den här tabellen är inte additiva över flera månader. Senaste månadens data i den här tabellen representerar den senaste statusen.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|Totalt Postlådor  <br/> |Antal användarpostlådor för Microsoft 365-prenumeration.  <br/> |
|IssueWarningQuota  <br/> |Totalkvot för att utfärda en varning för alla användarpostlådor.  <br/> |
|ProhibitSendQuota  <br/> |Totalkvot för att förhindra sändning för alla användarpostlådor.  <br/> |
|ProhibitSendReceiveQuota  <br/> |Totalkvot för kvot för att förhindra sändning/mottagning för alla användarpostlådor.  <br/> |
|TotalItemBytes  <br/> |Mängden lagringsutrymme som används för alla användarpostlådor i byte.  <br/> |
|BrevlådorObvarning  <br/> |Antalet användarpostlådor som låg under gränsen för lagringsutrymmesvarning.  <br/> |
|MailboxesIssueVarning  <br/> |Antalet användarpostlådor för vilka det utfärdats en varning för lagringskvot.  <br/> |
|BrevlådorExceedSendQuota  <br/> |Antalet användarpostlådor som har överskridit sändningskvoten.  <br/> |
|BrevlådorExceedSendReceiveQuota  <br/> |Antalet användarpostlådor som har överskridit sändnings-/mottagningskvoten.  <br/> |
|DeletedMailboxes  <br/> |Antalet användarpostlådor som tagits bort inom tidsperioden.  <br/> |
|Timeframe  <br/> |Månadsvärdet.  <br/> |
|Content Date  <br/> |Om tidsperioden är aktuell månad representerar det här värdet det senaste datumet i den aktuella månaden för vilket det finns tillgängliga data.  <br/> Om tidsperioden är föregående månad representerar det här värdet det sista datumet i månaden inom tidsperioden.  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>Datatabell - Klientorganisationens klientanvändning

Den här tabellen innehåller sammanfattningsdata månad för månad om klienter som användarna använder för att ansluta till Exchange Online, Skype för företag och Yammer. Den här tabellen har ännu inte klientanvändningsdata för SharePoint Online och OneDrive för företag.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|Produkt  <br/> |Namnet på den produkt inom Microsoft 365 för vilken klientanvändningsdata är tillgängliga.  <br/> |
|ClientId (klientId)  <br/> |Namnet på varje enhet som används för att ansluta till produkten.  <br/> |
|UserCount (AnvändareCount)  <br/> |Antalet användare som använt de olika klienterna för de olika produkterna.  <br/> |
|Timeframe  <br/> |Månadsvärdet  <br/> |
|Content Date  <br/> |Om tidsperioden är aktuell månad representerar det här värdet det senaste datumet i den aktuella månaden för vilket det finns tillgängliga data.  <br/> Om tidsperioden är föregående månad representerar det här värdet det sista datumet i månaden inom tidsperioden.  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>Datatabell - Klientorganisationens användning av SharePoint Online

Den här tabellen innehåller sammanfattningsdata månad för månad om användning eller aktiviteten på SharePoint Online-webbplatser. Detta omfattar endast gruppwebbplatser. I den här kolumnen visas SharePoint Online-webbplatsernas status vid månadsslutet. Om en användare till exempel skapar 5 dokument och använder 10MB av det totala lagringsutrymmet och sedan tar bort en del filer och lägger till andra filer så att statusen vid månadsslutet är totalt 7 filer som använder 5MB lagringsutrymme, blir värdet som visas i den här tabellen statusen vid månadsslutet. Den här tabellen är dold för att undvika dubbletter och används som källa för att skapa två referenstabeller.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|SiteType (Platstyp)  <br/> |Typvärde för webbplats (valfri/team/grupp) (valfri motsvarar någon av följande två typer av webbplatser).  <br/> |
|TotalPlatser  <br/> |Antalet webbplatser som fanns vid tidsperiodens slut.  <br/> |
|DokumentCount  <br/> |Totalt antal dokument som fanns på webbplatsen vid tidsperiodens slut.  <br/> |
|Diplansed (diplansed)  <br/> |Total lagringskvot som används för alla webbplatserna vid tidsperiodens slut.  <br/> |
|ActivityType (Aktivitetstyp)  <br/> |Antalet webbplatser som registrerade de olika typerna av filaktivitet (valfri/aktiva filer/delade filer EXT/INT/synkroniserade filer).  <br/> Valfri betyder att någon av filaktiviteterna utfördes.  <br/> |
|WebbplatserMedOwnerActivities  <br/> |Antalet aktiva platser där webbplatsägaren utfört en viss filaktivitet på sina egna webbplatser.  <br/> |
|WebbplatserMedNonOwnerActivities  <br/> |Antalet aktiva platser som summeras för månaden, där andra användare än webbplatsägaren utfört en viss filaktivitet på webbplatser.  <br/> |
|ActivityTotalSites  <br/> |Antalet webbplatser där någon aktivitet registrerats inom tidsperioden. Om en webbplats hade aktivitet tidigare inom tidsperioden och sedan togs bort i slutet av tidsperioden skulle den fortfarande räknas in i totalen för den aktiva webbplatsen för den tidsperioden.  <br/> |
|Timeframe  <br/> |Den här kolumnen innehåller datumvärdet. Används som ett-till-många-samband för kalendertabellen.  <br/> |
|Content Date  <br/> |Om tidsperioden är aktuell månad representerar det här värdet det senaste datumet i den aktuella månaden för vilket det finns tillgängliga data.  <br/> Om tidsperioden är föregående månad representerar det här värdet det sista datumet i månaden inom tidsperioden.  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>Datatabell - klientorganisationens OneDrive-användning

Den här tabellen innehåller information om OneDrive-kontona, till exempel antalet konton, antalet dokument för alla OneDrive-konton, lagringsutrymme som används och antalet filer efter aktivitetstyp. Statusen vid månadsslutet för OneDrive för företag-konton som visas i den här tabellen. Om en användare till exempel skapar 5 dokument som använder 10MB av det totala lagringsutrymmet och sedan tar bort en del filer och lägger till andra filer så att han eller hon i slutet av månaden har 7 filer som använder 5MB lagringsutrymme, visas värdet vid månadsslutet i den här tabellen i slutet av månaden.
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|SiteType (Platstyp)  <br/> |Värdet är "OneDrive".  <br/> |
|TotalPlatser  <br/> |Antalet OneDrive för företag-konton som finns i slutet av tidsperioden.  <br/> |
|DokumentCount  <br/> |Det totala antalet dokument som fanns i alla OneDrive för företag-konton i slutet av tidsperioden  <br/> |
|Diplansed (diplansed)  <br/> |Totalt lagringsutrymme som används för alla OneDrive-konton vid tidsperiodens slut.  <br/> |
|ActivityType (Aktivitetstyp)  <br/> |Antalet konton som registrerade de olika typerna av filaktivitet (valfri/aktiva filer/delade filer EXT/INT/synkroniserade filer).  <br/> Valfri betyder att någon av filaktiviteterna utfördes  <br/> |
|WebbplatserMedOwnerActivities  <br/> |Antalet aktiva OneDrive för företag-konton, där kontoinnehavaren utfört en viss filaktivitet på sitt eget konto.  <br/> |
|WebbplatserMedNonOwnerActivities  <br/> |Antalet OneDrive för företag-konton där filaktivitet utförts av andra användare än kontoinnehavaren.  <br/> |
|ActivityTotalSites  <br/> |Antalet OneDrive för företag-konton som registrerat någon aktivitet under tidsperioden. Om ett OneDrive för företag-konto hade aktivitet tidigare under tidsperioden och sedan togs bort i slutet av tidsperioden skulle det fortfarande räknas som aktivt OneDrive för företag-konto för den tidsperioden.  <br/> |
|Timeframe  <br/> |Den här kolumnen innehåller datumvärdet. Används som ett-till-många-samband för kalendertabellen.  <br/> |
|Content Date  <br/> |Om tidsperioden är aktuell månad representerar det här värdet det senaste datumet i den aktuella månaden för vilket det finns tillgängliga data.  <br/> Om tidsperioden är föregående månad representerar det här värdet det sista datumet i månaden inom tidsperioden.  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>Datatabell – Användning av Microsoft 365-grupper för klientorganisation

Den här tabellen innehåller data om hur Microsoft 365-grupper används i hela organisationen.
  
****

|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|Tidsram  <br/> |Månadsvärdet. Det kommer att finnas en rad per produkt per månad för de senaste 12 månaderna, inklusive del av aktuell månad.  <br/> |
|Grupptyp  <br/> |Typ av grupp (privat/offentlig/alla).  <br/> |
|Totalt Antal grupper  <br/> |Antalet grupper i varje grupptyp.  <br/> |
|Aktiva grupper  <br/> |Antalet aktiva grupper.  <br/> |
|MBX_TotalGroups  <br/> |Antalet postlådegrupper.  <br/> |
|MBX_ActiveGroups  <br/> |Antalet aktiva postlådegrupper.  <br/> |
|MBX_TotalActivities  <br/> |Antalet postlådeaktiviteter.  <br/> |
|MBX_TotalItems  <br/> |Antalet postlådeobjekt.  <br/> |
|MBX_StorageUsed  <br/> |Mängden använt lagringsutrymme.  <br/> |
|SPO_TotalGroups  <br/> |Antalet SharePoint-grupper.  <br/> |
|SPO_ActiveGroups  <br/> |Antalet aktiva SharePoint-grupper.  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |Antalet SharePoint-grupper som har filåtkomstaktiviteter.  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |Antalet SharePoint-grupper som har filsynkroniseringsaktiviteter.  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |Antal SharePoint-grupper som har delat aktiviteter internt eller med grupper (som kan omfatta externa användare).  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |Antalet SharePoint-grupper som har externdelningsaktiviteter.  <br/> |
|SPO_TotalActivities  <br/> |Antalet SharePoint-aktiviteter.  <br/> |
|SPO_FileAccessedActivities  <br/> |Antalet SharePoint filåtkomstaktiviteter.  <br/> |
|SPO_FileSyncedActivities  <br/> |Antalet SharePoint filsynkroniseringsaktiviteter.  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |Antal delade SharePoint-filer internt eller med grupper (som kan innehålla externa medlemmar).  <br/> |
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

Tabellen innehåller data om antalet Office-prenumerationsaktiveringar i tjänstplanerna, till exempel Microsoft 365 Apps for enterprises, Visio, Project. Här finns även information om antalet aktiveringar per enhet (Android/iOS/Mac/PC).
  
|**Kolumnnamn**|**Kolumnbeskrivning**|
|:-----|:-----|
|ServicePlanName  <br/> |Lista med värden för namn på tjänstplaner och antalet aktiveringar efter enheter, som i kolumnerna nedan.  <br/> |
|TotaltEnabled  <br/> |Antalet användare som är aktiverade per tjänstplansnamn i slutet av tidsperioden.  <br/> |
|Totalt Inaktiveradeanvändare  <br/> |Antalet användare som har aktiverat de olika tjänstplanerna i slutet av tidsperioden.  <br/> |
|AndroidCount (AndroidCount)  <br/> |Antalet aktiveringar per tjänstplan för Android-enhet i slutet av tidsperioden.  <br/> |
|iOSCount (iOSCount)  <br/> |Antalet aktiveringar per tjänstplan för iOS-enhet i slutet av tidsperioden.  <br/> |
|MacCount (olikartade)  <br/> |Antalet aktiveringar per tjänstplan för MAC-enhet i slutet av tidsperioden.  <br/> |
|PcCount (olikartade)  <br/> |Antalet aktiveringar per tjänstplan för PC-enhet i slutet av tidsperioden.  <br/> |
|WinRtCount (olikartade)  <br/> |Antalet aktiveringar per tjänstplan för Windows Mobile-enhet i slutet av tidsperioden.  <br/> |
|Timeframe  <br/> |Den här kolumnen innehåller datumvärdet. Används som ett-till-många-samband för kalendertabellen.  <br/> |
|Content Date  <br/> |Om tidsperioden är aktuell månad representerar det här värdet det senaste datumet i den aktuella månaden för vilket det finns tillgängliga data.  <br/> Om tidsperioden är föregående månad representerar det här värdet det sista datumet i månaden inom tidsperioden.  <br/> |
   

