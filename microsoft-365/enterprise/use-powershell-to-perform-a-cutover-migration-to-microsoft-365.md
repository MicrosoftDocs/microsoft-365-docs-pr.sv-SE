---
title: Använda PowerShell för att utföra en snabb migrering till Microsoft 365
ms.author: sirkkuw
author: sirkkuw
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
description: Lär dig hur du använder PowerShell för att flytta innehållet från ett käll-e-postsystem samtidigt genom att utföra en snabbmigrering migrering till Microsoft 365.
ms.openlocfilehash: 74e7791c4292598e4717e56af25e39b3c8208108
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948202"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a><span data-ttu-id="98618-103">Använda PowerShell för att utföra en snabb migrering till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="98618-103">Use PowerShell to perform a cutover migration to Microsoft 365</span></span>

<span data-ttu-id="98618-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="98618-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="98618-105">Du kan migrera innehållet i användar post lådor från ett käll-e-postsystem till Microsoft 365 alla samtidigt genom att använda en snabbmigrering-migrering.</span><span class="sxs-lookup"><span data-stu-id="98618-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 all at once by using a cutover migration.</span></span> <span data-ttu-id="98618-106">I den här artikeln får du stegvisa instruktioner för en e-snabbmigrering migrering genom att använda Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98618-106">This article walks you through the tasks for an email cutover migration by using Exchange Online PowerShell.</span></span>

<span data-ttu-id="98618-107">Genom att granska avsnittet, [vad du behöver veta om en snabbmigrering-migrering till Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536688), kan du få en översikt över migreringen.</span><span class="sxs-lookup"><span data-stu-id="98618-107">By reviewing the topic, [What you need to know about a cutover email migration to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536688), you can get an overview of the migration process.</span></span> <span data-ttu-id="98618-108">När du har bekantat dig med innehållet i den artikeln kan du använda den här för att börja migrera postlådor från ett e-postsystem till ett annat.</span><span class="sxs-lookup"><span data-stu-id="98618-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>

