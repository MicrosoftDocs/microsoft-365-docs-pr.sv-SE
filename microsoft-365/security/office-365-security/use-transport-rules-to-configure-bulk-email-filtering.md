---
title: Använda e-postflödesregler för att filtrera massutskick
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att använda e-postflödesregler (transportregler) för att identifiera och filtrera massutskick (grå e-post) i Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c86f229d6c7371854878a67937cc38374ed00961
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207206"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="740ed-103">Använda e-postflödesregler för att filtrera massutskick i EOP</span><span class="sxs-lookup"><span data-stu-id="740ed-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="740ed-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="740ed-104">**Applies to**</span></span>
- [<span data-ttu-id="740ed-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="740ed-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="740ed-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="740ed-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="740ed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="740ed-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="740ed-108">I Microsoft 365-organisationer som har postlådor i Exchange Online eller fristående organisationer som har Exchange Online Protection (EOP) utan Exchange Online-postlådor använder EOP principer för skräppostskydd (kallas även principer för skräppostfilter eller principer för innehållsfilter) för att söka efter inkommande meddelanden efter skräppost och massutskick (kallas även grå e-post).</span><span class="sxs-lookup"><span data-stu-id="740ed-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="740ed-109">Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="740ed-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="740ed-110">Om du vill ha fler alternativ för att filtrera massutskick kan du skapa e-postflödesregler (kallas även transportregler) för att söka efter textmönster eller fraser som ofta förekommer i massutskick och markera dessa meddelanden som skräppost.</span><span class="sxs-lookup"><span data-stu-id="740ed-110">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="740ed-111">Mer information om massutskick finns i Vad är skillnaden mellan skräppost och massutskick [av](what-s-the-difference-between-junk-email-and-bulk-email.md) e-post? och Nivå för mass klagomål [(BCL) i EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="740ed-111">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="740ed-112">I det här avsnittet beskrivs hur du skapar de här e-postflödesreglerna i administrationscentret för Exchange (EAC) och PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="740ed-112">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="740ed-113">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="740ed-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="740ed-114">Du måste ha tilldelats behörigheter i Exchange Online eller Exchange Online Protection innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="740ed-114">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="740ed-115">Specifikt behöver du rollen **Transportregler,** som är tilldelad rollgrupperna **Organisationshantering,**  Efterlevnadshantering (globala administratörer) och **Hantering** av arkivhandlingar som standard.</span><span class="sxs-lookup"><span data-stu-id="740ed-115">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="740ed-116">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="740ed-116">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="740ed-117">Behörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="740ed-117">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="740ed-118">Behörigheter i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="740ed-118">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="740ed-119">Använd EAC för att ändra listan över medlemmar i rollgrupper</span><span class="sxs-lookup"><span data-stu-id="740ed-119">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="740ed-120">Information om hur du öppnar EAC i Exchange Online finns i [Administrationscenter för Exchange i Exchange Online.](/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="740ed-120">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="740ed-121">Information om hur du öppnar EAC i fristående EOP finns i [Administrationscenter för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="740ed-121">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="740ed-122">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="740ed-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="740ed-123">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="740ed-123">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="740ed-124">Mer information om e-postflödesregler i Exchange Online och fristående EOP finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="740ed-124">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="740ed-125">E-postflödesregler (transportregler) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="740ed-125">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="740ed-126">Villkor och undantag för e-postflödesregel (predikat) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="740ed-126">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="740ed-127">Åtgärder för e-postflödesregel i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="740ed-127">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="740ed-128">Listan med ord och textmönster som används för att identifiera massutskick i exemplen är inte uttömmande. du kan lägga till och ta bort poster efter behov.</span><span class="sxs-lookup"><span data-stu-id="740ed-128">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="740ed-129">De är dock en bra utgångspunkt.</span><span class="sxs-lookup"><span data-stu-id="740ed-129">However, they are a good starting point.</span></span>

- <span data-ttu-id="740ed-130">Sökningen efter ord eller textmönster i ämnes- eller andra  rubrikfält i meddelandet inträffar när meddelandet har avkodats från kodningsmetoden för MIME-innehållsöverföring som användes för att överföra det binära meddelandet mellan SMTP-servrar i ASCII-text.</span><span class="sxs-lookup"><span data-stu-id="740ed-130">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text.</span></span> <span data-ttu-id="740ed-131">Du kan inte använda villkor eller undantag för att söka efter rådata (vanligtvis Base64) kodade värden för ämnesfält eller andra rubrikfält i meddelanden.</span><span class="sxs-lookup"><span data-stu-id="740ed-131">You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="740ed-132">Så här markerar du ett massmeddelande som skräppost för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="740ed-132">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="740ed-133">Du kan dock lägga till ytterligare ett villkor för att tillämpa de här reglerna endast för specifika mottagare, så att du kan använda aggressiv filtrering på några få användare med hög målgrupp, medan övriga användare (som i de flesta fall får massutskick som de registrerat sig för) inte påverkas.</span><span class="sxs-lookup"><span data-stu-id="740ed-133">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="740ed-134">Använda EAC för att skapa e-postflödesregler som filtrerar massutskick av e-post</span><span class="sxs-lookup"><span data-stu-id="740ed-134">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="740ed-135">Gå till E-postflödesregler **i** \> EAC.</span><span class="sxs-lookup"><span data-stu-id="740ed-135">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="740ed-136">Klicka **på ikonen** Lägg till lägg till och välj sedan Skapa en ny ![ ](../../media/ITPro-EAC-AddIcon.png) **regel.**</span><span class="sxs-lookup"><span data-stu-id="740ed-136">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="740ed-137">På sidan **Ny regel** som öppnas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="740ed-137">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="740ed-138">**Namn**: Ange ett unikt, beskrivande namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="740ed-138">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="740ed-139">Klicka **på Fler alternativ.**</span><span class="sxs-lookup"><span data-stu-id="740ed-139">Click **More Options**.</span></span>

   - <span data-ttu-id="740ed-140">**Använd den här regeln om:** Konfigurera någon av följande inställningar för att söka efter innehåll i meddelanden med hjälp av reguljära uttryck (RegEx) eller ord eller fraser:</span><span class="sxs-lookup"><span data-stu-id="740ed-140">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="740ed-141">**Ämnet eller brödtexten** \> ämne eller brödtext matchar dessa textmönster: I dialogrutan Ange ord eller fraser som  visas anger du något av följande värden, klickar på Lägg till ikon och upprepar **tills** du har angett alla  ![ ](../../media/ITPro-EAC-AddIcon.png) värden.</span><span class="sxs-lookup"><span data-stu-id="740ed-141">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="740ed-142">Om du vill redigera en post markerar du den och klickar **på Redigera** ![ redigeringsikon ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="740ed-142">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="740ed-143">Om du vill ta bort en post markerar du den och klickar på **ta** ![ bort-ikonen ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="740ed-143">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="740ed-144">När du är klar klickar du på **OK.**</span><span class="sxs-lookup"><span data-stu-id="740ed-144">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="740ed-145">**Ämnet eller brödtexten** \> **ämne eller** brödtext innehåller något av följande ord: I dialogrutan Ange ord eller  fraser som visas anger du något av följande värden, klickar på Lägg till ikon och upprepar **tills** du har angett alla ![ ](../../media/ITPro-EAC-AddIcon.png) värden.</span><span class="sxs-lookup"><span data-stu-id="740ed-145">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="740ed-146">Om du vill redigera en post markerar du den och klickar **på Redigera** ![ redigeringsikon ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="740ed-146">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="740ed-147">Om du vill ta bort en post markerar du den och klickar på **ta** ![ bort-ikonen ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="740ed-147">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="740ed-148">När du är klar klickar du på **OK.**</span><span class="sxs-lookup"><span data-stu-id="740ed-148">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="740ed-149">**Gör följande:** Välj **Ändra meddelandeegenskaperna** \> **för att ange SCL (Spam Confidence Level).**</span><span class="sxs-lookup"><span data-stu-id="740ed-149">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="740ed-150">I dialogrutan **Ange SCL** konfigurerar du någon av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="740ed-150">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="740ed-151">Om du vill markera meddelanden **som skräppost** väljer du **6**.</span><span class="sxs-lookup"><span data-stu-id="740ed-151">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="740ed-152">Åtgärden som du har konfigurerat  för filtrering av skräppost i dina principer mot skräppost tillämpas på meddelandena (standardvärdet är Flytta meddelandet till mappen **Skräppost).**</span><span class="sxs-lookup"><span data-stu-id="740ed-152">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="740ed-153">Om du vill markera meddelanden **som skräppost med hög konfidens** väljer du **9**.</span><span class="sxs-lookup"><span data-stu-id="740ed-153">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="740ed-154">Åtgärden som du har konfigurerat  för hög konfidens för skräppostfiltrering av skräppost-bedömningar i dina principer för skydd mot skräppost tillämpas på meddelandena (standardvärdet är Flytta meddelandet till **mappen Skräppost).**</span><span class="sxs-lookup"><span data-stu-id="740ed-154">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="740ed-155">Mer information om SCL-värden finns [i SCL (Spam Confidence Level) i EOP.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="740ed-155">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="740ed-156">När du är klar klickar du på **Spara**</span><span class="sxs-lookup"><span data-stu-id="740ed-156">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="740ed-157">Använda PowerShell för att skapa e-postflödesregler som filtrerar massutskick av e-post</span><span class="sxs-lookup"><span data-stu-id="740ed-157">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="740ed-158">Använd följande syntax för att skapa en eller båda e-postflödesreglerna (reguljära uttryck kontra ord):</span><span class="sxs-lookup"><span data-stu-id="740ed-158">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="740ed-159">I det här exemplet skapas en ny regel med namnet "Massfiltrering av e-post – RegEx" som använder samma lista med reguljära uttryck från tidigare i avsnittet för att ange meddelanden som **Skräppost.**</span><span class="sxs-lookup"><span data-stu-id="740ed-159">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="740ed-160">I det här exemplet skapas en ny regel med namnet "Massfiltrering av e-post – ord" som använder samma lista med ord från tidigare i avsnittet för att ange skräppost med **hög konfidens.**</span><span class="sxs-lookup"><span data-stu-id="740ed-160">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="740ed-161">Detaljerad information om syntax och parametrar finns i [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="740ed-161">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="740ed-162">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="740ed-162">How do you know this worked?</span></span>

<span data-ttu-id="740ed-163">Kontrollera att du har konfigurerat e-postflödesregler för att filtrera massutskick genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="740ed-163">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="740ed-164">I EAC går du till **E-postflödesregler** \>  \> väljer regeln och \> klickar på **Redigera** ![ ](../../media/ITPro-EAC-EditIcon.png) redigeringsikon och kontrollerar inställningarna.</span><span class="sxs-lookup"><span data-stu-id="740ed-164">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="740ed-165">I PowerShell \<Rule Name\> ersätter du med namnet på regeln och kör följande kommando för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="740ed-165">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="740ed-166">Skicka ett testmeddelande från ett externt konto till en mottagare som innehåller något av fraserna eller textmönstren och verifiera resultatet.</span><span class="sxs-lookup"><span data-stu-id="740ed-166">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>