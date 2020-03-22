---
title: Skydda mot hot i Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 05/09/2019
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Använd den här artikeln som en guide för att konfigurera dina hotskyddsfunktioner nu.
ms.openlocfilehash: da920083b521e905633473efbabc5930ad7a6770
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895317"
---
# <a name="protect-against-threats-in-office-365"></a><span data-ttu-id="62d78-103">Skydda mot hot i Office 365</span><span class="sxs-lookup"><span data-stu-id="62d78-103">Protect against threats in Office 365</span></span>

<span data-ttu-id="62d78-104">Office 365 innehåller en mängd olika hotskyddsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="62d78-104">Office 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="62d78-105">Här är en snabbstartsguide som du kan använda som checklista för att se till att dina hotskyddsfunktioner är konfigurerade för din organisation.</span><span class="sxs-lookup"><span data-stu-id="62d78-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="62d78-106">Om du inte har använt hotskyddsfunktionerna i Office 365 tidigare, eller om du bara inte är säker på var du ska börja, använder du följande vägledning som utgångspunkt.</span><span class="sxs-lookup"><span data-stu-id="62d78-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62d78-107">**De första rekommenderade inställningarna ingår för varje typ av princip, men många alternativ är tillgängliga och du kan justera inställningarna så att de uppfyller organisationens behov**.</span><span class="sxs-lookup"><span data-stu-id="62d78-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="62d78-108">Tillåt cirka 30 minuter för dina principer eller ändringar att arbeta sig igenom ditt datacenter.</span><span class="sxs-lookup"><span data-stu-id="62d78-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="62d78-109">Krav</span><span class="sxs-lookup"><span data-stu-id="62d78-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="62d78-110">Prenumerationer</span><span class="sxs-lookup"><span data-stu-id="62d78-110">Subscriptions</span></span>

<span data-ttu-id="62d78-111">Hotskyddsfunktioner ingår i alla Office 365-prenumerationer. Vissa prenumerationer innehåller dock mer avancerade funktioner.</span><span class="sxs-lookup"><span data-stu-id="62d78-111">Threat protection features are included in all Office 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="62d78-112">I följande tabell visas de skyddsfunktioner som ingår i den här artikeln tillsammans med minimikraven för prenumeration.</span><span class="sxs-lookup"><span data-stu-id="62d78-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span><br/>

