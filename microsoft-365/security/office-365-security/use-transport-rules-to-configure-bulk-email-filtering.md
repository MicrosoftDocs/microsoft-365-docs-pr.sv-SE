---
title: Använda regler för e-postflöde för att filtrera massutskick av e-post i Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
ms.openlocfilehash: b08edfdd88f6f522d3bf212b209ee4b293d7198a
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033644"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a><span data-ttu-id="39a09-103">Använda regler för e-postflöde för att filtrera massutskick av e-post i Office 365</span><span class="sxs-lookup"><span data-stu-id="39a09-103">Use mail flow rules to filter bulk email in Office 365</span></span>

<span data-ttu-id="39a09-104">Om du är office 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection-kund (EOP) utan Exchange Online-postlådor använder EOP policyer mot skräppost (kallas även principer för skräppostfilter eller innehållsfilterprinciper) för att skanna inkommande meddelanden för skräppost och massutskick (kallas även grå e-post).</span><span class="sxs-lookup"><span data-stu-id="39a09-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="39a09-105">Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="39a09-105">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="39a09-106">Om du vill att fler alternativ ska filtrera massutskick kan du skapa regler för e-postflöde (kallas även transportregler) för att söka efter textmönster eller fraser som ofta finns i massutskick och markera dessa meddelanden som skräppost.</span><span class="sxs-lookup"><span data-stu-id="39a09-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="39a09-107">Mer information om massutskick finns i Vad är skillnaden mellan [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md)skräppost [och massmeddelande?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="39a09-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="39a09-108">I det här avsnittet beskrivs hur du skapar dessa regler för e-postflöde i Administrationscenter för Exchange (EAC) och PowerShell (Exchange Online PowerShell för Office 365-kunder. Exchange Online Protection PowerShell för fristående EOP-kunder).</span><span class="sxs-lookup"><span data-stu-id="39a09-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="39a09-109">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="39a09-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="39a09-110">Du måste tilldelas behörigheter i Exchange Online innan du kan göra dessa procedurer.</span><span class="sxs-lookup"><span data-stu-id="39a09-110">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="39a09-111">Du måste ha tilldelats rollen **Transportregler,** som tilldelas rollerna **Organisationshantering,** **Efterlevnadshantering**och **Arkivhandling** som standard.</span><span class="sxs-lookup"><span data-stu-id="39a09-111">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="39a09-112">Mer information finns [i Hantera rollgrupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="39a09-112">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="39a09-113">Information om hur du öppnar EAC i Exchange Online finns [i Administrationscenter för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="39a09-113">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="39a09-114">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="39a09-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="39a09-115">Information om hur du använder Windows PowerShell för att ansluta till fristående Exchange Online Protection PowerShell finns i artikeln om att [ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="39a09-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="39a09-116">Mer information om regler för e-postflöde i Exchange Online och fristående EOP finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="39a09-116">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="39a09-117">Regler för e-postflöde (transportregler) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="39a09-117">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="39a09-118">Villkor och undantag för e-postflödesregel (predikat) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="39a09-118">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="39a09-119">Regelåtgärder för e-postflöde i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="39a09-119">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="39a09-120">Listan över ord och textmönster som används för att identifiera massutskick i exemplen är inte uttömmande. Du kan lägga till och ta bort poster efter behov.</span><span class="sxs-lookup"><span data-stu-id="39a09-120">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="39a09-121">Men de är en bra utgångspunkt.</span><span class="sxs-lookup"><span data-stu-id="39a09-121">However, they are a good starting point.</span></span>

- <span data-ttu-id="39a09-122">Sökningen efter ord eller textmönster i ämnet eller andra rubrikfält i meddelandet sker *efter* att meddelandet har avkodats från MIME-innehållsöverföringskodningsmetoden som användes för att överföra det binära meddelandet mellan SMTP-servrar i ASCII-text.</span><span class="sxs-lookup"><span data-stu-id="39a09-122">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text.</span></span> <span data-ttu-id="39a09-123">Du kan inte använda villkor eller undantag för att söka efter de råa (vanligtvis Base64) kodade värdena för ämnet eller andra rubrikfält i meddelanden.</span><span class="sxs-lookup"><span data-stu-id="39a09-123">You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="39a09-124">Följande procedurer markerar ett massmeddelande som skräppost för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="39a09-124">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="39a09-125">Du kan dock lägga till ett annat villkor för att tillämpa dessa regler endast för specifika mottagare, så att du kan använda aggressiv filtrering på ett fåtal, mycket riktade användare, medan resten av användarna (som oftast får den mass-e-post de registrerat sig för) inte påverkas.</span><span class="sxs-lookup"><span data-stu-id="39a09-125">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="39a09-126">Använd EAC för att skapa regler för e-postflöde som filtrerar massutskick av e-post</span><span class="sxs-lookup"><span data-stu-id="39a09-126">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="39a09-127">Gå till **Regler för** **e-postflöde** \> i EAC .</span><span class="sxs-lookup"><span data-stu-id="39a09-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="39a09-128">Klicka på](../../media/ITPro-EAC-AddIcon.png) Ikonen Lägg **till** ![och välj sedan Skapa en ny **regel**.</span><span class="sxs-lookup"><span data-stu-id="39a09-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="39a09-129">Konfigurera följande inställningar på sidan **Ny regel** som öppnas:</span><span class="sxs-lookup"><span data-stu-id="39a09-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="39a09-130">**Namn**: Ange ett unikt, beskrivande namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="39a09-130">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="39a09-131">Klicka på **Fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="39a09-131">Click **More Options**.</span></span>

   - <span data-ttu-id="39a09-132">**Använd den här regeln om:** Konfigurera någon av följande inställningar för att söka efter innehåll i meddelanden med reguljära uttryck (RegEx) eller ord eller fraser:</span><span class="sxs-lookup"><span data-stu-id="39a09-132">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="39a09-133">**Ämnet eller** \> **brödtexten eller brödtexten matchar dessa textmönster:** Ange ett av följande värden i dialogrutan Ange ord eller **fraser** som visas, klicka på Lägg **till** ![ikon](../../media/ITPro-EAC-AddIcon.png)och upprepa tills du har angett alla värden.</span><span class="sxs-lookup"><span data-stu-id="39a09-133">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="39a09-134">Om du vill redigera en post](../../media/ITPro-EAC-EditIcon.png)markerar du den och klickar på **Ikonen Redigera** ![redigering .</span><span class="sxs-lookup"><span data-stu-id="39a09-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="39a09-135">Om du vill ta bort en](../../media/ITPro-EAC-DeleteIcon.png)post markerar du den och klickar på Ikonen Ta bort ta **bort** ![.</span><span class="sxs-lookup"><span data-stu-id="39a09-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="39a09-136">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="39a09-136">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="39a09-137">**Ämnet eller** \> **brödtexten eller brödtexten innehåller något av dessa ord:** Ange ett av följande värden i dialogrutan Ange ord eller **fraser** som visas, klicka på Lägg **till** ![ikon](../../media/ITPro-EAC-AddIcon.png)och upprepa tills du har angett alla värden.</span><span class="sxs-lookup"><span data-stu-id="39a09-137">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="39a09-138">Om du vill redigera en post](../../media/ITPro-EAC-EditIcon.png)markerar du den och klickar på **Ikonen Redigera** ![redigering .</span><span class="sxs-lookup"><span data-stu-id="39a09-138">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="39a09-139">Om du vill ta bort en](../../media/ITPro-EAC-DeleteIcon.png)post markerar du den och klickar på Ikonen Ta bort ta **bort** ![.</span><span class="sxs-lookup"><span data-stu-id="39a09-139">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="39a09-140">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="39a09-140">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="39a09-141">**Gör följande:** Välj **Ändra meddelandeegenskaperna** \> **ange scl (Spam Confidence Level)**.</span><span class="sxs-lookup"><span data-stu-id="39a09-141">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="39a09-142">Konfigurera någon av följande inställningar i dialogrutan **Ange SCL:**</span><span class="sxs-lookup"><span data-stu-id="39a09-142">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="39a09-143">Om du vill markera meddelanden som **skräppost**väljer du **6**.</span><span class="sxs-lookup"><span data-stu-id="39a09-143">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="39a09-144">Åtgärden som du har konfigurerat för skräppostfiltreringsutslag i dina anti-spam-principer tillämpas på meddelandena (standardvärdet är **Flytta meddelande till mappen Skräppost**). **Spam**</span><span class="sxs-lookup"><span data-stu-id="39a09-144">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="39a09-145">Om du vill markera meddelanden som **skräppost med högt förtroende** väljer du **9**.</span><span class="sxs-lookup"><span data-stu-id="39a09-145">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="39a09-146">Åtgärden som du har konfigurerat för skräppostfiltreringsdomar med **högt förtroende** i dina anti-spam-principer tillämpas på meddelandena (standardvärdet är **Flytta meddelande till mappen Skräppost**).</span><span class="sxs-lookup"><span data-stu-id="39a09-146">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="39a09-147">Mer information om SCL-värden finns [i SCL (Spam Confidence Level) i Office 365](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="39a09-147">For more information about SCL values, see [Spam confidence level (SCL) in Office 365](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="39a09-148">När du är klar klickar du på **Spara**</span><span class="sxs-lookup"><span data-stu-id="39a09-148">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="39a09-149">Använda PowerShell för att skapa regler för e-postflöde som filtrerar massutskick av e-post</span><span class="sxs-lookup"><span data-stu-id="39a09-149">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="39a09-150">Använd följande syntax för att skapa en eller båda av reglerna för e-postflöde (reguljära uttryck kontra ord):</span><span class="sxs-lookup"><span data-stu-id="39a09-150">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="39a09-151">I det här exemplet skapas en ny regel med namnet "Massfiltrering av e-post - RegEx" som använder samma lista med reguljära uttryck från tidigare i avsnittet för att ange meddelanden som **skräppost**.</span><span class="sxs-lookup"><span data-stu-id="39a09-151">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="39a09-152">Det här exemplet skapar en ny regel med namnet "Mass-e-filtrering - Ord" som använder samma lista med ord från tidigare i avsnittet för att ange meddelanden som **skräppost med högt förtroende**.</span><span class="sxs-lookup"><span data-stu-id="39a09-152">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="39a09-153">Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="39a09-153">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="39a09-154">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="39a09-154">How do you know this worked?</span></span>

<span data-ttu-id="39a09-155">Så här kontrollerar du att du har konfigurerat regler för e-postflöde för att filtrera massutskick av e-post:</span><span class="sxs-lookup"><span data-stu-id="39a09-155">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="39a09-156">Gå till EAC-regler för att skicka **Edit** ![till](../../media/ITPro-EAC-EditIcon.png) **E-postflödesregler** \> **Rules** \> och markera regeln \> klicka på Redigera redigera ikon och kontrollera inställningarna.</span><span class="sxs-lookup"><span data-stu-id="39a09-156">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="39a09-157">I PowerShell \<ersätter\> du Regelnamn med namnet på regeln och kör följande kommando för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="39a09-157">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="39a09-158">Från ett externt konto skickar du ett testmeddelanden till en berörd mottagare som innehåller en av fraserna eller textmönstren och verifierar resultaten.</span><span class="sxs-lookup"><span data-stu-id="39a09-158">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
