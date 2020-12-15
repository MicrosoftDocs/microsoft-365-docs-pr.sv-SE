---
title: Aktivera Microsoft Defender för Office 365-SharePoint, OneDrive & team
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
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
ms.openlocfilehash: 44d487810156d5de5ae152e08040e8dccd2a4ee0
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682597"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="5b85b-103">Aktivera ATP för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b85b-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5b85b-104">Microsoft Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams skyddar din organisation från oavsiktlig delning av skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="5b85b-104">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="5b85b-105">Mer information finns i [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="5b85b-105">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="5b85b-106">I den här artikeln beskrivs hur du aktiverar och konfigurerar ATP för SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5b85b-106">This article contains the steps for enabling and configuring ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5b85b-107">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="5b85b-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5b85b-108">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="5b85b-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="5b85b-109">Om du vill gå direkt till sidan **betrodda säkerhets** meddelanden via ATP öppnar du <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="5b85b-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="5b85b-110">För att aktivera ATP för SharePoint, OneDrive och Microsoft Teams måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="5b85b-110">To turn on ATP for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="5b85b-111">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5b85b-111">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="5b85b-112">Om du vill använda SharePoint Online PowerShell för att förhindra att andra laddar ned skadliga filer måste du vara medlem i rollen [Global administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) eller [administratör för SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5b85b-112">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="5b85b-113">Kontrol lera att gransknings loggning är aktiverat för din organisation.</span><span class="sxs-lookup"><span data-stu-id="5b85b-113">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="5b85b-114">Mer information finns i [Aktivera eller inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="5b85b-114">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="5b85b-115">Tillåt upp till 30 minuter innan ändringarna börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="5b85b-115">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="5b85b-116">Steg 1: Använd säkerhets & Compliance Center för att aktivera ATP för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b85b-116">Step 1: Use the Security & Compliance Center to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="5b85b-117">I säkerhets & Compliance Center går du till **Threat Management** \> **policys** \> och kan välja **globala inställningar**.</span><span class="sxs-lookup"><span data-stu-id="5b85b-117">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="5b85b-118">I de **globala inställningarna** , flyg ut som visas, går du till inställningen **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="5b85b-118">In the **Global settings** fly out that appears, go to the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="5b85b-119">Flytta växlings knappen till höger ![ om ](../../media/scc-toggle-on.png) du vill aktivera ATP för SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5b85b-119">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="5b85b-120">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="5b85b-120">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="5b85b-121">Använda Exchange Online PowerShell för att aktivera ATP för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b85b-121">Use Exchange Online PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="5b85b-122">Om du hellre vill använda PowerShell för att aktivera ATP för SharePoint, OneDrive och Microsoft Teams [ansluter du till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="5b85b-122">If you'd rather use PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="5b85b-123">Detaljerad information om syntax och parametrar finns i [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="5b85b-123">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="5b85b-124">Steg 2: (rekommenderas) Använd SharePoint Online PowerShell för att förhindra att användare laddar ned skadliga filer</span><span class="sxs-lookup"><span data-stu-id="5b85b-124">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="5b85b-125">Som standard kan användare inte öppna, flytta, kopiera eller dela filer som identifieras via ATP.</span><span class="sxs-lookup"><span data-stu-id="5b85b-125">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="5b85b-126">Men de kan ta bort och hämta skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="5b85b-126">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="5b85b-127">För att förhindra att användare laddar ned skadliga filer, [Anslut till SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="5b85b-127">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="5b85b-128">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="5b85b-128">**Notes**:</span></span>

- <span data-ttu-id="5b85b-129">Den här inställningen påverkar både användare och administratörer.</span><span class="sxs-lookup"><span data-stu-id="5b85b-129">This setting affects both users and admins.</span></span>
- <span data-ttu-id="5b85b-130">Personer kan fortfarande ta bort skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="5b85b-130">People can still delete malicious files.</span></span>

<span data-ttu-id="5b85b-131">Detaljerad information om syntax och parametrar finns i [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="5b85b-131">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="5b85b-132">Steg 3 (rekommenderas) Använd säkerhets & Compliance Center för att skapa en aviserings princip för identifierade filer</span><span class="sxs-lookup"><span data-stu-id="5b85b-132">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="5b85b-133">Du kan skapa en aviserings policy som meddelar dig och andra administratörer när ATP för SharePoint, OneDrive och Microsoft Teams identifierar en skadlig fil.</span><span class="sxs-lookup"><span data-stu-id="5b85b-133">You can create an alert policy that notifies you and other admins when ATP for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="5b85b-134">Om du vill veta mer om aviseringar läser [du skapa aktivitets aviseringar i avsnittet säkerhets & efterlevnad](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="5b85b-134">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="5b85b-135">Gå till **aviserings** principer för varningar eller öppna i fönstret [säkerhets & efterlevnad](https://protection.office.com) \>  <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="5b85b-135">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="5b85b-136">Klicka på **ny aviserings princip** på sidan **aviserings principer** .</span><span class="sxs-lookup"><span data-stu-id="5b85b-136">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="5b85b-137">Guiden **ny aviserings princip** öppnas när du flyger ut. På sidan **namnge din avisering** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="5b85b-137">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="5b85b-138">**Name**: Skriv in ett unikt och beskrivande namn.</span><span class="sxs-lookup"><span data-stu-id="5b85b-138">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="5b85b-139">Till exempel skadliga filer i bibliotek.</span><span class="sxs-lookup"><span data-stu-id="5b85b-139">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="5b85b-140">**Beskrivning**: Skriv en valfri beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5b85b-140">**Description**: Type an optional description.</span></span> <span data-ttu-id="5b85b-141">Till exempel meddelar administratörer när skadlig filer identifieras i SharePoint Online, OneDrive eller Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5b85b-141">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="5b85b-142">**Allvarlighets grad**: lämna standardvärdet **lågt** markerat eller Välj **mellan** eller **hög**.</span><span class="sxs-lookup"><span data-stu-id="5b85b-142">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="5b85b-143">**Välj en kategori**: Välj **Threat Management**.</span><span class="sxs-lookup"><span data-stu-id="5b85b-143">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="5b85b-144">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5b85b-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="5b85b-145">Konfigurera följande inställningar på sidan **skapa aviserings inställningar** :</span><span class="sxs-lookup"><span data-stu-id="5b85b-145">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="5b85b-146">**Vad vill du varna för?: aktiviteten är**: Välj **upptäckt skadlig kod i filen**.</span><span class="sxs-lookup"><span data-stu-id="5b85b-146">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="5b85b-147">**Hur vill du att notifieringen ska utlösas?** lämna standardvärdet **varje gång en aktivitet matchar den valda regeln** .</span><span class="sxs-lookup"><span data-stu-id="5b85b-147">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="5b85b-148">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5b85b-148">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="5b85b-149">På sidan **Ange mottagarna** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="5b85b-149">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="5b85b-150">**Skicka e-postmeddelanden**: kontrol lera att den här inställningen är markerad.</span><span class="sxs-lookup"><span data-stu-id="5b85b-150">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="5b85b-151">I rutan **e-postmottagare** väljer du en eller flera globala administratörer, säkerhets administratörer eller säkerhets läsare som ska få avisering när en skadlig fil identifieras.</span><span class="sxs-lookup"><span data-stu-id="5b85b-151">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="5b85b-152">**Daglig meddelande gräns**: lämna standardvärdet **ingen gräns** markerat.</span><span class="sxs-lookup"><span data-stu-id="5b85b-152">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="5b85b-153">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5b85b-153">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="5b85b-154">På sidan **Granska inställningar** granskar du inställningarna och klickar på **Redigera** i något av avsnitten för att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="5b85b-154">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="5b85b-155">I avsnittet **vill du aktivera policyn direkt? lämnar du** standardvärdet **Ja, sätter det på direkt** markerat.</span><span class="sxs-lookup"><span data-stu-id="5b85b-155">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="5b85b-156">När du är klar klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="5b85b-156">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="5b85b-157">Använda säkerhets & kompabilitet för att skapa en aviserings princip för identifierade filer</span><span class="sxs-lookup"><span data-stu-id="5b85b-157">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="5b85b-158">Om du hellre vill använda PowerShell för att skapa samma aviserings princip enligt beskrivningen i föregående avsnitt, [ansluter du till säkerhets & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="5b85b-158">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="5b85b-159">**Obs!** standardvärdet för _allvarlighets grad_ är lågt.</span><span class="sxs-lookup"><span data-stu-id="5b85b-159">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="5b85b-160">Om du vill ange medium eller hög inkluderar du _allvarlighets GRADS_ parametern och värdet i kommandot.</span><span class="sxs-lookup"><span data-stu-id="5b85b-160">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="5b85b-161">Detaljerad information om syntax och parametrar finns i [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="5b85b-161">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="5b85b-162">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="5b85b-162">How do you know these procedures worked?</span></span>

- <span data-ttu-id="5b85b-163">Så här kontrollerar du att du har aktiverat ATP för SharePoint, OneDrive och Microsoft Teams på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="5b85b-163">To verify that you've successfully turned on ATP for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="5b85b-164">I [säkerhets & Compliance Center](https://protection.office.com)går du till **hanterings princip för hot Management** \>  \> , väljer **globala inställningar** och kontrollerar värdet på inställningen för att **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="5b85b-164">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="5b85b-165">I Exchange Online PowerShell kör du följande kommando för att kontrol lera inställningen för egenskapen:</span><span class="sxs-lookup"><span data-stu-id="5b85b-165">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="5b85b-166">Detaljerad information om syntax och parametrar finns i [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="5b85b-166">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="5b85b-167">Om du vill kontrol lera att du har blockerat personer från att ladda ned skadliga filer öppnar du SharePoint Online PowerShell och kör följande kommando för att verifiera egenskapens värde:</span><span class="sxs-lookup"><span data-stu-id="5b85b-167">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="5b85b-168">Detaljerad information om syntax och parametrar finns i [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="5b85b-168">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="5b85b-169">Så här kontrollerar du att du har konfigurerat en aviserings princip för identifierade filer:</span><span class="sxs-lookup"><span data-stu-id="5b85b-169">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="5b85b-170">Gå till **aviserings** principer i säkerhets & för säkerhet \>  \> och välj varnings principen och kontrol lera inställningarna.</span><span class="sxs-lookup"><span data-stu-id="5b85b-170">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="5b85b-171">I säkerhets & Compliance Center PowerShell, Ersätt \<AlertPolicyName\> med namnet på aviserings principen, kör följande kommando och verifierar egenskapsvärdena:</span><span class="sxs-lookup"><span data-stu-id="5b85b-171">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="5b85b-172">Detaljerad information om syntax och parametrar finns i [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="5b85b-172">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="5b85b-173">Använd [rapporten Threat Protection status](view-email-security-reports.md#threat-protection-status-report) för att visa information om identifierade filer i SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5b85b-173">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="5b85b-174">Specifikt kan du använda **Visa data via: vyn \> skadlig program vara** .</span><span class="sxs-lookup"><span data-stu-id="5b85b-174">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
