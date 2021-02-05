---
title: Åtgärder och effekter för migreringsfaserna för migreringen från Microsoft Cloud Deutschland (allmänt)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 01/26/2021
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
description: 'Sammanfattning: Förstå åtgärderna i migreringsfaserna och hur de påverkar flytten från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterområdet.'
ms.openlocfilehash: c0fdfc83bbdb8ec4c2f408cef113a487908957bf
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110035"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Åtgärder och effekter för migreringsfaserna för migreringen från Microsoft Cloud Deutschland (allmänt)

Klientmigrering från Microsoft Cloud Deutschland till Regionen Tyskland för Microsofts Office 365-tjänster utförs som en uppsättning faser och deras konfigurerade åtgärder för varje arbetsbelastning. I den här bilden visas de nio faserna av migreringen till de nya tyska datacenteren.

![De nio faserna av migreringen till de nya Tyskland-datacenter](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Faserna och deras åtgärder säkerställer att kritiska data och upplevelser migreras till Office 365-tjänsterna. När klientorganisationen har lagts till i migreringskön slutförs varje arbetsbelastning som en uppsättning steg som körs på backend-tjänsten. Vissa arbetsbelastningar kan kräva åtgärder av administratören (eller användaren), eller så kan migreringen påverka användningen av faserna som utförs och diskuteras i Hur organiseras [migreringen?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Följande avsnitt innehåller åtgärder och effekter för arbetsbelastningar när de fortskrider genom olika faser av migreringen. Granska tabellerna och bestäm vilka åtgärder eller effekter som gäller för din organisation. Se till att du är redo att utföra stegen i respektive fas efter behov. Om du inte utför de steg som krävs kan det leda till avbrott i tjänsten och kan fördröja slutförandet av migreringen till Office 365-tjänsterna.

## <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (fas 4 av 9)

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| SharePoint och OneDrive har nu övergångar. | SharePoint och OneDrive migreras från Microsoft Cloud Deutschland till Office 365-tjänster i den här fasen. Befintliga URL-adresser för Microsoft Cloud Deutschland bevaras (till `contoso.sharepoint.de` exempel). Token som har utfärdats av Microsoft Cloud Deutschland eller Office 365-tjänster är giltiga under övergången. | SharePoint-kunder | – Innehållet är skrivskyddat under två korta perioder under migreringen. Under tiden kan du förvänta dig en banderoll som säger att du inte kan redigera innehåll i SharePoint. <br><br> - Sökindexet bevaras inte och kan ta upp till 10 dagar tills det återskapas. <br><br> – SharePoint-/OneDrive-innehåll är skrivskyddat under två korta perioder under migreringen. Användarna kommer att se banderollen "du kan inte redigera innehåll" kort under denna tid. <br><br> - Sökindexet kanske inte är tillgängligt när indexet återskapas. Under den här perioden kan det hända att sökfrågor inte returnerar fullständiga resultat. <br><br> – Befintliga webbplatser bevaras. |
|||||

Ytterligare överväganden:

- När SharePoint Online-migreringen till den tyska regionen är slutförd återskapas dataindex. Funktioner som är beroende av sökindex kan påverkas när du indexerar om.

- Om organisationen fortfarande använder SharePoint 2010-arbetsflöden kommer de inte längre att fungera efter den 31 december 2021. SharePoint 2013-arbetsflöden stöds fortfarande, även om de är inaktiverade som standard för nya klientorganisationen från och med den 1 november 2020. När migreringen till SharePoint Online-tjänsten är klar rekommenderar vi att du går över till Power Automate eller andra lösningar som stöds.

- När OneDrive-migreringen till den tyska regionen slutförs återskapas dataindex. Funktioner som är beroende av sökindex kan påverkas när omindexeringen pågår.

- Microsoft Cloud Deutschland-kunder vars SharePoint Online-instans ännu inte har migrerats måste stanna kvar på SharePoint Online PowerShell-modulen/Microsoft.SharePointOnline.CSOM version 16.0.20616.12000 eller senare. Annars misslyckas anslutningar till SharePoint Online via PowerShell eller objektmodellen på klientsidan.

- Microsoft Cloud Deutschland-kunder vars SharePoint Online-instans har migrerats måste uppdatera SharePoint Online PowerShell-modulen/Microsoft.SharePointOnline.CSOM till version 16.0.20717.12000 eller senare. Annars misslyckas anslutningar till SharePoint Online via PowerShell eller objektmodellen på klientsidan.


## <a name="exchange-online-phase-5-of-9"></a>Exchange Online (fas 5 av 9)

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Nya Tyskland-regionen läggs till i den befintliga organisationskonfigurationen och postlådor flyttas till Office 365-tjänster. | Exchange Online-konfigurationen lägger till den nya lokala tyska regionen i övergången. Det här Office 365-tjänsteområdet är inställt som standard, vilket gör att den interna belastningsutjämningstjänsten kan distribuera postlådor till rätt standardområde i Office 365-tjänster. I den här övergången finns användarna på vardera sidan (Tyskland eller Office 365-tjänster) i samma organisation och kan använda någon av URL-slutpunkterna. | Exchange Online | - Gå över till URL-adresser för Office 365-tjänster från Tyskland (URL:er) till Office 365-tjänster `https://outlook.office365.com` (). <br><br> – Användarna fortsätter att få åtkomst till tjänsten via äldre Tyskland-URL:er under migreringen. Ingen omedelbar åtgärd krävs. <br><br> - Användarna bör börja använda office.com Office Online-funktioner (kalender, e-post, kontakter). Navigering till tjänster som ännu inte migrerats till Office 365-tjänster måste migreras. <br><br> - Outlook Web App tillhandahåller inte den gemensamma mappen under migreringen. |
|||||

Ytterligare överväganden:

- `myaccount.msft.com` fungerar bara efter office 365-övergången. Länkar ger felmeddelanden om att något gick fel tills dess.

- Användare av Outlook Web App som har åtkomst till en delad postlåda i den andra miljön (till exempel om en användare i Tyskland-miljön har åtkomst till en delad postlåda i den globala miljön) uppmanas att autentisera en andra gång. Användaren måste först autentisera och komma åt postlådan i `outlook.office.de` och sedan öppna den delade postlådan som finns `outlook.office365.com` i. De måste autentiseras en andra gång när de har åtkomst till de delade resurser som finns i den andra tjänsten.

- För befintliga Microsoft Cloud Deutschland-kunder eller under övergång: när en delad postlåda läggs till i Outlook med hjälp av **File > Info > Lägg** till konto kan det hända att kalenderbehörigheter inte kan visas (Outlook-klienten försöker använda Rest `https://outlook.office.de/api/v2.0/Me/Calendars` API).) Kunder som vill lägga till ett konto för att visa kalenderbehörigheter kan lägga till registernyckeln enligt beskrivningen i Användarupplevelse ändringar för delning av en kalender i [Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) för att säkerställa att den här åtgärden kommer att lyckas. Den här registernyckeln kan distribueras i hela organisationen med hjälp av grupprincip.

- Under migreringsfasen kan det uppstå fel (fel på proxy) om du använder **PowerShell-cmdlets** Ny **migreringEndpoint, Set-MigrationEndpoint** och **Test-MigrationsServerAvailability.** Det här inträffar när skiljeförfarandespostlådan har migrerats till hela världen men inte administratörspostlådan har det eller vice versa. Du kan lösa problemet genom att använda skiljepostlådan som tips om routning i ConnectionUri när du skapar PowerShell-sessionen **för klientorganisationen.** Till exempel: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Om du använder Exchange Online-hybrid:

    - Du måste köra hybridkonfigurationsguiden (HCW) igen för att uppdatera den lokala konfigurationen mot Microsoft Cloud Deutschland innan övergången och köra HCW igen vid rensning mot Office 365-tjänsterna. Ytterligare DNS-uppdateringar kan krävas om du använder anpassade domäner.

Om du vill veta mer om skillnaderna för organisationer vid migrering och när Exchange Online-resurser har migrerats kan du läsa informationen i Kundupplevelse under migreringen till [Office 365-tjänster](ms-cloud-germany-transition-experience.md)i de nya tyska datacenterområdena.

## <a name="exchange-online-protection-phase-6-of-9"></a>Exchange Online Protection (fas 6 av 9)

Backend Exchange Online Protection (EOP) funktioner kopieras till den nya Tyskland-region. 

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Migrering av Exchange Online-routning och historiska meddelandedetaljer. | Exchange Online aktiverar routning från externa värdar till Office 365. De externa MX-posterna förs över till routen till EOP-tjänsten. Klientkonfiguration och historisk information migreras. | Exchange Online-kunder | – Microsoft-hanterade DNS-poster uppdateras från Office 365 Germany EOP till Office 365-tjänster. <br><br> - Kunder bör vänta i 30 dagar efter EOP med dubbla skrivning för EOP-migrering. Annars kan data gå förlorade. |
|||||



## <a name="skype-for-business-online-phase-7-of-9"></a>Skype för företag – Online (fas 7 av 9)

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Migrering av Skype för företag till Teams. | Befintliga Skype för företag-kunder migreras till Office 365-tjänster i Europa och flyttas sedan till Microsoft Teams i Tyskland-regionen för Office 365-tjänster. | Skype för företag-kunder | – Användarna kan inte logga in i Skype för företag på migreringsdatumet. Tio dagar före migreringen publicerar vi ett inlägg i administrationscentret för att berätta när migreringen kommer att ske, och igen när vi påbörjar migreringen. <br><br> - Principkonfigurationen migreras. <br><br> - Användarna migreras till Teams och kommer inte längre att ha Skype för företag efter migreringen. <br><br> - Användarna måste ha Teams-skrivbordsklienten installerad. Installationen sker under de 10 dagarna via principen för Infrastrukturen för Skype för företag, men om det misslyckas måste användarna fortfarande ladda ned klienten eller ansluta med en webbläsare som stöds. <br><br> - Kontakter och möten migreras till Teams. <br><br> - Användarna kan inte logga in i Skype för företag mellan tidstjänstens övergångar till Office 365-tjänster och inte förrän dns-posterna från kunder har slutförts. <br><br> - Kontakter och befintliga möten fortsätter att fungera som Skype för företag-möten. |
|||||

## <a name="office-services"></a>Office-tjänster

Den senast använda tjänsten i Office är en övergång från Tyskland-tjänsten till Office 365-tjänster, inte en migrering. Endast MNA-länkar från Office 365-tjänstsidan kommer att visas efter migreringen Office.com portalen. MRU-länkar från Tyskland-tjänsten visas inte som mru-länkar i Office 365-tjänster. I Office 365 är MNA-länkar bara tillgängliga när klientorganisationen har migrerat.

## <a name="subscription"></a>Prenumeration

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Vi kan inte migrera kunder utan medgivande. | Microsoft får rätten att migrera på ett av två sätt, vilket gör att Microsoft kan överföra data och tjänster till Office 365-tjänstinstansen. <br> Administratören väljer att delta i den Microsoft-drivna migreringen. <br> Kunder förnyar alla prenumerationer i Sin Microsoft Cloud Deutschland-klientorganisation efter den 1 maj 2020. Vi meddelar dessa kunder om migreringen varje månad, vänta i 30 dagar för att ge kunderna möjlighet att avbryta och sedan registrera sig direkt i ICM. | Alla Office-kunder | – Klientorganisationen har markerats som godkännande för migrering och admincentret visar en bekräftelse. <br><br> - Bekräftelse publiceras i Cloud Germany Message Center-klientorganisationen. Tjänstkonfigurationen fortsätter från Microsoft Cloud Deutschland-slutpunkter. <br><br> - Övervaka meddelandecentret för uppdateringar om status för migreringsfasen. |
| Prenumerationer överförs och licenser tilldelas om. | När klientorganisationen har övergåt till Office 365-tjänster köps motsvarande Office 365-tjänstprenumerationer till de överförda Microsoft Cloud Deutschland-prenumerationerna. Användare med tilldelade Microsoft Cloud Deutschland-licenser tilldelas Office 365-tjänstlicenser. Äldre Microsoft Cloud Deutschland-prenumerationer tas bort från Office 365-tjänstklientorganisationen när de slutförs. | Alla Office-kunder | – Ändringar av befintliga prenumerationer kommer att blockeras (t.ex. inga ändringar av nya prenumerationsköp eller antal platser) under den här fasen. <br><br> - Ändringar av licenstilldelning blockeras. <br><br> - Microsoft Cloud Deutschland-prenumerationen migreras till motsvarande Office 365-tjänstprenumeration. Office 365-tjänsterbjudandet för prenumerationen definieras av Microsoft (kallas även _erbjudandemappning)._ <br><br> - Antalet funktioner (tjänstplaner) som erbjuds av Office 365-tjänster kan vara större än i det ursprungliga Microsoft Cloud Deutschland-erbjudandet. Användarlicenser i Office 365-tjänster tilldelas likvärdigt med liknande Microsoft Cloud Deutschland-funktioner (tjänstplaner). Användarlicenserna för alla användare tilldelas automatiskt de nya funktionerna. Administratören måste vidta en uttrycklig åtgärd för att inaktivera licenserna, om det behövs. <br><br> – När prenumerationsmigrering har slutförts visas både Office 365-tjänster och Germany-prenumerationer i administrationsportalen för Office 365, med statusen för Germany-prenumerationer som _återkallad._ <br><br> - Användare kommer att omtilldelas licenser som är kopplade till de nya prenumerationerna på Office 365-tjänster. Alla kundprocesser som har beroenden på Germany-prenumerationer eller SKU GUID bryts och måste revideras med Office 365-tjänsterbjudandet. <br><br> - Nya prenumerationer på Office 365-tjänsterna köps med den nya perioden (varje månad/kvartal/år), och kunden får en prorerad återbetalning för det oanvända saldot för Microsoft Cloud Deutschland-prenumerationen. <br><br> – Partner Microsoft Cloud Deutschland-klientorganisationen migreras inte. Kunder som använder CSP migreras till Office 365-tjänster enligt den nya Klientorganisationen för Office 365-tjänster hos samma partner. Efter kundmigrering kan partnern endast hantera den här kunden från Office 365-tjänstklientorganisationen. <br><br> - Ytterligare funktioner är tillgängliga (till exempel Microsoft Planner och Microsoft Flow), om de inte inaktiveras av administratören för klientorganisationen. Mer information om hur du inaktiverar tjänstplaner som tilldelas till användarnas licenser finns i Inaktivera åtkomst till [Microsoft 365-tjänster när du tilldelar användarlicenser.](disable-access-to-services-while-assigning-user-licenses.md)  |
|||||

## <a name="next-step"></a>Nästa steg

[Utföra ytterligare förarbete](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska datacenterområdena](ms-cloud-germany-transition.md)
- [Migreringshjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du in för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kundupplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom övergången:

- [Ytterligare förarbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och AD [FS.](ms-cloud-germany-transition-add-adfs.md)

Molnappar:

- [Information om Dynamics 365-migreringsprogram](https://aka.ms/d365ceoptin)
- [Information om migreringsprogrammet för Power BI](https://aka.ms/pbioptin)
- [Komma igång med uppgraderingen till Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
