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
description: Administratörer och slutanvändare kan lära sig att e-postmeddelanden (bra e-postmeddelanden som markerats som dåliga eller dåliga e-postmeddelanden) till Microsoft för analys.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 98964d17c41222fa708bdf0059c0e67151582ef1
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290375"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="24a44-103">Skicka meddelanden till Microsoft manuellt för analys</span><span class="sxs-lookup"><span data-stu-id="24a44-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="24a44-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="24a44-104">**Applies to**</span></span>
- [<span data-ttu-id="24a44-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="24a44-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="24a44-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="24a44-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="24a44-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24a44-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> <span data-ttu-id="24a44-108">Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inskickade i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="24a44-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="24a44-109">Mer information finns i Använda [administrationsinskick för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="24a44-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="24a44-110">Det kan vara frustrerande när användare i organisationen får skräppost (skräppost) eller nätfiskemeddelanden i Inkorgen, eller om de inte får ett legitimt e-postmeddelande eftersom det markeras som skräppost.</span><span class="sxs-lookup"><span data-stu-id="24a44-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="24a44-111">Vi finjusterar kontinuerligt våra skräppostfilter för att bli mer exakta.</span><span class="sxs-lookup"><span data-stu-id="24a44-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="24a44-112">Du och dina användare kan hjälpa till med detta genom att skicka falska positiva meddelanden (bra e-post markerad som dålig), falska negativa meddelanden (felaktig e-post tillåts) och nätfiskemeddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="24a44-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="24a44-113">På grund av den stora mängden inskickade uppgifter kan vi kanske inte besvara alla förfrågningar om analys.</span><span class="sxs-lookup"><span data-stu-id="24a44-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="24a44-114">Skicka falska negativa tal till Microsoft</span><span class="sxs-lookup"><span data-stu-id="24a44-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="24a44-115">Istället för att använda följande procedurer för att rapportera falska negativa tal kan användare i Outlook och Outlook på webben (tidigare kallat Outlook Web App) använda tillägget Rapportmeddelande eller tillägget Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="24a44-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="24a44-116">Mer information om hur du installerar [](enable-the-report-message-add-in.md) och använder de här verktygen finns i Aktivera tillägget Rapportmeddelande och Aktivera tillägget [Rapport nätfiske.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="24a44-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="24a44-117">Om du får ett meddelande som har passerat skräppostfiltrering som borde ha identifierats som skräppost eller nätfiske kan du skicka meddelandet till Microsofts team för skräppostanalys och Microsofts nätfiskeanalys.</span><span class="sxs-lookup"><span data-stu-id="24a44-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="24a44-118">Analytikerna granskar meddelandet och lägger till det i filtren för hela tjänsten om det uppfyller klassificeringskriterierna.</span><span class="sxs-lookup"><span data-stu-id="24a44-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="24a44-119">Skapa ett nytt, tomt e-postmeddelande med någon av följande mottagare:</span><span class="sxs-lookup"><span data-stu-id="24a44-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="24a44-120">**Skräppost:**`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="24a44-120">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="24a44-121">**Nätfiske:**`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="24a44-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="24a44-122">Dra och släpp skräppost- eller nätfiskemeddelandet i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="24a44-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="24a44-123">Då sparas skräppost- eller nätfiskemeddelandet som en bifogad fil i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="24a44-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="24a44-124">Kopiera inte och klistra inte in innehållet i meddelandet eller vidarebefordra meddelandet (vi behöver det ursprungliga meddelandet så att vi kan granska meddelanderubrikerna).</span><span class="sxs-lookup"><span data-stu-id="24a44-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="24a44-125">Du kan bifoga flera meddelanden i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="24a44-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="24a44-126">Kontrollera att alla meddelanden har samma typ: nätfiskemeddelanden eller skräppost.</span><span class="sxs-lookup"><span data-stu-id="24a44-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="24a44-127">Lämna brödtexten i det nya meddelandet tom.</span><span class="sxs-lookup"><span data-stu-id="24a44-127">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="24a44-128">Använd antingen .msg-format (standardformatet i Outlook) eller .eml-format (standardformatet i Outlook på webben) för bifogade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="24a44-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="24a44-129">Klicka på Skicka när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="24a44-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="24a44-130">Administratörer kan blockera specifika meddelanden som felaktigt stavas som skräppost på flera olika sätt.</span><span class="sxs-lookup"><span data-stu-id="24a44-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="24a44-131">Mer information finns i [Skapa listor med spärrade avsändare i EOP.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="24a44-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="24a44-132">Skicka falska positiva resultat till Microsoft</span><span class="sxs-lookup"><span data-stu-id="24a44-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="24a44-133">I stället för att använda följande procedurer för att rapportera falska positiva resultat kan användare i Outlook och Outlook på webben (tidigare kallat Outlook Web App) använda tillägget Rapportmeddelande eller tillägget Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="24a44-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="24a44-134">Mer information om hur du installerar [](enable-the-report-message-add-in.md) och använder de här verktygen finns i Aktivera tillägget Rapportmeddelande och Aktivera tillägget [Rapport nätfiske.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="24a44-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>


<span data-ttu-id="24a44-135">Om ett meddelande felaktigt identifierats som skräppost kan du skicka meddelandet till Microsofts team för skräppostanalys.</span><span class="sxs-lookup"><span data-stu-id="24a44-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="24a44-136">Analytikerna kommer att utvärdera meddelandet och (beroende på resultatet av analysen) kan filtren för hela tjänsten justeras så att meddelandet tillåts.</span><span class="sxs-lookup"><span data-stu-id="24a44-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="24a44-137">Skapa ett nytt, tomt e-postmeddelande `not_junk@office365.microsoft.com` med mottagaren:</span><span class="sxs-lookup"><span data-stu-id="24a44-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="24a44-138">Dra och släpp det felidentifierade meddelandet i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="24a44-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="24a44-139">Då sparas det felidentifierade meddelandet som en bifogad fil i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="24a44-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="24a44-140">Kopiera inte och klistra inte in innehållet i meddelandet eller vidarebefordra meddelandet (vi behöver det ursprungliga meddelandet så att vi kan granska meddelanderubrikerna).</span><span class="sxs-lookup"><span data-stu-id="24a44-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="24a44-141">Du kan bifoga flera meddelanden i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="24a44-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="24a44-142">Kontrollera att alla meddelanden har samma typ: nätfiskemeddelanden eller skräppost.</span><span class="sxs-lookup"><span data-stu-id="24a44-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="24a44-143">Lämna brödtexten i det nya meddelandet tom.</span><span class="sxs-lookup"><span data-stu-id="24a44-143">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="24a44-144">Använd antingen .msg-format (standardformatet i Outlook) eller .eml-format (standardformatet i Outlook på webben) för bifogade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="24a44-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="24a44-145">Klicka på Skicka när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="24a44-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="24a44-146">Administratörer kan tillåta filtrering av skräppost på flera olika sätt.</span><span class="sxs-lookup"><span data-stu-id="24a44-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="24a44-147">Mer information finns i [Skapa listor över betrodda avsändare i EOP.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="24a44-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="24a44-148">Var lagras data från inskickade data till Microsoft?</span><span class="sxs-lookup"><span data-stu-id="24a44-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="24a44-149">Data finns i Efterlevnadsgränsen för Office 365 i nordamerikas datacenter.</span><span class="sxs-lookup"><span data-stu-id="24a44-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="24a44-150">Data granskas av analytiker i teknikteamet för att hjälpa till att göra filtren mer effektiva.</span><span class="sxs-lookup"><span data-stu-id="24a44-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="24a44-151">Skapa en e-postflödesregel för att ta emot kopior av meddelanden som rapporterats till Microsoft</span><span class="sxs-lookup"><span data-stu-id="24a44-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="24a44-152">Instruktioner finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="24a44-152">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
