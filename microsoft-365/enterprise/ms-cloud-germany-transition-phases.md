---
title: Åtgärder och konsekvenser för migreringen från Microsoft Cloud Deutschland (allmänt)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
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
ms.openlocfilehash: 940ad0799aca7ead20d226cfcf3cc4b7b21c6cdb
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760204"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Åtgärder och konsekvenser för migreringen från Microsoft Cloud Deutschland (allmänt)

Migrering av klient organisationer från Microsoft Cloud Deutschland till Tyskland i Microsofts Office 365-tjänster körs som en uppsättning konfigurerade åtgärder för varje arbets belastning. Dessa åtgärder säkerställer att viktiga data och erfarenheter migreras till Office 365-tjänsterna. När klient organisationen har lagts till i migreringsarkivet bevaras varje belastning som en uppsättning steg som körs på backend-tjänsten. Vissa arbets belastningar kan kräva att administratörer (eller användare) eller migreringen kan påverka användning för de faser som körs och diskuteras i [hur är migreringen organiserad?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Följande avsnitt innehåller åtgärder och effekter för arbets belastning allteftersom de fortskrider genom olika faser av migreringen. Granska tabellerna och se vilka åtgärder som gäller för din organisation. Se till att du är för beredd att utföra stegen i respektive faser efter behov. Om det inte går att slutföra nödvändiga åtgärder kan det orsaka avbrott i tjänsten och kan fördröja migreringen till Office 365-tjänsterna.

## <a name="exchange-online"></a>Exchange Online

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Ny tysk region läggs till i befintlig organisations konfiguration och post lådor flyttas till Office 365-tjänster. | Med Exchange Online-konfiguration läggs den nya lokala tyska regionen till i över gången. Den här Office 365-regionen är inställd som standard, vilket gör det möjligt för intern belastnings utjämning att distribuera post lådor till rätt standard region i Office 365-tjänster. I den här över gången finns användare på vardera sidan (Tyskland eller Office 365-tjänster) inom samma organisation och kan använda antingen URL-slutpunkt. | Exchange Online | -Över gångs användare och tjänster från Tyskland URL-adresser till Office 365-adresser ( `https://outlook.office365.com` ). <br><br> -Användare kommer att fortsätta använda tjänsten via äldre Tyskland-URL: er under migreringen. Ingen omedelbar åtgärd nödvändig. <br><br> -Användarna bör börja använda office.com-portalen för Office Online-funktioner (kalender, e-post, kontakter). Navigering till tjänster som ännu inte migrerats till Office 365-tjänster fungerar inte förrän migreras. <br><br> -Outlook Web App tillhandahåller inte den offentliga mappens upplevelse under migreringen. |
|||||

Ytterligare överväganden:

- `myaccount.msft.com` fungerar bara efter snabbmigrering av Office 365. Länkar ger fel meddelandet "något gick fel" till den tiden.

- Användare av Outlook Web App som har till gång till en delad post låda i den andra miljön (till exempel att en användare i Tyskland får åtkomst till en delad post låda i den globala miljön) uppmanas att verifiera en andra gång. Användaren måste först verifiera och komma åt post lådan i `outlook.office.de` och sedan öppna den delade post lådan `outlook.office365.com` . De måste verifiera en andra gång när de använder de delade resurserna som finns på den andra tjänsten.

- Om du har en delad post låda i Outlook genom att använda **fil > information > Lägg till konto**, kan det hända att det inte går att använda REST API för befintliga Microsoft Cloud-Deutschland kunder eller dem i över gången `https://outlook.office.de/api/v2.0/Me/Calendars` . Kunder som vill lägga till ett konto för att Visa kalender behörigheter kan lägga till register nyckel enligt beskrivningen i [användar miljö ändringar för att dela en kalender i Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) för att kontrol lera att åtgärden lyckas. Denna register nyckel kan distribueras till hela organisationen med hjälp av grup princip.

- Under migreringsprocessen kan du använda PowerShell-cmdleten **New-migrationEndpoint**, **set-migrationEndpoint** och **test-MigrationsServerAvailability** kan resultera i fel (fel på proxy). Det här inträffar om medlings post lådan har migrerats till över hela världen men administratörs post lådan inte har eller vice versa. Lös problemet genom att använda medlings post lådan som cirkulations fältet i **ConnectionUri** när du skapar klientens PowerShell-session. Till exempel: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Om du använder Exchange Online hybrid:

    - Du måste köra hybrid konfigurations guiden igen (HCW) för att uppdatera lokal konfiguration mot Microsoft Cloud Deutschland före över gången och sedan köra HCW vid rensning mot Office 365-tjänsterna. Ytterligare DNS-uppdateringar kan krävas om du använder anpassade domäner.

Om du vill veta mer om skillnaderna mellan organisationer i migreringen och efter att Exchange Online-resurserna har migrerats läser du informationen i [kund upplevelsen under migreringen till Office 365-tjänster i de nya tyska Data Center-tjänsterna](ms-cloud-germany-transition-experience.md).

## <a name="exchange-online-protection"></a>Exchange Online Protection

Backend Exchange Online Protection (EOP)-funktioner kopieras till nytt Tyskland. 

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Migrering av Exchange Online-Routning och historik meddelanden. | Med Exchange Online kan du routas från externa värdar till Office 365. De externa MX-posterna övergår till routing till EOP-tjänsten. Klient konfiguration och historik information migreras. | Exchange Online-kunder | -Microsoft-hanterade DNS-poster uppdateras från Office 365 Germany EOP till Office 365-tjänster. <br><br> -Kunderna bör vänta 30 dagar efter EOP dubbel skrivning för EOP-migrering. Annars kan data gå förlorade. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| SharePoint och OneDrive är över gången. | SharePoint och OneDrive migreras från Microsoft Cloud Deutschland till Office 365-tjänster i den här fasen. Befintliga Microsoft Cloud Deutschland-URL: er bevaras (till exempel `contoso.sharepoint.de` ). Token som har utfärdats av Microsoft Cloud Deutschland eller Office 365-tjänsterna är giltiga under över gången. | SharePoint-kunder | -Innehållet blir skrivskyddat under två korta perioder under migreringen. Under den här tiden förväntar vi dig en "det går inte att redigera innehåll" i SharePoint. <br><br> -Sök indexet sparas inte och kan ta upp till 10 dagar innan det återskapas. <br><br> -SharePoint/OneDrive-innehåll är skrivskyddat under två korta perioder under migreringen. Användarna ser en "du kan inte redigera innehållet"-banderollen kortas under den här tiden. <br><br> -Sök indexet kanske inte är tillgängligt när indexet återskapas. Under den här perioden kan det hända att Sök frågor inte returnerar fullständiga resultat. <br><br> -Befintliga webbplatser bevaras. |
|||||

Ytterligare överväganden:

- När SharePoint Online-migreringen har slutförts till tyska-regionen återskapas data indexet. Funktioner som är beroende av Sök index kan påverkas när Omindexering är klar.

- Om din organisation ändå använder SharePoint 2010-arbetsflöden fungerar de inte längre efter 31 december 2021. SharePoint 2013-arbets flöden fortsätter att fungera men är inaktiverat som standard för nya klient organisationer som börjar den 1 november 2020. När migreringen till SharePoint Online-tjänsten är klar rekommenderar vi att du går vidare till Power automatisering eller andra lösningar som stöds.

- När migreringen av OneDrive har genomförts till den tyska regionen återskapas data indexet. Funktioner som är beroende av Sök index kan påverkas under Omindexering.

- Microsoft Cloud Deutschland kunder vars SharePoint Online-instans ännu inte migrerats måste finnas kvar på SharePoint Online PowerShell-modulen/Microsoft. SharePointOnline. CSOM version 16.0.20616.12000 eller tidigare. Annars Miss lyckas anslutningar till SharePoint Online via PowerShell eller klient objekt modellen.

- Microsoft Cloud Deutschland-kunder vars SharePoint Online-instans migreras måste uppdatera SharePoint Online PowerShell-modulen/Microsoft. SharePointOnline. CSOM till version 16.0.20717.12000 eller senare. Annars Miss lyckas anslutningar till SharePoint Online via PowerShell eller klient objekt modellen.


## <a name="skype-for-business-online"></a>Skype för företag online

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Migrering av Skype för företag till Teams. | Befintliga Skype för företag-kunder migreras till Office 365-tjänster i Europa och sedan övergår till Microsoft Teams i Tyskland för Office 365-tjänster. | Skype för företag-kunder | -Användare kan inte logga in på Skype för företag på migrations datumet. Tio dagar före migreringen skickar vi till administrations centret för att informera dig om när migreringen sker och när vi påbörjar migreringen. <br><br> -Princip konfigurationen migreras. <br><br> -Användarna migreras till Teams och har inte längre Skype för företag efter migreringen. <br><br> -Användare måste ha en stationär klient program vara installerad. Installationen sker under de tio dagarna via policyn i Skype för företag-infrastrukturen, men om det inte fungerar kan användarna ändå Ladda ner klienten eller ansluta med en webbläsare som stöds. <br><br> -Kontakter och möten migreras till Teams. <br><br> -Användare kan inte logga in på Skype för företag mellan tids tjänst över gångar till Office 365-tjänster, och inte förrän kundernas DNS-poster har slutförts. <br><br> -Kontakter och befintliga möten fortsätter att fungera som Skype för företag-möten. |
|||||

## <a name="office-services"></a>Office-tjänster

Den senast använda tjänsten i Office är en snabbmigrering från Tyskland-tjänsten till Office 365-tjänster, inte en migrering. Endast MRU-länkar från Office 365-sidan visas efter migrering från Office.com-portalen. MRU-länkar från Tyskland-tjänsten visas inte som MRU-länkar i Office 365-tjänster. I Office 365 är MRU-länkar endast tillgängliga när klient migreringen har slutförts.

## <a name="subscription"></a>Prenumerationsvy

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Vi kan inte migrera kunder utan medgivande. | Microsoft får rätten att migrera på två olika sätt, vilket gör att Microsoft dirigerar över gången från data och tjänster till Office 365 Services-instansen. <br> Administratören väljer att använda Microsoft-driven migration. <br> Kunderna förnyar eventuella prenumerationer i sin Microsoft Cloud Deutschland-klient organisation efter den 1 maj 2020. Vi meddelar de här kunderna om migreringen varje månad, vänta 30 dagar för att ge kunderna chansen att avbryta och sedan direkt välja dem som spåras i ICM. | Alla Office-kunder | -Klient organisationen har marker ATS som översänt för migrering och administrations centret visar bekräftelse. <br><br> -Bekräftelse skickas till molnet i Tyskland. Tjänst konfigurationen fortsätter från Microsofts moln Deutschland slut punkter. <br><br> -Övervaka meddelande Center för uppdateringar av status för tillståndsmigrering. |
| Abonnemang överförs och licenser omfördelas. | När klient organisationen har gått över till Office 365 365-tjänster köps prenumerationen på de överförda abonnemangen för Microsoft Cloud Deutschland. Användare med tilldelade licenser för Microsoft Cloud Deutschland tilldelas Office 365-tjänst licenser. Microsoft Cloud Deutschland-prenumerationer tas bort från Office 365-klient organisationen när den är klar. | Alla Office-kunder | -Ändringar av befintliga abonnemang kommer att blockeras (till exempel inga nya abonnemangs köp eller ändringar av antalet) under den här fasen. <br><br> -Ändringar av licens tilldelning kommer att blockeras. <br><br> -Abonnemanget för Microsoft Cloud Deutschland migreras till motsvarande Office 365-tjänst-prenumeration. Office 365-tjänsterna för abonnemanget definieras av Microsoft (kallas även för _erbjudande mappning_). <br><br> -Antalet funktioner (tjänste abonnemang) som erbjuds av Office 365-tjänster kan vara större än det ursprungliga Microsoft Cloud Deutschland-erbjudande. Användar licenser i Office 365-tjänster är likvärdigt kopplade till liknande Microsoft Cloud Deutschland-funktioner (tjänste abonnemang). Användar licenser för alla användare tilldelas automatiskt till de nya funktionerna. Administratören måste vidta en uttrycklig åtgärd för att inaktivera dessa licenser om det behövs. <br><br> -När migreringen är klar kommer både Office 365-tjänsterna och Germany för Tyskland att synas i administrations portalen för Office 365, med statusen för Tyskland -abonnemangen. <br><br> -Användare tilldelas licenser som är kopplade till nya Office 365-abonnemang. Alla kund processer som är beroende av Tyskland-abonnemang eller SKU-GUID blir skadade och måste ändras med Office 365-tjänstens erbjudande. <br><br> -Nya prenumerationer i Office 365-tjänsterna kommer att köpas med den nya termen (per månad/kvartal eller år) och kunden får en proportionell åter betalning för den outnyttjade balansen för Microsoft Cloud Deutschland-prenumerationen. <br><br> -Partner Deutschland-klient organisationer migreras inte. CSP-kunder migreras till Office 365-tjänster under den nya Office 365-tjänstens klient organisation. Efter migrering kan partnern bara hantera den här kunden från Office 365-tjänstens klient organisation. <br><br> -Fler funktioner är tillgängliga (till exempel Microsoft Planner och Microsoft-flöde) om inte inaktive ras av klient organisationens administratör. Information om hur du inaktiverar tjänste abonnemang som är tilldelade till användarnas licenser finns i [inaktivera åtkomst till Microsoft 365-tjänster när du tilldelar användar licenser](disable-access-to-services-while-assigning-user-licenses.md).  |
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
- Ytterligare information för [Azure AD](ms-cloud-germany-transition-azure-ad.md), [enheter](ms-cloud-germany-transition-add-devices.md), [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS](ms-cloud-germany-transition-add-adfs.md).

Molnappar:

- [Information om programmet för Dynamics 365 migration](https://aka.ms/d365ceoptin)
- [Information om datamigreringshanteraren för Power BI](https://aka.ms/pbioptin)
- [Komma igång med din uppgradering av Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
