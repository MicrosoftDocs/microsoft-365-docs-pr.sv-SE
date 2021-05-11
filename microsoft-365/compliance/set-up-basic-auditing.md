---
title: Konfigurera grundläggande granskning i Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: I den här artikeln beskrivs hur du ställer in Grundläggande granskning så att du kan börja söka efter granskningsaktiviteter som utförs av användare och administratörer i organisationen.
ms.openlocfilehash: ff1f973226378e5408dfae1d467394a5a5153196
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314407"
---
# <a name="set-up-basic-auditing-in-microsoft-365"></a><span data-ttu-id="3204a-103">Konfigurera grundläggande granskning i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3204a-103">Set up Basic auditing in Microsoft 365</span></span>

<span data-ttu-id="3204a-104">Med grundläggande granskning i Microsoft 365 kan du söka efter granskningsposter för aktiviteter som utförts Microsoft 365 olika tjänster av användare och administratörer.</span><span class="sxs-lookup"><span data-stu-id="3204a-104">Basic auditing in Microsoft 365 lets you search for audit records for activities performed in the different Microsoft 365 services by users and admins.</span></span> <span data-ttu-id="3204a-105">Eftersom Grundläggande granskning är aktiverat som standard för de flesta Microsoft 365- och Office 365-organisationer finns det bara några saker du behöver göra innan du och andra i organisationen kan söka i granskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="3204a-105">Because Basic auditing is enabled by default for most Microsoft 365 and Office 365 organizations, there's only a few things you need to do before you and others in your organization can search the audit log.</span></span>

<span data-ttu-id="3204a-106">I den här artikeln beskrivs följande steg för att konfigurera Grundläggande granskning.</span><span class="sxs-lookup"><span data-stu-id="3204a-106">This article discusses the following steps necessary to set up Basic auditing.</span></span>

![Steg för att konfigurera grundläggande granskning](../media/BasicAuditingWorkflow.png)

<span data-ttu-id="3204a-108">De här stegen omfattar att säkerställa korrekt organisationsprenumerationer och användarlicensiering som krävs för att generera och bevara granskningsposter och tilldela behörigheter till gruppmedlemmar i dina säkerhetsåtgärder, IT-, efterlevnads- och juridiska grupper så att du kan söka i granskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="3204a-108">These steps include ensuring the proper organizational subscriptions and user licensing required to generate and preserve audit records and assigning permissions to team members of your security operations, IT, compliance, and legal teams so that can search the audit log.</span></span>

