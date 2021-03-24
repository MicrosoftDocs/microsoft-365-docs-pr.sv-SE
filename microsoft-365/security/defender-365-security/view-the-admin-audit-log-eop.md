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
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Administratörer kan läsa om hur de visar och söker i granskningsloggen för administratörer i fristående Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ed1d1eb121c06e6f5727e8782ba1d8bc8d23a99
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070945"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="3d4d8-103">Visa administratörsgranskningsloggen i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="3d4d8-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="3d4d8-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="3d4d8-104">**Applies to**</span></span>
- [<span data-ttu-id="3d4d8-105">Exchange Online Protection fristående</span><span class="sxs-lookup"><span data-stu-id="3d4d8-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3d4d8-106">I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan du använda Administrationscenter för Exchange (EAC) eller fristående EOP PowerShell för att söka efter och visa poster i granskningsloggen för administratörer.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="3d4d8-107">I granskningsloggen för administratörer registrerar du specifika åtgärder, baserat på fristående EOP PowerShell-cmdlets, som utförs av administratörer och användare som har tilldelats administratörsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-107">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="3d4d8-108">Posterna i administratörsgranskningsloggen ger dig information om vilken cmdlet som körts, vilka parametrar som användes, vem som körde cmdleten och vilka objekt som påverkades.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-108">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="3d4d8-109">Granskningsloggning för administratörer är aktiverat som standard och du kan inte inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-109">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="3d4d8-110">I granskningsloggen för administratörer spelas inte åtgärder in baserat på cmdlets som börjar med verben **Hämta,** **Sök** eller **Testa.**</span><span class="sxs-lookup"><span data-stu-id="3d4d8-110">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="3d4d8-111">Granskningsloggposter sparas i 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-111">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="3d4d8-112">När en post är äldre än 90 dagar tas den bort</span><span class="sxs-lookup"><span data-stu-id="3d4d8-112">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3d4d8-113">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="3d4d8-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3d4d8-114">Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="3d4d8-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="3d4d8-115">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="3d4d8-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3d4d8-116">Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="3d4d8-117">Mer specifikt behöver  du  rollen Granskningsloggar eller Visningsskyddade granskningsloggar som tilldelas rollgrupperna Organisationshantering, Efterlevnadshantering och **Säkerhetsadministratör** som standard. </span><span class="sxs-lookup"><span data-stu-id="3d4d8-117">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="3d4d8-118">Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) och Använda EAC för att [ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="3d4d8-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="3d4d8-119">Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för [Administrationscenter för Exchange i Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="3d4d8-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="3d4d8-120">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="3d4d8-120">Having problems?</span></span> <span data-ttu-id="3d4d8-121">Be om hjälp i [Forumet för Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)</span><span class="sxs-lookup"><span data-stu-id="3d4d8-121">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="3d4d8-122">Använda EAC för att visa granskningsloggen för administratören</span><span class="sxs-lookup"><span data-stu-id="3d4d8-122">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="3d4d8-123">Gå till Granskning av efterlevnadshantering **i** EAC \> **och** välj sedan **Kör granskningsloggrapport för administratör.**</span><span class="sxs-lookup"><span data-stu-id="3d4d8-123">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="3d4d8-124">På sidan Sök efter ändringar i **administratörsrollgrupper** som öppnas väljer du startdatum och slutdatum (standardintervallet är de senaste två veckorna) och väljer sedan **Sök**.  </span><span class="sxs-lookup"><span data-stu-id="3d4d8-124">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="3d4d8-125">Alla konfigurationsändringar som gjorts under den angivna tidsperioden visas och kan sorteras med hjälp av följande information:</span><span class="sxs-lookup"><span data-stu-id="3d4d8-125">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="3d4d8-126">**Datum:** Datum och tid då konfigurationsändringen gjordes.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-126">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="3d4d8-127">Datum och tid lagras i UTC-format (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="3d4d8-127">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="3d4d8-128">**Cmdlet:** Namnet på den cmdlet som användes för att göra konfigurationsändringen.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-128">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="3d4d8-129">**Användare**: Namnet på användarkontot för den användare som gjorde konfigurationsändringen.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-129">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="3d4d8-130">Upp till 5 000 poster visas på flera sidor.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-130">Up to 5000 entries will be displayed on multiple pages.</span></span> <span data-ttu-id="3d4d8-131">Ange ett mindre datumintervall om du behöver begränsa resultatet.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-131">Specify a smaller date range if you need to narrow your results.</span></span> <span data-ttu-id="3d4d8-132">Om du väljer ett enskilt sökresultat visas följande ytterligare information i informationsfönstret:</span><span class="sxs-lookup"><span data-stu-id="3d4d8-132">If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="3d4d8-133">**Ändrad objekt:** Objektet som ändrades av cmdleten.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-133">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="3d4d8-134">**Parametrar (Parameter:Värde)**: Cmdlet-parametrarna som användes och alla värden som anges med parametern.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-134">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="3d4d8-135">Om du vill skriva ut en viss granskningsloggpost väljer **du knappen** Skriv ut i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-135">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="3d4d8-136">Använda fristående EOP PowerShell för att visa granskningsloggen för administratörer</span><span class="sxs-lookup"><span data-stu-id="3d4d8-136">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="3d4d8-137">Du kan använda fristående EOP PowerShell för att söka efter granskningsloggposter som uppfyller de villkor du anger.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-137">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="3d4d8-138">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="3d4d8-138">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="3d4d8-139">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="3d4d8-139">**Notes**:</span></span>

- <span data-ttu-id="3d4d8-140">Du kan bara använda _parametern Parameters_ tillsammans med _Cmdlets-parametern._</span><span class="sxs-lookup"><span data-stu-id="3d4d8-140">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="3d4d8-141">Parametern _ObjectIds_ filtrerar resultaten av objektet som ändrades av cmdleten.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-141">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="3d4d8-142">Ett giltigt värde beror på hur objektet representeras i granskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-142">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="3d4d8-143">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="3d4d8-143">For example:</span></span>

  - <span data-ttu-id="3d4d8-144">Namn</span><span class="sxs-lookup"><span data-stu-id="3d4d8-144">Name</span></span>
  - <span data-ttu-id="3d4d8-145">Canonical distinguished name (till exempel contoso.com/Users/Akia Al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="3d4d8-145">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="3d4d8-146">Du måste förmodligen använda andra filtreringsparametrar i den här cmdleten för att begränsa resultatet och identifiera de typer av objekt som du är intresserad av.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-146">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="3d4d8-147">Parametern _UserIds_ filtrerar resultatet av den användare som gjorde ändringen (som körde cmdleten).</span><span class="sxs-lookup"><span data-stu-id="3d4d8-147">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="3d4d8-148">Om du anger  ett datum-/tidsvärde utan en tidszon för parametrarna _Startdatum_ och Slutdatum anges värdet i UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="3d4d8-148">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="3d4d8-149">Om du vill ange ett datum-/tidsvärde för den här parametern använder du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="3d4d8-149">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="3d4d8-150">Ange datum-/tidsvärdet i UTC: Till exempel "2016-05-06 14:30:00z".</span><span class="sxs-lookup"><span data-stu-id="3d4d8-150">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="3d4d8-151">Ange datum-/tidsvärdet som en formel som konverterar datum/tid i din lokala tidszon till UTC: till exempel `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` .</span><span class="sxs-lookup"><span data-stu-id="3d4d8-151">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="3d4d8-152">Mer information finns i [Hämta datum.](/powershell/module/microsoft.powershell.utility/get-date)</span><span class="sxs-lookup"><span data-stu-id="3d4d8-152">For more information, see [Get-Date](/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="3d4d8-153">Cmdleten returnerar högst 1 000 loggposter som standard.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-153">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="3d4d8-154">Använd _parametern ResultSize_ till att ange upp till 250 000 loggposter.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-154">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="3d4d8-155">Du kan också använda värdet `Unlimited` för att returnera alla poster.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-155">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="3d4d8-156">I det här exemplet utförs en sökning efter alla granskningsloggposter med följande kriterier:</span><span class="sxs-lookup"><span data-stu-id="3d4d8-156">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="3d4d8-157">**Startdatum:** 4 augusti 2019</span><span class="sxs-lookup"><span data-stu-id="3d4d8-157">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="3d4d8-158">**Slutdatum:** 3 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="3d4d8-158">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="3d4d8-159">**Cmdlets**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="3d4d8-159">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="3d4d8-160">Detaljerad information om syntax och parametrar finns [i Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="3d4d8-160">For detailed syntax and parameter information, see [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="3d4d8-161">Visa information om granskningsloggposter</span><span class="sxs-lookup"><span data-stu-id="3d4d8-161">View details of audit log entries</span></span>

<span data-ttu-id="3d4d8-162">**Cmdlet:en Search-AdminAuditLog** returnerar de fält som beskrivs i avsnittet Granskningslogginnehåll längre fram i den här artikeln. [](#audit-log-contents)</span><span class="sxs-lookup"><span data-stu-id="3d4d8-162">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this article.</span></span> <span data-ttu-id="3d4d8-163">Av de fält som returneras av cmdleten innehåller två fält, **CmdletParameters** **och ModifiedProperties,** ytterligare information som inte returneras som standard.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-163">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="3d4d8-164">Gör så här om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties.**</span><span class="sxs-lookup"><span data-stu-id="3d4d8-164">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="3d4d8-165">Bestäm vilka kriterier du vill söka efter, kör cmdleten **Search-AdminAuditLog** och lagra resultaten i en variabel med hjälp av följande kommando.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-165">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="3d4d8-166">Varje granskningsloggpost lagras som ett matriselement i variabeln `$Results` .</span><span class="sxs-lookup"><span data-stu-id="3d4d8-166">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="3d4d8-167">Du kan välja ett matriselement genom att ange dess matriselementindex.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-167">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="3d4d8-168">Matriselementindex börjar med noll (0) för det första matriselementet.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-168">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="3d4d8-169">Om du till exempel vill hämta det femte matriselementet, som har indexet 4, använder du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-169">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="3d4d8-170">Föregående kommando returnerar loggposten som lagrats i matriselement 4.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-170">The previous command returns the log entry stored in array element 4.</span></span> <span data-ttu-id="3d4d8-171">Använd följande kommandon för att visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** för den här loggposten.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-171">To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="3d4d8-172">Om du vill visa innehållet i **fälten CmdletParameters** eller **ModifiedParameters** i en annan loggpost ändrar du matriselementindexet.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-172">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="3d4d8-173">Granska logginnehåll</span><span class="sxs-lookup"><span data-stu-id="3d4d8-173">Audit log contents</span></span>

<span data-ttu-id="3d4d8-174">Varje granskningsloggpost innehåller den information som beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-174">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="3d4d8-175">Granskningsloggen innehåller en eller flera granskningsloggposter.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-175">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="3d4d8-176">Fält</span><span class="sxs-lookup"><span data-stu-id="3d4d8-176">Field</span></span>|<span data-ttu-id="3d4d8-177">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3d4d8-177">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="3d4d8-178">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-178">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="3d4d8-179">Det här fältet innehåller det objekt som ändrades av den cmdlet som anges i `CmdletName` fältet.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-179">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="3d4d8-180">Det här fältet innehåller namnet på den cmdlet som körts av användaren i `Caller` fältet.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-180">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="3d4d8-181">Det här fältet innehåller de parametrar som angavs när cmdleten `CmdletName` i fältet körts.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-181">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="3d4d8-182">Det värde som anges med parametern, om det finns något, lagras också i det här fältet, men inte visas i standardutdata.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-182">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="3d4d8-183">Det här fältet innehåller de egenskaper som har ändrats för objektet i `ObjectModified` fältet.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-183">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="3d4d8-184">Det gamla värdet för egenskapen och det nya värdet som lagrats är samma som det som lagrats i det här fältet, men inte visas i standardutdata.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-184">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="3d4d8-185">Det här fältet innehåller användarkontot för användaren som körde cmdleten i `CmdletName` fältet.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-185">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="3d4d8-186">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-186">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="3d4d8-187">Det här fältet anger om cmdleten i `CmdletName` fältet har körts.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-187">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="3d4d8-188">Värdet är antingen `True` eller `False` .</span><span class="sxs-lookup"><span data-stu-id="3d4d8-188">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="3d4d8-189">Det här fältet innehåller det felmeddelande som genereras om cmdleten `CmdletName` i fältet inte kunde slutföras.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-189">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="3d4d8-190">Det här fältet innehåller datum och tid då cmdleten `CmdletName` i fältet körts.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-190">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="3d4d8-191">Datum och tid lagras i UTC-format (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="3d4d8-191">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="3d4d8-192">Det här fältet anger den server där cmdleten som anges i `CmdletName` fältet körs.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-192">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="3d4d8-193">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-193">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="3d4d8-194">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-194">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="3d4d8-195">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-195">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="3d4d8-196">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-196">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="3d4d8-197">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-197">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="3d4d8-198">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-198">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="3d4d8-199">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="3d4d8-199">This field is used internally by EOP.</span></span>|
|