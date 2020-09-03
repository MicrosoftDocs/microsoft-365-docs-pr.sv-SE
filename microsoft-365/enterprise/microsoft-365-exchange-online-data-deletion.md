---
title: Microsoft 365 Exchange Online-Databorttagning
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Lär dig hur mjuka och hårda data borttagningar för post lådor och objekt i post lådor hanteras i Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63bb5dcde334f7c53554f910b1a8d17e1d0d69cc
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332526"
---
# <a name="exchange-online-data-deletion-in-microsoft-365"></a>Exchange Online-Databorttagning i Microsoft 365

I Exchange Online finns det två typer av borttagningar: mjuka borttagningar och borttagningar. Detta gäller både post lådor och objekt i en post låda.

## <a name="soft-deleted-and-hard-deleted-mailboxes"></a>Raderade och borttagna post lådor
En mjuk, borttagen post låda är en post låda som tagits bort med hjälp av Microsoft 365 Admin Center eller cmdleten Remove-Mailbox och som fortfarande finns i Azure Active Directory-pappers korgen i mindre än 30 dagar. En post låda kan tas bort på något av följande sätt:
- Användar post lådans associerade Azure Active Directory-användar konto är mjuk – borttaget (användarobjektet är utanför scopet eller i behållaren för pappers korgen).
- Användar post lådans associerade Azure Active Directory-användarkonto har tagits bort, men Exchange Online-postlådan är under en behållar spärr eller eDiscovery-undantag.
- Användar post lådans associerade Azure Active Directory-konto har tagits bort under de senaste 30 dagarna. vilket är den maximala Retentions tids längd som Exchange Online behåller post lådan i ett läget mjukt borttaget innan den tas bort permanent.

En permanent användar post låda är en post låda som tagits bort på något av följande sätt:
- Användarens post låda har tagits bort i mer än 30 dagar och den associerade Azure Active Directory-användaren har tagits bort. Allt innehåll i post lådan som e-postmeddelanden, kontakter och filer tas bort permanent.
- Användar kontot som är kopplat till användarens post låda har tagits bort från Azure Active Directory. Användarens post låda är nu mjuk – borttagen i Exchange Online och finns i ett läget mjukt borttaget i 30 dagar. Om den 30-dagars perioden en ny Azure Active Directory-användare synkroniseras från det ursprungliga mottagar kontot med samma **ExchangeGUID** eller **ArchiveGuid**och det nya kontot är licensierat för Exchange Online, innebär detta att den ursprungliga post lådan tas bort. Allt innehåll i post lådan som e-postmeddelanden, kontakter och filer tas bort permanent.
- En borttagen post låda tas bort med hjälp av **Remove-Mailbox-PermanentlyDelete**.

Ovanstående borttagnings scenarion utgår från att användarens post låda inte finns i något av spärr tillstånd, till exempel en anslags åtgärd eller eDiscovery. Om det finns någon typ av undantag i post lådan kan du inte ta bort post lådan. För alla typer av e-post-användare ignoreras alla [undantags](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e?ui=en-US&rs=en-US&ad=US) inställningar och har ingen effekt på hårda borttagningar eller borttagningar.

## <a name="soft-deleted-and-hard-deleted-items"></a>Mjukt borttagna och hårt använda objekt
När en användare tar bort ett post låda-objekt (till exempel ett e-postmeddelande, en kontakt, en avtalad tid i kalendern eller en uppgift) flyttas objektet till mappen återställnings bara objekt och till en undermapp med namnet "borttagna". Detta kallas för en mjuk borttagning. Hur länge borttagna objekt behålls i mappen Borttaget beror på vilken bevarande period för borttagna objekt som är inställd för post lådan. En Exchange Online-postlåda behåller borttagna objekt i 14 dagar som standard, men Exchange Online-administratörer kan ändra den här inställningen för att öka tiden till maximalt 30 dagar. (Detaljerade anvisningar om hur du kan öka lagrings perioden för borttagna objekt för en Exchange Online-postlåda finns i [ändra hur länge permanent borttagna objekt sparas för en Exchange Online-postlåda](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/change-deleted-item-retention).) Användare kan återställa eller tömma borttagna objekt innan Retentions tiden för ett borttaget objekt upphör. För att göra det använder de funktionen Återskapa borttagna objekt i Microsoft Outlook eller Outlook på webben.

Om en användare tar bort ett borttaget objekt med hjälp av funktionen Återställ borttagna objekt i Outlook eller Outlook på webben kallas det för att ta bort en hård borttagning. I Exchange Online är återställning av enskilt objekt aktiverat som standard när en ny post låda skapas, så att en administratör kan ändå [återställa](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/recover-deleted-messages) pappers borttagna objekt innan lagrings perioden för borttagna objekt går ut. Om ett meddelande ändras av en användare eller process bevaras också kopior av originalobjektet när enkel återställning av objekt aktive ras.

## <a name="page-zeroing"></a>Nollställa Sidan
Att *nollställa* är en säkerhetsmekanism som skriver antingen nollor eller ett binärt mönster jämfört med borttagna data så att borttagna data blir svårare att återställa. I Exchange Online använder Mailbox-databaser *sidor* som lagrings enhet och implementerar en överskrivnings process som kallas *sid nollor*. Sidan nollställning är aktive rad som standard och kan inte inaktive ras av kunder eller av Microsoft. Åtgärderna för att nollställa sidan registreras i transaktionsloggfiler så att alla kopior av en viss databas visas på liknande sätt. Om du nollställer en sida i en aktiv databas kopia får sidan en nolla för passiva kopior av databasen.

