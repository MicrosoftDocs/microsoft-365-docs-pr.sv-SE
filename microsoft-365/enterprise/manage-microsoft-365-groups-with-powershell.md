---
title: Hantera Microsoft 365-grupper med PowerShell
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: I den här artikeln lär du dig hur du utför vanliga hanterings uppgifter för Microsoft 365-grupper i PowerShell.
ms.openlocfilehash: c1aa551597644b7f41c3445a791ea27579464f7b
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277480"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="54bfc-103">Hantera Microsoft 365-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="54bfc-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="54bfc-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="54bfc-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="54bfc-105">I den här artikeln finns anvisningar för att utföra vanliga hanterings uppgifter för grupper i Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54bfc-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="54bfc-106">Dessutom visas PowerShell-cmdletar för grupper.</span><span class="sxs-lookup"><span data-stu-id="54bfc-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="54bfc-107">Information om hur du hanterar SharePoint-webbplatser finns i [hantera SharePoint Online-webbplatser med PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="54bfc-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="54bfc-108">Länk till dina användnings rikt linjer för Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="54bfc-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="54bfc-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="54bfc-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="54bfc-110">När användare [skapar eller redigerar en grupp i Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)kan du visa dem en länk till organisationens rikt linjer för användning.</span><span class="sxs-lookup"><span data-stu-id="54bfc-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="54bfc-111">Om du till exempel vill lägga till ett prefix eller suffix i ett grupp namn.</span><span class="sxs-lookup"><span data-stu-id="54bfc-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="54bfc-112">Använd Azure Active Directory (Azure AD) PowerShell för att hänvisa användarna till organisationens användnings rikt linjer för Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="54bfc-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="54bfc-113">Kolla in [Azure Active Directory-cmdlets för att konfigurera grupp inställningar](https://go.microsoft.com/fwlink/?LinkID=827484) och följ stegen i **skapa inställningar på katalog nivå** för att definiera länken för användnings rikt linjer.</span><span class="sxs-lookup"><span data-stu-id="54bfc-113">Check out [Azure Active Directory cmdlets for configuring group settings](https://go.microsoft.com/fwlink/?LinkID=827484) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="54bfc-114">När du kör AAD-cmdleten visas länken till dina rikt linjer när de skapar eller redigerar en grupp i Outlook.</span><span class="sxs-lookup"><span data-stu-id="54bfc-114">Once you run the AAD cmdlet, user's will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![Skapa en ny grupp med länken för användnings regler](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Klicka på rikt linjer för grupp användning för att se dina organisationers Office 365-regler](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="54bfc-117">Tillåt användare att skicka som Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="54bfc-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="54bfc-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="54bfc-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="54bfc-119">Om du vill aktivera dina Microsoft 365-grupper till "Skicka som" använder du cmdletarna [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) och [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) för att konfigurera detta.</span><span class="sxs-lookup"><span data-stu-id="54bfc-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="54bfc-120">När du aktiverar den här inställningen kan Microsoft 365 Group-användare använda Outlook eller Outlook på webben för att skicka och svara på e-post som Microsoft 365-gruppen.</span><span class="sxs-lookup"><span data-stu-id="54bfc-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="54bfc-121">Användare kan gå till gruppen, skapa ett nytt e-postmeddelande och ändra fältet "Skicka som" till gruppens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="54bfc-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="54bfc-122">([Du kan också göra det i administrations centret för Exchange](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span><span class="sxs-lookup"><span data-stu-id="54bfc-122">([You can also do this in the Exchange Admin Center](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="54bfc-123">Använd följande skript, Ersätt *\<GroupAlias\>* med alias för den grupp du vill uppdatera och *\<UserAlias\>* med alias för den användare som du vill ge behörighet till.</span><span class="sxs-lookup"><span data-stu-id="54bfc-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="54bfc-124">[Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) för att köra det här skriptet.</span><span class="sxs-lookup"><span data-stu-id="54bfc-124">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="54bfc-125">När cmdleten körs kan användarna gå till Outlook eller Outlook på webben och skicka som grupper genom att lägga till gruppens e-postadress i fältet **från** .</span><span class="sxs-lookup"><span data-stu-id="54bfc-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="54bfc-126">Skapa klassificeringar för Microsoft 365-grupper i organisationen</span><span class="sxs-lookup"><span data-stu-id="54bfc-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="54bfc-127">Du kan skapa känslighets etiketter som användarna i organisationen kan ange när de skapar en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="54bfc-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="54bfc-128">Om du vill klassificera grupper rekommenderar vi att du använder känslighets etiketter i stället för de tidigare funktionerna för grupp klassificering.</span><span class="sxs-lookup"><span data-stu-id="54bfc-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="54bfc-129">Information om hur du använder känslighets etiketter finns i [använda känslighets etiketter för att skydda innehåll i Microsoft Teams, microsoft 365 Groups och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="54bfc-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54bfc-130">Om du använder klassificerings etiketter är de inte längre tillgängliga för användare som skapar grupper när du har aktiverat känslighets etiketter.</span><span class="sxs-lookup"><span data-stu-id="54bfc-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="54bfc-131">Du kan fortfarande använda den föregående gruppen klassificerings funktion.</span><span class="sxs-lookup"><span data-stu-id="54bfc-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="54bfc-132">Du kan skapa klassificeringar som användarna i organisationen kan ange när de skapar en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="54bfc-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="54bfc-133">Du kan till exempel låta användarna ställa in "standard", "hemligt" och "Top Secret" i grupper som de skapar.</span><span class="sxs-lookup"><span data-stu-id="54bfc-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="54bfc-134">Grupp klassificeringar är inte standard och du måste skapa det för att användarna ska kunna ställa in den.</span><span class="sxs-lookup"><span data-stu-id="54bfc-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="54bfc-135">Använd Azure Active Directory PowerShell för att hänvisa användarna till organisationens användnings rikt linjer för Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="54bfc-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="54bfc-136">Kolla in [Azure Active Directory-cmdlets för att konfigurera grupp inställningar](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) och följ stegen i **skapa inställningar på katalog nivå** för att definiera klassificeringen för Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="54bfc-136">Check out [Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="54bfc-137">Om du vill koppla en beskrivning till varje klassificering kan du använda attributet Settings  *klassificerings beskrivningar* för att definiera.</span><span class="sxs-lookup"><span data-stu-id="54bfc-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="54bfc-138">där klassificering matchar strängarna i klassificerings lista.</span><span class="sxs-lookup"><span data-stu-id="54bfc-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="54bfc-139">Exempel:</span><span class="sxs-lookup"><span data-stu-id="54bfc-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="54bfc-140">När du har kört den här Azure Active Directory-cmdleten för att ange din klassificering kör du cmdleten [set-unifiedgrouphttps](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) om du vill ange klassificering för en viss grupp.</span><span class="sxs-lookup"><span data-stu-id="54bfc-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="54bfc-141">Eller skapa en ny grupp med en klassificering.</span><span class="sxs-lookup"><span data-stu-id="54bfc-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="54bfc-142">Läs [Använda PowerShell med Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) och [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) om du vill ha mer information om hur du använder Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54bfc-142">Check out [Using PowerShell with Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="54bfc-143">När de här inställningarna är aktiverade kan gruppens ägare välja en klassificering från den nedrullningsbara menyn i Outlook på webben och i Outlook och sedan spara den från sidan **Redigera** grupp.</span><span class="sxs-lookup"><span data-stu-id="54bfc-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![Välj Microsoft 365-grupp klassificering](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="54bfc-145">Dölj Microsoft 365-grupper från den globala adress listan.</span><span class="sxs-lookup"><span data-stu-id="54bfc-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="54bfc-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="54bfc-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="54bfc-147">Du kan ange om en Microsoft 365-grupp visas i den globala adress listan (GAL) och andra listor i organisationen.</span><span class="sxs-lookup"><span data-stu-id="54bfc-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="54bfc-148">Om du till exempel har en juridisk avdelnings grupp som du inte vill visa i adress listan kan du stoppa gruppen från att visas i GAL.</span><span class="sxs-lookup"><span data-stu-id="54bfc-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="54bfc-149">Kör cmdleten Set-Ungroup för att dölja gruppen från adress listan så här:</span><span class="sxs-lookup"><span data-stu-id="54bfc-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="54bfc-150">Tillåt endast interna användare att skicka meddelanden till Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="54bfc-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="54bfc-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="54bfc-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="54bfc-152">Om du inte vill att användare från andra organisationer ska kunna skicka e-post till en Microsoft 365-grupp kan du ändra inställningarna för gruppen.</span><span class="sxs-lookup"><span data-stu-id="54bfc-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="54bfc-153">Den tillåter bara interna användare att skicka ett e-postmeddelande till din grupp.</span><span class="sxs-lookup"><span data-stu-id="54bfc-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="54bfc-154">Om en extern användare försöker skicka ett meddelande till gruppen kommer den att nekas.</span><span class="sxs-lookup"><span data-stu-id="54bfc-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="54bfc-155">Kör cmdleten Set-Unifiedgrouphttps för att uppdatera den här inställningen:</span><span class="sxs-lookup"><span data-stu-id="54bfc-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="54bfc-156">Lägga till e-posttips för Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="54bfc-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="54bfc-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="54bfc-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="54bfc-158">När en avsändare försöker skicka ett e-postmeddelande till en Microsoft 365-grupp kan en posttips visas för dem.</span><span class="sxs-lookup"><span data-stu-id="54bfc-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="54bfc-159">Kör cmdleten Set-Ungroup för att lägga till en posttips i gruppen:</span><span class="sxs-lookup"><span data-stu-id="54bfc-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="54bfc-160">Tillsammans med posttips kan du också ange MailTipTranslations som anger ytterligare språk för posttips.</span><span class="sxs-lookup"><span data-stu-id="54bfc-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="54bfc-161">Anta att du vill ha en spansk översättning och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="54bfc-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="54bfc-162">Ändra visnings namnet för Microsoft 365-gruppen</span><span class="sxs-lookup"><span data-stu-id="54bfc-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="54bfc-163">Visnings namnet anger namnet på Microsoft 365-gruppen.</span><span class="sxs-lookup"><span data-stu-id="54bfc-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="54bfc-164">Du kan se detta namn i administrations centret för Exchange eller Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="54bfc-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="54bfc-165">Du kan redigera gruppens visnings namn eller tilldela ett visnings namn till en befintlig Microsoft 365-grupp genom att köra kommandot Set-Unifiedgrouphttps:</span><span class="sxs-lookup"><span data-stu-id="54bfc-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="54bfc-166">Ändra standardinställningen för Microsoft 365 Groups för Outlook till offentlig eller privat</span><span class="sxs-lookup"><span data-stu-id="54bfc-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="54bfc-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="54bfc-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="54bfc-168">Microsoft 365-grupper i Outlook skapas som privata som standard.</span><span class="sxs-lookup"><span data-stu-id="54bfc-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="54bfc-169">Om din organisation vill att Microsoft 365-grupper ska skapas som offentliga som standard (eller tillbaka till privat) använder du följande PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="54bfc-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="54bfc-170">Så här anger du till privat:</span><span class="sxs-lookup"><span data-stu-id="54bfc-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="54bfc-171">Så här kontrollerar du inställningen:</span><span class="sxs-lookup"><span data-stu-id="54bfc-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="54bfc-172">Mer information finns i [set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).</span><span class="sxs-lookup"><span data-stu-id="54bfc-172">To learn more, see [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="54bfc-173">Cmdlets för Microsoft 365 Groups</span><span class="sxs-lookup"><span data-stu-id="54bfc-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="54bfc-174">Följande cmdletar kan användas med Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="54bfc-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="54bfc-175">**Namn på cmdlet**</span><span class="sxs-lookup"><span data-stu-id="54bfc-175">**Cmdlet name**</span></span>|<span data-ttu-id="54bfc-176">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="54bfc-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="54bfc-177">Get-Unifiedgrouphttps</span><span class="sxs-lookup"><span data-stu-id="54bfc-177">Get-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |<span data-ttu-id="54bfc-178">Använd denna cmdlet för att slå upp befintliga Microsoft 365-grupper och för att visa egenskaperna för gruppobjektet</span><span class="sxs-lookup"><span data-stu-id="54bfc-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="54bfc-179">Set-Unifiedgrouphttps</span><span class="sxs-lookup"><span data-stu-id="54bfc-179">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |<span data-ttu-id="54bfc-180">Uppdatera egenskaperna för en viss Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="54bfc-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="54bfc-181">New-Unifiedgrouphttps</span><span class="sxs-lookup"><span data-stu-id="54bfc-181">New-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |<span data-ttu-id="54bfc-182">Skapa en ny Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="54bfc-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="54bfc-183">Denna cmdlet ger en minimal uppsättning parametrar.</span><span class="sxs-lookup"><span data-stu-id="54bfc-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="54bfc-184">Om du vill ange värden för utökade egenskaper använder du Set-Unifiedgrouphttps när du har skapat den nya gruppen</span><span class="sxs-lookup"><span data-stu-id="54bfc-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="54bfc-185">Remove-Unifiedgrouphttps</span><span class="sxs-lookup"><span data-stu-id="54bfc-185">Remove-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |<span data-ttu-id="54bfc-186">Ta bort en befintlig Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="54bfc-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="54bfc-187">Get-Unifiedgrouplinkshttps</span><span class="sxs-lookup"><span data-stu-id="54bfc-187">Get-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |<span data-ttu-id="54bfc-188">Hämta information om medlemskap och ägare för en Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="54bfc-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="54bfc-189">Add-Unifiedgrouplinkshttps</span><span class="sxs-lookup"><span data-stu-id="54bfc-189">Add-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |<span data-ttu-id="54bfc-190">Lägga till hundratals eller tusentals användare, eller nya ägare, i en befintlig Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="54bfc-190">Add hundreds or thousands of users, or new owners, to an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="54bfc-191">Remove-Unifiedgrouplinkshttps</span><span class="sxs-lookup"><span data-stu-id="54bfc-191">Remove-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |<span data-ttu-id="54bfc-192">Ta bort ägare och medlemmar från en befintlig Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="54bfc-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="54bfc-193">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="54bfc-193">Get-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |<span data-ttu-id="54bfc-194">Används för att visa information om användar fotot som är kopplat till ett konto.</span><span class="sxs-lookup"><span data-stu-id="54bfc-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="54bfc-195">Användar foton lagras i Active Directory</span><span class="sxs-lookup"><span data-stu-id="54bfc-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="54bfc-196">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="54bfc-196">Set-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |<span data-ttu-id="54bfc-197">Används för att koppla en användar bild till ett konto.</span><span class="sxs-lookup"><span data-stu-id="54bfc-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="54bfc-198">Användar foton lagras i Active Directory</span><span class="sxs-lookup"><span data-stu-id="54bfc-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="54bfc-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="54bfc-199">Remove-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |<span data-ttu-id="54bfc-200">Ta bort fotot för en Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="54bfc-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="54bfc-201">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="54bfc-201">Related topics</span></span>

[<span data-ttu-id="54bfc-202">Uppgradera distributions listor till Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="54bfc-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="54bfc-203">Hantera vilka som kan skapa Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="54bfc-203">Manage who can create Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="54bfc-204">Hantera gäst åtkomst till Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="54bfc-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="54bfc-205">Ändra medlemskap i statisk grupp till dynamisk i</span><span class="sxs-lookup"><span data-stu-id="54bfc-205">Change static group membership to dynamic in</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
