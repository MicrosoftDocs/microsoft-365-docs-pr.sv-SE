---
title: Inbyggt virus skydd i SharePoint Online, OneDrive och Microsoft Teams
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
ms.openlocfilehash: 38d6111fe665e0af79cbd93f534b1058881ff76c
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327993"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Inbyggt virus skydd i SharePoint Online, OneDrive och Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

I Microsoft 365 används en vanlig antivirus motor för genomsökning av filer som användare laddar upp till SharePoint Online, OneDrive och Microsoft Teams. Detta skydd ingår i alla abonnemang som innehåller SharePoint Online, OneDrive och Microsoft Teams.

> [!IMPORTANT]
> De inbyggda Antivirus funktionerna är ett sätt att hjälpa dig att skapa virus. De är inte avsedda som en enda försvars punkt mot skadlig program vara för din miljö. Vi uppmuntrar alla kunder att undersöka och implementera skydd mot skadlig program vara på olika lager och tillämpa metod tips för att skydda sin företags infrastruktur. Mer information om strategier och metod tips finns i [säkerhets översikt](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Vad händer när en angripen fil laddas upp till SharePoint Online?

Microsoft 365-Antivirus motorn körs asynkront i SharePoint Online. **Alla filer skannas inte automatiskt vid uppladdning**. Heuristiken bestämmer vilka filer som ska genomsökas. När en fil hittas som innehåller ett virus flaggas filen så att den inte kan hämtas igen. I april 2018 tog vi bort 25 MB-gränsen för inlästa filer.

Så här gör du:

1. En användare laddar upp en fil till SharePoint Online.
2. SharePoint Online bestämmer om filen uppfyller villkoren för en sökning.
3. Antivirus verktyget söker igenom filen.
4. Om ett virus hittas anger Antivirus motorn en egenskap för filen som anger att den är smittad.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Vad händer när en användare försöker ladda ned en infekterad fil med webbläsaren?

Om en fil är infekterad kan användare inte ladda ned filen från SharePoint Online med hjälp av en webbläsare.

Så här gör du:

1. En användare öppnar en webbläsare och försöker ladda ned en angripen fil från SharePoint Online.
2. Användaren får ett varnings meddelande om att ett virus har hittats. Som standard ges användaren möjlighet att ladda ner filen och försöka rensa den med antivirus programmet på egen hand.

> [!NOTE]
>
> Administratörer kan använda parametern *DisallowInfectedFileDownload* i cmdleten [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) i SharePoint Online PowerShell för att förhindra att användare laddar ner infekterade filer även i varnings fönstret mot virus. Anvisningar finns i [använda SharePoint Online PowerShell för att förhindra att användare laddar ned skadliga filer](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).
>
> Så fort du aktiverar *DisallowInfectedFileDownload* -parametern blockeras åtkomst till de identifierade/blockerade filerna helt för användare och administratörer.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Vad händer när en OneDrive-synkroniseringsklient försöker synkronisera en infekterad fil?

För OneDrive-synkroniseringsklienten hämtas inte filer som innehåller virus. Synkroniseringsklienten visar ett meddelande om att filen inte kan synkroniseras.

## <a name="extended-capabilities-with-office-365-advanced-threat-protection"></a>Utökade funktioner med Office 365 Avancerat skydd

Microsoft 365-organisationer som har [Office 365 Avancerat skydd (ATP)](office-365-atp.md) ingår i deras abonnemang eller köps som ett tillägg kan aktivera ATP för SharePoint-, OneDrive-och Microsoft Teams för bättre rapportering och skydd. Mer information finns i [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md).

## <a name="more-information"></a>Mer information

Mer information om antivirus i SharePoint Online, OneDrive och Microsoft Teams finns i [skydda mot hot](protect-against-threats.md) och [Aktivera ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).
