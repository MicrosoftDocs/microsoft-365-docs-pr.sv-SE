---
title: Aktivera Office 365 ATP - SharePoint, OneDrive & Teams
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
ms.openlocfilehash: b4dfe56b635714cedf033f2d4f14cd6bc0286650
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224617"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="86500-103">Aktivera ATP för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86500-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86500-104">Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="86500-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="86500-105">Om du är hemanvändare och letar efter information om säkra länkar i Outlook läser du [Avancerad Outlook.com säkerhet](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="86500-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="86500-106">[Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) skyddar din organisation från att oavsiktligt dela skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="86500-106">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="86500-107">När en skadlig fil upptäcks blockeras filen så att ingen kan öppna, kopiera, flytta eller dela den förrän ytterligare åtgärder vidtas av organisationens säkerhetsteam.</span><span class="sxs-lookup"><span data-stu-id="86500-107">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="86500-108">Läs den här artikeln om du vill aktivera ATP för SharePoint, OneDrive och Teams, konfigurera aviseringar som ska meddelas om identifierade filer och vidta nästa steg.</span><span class="sxs-lookup"><span data-stu-id="86500-108">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span>

<span data-ttu-id="86500-109">Om du vill definiera (eller redigera) ATP-principer måste du tilldelas en lämplig roll.</span><span class="sxs-lookup"><span data-stu-id="86500-109">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="86500-110">Några exempel beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="86500-110">Some examples are described in the following table:</span></span>

