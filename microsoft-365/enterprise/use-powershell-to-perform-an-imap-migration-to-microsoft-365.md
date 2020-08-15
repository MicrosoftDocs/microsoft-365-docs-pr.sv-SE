---
title: Använda PowerShell för att utföra en IMAP-migrering till Microsoft 365
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
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: Lär dig hur du använder PowerShell för att utföra en IMAP-migrering (Internet Mail Access Protocol) till Microsoft 365.
ms.openlocfilehash: 6eb422455d0bdf31fa1859bd0231b68e5568748c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694738"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a><span data-ttu-id="fecdb-103">Använda PowerShell för att utföra en IMAP-migrering till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fecdb-103">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>

<span data-ttu-id="fecdb-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fecdb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fecdb-105">Som en del av processen med att distribuera Microsoft 365 kan du välja att migrera innehållet i användar post lådor från en e-posttjänst via IMAP (Internet Mail Access Protocol) till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fecdb-105">As part of the process of deploying Microsoft 365, you can choose to migrate the contents of user mailboxes from an Internet Mail Access Protocol (IMAP) email service to Microsoft 365.</span></span> <span data-ttu-id="fecdb-106">I den här artikeln får du stegvisa instruktioner för ett e-postmeddelande med IMAP-migrering genom att använda Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fecdb-106">This article walks you through the tasks for an email IMAP migration by using Exchange Online PowerShell.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fecdb-107">Du kan också använda administrations centret för Exchange för att utföra en IMAP-migrering.</span><span class="sxs-lookup"><span data-stu-id="fecdb-107">You can also use the Exchange admin center to perform an IMAP migration.</span></span> <span data-ttu-id="fecdb-108">Se [migrera dina IMAP-postlådor](https://go.microsoft.com/fwlink/p/?LinkId=536685).</span><span class="sxs-lookup"><span data-stu-id="fecdb-108">See [Migrate your IMAP mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=536685).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fecdb-109">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="fecdb-109">What do you need to know before you begin?</span></span>

