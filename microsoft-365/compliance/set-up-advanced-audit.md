---
title: Konfigurera avancerad granskning i Microsoft 365
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
description: I den här artikeln beskrivs hur du ställer in Avancerad granskning så att du kan utföra undersökningar av en forensisk undersökning när användarkonton har komprometterats eller undersöka andra säkerhetsrelaterade incidenter.
ms.openlocfilehash: d1752ee7714056254a6c0e5c009aa9aa79ddff3b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314415"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a><span data-ttu-id="5584b-103">Konfigurera avancerad granskning i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5584b-103">Set up Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="5584b-104">Om organisationen har en prenumeration och licensiering för slutanvändare som stöder avancerad granskning utför du följande steg för att konfigurera och använda de ytterligare funktionerna i Avancerad granskning.</span><span class="sxs-lookup"><span data-stu-id="5584b-104">If your organization has a subscription and end user licensing that supports Advanced Audit, perform the following steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![Arbetsflöde för att konfigurera Avancerad granskning för användare](../media/AdvancedAuditWorkflow.png)

## <a name="step1-set-up-advanced-audit-for-users"></a><span data-ttu-id="5584b-106">Steg1: Konfigurera avancerad granskning för användare</span><span class="sxs-lookup"><span data-stu-id="5584b-106">Step1: Set up Advanced Audit for users</span></span>

<span data-ttu-id="5584b-107">För Avancerad granskning-funktioner som möjligheten att logga viktiga händelser, till exempel MailItemsAccessed och Send, måste användarna ha tilldelats rätt E5-licens.</span><span class="sxs-lookup"><span data-stu-id="5584b-107">Advanced Audit features such as the ability to log crucial events such as MailItemsAccessed and Send require an appropriate E5 license assigned to users.</span></span> <span data-ttu-id="5584b-108">Dessutom måste appen/tjänstplanen Advanced Auditing vara aktiverad för dessa användare.</span><span class="sxs-lookup"><span data-stu-id="5584b-108">Additionally, the Advanced Auditing app/service plan must be enabled for those users.</span></span> <span data-ttu-id="5584b-109">Du kan kontrollera att appen Advanced Auditing har tilldelats användarna genom att utföra följande steg för varje användare:</span><span class="sxs-lookup"><span data-stu-id="5584b-109">To verify that the Advanced Auditing app is assigned to users, perform the following steps for each user:</span></span>