|<span data-ttu-id="62d78-113">Typ av skydd</span><span class="sxs-lookup"><span data-stu-id="62d78-113">Protection type</span></span>|<span data-ttu-id="62d78-114">Abonnemangskrav</span><span class="sxs-lookup"><span data-stu-id="62d78-114">Subscription requirement</span></span>|
|---------|---------|
|<span data-ttu-id="62d78-115">Skydd mot skadlig kod</span><span class="sxs-lookup"><span data-stu-id="62d78-115">Anti-malware protection</span></span>|<span data-ttu-id="62d78-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)</span><span class="sxs-lookup"><span data-stu-id="62d78-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="62d78-117">Skydd mot skadliga webbadresser och filer i e-post- och Office-dokument</span><span class="sxs-lookup"><span data-stu-id="62d78-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="62d78-118">[Office 365 Avancerat skydd mot hot](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span><span class="sxs-lookup"><span data-stu-id="62d78-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="62d78-119">Skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="62d78-119">Anti-phishing protection</span></span>|[<span data-ttu-id="62d78-120">EOP (på andra sätt)</span><span class="sxs-lookup"><span data-stu-id="62d78-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="62d78-121">Avancerat skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="62d78-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="62d78-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="62d78-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="62d78-123">Skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="62d78-123">Anti-spam protection</span></span>|[<span data-ttu-id="62d78-124">EOP (på andra sätt)</span><span class="sxs-lookup"><span data-stu-id="62d78-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="62d78-125">Nolltimmars automatisk rensning (för e-post)</span><span class="sxs-lookup"><span data-stu-id="62d78-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="62d78-126">EOP (på andra sätt)</span><span class="sxs-lookup"><span data-stu-id="62d78-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="62d78-127">Granskningsloggning (detta används för rapportering)</span><span class="sxs-lookup"><span data-stu-id="62d78-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="62d78-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="62d78-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="62d78-129">Roller och behörigheter</span><span class="sxs-lookup"><span data-stu-id="62d78-129">Roles and permissions</span></span>

<span data-ttu-id="62d78-130">Du måste tilldelas en lämplig roll för att konfigurera principer i [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="62d78-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="62d78-131">Följande tabell innehåller några exempel:</span><span class="sxs-lookup"><span data-stu-id="62d78-131">The following table includes some examples:</span></span>

|<span data-ttu-id="62d78-132">Roll eller rollgrupp</span><span class="sxs-lookup"><span data-stu-id="62d78-132">Role or role group</span></span>|<span data-ttu-id="62d78-133">Här kan du läsa mer</span><span class="sxs-lookup"><span data-stu-id="62d78-133">Where to learn more</span></span>|
|---------|---------|
|<span data-ttu-id="62d78-134">Global administratör för Office 365</span><span class="sxs-lookup"><span data-stu-id="62d78-134">Office 365 Global Administrator</span></span>|[<span data-ttu-id="62d78-135">Om Office 365-administratörsroller</span><span class="sxs-lookup"><span data-stu-id="62d78-135">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="62d78-136">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="62d78-136">Security Administrator</span></span>|[<span data-ttu-id="62d78-137">Administratörsrollbehörigheter i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="62d78-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="62d78-138">Hantering av Exchange Online-organisation</span><span class="sxs-lookup"><span data-stu-id="62d78-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="62d78-139">Behörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="62d78-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="62d78-140">Och</span><span class="sxs-lookup"><span data-stu-id="62d78-140">and</span></span><br> [<span data-ttu-id="62d78-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="62d78-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|

<span data-ttu-id="62d78-142">Mer information finns [i Behörigheter i Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="62d78-142">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="62d78-143">Del 1 - Skydd mot skadlig kod</span><span class="sxs-lookup"><span data-stu-id="62d78-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="62d78-144">[Skydd mot skadlig kod](anti-malware-protection.md) är tillgängligt i prenumerationer som inkluderar [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="62d78-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="62d78-145">Välj Policy mot**skadlig kod**för **Threat management** > **Policy** > & säkerhet i [säkerhetsorganisationscenter.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="62d78-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="62d78-146">Dubbelklicka på **standardprincipen** och välj sedan **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="62d78-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="62d78-147">Ange följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62d78-147">Specify the following settings:</span></span>

    - <span data-ttu-id="62d78-148">Behåll **Malware Detection Response** standardinställningen **nr.**</span><span class="sxs-lookup"><span data-stu-id="62d78-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="62d78-149">I avsnittet **Filter för vanliga typer av bifogade filer** väljer du **På**.</span><span class="sxs-lookup"><span data-stu-id="62d78-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="62d78-150">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="62d78-150">Click **Save**.</span></span>

<span data-ttu-id="62d78-151">Mer information om policyalternativ mot skadlig kod finns i [Konfigurera policyer mot skadlig kod](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="62d78-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="62d78-152">Del 2 - Skydd mot skadliga webbadresser och filer</span><span class="sxs-lookup"><span data-stu-id="62d78-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="62d78-153">Tidsberedskapsskydd mot skadliga webbadresser och filer är tillgängligt i prenumerationer som innehåller [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) och konfigureras via [ATP-principer för säkra bilagor](atp-safe-attachments.md) och [ATP-principer](atp-safe-links.md) för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="62d78-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="62d78-154">ATP-principer för säkra bilagor</span><span class="sxs-lookup"><span data-stu-id="62d78-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="62d78-155">Om du vill ställa in [ATP-säkra bilagor](atp-safe-attachments.md)måste du definiera minst en ATP-princip för säkra bilagor.</span><span class="sxs-lookup"><span data-stu-id="62d78-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="62d78-156">I [Security & Compliance Center](https://protection.office.com)väljer du**ATP-säkra atp-betrodda bilagor**för **hothanteringsprincip.** > **Policy** > </span><span class="sxs-lookup"><span data-stu-id="62d78-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="62d78-157">Välj alternativet **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="62d78-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="62d78-158">Klicka på plustecknet ( i avsnittet**+** **Skydda e-postbilagor).**</span><span class="sxs-lookup"><span data-stu-id="62d78-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="62d78-159">Ange följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62d78-159">Specify the following settings:</span></span>

   - <span data-ttu-id="62d78-160">Skriv `Block malware`i rutan **Namn** .</span><span class="sxs-lookup"><span data-stu-id="62d78-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="62d78-161">I svarsavsnittet väljer du **Blockera**.</span><span class="sxs-lookup"><span data-stu-id="62d78-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="62d78-162">I avsnittet **Omdirigera bifogad fil** väljer du alternativet **Aktivera omdirigering**och anger sedan e-postadressen för organisationens säkerhetsadministratör eller operatör som ska granska identifierade filer.</span><span class="sxs-lookup"><span data-stu-id="62d78-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="62d78-163">I avsnittet **Tillämpad** på väljer du **Den mottagande domänen är**.</span><span class="sxs-lookup"><span data-stu-id="62d78-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="62d78-164">Välj sedan din domän, välj **Lägg till**och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="62d78-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="62d78-165">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="62d78-165">Click **Save**.</span></span>

6. <span data-ttu-id="62d78-166">**(Rekommenderat ytterligare steg)** Som global administratör eller SharePoint **[Online-administratör kör cmdlet set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med parametern **DisallowInfectedFileDownload** inställd på *true* för din Office 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="62d78-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="62d78-167">(Detta förhindrar att personer öppnar, flyttar, kopierar eller delar filer som identifieras som skadliga.)</span><span class="sxs-lookup"><span data-stu-id="62d78-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="62d78-168">Mer information finns i Konfigurera principer för [betrodda anslutningspunkter för Office 365 ATP](set-up-atp-safe-attachments-policies.md) och [Aktivera Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="62d78-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="62d78-169">ATP-principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="62d78-169">ATP Safe Links policies</span></span>

<span data-ttu-id="62d78-170">Om du vill konfigurera [atp-säkra länkar](atp-safe-links.md)granskar och redigerar du standardprincipen och lägger till en princip för specifika användare.</span><span class="sxs-lookup"><span data-stu-id="62d78-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="62d78-171">I [Security & Compliance Center](https://protection.office.com)väljer du**ATP Safe Links**för **hothanteringsprincip.** > **Policy** > </span><span class="sxs-lookup"><span data-stu-id="62d78-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="62d78-172">Dubbelklicka **Default** på standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="62d78-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="62d78-173">I avsnittet **Använd säkra länkar i** väljer du alternativet Office **365 ProPlus, Office för iOS och Android**och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="62d78-173">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="62d78-174">Klicka **på** plustecknet (**+**).</span><span class="sxs-lookup"><span data-stu-id="62d78-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="62d78-175">Ange följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62d78-175">Specify the following settings:</span></span>

   - <span data-ttu-id="62d78-176">Skriv ett namn i rutan **Namn,** till exempel `Safe Links`.</span><span class="sxs-lookup"><span data-stu-id="62d78-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="62d78-177">Välj **På**i avsnittet **Välj åtgärd** .</span><span class="sxs-lookup"><span data-stu-id="62d78-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="62d78-178">Välj de här alternativen:</span><span class="sxs-lookup"><span data-stu-id="62d78-178">Select these options:</span></span>

     - <span data-ttu-id="62d78-179">**Använd säkra bilagor för att skanna nedladdningsbart innehåll**</span><span class="sxs-lookup"><span data-stu-id="62d78-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="62d78-180">**Använda säkra länkar till e-postmeddelanden som skickas inom organisationen**</span><span class="sxs-lookup"><span data-stu-id="62d78-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="62d78-181">**Låt inte användare klicka igenom säkra länkar till den ursprungliga webbadressen**</span><span class="sxs-lookup"><span data-stu-id="62d78-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="62d78-182">I avsnittet **Tillämpad** på väljer du **Den mottagande domänen är**.</span><span class="sxs-lookup"><span data-stu-id="62d78-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="62d78-183">Välj sedan din domän, välj **Lägg till**och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="62d78-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="62d78-184">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="62d78-184">Click **Save**.</span></span>

<span data-ttu-id="62d78-185">Mer information finns i [Konfigurera principer för betrodda länkar för Office 365 ATP](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="62d78-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="62d78-186">Del 3 - Skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="62d78-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="62d78-187">[Skydd mot nätfiske](anti-phishing-protection.md) är tillgängligt i prenumerationer som inkluderar [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="62d78-187">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="62d78-188">Avancerat skydd mot nätfiske finns i [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="62d78-188">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="62d78-189">I följande procedur beskrivs hur du konfigurerar en ATP-princip mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="62d78-189">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="62d78-190">Stegen är liknande för att konfigurera en anti-phishing-policy (utan ATP).</span><span class="sxs-lookup"><span data-stu-id="62d78-190">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="62d78-191">I [Security & Compliance Center](https://protection.office.com)väljer du**ATP-principen\*\*\*\*Policy** >  **mot hothantering.** > </span><span class="sxs-lookup"><span data-stu-id="62d78-191">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="62d78-192">Klicka på **Standardprincip**.</span><span class="sxs-lookup"><span data-stu-id="62d78-192">Click **Default policy**.</span></span>

3. <span data-ttu-id="62d78-193">Klicka på **Redigera**i avsnittet **Personifiering** och ange sedan följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62d78-193">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="62d78-194">Aktivera skyddet på fliken **Lägg till användare för att skydda.**</span><span class="sxs-lookup"><span data-stu-id="62d78-194">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="62d78-195">Lägg sedan till användare, till exempel organisationens styrelseledamöter, din VD, EKONOMI och ANDRA ledande befattningshavare.</span><span class="sxs-lookup"><span data-stu-id="62d78-195">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="62d78-196">(Du kan skriva en enskild e-postadress eller klicka för att visa en lista.)</span><span class="sxs-lookup"><span data-stu-id="62d78-196">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="62d78-197">På fliken **Lägg till domäner för att skydda** aktiverar du Automatiskt de **domäner jag äger**.</span><span class="sxs-lookup"><span data-stu-id="62d78-197">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="62d78-198">Om du har anpassade domäner, lägg till dessa också.</span><span class="sxs-lookup"><span data-stu-id="62d78-198">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="62d78-199">På fliken **Åtgärder** väljer du **Karantän för både** den **personifierade användaren** och de **personifierade domänalternativen.**</span><span class="sxs-lookup"><span data-stu-id="62d78-199">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="62d78-200">Dessutom aktiverar du säkerhetstips för personifiering.</span><span class="sxs-lookup"><span data-stu-id="62d78-200">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="62d78-201">Kontrollera att postlådeinformation är aktiverat på fliken **Postlådeinformation.**</span><span class="sxs-lookup"><span data-stu-id="62d78-201">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="62d78-202">Dessutom aktiverar du informationsbaserat personifieringsskydd för postlådan.</span><span class="sxs-lookup"><span data-stu-id="62d78-202">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="62d78-203">Välj **Karantän meddelandet** **i om e-postmeddelandet skickas av en personifierad användarlista** .</span><span class="sxs-lookup"><span data-stu-id="62d78-203">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="62d78-204">På fliken **Lägg till betrodda avsändare och domäner** anger du alla betrodda avsändare eller domäner som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="62d78-204">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="62d78-205">Klicka på **Spara**när du har granskat inställningarna på fliken **Granska dina inställningar** .</span><span class="sxs-lookup"><span data-stu-id="62d78-205">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="62d78-206">Klicka på **Redigera**i avsnittet **Spoof** och ange sedan följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62d78-206">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="62d78-207">Kontrollera att förfalskningsskydd är aktiverat på fliken **Spoofing** filter settings.</span><span class="sxs-lookup"><span data-stu-id="62d78-207">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="62d78-208">Välj Karantän meddelandet **på**fliken **Åtgärder** .</span><span class="sxs-lookup"><span data-stu-id="62d78-208">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="62d78-209">Klicka på **Spara**när du har granskat inställningarna på fliken **Granska dina inställningar** .</span><span class="sxs-lookup"><span data-stu-id="62d78-209">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="62d78-210">(Om du inte har gjort några ändringar klickar du på **Avbryt**.)</span><span class="sxs-lookup"><span data-stu-id="62d78-210">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="62d78-211">Stäng sidan standardinställningsinställningar.</span><span class="sxs-lookup"><span data-stu-id="62d78-211">Close the default policy settings page.</span></span>

<span data-ttu-id="62d78-212">Mer information om dina policyalternativ mot nätfiske finns i [Konfigurera policyer mot nätfiske](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="62d78-212">To learn more about your anti-phishing policy options, see [Set up anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="62d78-213">Del 4 - Skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="62d78-213">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="62d78-214">[Skydd mot skräppost](anti-spam-protection.md) är tillgängligt i prenumerationer som inkluderar [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="62d78-214">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="62d78-215">Välj Policy mot **Threat management** > **Policy** > **skräppost**för & säkerhet i [säkerhetsorganisationscenter.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="62d78-215">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="62d78-216">Aktivera **Anpassade inställningar** på fliken **Anpassad.**</span><span class="sxs-lookup"><span data-stu-id="62d78-216">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="62d78-217">Expandera **standardprincip för skräppostfilter,** klicka på **Redigera princip**och ange sedan följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="62d78-217">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="62d78-218">I avsnittet **Skräppost och massåtgärder** anger du tröskelvärdet till ett värde av 5 eller 6.</span><span class="sxs-lookup"><span data-stu-id="62d78-218">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="62d78-219">Granska (och vid behov redigera) tillåtna avsändare och domäner i avsnittet **Tillåt listor.**</span><span class="sxs-lookup"><span data-stu-id="62d78-219">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="62d78-220">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="62d78-220">Click **Save**.</span></span>

<span data-ttu-id="62d78-221">Mer information om alternativ för anti-spam finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="62d78-221">To learn more about your anti-spam policy options, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="62d78-222">Del 5 - Ytterligare inställningar för att konfigurera</span><span class="sxs-lookup"><span data-stu-id="62d78-222">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="62d78-223">Förutom att konfigurera skydd mot skadlig kod, skadliga webbadresser och filer, nätfiske och skräppost rekommenderar vi att du konfigurerar inställningarna för automatisk rensning och granskning av nolltimmarstimmar.</span><span class="sxs-lookup"><span data-stu-id="62d78-223">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="62d78-224">Nolltimmars automatisk rensning för e-post</span><span class="sxs-lookup"><span data-stu-id="62d78-224">Zero-hour auto purge for email</span></span>

<span data-ttu-id="62d78-225">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) är tillgängligt i prenumerationer som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="62d78-225">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="62d78-226">Det här skyddet är aktiverat som standard. Följande villkor måste dock vara uppfyllda för att skyddet skall vara i kraft:</span><span class="sxs-lookup"><span data-stu-id="62d78-226">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="62d78-227">Skräppoståtgärder är inställda på **Flytta meddelande till skräppostmapp** i [anti-spam-policyer](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="62d78-227">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="62d78-228">Användare har behållit sina [standardinställningar för skräppost](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)och har inte inaktiverat skydd för skräppost.</span><span class="sxs-lookup"><span data-stu-id="62d78-228">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="62d78-229">Mer information finns i [Zero-hour auto purge - skydd mot skräppost och skadlig kod](zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="62d78-229">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="62d78-230">Revisionsloggning för rapportering och utredning</span><span class="sxs-lookup"><span data-stu-id="62d78-230">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="62d78-231">Granskningsloggning är tillgängligt i prenumerationer som inkluderar [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span><span class="sxs-lookup"><span data-stu-id="62d78-231">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="62d78-232">För att kunna visa data i rapporter om skydd mot hot, till exempel [säkerhetspanelen,](security-dashboard.md) [e-postsäkerhetsrapporter](view-email-security-reports.md)och [Utforskaren,](threat-explorer.md)måste granskningsloggning vara aktiverat för din organisation.</span><span class="sxs-lookup"><span data-stu-id="62d78-232">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="62d78-233">Mer information finns i [Aktivera eller inaktivera granskningsloggsökning för Office 365.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="62d78-233">To learn more, see [Turn Office 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="62d78-234">Uppgifter efter installationen</span><span class="sxs-lookup"><span data-stu-id="62d78-234">Post-setup tasks</span></span>

<span data-ttu-id="62d78-235">När du har konfigurerat hotskyddsfunktionerna ska du se till att övervaka hur dessa funktioner fungerar, granska och ändra dina principer efter behov och titta efter nya funktioner och tjänstuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="62d78-235">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

|<span data-ttu-id="62d78-236">Vad du ska göra</span><span class="sxs-lookup"><span data-stu-id="62d78-236">What to do</span></span>|<span data-ttu-id="62d78-237">Resurser för att lära dig mer</span><span class="sxs-lookup"><span data-stu-id="62d78-237">Resources to learn more</span></span>|
|---------|---------|
|<span data-ttu-id="62d78-238">Se hur hotskyddsfunktioner fungerar för din organisation genom att visa rapporter</span><span class="sxs-lookup"><span data-stu-id="62d78-238">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="62d78-239">Instrumentpanel för säkerhet</span><span class="sxs-lookup"><span data-stu-id="62d78-239">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="62d78-240">Säkerhetsrapporter för e-post</span><span class="sxs-lookup"><span data-stu-id="62d78-240">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="62d78-241">Rapporter för OFFICE 365 ATP</span><span class="sxs-lookup"><span data-stu-id="62d78-241">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="62d78-242">Hot Explorer</span><span class="sxs-lookup"><span data-stu-id="62d78-242">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="62d78-243">Granska och revidera regelbundet dina policyer för hotskydd efter behov</span><span class="sxs-lookup"><span data-stu-id="62d78-243">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="62d78-244">Säkra poäng</span><span class="sxs-lookup"><span data-stu-id="62d78-244">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="62d78-245">Smarta rapporter och insikter</span><span class="sxs-lookup"><span data-stu-id="62d78-245">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="62d78-246">Funktioner för utredning och svar av hot i Office 365</span><span class="sxs-lookup"><span data-stu-id="62d78-246">Office 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="62d78-247">Håll utkik efter nya funktioner och serviceuppdateringar</span><span class="sxs-lookup"><span data-stu-id="62d78-247">Watch for new features and service updates</span></span>|[<span data-ttu-id="62d78-248">Standard- och målutgivningsalternativ</span><span class="sxs-lookup"><span data-stu-id="62d78-248">Standard and Targeted release options</span></span>](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[<span data-ttu-id="62d78-249">Meddelandecentral</span><span class="sxs-lookup"><span data-stu-id="62d78-249">Message Center</span></span>](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[<span data-ttu-id="62d78-250">Översikt över Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62d78-250">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="62d78-251">Beskrivningar av tjänsten</span><span class="sxs-lookup"><span data-stu-id="62d78-251">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
