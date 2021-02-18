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
description: Administratörer kan lära sig hur de aktiverar Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams, inklusive hur du ställer in aviseringar för identifierade filer.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9688af82d194b1818d6bd3323d39bde51db20cb2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286375"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="16d15-103">Aktivera säkra bilagor för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16d15-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="16d15-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="16d15-104">**Applies to**</span></span>
- [<span data-ttu-id="16d15-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="16d15-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="16d15-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16d15-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="16d15-107">Microsoft Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams skyddar organisationen från att oavsiktligt dela skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="16d15-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="16d15-108">Mer information finns i Säkra [bifogade filer för SharePoint, OneDrive och Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="16d15-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="16d15-109">Den här artikeln innehåller anvisningar för hur du aktiverar och konfigurerar säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="16d15-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="16d15-110">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="16d15-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="16d15-111">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="16d15-111">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="16d15-112">Gå direkt till **atp-sidan för säkra bifogade** filer genom att <https://protection.office.com/safeattachmentv2> öppna.</span><span class="sxs-lookup"><span data-stu-id="16d15-112">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="16d15-113">Om du vill aktivera Säkra bifogade filer för SharePoint, OneDrive och  Microsoft  Teams måste du vara medlem i rollgrupperna Organisationshantering eller Säkerhetsadministratör i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="16d15-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="16d15-114">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="16d15-114">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="16d15-115">Om du vill använda SharePoint Online PowerShell för att förhindra att användare laddar ned skadliga filer måste du vara medlem i rollerna [Global administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) eller [SharePoint-administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="16d15-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="16d15-116">Kontrollera att granskningsloggning är aktiverad för organisationen.</span><span class="sxs-lookup"><span data-stu-id="16d15-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="16d15-117">Mer information finns i Aktivera [eller inaktivera granskningsloggsökning.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="16d15-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="16d15-118">Det kan ta upp till 30 minuter innan inställningarna verkställs.</span><span class="sxs-lookup"><span data-stu-id="16d15-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="16d15-119">Steg 1: Använd Säkerhets- & för att aktivera Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16d15-119">Step 1: Use the Security & Compliance Center to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="16d15-120">Gå till  ATP för & säkerhets- och efterlevnadscenter och klicka på \>  \>  **Globala inställningar.**</span><span class="sxs-lookup"><span data-stu-id="16d15-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="16d15-121">I den globala inställningsflaggan som visas går du till Aktivera Defender för **Office 365 för SharePoint, OneDrive och Microsoft Teams-inställningen.** </span><span class="sxs-lookup"><span data-stu-id="16d15-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="16d15-122">Flytta reglaget till höger omkopplare för att aktivera Säkra bifogade ![ ](../../media/scc-toggle-on.png) filer för SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="16d15-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="16d15-123">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="16d15-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="16d15-124">Använda Exchange Online PowerShell för att aktivera Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16d15-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="16d15-125">Om du hellre vill använda PowerShell för att aktivera Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams ansluter du till [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="16d15-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="16d15-126">Detaljerad information om syntax och parametrar finns [i Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="16d15-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="16d15-127">Steg 2: (Rekommenderas) Använd SharePoint Online PowerShell för att hindra användare från att ladda ned skadliga filer</span><span class="sxs-lookup"><span data-stu-id="16d15-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="16d15-128">Som standard kan användare inte öppna, flytta, kopiera eller dela skadliga filer som identifieras av ATP.</span><span class="sxs-lookup"><span data-stu-id="16d15-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="16d15-129">Däremot kan de ta bort och ladda ned skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="16d15-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="16d15-130">Om du vill hindra användare från att ladda ned skadliga [filer ansluter du till SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="16d15-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="16d15-131">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="16d15-131">**Notes**:</span></span>

- <span data-ttu-id="16d15-132">Den här inställningen påverkar både användare och administratörer.</span><span class="sxs-lookup"><span data-stu-id="16d15-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="16d15-133">Användare kan fortfarande ta bort skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="16d15-133">People can still delete malicious files.</span></span>

<span data-ttu-id="16d15-134">Detaljerad information om syntax och parametrar finns [i Set-SPOTenant.](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="16d15-134">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="16d15-135">Steg 3 (rekommenderas) Använd Säkerhets- & Center för att skapa en aviseringsprincip för identifierade filer</span><span class="sxs-lookup"><span data-stu-id="16d15-135">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="16d15-136">Du kan skapa en aviseringsprincip som meddelar dig och andra administratörer när säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams identifierar en skadlig fil.</span><span class="sxs-lookup"><span data-stu-id="16d15-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="16d15-137">Mer information om aviseringar finns i [Skapa aktivitetsaviseringar i Säkerhets- & Efterlevnadscenter.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="16d15-137">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="16d15-138">Gå till [aviseringsprinciperna eller öppna i säkerhets-](https://protection.office.com)och **&** säkerhets- \>  och efterlevnadscentret. <https://protection.office.com/alertpolicies></span><span class="sxs-lookup"><span data-stu-id="16d15-138">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="16d15-139">Klicka på **Ny aviseringsprincip** **på sidan Aviseringsprinciper.**</span><span class="sxs-lookup"><span data-stu-id="16d15-139">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="16d15-140">Guiden **Ny aviseringsprincip** öppnas i en farten. På sidan **Namnge din avisering** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="16d15-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="16d15-141">**Namn:** Ange ett unikt och beskrivande namn.</span><span class="sxs-lookup"><span data-stu-id="16d15-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="16d15-142">Till exempel skadliga filer i bibliotek.</span><span class="sxs-lookup"><span data-stu-id="16d15-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="16d15-143">**Beskrivning:** Ange en valfri beskrivning.</span><span class="sxs-lookup"><span data-stu-id="16d15-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="16d15-144">Meddela till exempel administratörer när skadliga filer upptäcks i SharePoint Online, OneDrive eller Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="16d15-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="16d15-145">**Allvarlighetsgrad:** Lämna standardvärdet **Låg markerat** eller välj **Medel** eller **Hög.**</span><span class="sxs-lookup"><span data-stu-id="16d15-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="16d15-146">**Välj en kategori:** Välj **Hothantering.**</span><span class="sxs-lookup"><span data-stu-id="16d15-146">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="16d15-147">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="16d15-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="16d15-148">Konfigurera **följande inställningar på** sidan Skapa aviseringsinställningar:</span><span class="sxs-lookup"><span data-stu-id="16d15-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="16d15-149">**Vad vill du avisering om?: Aktivitet är:** Välj **Identifierade skadlig programvara i filen.**</span><span class="sxs-lookup"><span data-stu-id="16d15-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="16d15-150">**Hur vill du att aviseringen ska utlösas?**: Lämna standardvärdet varje gång en **aktivitet matchar den valda** regeln.</span><span class="sxs-lookup"><span data-stu-id="16d15-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="16d15-151">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="16d15-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="16d15-152">Konfigurera **följande inställningar på** sidan Ange mottagare:</span><span class="sxs-lookup"><span data-stu-id="16d15-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="16d15-153">**Skicka e-postaviseringar:** Kontrollera att den här inställningen är markerad.</span><span class="sxs-lookup"><span data-stu-id="16d15-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="16d15-154">I rutan **E-postmottagare** väljer du en eller flera globala administratörer, säkerhetsadministratörer eller säkerhetsläsare som ska få ett meddelande när en skadlig fil identifieras.</span><span class="sxs-lookup"><span data-stu-id="16d15-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="16d15-155">**Daglig meddelandegräns:** Lämna standardvärdet **Ingen gräns** markerat.</span><span class="sxs-lookup"><span data-stu-id="16d15-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="16d15-156">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="16d15-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="16d15-157">Granska inställningarna **på sidan Granska** dina inställningar och klicka på Redigera **i** något av avsnitten för att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="16d15-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="16d15-158">I avsnittet Vill du aktivera principen på **en gång?** låter du standardvärdet vara Ja, aktivera **det direkt markerat.**</span><span class="sxs-lookup"><span data-stu-id="16d15-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="16d15-159">Klicka på Slutför när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="16d15-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="16d15-160">Använd Säkerhets- & PowerShell för att skapa en aviseringsprincip för identifierade filer</span><span class="sxs-lookup"><span data-stu-id="16d15-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="16d15-161">Om du hellre vill använda PowerShell för att skapa samma aviseringsprincip som beskrivs i föregående avsnitt, ansluter du till [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="16d15-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="16d15-162">**Obs!** Standardvärdet _för allvarlighetsgrad_ är Låg.</span><span class="sxs-lookup"><span data-stu-id="16d15-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="16d15-163">Om du vill ange medel eller hög tar du med _parametern_ allvarlighetsgrad och värde i kommandot.</span><span class="sxs-lookup"><span data-stu-id="16d15-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="16d15-164">Detaljerad information om syntax och parametrar finns [i New-ActivityAlert.](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)</span><span class="sxs-lookup"><span data-stu-id="16d15-164">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="16d15-165">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="16d15-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="16d15-166">Kontrollera att du har aktiverat Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="16d15-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="16d15-167">I [Säkerhets- &](https://protection.office.com)Efterlevnadscenter går  du till ATP för hanteringspolicy för säkra bifogade filer, väljer globala inställningar och verifierar värdet för inställningen Aktivera Defender för \>  \>  **Office 365 för SharePoint, OneDrive** och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="16d15-167">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="16d15-168">Kör följande kommando i Exchange Online PowerShell för att verifiera egenskapsinställningen:</span><span class="sxs-lookup"><span data-stu-id="16d15-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="16d15-169">Detaljerad information om syntax och parametrar finns i [Get-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="16d15-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="16d15-170">Kontrollera att du har blockerat användare från att ladda ned skadliga filer genom att öppna SharePoint Online PowerShell och köra följande kommando för att verifiera egenskapsvärdet:</span><span class="sxs-lookup"><span data-stu-id="16d15-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="16d15-171">Detaljerad information om syntax och parametrar finns [i Get-SPOTenant.](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="16d15-171">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="16d15-172">Kontrollera att du har konfigurerat en aviseringsprincip för identifierade filer genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="16d15-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="16d15-173">I Säkerhets- & säkerhets- och **efterlevnadscenter** går du till aviseringsprinciperna för \>  \> aviseringar, väljer aviseringsprincipen och kontrollerar inställningarna.</span><span class="sxs-lookup"><span data-stu-id="16d15-173">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="16d15-174">I Säkerhetscenter & PowerShell ersätter du med namnet på aviseringsprincipen, kör följande kommando \<AlertPolicyName\> och verifierar egenskapsvärdena:</span><span class="sxs-lookup"><span data-stu-id="16d15-174">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="16d15-175">Detaljerad information om syntax och parametrar finns [i Get-ActivityAlert.](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)</span><span class="sxs-lookup"><span data-stu-id="16d15-175">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="16d15-176">Använd [statusrapporten för skydd mot](view-email-security-reports.md#threat-protection-status-report) hot för att visa information om identifierade filer i SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="16d15-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="16d15-177">Mer specifikt kan du använda vyn **Visa data efter: Vyn \> Skadlig** programvara för innehåll.</span><span class="sxs-lookup"><span data-stu-id="16d15-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
