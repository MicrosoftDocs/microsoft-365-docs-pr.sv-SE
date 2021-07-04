---
title: Undersöka komprometterade konton med hjälp av Avancerad granskning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Använd granskningsåtgärden MailItemsAccessed för postlådan till att utföra tekniska undersökningar av komprometterade användarkonton.
ms.openlocfilehash: 64f3e5f3423f5182277fe7640199a39dc11068f2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288785"
---
# <a name="use-advanced-audit-to-investigate-compromised-accounts"></a>Undersöka komprometterade konton med hjälp av Avancerad granskning

Ett komprometterat användarkonto (kallas även *-kontoövertagande*) är en typ av attack när angriparen får åtkomst till ett användarkonto som användare. Den här typen av attacker kan ibland orsaka mer skada än vad angriparen har tänkt sig. När du undersöker komprometterade e-postkonton måste du förutsätta att mer e-postdata har komprometterats än vad som visas vid spårningen av angriparens faktiska närvaro. Beroende på typen av data i e-postmeddelandena måste du förutsätta att känslig information har komprometterats eller kan omfattas av tillsynsböter, såvida du inte kan bevisa att känslig information inte har exponerats. Exempelvis får HIPAA-reglerade organisationer avsevärda böter om det finns bevis på att information om patienthälsa har exponerats. I dessa fall är angriparna sannolikt inte intresserade av patienhälsoinformationen, men organisationen måste rapportera dataöverträdelserna såvida de inte kan bevisa något annat.

För att hjälpa dig att undersöka komprometterade e-postkonton granskar vi nu åtkomsten till e-postdata per e-postprotokoll och klienter med åtgärden *MailItemsAccessed* för postlådegranskning. Den här nya granskningsåtgärden gör det enklare att förstå e-postdataintrång och hjälper dig att se omfattningen av de specifika e-postobjekt som kan ha komprometterats. Syftet med att använda den här nya granskningsåtgärden är att få ett tekniskt skydd som garanterar att viss e-postdata inte har komprometterats. Om en angripare får åtkomst till ett visst e-postmeddelande granskas händelsen i Exchange Online, även om det inte finns någon indikation på att e-postobjektet faktiskt har lästs.

## <a name="the-mailitemsaccessed-mailbox-auditing-action"></a>Granskningsåtgärden MailItemsAccessed för postlådor

