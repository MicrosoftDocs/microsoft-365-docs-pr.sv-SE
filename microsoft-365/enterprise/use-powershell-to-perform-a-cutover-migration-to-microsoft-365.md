---
title: Använda PowerShell för att utföra en snabb migrering till Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: Lär dig hur du använder PowerShell för att flytta innehållet från ett käll-e-postsystem på en gång genom att utföra en migrering till Microsoft 365.
ms.openlocfilehash: 6e59ac4d590208e0faed22e94cabe05601b17f18
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581064"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a><span data-ttu-id="68725-103">Använda PowerShell för att utföra en snabb migrering till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="68725-103">Use PowerShell to perform a cutover migration to Microsoft 365</span></span>

<span data-ttu-id="68725-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="68725-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="68725-105">Du kan migrera innehållet i användarpostlådor från ett källsystem för e-post till Microsoft 365 på en gång med hjälp av en cutover-migrering.</span><span class="sxs-lookup"><span data-stu-id="68725-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 all at once by using a cutover migration.</span></span> <span data-ttu-id="68725-106">I den här artikeln får du hjälp med uppgifterna för en e-postmigrering med Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68725-106">This article walks you through the tasks for an email cutover migration by using Exchange Online PowerShell.</span></span>

<span data-ttu-id="68725-107">Genom att gå igenom avsnittet Vad du behöver veta om en snabb e-postmigrering till [Microsoft 365](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)får du en översikt över migreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="68725-107">By reviewing the topic, [What you need to know about a cutover email migration to Microsoft 365](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration), you can get an overview of the migration process.</span></span> <span data-ttu-id="68725-108">När du har bekantat dig med innehållet i den artikeln kan du använda den här för att börja migrera postlådor från ett e-postsystem till ett annat.</span><span class="sxs-lookup"><span data-stu-id="68725-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>

> [!NOTE]
> <span data-ttu-id="68725-109">Du kan också använda Exchange admin center för att utföra en cutover-migrering.</span><span class="sxs-lookup"><span data-stu-id="68725-109">You can also use the Exchange admin center to perform a cutover migration.</span></span> <span data-ttu-id="68725-110">Se [Utföra en cutover-migrering av e-post till Microsoft 365.](/Exchange/mailbox-migration/cutover-migration-to-office-365)</span><span class="sxs-lookup"><span data-stu-id="68725-110">See [Perform a cutover migration of email to Microsoft 365](/Exchange/mailbox-migration/cutover-migration-to-office-365).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="68725-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="68725-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="68725-112">Beräknad tid för att slutföra den här uppgiften: 2–5 minuter för att skapa en migreringsbatch.</span><span class="sxs-lookup"><span data-stu-id="68725-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="68725-113">När migreringsbatchen har startats varierar varaktigheten för migreringen beroende på antalet postlådor i batchen, storleken på varje postlåda och din tillgängliga nätverkskapacitet.</span><span class="sxs-lookup"><span data-stu-id="68725-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="68725-114">Information om andra faktorer som påverkar hur lång tid det tar att migrera postlådor till Microsoft 365 finns i [Migreringsprestanda.](/Exchange/mailbox-migration/office-365-migration-best-practices)</span><span class="sxs-lookup"><span data-stu-id="68725-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).</span></span>

<span data-ttu-id="68725-115">Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna.</span><span class="sxs-lookup"><span data-stu-id="68725-115">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="68725-116">Du kan se vilka behörigheter du behöver i migreringsposten i en tabell i [avsnittet Behörigheter för](/exchange/recipients-permissions-exchange-2013-help) mottagare.</span><span class="sxs-lookup"><span data-stu-id="68725-116">To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.</span></span>

