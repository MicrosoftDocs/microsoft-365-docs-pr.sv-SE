---
title: ATP för SharePoint, OneDrive och Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Lär dig mer om Office 365 Avancerat skydd för filer i SharePoint Online, OneDrive för företag och Microsoft Teams.
ms.openlocfilehash: 194b8e45e573ae4c4cd1f3428a1f80c48e1d80c8
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326871"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP för SharePoint, OneDrive och Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

ATP för SharePoint-, OneDrive-och Microsoft Teams i [Office 365 Avancerat skydd (ATP)](office-365-atp.md) tillhandahåller ytterligare ett skydds lager för filer som redan har skannats vid uppladdning av den [vanliga antivirus motorn i Microsoft 365](virus-detection-in-spo.md). ATP för SharePoint, OneDrive och Microsoft Teams hjälper till att upptäcka och blockera befintliga filer som identifieras som skadligt för grupp webbplatser och dokument bibliotek.

ATP för SharePoint, OneDrive och Microsoft Teams är inte aktiverat som standard. Information om hur du aktiverar funktionen finns i [Aktivera ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Så fungerar ATP för SharePoint, OneDrive och Microsoft Teams

När ATP för SharePoint, OneDrive och Microsoft Teams är aktiverat och identifierar en fil som skadligt är filen låst med hjälp av direkt integrering med fil arkiven. Följande bild visar ett exempel på en skadlig fil som identifieras i ett bibliotek.

![Filer i OneDrive för företag med en identifierad som skadlig](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Även om den blockerade filen fortfarande visas i dokument biblioteket och i webb-, mobil-eller Skriv bords program kan de inte öppna, kopiera, flytta eller dela filen. Men de kan ta bort den blockerade filen.

Här är ett exempel på hur en blockerad fil ser ut på en mobil enhet:

![Ta bort en blockerad fil från OneDrive för företag från OneDrive-mobilappen](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Som standard kan folk Ladda ned en blockerad fil. Så här laddar du ned en blockerad fil på en mobil enhet:

![Ladda ned en blockerad fil i OneDrive för företag](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online-administratörer kan förhindra att personer laddar ned skadliga filer. Anvisningar finns i [använda SharePoint Online PowerShell för att förhindra att användare laddar ned skadliga filer](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

Om du vill veta mer om användar upplevelsen när en fil har identifierats som skadlig, se [vad du kan göra när en skadlig fil finns i SharePoint Online, OneDrive eller Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Visa information om skadliga filer som identifieras av ATP för SharePoint, OneDrive och Microsoft Teams

Filer som identifieras som skadligt för ATP visas i [rapporter för Office 365 Avancerat skydd för hotet](view-reports-for-atp.md) och i [Utforskaren (och real tids identifieringar)](threat-explorer.md).

Från och med den 2018 maj kan filen också vara tillgänglig i karantän när en fil identifieras som skadlig för ATP. Mer information finns i [använda säkerhets & Compliance Center för att hantera filer i karantän](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="keep-these-points-in-mind"></a>Tänk på följande saker

- ATP kommer inte att söka igenom alla filer i SharePoint Online, OneDrive för företag eller Microsoft Teams. Detta är avsiktligt. Filer skannas asynkront. Processen använder delnings-och gäst aktiviteter tillsammans med smarta heuristik och hot signaler för att identifiera skadliga filer.

- Kontrol lera att dina SharePoint-webbplatser är konfigurerade för att använda den [moderna upplevelsen](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). ATP-skydd gäller om den moderna upplevelsen eller vyn Klassisk används; visuella indikatorer som en fil är blockerade är bara tillgängliga i den moderna upplevelsen.

- ATP för SharePoint, OneDrive och Microsoft Teams är en del av organisationens övergripande hot skydds strategi, som inkluderar skydd mot skräp post och skyddar mot skadlig program vara i Exchange Online Protection (EOP), samt säkra länkar och säkra bifogade filer i Office 365 ATP. Mer information finns i [skydda mot hot i Office 365](protect-against-threats.md).
