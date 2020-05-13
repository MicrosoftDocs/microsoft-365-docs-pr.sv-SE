---
title: Rapportera skräppost, icke-skräppost och nätfiskemeddelanden till Microsoft
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
description: Administratörer kan lära sig mer om de olika sätten att rapportera bra och dåliga meddelanden och filer till Microsoft för analys.
ms.openlocfilehash: f77346b1f7551ade572c695e1c2d29e402c6c2a2
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206460"
---
# <a name="report-messages-and-files-to-microsoft"></a>Rapportera meddelanden och filer till Microsoft

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor har både användare och administratörer flera olika metoder för att rapportera e-postmeddelanden och filer till Microsoft.

|||
|---|---|
|**Metod**|**Beskrivning**|
|[Använd administratörsöverföring för att skicka misstänkt skräppost, phish, webbadresser och filer till Microsoft](admin-submission.md)|Den rekommenderade rapporteringsmetoden för administratörer i organisationer med Exchange Online-postlådor (inte tillgänglig i fristående EOP).|
|[Aktivera tillägget för att rapportera meddelande](enable-the-report-message-add-in.md)|Fungerar med Outlook, Outlook för Mac och Outlook på webben (tidigare kallat Outlook Web App) och är det rekommenderade tillägget. <br/><br/> Beroende på din prenumeration är meddelanden som användare rapporterade med tillägget tillgängliga i [portalen Admin Submissions,](admin-submission.md) [Automated investigation and response (AIR),](air-view-investigation-results.md)rapporten [Användarrapporterade meddelanden](view-email-security-reports.md#user-reported-messages-report)och Threat [Explorer](threat-explorer-views.md#email--submissions). <br/><br/> Du kan konfigurera rapporterade meddelanden som ska kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i [Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden i EOP](user-submission.md).|
|[Installera och använda tillägget Skräppostrapportering för Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Fungerar bara i Outlook.|
|[Rapportera skräppost och nätfiskemeddelanden i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Använd de inbyggda funktionerna i Outlook på webben för organisationer med Exchange Online-postlådor (inte tillgängligt i fristående EOP). <br/><br/> Meddelanden som användare rapporterar är tillgängliga i [portalen För administratörsbidrag](admin-submission.md). <br/><br/> Du kan konfigurera rapporterade meddelanden som ska kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i [Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden i Exchange online](user-submission.md).|
|[Skicka meddelanden manuellt till Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Skicka kopplade meddelanden manuellt till specifika Microsoft-e-postadresser för skräppost, inte skräppost och nätfiske.|
|[Använd regler för e-postflöde för att se vad dina användare rapporterar till Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Lär dig hur du skapar en regel för e-postflöde (kallas även en transportregel) som meddelar dig när användare rapporterar meddelanden till Microsoft för analys.|
|||
|[Skicka skadlig kod och icke-skadlig kod till Microsoft för analys](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Använd webbplatsen Microsoft Security Intelligence för att skicka bifogade filer och andra filer.|
|

Om skräppost- eller nätfiskemeddelandena sattes i karantän i stället för levererade kan användarna rapportera meddelandena till Microsoft från karantänportalen i Security & Compliance Center. Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).
