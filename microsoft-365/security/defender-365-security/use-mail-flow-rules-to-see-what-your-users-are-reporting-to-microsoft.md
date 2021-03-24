---
title: Använd regler för e-postflöde för att se vad dina användare rapporterar till Microsoft
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
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att använda e-postflödesregler (kallas även transportregler) för att ta emot kopior av meddelanden som användare rapporterar till Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e6428a228ae64562f0b529f6aa90ddc3be46fdc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069937"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="62678-103">Använd regler för e-postflöde för att se vad dina användare rapporterar till Microsoft</span><span class="sxs-lookup"><span data-stu-id="62678-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="62678-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="62678-104">**Applies to**</span></span>
- [<span data-ttu-id="62678-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="62678-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="62678-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="62678-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="62678-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62678-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="62678-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor finns det flera sätt för användare att rapportera meddelanden till Microsoft för analys enligt beskrivningen i Rapportera meddelanden och filer till [Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="62678-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="62678-109">Du kan skapa en e-postflödesregel (kallas även transportregel) som söker efter meddelanden som användare rapporterar till Microsoft, och du kan konfigurera mottagare av hemlig kopia av de här rapporterade meddelandena.</span><span class="sxs-lookup"><span data-stu-id="62678-109">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="62678-110">Du kan skapa e-postflödesregeln i administrationscentret för Exchange (EAC) och PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="62678-110">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="62678-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="62678-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="62678-112">Du måste ha tilldelats behörigheter i Exchange Online eller Exchange Online Protection innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="62678-112">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="62678-113">Specifikt behöver du rollen **Transportregler,** som är tilldelad rollgrupperna **Organisationshantering,**  Efterlevnadshantering (globala administratörer) och **Hantering** av arkivhandlingar som standard.</span><span class="sxs-lookup"><span data-stu-id="62678-113">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="62678-114">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="62678-114">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="62678-115">Behörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="62678-115">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="62678-116">Behörigheter i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="62678-116">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="62678-117">Använd EAC för att ändra listan över medlemmar i rollgrupper</span><span class="sxs-lookup"><span data-stu-id="62678-117">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="62678-118">Information om hur du öppnar EAC i Exchange Online finns i [Administrationscenter för Exchange i Exchange Online.](/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="62678-118">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="62678-119">Information om hur du öppnar EAC i fristående EOP finns i [Administrationscenter för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="62678-119">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="62678-120">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="62678-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="62678-121">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="62678-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="62678-122">Mer information om e-postflödesregler i Exchange Online och fristående EOP finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="62678-122">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="62678-123">E-postflödesregler (transportregler) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="62678-123">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="62678-124">Villkor och undantag för e-postflödesregel (predikat) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="62678-124">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="62678-125">Åtgärder för e-postflödesregel i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="62678-125">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="62678-126">Använda EAC för att skapa en e-postflödesregel för att ta emot kopior av rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="62678-126">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="62678-127">Gå till E-postflödesregler **i** \> EAC.</span><span class="sxs-lookup"><span data-stu-id="62678-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="62678-128">Klicka **på ikonen** Lägg till lägg till och välj sedan Skapa en ny ![ ](../../media/ITPro-EAC-AddIcon.png) **regel.**</span><span class="sxs-lookup"><span data-stu-id="62678-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="62678-129">På sidan **Ny regel** som öppnas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62678-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="62678-130">**Namn**: Ange ett unikt, beskrivande namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="62678-130">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="62678-131">Till exempel har Hemlig kopia av meddelanden rapporterats till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="62678-131">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="62678-132">Klicka **på Fler alternativ.**</span><span class="sxs-lookup"><span data-stu-id="62678-132">Click **More Options**.</span></span>

   - <span data-ttu-id="62678-133">Använd den här  regeln **om:** Välj Mottagaradressen innehåller något av följande ord: I dialogrutan Ange ord eller fraser som visas anger du något av följande värden, klickar på Lägg till ikon och upprepar \>  **tills** du har angett alla  ![ ](../../media/ITPro-EAC-AddIcon.png) värden.</span><span class="sxs-lookup"><span data-stu-id="62678-133">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     <span data-ttu-id="62678-134">Om du vill redigera en post markerar du den och klickar **på Redigera** ![ redigeringsikon ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="62678-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="62678-135">Om du vill ta bort en post markerar du den och klickar på **ta** ![ bort-ikonen ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="62678-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="62678-136">När du är klar klickar du på **OK.**</span><span class="sxs-lookup"><span data-stu-id="62678-136">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="62678-137">**Gör så här:** Välj **Lägg till** \> **mottagare i rutan Hemlig kopia.**</span><span class="sxs-lookup"><span data-stu-id="62678-137">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="62678-138">I dialogrutan som visas går du till och väljer de mottagare som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="62678-138">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="62678-139">När du är klar klickar du på **OK.**</span><span class="sxs-lookup"><span data-stu-id="62678-139">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="62678-140">Du kan göra ytterligare val för att granska regeln, testa regeln, aktivera regeln under en viss tidsperiod och andra inställningar.</span><span class="sxs-lookup"><span data-stu-id="62678-140">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="62678-141">Vi rekommenderar att du testar regeln innan du tillämpar den.</span><span class="sxs-lookup"><span data-stu-id="62678-141">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="62678-142">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="62678-142">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="62678-143">Använda PowerShell för att skapa en e-postflödesregel för att ta emot kopior av rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="62678-143">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="62678-144">I det här exemplet skapas en ny e-postflödesregel med namnet Hemlig kopia av meddelanden som rapporterats till Microsoft och som söker efter e-postmeddelanden som rapporteras till Microsoft med de metoder som beskrivs i den här artikeln, och lägger till användarna laura@contoso.com och julia@contoso.com som mottagare av hemlig kopia.</span><span class="sxs-lookup"><span data-stu-id="62678-144">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="62678-145">Detaljerad information om syntax och parametrar finns i [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="62678-145">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="62678-146">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="62678-146">How do you know this worked?</span></span>

<span data-ttu-id="62678-147">För att verifiera att du har konfigurerat en e-postflödesregler för att ta emot kopior av rapporterade meddelanden gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="62678-147">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="62678-148">I EAC går du till **E-postflödesregler** \>  \> väljer regeln och \> klickar på **Redigera** ![ ](../../media/ITPro-EAC-EditIcon.png) redigeringsikon och kontrollerar inställningarna.</span><span class="sxs-lookup"><span data-stu-id="62678-148">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="62678-149">Kör följande kommando i PowerShell för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="62678-149">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="62678-150">Skicka ett testmeddelande till en av de rapporterande e-postadresserna och verifiera resultatet.</span><span class="sxs-lookup"><span data-stu-id="62678-150">Send a test messages to one of the reporting email addresses and verify the results.</span></span>