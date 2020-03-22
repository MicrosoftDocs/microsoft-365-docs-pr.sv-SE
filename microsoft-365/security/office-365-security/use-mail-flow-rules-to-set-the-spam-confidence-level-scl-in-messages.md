---
title: Använda regler för e-postflöde till SCL i meddelanden
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
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du ställer in SCL för meddelanden i Exchange Online Protection.
ms.openlocfilehash: b7ea9a0f046e5a48f0de8d4ac9ae6d53821f03c0
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895101"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="17e93-103">Använd regler för e-postflöde för att ställa in scl (Spam Confidence Level) i meddelanden</span><span class="sxs-lookup"><span data-stu-id="17e93-103">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="17e93-104">Om du är office 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection-kund (EOP) utan Exchange Online-postlådor använder EOP policyer mot skräppost (kallas även principer för skräppostfilter eller innehållsfilterprinciper) för att skanna inkommande meddelanden för skräppost.</span><span class="sxs-lookup"><span data-stu-id="17e93-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="17e93-105">Mer information finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="17e93-105">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="17e93-106">Om du vill markera specifika meddelanden som skräppost innan de ens skannas av skräppostfiltrering eller markera meddelanden så att de hoppar över skräppostfiltrering kan du skapa regler för e-postflöde (kallas även transportregler) för att identifiera meddelandena och ställa in säkerhetsnivån för skräppost (SCL).</span><span class="sxs-lookup"><span data-stu-id="17e93-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="17e93-107">Mer information om SCL finns [i SCL (Spam Confidence Level) i Office 365](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="17e93-107">For more information about the SCL, see [Spam confidence level (SCL) in Office 365](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="17e93-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="17e93-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="17e93-109">Du måste tilldelas behörigheter i Exchange Online innan du kan göra dessa procedurer.</span><span class="sxs-lookup"><span data-stu-id="17e93-109">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="17e93-110">Du måste ha tilldelats rollen **Transportregler,** som tilldelas rollerna **Organisationshantering,** **Efterlevnadshantering**och **Arkivhandling** som standard.</span><span class="sxs-lookup"><span data-stu-id="17e93-110">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="17e93-111">Mer information finns [i Hantera rollgrupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="17e93-111">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="17e93-112">Information om hur du öppnar EAC i Exchange Online finns [i Administrationscenter för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="17e93-112">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="17e93-113">Mer information om regler för e-postflöde i Exchange Online finns [i Regler för e-postflöde (transportregler) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="17e93-113">For more information about mail flow rules in Exchange Online, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="17e93-114">Använda EAC för att skapa en regel för e-postflöde som anger SCL för ett meddelande</span><span class="sxs-lookup"><span data-stu-id="17e93-114">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="17e93-115">Gå till **Regler för** **e-postflöde** \> i EAC .</span><span class="sxs-lookup"><span data-stu-id="17e93-115">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="17e93-116">Klicka på](../../media/ITPro-EAC-AddIcon.png) Ikonen Lägg **till** ![och välj sedan Skapa en ny **regel**.</span><span class="sxs-lookup"><span data-stu-id="17e93-116">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="17e93-117">Konfigurera följande inställningar på sidan **Ny regel** som öppnas:</span><span class="sxs-lookup"><span data-stu-id="17e93-117">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="17e93-118">**Namn**: Ange ett unikt, beskrivande namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="17e93-118">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="17e93-119">Klicka på **Fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="17e93-119">Click **More Options**.</span></span>

   - <span data-ttu-id="17e93-120">**Använd den här regeln om**: Välj ett eller flera villkor för att identifiera meddelanden.</span><span class="sxs-lookup"><span data-stu-id="17e93-120">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="17e93-121">Mer information finns i [Villkor och undantag för regel för e-postflöde (predikat) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="17e93-121">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="17e93-122">**Gör följande:** Välj **Ändra meddelandeegenskaperna** \> **ange scl (Spam Confidence Level)**.</span><span class="sxs-lookup"><span data-stu-id="17e93-122">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="17e93-123">Konfigurera ett av följande värden i dialogrutan **Ange SCL** som visas:</span><span class="sxs-lookup"><span data-stu-id="17e93-123">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="17e93-124">**Bypass spam filtrering:** Detta ställer in SCL till -1, vilket innebär att meddelandena kommer att hoppa över spam filtrering.</span><span class="sxs-lookup"><span data-stu-id="17e93-124">**Bypass spam filtering**: This sets the SCL to -1, which means the messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="17e93-125">Var mycket försiktig med att tillåta meddelanden att hoppa över skräppostfiltrering.</span><span class="sxs-lookup"><span data-stu-id="17e93-125">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="17e93-126">Angripare kan använda det här säkerhetsproblemet för att skicka nätfiske och andra skadliga meddelanden till din organisation.</span><span class="sxs-lookup"><span data-stu-id="17e93-126">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="17e93-127">Reglerna för e-postflöde kräver mer än bara avsändarens e-postadress eller domän.</span><span class="sxs-lookup"><span data-stu-id="17e93-127">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="17e93-128">Mer information finns [i Skapa listor över betrodda avsändare i Office 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="17e93-128">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="17e93-129">**0 till 4**: Meddelandet skickas via skräppostfiltrering för ytterligare bearbetning.</span><span class="sxs-lookup"><span data-stu-id="17e93-129">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="17e93-130">**5 eller 6**: Meddelandet är markerat som **spam**.</span><span class="sxs-lookup"><span data-stu-id="17e93-130">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="17e93-131">Åtgärden som du har konfigurerat för skräppostfiltreringsutslag i dina anti-spam-principer tillämpas på meddelandet (standardvärdet är **Flytta meddelande till mappen Skräppost**). **Spam**</span><span class="sxs-lookup"><span data-stu-id="17e93-131">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="17e93-132">**7 till 9:** Meddelandet är markerat som **Hög förtroende spam**.</span><span class="sxs-lookup"><span data-stu-id="17e93-132">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="17e93-133">Åtgärden som du har konfigurerat för skräppostfiltreringsdomar med **högt förtroende** i dina anti-spam-principer tillämpas på meddelandet (standardvärdet är **Flytta meddelande till mappen Skräppost).**</span><span class="sxs-lookup"><span data-stu-id="17e93-133">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="17e93-134">Ange eventuella ytterligare egenskaper som du vill ha för regeln.</span><span class="sxs-lookup"><span data-stu-id="17e93-134">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="17e93-135">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="17e93-135">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="17e93-136">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="17e93-136">How do you know this worked?</span></span>

<span data-ttu-id="17e93-137">Om du vill kontrollera att den här proceduren fungerar korrekt skickar du ett e-postmeddelande till någon i organisationen och kontrollerar att åtgärden som utförs i meddelandet är som förväntat.</span><span class="sxs-lookup"><span data-stu-id="17e93-137">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="17e93-138">Om du till exempel **ställer in scl (Spam Confidence Level)** på **Kringgå skräppostfiltrering**ska meddelandet skickas till den angivna mottagarens inkorg.</span><span class="sxs-lookup"><span data-stu-id="17e93-138">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="17e93-139">Men om du **ställer in spam förtroendenivå (SCL)** till **9**, och **hög förtroende spam** åtgärder för din tillämpliga innehåll filter politik är att flytta meddelandet till mappen Skräppost, då meddelandet ska skickas till den angivna mottagarens skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="17e93-139">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