Den nya MailItemsAccessed-åtgärden ingår i den nya funktionen för [avancerad granskning](advanced-audit.md). Det är en del av [Exchanges postlådegranskning](/office365/securitycompliance/enable-mailbox-auditing#mailbox-auditing-actions) och är aktiverad som standard för användare som har tilldelats en Office 365- eller Microsoft 365 E5-licens, eller för organisationer med en prenumeration på tillägget Microsoft 365 E5 Compliance.

Granskningsåtgärden MailItemsAccessed för postlådor omfattar alla e-postprotokoll: POP, IMAP, MAPI, EWS, Exchange ActiveSync och REST. Den omfattar även båda typerna av åtkomst till e-post: *synkronisering* och *bindning*.

### <a name="auditing-sync-access"></a>Granskning av synkroniseringsåtkomst

Synkroniseringsåtgärder registreras bara när en postlåda används i en skrivbordsversion av Outlook-klienten för Windows eller Mac. Under synkroniseringen laddar dessa klienter vanligtvis ned en stor uppsättning e-postobjekt från molnet till en lokal dator. Granskningsvolymen för synkroniseringsåtgärder är enorm. I stället för att generera en granskningspost för varje e-postobjekt som synkroniseras, genererar vi bara en granskningshändelse för e-postmappen med de objekt som har synkroniserats. Det görs ett antagande att *alla* e-postobjekt i den synkroniserade mappen har komprometterats. Åtkomsttypen registreras i fältet OperationProperties i granskningsposten.

Se steg 2 i avsnittet [Använda MailItemsAccessed-granskningsposter för tekniska undersökningar](#use-mailitemsaccessed-audit-records-for-forensic-investigations) för ett exempel på hur du visar typen av synkroniseringsåtkomst i en granskningspost.

### <a name="auditing-bind-access"></a>Granskning av bindningsåtkomst

En bindningsåtgärd är en enskild åtkomst till ett e-postmeddelande. Vid bindningsåtkomst registreras InternetMessageId för enskilda meddelanden i granskningsposten. Granskningsåtgärden MailItemsAccessed registrerar bindningsåtgärderna som sedan sammanställs till en enda granskningspost. Alla bindningsåtgärder som utförs inom ett 2-minutersintervall sammanställs i en enskild granskningspost i fältet Mappar inom AuditData-egenskapen. Varje meddelande som öppnades identifieras med sitt InternetMessageId. Antalet bindningsåtgärder som sammanställdes i posten visas i fältet OperationCount i AuditData-egenskapen.

Se steg 4 i avsnittet [Använda MailItemsAccessed-granskningsposter för tekniska undersökningar](#use-mailitemsaccessed-audit-records-for-forensic-investigations) för ett exempel på hur du visar typen av bindningsåtkomst i en granskningspost.

### <a name="throttling-of-mailitemsaccessed-audit-records"></a>Begränsning av MailItemsAccessed-granskningsposter

Om fler än 1 000 MailItemsAccessed-granskningsposter genereras på mindre än 24 timmar, kommer Exchange Online att sluta generera granskningsposter för MailItemsAccessed-aktivitet. När en postlåda begränsas loggas inte MailItemsAccessed-aktiviteten i 24 timmar efter att postlådan har begränsats. Om det inträffar finns det en risk att postlådan har komprometterats under perioden. Registreringen av MailItemsAccessed-aktivitet återupptas efter en 24-timmars period.

Här är några saker att tänka på vid begränsning:

- Mindre än 1 % av alla postlådor i Exchange Online är begränsade
- När en postlåda är begränsad är det bara granskningsposter för MailItemsAccessed-aktiviteten som inte granskas. Andra granskningsåtgärder för postlådan påverkas inte.
- Postlådor begränsas endast för bindningsåtgärder. Granskningsposter för synkroniseringsåtgärder är inte begränsade.
- Om en postlåda är begränsad kan du antagligen förutsätta att det fanns MailItemsAccessed-aktivitet som inte registrerades i granskningsloggarna.

Se steg 1 i avsnittet [Använda MailItemsAccessed-granskningsposter för tekniska undersökningar](#use-mailitemsaccessed-audit-records-for-forensic-investigations) för ett exempel på hur du visar IsThrottled-egenskapen i en granskningspost.

## <a name="use-mailitemsaccessed-audit-records-for-forensic-investigations"></a>Använda MailItemsAccessed-granskningsposter för tekniska undersökningar

En granskning av postlådor genererar granskningsposter för åtkomst till e-postmeddelanden, så att du kan vara säker på att e-postmeddelandena inte har komprometterats. När vi inte är säkra på att åtkomst har funnits till viss data, antar vi därför att detta har skett genom att registrera all e-poståtkomstaktivitet.

Användningen av MailItemsAccessed-granskningsposter i tekniskt syfte utförs vanligtvis när ett dataintrång har åtgärdats och angriparen har avlägsnats. Påbörja undersökningen genom att identifiera den uppsättning postlådor som har komprometterats och fastställ tidsperioden då angriparen hade åtkomst till postlådor i organisationen. Du kan sedan använda cmdletarna **Search-UnifiedAuditLog** eller **Search-MailboxAuditLog** i [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) för att söka i granskningsposter som motsvarar dataintrånget.

Du kan köra ett av följande kommandon för att söka efter MailItemsAccessed-granskningsposter:

**Enhetlig granskningslogg**:

```powershell
Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000
```

**Granskningslogg för postlåda**:

```powershell
Search-MailboxAuditLog -Identity <user> -StartDate 01/06/2020 -EndDate 01/20/2020 -Operations MailItemsAccessed -ResultSize 1000 -ShowDetails
```

> [!TIP]
> En viktig skillnad mellan dessa två cmdletar är att du kan använda cmdleten **Search-UnifiedAuditLog** till att söka efter granskningsposter för aktivitet som har utförts av en eller flera användare. Det beror på att *UserIds* är en parameter med flera värden. Cmdleten **Search-MailboxAuditLog** söker i granskningsloggen för postlådan efter en enskild användare.

Här är stegen för att använda MailItemsAccessed-granskningsposter vid undersökning av ett komprometterat användarangrepp. Varje steg visar kommandosyntaxen för cmdletarna **Search-UnifiedAuditLog** eller **Search-MailboxAuditLog**.

1. Kontrollera om postlådan har begränsats. I så fall kan det innebära att vissa granskningsposter för postlådan inte har loggats. Om någon granskningspost har ”IsThrottled” som ”Sant” kan du förutsätta att under en 24-timmarsperiod efter att posten genererades granskades inte någon åtkomst till postlådan och att alla e-postdata har komprometterats.

   Om du vill söka efter MailItemsAccessed-poster där postlådan var begränsad kör du följande kommando:

   **Enhetlig granskningslogg**:

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"IsThrottled","Value":"True"*'} | FL
   ```

   **Granskningslogg för postlåda**:

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*IsThrottled:True*"} | FL
   ```

2. Kontrollera om det finns synkroniseringsaktiviteter. Om en angripare använder en e-postklient för att hämta meddelanden i en postlåda, kan de koppla bort datorn från Internet och komma åt meddelandena lokalt utan att interagera med servern. Det innebär att granskningen av postlådan inte kan granska de här aktiviteterna.

   Om du vill söka efter MailItemsAccessed-poster där e-postobjekten användes av en synkroniseringsåtgärd, kör du följande kommando:

   **Enhetlig granskningslogg**:

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 02/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Sync"*'} | FL
   ```

   **Granskningslogg för postlåda**:

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Sync*"} | FL
   ```

3. Kontrollera synkroniseringsaktiviteterna för att fastställa om någon av dem har inträffat i samma kontext som den som användes av angriparen. Kontext identifieras och differentieras av IP-adressen till den klientdator som används för åtkomst till postlådan och e-postprotokollet. Mer information finns i avsnittet [Identifiera åtkomstkontexterna för olika granskningsposter](#identifying-the-access-contexts-of-different-audit-records).

   Använd egenskaperna nedan vid undersökningen. Egenskaperna finns i egenskapen AuditData eller OperationProperties. Om någon av synkroniseringarna sker i samma kontext som angriparens aktivitet, förutsätter du att angriparen har synkroniserat alla e-postobjekt till klienten, vilket innebär att hela postlådan troligen har komprometterats.

   <br>

   ****

   |Egenskap|Beskrivning|
   |---|---|
   |ClientInfoString|Beskriver protokoll och klient (inkl. version)|
   |ClientIPAddress|IP-adressen till klientdatorn.|
   |SessionId|Med ett sessions-ID kan du skilja på angriparens åtgärder och dagliga användaraktiviteter på samma konto (om ett konto har komprometterats)|
   |UserId|UPN för användaren som läser meddelandet.|
   |

4. Kontrollera om det finns bindningsaktiviteter. När du har utfört steg 2 och 3 kan du vara säker på att all annan åtkomst till e-postmeddelanden för angriparen fångas i granskningsposterna för MailItemsAccessed som har egenskapen MailAccessType med värdet ”Bindning”.

   Om du vill söka efter MailItemsAccessed-poster där e-postobjekten användes av en bindningsåtgärd kör du följande kommando.

   **Enhetlig granskningslogg**:

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Bind"*'} | FL
   ```

   **Granskningslogg för postlåda**:

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Bind*"} | FL
   ```

   E-postmeddelanden som har öppnats identifieras med sitt ID för Internetmeddelanden. Du kan också kontrollera om några granskningsposter har samma kontext som de i angriparens aktivitet. Mer information finns i avsnittet [Identifiera åtkomstkontexterna för olika granskningsposter](#identifying-the-access-contexts-of-different-audit-records).

   Du kan använda granskningsdata för bindningsåtgärder på två olika sätt:

   - Komma åt eller samla in alla e-postmeddelanden som angriparen fick åtkomst till med hjälp av InternetMessageId för att hitta dem och sedan kontrollera om något av dessa meddelanden innehåller känslig information.
   - Använda InternetMessageId för att söka efter granskningsposter som är relaterade till en uppsättning potentiellt känsliga e-postmeddelanden. Det här är användbart om du bara är orolig för ett litet antal meddelanden.

## <a name="filtering-of-duplicate-audit-records"></a>Filtrera dubbletter av granskningsposter

Dubbletter av granskningsposter för samma bindningsåtgärder som inträffar inom en timme filtreras bort. Synkroniseringsåtgärder filtreras också bort med en timmes intervall. Undantag till dedupliceringsprocessen inträffar om någon av egenskaperna som beskrivs i tabellen nedan skiljer sig för samma InternetMessageId. Om en av de här egenskaperna skiljer sig åt vid en dubblettåtgärd genereras en ny granskningspost. Den här processen beskrivs mer ingående i nästa avsnitt.

<br>

****

|Egenskap|Beskrivning|
|---|---|
|ClientIPAddress|IP-adressen till klientdatorn.|
|ClientInfoString|Klientprotokollet som klienten använde för att komma åt postlådan.|
|ParentFolder|Den fullständiga mappsökvägen till det e-postobjekt som öppnades.|
|Logon_type|Inloggningstypen för användaren som utförde åtgärden. Inloggningstyperna (och deras motsvarande uppräkningsvärde) är Ägare (0), Administratör (1) eller Ombud (2).|
|MailAccessType|Om åtkomsten är en bindnings- eller synkroniseringsåtgärd.|
|MailboxUPN|UPN för postlådan där det lästa meddelandet finns.|
|Användare|UPN för användaren som läser meddelandet.|
|SessionId|Sessions-ID:t används till att skilja på angriparens åtgärder och dagliga användaraktiviteter i samma postlåda (om kontot har komprometterats). Mer information om sessioner finns i [Sammanhangsberoende angreppsaktivitet i sessioner i Exchange Online](https://techcommunity.microsoft.com/t5/exchange-team-blog/contextualizing-attacker-activity-within-sessions-in-exchange/ba-p/608801).|
|

## <a name="identifying-the-access-contexts-of-different-audit-records"></a>Identifiera åtkomstkontexterna för olika granskningsposter

Det är vanligt att en angripare får åtkomst till en postlåda samtidigt som postlådans ägare öppnar den. Det finns granskningspostegenskaper som definierar åtkomstkontexten som används för att skilja mellan åtkomst av angriparen och postlådans ägare. Som tidigare beskrivits genereras separata granskningsposter när värdena för de här egenskaperna är olika, även om aktiviteten inträffar inom aggregeringsintervallet. I följande exempel finns det tre olika granskningsposter. Var och en differentieras med hjälp av sessions-ID och ClientIPAddress-egenskaper. De meddelanden som öppnas identifieras också.

<br>

****

|Granskningspost 1|Granskningspost 2|Granskningspost 3|
|---|---|---|
|ClientIPAddress **1**<br/>SessionId **2**|ClientIPAddress **2**<br/>SessionId **2**|ClientIPAddress **1**<br/>SessionId **3**|
|InternetMessageId **A**<br/>InternetMessageId **D**<br/>InternetMessageId **E**<br/>InternetMessageId **F**<br/>|InternetMessageId **A**<br/>InternetMessageId **C**|InternetMessageId **B**|
|

Om någon av egenskaperna i tabellen i föregående [avsnitt](#filtering-of-duplicate-audit-records) skiljer sig åt, genereras en separat granskningspost för att kunna spåra den nya kontexten. Åtkomsterna sorteras i de separata granskningsposterna beroende på den kontext där aktiviteten ägde rum.

I exempelvis de granskningsposter som visas i följande skärmbild, sorteras åtkomstaktiviteten i olika granskningsposter beroende på den kontext där åtkomsten ägde rum, även om vi öppnar e-posten från EWSEditor och OWA samtidigt. I det här fallet definieras kontexten med olika värden för ClientInfoString-egenskapen.

![Olika granskningsposter utifrån kontext](../media/MailItemsAccessed4.png)

Här är syntaxen för kommandot som visades i föregående skärmbild:

```powershell
Search-MailboxAuditLog -Identity admin -ShowDetails -Operations MailItemsAccessed -ResultSize 2000 | Select LastAccessed,Operation,AuditOperationsCountInAggregatedRecord,ClientInfoString
```
