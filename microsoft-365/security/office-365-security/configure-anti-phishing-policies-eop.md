---
title: Konfigurera standardprincipen mot nätfiske i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du ändrar de inställningar mot förfalskning som är tillgängliga i standardpolicyn mot nätfiske i Office 365-organisationer med Exchange Online-postlådor.
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537539"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a><span data-ttu-id="6a6d9-103">Konfigurera standardprincipen mot nätfiske i EOP</span><span class="sxs-lookup"><span data-stu-id="6a6d9-103">Configure the default anti-phishing policy in EOP</span></span>

<span data-ttu-id="6a6d9-104">Office 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor har en standardprincip mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have a default anti-phishing policy.</span></span> <span data-ttu-id="6a6d9-105">Den här principen innehåller ett begränsat antal anti-spoofing-funktioner som är aktiverade som standard.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-105">This policy contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="6a6d9-106">Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="6a6d9-106">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="6a6d9-107">Office 365-organisationer med Exchange Online-postlådor kan ändra standardprincipen mot nätfiske i Office 365 Security & Compliance Center eller Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-107">Office 365 organizations with Exchange Online mailboxes can modify the default anti-phishing policy in the Office 365 Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="6a6d9-108">Fristående EOP-organisationer utan Exchange Online-postlådor kan inte ändra sin standardpolicy mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-108">Standalone EOP organizations without Exchange Online mailboxes can't modify their default anti-phishing policy.</span></span>

