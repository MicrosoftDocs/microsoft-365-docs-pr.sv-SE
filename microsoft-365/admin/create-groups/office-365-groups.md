---
title: Översikt över Microsoft 365-grupper för administratörer
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Läs mer om Microsoft 365-grupper.
ms.openlocfilehash: b3bc0c30f4ac292da7af46678fc742854984db12
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925356"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Översikt över Microsoft 365-grupper för administratörer

Microsoft 365 Groups är den grundläggande medlemskapstjänsten som driver allt teamarbete i Microsoft 365. Med Microsoft 365-grupper kan du ge en grupp personer åtkomst till en samling delade resurser. Resurserna omfattar:

- En delad Outlook-inkorg
- En delad kalender
- Ett SharePoint-dokumentbibliotek
- En Planner
- En OneNote-anteckningsbok
- Power BI
- Yammer (om gruppen skapades från Yammer)
- Ett team (om gruppen skapades från Teams)
- Översikt (om du har Project för webben)

Med en Microsoft 365-grupp behöver du inte tilldela behörigheter för var och en av dessa resurser manuellt. När du lägger till personer i gruppen får de automatiskt de behörigheter de behöver.

Alla användare kan skapa en grupp om du inte [begränsar skapandet av grupper till en viss uppsättning personer.](manage-creation-of-groups.md) Om du begränsar skapandet av grupper kommer användare som inte kan skapa grupper inte att kunna skapa SharePoint-webbplatser, planerare eller team. De här tjänsterna kräver att personerna som skapar dem ska kunna skapa en grupp. Användare kan fortfarande delta i gruppaktiviteter, till exempel skapa uppgifter i Planner eller använda Teams-chatt, förutsatt att de är medlemmar i gruppen.

Grupper har följande roller:

- **Ägare** – gruppägare kan lägga till eller ta bort medlemmar och har unika behörigheter som möjligheten att ta bort konversationer från den delade inkorgen eller ändra olika inställningar för gruppen. Gruppägare kan byta namn på gruppen, uppdatera beskrivningen eller bilden med mera.
- **Medlemmar** – medlemmar kan komma åt allt i gruppen, men kan inte ändra gruppinställningar. Som standard kan gruppmedlemmar bjuda in gäster till gruppen, men du kan [styra den inställningen.](manage-guest-access-in-groups.md)
- **Gäster** – Grupp gäster är medlemmar som kommer utifrån din organisation.

Endast globala administratörer, användaradministratörer och gruppadministratörer kan skapa och hantera grupper i administrationscentret för Microsoft 365. Du får inte vara delegerad administratör (till exempel en konsult som är administratör för någons räkning).

Som administratör kan du:

- [Ange vem som kan skapa grupper](manage-creation-of-groups.md)
- [Skapa en namnprincip för grupper i organisationen](groups-naming-policy.md)
- [Välj vilken domän som ska användas när du skapar en grupp](choose-domain-to-create-groups.md)
- [Hantera gäståtkomst till grupper](manage-guest-access-in-groups.md)
- [Återställa en borttagen grupp](restore-deleted-group.md) (inom 30 dagar efter borttagningen)

Om du föredrar ett mer automatiserat sätt att hantera livscykeln för Microsoft 365-grupper kan du använda förfalloprinciper så att grupper upphör att gälla efter ett visst tidsintervall. Gruppens ägare får ett e-postmeddelande 30 dagar, 15 dagar och 1 dag innan gruppen upphör, så att de kan förnya gruppen om den fortfarande behövs. Mer information: [Förfalloprincip för Microsoft 365-grupper.](office-365-groups-expiration-policy.md)

Du kan administrera grupper från administrationscentret för Microsoft 365 eller [med hjälp av PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershel)

Om du har många användare, till exempel i ett stort företag eller företag, kanske du har många användare som skapar grupper för olika ändamål. Vi rekommenderar att du granskar [plan för styrning i Microsoft 365-grupper](plan-for-groups-governance.md) för bästa praxis.

## <a name="group-limits"></a>Gruppbegränsningar

Följande begränsningar gäller för Microsoft 365-grupper:

