---
title: Åtgärder och konsekvenser för migreringen
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Sammanfattning: förstå åtgärderna för migrering och påverkan av förflyttning från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster i det nya tyska Data Center-området.'
ms.openlocfilehash: 9ffdb0bbe60bdb96d6e110ac08cba4030272c7e9
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551663"
---
# <a name="migration-phases-actions-and-impacts"></a>Åtgärder och konsekvenser för migreringen

Migrering av klient organisationer från Microsoft Cloud Deutschland till Tyskland i Microsofts Office 365-tjänster körs som en uppsättning konfigurerade åtgärder för varje arbets belastning. Dessa åtgärder säkerställer att viktiga data och erfarenheter migreras till Office 365-tjänsterna. När klient organisationen har lagts till i migreringsarkivet bevaras varje belastning som en uppsättning steg som körs på backend-tjänsten. Vissa arbets belastningar kan kräva att administratörer (eller användare) eller migreringen kan påverka användning för de faser som körs och diskuteras i [hur är migreringen organiserad?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Följande avsnitt innehåller åtgärder och effekter för arbets belastning allteftersom de fortskrider genom olika faser av migreringen. Granska tabellerna och se vilka åtgärder som gäller för din organisation. Se till att du är för beredd att utföra stegen i respektive faser efter behov. Om det inte går att slutföra nödvändiga åtgärder kan det orsaka avbrott i tjänsten och kan fördröja migreringen till Office 365-tjänsterna.

## <a name="exchange-online"></a>Exchange Online

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Ny tysk region läggs till i befintlig organisations konfiguration och post lådor flyttas till Office 365-tjänster. | Med Exchange Online-konfiguration läggs den nya lokala tyska regionen till i över gången. Den här Office 365-regionen är inställd som standard, vilket gör det möjligt för intern belastnings utjämning att distribuera post lådor till rätt standard region i Office 365-tjänster. I den här över gången finns användare på vardera sidan (Tyskland eller Office 365-tjänster) inom samma organisation och kan använda antingen URL-slutpunkt. | Exchange Online | -Över gångs användare och tjänster från Tyskland URL-adresser till Office 365-adresser ( `https://outlook.office365.com` ). <br><br> -Användare kommer att fortsätta använda tjänsten via äldre Tyskland-URL: er under migreringen. Ingen omedelbar åtgärd nödvändig. <br><br> -Användarna bör börja använda office.com-portalen för Office Online-funktioner (kalender, e-post, kontakter). Navigering till tjänster som ännu inte migrerats till Office 365-tjänster fungerar inte förrän migreras. <br><br> -Outlook Web App tillhandahåller inte den offentliga mappens upplevelse under migreringen. |
|||||

Om du vill veta mer om skillnaderna mellan organisationer i migreringen och efter att Exchange Online-resurserna har migrerats läser du informationen i [kund upplevelsen under migreringen till Office 365-tjänster i de nya tyska Data Center-tjänsterna](ms-cloud-germany-transition-experience.md).

## <a name="exchange-online-protection"></a>Exchange Online Protection

Backend Exchange Online Protection (EOP)-funktioner kopieras till nytt Tyskland. 

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Migrering av Exchange Online-Routning och historik meddelanden. | Med Exchange Online kan du routas från externa värdar till Office 365. De externa MX-posterna övergår till routing till EOP-tjänsten. Klient konfiguration och historik information migreras. | Exchange Online-kunder | -Microsoft-hanterade DNS-poster uppdateras från Office 365 Germany EOP till Office 365-tjänster. <br><br> -Kunderna bör vänta 30 dagar efter EOP dubbel skrivning för EOP-migrering. Annars kan data gå förlorade. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

<!--

| Step(s) | Description | Applies to | Impact |
|:-------|:-----|:-------|:-------|
| SharePoint and OneDrive are transitioned. | SharePoint and OneDrive are migrated from Microsoft Cloud Deutschland to Office 365 services in this phase. Existing Microsoft Cloud Deutschland URLs are preserved (for example, `contoso.sharepoint.de`). Tokens that were issued by Microsoft Cloud Deutschland or Office 365 services are valid during the transition. | SharePoint customers | - Content will be read-only for two brief periods (less than x minutes) during migration. During this time, expect a "you can't edit content" banner in SharePoint. <br><br> - The search index won't be preserved, and may take up to 10 days to be rebuilt. <br><br> - SharePoint/OneDrive content will be read-only for two brief periods (less than x minutes) during migration. Users will see a "you can't edit content" banner briefly during this time. <br><br> - The search index may be unavailable while the index is rebuilt. During this period, search queries might not return complete results. <br><br> - Existing sites are preserved. |
|||||

--> 

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| SharePoint och OneDrive är över gången. | SharePoint och OneDrive migreras från Microsoft Cloud Deutschland till Office 365-tjänster i den här fasen. Befintliga Microsoft Cloud Deutschland-URL: er bevaras (till exempel `contoso.sharepoint.de` ). Token som har utfärdats av Microsoft Cloud Deutschland eller Office 365-tjänsterna är giltiga under över gången. | SharePoint-kunder | -Innehållet blir skrivskyddat under två korta perioder under migreringen. Under den här tiden förväntar vi dig en "det går inte att redigera innehåll" i SharePoint. <br><br> -Sök indexet sparas inte och kan ta upp till 10 dagar innan det återskapas. <br><br> -SharePoint/OneDrive-innehåll är skrivskyddat under två korta perioder under migreringen. Användarna ser en "du kan inte redigera innehållet"-banderollen kortas under den här tiden. <br><br> -Sök indexet kanske inte är tillgängligt när indexet återskapas. Under den här perioden kan det hända att Sök frågor inte returnerar fullständiga resultat. <br><br> -Befintliga webbplatser bevaras. |
|||||


## <a name="skype-for-business-online"></a>Skype för företag online

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Migrering av Skype för företag till Teams. | Befintliga Skype för företag-kunder migreras till Office 365-tjänster i Europa och sedan övergår till Microsoft Teams i Tyskland för Office 365-tjänster. | Skype för företag-kunder | -Användare kan inte logga in på Skype för företag på migrations datumet. Tio dagar före migreringen meddelar vi slutanvändare via den Skype för företag-klient som de uppgraderar till Teams. Vi kommer även att publicera i administrations centret om dessa ändringar inträffar efter de 10 dagarna. <br><br> -Princip konfigurationen migreras. <br><br> -Användarna migreras till Teams och har inte längre Skype för företag efter migreringen. <br><br> -Användare måste ha en stationär klient program vara installerad. Installationen sker under de tio dagarna via policyn i Skype för företag-infrastrukturen, men om det inte fungerar kan användarna ändå Ladda ner klienten eller ansluta med en webbläsare som stöds. <br><br> -Kontakter och möten migreras till Teams. <br><br> -Användare kan inte logga in på Skype för företag mellan tids tjänst över gångar till Office 365-tjänster, och inte förrän kundernas DNS-poster har slutförts. <br><br> -Kontakter och befintliga möten fortsätter att fungera som Skype för företag-möten. |
|||||
        
## <a name="subscription"></a>Prenumerationsvy

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Vi kan inte migrera kunder utan medgivande. | Microsoft får rätten att migrera på två olika sätt, vilket gör att Microsoft dirigerar över gången från data och tjänster till Office 365 Services-instansen. <br> Administratören väljer att använda Microsoft-driven migration. <br> Kunderna förnyar eventuella prenumerationer i sin Microsoft Cloud Deutschland-klient organisation efter den 1 maj 2020. Vi meddelar de här kunderna om migreringen varje månad, vänta 30 dagar för att ge kunderna chansen att avbryta och sedan direkt välja dem som spåras i ICM. | Alla Office-kunder | -Klient organisationen har marker ATS som översänt för migrering och administrations centret visar bekräftelse. <br><br> -Bekräftelse skickas till molnet i Tyskland. Tjänst konfigurationen fortsätter från Microsofts moln Deutschland slut punkter. <br><br> -Övervaka meddelande Center för uppdateringar av status för tillståndsmigrering. |
| Abonnemang överförs och licenser omfördelas. | När klient organisationen har gått över till Office 365 365-tjänster köps prenumerationen på de överförda abonnemangen för Microsoft Cloud Deutschland. Användare med tilldelade licenser för Microsoft Cloud Deutschland tilldelas Office 365-tjänst licenser. Microsoft Cloud Deutschland-prenumerationer tas bort från Office 365-klient organisationen när den är klar. | Alla Office-kunder | -Ändringar av befintliga abonnemang kommer att blockeras (till exempel inga nya abonnemangs köp eller ändringar av antalet) under den här fasen. <br><br> -Ändringar av licens tilldelning kommer att blockeras. <br><br> -Abonnemanget för Microsoft Cloud Deutschland migreras till motsvarande Office 365-tjänst-prenumeration. Office 365-tjänsterna för abonnemanget definieras av Microsoft (kallas även för _erbjudande mappning_). <br><br> -Antalet funktioner (tjänste abonnemang) som erbjuds av Office 365-tjänster kan vara större än det ursprungliga Microsoft Cloud Deutschland-erbjudande. Användar licenser i Office 365-tjänster är likvärdigt kopplade till liknande Microsoft Cloud Deutschland-funktioner (tjänste abonnemang). Användar licenser för alla användare tilldelas automatiskt till de nya funktionerna. Administratören måste vidta en uttrycklig åtgärd för att inaktivera dessa licenser om det behövs. <br><br> -När migreringen är klar kommer både Office 365-tjänsterna och Germany för Tyskland att synas i administrations portalen för Office 365, med statusen för Tyskland _deprovisioned_-abonnemangen. <br><br> -Användare tilldelas licenser som är kopplade till nya Office 365-abonnemang. Alla kund processer som är beroende av Tyskland-abonnemang eller SKU-GUID blir skadade och måste ändras med Office 365-tjänstens erbjudande. <br><br> -Nya prenumerationer i Office 365-tjänsterna kommer att köpas med den nya termen (per månad/kvartal eller år) och kunden får en proportionell åter betalning för den outnyttjade balansen för Microsoft Cloud Deutschland-prenumerationen. <br><br> -Partner Deutschland-klient organisationer migreras inte. CSP-kunder migreras till Office 365-tjänster under den nya Office 365-tjänstens klient organisation. Efter migrering kan partnern bara hantera den här kunden från Office 365-tjänstens klient organisation. <br><br> -Fler funktioner är tillgängliga (till exempel Microsoft Planner och Microsoft-flöde) om inte inaktive ras av klient organisationens administratör. Information om hur du inaktiverar tjänste abonnemang som är tilldelade till användarnas licenser finns i [inaktivera åtkomst till Microsoft 365-tjänster när du tilldelar användar licenser](disable-access-to-services-while-assigning-user-licenses.md).  |
|||||

## <a name="next-step"></a>Nästa steg

[Utför ytterligare arbete](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska Data Center-regionerna](ms-cloud-germany-transition.md)
- [Hjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kund upplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom över gången:

- [Övrig för hands arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information om [tjänster](ms-cloud-germany-transition-add-general.md), [enheter](ms-cloud-germany-transition-add-devices.md), [erfarenheter](ms-cloud-germany-transition-add-experience.md)och [AD FS](ms-cloud-germany-transition-add-adfs.md).

Molnappar:

- [Information om programmet för Dynamics 365 migration](https://aka.ms/d365ceoptin)
- [Information om datamigreringshanteraren för Power BI](https://aka.ms/pbioptin)
- [Komma igång med din uppgradering av Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
