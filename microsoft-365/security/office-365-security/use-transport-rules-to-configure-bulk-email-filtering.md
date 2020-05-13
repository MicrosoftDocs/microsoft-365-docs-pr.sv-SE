---
title: Använda regler för e-postflöde för att filtrera massutskick
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
description: Administratörer kan lära sig hur du använder regler för e-postflöde (transportregler) för att identifiera och filtrera massutskick (grå e-post) i Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb305551db1e86d8d6eccf5e95cdaad29e6711ef
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208531"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="73075-103">Använd regler för e-postflöde för att filtrera massutskick i EOP</span><span class="sxs-lookup"><span data-stu-id="73075-103">Use mail flow rules to filter bulk email in EOP</span></span>

<span data-ttu-id="73075-104">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor använder EOP policyer mot skräppost (kallas även principer för skräppostfilter eller innehållsfilter) för att söka igenom inkommande meddelanden efter skräppost och massutskick (kallas även grå e-post).</span><span class="sxs-lookup"><span data-stu-id="73075-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="73075-105">Mer information finns [i Konfigurera principer mot skräppost i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="73075-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="73075-106">Om du vill att fler alternativ ska filtrera massutskick kan du skapa regler för e-postflöde (kallas även transportregler) för att söka efter textmönster eller fraser som ofta finns i massutskick och markera dessa meddelanden som skräppost.</span><span class="sxs-lookup"><span data-stu-id="73075-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="73075-107">Mer information om massutskick finns i Vad är skillnaden mellan [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md)skräppost [och massmeddelande?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="73075-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="73075-108">I det här avsnittet beskrivs hur du skapar dessa regler för e-postflöde i Administrationscenter för Exchange (EAC) och PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="73075-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="73075-109">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="73075-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="73075-110">Du måste tilldelas behörigheter innan du kan göra följande:</span><span class="sxs-lookup"><span data-stu-id="73075-110">You need to be assigned permissions before you can do these procedures:</span></span>

  - <span data-ttu-id="73075-111">I Exchange Online läser du posten "E-postflöde" i [Funktionsbehörigheter i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span><span class="sxs-lookup"><span data-stu-id="73075-111">In Exchange Online, see the "Mail flow" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span></span>
  
  - <span data-ttu-id="73075-112">I fristående EOP behöver du rollen Transportregler, som tilldelas rollerna OrganizationManagement, ComplianceManagement och RecordsManagement som standard.</span><span class="sxs-lookup"><span data-stu-id="73075-112">In standalone EOP, you need the Transport Rules role, which is assigned to the OrganizationManagement, ComplianceManagement, and RecordsManagement roles by default.</span></span> <span data-ttu-id="73075-113">Mer information finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd EAC ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="73075-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="73075-114">Information om hur du öppnar EAC i Exchange Online finns [i Administrationscenter för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="73075-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="73075-115">Om du vill öppna EAC i fristående EOP finns [i Exchange admin center i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="73075-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="73075-116">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="73075-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="73075-117">Information om hur du använder Windows PowerShell för att ansluta till fristående Exchange Online Protection PowerShell finns i artikeln om att [ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="73075-117">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="73075-118">Mer information om regler för e-postflöde i Exchange Online och fristående EOP finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="73075-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="73075-119">Regler för e-postflöde (transportregler) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="73075-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="73075-120">Villkor och undantag för e-postflödesregel (predikat) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="73075-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="73075-121">Regelåtgärder för e-postflöde i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="73075-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="73075-122">Listan över ord och textmönster som används för att identifiera massutskick i exemplen är inte uttömmande. Du kan lägga till och ta bort poster efter behov.</span><span class="sxs-lookup"><span data-stu-id="73075-122">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="73075-123">Men de är en bra utgångspunkt.</span><span class="sxs-lookup"><span data-stu-id="73075-123">However, they are a good starting point.</span></span>

- <span data-ttu-id="73075-124">Sökningen efter ord eller textmönster i ämnet eller andra rubrikfält i meddelandet sker *efter* att meddelandet har avkodats från MIME-innehållsöverföringskodningsmetoden som användes för att överföra det binära meddelandet mellan SMTP-servrar i ASCII-text.</span><span class="sxs-lookup"><span data-stu-id="73075-124">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text.</span></span> <span data-ttu-id="73075-125">Du kan inte använda villkor eller undantag för att söka efter de råa (vanligtvis Base64) kodade värdena för ämnet eller andra rubrikfält i meddelanden.</span><span class="sxs-lookup"><span data-stu-id="73075-125">You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="73075-126">Följande procedurer markerar ett massmeddelande som skräppost för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="73075-126">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="73075-127">Du kan dock lägga till ett annat villkor för att tillämpa dessa regler endast för specifika mottagare, så att du kan använda aggressiv filtrering på ett fåtal, mycket riktade användare, medan resten av användarna (som oftast får den mass-e-post de registrerat sig för) inte påverkas.</span><span class="sxs-lookup"><span data-stu-id="73075-127">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="73075-128">Använd EAC för att skapa regler för e-postflöde som filtrerar massutskick av e-post</span><span class="sxs-lookup"><span data-stu-id="73075-128">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="73075-129">Gå till Regler för **e-postflöde** i EAC \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="73075-129">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="73075-130">Klicka på **Ikonen Lägg till** och välj sedan Skapa en ny ![ ](../../media/ITPro-EAC-AddIcon.png) **regel**.</span><span class="sxs-lookup"><span data-stu-id="73075-130">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="73075-131">Konfigurera följande inställningar på sidan **Ny regel** som öppnas:</span><span class="sxs-lookup"><span data-stu-id="73075-131">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="73075-132">**Namn**: Ange ett unikt, beskrivande namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="73075-132">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="73075-133">Klicka på **Fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="73075-133">Click **More Options**.</span></span>

   - <span data-ttu-id="73075-134">**Använd den här regeln om:** Konfigurera någon av följande inställningar för att söka efter innehåll i meddelanden med reguljära uttryck (RegEx) eller ord eller fraser:</span><span class="sxs-lookup"><span data-stu-id="73075-134">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="73075-135">**Ämnet eller kroppen** \> **ämne eller brödtext matchar dessa textmönster**: Ange **ord eller fraser** som visas, ange ett av följande värden, klicka på Lägg **till** ikonen och upprepa ![ ](../../media/ITPro-EAC-AddIcon.png) tills du har angett alla värden.</span><span class="sxs-lookup"><span data-stu-id="73075-135">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="73075-136">Om du vill redigera en post markerar du den och klickar på **Ikonen Redigera** ![ redigering ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="73075-136">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="73075-137">Om du vill ta bort en post markerar du den och klickar på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="73075-137">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="73075-138">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="73075-138">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="73075-139">**Ämnet eller kroppen** \> **ämne eller brödtext innehåller något av dessa ord**: Ange ord eller **fraser** som visas anger du ett av följande värden, klickar på **Lägg till** ![ ikon och upprepar ](../../media/ITPro-EAC-AddIcon.png) tills du har angett alla värden.</span><span class="sxs-lookup"><span data-stu-id="73075-139">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="73075-140">Om du vill redigera en post markerar du den och klickar på **Ikonen Redigera** ![ redigering ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="73075-140">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="73075-141">Om du vill ta bort en post markerar du den och klickar på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="73075-141">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="73075-142">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="73075-142">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="73075-143">**Gör följande:** Välj **Ändra meddelandeegenskaperna** \> **ange scl (Spam Confidence Level)**.</span><span class="sxs-lookup"><span data-stu-id="73075-143">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="73075-144">Konfigurera någon av följande inställningar i dialogrutan **Ange SCL:**</span><span class="sxs-lookup"><span data-stu-id="73075-144">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="73075-145">Om du vill markera meddelanden som **skräppost**väljer du **6**.</span><span class="sxs-lookup"><span data-stu-id="73075-145">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="73075-146">Åtgärden som du har konfigurerat för skräppostfiltreringsutslag i dina anti-spam-principer tillämpas på meddelandena (standardvärdet är **Flytta meddelande till mappen Skräppost**). **Spam**</span><span class="sxs-lookup"><span data-stu-id="73075-146">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="73075-147">Om du vill markera meddelanden som **skräppost med högt förtroende** väljer du **9**.</span><span class="sxs-lookup"><span data-stu-id="73075-147">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="73075-148">Åtgärden som du har konfigurerat för skräppostfiltreringsdomar med **högt förtroende** i dina anti-spam-principer tillämpas på meddelandena (standardvärdet är **Flytta meddelande till mappen Skräppost**).</span><span class="sxs-lookup"><span data-stu-id="73075-148">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="73075-149">Mer information om SCL-värden finns i [SCL (Spam Confidence Level) i EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="73075-149">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="73075-150">När du är klar klickar du på **Spara**</span><span class="sxs-lookup"><span data-stu-id="73075-150">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="73075-151">Använda PowerShell för att skapa regler för e-postflöde som filtrerar massutskick av e-post</span><span class="sxs-lookup"><span data-stu-id="73075-151">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="73075-152">Använd följande syntax för att skapa en eller båda av reglerna för e-postflöde (reguljära uttryck kontra ord):</span><span class="sxs-lookup"><span data-stu-id="73075-152">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="73075-153">I det här exemplet skapas en ny regel med namnet "Massfiltrering av e-post - RegEx" som använder samma lista med reguljära uttryck från tidigare i avsnittet för att ange meddelanden som **skräppost**.</span><span class="sxs-lookup"><span data-stu-id="73075-153">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="73075-154">Det här exemplet skapar en ny regel med namnet "Mass-e-filtrering - Ord" som använder samma lista med ord från tidigare i avsnittet för att ange meddelanden som **skräppost med högt förtroende**.</span><span class="sxs-lookup"><span data-stu-id="73075-154">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="73075-155">Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="73075-155">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="73075-156">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="73075-156">How do you know this worked?</span></span>

<span data-ttu-id="73075-157">Så här kontrollerar du att du har konfigurerat regler för e-postflöde för att filtrera massutskick av e-post:</span><span class="sxs-lookup"><span data-stu-id="73075-157">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="73075-158">Gå till **EAC-regler** för att skicka till \> **E-postflödesregler** \> och markera regeln klicka på \> **Redigera** ![ redigera ikon och kontrollera ](../../media/ITPro-EAC-EditIcon.png) inställningarna.</span><span class="sxs-lookup"><span data-stu-id="73075-158">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="73075-159">I PowerShell ersätter du \< Regelnamn \> med namnet på regeln och kör följande kommando för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="73075-159">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="73075-160">Från ett externt konto skickar du ett testmeddelanden till en berörd mottagare som innehåller en av fraserna eller textmönstren och verifierar resultaten.</span><span class="sxs-lookup"><span data-stu-id="73075-160">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
