---
title: Vad kommer att ändras efter migreringen Office 365 tjänster i de nya tyska datacenterområdena
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Sammanfattning Förstå vad som har ändrats när du flyttar från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365 tjänster i den nya tyska datacenterområdet.
ms.openlocfilehash: 74ad9a662d3ea7a68ef1f82961864eb4468f6098
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591786"
---
# <a name="what-will-change-after-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Vad kommer att ändras efter migreringen Office 365 tjänster i de nya tyska datacenterområdena

Klientorganisationens migreringar har utformats för att ha minimal effekt på administratörer och användare. Det finns dock saker att tänka på för varje arbetsbelastning. Läs följande avsnitt för att få bättre förståelse för migreringsupplevelsen för arbetsbelastningen.

Här följer de viktigaste skillnaderna mellan Microsoft Cloud Deutschland och Office 365 i de nya tyska datacenterområdena.

| Kategori | Microsoft Cloud Germany (Microsoft Cloud Deutschland) | Office 365 i de nya tyska datacenterområdena |
|:-------|:-----|:-------|
| Microsoft 365-tjänster som är tillgängliga för prenumeration med bara Office 365 klientorganisation | 15 tjänster | 29 tjänster <br><br> Mer information finns i [Vad är tjänstens tillgänglighet mellan de olika Office 365 molntjänsterbjudandena?](ms-cloud-germany-transition.md#serv-avail). |
| Nya funktioner | Inga nya funktioner blir tillgängliga. | Nya funktioner blir tillgängliga konsekventa med Office 365 tjänster. |
| Dataförvaltaren | Ja | Nej |
| Samarbete mellan klientorganisation med globala Office 365 klientorganisationen | Nej | Ja |
| Kundens datahem | Kunddata lagras enbart i tyska datacenter. | Microsoft lagrar följande kunddata i vila exklusivt i Tyskland: <ul><li> Exchange Online innehållet i postlådan (brödtext, kalenderposter och innehållet i e-postbilagor) </li><li> SharePoint Onlinewebbplatsinnehåll och filer som lagrats på webbplatsen och filer som laddats upp till OneDrive för företag </li></ul> |
| Tillämpliga villkor | [Villkor för onlinetjänster](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) med detta [tillägg](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Villkor för onlinetjänster](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

Vad ändras inte:

- Klientorganisationens initiala domän (till `contoso.onmicrosoft.de` exempel ) med klientorganisations-ID (GUID) och anpassade domäner finns kvar efter migreringen. 

- Autentiseringsförfrågningar för resurser som migreras till Office 365-tjänster beviljas av Office 365 Azure-autentiseringstjänsten ( `login.microsoftonline.com` ). Under migreringen autentiseras resurser som fortfarande finns kvar i Office 365 Germany av den befintliga Azure-tjänsten för Tyskland ( `login.microsoftonline.de` ).

Att tänka på:

- För hanterade domänkonton måste kopieringen av den första Azure Active Directory-klientorganisationen (Azure AD) slutföras (vilket är det första steget av Azure AD-migrering till Azure AD-tjänstens Office 365-tjänster), lösenordsändringar, självbetjäning för återställning av lösenord (SSPR) och lösenordsåterställningar av administratörer måste göras från Office 365-tjänstportalerna. Begäran om att uppdatera lösenord från Tyskland-tjänsten kommer inte att lyckas i det här läget, eftersom Azure AD-klientorganisationen har migrerats till Office 365 tjänster. Återställningar av lösenord för federerade domäner påverkas inte, eftersom dessa har slutförts i den lokala katalogen.

- Azure-inloggningar visas i portalen där användaren försöker komma åt dem. Granskningsloggar är endast tillgängliga Office 365 slutpunkten för tjänster efter övergången. Innan migreringen är klar sparar du inloggnings- och granskningsloggar från Microsoft Cloud Deutschland-portalen.

- Återställning av lösenord, ändringar av lösenord, återställning av lösenord av en administratör för hanterade organisationer (som inte använder Active Directory Federation Services) måste utföras via Office 365 Services-portalen. Försök av användare som har åtkomst till Microsoft Cloud Deutschland-portaler att återställa lösenord kommer att misslyckas.

- Allmän dataskyddsförordning (GDPR) Data Subject Requests (DSRs) körs från Azure Office 365-administratörsportalen för framtida förfrågningar. Alla äldre eller icke-kunddiagnostikdata som finns i Microsoft Cloud Deutschland tas bort efter eller före 30 dagar.

## <a name="subscriptions--licenses"></a>Prenumerationer & Licenser

- Office 365 och Dynamics-prenumerationer från Microsoft Cloud Deutschland flyttas över till den tyska regionen med Azure AD-härjning. Organisationen uppdateras sedan för att återspegla nya abonnemang Office 365-tjänster. Under den korta överföringsprocessen av prenumerationer blockeras ändringar av prenumerationer.

- Allt eftersom klientorganisationen övergår till Office 365 tjänster standardiseras dess Tyskland-specifika abonnemang och licenser med nya funktioner Office 365-tjänster. Motsvarande Office 365 köpta abonnemang på de överförda Tyskland-prenumerationerna. Användare som har Germany-licenser tilldelas Office 365-tjänstelicenser. När det är klart avbryts de äldre Germany-prenumerationerna och tas bort från Office 365-tjänstklientorganisationen.

- Efter migrering av enskilda arbetsbelastningar blir ytterligare funktioner tillgängliga via Office 365-tjänsterna (till exempel Microsoft Planner och Microsoft Flow) på grund av de nya abonnemangen Office 365-tjänster. Om det passar för din organisation kan klientorganisationens eller licensadministratören inaktivera nya tjänstplaner när du planerar att ändra hanteringen och introducera de nya tjänsterna. Information om hur du inaktiverar tjänstplaner som är tilldelade till användarnas licenser finns i Inaktivera [åtkomst till Microsoft 365-tjänster när du tilldelar användarlicenser.](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)

## <a name="exchange-online"></a>Exchange Online

- Exchange för resurs-URL:er går över från den äldre `outlook.office.de` Tyskland-slutpunkten till Office 365-tjänstslutpunkten `outlook.office365.com` efter migreringen. Användarna kan komma åt sin migrerade postlåda med hjälp av den äldre URL-adressen tills migreringen har slutförts. Kunder bör gå över till den nya URL-adressen så snart som möjligt Exchange efter att migreringen har börjat så att den inte påverkar Tyskland-miljön. URL Office 365 för e-posttjänster Outlook blir tillgängliga först när Exchange migreringen har startat.

- Postlådor migreras som en backend-process. Användare i organisationen kan vara i antingen Microsoft Cloud Deutschland eller den tyska regionen under övergången och är en del av samma Exchange-organisation (i samma globala adresslista).

- Användare av Outlook Web App som använder tjänsten genom att använda en URL-adress där deras postlåda inte finns kommer att se en extra autentiseringsfråga. Om användarens postlåda till exempel finns i Office 365-tjänsterna och användarens Outlook Web App-anslutning använder den äldre slutpunkten autentiseras användaren först i och sedan `outlook.office.de` `login.microsoftonline.de` till `login.microsoftonline.com` . När migreringen är klar kan användaren komma åt den nya URL:en ( ), och de ser endast den `https://outlook.office365.com` enda, förväntade inloggningsförfrågan. 

## <a name="office-services"></a>Office Tjänster

Office Onlinetjänster är åtkomliga via `office.de` före och under övergången. När användarnas postlådor har övergåt till Office 365 tjänster bör användarna börja använda Office 365-URL:er. När efterföljande arbetsbelastningar migreras Office 365 tjänster börjar gränssnittet från office.com-portalen att fungera.

Den senast använda tjänsten (MRU) i Office är en övergång från Microsoft Cloud Deutschland till Office 365 globala tjänster, inte en migrering. Endast MU-länkar Office 365 globala tjänster visas efter migreringen från Office.com-portalen. MRU-länkar från Microsoft Cloud Deutschland visas inte som mrU-länkar i Office 365 globala tjänster. I Office 365 globala tjänster är MNAU-länkar bara tillgängliga när klientorganisationens migrering har nått fas 9.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- EOP-Exchange Online Protection backend-funktioner kopieras till den nya region i Tyskland.
- Office 365 Användare av säkerhets- och efterlevnadscentret måste gå över till att använda globala `https://protection.office.com` URL:er som en del av migreringen.

## <a name="skype-for-business-online"></a>Skype för företag – Online

Befintliga Skype för företag Online-kunder går över till Microsoft Teams. Mer information finns i [https://aka.ms/SkypeToTeams-Home](/microsoftteams/upgrade-start-here) .

## <a name="office-365-video"></a>Office 365 Video

Office 365 Video dras tillbaka den 1 mars 2021 och Office 365 Video stöds inte när migreringen av SharePoint Online till nya tyska datacenterområden har slutförts. Innehåll från Office 365 Video migreras som en del av migreringen SharePoint Online. Men videor i Office 365 Video spelas inte upp i användargränssnittet för Office 365 Video efter SharePoint migreringen. Läs mer om tidslinjen för migrering [Office 365 en videoövergång till översikten för Microsoft Stream (klassisk).](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="next-step"></a>Nästa steg

[Förstå åtgärder och påverkan på migreringsfaser](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365 i de nya tyska datacenterområdena](ms-cloud-germany-transition.md)
- [Migreringshjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du in för migrering](ms-cloud-germany-migration-opt-in.md)

Flytta genom övergången:

- [Åtgärder och påverkan i migreringsfaser](ms-cloud-germany-transition-phases.md)
- [Ytterligare arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Molnappar:

- [Information om Dynamics 365-migreringsprogram](/dynamics365/get-started/migrate-data-german-region)
- [Power BI i migreringsprogrammet](/power-bi/admin/service-admin-migrate-data-germany)
- [Komma igång med din Microsoft Teams uppgradering](/microsoftteams/upgrade-start-here)
