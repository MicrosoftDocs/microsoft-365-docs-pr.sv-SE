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
description: Läs mer om Microsoft Defender Office 365 för filer i SharePoint Online, OneDrive för företag och Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 67bd2a0952ac630888b07eaf05d365736a0472ea
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028841"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Säkra bilagor för SharePoint, OneDrive och Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Valv Bifogade filer för SharePoint, OneDrive och Microsoft Teams i [Microsoft Defender för Office 365](whats-new-in-defender-for-office-365.md) ger ytterligare ett skyddslager för filer som redan har genomsökts vid uppladdningen av den vanliga motor för virus i [Microsoft 365.](virus-detection-in-spo.md) Valv Bifogade filer SharePoint, OneDrive filer och Microsoft Teams hjälper till att identifiera och blockera befintliga filer som identifieras som skadliga på gruppwebbplatser och dokumentbibliotek.

Valv Bifogade filer SharePoint, OneDrive och Microsoft Teams är inte aktiverade som standard. Om du vill aktivera den går [du till Aktivera Valv för SharePoint, OneDrive och Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Hur Valv bifogade filer SharePoint, OneDrive och Microsoft Teams fungerar

När Valv bifogade filer för SharePoint, OneDrive och Microsoft Teams är aktiverat och identifierar en fil som skadlig är filen låst med direkt integrering med filbutikerna. Följande bild visar ett exempel på en skadlig fil som upptäckts i ett bibliotek.

![Filer i OneDrive för företag där en identifierades som skadlig](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Även om den blockerade filen fortfarande finns med i dokumentbiblioteket och i webb-, mobil- eller datorprogram kan andra inte öppna, kopiera, flytta eller dela filen. Men de kan ta bort den blockerade filen.

Här är ett exempel på hur en blockerad fil ser ut på en mobil enhet:

![Ta bort en blockerad fil från OneDrive för företag från OneDrive-mobilappen](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Som standard kan personer ladda ned en blockerad fil. Så här ser nedladdningen av en blockerad fil ut på en mobil enhet:

![En blockerad fil hämtas i OneDrive för företag](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Onlineadministratörer kan hindra användare från att ladda ned skadliga filer. Instruktioner finns i Använda [SharePoint Online PowerShell för att hindra användare från att hämta skadliga filer.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)

Mer information om användarupplevelsen när en fil har identifierats som skadlig finns i Vad kan jag göra när en skadlig fil hittas i [SharePoint Online, OneDrive eller Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Visa information om skadliga filer som upptäckts Valv bifogade filer för SharePoint, OneDrive och Microsoft Teams

Filer som identifieras som skadliga av Valv Bifogade filer för SharePoint, OneDrive och Microsoft Teams visas i rapporter för [Microsoft Defender för Office 365](view-reports-for-mdo.md) och i [Utforskaren (och](threat-explorer.md)identifieringar i realtid).

Efter maj 2018, när en fil identifieras som skadlig av Valv Bifogade filer för SharePoint, OneDrive och Microsoft Teams, finns filen även i karantän. Mer information finns i [Hantera filer i karantän i Defender för Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).


## <a name="keep-these-points-in-mind"></a>Tänk på följande punkter

- Defender för Office 365 genomsöker inte alla filer i SharePoint Online, OneDrive för företag eller Microsoft Teams. Detta är avsiktligt. Filer genomsöks asynkront. I processen används delning och gästaktivitetshändelser tillsammans med smart heuristics och hotsignaler för att identifiera skadliga filer.

- Kontrollera att dina SharePoint är konfigurerade för att använda [det moderna använda-upplevelsen.](/sharepoint/guide-to-sharepoint-modern-experience) Defender Office 365 skydd gäller oavsett om det moderna eller den klassiska vyn används. Men visuella indikatorerna för att en fil blockeras är endast tillgängliga i det moderna användande programmet.

- Valv Bifogade filer i SharePoint, OneDrive och Microsoft Teams är en del av organisationens övergripande strategi för skydd mot hot, som omfattar skydd mot skräppost och skadlig programvara i Exchange Online Protection (EOP) samt Valv-länkar och Valv-bilagor i Microsoft Defender för Office 365. Mer information finns i [Skydda mot hot i Office 365](protect-against-threats.md).
