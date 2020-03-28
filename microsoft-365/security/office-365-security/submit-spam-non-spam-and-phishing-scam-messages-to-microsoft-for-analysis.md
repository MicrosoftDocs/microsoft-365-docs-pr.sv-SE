---
title: Skicka meddelanden manuellt till Microsoft för analys
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
ms.openlocfilehash: 13b2e42f749b54e0c2b71fe095c077992560ea8c
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032810"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="47de7-103">Skicka meddelanden manuellt till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="47de7-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="47de7-104">Om du är administratör i en Office 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inlämningar i Office 365 Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="47de7-104">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="47de7-105">Mer information finns i [Använda administratörsöverföring för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="47de7-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="47de7-106">Det kan vara frustrerande när användare i organisationen får skräppost eller nätfiskemeddelanden i inkorgen, eller om de inte får ett legitimt e-postmeddelande eftersom det är markerat som skräppost.</span><span class="sxs-lookup"><span data-stu-id="47de7-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="47de7-107">Vi finjusterar ständigt våra skräppostfilter för att vara mer exakta.</span><span class="sxs-lookup"><span data-stu-id="47de7-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="47de7-108">Du och dina användare kan hjälpa den här processen genom att skicka in falska positiva identifieringar (bra e-post markerad som dålig), falska negativ (felaktig e-post tillåten) och nätfiskemeddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="47de7-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="47de7-109">På grund av den stora mängden inlagor som vi får kanske vi inte kan svara på alla förfrågningar om analys.</span><span class="sxs-lookup"><span data-stu-id="47de7-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="47de7-110">Skicka falska negativ till Microsoft</span><span class="sxs-lookup"><span data-stu-id="47de7-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="47de7-111">I stället för att använda följande procedurer för att rapportera falska negativ kan användare i Outlook och Outlook på webben (tidigare kallat Outlook Web App) använda tillägget Rapportmeddelande för Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="47de7-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="47de7-112">Information om hur du installerar och använder det här verktyget finns [i Aktivera tillägget Rapportmeddelande](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="47de7-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="47de7-113">Om du får ett meddelande som skickades genom skräppostfiltrering som borde ha identifierats som skräppost eller nätfiske kan du skicka meddelandet till microsofts team för skräppostanalys och Microsofts nätfiskeanalys efter behov.</span><span class="sxs-lookup"><span data-stu-id="47de7-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="47de7-114">Analytikerna granskar meddelandet och lägger till det i de serviceomfattande filtren om det uppfyller klassificeringskriterierna.</span><span class="sxs-lookup"><span data-stu-id="47de7-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="47de7-115">Skapa ett nytt, tomt e-postmeddelande med någon av följande mottagare:</span><span class="sxs-lookup"><span data-stu-id="47de7-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="47de7-116">**Skräp:**`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="47de7-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="47de7-117">**Nätfiske:**`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="47de7-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="47de7-118">Dra och släpp skräppost- eller nätfiskemeddelandet i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="47de7-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="47de7-119">Detta sparar skräppost- eller nätfiskemeddelandet som en bifogad fil i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="47de7-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="47de7-120">Kopiera och klistra inte in innehållet i meddelandet eller vidarebefordra meddelandet (vi behöver det ursprungliga meddelandet så att vi kan inspektera meddelanderubrikerna).</span><span class="sxs-lookup"><span data-stu-id="47de7-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="47de7-121">Du kan bifoga flera meddelanden i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="47de7-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="47de7-122">Kontrollera att alla meddelanden är av samma typ: antingen meddelanden om nätfiske eller skräppost.</span><span class="sxs-lookup"><span data-stu-id="47de7-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="47de7-123">Lämna brödtexten i det nya meddelandet tom.</span><span class="sxs-lookup"><span data-stu-id="47de7-123">Leave the body of the new message empty.</span></span><li></li><span data-ttu-id="47de7-124">Använd antingen MSG-format (standardformatet Outlook) eller .eml (standardformatet Outlook på webben) för de bifogade meddelandena.</span><span class="sxs-lookup"><span data-stu-id="47de7-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="47de7-125">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="47de7-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="47de7-126">Administratörer har flera olika sätt att blockera specifika meddelanden som felidentifieras som skräppost.</span><span class="sxs-lookup"><span data-stu-id="47de7-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="47de7-127">Mer information finns [i Skapa blockerade avsändarelistor i Office 365](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="47de7-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="47de7-128">Skicka falska positiva identifieringar till Microsoft</span><span class="sxs-lookup"><span data-stu-id="47de7-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="47de7-129">I stället för att använda följande procedurer för att rapportera falska positiva identifieringar kan användare i Outlook och Outlook på webben använda tillägget Rapportmeddelande för Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="47de7-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="47de7-130">Information om hur du installerar och använder det här verktyget finns [i Aktivera tillägget Rapportmeddelande](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="47de7-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="47de7-131">Om ett meddelande har identifierats felaktigt som skräppost kan du skicka meddelandet till Microsoft Spam Analysis Team.</span><span class="sxs-lookup"><span data-stu-id="47de7-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="47de7-132">Analytikerna kommer att utvärdera meddelandet, och (beroende på resultaten av analysen) kan de serviceomfattande filtren justeras så att meddelandet går igenom.</span><span class="sxs-lookup"><span data-stu-id="47de7-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="47de7-133">Skapa ett nytt, tomt `not_junk@office365.microsoft.com` e-postmeddelande med som mottagare:</span><span class="sxs-lookup"><span data-stu-id="47de7-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="47de7-134">Dra och släpp det felidentifierade meddelandet i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="47de7-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="47de7-135">Då sparas det felidentifierade meddelandet som en bifogad fil i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="47de7-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="47de7-136">Kopiera och klistra inte in innehållet i meddelandet eller vidarebefordra meddelandet (vi behöver det ursprungliga meddelandet så att vi kan inspektera meddelanderubrikerna).</span><span class="sxs-lookup"><span data-stu-id="47de7-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="47de7-137">Du kan bifoga flera meddelanden i det nya meddelandet.</span><span class="sxs-lookup"><span data-stu-id="47de7-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="47de7-138">Kontrollera att alla meddelanden är av samma typ: antingen meddelanden om nätfiske eller skräppost.</span><span class="sxs-lookup"><span data-stu-id="47de7-138">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="47de7-139">Lämna brödtexten i det nya meddelandet tom.</span><span class="sxs-lookup"><span data-stu-id="47de7-139">Leave the body of the new message empty.</span></span><li></li><span data-ttu-id="47de7-140">Använd antingen MSG-format (standardformatet Outlook) eller .eml (standardformatet Outlook på webben) för de bifogade meddelandena.</span><span class="sxs-lookup"><span data-stu-id="47de7-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="47de7-141">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="47de7-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="47de7-142">Administratörer har flera olika sätt att tillåta specifika meddelanden att hoppa över skräppostfiltrering.</span><span class="sxs-lookup"><span data-stu-id="47de7-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="47de7-143">Mer information finns [i Skapa listor över betrodda avsändare i Office 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="47de7-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="47de7-144">Skapa en regel för e-postflöde för att ta emot kopior av meddelanden som rapporteras till Microsoft</span><span class="sxs-lookup"><span data-stu-id="47de7-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="47de7-145">Du kan skapa en regel för e-postflöde (kallas även en transportregel) som söker efter e-postmeddelanden som rapporteras till Microsoft med hjälp av de metoder som beskrivs i det här avsnittet, och du kan konfigurera mottagare av hemlig kopia så att de tar emot kopior av dessa rapporterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="47de7-145">You can create a mail flow rule (also known as a transport rule) that looks for email messages that are reported to Microsoft by using the methods described in this topic, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="47de7-146">Du kan skapa e-postflödesregeln i Administrationscenter för Exchange (EAC) och PowerShell (Exchange Online PowerShell för Office 365-kunder. Exchange Online Protection PowerShell för fristående EOP-kunder).</span><span class="sxs-lookup"><span data-stu-id="47de7-146">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="47de7-147">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="47de7-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="47de7-148">Du måste tilldelas behörigheter i Exchange Online innan du kan göra dessa procedurer.</span><span class="sxs-lookup"><span data-stu-id="47de7-148">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="47de7-149">Du måste ha tilldelats rollen **Transportregler,** som tilldelas rollerna **Organisationshantering,** **Efterlevnadshantering**och **Arkivhandling** som standard.</span><span class="sxs-lookup"><span data-stu-id="47de7-149">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="47de7-150">Mer information finns [i Hantera rollgrupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="47de7-150">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="47de7-151">Information om hur du öppnar EAC i Exchange Online finns [i Administrationscenter för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="47de7-151">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="47de7-152">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="47de7-152">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="47de7-153">Information om hur du använder Windows PowerShell för att ansluta till fristående Exchange Online Protection PowerShell finns i artikeln om att [ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="47de7-153">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="47de7-154">Mer information om regler för e-postflöde i Exchange Online och fristående EOP finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="47de7-154">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="47de7-155">Regler för e-postflöde (transportregler) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="47de7-155">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="47de7-156">Villkor och undantag för e-postflödesregel (predikat) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="47de7-156">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="47de7-157">Regelåtgärder för e-postflöde i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="47de7-157">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="47de7-158">Använda EAC för att skapa en regel för e-postflöde för att ta emot kopior av rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="47de7-158">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="47de7-159">Gå till **Regler för** **e-postflöde** \> i EAC .</span><span class="sxs-lookup"><span data-stu-id="47de7-159">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="47de7-160">Klicka på](../../media/ITPro-EAC-AddIcon.png) Ikonen Lägg **till** ![och välj sedan Skapa en ny **regel**.</span><span class="sxs-lookup"><span data-stu-id="47de7-160">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="47de7-161">Konfigurera följande inställningar på sidan **Ny regel** som öppnas:</span><span class="sxs-lookup"><span data-stu-id="47de7-161">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="47de7-162">**Namn**: Ange ett unikt, beskrivande namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="47de7-162">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="47de7-163">Till exempel hemlig kopia meddelanden som rapporterats till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="47de7-163">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="47de7-164">Klicka på **Fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="47de7-164">Click **More Options**.</span></span>

   - <span data-ttu-id="47de7-165">**Använd den här regeln om:** Välj **Mottagaradressen** \> **innehåller något av dessa ord**: I dialogrutan Ange ord eller **fraser** anger du ett av följande värden, klickar på **Lägg till** ![ikon](../../media/ITPro-EAC-AddIcon.png)och upprepar tills du har angett alla värden.</span><span class="sxs-lookup"><span data-stu-id="47de7-165">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="47de7-166">Om du vill redigera en post](../../media/ITPro-EAC-EditIcon.png)markerar du den och klickar på **Ikonen Redigera** ![redigering .</span><span class="sxs-lookup"><span data-stu-id="47de7-166">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="47de7-167">Om du vill ta bort en](../../media/ITPro-EAC-DeleteIcon.png)post markerar du den och klickar på Ikonen Ta bort ta **bort** ![.</span><span class="sxs-lookup"><span data-stu-id="47de7-167">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="47de7-168">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="47de7-168">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="47de7-169">**Gör så här:** Välj **Lägg till mottagare** \> **i rutan Hemlig kopia**.</span><span class="sxs-lookup"><span data-stu-id="47de7-169">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="47de7-170">Leta reda på och markera de mottagare som du vill lägga till i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="47de7-170">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="47de7-171">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="47de7-171">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="47de7-172">Du kan göra ytterligare val för att granska regeln, testa regeln, aktivera regeln under en viss tidsperiod och andra inställningar.</span><span class="sxs-lookup"><span data-stu-id="47de7-172">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="47de7-173">Vi rekommenderar att du testar regeln innan du tillämpar den.</span><span class="sxs-lookup"><span data-stu-id="47de7-173">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="47de7-174">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="47de7-174">When you're finished, click **Save**.</span></span>

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="47de7-175">Använda PowerShell för att skapa en regel för e-postflöde för att ta emot kopior av rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="47de7-175">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="47de7-176">I det här exemplet skapas en ny regel för e-postflöde med namnet Hemlig kopia meddelanden som rapporterats till Microsoft och som söker efter e-postmeddelanden som rapporteras till Microsoft med hjälp av de metoder som beskrivs i det här avsnittet och lägger till användarna laura@contoso.com och julia@contoso.com som mottagare av hemlig kopia.</span><span class="sxs-lookup"><span data-stu-id="47de7-176">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="47de7-177">Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="47de7-177">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="47de7-178">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="47de7-178">How do you know this worked?</span></span>

<span data-ttu-id="47de7-179">Så här kontrollerar du att du har konfigurerat regler för e-postflöde för att ta emot kopior av rapporterade meddelanden:</span><span class="sxs-lookup"><span data-stu-id="47de7-179">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="47de7-180">Gå till EAC-regler för att skicka **Edit** ![till](../../media/ITPro-EAC-EditIcon.png) **E-postflödesregler** \> **Rules** \> och markera regeln \> klicka på Redigera redigera ikon och kontrollera inställningarna.</span><span class="sxs-lookup"><span data-stu-id="47de7-180">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="47de7-181">I PowerShell kör du följande kommando för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="47de7-181">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="47de7-182">Skicka ett testmeddelanden till en av de rapporterande e-postadresserna och verifiera resultaten.</span><span class="sxs-lookup"><span data-stu-id="47de7-182">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
