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
description: Lär dig mer om hur SharePoint Online identifierar virus i filer som användare laddar upp och förhindrar att användare laddar ned och synkroniserar filerna.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8c65db566f165939d72429bcd61b7d0a880814e0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196517"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Virus identifiering i SharePoint Online, OneDrive och Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Microsoft 365 skyddar din miljö mot skadlig program vara genom att upptäcka virus i filer som användare laddar upp till SharePoint Online, OneDrive och Microsoft Teams. Filer kan genomsökas efter virus när de har laddats upp. Om en fil är infekterad anges en egenskap så att användare inte kan ladda ned eller synkronisera filen.

> [!IMPORTANT]
> Dessa Antivirus funktioner i SharePoint Online är ett sätt att innehålla virus. De är inte avsedda som en enda försvars punkt mot skadlig program vara för din miljö. Vi uppmuntrar alla kunder att utvärdera och implementera skydd mot skadlig program vara på olika lager och tillämpa metod tips för att skydda företagets infrastruktur. Mer information om strategier och metod tips finns i [säkerhets översikt](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Vad händer när en angripen fil laddas upp till SharePoint Online?

Microsoft 365 använder en vanlig Antivirus funktion. Motorn körs asynkront i SharePoint Online och vissa filer genomsöks efter att de har laddats upp. Heuristik används för att avgöra vilka filer som genomsöks. När en fil hittas som innehåller ett virus flaggas den så att den inte kan hämtas igen. I april 2018 tog vi bort 25 MB-gränsen för inlästa filer.

Så här gör du:

1. En användare laddar upp en fil till SharePoint Online.

2. SharePoint Online bestämmer om filen uppfyller villkoren för en sökning.

3. Antivirus verktyget söker igenom filen.

4. Om ett virus hittas anger Antivirus motorn en egenskap för filen som anger att den är smittad.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Vad händer när en användare försöker ladda ned en infekterad fil med webbläsaren?

Om en fil är infekterad kan användare inte ladda ned filen från SharePoint Online med hjälp av webbläsaren.

Så här gör du:

1. En användare öppnar en webbläsare och försöker ladda ned en angripen fil från SharePoint Online.

2. Användaren får ett varnings meddelande om att ett virus har hittats. Användaren kan välja att ladda ner filen och försöka rensa den med hjälp av sitt eget antivirus program.

> [!NOTE]
>
> Du kan använda parametern *DisallowInfectedFileDownload* i cmdleten [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) i SharePoint Online PowerShell för att förhindra att användare laddar ned en angripen fil, även i fönstret antivirus varning.
>
> Tänk på att när du aktiverar *DisallowInfectedFileDownload* -parametern är det också bra att komma åt de identifierade/blockerade filerna helt och hållet för användare och administratörer.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Vad händer när en OneDrive-synkroniseringsklient försöker synkronisera en infekterad fil?

Om användarna synkroniserar filer med den nya synkroniseringsklienten för OneDrive (OneDrive.exe) eller den föregående synkroniseringsklienten för OneDrive för företag (Groove.exe) om en fil innehåller ett virus laddas inte synkroniseringsklienten. Synkroniseringsklienten visar ett meddelande om att filen inte kan synkroniseras.

## <a name="extended-capabilities-with-office-365-atp"></a>Utökade funktioner med Office 365 ATP

Kunder som har aktiverat Office 365 ATP för SharePoint, OneDrive och Microsoft Teams [aktiverar ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) för att använda säkerhets & Compliance Center för att hantera filer i karantänen för av-och ATP-identifieringar. [Endast ATP: Använd säkerhets & Compliance Center för att hantera filer i karantän](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="more-information"></a>Mer information

Se [skydda mot hot](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) och [Aktivera ATP för SharePoint, OneDrive och Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) om du vill ha mer information om hur du konfigurerar SharePoint Online Antivirus.


