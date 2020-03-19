---
title: Använd e-postflödesregler för att konfigurera massfiltrering av e-post i Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du använder regler för e-postflöde i Exchange Online Protection för massfiltrering av e-post.
ms.openlocfilehash: 81b0f4cc58d712c3a1c1e09dab02d1c6f56cb69d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809355"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a><span data-ttu-id="4d2c4-103">Använd e-postflödesregler för att konfigurera massfiltrering av e-post i Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4d2c4-103">Use mail flow rules to configure bulk email filtering in Exchange Online Protection</span></span>

<span data-ttu-id="4d2c4-104">Du kan ange innehållsfilter för skräppost och masse-e-post med hjälp av standardprinciperna för skräppostinnehåll.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-104">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies.</span></span> <span data-ttu-id="4d2c4-105">Kolla [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md) och [Ange ContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) om hur du ställer in principer för innehållsfilter.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-105">Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) on how to set the content filter policies.</span></span>

<span data-ttu-id="4d2c4-106">Om du vill ha fler alternativ för att filtrera massmeddelanden kan du skapa regler för e-postflöde (kallas även transportregler) för att söka efter textmönster eller fraser som ofta finns i massmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-106">If you want to more options to filter bulk messages, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases frequently found in bulk emails.</span></span> <span data-ttu-id="4d2c4-107">Alla meddelanden som innehåller dessa egenskaper markeras som skräppost.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-107">Any message containing these characteristics will be marked as spam.</span></span> <span data-ttu-id="4d2c4-108">Om du använder dessa regler kan mängden oönskad masse-e-post som organisationen tar emot minskas.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-108">Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d2c4-109">Innan du skapar reglerna för e-postflöde dokumenteras det här avsnittet, rekommenderar vi att du först läsa [Vad är skillnaden mellan skräppost och mass-e-post?](what-s-the-difference-between-junk-email-and-bulk-email.md) och Bulk [klagomålnivå värden](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="4d2c4-109">Before creating the mail flow rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span><br>
> <span data-ttu-id="4d2c4-110">Följande procedurer markerar ett meddelande som skräppost för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-110">The following procedures mark a message as spam for your entire organization.</span></span> <span data-ttu-id="4d2c4-111">Du kan dock lägga till ett annat villkor om du bara vill tillämpa dessa regler på specifika mottagare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-111">However, you can add another condition to apply these rules only to specific recipients in your organization.</span></span> <span data-ttu-id="4d2c4-112">På så sätt kan de aggressiva massinställningarna för filtrering av e-post tillämpas på ett fåtal användare som är mycket målinriktade, medan resten av användarna (som oftast får massmeddelandet de registrerat sig för) inte påverkas.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-112">This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="4d2c4-113">Skapa en regel för e-postflöde för att filtrera massmeddelanden baserat på textmönster</span><span class="sxs-lookup"><span data-stu-id="4d2c4-113">Create a mail flow rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="4d2c4-114">Gå till Regler för **e-postflöde** \> **i**administrationscentret för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="4d2c4-114">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="4d2c4-115">Klicka på](../../media/ITPro-EAC-AddIcon.gif) Lägg **till** ![ikonen och välj sedan Skapa en ny **regel**.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-115">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="4d2c4-116">Ange ett namn på regeln.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-116">Specify a name for the rule.</span></span>

4. <span data-ttu-id="4d2c4-117">Klicka på **Fler** ![](../../media/ITPro-EAC-MoreOptionsIcon.png)alternativ Fler alternativ ikon .</span><span class="sxs-lookup"><span data-stu-id="4d2c4-117">Click **More options** ![More options icon](../../media/ITPro-EAC-MoreOptionsIcon.png).</span></span> <span data-ttu-id="4d2c4-118">Under **Använd den här regeln om**du väljer **Ämnes- eller brödtexteller** \> **brödtext matchar dessa textmönster**.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-118">Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>

5. <span data-ttu-id="4d2c4-119">I dialogrutan **Ange ord eller fraser** lägger du till följande reguljära uttryck som vanligen finns i massmeddelanden, en i taget och klickar på **OK** när du är klar:</span><span class="sxs-lookup"><span data-stu-id="4d2c4-119">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **OK** when you're done:</span></span>

   - `If you are unable to view the content of this email\, please`

   - `\>(safe )?unsubscribe( here)?\</a\>`

   - `If you do not wish to receive further communications like this\, please`

   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`

   - `To stop receiving these+emails\:http\://`

   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`

   - `no longer (wish )?(to )?(be sent|receive) w+ email`

   - `If you are unable to view the content of this email\, please click here`

   - `To ensure you receive (your daily deals|our e-?mails)\, add`

   - `If you no longer wish to receive these emails`

   - `to change your (subscription preferences|preferences or unsubscribe)`

   - `click (here to|the) unsubscribe`

   <span data-ttu-id="4d2c4-120">Listan ovan är inte en uttömmande uppsättning reguljära uttryck som finns i masse-e-postmeddelanden. mer kan läggas till eller tas bort efter behov.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-120">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed.</span></span> <span data-ttu-id="4d2c4-121">Men det är en bra utgångspunkt.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-121">However, it's a good starting point.</span></span>

   <span data-ttu-id="4d2c4-122">Sökningen efter ord eller textmönster i ämnes- eller andra rubrikfält en i meddelandet inträffar *efter* att meddelandet har avkodats från MIME-kodningsmetoden för innehållsöverföring som användes för att överföra det binära meddelandet mellan SMTP-servrar i ASCII-text.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-122">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text.</span></span> <span data-ttu-id="4d2c4-123">Du kan inte använda villkor eller undantag för att söka efter de råa (vanligtvis Base64) kodade värdena för ämnes- eller andra rubrikfält i meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-123">You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

6. <span data-ttu-id="4d2c4-124">Under **Gör följande**väljer du Ändra **meddelandeegenskaperna** \> som anges på **förtroendenivån för skräppost (SCL).**</span><span class="sxs-lookup"><span data-stu-id="4d2c4-124">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>

7. <span data-ttu-id="4d2c4-125">I dialogrutan **Ange SCL** ställer du in SCL till **5,** **6**eller **9**och klickar på **ok**.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-125">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>

   <span data-ttu-id="4d2c4-126">Om du ställer in SCL till 5 eller 6 krävs **åtgärden Skräppost,** samtidigt som scl-värdet ställs in på 9, vilket är **skräpet på skräpposten,** som konfigurerats i innehållsfilterprincipen.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-126">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy.</span></span> <span data-ttu-id="4d2c4-127">Tjänsten utför åtgärden i innehållsfilterprincipen.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-127">The service will perform the action set in the content filter policy.</span></span> <span data-ttu-id="4d2c4-128">Standardåtgärden är att leverera meddelandet till mottagarnas skräppostmapp, men olika åtgärder kan konfigureras enligt beskrivningen i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4d2c4-128">The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

   <span data-ttu-id="4d2c4-129">Om den konfigurerade åtgärden är att sätta meddelandet i karantän i stället för att skicka det till mottagarens skräppostmapp skickas meddelandet till administratörskarantänen som en regel match för e-postflödet, och det kommer inte att vara tillgängligt i slutanvändarens skräppostkarantän eller via slutanvändaren spam-meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-129">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span>

   <span data-ttu-id="4d2c4-130">Mer information om SCL-värden i tjänsten finns i [Förtroendenivåer för skräppost](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4d2c4-130">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="4d2c4-131">Spara regeln.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-131">Save the rule.</span></span>

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="4d2c4-132">Skapa en regel för e-postflöde för att filtrera massmeddelanden baserat på fraser</span><span class="sxs-lookup"><span data-stu-id="4d2c4-132">Create a mail flow rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="4d2c4-133">I EAC går du till **regler för e-postflöde** \> **.**</span><span class="sxs-lookup"><span data-stu-id="4d2c4-133">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="4d2c4-134">Klicka på](../../media/ITPro-EAC-AddIcon.gif) Lägg **till** ![ikonen och välj sedan Skapa en ny **regel**.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-134">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="4d2c4-135">Ange ett namn på regeln.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-135">Specify a name for the rule.</span></span>

4. <span data-ttu-id="4d2c4-136">Klicka på **Fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-136">Click **More options**.</span></span> <span data-ttu-id="4d2c4-137">Under **Använd den här regeln om**du väljer Ämnet eller **brödtexten** \> eller **brödtexten innehåller något av dessa ord**.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-137">Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>

5. <span data-ttu-id="4d2c4-138">I dialogrutan **Ange ord eller fraser** lägger du till följande fraser som vanligen finns i massmeddelanden, en i taget och klickar på **ok** när du är klar:</span><span class="sxs-lookup"><span data-stu-id="4d2c4-138">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span>

   - `to change your preferences or unsubscribe`

   - `Modify email preferences or unsubscribe`

   - `This is a promotional email`

   - `You are receiving this email because you requested a subscription`

   - `click here to unsubscribe`

   - `You have received this email because you are subscribed`

   - `If you no longer wish to receive our email newsletter`

   - `to unsubscribe from this newsletter`

   - `If you have trouble viewing this email`

   - `This is an advertisement`

   - `you would like to unsubscribe or change your`

   - `view this email as a webpage`

   - `You are receiving this email because you are subscribed`

   <span data-ttu-id="4d2c4-139">Den här listan är inte en uttömmande uppsättning fraser som finns i bulk e-postmeddelanden; mer kan läggas till eller tas bort efter behov.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-139">This list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed.</span></span> <span data-ttu-id="4d2c4-140">Men det är en bra utgångspunkt.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-140">However, it's a good starting point.</span></span>

6. <span data-ttu-id="4d2c4-141">Under **Gör följande**väljer du Ändra **meddelandeegenskaperna** \> som anges på **förtroendenivån för skräppost (SCL).**</span><span class="sxs-lookup"><span data-stu-id="4d2c4-141">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>

7. <span data-ttu-id="4d2c4-142">I dialogrutan **Ange SCL** ställer du in SCL till **5,** **6**eller **9**och klickar på **ok**.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-142">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>

   <span data-ttu-id="4d2c4-143">Om du ställer in SCL till 5 eller 6 krävs **åtgärden Skräppost,** samtidigt som scl-värdet ställs in på 9, vilket är **skräpet på skräpposten,** som konfigurerats i innehållsfilterprincipen.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-143">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy.</span></span> <span data-ttu-id="4d2c4-144">Tjänsten utför åtgärden i innehållsfilterprincipen.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-144">The service will perform the action set in the content filter policy.</span></span> <span data-ttu-id="4d2c4-145">Standardåtgärden är att leverera meddelandet till mottagarnas skräppostmapp, men olika åtgärder kan konfigureras enligt beskrivningen i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4d2c4-145">The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

   <span data-ttu-id="4d2c4-146">Om den konfigurerade åtgärden är att sätta meddelandet i karantän i stället för att skicka det till mottagarens skräppostmapp skickas meddelandet till administratörskarantänen som en regel match för e-postflödet, och det kommer inte att vara tillgängligt i slutanvändarens skräppostkarantän eller via slutanvändaren spam-meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-146">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span>

   <span data-ttu-id="4d2c4-147">Mer information om SCL-värden i tjänsten finns i [Förtroendenivåer för skräppost](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4d2c4-147">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="4d2c4-148">Spara regeln.</span><span class="sxs-lookup"><span data-stu-id="4d2c4-148">Save the rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="4d2c4-149">Mer information</span><span class="sxs-lookup"><span data-stu-id="4d2c4-149">For more information</span></span>

[<span data-ttu-id="4d2c4-150">Vad är skillnaden mellan skräppost och masse-e-post?</span><span class="sxs-lookup"><span data-stu-id="4d2c4-150">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)

[<span data-ttu-id="4d2c4-151">Värden på massklagomålsnivå</span><span class="sxs-lookup"><span data-stu-id="4d2c4-151">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)

[<span data-ttu-id="4d2c4-152">Konfigurera principer för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="4d2c4-152">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="4d2c4-153">Avancerade alternativ för skräppostfiltrering</span><span class="sxs-lookup"><span data-stu-id="4d2c4-153">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
