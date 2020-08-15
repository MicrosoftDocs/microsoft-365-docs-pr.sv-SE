---
title: Använda PowerShell för att utföra en stegvis migrering till Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: Lär dig hur du använder PowerShell för att flytta innehåll från ett käll-e-postsystem över tid med hjälp av en stegvis migrering till Microsoft 365.
ms.openlocfilehash: ebf2067fe7ae9fc2d2b58d0aa804c7843295b38a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694469"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a><span data-ttu-id="67383-103">Använda PowerShell för att utföra en stegvis migrering till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="67383-103">Use PowerShell to perform a staged migration to Microsoft 365</span></span>

<span data-ttu-id="67383-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="67383-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="67383-105">Du kan migrera innehållet i användar post lådor från ett käll-e-postsystem till Microsoft 365 över tiden med en stegvis migrering.</span><span class="sxs-lookup"><span data-stu-id="67383-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 over time using a staged migration.</span></span>
  
<span data-ttu-id="67383-106">I den här artikeln får du stegvisa instruktioner för hur du använder en stegvis e-postmigrering med Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67383-106">This article walks you through the tasks involved with for a staged email migration using Exchange Online PowerShell.</span></span> <span data-ttu-id="67383-107">I det här avsnittet får du en översikt över hur du migrerar [e-postmigreringen](https://go.microsoft.com/fwlink/p/?LinkId=536487).</span><span class="sxs-lookup"><span data-stu-id="67383-107">The topic, [What you need to know about a staged email migration](https://go.microsoft.com/fwlink/p/?LinkId=536487), gives you an overview of the migration process.</span></span> <span data-ttu-id="67383-108">När du har bekantat dig med innehållet i den artikeln kan du använda den här för att börja migrera postlådor från ett e-postsystem till ett annat.</span><span class="sxs-lookup"><span data-stu-id="67383-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>
  
