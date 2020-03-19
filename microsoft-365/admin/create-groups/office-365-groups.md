---
title: Översikt över Office 365-grupper för administratörer
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: v-teflor
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
ms.openlocfilehash: e7a65c41d4ecdbc91e163d9a84241ae549a2f9ec
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807836"
---
# <a name="overview-of-office-365-groups-for-administrators"></a>Översikt över Office 365-grupper för administratörer

Office 365 Groups är den grundläggande medlemstjänst som driver allt lagarbete i Microsoft 365. Med Office 365-grupper kan du ge en grupp personer åtkomst till en samling samarbetsresurser som dessa personer kan dela. Dessa resurser omfattar:

- En delad Outlook-inkorg
- En delad kalender
- Ett SharePoint-dokumentbibliotek
- En planerare
- Power BI
- Yammer (om gruppen skapades från Yammer)
- Ett team (om gruppen skapades från Teams)
- Färdplan (om du har Project för webben)

Med en Office 365-grupp behöver du inte tilldela behörigheter manuellt till var och en av dessa resurser, eftersom tillägg av medlemmar i gruppen automatiskt ger dem de behörigheter de behöver till de verktyg som gruppen tillhandahåller.

Alla Office 365-användare kan skapa en grupp om du inte [begränsar gruppskapandet till en viss uppsättning personer](manage-creation-of-groups.md). Observera att om du begränsar gruppskapande kan användare som inte kan skapa grupper inte skapa SharePoint-webbplatser, planerare eller team. Dessa tjänster måste kunna skapa en grupp med hjälp av användarkontexten. Användare kan fortfarande delta i gruppaktiviteter, till exempel skapa uppgifter i Planner eller svara på konversationer i Outlook, förutsatt att de är medlemmar i gruppen.

Grupper har följande roller:

- **Ägare** - Gruppägare kan lägga till eller ta bort medlemmar och ha unika behörigheter som möjligheten att ta bort konversationer från den delade inkorgen eller ändra olika inställningar om gruppen. Gruppägare kan byta namn på gruppen, uppdatera beskrivningen eller bilden med mera.
- **Medlemmar** - Medlemmar kan komma åt allt i gruppen, men kan inte ändra gruppinställningar.
- **Gäster** - Gruppgäster är medlemmar som är utanför organisationen. Som standard kan gruppmedlemmar bjuda in gäster att gå med i din grupp, men du kan [styra den inställningen](manage-guest-access-in-groups.md).

Endast globala administratörer och användarhanteringsadministratörer kan skapa och hantera grupper i administrationscentret. Du får inte vara delegerad administratör (till exempel en konsult som är administratör för någons räkning).

Som administratör kan du:

- [Ange vem som kan skapa grupper](manage-creation-of-groups.md)
- [Skapa en namngivningsprincip för grupper i organisationen](groups-naming-policy.md)
- [Välj vilken domän som ska användas när du skapar en grupp](choose-domain-to-create-groups.md)
- [Hantera gäståtkomst till grupper](manage-guest-access-in-groups.md)
- [Återställa en borttagen grupp](restore-deleted-group.md) (inom 30 dagar efter borttagning)

Om du föredrar ett mer automatiserat sätt att hantera livscykeln för dina Office 365-grupper kan du använda förfalloprinciper för att förfalla grupper med ett visst tidsintervall. Gruppens ägare får ett e-postmeddelande 30, 15 och 1 dag före gruppens utgångsdatum som gör att de enkelt kan förnya gruppen om det fortfarande behövs. Se: [Office 365-gruppförfallodatumprincip](office-365-groups-expiration-policy.md).

Du kan administrera dina grupper från administrationscentret för Microsoft 365 eller [genom att använda PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).

Om du har många användare, till exempel i ett stort företag eller företag, kan du ha många användare som skapar grupper för olika ändamål. Vi rekommenderar starkt att du granskar [Plan för styrning i Office 365-grupper](plan-for-groups-governance.md) för bästa praxis.

## <a name="group-limits"></a>Gruppgränser

Följande gränser gäller för Office 365-grupper:

|Maximal...|Value|
|:---------|:----|
|Ägare per grupp|100|
|Grupper som en användare kan skapa|250|
|Grupper som en administratör kan skapa|Upp till standardklientgränsen på 500 K|
|Antal medlemmar|Mer än 1 000, men bara 1 000 kan komma åt gruppkonversationerna samtidigt. <br>Användare kan märka fördröjningar när de kommer åt kalendern och konversationer i mycket stora grupper i Outlook.|
|Antal grupper som en användare kan vara medlem i|1,000|
|Fillagring|1 Terabyte + 10 GB per användare som prenumererar + ytterligare lagringsutrymme som köpts. Du kan köpa ett obegränsat antal ytterligare lagringsutrymme.|
|Storlek på grupppostlådan|50 GB|

Som standard är 500 000 det maximala antalet Grupper i Office 365 en Office 365-organisation kan ha, men det kan ökas på begäran. Mer information om begränsningar för Office 365-grupper finns i [Office 365 Groups – Hjälp för administratörer](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

Det är mer effektivt att hantera dina Office 365-grupper när du har användbar information om användning av grupper. Administrationscentret för Microsoft 365 har ett rapporteringsverktyg som gör att du kan se saker som lagring, hur många aktiva grupper du har och till och med hur användarna använder grupperna. Mer information finns [i: Office 365 Reports i administrationscentret.](../activity-reports/office-365-groups.md)

## <a name="which-office-365-plans-include-groups"></a>Vilka Office 365-abonnemang innehåller grupper?

Alla Office 365-prenumerationer som har Exchange Online och SharePoint Online stöder grupper. Det inkluderar Business Essentials- och Business Premium-abonnemangen samt Enterprise E1-, E3- och E5-abonnemangen. Koncernen tar på sig licensiering en person som skapar koncernen (även känd som "organisatör" av koncernen). Så länge arrangören har rätt licens för vilka funktioner du vill att koncernen ska ha, kommer den licensen att förmedla till koncernen.

> [!NOTE]
> Mer information om Office 365-servicefamiljer och abonnemang finns i [alternativ för Office 365-abonnemang](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Om du har ett Exchange-abonnemang kan du fortfarande hämta de delade inkorgen och de delade kalenderfunktionerna i grupper i Outlook, men du får inte dokumentbiblioteket, Planner eller någon av de andra funktionerna.

Office 365-grupper fungerar med Azure Active Directory (AAD). Vilka grupper funktioner du får beror på vilken Azure Active Directory-prenumeration du har och vilka licenser som tilldelas gruppens organisatör.

> [!IMPORTANT]
> För alla grupper funktioner, om du har en Azure AD Premium-prenumeration, användare kan gå med i gruppen oavsett om de har en AAD P1-licens tilldelas dem. Licensieringen tillämpas inte.
> Med jämna mellanrum genererar vi användningsrapporter som talar om för dig vilka användare som saknar en licens och behöver en som tilldelats dem för att vara kompatibel med licenskraven. Anta till exempel att en användare inte har någon licens och att de läggs till i en grupp där namngivningsprincipen tillämpas. Rapporten flaggar för att de behöver en licens.

## <a name="related-articles"></a>Relaterade artiklar

[Läs om Office 365-grupper](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Uppgradera distributionslistor till Office 365-grupper](../manage/upgrade-distribution-lists.md)

[Manage Office 365 Groups with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[Begränsningar för SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
