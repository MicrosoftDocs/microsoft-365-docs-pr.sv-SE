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
description: Läs mer om SharePoint online identifierar virus i filer som användare överför och hindrar användare från att ladda ned eller synkronisera filerna.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ab11d4c1e2a064ad0717e6619f72a38b0cbc831
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2021
ms.locfileid: "52932836"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Inbyggt virusskydd i SharePoint Online, OneDrive och Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)

Microsoft 365 vanliga motor för virusidentifiering för att söka igenom filer som användarna laddar upp till SharePoint Online, OneDrive och Microsoft Teams. Det här skyddet ingår i alla prenumerationer som inkluderar SharePoint Online, OneDrive och Microsoft Teams.

> [!IMPORTANT]
> De inbyggda virusfunktionerna är ett sätt att förhindra virus. De är inte avsedda som det enda skydd mot skadlig programvara i din miljö. Vi rekommenderar alla kunder att undersöka och implementera skydd mot skadlig programvara på olika nivåer och tillämpa de bästa metoderna för att skydda företagsinfrastrukturen. Mer information om strategier och metodtips finns i Översikt [över säkerhet.](security-roadmap.md)

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>Vad händer om en smittad fil laddas upp till SharePoint Online?

Datorn Microsoft 365 körs asynkront (oberoende av filuppladdningar) inom SharePoint Online. **Alla filer genomsöks inte automatiskt.** Heuristics bestäm vilka filer som ska skannas. När en fil påträffas som innehåller virus flaggas filen. I april 2018 tog vi bort gränsen på 25 MB för skannade filer.

Så här går det till:

1. En användare laddar upp en fil till SharePoint Online.
2. SharePoint Online, som en del av virussökprocesserna, avgör senare om filen uppfyller sökvillkoren.
3. Om filen uppfyller villkoren för en genomsökning söker virusidentifieringsmotorn igenom filen.
4. Om ett virus påträffas i den skannade filen anger virusmotorn en egenskap på filen som anger att den är smittad.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Vad händer när en användare försöker hämta en smittad fil med hjälp av webbläsaren?

Om en fil är smittad kan användare inte hämta filen från SharePoint Online med hjälp av en webbläsare.

Så här går det till:

1. En användare öppnar en webbläsare och försöker hämta en smittad fil från SharePoint Online.
2. Användaren får en varning om att ett virus har upptäckts. Som standard får användaren möjlighet att ladda ned filen och försöka rensa den med hjälp av antivirusprogrammet på sin egen enhet.

> [!NOTE]
>
> Administratörer kan använda parametern *DisallowInfectedFileDownload* i cmdleten [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) i SharePoint Online PowerShell för att hindra användare från att hämta smittade filer, även i fönstret med virusvarning. Instruktioner finns i Använda [SharePoint Online PowerShell för att hindra användare från att hämta skadliga filer.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)
>
> Så snart du aktiverar *parametern DisallowInfectedFileDownload* blockeras åtkomsten till de identifierade/blockerade filerna helt och hållet för användare och administratörer.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Vad händer när OneDrive försöker synkronisera en smittad fil?

När en skadlig fil överförs till OneDrive synkroniseras den med den lokala datorn innan den markeras som skadlig programvara. När det har markerats som skadlig programvara kan användaren inte längre öppna den synkroniserade filen från sin lokala dator.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Utökade funktioner med Microsoft Defender för Office 365

Microsoft 365 organisationer där [Microsoft Defender](defender-for-office-365.md) för Office 365 ingår i prenumerationen eller köper som ett tillägg kan du aktivera bifogade filer i Valv för SharePoint, OneDrive och Microsoft Teams för bättre rapportering och skydd. Mer information finns i Bifoga [Valv för SharePoint, OneDrive och Microsoft Teams](mdo-for-spo-odb-and-teams.md).

## <a name="related-articles"></a>Relaterade artiklar

[Skydd mot skadlig programvara och utpressningstrojaner i Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)

Mer information om antivirus i SharePoint Online, OneDrive och Microsoft Teams finns i Skydda [](protect-against-threats.md) mot hot och Aktivera [Valv-bilagor för SharePoint, OneDrive och Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)
