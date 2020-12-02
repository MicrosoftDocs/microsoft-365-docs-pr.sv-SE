---
title: Kund upplevelse under migreringen till Office 365-tjänster i de nya tyska Data Center-regionerna
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
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 'Sammanfattning: förstå upplevelsen av att flytta från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster i det nya tyska data centret.'
ms.openlocfilehash: a44fbe504a9a710856deeb3baf258feb124ce7ae
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551701"
---
# <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Kund upplevelse under migreringen till Office 365-tjänster i de nya tyska Data Center-regionerna

Migrering av klient organisationer har utformats för att få minimal påverkan på administratörer och användare. Men det finns faktorer för varje arbets belastning. Kontrol lera följande avsnitt för att få en bättre förståelse för migreringsprocessen.

Här följer viktiga skillnader mellan Microsoft Cloud Deutschland och Office 365-tjänsterna i de nya tyska Data Center-regionerna.

| Kategori | Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) | Office 365-tjänster i de nya tyska Data Center-områdena |
|:-------|:-----|:-------|
| Microsoft 365-tjänster som är tillgängliga för abonnemang med bara en Office 365-klient organisation | 15 tjänster | 29 tjänster <br><br> Mer information finns i [Vad är tjänst tillgänglighet mellan de olika Office 365 Cloud Service-tjänsterna?](ms-cloud-germany-transition.md#serv-avail). |
| Nya funktioner | Det finns inga nya funktioner. | Nya funktioner blir tillgängliga i överensstämmelse med Office 365-tjänster. |
| Data förvaltare | Ja | Nej |
| Samarbete mellan innehavare med globala Office 365-klient organisationer | Nej | Ja |
| De för kund data | Kunddata lagras bara i tyska Data Center. | Microsoft lagrar följande Kunddata endast i Tyskland: <ul><li> Innehåll för Exchange Online-postlådan (e-post, kalender poster och innehållet i e-postbilagor) </li><li> SharePoint Online-webbinnehåll och filer som lagrats på webbplatsen och filer som laddats upp till OneDrive för företag </li></ul> |
| Tillämpliga villkor | [Villkor för online tjänster](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) med detta [tillägg](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Villkor för online tjänster](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

Vad är inte ändrat:

- Den första domänen i klient organisationen (till exempel `contoso.onmicrosoft.de` ) med klient organisationens ID (GUID) och anpassade domäner kvarstår efter migreringen. 

- Autentiseringsbegäranden för resurser som migreras till Office 365-tjänster beviljas av Office 365-tjänsterna Azure-autentiseringstjänst ( `login.microsoftonline.com` ). Under migreringen autentiseras resurser som fortfarande finns kvar i Office 365 Tyskland av den befintliga Tyskland Azure-tjänsten ( `login.microsoftonline.de` ).

Tänk på följande:

- För hanterade domän konton, efter kopiering av den första Azure Active Directory (Azure AD)-klient organisationen, är fullständig (vilket är det första steget i Azure AD migration till Office 365 Services Azure AD-tjänsten), lösen ords ändringar, självbetjäning för återställning av lösen ord och lösen ord som ska återställas av administratörer måste göras från Office 365-tjänstens portaler. Det går inte att uppdatera lösen ord från Tyskland-tjänsten just nu eftersom Azure AD-innehavaren har migrerats till Office 365-tjänster. Återställning av sammanslagna domän lösen ord påverkas inte, eftersom dessa är slutförda i den lokala katalogen.

- Azure-inloggningar visas i portalen där användaren försöker komma åt den. Gransknings loggar är endast tillgängliga från Office 365-tjänstens slut punkt efter över gången. Innan migreringen genomförs måste du spara inloggnings-och gransknings loggar från Microsoft Cloud Deutschland-portalen.

- Återställning av lösen ord, lösen ords ändringar och lösen ordet återställs av en administratör för hanterade organisationer (som inte använder Active Directory Federation Services) måste utföras via Office 365-tjänst portalen. Användare som har till gång till Microsoft Cloud Deutschland portaler kan inte återställa lösen ord.

- Allmänna data inGDPRs begär Anden (DSRs) körs från administrations portalen för Office 365-tjänsterna Azure för framtida förfrågningar. Alla äldre och icke-kunddiagnostikdata som är bosatta i Microsoft Cloud Deutschland tas bort på eller före 30 dagar.

## <a name="subscriptions--licenses"></a>Abonnemang & licenser

- Office 365-och Dynamics-abonnemang från Microsoft Cloud Deutschland övergår till det tyska området med Azure AD reposition. Organisationen uppdateras då och visar nya Office 365-abonnemang. Under den korta abonnemangs överförings processen blockeras ändringar av abonnemang.

- Eftersom klient organisationen övergår till Office 365-tjänster är dess Tyskland-specifika abonnemang och licenser standardiserade med nya Office 365-tjänster. Motsvarande Office 365-abonnemang köps för de överförda Tyskland-abonnemangen. Användare som har Tyskland-licenser tilldelas Office 365-tjänste licenser. Vid slut för ande avbryts äldre Germany för Tyskland från den aktuella Office 365-tjänstens klient organisation.

- När de enskilda arbets belastningarna migreras blir fler funktioner tillgängliga via Office 365-tjänsterna (till exempel Microsoft Planner och Microsoft-flöde) på grund av de nya abonnemangen för Office 365-tjänster. Om det är lämpligt för din organisation kan klient organisationen eller licensierings administratören inaktivera nya tjänst planer när du planerar för ändrings hantering för att introducera de nya tjänsterna. Råd om hur du inaktiverar tjänste abonnemang som är tilldelade till användarnas licenser finns i [inaktivera åtkomst till Microsoft 365-tjänster när du tilldelar användar licenser](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

## <a name="exchange-online"></a>Exchange Online

- URL-adresser över från den äldre Tyskland `outlook.office.de` till Office 365-tjänstens slut punkt `outlook.office365.com` efter migreringen. Användarna kan komma åt sina migrerade post lådor genom att använda den gamla URL-adressen tills migreringen är slutförd. Kunderna bör överta användare till den nya URL: en så snart som möjligt efter det att Exchange-migreringen inte påverkar pensions miljön. Office 365-tjänsterna för Outlook Services blir bara tillgängliga när Exchange-migreringen startar.

- Post lådor migreras som en server del. Användare i din organisation kan vara i Microsoft Cloud Deutschland eller den tyska regionen under över gången och ingår i samma Exchange-organisation (i samma globala adress lista).

- Användare av Outlook Web App som använder tjänsten genom att använda en URL-adress där post lådan inte finns visas med en extra behörighets fråga. Om användarens post låda till exempel finns i Office 365-tjänsterna och användarens Outlook Web App-anslutning använder den äldre slut punkten `outlook.office.de` autentiseras användaren till `login.microsoftonline.de` och sedan till `login.microsoftonline.com` . När migreringen är slutförd kan användaren komma åt den nya URL: en ( `https://outlook.office365.com` ), och de kommer bara att se den enda förväntade inloggnings förfrågan. 

## <a name="office-services"></a>Office-tjänster

Office Online-tjänsterna är tillgängliga via `office.de` före och under över gången. När användarnas post lådor är över till Office 365-tjänsterna ska användarna börja använda URL: er för Office 365-tjänster. När efterföljande arbets belastningar migreras till Office 365-tjänster börjar deras gränssnitt från office.com-portalen att fungera.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- Backend Exchange Online Protection (EOP)-funktioner kopieras till nytt Tyskland.
- Office 365 säkerhets-och efterlevnadsprinciper-användare måste gå över till att använda globala URL-adresser, `https://protection.office.com` som en del av migreringen.

## <a name="skype-for-business-online"></a>Skype för företag online

Befintliga kunder i Skype för företag – online över gång till Microsoft Teams. Mer information finns i [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) .

## <a name="office-365-video"></a>Office 365 Video

Office 365 Video dras tillbaka den 1 mars 2021 och Office 365-Video stöds inte när migrering av SharePoint Online till de nya tyska Data Center-regionerna är klar. Innehåll från Office 365-videon migreras som en del av migrering av SharePoint Online. Men det går inte 365 att spela upp videor i Office 365 Video-gränssnittet efter SharePoint-migreringen. Läs mer om tids linje för migrering på [Office 365 Video över gång till Microsoft Stream (klassisk)-Översikt](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).

## <a name="next-step"></a>Nästa steg

[Förstå åtgärder och konsekvenser för migreringsåtgärder](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska Data Center-regionerna](ms-cloud-germany-transition.md)
- [Hjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du för migrering](ms-cloud-germany-migration-opt-in.md)

Flytta genom över gången:

- [Åtgärder och konsekvenser för migreringen](ms-cloud-germany-transition-phases.md)
- [Övrig för hands arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information om [tjänster](ms-cloud-germany-transition-add-general.md), [enheter](ms-cloud-germany-transition-add-devices.md), [erfarenheter](ms-cloud-germany-transition-add-experience.md)och [AD FS](ms-cloud-germany-transition-add-adfs.md).

Molnappar:

- [Information om programmet för Dynamics 365 migration](https://aka.ms/d365ceoptin)
- [Information om datamigreringshanteraren för Power BI](https://aka.ms/pbioptin)
- [Komma igång med din uppgradering av Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