> [!NOTE]
> <span data-ttu-id="98618-109">Du kan också använda administrations centret för Exchange för att utföra en snabbmigrering migrering.</span><span class="sxs-lookup"><span data-stu-id="98618-109">You can also use the Exchange admin center to perform a cutover migration.</span></span> <span data-ttu-id="98618-110">Se [utföra en snabbmigrering migrering av e-post till Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536689).</span><span class="sxs-lookup"><span data-stu-id="98618-110">See [Perform a cutover migration of email to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536689).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="98618-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="98618-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="98618-112">Uppskattad tid för att slutföra den här uppgiften: 2-5 minuter för att skapa en migreringstabell.</span><span class="sxs-lookup"><span data-stu-id="98618-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="98618-113">När migreringen har startat varierar varaktigheten för migreringen baserat på antalet post lådor i gruppen, storleken på varje post låda och din tillgängliga nätverks kapacitet.</span><span class="sxs-lookup"><span data-stu-id="98618-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="98618-114">Information om andra faktorer som påverkar hur lång tid det tar att migrera post lådor till Microsoft 365 finns i [migreringens prestanda](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span><span class="sxs-lookup"><span data-stu-id="98618-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span></span>

<span data-ttu-id="98618-115">Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna.</span><span class="sxs-lookup"><span data-stu-id="98618-115">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="98618-116">Om du vill se vilka behörigheter du behöver läser du "migration"-posten i en tabell i avsnittet [mottagare](https://go.microsoft.com/fwlink/p/?LinkId=534105) .</span><span class="sxs-lookup"><span data-stu-id="98618-116">To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](https://go.microsoft.com/fwlink/p/?LinkId=534105) topic.</span></span>

<span data-ttu-id="98618-117">För att använda PowerShell-cmdletar för Exchange Online måste du logga in och importera cmdletarna till din lokala Windows PowerShell-session.</span><span class="sxs-lookup"><span data-stu-id="98618-117">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session.</span></span> <span data-ttu-id="98618-118">Se [ansluta till Exchange Online med Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) för instruktioner.</span><span class="sxs-lookup"><span data-stu-id="98618-118">See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>

<span data-ttu-id="98618-119">En fullständig lista över migreringsåtgärder finns i avsnittet [flytta och migrera cmdletar](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="98618-119">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>

## <a name="migration-steps"></a><span data-ttu-id="98618-120">Migreringsåtgärder</span><span class="sxs-lookup"><span data-stu-id="98618-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-cutover-migration"></a><span data-ttu-id="98618-121">Steg 1: förbereda en snabbmigrering migrering</span><span class="sxs-lookup"><span data-stu-id="98618-121">Step 1: Prepare for a cutover migration</span></span>
<span data-ttu-id="98618-122"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="98618-122"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="98618-123">**Lägg till din lokala Exchange-organisation som en godkänd domän i din Microsoft 365-organisation.**</span><span class="sxs-lookup"><span data-stu-id="98618-123">**Add your on-premises Exchange organization as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="98618-124">Migreringstjänster använder SMTP-adressen för dina lokala post lådor för att skapa användar-ID för Microsoft Online Services och e-postadress för de nya Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="98618-124">The migration service uses the SMTP address of your on-premises mailboxes to create the Microsoft Online Services user ID and email address for the new Microsoft 365 mailboxes.</span></span> <span data-ttu-id="98618-125">Migreringen Miss lyckas om din Exchange-domän inte är en godkänd domän eller din Microsoft 365-organisations primära domän.</span><span class="sxs-lookup"><span data-stu-id="98618-125">Migration will fail if your Exchange domain isn't an accepted domain or the primary domain of your Microsoft 365 organization.</span></span> <span data-ttu-id="98618-126">Mer information finns i [Verifiera din domän](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span><span class="sxs-lookup"><span data-stu-id="98618-126">For more information, see [Verify your domain](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span></span>

- <span data-ttu-id="98618-127">**Konfigurera Outlook överallt på din lokala Exchange-Server.**</span><span class="sxs-lookup"><span data-stu-id="98618-127">**Configure Outlook Anywhere on your on-premises Exchange server.**</span></span> <span data-ttu-id="98618-128">Tjänsten för e-postmigrering använder RPC via HTTP eller Outlook överallt för att ansluta till din lokala Exchange-Server.</span><span class="sxs-lookup"><span data-stu-id="98618-128">The email migration service uses RPC over HTTP, or Outlook Anywhere, to connect to your on-premises Exchange server.</span></span> <span data-ttu-id="98618-129">Mer information om hur du konfigurerar Outlook överallt för Exchange 2010, Exchange 2007 och Exchange 2003 finns här:</span><span class="sxs-lookup"><span data-stu-id="98618-129">For information about how to set up Outlook Anywhere for Exchange 2010, Exchange 2007, and Exchange 2003, see the following:</span></span>

  - [<span data-ttu-id="98618-130">Exchange 2010: Aktivera Outlook överallt</span><span class="sxs-lookup"><span data-stu-id="98618-130">Exchange 2010: Enable Outlook Anywhere</span></span>](https://go.microsoft.com/fwlink/?LinkID=187249)

  - [<span data-ttu-id="98618-131">Exchange 2007: Aktivera Outlook överallt</span><span class="sxs-lookup"><span data-stu-id="98618-131">Exchange 2007: How to Enable Outlook Anywhere</span></span>](https://go.microsoft.com/fwlink/?LinkID=167210)

  - [<span data-ttu-id="98618-132">Exchange 2003: distributions scenarier för RPC via HTTP</span><span class="sxs-lookup"><span data-stu-id="98618-132">Exchange 2003: Deployment Scenarios for RPC over HTTP</span></span>](https://go.microsoft.com/fwlink/?LinkID=73657)

  - [<span data-ttu-id="98618-133">Konfigurera Outlook överallt med Exchange 2003</span><span class="sxs-lookup"><span data-stu-id="98618-133">How to Configure Outlook Anywhere with Exchange 2003</span></span>](https://go.microsoft.com/fwlink/?LinkID=167209)

    > [!IMPORTANT]
    > <span data-ttu-id="98618-134">Din Outlook Anywhere-konfiguration måste konfigureras med ett certifikat utfärdat av en betrodd certifikat utfärdare (CA).</span><span class="sxs-lookup"><span data-stu-id="98618-134">Your Outlook Anywhere configuration must be configured with a certificate issued by a trusted certification authority (CA).</span></span> <span data-ttu-id="98618-135">Den kan inte konfigureras med ett självsignerat certifikat.</span><span class="sxs-lookup"><span data-stu-id="98618-135">It can't be configured with a self-signed certificate.</span></span> <span data-ttu-id="98618-136">Mer information finns i [så här konfigurerar du SSL för Outlook överallt](https://go.microsoft.com/fwlink/?LinkID=80875).</span><span class="sxs-lookup"><span data-stu-id="98618-136">For more information, see [How to Configure SSL for Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=80875).</span></span>

- <span data-ttu-id="98618-137">**Kontrol lera att du kan ansluta till Exchange-organisationen med hjälp av Outlook överallt.**</span><span class="sxs-lookup"><span data-stu-id="98618-137">**Verify that you can connect to your Exchange organization using Outlook Anywhere.**</span></span> <span data-ttu-id="98618-138">Prova med någon av följande metoder för att testa dina anslutnings inställningar:</span><span class="sxs-lookup"><span data-stu-id="98618-138">Try one of these methods to test your connection settings:</span></span>

  - <span data-ttu-id="98618-139">Använd Microsoft Outlook utanför företagets nätverk för att ansluta till den lokala Exchange-postlådan.</span><span class="sxs-lookup"><span data-stu-id="98618-139">Use Microsoft Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>

  - <span data-ttu-id="98618-140">Använd Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) för att testa dina anslutnings inställningar.</span><span class="sxs-lookup"><span data-stu-id="98618-140">Use the Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) to test your connection settings.</span></span> <span data-ttu-id="98618-141">Använd Outlook överallt (RPC över HTTP) eller Outlook Automatisk upptäckt av tester.</span><span class="sxs-lookup"><span data-stu-id="98618-141">Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>

  - <span data-ttu-id="98618-142">Kör följande kommandon i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98618-142">Run the following commands in Exchange Online PowerShell.</span></span>

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- <span data-ttu-id="98618-143">**Tilldela ett lokalt användar konto de behörigheter som krävs för att komma åt post lådor i din Exchange-organisation.**</span><span class="sxs-lookup"><span data-stu-id="98618-143">**Assign an on-premises user account the necessary permissions to access mailboxes in your Exchange organization.**</span></span> <span data-ttu-id="98618-144">Det lokala användar kontot som du använder för att ansluta till den lokala Exchange-organisationen (kallas även för administratör för migrering) måste ha nödvändig behörighet för att få åtkomst till de lokala post lådorna som du vill migrera till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="98618-144">The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="98618-145">Detta användar konto används för att skapa en slut punkt för migrering till din lokala organisation.</span><span class="sxs-lookup"><span data-stu-id="98618-145">This user account is used to create a migration endpoint to your on-premises organization.</span></span>

    <span data-ttu-id="98618-146">Följande lista visar de administratörs behörigheter som krävs för att migrera post lådor med en snabbmigrering-migrering.</span><span class="sxs-lookup"><span data-stu-id="98618-146">The following list shows the administrative privileges required to migrate mailboxes using a cutover migration.</span></span> <span data-ttu-id="98618-147">Det finns tre möjliga alternativ.</span><span class="sxs-lookup"><span data-stu-id="98618-147">There are three possible options.</span></span>

  - <span data-ttu-id="98618-148">Uppgraderingen måste vara medlem i gruppen **Domain admins** i Active Directory i den lokala organisationen.</span><span class="sxs-lookup"><span data-stu-id="98618-148">The migration administrator must be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>

    <span data-ttu-id="98618-149">Eller</span><span class="sxs-lookup"><span data-stu-id="98618-149">Or</span></span>

  - <span data-ttu-id="98618-150">Migreringsadministratören måste ha **FullAccess** -behörighet för var och en av de lokala postlådorna.</span><span class="sxs-lookup"><span data-stu-id="98618-150">The migration administrator must be assigned the **FullAccess** permission for each on-premises mailbox.</span></span>

    <span data-ttu-id="98618-151">Eller</span><span class="sxs-lookup"><span data-stu-id="98618-151">Or</span></span>

  - <span data-ttu-id="98618-152">Överflyttnings administratören måste ha behörigheten **Receive As** för den lokala post lådan som lagrar användar post lådorna.</span><span class="sxs-lookup"><span data-stu-id="98618-152">The migration administrator must be assigned the **Receive As** permission on the on-premises mailbox database that stores the user mailboxes.</span></span>

- <span data-ttu-id="98618-153">**Inaktivera Unified Messaging.**</span><span class="sxs-lookup"><span data-stu-id="98618-153">**Disable Unified Messaging.**</span></span> <span data-ttu-id="98618-154">Om de lokala post lådorna som du migrerar är aktiverade för Unified Messaging (UM) måste du inaktivera UM på post lådorna innan du migrerar dem.</span><span class="sxs-lookup"><span data-stu-id="98618-154">If the on-premises mailboxes you're migrating are enabled for Unified Messaging (UM), you have to disable UM on the mailboxes before you migrate them.</span></span> <span data-ttu-id="98618-155">Du kan sedan aktivera UM på post lådorna efter migreringen.</span><span class="sxs-lookup"><span data-stu-id="98618-155">You can then enable UM on the mailboxes after the migration is complete.</span></span>

- <span data-ttu-id="98618-156">**Säkerhets grupper och ombud** Tjänsten för e-postmigrering kan inte identifiera om lokala Active Directory-grupper är säkerhets grupper eller inte, så den kan inte etablera migrerade grupper som säkerhets grupper i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="98618-156">**Security Groups and Delegates** The email migration service cannot detect whether on-premises Active Directory groups are security groups or not, so it cannot provision any migrated groups as security groups in Microsoft 365.</span></span> <span data-ttu-id="98618-157">Om du vill ha säkerhets grupper i din Microsoft 365-klient organisation måste du först etablera en tom e-postaktiverad säkerhets grupp i din Microsoft 365-klient organisation innan du kan starta snabbmigrering-migreringen.</span><span class="sxs-lookup"><span data-stu-id="98618-157">If you want to have security groups in your Microsoft 365 tenant, you must first provision an empty mail-enabled security group in your Microsoft 365 tenant before starting the cutover migration.</span></span> <span data-ttu-id="98618-158">Dessutom flyttas den här metoden endast för post lådor, e-postsamt e-postkontakter och e-postaktiverade grupper.</span><span class="sxs-lookup"><span data-stu-id="98618-158">Additionally, this migration method only moves mailboxes, mail users, mail contacts, and mail-enabled groups.</span></span> <span data-ttu-id="98618-159">Om ett annat Active Directory-objekt, till exempel användare som inte migreras till Microsoft 365, tilldelas som chef eller ombud för ett objekt som migreras, måste de tas bort från objektet innan du migrerar.</span><span class="sxs-lookup"><span data-stu-id="98618-159">If any other Active Directory object, such as user that is not migrated to Microsoft 365, is assigned as a manager or delegate to an object being migrated, they must be removed from the object before you migrate.</span></span>

### <a name="step-2-create-a-migration-endpoint"></a><span data-ttu-id="98618-160">Steg 2: skapa en slut punkt för migrering</span><span class="sxs-lookup"><span data-stu-id="98618-160">Step 2: Create a migration endpoint</span></span>
<span data-ttu-id="98618-161"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="98618-161"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="98618-162">För att migrera e-post måste Microsoft 365 ansluta och kommunicera med käll-e-postsystemet.</span><span class="sxs-lookup"><span data-stu-id="98618-162">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="98618-163">För att göra det, använder Microsoft 365 en slut punkt för migrering.</span><span class="sxs-lookup"><span data-stu-id="98618-163">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="98618-164">Om du vill skapa en migrerings slut punkt för Outlook för snabbmigrering migration [ansluter du först till Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span><span class="sxs-lookup"><span data-stu-id="98618-164">To create an Outlook Anywhere migration endpoint for cutover migration, first [connect to Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span></span>

<span data-ttu-id="98618-165">En fullständig lista över migreringsåtgärder finns i avsnittet [flytta och migrera cmdletar](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="98618-165">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>

<span data-ttu-id="98618-166">Kör följande kommandon i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="98618-166">Run the following commands in Exchange Online PowerShell:</span></span>

```powershell
$Credentials = Get-Credential
```

<span data-ttu-id="98618-167">I exemplet används cmdleten [test-MigrationServerAvailability](https://go.microsoft.com/fwlink/p/?LinkId=534752) för att hämta och testa anslutnings inställningarna till den lokala Exchange-servern, och sedan används dessa anslutnings inställningar för att skapa migrerings slut punkten med namnet "CutoverEndpoint".</span><span class="sxs-lookup"><span data-stu-id="98618-167">The example uses the [Test-MigrationServerAvailability](https://go.microsoft.com/fwlink/p/?LinkId=534752) cmdlet to obtain and test the connection settings to the on-premises Exchange server, and then uses those connection settings to create the migration endpoint called "CutoverEndpoint".</span></span>

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> <span data-ttu-id="98618-168">Cmdleten **New-MigrationEndpoint** kan användas för att ange en databas som ska användas med alternativet **-TargetDatabase** .</span><span class="sxs-lookup"><span data-stu-id="98618-168">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option.</span></span> <span data-ttu-id="98618-169">I annat fall tilldelas en databas slumpmässigt från AD FS-2,0 (Active Directory Federation Services) där hanterings post lådan finns.</span><span class="sxs-lookup"><span data-stu-id="98618-169">Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>

#### <a name="verify-it-worked"></a><span data-ttu-id="98618-170">Verifiera att den fungerade</span><span class="sxs-lookup"><span data-stu-id="98618-170">Verify it worked</span></span>

<span data-ttu-id="98618-171">I Exchange Online PowerShell kör du följande kommando för att visa information om "CutoverEndpoint"-slut punkt för migrering:</span><span class="sxs-lookup"><span data-stu-id="98618-171">In Exchange Online PowerShell, run the following command to display information about the "CutoverEndpoint" migration endpoint:</span></span>

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a><span data-ttu-id="98618-172">Steg 3: Skapa snabbmigreringsbatch</span><span class="sxs-lookup"><span data-stu-id="98618-172">Step 3: Create the cutover migration batch</span></span>
<span data-ttu-id="98618-173"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="98618-173"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="98618-174">Du kan använda cmdleten **New-MigrationBatch** i Exchange Online PowerShell för att skapa en migreringstabell för en snabbmigrering-migrering.</span><span class="sxs-lookup"><span data-stu-id="98618-174">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration.</span></span> <span data-ttu-id="98618-175">Du kan skapa en migreringstabell och starta den automatiskt genom att inkludera _Autostart_ -parametern.</span><span class="sxs-lookup"><span data-stu-id="98618-175">You can create a migration batch and start it automatically by including the _AutoStart_ parameter.</span></span> <span data-ttu-id="98618-176">Alternativt kan du skapa migreringstabellen och sedan starta den manuellt med hjälp av cmdleten **Start-MigrationBatch** .</span><span class="sxs-lookup"><span data-stu-id="98618-176">Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet.</span></span> <span data-ttu-id="98618-177">I det här exemplet skapas ett migreringsarkiv med namnet "CutoverBatch" och används den slut punkt som skapades i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="98618-177">This example creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

<span data-ttu-id="98618-178">I det här exemplet skapas en migreringstabell med namnet "CutoverBatch" och används den migrerings slut punkt som skapades i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="98618-178">This example also creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.</span></span> <span data-ttu-id="98618-179">Eftersom den  _Autostart_ -parametern inte är inkluderad måste migreringsverktyget startas manuellt på kontroll panelen för migreringen eller genom att använda cmdleten **Start-MigrationBatch** .</span><span class="sxs-lookup"><span data-stu-id="98618-179">Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet.</span></span> <span data-ttu-id="98618-180">Som tidigare angiven kan bara en snabbmigrering för migrering finnas åt gången.</span><span class="sxs-lookup"><span data-stu-id="98618-180">As previously stated, only one cutover migration batch can exist at a time.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="98618-181">Verifiera att den fungerade</span><span class="sxs-lookup"><span data-stu-id="98618-181">Verify it worked</span></span>

<span data-ttu-id="98618-182">Om du vill kontrol lera att du har skapat en migreringstabell för en snabbmigrering migrering kör du följande kommando i Exchange Online PowerShell och visar information om den nya migreringstabellen:</span><span class="sxs-lookup"><span data-stu-id="98618-182">To verify that you've successfully created a migration batch for a cutover migration, run the following command in Exchange Online PowerShell to display information about the new migration batch:</span></span>

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a><span data-ttu-id="98618-183">Steg 4: Starta snabbmigreringsbatchen</span><span class="sxs-lookup"><span data-stu-id="98618-183">Step 4: Start the cutover migration batch</span></span>
<span data-ttu-id="98618-184"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="98618-184"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="98618-185">Om du vill starta migreringsverktyget i Exchange Online PowerShell kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="98618-185">To start the migration batch in Exchange Online PowerShell, run the following command.</span></span> <span data-ttu-id="98618-186">Detta skapar ett migreringsarkiv med namnet "CutoverBatch".</span><span class="sxs-lookup"><span data-stu-id="98618-186">This will create a migration batch called "CutoverBatch".</span></span>

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a><span data-ttu-id="98618-187">Verifiera att den fungerade</span><span class="sxs-lookup"><span data-stu-id="98618-187">Verify it worked</span></span>

<span data-ttu-id="98618-188">Om en migreringstabell har startat anges dess status på kontroll panelen för migrering som synkronisering.</span><span class="sxs-lookup"><span data-stu-id="98618-188">If a migration batch is successfully started, its status on the migration dashboard is specified as Syncing.</span></span> <span data-ttu-id="98618-189">Om du vill kontrol lera att du har startat en migreringstabell med Exchange Online PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="98618-189">To verify that you've successfully started a migration batch using Exchange Online PowerShell, run the following command:</span></span>

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="98618-190">Steg 5: dirigera din e-post till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="98618-190">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="98618-191"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="98618-191"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="98618-192">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span><span class="sxs-lookup"><span data-stu-id="98618-192">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="98618-193">Under e-postmigreringen pekar din MX-post på ditt käll-e-postsystem.</span><span class="sxs-lookup"><span data-stu-id="98618-193">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="98618-194">Nu när e-postmigreringen till Microsoft 365 är klar är det dags att skicka MX-posten på Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="98618-194">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="98618-195">Då ser du till att e-post skickas till dina Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="98618-195">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="98618-196">Genom att flytta MX-posten kan du även inaktivera det gamla e-postsystemet när du är klar.</span><span class="sxs-lookup"><span data-stu-id="98618-196">By moving the MX record, you can also you turn off your old email system when you're ready.</span></span>

<span data-ttu-id="98618-197">För många DNS-leverantörer finns det särskilda anvisningar för hur du ändrar MX-posten.</span><span class="sxs-lookup"><span data-stu-id="98618-197">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="98618-198">Om din DNS-värd inte finns med eller om du bara allmänt vill se hur anvisningarna ser ut, finns det även [allmänna anvisningar för MX-posten](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx).</span><span class="sxs-lookup"><span data-stu-id="98618-198">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx) are provided as well.</span></span>

<span data-ttu-id="98618-199">Det kan ta upp till 72 timmar för kunders och partners e-postsystem att se den ändrade MX-posten.</span><span class="sxs-lookup"><span data-stu-id="98618-199">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record.</span></span> <span data-ttu-id="98618-200">Vänta minst 72 timmar innan du går vidare till nästa uppgift: [steg 6: ta bort snabbmigrering](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span><span class="sxs-lookup"><span data-stu-id="98618-200">Wait at least 72 hours before you proceed to the next task: [Step 6: Delete the cutover migration batch](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span></span>

### <a name="step-6-delete-the-cutover-migration-batch"></a><span data-ttu-id="98618-201">Steg 6: Ta bort snabbmigreringsbatchen</span><span class="sxs-lookup"><span data-stu-id="98618-201">Step 6: Delete the cutover migration batch</span></span>
<span data-ttu-id="98618-202"><a name="Bk_step6"> </a></span><span class="sxs-lookup"><span data-stu-id="98618-202"><a name="Bk_step6"> </a></span></span>

<span data-ttu-id="98618-203">När du har ändrat MX-posten och kontrollerat att all e-post dirigeras till Microsoft 365-postlådor och meddelar användarna att deras e-post ska skickas till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="98618-203">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="98618-204">Därefter kan du ta bort snabbmigrering.</span><span class="sxs-lookup"><span data-stu-id="98618-204">After this, you can delete the cutover migration batch.</span></span> <span data-ttu-id="98618-205">Kontrollera följande innan du tar bort migreringsbatchen.</span><span class="sxs-lookup"><span data-stu-id="98618-205">Verify the following before you delete the migration batch.</span></span>

- <span data-ttu-id="98618-206">Alla användare använder Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="98618-206">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="98618-207">När du har tagit bort gruppen kopieras inte e-post till post lådor på den lokala Exchange-servern till motsvarande Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="98618-207">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>

- <span data-ttu-id="98618-208">Microsoft 365-postlådor synkroniserades minst en gång efter att e-post började skickas direkt till dem.</span><span class="sxs-lookup"><span data-stu-id="98618-208">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="98618-209">Det gör du genom att se till att värdet i rutan för den senast synkroniserade tiden för migreringstabellen är senare än när e-post som har börjat dirigeras direkt till Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="98618-209">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="98618-210">Om du vill ta bort "CutoverBatch"-migreringsverktyget i Exchange Online PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="98618-210">To delete the "CutoverBatch" migration batch in Exchange Online PowerShell, run the following command:</span></span>

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a><span data-ttu-id="98618-211">Avsnitt 7: Tilldela användar licenser</span><span class="sxs-lookup"><span data-stu-id="98618-211">Section 7: Assign user licenses</span></span>
<span data-ttu-id="98618-212"><a name="BK_Step7"> </a></span><span class="sxs-lookup"><span data-stu-id="98618-212"><a name="BK_Step7"> </a></span></span>

 <span data-ttu-id="98618-213">**Aktivera Microsoft 365-användarkonton för de migrerade kontona genom att tilldela licenser.**</span><span class="sxs-lookup"><span data-stu-id="98618-213">**Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.**</span></span> <span data-ttu-id="98618-214">Om du inte tilldelar en licens inaktiveras postlådan när tidsfristen löper ut (30 dagar).</span><span class="sxs-lookup"><span data-stu-id="98618-214">If you don't assign a license, the mailbox is disabled when the grace period ends (30 days).</span></span> <span data-ttu-id="98618-215">Information om hur du tilldelar en licens i administrations centret för Microsoft 365 finns i [tilldela eller ta bort licenser](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="98618-215">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="98618-216">Steg 8: slutföra uppgifter efter migreringen</span><span class="sxs-lookup"><span data-stu-id="98618-216">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="98618-217"><a name="BK_Step8"> </a></span><span class="sxs-lookup"><span data-stu-id="98618-217"><a name="BK_Step8"> </a></span></span>

- <span data-ttu-id="98618-218">**Skapa en DNS-post för automatisk upptäckt så att användarna enkelt kan komma till sina postlådor.**</span><span class="sxs-lookup"><span data-stu-id="98618-218">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="98618-219">När alla lokala post lådor har migrerats till Microsoft 365 kan du konfigurera en DNS-post för automatisk upptäckt för din Microsoft 365-organisation så att användarna enkelt kan ansluta till deras nya Microsoft 365-postlådor med Outlook-och mobila klienter.</span><span class="sxs-lookup"><span data-stu-id="98618-219">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="98618-220">Den nya DNS-posten Autodiscover måste använda samma namn område som du använder för din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="98618-220">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="98618-221">Om ditt molnbaserade namnområde till exempel är cloud.contoso.com, behöver du skapa DNS-posten autodiscover.cloud.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="98618-221">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>

    <span data-ttu-id="98618-222">Om du behåller Exchange-servern bör du också se till att automatisk upptäckt av DNS CNAME-posten måste peka på Microsoft 365 i både intern och extern DNS efter migreringen så att Outlook-klienten ansluter till rätt post låda.</span><span class="sxs-lookup"><span data-stu-id="98618-222">If you keep your Exchange Server, you should also make sure that Autodiscover DNS CNAME record has to point to Microsoft 365 in both internal and external DNS after the migration so that the Outlook client will to connect to the correct mailbox.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="98618-223">I Exchange 2007, Exchange 2010 och Exchange 2013 ska du också ställa in `Set-ClientAccessServer AutodiscoverInternalConnectionURI` på `Null` .</span><span class="sxs-lookup"><span data-stu-id="98618-223">In Exchange 2007, Exchange 2010, and Exchange 2013 you should also set `Set-ClientAccessServer AutodiscoverInternalConnectionURI` to `Null`.</span></span>

    <span data-ttu-id="98618-224">I Microsoft 365 används en CNAME-post för att implementera tjänsten för automatisk upptäckt för Outlook och mobila klienter.</span><span class="sxs-lookup"><span data-stu-id="98618-224">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="98618-225">CNAME-posten för automatisk upptäckt måste innehålla följande information:</span><span class="sxs-lookup"><span data-stu-id="98618-225">The Autodiscover CNAME record must contain the following information:</span></span>

  - <span data-ttu-id="98618-226">**Alias:** autodiscover</span><span class="sxs-lookup"><span data-stu-id="98618-226">**Alias:** autodiscover</span></span>

  - <span data-ttu-id="98618-227">**Target:** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="98618-227">**Target:** autodiscover.outlook.com</span></span>

    <span data-ttu-id="98618-228">Mer information finns i [lägga till DNS-poster för att ansluta din domän](https://go.microsoft.com/fwlink/p/?LinkId=535028).</span><span class="sxs-lookup"><span data-stu-id="98618-228">For more information, see [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=535028).</span></span>

- <span data-ttu-id="98618-229">**Inaktivera lokala Exchange-servrar.**</span><span class="sxs-lookup"><span data-stu-id="98618-229">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="98618-230">När du har verifierat att all e-post dirigeras direkt till Microsoft 365-postlådor och du inte längre behöver underhålla den lokala e-postorganisationen eller inte planerar att implementera en lösning för enkel inloggning (SSO), kan du avinstallera Exchange från dina servrar och ta bort din lokala Exchange-organisation.</span><span class="sxs-lookup"><span data-stu-id="98618-230">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing a single sign-on (SSO) solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>

    <span data-ttu-id="98618-231">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="98618-231">For more information, see the following:</span></span>

  - [<span data-ttu-id="98618-232">Ändra eller ta bort Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="98618-232">Modify or Remove Exchange 2010</span></span>](https://go.microsoft.com/fwlink/?LinkId=217936)

  - [<span data-ttu-id="98618-233">Ta bort en Exchange 2007-organisation</span><span class="sxs-lookup"><span data-stu-id="98618-233">How to Remove an Exchange 2007 Organization</span></span>](https://go.microsoft.com/fwlink/?LinkID=100485)

  - [<span data-ttu-id="98618-234">Avinstallera Exchange Server 2003</span><span class="sxs-lookup"><span data-stu-id="98618-234">How to Uninstall Exchange Server 2003</span></span>](https://go.microsoft.com/fwlink/?LinkID=56561)


