---
title: Köra en administratörsrapport för rollgrupp i fristående EOP
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
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig hur du kör en administratörsrollgruppsrapport i fristående Exchange Online Protection (EOP). Den här rapporten loggar när en administratör lägger till medlemmar i eller tar bort medlemmar från administratörsrollgrupper, EOP loggar varje förekomst.
ms.openlocfilehash: 0c504460657a153aad7d3dd065c81007a68ba916
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587370"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="81cb0-104">Köra en administratörsrapport för rollgrupp i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="81cb0-104">Run an administrator role group report in standalone EOP</span></span>

<span data-ttu-id="81cb0-105">I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor, när en administratör lägger till medlemmar i eller tar bort medlemmar från administrativa rollgrupper, loggar tjänsten varje förekomst.</span><span class="sxs-lookup"><span data-stu-id="81cb0-105">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="81cb0-106">Mer information om rollgrupper i fristående EOP finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="81cb0-106">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="81cb0-107">När du kör en administratörsrollgruppsrapport i Administrationscenter för Exchange (EAC) visas poster som sökresultat och inkluderar de rollgrupper som påverkas, vem som har ändrat rollgruppsmedlemskapet och när och vilka medlemsuppdateringar som gjordes.</span><span class="sxs-lookup"><span data-stu-id="81cb0-107">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="81cb0-108">Använd den här rapporten om du vill övervaka ändringar av de administrativa behörigheter som tilldelats användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="81cb0-108">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="81cb0-109">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="81cb0-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="81cb0-110">Om du vill öppna administrationscentret för Exchange finns [i Administrationscenter för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="81cb0-110">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="81cb0-111">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="81cb0-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="81cb0-112">Du behöver rollen Granskningsloggar eller granskningsloggar för endast granskning, som tilldelas rollgrupperna ComplianceManagement, OrganizationManagement (global admins) och SecurityAdministrator som standard.</span><span class="sxs-lookup"><span data-stu-id="81cb0-112">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="81cb0-113">Mer information finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd EAC ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="81cb0-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="81cb0-114">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="81cb0-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="81cb0-115">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="81cb0-115">Having problems?</span></span> <span data-ttu-id="81cb0-116">Be om hjälp i Forumet för [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="81cb0-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="81cb0-117">Använda EAC för att köra en administratörsrollgruppsrapport</span><span class="sxs-lookup"><span data-stu-id="81cb0-117">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="81cb0-118">Kör rapporten administratörsrollgrupp för att hitta ändringarna i hanteringsrollgrupper i organisationen inom en viss tidsram.</span><span class="sxs-lookup"><span data-stu-id="81cb0-118">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="81cb0-119">Gå till Granskning av **efterlevnadshantering** i EAC \> **Auditing**och välj sedan Kör **en administratörsrollgruppsrapport**.</span><span class="sxs-lookup"><span data-stu-id="81cb0-119">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="81cb0-120">Konfigurera följande inställningar på sidan **Sök efter ändringar i administratörsrollgrupper** som öppnas:</span><span class="sxs-lookup"><span data-stu-id="81cb0-120">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="81cb0-121">**Startdatum** och **slutdatum**: Ange ett datumintervall.</span><span class="sxs-lookup"><span data-stu-id="81cb0-121">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="81cb0-122">Som standard söker rapporten efter ändringar som gjorts i administratörsrollgrupper under de senaste två veckorna.</span><span class="sxs-lookup"><span data-stu-id="81cb0-122">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="81cb0-123">**Välj rollgrupper**: Som standard genomsöks alla rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="81cb0-123">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="81cb0-124">Om du vill filtrera resultaten efter specifika rollgrupper klickar du på **Välj rollgrupper**.</span><span class="sxs-lookup"><span data-stu-id="81cb0-124">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="81cb0-125">I dialogrutan som visas markerar du en rollgrupp och klickar på **Lägg till ->**.</span><span class="sxs-lookup"><span data-stu-id="81cb0-125">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="81cb0-126">Upprepa det här steget så många gånger som behövs och klicka sedan på **OK** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="81cb0-126">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="81cb0-127">När du är klar klickar du på **Sök**.</span><span class="sxs-lookup"><span data-stu-id="81cb0-127">When you're finished, click **Search**.</span></span>

<span data-ttu-id="81cb0-128">Om några ändringar hittas med hjälp av de angivna villkoren visas de i resultatfönstret.</span><span class="sxs-lookup"><span data-stu-id="81cb0-128">If any changes are found using the criteria you specified, they will appear in the results pane.</span></span> <span data-ttu-id="81cb0-129">Klicka på en rollgrupp i sökresultaten om du vill se ändringarna i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="81cb0-129">Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="81cb0-130">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="81cb0-130">How do you know this worked?</span></span>

<span data-ttu-id="81cb0-131">Om du har kört en rapport över administratörsrollgrupper visas rollgrupper som har ändrats inom datumintervallet i sökresultatfönstret.</span><span class="sxs-lookup"><span data-stu-id="81cb0-131">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane.</span></span> <span data-ttu-id="81cb0-132">Om det inte finns några resultat har inga ändringar av rollgrupper skett inom det angivna datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="81cb0-132">If there are no results, then no changes to role groups have taken place within the specified date range.</span></span> <span data-ttu-id="81cb0-133">Om du tycker att det ska finnas resultat ändrar du datumintervallet och kör rapporten igen.</span><span class="sxs-lookup"><span data-stu-id="81cb0-133">If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="81cb0-134">Övervaka ändringar i rollgruppsmedlemskap</span><span class="sxs-lookup"><span data-stu-id="81cb0-134">Monitor changes to role group membership</span></span>

<span data-ttu-id="81cb0-135">När medlemmar läggs till eller tas bort från en rollgrupp anger sökresultaten i informationsfönstret att rollgruppens medlemskap har uppdaterats och de aktuella medlemmarna visas.</span><span class="sxs-lookup"><span data-stu-id="81cb0-135">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members.</span></span> <span data-ttu-id="81cb0-136">Resultaten anger inte uttryckligen vilken användare som har lagts till eller tagits bort.</span><span class="sxs-lookup"><span data-stu-id="81cb0-136">The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="81cb0-137">För att avgöra om en användare har lagts till eller tagits bort måste du jämföra två separata poster i rapporten.</span><span class="sxs-lookup"><span data-stu-id="81cb0-137">To determine if a user was added or removed, you have to compare two separate entries in the report.</span></span> <span data-ttu-id="81cb0-138">Låt oss till exempel titta på följande loggposter för **rollgruppen HelpDesk:**</span><span class="sxs-lookup"><span data-stu-id="81cb0-138">For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="81cb0-139">2018-01-27 16:43</span><span class="sxs-lookup"><span data-stu-id="81cb0-139">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="81cb0-140">Administratör</span><span class="sxs-lookup"><span data-stu-id="81cb0-140">Administrator</span></span> <br> <span data-ttu-id="81cb0-141">Uppdaterade medlemmar: Administratör;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="81cb0-141">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="81cb0-142">2018-06-06 10:09</span><span class="sxs-lookup"><span data-stu-id="81cb0-142">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="81cb0-143">Administratör</span><span class="sxs-lookup"><span data-stu-id="81cb0-143">Administrator</span></span> <br> <span data-ttu-id="81cb0-144">Uppdaterade medlemmar: Administratör;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="81cb0-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="81cb0-145">2018-02-19 14:12</span><span class="sxs-lookup"><span data-stu-id="81cb0-145">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="81cb0-146">Administratör</span><span class="sxs-lookup"><span data-stu-id="81cb0-146">Administrator</span></span> <br> <span data-ttu-id="81cb0-147">Uppdaterade medlemmar: Administratör;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="81cb0-147">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="81cb0-148">I det här exemplet har administratörsanvändarkontot gjort följande ändringar:</span><span class="sxs-lookup"><span data-stu-id="81cb0-148">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="81cb0-149">Den 2018-02-06 lade de till användarens tonip.</span><span class="sxs-lookup"><span data-stu-id="81cb0-149">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="81cb0-150">Den 2018-02-19 tog de bort användarens pilarp.</span><span class="sxs-lookup"><span data-stu-id="81cb0-150">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="81cb0-151">Använd fristående Exchange Online PowerShell för att söka efter granskningsloggposter</span><span class="sxs-lookup"><span data-stu-id="81cb0-151">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="81cb0-152">Du kan använda Exchange Online PowerShell för att söka efter granskningsloggposter som uppfyller de kriterier du anger.</span><span class="sxs-lookup"><span data-stu-id="81cb0-152">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="81cb0-153">En lista över sökvillkor finns i [Sökvillkor för Söksökning](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)för sök .</span><span class="sxs-lookup"><span data-stu-id="81cb0-153">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="81cb0-154">Den här proceduren använder cmdleten **Search-AdminAuditLog** och visar sökresultat i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81cb0-154">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="81cb0-155">Du kan använda den här cmdleten när du behöver returnera en uppsättning resultat som överskrider de gränser som definierats i cmdleten **New-AdminAuditLogSearch** eller i EAC Audit Reporting-rapporterna.</span><span class="sxs-lookup"><span data-stu-id="81cb0-155">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="81cb0-156">Om du vill söka i granskningsloggen efter villkor som du anger använder du följande syntax.</span><span class="sxs-lookup"><span data-stu-id="81cb0-156">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="81cb0-157">**Cmdlet search-adminAuditLog** returnerar som standard högst 1 000 loggposter.</span><span class="sxs-lookup"><span data-stu-id="81cb0-157">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="81cb0-158">Använd parametern _ResultSize_ för att ange upp till 250 000 loggposter.</span><span class="sxs-lookup"><span data-stu-id="81cb0-158">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="81cb0-159">Du kan också använda värdet `Unlimited` för att returnera alla transaktioner.</span><span class="sxs-lookup"><span data-stu-id="81cb0-159">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="81cb0-160">I det här exemplet söker du efter alla granskningsloggposter med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="81cb0-160">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="81cb0-161">**Startdatum**: 2018-08-04</span><span class="sxs-lookup"><span data-stu-id="81cb0-161">**Start date**: 08/04/2018</span></span>

- <span data-ttu-id="81cb0-162">**Slutdatum**: 2018-10-03</span><span class="sxs-lookup"><span data-stu-id="81cb0-162">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="81cb0-163">**Användar-ID:** Davids, Chrisd, Kima</span><span class="sxs-lookup"><span data-stu-id="81cb0-163">**User IDs**: davids, chrisd, kima</span></span>

- <span data-ttu-id="81cb0-164">**Cmdlets**: **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="81cb0-164">**Cmdlets**: **Set-Mailbox**</span></span>

- <span data-ttu-id="81cb0-165">**Parametrar**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="81cb0-165">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="81cb0-166">I det här exemplet söker du efter ändringar som gjorts i en viss postlåda.</span><span class="sxs-lookup"><span data-stu-id="81cb0-166">This example searches for changes made to a specific mailbox.</span></span> <span data-ttu-id="81cb0-167">Detta är användbart om du felsöker eller om du behöver ange information för en undersökning.</span><span class="sxs-lookup"><span data-stu-id="81cb0-167">This is useful if you're troubleshooting or you need to provide information for an investigation.</span></span> <span data-ttu-id="81cb0-168">Följande kriterier används:</span><span class="sxs-lookup"><span data-stu-id="81cb0-168">The following criteria are used:</span></span>

- <span data-ttu-id="81cb0-169">**Startdatum**: 2018-05-01</span><span class="sxs-lookup"><span data-stu-id="81cb0-169">**Start date**: 05/01/2018</span></span>

- <span data-ttu-id="81cb0-170">**Slutdatum**: 2018-10-03</span><span class="sxs-lookup"><span data-stu-id="81cb0-170">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="81cb0-171">**Objekt-ID:** contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="81cb0-171">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="81cb0-172">Om dina sökningar returnerar många loggposter rekommenderar vi att du använder proceduren i **Använd Exchange Online PowerShell för att söka efter granskningsloggposter och skicka resultat till en mottagare** senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="81cb0-172">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic.</span></span> <span data-ttu-id="81cb0-173">Proceduren i det avsnittet skickar en XML-fil som en e-postbilaga till de mottagare du anger, så att du lättare kan extrahera de data du är intresserad av.</span><span class="sxs-lookup"><span data-stu-id="81cb0-173">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="81cb0-174">Detaljerad syntax- och parameterinformation finns i [Sök-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="81cb0-174">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="81cb0-175">Visa information om granskningsloggposter</span><span class="sxs-lookup"><span data-stu-id="81cb0-175">View details of audit log entries</span></span>

<span data-ttu-id="81cb0-176">**Cmdlet search-adminAuditLog** returnerar de fält som beskrivs i [granskningslogginnehållet](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span><span class="sxs-lookup"><span data-stu-id="81cb0-176">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="81cb0-177">Av de fält som returneras av cmdlet, två fält, **CmdletParameters** och **ModifiedProperties**, innehåller ytterligare information som inte kan visas som standard.</span><span class="sxs-lookup"><span data-stu-id="81cb0-177">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="81cb0-178">Om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** använder du följande steg.</span><span class="sxs-lookup"><span data-stu-id="81cb0-178">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="81cb0-179">Du kan också använda proceduren i **Använda Exchange Online PowerShell för att söka efter granskningsloggposter och skicka resultat till en mottagare** senare i det här avsnittet för att skapa en XML-fil.</span><span class="sxs-lookup"><span data-stu-id="81cb0-179">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic to create an XML file.</span></span>

<span data-ttu-id="81cb0-180">I den här proceduren används följande begrepp:</span><span class="sxs-lookup"><span data-stu-id="81cb0-180">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="81cb0-181">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="81cb0-181">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="81cb0-182">about_Variables</span><span class="sxs-lookup"><span data-stu-id="81cb0-182">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="81cb0-183">Bestäm vilka villkor du vill söka efter, kör cmdleten **Sök-AdminAuditLog** och lagra resultaten i en variabel med följande kommando.</span><span class="sxs-lookup"><span data-stu-id="81cb0-183">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="81cb0-184">Varje granskningsloggpost lagras som ett matriselement i variabeln `$Results` .</span><span class="sxs-lookup"><span data-stu-id="81cb0-184">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="81cb0-185">Du kan markera ett matriselement genom att ange dess matriselementindex.</span><span class="sxs-lookup"><span data-stu-id="81cb0-185">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="81cb0-186">Matriselementindex börjar vid noll (0) för det första matriselementet.</span><span class="sxs-lookup"><span data-stu-id="81cb0-186">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="81cb0-187">Om du till exempel vill hämta det 5:e matriselementet, som har ett index på 4, använder du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="81cb0-187">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="81cb0-188">Föregående kommando returnerar loggposten som lagras i matriselement 4.</span><span class="sxs-lookup"><span data-stu-id="81cb0-188">The previous command returns the log entry stored in array element 4.</span></span> <span data-ttu-id="81cb0-189">Om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** för den här loggposten använder du följande kommandon.</span><span class="sxs-lookup"><span data-stu-id="81cb0-189">To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="81cb0-190">Om du vill visa innehållet i fälten **CmdletParameters** eller **ModifiedParameters** i en annan loggpost ändrar du matriselementindexet.</span><span class="sxs-lookup"><span data-stu-id="81cb0-190">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>