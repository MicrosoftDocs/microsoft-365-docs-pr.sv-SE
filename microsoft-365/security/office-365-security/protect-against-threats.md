---
title: Skydda mot hot
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa om hotets skydd i Microsoft 365 och konfigurera hur det ska användas för din organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8c2786ebda18b5730e1cbe93316f0d6cc319f6a9
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656641"
---
# <a name="protect-against-threats"></a><span data-ttu-id="0e8d6-103">Skydda mot hot</span><span class="sxs-lookup"><span data-stu-id="0e8d6-103">Protect against threats</span></span>

<span data-ttu-id="0e8d6-104">Microsoft 365 innehåller flera olika skydds funktioner.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-104">Microsoft 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="0e8d6-105">Här är en snabb start guide som du kan använda som check lista för att kontrol lera att dina skydds funktioner är inställda för din organisation.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="0e8d6-106">Om du är nybörjare i Office 365, eller om du inte är säker på var du ska börja, kan du använda följande vägledning som utgångs punkt.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e8d6-107">**Initiala rekommenderade inställningar är tillgängliga för alla typer av principer, men du kan också ändra dina inställningar för att uppfylla specifika organisationens behov**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="0e8d6-108">Tillåt cirka 30 minuter för dina principer eller ändringar för att fungera på ett annat sätt via ditt data Center.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="0e8d6-109">Krav</span><span class="sxs-lookup"><span data-stu-id="0e8d6-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="0e8d6-110">Prenumerera</span><span class="sxs-lookup"><span data-stu-id="0e8d6-110">Subscriptions</span></span>

<span data-ttu-id="0e8d6-111">Hot Protection-funktioner ingår i alla Microsoft 365-abonnemang; Vissa abonnemang innehåller dessutom mer avancerade funktioner.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-111">Threat protection features are included in all Microsoft 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="0e8d6-112">I följande tabell finns de skydds funktioner som ingår i den här artikeln tillsammans med de minsta abonnemangs kraven.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span>

****