<span data-ttu-id="68725-117">Om du vill använda Exchange Online PowerShell-cmdlets måste du logga in och importera cmdletarna till din lokala Windows PowerShell-session.</span><span class="sxs-lookup"><span data-stu-id="68725-117">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session.</span></span> <span data-ttu-id="68725-118">Instruktioner [finns i Ansluta till Exchange Online med fjärr-PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="68725-118">See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>

<span data-ttu-id="68725-119">En fullständig lista över migreringskommandon finns i [Flytta och migrera cmdlets.](/powershell/exchange/)</span><span class="sxs-lookup"><span data-stu-id="68725-119">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

## <a name="migration-steps"></a><span data-ttu-id="68725-120">Migreringssteg</span><span class="sxs-lookup"><span data-stu-id="68725-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-cutover-migration"></a><span data-ttu-id="68725-121">Steg 1: Förbereda för en cutover-migrering</span><span class="sxs-lookup"><span data-stu-id="68725-121">Step 1: Prepare for a cutover migration</span></span>
<span data-ttu-id="68725-122"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="68725-122"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="68725-123">**Lägg till din lokala Exchange-organisation som en godkänd domän i din Microsoft 365-organisation.**</span><span class="sxs-lookup"><span data-stu-id="68725-123">**Add your on-premises Exchange organization as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="68725-124">Migreringstjänsten använder SMTP-adressen för dina lokala postlådor för att skapa Microsoft Online Services användar-ID och e-postadress för de nya Microsoft 365-postlådorna.</span><span class="sxs-lookup"><span data-stu-id="68725-124">The migration service uses the SMTP address of your on-premises mailboxes to create the Microsoft Online Services user ID and email address for the new Microsoft 365 mailboxes.</span></span> <span data-ttu-id="68725-125">Migreringen misslyckas om din Exchange-domän inte är en godkänd domän eller primär domän i din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="68725-125">Migration will fail if your Exchange domain isn't an accepted domain or the primary domain of your Microsoft 365 organization.</span></span> <span data-ttu-id="68725-126">Mer information finns i [Verifiera din domän.](../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="68725-126">For more information, see [Verify your domain](../admin/setup/add-domain.md).</span></span>

- <span data-ttu-id="68725-127">**Konfigurera Outlook överallt på den lokala Exchange-servern.**</span><span class="sxs-lookup"><span data-stu-id="68725-127">**Configure Outlook Anywhere on your on-premises Exchange server.**</span></span> <span data-ttu-id="68725-128">E-postmigreringstjänsten använder RPC över HTTP, eller Outlook Anywhere, för att ansluta till din lokala Exchange-server.</span><span class="sxs-lookup"><span data-stu-id="68725-128">The email migration service uses RPC over HTTP, or Outlook Anywhere, to connect to your on-premises Exchange server.</span></span> <span data-ttu-id="68725-129">Mer information om hur du konfigurerar Outlook överallt för Exchange 2010, Exchange 2007 och Exchange 2003 finns här:</span><span class="sxs-lookup"><span data-stu-id="68725-129">For information about how to set up Outlook Anywhere for Exchange 2010, Exchange 2007, and Exchange 2003, see the following:</span></span>

  - <span data-ttu-id="68725-130">[Exchange 2010: Aktivera Outlook överallt](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="68725-130">[Exchange 2010: Enable Outlook Anywhere](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))</span></span>

  - <span data-ttu-id="68725-131">[Exchange 2007: Aktivera Outlook överallt](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="68725-131">[Exchange 2007: How to Enable Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))</span></span>

  - <span data-ttu-id="68725-132">[Exchange 2003: Distributionsscenarier för RPC över HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="68725-132">[Exchange 2003: Deployment Scenarios for RPC over HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))</span></span>

  - <span data-ttu-id="68725-133">[Så här konfigurerar du Outlook var som helst med Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="68725-133">[How to Configure Outlook Anywhere with Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="68725-134">Konfigurationen för Outlook Anywhere måste konfigureras med ett certifikat utfärdat av en betrodd certifikatutfärdare (CA).</span><span class="sxs-lookup"><span data-stu-id="68725-134">Your Outlook Anywhere configuration must be configured with a certificate issued by a trusted certification authority (CA).</span></span> <span data-ttu-id="68725-135">Det kan inte konfigureras med ett själv signerat certifikat.</span><span class="sxs-lookup"><span data-stu-id="68725-135">It can't be configured with a self-signed certificate.</span></span> <span data-ttu-id="68725-136">Mer information finns i Konfigurera [SSL för Outlook överallt.](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="68725-136">For more information, see [How to Configure SSL for Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).</span></span>

- <span data-ttu-id="68725-137">**Kontrollera att du kan ansluta till Exchange-organisationen med Outlook överallt.**</span><span class="sxs-lookup"><span data-stu-id="68725-137">**Verify that you can connect to your Exchange organization using Outlook Anywhere.**</span></span> <span data-ttu-id="68725-138">Prova någon av de här metoderna för att testa dina anslutningsinställningar:</span><span class="sxs-lookup"><span data-stu-id="68725-138">Try one of these methods to test your connection settings:</span></span>

  - <span data-ttu-id="68725-139">Använd Microsoft Outlook utanför företagsnätverket för att ansluta till din lokala Exchange-postlåda.</span><span class="sxs-lookup"><span data-stu-id="68725-139">Use Microsoft Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>

  - <span data-ttu-id="68725-140">Använd Microsoft [Analysverktyg för fjärranslutning för](https://www.testexchangeconnectivity.com/) Att testa dina anslutningsinställningar.</span><span class="sxs-lookup"><span data-stu-id="68725-140">Use the Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) to test your connection settings.</span></span> <span data-ttu-id="68725-141">Använd Outlook överallt (RPC över HTTP) eller Outlook Automatisk upptäckt av tester.</span><span class="sxs-lookup"><span data-stu-id="68725-141">Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>

  - <span data-ttu-id="68725-142">Kör följande kommandon i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68725-142">Run the following commands in Exchange Online PowerShell.</span></span>

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- <span data-ttu-id="68725-143">**Tilldela ett lokalt användarkonto nödvändiga behörigheter för åtkomst till postlådor i din Exchange-organisation.**</span><span class="sxs-lookup"><span data-stu-id="68725-143">**Assign an on-premises user account the necessary permissions to access mailboxes in your Exchange organization.**</span></span> <span data-ttu-id="68725-144">Det lokala användarkonto som du använder för att ansluta till den lokala Exchange-organisationen (kallas även migreringsadministratör) måste ha nödvändiga behörigheter för att få åtkomst till de lokala postlådor som du vill migrera till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="68725-144">The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="68725-145">Det här användarkontot används för att skapa en migreringsslutpunkt för den lokala organisationen.</span><span class="sxs-lookup"><span data-stu-id="68725-145">This user account is used to create a migration endpoint to your on-premises organization.</span></span>

    <span data-ttu-id="68725-146">I följande lista visas de administratörsrättigheter som krävs för att migrera postlådor med hjälp av en cutover-migrering.</span><span class="sxs-lookup"><span data-stu-id="68725-146">The following list shows the administrative privileges required to migrate mailboxes using a cutover migration.</span></span> <span data-ttu-id="68725-147">Det finns tre möjliga alternativ.</span><span class="sxs-lookup"><span data-stu-id="68725-147">There are three possible options.</span></span>

  - <span data-ttu-id="68725-148">Migreringsadministratören måste vara medlem i **gruppen Domänadministratörer** i Active Directory i den lokala organisationen.</span><span class="sxs-lookup"><span data-stu-id="68725-148">The migration administrator must be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>

    <span data-ttu-id="68725-149">Eller</span><span class="sxs-lookup"><span data-stu-id="68725-149">Or</span></span>

  - <span data-ttu-id="68725-150">Migreringsadministratören måste ha **FullAccess** -behörighet för var och en av de lokala postlådorna.</span><span class="sxs-lookup"><span data-stu-id="68725-150">The migration administrator must be assigned the **FullAccess** permission for each on-premises mailbox.</span></span>

    <span data-ttu-id="68725-151">Eller</span><span class="sxs-lookup"><span data-stu-id="68725-151">Or</span></span>

  - <span data-ttu-id="68725-152">Migreringsadministratören måste ha **Receive As-behörighet** till den lokala postlådedatabas där användarnas postlådor lagras.</span><span class="sxs-lookup"><span data-stu-id="68725-152">The migration administrator must be assigned the **Receive As** permission on the on-premises mailbox database that stores the user mailboxes.</span></span>

- <span data-ttu-id="68725-153">**Inaktivera Unified Messaging.**</span><span class="sxs-lookup"><span data-stu-id="68725-153">**Disable Unified Messaging.**</span></span> <span data-ttu-id="68725-154">Om de lokala postlådor du migrerar har aktiverats för Unified Messaging (UM) måste du inaktivera UM för postlådorna innan du migrerar dem.</span><span class="sxs-lookup"><span data-stu-id="68725-154">If the on-premises mailboxes you're migrating are enabled for Unified Messaging (UM), you have to disable UM on the mailboxes before you migrate them.</span></span> <span data-ttu-id="68725-155">Du kan sedan aktivera UM för postlådorna när migreringen är klar.</span><span class="sxs-lookup"><span data-stu-id="68725-155">You can then enable UM on the mailboxes after the migration is complete.</span></span>

- <span data-ttu-id="68725-156">**Säkerhetsgrupper och ombud** E-postmigreringstjänsten kan inte identifiera om lokala Active Directory-grupper är säkerhetsgrupper eller inte. Därför kan den inte tillhandahålla några migrerade grupper som säkerhetsgrupper i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="68725-156">**Security Groups and Delegates** The email migration service cannot detect whether on-premises Active Directory groups are security groups or not, so it cannot provision any migrated groups as security groups in Microsoft 365.</span></span> <span data-ttu-id="68725-157">Om du vill ha säkerhetsgrupper i Microsoft 365-klienten måste du först tillhandahålla en tom e-postaktiverad säkerhetsgrupp i Microsoft 365-klientorganisationen innan du påbörjar migreringen.</span><span class="sxs-lookup"><span data-stu-id="68725-157">If you want to have security groups in your Microsoft 365 tenant, you must first provision an empty mail-enabled security group in your Microsoft 365 tenant before starting the cutover migration.</span></span> <span data-ttu-id="68725-158">Med den här migreringsmetoden flyttas dessutom bara postlådor, e-postanvändare, e-postkontakter och e-postgrupper.</span><span class="sxs-lookup"><span data-stu-id="68725-158">Additionally, this migration method only moves mailboxes, mail users, mail contacts, and mail-enabled groups.</span></span> <span data-ttu-id="68725-159">Om något annat Active Directory-objekt, till exempel en användare som inte har migrerats till Microsoft 365, tilldelas som chef eller ombud till ett objekt som migreras måste de tas bort från objektet innan du migrerar.</span><span class="sxs-lookup"><span data-stu-id="68725-159">If any other Active Directory object, such as user that is not migrated to Microsoft 365, is assigned as a manager or delegate to an object being migrated, they must be removed from the object before you migrate.</span></span>

### <a name="step-2-create-a-migration-endpoint"></a><span data-ttu-id="68725-160">Steg 2: Skapa en migreringsslutpunkt</span><span class="sxs-lookup"><span data-stu-id="68725-160">Step 2: Create a migration endpoint</span></span>
<span data-ttu-id="68725-161"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="68725-161"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="68725-162">För att e-post ska migreras måste Microsoft 365 ansluta till och kommunicera med käll-e-postsystemet.</span><span class="sxs-lookup"><span data-stu-id="68725-162">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="68725-163">För att göra det använder Microsoft 365 en migreringsslutpunkt.</span><span class="sxs-lookup"><span data-stu-id="68725-163">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="68725-164">Om du vill skapa en migreringsslutpunkt för Outlook Överallt för en migrering i Outlook ska [du först ansluta till Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="68725-164">To create an Outlook Anywhere migration endpoint for cutover migration, first [connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="68725-165">En fullständig lista över migreringskommandon finns i [Flytta och migrera cmdlets.](/powershell/exchange/)</span><span class="sxs-lookup"><span data-stu-id="68725-165">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

<span data-ttu-id="68725-166">Kör följande kommandon i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68725-166">Run the following commands in Exchange Online PowerShell:</span></span>

```powershell
$Credentials = Get-Credential
```

<span data-ttu-id="68725-167">I exemplet används cmdleten [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) för att hämta och testa anslutningsinställningarna till den lokala Exchange-servern, och sedan används dessa anslutningsinställningar för att skapa migreringsslutpunkten med namnet "CutoverEndpoint".</span><span class="sxs-lookup"><span data-stu-id="68725-167">The example uses the [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) cmdlet to obtain and test the connection settings to the on-premises Exchange server, and then uses those connection settings to create the migration endpoint called "CutoverEndpoint".</span></span>

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> <span data-ttu-id="68725-168">Cmdleten **New-MigrationEndpoint** kan användas för att ange en databas för tjänsten som ska användas med **alternativet -TargetDatabase.**</span><span class="sxs-lookup"><span data-stu-id="68725-168">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option.</span></span> <span data-ttu-id="68725-169">Annars tilldelas en databas slumpmässigt från AD FS 2.0-webbplatsen (Active Directory Federation Services) där hanteringspostlådan finns.</span><span class="sxs-lookup"><span data-stu-id="68725-169">Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>

#### <a name="verify-it-worked"></a><span data-ttu-id="68725-170">Kontrollera att det fungerade</span><span class="sxs-lookup"><span data-stu-id="68725-170">Verify it worked</span></span>

<span data-ttu-id="68725-171">Kör följande kommando i Exchange Online PowerShell för att visa information om migreringsslutpunkten "CutoverEndpoint":</span><span class="sxs-lookup"><span data-stu-id="68725-171">In Exchange Online PowerShell, run the following command to display information about the "CutoverEndpoint" migration endpoint:</span></span>

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a><span data-ttu-id="68725-172">Steg 3: Skapa snabbmigreringsbatch</span><span class="sxs-lookup"><span data-stu-id="68725-172">Step 3: Create the cutover migration batch</span></span>
<span data-ttu-id="68725-173"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="68725-173"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="68725-174">Du kan använda cmdleten **New-MigrationBatch** i Exchange Online PowerShell för att skapa en migreringsbatch för en migreringsbatch.</span><span class="sxs-lookup"><span data-stu-id="68725-174">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration.</span></span> <span data-ttu-id="68725-175">Du kan skapa en migreringsbatch och starta den automatiskt genom att ta med _parametern AutoStart._</span><span class="sxs-lookup"><span data-stu-id="68725-175">You can create a migration batch and start it automatically by including the _AutoStart_ parameter.</span></span> <span data-ttu-id="68725-176">Alternativt kan du skapa migreringsbatchen och sedan starta den manuellt efteråt med hjälp av cmdleten **Start-MigrationBatch.**</span><span class="sxs-lookup"><span data-stu-id="68725-176">Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet.</span></span> <span data-ttu-id="68725-177">Det här exemplet skapar en migreringsbatch med namnet "CutoverBatch" och använder migreringsslutpunkten som skapades i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="68725-177">This example creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

<span data-ttu-id="68725-178">Det här exemplet skapar också en migreringsbatch med namnet "CutoverBatch" och använder migreringsslutpunkten som skapades i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="68725-178">This example also creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.</span></span> <span data-ttu-id="68725-179">Eftersom _parametern AutoStart_ inte ingår måste migreringsbatchen startas manuellt på instrumentpanelen för migrering eller med hjälp av **cmdleten Start-MigrationBatch.**</span><span class="sxs-lookup"><span data-stu-id="68725-179">Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet.</span></span> <span data-ttu-id="68725-180">Som tidigare nämnts kan bara en batch för migreringsmigrering finnas i taget.</span><span class="sxs-lookup"><span data-stu-id="68725-180">As previously stated, only one cutover migration batch can exist at a time.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="68725-181">Kontrollera att det fungerade</span><span class="sxs-lookup"><span data-stu-id="68725-181">Verify it worked</span></span>

<span data-ttu-id="68725-182">Kontrollera att du har skapat en migreringsbatch för en migreringsbatch genom att köra följande kommando i Exchange Online PowerShell för att visa information om den nya migreringsbatchen:</span><span class="sxs-lookup"><span data-stu-id="68725-182">To verify that you've successfully created a migration batch for a cutover migration, run the following command in Exchange Online PowerShell to display information about the new migration batch:</span></span>

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a><span data-ttu-id="68725-183">Steg 4: Starta snabbmigreringsbatchen</span><span class="sxs-lookup"><span data-stu-id="68725-183">Step 4: Start the cutover migration batch</span></span>
<span data-ttu-id="68725-184"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="68725-184"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="68725-185">Starta migreringsbatchen i Exchange Online PowerShell genom att köra följande kommando.</span><span class="sxs-lookup"><span data-stu-id="68725-185">To start the migration batch in Exchange Online PowerShell, run the following command.</span></span> <span data-ttu-id="68725-186">Det här skapar en migreringsbatch med namnet "CutoverBatch".</span><span class="sxs-lookup"><span data-stu-id="68725-186">This will create a migration batch called "CutoverBatch".</span></span>

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a><span data-ttu-id="68725-187">Kontrollera att det fungerade</span><span class="sxs-lookup"><span data-stu-id="68725-187">Verify it worked</span></span>

<span data-ttu-id="68725-188">Om en migreringsbatch har startats anges dess status på instrumentpanelen för migrering som Synkroniserar.</span><span class="sxs-lookup"><span data-stu-id="68725-188">If a migration batch is successfully started, its status on the migration dashboard is specified as Syncing.</span></span> <span data-ttu-id="68725-189">Kör följande kommando för att verifiera att du har startat en migreringsbatch med Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68725-189">To verify that you've successfully started a migration batch using Exchange Online PowerShell, run the following command:</span></span>

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="68725-190">Steg 5: Dirigera din e-post till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="68725-190">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="68725-191"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="68725-191"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="68725-192">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span><span class="sxs-lookup"><span data-stu-id="68725-192">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="68725-193">Under e-postmigreringsprocessen pekade MX-posten på ditt käll-e-postsystem.</span><span class="sxs-lookup"><span data-stu-id="68725-193">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="68725-194">Nu när e-postmigrering till Microsoft 365 är klar är det dags att peka MX-posten på Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="68725-194">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="68725-195">Då ser du till att e-posten levereras till dina Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="68725-195">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="68725-196">Genom att flytta MX-posten kan du också stänga av ditt gamla e-postsystem när du är redo.</span><span class="sxs-lookup"><span data-stu-id="68725-196">By moving the MX record, you can also you turn off your old email system when you're ready.</span></span>

<span data-ttu-id="68725-197">För många DNS-leverantörer finns det särskilda anvisningar för hur du ändrar MX-posten.</span><span class="sxs-lookup"><span data-stu-id="68725-197">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="68725-198">Om din DNS-värd inte finns med eller om du bara allmänt vill se hur anvisningarna ser ut, finns det även [allmänna anvisningar för MX-posten](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx).</span><span class="sxs-lookup"><span data-stu-id="68725-198">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx) are provided as well.</span></span>

<span data-ttu-id="68725-199">Det kan ta upp till 72 timmar för kunders och partners e-postsystem att se den ändrade MX-posten.</span><span class="sxs-lookup"><span data-stu-id="68725-199">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record.</span></span> <span data-ttu-id="68725-200">Vänta i minst 72 timmar innan du går vidare till nästa uppgift: [Steg 6: Ta bort batchen för cutover-migrering.](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6)</span><span class="sxs-lookup"><span data-stu-id="68725-200">Wait at least 72 hours before you proceed to the next task: [Step 6: Delete the cutover migration batch](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span></span>

### <a name="step-6-delete-the-cutover-migration-batch"></a><span data-ttu-id="68725-201">Steg 6: Ta bort snabbmigreringsbatchen</span><span class="sxs-lookup"><span data-stu-id="68725-201">Step 6: Delete the cutover migration batch</span></span>
<span data-ttu-id="68725-202"><a name="Bk_step6"> </a></span><span class="sxs-lookup"><span data-stu-id="68725-202"><a name="Bk_step6"> </a></span></span>

<span data-ttu-id="68725-203">När du har ändrat MX-posten och verifierat att all e-post dirigeras till postlådor i Microsoft 365 informerar du användarna om att deras e-post kommer till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="68725-203">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="68725-204">Därefter kan du ta bort batchen för cutover-migrering.</span><span class="sxs-lookup"><span data-stu-id="68725-204">After this, you can delete the cutover migration batch.</span></span> <span data-ttu-id="68725-205">Kontrollera följande innan du tar bort migreringsbatchen.</span><span class="sxs-lookup"><span data-stu-id="68725-205">Verify the following before you delete the migration batch.</span></span>

- <span data-ttu-id="68725-206">Alla användare använder Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="68725-206">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="68725-207">När batchen har tagits bort kopieras inte e-post som skickas till postlådorna på den lokala Exchange Server till motsvarande Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="68725-207">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>

- <span data-ttu-id="68725-208">Microsoft 365-postlådor synkroniserades minst en gång efter att e-posten började skickas direkt till dem.</span><span class="sxs-lookup"><span data-stu-id="68725-208">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="68725-209">Det gör du genom att kontrollera att värdet i rutan Senaste synkronisering är senare än när e-posten började dirigeras direkt till Microsoft 365-postlådorna.</span><span class="sxs-lookup"><span data-stu-id="68725-209">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="68725-210">Om du vill ta bort migreringsbatchen "CutoverBatch" i Exchange Online PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="68725-210">To delete the "CutoverBatch" migration batch in Exchange Online PowerShell, run the following command:</span></span>

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a><span data-ttu-id="68725-211">Avsnitt 7: Tilldela användarlicenser</span><span class="sxs-lookup"><span data-stu-id="68725-211">Section 7: Assign user licenses</span></span>
<span data-ttu-id="68725-212"><a name="BK_Step7"> </a></span><span class="sxs-lookup"><span data-stu-id="68725-212"><a name="BK_Step7"> </a></span></span>

 <span data-ttu-id="68725-213">**Aktivera Microsoft 365-användarkonton för de migrerade kontona genom att tilldela licenser.**</span><span class="sxs-lookup"><span data-stu-id="68725-213">**Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.**</span></span> <span data-ttu-id="68725-214">Om du inte tilldelar en licens inaktiveras postlådan när tidsfristen löper ut (30 dagar).</span><span class="sxs-lookup"><span data-stu-id="68725-214">If you don't assign a license, the mailbox is disabled when the grace period ends (30 days).</span></span> <span data-ttu-id="68725-215">Information om hur du tilldelar en licens i administrationscentret för Microsoft 365 finns i [Tilldela eller ta bort licenser.](../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="68725-215">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](../admin/manage/assign-licenses-to-users.md).</span></span>

### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="68725-216">Steg 8: Slutför uppgifter efter migreringen</span><span class="sxs-lookup"><span data-stu-id="68725-216">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="68725-217"><a name="BK_Step8"> </a></span><span class="sxs-lookup"><span data-stu-id="68725-217"><a name="BK_Step8"> </a></span></span>

- <span data-ttu-id="68725-218">**Skapa en DNS-post för automatisk upptäckt så att användarna enkelt kan komma till sina postlådor.**</span><span class="sxs-lookup"><span data-stu-id="68725-218">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="68725-219">När alla lokala postlådor har migrerats till Microsoft 365 kan du konfigurera en DNS-post för automatisk upptäckt för Microsoft 365-organisationen så att användare enkelt kan ansluta till sina nya Microsoft 365-postlådor med Outlook och mobila klienter.</span><span class="sxs-lookup"><span data-stu-id="68725-219">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="68725-220">Den nya DNS-posten för automatisk upptäckt måste använda samma namnområde som du använder för Microsoft 365-organisationen.</span><span class="sxs-lookup"><span data-stu-id="68725-220">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="68725-221">Om ditt molnbaserade namnområde till exempel är cloud.contoso.com, behöver du skapa DNS-posten autodiscover.cloud.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="68725-221">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>

    <span data-ttu-id="68725-222">Om du behåller Exchange Server bör du också se till att automatisk upptäckt av DNS CNAME-posten pekar på Microsoft 365 i både intern och extern DNS efter migreringen så att Outlook-klienten kan ansluta till rätt postlåda.</span><span class="sxs-lookup"><span data-stu-id="68725-222">If you keep your Exchange Server, you should also make sure that Autodiscover DNS CNAME record has to point to Microsoft 365 in both internal and external DNS after the migration so that the Outlook client will to connect to the correct mailbox.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="68725-223">I Exchange 2007, Exchange 2010 och Exchange 2013 bör du också ange `Set-ClientAccessServer AutodiscoverInternalConnectionURI` `Null` .</span><span class="sxs-lookup"><span data-stu-id="68725-223">In Exchange 2007, Exchange 2010, and Exchange 2013 you should also set `Set-ClientAccessServer AutodiscoverInternalConnectionURI` to `Null`.</span></span>

    <span data-ttu-id="68725-224">Microsoft 365 använder en CNAME-post för att implementera tjänsten för automatisk upptäckt för Outlook och mobila klienter.</span><span class="sxs-lookup"><span data-stu-id="68725-224">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="68725-225">CNAME-posten för automatisk upptäckt måste innehålla följande information:</span><span class="sxs-lookup"><span data-stu-id="68725-225">The Autodiscover CNAME record must contain the following information:</span></span>

  - <span data-ttu-id="68725-226">**Alias:** autodiscover</span><span class="sxs-lookup"><span data-stu-id="68725-226">**Alias:** autodiscover</span></span>

  - <span data-ttu-id="68725-227">**Target:** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="68725-227">**Target:** autodiscover.outlook.com</span></span>

    <span data-ttu-id="68725-228">Mer information finns i Lägga [till DNS-poster för att ansluta din domän.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="68725-228">For more information, see [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

- <span data-ttu-id="68725-229">**Inaktivera lokala Exchange-servrar.**</span><span class="sxs-lookup"><span data-stu-id="68725-229">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="68725-230">När du har kontrollerat att all e-post dirigeras direkt till Microsoft 365-postlådorna och du inte längre behöver underhålla din lokala e-postorganisation eller inte planerar att implementera enkel inloggning (SSO), kan du avinstallera Exchange från dina servrar och ta bort din lokala Exchange-organisation.</span><span class="sxs-lookup"><span data-stu-id="68725-230">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing a single sign-on (SSO) solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>

    <span data-ttu-id="68725-231">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="68725-231">For more information, see the following:</span></span>

  - <span data-ttu-id="68725-232">[Ändra eller ta bort Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="68725-232">[Modify or Remove Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))</span></span>

  - <span data-ttu-id="68725-233">[Ta bort en Exchange 2007-organisation](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="68725-233">[How to Remove an Exchange 2007 Organization](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))</span></span>

  - <span data-ttu-id="68725-234">[Avinstallera Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="68725-234">[How to Uninstall Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))</span></span>