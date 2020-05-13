---
title: Visa administratörsgranskningsloggen i fristående EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Administratörer kan lära sig att visa och söka i administratörsgranskningsloggen i fristående Exchange Online Protection (EOP).
ms.openlocfilehash: 3aedebc97ccd32c1641510017a276ddbe4770633
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208482"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="3f497-103">Visa administratörsgranskningsloggen i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="3f497-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="3f497-104">I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan du använda Administrationscenter för Exchange (EAC) eller fristående EOP PowerShell för att söka efter och visa poster i administratörsgranskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="3f497-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="3f497-105">Administratörsgranskningsloggen registrerar specifika åtgärder, baserat på fristående EOP PowerShell-cmdletar, som utförs av administratörer och användare som har tilldelats administratörsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="3f497-105">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="3f497-106">Posterna i administratörsgranskningsloggen ger dig information om vad cmdlet kördes, vilka parametrar som användes, vem som körde cmdleten och vilka objekt som påverkades.</span><span class="sxs-lookup"><span data-stu-id="3f497-106">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
> <ul><li><span data-ttu-id="3f497-107">Administratörsgranskningsloggning är aktiverat som standard och du kan inte inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="3f497-107">Admin auditing logging is enabled by default, and you can't disable it.</span></span></li><li><span data-ttu-id="3f497-108">Administratörsgranskningsloggen registrerar inte åtgärder baserat på cmdlets som börjar med verben **Get**, **Search**eller **Test**.</span><span class="sxs-lookup"><span data-stu-id="3f497-108">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span></li><li><span data-ttu-id="3f497-109">Granskningsloggposter sparas i 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="3f497-109">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="3f497-110">När en post är äldre än 90 dagar tas den bort</span><span class="sxs-lookup"><span data-stu-id="3f497-110">When an entry is older than 90 days, it's deleted</span></span></li></ul>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3f497-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="3f497-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3f497-112">Om du vill öppna administrationscentret för Exchange finns [i Administrationscenter för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="3f497-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="3f497-113">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="3f497-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3f497-114">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="3f497-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="3f497-115">Du behöver rollen Granskningsloggar eller granskningsloggar för endast granskning, som tilldelas rollgrupperna ComplianceManagement, OrganizationManagement (global admins) och SecurityAdministrator som standard.</span><span class="sxs-lookup"><span data-stu-id="3f497-115">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="3f497-116">Mer information finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd EAC ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="3f497-116">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="3f497-117">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="3f497-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="3f497-118">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="3f497-118">Having problems?</span></span> <span data-ttu-id="3f497-119">Be om hjälp i Forumet för [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="3f497-119">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="3f497-120">Använd EAC för att visa administratörsgranskningsloggen</span><span class="sxs-lookup"><span data-stu-id="3f497-120">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="3f497-121">Gå till Granskning av **efterlevnadshantering** i EAC \> **Auditing**och välj sedan Kör rapporten **för administratörsgranskningsloggen**.</span><span class="sxs-lookup"><span data-stu-id="3f497-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="3f497-122">På sidan **Sök efter ändringar på administratörsrollgrupper** som öppnas väljer du ett **startdatum** och **slutdatum** (standardintervallet är de senaste två veckorna) och välj sedan **Sök**.</span><span class="sxs-lookup"><span data-stu-id="3f497-122">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="3f497-123">Alla konfigurationsändringar som görs under den angivna tidsperioden visas och kan sorteras med hjälp av följande information:</span><span class="sxs-lookup"><span data-stu-id="3f497-123">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="3f497-124">**Datum**: Datum och tid då konfigurationsändringen gjordes.</span><span class="sxs-lookup"><span data-stu-id="3f497-124">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="3f497-125">Datum och tid lagras i UTC-format (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="3f497-125">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="3f497-126">**Cmdlet**: Namnet på den cmdlet som användes för att göra konfigurationen ändras.</span><span class="sxs-lookup"><span data-stu-id="3f497-126">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="3f497-127">**Användare**: Namnet på användarkontot för den användare som gjorde konfigurationsändringen.</span><span class="sxs-lookup"><span data-stu-id="3f497-127">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="3f497-128">Upp till 5000 poster visas på flera sidor.</span><span class="sxs-lookup"><span data-stu-id="3f497-128">Up to 5000 entries will be displayed on multiple pages.</span></span> <span data-ttu-id="3f497-129">Ange ett mindre datumintervall om du behöver begränsa resultaten.</span><span class="sxs-lookup"><span data-stu-id="3f497-129">Specify a smaller date range if you need to narrow your results.</span></span> <span data-ttu-id="3f497-130">Om du väljer ett enskilt sökresultat visas följande ytterligare information i informationsfönstret:</span><span class="sxs-lookup"><span data-stu-id="3f497-130">If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="3f497-131">**Objektet har ändrats**: Objektet som har ändrats av cmdleten.</span><span class="sxs-lookup"><span data-stu-id="3f497-131">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="3f497-132">**Parametrar (parameter:Värde)**: De cmdletparametrar som användes och alla värden som anges med parametern.</span><span class="sxs-lookup"><span data-stu-id="3f497-132">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="3f497-133">Om du vill skriva ut en viss granskningsloggpost väljer du knappen **Skriv ut** i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3f497-133">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="3f497-134">Använd fristående EOP PowerShell för att visa administratörsgranskningsloggen</span><span class="sxs-lookup"><span data-stu-id="3f497-134">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="3f497-135">Du kan använda fristående EOP PowerShell för att söka efter granskningsloggposter som uppfyller de villkor du anger.</span><span class="sxs-lookup"><span data-stu-id="3f497-135">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="3f497-136">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="3f497-136">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="3f497-137">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="3f497-137">**Notes**:</span></span>

- <span data-ttu-id="3f497-138">Du kan bara använda _parametern Parametrar_ tillsammans med parametern _Cmdlets._</span><span class="sxs-lookup"><span data-stu-id="3f497-138">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="3f497-139">Parametern _ObjectIds filtrerar_ resultatet efter objektet som ändrades av cmdleten.</span><span class="sxs-lookup"><span data-stu-id="3f497-139">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="3f497-140">Ett giltigt värde beror på hur objektet representeras i granskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="3f497-140">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="3f497-141">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="3f497-141">For example:</span></span>

  - <span data-ttu-id="3f497-142">Namn</span><span class="sxs-lookup"><span data-stu-id="3f497-142">Name</span></span>
  - <span data-ttu-id="3f497-143">Kanoniskt unikt namn (till exempel contoso.com/Users/Akia Al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="3f497-143">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="3f497-144">Du kommer förmodligen att behöva använda andra filtreringsparametrar på den här cmdleten för att begränsa resultaten och identifiera vilka typer av objekt som du är intresserad av.</span><span class="sxs-lookup"><span data-stu-id="3f497-144">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="3f497-145">Parametern _UserIds_ filtrerar resultatet av den användare som gjorde ändringen (som körde cmdleten).</span><span class="sxs-lookup"><span data-stu-id="3f497-145">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="3f497-146">Om du anger ett datum-/tidsvärde utan tidszon för _parametrarna StartDate_ och _EndDate_ finns värdet i Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="3f497-146">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="3f497-147">Om du vill ange ett datum-/tidsvärde för den här parametern använder du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="3f497-147">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="3f497-148">Ange datum-/tidsvärdet i UTC: Till exempel "2016-05-06 14:30:00z".</span><span class="sxs-lookup"><span data-stu-id="3f497-148">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="3f497-149">Ange datum-/tidsvärdet som en formel som konverterar datum/tid i den lokala tidszonen till UTC: Till exempel `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` .</span><span class="sxs-lookup"><span data-stu-id="3f497-149">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="3f497-150">Mer information finns i [Hämta datum](https://go.microsoft.com/fwlink/p/?LinkID=113313).</span><span class="sxs-lookup"><span data-stu-id="3f497-150">For more information, see [Get-Date](https://go.microsoft.com/fwlink/p/?LinkID=113313).</span></span>

- <span data-ttu-id="3f497-151">Cmdlet returnerar som standard högst 1 000 loggposter.</span><span class="sxs-lookup"><span data-stu-id="3f497-151">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="3f497-152">Använd parametern _ResultSize_ för att ange upp till 250 000 loggposter.</span><span class="sxs-lookup"><span data-stu-id="3f497-152">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="3f497-153">Du kan också använda värdet `Unlimited` för att returnera alla transaktioner.</span><span class="sxs-lookup"><span data-stu-id="3f497-153">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="3f497-154">I det här exemplet söker du efter alla granskningsloggposter med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3f497-154">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="3f497-155">**Startdatum**: 4 augusti 2019</span><span class="sxs-lookup"><span data-stu-id="3f497-155">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="3f497-156">**Slutdatum**: 3 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="3f497-156">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="3f497-157">**Cmdlets**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="3f497-157">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="3f497-158">Detaljerad syntax- och parameterinformation finns i [Sök-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="3f497-158">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="3f497-159">Visa information om granskningsloggposter</span><span class="sxs-lookup"><span data-stu-id="3f497-159">View details of audit log entries</span></span>

<span data-ttu-id="3f497-160">**Cmdlet search-adminAuditLog** returnerar de fält som beskrivs i avsnittet [Granskningslogginnehåll](#audit-log-contents) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="3f497-160">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this topic.</span></span> <span data-ttu-id="3f497-161">Av de fält som returneras av cmdlet, två fält, **CmdletParameters** och **ModifiedProperties**, innehåller ytterligare information som inte returneras som standard.</span><span class="sxs-lookup"><span data-stu-id="3f497-161">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="3f497-162">Om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** använder du följande steg.</span><span class="sxs-lookup"><span data-stu-id="3f497-162">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="3f497-163">Bestäm vilka villkor du vill söka efter, kör cmdleten **Sök-AdminAuditLog** och lagra resultaten i en variabel med följande kommando.</span><span class="sxs-lookup"><span data-stu-id="3f497-163">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="3f497-164">Varje granskningsloggpost lagras som ett matriselement i variabeln `$Results` .</span><span class="sxs-lookup"><span data-stu-id="3f497-164">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="3f497-165">Du kan markera ett matriselement genom att ange dess matriselementindex.</span><span class="sxs-lookup"><span data-stu-id="3f497-165">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="3f497-166">Matriselementindex börjar vid noll (0) för det första matriselementet.</span><span class="sxs-lookup"><span data-stu-id="3f497-166">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="3f497-167">Om du till exempel vill hämta det 5:e matriselementet, som har ett index på 4, använder du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="3f497-167">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="3f497-168">Föregående kommando returnerar loggposten som lagras i matriselement 4.</span><span class="sxs-lookup"><span data-stu-id="3f497-168">The previous command returns the log entry stored in array element 4.</span></span> <span data-ttu-id="3f497-169">Om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** för den här loggposten använder du följande kommandon.</span><span class="sxs-lookup"><span data-stu-id="3f497-169">To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="3f497-170">Om du vill visa innehållet i fälten **CmdletParameters** eller **ModifiedParameters** i en annan loggpost ändrar du matriselementindexet.</span><span class="sxs-lookup"><span data-stu-id="3f497-170">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="3f497-171">Innehåll i granskningsloggen</span><span class="sxs-lookup"><span data-stu-id="3f497-171">Audit log contents</span></span>

<span data-ttu-id="3f497-172">Varje granskningsloggpost innehåller den information som beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="3f497-172">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="3f497-173">Granskningsloggen innehåller en eller flera granskningsloggposter.</span><span class="sxs-lookup"><span data-stu-id="3f497-173">The audit log contains one or more audit log entries.</span></span>

|||
|---|---|
|<span data-ttu-id="3f497-174">**Fält**</span><span class="sxs-lookup"><span data-stu-id="3f497-174">**Field**</span></span>|<span data-ttu-id="3f497-175">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="3f497-175">**Description**</span></span>|
|`RunspaceId`|<span data-ttu-id="3f497-176">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3f497-176">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="3f497-177">Det här fältet innehåller det objekt som har ändrats av den cmdlet som anges i `CmdletName` fältet .</span><span class="sxs-lookup"><span data-stu-id="3f497-177">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="3f497-178">Det här fältet innehåller namnet på den cmdlet som kördes av användaren i `Caller` fältet .</span><span class="sxs-lookup"><span data-stu-id="3f497-178">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="3f497-179">Det här fältet innehåller de parametrar som angavs när cmdleten i `CmdletName` fältet kördes.</span><span class="sxs-lookup"><span data-stu-id="3f497-179">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="3f497-180">Också lagras i det här fältet, men inte synlig i standardutdata, är det värde som anges med parametern, om någon.</span><span class="sxs-lookup"><span data-stu-id="3f497-180">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="3f497-181">Det här fältet innehåller de egenskaper som har ändrats för objektet i `ObjectModified` fältet.</span><span class="sxs-lookup"><span data-stu-id="3f497-181">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="3f497-182">Också lagras i det här fältet, men inte synlig i standardutdata, är det gamla värdet för egenskapen och det nya värdet som lagrades.</span><span class="sxs-lookup"><span data-stu-id="3f497-182">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="3f497-183">Det här fältet innehåller användarkontot för den användare som körde cmdleten i `CmdletName` fältet .</span><span class="sxs-lookup"><span data-stu-id="3f497-183">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="3f497-184">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3f497-184">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="3f497-185">Det här fältet anger om cmdleten i `CmdletName` fältet kördes.</span><span class="sxs-lookup"><span data-stu-id="3f497-185">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="3f497-186">Värdet är antingen `True` eller `False` .</span><span class="sxs-lookup"><span data-stu-id="3f497-186">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="3f497-187">Det här fältet innehåller felmeddelandet som genereras om cmdleten i `CmdletName` fältet inte kunde slutföras.</span><span class="sxs-lookup"><span data-stu-id="3f497-187">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="3f497-188">Det här fältet innehåller datum och tid då cmdleten i `CmdletName` fältet kördes.</span><span class="sxs-lookup"><span data-stu-id="3f497-188">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="3f497-189">Datum och tid lagras i UTC-format (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="3f497-189">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="3f497-190">Det här fältet anger den server där den cmdlet som anges i `CmdletName` fältet kördes.</span><span class="sxs-lookup"><span data-stu-id="3f497-190">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="3f497-191">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3f497-191">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="3f497-192">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3f497-192">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="3f497-193">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3f497-193">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="3f497-194">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3f497-194">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="3f497-195">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3f497-195">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="3f497-196">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3f497-196">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="3f497-197">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3f497-197">This field is used internally by EOP.</span></span>|
|