> [!NOTE]
> <span data-ttu-id="67383-109">Du kan också använda administrations centret för Exchange för att utföra stegvis migrering.</span><span class="sxs-lookup"><span data-stu-id="67383-109">You can also use the Exchange admin center to perform staged migration.</span></span> <span data-ttu-id="67383-110">Se [utföra en stegvis migrering av e-post till Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536687).</span><span class="sxs-lookup"><span data-stu-id="67383-110">See [Perform a staged migration of email to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536687).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="67383-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="67383-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="67383-112">Uppskattad tid för att slutföra den här uppgiften: 2-5 minuter för att skapa en migreringstabell.</span><span class="sxs-lookup"><span data-stu-id="67383-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="67383-113">När migreringen har startat varierar varaktigheten för migreringen baserat på antalet post lådor i gruppen, storleken på varje post låda och din tillgängliga nätverks kapacitet.</span><span class="sxs-lookup"><span data-stu-id="67383-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="67383-114">Information om andra faktorer som påverkar hur lång tid det tar att migrera post lådor till Microsoft 365 finns i [migreringens prestanda](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span><span class="sxs-lookup"><span data-stu-id="67383-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span></span>
  
<span data-ttu-id="67383-115">Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna.</span><span class="sxs-lookup"><span data-stu-id="67383-115">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="67383-116">Om du vill se vilka behörigheter du behöver läser du "migration"-posten i avsnittet [mottagare](https://go.microsoft.com/fwlink/p/?LinkId=534105) .</span><span class="sxs-lookup"><span data-stu-id="67383-116">To see what permissions you need, see the "Migration" entry in the [Recipients Permissions](https://go.microsoft.com/fwlink/p/?LinkId=534105) topic.</span></span>
  
<span data-ttu-id="67383-117">För att använda PowerShell-cmdletar för Exchange Online måste du logga in och importera cmdletarna till din lokala Windows PowerShell-session.</span><span class="sxs-lookup"><span data-stu-id="67383-117">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session.</span></span> <span data-ttu-id="67383-118">Se [ansluta till Exchange Online med Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) för instruktioner.</span><span class="sxs-lookup"><span data-stu-id="67383-118">See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
  
<span data-ttu-id="67383-119">En fullständig lista över migreringsåtgärder finns i avsnittet [flytta och migrera cmdletar](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="67383-119">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
## <a name="migration-steps"></a><span data-ttu-id="67383-120">Migreringsåtgärder</span><span class="sxs-lookup"><span data-stu-id="67383-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-staged-migration"></a><span data-ttu-id="67383-121">Steg 1: förbereda en stegvis migrering</span><span class="sxs-lookup"><span data-stu-id="67383-121">Step 1: Prepare for a staged migration</span></span>

<span data-ttu-id="67383-122">Innan du migrerar post lådor till Microsoft 365 med en stegvis migrering finns det några ändringar du måste göra i din Exchange-miljö.</span><span class="sxs-lookup"><span data-stu-id="67383-122">Before you migrate mailboxes to Microsoft 365 by using a staged migration, there are a few changes you must make to your Exchange environment.</span></span>
  
 <span data-ttu-id="67383-123">**Konfigurera Outlook överallt på din lokala Exchange Server** E-postmigreringstjänsten använder Outlook överallt (som även kallas RPC över HTTP) för att ansluta till din lokala Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="67383-123">**Configure Outlook Anywhere on your on-premises Exchange Server** The email migration service uses Outlook Anywhere (also known as RPC over HTTP), to connect to your on-premises Exchange Server.</span></span> <span data-ttu-id="67383-124">Information om hur du konfigurerar Outlook för Exchange Server 2007 och Exchange 2003 finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="67383-124">For information about how to set up Outlook Anywhere for Exchange Server 2007, and Exchange 2003, see the following:</span></span>
  
- [<span data-ttu-id="67383-125">Exchange 2007: Aktivera Outlook överallt</span><span class="sxs-lookup"><span data-stu-id="67383-125">Exchange 2007: How to Enable Outlook Anywhere</span></span>](https://go.microsoft.com/fwlink/?LinkID=167210)
    
- [<span data-ttu-id="67383-126">Konfigurera Outlook överallt med Exchange 2003</span><span class="sxs-lookup"><span data-stu-id="67383-126">How to configure Outlook Anywhere with Exchange 2003</span></span>](https://go.microsoft.com/fwlink/?LinkID=167209)
    
> [!IMPORTANT]
> <span data-ttu-id="67383-p107">Du måste använda ett certifikat som utfärdats av en pålitlig certifikatutfärdare (CA) med din Outlook överallt-konfiguration. Outlook överallt kan inte konfigureras med ett självsignerat certifikat. Mer information finns i [Konfigurera SSL för Outlook överallt](https://go.microsoft.com/fwlink/?LinkID=80875).</span><span class="sxs-lookup"><span data-stu-id="67383-p107">You must use a certificate issued by a trusted certification authority (CA) with your Outlook Anywhere configuration. Outlook Anywhere can't be configured with a self-signed certificate. For more information, see [How to configure SSL for Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=80875).</span></span> 
  
 <span data-ttu-id="67383-130">**Valfritt: Kontrollera att du kan ansluta till din Exchange-organisation med Outlook överallt** Prova någon av följande metoder för att testa dina anslutningsinställningar.</span><span class="sxs-lookup"><span data-stu-id="67383-130">**Optional: Verify that you can connect to your Exchange organization using Outlook Anywhere** Try one of the following methods to test your connection settings.</span></span>
  
- <span data-ttu-id="67383-131">Använd Outlook utanför företagets nätverk för att ansluta till den lokala Exchange postlådan.</span><span class="sxs-lookup"><span data-stu-id="67383-131">Use Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>
    
- <span data-ttu-id="67383-132">Använd [Microsoft Remote Connectivity Analyzer](https://https://testconnectivity.microsoft.com/) för att testa dina anslutnings inställningar.</span><span class="sxs-lookup"><span data-stu-id="67383-132">Use the [Microsoft Remote Connectivity Analyzer](https://https://testconnectivity.microsoft.com/) to test your connection settings.</span></span> <span data-ttu-id="67383-133">Använd Outlook överallt (RPC över HTTP) eller Outlook Automatisk upptäckt av tester.</span><span class="sxs-lookup"><span data-stu-id="67383-133">Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>
    
- <span data-ttu-id="67383-134">Kör följande kommandon i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="67383-134">Run the following commands in Exchange Online PowerShell:</span></span>
    
  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 <span data-ttu-id="67383-135">**Ange behörigheter** Det lokala användar kontot som du använder för att ansluta till den lokala Exchange-organisationen (kallas även för administratör för migrering) måste ha nödvändig behörighet för att få åtkomst till de lokala post lådorna som du vill migrera till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="67383-135">**Set permissions** The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="67383-136">Det här användar kontot används när du ansluter till ditt e-postsystem genom att skapa en slut punkt för migrering senare i den här proceduren ([steg 3: skapa en migrerings slut punkt](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint) ).</span><span class="sxs-lookup"><span data-stu-id="67383-136">This user account is used when you connect to your email system by creating a migration endpoint later in this procedure ([Step 3: Create a migration endpoint](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint) ).</span></span>
  
<span data-ttu-id="67383-137">För att kunna migrera postlådor måste administratören ha någon av följande behörigheter:</span><span class="sxs-lookup"><span data-stu-id="67383-137">To migrate the mailboxes, the admin must have one of the following permission sets:</span></span>
  
- <span data-ttu-id="67383-138">Bli medlem i gruppen **Domain admins** i Active Directory i den lokala organisationen.</span><span class="sxs-lookup"><span data-stu-id="67383-138">Be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>
    
    <span data-ttu-id="67383-139">eller</span><span class="sxs-lookup"><span data-stu-id="67383-139">or</span></span>
    
- <span data-ttu-id="67383-140">Tilldelas **behörigheten Full Access** -behörighet för varje lokal post låda och **WriteProperty** -behörigheten för att ändra egenskapen **targetAddress** för lokala användar konton.</span><span class="sxs-lookup"><span data-stu-id="67383-140">Be assigned the **FullAccess** permission for each on-premises mailbox and the **WriteProperty** permission to modify the **TargetAddress** property on the on-premises user accounts.</span></span>
    
    <span data-ttu-id="67383-141">eller</span><span class="sxs-lookup"><span data-stu-id="67383-141">or</span></span>
    
- <span data-ttu-id="67383-142">Tilldelas behörigheten **Receive As** för den lokala post lådan som lagrar användar post lådor och **WriteProperty** -behörigheten för att ändra egenskapen **targetAddress** för lokala användar konton.</span><span class="sxs-lookup"><span data-stu-id="67383-142">Be assigned the **Receive As** permission on the on-premises mailbox database that stores user mailboxes and the **WriteProperty** permission to modify the **TargetAddress** property on the on-premises user accounts.</span></span>
    
<span data-ttu-id="67383-143">Anvisningar om hur du anger de här behörigheterna finns i [tilldela behörigheter för att migrera post lådor till Microsoft 365](https://go.microsoft.com/fwlink/?LinkId=521656).</span><span class="sxs-lookup"><span data-stu-id="67383-143">For instructions about how to set these permissions, see [Assign permissions to migrate mailboxes to Microsoft 365](https://go.microsoft.com/fwlink/?LinkId=521656).</span></span>
  
 <span data-ttu-id="67383-144">**Inaktivera Unified Messaging (UM)** Om UM är aktiverat för de lokala postlådorna som du migrerar, stänger du av UM före migreringen.</span><span class="sxs-lookup"><span data-stu-id="67383-144">**Disable Unified Messaging (UM)** If UM is turned on for the on-premises mailboxes you're migrating, turn off UM before migration.</span></span> <span data-ttu-id="67383-145">Aktivera UM för postlådorna när migreringen är klar.</span><span class="sxs-lookup"><span data-stu-id="67383-145">Turn on UM for the mailboxes after migration is complete.</span></span> <span data-ttu-id="67383-146">Instruktioner finns i[inaktivera Unified Messaging](https://go.microsoft.com/fwlink/?LinkId=521891).</span><span class="sxs-lookup"><span data-stu-id="67383-146">For how-to steps, see[disable unified messaging](https://go.microsoft.com/fwlink/?LinkId=521891).</span></span>
  
 <span data-ttu-id="67383-147">**Använd katalog-synkronisering för att skapa nya användare i Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="67383-147">**Use directory synchronization to create new users in Microsoft 365.**</span></span> <span data-ttu-id="67383-148">Du använder katalog synkronisering för att skapa alla lokala användare i din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="67383-148">You use directory synchronization to create all the on-premises users in your Microsoft 365 organization.</span></span>
  
<span data-ttu-id="67383-149">Du måste licensiera användarna efter att de har skapats.</span><span class="sxs-lookup"><span data-stu-id="67383-149">You need to license the users after they're created.</span></span> <span data-ttu-id="67383-150">Du har 30 dagar på dig att lägga till licenser efter att användarna skapats.</span><span class="sxs-lookup"><span data-stu-id="67383-150">You have 30 days to add licenses after the users are created.</span></span> <span data-ttu-id="67383-151">Anvisningar för hur du lägger till licenser finns i [steg 8: slutföra uppgifter efter migreringen](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration).</span><span class="sxs-lookup"><span data-stu-id="67383-151">For steps to add licenses, see [Step 8: Complete post-migration tasks](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration).</span></span>
  
 <span data-ttu-id="67383-152">Du kan använda Microsoft Azure Active Directory-synkroniseringsfunktionen (Azure AD) eller Microsoft Azure AD Sync Services för att synkronisera och skapa lokala användare i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="67383-152">You can use either the Microsoft Azure Active Directory (Azure AD) Synchronization Tool or the Microsoft Azure AD Sync Services  to synchronize and create your on-premises users in Microsoft 365.</span></span> <span data-ttu-id="67383-153">När post lådor har migrerats till Microsoft 365 kan du hantera användar konton i din lokala organisation och de synkroniseras med din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="67383-153">After mailboxes are migrated to Microsoft 365, you manage user accounts in your on-premises organization, and they're synchronized with your Microsoft 365 organization.</span></span> <span data-ttu-id="67383-154">Mer information finns i[katalog integrering](https://go.microsoft.com/fwlink/?LinkId=521788) .</span><span class="sxs-lookup"><span data-stu-id="67383-154">For more information, see[Directory Integration](https://go.microsoft.com/fwlink/?LinkId=521788) .</span></span>
  
### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a><span data-ttu-id="67383-155">Steg 2: skapa en CSV-fil för ett batchjobb med stegvis migrering</span><span class="sxs-lookup"><span data-stu-id="67383-155">Step 2: Create a CSV file for a staged migration batch</span></span>

<span data-ttu-id="67383-156">När du har identifierat de användare vars lokala post lådor du vill migrera till Microsoft 365 använder du en CSV-fil (kommaseparerade värden) för att skapa en migreringstabell.</span><span class="sxs-lookup"><span data-stu-id="67383-156">After you identify the users whose on-premises mailboxes you want to migrate to Microsoft 365, you use a comma separated value (CSV ) file to create a migration batch.</span></span> <span data-ttu-id="67383-157">Varje rad i CSV-filen – som används av Microsoft 365 för att köra migreringen – innehåller information om en lokal post låda.</span><span class="sxs-lookup"><span data-stu-id="67383-157">Each row in the CSV file—used by Microsoft 365 to run the migration—contains information about an on-premises mailbox.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="67383-158">Det finns inte någon begränsning för hur många post lådor du kan migrera till Microsoft 365 med en stegvis migrering.</span><span class="sxs-lookup"><span data-stu-id="67383-158">There isn't a limit for the number of mailboxes that you can migrate to Microsoft 365 using a staged migration.</span></span> <span data-ttu-id="67383-159">CSV-filen för en migreringsbatch rymmer högst 2 000 rader.</span><span class="sxs-lookup"><span data-stu-id="67383-159">The CSV file for a migration batch can contain a maximum of 2,000 rows.</span></span> <span data-ttu-id="67383-160">Om du vill migrera fler än 2 000 postlådor måste du skapa ytterligare CSV-filer och använda varje fil för att skapa en ny batch.</span><span class="sxs-lookup"><span data-stu-id="67383-160">To migrate more than 2,000 mailboxes, create additional CSV files and use each file to create a new migration batch.</span></span> 
  
 <span data-ttu-id="67383-161">**Attribut som stöds**</span><span class="sxs-lookup"><span data-stu-id="67383-161">**Supported attributes**</span></span>
  
<span data-ttu-id="67383-p116">CSV-filen för en stegvis migrering har stöd för följande tre attribut. Varje rad i CSV-filen motsvarar en postlåda och måste innehålla ett värde för vart och ett av de här attributen.</span><span class="sxs-lookup"><span data-stu-id="67383-p116">The CSV file for a staged migration supports the following three attributes. Each row in the CSV file corresponds to a mailbox and must contain a value for each of these attributes.</span></span>
  
|<span data-ttu-id="67383-164">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="67383-164">**Attribute**</span></span>|<span data-ttu-id="67383-165">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="67383-165">**Description**</span></span>|<span data-ttu-id="67383-166">**Obligatorisk**</span><span class="sxs-lookup"><span data-stu-id="67383-166">**Required?**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="67383-167">EmailAddress</span><span class="sxs-lookup"><span data-stu-id="67383-167">EmailAddress</span></span>  <br/> |<span data-ttu-id="67383-168">Anger den primära SMTP-e-postadressen, till exempel pilarp@contoso.com, för lokala postlådor.</span><span class="sxs-lookup"><span data-stu-id="67383-168">Specifies the primary SMTP email address, for example, pilarp@contoso.com, for on-premises mailboxes.</span></span>  <br/> <span data-ttu-id="67383-169">Använd den primära SMTP-adressen för lokala post lådor och inte användar-ID: n från Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="67383-169">Use the primary SMTP address for on-premises mailboxes and not user IDs from the Microsoft 365.</span></span> <span data-ttu-id="67383-170">Om den lokala domänen till exempel heter contoso.com men Microsoft 365-e-postdomänen heter service.contoso.com, använder du contoso.com domän namn för e-postadresser i CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="67383-170">For example, if the on-premises domain is named contoso.com but the Microsoft 365 email domain is named service.contoso.com, you would use the contoso.com domain name for email addresses in the CSV file.</span></span>  <br/> |<span data-ttu-id="67383-171">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="67383-171">Required</span></span>  <br/> |
|<span data-ttu-id="67383-172">Lösenord</span><span class="sxs-lookup"><span data-stu-id="67383-172">Password</span></span>  <br/> |<span data-ttu-id="67383-173">Lösen ordet som ska anges för den nya Microsoft 365-postlådan.</span><span class="sxs-lookup"><span data-stu-id="67383-173">The password to be set for the new Microsoft 365 mailbox.</span></span> <span data-ttu-id="67383-174">Eventuella lösen ords begränsningar som gäller för Microsoft 365-organisationen gäller också för lösen ord som ingår i CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="67383-174">Any password restrictions that are applied to your Microsoft 365 organization also apply to the passwords included in the CSV file.</span></span>  <br/> |<span data-ttu-id="67383-175">Valfri</span><span class="sxs-lookup"><span data-stu-id="67383-175">Optional</span></span>  <br/> |
|<span data-ttu-id="67383-176">ForceChangePassword</span><span class="sxs-lookup"><span data-stu-id="67383-176">ForceChangePassword</span></span>  <br/> |<span data-ttu-id="67383-177">Anger om en användare måste ändra lösen ordet första gången de loggar in i sin nya Microsoft 365-postlåda.</span><span class="sxs-lookup"><span data-stu-id="67383-177">Specifies whether a user must change the password the first time they sign in to their new Microsoft 365 mailbox.</span></span> <span data-ttu-id="67383-178">Använd **True** eller **False** för den här parameterns värde.</span><span class="sxs-lookup"><span data-stu-id="67383-178">Use **True** or **False** for the value of this parameter.</span></span> <br/> <span data-ttu-id="67383-179">> [!NOTE]> om du har implementerat en lösning för enkel inloggning (SSO) genom att distribuera Active Directory Federation Services (AD FS) eller större i din lokala organisation, måste du använda **falskt** för värdet för attributet **ForceChangePassword** .</span><span class="sxs-lookup"><span data-stu-id="67383-179">> [!NOTE]> If you've implemented a single sign-on (SSO) solution by deploying Active Directory Federation Services (AD FS) or greater in your on-premises organization, you must use **False** for the value of the **ForceChangePassword** attribute.</span></span>          |<span data-ttu-id="67383-180">Valfri</span><span class="sxs-lookup"><span data-stu-id="67383-180">Optional</span></span>  <br/> |
   
 <span data-ttu-id="67383-181">**CSV-filformat**</span><span class="sxs-lookup"><span data-stu-id="67383-181">**CSV file format**</span></span>
  
<span data-ttu-id="67383-182">Här följer ett exempel på CSV-filens format.</span><span class="sxs-lookup"><span data-stu-id="67383-182">Here's an example of the format for the CSV file.</span></span> <span data-ttu-id="67383-183">I det här exemplet migreras tre lokala post lådor till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="67383-183">In this example, three on-premises mailboxes are migrated to Microsoft 365.</span></span>
  
<span data-ttu-id="67383-p121">CSV-filens första rad, eller rubrikraden, visar namnen på de attribut, eller fält, som anges i de följande raderna. Varje attributnamn avgränsas av ett kommatecken.</span><span class="sxs-lookup"><span data-stu-id="67383-p121">The first row, or header row, of the CSV file lists the names of the attributes, or fields, specified in the rows that follow. Each attribute name is separated by a comma.</span></span>
  
```powershell
EmailAddress,Password,ForceChangePassword 
pilarp@contoso.com,Pa$$w0rd,False 
tobyn@contoso.com,Pa$$w0rd,False 
briant@contoso.com,Pa$$w0rd,False 
```

<span data-ttu-id="67383-p122">Varje rad under rubrikraden representerar en användare och ger den information som ska användas för att migrera användarens postlåda. Attributvärdena på varje rad måste vara placerade i samma ordning som attributnamnen på rubrikraden.</span><span class="sxs-lookup"><span data-stu-id="67383-p122">Each row under the header row represents one user and supplies the information that will be used to migrate the user's mailbox. The attribute values in each row must be in the same order as the attribute names in the header row.</span></span> 
  
<span data-ttu-id="67383-188">Använd valfri text redigerare eller ett program som Excel för att skapa CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="67383-188">Use any text editor, or an application like Excel , to create the CSV file.</span></span> <span data-ttu-id="67383-189">Spara filen som CSV eller TXT.</span><span class="sxs-lookup"><span data-stu-id="67383-189">Save the file as a .csv or .txt file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="67383-190">Om CSV-filen innehåller specialtecken eller andra tecken än ASCII-tecken sparar du CSV-filen med UTF-8-kodning eller annan Unicode-kodning.</span><span class="sxs-lookup"><span data-stu-id="67383-190">If the CSV file contains non-ASCII or special characters, save the CSV file with UTF-8 or other Unicode encoding.</span></span> <span data-ttu-id="67383-191">Beroende på programmet kan det vara enklare att spara CSV-filen med UTF-8 eller annan Unicode-kodning när datorns system språk matchar det språk som används i CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="67383-191">Depending on the application, saving the CSV file with UTF-8 or other Unicode encoding can be easier when the system locale of the computer matches the language used in the CSV file.</span></span> 
  
### <a name="step-3-create-a-migration-endpoint"></a><span data-ttu-id="67383-192">Steg 3: skapa en slut punkt för migrering</span><span class="sxs-lookup"><span data-stu-id="67383-192">Step 3: Create a migration endpoint</span></span>
<span data-ttu-id="67383-193"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="67383-193"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="67383-194">För att migrera e-post måste Microsoft 365 ansluta och kommunicera med käll-e-postsystemet.</span><span class="sxs-lookup"><span data-stu-id="67383-194">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="67383-195">För att göra det, använder Microsoft 365 en slut punkt för migrering.</span><span class="sxs-lookup"><span data-stu-id="67383-195">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="67383-196">Om du vill skapa en uppgraderings slut punkt för Outlook överallt med PowerShell, för stegvis migrering, [ansluter du först till Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span><span class="sxs-lookup"><span data-stu-id="67383-196">To create an Outlook Anywhere migration endpoint by using PowerShell, for staged migration, first [connect to Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span></span> 
  
<span data-ttu-id="67383-197">En fullständig lista över migreringsåtgärder finns i avsnittet [flytta och migrera cmdletar](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="67383-197">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="67383-198">Om du vill skapa en migrerings slut punkt för Outlook överallt med namnet "StagedEndpoint" i Exchange Online PowerShell kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="67383-198">To create an Outlook Anywhere migration endpoint called "StagedEndpoint" in Exchange Online PowerShell, run the following commands:</span></span>
  
```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

<span data-ttu-id="67383-199">Mer information om **New-MigrationEndpoint** -cmdleten finns i[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).</span><span class="sxs-lookup"><span data-stu-id="67383-199">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).</span></span>
  
> [!NOTE]
> <span data-ttu-id="67383-200">Cmdleten **New-MigrationEndpoint** kan användas för att ange en databas som ska användas med alternativet **-TargetDatabase** .</span><span class="sxs-lookup"><span data-stu-id="67383-200">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option.</span></span> <span data-ttu-id="67383-201">I annat fall tilldelas en databas slumpmässigt från AD FS-2,0 (Active Directory Federation Services) där hanterings post lådan finns.</span><span class="sxs-lookup"><span data-stu-id="67383-201">Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="67383-202">Verifiera att den fungerade</span><span class="sxs-lookup"><span data-stu-id="67383-202">Verify it worked</span></span>

<span data-ttu-id="67383-203">I Exchange Online PowerShell kör du följande kommando för att visa information om "StagedEndpoint"-slut punkt för migrering:</span><span class="sxs-lookup"><span data-stu-id="67383-203">In Exchange Online PowerShell, run the following command to display information about the "StagedEndpoint" migration endpoint:</span></span>
  
```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a><span data-ttu-id="67383-204">Steg 4: skapa och starta ett batchjobb för en fas</span><span class="sxs-lookup"><span data-stu-id="67383-204">Step 4: Create and start a stage migration batch</span></span>
<span data-ttu-id="67383-205"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="67383-205"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="67383-206">Du kan använda cmdleten **New-MigrationBatch** i Exchange Online PowerShell för att skapa en migreringstabell för en snabbmigrering-migrering.</span><span class="sxs-lookup"><span data-stu-id="67383-206">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration.</span></span> <span data-ttu-id="67383-207">Du kan skapa en migreringstabell och starta den automatiskt genom att inkludera _Autostart_ -parametern.</span><span class="sxs-lookup"><span data-stu-id="67383-207">You can create a migration batch and start it automatically by including the _AutoStart_ parameter.</span></span> <span data-ttu-id="67383-208">Alternativt kan du skapa migreringstabellen och sedan starta den manuellt med hjälp av cmdleten **Start-MigrationBatch** .</span><span class="sxs-lookup"><span data-stu-id="67383-208">Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet.</span></span> <span data-ttu-id="67383-209">I det här exemplet skapas ett migreringsarkiv med namnet "StagedBatch1" och används den slut punkt som skapades i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="67383-209">This example creates a migration batch called "StagedBatch1" and uses the migration endpoint that was created in the previous step.</span></span>
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

<span data-ttu-id="67383-210">I det här exemplet skapas en migreringstabell med namnet "StagedBatch1" och används den migrerings slut punkt som skapades i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="67383-210">This example also creates a migration batch called "StagedBatch1" and uses the migration endpoint that was created in the previous step.</span></span> <span data-ttu-id="67383-211">Eftersom den  _Autostart_ -parametern inte är inkluderad måste migreringsverktyget startas manuellt på kontroll panelen för migreringen eller genom att använda cmdleten **Start-MigrationBatch** .</span><span class="sxs-lookup"><span data-stu-id="67383-211">Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet.</span></span> <span data-ttu-id="67383-212">Som tidigare angiven kan bara en snabbmigrering för migrering finnas åt gången.</span><span class="sxs-lookup"><span data-stu-id="67383-212">As previously stated, only one cutover migration batch can exist at a time.</span></span>
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="67383-213">Verifiera att den fungerade</span><span class="sxs-lookup"><span data-stu-id="67383-213">Verify it worked</span></span>

<span data-ttu-id="67383-214">Kör följande kommando i Exchange Online PowerShell för att visa information om "StagedBatch1":</span><span class="sxs-lookup"><span data-stu-id="67383-214">Run the following command in Exchange Online PowerShell to display information about the "StagedBatch1":</span></span>
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

<span data-ttu-id="67383-215">Du kan också kontrol lera att batchjobbet har startat genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="67383-215">You can also verify that the batch has started by running the following command:</span></span>
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

<span data-ttu-id="67383-216">Mer information om cmdleten **Get-MigrationBatch** finns i[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span><span class="sxs-lookup"><span data-stu-id="67383-216">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span></span>
  
### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a><span data-ttu-id="67383-217">Steg 5: konvertera lokala post lådor till e-postaktiverade användare</span><span class="sxs-lookup"><span data-stu-id="67383-217">Step 5: Convert on-premises mailboxes to mail-enabled users</span></span>
<span data-ttu-id="67383-218"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="67383-218"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="67383-219">När du har migrerat en grupp postlådor måste användarna kunna komma åt sin e-post.</span><span class="sxs-lookup"><span data-stu-id="67383-219">After you have successfully migrated a batch of mailboxes, you need some way to let users get to their mail.</span></span> <span data-ttu-id="67383-220">En användare vars post låda har migrerats har nu både en post låda och en i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="67383-220">A user whose mailbox has been migrated now has both a mailbox on-premises and one in Microsoft 365.</span></span> <span data-ttu-id="67383-221">Användare som har en post låda i Microsoft 365 slutar att få ny e-post i sin lokala post låda.</span><span class="sxs-lookup"><span data-stu-id="67383-221">Users who have a mailbox in Microsoft 365 will stop receiving new mail in their on-premises mailbox.</span></span> 
  
<span data-ttu-id="67383-222">Eftersom du inte är uppkopplad med dina migreringar är du inte redo att direkt dirigera alla användare till Microsoft 365 för deras e-post.</span><span class="sxs-lookup"><span data-stu-id="67383-222">Because you are not done with your migrations, you are not yet ready to direct all users to Microsoft 365 for their email.</span></span> <span data-ttu-id="67383-223">Vad gör man då med de personer som har båda postlådorna?</span><span class="sxs-lookup"><span data-stu-id="67383-223">So what do you do for those people who have both?</span></span> <span data-ttu-id="67383-224">En sak som du kan göra är att ändra de lokala postlådorna som du redan har migrerat till e-postanvändare.</span><span class="sxs-lookup"><span data-stu-id="67383-224">What you can do is change the on-premises mailboxes that you've already migrated to mail-enabled users.</span></span> <span data-ttu-id="67383-225">När du ändrar från en post låda till en e-postaktiverad användare kan du dirigera användaren till Microsoft 365 för e-post i stället för att gå till den lokala post lådan.</span><span class="sxs-lookup"><span data-stu-id="67383-225">When you change from a mailbox to a mail-enabled user, you can direct the user to Microsoft 365 for their email instead of going to their on-premises mailbox.</span></span> 
  
<span data-ttu-id="67383-226">En annan viktig anledning att konvertera lokala post lådor till e-postaktiverade användare är att behålla proxyadresser från Microsoft 365-postlådor genom att kopiera proxyadresser till e-postaktiverade användare.</span><span class="sxs-lookup"><span data-stu-id="67383-226">Another important reason to convert on-premises mailboxes to mail-enabled users is to retain proxy addresses from the Microsoft 365 mailboxes by copying proxy addresses to the mail-enabled users.</span></span> <span data-ttu-id="67383-227">Med den här funktionen kan du hantera molnbaserade användare från din lokala organisation genom att använda Active Directory.</span><span class="sxs-lookup"><span data-stu-id="67383-227">This lets you manage cloud-based users from your on-premises organization by using Active Directory.</span></span> <span data-ttu-id="67383-228">Om du bestämmer dig för att inaktivera din lokala Exchange Server-organisation efter att alla post lådor har migrerats till Microsoft 365, kommer de proxyservrar som du har kopierat till e-postaktiverade användare att bevaras i din lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="67383-228">Also, if you decide to decommission your on-premises Exchange Server organization after all mailboxes are migrated to Microsoft 365, the proxy addresses you've copied to the mail-enabled users will remain in your on-premises Active Directory.</span></span>
    
### <a name="step-6-delete-a-staged-migration-batch"></a><span data-ttu-id="67383-229">Steg 6: ta bort batchen för stegvis migrering</span><span class="sxs-lookup"><span data-stu-id="67383-229">Step 6: Delete a staged migration batch</span></span>
<span data-ttu-id="67383-230"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="67383-230"><a name="BK_Endpoint"> </a></span></span>

 <span data-ttu-id="67383-231">När alla post lådor i en migreringstabell har migrerats och du har konverterat de lokala post lådorna i gruppen till e-postaktiverade användare är det dags att ta bort ett batchjobb för stegvis migrering.</span><span class="sxs-lookup"><span data-stu-id="67383-231">After all mailboxes in a migration batch have been successfully migrated, and you've converted the on-premises mailboxes in the batch to mail-enabled users, you're ready to delete a staged migration batch.</span></span> <span data-ttu-id="67383-232">Kontrol lera att e-post vidarekopplas till Microsoft 365-postlådor i fältet migration.</span><span class="sxs-lookup"><span data-stu-id="67383-232">Be sure to verify that mail is being forwarded to the Microsoft 365 mailboxes in the migration batch.</span></span> <span data-ttu-id="67383-233">När du tar bort ett batchjobb för stegvis migrering rensar migreringsguiden alla poster relaterade till migreringsverktyget och tar bort migreringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="67383-233">When you delete a staged migration batch, the migration service cleans up any records related to the migration batch and deletes the migration batch.</span></span>
  
<span data-ttu-id="67383-234">Om du vill ta bort batchjobbet "StagedBatch1" i Exchange Online PowerShell kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="67383-234">To delete the "StagedBatch1" migration batch in Exchange Online PowerShell, run the following command.</span></span>
  
```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

<span data-ttu-id="67383-235">Mer information om cmdleten **Remove-MigrationBatch** finns i[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span><span class="sxs-lookup"><span data-stu-id="67383-235">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="67383-236">Verifiera att den fungerade</span><span class="sxs-lookup"><span data-stu-id="67383-236">Verify it worked</span></span>

<span data-ttu-id="67383-237">Kör följande kommando i Exchange Online PowerShell för att visa information om "IMAPBatch1":</span><span class="sxs-lookup"><span data-stu-id="67383-237">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch StagedBatch1
```

<span data-ttu-id="67383-238">Kommandot returnerar antingen migreringsarkivet med **statusen borttagen**eller returnerar ett fel meddelande som säger att det inte gick att hitta den Överflyttnings journal som verifierar att gruppen har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="67383-238">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>
  
<span data-ttu-id="67383-239">Mer information om cmdleten **Get-MigrationBatch** finns i[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span><span class="sxs-lookup"><span data-stu-id="67383-239">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span></span>
  
### <a name="step7-assign-licenses-to-microsoft-365-users"></a><span data-ttu-id="67383-240">Step7: tilldela licenser till Microsoft 365-användare</span><span class="sxs-lookup"><span data-stu-id="67383-240">Step7: Assign licenses to Microsoft 365 users</span></span>
<span data-ttu-id="67383-241"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="67383-241"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="67383-242">Aktivera Microsoft 365-användarkonton för de migrerade kontona genom att tilldela licenser.</span><span class="sxs-lookup"><span data-stu-id="67383-242">Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.</span></span> <span data-ttu-id="67383-243">Om du inte tilldelar en licens inaktiveras postlådan när tidsfristen löper ut (30 dagar).</span><span class="sxs-lookup"><span data-stu-id="67383-243">If you don't assign a license, the mailbox is disabled when the grace period (30 days) ends.</span></span> <span data-ttu-id="67383-244">Information om hur du tilldelar en licens i administrations centret för Microsoft 365 finns i [tilldela eller ta bort licenser](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="67383-244">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>
  
### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="67383-245">Steg 8: slutföra uppgifter efter migreringen</span><span class="sxs-lookup"><span data-stu-id="67383-245">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="67383-246"><a name="BK_Postmigration"> </a></span><span class="sxs-lookup"><span data-stu-id="67383-246"><a name="BK_Postmigration"> </a></span></span>

- <span data-ttu-id="67383-247">**Skapa en DNS-post för automatisk upptäckt så att användarna enkelt kan komma till sina postlådor.**</span><span class="sxs-lookup"><span data-stu-id="67383-247">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="67383-248">När alla lokala post lådor har migrerats till Microsoft 365 kan du konfigurera en DNS-post för automatisk upptäckt för din Microsoft 365-organisation så att användarna enkelt kan ansluta till deras nya Microsoft 365-postlådor med Outlook-och mobila klienter.</span><span class="sxs-lookup"><span data-stu-id="67383-248">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="67383-249">Den nya DNS-posten Autodiscover måste använda samma namn område som du använder för din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="67383-249">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="67383-250">Om ditt molnbaserade namnområde till exempel är cloud.contoso.com, behöver du skapa DNS-posten autodiscover.cloud.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="67383-250">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>
    
    <span data-ttu-id="67383-251">I Microsoft 365 används en CNAME-post för att implementera tjänsten för automatisk upptäckt för Outlook och mobila klienter.</span><span class="sxs-lookup"><span data-stu-id="67383-251">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="67383-252">CNAME-posten för automatisk upptäckt måste innehålla följande information:</span><span class="sxs-lookup"><span data-stu-id="67383-252">The Autodiscover CNAME record must contain the following information:</span></span>
    
  - <span data-ttu-id="67383-253">**Alias:** autodiscover</span><span class="sxs-lookup"><span data-stu-id="67383-253">**Alias:** autodiscover</span></span>
    
  - <span data-ttu-id="67383-254">**Target:** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="67383-254">**Target:** autodiscover.outlook.com</span></span>
    
    <span data-ttu-id="67383-255">Mer information finns i [lägga till DNS-poster för att ansluta din domän](https://go.microsoft.com/fwlink/p/?LinkId=535028).</span><span class="sxs-lookup"><span data-stu-id="67383-255">For more information, see [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=535028).</span></span>
    
- <span data-ttu-id="67383-256">**Inaktivera lokala Exchange-servrar.**</span><span class="sxs-lookup"><span data-stu-id="67383-256">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="67383-257">När du har verifierat att all e-post dirigeras direkt till Microsoft 365-postlådor och du inte längre behöver underhålla din lokala e-postorganisation eller inte tänker implementera en SSO-lösning kan du avinstallera Exchange från dina servrar och ta bort din lokala Exchange-organisation.</span><span class="sxs-lookup"><span data-stu-id="67383-257">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing an SSO solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>
    
    <span data-ttu-id="67383-258">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="67383-258">For more information, see the following:</span></span>
    
  - [<span data-ttu-id="67383-259">Ändra eller ta bort Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="67383-259">Modify or Remove Exchange 2010</span></span>](https://go.microsoft.com/fwlink/?LinkId=217936)
    
  - [<span data-ttu-id="67383-260">Ta bort en Exchange 2007-organisation</span><span class="sxs-lookup"><span data-stu-id="67383-260">How to Remove an Exchange 2007 Organization</span></span>](https://go.microsoft.com/fwlink/?LinkID=100485)
    
  - [<span data-ttu-id="67383-261">Avinstallera Exchange Server 2003</span><span class="sxs-lookup"><span data-stu-id="67383-261">How to Uninstall Exchange Server 2003</span></span>](https://go.microsoft.com/fwlink/?LinkID=56561)
    