|Maximalt...|Value|
|:---------|:----|
|Ägare per grupp|100|
|Grupper som en användare kan skapa|250|
|Grupper som en administratör kan skapa|Upp till standardklientgränsen på 500 K|
|Antal medlemmar|Fler än 1 000, men bara 1 000 kan komma åt gruppkonversationer samtidigt. <br>Användarna kan märka fördröjningar när de ska använda kalendern och konversationer i stora grupper i Outlook.|
|Antal grupper en användare kan vara medlem i|7,000|
|Fillagring|1 TB + 10 GB per prenumerant + annat lagringsutrymme som köpts. Du kan köpa en obegränsad mängd extra lagringsutrymme.|
|Postlådestorlek för grupp|50 GB|

Det maximala antalet Microsoft 365-grupper en organisation kan ha som standard är 500 000. Om du vill gå utöver standardgränsen måste du kontakta Microsoft Support. Mer information om begränsningar för Microsoft 365-grupper finns i [Microsoft 365-grupper – hjälp för administratörer.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

Att hantera Microsoft 365-grupper är effektivare med åtgärdsbar information om gruppanvändning. Administrationscentret för Microsoft 365 har ett rapportverktyg som gör att du kan se lagringsanvändning, hur många aktiva grupper du har och hur användarna använder grupperna. Mer information finns [i Microsoft 365-rapporter i administrationscentret.](../activity-reports/office-365-groups.md)

## <a name="sensitivity-labels"></a>Känslighetsetiketter

Du kan skapa känslighetsetiketter som användarna i organisationen kan ange när de skapar en Microsoft 365-grupp. Med känslighetsetiketter kan du konfigurera: 

- Sekretess (offentlig eller privat)
- Åtkomst för externa användare
- Ohanterad enhetsåtkomst

Du kan till exempel skapa  en etikett med namnet Mycket konfidentiellt och ange att alla grupper som skapas med den här etiketten ska vara privata och inte tillåta externa användare. När användare i organisationen väljer den här etiketten när gruppen skapas sätts gruppen till privat och gruppmedlemmar kan inte lägga till externa användare i gruppen.

> [!IMPORTANT]
> Om du använder klassificeringsetiketter är de för närvarande inte längre tillgängliga för användare som skapar grupper när känslighetsetiketter har aktiverats. 

Mer information om hur du skapar, hanterar och använder känslighetsetiketter finns i Använda känslighetsetiketter för att skydda innehåll i [Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

## <a name="which-microsoft-365-plans-include-groups"></a>Vilka Microsoft 365-abonnemang inkluderar grupper?

En Microsoft 365-prenumeration med Exchange Online och SharePoint Online har stöd för grupper. Detta inkluderar Business Essentials- och Business Premium-abonnemangen och Enterprise E1-, E3- och E5-abonnemangen. Gruppen använder licensiering för den person som skapar gruppen (kallas även "organisatör" för gruppen). Så länge organisatören har rätt licens för de funktioner som du vill att gruppen ska ha, kommer den licensen att förmedla till gruppen.

> [!NOTE]
> Mer information om tjänstfamiljer och abonnemang för Microsoft 365 finns i alternativen för [Microsoft 365-abonnemang.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Om du har ett abonnemang med endast Exchange kan du ändå få funktioner för delad inkorg och delad kalender för grupper i Outlook, men du får inte dokumentbibliotek, Planner eller någon av de andra funktionerna.

Microsoft 365-grupper fungerar med Azure Active Directory. Vilka gruppfunktioner du får beror på vilken Azure Active Directory-prenumeration du har och vilka licenser som har tilldelats till organisatören av gruppen.

> [!IMPORTANT]
> För alla gruppfunktioner kan användare, om du har en Azure AD Premium-prenumeration, gå med i gruppen oavsett om de har tilldelats en AAD P1-licens eller inte. Licensiering tillämpas inte.
> Då och då genererar vi användningsrapporter som berättar vilka användare som saknar licens och behöver tilldelas en licens för att uppfylla licenskraven. Anta till exempel att en användare inte har någon licens och att de läggs till i en grupp där namnprincipen tillämpas. Rapporten flaggar för dig att de behöver en licens.

## <a name="related-articles"></a>Relaterade artiklar

[Läs mer om Microsoft 365-grupper](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Uppgradera distributionslistor till Microsoft 365-grupper](../manage/upgrade-distribution-lists.md)

[Hantera Microsoft 365-grupper med PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[Begränsningar för SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
