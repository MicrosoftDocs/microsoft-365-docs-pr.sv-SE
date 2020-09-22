---
title: Använd regler för e-postflöde för att se vad dina användare rapporterar till Microsoft
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
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur de använder regler för e-postflöde (kallas även transport regler) för att ta emot kopior av meddelanden som användare rapporterar till Microsoft.
ms.openlocfilehash: 9798e808470a506da3d6dff65a5ea91934c1690d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195873"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="7f06f-103">Använd regler för e-postflöde för att se vad dina användare rapporterar till Microsoft</span><span class="sxs-lookup"><span data-stu-id="7f06f-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7f06f-104">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor finns det flera sätt för användare att rapportera meddelanden till Microsoft för analys enligt beskrivningen i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="7f06f-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="7f06f-105">Du kan skapa en regel för e-postflöde (kallas även för en transport regel) som letar efter meddelanden som användare rapporterar till Microsoft och du kan konfigurera mottagarnas mottagare för att få kopior av dessa rapporterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="7f06f-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="7f06f-106">Du kan skapa regeln för e-postflöden i administrations centret för Exchange (UK) och PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="7f06f-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7f06f-107">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="7f06f-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7f06f-108">Du måste ha behörighet i Exchange Online eller EOP för att kunna göra detta.</span><span class="sxs-lookup"><span data-stu-id="7f06f-108">You need to be assigned permissions in Exchange Online or EOP before you can do these procedures.</span></span> <span data-ttu-id="7f06f-109">Specifikt måste du ha tilldelats rollen **transport regler** , som tilldelats rollerna **organisations hantering**, **regelefterlevnad**och hantering av **Arkiv handlingar** .</span><span class="sxs-lookup"><span data-stu-id="7f06f-109">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="7f06f-110">Mer information finns i [Hantera roll grupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="7f06f-110">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="7f06f-111">Om du vill öppna UK läser du [administrations Center för Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) eller [Exchange Admin Center i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="7f06f-111">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="7f06f-112">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7f06f-112">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="7f06f-113">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="7f06f-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7f06f-114">Mer information om regler för e-postflöden i Exchange Online och fristående EOP finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="7f06f-114">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="7f06f-115">Regler för e-postflöde (transport regler) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7f06f-115">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="7f06f-116">Villkor och undantag för e-postflödes regel (predikat) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7f06f-116">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="7f06f-117">Åtgärder för e-postflödes regler i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7f06f-117">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="7f06f-118">Använd UK för att skapa en regel för e-postflöde för att ta emot kopior av rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="7f06f-118">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="7f06f-119">Gå till regler för **e-postflöde** i UK \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="7f06f-119">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="7f06f-120">Klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) och välj sedan **skapa en ny regel**.</span><span class="sxs-lookup"><span data-stu-id="7f06f-120">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="7f06f-121">På sidan **ny regel** som öppnas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="7f06f-121">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="7f06f-122">**Namn**: Ange ett unikt, beskrivande namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="7f06f-122">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="7f06f-123">Till exempel rapporteras hemliga kopior till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f06f-123">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="7f06f-124">Klicka på **fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="7f06f-124">Click **More Options**.</span></span>

   - <span data-ttu-id="7f06f-125">**Använd den här regeln om**: Välj **mottagarens** \> **adress innehåller något av följande ord**: i dialog rutan **Ange ord eller fraser** som visas anger du ett av nedanstående värden, klickar på **Lägg** till ![ Lägg till ikonen ](../../media/ITPro-EAC-AddIcon.png) och upprepar tills du har angett alla värden.</span><span class="sxs-lookup"><span data-stu-id="7f06f-125">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="7f06f-126">Om du vill redigera en post markerar du den och klickar på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="7f06f-126">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="7f06f-127">För att ta bort en post markerar du den och klickar på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="7f06f-127">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="7f06f-128">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f06f-128">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="7f06f-129">**Gör följande**: Välj **Lägg till mottagare** \> **i rutan hemlig kopia**.</span><span class="sxs-lookup"><span data-stu-id="7f06f-129">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="7f06f-130">Leta upp och markera de mottagare som du vill lägga till i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="7f06f-130">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="7f06f-131">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f06f-131">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="7f06f-132">Du kan göra ytterligare val för att granska regeln, testa regeln, aktivera regeln under en viss tids period och andra inställningar.</span><span class="sxs-lookup"><span data-stu-id="7f06f-132">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="7f06f-133">Vi rekommenderar att du testar regeln innan du använder den.</span><span class="sxs-lookup"><span data-stu-id="7f06f-133">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="7f06f-134">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="7f06f-134">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="7f06f-135">Använd PowerShell för att skapa en regel för e-postflöde för att ta emot kopior av rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="7f06f-135">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="7f06f-136">I det här exemplet skapas en ny e-postflödes regel med namnet hemlig kopia som rapporteras till Microsoft och som letar efter e-postmeddelanden som rapporteras till Microsoft med de metoder som beskrivs i det här avsnittet och lägger till användarna laura@contoso.com och julia@contoso.com som mottagare av hemlig kopia.</span><span class="sxs-lookup"><span data-stu-id="7f06f-136">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="7f06f-137">Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="7f06f-137">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7f06f-138">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="7f06f-138">How do you know this worked?</span></span>

<span data-ttu-id="7f06f-139">Gör något av följande om du vill kontrol lera att du har konfigurerat ett regel för e-postflöde för att få kopior av rapporterade meddelanden:</span><span class="sxs-lookup"><span data-stu-id="7f06f-139">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="7f06f-140">Gå till regler för **e-postflöde** i UK och \> **Rules** \> Välj regeln \> Klicka på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) och kontrol lera inställningarna.</span><span class="sxs-lookup"><span data-stu-id="7f06f-140">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="7f06f-141">I PowerShell kör du följande kommando för att kontrol lera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="7f06f-141">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="7f06f-142">Skicka ett test meddelande till en av rapporterings-e-postadresser och bekräfta resultaten.</span><span class="sxs-lookup"><span data-stu-id="7f06f-142">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
