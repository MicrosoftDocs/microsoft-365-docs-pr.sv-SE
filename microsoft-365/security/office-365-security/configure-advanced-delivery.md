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
ms.openlocfilehash: 01d35c1f0c7abc7b6ce34fc9c2ec4d5fd5b228ae
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137745"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="f2ba9-103">Konfigurera leverans av nätfiskebedrägerier från tredje part till användare och ofiltrerade meddelanden till SecOps-postlådor</span><span class="sxs-lookup"><span data-stu-id="f2ba9-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="f2ba9-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="f2ba9-104">**Applies to**</span></span>
- [<span data-ttu-id="f2ba9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f2ba9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f2ba9-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="f2ba9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f2ba9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2ba9-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="f2ba9-108">Funktionen som beskrivs i den här artikeln är i förhandsversion, är inte tillgänglig för alla och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="f2ba9-109">För att hålla [organisationen](secure-by-default.md)säker som standard tillåter Exchange Online Protection (EOP) inte säkra listor eller filtreringsförkoppling för meddelanden som identifieras som skadlig kod eller nätfiske med hög konfidens.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="f2ba9-110">Men det finns särskilda scenarier som kräver leverans av ofiltrerade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="f2ba9-111">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-111">For example:</span></span>

- <span data-ttu-id="f2ba9-112">**Nätfiskebedrägerier från tredje** part : Simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar din organisation.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="f2ba9-113">**Säkerhetsåtgärder (SecOps)-postlådor:** Dedikerade postlådor som används av säkerhetsteam för att samla in och analysera ofiltrerade meddelanden (både bra och dåliga).</span><span class="sxs-lookup"><span data-stu-id="f2ba9-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="f2ba9-114">Du använder principen _för avancerad leverans i_ Microsoft 365 förhindra att dessa meddelanden i dessa specifika _scenarier_ filtreras. <sup>\*</sup> Med principen för avancerad leverans säkerställer du att meddelanden i följande scenarier uppnår följande resultat:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="f2ba9-115">Filter i EOP och Microsoft Defender för Office 365 inga åtgärder vidtas på dessa meddelanden.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f2ba9-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="f2ba9-116">[ZAP (Zero-hour Purge)](zero-hour-auto-purge.md) för skräppost och nätfiske åtgärdar inte dessa meddelanden.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f2ba9-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="f2ba9-117">[Standardsystemaviseringar](alerts.md) utlöses inte för dessa scenarier.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="f2ba9-118">[AIR och clustering i Defender för Office 365](office-365-air.md) ignorerar dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="f2ba9-119">Särskilt för nätfiskebedrägerier från tredje part:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="f2ba9-120">[Administratörsinskick](admin-submission.md) genererar ett automatiskt svar som säger att meddelandet är en del av en phishing-simuleringskampanj och inte är ett riktigt hot.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="f2ba9-121">Aviseringar och AIR utlöses inte.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="f2ba9-122">[Valv i Defender för Office 365](safe-links.md) blockeras eller avaktiverar inte de specifikt identifierade webbadresserna i dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="f2ba9-123">[Valv i Defender för Office 365](safe-attachments.md) avaktiverar inte bifogade filer i dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="f2ba9-124"><sup>\*</sup> Du kan inte kringgå filtrering av skadlig programvara eller ZAP för skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="f2ba9-125">Meddelanden som identifieras av den avancerade leveranspolicyn är inte säkerhetshot, så meddelandena markeras som system åsidosätter.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="f2ba9-126">Administratörer kan filtrera och analysera dessa system åsidosättningar i följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="f2ba9-127">Hotutforskaren/identifieringar i realtid i Defender för Office 365 abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="f2ba9-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="f2ba9-128">Sidan [E-post entitet i Hotutforskaren/realtidsidentifiering](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="f2ba9-129">Statusrapport [för skydd mot hot](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="f2ba9-130">Avancerad sökning i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f2ba9-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="f2ba9-131">Kampanjvyer</span><span class="sxs-lookup"><span data-stu-id="f2ba9-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f2ba9-132">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="f2ba9-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f2ba9-133">Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-133">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="f2ba9-134">Gå direkt till sidan **Avancerad leverans** genom att öppna <https://security.microsoft.com/advanceddelivery> .</span><span class="sxs-lookup"><span data-stu-id="f2ba9-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="f2ba9-135">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f2ba9-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f2ba9-136">Du måste ha tilldelats behörigheter innan du kan utföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f2ba9-137">Om du vill skapa, ändra eller ta bort konfigurerade inställningar i  den avancerade leveransprincipen måste du vara medlem  i rollgruppen Säkerhetsadministratör i **Microsoft 365 Defender-portalen** och medlem i rollgruppen Organisationshantering **i Exchange Online.**</span><span class="sxs-lookup"><span data-stu-id="f2ba9-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Microsoft 365 Defender portal** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>
  - <span data-ttu-id="f2ba9-138">För skrivskyddade åtkomst till avancerade leveransprinciper måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="f2ba9-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f2ba9-139">Mer information finns i [Behörigheter i Microsoft 365 Defender och](permissions-microsoft-365-security-center.md) Behörigheter i [Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-139">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="f2ba9-140">Om du lägger till användare i Azure Active Directory-rollen får användarna de  behörigheter som krävs i Microsoft 365 Defender-portalen samt behörighet för andra funktioner Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-140">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f2ba9-141">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f2ba9-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="f2ba9-142">Använd Microsoft 365 Defender för att konfigurera SecOps-postlådor i den avancerade leveranspolicyn</span><span class="sxs-lookup"><span data-stu-id="f2ba9-142">Use the Microsoft 365 Defender portal to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="f2ba9-143">I Microsoft 365 Defender-portalen går du till avsnittet **Regler för &** e-& för samarbete & Regler för \>  \>  \>  \> **hot.**</span><span class="sxs-lookup"><span data-stu-id="f2ba9-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="f2ba9-144">På sidan **Advanced delivery** kontrollerar du att **secOps-postlådefliken** är markerad och gör sedan något av följande:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-144">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="f2ba9-145">Klicka ![ på Redigera-ikonen ](../../media/m365-cc-sc-edit-icon.png) **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="f2ba9-145">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="f2ba9-146">Om det inte finns några konfigurerade nätfiskebedrägerier klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-146">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="f2ba9-147">På den **utfäll plats** för Redigera sekOps-postlådor som öppnas anger du en befintlig Exchange Online-postlåda som du vill ange som SecOps-postlåda genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-147">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="f2ba9-148">Klicka i rutan, lös listan över postlådor och välj sedan postlådan.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-148">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="f2ba9-149">Klicka i rutan och skriv en identifierare för postlådan (namn, visningsnamn, alias, e-postadress, kontonamn osv.) och välj postlådan (visningsnamn) i resultatet.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-149">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="f2ba9-150">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-150">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="f2ba9-151">Distributionsgrupper tillåts inte.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-151">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="f2ba9-152">Om du vill ta bort ett befintligt värde klickar du Ta bort</span><span class="sxs-lookup"><span data-stu-id="f2ba9-152">To remove an existing value, click remove</span></span> ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="f2ba9-154">bredvid värdet.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-154">next to the value.</span></span>

4. <span data-ttu-id="f2ba9-155">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-155">When you're finished, click **Save**.</span></span>

<span data-ttu-id="f2ba9-156">Postlådepostlådorna för SecOps som du har konfigurerat visas på **fliken SecOps-postlåda.** Om du vill göra ändringar klickar ![ du på ](../../media/m365-cc-sc-edit-icon.png) **Redigera-ikonen** Redigera på fliken.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-156">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="f2ba9-157">Använd Microsoft 365 Defender-portalen för att konfigurera nätfiskebedrägerier från tredje part i den avancerade leveranspolicyn</span><span class="sxs-lookup"><span data-stu-id="f2ba9-157">Use the Microsoft 365 Defender portal to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="f2ba9-158">I Microsoft 365 Defender-portalen går du till avsnittet **Regler för &** e-& för samarbete & Regler för \>  \>  \>  \> **hot.**</span><span class="sxs-lookup"><span data-stu-id="f2ba9-158">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="f2ba9-159">På sidan **Avancerad leverans** väljer du fliken **Phishing simulering** och gör sedan något av följande:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-159">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="f2ba9-160">Klicka ![ på Redigera-ikonen ](../../media/m365-cc-sc-edit-icon.png) **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="f2ba9-160">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="f2ba9-161">Om det inte finns några konfigurerade nätfiskebedrägerier klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-161">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="f2ba9-162">På den **utfällande menyn Redigera nätfiske** från tredje part som öppnas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-162">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="f2ba9-163">**Skicka domän:** Utöka den här inställningen och ange minst en e-postadressdomän (till exempel contoso.com) genom att klicka i rutan, ange ett värde och sedan trycka på Retur eller välja värdet som visas under rutan.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-163">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="f2ba9-164">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-164">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="f2ba9-165">Du kan lägga till upp till 10 poster.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-165">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="f2ba9-166">**Skicka IP:** Utöka den här inställningen och ange minst en giltig IPv4-adress genom att klicka i rutan, ange ett värde och sedan trycka på Retur eller välja värdet som visas under rutan.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-166">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="f2ba9-167">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-167">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="f2ba9-168">Du kan lägga till upp till 10 poster.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-168">You can add up to 10 entries.</span></span> <span data-ttu-id="f2ba9-169">Giltiga värden är:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-169">Valid values are:</span></span>
     - <span data-ttu-id="f2ba9-170">Enskild IP: Till exempel 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-170">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="f2ba9-171">IP-intervall: Till exempel 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-171">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="f2ba9-172">CIDR IP: Till exempel 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-172">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="f2ba9-173">**Simulerings-URL:er** som ska tillåtas: Utöka den här inställningen och ange eventuellt specifika URL-adresser som är en del av din phishing-simuleringskampanj som inte ska blockeras eller detoneras genom att klicka i rutan, ange ett värde och sedan trycka på Retur eller välja värdet som visas under rutan.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-173">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="f2ba9-174">Du kan lägga till upp till 10 poster.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-174">You can add up to 10 entries.</span></span>

   <span data-ttu-id="f2ba9-175">Om du vill ta bort ett befintligt värde klickar du Ta bort</span><span class="sxs-lookup"><span data-stu-id="f2ba9-175">To remove an existing value, click remove</span></span> ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="f2ba9-177">bredvid värdet.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-177">next to the value.</span></span>

4. <span data-ttu-id="f2ba9-178">Gör något av följande när du är klar:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-178">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="f2ba9-179">**Första gången:** Klicka **på Lägg** till och sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="f2ba9-179">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="f2ba9-180">**Redigera befintligt:** Klicka **på Spara** och sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="f2ba9-180">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="f2ba9-181">De simuleringsposter för nätfiske från tredje part som du har konfigurerat visas på fliken **Nätfiskebedrägerier.** Om du vill göra ändringar klickar ![ du på ](../../media/m365-cc-sc-edit-icon.png) **Redigera-ikonen** Redigera på fliken.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-181">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="f2ba9-182">Ytterligare scenarier som kräver förbikoppling av filtrering</span><span class="sxs-lookup"><span data-stu-id="f2ba9-182">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="f2ba9-183">Utöver de två scenarier som den avancerade leveransprincipen kan hjälpa dig med finns det andra scenarier som kan innebära att du måste kringgå filtrering:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-183">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="f2ba9-184">**Filter från tredje part:** Om domänens MX-post inte pekar på Office 365 (meddelanden dirigeras någon annanstans [först)](secure-by-default.md) är säker som standard *inte tillgänglig.* </span><span class="sxs-lookup"><span data-stu-id="f2ba9-184">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span> <span data-ttu-id="f2ba9-185">Om du vill lägga till skydd måste du aktivera Utökad filtrering för kopplingar (kallas även för hoppa *över post).*</span><span class="sxs-lookup"><span data-stu-id="f2ba9-185">If you'd like to add protection, you'll need to enable Enhanced Filtering for Connectors (also known as *skip listing*).</span></span> <span data-ttu-id="f2ba9-186">Mer information finns i Hantera [e-postflöde med hjälp av en molnbaserad tjänst från tredje Exchange Online.](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-186">For more information, see [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span></span> <span data-ttu-id="f2ba9-187">Om du inte vill ha utökad filtrering för kopplingar kan du använda e-postflödesregler (kallas även transportregler) för att kringgå Microsoft-filtrering för meddelanden som redan har utvärderats av filtrering från tredje part.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-187">If you don't want Enhanced Filtering for Connectors,use mail flow rules (also known as transport rules) to bypass Microsoft filtering for messages that have already been evaluated by third-party filtering.</span></span> <span data-ttu-id="f2ba9-188">Mer information finns i Använda [e-postflödesregler för att ange SCL i meddelanden.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-188">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="f2ba9-189">**Falska** positiva resultat under granskning: Du kanske tillfälligt vill tillåta att vissa meddelanden som fortfarande analyseras av Microsoft via administratörer rapporterar kända bra meddelanden som felaktigt [markeras](admin-submission.md) som dåliga för Microsoft (falska positiva resultat).</span><span class="sxs-lookup"><span data-stu-id="f2ba9-189">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="f2ba9-190">Precis som med alla åsidosättningar rekommenderar **_vi att_** dessa tillåtna produkter är tillfälliga.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-190">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="f2ba9-191">Exchange Online PowerShell-procedurer för SecOps-postlådor i den avancerade leveranspolicyn</span><span class="sxs-lookup"><span data-stu-id="f2ba9-191">Exchange Online PowerShell procedures for SecOps mailboxes in the advanced delivery policy</span></span>

<span data-ttu-id="f2ba9-192">I Exchange Online PowerShell är de grundläggande elementen i SecOps-postlådorna i den avancerade leveransprincipen:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-192">In Exchange Online PowerShell, the basic elements of SecOps mailboxes in the advanced delivery policy are:</span></span>

- <span data-ttu-id="f2ba9-193">**Åsidosättningspolicyn i SecOps:** Reglerad av **\* cmdletarna -SecOpsOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="f2ba9-193">**The SecOps override policy**: Controlled by the **\*-SecOpsOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="f2ba9-194">**Regeln för SecOps åsidosättning:** Kontrollerad av **\* cmdletarna -SecOpsOverrideRule.**</span><span class="sxs-lookup"><span data-stu-id="f2ba9-194">**The SecOps override rule**: Controlled by the **\*-SecOpsOverrideRule** cmdlets.</span></span>

<span data-ttu-id="f2ba9-195">Det här beteendet har följande resultat:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-195">This behavior has the following results:</span></span>

- <span data-ttu-id="f2ba9-196">Du skapar principen först och sedan skapar du den regel som identifierar principen som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-196">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="f2ba9-197">När du tar bort en princip från PowerShell tas även motsvarande regel bort.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-197">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="f2ba9-198">När du tar bort en regel från PowerShell tas motsvarande princip inte bort.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-198">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="f2ba9-199">Du måste ta bort motsvarande princip manuellt.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-199">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-secops-mailboxes"></a><span data-ttu-id="f2ba9-200">Använda PowerShell för att konfigurera SecOps-postlådor</span><span class="sxs-lookup"><span data-stu-id="f2ba9-200">Use PowerShell to configure SecOps mailboxes</span></span>

<span data-ttu-id="f2ba9-201">Att konfigurera en SecOps-postlåda i principen för avancerad leverans i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-201">Configuring a SecOps mailbox in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="f2ba9-202">Skapa åsidosättningspolicyn SecOps.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-202">Create the SecOps override policy.</span></span>
2. <span data-ttu-id="f2ba9-203">Skapa regeln för secOps-åsidosättning som anger den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-203">Create the SecOps override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a><span data-ttu-id="f2ba9-204">Steg 1: Använd PowerShell för att skapa åsidosättsprincipen för SecOps</span><span class="sxs-lookup"><span data-stu-id="f2ba9-204">Step 1: Use PowerShell to create the SecOps override policy</span></span>

<span data-ttu-id="f2ba9-205">Använd följande syntax för att skapa åsidosättningspolicyn SecOps:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-205">To create the SecOps override policy, use the following syntax:</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

<span data-ttu-id="f2ba9-206">**Obs!** Oavsett vilket namnvärde du anger blir principnamnet SecOpsOverridePolicy, så du kan lika gärna använda det värdet.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-206">**Note**: Regardless of the Name value you specify, the policy name will be SecOpsOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="f2ba9-207">I det här exemplet skapas SecOps-postlådeprincipen.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-207">This example creates the SecOps mailbox policy.</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SendTo secops@contoso.com
```

<span data-ttu-id="f2ba9-208">Detaljerad information om syntax och parametrar finns [i New-SecOpsOverridePolicy.](/powershell/module/exchange/new-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-208">For detailed syntax and parameter information, see [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a><span data-ttu-id="f2ba9-209">Steg 2: Använd PowerShell för att skapa åsidosättningsregeln för SecOps</span><span class="sxs-lookup"><span data-stu-id="f2ba9-209">Step 2: Use PowerShell to create the SecOps override rule</span></span>

<span data-ttu-id="f2ba9-210">I det här exemplet skapas SecOps-postlåderegeln med angivna inställningar.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-210">This example creates the SecOps mailbox rule with the specified settings.</span></span>

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

<span data-ttu-id="f2ba9-211">\*\*Obs!\*\*\*\* Oavsett vilket namnvärde du anger blir regelnamnet SecOpsOverrideRule där det är ett unikt \<GUID\> \<GUID\> GUID-värde (till exempel 6fed4b63-3563-495d-a481-b24a311f8329).</span><span class="sxs-lookup"><span data-stu-id="f2ba9-211">**Note**: \*\*Regardless of the Name value you specify, the rule name will be SecOpsOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, 6fed4b63-3563-495d-a481-b24a311f8329).</span></span>

<span data-ttu-id="f2ba9-212">Detaljerad information om syntax och parametrar finns [i New-SecOpsOverrideRule.](/powershell/module/exchange/new-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-212">For detailed syntax and parameter information, see [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span></span>

### <a name="use-powershell-to-view-the-secops-override-policy"></a><span data-ttu-id="f2ba9-213">Använda PowerShell för att visa åsidosättningspolicyn i SecOps</span><span class="sxs-lookup"><span data-stu-id="f2ba9-213">Use PowerShell to view the SecOps override policy</span></span>

<span data-ttu-id="f2ba9-214">Det här exemplet returnerar detaljerad information om den enda SecOps-postlådeprincipen.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-214">This example returns detailed information about the one and only SecOps mailbox policy.</span></span>

```powershell
Get-SecOpsOverridePolicy
```

<span data-ttu-id="f2ba9-215">Detaljerad information om syntax och parametrar finns i [Get-SecOpsOverridePolicy.](/powershell/module/exchange/get-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-215">For detailed syntax and parameter information, see [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-view-secops-override-rules"></a><span data-ttu-id="f2ba9-216">Använda PowerShell för att visa regler som åsidosätter SecOps</span><span class="sxs-lookup"><span data-stu-id="f2ba9-216">Use PowerShell to view SecOps override rules</span></span>

<span data-ttu-id="f2ba9-217">Det här exemplet returnerar detaljerad information om regler för SecOps-åsidosättning.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-217">This example returns detailed information about SecOps override rules.</span></span>

```powershell
Get-SecOpsOverrideRule
```

<span data-ttu-id="f2ba9-218">Även om föregående kommando endast ska returnera en regel, kan även regler som väntar på att tas bort ingå i resultatet.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-218">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="f2ba9-219">I det här exemplet identifieras den giltiga regeln (en) och alla ogiltiga regler.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-219">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="f2ba9-220">När du har identifierat ogiltiga regler kan du ta bort dem med hjälp av cmdleten **Remove-SecOpsOverrideRule** enligt beskrivningen längre fram [i den här artikeln.](#use-powershell-to-remove-secops-override-rules)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-220">After you identify the invalid rules, you can remove them by using the **Remove-SecOpsOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-secops-override-rules).</span></span>

<span data-ttu-id="f2ba9-221">Detaljerad information om syntax och parametrar finns i [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-221">For detailed syntax and parameter information, see [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span></span>

### <a name="use-powershell-to-modify-the-secops-override-policy"></a><span data-ttu-id="f2ba9-222">Använda PowerShell för att ändra åsidosättningspolicyn i SecOps</span><span class="sxs-lookup"><span data-stu-id="f2ba9-222">Use PowerShell to modify the SecOps override policy</span></span>

<span data-ttu-id="f2ba9-223">Använd följande syntax för att ändra åsidosättningsprincipen för SecOps:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-223">To modify the SecOps override policy, use the following syntax:</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

<span data-ttu-id="f2ba9-224">I det här exemplet läggs secops2@contoso.com till i SecOps åsidosättningspolicyn.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-224">This example adds secops2@contoso.com to the SecOps override policy.</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

<span data-ttu-id="f2ba9-225">**Obs!** Om det finns en associerad, giltig åsidosättningsregel för SecOps uppdateras även e-postadresserna i regeln.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-225">**Note**: If an associated, valid SecOps override rule exists, the email addresses in the rule will also be updated.</span></span>

<span data-ttu-id="f2ba9-226">Detaljerad information om syntax och parametrar finns [i Set-SecOpsOverridePolicy.](/powershell/module/exchange/set-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-226">For detailed syntax and parameter information, see [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-secops-override-rule"></a><span data-ttu-id="f2ba9-227">Använda PowerShell för att ändra en åsidosättningsregel för SecOps</span><span class="sxs-lookup"><span data-stu-id="f2ba9-227">Use PowerShell to modify a SecOps override rule</span></span>

<span data-ttu-id="f2ba9-228">**Cmdlet:en Set-SecOpsOverrideRule** ändrar inte e-postadresserna i regeln om åsidosättning av SecOps.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-228">The **Set-SecOpsOverrideRule** cmdlet does not modify the email addresses in the SecOps override rule.</span></span> <span data-ttu-id="f2ba9-229">Använd cmdleten **Set-SecOpsOverridePolicy** för att ändra e-postadresserna i regeln för SecOps-åsidosättning.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-229">To modify the email addresses in the SecOps override rule, use the **Set-SecOpsOverridePolicy** cmdlet.</span></span>

<span data-ttu-id="f2ba9-230">Detaljerad information om syntax och parametrar finns [i Set-SecOpsOverrideRule.](/powershell/module/exchange/set-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-230">For detailed syntax and parameter information, see [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).</span></span>

### <a name="use-powershell-to-remove-the-secops-override-policy"></a><span data-ttu-id="f2ba9-231">Använda PowerShell för att ta bort principen för SecOps-åsidosättning</span><span class="sxs-lookup"><span data-stu-id="f2ba9-231">Use PowerShell to remove the SecOps override policy</span></span>

<span data-ttu-id="f2ba9-232">Det här exemplet tar bort SecOps-postlådeprincipen och motsvarande regel.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-232">This example removes the SecOps Mailbox policy and the corresponding rule.</span></span>

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

<span data-ttu-id="f2ba9-233">Detaljerad information om syntax och parametrar finns i [Remove-SecOpsOverridePolicy.](/powershell/module/exchange/remove-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-233">For detailed syntax and parameter information, see [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-secops-override-rules"></a><span data-ttu-id="f2ba9-234">Använda PowerShell för att ta bort regler för SecOps-åsidosättning</span><span class="sxs-lookup"><span data-stu-id="f2ba9-234">Use PowerShell to remove SecOps override rules</span></span>

<span data-ttu-id="f2ba9-235">Använd följande syntax för att ta bort en regel som åsidosätter SecOps:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-235">To remove a SecOps override rule, use the following syntax:</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="f2ba9-236">I det här exemplet tas den angivna SecOps-regeln bort.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-236">This example removes the specified SecOps override rule.</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

<span data-ttu-id="f2ba9-237">Detaljerad information om syntax och parametrar finns i [Remove-SecOpsOverrideRule.](/powershell/module/exchange/remove-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-237">For detailed syntax and parameter information, see [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span></span>

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="f2ba9-238">Exchange Online PowerShell-procedurer för nätfiskebedrägerier från tredje part i den avancerade leveranspolicyn</span><span class="sxs-lookup"><span data-stu-id="f2ba9-238">Exchange Online PowerShell procedures for third-party phishing simulations in the advanced delivery policy</span></span>

<span data-ttu-id="f2ba9-239">I Exchange Online PowerShell är de grundläggande elementen i simuleringar av nätfiske från tredje part i den avancerade leveranspolicyn:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-239">In Exchange Online PowerShell, the basic elements of third-party phishing simulations in the advanced delivery policy are:</span></span>

- <span data-ttu-id="f2ba9-240">**Åsidosättningsprincipen för nätfiske:** Styrs av cmdletarna **\* -PhishSimOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="f2ba9-240">**The phishing simulation override policy**: Controlled by the **\*-PhishSimOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="f2ba9-241">**Regeln för åsidosättning av nätfiske:** Styrs av cmdletarna **\* -PhishSimOverrideRule.**</span><span class="sxs-lookup"><span data-stu-id="f2ba9-241">**The phishing simulation override rule**: Controlled by the **\*-PhishSimOverrideRule** cmdlets.</span></span>

<span data-ttu-id="f2ba9-242">Det här beteendet har följande resultat:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-242">This behavior has the following results:</span></span>

- <span data-ttu-id="f2ba9-243">Du skapar principen först och sedan skapar du den regel som identifierar principen som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-243">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="f2ba9-244">Du ändrar inställningarna i principen och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-244">You modify the settings in the policy and the rule separately.</span></span>
- <span data-ttu-id="f2ba9-245">När du tar bort en princip från PowerShell tas även motsvarande regel bort.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-245">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="f2ba9-246">När du tar bort en regel från PowerShell tas motsvarande princip inte bort.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-246">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="f2ba9-247">Du måste ta bort motsvarande princip manuellt.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-247">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a><span data-ttu-id="f2ba9-248">Använda PowerShell för att konfigurera nätfiskebedrägerier från tredje part</span><span class="sxs-lookup"><span data-stu-id="f2ba9-248">Use PowerShell to configure third-party phishing simulations</span></span>

<span data-ttu-id="f2ba9-249">Konfigurera en nätfiskebedrägeri från tredje part i den avancerade leveranspolicyn i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-249">Configuring a third-party phishing simulation in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="f2ba9-250">Skapa åsidosättningsprincipen för nätfiskebedrägerier.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-250">Create the phishing simulation override policy.</span></span>
2. <span data-ttu-id="f2ba9-251">Skapa regeln för åsidosättning av nätfiske som anger principen som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-251">Create the phishing simulation override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a><span data-ttu-id="f2ba9-252">Steg 1: Använd PowerShell för att skapa principen för att åsidosätta nätfiske</span><span class="sxs-lookup"><span data-stu-id="f2ba9-252">Step 1: Use PowerShell to create the phishing simulation override policy</span></span>

<span data-ttu-id="f2ba9-253">I det här exemplet skapas en åsidosättningsprincip för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-253">This example creates the phishing simulation override policy.</span></span>

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

<span data-ttu-id="f2ba9-254">**Obs!** Oavsett vilket namnvärde du anger blir principnamnet PhishSimOverridePolicy, så du kan lika gärna använda det värdet.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-254">**Note**: Regardless of the Name value you specify, the policy name will be PhishSimOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="f2ba9-255">Detaljerad information om syntax och parametrar finns i [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="f2ba9-255">For detailed syntax and parameter information, see [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a><span data-ttu-id="f2ba9-256">Steg 2: Använd PowerShell för att skapa regeln för åsidosättning av nätfiske</span><span class="sxs-lookup"><span data-stu-id="f2ba9-256">Step 2: Use PowerShell to create the phishing simulation override rule</span></span>

<span data-ttu-id="f2ba9-257">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-257">Use the following syntax:</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

<span data-ttu-id="f2ba9-258">Oavsett vilket namnvärde du anger blir regelnamnet PhishSimOverrideRule, där det är ett unikt \<GUID\> \<GUID\> GUID-värde (till exempel a0eae53e-d755-4a42-9320-b9c6b55c5011).</span><span class="sxs-lookup"><span data-stu-id="f2ba9-258">Regardless of the Name value you specify, the rule name will be PhishSimOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span></span>

<span data-ttu-id="f2ba9-259">En giltig IP-adresspost är något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-259">A valid IP address entry is one of the following values:</span></span>

- <span data-ttu-id="f2ba9-260">Enskild IP: Till exempel 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-260">Single IP: For example, 192.168.1.1.</span></span>
- <span data-ttu-id="f2ba9-261">IP-intervall: Till exempel 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-261">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
- <span data-ttu-id="f2ba9-262">CIDR IP: Till exempel 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-262">CIDR IP: For example, 192.168.0.1/25.</span></span>

<span data-ttu-id="f2ba9-263">I det här exemplet skapas regeln för åsidosättning av nätfiske med angivna inställningar.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-263">This example creates the phishing simulation override rule with the specified settings.</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

<span data-ttu-id="f2ba9-264">Detaljerad information om syntax och parametrar finns i [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="f2ba9-264">For detailed syntax and parameter information, see [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a><span data-ttu-id="f2ba9-265">Använda PowerShell för att visa åsidosättningsprincip för nätfiske</span><span class="sxs-lookup"><span data-stu-id="f2ba9-265">Use PowerShell to view the phishing simulation override policy</span></span>

<span data-ttu-id="f2ba9-266">Det här exemplet returnerar detaljerad information om den enda åsidosättningsprincipen för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-266">This example returns detailed information about the one and only phishing simulation override policy.</span></span>

```powershell
Get-PhishSimOverridePolicy
```

<span data-ttu-id="f2ba9-267">Detaljerad information om syntax och parametrar finns i [Get-PhishSimOverridePolicy.](/powershell/module/exchange/get-phishsimoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-267">For detailed syntax and parameter information, see [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a><span data-ttu-id="f2ba9-268">Använda PowerShell för att visa regler för att åsidosätta nätfiske</span><span class="sxs-lookup"><span data-stu-id="f2ba9-268">Use PowerShell to view phishing simulation override rules</span></span>

<span data-ttu-id="f2ba9-269">Det här exemplet returnerar detaljerad information om regler för att åsidosätta nätfiske.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-269">This example returns detailed information about phishing simulation override rules.</span></span>

```powershell
Get-PhishSimOverrideRule
```

<span data-ttu-id="f2ba9-270">Även om föregående kommando endast ska returnera en regel, kan även regler som väntar på att tas bort ingå i resultatet.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-270">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="f2ba9-271">I det här exemplet identifieras den giltiga regeln (en) och alla ogiltiga regler.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-271">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="f2ba9-272">När du har identifierat ogiltiga regler kan du ta bort dem med hjälp av cmdleten **Remove-PhisSimOverrideRule** enligt beskrivningen längre fram [i den här artikeln.](#use-powershell-to-remove-phishing-simulation-override-rules)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-272">After you identify the invalid rules, you can remove them by using the **Remove-PhisSimOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-phishing-simulation-override-rules).</span></span>

<span data-ttu-id="f2ba9-273">Detaljerad information om syntax och parametrar finns i [Get-PhishSimOverrideRule.](/powershell/module/exchange/get-phishsimoverriderule)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-273">For detailed syntax and parameter information, see [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a><span data-ttu-id="f2ba9-274">Använda PowerShell för att ändra åsidosättningsprincipen för nätfiske</span><span class="sxs-lookup"><span data-stu-id="f2ba9-274">Use PowerShell to modify the phishing simulation override policy</span></span>

<span data-ttu-id="f2ba9-275">Använd följande syntax för att ändra åsidosättningsprincipen för nätfiske:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-275">To modify the phishing simulation override policy, use the following syntax:</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="f2ba9-276">I det här exemplet inaktiveras principen för åsidosättning av nätfiske.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-276">This example disables the phishing simulation override policy.</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

<span data-ttu-id="f2ba9-277">Detaljerad information om syntax och parametrar finns [i Set-PhishSimOverridePolicy.](/powershell/module/exchange/set-phishsimoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-277">For detailed syntax and parameter information, see [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a><span data-ttu-id="f2ba9-278">Använda PowerShell för att ändra en åsidosättningsregel för nätfiske</span><span class="sxs-lookup"><span data-stu-id="f2ba9-278">Use PowerShell to modify a phishing simulation override rule</span></span>

<span data-ttu-id="f2ba9-279">Använd följande syntax för att ändra regeln för åsidosättning av nätfiske:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-279">To modify the phishing simulation override rule, use the following syntax:</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

<span data-ttu-id="f2ba9-280">I det här exemplet ändras den angivna regeln för åsidosättning av nätfiske med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-280">This example modifies the specified phishing simulation override rule with the following settings:</span></span>

- <span data-ttu-id="f2ba9-281">Lägg till domänposten blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-281">Add the domain entry blueyonderairlines.com.</span></span>
- <span data-ttu-id="f2ba9-282">Ta bort IP-adressposten 192.168.1.55.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-282">Remove the IP address entry 192.168.1.55.</span></span>

<span data-ttu-id="f2ba9-283">Observera att dessa ändringar inte påverkar befintliga poster.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-283">Note that these changes don't affect existing entries.</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

<span data-ttu-id="f2ba9-284">Detaljerad information om syntax och parametrar finns [i Set-PhishSimOverrideRule.](/powershell/module/exchange/set-phishsimoverriderule)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-284">For detailed syntax and parameter information, see [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a><span data-ttu-id="f2ba9-285">Använda PowerShell för att ta bort en åsidosättningsprincip för nätfiske</span><span class="sxs-lookup"><span data-stu-id="f2ba9-285">Use PowerShell to remove a phishing simulation override policy</span></span>

<span data-ttu-id="f2ba9-286">I det här exemplet tas åsidosättningsprincipen för nätfiske bort och motsvarande regel.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-286">This example removes the phishing simulation override policy and the corresponding rule.</span></span>

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

<span data-ttu-id="f2ba9-287">Detaljerad information om syntax och parametrar finns i [Remove-PhishSimOverridePolicy.](/powershell/module/exchange/remove-phishsimoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-287">For detailed syntax and parameter information, see [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a><span data-ttu-id="f2ba9-288">Använda PowerShell för att ta bort regler för att åsidosätta nätfiske</span><span class="sxs-lookup"><span data-stu-id="f2ba9-288">Use PowerShell to remove phishing simulation override rules</span></span>

<span data-ttu-id="f2ba9-289">Använd följande syntax för att ta bort en regel för att åsidosätta nätfiske:</span><span class="sxs-lookup"><span data-stu-id="f2ba9-289">To remove a phishing simulation override rule, use the following syntax:</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="f2ba9-290">Det här exemplet tar bort den angivna regeln för åsidosättning av nätfiske.</span><span class="sxs-lookup"><span data-stu-id="f2ba9-290">This example removes the specified phishing simulation override rule.</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

<span data-ttu-id="f2ba9-291">Detaljerad information om syntax och parametrar finns i [Remove-PhishSimOverrideRule.](/powershell/module/exchange/remove-phishsimoverriderule)</span><span class="sxs-lookup"><span data-stu-id="f2ba9-291">For detailed syntax and parameter information, see [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span></span>
