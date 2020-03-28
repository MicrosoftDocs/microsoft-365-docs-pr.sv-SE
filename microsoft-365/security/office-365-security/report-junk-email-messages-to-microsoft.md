---
title: Rapportera skräppost, icke-skräppost och nätfiskemeddelanden till Microsoft
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 'Microsofts tillägg för skräppostrapportering för Microsoft Office Outlook innehåller flera sätt att rapportera skräppostmeddelanden:'
ms.openlocfilehash: b7e7ed56f171ee3b74b36ed7c10c46286fb1e570
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033668"
---
# <a name="report-messages-and-files-to-microsoft"></a>Rapportera meddelanden och filer till Microsoft

Användare och administratörer i Office 365-organisationer med postlådor i Exchange Online, eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor för att skicka e-postmeddelanden har flera olika metoder för att rapportera meddelanden och filer till Microsoft.

|||
|---|---|
|**Metod**|**Beskrivning**|
|[Använd administratörsöverföring för att skicka misstänkt skräppost, phish, webbadresser och filer till Microsoft](admin-submission.md)|Detta är den rekommenderade rapporteringsmetoden för administratörer i organisationer med Exchange Online-postlådor (inte tillgängligt i fristående EOP).|
|[Aktivera tillägget Rapportmeddelande i Office 365](enable-the-report-message-add-in.md)|Fungerar med Outlook, Outlook för Mac och Outlook på webben. Detta är det rekommenderade tillägget. <br/><br/> Beroende på din licens är de rapporterade meddelandena tillgängliga i [resultat av automatisk undersökning och svar (AIR),](air-view-investigation-results.md)rapporten [Användarrapporterade meddelanden](view-email-security-reports.md#user-reported-messages-report) och Threat [Explorer](threat-explorer-views.md#email--submissions).|
|[Installera och använda tillägget Skräppostrapportering för Microsoft Outlook i Office 365](junk-email-reporting-add-in-for-microsoft-outlook.md)|Fungerar bara i Outlook.|
|[Rapportera skräppost och nätfiskemeddelanden i Outlook på webben i Office 365](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Använd de inbyggda funktionerna i Outlook på webben för organisationer med Exchange Online-postlådor (inte tillgängligt i fristående EOP).|
|[Skicka skadlig kod och icke-skadlig kod till Microsoft för analys](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Använd webbplatsen Microsoft Security Intelligence för att skicka bifogade filer och andra filer.|
|

Om skräppost- eller nätfiskemeddelandena sattes i karantän i stället för levererade kan användarna rapportera meddelandena till Microsoft från karantänportalen i Office 365 Security & Compliance Center. Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Office 365](find-and-release-quarantined-messages-as-a-user.md).