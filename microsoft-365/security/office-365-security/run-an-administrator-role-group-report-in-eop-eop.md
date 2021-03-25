---
title: Köra en administratörsrapport för rollgrupp i fristående EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa om hur de kör rapporten om administratörsrollgrupper i fristående Exchange Online Protection (EOP). Den här rapporten loggar när en administratör lägger till medlemmar i eller tar bort medlemmar från administratörsrollgrupper.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0281dcb13f5cee0ba8db8c4faed5054f481337cf
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207400"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="ac3fc-104">Köra en administratörsrapport för rollgrupp i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="ac3fc-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ac3fc-105">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="ac3fc-105">**Applies to**</span></span>
-  [<span data-ttu-id="ac3fc-106">Exchange Online Protection fristående</span><span class="sxs-lookup"><span data-stu-id="ac3fc-106">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="ac3fc-107">I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor loggas alla förekomster när en administratör lägger till medlemmar i eller tar bort medlemmar från administratörsrollgrupper.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-107">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="ac3fc-108">Mer information om rollgrupper i fristående EOP finns i [Behörigheter i fristående EOP.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="ac3fc-108">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="ac3fc-109">När du kör en rapport om administratörsrollgrupper i administrationscentret för Exchange (EAC) visas poster som sökresultat och omfattar de rollgrupper som påverkas, vem som ändrade medlemskap i rollgrupper och när och vilka medlemskapsuppdateringar som gjordes.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-109">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="ac3fc-110">Använd den här rapporten för att övervaka ändringar av administratörsbehörigheter som användare i organisationen tilldelats.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-110">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ac3fc-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="ac3fc-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ac3fc-112">Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="ac3fc-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="ac3fc-113">Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="ac3fc-114">Mer specifikt behöver  du  rollen Granskningsloggar eller Visningsskyddade granskningsloggar som tilldelas rollgrupperna Organisationshantering, Efterlevnadshantering och **Säkerhetsadministratör** som standard. </span><span class="sxs-lookup"><span data-stu-id="ac3fc-114">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="ac3fc-115">Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) och Använda EAC för att [ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="ac3fc-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="ac3fc-116">Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för [Administrationscenter för Exchange i Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="ac3fc-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="ac3fc-117">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="ac3fc-117">Having problems?</span></span> <span data-ttu-id="ac3fc-118">Be om hjälp i [Forumet för Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)</span><span class="sxs-lookup"><span data-stu-id="ac3fc-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="ac3fc-119">Använda EAC för att köra rapporten över administratörsrollgrupper</span><span class="sxs-lookup"><span data-stu-id="ac3fc-119">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="ac3fc-120">Kör rapporten om administratörsrollgrupper för att hitta ändringar i hanteringsrollgrupper inom en viss tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-120">Run the administrator role group report to find the changes to management role groups within a particular time frame.</span></span>

1. <span data-ttu-id="ac3fc-121">Gå till Granskning av efterlevnadshantering **i** EAC \> **och** välj sedan Kör **en rapport över administratörsrollgrupper.**</span><span class="sxs-lookup"><span data-stu-id="ac3fc-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="ac3fc-122">På sidan **Sök efter ändringar i administratörsrollgrupper** som öppnas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ac3fc-122">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="ac3fc-123">**Startdatum och** **Slutdatum: Ange** ett datumintervall.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-123">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="ac3fc-124">Som standard söker rapporten efter ändringar som gjorts i administratörsrollgrupper de senaste två veckorna.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-124">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="ac3fc-125">**Välj rollgrupper:** Som standard genomsöks alla rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-125">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="ac3fc-126">Om du vill filtrera resultatet efter specifika rollgrupper klickar du **på Välj rollgrupper**.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-126">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="ac3fc-127">I dialogrutan som visas väljer du en rollgrupp och klickar på **lägg till ->**.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-127">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="ac3fc-128">Upprepa det här steget så många gånger som behövs och klicka sedan **på OK** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-128">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="ac3fc-129">När du är klar klickar du på **Sök**.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-129">When you're finished, click **Search**.</span></span>

<span data-ttu-id="ac3fc-130">Om några ändringar hittas med hjälp av villkoret du angav visas de i resultatfönstret.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-130">If any changes are found using the criteria you specified, they will appear in the results pane.</span></span> <span data-ttu-id="ac3fc-131">Klicka på en rollgrupp i sökresultatet för att se ändringarna i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-131">Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ac3fc-132">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="ac3fc-132">How do you know this worked?</span></span>

<span data-ttu-id="ac3fc-133">Om du har kört en administratörsrollgruppsrapport visas rollgrupper som har ändrats inom datumintervallet i sökresultatfönstret.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-133">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane.</span></span> <span data-ttu-id="ac3fc-134">Om det inte finns några resultat har inga ändringar av rollgrupper skett inom det angivna datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-134">If there are no results, then no changes to role groups have taken place within the specified date range.</span></span> <span data-ttu-id="ac3fc-135">Om du tror att det ska finnas resultat ändrar du datumintervallet och kör rapporten igen.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-135">If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="ac3fc-136">Övervaka ändringar av medlemskap i rollgrupper</span><span class="sxs-lookup"><span data-stu-id="ac3fc-136">Monitor changes to role group membership</span></span>

<span data-ttu-id="ac3fc-137">När medlemmar läggs till i eller tas bort från en rollgrupp visar sökresultatet i informationsfönstret att rollgruppsmedlemskapet uppdaterades och listar de aktuella medlemmarna.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-137">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members.</span></span> <span data-ttu-id="ac3fc-138">Resultatet anger inte uttryckligen vilken användare som har lagts till eller tagits bort.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-138">The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="ac3fc-139">Om du vill avgöra om en användare har lagts till eller tagits bort måste du jämföra två separata poster i rapporten.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-139">To determine if a user was added or removed, you have to compare two separate entries in the report.</span></span> <span data-ttu-id="ac3fc-140">Låt oss till exempel titta på följande loggposter för **rollgruppen HelpDesk:**</span><span class="sxs-lookup"><span data-stu-id="ac3fc-140">For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="ac3fc-141">2018-01-27 16:43</span><span class="sxs-lookup"><span data-stu-id="ac3fc-141">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="ac3fc-142">Administratör</span><span class="sxs-lookup"><span data-stu-id="ac3fc-142">Administrator</span></span> <br> <span data-ttu-id="ac3fc-143">Uppdaterade medlemmar: Administrator;annb,lff;pilarp</span><span class="sxs-lookup"><span data-stu-id="ac3fc-143">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="ac3fc-144">2/06/2018 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="ac3fc-144">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="ac3fc-145">Administratör</span><span class="sxs-lookup"><span data-stu-id="ac3fc-145">Administrator</span></span> <br> <span data-ttu-id="ac3fc-146">Uppdaterade medlemmar: Administrator;annb;fsf;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="ac3fc-146">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="ac3fc-147">2/19/2018 14:12</span><span class="sxs-lookup"><span data-stu-id="ac3fc-147">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="ac3fc-148">Administratör</span><span class="sxs-lookup"><span data-stu-id="ac3fc-148">Administrator</span></span> <br> <span data-ttu-id="ac3fc-149">Uppdaterade medlemmar: Administrator;annb;lff;tonip</span><span class="sxs-lookup"><span data-stu-id="ac3fc-149">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="ac3fc-150">I det här exemplet har administratörsanvändarkontot gjort följande ändringar:</span><span class="sxs-lookup"><span data-stu-id="ac3fc-150">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="ac3fc-151">Den 2018-02-06 lade de till användaren tonip.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-151">On 2/06/2018, they added the user tonip.</span></span>
- <span data-ttu-id="ac3fc-152">Den 19/2/2018 tog de bort användaren pilarp.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-152">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="ac3fc-153">Använda fristående Exchange Online PowerShell för att söka efter granskningsloggposter</span><span class="sxs-lookup"><span data-stu-id="ac3fc-153">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="ac3fc-154">Du kan använda Exchange Online PowerShell för att söka efter granskningsloggposter som uppfyller de villkor du anger.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-154">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="ac3fc-155">En lista med sökvillkor finns i [Sök-AdminGranskningSlog-sökvillkor](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span><span class="sxs-lookup"><span data-stu-id="ac3fc-155">For a list of search criteria, see [Search-AdminAuditLog search criteria](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="ac3fc-156">I den här proceduren **används cmdleten Search-AdminAuditLog** och sökresultaten visas i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-156">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="ac3fc-157">Du kan använda den här cmdleten när du behöver returnera en uppsättning resultat som överskrider gränserna som definierats i cmdleten **New-AdminAuditLogSearch** eller i EAC-granskningsrapporteringsrapporter.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-157">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="ac3fc-158">Använd följande syntax för att söka i granskningsloggen efter villkor som du anger.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-158">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="ac3fc-159">**Cmdlet:en Search-AdminAuditLog** returnerar högst 1 000 loggposter som standard.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-159">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="ac3fc-160">Använd _parametern ResultSize_ till att ange upp till 250 000 loggposter.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-160">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="ac3fc-161">Du kan också använda värdet `Unlimited` för att returnera alla poster.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-161">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="ac3fc-162">I det här exemplet utförs en sökning efter alla granskningsloggposter med följande kriterier:</span><span class="sxs-lookup"><span data-stu-id="ac3fc-162">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="ac3fc-163">**Startdatum:** 2018-08-04</span><span class="sxs-lookup"><span data-stu-id="ac3fc-163">**Start date**: 08/04/2018</span></span>
- <span data-ttu-id="ac3fc-164">**Slutdatum:** 2018-10-03</span><span class="sxs-lookup"><span data-stu-id="ac3fc-164">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="ac3fc-165">**Användar-ID:,** `davids` `chrisd` , `kima`</span><span class="sxs-lookup"><span data-stu-id="ac3fc-165">**User IDs**: `davids`, `chrisd`, `kima`</span></span>
- <span data-ttu-id="ac3fc-166">**Cmdlets:** **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="ac3fc-166">**Cmdlets**: **Set-Mailbox**</span></span>
- <span data-ttu-id="ac3fc-167">**Parametrar:** _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="ac3fc-167">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="ac3fc-168">Det här exemplet söker efter ändringar som gjorts i en viss postlåda.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-168">This example searches for changes made to a specific mailbox.</span></span> <span data-ttu-id="ac3fc-169">Det är användbart om du felsöker eller behöver ange information för en undersökning.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-169">This is useful if you're troubleshooting or you need to provide information for an investigation.</span></span> <span data-ttu-id="ac3fc-170">Följande villkor används:</span><span class="sxs-lookup"><span data-stu-id="ac3fc-170">The following criteria are used:</span></span>

- <span data-ttu-id="ac3fc-171">**Startdatum:** 2018-05-01</span><span class="sxs-lookup"><span data-stu-id="ac3fc-171">**Start date**: 05/01/2018</span></span>
- <span data-ttu-id="ac3fc-172">**Slutdatum:** 2018-10-03</span><span class="sxs-lookup"><span data-stu-id="ac3fc-172">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="ac3fc-173">**Objekt-ID:** contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="ac3fc-173">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="ac3fc-174">Om dina sökningar returnerar många loggposter rekommenderar vi att du använder proceduren som finns i Använda **Exchange Online PowerShell** för att söka efter granskningsloggposter och skicka resultat till en mottagare senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-174">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article.</span></span> <span data-ttu-id="ac3fc-175">Proceduren i det avsnittet skickar en XML-fil som en e-postbilaga till de mottagare du anger, så att det blir enklare att extrahera de data du är intresserad av.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-175">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="ac3fc-176">Detaljerad information om syntax och parametrar finns [i Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="ac3fc-176">For detailed syntax and parameter information, see [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="ac3fc-177">Visa information om granskningsloggposter</span><span class="sxs-lookup"><span data-stu-id="ac3fc-177">View details of audit log entries</span></span>

<span data-ttu-id="ac3fc-178">**Cmdlet:en Search-AdminAuditLog** returnerar de fält som beskrivs i [Granskningsloggens innehåll.](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)</span><span class="sxs-lookup"><span data-stu-id="ac3fc-178">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="ac3fc-179">Av de fält som returneras av cmdleten innehåller två fält, **CmdletParameters** och **ModifiedProperties,** ytterligare information som inte kan visas som standard.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-179">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="ac3fc-180">Gör så här om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties.**</span><span class="sxs-lookup"><span data-stu-id="ac3fc-180">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="ac3fc-181">Du kan också använda proceduren i Använda **Exchange Online PowerShell** för att söka efter granskningsloggposter och skicka resultat till en mottagare senare i den här artikeln för att skapa en XML-fil.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-181">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article to create an XML file.</span></span>

<span data-ttu-id="ac3fc-182">I den här proceduren används följande begrepp:</span><span class="sxs-lookup"><span data-stu-id="ac3fc-182">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="ac3fc-183">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="ac3fc-183">about_Arrays</span></span>](/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="ac3fc-184">about_Variables</span><span class="sxs-lookup"><span data-stu-id="ac3fc-184">about_Variables</span></span>](/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="ac3fc-185">Bestäm vilka kriterier du vill söka efter, kör cmdleten **Search-AdminAuditLog** och lagra resultaten i en variabel med hjälp av följande kommando.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-185">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. <span data-ttu-id="ac3fc-186">Varje granskningsloggpost lagras som ett matriselement i variabeln `$Results` .</span><span class="sxs-lookup"><span data-stu-id="ac3fc-186">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="ac3fc-187">Du kan välja ett matriselement genom att ange dess matriselementindex.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-187">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="ac3fc-188">Matriselementindex börjar med noll (0) för det första matriselementet.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-188">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="ac3fc-189">Om du till exempel vill hämta det femte matriselementet, som har indexet 4, använder du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-189">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

   ```PowerShell
   $Results[4]
   ```

3. <span data-ttu-id="ac3fc-190">Föregående kommando returnerar loggposten som lagrats i matriselement 4.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-190">The previous command returns the log entry stored in array element 4.</span></span> <span data-ttu-id="ac3fc-191">Använd följande kommandon för att visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** för den här loggposten.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-191">To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. <span data-ttu-id="ac3fc-192">Om du vill visa innehållet i **fälten CmdletParameters** eller **ModifiedParameters** i en annan loggpost ändrar du matriselementindexet.</span><span class="sxs-lookup"><span data-stu-id="ac3fc-192">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>