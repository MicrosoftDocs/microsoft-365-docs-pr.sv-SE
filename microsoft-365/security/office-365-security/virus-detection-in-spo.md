---
title: Inbyggt virusskydd i SharePoint Online, OneDrive och Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Läs mer om hur SharePoint Online identifierar virus i filer som användare laddar upp och hindrar användare från att ladda ned eller synkronisera filerna.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0eafb9e5e2f0c9d86791fe83931276e420afcd9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286507"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Inbyggt virusskydd i SharePoint Online, OneDrive och Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)

Microsoft 365 använder en vanlig motor för virusidentifiering för att söka igenom filer som användarna laddar upp till SharePoint Online, OneDrive och Microsoft Teams. Det här skyddet ingår i alla prenumerationer som innehåller SharePoint Online, OneDrive och Microsoft Teams.

> [!IMPORTANT]
> De inbyggda antivirusfunktionerna är ett sätt att förhindra virus. De är inte avsedda som ett enda skydd mot skadlig programvara för din miljö. Vi rekommenderar alla kunder att undersöka och implementera skydd mot skadlig programvara på olika nivåer och tillämpa metodtips för att skydda företagsinfrastrukturen. Mer information om strategier och metodtips finns i [säkerhetsöversikten.](security-roadmap.md)

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Vad händer när en smittad fil laddas upp till SharePoint Online?

Microsoft 365-motor för virusidentifiering körs asynkront i SharePoint Online. **Alla filer genomsöks inte automatiskt vid uppladdningen.** Heuristics avgör vilka filer som ska genomsöks. När en fil innehåller virus flaggas filen så att den inte kan laddas ned igen. I april 2018 tog vi bort gränsen på 25 MB för skannade filer.

Det här händer:

1. En användare laddar upp en fil till SharePoint Online.
2. SharePoint Online avgör om filen uppfyller villkoren för en genomsökning.
3. Virusidentifieringsmotorn söker igenom filen.
4. Om ett virus påträffas anges en egenskap för filen som anger att den är smittad.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Vad händer när en användare försöker hämta en smittad fil med hjälp av webbläsaren?

Om en fil är smittad kan användare inte hämta filen från SharePoint Online med hjälp av en webbläsare.

Det här händer:

1. En användare öppnar en webbläsare och försöker hämta en smittad fil från SharePoint Online.
2. Användaren får en varning om att ett virus har upptäckts. Som standard har användaren möjlighet att ladda ned filen och försöka rensa den med antivirusprogrammet på sin egen enhet.

> [!NOTE]
>
> Administratörer kan använda parametern *DisallowInfectedFileDownload* på [Set-SPOTenant-cmdleten](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) i SharePoint Online PowerShell för att hindra användare från att hämta smittade filer, även i fönstret med virusvarning. Instruktioner finns i Använda [SharePoint Online PowerShell för att hindra användare från att hämta skadliga filer.](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)
>
> Så snart du aktiverar *parametern DisallowInfectedFileDownload* blockeras åtkomsten till de identifierade/blockerade filerna helt och hållet för användare och administratörer.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Vad händer när OneDrive-synkroniseringsklienten försöker synkronisera en smittad fil?

OneDrive-synkroniseringsklienter laddar inte ned filer som innehåller virus. Synkroniseringsklienten visar ett meddelande om att filen inte kan synkroniseras.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Utökade funktioner med Microsoft Defender för Office 365

Microsoft 365-organisationer där Microsoft Defender för [Office 365](office-365-atp.md) ingår i prenumerationen eller köps som ett tillägg kan aktivera Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams för bättre rapportering och skydd. Mer information finns i Säkra [bifogade filer för SharePoint, OneDrive och Microsoft Teams.](atp-for-spo-odb-and-teams.md)

## <a name="related-articles"></a>Relaterade artiklar

[Skydd mot skadlig programvara och utpressningstrojaner i Microsoft 365](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

Mer information om antivirus i SharePoint Online, OneDrive och [](protect-against-threats.md) Microsoft Teams finns i Skydda mot hot och Aktivera säkra bifogade filer för [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md)och Microsoft Teams.
