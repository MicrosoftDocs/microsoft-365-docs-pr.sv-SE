---
title: Rapportera skräppost, icke-skräppost och nätfiskemeddelanden till Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig mer om de olika sätten att rapportera bra och dåliga meddelanden och filer till Microsoft för analys.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d7534d5d88fe19fba39ac1ebef16c72cac25cae7
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625047"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="998d2-103">Rapportera meddelanden och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="998d2-103">Report messages and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="998d2-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="998d2-104">**Applies to**</span></span>
- [<span data-ttu-id="998d2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="998d2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="998d2-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="998d2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="998d2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="998d2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="998d2-108">I Microsoft 365 organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor har både användare och administratörer flera olika metoder för att rapportera e-postmeddelanden och filer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="998d2-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, both users and admins have several different methods for reporting email messages and files to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="998d2-109">Metod</span><span class="sxs-lookup"><span data-stu-id="998d2-109">Method</span></span>|<span data-ttu-id="998d2-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="998d2-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="998d2-111">Använd administrationsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="998d2-111">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="998d2-112">Den rekommenderade rapporteringsmetoden för administratörer i organisationer med Exchange Online (inte tillgängligt i fristående EOP).</span><span class="sxs-lookup"><span data-stu-id="998d2-112">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="998d2-113">Aktivera rapportmeddelandet eller tilläggen för nätfiske</span><span class="sxs-lookup"><span data-stu-id="998d2-113">Enable the Report Message or the Report Phishing add-ins</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="998d2-114">Fungerar med Outlook och Outlook på webben (kallades tidigare för Outlook Web App).</span><span class="sxs-lookup"><span data-stu-id="998d2-114">Works with Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <p> <span data-ttu-id="998d2-115">Beroende på din prenumeration finns meddelanden som användare rapporterat med tilläggen tillgängliga i portalen för administrationsinskick, AIR-resultat [(Automated investigation and response),](air-view-investigation-results.md)rapporten över användarrapporter och [Threat Explorer.](threat-explorer-views.md#email--submissions) [](admin-submission.md) [](view-email-security-reports.md#user-reported-messages-report)</span><span class="sxs-lookup"><span data-stu-id="998d2-115">Depending on your subscription, messages that users reported with the add-ins are available in [the Admin Submissions portal](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span> <p> <span data-ttu-id="998d2-116">Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="998d2-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="998d2-117">Mer information finns i Principer [för användarinskick.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="998d2-117">For more information, see [User submissions policies](user-submission.md).</span></span>
|[<span data-ttu-id="998d2-118">Rapportera falska positiva resultat och falska negativa tal till Outlook</span><span class="sxs-lookup"><span data-stu-id="998d2-118">Report false positives and false negatives to Outlook</span></span>](report-false-positives-and-false-negatives.md)|<span data-ttu-id="998d2-119">Skicka falska positiva resultat (bra e-postmeddelande som har blockerats eller skickats till skräppostmappen) och falska negativa meddelanden (oönskad e-post eller nätfingr som skickats till Inkorgen) till Exchange Online Protection (EOP) med hjälp av funktionen Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="998d2-119">Submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP) using the Report Message feature.</span></span>|
|[<span data-ttu-id="998d2-120">Skicka meddelanden till Microsoft manuellt för analys</span><span class="sxs-lookup"><span data-stu-id="998d2-120">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="998d2-121">Skicka bifogade meddelanden manuellt till specifika Microsoft-e-postadresser för skräppost, inte skräppost och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="998d2-121">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span>|
|[<span data-ttu-id="998d2-122">Använd e-postflödesregler för att se vad användarna rapporterar till Microsoft</span><span class="sxs-lookup"><span data-stu-id="998d2-122">Use mail flow rules to see what users are reporting to Microsoft</span></span>](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|<span data-ttu-id="998d2-123">Lär dig hur du skapar en e-postflödesregel (kallas även transportregel) som meddelar dig när användare rapporterar meddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="998d2-123">Learn how to create a mail flow rule (also known as a transport rule) that notifies you when users report messages to Microsoft for analysis.</span></span>|
|[<span data-ttu-id="998d2-124">Skicka skadlig programvara och icke-skadlig programvara till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="998d2-124">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="998d2-125">Använd webbplatsen Microsoft Säkerhetsinsikter skicka bifogade filer och andra filer.</span><span class="sxs-lookup"><span data-stu-id="998d2-125">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="998d2-126">Om skräppost- eller nätfiskemeddelanden har satts i karantän i stället för att levereras kan användare rapportera meddelandena till Microsoft från karantänportalen i säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="998d2-126">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Security & Compliance Center.</span></span> <span data-ttu-id="998d2-127">Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="998d2-127">For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

> [!NOTE]
> <span data-ttu-id="998d2-128">Data från inskickade data till Microsoft lagras Office 365 gränsen för efterlevnad i nordamerikas datacenter.</span><span class="sxs-lookup"><span data-stu-id="998d2-128">Data from submissions to Microsoft resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="998d2-129">Data granskas av analytikerna i teknikteamet för att hjälpa till att göra filtren mer effektiva.</span><span class="sxs-lookup"><span data-stu-id="998d2-129">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>
