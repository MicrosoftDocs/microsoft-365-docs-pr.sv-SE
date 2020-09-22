---
title: Skydda mot hot
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa om hotets skydd i Microsoft 365 och konfigurera hur det ska användas för din organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ad74e9bdcd7b937873108d2ba049c16db8c235b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202585"
---
# <a name="protect-against-threats"></a><span data-ttu-id="35e0f-103">Skydda mot hot</span><span class="sxs-lookup"><span data-stu-id="35e0f-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="35e0f-104">Här är en snabb start guide som bryter ned konfigurationen av avancerat skydd mot segment.</span><span class="sxs-lookup"><span data-stu-id="35e0f-104">Here's a quick-start guide that breaks the configuration of Advanced Threat Protection into chunks.</span></span> <span data-ttu-id="35e0f-105">Om du är nybörjare i Office 365 och inte vet var du ska börja, eller om du får det genom *att göra*, kan du använda den här vägledningen som en check lista och en utgångs punkt.</span><span class="sxs-lookup"><span data-stu-id="35e0f-105">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35e0f-106">**Initiala rekommenderade inställningar är tillgängliga för alla typer av principer, men du kan också ändra dina inställningar för att uppfylla specifika organisationens behov**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-106">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="35e0f-107">Tillåt cirka 30 minuter för dina principer eller ändringar för att fungera på ett annat sätt via ditt data Center.</span><span class="sxs-lookup"><span data-stu-id="35e0f-107">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="35e0f-108">Krav</span><span class="sxs-lookup"><span data-stu-id="35e0f-108">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="35e0f-109">Prenumerationer</span><span class="sxs-lookup"><span data-stu-id="35e0f-109">Subscriptions</span></span>

<span data-ttu-id="35e0f-110">Hot Protection-funktioner är inkluderade i *alla* Microsoft-eller Office 365-abonnemang; Vissa abonnemang har emellertid avancerade funktioner.</span><span class="sxs-lookup"><span data-stu-id="35e0f-110">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="35e0f-111">I tabellen nedan visas de skydds funktioner som ingår i den här artikeln tillsammans med de minsta abonnemangs kraven.</span><span class="sxs-lookup"><span data-stu-id="35e0f-111">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="35e0f-112">Observera att, utöver anvisningarna för att aktivera granskning, *att börja mot* skadlig program vara, nätfiske och anti-spam, som är markerade som en del av Office 365 Exchange Online Protection (**EOP**).</span><span class="sxs-lookup"><span data-stu-id="35e0f-112">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="35e0f-113">Detta kan verka så udda ut i en artikel för avancerat skydd, tills du får ett avancerat skydd (**ATP**) och bygger på EOP.</span><span class="sxs-lookup"><span data-stu-id="35e0f-113">This can seem odd in an Advanced Threat Protection article, until you remember Advanced Threat Protection (**ATP**) contains, and builds on, EOP.</span></span>

****

