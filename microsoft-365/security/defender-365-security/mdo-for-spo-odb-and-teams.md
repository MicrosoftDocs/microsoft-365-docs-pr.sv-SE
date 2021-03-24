---
title: Säkra bilagor för SharePoint, OneDrive och Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Läs mer om Microsoft Defender för Office 365 för filer i SharePoint Online, OneDrive för företag och Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80e30a52ef77dad32450bdfecc5010752b199b37
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071322"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Säkra bilagor för SharePoint, OneDrive och Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Säkra bifogade filer i SharePoint, OneDrive och Microsoft Teams i Microsoft Defender för [Office 365](whats-new-in-defender-for-office-365.md) ger ytterligare ett skyddslager för filer som redan har genomsökts vid uppladdningen av den vanliga motor för virusidentifiering i [Microsoft 365.](virus-detection-in-spo.md) Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams hjälper till att identifiera och blockera befintliga filer som identifieras som skadliga på gruppwebbplatser och dokumentbibliotek.

Säkra bifogade filer i SharePoint, OneDrive och Microsoft Teams är inte aktiverat som standard. Information om hur du aktiverar finns [i Aktivera säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Hur säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams fungerar

När Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams har aktiverats och identifierar en fil som skadlig låses filen med direkt integrering med filbutikerna. Följande bild visar ett exempel på en skadlig fil som upptäckts i ett bibliotek.

![Filer i OneDrive för företag med en som identifierats som skadliga](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Även om den blockerade filen fortfarande finns med i dokumentbiblioteket och i webb-, mobil- eller datorprogram kan andra inte öppna, kopiera, flytta eller dela filen. Men de kan ta bort den blockerade filen.

Här är ett exempel på hur en blockerad fil ser ut på en mobil enhet:

![Ta bort en blockerad fil från OneDrive för företag från OneDrive-mobilappen](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Som standard kan personer ladda ned en blockerad fil. Så här ser nedladdningen av en blockerad fil ut på en mobil enhet:

![Ladda ned en blockerad fil i OneDrive för företag](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online-administratörer kan hindra användare från att ladda ned skadliga filer. Instruktioner finns i Använda [SharePoint Online PowerShell för att hindra användare från att hämta skadliga filer.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)

Mer information om användarupplevelsen när en fil har identifierats som skadlig finns i Vad kan jag göra när en skadlig fil hittas i [SharePoint Online, OneDrive eller Microsoft Teams.](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Visa information om skadliga filer som upptäckts av säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams

Filer som identifieras som skadliga av Microsoft Defender för Office 365 visas i rapporter för Microsoft Defender för [Office 365](view-reports-for-mdo.md) och i [Utforskaren (och](threat-explorer.md)identifieringar i realtid).

Efter maj 2018, när en fil identifieras som skadlig av Microsoft Defender för Office 365, finns filen även i karantän. Mer information finns i Använda [säkerhets- & för att hantera filer i karantän.](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)

## <a name="keep-these-points-in-mind"></a>Tänk på följande punkter

- Defender för Office 365 söker inte igenom alla filer i SharePoint Online, OneDrive för företag eller Microsoft Teams. Detta är avsiktligt. Filer genomsöks asynkront. I processen används delning och gästaktivitetshändelser tillsammans med smart heuristics och hotsignaler för att identifiera skadliga filer.

- Kontrollera att dina SharePoint-webbplatser är konfigurerade för att använda [det moderna använda-upplevelsen.](/sharepoint/guide-to-sharepoint-modern-experience) Defender för Office 365-skydd gäller oavsett om det moderna eller den klassiska vyn används. Men visuella indikatorerna för att en fil blockeras är endast tillgängliga i det moderna användande programmet.

- Säkra bifogade filer i SharePoint, OneDrive och Microsoft Teams är en del av organisationens övergripande strategi för skydd mot hot, som omfattar skydd mot skräppost och skadlig programvara i Exchange Online Protection (EOP), samt säkra länkar och säkra bifogade filer i Microsoft Defender för Office 365. Mer information finns i [Skydda mot hot i Office 365.](protect-against-threats.md)