<span data-ttu-id="3204a-109">Mer information finns i [Grundläggande granskning i Microsoft 365](auditing-solutions-overview.md#basic-auditing).</span><span class="sxs-lookup"><span data-stu-id="3204a-109">For more information, see [Basic auditing in Microsoft 365](auditing-solutions-overview.md#basic-auditing).</span></span>

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a><span data-ttu-id="3204a-110">Steg 1: Kontrollera organisationens prenumeration och användarlicensiering</span><span class="sxs-lookup"><span data-stu-id="3204a-110">Step 1: Verify organization subscription and user licensing</span></span>

<span data-ttu-id="3204a-111">Licensiering för grundläggande granskning kräver en lämplig organisationsprenumeration som ger åtkomst till verktyget för granskningsloggsökning och licensiering per användare som krävs för att logga och behålla granskningsposter.</span><span class="sxs-lookup"><span data-stu-id="3204a-111">Licensing for Basic auditing requires the appropriate organization subscription that provides access to audit log search tool and per-user licensing that's required to log and retain audit records.</span></span>

<span data-ttu-id="3204a-112">När en granskad aktivitet utförs av en användare eller administratör genereras en granskningspost och lagras i granskningsloggen för din organisation.</span><span class="sxs-lookup"><span data-stu-id="3204a-112">When an audited activity is performed by a user or admin, an audit record is generated and stored in the audit log for your organization.</span></span> <span data-ttu-id="3204a-113">I grundläggande granskning behålls granskningsposter och är sökbara i granskningsloggen i 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="3204a-113">In Basic auditing, audit records are retained and searchable in the audit log for 90 days.</span></span>

<span data-ttu-id="3204a-114">En lista över prenumerations- och licenskrav för grundläggande granskning finns [i Granskningslösningar i Microsoft 365](auditing-solutions-overview.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="3204a-114">For a list of subscription and licensing requirements for Basic auditing, see [Auditing solutions in Microsoft 365](auditing-solutions-overview.md#licensing-requirements).</span></span>

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a><span data-ttu-id="3204a-115">Steg 2: Tilldela behörigheter för att söka i granskningsloggen</span><span class="sxs-lookup"><span data-stu-id="3204a-115">Step 2: Assign permissions to search the audit log</span></span>

<span data-ttu-id="3204a-116">Administratörer och medlemmar i undersökningsgrupper måste ha tilldelats rollen View-Only granskningsloggar eller granskningsloggar i Exchange Online att söka i granskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="3204a-116">Admins and members of investigation teams must be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the audit log.</span></span> <span data-ttu-id="3204a-117">Som standard tilldelas de här rollerna till rollgrupperna  Efterlevnadshantering och Organisationshantering på sidan Behörigheter Exchange administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="3204a-117">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="3204a-118">Globala administratörer i Office 365 och Microsoft 365 läggs automatiskt till som medlemmar i rollgruppen Organisationshantering i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3204a-118">Global administrators in Office 365 and Microsoft 365 are automatically added as members of the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="3204a-119">Om du vill ge en användare möjlighet att söka i granskningsloggen med den lägsta nivån av behörigheter kan du skapa en anpassad rollgrupp i Exchange Online, lägga till rollen View-Only Granskningsloggar eller Granskningsloggar och sedan lägga till användaren som medlem i den nya rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="3204a-119">To give a user the ability to search the audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="3204a-120">Mer information finns i [Hantera rollgrupper i Exchange Online](/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="3204a-120">For more information, see [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups).</span></span>

<span data-ttu-id="3204a-121">Följande skärmbild visar de två granskningsrelaterade rollerna som tilldelats rollgruppen Organisationshantering i Exchange administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="3204a-121">The following screenshot shows the two audit-related roles assigned to the Organization Management role group in the Exchange admin center.</span></span>

![Granska roller som tilldelats rollgrupp i Exchange Online](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a><span data-ttu-id="3204a-123">Steg 3: Söka i granskningsloggen</span><span class="sxs-lookup"><span data-stu-id="3204a-123">Step 3: Search the audit log</span></span>

<span data-ttu-id="3204a-124">Nu är du redo att söka i granskningsloggen i Microsoft 365 efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="3204a-124">Now you're ready to search the audit log in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="3204a-125">Gå till <https://compliance.microsoft.com> och logga in med ett konto som har tilldelats lämpliga granskningsbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="3204a-125">Go to <https://compliance.microsoft.com> and sign in using an account that has been assigned the appropriate audit permissions.</span></span>

2. <span data-ttu-id="3204a-126">I det vänstra navigeringsfönstret i Microsoft 365, klickar du på **Visa alla och** sedan på **Granska.**</span><span class="sxs-lookup"><span data-stu-id="3204a-126">In the left navigation pane of the Microsoft 365 compliance center, click **Show all** and then click **Audit**.</span></span>

3. <span data-ttu-id="3204a-127">På **sidan Granskning** konfigurerar du sökningen enligt följande villkor på **fliken** Sök.</span><span class="sxs-lookup"><span data-stu-id="3204a-127">On the **Audit** page, configure the search using the following conditions on the **Search** tab.</span></span> 

   ![Konfigurationsinställningar för granskningsloggsökning](../media/AuditLogSearchToolMCCCallouts.png)

   1. <span data-ttu-id="3204a-129">**Datum- och tidsintervall**.</span><span class="sxs-lookup"><span data-stu-id="3204a-129">**Date and time range**.</span></span> <span data-ttu-id="3204a-130">Välj ett datum- och tidsintervall för att visa händelser som inträffat under perioden.</span><span class="sxs-lookup"><span data-stu-id="3204a-130">Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="3204a-131">Datum och tid presenteras i lokal tid.</span><span class="sxs-lookup"><span data-stu-id="3204a-131">The date and time are presented in local time.</span></span> <span data-ttu-id="3204a-132">De senaste sju dagarna är valda som standard.</span><span class="sxs-lookup"><span data-stu-id="3204a-132">The last seven days are selected by default.</span></span>
  
   2. <span data-ttu-id="3204a-133">**Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="3204a-133">**Activities**.</span></span> <span data-ttu-id="3204a-134">Välj de aktiviteter du vill söka efter.</span><span class="sxs-lookup"><span data-stu-id="3204a-134">Select the activities to search for.</span></span> <span data-ttu-id="3204a-135">Använd sökrutan för att söka efter aktiviteter som du vill lägga till i listan.</span><span class="sxs-lookup"><span data-stu-id="3204a-135">Use the search box to search for activities to add to the list.</span></span> <span data-ttu-id="3204a-136">En delvis lista över granskade aktiviteter finns i [Granskade aktiviteter.](search-the-audit-log-in-security-and-compliance.md#audited-activities)</span><span class="sxs-lookup"><span data-stu-id="3204a-136">For a partial list of audited activities, see [Audited activities](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span> <span data-ttu-id="3204a-137">Lämna rutan tom för att returnera poster för alla granskade aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="3204a-137">Leave this box blank to return entries for all audited activities.</span></span>
  
   3. <span data-ttu-id="3204a-138">**Användare.**</span><span class="sxs-lookup"><span data-stu-id="3204a-138">**Users**.</span></span>  <span data-ttu-id="3204a-139">Klicka i den här rutan och börja skriva namnet på de användare som du vill visa sökresultat för.</span><span class="sxs-lookup"><span data-stu-id="3204a-139">Click in this box and start typing the name of users to display search results for.</span></span> <span data-ttu-id="3204a-140">I resultatlistan visas granskningsloggposterna för de markerade aktiviteter som utförts av de användare du väljer i den här rutan.</span><span class="sxs-lookup"><span data-stu-id="3204a-140">The audit log entries for the selected activities performed by the users you select in this box are displayed in the list of results.</span></span> <span data-ttu-id="3204a-141">Lämna rutan tom för att returnera poster för alla användare (och tjänstkonton) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3204a-141">Leave this box blank to return entries for all users (and service accounts) in your organization.</span></span>
  
   4. <span data-ttu-id="3204a-142">**Fil, mapp eller webbplats**.</span><span class="sxs-lookup"><span data-stu-id="3204a-142">**File, folder, or site**.</span></span> <span data-ttu-id="3204a-143">Skriv en del av eller hela fil- eller mappnamnet för att söka efter aktivitet relaterad till filen i mappen som innehåller det angivna nyckelordet.</span><span class="sxs-lookup"><span data-stu-id="3204a-143">Type some or all of a file or folder name to search for activity related to the file of folder that contains the specified keyword.</span></span> <span data-ttu-id="3204a-144">Du kan också ange URL-adressen till en fil eller mapp.</span><span class="sxs-lookup"><span data-stu-id="3204a-144">You can also specify a URL of a file or folder.</span></span> <span data-ttu-id="3204a-145">Om du använder URL-adressen till en fil eller mapp ska du se till att skriva den fullständiga URL-sökvägen. Om du skriver en del av URL:en får du inte skriva några specialtecken eller blanksteg.</span><span class="sxs-lookup"><span data-stu-id="3204a-145">If you use a URL of a file or folder, be sure the type the full URL path or if you type a portion of the URL, don't include any special characters or spaces.</span></span> <span data-ttu-id="3204a-146">Lämna rutan tom för att returnera poster för alla filer och mappar i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3204a-146">Leave this box blank to return entries for all files and folders in your organization.</span></span>

4. <span data-ttu-id="3204a-147">Klicka **på Sök** för att köra sökningen.</span><span class="sxs-lookup"><span data-stu-id="3204a-147">Click **Search** to run the search.</span></span>

<span data-ttu-id="3204a-148">En ny sida visas som visar att granskningsloggsökningen körs.</span><span class="sxs-lookup"><span data-stu-id="3204a-148">A new page is display that shows the audit log search is running.</span></span> <span data-ttu-id="3204a-149">När sökningen är klar visas granskningsposter på sidan.</span><span class="sxs-lookup"><span data-stu-id="3204a-149">When the search is completed, audit records are displayed on the page.</span></span> <span data-ttu-id="3204a-150">Klicka på en post för att visa en utfällsida med detaljerade egenskaper.</span><span class="sxs-lookup"><span data-stu-id="3204a-150">Click a record to display a flyout page with detailed properties.</span></span>

<span data-ttu-id="3204a-151">Mer detaljerade anvisningar finns i Söka [i granskningsloggen i efterlevnadscentret.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="3204a-151">For more detailed instructions, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md).</span></span>
