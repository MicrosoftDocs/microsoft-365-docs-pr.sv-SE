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
description: Administratörer kan lära sig mer om olika sätt att rapportera bra och dåliga meddelanden till Microsoft.
ms.openlocfilehash: b5f0d24e7e7edf3119f49965be73a1386ebd219e
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921474"
---
# <a name="report-messages-and-files-to-microsoft"></a>Rapportera meddelanden och filer till Microsoft

Användare och administratörer i Microsoft 365-organisationer med postlådor i Exchange Online, eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor har flera olika metoder för att rapportera meddelanden och filer till Microsoft.

|||
|---|---|
|**Metod**|**Beskrivning**|
|[Använd administratörsöverföring för att skicka misstänkt skräppost, phish, webbadresser och filer till Microsoft](admin-submission.md)|Den rekommenderade rapporteringsmetoden för administratörer i organisationer med Exchange Online-postlådor (inte tillgänglig i fristående EOP).|
|[Aktivera tillägget Rapportmeddelande i Office 365](enable-the-report-message-add-in.md)|Fungerar med Outlook, Outlook för Mac och Outlook på webben (tidigare kallat Outlook Web App) och är det rekommenderade tillägget. <br/><br/> Beroende på din prenumeration är meddelanden som användare rapporterade med tillägget tillgängliga i [portalen Admin Submissions,](admin-submission.md) [Automated investigation and response (AIR),](air-view-investigation-results.md)rapporten [Användarrapporterade meddelanden](view-email-security-reports.md#user-reported-messages-report)och Threat [Explorer](threat-explorer-views.md#email--submissions). <br/><br/> Du kan konfigurera rapporterade meddelanden som ska kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i [Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden i Office 365](user-submission.md).|
|[Installera och använda tillägget Skräppostrapportering för Microsoft Outlook i Office 365](junk-email-reporting-add-in-for-microsoft-outlook.md)|Fungerar bara i Outlook.|
|[Rapportera skräppost och nätfiskemeddelanden i Outlook på webben i Office 365](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Använd de inbyggda funktionerna i Outlook på webben för organisationer med Exchange Online-postlådor (inte tillgängligt i fristående EOP). <br/><br/> Meddelanden som användare rapporterar är tillgängliga i [portalen För administratörsbidrag](admin-submission.md). <br/><br/> Du kan konfigurera rapporterade meddelanden som ska kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i [Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden i Office 365](user-submission.md).|
|[Skicka meddelanden manuellt till Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Skicka kopplade meddelanden manuellt till specifika Microsoft-e-postadresser för skräppost, inte skräppost och nätfiske. <br/><br/> Lär dig också hur du skapar en regel för e-postflöde (kallas även en transportregel) som meddelar dig när användare skickar meddelanden till dessa rapporterande e-postadresser.|
|[Skicka skadlig kod och icke-skadlig kod till Microsoft för analys](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Använd webbplatsen Microsoft Security Intelligence för att skicka bifogade filer och andra filer.|
|

Om skräppost- eller nätfiskemeddelandena sattes i karantän i stället för levererade kan användarna rapportera meddelandena till Microsoft från karantänportalen i Security & Compliance Center. Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).