|<span data-ttu-id="35e0f-114">Skydds typ</span><span class="sxs-lookup"><span data-stu-id="35e0f-114">Protection type</span></span>|<span data-ttu-id="35e0f-115">Abonnemangs behov</span><span class="sxs-lookup"><span data-stu-id="35e0f-115">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="35e0f-116">Gransknings loggning (för rapporterings ändamål)</span><span class="sxs-lookup"><span data-stu-id="35e0f-116">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="35e0f-117">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="35e0f-117">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="35e0f-118">Skydd mot skadlig kod</span><span class="sxs-lookup"><span data-stu-id="35e0f-118">Anti-malware protection</span></span>|<span data-ttu-id="35e0f-119">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span><span class="sxs-lookup"><span data-stu-id="35e0f-119">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="35e0f-120">Skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="35e0f-120">Anti-phishing protection</span></span>|[<span data-ttu-id="35e0f-121">EOP</span><span class="sxs-lookup"><span data-stu-id="35e0f-121">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="35e0f-122">Skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="35e0f-122">Anti-spam protection</span></span>|[<span data-ttu-id="35e0f-123">EOP</span><span class="sxs-lookup"><span data-stu-id="35e0f-123">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="35e0f-124">Automatisk rensning av Tom timme (för e-post)</span><span class="sxs-lookup"><span data-stu-id="35e0f-124">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="35e0f-125">EOP</span><span class="sxs-lookup"><span data-stu-id="35e0f-125">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="35e0f-126">Skydda från skadliga URL-adresser och filer i e-post och Office-dokument (säkra länkar och säkra bifogade filer)</span><span class="sxs-lookup"><span data-stu-id="35e0f-126">Protection from malicious URLs and files in email and Office documents (safe links and safe attachments)</span></span>|<span data-ttu-id="35e0f-127">[Office 365 Avancerat skydd](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**)</span><span class="sxs-lookup"><span data-stu-id="35e0f-127">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**)</span></span>|
|<span data-ttu-id="35e0f-128">Aktivera ATP för arbets belastning för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35e0f-128">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>| [<span data-ttu-id="35e0f-129">LOVA</span><span class="sxs-lookup"><span data-stu-id="35e0f-129">ATP</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide)|
|<span data-ttu-id="35e0f-130">Avancerat skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="35e0f-130">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="35e0f-131">LOVA</span><span class="sxs-lookup"><span data-stu-id="35e0f-131">ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="35e0f-132">Roller och behörigheter</span><span class="sxs-lookup"><span data-stu-id="35e0f-132">Roles and permissions</span></span>

<span data-ttu-id="35e0f-133">För att kunna konfigurera ATP-principer måste du ha tilldelats en lämplig roll i [säkerhets & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="35e0f-133">To configure ATP policies, you must be assigned an appropriate role in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="35e0f-134">Ta en titt på tabellen nedan för roller som kan utföra de här åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="35e0f-134">Take a look at the table below for roles that can do these actions.</span></span>

****

|<span data-ttu-id="35e0f-135">Roll eller rollgrupp</span><span class="sxs-lookup"><span data-stu-id="35e0f-135">Role or role group</span></span>|<span data-ttu-id="35e0f-136">Var kan jag läsa mer?</span><span class="sxs-lookup"><span data-stu-id="35e0f-136">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="35e0f-137">global administratör</span><span class="sxs-lookup"><span data-stu-id="35e0f-137">global administrator</span></span>|[<span data-ttu-id="35e0f-138">Om administratörsroller i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="35e0f-138">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="35e0f-139">Säkerhets administratör</span><span class="sxs-lookup"><span data-stu-id="35e0f-139">Security Administrator</span></span>|[<span data-ttu-id="35e0f-140">Administratörens rollbehörigheter i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="35e0f-140">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="35e0f-141">Organisations hantering i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="35e0f-141">Exchange Online Organization Management</span></span>|[<span data-ttu-id="35e0f-142">Behörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="35e0f-142">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="35e0f-143">och</span><span class="sxs-lookup"><span data-stu-id="35e0f-143">and</span></span><br> [<span data-ttu-id="35e0f-144">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="35e0f-144">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="35e0f-145">Mer information finns i [behörigheter i säkerhets &amp; kontroll Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="35e0f-145">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="35e0f-146">Innan du börjar aktiverar du gransknings loggning för rapportering och undersökning</span><span class="sxs-lookup"><span data-stu-id="35e0f-146">Before you begin, turn on Audit logging for reporting and investigation</span></span>

<span data-ttu-id="35e0f-147">Starta din gransknings loggning tidigt.</span><span class="sxs-lookup"><span data-stu-id="35e0f-147">Start your audit logging early.</span></span> <span data-ttu-id="35e0f-148">Du behöver **Granska för vissa** av stegen som följer.</span><span class="sxs-lookup"><span data-stu-id="35e0f-148">You'll need auditing to be **ON** for certain of the steps that follow.</span></span> <span data-ttu-id="35e0f-149">Gransknings loggning är tillgängligt i abonnemang som innehåller [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span><span class="sxs-lookup"><span data-stu-id="35e0f-149">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="35e0f-150">Gransknings loggning måste vara *aktiverat*för att du ska kunna visa data i Threat Protection [email security reports](view-email-security-reports.md)-rapporter, till exempel [säkerhets instrument panelen](security-dashboard.md)och [Utforskaren](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="35e0f-150">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="35e0f-151">Mer information finns i [Aktivera eller inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="35e0f-151">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="35e0f-152">Del 1 – skydd mot skadlig program vara</span><span class="sxs-lookup"><span data-stu-id="35e0f-152">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="35e0f-153">[Skydd mot skadlig program](anti-malware-protection.md) vara finns i abonnemang som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="35e0f-153">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="35e0f-154">Välj skydd mot **Threat management**skadligt Management policy i [Center för säkerhet & efterlevnad](https://protection.office.com)  >  **Policy**  >  **Anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-154">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="35e0f-155">Dubbelklicka på **standard** principen och välj sedan **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-155">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="35e0f-156">Ange följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="35e0f-156">Specify the following settings:</span></span>

    - <span data-ttu-id="35e0f-157">Behåll standardinställningen i avsnittet för **identifiering av skadlig program** **vara.**</span><span class="sxs-lookup"><span data-stu-id="35e0f-157">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="35e0f-158">I **filter avsnittet gemensamma bilagor** väljer du **på**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-158">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="35e0f-159">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-159">Click **Save**.</span></span>

<span data-ttu-id="35e0f-160">Mer information om alternativ för principer mot skadlig program vara finns i [Konfigurera principer för skadlig program vara](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="35e0f-160">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection"></a><span data-ttu-id="35e0f-161">Del 2 – skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="35e0f-161">Part 2 - Anti-phishing protection</span></span>

<span data-ttu-id="35e0f-162">[Anti-nätfiske]</span><span class="sxs-lookup"><span data-stu-id="35e0f-162">[Anti-phishing]</span></span>

<span data-ttu-id="35e0f-163">[Skydd mot nätfiske](anti-phishing-protection.md) är tillgängligt i abonnemang med [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="35e0f-163">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="35e0f-164">Avancerat skydd mot nätfiske är tillgängligt i [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="35e0f-164">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="35e0f-165">Här beskrivs hur du konfigurerar en policy för ATP-anti-nätfiske.</span><span class="sxs-lookup"><span data-stu-id="35e0f-165">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="35e0f-166">De här stegen är liknande för att konfigurera en anti-nätfiske-princip (utan ATP).</span><span class="sxs-lookup"><span data-stu-id="35e0f-166">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="35e0f-167">Välj **Threat Management**policy [Security & Compliance Center](https://protection.office.com)  >  **Policy**  >  **ATP-nätfiske**i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="35e0f-167">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="35e0f-168">Klicka på **standard policy**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-168">Click **Default policy**.</span></span>

3. <span data-ttu-id="35e0f-169">Klicka på **Redigera**i avsnittet **personifiering** och ange sedan följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="35e0f-169">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="35e0f-170">På fliken **Lägg till användare på skydda** *aktiverar du* skydd.</span><span class="sxs-lookup"><span data-stu-id="35e0f-170">On the **Add users to protect** tab, turn *On* protection.</span></span> <span data-ttu-id="35e0f-171">Lägg sedan till användare, till exempel organisationens styrelse medlemmar, VD, ekonomi och andra chefs ledare.</span><span class="sxs-lookup"><span data-stu-id="35e0f-171">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="35e0f-172">(Du kan skriva en enskild e-postadress eller klicka på för att visa en lista.)</span><span class="sxs-lookup"><span data-stu-id="35e0f-172">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="35e0f-173">På fliken **Lägg till domäner på skydda** aktiverar **du automatiskt de domäner jag äger**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-173">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="35e0f-174">Om du har anpassade domäner kan du lägga till dem nu.</span><span class="sxs-lookup"><span data-stu-id="35e0f-174">If you have custom domains, add them now.</span></span>

   - <span data-ttu-id="35e0f-175">På fliken **åtgärder** väljer du **Quarantine meddelandet** för både den **personifierade användaren** och de **personifierade domän** alternativen.</span><span class="sxs-lookup"><span data-stu-id="35e0f-175">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="35e0f-176">Aktivera också säkerhets tips.</span><span class="sxs-lookup"><span data-stu-id="35e0f-176">Also, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="35e0f-177">På fliken **Mailbox** Intelligence kontrollerar du att post låda-intelligens är aktiverat och aktiverar postbaserad skydd mot postlådan.</span><span class="sxs-lookup"><span data-stu-id="35e0f-177">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on and turn on mailbox intelligence-based impersonation protection.</span></span> <span data-ttu-id="35e0f-178">I listan **om e-post som skickas av en personifierad användare** väljer **du sätt i karantän meddelandet**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-178">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="35e0f-179">På fliken **Lägg till betrodda avsändare och domäner** anger du betrodda avsändare eller domäner som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="35e0f-179">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="35e0f-180">**Spara** på fliken **Granska inställningar** när du har granskat dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="35e0f-180">**Save** on the **Review your settings** tab after you've reviewed your settings.</span></span>

4. <span data-ttu-id="35e0f-181">Klicka på **Redigera**i avsnittet **Spoof** och ange sedan följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="35e0f-181">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="35e0f-182">Kontrol lera att skyddet mot förfalskning är aktiverat på fliken **Inställningar för falska filter** .</span><span class="sxs-lookup"><span data-stu-id="35e0f-182">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="35e0f-183">Välj **Quarantine The meddelande**på fliken **Actions** .</span><span class="sxs-lookup"><span data-stu-id="35e0f-183">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="35e0f-184">**Spara** på fliken **Granska inställningar** när du har granskat dina ändringar.</span><span class="sxs-lookup"><span data-stu-id="35e0f-184">**Save** on the **Review your settings** tab after you have reviewed your changes.</span></span> <span data-ttu-id="35e0f-185">(Om du inte har gjort några ändringar **avbryter**du.)</span><span class="sxs-lookup"><span data-stu-id="35e0f-185">(If you didn't make any changes, **Cancel**.)</span></span>

5. <span data-ttu-id="35e0f-186">Stäng sidan standardinställningar för princip inställningar.</span><span class="sxs-lookup"><span data-stu-id="35e0f-186">Close the default policy settings page.</span></span>

<span data-ttu-id="35e0f-187">Mer information om dina alternativ för skydd mot nätfiske finns i avsnittet [Konfigurera AntiPhishing-principer för ATP](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="35e0f-187">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection"></a><span data-ttu-id="35e0f-188">Del 3-skydd mot skräp post</span><span class="sxs-lookup"><span data-stu-id="35e0f-188">Part 3 - Anti-spam protection</span></span>

<span data-ttu-id="35e0f-189">[Skydd mot skräp post](anti-spam-protection.md) finns i abonnemang som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="35e0f-189">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="35e0f-190">I [säkerhets & Compliance Center](https://protection.office.com)väljer du **hot Management**  >  **policy**  >  **anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-190">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="35e0f-191">Aktivera anpassade inställningar på fliken **anpassad** .</span><span class="sxs-lookup"><span data-stu-id="35e0f-191">On the **Custom** tab, turn on Custom settings.</span></span>

3. <span data-ttu-id="35e0f-192">Expandera **standard filter princip för skräp post**, klicka på **Redigera princip**och ange sedan följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="35e0f-192">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="35e0f-193">I avsnittet **skräp post och Mass åtgärder** anger du tröskelvärdet till 5 eller 6.</span><span class="sxs-lookup"><span data-stu-id="35e0f-193">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="35e0f-194">Granska (och/eller redigera) dina tillåtna avsändare och domäner i avsnittet **tillåta listor** .</span><span class="sxs-lookup"><span data-stu-id="35e0f-194">In the **Allow lists** section, review (and/or edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="35e0f-195">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-195">Click **Save**.</span></span>

<span data-ttu-id="35e0f-196">Mer information om alternativen för att förhindra skräp post finns i [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="35e0f-196">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments"></a><span data-ttu-id="35e0f-197">Del 4 – skydda skadlig URL och filer (säkra länkar och säkra bifogade filer)</span><span class="sxs-lookup"><span data-stu-id="35e0f-197">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments)</span></span>

<span data-ttu-id="35e0f-198">Skydd mot skadlig URL-adress och filer är tillgängligt i abonnemang som inkluderar [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP).</span><span class="sxs-lookup"><span data-stu-id="35e0f-198">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP).</span></span> <span data-ttu-id="35e0f-199">Det är inställt med principer för säkra [bilagor via ATP](atp-safe-attachments.md) och [Safe Links för ATP](atp-safe-links.md) .</span><span class="sxs-lookup"><span data-stu-id="35e0f-199">It's set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="35e0f-200">Principer för säkra bifogade filer via ATP</span><span class="sxs-lookup"><span data-stu-id="35e0f-200">ATP Safe Attachments policies</span></span>

<span data-ttu-id="35e0f-201">För att konfigurera [säkerhet för säkerhets](atp-safe-attachments.md)skull för ATP måste du definiera minst en policy för säker användning av ATP.</span><span class="sxs-lookup"><span data-stu-id="35e0f-201">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="35e0f-202">Välj **Threat Management**policy [Security & Compliance Center](https://protection.office.com)  >  **Policy**  >  **Safe Attachments**i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="35e0f-202">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="35e0f-203">Välj alternativet **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-203">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="35e0f-204">Klicka på plus tecknet () i avsnittet **skydda e-postbilagor** **+** .</span><span class="sxs-lookup"><span data-stu-id="35e0f-204">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="35e0f-205">Ange följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="35e0f-205">Specify the following settings:</span></span>

   - <span data-ttu-id="35e0f-206">Skriv i rutan **namn** `Block malware` .</span><span class="sxs-lookup"><span data-stu-id="35e0f-206">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="35e0f-207">I avsnittet svar väljer du **blockera**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-207">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="35e0f-208">I avsnittet **omdirigera bilaga** väljer du alternativet **Aktivera omdirigering**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-208">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="35e0f-209">Ange e-postadressen för organisationens säkerhets administratör eller-ansvarig, som ska granska upptäckta filer.</span><span class="sxs-lookup"><span data-stu-id="35e0f-209">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

   - <span data-ttu-id="35e0f-210">I avsnittet **används för** väljer **du mottagaren**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-210">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="35e0f-211">Välj sedan din domän, Välj **Lägg till**och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-211">Then, select your domain, choose **Add**, and then **OK**.</span></span>

5. <span data-ttu-id="35e0f-212">**Spara**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-212">**Save**.</span></span>

6. <span data-ttu-id="35e0f-213">(**Rekommenderat steg**) Som global administratör eller SharePoint Online-administratör kör du cmdleten **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med parametern **DisallowInfectedFileDownload** inställd på  *True* för din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="35e0f-213">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="35e0f-214">(Detta förhindrar att personer öppnar, flyttar, kopierar eller delar filer som identifieras som skadliga.)</span><span class="sxs-lookup"><span data-stu-id="35e0f-214">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="35e0f-215">Mer information finns i [Konfigurera office 365-principer för säkra bifogade filer](set-up-atp-safe-attachments-policies.md) och [aktivera Office 365 ATP för SharePoint-, OneDrive-och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="35e0f-215">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="35e0f-216">Principer för säkraste säkerhets länkar</span><span class="sxs-lookup"><span data-stu-id="35e0f-216">ATP Safe Links policies</span></span>

<span data-ttu-id="35e0f-217">Om du vill ställa in [säkerhets Länkar för ATP](atp-safe-links.md)kan du läsa och redigera standard principen och lägga till en princip för specifika användare.</span><span class="sxs-lookup"><span data-stu-id="35e0f-217">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="35e0f-218">Välj **Threat Management**policy säkerhets länkar i [säkerhets& efterlevnad](https://protection.office.com)  >  **Policy**  >  **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-218">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="35e0f-219">Dubbelklicka på **standard** policyn.</span><span class="sxs-lookup"><span data-stu-id="35e0f-219">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="35e0f-220">I avsnittet **Använd säkra länkar i** väljer du alternativet **Microsoft 365-appar för Enterprise, Office för iOS och Android**och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-220">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="35e0f-221">Klicka på plus tecknet () i avsnittet **principer som gäller för specifika mottagare** **+** .</span><span class="sxs-lookup"><span data-stu-id="35e0f-221">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="35e0f-222">Ange följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="35e0f-222">Specify the following settings:</span></span>

   - <span data-ttu-id="35e0f-223">Skriv ett namn i rutan **namn** , till exempel `Safe Links` .</span><span class="sxs-lookup"><span data-stu-id="35e0f-223">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="35e0f-224">I avsnittet **Välj åtgärd väljer du** **på**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-224">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="35e0f-225">Välj de här alternativen:</span><span class="sxs-lookup"><span data-stu-id="35e0f-225">Select these options:</span></span>

     - <span data-ttu-id="35e0f-226">**Använda säkra bifogade filer för att skanna nedladdnings Bart innehåll**</span><span class="sxs-lookup"><span data-stu-id="35e0f-226">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="35e0f-227">**Använda säkra länkar till e-postmeddelanden som skickas inom organisationen**</span><span class="sxs-lookup"><span data-stu-id="35e0f-227">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="35e0f-228">**Tillåt inte att användare klickar genom säkra länkar till ursprunglig URL**</span><span class="sxs-lookup"><span data-stu-id="35e0f-228">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="35e0f-229">I avsnittet **används för** väljer **du mottagaren**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-229">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="35e0f-230">Välj sedan din domän, Välj **Lägg till**och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-230">Then, select your domain, choose **Add**, and then **OK**.</span></span>

6. <span data-ttu-id="35e0f-231">**Spara**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-231">**Save**.</span></span>

<span data-ttu-id="35e0f-232">Mer information finns i [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md)(Konfigurera Office 365 ATP-principer för säkra länkar).</span><span class="sxs-lookup"><span data-stu-id="35e0f-232">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads"></a><span data-ttu-id="35e0f-233">Del 5 – aktivera ATP för arbets belastning för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35e0f-233">Part 5 - Turn on ATP for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>

<span data-ttu-id="35e0f-234">Arbets belastningar som SharePoint, OneDrive och Teams är byggda för samarbete.</span><span class="sxs-lookup"><span data-stu-id="35e0f-234">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="35e0f-235">Genom att använda ATP kan du blockera och upptäcka filer som identifieras som skadliga på grupp webbplatser och dokument bibliotek.</span><span class="sxs-lookup"><span data-stu-id="35e0f-235">Using ATP helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="35e0f-236">Du kan läsa mer om hur det fungerar [här](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="35e0f-236">You can read more about how that works [here](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams?view=o365-worldwide).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35e0f-237">**Innan du påbörjar den här proceduren bör du kontrol lera att gransknings loggning redan är aktiverat för din Microsoft 365-miljö**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-237">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="35e0f-238">Det gör du vanligt vis av någon som har rollen gransknings loggar som tilldelats i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="35e0f-238">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="35e0f-239">Mer information finns i [Aktivera eller inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md)!</span><span class="sxs-lookup"><span data-stu-id="35e0f-239">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="35e0f-240">Gå till <https://protection.office.com> och logga in med ditt arbets-eller skol konto.</span><span class="sxs-lookup"><span data-stu-id="35e0f-240">Go to <https://protection.office.com>, and sign in with your work or school account.</span></span>

2. <span data-ttu-id="35e0f-241">I det vänstra navigerings **fältet under säkerhets**& Compliance Center väljer du **policy** \> **Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-241">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![Välj Threat Management policy i Center för säkerhet & efterlevnad \>](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="35e0f-243">Välj **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-243">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![Aktivera avancerat skydd för SharePoint Online, OneDrive för företag och Microsoft Teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="35e0f-245">**Spara**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-245">**Save**.</span></span>

5. <span data-ttu-id="35e0f-246">Granska (och, om tillämpligt, redigera) organisationens principer för [säkert bifogade filer](set-up-atp-safe-attachments-policies.md) och [säkra länkar](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="35e0f-246">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="35e0f-247">Lämpligt Som global administratör eller SharePoint Online-administratör kör du cmdleten **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med parametern _DisallowInfectedFileDownload_ inställd på `$true` .</span><span class="sxs-lookup"><span data-stu-id="35e0f-247">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.</span></span>

   - <span data-ttu-id="35e0f-248">`$true` blockerar alla åtgärder (förutom borttagning) för identifierade filer.</span><span class="sxs-lookup"><span data-stu-id="35e0f-248">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="35e0f-249">Personer kan inte öppna, flytta, kopiera eller dela identifierade filer.</span><span class="sxs-lookup"><span data-stu-id="35e0f-249">People cannot open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="35e0f-250">`$false` alla åtgärder förutom Delete och nedladdning blockeras.</span><span class="sxs-lookup"><span data-stu-id="35e0f-250">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="35e0f-251">Andra kan välja att acceptera risken och hämta en identifierad fil.</span><span class="sxs-lookup"><span data-stu-id="35e0f-251">People can choose to accept the risk and download a detected file.</span></span>

   > [!TIP]
   > <span data-ttu-id="35e0f-252">Mer information om hur du använder PowerShell med Microsoft 365 finns i [Hantera Microsoft 365 med PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="35e0f-252">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).</span></span>

7. <span data-ttu-id="35e0f-253">Tillåt upp till 30 minuter för att ändringarna ska spridas till alla Microsoft 365-datacenter.</span><span class="sxs-lookup"><span data-stu-id="35e0f-253">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="35e0f-254">Konfigurera aviseringar för identifierade filer</span><span class="sxs-lookup"><span data-stu-id="35e0f-254">Now set up alerts for detected files</span></span>

<span data-ttu-id="35e0f-255">Om du vill få aviseringar när en fil i SharePoint Online, OneDrive för företag eller Microsoft Teams har identifierats som skadlig kan du ställa in en avisering.</span><span class="sxs-lookup"><span data-stu-id="35e0f-255">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="35e0f-256">I fönstret [säkerhets & efterlevnad](https://protection.office.com)väljer du **aviseringar** \> **Hantera aviseringar**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-256">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="35e0f-257">Välj **ny aviserings princip**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-257">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="35e0f-258">Ange ett namn för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="35e0f-258">Specify a name for the alert.</span></span> <span data-ttu-id="35e0f-259">Du kan till exempel skriva in skadliga filer i bibliotek.</span><span class="sxs-lookup"><span data-stu-id="35e0f-259">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="35e0f-260">Ange en beskrivning av aviseringen.</span><span class="sxs-lookup"><span data-stu-id="35e0f-260">Type a description for the alert.</span></span> <span data-ttu-id="35e0f-261">Du kan till exempel skriva meddelanden administratörer när skadliga filer upptäcks i SharePoint Online, OneDrive eller Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="35e0f-261">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="35e0f-262">I avsnittet **Skicka aviseringen när...** anger du:</span><span class="sxs-lookup"><span data-stu-id="35e0f-262">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="35e0f-263">a.</span><span class="sxs-lookup"><span data-stu-id="35e0f-263">a.</span></span> <span data-ttu-id="35e0f-264">Välj **upptäckt skadlig kod i filen**i listan **aktiviteter** .</span><span class="sxs-lookup"><span data-stu-id="35e0f-264">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="35e0f-265">b.</span><span class="sxs-lookup"><span data-stu-id="35e0f-265">b.</span></span> <span data-ttu-id="35e0f-266">Lämna fältet **användare** tomma.</span><span class="sxs-lookup"><span data-stu-id="35e0f-266">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="35e0f-267">I avsnittet **Skicka aviseringen till... väljer du** en eller flera globala administratörer, säkerhets administratörer eller säkerhets läsare som ska få avisering när en skadlig fil identifieras.</span><span class="sxs-lookup"><span data-stu-id="35e0f-267">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="35e0f-268">**Spara**.</span><span class="sxs-lookup"><span data-stu-id="35e0f-268">**Save**.</span></span>

<span data-ttu-id="35e0f-269">Om du vill veta mer om aviseringar läser [du skapa aktivitets aviseringar i avsnittet säkerhets & efterlevnad](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="35e0f-269">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="35e0f-270">När du är klar med konfigurationen kan du använda de här länkarna för att starta arbets belastnings undersökningar:</span><span class="sxs-lookup"><span data-stu-id="35e0f-270">When you're finished configuring, use these links to start workload investigations:</span></span>
>
> - [<span data-ttu-id="35e0f-271">Visa information om skadliga filer som identifieras i SharePoint, OneDrive eller Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35e0f-271">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
> - [<span data-ttu-id="35e0f-272">Vad kan jag göra? när en skadlig fil hittas i SharePoint Online, OneDrive eller Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35e0f-272">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
> - [<span data-ttu-id="35e0f-273">Hantera meddelanden och filer i karantän som administratör i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="35e0f-273">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="35e0f-274">Del 6 – ytterligare inställningar att konfigurera</span><span class="sxs-lookup"><span data-stu-id="35e0f-274">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="35e0f-275">Förutom att konfigurera skydd från skadlig program vara, skadliga URL-adresser och filer, nätfiske och skräp post rekommenderar vi att du konfigurerar automatisk rensning av en tom timme.</span><span class="sxs-lookup"><span data-stu-id="35e0f-275">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="35e0f-276">Automatisk rensning av Tom timme för e-post i EOP</span><span class="sxs-lookup"><span data-stu-id="35e0f-276">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="35e0f-277">[Automatisk rensning för noll-timme](zero-hour-auto-purge.md) är tillgängligt i abonnemang som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="35e0f-277">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="35e0f-278">Detta skydd är aktiverat som standard. men följande villkor måste uppfyllas för att skydd ska vara aktivt:</span><span class="sxs-lookup"><span data-stu-id="35e0f-278">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="35e0f-279">Spam åtgärder är inställda på att **flytta meddelanden till mappen skräp post** i [principer för skräp post](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="35e0f-279">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="35e0f-280">Användare har förbehållit sina standardinställningar för [skräp](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)post och har inte avaktiverat skydd mot skräp post.</span><span class="sxs-lookup"><span data-stu-id="35e0f-280">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="35e0f-281">Mer information finns i [nollställning av automatiskt skydd mot skräp post och skadlig program vara](zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="35e0f-281">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="35e0f-282">Åtgärder efter installationen och nästa steg</span><span class="sxs-lookup"><span data-stu-id="35e0f-282">Post-setup tasks and next steps</span></span>

<span data-ttu-id="35e0f-283">När du har konfigurerat hotets skydds funktioner ser du till att övervaka hur funktionerna fungerar!</span><span class="sxs-lookup"><span data-stu-id="35e0f-283">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="35e0f-284">Granska och omarbeta dina principer så att de gör det du behöver dem.</span><span class="sxs-lookup"><span data-stu-id="35e0f-284">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="35e0f-285">Titta också efter nya funktioner och tjänst uppdateringar som kan lägga till ett värde.</span><span class="sxs-lookup"><span data-stu-id="35e0f-285">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="35e0f-286">Vad kan jag göra?</span><span class="sxs-lookup"><span data-stu-id="35e0f-286">What to do</span></span>|<span data-ttu-id="35e0f-287">Resurser för att få mer information</span><span class="sxs-lookup"><span data-stu-id="35e0f-287">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="35e0f-288">Se hur hot Protection-funktioner fungerar för din organisation genom att visa rapporter</span><span class="sxs-lookup"><span data-stu-id="35e0f-288">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="35e0f-289">Säkerhets instrument panel</span><span class="sxs-lookup"><span data-stu-id="35e0f-289">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="35e0f-290">Säkerhets rapporter för e-post</span><span class="sxs-lookup"><span data-stu-id="35e0f-290">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="35e0f-291">Rapporter för Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="35e0f-291">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="35e0f-292">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="35e0f-292">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="35e0f-293">Regelbundet granska och omarbeta dina skydds principer om det behövs</span><span class="sxs-lookup"><span data-stu-id="35e0f-293">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="35e0f-294">Säkra Poäng</span><span class="sxs-lookup"><span data-stu-id="35e0f-294">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="35e0f-295">Smarta rapporter och insikter</span><span class="sxs-lookup"><span data-stu-id="35e0f-295">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="35e0f-296">Microsoft 365 hot-och svars funktioner</span><span class="sxs-lookup"><span data-stu-id="35e0f-296">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="35e0f-297">Titta efter nya funktioner och tjänste uppdateringar</span><span class="sxs-lookup"><span data-stu-id="35e0f-297">Watch for new features and service updates</span></span>|[<span data-ttu-id="35e0f-298">Standard-och riktade versions alternativ</span><span class="sxs-lookup"><span data-stu-id="35e0f-298">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="35e0f-299">Meddelandecentral</span><span class="sxs-lookup"><span data-stu-id="35e0f-299">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="35e0f-300">Översikt över Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="35e0f-300">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="35e0f-301">Tjänst beskrivningar</span><span class="sxs-lookup"><span data-stu-id="35e0f-301">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="35e0f-302">Lär dig mer om rekommenderade standard-och strikta säkerhetskonfigurationer för EOP och ATP</span><span class="sxs-lookup"><span data-stu-id="35e0f-302">Learn the details about recommended Standard and Strict security configurations for EOP and ATP</span></span> | [<span data-ttu-id="35e0f-303">Rekommenderade inställningar för EOP och Office 365 säkerhet för ATP</span><span class="sxs-lookup"><span data-stu-id="35e0f-303">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) |
