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
ms.openlocfilehash: ec7145b68548bb5e1d6841387a18e86b74ec2a78
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751577"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="ea583-103">Använd regler för e-postflöde för att se vad dina användare rapporterar till Microsoft</span><span class="sxs-lookup"><span data-stu-id="ea583-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ea583-104">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor finns det flera sätt för användare att rapportera meddelanden till Microsoft för analys enligt beskrivningen i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ea583-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="ea583-105">Du kan skapa en regel för e-postflöde (kallas även för en transport regel) som letar efter meddelanden som användare rapporterar till Microsoft och du kan konfigurera mottagarnas mottagare för att få kopior av dessa rapporterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="ea583-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="ea583-106">Du kan skapa regeln för e-postflöden i administrations centret för Exchange (UK) och PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="ea583-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ea583-107">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="ea583-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ea583-108">Du måste tilldelas behörigheter i Exchange Online eller Exchange Online Protection innan du kan göra det i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ea583-108">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="ea583-109">För det specifika måste du ha rollen **Transport regel** , som är tilldelad till **organisations hantering**, **hantering av efterlevnad** (globala administratörer) och roll grupperna **Arkiv handlings hantering** som standard.</span><span class="sxs-lookup"><span data-stu-id="ea583-109">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="ea583-110">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="ea583-110">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="ea583-111">Behörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ea583-111">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="ea583-112">Behörigheter i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="ea583-112">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="ea583-113">Använda UK ändra listan över medlemmar i roll grupper</span><span class="sxs-lookup"><span data-stu-id="ea583-113">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="ea583-114">Om du vill öppna UK i Exchange Online läser du [administrations Center för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="ea583-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="ea583-115">Information om hur du öppnar UK i fristående EOP finns i [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="ea583-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="ea583-116">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ea583-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ea583-117">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="ea583-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ea583-118">Mer information om regler för e-postflöden i Exchange Online och fristående EOP finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="ea583-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="ea583-119">Regler för e-postflöde (transport regler) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ea583-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="ea583-120">Villkor och undantag för e-postflödes regel (predikat) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ea583-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="ea583-121">Åtgärder för e-postflödes regler i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ea583-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="ea583-122">Använd UK för att skapa en regel för e-postflöde för att ta emot kopior av rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="ea583-122">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="ea583-123">Gå till regler för **e-postflöde** i UK \> .</span><span class="sxs-lookup"><span data-stu-id="ea583-123">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="ea583-124">Klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) och välj sedan **skapa en ny regel**.</span><span class="sxs-lookup"><span data-stu-id="ea583-124">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="ea583-125">På sidan **ny regel** som öppnas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ea583-125">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="ea583-126">**Namn**: Ange ett unikt, beskrivande namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="ea583-126">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="ea583-127">Till exempel rapporteras hemliga kopior till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ea583-127">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="ea583-128">Klicka på **fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="ea583-128">Click **More Options**.</span></span>

   - <span data-ttu-id="ea583-129">**Använd den här regeln om**: Välj **mottagarens** \> **adress innehåller något av följande ord**: i dialog rutan **Ange ord eller fraser** som visas anger du ett av nedanstående värden, klickar på **Lägg** till ![ Lägg till ikonen ](../../media/ITPro-EAC-AddIcon.png) och upprepar tills du har angett alla värden.</span><span class="sxs-lookup"><span data-stu-id="ea583-129">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     <span data-ttu-id="ea583-130">Om du vill redigera en post markerar du den och klickar på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="ea583-130">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="ea583-131">För att ta bort en post markerar du den och klickar på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="ea583-131">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="ea583-132">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea583-132">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="ea583-133">**Gör följande**: Välj **Lägg till mottagare** \> **i rutan hemlig kopia**.</span><span class="sxs-lookup"><span data-stu-id="ea583-133">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="ea583-134">Leta upp och markera de mottagare som du vill lägga till i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="ea583-134">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="ea583-135">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea583-135">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="ea583-136">Du kan göra ytterligare val för att granska regeln, testa regeln, aktivera regeln under en viss tids period och andra inställningar.</span><span class="sxs-lookup"><span data-stu-id="ea583-136">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="ea583-137">Vi rekommenderar att du testar regeln innan du använder den.</span><span class="sxs-lookup"><span data-stu-id="ea583-137">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="ea583-138">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ea583-138">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="ea583-139">Använd PowerShell för att skapa en regel för e-postflöde för att ta emot kopior av rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="ea583-139">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="ea583-140">I det här exemplet skapas en ny e-postflödes regel med namnet hemlig kopia som rapporteras till Microsoft och som letar efter e-postmeddelanden som rapporteras till Microsoft med de metoder som beskrivs i den här artikeln och lägger till användarna laura@contoso.com och julia@contoso.com som mottagare av hemlig kopia.</span><span class="sxs-lookup"><span data-stu-id="ea583-140">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="ea583-141">Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="ea583-141">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ea583-142">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="ea583-142">How do you know this worked?</span></span>

<span data-ttu-id="ea583-143">Gör något av följande om du vill kontrol lera att du har konfigurerat ett regel för e-postflöde för att få kopior av rapporterade meddelanden:</span><span class="sxs-lookup"><span data-stu-id="ea583-143">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="ea583-144">Gå till regler för **e-postflöde** i UK och \>  \> Välj regeln \> Klicka på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) och kontrol lera inställningarna.</span><span class="sxs-lookup"><span data-stu-id="ea583-144">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="ea583-145">I PowerShell kör du följande kommando för att kontrol lera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="ea583-145">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="ea583-146">Skicka ett test meddelande till en av rapporterings-e-postadresser och bekräfta resultaten.</span><span class="sxs-lookup"><span data-stu-id="ea583-146">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