|<span data-ttu-id="86500-111">Roll</span><span class="sxs-lookup"><span data-stu-id="86500-111">Role</span></span>|<span data-ttu-id="86500-112">Var/hur tilldelas</span><span class="sxs-lookup"><span data-stu-id="86500-112">Where/how assigned</span></span>|
|---------|---------|
|<span data-ttu-id="86500-113">global administratör</span><span class="sxs-lookup"><span data-stu-id="86500-113">global administrator</span></span>|<span data-ttu-id="86500-114">Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard.</span><span class="sxs-lookup"><span data-stu-id="86500-114">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="86500-115">(Läs [mer om Microsoft 365-administratörsroller.)](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="86500-115">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="86500-116">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="86500-116">Security Administrator</span></span>|<span data-ttu-id="86500-117">Administrationscenter för Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="86500-117">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="86500-118">Hantering av Exchange Online-organisation</span><span class="sxs-lookup"><span data-stu-id="86500-118">Exchange Online Organization Management</span></span>|<span data-ttu-id="86500-119">Administrationscenter för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="86500-119">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="86500-120">eller</span><span class="sxs-lookup"><span data-stu-id="86500-120">or</span></span> <br>  <span data-ttu-id="86500-121">PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="86500-121">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span>|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="86500-122">Aktivera ATP för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86500-122">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="86500-123">**Innan du påbörjar den här proceduren kontrollerar du att granskningsloggning redan är aktiverat för din Microsoft 365-miljö**.</span><span class="sxs-lookup"><span data-stu-id="86500-123">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="86500-124">Detta görs vanligtvis av någon som har rollen Granskningsloggar tilldelad i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="86500-124">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="86500-125">Mer information finns i [Aktivera eller inaktivera granskningsloggsökning](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="86500-125">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="86500-126">Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt arbets- eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="86500-126">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>

2. <span data-ttu-id="86500-127">I säkerhets- & Compliance Center, i det vänstra navigeringsfönstret, under **Hothantering,** väljer du **Policy** \> **Principsäkra bilagor**.</span><span class="sxs-lookup"><span data-stu-id="86500-127">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![I Security & Compliance Center väljer du Policy för hantering \> av hot](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="86500-129">Välj **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="86500-129">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![Aktivera Avancerat skydd mot hot för SharePoint Online, OneDrive för företag och Microsoft Teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="86500-131">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="86500-131">Click **Save**.</span></span>

5. <span data-ttu-id="86500-132">Granska (och, beroende på vad som är lämpligt, redigera) organisationens [principer för säkra bilagor](set-up-atp-safe-attachments-policies.md) och principer för säkra [länkar](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="86500-132">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="86500-133">(Rekommenderas) Som global administratör eller SharePoint Online-administratör kör du cmdleten **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med parametern _DisallowInfectedFileDownload_ inställd på *true*.</span><span class="sxs-lookup"><span data-stu-id="86500-133">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to *true*.</span></span>

   - <span data-ttu-id="86500-134">Om du ställer in parametern på *true* blockerar alla åtgärder (utom Ta bort) för identifierade filer.</span><span class="sxs-lookup"><span data-stu-id="86500-134">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="86500-135">Personer kan inte öppna, flytta, kopiera eller dela identifierade filer.</span><span class="sxs-lookup"><span data-stu-id="86500-135">People cannot open, move, copy, or share detected files.</span></span>

   - <span data-ttu-id="86500-136">Om du ställer in parametern för *att fela* blockerar alla åtgärder utom Ta bort och hämta.</span><span class="sxs-lookup"><span data-stu-id="86500-136">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="86500-137">Personer kan välja att acceptera risken och ladda ner en upptäckt fil.</span><span class="sxs-lookup"><span data-stu-id="86500-137">People can choose to accept the risk and download a detected file.</span></span>

7. <span data-ttu-id="86500-138">Tillåt upp till 30 minuter innan ändringarna sprids till alla Microsoft 365-datacenter.</span><span class="sxs-lookup"><span data-stu-id="86500-138">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

8. <span data-ttu-id="86500-139">(Rekommenderas) Fortsätt att ställa in aviseringar för identifierade filer.</span><span class="sxs-lookup"><span data-stu-id="86500-139">(Recommended) Proceed to set up alerts for detected files.</span></span>

<span data-ttu-id="86500-140">Mer information om hur du använder PowerShell med Microsoft 365 finns i [Hantera Microsoft 365 med PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="86500-140">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span>

<span data-ttu-id="86500-141">Mer information om användarupplevelsen när en fil har identifierats som skadlig finns [i Vad du ska göra när en skadlig fil hittas i SharePoint Online, OneDrive eller Microsoft Teams](https://support.microsoft.com/en-us/office/what-to-do-when-a-malicious-file-is-found-in-sharepoint-online-onedrive-or-microsoft-teams-01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="86500-141">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/en-us/office/what-to-do-when-a-malicious-file-is-found-in-sharepoint-online-onedrive-or-microsoft-teams-01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="86500-142">Konfigurera aviseringar för identifierade filer</span><span class="sxs-lookup"><span data-stu-id="86500-142">Set up alerts for detected files</span></span>

<span data-ttu-id="86500-143">Om du vill få ett meddelande när en fil i SharePoint Online, OneDrive för företag eller Microsoft Teams har identifierats som skadlig kan du ställa in en avisering.</span><span class="sxs-lookup"><span data-stu-id="86500-143">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="86500-144">I [Säkerhets- & Compliance Center](https://protection.office.com)väljer du **Aviseringar** \> **Hantera aviseringar**.</span><span class="sxs-lookup"><span data-stu-id="86500-144">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="86500-145">Välj **Ny aviseringsprincip**.</span><span class="sxs-lookup"><span data-stu-id="86500-145">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="86500-146">Ange ett namn för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="86500-146">Specify a name for the alert.</span></span> <span data-ttu-id="86500-147">Du kan till exempel skriva skadliga filer i bibliotek.</span><span class="sxs-lookup"><span data-stu-id="86500-147">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="86500-148">Skriv en beskrivning för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="86500-148">Type a description for the alert.</span></span> <span data-ttu-id="86500-149">Du kan till exempel skriva Notifierar administratörer när skadliga filer identifieras i SharePoint Online, OneDrive eller Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="86500-149">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="86500-150">Gör följande i avsnittet Skicka den **här varningen när...**</span><span class="sxs-lookup"><span data-stu-id="86500-150">In the **Send this alert when...** section, do the following:</span></span>

   <span data-ttu-id="86500-151">a.</span><span class="sxs-lookup"><span data-stu-id="86500-151">a.</span></span> <span data-ttu-id="86500-152">I listan **Aktiviteter** väljer du **Identifierad skadlig kod i filen**.</span><span class="sxs-lookup"><span data-stu-id="86500-152">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="86500-153">b.</span><span class="sxs-lookup"><span data-stu-id="86500-153">b.</span></span> <span data-ttu-id="86500-154">Lämna fältet **Användare** tomt.</span><span class="sxs-lookup"><span data-stu-id="86500-154">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="86500-155">I avsnittet **Skicka den här aviseringen till...** väljer du en eller flera globala administratörer, säkerhetsadministratörer eller säkerhetsläsare som ska få ett meddelande när en skadlig fil identifieras.</span><span class="sxs-lookup"><span data-stu-id="86500-155">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="86500-156">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="86500-156">Click **Save**.</span></span>

<span data-ttu-id="86500-157">Mer information om aviseringar finns [i Skapa aktivitetsaviseringar i Säkerhets- & Compliance Center](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="86500-157">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="86500-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="86500-158">Next steps</span></span>

1. [<span data-ttu-id="86500-159">Visa information om skadliga filer som upptäckts i SharePoint, OneDrive eller Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86500-159">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

2. [<span data-ttu-id="86500-160">Hantera meddelanden och filer i karantän som administratör i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="86500-160">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
