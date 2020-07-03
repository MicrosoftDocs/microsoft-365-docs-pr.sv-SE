---
title: Virusskydd i SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Lär dig mer om hur SharePoint Online identifierar virus i filer som användare laddar upp och hindrar användare från att hämta eller synkronisera filerna.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60d696769ea402e6e2d0e52a1f6633e7962b8329
ms.sourcegitcommit: f2275d2fbc17a8b5b5da723c7353d3f36c6fb2a7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45029614"
---
# <a name="virus-detection-in-sharepoint-online"></a>Virusskydd i SharePoint Online

Microsoft 365 kan skydda din miljö från skadlig kod genom att upptäcka virus i filer som användare laddar upp till SharePoint Online. Filer kan sökas efter virus när de har laddats upp. Om det visar sig att en fil är infekterad anges en egenskap så att användarna inte kan hämta eller synkronisera filen.

> [!IMPORTANT]
> Dessa antivirusfunktioner i SharePoint Online är ett sätt att innehålla virus. De är inte avsedda som en enda försvarspunkt mot skadlig kod för din miljö. Vi uppmuntrar alla kunder att bedöma och implementera skydd mot skadlig kod på olika lager och tillämpa bästa praxis för att skydda företagets infrastruktur. Mer information om strategier och metodtips finns i [Översikt över säkerhet](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Vad händer när en infekterad fil överförs till SharePoint Online?

Microsoft 365 använder en vanlig virusdetekteringsmotor. Motorn körs asynkront i SharePoint Online och söker igenom vissa filer när de har laddats upp. Heuristik används för att avgöra vilka filer som skannas. När en fil visar sig innehålla ett virus flaggas den så att den inte kan hämtas igen. I april 2018 tog vi bort gränsen på 25 MB för skannade filer.

Så här går det till:

1. En användare laddar upp en fil till SharePoint Online.

2. SharePoint Online avgör om filen uppfyller kriterierna för en genomsökning.

3. Virusdetekteringsmotorn söker igenom filen.

4. Om ett virus hittas anger virusmotorn en egenskap på filen som anger att den är infekterad.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Vad händer när en användare försöker hämta en infekterad fil med hjälp av webbläsaren?

Om en fil är infekterad kan användarna inte hämta filen från SharePoint Online med hjälp av webbläsaren.

Så här går det till:

1. En användare öppnar en webbläsare och försöker hämta en infekterad fil från SharePoint Online.

2. Användaren får en varning om att ett virus har upptäckts. Användaren ges möjlighet att ladda ner filen och försöka rengöra den med sitt eget antivirusprogram.

> [!NOTE]
> Du kan använda parametern *DisallowInfectedFileDownload* på cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) i SharePoint Online PowerShell för att förhindra att användare hämtar en infekterad fil, även i varningsfönstret mot virus.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Vad händer när OneDrive-synkroniseringsklienten försöker synkronisera en infekterad fil?

Oavsett om användarna synkroniserar filer med den nya OneDrive-synkroniseringsklienten (OneDrive.exe) eller den tidigare Synkroniseringsklienten för OneDrive för företag (Groove.exe), om en fil innehåller ett virus, hämtas den inte synkroniseringsklienten. Synkroniseringsklienten visar ett meddelande om att filen inte kan synkroniseras.

## <a name="more-information"></a>Mer information

Mer information om hur du [konfigurerar](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) SharePoint Online-antivirus finns i Skydda mot hot [och Aktivera ATP för SharePoint, OneDrive och Microsoft Teams.](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide)