<span data-ttu-id="6a6d9-109">Information om hur du skapar och ändrar de mer avancerade ATP-principerna för nätfiske som är tillgängliga i Office 365 Advanced Threat Protection finns [i Konfigurera ATP-principer för nätfiske i Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6a6d9-109">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6a6d9-110">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="6a6d9-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6a6d9-111">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6a6d9-112">Om du vill gå direkt till <https://protection.office.com/antiphishing>sidan **Mot nätfiske** använder du .</span><span class="sxs-lookup"><span data-stu-id="6a6d9-112">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="6a6d9-113">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6a6d9-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="6a6d9-114">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="6a6d9-115">Om du vill lägga till, ändra och ta bort principer för nätfiske måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="6a6d9-115">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="6a6d9-116">För skrivskyddad åtkomst till anti-phishing-principer måste du vara medlem i rollgruppen **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="6a6d9-116">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="6a6d9-117">Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter för Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6a6d9-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="6a6d9-118">Våra rekommenderade inställningar för standardpolicyn mot nätfiske finns i [EOP:s standardinställningar för anti-nätfiske](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="6a6d9-118">For our recommended settings for the default anti-phishing policy, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="6a6d9-119">Tillåt upp till 30 minuter för den uppdaterade principen som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-119">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="6a6d9-120">Information om var principer mot nätfiske tillämpas i filtreringspipelinen finns [i Ordning och prioritet för e-postskydd i Office 365](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="6a6d9-120">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="6a6d9-121">Använd Security & Compliance Center för att ändra standardprincipen mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="6a6d9-121">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="6a6d9-122">Standardprincipen mot nätfiske heter Office365 AntiPhish Default och visas inte i listan över principer.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-122">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="6a6d9-123">Så här ändrar du standardpolicyn mot nätfiske:</span><span class="sxs-lookup"><span data-stu-id="6a6d9-123">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="6a6d9-124">Gå till **Policy** \> **Anti-phishing** **Threat management** \> i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="6a6d9-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="6a6d9-125">Klicka på **Standardprincip**på sidan **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="6a6d9-125">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="6a6d9-126">Sidan **Redigera din princip office365 AntiPhish Standard** visas.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-126">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="6a6d9-127">Klicka på **Redigera**i avsnittet **Spoof.**</span><span class="sxs-lookup"><span data-stu-id="6a6d9-127">In the **Spoof** section, click **Edit**.</span></span>

   <span data-ttu-id="6a6d9-128">Observera att dessa inställningar är identiska med de falska inställningar som är tillgängliga i ATP:s principer för phishing.Note that these settings are identical to the spoof settings that are available in ATP anti-phishing policies.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-128">Note that these settings are identical to the spoof settings that are available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="6a6d9-129">**Spoofing filterinställningar:** Standardvärdet är **På**, och vi rekommenderar att du lämnar den på.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-129">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="6a6d9-130">Om du vill inaktivera den drar du växlingsknappen till **Av**.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-130">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="6a6d9-131">Mer information finns [i Konfigurera falska underrättelser i Office 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="6a6d9-131">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="6a6d9-132">Du behöver inte inaktivera förfalskningsskydd om MX-posten inte pekar på Office 365. du aktiverar utökad filtrering för kopplingar i stället.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-132">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="6a6d9-133">Instruktioner finns i [Förbättrad filtrering för anslutningsappar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="6a6d9-133">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="6a6d9-134">**Aktivera funktionen Oautentiserade avsändare**: Lägger till ett frågetecken i avsändarens foto om meddelandet inte fungerar e-postautentisering.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-134">**Enable Unauthenticated Sender feature**: Adds a question mark to the sender's photo if the message fails email authentication checks.</span></span> <span data-ttu-id="6a6d9-135">Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="6a6d9-135">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span> <span data-ttu-id="6a6d9-136">Standardvärdet är **På**.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-136">The default value is **On**.</span></span> <span data-ttu-id="6a6d9-137">Om du vill inaktivera den drar du växlingsknappen till **Av**.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-137">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="6a6d9-138">**Åtgärder**: Ange vilken åtgärd som ska vidtas för meddelanden som inte innehåller falska underrättelser:</span><span class="sxs-lookup"><span data-stu-id="6a6d9-138">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="6a6d9-139">**Om e-post skickas av någon som inte får förfalska din domän:**</span><span class="sxs-lookup"><span data-stu-id="6a6d9-139">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="6a6d9-140">**Flytta meddelande till mottagarnas skräppostmappar** (Detta är standardvärdet.)</span><span class="sxs-lookup"><span data-stu-id="6a6d9-140">**Move message to the recipients' Junk Email folders** (This is the default value.)</span></span>
     - <span data-ttu-id="6a6d9-141">**Karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="6a6d9-141">**Quarantine the message**</span></span>

   - <span data-ttu-id="6a6d9-142">**Granska dina inställningar**: I stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-142">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="6a6d9-143">Du kan klicka på **Redigera** i varje avsnitt om du vill gå tillbaka till den aktuella sidan.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-143">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="6a6d9-144">Du kan växla följande inställningar **På** eller **Av** direkt på den här sidan:</span><span class="sxs-lookup"><span data-stu-id="6a6d9-144">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="6a6d9-145">**Aktivera skydd mot förfalskning**</span><span class="sxs-lookup"><span data-stu-id="6a6d9-145">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="6a6d9-146">**Aktivera funktionen Oautentiserad avsändare**</span><span class="sxs-lookup"><span data-stu-id="6a6d9-146">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="6a6d9-147">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-147">When you're finished, click **Save** on any page.</span></span>

4. <span data-ttu-id="6a6d9-148">Tillbaka på sidan **Redigera din princip Office365 AntiPhish Standard,** granska dina inställningar och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-148">Back on the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a><span data-ttu-id="6a6d9-149">Använda Security & Compliance Center för att visa standardprincipen mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="6a6d9-149">Use the Security & Compliance Center to view the default anti-phishing policy</span></span>

1. <span data-ttu-id="6a6d9-150">I Security & Compliance Center och gå till **Atp-anti-phishing-principen** **mot hothanteringspolicy** \> **Policy** \> .</span><span class="sxs-lookup"><span data-stu-id="6a6d9-150">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="6a6d9-151">Klicka på **Standardprincip** om du vill visa standardprincipen mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-151">Click **Default policy** to view the default anti-phishing policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a><span data-ttu-id="6a6d9-152">Använda Exchange Online PowerShell för att konfigurera standardprincipen mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="6a6d9-152">Use Exchange Online PowerShell to configure the default anti-phishing policy</span></span>

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a><span data-ttu-id="6a6d9-153">Använda PowerShell för att visa standardprincipen mot phish</span><span class="sxs-lookup"><span data-stu-id="6a6d9-153">Use PowerShell to view the default anti-phish policy</span></span>

<span data-ttu-id="6a6d9-154">Om du vill visa standardprincipen mot phish kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="6a6d9-154">To view the default anti-phish policy, run the following command:</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

<span data-ttu-id="6a6d9-155">Detaljerad syntax- och parameterinformation finns i [Hämta-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="6a6d9-155">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a><span data-ttu-id="6a6d9-156">Använda PowerShell för att ändra standardprincipen mot phish</span><span class="sxs-lookup"><span data-stu-id="6a6d9-156">Use PowerShell to modify the default anti-phish policy</span></span>

<span data-ttu-id="6a6d9-157">Om du vill ändra standardprincipen mot phish använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="6a6d9-157">To modify the default anti-phish policy, use the following syntax:</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="6a6d9-158">I det här exemplet ändras åtgärden för falska meddelanden som misslyckas med autentiseringskontroller till karantän.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-158">This example changes the action for spoofed messages that fail authentication checks to quarantine.</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="6a6d9-159">Detaljerad syntax- och parameterinformation finns i [Ange-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="6a6d9-159">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6a6d9-160">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="6a6d9-160">How do you know these procedures worked?</span></span>

<span data-ttu-id="6a6d9-161">Så här kontrollerar du att du har konfigurerat standardprincipen mot nätfiske:</span><span class="sxs-lookup"><span data-stu-id="6a6d9-161">To verify that you've successfully configured the default anti-phishing policy, do any of the following steps:</span></span>

- <span data-ttu-id="6a6d9-162">Gå till **Policy** \> **Anti-phishing-principen** \> mot **nätfiske** \> **i** Security & Compliance Center och visa information i det utfällbara utfällbara energiläget.</span><span class="sxs-lookup"><span data-stu-id="6a6d9-162">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="6a6d9-163">I Exchange Online PowerShell kör du följande kommando och verifierar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="6a6d9-163">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
