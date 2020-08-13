---
title: Rapportera skräp post, icke skräp post och nät fiske meddelanden till Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa om olika sätt att rapportera bra och dåliga meddelanden och filer till Microsoft för analys.
ms.openlocfilehash: 44254aa6e5c43e0eac1d63c153b1212b4f099840
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652831"
---
# <a name="report-messages-and-files-to-microsoft"></a>Rapportera meddelanden och filer till Microsoft

I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor finns det flera olika metoder för att rapportera e-postmeddelanden och filer till Microsoft.

****

|Metod|Beskrivning|
|---|---|
|[Använd administratörs sändning för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft](admin-submission.md)|Den rekommenderade rapporterings metoden för administratörer i organisationer med Exchange Online-postlådor (finns inte i fristående EOP).|
|[Aktivera tillägget för att rapportera meddelande](enable-the-report-message-add-in.md)|Fungerar med Outlook, Outlook för Mac och Outlook på webben (kallades tidigare Outlook Web App) och är det rekommenderade tillägget. <br/><br/> Beroende på ditt abonnemang är meddelanden som användare rapporterade med tillägget tillgängliga i [portalen för administration av](admin-submission.md)underställda- [och svars uppgifter, automatiserade undersökningar och reaktioner (Air)](air-view-investigation-results.md), rapporter om [meddelanden och meddelande](view-email-security-reports.md#user-reported-messages-report) [Utforskaren](threat-explorer-views.md#email--submissions). <br/><br/> Du kan konfigurera vilka meddelanden som ska kopieras eller dirigeras om till en post låda som du anger. Mer information finns i [Ange en post låda för användar överföringar av skräp post och nät fiske meddelanden i EOP](user-submission.md).|
|[Installera och använda tillägget skräp post rapportering för Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Fungerar bara i Outlook.|
|[Rapportera skräp post och nätfiske i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Använd de inbyggda funktionerna i Outlook på webben för organisationer med Exchange Online-postlådor (inte tillgängligt i fristående EOP). <br/><br/> Meddelanden som användare rapporterar är tillgängliga i [portalen för administrations överföringar](admin-submission.md). <br/><br/> Du kan konfigurera vilka meddelanden som ska kopieras eller dirigeras om till en post låda som du anger. Mer information finns i [Ange en post låda för användar överföringar av skräp post och nät fiske meddelanden i Exchange Online](user-submission.md).|
|[Skicka meddelanden till Microsoft för analys manuellt](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Manuellt skicka bifogade meddelanden till specifika Microsoft-e-postadresser för skräp post, inte skräp post och nätfiske.|
|[Använd regler för e-postflöde för att se vad dina användare rapporterar till Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Lär dig hur du skapar en regel för e-postflöde (kallas även transport regel) som meddelar dig när användare rapporterar meddelanden till Microsoft för analys.
|||
|[Skicka skadlig program vara och icke-malware till Microsoft för analys](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Använd webbplatsen Microsoft Security Intelligence för att skicka bilagor och andra filer.|
|

Om skräp post eller nätfiske-meddelanden sattes i stället för att levereras kan användarna rapportera meddelanden till Microsoft från karantäns portalen i säkerhets & Compliance Center. Mer information finns i [hitta och släppa meddelanden i karantän som en användare i Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).
