---
title: Aktivera Office 365 ATP – SharePoint, OneDrive & Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Lär dig hur du aktiverar ATP för SharePoint, OneDrive och Teams, inklusive hur du ställer in aviseringar för identifierade filer.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c8c8d0f3caa3e717f8193a3c0d6b7bb1d40dab6
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201597"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="f6a83-103">Aktivera ATP för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6a83-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="f6a83-104">Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="f6a83-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="f6a83-105">Om du är hem användare letar efter information om säkra länkar i Outlook kan du läsa mer i [avancerad Outlook.com säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="f6a83-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="f6a83-106">[Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) skyddar din organisation från oavsiktlig delning av skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="f6a83-106">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="f6a83-107">När en skadlig fil identifieras blockeras den så att ingen kan öppna, kopiera, flytta eller dela den innan ytterligare åtgärder vidtas av organisationens säkerhets team.</span><span class="sxs-lookup"><span data-stu-id="f6a83-107">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="f6a83-108">Läs den här artikeln om du vill aktivera ATP för SharePoint, OneDrive och Teams, konfigurera aviseringar om du vill få meddelanden om identifierade filer och ta nästa steg.</span><span class="sxs-lookup"><span data-stu-id="f6a83-108">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span>

<span data-ttu-id="f6a83-109">Om du vill definiera (eller redigera) ATP-principer måste du ha en lämplig roll.</span><span class="sxs-lookup"><span data-stu-id="f6a83-109">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="f6a83-110">Några exempel beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="f6a83-110">Some examples are described in the following table:</span></span>

****

|<span data-ttu-id="f6a83-111">Roll</span><span class="sxs-lookup"><span data-stu-id="f6a83-111">Role</span></span>|<span data-ttu-id="f6a83-112">Där/hur kopplat</span><span class="sxs-lookup"><span data-stu-id="f6a83-112">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="f6a83-113">global administratör</span><span class="sxs-lookup"><span data-stu-id="f6a83-113">global administrator</span></span>|<span data-ttu-id="f6a83-114">Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard.</span><span class="sxs-lookup"><span data-stu-id="f6a83-114">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="f6a83-115">(Mer information finns i [om administratörs roller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)</span><span class="sxs-lookup"><span data-stu-id="f6a83-115">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="f6a83-116">Säkerhets administratör</span><span class="sxs-lookup"><span data-stu-id="f6a83-116">Security Administrator</span></span>|<span data-ttu-id="f6a83-117">Azure Active Directory-administratörs Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="f6a83-117">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="f6a83-118">Organisations hantering i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f6a83-118">Exchange Online Organization Management</span></span>|<span data-ttu-id="f6a83-119">Administrations Center för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="f6a83-119">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="f6a83-120">eller</span><span class="sxs-lookup"><span data-stu-id="f6a83-120">or</span></span> <br>  <span data-ttu-id="f6a83-121">PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="f6a83-121">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="f6a83-122">Aktivera ATP för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6a83-122">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f6a83-123">**Innan du påbörjar den här proceduren bör du kontrol lera att gransknings loggning redan är aktiverat för din Microsoft 365-miljö**.</span><span class="sxs-lookup"><span data-stu-id="f6a83-123">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="f6a83-124">Det gör du vanligt vis av någon som har rollen gransknings loggar som tilldelats i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f6a83-124">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="f6a83-125">Mer information finns i [Aktivera eller inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="f6a83-125">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="f6a83-126">Gå till <https://protection.office.com> och logga in med ditt arbets-eller skol konto.</span><span class="sxs-lookup"><span data-stu-id="f6a83-126">Go to <https://protection.office.com>, and sign in with your work or school account.</span></span>

2. <span data-ttu-id="f6a83-127">I det vänstra navigerings **fältet under säkerhets**& Compliance Center väljer du **policy** \> **Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="f6a83-127">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![Välj Threat Management policy i Center för säkerhet & efterlevnad \>](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="f6a83-129">Välj **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f6a83-129">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![Aktivera avancerat skydd för SharePoint Online, OneDrive för företag och Microsoft Teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="f6a83-131">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f6a83-131">Click **Save**.</span></span>

5. <span data-ttu-id="f6a83-132">Granska (och, om tillämpligt, redigera) organisationens principer för [säkert bifogade filer](set-up-atp-safe-attachments-policies.md) och [säkra länkar](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f6a83-132">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="f6a83-133">Lämpligt Som global administratör eller SharePoint Online-administratör kör du cmdleten **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med parametern _DisallowInfectedFileDownload_ angiven till *True*.</span><span class="sxs-lookup"><span data-stu-id="f6a83-133">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to *true*.</span></span>

   - <span data-ttu-id="f6a83-134">Om du anger parametern till *True* blockeras alla åtgärder (förutom borttagning) för identifierade filer.</span><span class="sxs-lookup"><span data-stu-id="f6a83-134">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="f6a83-135">Personer kan inte öppna, flytta, kopiera eller dela identifierade filer.</span><span class="sxs-lookup"><span data-stu-id="f6a83-135">People cannot open, move, copy, or share detected files.</span></span>

   - <span data-ttu-id="f6a83-136">Om du anger parametern till *falskt* blockeras alla åtgärder förutom Delete och nedladdning.</span><span class="sxs-lookup"><span data-stu-id="f6a83-136">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="f6a83-137">Andra kan välja att acceptera risken och hämta en identifierad fil.</span><span class="sxs-lookup"><span data-stu-id="f6a83-137">People can choose to accept the risk and download a detected file.</span></span>

7. <span data-ttu-id="f6a83-138">Tillåt upp till 30 minuter för att ändringarna ska spridas till alla Microsoft 365-datacenter.</span><span class="sxs-lookup"><span data-stu-id="f6a83-138">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

8. <span data-ttu-id="f6a83-139">Lämpligt Fortsätt med att konfigurera aviseringar för identifierade filer.</span><span class="sxs-lookup"><span data-stu-id="f6a83-139">(Recommended) Proceed to set up alerts for detected files.</span></span>

<span data-ttu-id="f6a83-140">Mer information om hur du använder PowerShell med Microsoft 365 finns i [Hantera Microsoft 365 med PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6a83-140">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).</span></span>

<span data-ttu-id="f6a83-141">Om du vill veta mer om användar upplevelsen när en fil har identifierats som skadlig, se [vad du kan göra när en skadlig fil finns i SharePoint Online, OneDrive eller Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="f6a83-141">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="f6a83-142">Konfigurera aviseringar för identifierade filer</span><span class="sxs-lookup"><span data-stu-id="f6a83-142">Set up alerts for detected files</span></span>

<span data-ttu-id="f6a83-143">Om du vill få aviseringar när en fil i SharePoint Online, OneDrive för företag eller Microsoft Teams har identifierats som skadlig kan du ställa in en avisering.</span><span class="sxs-lookup"><span data-stu-id="f6a83-143">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="f6a83-144">I fönstret [säkerhets & efterlevnad](https://protection.office.com)väljer du **aviseringar** \> **Hantera aviseringar**.</span><span class="sxs-lookup"><span data-stu-id="f6a83-144">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="f6a83-145">Välj **ny aviserings princip**.</span><span class="sxs-lookup"><span data-stu-id="f6a83-145">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="f6a83-146">Ange ett namn för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="f6a83-146">Specify a name for the alert.</span></span> <span data-ttu-id="f6a83-147">Du kan till exempel skriva in skadliga filer i bibliotek.</span><span class="sxs-lookup"><span data-stu-id="f6a83-147">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="f6a83-148">Ange en beskrivning av aviseringen.</span><span class="sxs-lookup"><span data-stu-id="f6a83-148">Type a description for the alert.</span></span> <span data-ttu-id="f6a83-149">Du kan till exempel skriva meddelanden administratörer när skadliga filer upptäcks i SharePoint Online, OneDrive eller Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6a83-149">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="f6a83-150">Gör följande i avsnittet **Skicka aviseringen när...** :</span><span class="sxs-lookup"><span data-stu-id="f6a83-150">In the **Send this alert when...** section, do the following:</span></span>

   <span data-ttu-id="f6a83-151">a.</span><span class="sxs-lookup"><span data-stu-id="f6a83-151">a.</span></span> <span data-ttu-id="f6a83-152">Välj **upptäckt skadlig kod i filen**i listan **aktiviteter** .</span><span class="sxs-lookup"><span data-stu-id="f6a83-152">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="f6a83-153">b.</span><span class="sxs-lookup"><span data-stu-id="f6a83-153">b.</span></span> <span data-ttu-id="f6a83-154">Lämna fältet **användare** tomma.</span><span class="sxs-lookup"><span data-stu-id="f6a83-154">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="f6a83-155">I avsnittet **Skicka aviseringen till... väljer du** en eller flera globala administratörer, säkerhets administratörer eller säkerhets läsare som ska få avisering när en skadlig fil identifieras.</span><span class="sxs-lookup"><span data-stu-id="f6a83-155">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="f6a83-156">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f6a83-156">Click **Save**.</span></span>

<span data-ttu-id="f6a83-157">Om du vill veta mer om aviseringar läser [du skapa aktivitets aviseringar i avsnittet säkerhets & efterlevnad](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="f6a83-157">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6a83-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="f6a83-158">Next steps</span></span>

1. [<span data-ttu-id="f6a83-159">Visa information om skadliga filer som identifieras i SharePoint, OneDrive eller Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6a83-159">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

2. [<span data-ttu-id="f6a83-160">Hantera meddelanden och filer i karantän som administratör i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f6a83-160">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