|<span data-ttu-id="0e8d6-113">Skydds typ</span><span class="sxs-lookup"><span data-stu-id="0e8d6-113">Protection type</span></span>|<span data-ttu-id="0e8d6-114">Abonnemangs behov</span><span class="sxs-lookup"><span data-stu-id="0e8d6-114">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="0e8d6-115">Skydd mot skadlig kod</span><span class="sxs-lookup"><span data-stu-id="0e8d6-115">Anti-malware protection</span></span>|<span data-ttu-id="0e8d6-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span><span class="sxs-lookup"><span data-stu-id="0e8d6-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="0e8d6-117">Skydda från skadliga URL-adresser och filer i e-post-och Office-dokument</span><span class="sxs-lookup"><span data-stu-id="0e8d6-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="0e8d6-118">[Office 365 Avancerat skydd](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span><span class="sxs-lookup"><span data-stu-id="0e8d6-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="0e8d6-119">Skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="0e8d6-119">Anti-phishing protection</span></span>|[<span data-ttu-id="0e8d6-120">EOP</span><span class="sxs-lookup"><span data-stu-id="0e8d6-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="0e8d6-121">Avancerat skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="0e8d6-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="0e8d6-122">Skaffa Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="0e8d6-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="0e8d6-123">Skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="0e8d6-123">Anti-spam protection</span></span>|[<span data-ttu-id="0e8d6-124">EOP</span><span class="sxs-lookup"><span data-stu-id="0e8d6-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="0e8d6-125">Automatisk rensning av Tom timme (för e-post)</span><span class="sxs-lookup"><span data-stu-id="0e8d6-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="0e8d6-126">EOP</span><span class="sxs-lookup"><span data-stu-id="0e8d6-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="0e8d6-127">Gransknings loggning (används för rapporterings ändamål)</span><span class="sxs-lookup"><span data-stu-id="0e8d6-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="0e8d6-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0e8d6-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a><span data-ttu-id="0e8d6-129">Roller och behörigheter</span><span class="sxs-lookup"><span data-stu-id="0e8d6-129">Roles and permissions</span></span>

<span data-ttu-id="0e8d6-130">Du måste ha en lämplig roll för att konfigurera principer i [säkerhets & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="0e8d6-131">Följande tabell innehåller några exempel:</span><span class="sxs-lookup"><span data-stu-id="0e8d6-131">The following table includes some examples:</span></span>

****

|<span data-ttu-id="0e8d6-132">Roll eller rollgrupp</span><span class="sxs-lookup"><span data-stu-id="0e8d6-132">Role or role group</span></span>|<span data-ttu-id="0e8d6-133">Var kan jag läsa mer?</span><span class="sxs-lookup"><span data-stu-id="0e8d6-133">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="0e8d6-134">global administratör</span><span class="sxs-lookup"><span data-stu-id="0e8d6-134">global administrator</span></span>|[<span data-ttu-id="0e8d6-135">Om administratörsroller i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0e8d6-135">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="0e8d6-136">Säkerhets administratör</span><span class="sxs-lookup"><span data-stu-id="0e8d6-136">Security Administrator</span></span>|[<span data-ttu-id="0e8d6-137">Administratörens rollbehörigheter i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0e8d6-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="0e8d6-138">Organisations hantering i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0e8d6-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="0e8d6-139">Behörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0e8d6-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="0e8d6-140">och</span><span class="sxs-lookup"><span data-stu-id="0e8d6-140">and</span></span><br> [<span data-ttu-id="0e8d6-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e8d6-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="0e8d6-142">Mer information finns i [behörigheter i säkerhets &amp; kontroll Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-142">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="0e8d6-143">Del 1 – skydd mot skadlig program vara</span><span class="sxs-lookup"><span data-stu-id="0e8d6-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="0e8d6-144">[Skydd mot skadlig program](anti-malware-protection.md) vara finns i abonnemang som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="0e8d6-145">Välj skydd mot **Threat management**skadligt Management policy i [Center för säkerhet & efterlevnad](https://protection.office.com)  >  **Policy**  >  **Anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="0e8d6-146">Dubbelklicka på **standard** principen och välj sedan **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="0e8d6-147">Ange följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0e8d6-147">Specify the following settings:</span></span>

    - <span data-ttu-id="0e8d6-148">Behåll standardinställningen i avsnittet för **identifiering av skadlig program** **vara.**</span><span class="sxs-lookup"><span data-stu-id="0e8d6-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="0e8d6-149">I **filter avsnittet gemensamma bilagor** väljer du **på**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="0e8d6-150">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-150">Click **Save**.</span></span>

<span data-ttu-id="0e8d6-151">Mer information om alternativ för principer mot skadlig program vara finns i [Konfigurera principer för skadlig program vara](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="0e8d6-152">Del 2 – skydda skadlig URL och filer</span><span class="sxs-lookup"><span data-stu-id="0e8d6-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="0e8d6-153">Skydd mot skadlig URL-adress och filer är tillgängligt i prenumerationer som inkluderar [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) och som har kon figurer ATS med principer för säkra [bifogade filer](atp-safe-attachments.md) och [ATP-länkar](atp-safe-links.md) .</span><span class="sxs-lookup"><span data-stu-id="0e8d6-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="0e8d6-154">Principer för säkra bifogade filer via ATP</span><span class="sxs-lookup"><span data-stu-id="0e8d6-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="0e8d6-155">För att konfigurera [säkerhet för säkerhets](atp-safe-attachments.md)skull för ATP måste du definiera minst en policy för säker användning av ATP.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="0e8d6-156">Välj **Threat Management**policy [Security & Compliance Center](https://protection.office.com)  >  **Policy**  >  **Safe Attachments**i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="0e8d6-157">Välj alternativet **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="0e8d6-158">Klicka på plus tecknet () i avsnittet **skydda e-postbilagor** **+** .</span><span class="sxs-lookup"><span data-stu-id="0e8d6-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="0e8d6-159">Ange följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0e8d6-159">Specify the following settings:</span></span>

   - <span data-ttu-id="0e8d6-160">Skriv i rutan **namn** `Block malware` .</span><span class="sxs-lookup"><span data-stu-id="0e8d6-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="0e8d6-161">I avsnittet svar väljer du **blockera**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="0e8d6-162">I avsnittet **omdirigera bilaga** väljer du alternativet **Aktivera omdirigering**och anger sedan e-postadressen för organisationens säkerhets administratör eller operatör som ska granska upptäckta filer.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="0e8d6-163">I avsnittet **används för** väljer **du mottagaren**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="0e8d6-164">Välj sedan din domän, Välj **Lägg till**och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="0e8d6-165">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-165">Click **Save**.</span></span>

6. <span data-ttu-id="0e8d6-166">(**Rekommenderat steg**) Som global administratör eller SharePoint Online-administratör kör cmdleten **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med parametern **DisallowInfectedFileDownload** inställd på *True* för din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="0e8d6-167">(Detta förhindrar att personer öppnar, flyttar, kopierar eller delar filer som identifieras som skadliga.)</span><span class="sxs-lookup"><span data-stu-id="0e8d6-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="0e8d6-168">Mer information finns i [Konfigurera office 365-principer för säkra bifogade filer](set-up-atp-safe-attachments-policies.md) och [aktivera Office 365 ATP för SharePoint-, OneDrive-och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="0e8d6-169">Principer för säkraste säkerhets länkar</span><span class="sxs-lookup"><span data-stu-id="0e8d6-169">ATP Safe Links policies</span></span>

<span data-ttu-id="0e8d6-170">Om du vill ställa in [säkerhets Länkar för ATP](atp-safe-links.md)kan du läsa och redigera standard principen och lägga till en princip för specifika användare.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="0e8d6-171">Välj **Threat Management**policy säkerhets länkar i [säkerhets& efterlevnad](https://protection.office.com)  >  **Policy**  >  **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="0e8d6-172">Dubbelklicka på **standard** policyn.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="0e8d6-173">I avsnittet **Använd säkra länkar i** väljer du alternativet **Microsoft 365-appar för Enterprise, Office för iOS och Android**och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-173">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="0e8d6-174">Klicka på plus tecknet () i avsnittet **principer som gäller för specifika mottagare** **+** .</span><span class="sxs-lookup"><span data-stu-id="0e8d6-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="0e8d6-175">Ange följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0e8d6-175">Specify the following settings:</span></span>

   - <span data-ttu-id="0e8d6-176">Skriv ett namn i rutan **namn** , till exempel `Safe Links` .</span><span class="sxs-lookup"><span data-stu-id="0e8d6-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="0e8d6-177">I avsnittet **Välj åtgärd väljer du** **på**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="0e8d6-178">Välj de här alternativen:</span><span class="sxs-lookup"><span data-stu-id="0e8d6-178">Select these options:</span></span>

     - <span data-ttu-id="0e8d6-179">**Använda säkra bifogade filer för att skanna nedladdnings Bart innehåll**</span><span class="sxs-lookup"><span data-stu-id="0e8d6-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="0e8d6-180">**Använda säkra länkar till e-postmeddelanden som skickas inom organisationen**</span><span class="sxs-lookup"><span data-stu-id="0e8d6-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="0e8d6-181">**Tillåt inte att användare klickar genom säkra länkar till ursprunglig URL**</span><span class="sxs-lookup"><span data-stu-id="0e8d6-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="0e8d6-182">I avsnittet **används för** väljer **du mottagaren**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="0e8d6-183">Välj sedan din domän, Välj **Lägg till**och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="0e8d6-184">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-184">Click **Save**.</span></span>

<span data-ttu-id="0e8d6-185">Mer information finns i [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md)(Konfigurera Office 365 ATP-principer för säkra länkar).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="0e8d6-186">Del 3-skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="0e8d6-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="0e8d6-187">[Anti-nätfiske]</span><span class="sxs-lookup"><span data-stu-id="0e8d6-187">[Anti-phishing]</span></span>

<span data-ttu-id="0e8d6-188">[Skydd mot nätfiske](anti-phishing-protection.md) är tillgängligt i abonnemang med [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-188">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="0e8d6-189">Avancerat skydd mot nätfiske är tillgängligt i [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-189">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="0e8d6-190">Här beskrivs hur du konfigurerar en policy för ATP-anti-nätfiske.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-190">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="0e8d6-191">De här stegen är liknande för att konfigurera en anti-nätfiske-princip (utan ATP).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-191">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="0e8d6-192">Välj **Threat Management**policy [Security & Compliance Center](https://protection.office.com)  >  **Policy**  >  **ATP-nätfiske**i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-192">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0e8d6-193">Klicka på **standard policy**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-193">Click **Default policy**.</span></span>

3. <span data-ttu-id="0e8d6-194">Klicka på **Redigera**i avsnittet **personifiering** och ange sedan följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0e8d6-194">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="0e8d6-195">På fliken **Lägg till användare på skydda** aktiverar du skydd.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-195">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="0e8d6-196">Lägg sedan till användare, till exempel organisationens styrelse medlemmar, VD, ekonomi och andra chefs ledare.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-196">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="0e8d6-197">(Du kan skriva en enskild e-postadress eller klicka på för att visa en lista.)</span><span class="sxs-lookup"><span data-stu-id="0e8d6-197">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="0e8d6-198">På fliken **Lägg till domäner på skydda** aktiverar **du automatiskt de domäner jag äger**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-198">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="0e8d6-199">Om du har anpassade domäner kan du även lägga till dem.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-199">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="0e8d6-200">På fliken **åtgärder** väljer du **Quarantine meddelandet** för både den **personifierade användaren** och de **personifierade domän** alternativen.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-200">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="0e8d6-201">Aktivera dessutom säkerhets tips.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-201">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="0e8d6-202">På fliken **Mailbox Intelligence** kontrollerar du att post låda-intelligens är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-202">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="0e8d6-203">Aktivera dessutom post låda baserat skydd mot postsamtal.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-203">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="0e8d6-204">I listan **om e-post som skickas av en personifierad användare** väljer **du sätt i karantän meddelandet**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-204">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="0e8d6-205">På fliken **Lägg till betrodda avsändare och domäner** anger du betrodda avsändare eller domäner som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-205">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="0e8d6-206">Klicka på **Spara**på fliken **Granska inställningar** när du har granskat dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-206">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="0e8d6-207">Klicka på **Redigera**i avsnittet **Spoof** och ange sedan följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0e8d6-207">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="0e8d6-208">Kontrol lera att skyddet mot förfalskning är aktiverat på fliken **Inställningar för falska filter** .</span><span class="sxs-lookup"><span data-stu-id="0e8d6-208">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="0e8d6-209">Välj **Quarantine The meddelande**på fliken **Actions** .</span><span class="sxs-lookup"><span data-stu-id="0e8d6-209">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="0e8d6-210">Klicka på **Spara**på fliken **Granska inställningar** när du har granskat dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-210">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="0e8d6-211">(Om du inte har gjort några ändringar klickar du på **Avbryt**.)</span><span class="sxs-lookup"><span data-stu-id="0e8d6-211">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="0e8d6-212">Stäng sidan standardinställningar för princip inställningar.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-212">Close the default policy settings page.</span></span>

<span data-ttu-id="0e8d6-213">Mer information om dina alternativ för skydd mot nätfiske finns i avsnittet [Konfigurera AntiPhishing-principer för ATP](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-213">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="0e8d6-214">Del 4-skydd mot skräp post</span><span class="sxs-lookup"><span data-stu-id="0e8d6-214">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="0e8d6-215">[Skydd mot skräp post](anti-spam-protection.md) finns i abonnemang som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-215">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="0e8d6-216">I [säkerhets & Compliance Center](https://protection.office.com)väljer du **hot Management**  >  **policy**  >  **anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-216">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="0e8d6-217">På fliken **anpassad** aktiverar du **anpassade inställningar** .</span><span class="sxs-lookup"><span data-stu-id="0e8d6-217">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="0e8d6-218">Expandera **standard filter princip för skräp post**, klicka på **Redigera princip**och ange sedan följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0e8d6-218">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="0e8d6-219">I avsnittet **skräp post och Mass åtgärder** anger du tröskelvärdet till 5 eller 6.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-219">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="0e8d6-220">I avsnittet **tillåta listor** granskar du (och om det behövs, redigera) tillåtna avsändare och domäner.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-220">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="0e8d6-221">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-221">Click **Save**.</span></span>

<span data-ttu-id="0e8d6-222">Mer information om alternativen för att förhindra skräp post finns i [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-222">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="0e8d6-223">Del 5 – ytterligare inställningar att konfigurera</span><span class="sxs-lookup"><span data-stu-id="0e8d6-223">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="0e8d6-224">Förutom att konfigurera skydd från skadlig program vara, skadliga URL-adresser och filer, nätfiske och skräp post rekommenderar vi att du konfigurerar inställningarna för automatisk rensning och gransknings loggning för en tom timme.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-224">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="0e8d6-225">Automatisk rensning av Tom timme för e-post</span><span class="sxs-lookup"><span data-stu-id="0e8d6-225">Zero-hour auto purge for email</span></span>

<span data-ttu-id="0e8d6-226">[Automatisk rensning för noll-timme](zero-hour-auto-purge.md) är tillgängligt i abonnemang som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="0e8d6-227">Detta skydd är aktiverat som standard. men följande villkor måste uppfyllas för att skydd ska vara aktivt:</span><span class="sxs-lookup"><span data-stu-id="0e8d6-227">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="0e8d6-228">Spam åtgärder är inställda på att **flytta meddelanden till mappen skräp post** i [principer för skräp post](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-228">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="0e8d6-229">Användare har förbehållit sina standardinställningar för [skräp](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)post och har inte avaktiverat skydd mot skräp post.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-229">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="0e8d6-230">Mer information finns i [nollställning av automatiskt skydd mot skräp post och skadlig program vara](zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-230">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="0e8d6-231">Gransknings loggning för rapportering och undersökning</span><span class="sxs-lookup"><span data-stu-id="0e8d6-231">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="0e8d6-232">Gransknings loggning är tillgängligt i abonnemang som innehåller [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-232">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="0e8d6-233">För att kunna visa data i Threat Protection-rapporter, till exempel [säkerhets instrument panelen](security-dashboard.md)och [Utforskaren](threat-explorer.md) [, måste](view-email-security-reports.md)gransknings loggning vara aktiverat för din organisation.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-233">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="0e8d6-234">Mer information finns i [Aktivera eller inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="0e8d6-234">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="0e8d6-235">Uppgifter efter installationen</span><span class="sxs-lookup"><span data-stu-id="0e8d6-235">Post-setup tasks</span></span>

<span data-ttu-id="0e8d6-236">När du har konfigurerat dina hot Protection-funktioner bör du kontrol lera hur de funktionerna fungerar, granska och revidera dina principer och titta efter nya funktioner och tjänst uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="0e8d6-236">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

****

|<span data-ttu-id="0e8d6-237">Vad kan jag göra?</span><span class="sxs-lookup"><span data-stu-id="0e8d6-237">What to do</span></span>|<span data-ttu-id="0e8d6-238">Resurser för att få mer information</span><span class="sxs-lookup"><span data-stu-id="0e8d6-238">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="0e8d6-239">Se hur hot Protection-funktioner fungerar för din organisation genom att visa rapporter</span><span class="sxs-lookup"><span data-stu-id="0e8d6-239">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="0e8d6-240">Säkerhets instrument panel</span><span class="sxs-lookup"><span data-stu-id="0e8d6-240">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="0e8d6-241">Säkerhets rapporter för e-post</span><span class="sxs-lookup"><span data-stu-id="0e8d6-241">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="0e8d6-242">Rapporter för Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="0e8d6-242">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="0e8d6-243">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="0e8d6-243">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="0e8d6-244">Regelbundet granska och omarbeta dina skydds principer om det behövs</span><span class="sxs-lookup"><span data-stu-id="0e8d6-244">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="0e8d6-245">Säkra Poäng</span><span class="sxs-lookup"><span data-stu-id="0e8d6-245">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="0e8d6-246">Smarta rapporter och insikter</span><span class="sxs-lookup"><span data-stu-id="0e8d6-246">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="0e8d6-247">Microsoft 365 hot-och svars funktioner</span><span class="sxs-lookup"><span data-stu-id="0e8d6-247">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="0e8d6-248">Titta efter nya funktioner och tjänste uppdateringar</span><span class="sxs-lookup"><span data-stu-id="0e8d6-248">Watch for new features and service updates</span></span>|[<span data-ttu-id="0e8d6-249">Standard-och riktade versions alternativ</span><span class="sxs-lookup"><span data-stu-id="0e8d6-249">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="0e8d6-250">Meddelandecentral</span><span class="sxs-lookup"><span data-stu-id="0e8d6-250">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="0e8d6-251">Microsoft 365-översikt</span><span class="sxs-lookup"><span data-stu-id="0e8d6-251">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="0e8d6-252">Tjänst beskrivningar</span><span class="sxs-lookup"><span data-stu-id="0e8d6-252">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
