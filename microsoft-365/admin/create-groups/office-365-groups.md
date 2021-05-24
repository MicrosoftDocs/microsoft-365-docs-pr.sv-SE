---
title: Översikt över Microsoft 365 grupper för administratörer
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
description: Med Microsoft 365 grupper kan du skapa samarbete i Microsoft 365 genom att ge en grupp personer åtkomst till en samling delade resurser.
ms.openlocfilehash: f940872a3e4ba2aeeb62247c2898d5a4c0dec85f
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635756"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Översikt över Microsoft 365 grupper för administratörer

Microsoft 365 Grupper är den grundläggande medlemskapstjänsten som driver allt teamarbete i hela Microsoft 365. Med Microsoft 365 grupper kan du ge en grupp personer åtkomst till en samling delade resurser. Resurserna omfattar:

- En delad Outlook inkorg
- En delad kalender
- Ett SharePoint för dokumentbibliotek
- En Planner
- En OneNote anteckningsbok
- Power BI
- Yammer (om gruppen skapades från Yammer)
- Ett team (om gruppen har skapats från Teams)
- Översikt (om du har Project för webben)
- Stream

Med en Microsoft 365 grupp behöver du inte tilldela behörigheter för var och en av dessa resurser manuellt. Om du lägger till personer i gruppen får de automatiskt de behörigheter de behöver.

Alla användare kan skapa en grupp om du inte [begränsar skapandet av grupper till en särskild uppsättning personer.](../../solutions/manage-creation-of-groups.md) Om du begränsar skapandet av grupper kan användare som inte kan skapa grupper inte skapa SharePoint, Planerare eller team. För de här tjänsterna krävs att personerna som skapar dem ska kunna skapa en grupp. Användare kan fortfarande delta i gruppaktiviteter, till exempel skapa uppgifter i Planner eller använda Teams, förutsatt att de är medlemmar i gruppen.

Grupper har följande roller:

- **Ägare** – Gruppägare kan lägga till eller ta bort medlemmar och har unika behörigheter som möjligheten att ta bort konversationer från den delade inkorgen eller ändra olika inställningar för gruppen. Gruppägare kan byta namn på gruppen, uppdatera beskrivningen eller bilden med mera.
- **Medlemmar** – Medlemmar kan komma åt allt i gruppen, men kan inte ändra gruppinställningar. Som standard kan gruppmedlemmar bjuda in gäster att gå med i gruppen, men du kan [styra den inställningen.](manage-guest-access-in-groups.md)
- **Gäster** – Gruppgäster är medlemmar som kommer utifrån organisationen.

Endast globala administratörer, användaradministratörer och gruppadministratörer kan skapa och hantera grupper Microsoft 365 administrationscentret. Du får inte vara delegerad administratör (till exempel en konsult som är administratör för någons räkning).

Som administratör kan du:

- [Ange vem som kan skapa grupper](../../solutions/manage-creation-of-groups.md)
- [Skapa en namnprincip för grupper i organisationen](../../solutions/groups-naming-policy.md)
- [Välj vilken domän du vill använda när du skapar en grupp](../../solutions/choose-domain-to-create-groups.md)
- [Hantera gäståtkomst till grupper](manage-guest-access-in-groups.md)
- [Återställa en borttagen grupp](restore-deleted-group.md) (inom 30 dagar från det att den togs bort)

Om du föredrar ett mer automatiserat sätt att hantera livscykeln för Microsoft 365-grupper kan du använda förfalloprinciper så att grupper upphör att gälla efter ett visst tidsintervall. Gruppens ägare får ett e-postmeddelande 30, 15 och 1 dag innan gruppen upphör, så att de kan förnya gruppen om den fortfarande behövs. Mer information: [Microsoft 365 förfalloprincip för grupper.](../../solutions/microsoft-365-groups-expiration-policy.md)

Du kan administrera grupperna via Microsoft 365 eller [med PowerShell.](../../enterprise/manage-microsoft-365-groups-with-powershell.md)

Om du har många användare, till exempel på ett stort företag eller företag, kanske du har många användare som skapar grupper för olika ändamål. Vi rekommenderar att du granskar [Planera för styrning i Microsoft 365 för](../../solutions/collaboration-governance-overview.md) metodtips.

## <a name="group-limits"></a>Gruppbegränsningar

Följande begränsningar gäller för Microsoft 365 grupper:

