---
title: Översikt över Microsoft 365-grupper för administratörer
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig mer om Microsoft 365-grupper.
ms.openlocfilehash: 711ab7e7818b266d7cbdbe076e30355d29bc3eeb
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307271"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Översikt över Microsoft 365-grupper för administratörer

Microsoft 365-grupper är den grundläggande medlems tjänst som driver alla samarbeten i Microsoft 365. Med Microsoft 365 Groups kan du ge en grupp personer åtkomst till en samling samarbets resurser för de personer som ska dela. Resurserna inkluderar:

- En delad Outlook-inkorg
- En delad kalender
- Ett SharePoint-dokumentbibliotek
- En Planner
- En OneNote-anteckningsbok
- Power BI
- Yammer (om gruppen skapades från Yammer)
- Ett team (om gruppen skapades från Teams)
- Översikt (om du har Project för webben)

Med en Microsoft 365-grupp behöver du inte tilldela behörigheter till var och en av dessa resurser manuellt, eftersom du lägger till personer i gruppen automatiskt får dem de behörigheter de behöver för de verktyg som gruppen erbjuder.

Alla användare kan skapa en grupp såvida du inte [begränsar grupp skapandet till en viss uppsättning personer](manage-creation-of-groups.md). Observera att om du begränsar skapandet av grupper kan användare som inte kan skapa grupper inte skapa SharePoint-webbplatser,-planerare eller team. Dessa tjänster kräver att användarna skapar dem för att kunna skapa en grupp. Användare kan fortfarande delta i grupp aktiviteter, till exempel skapa uppgifter i Planner eller använda Teams-chatt, förutsatt att de är medlemmar i gruppen.

Grupper har följande roller:

- **Ägare** -grupp ägare kan lägga till eller ta bort medlemmar och ha unika behörigheter, till exempel möjligheten att ta bort konversationer från den delade Inkorgen eller ändra olika inställningar för gruppen. Grupp ägare kan byta namn på gruppen, uppdatera beskrivningen eller bilden med mera.
- **Medlemmar** – medlemmar kan komma åt allt i gruppen, men kan inte ändra grupp inställningar. Som standard kan grupp medlemmar bjuda in gäster att gå med i gruppen, men du kan [styra den inställningen](manage-guest-access-in-groups.md).
- **Gäster** – grupp gäster är medlemmar som är utanför din organisation.

Endast globala administratörer, användar administratörer och grupp administratörer kan skapa och hantera grupper i administrations centret för Microsoft 365. Du får inte vara delegerad administratör (till exempel en konsult som är administratör för någons räkning).

Som administratör kan du:

- [Ange vem som kan skapa grupper](manage-creation-of-groups.md)
- [Skapa en namngivnings princip för grupper i din organisation](groups-naming-policy.md)
- [Välj vilken domän du vill använda när du skapar en grupp](choose-domain-to-create-groups.md)
- [Hantera gäståtkomst till grupper](manage-guest-access-in-groups.md)
- [Återställa en borttagen grupp](restore-deleted-group.md) (inom 30 dagar efter borttagningen)

Om du föredrar ett mer automatiserat sätt att hantera livs cykeln för dina Microsoft 365-grupper kan du använda förfallo principer för att gå ut grupper vid ett visst tidsintervall. Gruppens ägare kommer att få ett e-postmeddelande om 30, 15 och 1 dag innan gruppen upphör att gälla så att de enkelt kan förnya gruppen om det behövs. Se: [giltighets princip för Microsoft 365-gruppen](office-365-groups-expiration-policy.md).

Du kan administrera dina grupper från administrations centret för Microsoft 365 eller med [hjälp av PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershel).

Om du har många användare, till exempel i ett stort företag eller i ett företag, kan du ha flera användare som skapar grupper för olika ändamål. Vi rekommenderar starkt att du granskar [planen för styrelserna i Microsoft 365 Groups](plan-for-groups-governance.md) för bästa praxis.

## <a name="group-limits"></a>Grupp gränser

Följande begränsningar gäller för Microsoft 365-grupper:

