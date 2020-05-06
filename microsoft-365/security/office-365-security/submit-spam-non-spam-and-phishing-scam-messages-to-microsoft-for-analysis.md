---
title: Skicka meddelanden manuellt till Microsoft för analys
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Du och dina användare kan skicka falska negativa och falska positiva skräppostmeddelanden till Microsoft för analys. '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7fc26e1cba976e68b8dcfee5ec8b4fe366b8c47
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035242"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="f8e17-103">Skicka meddelanden manuellt till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="f8e17-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="f8e17-104">Om du är administratör i en Microsoft 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inlämningar i Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="f8e17-104">If you're an admin in an Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f8e17-105">Mer information finns i [Använda administratörsöverföring för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="f8e17-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f8e17-106">Det kan vara frustrerande när användare i organisationen får skräppost eller nätfiskemeddelanden i inkorgen, eller om de inte får ett legitimt e-postmeddelande eftersom det är markerat som skräppost.</span><span class="sxs-lookup"><span data-stu-id="f8e17-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="f8e17-107">Vi finjusterar ständigt våra skräppostfilter för att vara mer exakta.</span><span class="sxs-lookup"><span data-stu-id="f8e17-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="f8e17-108">Du och dina användare kan hjälpa den här processen genom att skicka in falska positiva identifieringar (bra e-post markerad som dålig), falska negativ (felaktig e-post tillåten) och nätfiskemeddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="f8e17-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="f8e17-109">På grund av den stora mängden inlagor som vi får kanske vi inte kan svara på alla förfrågningar om analys.</span><span class="sxs-lookup"><span data-stu-id="f8e17-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="f8e17-110">Skicka falska negativ till Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8e17-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="f8e17-111">I stället för att använda följande procedurer för att rapportera falska negativ kan användare i Outlook och Outlook på webben (tidigare kallat Outlook Web App) använda tillägget Rapportmeddelande för Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="f8e17-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="f8e17-112">Information om hur du installerar och använder det här verktyget finns [i Aktivera tillägget Rapportmeddelande](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="f8e17-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="f8e17-113">Om du får ett meddelande som skickades genom skräppostfiltrering som borde ha identifierats som skräppost eller nätfiske kan du skicka meddelandet till microsofts team för skräppostanalys och Microsofts nätfiskeanalys efter behov.</span><span class="sxs-lookup"><span data-stu-id="f8e17-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="f8e17-114">Analytikerna granskar meddelandet och lägger till det i de serviceomfattande filtren om det uppfyller klassificeringskriterierna.</span><span class="sxs-lookup"><span data-stu-id="f8e17-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="f8e17-115">Skapa ett nytt, tomt e-postmeddelande med någon av följande mottagare:</span><span class="sxs-lookup"><span data-stu-id="f8e17-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="f8e17-116">**Skräp:**`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="f8e17-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="f8e17-117">**Nätfiske:**`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="f8e17-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="f8e17-118">Dra och släpp skräppost- eller nätfiskemeddelandet i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f8e17-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="f8e17-119">Detta sparar skräppost- eller nätfiskemeddelandet som en bifogad fil i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f8e17-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="f8e17-120">Kopiera och klistra inte in innehållet i meddelandet eller vidarebefordra meddelandet (vi behöver det ursprungliga meddelandet så att vi kan inspektera meddelanderubrikerna).</span><span class="sxs-lookup"><span data-stu-id="f8e17-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="f8e17-121">Du kan bifoga flera meddelanden i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f8e17-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="f8e17-122">Kontrollera att alla meddelanden är av samma typ: antingen meddelanden om nätfiske eller skräppost.</span><span class="sxs-lookup"><span data-stu-id="f8e17-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="f8e17-123">Lämna brödtexten i det nya meddelandet tom.</span><span class="sxs-lookup"><span data-stu-id="f8e17-123">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="f8e17-124">Använd antingen MSG-format (standardformatet Outlook) eller .eml (standardformatet Outlook på webben) för de bifogade meddelandena.</span><span class="sxs-lookup"><span data-stu-id="f8e17-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="f8e17-125">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="f8e17-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="f8e17-126">Administratörer har flera olika sätt att blockera specifika meddelanden som felidentifieras som skräppost.</span><span class="sxs-lookup"><span data-stu-id="f8e17-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="f8e17-127">Mer information finns [i Skapa blockerade avsändarelistor i Office 365](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f8e17-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="f8e17-128">Skicka falska positiva identifieringar till Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8e17-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="f8e17-129">I stället för att använda följande procedurer för att rapportera falska positiva identifieringar kan användare i Outlook och Outlook på webben använda tillägget Rapportmeddelande för Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="f8e17-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="f8e17-130">Information om hur du installerar och använder det här verktyget finns [i Aktivera tillägget Rapportmeddelande](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="f8e17-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="f8e17-131">Om ett meddelande har identifierats felaktigt som skräppost kan du skicka meddelandet till Microsoft Spam Analysis Team.</span><span class="sxs-lookup"><span data-stu-id="f8e17-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="f8e17-132">Analytikerna kommer att utvärdera meddelandet, och (beroende på resultaten av analysen) kan de serviceomfattande filtren justeras så att meddelandet går igenom.</span><span class="sxs-lookup"><span data-stu-id="f8e17-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="f8e17-133">Skapa ett nytt, tomt `not_junk@office365.microsoft.com` e-postmeddelande med som mottagare:</span><span class="sxs-lookup"><span data-stu-id="f8e17-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="f8e17-134">Dra och släpp det felidentifierade meddelandet i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f8e17-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="f8e17-135">Då sparas det felidentifierade meddelandet som en bifogad fil i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f8e17-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="f8e17-136">Kopiera och klistra inte in innehållet i meddelandet eller vidarebefordra meddelandet (vi behöver det ursprungliga meddelandet så att vi kan inspektera meddelanderubrikerna).</span><span class="sxs-lookup"><span data-stu-id="f8e17-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="f8e17-137">Du kan bifoga flera meddelanden i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f8e17-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="f8e17-138">Kontrollera att alla meddelanden är av samma typ: antingen nätfiskemeddelanden eller skräppostmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="f8e17-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span></li><li><span data-ttu-id="f8e17-139">Lämna brödtexten i det nya meddelandet tom.</span><span class="sxs-lookup"><span data-stu-id="f8e17-139">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="f8e17-140">Använd antingen MSG-format (standardformatet Outlook) eller .eml (standardformatet Outlook på webben) för de bifogade meddelandena.</span><span class="sxs-lookup"><span data-stu-id="f8e17-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="f8e17-141">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="f8e17-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="f8e17-142">Administratörer har flera olika sätt att tillåta specifika meddelanden att hoppa över skräppostfiltrering.</span><span class="sxs-lookup"><span data-stu-id="f8e17-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="f8e17-143">Mer information finns [i Skapa listor över betrodda avsändare i Office 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f8e17-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="f8e17-144">Skapa en regel för e-postflöde för att ta emot kopior av meddelanden som rapporteras till Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8e17-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="f8e17-145">Instruktioner finns i [Använda regler för e-postflöde för att se vad användarna rapporterar till Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f8e17-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