Med sid nolla skrivs ett binärt mönster över borttagna poster. Mönstret för sid nollor är specifikt för ESE-operationer (Extensible Storage Engine) (namnet på den interna databas motorn som används av servrar i Exchange Online), och den är inte samma som för körning av bakgrunds databaser. (Bakgrunds databas underhåll är en process som kontinuerligt kontrollerar kontroll och läser varje databas. Dess primär funktion är att beräkna kontrollernas databas sidor, men det går också att rensa och nollställa poster och sidor som inte har nollställts på grund av en lagrings krasch.)

I följande tabell visas de fyllnings mönster som motsvarar specifika kör tids operationer.

| Körning av ESE-åtgärd   | Fyllnings mönster |
|--------------------------|--------------|
| Byter                  | F            |
| Ta bort inspelning/lång värde | D            |
| Fritt sid avstånd         | T            |


I följande tabell visas de fyllnings mönster som motsvarar specifika åtgärder som inträffar under en databas underhåll av ESE-bakgrunden.

| Underhåll av ESE-databas | Fyllnings mönster |
|-----------------------------------------------|--------------|
| Ta bort post                                 | D            |
| Ta bort långt värde                             | L            |
| Fritt sid avstånd i en delvis Använd sida       | Z            |
| Fritt sid rymd med oanvänd sida               | L            |


### <a name="page-zeroing-process"></a>Processen för att nollställa Sidan
Processen för att nollställa sidan beror på borttagnings scenariot. I följande tabell beskrivs hur databas borttagningar fungerar och när en sida nollställs.

| Scenario för databas borttagning | ESE-process och-tidsram till noll-databas data |
|-----------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Objektet upphör att gälla baserat på det borttagna objektets lagrings tid. | En asynkron tråd skriver ett binärt mönster över borttagna data. Den här åtgärden sker inom millisekunder av borttagningen av en post. Om lagrings processen kraschar när det asynkrona nollning-jobbet fortfarande är försenat (eller om rensning av versions lagret avbröts på grund av att versions lagret har avbrutits), slutförs nollan när underhåll av bakgrunds databas behandlas i databasen. |
| Visa scenario: sista giltighets tiden för objekt från Outlook/Outlook i webblayoutläge (till exempel konversations läge) | Data nollor inträffar när databas underhåll i bakgrunden i databasen. |
| Flytta post låda/ta bort post låda scenario: käll post lådan tas bort (upphör att gälla) | Data nollor inträffar när databas underhåll i bakgrunden i databasen. |

### <a name="mailbox-data-types-without-page-zeroing"></a>Data typer för post lådor utan sid nollor
Följande data typer för post lådor har inga bestämmelser för sid nollor:
- **Databas loggar för post lådor** – när transaktions loggar tas bort som en del av vanliga åtgärder finns det ingen process för att nollställa de block i fil systemet som innehåller de borttagna loggfilerna. Det är troligt att fil systemet snabbt kan återanvända det lediga utrymmet för nya loggar, men det finns ingen garanti för att det sker.
- **Katalogfiler för innehålls index** – Exchange Online använder search Foundation (kallas även snabb sökning) för Sök indexerings funktionen. Sök index katalogen består av flera dussin filer som lagras på samma volym som databas filen för post lådan. När ett meddelande tas bort permanent från post lådans databas tas inte innehållet i Sök katalogen bort omedelbart. Innehållet tas bort när Sök tjänsten gör en skugg-eller huvud sammanslagning av många små katalogfiler i en enda större fil. När huvud sammanslagningen är slutförd tas de mindre katalogfilerna bort. Det finns ingen process för att nollställa de block som innehåller de borttagna katalogfilerna.

## <a name="continuous-replication"></a>Kontinuerlig replikering
Kontinuerlig replikering (kallas även för loggning) är en teknik i Exchange Online som skapar och underhåller kopior av varje Mailbox-databas för att tillhandahålla hög tillgänglighet, webbplats återhämtning och katastrof återställning. Kontinuerlig replikering använder Exchange Server-databasen för krasch återställning för att tillhandahålla teknik som utför asynkron uppdatering av en eller flera kopior av en post låda. Varje server för post lådor registrerar databas uppdateringar i en aktiv databas (till exempel en användares e-postaktivitet) som logg poster i en sekventiell uppsättning med 1 MB transaktionsloggfiler. Denna uppsättning filer kallas för logg strömmen. Vid kontinuerlig replikering används logg strömmen också för att asynkront uppdatera en eller flera kopior av en databas. Det gör du genom att överföra loggarna till en plats som innehåller en passiv kopia av den aktiva databasen och sedan spela upp den i den passiva databas kopian. Om alla loggar från den aktiva databasen upprepas till en passiv kopia av databasen, är de två databaserna likvärdiga och den är den som används för att replikera en fysisk ändring i en aktiv databas till alla passiva kopior av databasen.

Eventuell borttagning från en post lådans databas, oavsett om det är en post låda eller en hel post låda och om det är en mjuk borttagning eller en borttagning, representerar en fysisk ändring i den aktiva databasen. Med sid nollor kan du också göra fysiska ändringar i den aktiva databasen. Dessa ändringar skrivs till loggfilerna genom en process som heter kontinuerlig replikering och när dessa loggfiler spelas upp mot passiva kopior av databasen görs samma fysiska ändringar i de passiva databaserna.