1. <span data-ttu-id="5584b-110">I [Administrationscenter för Microsoft 365](https://admin.microsoft.com/Adminportal) går du till **Användare** > **Aktiva användare** och väljer en användare.</span><span class="sxs-lookup"><span data-stu-id="5584b-110">In the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal), go to **Users** > **Active users**, and select a user.</span></span>

2. <span data-ttu-id="5584b-111">Klicka på **Licenser och appar** på den utfällbara sidan med användaregenskaper.</span><span class="sxs-lookup"><span data-stu-id="5584b-111">On the user properties flyout page, click **Licenses and apps**.</span></span>

3. <span data-ttu-id="5584b-112">I avsnittet **Licenser** kontrollerar du att användaren har tilldelats en E5-licens eller har tilldelats en lämplig tilläggslicens.</span><span class="sxs-lookup"><span data-stu-id="5584b-112">In the **Licenses** section, verify that the user is assigned an E5 license or is assigned an appropriate add-on license.</span></span> <span data-ttu-id="5584b-113">En lista över licenser som stöder Avancerad granskning finns i [Licenskrav för avancerad granskning.](auditing-solutions-overview.md#advanced-audit-1)</span><span class="sxs-lookup"><span data-stu-id="5584b-113">For a list of licenses that support Advanced Audit, see [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).</span></span>

4. <span data-ttu-id="5584b-114">Visa avsnittet **Appar** och kontrollera att kryssrutan **Microsoft 365 Advanced Auditing** är markerad.</span><span class="sxs-lookup"><span data-stu-id="5584b-114">Expand the **Apps** section, and verify that the **Microsoft 365 Advanced Auditing** checkbox is selected.</span></span>

5. <span data-ttu-id="5584b-115">Om kryssrutan inte är markerad markerar du den och klickar sedan på **Spara ändringar.**</span><span class="sxs-lookup"><span data-stu-id="5584b-115">If the checkbox isn't selected, select it, and then click **Save changes.**</span></span>

   <span data-ttu-id="5584b-116">Loggning av granskningsposter för MailItemsAccessed och Send startar inom 24 timmar.</span><span class="sxs-lookup"><span data-stu-id="5584b-116">The logging of audit records for MailItemsAccessed and Send will begin within 24 hours.</span></span> <span data-ttu-id="5584b-117">Du måste utföra steg 3 för att börja loggning av två andra viktiga händelser för Avancerad granskning: SearchQueryInitiatedExchange och SearchQueryInitiatedSharePoint.</span><span class="sxs-lookup"><span data-stu-id="5584b-117">You have to perform Step 3 to start logging of two other Advanced Audit crucial events: SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint.</span></span>

<span data-ttu-id="5584b-118">Om organisationen tilldelar licenser till grupper av användare med hjälp av gruppbaserad licensiering måste du inaktivera licenstilldelningen för Microsoft 365 Advanced Auditing för gruppen.</span><span class="sxs-lookup"><span data-stu-id="5584b-118">For organizations that assign licenses to groups of users by using group-based licensing, you have to turn off the licensing assignment for Microsoft 365 Advanced Auditing for the group.</span></span> <span data-ttu-id="5584b-119">När du har sparat ändringarna kontrollerar du att Microsoft 365 Advanced Auditing är inaktiverat för gruppen.</span><span class="sxs-lookup"><span data-stu-id="5584b-119">After you save your changes, verify that Microsoft 365 Advanced Auditing is turned off for the group.</span></span> <span data-ttu-id="5584b-120">Aktivera sedan licenstilldelningen för gruppen igen.</span><span class="sxs-lookup"><span data-stu-id="5584b-120">Then turn the licensing assignment for the group back on.</span></span> <span data-ttu-id="5584b-121">Instruktioner för hur du använder gruppbaserad licensiering finns i [Tilldela licenser till användare efter gruppmedlemskap i Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="5584b-121">For instructions about group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="5584b-122">Om du har anpassat postlådeåtgärder som loggas på användarpostlådor eller delade postlådor, granskas inte automatiskt nya nödvändiga händelser som släppts av Microsoft för dessa postlådor.</span><span class="sxs-lookup"><span data-stu-id="5584b-122">Also, if you have customized the mailbox actions that are logged on user mailboxes or shared mailboxes, any new crucial events released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="5584b-123">Information om hur du ändrar postlådeåtgärderna som granskas för varje inloggningstyp finns i avsnittet ”Ändra eller återställa postlådeåtgärder som loggas som standard” i [Hantera postlådegranskning](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span><span class="sxs-lookup"><span data-stu-id="5584b-123">For information about changing the mailbox actions that are audited for each logon type, see the "Change or restore mailbox actions logged by default" section in [Manage mailbox auditing](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span></span>

## <a name="step-2-enable-crucial-events"></a><span data-ttu-id="5584b-124">Steg 2: Aktivera avgörande händelser</span><span class="sxs-lookup"><span data-stu-id="5584b-124">Step 2: Enable crucial events</span></span>

<span data-ttu-id="5584b-125">Du måste aktivera två avgörande händelser (SearchQueryInitiatedExchange och SearchQueryInitiatedSharePoint) som ska loggas när användare utför sökningar i Exchange Online och SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5584b-125">You have to enable two crucial events (SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint) to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="5584b-126">Om du vill aktivera de här två händelserna för användare kör du följande kommando (för varje användare) [i Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="5584b-126">To enable these two events to be audited for users, run the following command (for each user) in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

<span data-ttu-id="5584b-127">I en geomiljö med flera platser  måste du köra det tidigare kommandot Uppsättningspostlåda i skogen där användarens postlåda finns.</span><span class="sxs-lookup"><span data-stu-id="5584b-127">In a multi-geo environment, you must run the previous **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="5584b-128">Kör följande kommando för att identifiera användarens postlådas plats:</span><span class="sxs-lookup"><span data-stu-id="5584b-128">To identify the user's mailbox location, run the following command:</span></span> 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

<span data-ttu-id="5584b-129">Om kommandot för att aktivera granskning av sökfrågor tidigare kördes i en annan skog än den användarens postlåda finns i, måste du ta bort värdet searchQueryInitiated från användarens postlåda genom att köra och sedan lägga till det i användarens postlåda i skogen där användarens postlåda `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` finns.</span><span class="sxs-lookup"><span data-stu-id="5584b-129">If the command to enable the auditing of search queries was previously run in a forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

## <a name="step-3-set-up-audit-retention-policies"></a><span data-ttu-id="5584b-130">Steg 3: Konfigurera bevarandeprinciper för granskning</span><span class="sxs-lookup"><span data-stu-id="5584b-130">Step 3: Set up audit retention policies</span></span>

<span data-ttu-id="5584b-131">Utöver standardprincipen som behåller granskningsposter för Exchange, SharePoint och Azure AD i ett år kan du skapa ytterligare kvarhållningsprinciper för granskningsloggar så att de uppfyller kraven för organisationens säkerhetsåtgärder, IT- och efterlevnadsgrupper.</span><span class="sxs-lookup"><span data-stu-id="5584b-131">In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span> <span data-ttu-id="5584b-132">Mer information finns i [Hantera kvarhållningsprinciper för granskningsloggar](audit-log-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5584b-132">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="step-4-search-for-crucial-events"></a><span data-ttu-id="5584b-133">Steg 4: Sök efter viktiga händelser</span><span class="sxs-lookup"><span data-stu-id="5584b-133">Step 4: Search for crucial events</span></span>

<span data-ttu-id="5584b-134">Nu när du har ställt in Avancerad granskning för din organisation kan du söka efter avgörande händelser och andra aktiviteter när du genomför avgörande undersökningar.</span><span class="sxs-lookup"><span data-stu-id="5584b-134">Now that you have Advanced Audit set up for your organization, you can search for crucial events and other activities when conducting forensic investigations.</span></span> <span data-ttu-id="5584b-135">När du har slutfört steg 1 och steg 2 kan du söka i granskningsloggen efter avgörande händelser och andra aktiviteter under undersökningar av komprometterade konton och andra typer av säkerhets- och efterlevnadsundersökningar.</span><span class="sxs-lookup"><span data-stu-id="5584b-135">After completing Step 1 and Step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span> <span data-ttu-id="5584b-136">Mer information om en undersökning av komprometterade användarkonton genom att använda den viktiga händelsen MailItemsAccessed finns i Använda avancerad granskning för att undersöka [komprometterade konton.](mailitemsaccessed-forensics-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="5584b-136">For more information about conducting a forensics investigation of compromised user accounts by using the MailItemsAccessed crucial event, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>
