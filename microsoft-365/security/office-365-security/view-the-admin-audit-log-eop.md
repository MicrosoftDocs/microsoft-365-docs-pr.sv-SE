---
title: Visa administratörsgranskningsloggen i fristående EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Administratörer kan lära sig att visa och söka i administratörs gransknings loggen i fristående Exchange Online Protection (EOP).
ms.openlocfilehash: 8890ab8f2f2db01ed6bd22657a9bea8f77b25d08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825083"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="2b7c4-103">Visa administratörsgranskningsloggen i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="2b7c4-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="2b7c4-104">I fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor kan du använda Exchange Admin Center (UK) eller fristående EOP PowerShell för att söka efter och Visa poster i administratörs gransknings loggen.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="2b7c4-105">Administratörs gransknings loggen registrerar specifika åtgärder baserat på fristående EOP PowerShell-cmdlets, som utförs av administratörer och användare som har tilldelats administratörs behörighet.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-105">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="2b7c4-106">Poster i administratörs gransknings loggen ger dig information om vilken cmdlet som kördes, vilka parametrar som användes, vem som körde cmdleten och vilka objekt som påverkades.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-106">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="2b7c4-107">Loggning för administratörs granskning är aktiverat som standard och kan inte inaktive ras.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-107">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="2b7c4-108">Administratörs gransknings loggen spelar inte in åtgärder baserat på cmdlets som börjar med verben **Get**, **search**eller **test**.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-108">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="2b7c4-109">Gransknings logg poster bevaras i 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-109">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="2b7c4-110">När en post är äldre än 90 dagar raderas den</span><span class="sxs-lookup"><span data-stu-id="2b7c4-110">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2b7c4-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="2b7c4-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2b7c4-112">Om du vill öppna administrations centret för Exchange går du till [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="2b7c4-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="2b7c4-113">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="2b7c4-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2b7c4-114">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="2b7c4-115">Specifikt måste du ha rollen gransknings loggar eller skrivskyddade loggar, som är tilldelad till ComplianceManagement, i (globala administratörer) och SecurityAdministrator roll grupper som standard.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-115">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="2b7c4-116">Mer information finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd UK för att ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="2b7c4-116">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="2b7c4-117">Information om tangent bords gen vägar som kan gälla för procedurerna i det här avsnittet finns i kortkommandon [för administrations centret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="2b7c4-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="2b7c4-118">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="2b7c4-118">Having problems?</span></span> <span data-ttu-id="2b7c4-119">Be om hjälp i [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-119">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="2b7c4-120">Använda UK för att Visa administratörs gransknings loggen</span><span class="sxs-lookup"><span data-stu-id="2b7c4-120">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="2b7c4-121">Gå till granskning i **överensstämmelse hantering** i UK \> **Auditing**och välj sedan **kör rapporten administratörs Gransknings logg**.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="2b7c4-122">Välj ett **start datum** och **slutdatum** i listan **Sök efter ändringar på sidan för administratörs roller** som öppnas och välj sedan **Sök**.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-122">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="2b7c4-123">Alla konfigurations ändringar som görs under den angivna tids perioden visas och kan sorteras med hjälp av följande information:</span><span class="sxs-lookup"><span data-stu-id="2b7c4-123">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="2b7c4-124">**Datum**: det datum och den tid då konfigurations ändringen gjordes.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-124">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="2b7c4-125">Datum och tid sparas i UTC-format (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="2b7c4-125">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="2b7c4-126">**Cmdlet**: namnet på den cmdlet som användes för att göra konfigurations ändringen.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-126">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="2b7c4-127">**Användare**: namnet på användar kontot för den användare som gjorde konfigurations ändringen.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-127">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="2b7c4-128">Upp till 5000-poster visas på flera sidor.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-128">Up to 5000 entries will be displayed on multiple pages.</span></span> <span data-ttu-id="2b7c4-129">Ange ett kortare datum intervall om du vill begränsa resultatet.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-129">Specify a smaller date range if you need to narrow your results.</span></span> <span data-ttu-id="2b7c4-130">Om du väljer ett enskilt Sök resultat visas följande information i informations fönstret:</span><span class="sxs-lookup"><span data-stu-id="2b7c4-130">If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="2b7c4-131">**Objekt ändrat**: objektet som ändrades av cmdleten.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-131">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="2b7c4-132">**Parametrar (parameter: värde)**: cmdlet-parametrarna som användes och alla värden som anges med parametern.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-132">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="2b7c4-133">Om du vill skriva ut en viss Gransknings logg post väljer du knappen **Skriv ut** i informations fönstret.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-133">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="2b7c4-134">Använd fristående EOP PowerShell för att Visa administratörs gransknings loggen</span><span class="sxs-lookup"><span data-stu-id="2b7c4-134">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="2b7c4-135">Du kan använda fristående EOP PowerShell för att söka efter poster för gransknings loggar som uppfyller de villkor du anger.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-135">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="2b7c4-136">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="2b7c4-136">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="2b7c4-137">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="2b7c4-137">**Notes**:</span></span>

- <span data-ttu-id="2b7c4-138">Du kan bara använda parametern _Parameters_ tillsammans med parametern _cmdlets_ .</span><span class="sxs-lookup"><span data-stu-id="2b7c4-138">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="2b7c4-139">Parametern _ObjectIds_ filtrerar resultaten efter det objekt som har ändrats av cmdleten.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-139">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="2b7c4-140">Ett giltigt värde beror på hur objektet visas i gransknings loggen.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-140">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="2b7c4-141">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2b7c4-141">For example:</span></span>

  - <span data-ttu-id="2b7c4-142">Namn</span><span class="sxs-lookup"><span data-stu-id="2b7c4-142">Name</span></span>
  - <span data-ttu-id="2b7c4-143">Kanoniskt unikt namn (till exempel contoso.com/Users/Akia Al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="2b7c4-143">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="2b7c4-144">Du kommer troligen att behöva använda andra filtrerings parametrar för denna cmdlet för att begränsa resultaten och identifiera vilka typer av objekt du är intresse rad av.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-144">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="2b7c4-145">Parametern _UserIds_ filtrerar resultaten av användaren som gjorde ändringen (som körde cmdleten).</span><span class="sxs-lookup"><span data-stu-id="2b7c4-145">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="2b7c4-146">För parametrarna _StartDate_ och _EndDate_ om du anger ett datum-och tids värde utan en tidszon är värdet i Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="2b7c4-146">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="2b7c4-147">Om du vill ange ett datum/tid-värde för den här parametern använder du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="2b7c4-147">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="2b7c4-148">Ange datum-och tids värden i UTC: till exempel "2016-05-06 14:30:00Z".</span><span class="sxs-lookup"><span data-stu-id="2b7c4-148">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="2b7c4-149">Ange datum-och tids värden som en formel som konverterar datum/tid i din lokala tidszon till UTC: till exempel `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` .</span><span class="sxs-lookup"><span data-stu-id="2b7c4-149">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="2b7c4-150">Mer information finns i [Hämta-datum](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span><span class="sxs-lookup"><span data-stu-id="2b7c4-150">For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="2b7c4-151">Cmdleten returnerar högst 1 000 loggnings poster som standard.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-151">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="2b7c4-152">Använd parametern _ResultSize_ för att ange upp till 250 000-loggnings poster.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-152">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="2b7c4-153">Eller Använd värdet `Unlimited` för att returnera alla poster.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-153">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="2b7c4-154">I det här exemplet utförs en sökning efter alla gransknings loggar med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="2b7c4-154">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="2b7c4-155">**Start datum**: 4 augusti 2019</span><span class="sxs-lookup"><span data-stu-id="2b7c4-155">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="2b7c4-156">**Slutdatum**: 3 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="2b7c4-156">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="2b7c4-157">**Cmdletar**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="2b7c4-157">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="2b7c4-158">Detaljerad information om syntax och parametrar finns i [sökAdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="2b7c4-158">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="2b7c4-159">Visa information om Gransknings logg poster</span><span class="sxs-lookup"><span data-stu-id="2b7c4-159">View details of audit log entries</span></span>

<span data-ttu-id="2b7c4-160">Cmdleten **search-AdminAuditLog** returnerar fälten som beskrivs i avsnittet [granska logg innehåll](#audit-log-contents) längre ned i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-160">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this topic.</span></span> <span data-ttu-id="2b7c4-161">För de fält som returneras av cmdleten, två fält, **CmdletParameters** och **ModifiedProperties**, innehåller ytterligare information som inte returneras som standard.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-161">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="2b7c4-162">Om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-162">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="2b7c4-163">Välj de villkor du vill söka efter, kör **Sök-AdminAuditLog** cmdlet och lagra resultatet i en variabel med hjälp av följande kommando.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-163">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="2b7c4-164">Varje post för gransknings logg sparas som ett mat ris element i variabeln `$Results` .</span><span class="sxs-lookup"><span data-stu-id="2b7c4-164">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="2b7c4-165">Du kan välja ett mat ris element genom att ange dess mat ris element index.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-165">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="2b7c4-166">Mat ris element index börjar med noll (0) för det första mat ris elementet.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-166">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="2b7c4-167">Om du till exempel vill hämta femte mat ris elementet, som har index 4, använder du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-167">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="2b7c4-168">Föregående kommando returnerar den loggpost som är lagrad i mat ris element 4.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-168">The previous command returns the log entry stored in array element 4.</span></span> <span data-ttu-id="2b7c4-169">Använd följande kommandon för att visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** för den här logg posten.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-169">To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="2b7c4-170">Om du vill visa innehållet i fälten **CmdletParameters** eller **ModifiedParameters** i en annan loggpost ändrar du mat ris element indexet.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-170">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="2b7c4-171">Innehåll i gransknings loggen</span><span class="sxs-lookup"><span data-stu-id="2b7c4-171">Audit log contents</span></span>

<span data-ttu-id="2b7c4-172">Varje gransknings loggpost innehåller den information som beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-172">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="2b7c4-173">Gransknings loggen innehåller en eller flera Gransknings logg poster.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-173">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="2b7c4-174">Radfält</span><span class="sxs-lookup"><span data-stu-id="2b7c4-174">Field</span></span>|<span data-ttu-id="2b7c4-175">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2b7c4-175">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="2b7c4-176">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-176">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="2b7c4-177">Det här fältet innehåller objektet som ändrades av den cmdlet som anges i `CmdletName` fältet.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-177">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="2b7c4-178">Det här fältet innehåller namnet på den cmdlet som kördes av användaren i `Caller` fältet.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-178">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="2b7c4-179">Det här fältet innehåller de parametrar som angavs när cmdleten i `CmdletName` fältet kördes.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-179">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="2b7c4-180">I det här fältet, men inte visas i standardutdata, är det värde som anges med parametern, om det finns något.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-180">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="2b7c4-181">Det här fältet innehåller de egenskaper som har ändrats för objektet i `ObjectModified` fältet.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-181">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="2b7c4-182">I det här fältet, men inte visas i standardutdata, är det gamla värdet för egenskapen och det nya värdet som har lagrats.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-182">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="2b7c4-183">Det här fältet innehåller användar kontot för den användare som körde cmdleten i `CmdletName` fältet.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-183">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="2b7c4-184">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-184">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="2b7c4-185">Det här fältet anger om cmdleten i `CmdletName` fältet lyckades.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-185">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="2b7c4-186">Värdet är antingen `True` eller `False` .</span><span class="sxs-lookup"><span data-stu-id="2b7c4-186">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="2b7c4-187">Det här fältet innehåller fel meddelandet som skapas om cmdleten i `CmdletName` fältet inte gick att slutföra.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-187">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="2b7c4-188">I det här fältet visas det datum och den tid då cmdleten i `CmdletName` fältet kördes.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-188">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="2b7c4-189">Datum och tid sparas i UTC-format (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="2b7c4-189">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="2b7c4-190">I det här fältet visas den server där cmdleten som anges i `CmdletName` fältet kördes.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-190">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="2b7c4-191">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-191">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="2b7c4-192">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-192">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="2b7c4-193">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-193">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="2b7c4-194">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-194">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="2b7c4-195">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-195">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="2b7c4-196">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-196">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="2b7c4-197">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-197">This field is used internally by EOP.</span></span>|
|
