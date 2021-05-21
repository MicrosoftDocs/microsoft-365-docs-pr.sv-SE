---
title: Konfigurera leverans av nätfiskebedrägerier från tredje part till användare och ofiltrerade meddelanden till SecOps-postlådor
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Administratörer kan lära sig att använda den avancerade leveransprincipen i Exchange Online Protection (EOP) för att identifiera meddelanden som inte ska filtreras i specifika scenarier som stöds (nätfiskebedrägerier från tredje part och meddelanden som levereras till säkerhetsåtgärder (SecOps)-postlådor.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bebc094b56a20a43f92d1acf8d374110de43d71
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594127"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="4115d-103">Konfigurera leverans av nätfiskebedrägerier från tredje part till användare och ofiltrerade meddelanden till SecOps-postlådor</span><span class="sxs-lookup"><span data-stu-id="4115d-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="4115d-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="4115d-104">**Applies to**</span></span>
- [<span data-ttu-id="4115d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4115d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4115d-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="4115d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4115d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4115d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="4115d-108">Funktionen som beskrivs i den här artikeln är i förhandsversion, är inte tillgänglig för alla och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="4115d-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="4115d-109">För att [](secure-by-default.md)hålla organisationen säker som standard tillåter Exchange Online Protection (EOP) inte säkra listor eller filtrering av förbikoppling för meddelanden som resulterar i skadlig kod eller nätfiskeförsök med hög konfidens.</span><span class="sxs-lookup"><span data-stu-id="4115d-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that result in malware or high confidence phishing verdicts.</span></span> <span data-ttu-id="4115d-110">Men det finns särskilda scenarier som kräver leverans av ofiltrerade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4115d-110">But there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="4115d-111">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="4115d-111">For example:</span></span>

- <span data-ttu-id="4115d-112">**Nätfiskebedrägerier från tredje** part : Simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar din organisation.</span><span class="sxs-lookup"><span data-stu-id="4115d-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="4115d-113">**Säkerhetsåtgärder (SecOps)-postlådor:** Dedikerade postlådor som används av säkerhetsteam för att samla in och analysera ofiltrerade meddelanden (både bra och dåliga).</span><span class="sxs-lookup"><span data-stu-id="4115d-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="4115d-114">Du använder principen _för avancerad leverans i_ Microsoft 365 för att förhindra att dessa meddelanden i dessa specifika _scenarier_ <sup>\*</sup> filtreras.</span><span class="sxs-lookup"><span data-stu-id="4115d-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered<sup>\*</sup>.</span></span> <span data-ttu-id="4115d-115">Med principen för avancerad leverans säkerställs att meddelanden i följande scenarier inte filtreras:</span><span class="sxs-lookup"><span data-stu-id="4115d-115">The advanced delivery policy ensures that messages in these scenarios are not filtered:</span></span>

- <span data-ttu-id="4115d-116">Filter i EOP och Microsoft Defender för Office 365 inga åtgärder vidtas på dessa meddelanden.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4115d-116">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="4115d-117">[ZAP (Zero-hour Purge)](zero-hour-auto-purge.md) för skräppost och nätfiske vidtar ingen åtgärd för dessa meddelanden.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4115d-117">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing takes no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="4115d-118">[Standardsystemaviseringar](alerts.md) utlöses inte för dessa scenarier.</span><span class="sxs-lookup"><span data-stu-id="4115d-118">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="4115d-119">[AIR och clustering i Defender för Office 365](office-365-air.md) ignorerar dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4115d-119">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="4115d-120">Särskilt för nätfiskebedrägerier från tredje part:</span><span class="sxs-lookup"><span data-stu-id="4115d-120">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="4115d-121">[Administratörsinskick](admin-submission.md) genererar ett automatiskt svar som säger att meddelandet är en del av en phishing-simuleringskampanj och inte är ett riktigt hot.</span><span class="sxs-lookup"><span data-stu-id="4115d-121">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="4115d-122">Aviseringar och AIR utlöses inte.</span><span class="sxs-lookup"><span data-stu-id="4115d-122">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="4115d-123">[Valv i Defender för Office 365](safe-links.md) blockeras eller avaktiverar inte de specifikt identifierade webbadresserna i dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4115d-123">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="4115d-124">[Valv i Defender för Office 365](safe-attachments.md) avaktiverar inte bifogade filer i dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4115d-124">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="4115d-125"><sup>\*</sup> Du kan inte kringgå filtrering av skadlig programvara eller ZAP för skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="4115d-125"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="4115d-126">Meddelanden som identifieras av den avancerade leveranspolicyn är inte säkerhetshot, så meddelandena markeras som system åsidosätter.</span><span class="sxs-lookup"><span data-stu-id="4115d-126">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="4115d-127">Administratörer kan filtrera och analysera dessa system åsidosättningar i följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="4115d-127">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="4115d-128">Hotutforskaren/identifieringar i realtid i Defender för Office 365 abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="4115d-128">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="4115d-129">Sidan [E-post entitet i Hotutforskaren/realtidsidentifiering](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="4115d-129">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="4115d-130">Statusrapport [för skydd mot hot](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="4115d-130">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="4115d-131">Avancerad sökning i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="4115d-131">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="4115d-132">Kampanjvyer</span><span class="sxs-lookup"><span data-stu-id="4115d-132">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4115d-133">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="4115d-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4115d-134">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="4115d-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4115d-135">Gå direkt till sidan **Avancerad leverans** genom att öppna <https://protection.office.com/advanceddelivery> .</span><span class="sxs-lookup"><span data-stu-id="4115d-135">To go directly to the **Advanced delivery** page, open <https://protection.office.com/advanceddelivery>.</span></span>

- <span data-ttu-id="4115d-136">Du måste ha tilldelats behörigheter innan du kan utföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="4115d-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4115d-137">Om du vill skapa, ändra eller ta bort konfigurerade inställningar i  den avancerade leveransprincipen måste du vara medlem i  rollgruppen Säkerhetsadministratör i Säkerhets- och efterlevnadscenter **för &** och medlem i rollgruppen Organisationshantering i **Exchange Online.**</span><span class="sxs-lookup"><span data-stu-id="4115d-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Security & Compliance Center** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>  
  - <span data-ttu-id="4115d-138">För skrivskyddade åtkomst till avancerade leveransprinciper måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="4115d-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="4115d-139">Mer information finns i [Behörigheter i Säkerhets- & säkerhets- och](permissions-in-the-security-and-compliance-center.md) [behörighetscenter i Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="4115d-139">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="4115d-140">Använd Säkerhets- & efterlevnadscenter för att konfigurera nätfiskebedrägerier från tredje part i den avancerade leveranspolicyn</span><span class="sxs-lookup"><span data-stu-id="4115d-140">Use the Security & Compliance Center to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="4115d-141">I Säkerhets- & säkerhets- och efterlevnadscenter går du **till Avancerad leverans av** \>  \> **hothanteringspolicy.**</span><span class="sxs-lookup"><span data-stu-id="4115d-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="4115d-142">På sidan **Avancerad leverans** väljer du fliken Phishing **simulering** och klickar sedan på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="4115d-142">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then click **Edit**.</span></span>

3. <span data-ttu-id="4115d-143">Konfigurera följande **inställningar på den utfällbaserade** utfällningen av nätfiske från tredje part som öppnas:</span><span class="sxs-lookup"><span data-stu-id="4115d-143">On the **Third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="4115d-144">**Skicka domän:** Minst en e-postadressdomän krävs (till exempel contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4115d-144">**Sending domain**: At least one email address domain is required (for example, contoso.com).</span></span> <span data-ttu-id="4115d-145">Du kan lägga till upp till 10 poster.</span><span class="sxs-lookup"><span data-stu-id="4115d-145">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="4115d-146">**Skicka IP:** Minst en giltig IPv4-adress krävs.</span><span class="sxs-lookup"><span data-stu-id="4115d-146">**Sending IP**: At least one valid IPv4 address is required.</span></span> <span data-ttu-id="4115d-147">Du kan lägga till upp till 10 poster.</span><span class="sxs-lookup"><span data-stu-id="4115d-147">You can add up to 10 entries.</span></span> <span data-ttu-id="4115d-148">Giltiga värden är:</span><span class="sxs-lookup"><span data-stu-id="4115d-148">Valid values are:</span></span>
     - <span data-ttu-id="4115d-149">Enskild IP: Till exempel 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="4115d-149">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="4115d-150">IP-intervall: Till exempel 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="4115d-150">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="4115d-151">CIDR IP: Till exempel 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="4115d-151">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="4115d-152">**Simulerings-URL:er som** ska tillåtas : Du kan också ange specifika URL:er som är en del av din nätfiskekampanj som inte ska blockeras eller detoneras.</span><span class="sxs-lookup"><span data-stu-id="4115d-152">**Simulation URLs to allow**: Optionally, enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated.</span></span> <span data-ttu-id="4115d-153">Du kan lägga till upp till 10 poster.</span><span class="sxs-lookup"><span data-stu-id="4115d-153">You can add up to 10 entries.</span></span>

4. <span data-ttu-id="4115d-154">Klicka på Spara när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="4115d-154">When you're finished, click **Save.**</span></span>

<span data-ttu-id="4115d-155">De simuleringsposter för nätfiske från tredje part som du har konfigurerat visas på fliken **Nätfiskebedrägerier.** Om du vill göra ändringar **klickar du** på Redigera på fliken.</span><span class="sxs-lookup"><span data-stu-id="4115d-155">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click **Edit** on the tab.</span></span>

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="4115d-156">Använd Säkerhets- & kompatibilitetscenter för att konfigurera SecOps-postlådor i den avancerade leveranspolicyn</span><span class="sxs-lookup"><span data-stu-id="4115d-156">Use the Security & Compliance Center to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="4115d-157">I Säkerhets- & efterlevnadscenter går du till **Avancerad leverans av** \>  \> **hothanteringspolicy.**</span><span class="sxs-lookup"><span data-stu-id="4115d-157">In the Security & Compliance Center, go to **Threat Management** \> **Policy** \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="4115d-158">På sidan **Advanced delivery** väljer du fliken **SecOps mailbox** och klickar sedan på **Edit**.</span><span class="sxs-lookup"><span data-stu-id="4115d-158">On the **Advanced delivery** page, select the **SecOps mailbox** tab, and then click **Edit**.</span></span>

3. <span data-ttu-id="4115d-159">I den **utfällklienten** för SecOps-postlådan som öppnas anger du e-postadresserna för Exchange Online postlådor som du vill ange som SecOps-postlådor.</span><span class="sxs-lookup"><span data-stu-id="4115d-159">On the **SecOps mailbox** flyout that opens, enter the email addresses of existing Exchange Online mailboxes that you want to designate as SecOps mailboxes.</span></span> <span data-ttu-id="4115d-160">Distributionsgrupper tillåts inte.</span><span class="sxs-lookup"><span data-stu-id="4115d-160">Distribution groups are not allowed.</span></span>

4. <span data-ttu-id="4115d-161">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="4115d-161">When you're finished, click **Save**.</span></span>

<span data-ttu-id="4115d-162">Postlådepostlådorna för SecOps som du har konfigurerat visas på **fliken SecOps-postlåda.** Om du vill göra ändringar **klickar du** på Redigera på fliken.</span><span class="sxs-lookup"><span data-stu-id="4115d-162">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="4115d-163">Ytterligare scenarier som kräver förbikoppling av filtrering</span><span class="sxs-lookup"><span data-stu-id="4115d-163">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="4115d-164">Utöver de två scenarier som den avancerade leveransprincipen kan hjälpa dig med finns det andra scenarier som kan innebära att du måste kringgå filtrering:</span><span class="sxs-lookup"><span data-stu-id="4115d-164">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="4115d-165">**Filter från tredje part:** Om domänens MX-post inte pekar på Office 365 (meddelanden dirigeras någon annanstans [först)](secure-by-default.md) är säker som standard *inte tillgänglig.* </span><span class="sxs-lookup"><span data-stu-id="4115d-165">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span>

  <span data-ttu-id="4115d-166">Om du vill kringgå Microsoft-filtrering för meddelanden som redan har utvärderats av filtrering från tredje part använder du e-postflödesregler (kallas även transportregler) i Använda e-postflödesregler för att ange SCL i [meddelanden.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="4115d-166">To bypass Microsoft filtering for messages that have already been evaluated by third-party filtering, use mail flow rules (also known as transport rules), see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

- <span data-ttu-id="4115d-167">**Falska** positiva resultat under granskning: Du kanske tillfälligt vill tillåta att vissa meddelanden som fortfarande analyseras av Microsoft via administratörer rapporterar kända bra meddelanden som felaktigt [markeras](admin-submission.md) som dåliga för Microsoft (falska positiva resultat).</span><span class="sxs-lookup"><span data-stu-id="4115d-167">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="4115d-168">Precis som med alla åsidosättningar **_rekommenderar vi starkt_** att dessa tillägg görs tillfälligt.</span><span class="sxs-lookup"><span data-stu-id="4115d-168">As with all overrides, it is **_highly recommended_** that these allowances be made temporarily.</span></span>
