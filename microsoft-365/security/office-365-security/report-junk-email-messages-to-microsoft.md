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
ms.openlocfilehash: 4578e3d29a89e94d23c04e4d80e45c79c18cfb85
ms.sourcegitcommit: 1d5db6e8411b45d0dd1c517339074c2840e33a63
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/10/2020
ms.locfileid: "43216881"
---
# <a name="report-messages-and-files-to-microsoft"></a>Rapportera meddelanden och filer till Microsoft

Användare och administratörer i Office 365-organisationer med postlådor i Exchange Online, eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor har flera olika metoder för att rapportera meddelanden och filer till Microsoft.

|||
|---|---|
|**Metod**|**Beskrivning**|
|[Använd administratörsöverföring för att skicka misstänkt skräppost, phish, webbadresser och filer till Microsoft](admin-submission.md)|Den rekommenderade rapporteringsmetoden för administratörer i organisationer med Exchange Online-postlådor (inte tillgänglig i fristående EOP).|
|[Aktivera tillägget Rapportmeddelande i Office 365](enable-the-report-message-add-in.md)|Fungerar med Outlook, Outlook för Mac och Outlook på webben (tidigare kallat Outlook Web App) och är det rekommenderade tillägget. <br/><br/> Beroende på din prenumeration är meddelanden som användare rapporterade med tillägget tillgängliga i [AIR-resultat (Automated investigation and response),](air-view-investigation-results.md)rapporten [Användarrapporterade meddelanden](view-email-security-reports.md#user-reported-messages-report)och [Threat Explorer](threat-explorer-views.md#email--submissions).|
|[Installera och använda tillägget Skräppostrapportering för Microsoft Outlook i Office 365](junk-email-reporting-add-in-for-microsoft-outlook.md)|Fungerar bara i Outlook.|
|[Rapportera skräppost och nätfiskemeddelanden i Outlook på webben i Office 365](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Använd de inbyggda funktionerna i Outlook på webben för organisationer med Exchange Online-postlådor (inte tillgängligt i fristående EOP).|
|[Skicka meddelanden manuellt till Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Skicka kopplade meddelanden manuellt till specifika Microsoft-e-postadresser för skräppost, inte skräppost och nätfiske. <br/><br/> Lär dig också hur du skapar en regel för e-postflöde (kallas även en transportregel) som meddelar dig när användare skickar meddelanden till dessa rapporterande e-postadresser.|
|[Skicka skadlig kod och icke-skadlig kod till Microsoft för analys](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Använd webbplatsen Microsoft Security Intelligence för att skicka bifogade filer och andra filer.|
|

Om skräppost- eller nätfiskemeddelandena sattes i karantän i stället för levererade kan användarna rapportera meddelandena till Microsoft från karantänportalen i Office 365 Security & Compliance Center. Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Office 365](find-and-release-quarantined-messages-as-a-user.md).