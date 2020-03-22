---
title: Översikt över Office 365-grupper för administratörer
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
description: Läs mer om Office 365-grupper.
ms.openlocfilehash: 2257af16106e47b490beebd6d48e566bb3c07ca6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894497"
---
# <a name="overview-of-office-365-groups-for-administrators"></a>Översikt över Office 365-grupper för administratörer

Office 365-grupper är den grundläggande medlemskapstjänsten som driver allt lagarbete i Microsoft 365. Med Office 365-grupper kan du ge en grupp personer åtkomst till en samling samarbetsresurser som dessa personer kan dela. Dessa resurser omfattar:

- En delad Outlook-inkorg
- En delad kalender
- Ett SharePoint-dokumentbibliotek
- En planerare
- Power BI
- Yammer (om gruppen skapades från Yammer)
- Ett team (om gruppen skapades från Teams)
- Översikt (om du har Project for the web)

Med en Office 365-grupp behöver du inte manuellt tilldela behörigheter till var och en av dessa resurser, eftersom om du lägger till personer i gruppen automatiskt får de behörigheter de behöver i de verktyg som gruppen tillhandahåller.

Alla Office 365-användare kan skapa en grupp om du inte [begränsar gruppskapandet till en viss uppsättning personer.](manage-creation-of-groups.md) Observera att om du begränsar gruppskapandet kan användare som inte kan skapa grupper inte skapa SharePoint-webbplatser, planerare eller team. Dessa tjänster kräver att de personer som skapar dem kan skapa en grupp. Användare kan fortfarande delta i gruppaktiviteter, till exempel skapa uppgifter i Planner eller använda Teams-chatt, förutsatt att de är medlemmar i gruppen.

Grupper har följande roller:

- **Ägare** - Gruppägare kan lägga till eller ta bort medlemmar och har unika behörigheter som möjligheten att ta bort konversationer från den delade inkorgen eller ändra olika inställningar om gruppen. Gruppägare kan byta namn på gruppen, uppdatera beskrivningen eller bilden med mera.
- **Medlemmar** - Medlemmar kan komma åt allt i gruppen, men kan inte ändra gruppinställningar. Som standard kan gruppmedlemmar bjuda in gäster att gå med i gruppen, men du kan [styra den inställningen](manage-guest-access-in-groups.md).
- **Gäster** - Gruppgäster är medlemmar som kommer från utanför organisationen.

Endast globala administratörer, användaradministratörer och gruppadministratörer kan skapa och hantera grupper i microsoft 365-administrationscentret. Du får inte vara delegerad administratör (till exempel en konsult som är administratör för någons räkning).

Som administratör kan du:

- [Ange vem som kan skapa grupper](manage-creation-of-groups.md)
- [Skapa en namngivningsprincip för grupper i organisationen](groups-naming-policy.md)
- [Välj vilken domän som ska användas när du skapar en grupp](choose-domain-to-create-groups.md)
- [Hantera gäståtkomst till grupper](manage-guest-access-in-groups.md)
- [Återställa en borttagen grupp](restore-deleted-group.md) (inom 30 dagar efter borttagning)

Om du föredrar ett mer automatiserat sätt att hantera livscykeln för dina Office 365-grupper kan du använda förfalloprinciper för att förfalla grupper med ett visst tidsintervall. Gruppens ägare kommer att få ett e-postmeddelande 30, 15 och 1 dag före gruppens utgång som gör att de enkelt kan förnya gruppen om det fortfarande behövs. Se: [Policy för förfallodatum för Office 365-gruppen](office-365-groups-expiration-policy.md).

Du kan administrera dina grupper från Microsoft 365-administrationscentret eller [med PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).

Om du har många användare, till exempel i ett stort företag eller företag, kan du ha många användare som skapar grupper för olika ändamål. Vi rekommenderar starkt att du granskar [Planera för styrning i Office 365-grupper](plan-for-groups-governance.md) för bästa praxis.

## <a name="group-limits"></a>Gruppgränser

Följande begränsningar gäller för Office 365-grupper:

|Maximal...|Value|
|:---------|:----|
|Ägare per grupp|100|
|Grupper som en användare kan skapa|250|
|Grupper som en administratör kan skapa|Upp till standardklientgränsen på 500 000 000 000 000 000 000|
|Antal medlemmar|Mer än 1 000, men bara 1 000 kan komma åt gruppkonversationerna samtidigt. <br>Användare kan märka förseningar när de öppnar kalendern och konversationer i mycket stora grupper i Outlook.|
|Antal grupper som en användare kan vara medlem i|1,000|
|Fillagring|1 Terabyte + 10 GB per prenumererad användare + eventuellt extra lagringsutrymme som köpts. Du kan köpa ett obegränsat antal ytterligare lagringsutrymme.|
|Storlek på grupppostlåda|50 GB|

Det maximala standardantalet Office 365-grupper som en Office 365-organisation kan ha är 500 000, men kan ökas med begäran. Mer information om begränsningar för Office 365-grupper finns i [Hjälp om Office 365-grupper – administratör](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx).

Det är mer effektivt att hantera dina Office 365-grupper när du har användbar information om gruppanvändning. Microsoft 365-administrationscentret har ett rapporteringsverktyg som kan du se saker som lagringsanvändning, hur många aktiva grupper du har och till och med hur användarna använder grupperna. Mer information finns [i: Office 365-rapporter i administrationscentret.](../activity-reports/office-365-groups.md)

## <a name="which-office-365-plans-include-groups"></a>Vilka Office 365-abonnemang innehåller grupper?

Alla Office 365-prenumerationer som har Exchange Online och SharePoint Online stöder grupper. Det inkluderar Business Essentials och Business Premium-abonnemangen samt Enterprise E1-, E3- och E5-planerna. Gruppen tar på licensiering av den person som skapar gruppen (även känd som "organisatör" av gruppen). Så länge arrangören har rätt licens för vilka funktioner du vill att gruppen ska ha, kommer den licensen att förmedla till gruppen.

> [!NOTE]
> Mer information om servicefamiljer och abonnemang för Office 365 finns i [Alternativ för Office 365-abonnemang](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Om du har en Exchange-plan kan du fortfarande hämta den delade inkorgen och delade kalenderfunktioner i grupper i Outlook, men du får inte dokumentbiblioteket, planeraren eller någon av de andra funktionerna.

Office 365-grupper fungerar med Azure Active Directory (AAD). Vilka grupper funktioner du får beror på vilken Azure Active Directory-prenumeration du har och vilka licenser som tilldelas gruppens organisatör.

> [!IMPORTANT]
> Om du har en Azure AD Premium-prenumeration för alla gruppfunktioner kan användare gå med i gruppen oavsett om de har tilldelats en AAD P1-licens eller inte. Licensieringen tillämpas inte.
> Med jämna mellanrum genererar vi användningsrapporter som talar om vilka användare som saknar en licens och behöver en som tilldelats dem för att vara kompatibel med licenskraven. Anta till exempel att en användare inte har en licens och att de läggs till i en grupp där namngivningsprincipen tillämpas. Rapporten flaggar för att de behöver en licens.

## <a name="related-articles"></a>Relaterade artiklar

[Läs om Office 365-grupper](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Uppgradera distributionslistor till Office 365-grupper](../manage/upgrade-distribution-lists.md)

[Manage Office 365 Groups with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[Begränsningar för SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
