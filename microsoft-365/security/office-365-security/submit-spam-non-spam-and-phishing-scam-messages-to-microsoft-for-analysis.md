---
title: Skicka meddelanden till Microsoft manuellt för analys
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Administratörer och slutanvändare kan lära sig att e-postmeddelanden (bra e-postmeddelanden som markerats som dåliga eller dåliga e-postmeddelanden tillåtna) till Microsoft för analys.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d277df764ce2fb135f11c6320bc990e4d4142d6
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929773"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="885f4-103">Skicka meddelanden till Microsoft manuellt för analys</span><span class="sxs-lookup"><span data-stu-id="885f4-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="885f4-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="885f4-104">**Applies to**</span></span>
- [<span data-ttu-id="885f4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="885f4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="885f4-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="885f4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="885f4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="885f4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="885f4-108">Om du är administratör i en organisation med Exchange Online postlådor rekommenderar vi att du använder portalen för sändning i Microsoft 365 Defender-portalen.</span><span class="sxs-lookup"><span data-stu-id="885f4-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="885f4-109">Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="885f4-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="885f4-110">Det kan vara frustrerande när användare i organisationen tar emot skräppost eller nätfiskemeddelanden i Inkorgen, eller om de inte får ett legitimt e-postmeddelande eftersom det markeras som skräppost.</span><span class="sxs-lookup"><span data-stu-id="885f4-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="885f4-111">Vi finjusterar ständigt våra skräppostfilter så att de blir mer exakta.</span><span class="sxs-lookup"><span data-stu-id="885f4-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="885f4-112">Du och dina användare kan hjälpa till med detta genom att skicka falska positiva meddelanden (bra e-postmeddelande markerat som dåligt), falskt negativa (felaktig e-post tillåts) och nätfiskemeddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="885f4-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="885f4-113">På grund av den stora mängden inskickade meddelanden kan vi kanske inte besvara alla förfrågningar om analys.</span><span class="sxs-lookup"><span data-stu-id="885f4-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="885f4-114">Skicka falska negativa tal till Microsoft</span><span class="sxs-lookup"><span data-stu-id="885f4-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="885f4-115">I stället för att använda följande procedurer för att rapportera falska negativa tal kan användare i Outlook och Outlook på webben (tidigare kallat Outlook Web App) använda tilläggen Rapportmeddelande eller Rapportera nätfiske.</span><span class="sxs-lookup"><span data-stu-id="885f4-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="885f4-116">Mer information om hur du installerar [](enable-the-report-message-add-in.md) och använder dessa verktyg finns i Aktivera tillägget Rapportmeddelande och Aktivera tillägget [Rapportfiske.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="885f4-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="885f4-117">Om du får ett meddelande som har passerat skräppostfiltrering som borde ha identifierats som skräppost eller nätfiske kan du skicka meddelandet till Microsofts grupper för skräppostanalys och Microsoft-nätfiskeanalys.</span><span class="sxs-lookup"><span data-stu-id="885f4-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="885f4-118">Analytikerna granskar meddelandet och lägger till det i filtren för hela tjänsten om det uppfyller klassificeringskriterierna.</span><span class="sxs-lookup"><span data-stu-id="885f4-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="885f4-119">Skapa ett nytt, tomt e-postmeddelande med någon av följande mottagare:</span><span class="sxs-lookup"><span data-stu-id="885f4-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="885f4-120">**Skräppost:**`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="885f4-120">**Junk**: `junk@office365.microsoft.com`</span></span>
   - <span data-ttu-id="885f4-121">**Nätfiske:**`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="885f4-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="885f4-122">Dra och släpp skräppost- eller nätfiskemeddelandet i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="885f4-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="885f4-123">Då sparas skräppost- och nätfiskemeddelandet som en bifogad fil i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="885f4-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="885f4-124">Kopiera inte innehållet i meddelandet eller vidarebefordra det (vi behöver det ursprungliga meddelandet så att vi kan kontrollera meddelanderubrikerna).</span><span class="sxs-lookup"><span data-stu-id="885f4-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="885f4-125">Du kan bifoga flera meddelanden i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="885f4-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="885f4-126">Kontrollera att alla meddelanden har samma typ: antingen nätfiskemeddelanden eller skräppost.</span><span class="sxs-lookup"><span data-stu-id="885f4-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   > - <span data-ttu-id="885f4-127">Lämna brödtexten i det nya meddelandet tom.</span><span class="sxs-lookup"><span data-stu-id="885f4-127">Leave the body of the new message empty.</span></span>
   > - <span data-ttu-id="885f4-128">Använd antingen .msg-format (Outlook) eller .eml-format (Outlook på webben-format) för bifogade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="885f4-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="885f4-129">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="885f4-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="885f4-130">Administratörer kan blockera specifika meddelanden som felaktigt kan blockeras som skräppost på flera olika sätt.</span><span class="sxs-lookup"><span data-stu-id="885f4-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="885f4-131">Mer information finns i [Skapa spärrade avsändarlistor i EOP.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="885f4-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="885f4-132">Skicka falska positiva resultat till Microsoft</span><span class="sxs-lookup"><span data-stu-id="885f4-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="885f4-133">I stället för att använda följande procedurer för att rapportera falska positiva resultat kan användare i Outlook och Outlook på webben (tidigare kallat Outlook Web App) använda tilläggen Rapportmeddelande eller Rapportera nätfiske.</span><span class="sxs-lookup"><span data-stu-id="885f4-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="885f4-134">Mer information om hur du installerar [](enable-the-report-message-add-in.md) och använder dessa verktyg finns i Aktivera tillägget Rapportmeddelande och Aktivera tillägget [Rapportfiske.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="885f4-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="885f4-135">Om ett meddelande felaktigt identifierades som skräppost kan du skicka meddelandet till Microsofts team för skräppostanalys.</span><span class="sxs-lookup"><span data-stu-id="885f4-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="885f4-136">Analytikerna utvärderar meddelandet och (beroende på resultatet av analysen) kan filtren för hela tjänsten justeras så att meddelandet går att komma igenom.</span><span class="sxs-lookup"><span data-stu-id="885f4-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="885f4-137">Skapa ett nytt, tomt e-postmeddelande `not_junk@office365.microsoft.com` med som mottagare.</span><span class="sxs-lookup"><span data-stu-id="885f4-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient.</span></span>

2. <span data-ttu-id="885f4-138">Dra och släpp det felidentifierade meddelandet i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="885f4-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="885f4-139">Det här sparar det felidentifierade meddelandet som en bifogad fil i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="885f4-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="885f4-140">Kopiera inte innehållet i meddelandet eller vidarebefordra det (vi behöver det ursprungliga meddelandet så att vi kan kontrollera meddelanderubrikerna).</span><span class="sxs-lookup"><span data-stu-id="885f4-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="885f4-141">Du kan bifoga flera meddelanden i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="885f4-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="885f4-142">Kontrollera att alla meddelanden har samma typ: antingen nätfiskemeddelanden eller skräppost.</span><span class="sxs-lookup"><span data-stu-id="885f4-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   > - <span data-ttu-id="885f4-143">Lämna brödtexten i det nya meddelandet tom.</span><span class="sxs-lookup"><span data-stu-id="885f4-143">Leave the body of the new message empty.</span></span>
   > - <span data-ttu-id="885f4-144">Använd antingen .msg-format (Outlook) eller .eml-format (Outlook på webben-format) för bifogade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="885f4-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="885f4-145">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="885f4-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="885f4-146">Administratörer kan tillåta filtrering av skräppost på flera olika sätt.</span><span class="sxs-lookup"><span data-stu-id="885f4-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="885f4-147">Mer information finns i [Skapa listor över betrodda avsändare i EOP.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="885f4-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="885f4-148">Var lagras data från inskickade data till Microsoft?</span><span class="sxs-lookup"><span data-stu-id="885f4-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="885f4-149">Data finns i den Office 365 gränsen för efterlevnad i nordamerikas datacenter.</span><span class="sxs-lookup"><span data-stu-id="885f4-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="885f4-150">Data granskas av analytikerna i teknikteamet för att hjälpa till att göra filtren mer effektiva.</span><span class="sxs-lookup"><span data-stu-id="885f4-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="885f4-151">Skapa en e-postflödesregel för att ta emot kopior av meddelanden som rapporterats till Microsoft</span><span class="sxs-lookup"><span data-stu-id="885f4-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="885f4-152">Instruktioner finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="885f4-152">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