<span data-ttu-id="fecdb-110">Uppskattad tid för att slutföra den här uppgiften: 2-5 minuter för att skapa en migreringstabell.</span><span class="sxs-lookup"><span data-stu-id="fecdb-110">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="fecdb-111">När migreringen har startat varierar varaktigheten för migreringen baserat på antalet post lådor i gruppen, storleken på varje post låda och din tillgängliga nätverks kapacitet.</span><span class="sxs-lookup"><span data-stu-id="fecdb-111">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="fecdb-112">Information om andra faktorer som påverkar hur lång tid det tar att migrera post lådor till Microsoft 365 finns i [migreringens prestanda](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span><span class="sxs-lookup"><span data-stu-id="fecdb-112">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span></span>
  
<span data-ttu-id="fecdb-113">Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna.</span><span class="sxs-lookup"><span data-stu-id="fecdb-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="fecdb-114">Om du vill se vilka behörigheter du behöver läser du "migration"-posten i en tabell i avsnittet [mottagare](https://go.microsoft.com/fwlink/p/?LinkId=534105) .</span><span class="sxs-lookup"><span data-stu-id="fecdb-114">To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](https://go.microsoft.com/fwlink/p/?LinkId=534105) topic.</span></span>
  
<span data-ttu-id="fecdb-115">För att använda PowerShell-cmdletar för Exchange Online måste du logga in och importera cmdletarna till din lokala Windows PowerShell-session.</span><span class="sxs-lookup"><span data-stu-id="fecdb-115">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session.</span></span> <span data-ttu-id="fecdb-116">Se [ansluta till Exchange Online med Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) för instruktioner.</span><span class="sxs-lookup"><span data-stu-id="fecdb-116">See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
  
<span data-ttu-id="fecdb-117">En fullständig lista över migreringsåtgärder finns i avsnittet [flytta och migrera cmdletar](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="fecdb-117">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="fecdb-118">Följande begränsningar gäller för IMAP-migreringar:</span><span class="sxs-lookup"><span data-stu-id="fecdb-118">The following restrictions apply to IMAP migrations:</span></span>
  
- <span data-ttu-id="fecdb-119">Endast objekt i en användares inkorg eller andra e-postmappar kan migreras.</span><span class="sxs-lookup"><span data-stu-id="fecdb-119">Only items in a user's inbox or other mail folders can be migrated.</span></span> <span data-ttu-id="fecdb-120">Du kan inte migrera kontakter, Kalender objekt eller uppgifter.</span><span class="sxs-lookup"><span data-stu-id="fecdb-120">You can't migrate contacts, calendar items, or tasks.</span></span>
    
- <span data-ttu-id="fecdb-121">Högst 500 000 objekt kan migreras från en användares post låda.</span><span class="sxs-lookup"><span data-stu-id="fecdb-121">A maximum of 500,000 items can be migrated from a user's mailbox.</span></span>
    
- <span data-ttu-id="fecdb-122">Maximal meddelande storlek som kan migreras är 35 MB.</span><span class="sxs-lookup"><span data-stu-id="fecdb-122">The maximum message size that can be migrated is 35 MB.</span></span>
    
## <a name="migration-steps"></a><span data-ttu-id="fecdb-123">Migreringsåtgärder</span><span class="sxs-lookup"><span data-stu-id="fecdb-123">Migration steps</span></span>

### <a name="step-1-prepare-for-an-imap-migration"></a><span data-ttu-id="fecdb-124">Steg 1: förbereda en IMAP-migrering</span><span class="sxs-lookup"><span data-stu-id="fecdb-124">Step 1: Prepare for an IMAP migration</span></span>
<span data-ttu-id="fecdb-125"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="fecdb-125"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="fecdb-126">**Om du har en domän för IMAP-organisation lägger du till den som en godkänd domän i din Microsoft 365-organisation.**</span><span class="sxs-lookup"><span data-stu-id="fecdb-126">**If you have a domain for you IMAP organization, add it as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="fecdb-127">Om du vill använda samma domän som du redan äger för dina Microsoft 365-postlådor måste du först lägga till den som godkänd domän i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fecdb-127">If you want to use the same domain you already own for your Microsoft 365 mailboxes, you first have to add it as an accepted domain to Microsoft 365.</span></span> <span data-ttu-id="fecdb-128">När du har lagt till den kan du skapa användare i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fecdb-128">After you have added it, you can create your users in Microsoft 365.</span></span> <span data-ttu-id="fecdb-129">Mer information finns i[Verifiera din domän](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span><span class="sxs-lookup"><span data-stu-id="fecdb-129">For more information, see[Verify your domain](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span></span>
    
- <span data-ttu-id="fecdb-130">**Lägg till varje användare i Microsoft 365 så att de har en post låda.**</span><span class="sxs-lookup"><span data-stu-id="fecdb-130">**Add each user to Microsoft 365 so that they have a mailbox.**</span></span> <span data-ttu-id="fecdb-131">Anvisningar finns i[lägga till användare i Microsoft 365 för företag](https://go.microsoft.com/fwlink/p/?LinkId=535065).</span><span class="sxs-lookup"><span data-stu-id="fecdb-131">For instructions, see[Add users to Microsoft 365 for business](https://go.microsoft.com/fwlink/p/?LinkId=535065).</span></span>
    
- <span data-ttu-id="fecdb-132">**Skaffa IMAP-serverns FQDN**.</span><span class="sxs-lookup"><span data-stu-id="fecdb-132">**Obtain the FQDN of the IMAP server**.</span></span> <span data-ttu-id="fecdb-133">Du måste ange det fullständigt kvalificerade domän namnet (FQDN) (kallas även det fullständiga dator namnet) för IMAP-servern som du migrerar post lådor från när du skapar en slut punkt för IMAP-migrering.</span><span class="sxs-lookup"><span data-stu-id="fecdb-133">You need to provide the fully qualified domain name (FQDN) (also called the full computer name) of the IMAP server that you will migrate mailbox data from when you create an IMAP migration endpoint.</span></span> <span data-ttu-id="fecdb-134">Använd en IMAP-klient eller kommandot PING och kontrollera att du kan använda det fullständiga domännamnet för att kommunicera med IMAP-servern över Internet.</span><span class="sxs-lookup"><span data-stu-id="fecdb-134">Use an IMAP client or the PING command to verify that you can use the FQDN to communicate with the IMAP server over the Internet.</span></span>
    
- <span data-ttu-id="fecdb-135">**Konfigurera brand väggen för att tillåta IMAP-anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="fecdb-135">**Configure the firewall to allow IMAP connections**.</span></span> <span data-ttu-id="fecdb-136">Du kanske måste öppna portar i brand väggen för organisationen som är värd för IMAP-servern så att nätverks trafik från Microsoft-datacentret under migreringen tillåts ange den organisation som är värd för IMAP-servern.</span><span class="sxs-lookup"><span data-stu-id="fecdb-136">You might have to open ports in the firewall of the organization that hosts the IMAP server so network traffic originating from the Microsoft datacenter during the migration is allowed to enter the organization that hosts the IMAP server.</span></span> <span data-ttu-id="fecdb-137">En lista med IP-adresser som används av Microsoft Data Center finns i [URL: er och IP-adressintervall för Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=535066).</span><span class="sxs-lookup"><span data-stu-id="fecdb-137">For a list of IP addresses used by Microsoft datacenters, see [Exchange Online URLs and IP Address Ranges](https://go.microsoft.com/fwlink/p/?LinkId=535066).</span></span>
    
- <span data-ttu-id="fecdb-138">**Tilldela administratörs konto behörigheter till post lådor i IMAP-organisationen**.</span><span class="sxs-lookup"><span data-stu-id="fecdb-138">**Assign the administrator account permissions to access mailboxes in your IMAP organization**.</span></span> <span data-ttu-id="fecdb-139">Om du använder administratörsautentiseringsuppgifter i CSV-filen måste det konto som du använder ha nödvändig åtkomstbehörighet till de lokala postlådorna.</span><span class="sxs-lookup"><span data-stu-id="fecdb-139">If you use administrator credentials in the CSV file, the account that you use must have the necessary permissions to access the on-premises mailboxes.</span></span> <span data-ttu-id="fecdb-140">De behörigheter som krävs för att komma åt användar post lådorna bestäms av den specifika IMAP-servern.</span><span class="sxs-lookup"><span data-stu-id="fecdb-140">The permissions required to access user mailboxes is determined by the particular IMAP server.</span></span> 
    
- <span data-ttu-id="fecdb-141">**För att använda PowerShell-cmdletar för Exchange Online**måste du logga in och importera cmdletarna till din lokala Windows PowerShell-session.</span><span class="sxs-lookup"><span data-stu-id="fecdb-141">**To use the Exchange Online PowerShell cmdlets**, you need to sign in and import the cmdlets into your local Windows PowerShell session.</span></span> <span data-ttu-id="fecdb-142">Se [ansluta till Exchange Online med Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) för instruktioner.</span><span class="sxs-lookup"><span data-stu-id="fecdb-142">See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
    
    <span data-ttu-id="fecdb-143">En fullständig lista över migreringsåtgärder finns i avsnittet [flytta och migrera cmdletar](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="fecdb-143">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
    
- <span data-ttu-id="fecdb-144">**Kontrol lera att du kan ansluta till IMAP-servern**.</span><span class="sxs-lookup"><span data-stu-id="fecdb-144">**Verify that you can connect to your IMAP server**.</span></span> <span data-ttu-id="fecdb-145">Kör följande kommando i Exchange Online PowerShell för att testa anslutnings inställningarna till IMAP-servern.</span><span class="sxs-lookup"><span data-stu-id="fecdb-145">Run the following command in Exchange Online PowerShell to test the connection settings to your IMAP server.</span></span>
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    <span data-ttu-id="fecdb-146">För värdet på parametern **port** är det normalt att använda 143 för okrypterade eller TLS-anslutningar (Transport Layer Security) och för att använda 993 för SSL-anslutningar.</span><span class="sxs-lookup"><span data-stu-id="fecdb-146">For the value of the **Port** parameter, it's typical to use 143 for unencrypted or Transport Layer Security (TLS) connections and to use 993 for SSL connections.</span></span>
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a><span data-ttu-id="fecdb-147">Steg 2: skapa en CSV-fil för en IMAP-migrering</span><span class="sxs-lookup"><span data-stu-id="fecdb-147">Step 2: Create a CSV file for an IMAP migration batch</span></span>
<span data-ttu-id="fecdb-148"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="fecdb-148"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="fecdb-149">Identifiera gruppen med användare vars post lådor du vill migrera i ett batchjobb för IMAP-migrering.</span><span class="sxs-lookup"><span data-stu-id="fecdb-149">Identify the group of users whose mailboxes you want to migrate in an IMAP migration batch.</span></span> <span data-ttu-id="fecdb-150">Varje rad i CSV-filen innehåller information som behövs för att ansluta till en post låda i IMAP Messaging system.</span><span class="sxs-lookup"><span data-stu-id="fecdb-150">Each row in the CSV file contains information necessary to connect to a mailbox in the IMAP messaging system.</span></span>
  
<span data-ttu-id="fecdb-151">Här är de obligatoriska attributen för varje användare:</span><span class="sxs-lookup"><span data-stu-id="fecdb-151">Here are the required attributes for each user:</span></span> 
  
- <span data-ttu-id="fecdb-152">**EmailAddress** anger användar-ID: t för användarens Microsoft 365-postlåda.</span><span class="sxs-lookup"><span data-stu-id="fecdb-152">**EmailAddress** specifies the user ID for the user's Microsoft 365 mailbox.</span></span>
    
- <span data-ttu-id="fecdb-153">**Username** anger namnet på det konto som ska användas för att komma åt post lådan på IMAP-servern.</span><span class="sxs-lookup"><span data-stu-id="fecdb-153">**UserName** specifies the logon name for the account to use to access the mailbox on the IMAP server.</span></span>
    
- <span data-ttu-id="fecdb-154">**Lösen ord** anger lösen ordet för kontot i kolumnen **username** .</span><span class="sxs-lookup"><span data-stu-id="fecdb-154">**Password** specifies the password for the account in the **UserName** column.</span></span>
    
<span data-ttu-id="fecdb-155">Här följer ett exempel på CSV-filens format.</span><span class="sxs-lookup"><span data-stu-id="fecdb-155">Here's an example of the format for the CSV file.</span></span> <span data-ttu-id="fecdb-156">I det här exemplet migreras tre post lådor:</span><span class="sxs-lookup"><span data-stu-id="fecdb-156">In this example, three mailboxes are migrated:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

<span data-ttu-id="fecdb-157">För attributet **username** kan du förutom användar namnet använda autentiseringsuppgifterna för ett konto som har tilldelats nödvändiga behörigheter för att komma åt post lådor på IMAP-servern, men följande är några av de specifika format som används för vissa IMAP-servrar:</span><span class="sxs-lookup"><span data-stu-id="fecdb-157">For the **UserName** attribute, in addition to the user name, you can use the credentials of an account that has been assigned the necessary permissions to access mailboxes on the IMAP server, the following are some of the specific formats used for some of the IMAP servers:</span></span>
  
 <span data-ttu-id="fecdb-158">**Microsoft Exchange:**</span><span class="sxs-lookup"><span data-stu-id="fecdb-158">**Microsoft Exchange:**</span></span>
  
<span data-ttu-id="fecdb-159">Om du migrerar e-post från IMAP-implementeringen för Microsoft Exchange använder du formatet **Domain/Admin_UserName/User_UserName** för attributet **UserName** i CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="fecdb-159">If you're migrating email from the IMAP implementation for Microsoft Exchange, use the format **Domain/Admin_UserName/User_UserName** for the **UserName** attribute in the CSV file.</span></span> <span data-ttu-id="fecdb-160">Säg att du migrerar e-post från Exchange för Terry Adams, Ann Beebe och Paul Cannon.</span><span class="sxs-lookup"><span data-stu-id="fecdb-160">Let's say you're migrating email from Exchange for Terry Adams, Ann Beebe, and Paul Cannon.</span></span> <span data-ttu-id="fecdb-161">Du har ett e-postadministratörs konto med användar namnet **administratör** och lösen ordet är **P@ssw0rd**.</span><span class="sxs-lookup"><span data-stu-id="fecdb-161">You have a mail administrator account, where the user name is **mailadmin** and the password is **P@ssw0rd**.</span></span> <span data-ttu-id="fecdb-162">Så här skulle CSV-filen se ut:</span><span class="sxs-lookup"><span data-stu-id="fecdb-162">Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 <span data-ttu-id="fecdb-163">**Dovecot:**</span><span class="sxs-lookup"><span data-stu-id="fecdb-163">**Dovecot:**</span></span>
  
<span data-ttu-id="fecdb-164">För IMAP-servrar som stöder enkel inloggningsautentisering och säkerhets skikt (SASL), till exempel en Dovecot IMAP-server, använder du formatet **User_UserName \* Admin_UserName**, där asterisken (\*) är ett konfigurerbart avgränsnings tecken.</span><span class="sxs-lookup"><span data-stu-id="fecdb-164">For IMAP servers that support Simple Authentication and Security Layer (SASL), such as a Dovecot IMAP server, use the format **User_UserName\*Admin_UserName**, where the asterisk ( \* ) is a configurable separator character.</span></span> <span data-ttu-id="fecdb-165">Låt oss säga att du migrerar samma användares e-post från en Dovecot IMAP-server med **Administratörs** behörighet för administratörer och **P@ssw0rd**.</span><span class="sxs-lookup"><span data-stu-id="fecdb-165">Let's say you're migrating those same users' email from a Dovecot IMAP server using the administrator credentials **mailadmin** and **P@ssw0rd**.</span></span> <span data-ttu-id="fecdb-166">Så här skulle CSV-filen se ut:</span><span class="sxs-lookup"><span data-stu-id="fecdb-166">Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 <span data-ttu-id="fecdb-167">**Mirapoint**</span><span class="sxs-lookup"><span data-stu-id="fecdb-167">**Mirapoint:**</span></span>
  
<span data-ttu-id="fecdb-168">Om du migrerar e-post från Mirapoint Message Server använder du formatet **#user@domain#Admin_UserName#** för administratörsautentiseringsuppgifterna.</span><span class="sxs-lookup"><span data-stu-id="fecdb-168">If you're migrating email from Mirapoint Message Server, use the format **#user@domain#Admin_UserName#** for the administrator credentials.</span></span> <span data-ttu-id="fecdb-169">Om du vill migrera e-post från Mirapoint **med administratörs-och** **P@ssw0rd**för administratörer kan CSV-filen se ut så här:</span><span class="sxs-lookup"><span data-stu-id="fecdb-169">To migrate email from Mirapoint using the administrator credentials **mailadmin** and **P@ssw0rd**, your CSV file would look like this:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 <span data-ttu-id="fecdb-170">**Courier IMAP:**</span><span class="sxs-lookup"><span data-stu-id="fecdb-170">**Courier IMAP:**</span></span>
  
<span data-ttu-id="fecdb-171">Vissa käll-e-postsystem, till exempel Courier IMAP, stöder inte användning av administratörsautentiseringsuppgifter för att migrera post lådor till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fecdb-171">Some source email systems, such as Courier IMAP, don't support using mailbox admin credentials to migrate mailboxes to Microsoft 365.</span></span> <span data-ttu-id="fecdb-172">I stället kan du konfigurera käll-e-postsystemet till att använda virtuella delade mappar.</span><span class="sxs-lookup"><span data-stu-id="fecdb-172">Instead, you can set up your source email system to use virtual shared folders.</span></span> <span data-ttu-id="fecdb-173">Genom att använda virtuella delade mappar kan du använda administratörsautentiseringsuppgifter för att komma åt användar post lådor i e-postsystemet.</span><span class="sxs-lookup"><span data-stu-id="fecdb-173">By using virtual shared folders, you can use the mailbox admin credentials to access user mailboxes on the source email system.</span></span> <span data-ttu-id="fecdb-174">Mer information om hur du konfigurerar virtuella delade mappar för Courier IMAP finns i [Delade mappar](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span><span class="sxs-lookup"><span data-stu-id="fecdb-174">For more information about how to configure virtual shared folders for Courier IMAP, see [Shared Folders](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span></span>
  
<span data-ttu-id="fecdb-175">Om du vill migrera postlådor när du har konfigurerat virtuella delade mappar på ditt käll-e-postsystem måste du ta med det valfria attributet **UserRoot** i migreringsfilen.</span><span class="sxs-lookup"><span data-stu-id="fecdb-175">To migrate mailboxes after you set up virtual shared folders on your source email system, you have to include the optional attribute **UserRoot** in the migration file.</span></span> <span data-ttu-id="fecdb-176">Attributet anger platsen för varje användares postlåda i strukturen med virtuella delade mappar på käll-e-postsystemet.</span><span class="sxs-lookup"><span data-stu-id="fecdb-176">This attribute specifies the location of each user's mailbox in the virtual shared folder structure on the source email system.</span></span> <span data-ttu-id="fecdb-177">Till exempel är sökvägen till Terrys post låda/Users/Terry.Adams.</span><span class="sxs-lookup"><span data-stu-id="fecdb-177">For example, the path to Terry's mailbox is /users/terry.adams.</span></span>
  
<span data-ttu-id="fecdb-178">Här är ett exempel på en CSV-fil som innehåller attributet **UserRoot**:</span><span class="sxs-lookup"><span data-stu-id="fecdb-178">Here's an example of a CSV file that contains the **UserRoot** attribute:</span></span>
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a><span data-ttu-id="fecdb-179">Steg 3: skapa en slut punkt för en IMAP-migrering</span><span class="sxs-lookup"><span data-stu-id="fecdb-179">Step 3: Create an IMAP migration endpoint</span></span>
<span data-ttu-id="fecdb-180"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="fecdb-180"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="fecdb-181">För att migrera e-post måste Microsoft 365 ansluta till och kommunicera med käll-e-postsystemet.</span><span class="sxs-lookup"><span data-stu-id="fecdb-181">To migrate email successfully, Microsoft 365 needs to connect to and communicate with the source email system.</span></span> <span data-ttu-id="fecdb-182">För att göra det, använder Microsoft 365 en slut punkt för migrering.</span><span class="sxs-lookup"><span data-stu-id="fecdb-182">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="fecdb-183">Slut punkten för migreringen definierar också antalet post lådor som ska migreras samtidigt och antalet post lådor som synkroniseras samtidigt under stegvis synkronisering, vilket inträffar en gång var 24: e timme.</span><span class="sxs-lookup"><span data-stu-id="fecdb-183">The migration endpoint also defines the number of mailboxes to migrate simultaneously and the number of mailboxes to synchronize simultaneously during incremental synchronization, which occurs once every 24 hours.</span></span> <span data-ttu-id="fecdb-184">[Anslut först till Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121)för att skapa en slut punkt för migrering för IMAP-migrering.</span><span class="sxs-lookup"><span data-stu-id="fecdb-184">To create a migration end point for IMAP migration, first [connect to Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span></span> 
  
<span data-ttu-id="fecdb-185">En fullständig lista över migreringsåtgärder finns i avsnittet [flytta och migrera cmdletar](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="fecdb-185">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="fecdb-186">Om du vill skapa IMAP-migreringens slut punkt med namnet "IMAPEndpoint" i Exchange Online PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="fecdb-186">To create the IMAP migration endpoint called "IMAPEndpoint" in Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

<span data-ttu-id="fecdb-187">Du kan också lägga till parametrar för att ange samtidiga migreringar, stegvisa inkrementella migreringar och vilken port som ska användas.</span><span class="sxs-lookup"><span data-stu-id="fecdb-187">You can also add parameters to specify concurrent migrations, concurrent incremental migrations, and the port to use.</span></span> <span data-ttu-id="fecdb-188">Med följande Exchange Online PowerShell-kommando skapas en Endpoint-slutpunkt med namnet "IMAPEndpoint" som har stöd för 50-samtidiga migreringar och upp till 25 samtidiga inkrementella synkroniseringar.</span><span class="sxs-lookup"><span data-stu-id="fecdb-188">The following Exchange Online PowerShell command creates an IMAP migration endpoint called "IMAPEndpoint" that supports 50 concurrent migrations and up to 25 concurrent incremental synchronizations.</span></span> <span data-ttu-id="fecdb-189">Den konfigurerar också slut punkten så att port 143 används för TLS-kryptering.</span><span class="sxs-lookup"><span data-stu-id="fecdb-189">It also configures the endpoint to use port 143 for TLS encryption.</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

<span data-ttu-id="fecdb-190">Mer information om **New-MigrationEndpoint** -cmdleten finns i[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).</span><span class="sxs-lookup"><span data-stu-id="fecdb-190">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="fecdb-191">Verifiera att den fungerade</span><span class="sxs-lookup"><span data-stu-id="fecdb-191">Verify it worked</span></span>

<span data-ttu-id="fecdb-192">Kör följande kommando i Exchange Online PowerShell för att visa information om "IMAPEndpoint":</span><span class="sxs-lookup"><span data-stu-id="fecdb-192">Run the following command in Exchange Online PowerShell to display information about the "IMAPEndpoint":</span></span>
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a><span data-ttu-id="fecdb-193">Steg 4: skapa och starta en batch för IMAP-migrering</span><span class="sxs-lookup"><span data-stu-id="fecdb-193">Step 4: Create and start an IMAP migration batch</span></span>
<span data-ttu-id="fecdb-194"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="fecdb-194"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="fecdb-195">Du kan använda cmdleten [New-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536439) för att skapa en migreringstabell för en IMAP-migrering.</span><span class="sxs-lookup"><span data-stu-id="fecdb-195">You can use the [New-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536439) cmdlet to create a migration batch for an IMAP migration.</span></span> <span data-ttu-id="fecdb-196">Du kan skapa en migreringstabell och starta den automatiskt genom att inkludera _Autostart_ -parametern.</span><span class="sxs-lookup"><span data-stu-id="fecdb-196">You can create a migration batch and start it automatically by including the _AutoStart_ parameter.</span></span> <span data-ttu-id="fecdb-197">Alternativt kan du skapa migreringstabellen och sedan starta den efteråt med hjälp av cmdleten[Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440) .</span><span class="sxs-lookup"><span data-stu-id="fecdb-197">Alternatively, you can create the migration batch and then start it afterwards by using the[Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440) cmdlet.</span></span>
  
<span data-ttu-id="fecdb-198">Med följande Exchange Online PowerShell-kommando startas migreringsverktyget automatiskt för "IMAPBatch1" med IMAP-slutpunkten "IMAPEndpoint":</span><span class="sxs-lookup"><span data-stu-id="fecdb-198">The following Exchange Online PowerShell command will automatically start the migration batch called "IMAPBatch1" using the IMAP endpoint called "IMAPEndpoint":</span></span>
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a><span data-ttu-id="fecdb-199">Verifiera att den fungerade</span><span class="sxs-lookup"><span data-stu-id="fecdb-199">Verify it worked</span></span>

<span data-ttu-id="fecdb-200">Kör cmdleten [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441) för att visa information om "IMAPBatch1":</span><span class="sxs-lookup"><span data-stu-id="fecdb-200">Run the [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441) cmdlet to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

<span data-ttu-id="fecdb-201">Du kan också kontrol lera att batchjobbet har startat genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="fecdb-201">You can also verify that the batch has started by running the following command:</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="fecdb-202">Steg 5: dirigera din e-post till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fecdb-202">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="fecdb-203"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="fecdb-203"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="fecdb-204">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span><span class="sxs-lookup"><span data-stu-id="fecdb-204">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="fecdb-205">Under e-postmigreringen pekar din MX-post på ditt käll-e-postsystem.</span><span class="sxs-lookup"><span data-stu-id="fecdb-205">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="fecdb-206">Nu när e-postmigreringen till Microsoft 365 är klar är det dags att skicka MX-posten på Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fecdb-206">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="fecdb-207">Då ser du till att e-post skickas till dina Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="fecdb-207">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="fecdb-208">Genom att flytta MX-posten kan du även inaktivera det gamla e-postsystemet när du är klar.</span><span class="sxs-lookup"><span data-stu-id="fecdb-208">By moving the MX record, you can also turn off your old email system when you're ready.</span></span> 
  
<span data-ttu-id="fecdb-209">För många DNS-leverantörer finns det särskilda anvisningar för hur du ändrar MX-posten.</span><span class="sxs-lookup"><span data-stu-id="fecdb-209">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="fecdb-210">Om din DNS-leverantör inte är inkluderad, eller om du vill ha en uppfattning om de allmänna anvisningarna, kan du också få [allmänna MX Record-instruktioner ](https://go.microsoft.com/fwlink/?LinkId=397449) .</span><span class="sxs-lookup"><span data-stu-id="fecdb-210">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions ](https://go.microsoft.com/fwlink/?LinkId=397449) are provided as well.</span></span>
  
<span data-ttu-id="fecdb-211">Det kan ta upp till 72 timmar innan dina kunder och partners e-postsystem känner igen den ändrade MX-posten.</span><span class="sxs-lookup"><span data-stu-id="fecdb-211">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record.</span></span> <span data-ttu-id="fecdb-212">Vänta minst 72 timmar innan du går vidare till nästa uppgift: steg 6: ta bort ett batchjobb för IMAP-migrering.</span><span class="sxs-lookup"><span data-stu-id="fecdb-212">Wait at least 72 hours before you proceed to the next task: Step 6: Delete IMAP migration batch.</span></span> 
  
### <a name="step-6-delete-imap-migration-batch"></a><span data-ttu-id="fecdb-213">Steg 6: ta bort en batch för IMAP-migrering</span><span class="sxs-lookup"><span data-stu-id="fecdb-213">Step 6: Delete IMAP migration batch</span></span>
<span data-ttu-id="fecdb-214"><a name="BK_Step6"> </a></span><span class="sxs-lookup"><span data-stu-id="fecdb-214"><a name="BK_Step6"> </a></span></span>

<span data-ttu-id="fecdb-215">När du har ändrat MX-posten och kontrollerat att all e-post dirigeras till Microsoft 365-postlådor och meddelar användarna att deras e-post ska skickas till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fecdb-215">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="fecdb-216">Därefter kan du ta bort batchen för IMAP-migrering.</span><span class="sxs-lookup"><span data-stu-id="fecdb-216">After this, you can delete the IMAP migration batch.</span></span> <span data-ttu-id="fecdb-217">Kontrollera följande innan du tar bort migreringsbatchen.</span><span class="sxs-lookup"><span data-stu-id="fecdb-217">Verify the following before you delete the migration batch.</span></span>
  
- <span data-ttu-id="fecdb-218">Alla användare använder Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="fecdb-218">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="fecdb-219">När du har tagit bort gruppen kopieras inte e-post till post lådor på den lokala Exchange-servern till motsvarande Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="fecdb-219">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>
    
- <span data-ttu-id="fecdb-220">Microsoft 365-postlådor synkroniserades minst en gång efter att e-post började skickas direkt till dem.</span><span class="sxs-lookup"><span data-stu-id="fecdb-220">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="fecdb-221">Det gör du genom att se till att värdet i rutan för den senast synkroniserade tiden för migreringstabellen är senare än när e-post som har börjat dirigeras direkt till Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="fecdb-221">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>
    
<span data-ttu-id="fecdb-222">Om du vill ta bort IMAPBatch1 i Exchange Online PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="fecdb-222">To delete the "IMAPBatch1" migration batch from Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

<span data-ttu-id="fecdb-223">Mer information om cmdleten **Remove-MigrationBatch** finns i[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span><span class="sxs-lookup"><span data-stu-id="fecdb-223">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="fecdb-224">Verifiera att den fungerade</span><span class="sxs-lookup"><span data-stu-id="fecdb-224">Verify it worked</span></span>

<span data-ttu-id="fecdb-225">Kör följande kommando i Exchange Online PowerShell för att visa information om "IMAPBatch1":</span><span class="sxs-lookup"><span data-stu-id="fecdb-225">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

<span data-ttu-id="fecdb-226">Kommandot returnerar antingen migreringsarkivet med **statusen borttagen**eller returnerar ett fel meddelande som säger att det inte gick att hitta den Överflyttnings journal som verifierar att gruppen har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="fecdb-226">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>
  
<span data-ttu-id="fecdb-227">Mer information om cmdleten **Get-MigrationBatch** finns i[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span><span class="sxs-lookup"><span data-stu-id="fecdb-227">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fecdb-228">Se även</span><span class="sxs-lookup"><span data-stu-id="fecdb-228">See also</span></span>

[<span data-ttu-id="fecdb-229">Fel sökning för IMAP-migrering</span><span class="sxs-lookup"><span data-stu-id="fecdb-229">IMAP Migration Troubleshooter</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536482)

