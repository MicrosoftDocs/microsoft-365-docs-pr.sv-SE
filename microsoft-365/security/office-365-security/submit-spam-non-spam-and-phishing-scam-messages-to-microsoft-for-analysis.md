---
title: Skicka meddelanden till Microsoft för analys manuellt
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
description: Administratörer och slutanvändare kan läsa mer om hur man skickar meddelanden (god e-post markerat som dålig eller dålig e-post) till Microsoft för analys.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e90382b39b0cebb70568a53ac5aaeb40ac935f92
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653599"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="67939-103">Skicka meddelanden till Microsoft för analys manuellt</span><span class="sxs-lookup"><span data-stu-id="67939-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="67939-104">Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen för säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="67939-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="67939-105">Mer information finns i [använda administratörs överföring för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="67939-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="67939-106">Det kan vara frustrerande när användare i din organisation får skräp post eller nätfiske-meddelanden i sin inkorg, eller om de inte får ett legitimt e-postmeddelande eftersom det är markerat som skräp post.</span><span class="sxs-lookup"><span data-stu-id="67939-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="67939-107">Vi kan alltid finjustera våra skräp post filter så att de blir mer korrekta.</span><span class="sxs-lookup"><span data-stu-id="67939-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="67939-108">Du och dina användare kan hjälpa till med den här processen genom att skicka falsk identifiering (god e-post markerat som dåligt), falskt negativ (dålig e-post) och nätfiske-meddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="67939-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="67939-109">På grund av de stora mängder som vi tar emot kanske vi inte kan besvara alla förfrågningar om analys.</span><span class="sxs-lookup"><span data-stu-id="67939-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="67939-110">Skicka falska negativa negativ till Microsoft</span><span class="sxs-lookup"><span data-stu-id="67939-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="67939-111">I stället för att använda följande procedurer för att rapportera falska negativa tal kan användare i Outlook och Outlook på webben (tidigare Outlook Web App) använda tillägget rapport meddelande för Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="67939-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="67939-112">Information om hur du installerar och använder det här verktyget finns i [Aktivera rapport meddelande tillägget](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="67939-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="67939-113">Om du får ett meddelande som skickas via skräp post filter som skulle ha identifierats som skräp post eller nätfiske kan du skicka meddelandet till Microsoft spam och Microsoft Phishing Analysis Teams.</span><span class="sxs-lookup"><span data-stu-id="67939-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="67939-114">Analyserna granskar meddelandet och lägger till det i tjänstens globala filter om det uppfyller klassificerings villkoren.</span><span class="sxs-lookup"><span data-stu-id="67939-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="67939-115">Skapa ett nytt, tomt e-postmeddelande med någon av följande mottagare:</span><span class="sxs-lookup"><span data-stu-id="67939-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="67939-116">**Skräp post**:`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="67939-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="67939-117">**Nätfiske**:`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="67939-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="67939-118">Dra och släpp skräp post eller nätfiske till det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="67939-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="67939-119">Detta sparar skräp post-eller nät fiske meddelandet som en bifogad fil i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="67939-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="67939-120">Kopiera och klistra inte in innehållet i meddelandet eller vidarebefordra det (vi behöver det ursprungliga meddelandet så att vi kan kontrol lera meddelande huvudena).</span><span class="sxs-lookup"><span data-stu-id="67939-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="67939-121">Du kan bifoga flera meddelanden i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="67939-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="67939-122">Kontrol lera att alla meddelanden är av samma typ: antingen nät fiske meddelanden och skräp post.</span><span class="sxs-lookup"><span data-stu-id="67939-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="67939-123">Lämna bröd texten i det nya meddelandet tomt.</span><span class="sxs-lookup"><span data-stu-id="67939-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="67939-124">Använd antingen. msg (standard Outlook-format) eller. eml (standard i Outlook på webb format) format för bifogade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="67939-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="67939-125">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="67939-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="67939-126">Administratörer har flera olika sätt att blockera specifika meddelanden som identifieras som skräp post.</span><span class="sxs-lookup"><span data-stu-id="67939-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="67939-127">Mer information finns i [skapa spärrade avsändare i EOP](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="67939-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="67939-128">Skicka falsk positiv till Microsoft</span><span class="sxs-lookup"><span data-stu-id="67939-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="67939-129">I stället för att använda följande procedurer för att rapportera falsk identifiering kan användare i Outlook och Outlook på webben använda tillägget rapport meddelande för Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="67939-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="67939-130">Information om hur du installerar och använder det här verktyget finns i [Aktivera rapport meddelande tillägget](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="67939-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="67939-131">Om ett meddelande felaktigt har identifierats som skräp post kan du skicka meddelandet till Microsoft spam-gruppen.</span><span class="sxs-lookup"><span data-stu-id="67939-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="67939-132">Analyserna utvärderar meddelandet och (beroende på analys resultaten) kan de globala filtren justeras så att de tillåter meddelandet.</span><span class="sxs-lookup"><span data-stu-id="67939-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="67939-133">Skapa ett nytt, tomt e-postmeddelande med `not_junk@office365.microsoft.com` som mottagare:</span><span class="sxs-lookup"><span data-stu-id="67939-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="67939-134">Dra och släpp det felidentifierade meddelandet i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="67939-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="67939-135">Detta sparar det felidentifierade meddelandet som en bifogad fil i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="67939-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="67939-136">Kopiera och klistra inte in innehållet i meddelandet eller vidarebefordra det (vi behöver det ursprungliga meddelandet så att vi kan kontrol lera meddelande huvudena).</span><span class="sxs-lookup"><span data-stu-id="67939-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="67939-137">Du kan bifoga flera meddelanden i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="67939-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="67939-138">Kontrol lera att alla meddelanden är av samma typ: antingen nät fiske meddelanden och skräp post.</span><span class="sxs-lookup"><span data-stu-id="67939-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="67939-139">Lämna bröd texten i det nya meddelandet tomt.</span><span class="sxs-lookup"><span data-stu-id="67939-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="67939-140">Använd antingen. msg (standard Outlook-format) eller. eml (standard i Outlook på webb format) format för bifogade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="67939-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="67939-141">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="67939-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="67939-142">Administratörer har flera olika sätt att tillåta vissa meddelanden att hoppa över filtrering av skräp post.</span><span class="sxs-lookup"><span data-stu-id="67939-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="67939-143">Mer information finns i [skapa säkra avsändar listor i EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="67939-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="67939-144">Skapa en regel för e-postflöde för att ta emot kopior av meddelanden som rapporteras till Microsoft</span><span class="sxs-lookup"><span data-stu-id="67939-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="67939-145">Anvisningar finns i [använda e-postflödes regler för att se vad användarna rapporterar till Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="67939-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
