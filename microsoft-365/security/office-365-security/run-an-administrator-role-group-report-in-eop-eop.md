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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om hur man kör en administratörs grupp rapport i fristående Exchange Online Protection (EOP). Den här rapporten loggar när en administratör lägger till eller tar bort medlemmar från administratörs roll grupper, loggar EOP varje gång.
ms.openlocfilehash: f2f3e32a818825d14c02b2bbffdc136e82f83013
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200487"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="49ce1-104">Köra en administratörsrapport för rollgrupp i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="49ce1-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="49ce1-105">I fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor när en administratör lägger till eller tar bort medlemmar från administratörs roll grupper loggar tjänsten in varje förekomst.</span><span class="sxs-lookup"><span data-stu-id="49ce1-105">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="49ce1-106">Mer information om roll grupper i fristående EOP finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="49ce1-106">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="49ce1-107">När du kör en rapport i administratörs gruppen för administratörer i administrations centret för Exchange (UK) visas posterna som Sök Resultat och innehåller de roll grupper som påverkas, vem som ändrade roll gruppens medlemskap och när och vilka medlemskaps uppdateringar som har gjorts.</span><span class="sxs-lookup"><span data-stu-id="49ce1-107">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="49ce1-108">Använd den här rapporten för att övervaka ändringar av de administrativa behörigheter som tilldelats användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="49ce1-108">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="49ce1-109">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="49ce1-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="49ce1-110">Om du vill öppna administrations centret för Exchange går du till [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="49ce1-110">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="49ce1-111">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="49ce1-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="49ce1-112">Specifikt måste du ha rollen gransknings loggar eller skrivskyddade loggar, som är tilldelad till ComplianceManagement, i (globala administratörer) och SecurityAdministrator roll grupper som standard.</span><span class="sxs-lookup"><span data-stu-id="49ce1-112">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="49ce1-113">Mer information finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd UK för att ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="49ce1-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="49ce1-114">Information om tangent bords gen vägar som kan gälla för procedurerna i det här avsnittet finns i kortkommandon [för administrations centret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="49ce1-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="49ce1-115">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="49ce1-115">Having problems?</span></span> <span data-ttu-id="49ce1-116">Be om hjälp i [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span><span class="sxs-lookup"><span data-stu-id="49ce1-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="49ce1-117">Använda rapporten UK för att köra en administratörs roll</span><span class="sxs-lookup"><span data-stu-id="49ce1-117">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="49ce1-118">Kör rapporten administratörs grupp för att hitta ändringarna av roll grupperna för hantering i organisationen inom en viss tidsram.</span><span class="sxs-lookup"><span data-stu-id="49ce1-118">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="49ce1-119">Gå till granskning i **överensstämmelse hantering** i UK \> **Auditing**och välj sedan **kör en administratörs grupp rapport för administratörer**.</span><span class="sxs-lookup"><span data-stu-id="49ce1-119">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="49ce1-120">I sidan **Sök efter ändringar av gruppen Administratörer** som öppnas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="49ce1-120">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="49ce1-121">**Start datum** och **slutdatum**: Ange ett datum intervall.</span><span class="sxs-lookup"><span data-stu-id="49ce1-121">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="49ce1-122">Som standard söker rapporten efter ändringar som gjorts i administratörs roll grupper under de senaste två veckorna.</span><span class="sxs-lookup"><span data-stu-id="49ce1-122">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="49ce1-123">**Välj roll grupper**: som standard genomsöks alla roll grupper.</span><span class="sxs-lookup"><span data-stu-id="49ce1-123">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="49ce1-124">Om du vill filtrera resultaten efter specifika roll grupper klickar du på **Välj roll grupper**.</span><span class="sxs-lookup"><span data-stu-id="49ce1-124">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="49ce1-125">I dialog rutan som visas väljer du en roll grupp och klickar på **Lägg till >**.</span><span class="sxs-lookup"><span data-stu-id="49ce1-125">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="49ce1-126">Upprepa det här steget så många gånger som behövs och klicka sedan på **OK** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="49ce1-126">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="49ce1-127">När du är klar klickar du på **Sök**.</span><span class="sxs-lookup"><span data-stu-id="49ce1-127">When you're finished, click **Search**.</span></span>

<span data-ttu-id="49ce1-128">Om några ändringar hittas med de villkor du angett visas de i fönstret resultat.</span><span class="sxs-lookup"><span data-stu-id="49ce1-128">If any changes are found using the criteria you specified, they will appear in the results pane.</span></span> <span data-ttu-id="49ce1-129">Klicka på en roll grupp i Sök resultatet för att visa ändringarna i informations fönstret.</span><span class="sxs-lookup"><span data-stu-id="49ce1-129">Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="49ce1-130">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="49ce1-130">How do you know this worked?</span></span>

<span data-ttu-id="49ce1-131">Om du har kört en administratörs rapport för administratörer visas roll grupper som har ändrats inom datum intervallet i fönstret Sök resultat.</span><span class="sxs-lookup"><span data-stu-id="49ce1-131">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane.</span></span> <span data-ttu-id="49ce1-132">Om det inte finns några resultat ändras inga roll grupper i det angivna datum intervallet.</span><span class="sxs-lookup"><span data-stu-id="49ce1-132">If there are no results, then no changes to role groups have taken place within the specified date range.</span></span> <span data-ttu-id="49ce1-133">Om du tror att det borde finnas resultat, ändra datum intervallet och kör sedan rapporten igen.</span><span class="sxs-lookup"><span data-stu-id="49ce1-133">If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="49ce1-134">Övervaka ändringar i roll grupp medlemskap</span><span class="sxs-lookup"><span data-stu-id="49ce1-134">Monitor changes to role group membership</span></span>

<span data-ttu-id="49ce1-135">När medlemmar läggs till eller tas bort från en roll grupp indikerar Sök resultaten som visas i informations fönstret att roll grupp medlemskapet har uppdaterats och visar en lista över aktuella medlemmar.</span><span class="sxs-lookup"><span data-stu-id="49ce1-135">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members.</span></span> <span data-ttu-id="49ce1-136">Resultaten anger inte uttryckligen vilken användare som lades till eller togs bort.</span><span class="sxs-lookup"><span data-stu-id="49ce1-136">The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="49ce1-137">För att avgöra om en användare har lagts till eller tagits bort måste du jämföra två separata poster i rapporten.</span><span class="sxs-lookup"><span data-stu-id="49ce1-137">To determine if a user was added or removed, you have to compare two separate entries in the report.</span></span> <span data-ttu-id="49ce1-138">Låt oss titta på följande logg poster för roll gruppen **helpdesk** :</span><span class="sxs-lookup"><span data-stu-id="49ce1-138">For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="49ce1-139">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="49ce1-139">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="49ce1-140">Lösen</span><span class="sxs-lookup"><span data-stu-id="49ce1-140">Administrator</span></span> <br> <span data-ttu-id="49ce1-141">Uppdaterade medlemmar: administratör; annb; florencef; pilarp</span><span class="sxs-lookup"><span data-stu-id="49ce1-141">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="49ce1-142">2/06/2018 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="49ce1-142">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="49ce1-143">Lösen</span><span class="sxs-lookup"><span data-stu-id="49ce1-143">Administrator</span></span> <br> <span data-ttu-id="49ce1-144">Uppdaterade medlemmar: administratör; annb; florencef; pilarp; tonip</span><span class="sxs-lookup"><span data-stu-id="49ce1-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="49ce1-145">2/19/2018 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="49ce1-145">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="49ce1-146">Lösen</span><span class="sxs-lookup"><span data-stu-id="49ce1-146">Administrator</span></span> <br> <span data-ttu-id="49ce1-147">Uppdaterade medlemmar: administratör; annb; florencef; tonip</span><span class="sxs-lookup"><span data-stu-id="49ce1-147">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="49ce1-148">I det här exemplet utförde administratörs användar kontot följande ändringar:</span><span class="sxs-lookup"><span data-stu-id="49ce1-148">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="49ce1-149">I 2/06/2018 La de in användaren tonip.</span><span class="sxs-lookup"><span data-stu-id="49ce1-149">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="49ce1-150">På 2/19/2018 har de tagit bort användaren pilarp.</span><span class="sxs-lookup"><span data-stu-id="49ce1-150">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="49ce1-151">Använda fristående Exchange Online PowerShell för att söka efter Gransknings logg poster</span><span class="sxs-lookup"><span data-stu-id="49ce1-151">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="49ce1-152">Du kan använda Exchange Online PowerShell för att söka efter poster för gransknings loggar som uppfyller de villkor du anger.</span><span class="sxs-lookup"><span data-stu-id="49ce1-152">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="49ce1-153">En lista över Sök villkor finns i [Sök-AdminAuditLog Sök kriterier](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span><span class="sxs-lookup"><span data-stu-id="49ce1-153">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="49ce1-154">Den här proceduren använder cmdleten **search-AdminAuditLog** och visar Sök resultat i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49ce1-154">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="49ce1-155">Du kan använda denna cmdlet när du behöver returnera en uppsättning resultat som överskrider de gränser som är definierade för **New-AdminAuditLogSearch-** cmdleten eller i rapporteringen för UK-granskningen.</span><span class="sxs-lookup"><span data-stu-id="49ce1-155">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="49ce1-156">Använd följande syntax för att söka i den Gransknings logg efter villkor du anger.</span><span class="sxs-lookup"><span data-stu-id="49ce1-156">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="49ce1-157">Cmdleten **search-AdminAuditLog** returnerar högst 1 000-loggpost som standard.</span><span class="sxs-lookup"><span data-stu-id="49ce1-157">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="49ce1-158">Använd parametern _ResultSize_ för att ange upp till 250 000-loggnings poster.</span><span class="sxs-lookup"><span data-stu-id="49ce1-158">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="49ce1-159">Eller Använd värdet `Unlimited` för att returnera alla poster.</span><span class="sxs-lookup"><span data-stu-id="49ce1-159">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="49ce1-160">I det här exemplet utförs en sökning efter alla gransknings loggar med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="49ce1-160">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="49ce1-161">**Start datum**: 08/04/2018</span><span class="sxs-lookup"><span data-stu-id="49ce1-161">**Start date**: 08/04/2018</span></span>

- <span data-ttu-id="49ce1-162">**Slutdatum**: 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="49ce1-162">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="49ce1-163">**Användar-ID**: Davids, Chris Kima</span><span class="sxs-lookup"><span data-stu-id="49ce1-163">**User IDs**: davids, chrisd, kima</span></span>

- <span data-ttu-id="49ce1-164">**Cmdlet**: **set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="49ce1-164">**Cmdlets**: **Set-Mailbox**</span></span>

- <span data-ttu-id="49ce1-165">**Parametrar**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="49ce1-165">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="49ce1-166">I det här exemplet söker du efter ändringar som gjorts i en viss post låda.</span><span class="sxs-lookup"><span data-stu-id="49ce1-166">This example searches for changes made to a specific mailbox.</span></span> <span data-ttu-id="49ce1-167">Det är användbart om du felsöker eller om du behöver ange information för en undersökning.</span><span class="sxs-lookup"><span data-stu-id="49ce1-167">This is useful if you're troubleshooting or you need to provide information for an investigation.</span></span> <span data-ttu-id="49ce1-168">Följande kriterier används:</span><span class="sxs-lookup"><span data-stu-id="49ce1-168">The following criteria are used:</span></span>

- <span data-ttu-id="49ce1-169">**Start datum**: 05/01/2018</span><span class="sxs-lookup"><span data-stu-id="49ce1-169">**Start date**: 05/01/2018</span></span>

- <span data-ttu-id="49ce1-170">**Slutdatum**: 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="49ce1-170">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="49ce1-171">**Objekt-ID**: contoso.com/users/DavidS</span><span class="sxs-lookup"><span data-stu-id="49ce1-171">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="49ce1-172">Om dina sökningar returnerar många logg poster rekommenderar vi att du använder proceduren i **använda Exchange Online PowerShell för att söka efter poster för gransknings logg och skickar resultat till en mottagare** längre ned i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="49ce1-172">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic.</span></span> <span data-ttu-id="49ce1-173">Proceduren i avsnittet skickar en XML-fil som en e-postbilaga till de mottagare som du anger, vilket gör att du enkelt kan extrahera de data du är intresse rad av.</span><span class="sxs-lookup"><span data-stu-id="49ce1-173">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="49ce1-174">Detaljerad information om syntax och parametrar finns i [sökAdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="49ce1-174">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="49ce1-175">Visa information om Gransknings logg poster</span><span class="sxs-lookup"><span data-stu-id="49ce1-175">View details of audit log entries</span></span>

<span data-ttu-id="49ce1-176">Cmdleten **search-AdminAuditLog** returnerar fälten som beskrivs i [gransknings loggens innehåll](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span><span class="sxs-lookup"><span data-stu-id="49ce1-176">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="49ce1-177">För de fält som returneras av cmdleten, två fält, **CmdletParameters** och **ModifiedProperties**, innehåller ytterligare information som inte visas som standard.</span><span class="sxs-lookup"><span data-stu-id="49ce1-177">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="49ce1-178">Om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="49ce1-178">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="49ce1-179">Eller så kan du använda proceduren i **använda Exchange Online PowerShell för att söka efter poster för gransknings logg och skicka resultat till en mottagare** senare i det här avsnittet för att skapa en XML-fil.</span><span class="sxs-lookup"><span data-stu-id="49ce1-179">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic to create an XML file.</span></span>

<span data-ttu-id="49ce1-180">I den här proceduren används följande koncept:</span><span class="sxs-lookup"><span data-stu-id="49ce1-180">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="49ce1-181">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="49ce1-181">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="49ce1-182">about_Variables</span><span class="sxs-lookup"><span data-stu-id="49ce1-182">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="49ce1-183">Välj de villkor du vill söka efter, kör **Sök-AdminAuditLog** cmdlet och lagra resultatet i en variabel med hjälp av följande kommando.</span><span class="sxs-lookup"><span data-stu-id="49ce1-183">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="49ce1-184">Varje post för gransknings logg sparas som ett mat ris element i variabeln `$Results` .</span><span class="sxs-lookup"><span data-stu-id="49ce1-184">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="49ce1-185">Du kan välja ett mat ris element genom att ange dess mat ris element index.</span><span class="sxs-lookup"><span data-stu-id="49ce1-185">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="49ce1-186">Mat ris element index börjar med noll (0) för det första mat ris elementet.</span><span class="sxs-lookup"><span data-stu-id="49ce1-186">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="49ce1-187">Om du till exempel vill hämta femte mat ris elementet, som har index 4, använder du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="49ce1-187">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="49ce1-188">Föregående kommando returnerar den loggpost som är lagrad i mat ris element 4.</span><span class="sxs-lookup"><span data-stu-id="49ce1-188">The previous command returns the log entry stored in array element 4.</span></span> <span data-ttu-id="49ce1-189">Använd följande kommandon för att visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** för den här logg posten.</span><span class="sxs-lookup"><span data-stu-id="49ce1-189">To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="49ce1-190">Om du vill visa innehållet i fälten **CmdletParameters** eller **ModifiedParameters** i en annan loggpost ändrar du mat ris element indexet.</span><span class="sxs-lookup"><span data-stu-id="49ce1-190">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>