|Maximalt...|Värde|
|:---------|:----|
|Ägare per grupp|100|
|Grupper som en användare kan skapa|250|
|Grupper som en administratör kan skapa|Upp till standardklientgränsen på 500 K|
|Antal medlemmar|Fler än 1 000, men bara 1 000 kan komma åt gruppkonversationer samtidigt. <br>Användarna kan märka fördröjningar när de ska använda kalendern och konversationer i stora grupper i Outlook.|
|Antal grupper en användare kan vara medlem i|7,000|
|Fillagring|1 TB + 10 GB per prenumerant + annat lagringsutrymme som köps till. Du kan köpa en obegränsad mängd extra lagringsutrymme.|
|Postlådestorlek för grupp|50 GB|

Som standard kan maximalt Microsoft 365 grupper som en organisation kan ha är 500 000. Om du vill gå utöver standardgränsen måste du kontakta Microsoft Support. Mer information om begränsningar Microsoft 365 grupper finns i Artikeln [Microsoft 365 – hjälp för administratörer.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

Att hantera Microsoft 365 grupper är effektivare med åtgärdsbar information om gruppanvändning. I Microsoft 365 administrationscenter finns ett rapporteringsverktyg som gör att du kan se lagringsanvändningen, hur många aktiva grupper du har och hur användarna använder grupperna. Mer [information Microsoft 365: Microsoft 365 rapporter i](../activity-reports/office-365-groups.md) administrationscentret.

## <a name="sensitivity-labels"></a>Känslighetsetiketter

Du kan skapa känslighetsetiketter som användarna i organisationen kan ange när de skapar Microsoft 365 grupp. Med känslighetsetiketter kan du konfigurera: 

- Sekretess (offentlig eller privat)
- Åtkomst för externa användare
- Ohanterad enhetsåtkomst

Du kan till exempel skapa  etiketten Mycket konfidentiellt och ange att alla grupper som skapas med den här etiketten ska vara privata och inte tillåta externa användare. När användare i din organisation väljer den här etiketten när gruppen skapas sätts den till privat och gruppmedlemmar kommer inte att kunna lägga till externa användare i gruppen.

> [!IMPORTANT]
> Om du använder klassificeringsetiketter är de inte längre tillgängliga för användare som skapar grupper när känslighetsetiketter har aktiverats. 

Information om hur du skapar, hanterar och använder känslighetsetiketter finns i Använda känslighetsetiketter för att skydda innehåll i [Microsoft Teams, Microsoft 365 grupper och SharePoint webbplatser.](../../compliance/sensitivity-labels-teams-groups-sites.md)

## <a name="which-microsoft-365-plans-include-groups"></a>Vilka Microsoft 365 abonnemang inkluderar grupper?

Alla Microsoft 365-prenumerationer som har Exchange Online och SharePoint Online har stöd för grupper. Detta inkluderar Business Essentials- Premium Business-abonnemangen och Enterprise E1-, E3- och E5-abonnemangen. Gruppen tar på sig licensiering för den person som skapar gruppen (kallas även "organisatör" för gruppen). Så länge organisatören har rätt licens för de funktioner som du vill att gruppen ska ha, kommer licensen att förmedla till gruppen.

> [!NOTE]
> Mer information om Microsoft 365 tjänstfamiljer och abonnemang finns i Microsoft 365 [alternativ för abonnemang.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Om du har ett Exchange-abonnemang kan du ändå få funktioner för delad inkorg och delad kalender för grupper i Outlook men du får inte dokumentbiblioteket, Planner eller någon av de andra funktionerna.

Microsoft 365 grupper arbetar med Azure Active Directory. Vilka gruppfunktioner du får beror på vilken Azure Active Directory-prenumeration du har och vilka licenser som har tilldelats till organisatören av gruppen.

> [!IMPORTANT]
> För alla gruppfunktioner kan användare, om du har en Azure AD Premium-prenumeration, ansluta till gruppen oavsett om de har en AAD P1-licens tilldelad till sig eller inte. Licensiering tillämpas inte.
> Då och då genererar vi användningsrapporter som berättar vilka användare som saknar en licens och behöver tilldelas en licens för att uppfylla licenskraven. Anta till exempel att en användare inte har en licens och att de läggs till i en grupp där namnprincipen tillämpas. Rapporten flaggar för dig att de behöver en licens.

## <a name="related-content"></a>Relaterat innehåll

[Läs mer Microsoft 365 grupper](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (artikel)\
[Uppgradera distributionslistor till Microsoft 365 Grupper](../manage/upgrade-distribution-lists.md) (artikel)\
[Hantera Microsoft 365-grupper med PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (artikel)\
[SharePoint onlinebegränsningar](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) (artikel)\
[Ordna grupper och kanaler i Microsoft Stream](/stream/groups-channels-organization) (artikel)