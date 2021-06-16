---
title: Aktivera säkra bilagor för SharePoint, OneDrive och Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Administratörer kan lära sig hur de aktiverar Valv-filer för SharePoint, OneDrive och Microsoft Teams, inklusive hur du ställer in aviseringar för identifierade filer.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a654db40e5dec8d23d07ec7455216fe4e0a8c0e7
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933017"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="c6cb3-103">Aktivera säkra bilagor för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6cb3-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c6cb3-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="c6cb3-104">**Applies to**</span></span>
- [<span data-ttu-id="c6cb3-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="c6cb3-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c6cb3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6cb3-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c6cb3-107">Microsoft Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams skyddar organisationen från att oavsiktligt dela skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="c6cb3-108">Mer information finns i Bifoga [Valv för SharePoint, OneDrive och Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c6cb3-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="c6cb3-109">Den här artikeln innehåller anvisningar för hur du aktiverar och konfigurerar Valv bifogade filer för SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c6cb3-110">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="c6cb3-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c6cb3-111">Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="c6cb3-112">Gå direkt till sidan **Valv genom** att öppna <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="c6cb3-112">To go directly to the **Safe Attachments** page, open <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="c6cb3-113">Om du vill aktivera Valv-bilagor för SharePoint, OneDrive och Microsoft Teams måste du vara medlem i  rollgrupperna  Organisationshantering eller Säkerhetsadministratör i Microsoft 365 Defender-portalen.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="c6cb3-114">Mer information finns i [Behörigheter i Microsoft 365 Defender-portalen.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="c6cb3-114">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="c6cb3-115">Om du vill använda SharePoint Online PowerShell för att förhindra att användare [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) laddar ned skadliga filer måste du vara medlem i den globala administratören eller [administratörsrollen SharePoint](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="c6cb3-116">Kontrollera att granskningsloggning är aktiverat för organisationen.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="c6cb3-117">Du kan läsa mer i [Aktivera och inaktivera granskningsloggsökning](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="c6cb3-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="c6cb3-118">Det kan ta upp till 30 minuter innan inställningarna verkställs.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="c6cb3-119">Steg 1: Använd Microsoft 365 Defender-portalen för att aktivera Valv för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6cb3-119">Step 1: Use the Microsoft 365 Defender portal to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="c6cb3-120">I Defender Microsoft 365 portalen går du till **Principer för & principer** för \> **hotprinciper** Valv bifogade \>  \> **filer.**</span><span class="sxs-lookup"><span data-stu-id="c6cb3-120">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="c6cb3-121">På sidan **Valv bifogade** filer klickar du på **Globala inställningar.**</span><span class="sxs-lookup"><span data-stu-id="c6cb3-121">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="c6cb3-122">I den globala inställningsfällan som visas går du till avsnittet Skydda filer i **SharePoint, OneDrive och Microsoft Teams.** </span><span class="sxs-lookup"><span data-stu-id="c6cb3-122">In the **Global settings** fly out that appears, go to the **Protect files in SharePoint, OneDrive, and Microsoft Teams** section.</span></span>

   <span data-ttu-id="c6cb3-123">Flytta **växlingsknappen** Aktivera Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams till höger aktivera växlingsknappen för att aktivera ![ ](../../media/scc-toggle-on.png) Valv-bilagor för SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-123">Move the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="c6cb3-124">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-124">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="c6cb3-125">Använd Exchange Online PowerShell för att aktivera Valv bifogade filer för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6cb3-125">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="c6cb3-126">Om du hellre vill använda PowerShell för att aktivera Valv-bilagor för SharePoint, OneDrive och Microsoft Teams ansluter du [till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="c6cb3-126">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="c6cb3-127">Detaljerad information om syntax och parametrar finns i [Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="c6cb3-127">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="c6cb3-128">Steg 2: (Rekommenderas) Använd SharePoint Online PowerShell för att hindra användare från att hämta skadliga filer</span><span class="sxs-lookup"><span data-stu-id="c6cb3-128">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="c6cb3-129">Som standard kan användare inte öppna, flytta, kopiera eller dela skadliga filer som identifieras av <sup>\*</sup> Valv-bilagor för SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-129">By default, users can't open, move, copy, or share<sup>\*</sup> malicious files that are detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="c6cb3-130">Däremot kan de ta bort och ladda ned skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-130">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="c6cb3-131"><sup>\*</sup> Om användarna går **till Hantera åtkomst** är **alternativet** Dela fortfarande tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-131"><sup>\*</sup> If users go to **Manage access**, the **Share** option is still available.</span></span>

<span data-ttu-id="c6cb3-132">För att hindra användare från att hämta skadliga filer [ansluter du till SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="c6cb3-132">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="c6cb3-133">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="c6cb3-133">**Notes**:</span></span>

- <span data-ttu-id="c6cb3-134">Den här inställningen påverkar både användare och administratörer.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-134">This setting affects both users and admins.</span></span>
- <span data-ttu-id="c6cb3-135">Användare kan fortfarande ta bort skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-135">People can still delete malicious files.</span></span>

<span data-ttu-id="c6cb3-136">Detaljerad information om syntax och parametrar finns [i Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="c6cb3-136">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="c6cb3-137">Steg 3 (rekommenderas) Använd Microsoft 365 Defender-portalen för att skapa en aviseringsprincip för identifierade filer</span><span class="sxs-lookup"><span data-stu-id="c6cb3-137">Step 3 (Recommended) Use the Microsoft 365 Defender portal to create an alert policy for detected files</span></span>

<span data-ttu-id="c6cb3-138">Du kan skapa en aviseringsprincip som meddelar dig och andra administratörer när Valv-bilagor för SharePoint, OneDrive och Microsoft Teams upptäcker en skadlig fil.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-138">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="c6cb3-139">Mer information om aviseringar finns i Skapa [aktivitetsaviseringar i Microsoft 365 Defender-portalen.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="c6cb3-139">To learn more about alerts, see [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="c6cb3-140">I Defender Microsoft 365 portalen går du till **Principer &** \> **Aviseringsprincip** eller öppna <https://security.microsoft.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="c6cb3-140">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** or open <https://security.microsoft.com/alertpolicies>.</span></span>

2. <span data-ttu-id="c6cb3-141">Klicka på **Ny aviseringsprincip** **på sidan Aviseringsprincip.**</span><span class="sxs-lookup"><span data-stu-id="c6cb3-141">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="c6cb3-142">Guiden **Ny aviseringsprincip** öppnas i en flyg ut. På sidan **Namnge din avisering** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="c6cb3-142">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>
   - <span data-ttu-id="c6cb3-143">**Namn**: Ange ett unikt och beskrivande namn.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-143">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="c6cb3-144">Till exempel Skadliga filer i bibliotek.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-144">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="c6cb3-145">**Beskrivning**: Ange en valfri beskrivning.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-145">**Description**: Type an optional description.</span></span> <span data-ttu-id="c6cb3-146">Meddelar till exempel administratörer när skadliga filer identifieras i SharePoint Online, OneDrive eller Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-146">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="c6cb3-147">**Allvarlighetsgrad**: **Välj Låg,** **Medel** eller **Hög** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-147">**Severity**: Select **Low**, **Medium**, or **High** from the drop down list.</span></span>
   - <span data-ttu-id="c6cb3-148">**Kategori:** **Välj Hothantering** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-148">**Category**: Select **Threat management** from the drop down list.</span></span>

   <span data-ttu-id="c6cb3-149">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="c6cb3-150">Konfigurera **följande inställningar på** sidan Skapa aviseringsinställningar:</span><span class="sxs-lookup"><span data-stu-id="c6cb3-150">On the **Create alert settings** page, configure the following settings:</span></span>
   - <span data-ttu-id="c6cb3-151">**Vad vill du avisering om?** avsnitt \> **Aktivitet är** \> Välj Skadlig programvara i **filen** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-151">**What do you want to alert on?** section \> **Activity is** \> Select **Detected malware in file** from the drop down list.</span></span>
   - <span data-ttu-id="c6cb3-152">**Hur vill du att aviseringen ska utlösas?** avsnitt: Lämna standardvärdet **Varje gång en aktivitet matchar den valda** regeln.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-152">**How do you want the alert to be triggered?** section: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="c6cb3-153">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="c6cb3-154">På sidan **Ange mottagare** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="c6cb3-154">On the **Set your recipients** page, configure the following settings:</span></span>
   - <span data-ttu-id="c6cb3-155">Kontrollera **att Skicka e-postaviseringar** är markerat.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-155">Verify **Send email notifications** is selected.</span></span> <span data-ttu-id="c6cb3-156">I rutan **E-postmottagare** markerar du en eller flera globala administratörer, säkerhetsadministratörer eller säkerhetsläsare som ska få ett meddelande när en skadlig fil identifieras.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-156">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="c6cb3-157">**Daglig meddelandegräns:** Lämna standardvärdet **Ingen gräns** markerat.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-157">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="c6cb3-158">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-158">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="c6cb3-159">Granska **inställningarna på sidan** Granska dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-159">On the **Review your settings** page, review your settings.</span></span> <span data-ttu-id="c6cb3-160">Du kan välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-160">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="c6cb3-161">Eller så kan du klicka på **Föregående** eller välj den specifika sidan i guiden.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-161">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="c6cb3-162">I avsnittet Vill du aktivera principen **direkt?** låter du standardvärdet Vara **Ja, aktivera det direkt markerat.**</span><span class="sxs-lookup"><span data-stu-id="c6cb3-162">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="c6cb3-163">Klicka på Slutför när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="c6cb3-163">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="c6cb3-164">Använd Security & Compliance PowerShell för att skapa en aviseringsprincip för identifierade filer</span><span class="sxs-lookup"><span data-stu-id="c6cb3-164">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="c6cb3-165">Om du hellre vill använda PowerShell för att skapa samma aviseringsprincip som beskrivs i föregående avsnitt kan du ansluta till [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) och köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="c6cb3-165">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="c6cb3-166">**Obs!** Standardvärdet _för allvarlighetsgrad_ är Låg.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-166">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="c6cb3-167">Om du vill ange Medel eller Hög tar du _med parametern Allvarlighetsgrad_ och värdet i kommandot.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-167">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="c6cb3-168">Detaljerad information om syntax och parametrar finns [i New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="c6cb3-168">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c6cb3-169">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="c6cb3-169">How do you know these procedures worked?</span></span>

- <span data-ttu-id="c6cb3-170">Kontrollera att du har aktiverat Valv för SharePoint, OneDrive och Microsoft Teams genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="c6cb3-170">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="c6cb3-171">I Microsoft 365 Defender-portalen går du till Avsnittet **Principer &** regler Hotprinciper Valv Bifogade filer , väljer Globala inställningar och verifierar värdet för aktivera Defender för Office 365 för SharePoint, OneDrive och \>  \>  \>  **Microsoft Teams.** </span><span class="sxs-lookup"><span data-stu-id="c6cb3-171">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="c6cb3-172">I Exchange Online PowerShell kör du följande kommando för att verifiera egenskapsinställningen:</span><span class="sxs-lookup"><span data-stu-id="c6cb3-172">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="c6cb3-173">Detaljerad information om syntax och parametrar finns i [Get-AtpPolicyForO365.](/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="c6cb3-173">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="c6cb3-174">Kontrollera att du har blockerat användare från att hämta skadliga filer genom att öppna SharePoint Online PowerShell och köra följande kommando för att verifiera egenskapsvärdet:</span><span class="sxs-lookup"><span data-stu-id="c6cb3-174">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="c6cb3-175">Detaljerad information om syntax och parametrar finns i [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="c6cb3-175">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="c6cb3-176">Verifiera att du har konfigurerat en aviseringsprincip för identifierade filer genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="c6cb3-176">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>
  - <span data-ttu-id="c6cb3-177">I Microsoft 365 Defender-portalen går du **till Principer &** princip för avisering markerar \>  \> aviseringsprincipen och kontrollerar inställningarna.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-177">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** \> select the alert policy, and verify the settings.</span></span>
  - <span data-ttu-id="c6cb3-178">I Microsoft 365 Defender-portalen PowerShell ersätter du med namnet på aviseringsprincipen, kör följande kommando \<AlertPolicyName\> och verifierar egenskapsvärdena:</span><span class="sxs-lookup"><span data-stu-id="c6cb3-178">In Microsoft 365 Defender portal PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="c6cb3-179">Detaljerad information om syntax och parametrar finns i [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="c6cb3-179">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="c6cb3-180">Använd rapporten [status för skydd mot](view-email-security-reports.md#threat-protection-status-report) hot om du vill visa information om identifierade filer i SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-180">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="c6cb3-181">Specifikt kan du använda vyn Visa **data efter: Vyn \> Skadlig** programvara för innehåll.</span><span class="sxs-lookup"><span data-stu-id="c6cb3-181">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
