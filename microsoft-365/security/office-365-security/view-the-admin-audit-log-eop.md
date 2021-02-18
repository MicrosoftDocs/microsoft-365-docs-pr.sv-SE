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
ms.openlocfilehash: ab6bf0a2739a88a075b636b990539b24006f3e63
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286483"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="a0793-103">Visa administratörsgranskningsloggen i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="a0793-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="a0793-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="a0793-104">**Applies to**</span></span>
- [<span data-ttu-id="a0793-105">Exchange Online Protection fristående</span><span class="sxs-lookup"><span data-stu-id="a0793-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a0793-106">I fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor kan du använda administrationscentret för Exchange (EAC) eller fristående EOP PowerShell för att söka efter och visa poster i granskningsloggen för administratörer.</span><span class="sxs-lookup"><span data-stu-id="a0793-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="a0793-107">I granskningsloggen för administratörer registrerar du specifika åtgärder, baserat på fristående EOP PowerShell-cmdlets, som utförs av administratörer och användare som har tilldelats administratörsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="a0793-107">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="a0793-108">Poster i administratörsgranskningsloggen ger dig information om vilken cmdlet som kördes, vilka parametrar som användes, vem som körde cmdleten och vilka objekt som påverkades.</span><span class="sxs-lookup"><span data-stu-id="a0793-108">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="a0793-109">Granskningsloggning för administratörer är aktiverat som standard och du kan inte inaktivera det.</span><span class="sxs-lookup"><span data-stu-id="a0793-109">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="a0793-110">I granskningsloggen för administratörer spelas inte åtgärder in baserat på cmdlets som börjar med **verben** Hämta, **Sök** eller **Test.**</span><span class="sxs-lookup"><span data-stu-id="a0793-110">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="a0793-111">Granskningsloggposter sparas i 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="a0793-111">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="a0793-112">Om en post är äldre än 90 dagar tas den bort</span><span class="sxs-lookup"><span data-stu-id="a0793-112">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a0793-113">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="a0793-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a0793-114">Information om hur du öppnar administrationscentret för Exchange finns [i administrationscentret för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="a0793-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="a0793-115">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a0793-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a0793-116">Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="a0793-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="a0793-117">Mer specifikt behöver du  **rollen** Granskningsloggar eller Visningsskyddade granskningsloggar som tilldelas rollgrupperna Organisationshantering, Efterlevnadshantering och **Säkerhetsadministratör** som standard.  </span><span class="sxs-lookup"><span data-stu-id="a0793-117">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="a0793-118">Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) [och Använda EAC för att ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="a0793-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="a0793-119">Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för [administrationscentret för Exchange i Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="a0793-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="a0793-120">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="a0793-120">Having problems?</span></span> <span data-ttu-id="a0793-121">Be om hjälp i [forumet för Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)</span><span class="sxs-lookup"><span data-stu-id="a0793-121">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="a0793-122">Använda EAC för att visa granskningsloggen för administratörer</span><span class="sxs-lookup"><span data-stu-id="a0793-122">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="a0793-123">Gå till granskning av efterlevnadshantering **i** EAC \> **och** välj sedan **Kör granskningsloggrapporten för administratör.**</span><span class="sxs-lookup"><span data-stu-id="a0793-123">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="a0793-124">På sidan **Sök efter ändringar i** administratörsrollgrupper som öppnas väljer du startdatum och slutdatum (standardintervallet är de senaste två veckorna) och väljer sedan **Sök.**  </span><span class="sxs-lookup"><span data-stu-id="a0793-124">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="a0793-125">Alla konfigurationsändringar som gjorts under den angivna tidsperioden visas och kan sorteras med hjälp av följande information:</span><span class="sxs-lookup"><span data-stu-id="a0793-125">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="a0793-126">**Datum:** Datum och tid då konfigurationsändringen gjordes.</span><span class="sxs-lookup"><span data-stu-id="a0793-126">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="a0793-127">Datum och tid lagras i UTC-format (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="a0793-127">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="a0793-128">**Cmdlet:** Namnet på cmdleten som användes för att ändra konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="a0793-128">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="a0793-129">**Användare:** Namnet på användarkontot för den användare som gjorde konfigurationsändringen.</span><span class="sxs-lookup"><span data-stu-id="a0793-129">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="a0793-130">Upp till 5 000 poster visas på flera sidor.</span><span class="sxs-lookup"><span data-stu-id="a0793-130">Up to 5000 entries will be displayed on multiple pages.</span></span> <span data-ttu-id="a0793-131">Ange ett mindre datumintervall om du behöver begränsa resultatet.</span><span class="sxs-lookup"><span data-stu-id="a0793-131">Specify a smaller date range if you need to narrow your results.</span></span> <span data-ttu-id="a0793-132">Om du väljer ett enskilt sökresultat visas följande ytterligare information i informationsfönstret:</span><span class="sxs-lookup"><span data-stu-id="a0793-132">If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="a0793-133">**Ändrat objekt:** Objektet som ändrades av cmdleten.</span><span class="sxs-lookup"><span data-stu-id="a0793-133">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="a0793-134">**Parametrar (Parameter:Värde)**: Cmdlet-parametrarna som användes och alla värden angivna med parametern.</span><span class="sxs-lookup"><span data-stu-id="a0793-134">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="a0793-135">Om du vill skriva ut en viss granskningsloggpost väljer **du knappen** Skriv ut i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a0793-135">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="a0793-136">Använda fristående EOP PowerShell för att visa granskningsloggen för administratörer</span><span class="sxs-lookup"><span data-stu-id="a0793-136">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="a0793-137">Du kan använda fristående EOP PowerShell för att söka efter granskningsloggposter som uppfyller de villkor du anger.</span><span class="sxs-lookup"><span data-stu-id="a0793-137">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="a0793-138">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="a0793-138">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="a0793-139">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="a0793-139">**Notes**:</span></span>

- <span data-ttu-id="a0793-140">Du kan bara använda _parametern Parametrar_ tillsammans med _cmdletsparametern._</span><span class="sxs-lookup"><span data-stu-id="a0793-140">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="a0793-141">Parametern _ObjectIds_ filtrerar resultatet av det objekt som ändrades av cmdleten.</span><span class="sxs-lookup"><span data-stu-id="a0793-141">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="a0793-142">Ett giltigt värde beror på hur objektet representeras i granskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="a0793-142">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="a0793-143">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="a0793-143">For example:</span></span>

  - <span data-ttu-id="a0793-144">Namn</span><span class="sxs-lookup"><span data-stu-id="a0793-144">Name</span></span>
  - <span data-ttu-id="a0793-145">Canonical unikt namn (till exempel contoso.com/Users/Akia Al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="a0793-145">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="a0793-146">Du måste förmodligen använda andra filtreringsparametrar i den här cmdleten för att begränsa resultatet och identifiera de typer av objekt som du är intresserad av.</span><span class="sxs-lookup"><span data-stu-id="a0793-146">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="a0793-147">Parametern _UserIds_ filtrerar resultatet av den användare som gjorde ändringen (som körde cmdleten).</span><span class="sxs-lookup"><span data-stu-id="a0793-147">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="a0793-148">Om du anger  ett datum-/tidsvärde utan tidszon för parametrarna _Startdatum_ och Slutdatum ligger värdet i UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="a0793-148">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="a0793-149">Om du vill ange ett datum-/tidsvärde för den här parametern använder du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="a0793-149">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="a0793-150">Ange datum-/tidsvärdet i UTC: Till exempel "2016-05-06 14:30:00z".</span><span class="sxs-lookup"><span data-stu-id="a0793-150">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="a0793-151">Ange datum/tid som en formel som konverterar datum/tid i din lokala tidszon till UTC: Till `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` exempel.</span><span class="sxs-lookup"><span data-stu-id="a0793-151">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="a0793-152">Mer information finns under [Hämta datum.](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date)</span><span class="sxs-lookup"><span data-stu-id="a0793-152">For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="a0793-153">Cmdleten returnerar högst 1 000 loggposter som standard.</span><span class="sxs-lookup"><span data-stu-id="a0793-153">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="a0793-154">Använd _parametern ResultSize_ till att ange upp till 250 000 loggposter.</span><span class="sxs-lookup"><span data-stu-id="a0793-154">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="a0793-155">Du kan också använda värdet `Unlimited` för att returnera alla poster.</span><span class="sxs-lookup"><span data-stu-id="a0793-155">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="a0793-156">I det här exemplet utförs en sökning efter alla granskningsloggposter med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="a0793-156">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="a0793-157">**Startdatum:** 4 augusti 2019</span><span class="sxs-lookup"><span data-stu-id="a0793-157">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="a0793-158">**Slutdatum:** 3 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="a0793-158">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="a0793-159">**Cmdlets:** Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="a0793-159">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="a0793-160">Detaljerad information om syntax och parametrar finns [i Sök-AdminAuditLog.](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)</span><span class="sxs-lookup"><span data-stu-id="a0793-160">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="a0793-161">Visa information om granskningsloggposter</span><span class="sxs-lookup"><span data-stu-id="a0793-161">View details of audit log entries</span></span>

<span data-ttu-id="a0793-162">Cmdleten **Search-AdminAuditLog** returnerar fälten som beskrivs i avsnittet [Granskningslogginnehåll](#audit-log-contents) längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="a0793-162">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this article.</span></span> <span data-ttu-id="a0793-163">Av de fält som returneras av cmdleten innehåller två fält, **CmdletParameters** och **ModifiedProperties,** ytterligare information som inte returneras som standard.</span><span class="sxs-lookup"><span data-stu-id="a0793-163">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="a0793-164">Gör så här om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties.**</span><span class="sxs-lookup"><span data-stu-id="a0793-164">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="a0793-165">Bestäm vilka villkor du vill söka efter, kör cmdleten **Search-AdminAuditLog** och lagra resultaten i en variabel med följande kommando.</span><span class="sxs-lookup"><span data-stu-id="a0793-165">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="a0793-166">Varje granskningsloggpost lagras som ett matriselement i `$Results` variabeln.</span><span class="sxs-lookup"><span data-stu-id="a0793-166">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="a0793-167">Du kan välja ett matriselement genom att ange dess index för matriselement.</span><span class="sxs-lookup"><span data-stu-id="a0793-167">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="a0793-168">Matriselementindex börjar med noll (0) för det första matriselementet.</span><span class="sxs-lookup"><span data-stu-id="a0793-168">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="a0793-169">Om du till exempel vill hämta det femte matriselementet, som har indexet 4, använder du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="a0793-169">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="a0793-170">Föregående kommando returnerar loggposten som lagrats i matriselement 4.</span><span class="sxs-lookup"><span data-stu-id="a0793-170">The previous command returns the log entry stored in array element 4.</span></span> <span data-ttu-id="a0793-171">Använd följande kommandon för att visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** för den här loggposten.</span><span class="sxs-lookup"><span data-stu-id="a0793-171">To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="a0793-172">Om du vill visa innehållet i **fälten CmdletParameters** eller **ModifiedParameters** i en annan loggpost ändrar du index för matriselement.</span><span class="sxs-lookup"><span data-stu-id="a0793-172">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="a0793-173">Granska logginnehåll</span><span class="sxs-lookup"><span data-stu-id="a0793-173">Audit log contents</span></span>

<span data-ttu-id="a0793-174">Varje granskningsloggpost innehåller den information som beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a0793-174">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="a0793-175">Granskningsloggen innehåller en eller flera granskningsloggposter.</span><span class="sxs-lookup"><span data-stu-id="a0793-175">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="a0793-176">Fält</span><span class="sxs-lookup"><span data-stu-id="a0793-176">Field</span></span>|<span data-ttu-id="a0793-177">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a0793-177">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="a0793-178">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="a0793-178">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="a0793-179">Det här fältet innehåller det objekt som ändrades av den cmdlet som anges i `CmdletName` fältet.</span><span class="sxs-lookup"><span data-stu-id="a0793-179">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="a0793-180">Det här fältet innehåller namnet på cmdleten som körts av användaren i `Caller` fältet.</span><span class="sxs-lookup"><span data-stu-id="a0793-180">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="a0793-181">Det här fältet innehåller de parametrar som angavs när cmdleten `CmdletName` i fältet körts.</span><span class="sxs-lookup"><span data-stu-id="a0793-181">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="a0793-182">Det här fältet lagras också, men visas inte i standardutdata, är det värde som anges med parametern, om det finns något.</span><span class="sxs-lookup"><span data-stu-id="a0793-182">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="a0793-183">Det här fältet innehåller de egenskaper som ändrades för objektet i `ObjectModified` fältet.</span><span class="sxs-lookup"><span data-stu-id="a0793-183">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="a0793-184">Det gamla värdet för egenskapen och det nya värdet som lagrades är de som också lagras i det här fältet, men inte visas i standardutdata.</span><span class="sxs-lookup"><span data-stu-id="a0793-184">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="a0793-185">Det här fältet innehåller användarkontot för den användare som körde cmdleten i `CmdletName` fältet.</span><span class="sxs-lookup"><span data-stu-id="a0793-185">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="a0793-186">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="a0793-186">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="a0793-187">Det här fältet anger om cmdleten i `CmdletName` fältet kördes som den ska.</span><span class="sxs-lookup"><span data-stu-id="a0793-187">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="a0793-188">Värdet är antingen `True` `False` eller.</span><span class="sxs-lookup"><span data-stu-id="a0793-188">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="a0793-189">Det här fältet innehåller felmeddelandet som genereras om cmdleten `CmdletName` i fältet inte kunde slutföras.</span><span class="sxs-lookup"><span data-stu-id="a0793-189">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="a0793-190">Det här fältet innehåller datum och tid då cmdleten `CmdletName` i fältet körts.</span><span class="sxs-lookup"><span data-stu-id="a0793-190">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="a0793-191">Datum och tid lagras i UTC-format (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="a0793-191">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="a0793-192">Det här fältet anger den server där cmdleten som anges i `CmdletName` fältet körs.</span><span class="sxs-lookup"><span data-stu-id="a0793-192">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="a0793-193">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="a0793-193">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="a0793-194">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="a0793-194">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="a0793-195">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="a0793-195">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="a0793-196">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="a0793-196">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="a0793-197">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="a0793-197">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="a0793-198">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="a0793-198">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="a0793-199">Det här fältet används internt av EOP.</span><span class="sxs-lookup"><span data-stu-id="a0793-199">This field is used internally by EOP.</span></span>|
|
