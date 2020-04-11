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
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="1034b-103">Rapportera meddelanden och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="1034b-103">Report messages and files to Microsoft</span></span>

<span data-ttu-id="1034b-104">Användare och administratörer i Office 365-organisationer med postlådor i Exchange Online, eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor har flera olika metoder för att rapportera meddelanden och filer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1034b-104">Users and admins in Office 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have several different methods for reporting messages and files to Microsoft.</span></span>

|||
|---|---|
|<span data-ttu-id="1034b-105">**Metod**</span><span class="sxs-lookup"><span data-stu-id="1034b-105">**Method**</span></span>|<span data-ttu-id="1034b-106">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="1034b-106">**Description**</span></span>|
|[<span data-ttu-id="1034b-107">Använd administratörsöverföring för att skicka misstänkt skräppost, phish, webbadresser och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="1034b-107">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="1034b-108">Den rekommenderade rapporteringsmetoden för administratörer i organisationer med Exchange Online-postlådor (inte tillgänglig i fristående EOP).</span><span class="sxs-lookup"><span data-stu-id="1034b-108">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="1034b-109">Aktivera tillägget Rapportmeddelande i Office 365</span><span class="sxs-lookup"><span data-stu-id="1034b-109">Enable the Report Message add-in in Office 365</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="1034b-110">Fungerar med Outlook, Outlook för Mac och Outlook på webben (tidigare kallat Outlook Web App) och är det rekommenderade tillägget.</span><span class="sxs-lookup"><span data-stu-id="1034b-110">Works with Outlook, Outlook for Mac, and Outlook on the web (formerly known as Outlook Web App), and is the recommended add-in.</span></span> <br/><br/> <span data-ttu-id="1034b-111">Beroende på din prenumeration är meddelanden som användare rapporterade med tillägget tillgängliga i [AIR-resultat (Automated investigation and response),](air-view-investigation-results.md)rapporten [Användarrapporterade meddelanden](view-email-security-reports.md#user-reported-messages-report)och [Threat Explorer](threat-explorer-views.md#email--submissions).</span><span class="sxs-lookup"><span data-stu-id="1034b-111">Depending on your subscription, messages that users reported with the add-in are available in [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span>|
|[<span data-ttu-id="1034b-112">Installera och använda tillägget Skräppostrapportering för Microsoft Outlook i Office 365</span><span class="sxs-lookup"><span data-stu-id="1034b-112">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>](junk-email-reporting-add-in-for-microsoft-outlook.md)|<span data-ttu-id="1034b-113">Fungerar bara i Outlook.</span><span class="sxs-lookup"><span data-stu-id="1034b-113">Only works in Outlook.</span></span>|
|[<span data-ttu-id="1034b-114">Rapportera skräppost och nätfiskemeddelanden i Outlook på webben i Office 365</span><span class="sxs-lookup"><span data-stu-id="1034b-114">Report junk and phishing email in Outlook on the web in Office 365</span></span>](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|<span data-ttu-id="1034b-115">Använd de inbyggda funktionerna i Outlook på webben för organisationer med Exchange Online-postlådor (inte tillgängligt i fristående EOP).</span><span class="sxs-lookup"><span data-stu-id="1034b-115">Use the built-in capabilities in Outlook on the web for organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="1034b-116">Skicka meddelanden manuellt till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="1034b-116">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="1034b-117">Skicka kopplade meddelanden manuellt till specifika Microsoft-e-postadresser för skräppost, inte skräppost och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="1034b-117">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span> <br/><br/> <span data-ttu-id="1034b-118">Lär dig också hur du skapar en regel för e-postflöde (kallas även en transportregel) som meddelar dig när användare skickar meddelanden till dessa rapporterande e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="1034b-118">Also learn how to create a mail flow rule (also known as a transport rule) that notifies you when users send messages to these reporting email addresses.</span></span>|
|[<span data-ttu-id="1034b-119">Skicka skadlig kod och icke-skadlig kod till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="1034b-119">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="1034b-120">Använd webbplatsen Microsoft Security Intelligence för att skicka bifogade filer och andra filer.</span><span class="sxs-lookup"><span data-stu-id="1034b-120">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="1034b-121">Om skräppost- eller nätfiskemeddelandena sattes i karantän i stället för levererade kan användarna rapportera meddelandena till Microsoft från karantänportalen i Office 365 Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="1034b-121">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="1034b-122">Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="1034b-122">For details, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>