---
title: Filtrera Mass utskick via e-post
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur de använder regler för e-postflöde (transport regler) för att identifiera och filtrera Mass utskick (grå e-post) i Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfe841d3e80efc50d6ffbc702faefa1c9a971b13
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826759"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="ece80-103">Använda e-postflödesregler för att filtrera massutskick i EOP</span><span class="sxs-lookup"><span data-stu-id="ece80-103">Use mail flow rules to filter bulk email in EOP</span></span>

<span data-ttu-id="ece80-104">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor används principer för skräp post filtrering (kallas även för skräp post filter principer eller innehålls filter principer) för att söka igenom inkommande meddelanden för spam och Mass utskick (kallas även gråskala).</span><span class="sxs-lookup"><span data-stu-id="ece80-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="ece80-105">Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ece80-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="ece80-106">Om du vill ha fler alternativ för att filtrera Mass utskick kan du skapa regler för e-postflöde (kallas även transport regler) för att söka efter text mönster eller fraser som ofta hittas i Mass utskick och markera dessa meddelanden som skräp post.</span><span class="sxs-lookup"><span data-stu-id="ece80-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="ece80-107">Mer information om Mass utskick finns i [Vad är skillnaden mellan skräp post och Mass utskick?](what-s-the-difference-between-junk-email-and-bulk-email.md) och bulk- [nivå (BCL) i EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="ece80-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="ece80-108">I det här avsnittet förklaras hur du skapar dessa regler för e-post i administrations centret för Exchange (UK) och PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="ece80-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ece80-109">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="ece80-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ece80-110">Du måste tilldelas behörigheter innan du kan göra följande:</span><span class="sxs-lookup"><span data-stu-id="ece80-110">You need to be assigned permissions before you can do these procedures:</span></span>

  - <span data-ttu-id="ece80-111">I Exchange Online kan du läsa "mail flöde"-posten i [funktioner i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span><span class="sxs-lookup"><span data-stu-id="ece80-111">In Exchange Online, see the "Mail flow" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span></span>
  
  - <span data-ttu-id="ece80-112">I fristående EOP behöver du Transport regel rollen som är tilldelad till rollerna i, ComplianceManagement och RecordsManagement som standard.</span><span class="sxs-lookup"><span data-stu-id="ece80-112">In standalone EOP, you need the Transport Rules role, which is assigned to the OrganizationManagement, ComplianceManagement, and RecordsManagement roles by default.</span></span> <span data-ttu-id="ece80-113">Mer information finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd UK för att ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="ece80-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="ece80-114">Om du vill öppna UK i Exchange Online läser du [administrations Center för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="ece80-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="ece80-115">Information om hur du öppnar UK i fristående EOP finns i [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="ece80-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="ece80-116">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ece80-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ece80-117">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="ece80-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ece80-118">Mer information om regler för e-postflöden i Exchange Online och fristående EOP finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="ece80-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="ece80-119">Regler för e-postflöde (transport regler) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ece80-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="ece80-120">Villkor och undantag för e-postflödes regel (predikat) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ece80-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="ece80-121">Åtgärder för e-postflödes regler i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ece80-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="ece80-122">Listan med ord och text mönster som används för att identifiera Mass utskick i de här exemplen är inte uttömmande; Du kan lägga till och ta bort poster vid behov.</span><span class="sxs-lookup"><span data-stu-id="ece80-122">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="ece80-123">Men de är en bra start punkt.</span><span class="sxs-lookup"><span data-stu-id="ece80-123">However, they are a good starting point.</span></span>

- <span data-ttu-id="ece80-124">Sök efter ord eller text mönster i ämnes raden ämne eller andra rubrik fält i meddelandet inträffar *när* meddelandet har avkodats från den kodnings metod för MIME-innehålls överföring som användes för att överföra det binära meddelandet mellan SMTP-servrar i ASCII-text.</span><span class="sxs-lookup"><span data-stu-id="ece80-124">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text.</span></span> <span data-ttu-id="ece80-125">Du kan inte använda villkor eller undantag för att söka efter råa (vanligt vis base64) kodade värden för ämne eller andra huvud fält i meddelanden.</span><span class="sxs-lookup"><span data-stu-id="ece80-125">You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="ece80-126">Här beskrivs ett Mass meddelande som skräp post för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="ece80-126">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="ece80-127">Du kan emellertid bara lägga till ett annat villkor för att tillämpa dessa regler på specifika mottagare, så att du kan använda aggressiv filtrering på några få, ytterst riktade användare, medan resten av dina användare (som mest får det Mass utskick som de har registrerat sig för) inte påverkas.</span><span class="sxs-lookup"><span data-stu-id="ece80-127">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="ece80-128">Använd UK för att skapa regler för e-postflöde som filtrerar Mass utskick</span><span class="sxs-lookup"><span data-stu-id="ece80-128">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="ece80-129">Gå till regler för **e-postflöde** i UK \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="ece80-129">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="ece80-130">Klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) och välj sedan **skapa en ny regel**.</span><span class="sxs-lookup"><span data-stu-id="ece80-130">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="ece80-131">På sidan **ny regel** som öppnas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ece80-131">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="ece80-132">**Namn**: Ange ett unikt, beskrivande namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="ece80-132">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="ece80-133">Klicka på **fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="ece80-133">Click **More Options**.</span></span>

   - <span data-ttu-id="ece80-134">**Använd den här regeln om**: Konfigurera en av följande inställningar för att söka efter innehåll i meddelanden med hjälp av reguljära uttryck (regex) eller ord eller fraser:</span><span class="sxs-lookup"><span data-stu-id="ece80-134">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="ece80-135">**Ämne eller brödtext** \> **ämne eller brödtext matchar dessa text mönster**: ange något av följande värden i dialog rutan **Ange ord eller fraser** , klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) och upprepa tills du har angett alla värden.</span><span class="sxs-lookup"><span data-stu-id="ece80-135">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="ece80-136">Om du vill redigera en post markerar du den och klickar på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="ece80-136">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="ece80-137">För att ta bort en post markerar du den och klickar på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="ece80-137">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="ece80-138">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ece80-138">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="ece80-139">**Ämne eller brödtext** \> **ämne eller brödtext inkluderar något av**följande: i dialog rutan **Ange ord eller fraser** som visas anger du ett av nedanstående värden, klickar på **Lägg** till ![ Lägg till ikonen ](../../media/ITPro-EAC-AddIcon.png) och upprepar tills du har angett alla värden.</span><span class="sxs-lookup"><span data-stu-id="ece80-139">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="ece80-140">Om du vill redigera en post markerar du den och klickar på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="ece80-140">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="ece80-141">För att ta bort en post markerar du den och klickar på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="ece80-141">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="ece80-142">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ece80-142">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="ece80-143">**Gör följande**: Välj **ändra meddelande egenskaper** \> **ange nivån för skräp post (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="ece80-143">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="ece80-144">I dialog rutan **Ange SCL** som visas konfigurerar du en av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ece80-144">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="ece80-145">Om du vill markera meddelanden som **skräp post**väljer du **6**.</span><span class="sxs-lookup"><span data-stu-id="ece80-145">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="ece80-146">Den åtgärd som du har konfigurerat för **skräp post** filtrering verdicts i policyn för skräp post hantering tillämpas på meddelandena (standardvärdet **flyttas till mappen skräp post**).</span><span class="sxs-lookup"><span data-stu-id="ece80-146">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="ece80-147">Om du vill markera meddelanden som **skräp post** väljer du **9**.</span><span class="sxs-lookup"><span data-stu-id="ece80-147">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="ece80-148">Den åtgärd som du har konfigurerat för filtrering av skräp post med **hög exakthet** verdicts i dina meddelanden (standardvärdet **flyttas till mappen skräp post**).</span><span class="sxs-lookup"><span data-stu-id="ece80-148">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="ece80-149">Mer information om SCL-värden finns i [säkerhet för skräp post (SCL) i EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ece80-149">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="ece80-150">När du är klar klickar du på **Spara**</span><span class="sxs-lookup"><span data-stu-id="ece80-150">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="ece80-151">Använda PowerShell för att skapa e-postflödes regler som filtrerar Mass utskick</span><span class="sxs-lookup"><span data-stu-id="ece80-151">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="ece80-152">Använd följande syntax för att skapa en eller båda regler för e-postflöden (vanliga uttryck jämfört med ord):</span><span class="sxs-lookup"><span data-stu-id="ece80-152">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="ece80-153">I det här exemplet skapas en ny regel med namnet "Mass utskick av e-post-RegEx" som använder samma lista med vanliga uttryck från tidigare i avsnittet för att ange meddelanden som **skräp post**.</span><span class="sxs-lookup"><span data-stu-id="ece80-153">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="ece80-154">I det här exemplet skapas en ny regel med namnet "Mass utskick av e-post" som använder samma lista med ord från tidigare i avsnittet för att ange meddelanden som **skräp post**.</span><span class="sxs-lookup"><span data-stu-id="ece80-154">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="ece80-155">Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="ece80-155">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ece80-156">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="ece80-156">How do you know this worked?</span></span>

<span data-ttu-id="ece80-157">Gör något av följande om du vill kontrol lera att du har konfigurerat regler för e-postflöde för filtrering av Mass utskick:</span><span class="sxs-lookup"><span data-stu-id="ece80-157">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="ece80-158">Gå till regler för **e-postflöde** i UK och \> **Rules** \> Välj regeln \> Klicka på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) och kontrol lera inställningarna.</span><span class="sxs-lookup"><span data-stu-id="ece80-158">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="ece80-159">Ersätt \<Rule Name\> med regel namnet i PowerShell och kör följande kommando för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="ece80-159">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="ece80-160">Från ett externt konto kan du skicka ett test meddelande till en mottagare som innehåller en av fraserna eller text mönstren och bekräfta resultaten.</span><span class="sxs-lookup"><span data-stu-id="ece80-160">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