|Maximalt...|Value|
|:---------|:----|
|Ägare per grupp|100|
|Grupper som en användare kan skapa|250|
|Grupper som en administratör kan skapa|Upp till standard klient organisations gräns på 500 000|
|Antal medlemmar|Mer än 1 000, men endast 1 000 kan komma åt gruppkonversationer samtidigt. <br>Användarna kan märka fördröjningar när de ska använda kalendern och konversationer i stora grupper i Outlook.|
|Antal grupper en användare kan vara medlem i|1 000|
|Fil lagring|1 terabyte + 10 GB per användare med abonnemang + eventuell ytterligare lagring. Du kan köpa ett obegränsat antal lagrings utrymme.|
|Storlek på gruppens post låda|50 GB|

Det maximala antalet Microsoft 365-grupper som en organisation kan ha är 500 000. För att gå utöver standard gränsen måste du kontakta Microsofts support. Mer information om begränsningar i Microsoft 365-grupper finns i [microsoft 365-grupper – hjälp för administratörer](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Att hantera dina Microsoft 365-grupper är effektivare när du har åtgärds bara information om gruppernas användning. Administrations centret för Microsoft 365 har ett rapport verktyg som gör att du kan se sådant som lagrings bruk, hur många aktiva grupper du har och till och med hur du använder grupperna. Mer information finns i [Microsoft 365-rapporter i administrations centret](../activity-reports/office-365-groups.md) .

## <a name="sensitivity-labels"></a>Känslighetsetiketter

Du kan skapa känslighets etiketter som användarna i organisationen kan ange när de skapar en Microsoft 365-grupp. Med känslighets etiketter kan du konfigurera: 

- Sekretess (offentlig eller privat)
- Åtkomst till externa användare
- Åtkomst för ohanterad enhet

Du kan till exempel skapa en etikett som heter *mycket konfidentiell* och ange att en grupp som skapats med den här etiketten ska vara privat och inte tillåta externa användare. När användare i organisationen väljer den här etiketten när grupper skapas blir gruppen privat och grupp medlemmar inte tillåten att lägga till externa användare i gruppen.

> [!IMPORTANT]
> Om du använder klassificerings etiketter är de inte längre tillgängliga för användare som skapar grupper när du har aktiverat känslighets etiketter. 

Information om hur du skapar, hanterar och använder känslighets etiketter finns i [använda känslighets etiketter för att skydda innehåll i Microsoft Teams, microsoft 365 Groups och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

## <a name="which-microsoft-365-plans-include-groups"></a>Vilka Microsoft 365-abonnemang innehåller grupper?

Alla Microsoft 365-abonnemang som har Exchange Online och SharePoint Online har stöd för grupper. Som innehåller abonnemangen Business Essentials och Business Premium, samt planerna för Enterprise, E1, E3 och E5. Gruppen använder licensieringen för den person som skapar gruppen (kallas även "organisatören" för gruppen). Så länge organisatören har rätt licens för de funktioner som du vill att gruppen ska få, förmedlar den licensen till gruppen.

> [!NOTE]
> Mer information om Microsoft 365 service familjer och-abonnemang finns i [alternativ för microsoft 365-abonnemang](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).

Om du har ett abonnemang med bara en Exchange-prenumeration kan du fortfarande få till gång till delade inkorg och delade kalender funktioner för grupper i Outlook, men du får inte dokument biblioteket, Planner eller någon av de andra funktionerna.

Microsoft 365-grupper fungerar med Azure Active Directory (AAD). Vilka grupp funktioner du får beror på vilken Azure Active Directory-prenumeration du har och vilka licenser som har tilldelats gruppen.

> [!IMPORTANT]
> Om du har ett Azure AD Premium-abonnemang för alla grupper kan användarna gå med i gruppen oavsett om de har en AAD-licens tilldelad till sig eller inte. Licensiering är inte tvingande.
> Med jämna mellanrum skapar vi användnings rapporter som visar vilka användare som saknar en licens och behöver en tilldelad till dem för att vara kompatibel med licens kraven. Anta till exempel att en användare inte har någon licens och att de läggs till i en grupp där namngivnings principen tillämpas. Rapporten flaggar dig för att de behöver en licens.

## <a name="related-articles"></a>Relaterade artiklar

[Lär dig mer om Microsoft 365-grupper](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Uppgradera distributions listor till Microsoft 365-grupper](../manage/upgrade-distribution-lists.md)

[Hantera Microsoft 365-grupper med PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[Begränsningar för SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
