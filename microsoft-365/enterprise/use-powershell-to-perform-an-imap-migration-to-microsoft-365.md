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
ms.openlocfilehash: fbfc0340e80ce70aa8a706d89a4d27729b91535b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924774"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a><span data-ttu-id="15523-103">Använda PowerShell för att utföra en IMAP-migrering till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="15523-103">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>

<span data-ttu-id="15523-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="15523-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="15523-105">Som en del av distributionen av Microsoft 365 kan du välja att migrera innehållet i användarpostlådor från en E-posttjänst med IMAP (Internet Mail Access Protocol) till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15523-105">As part of the process of deploying Microsoft 365, you can choose to migrate the contents of user mailboxes from an Internet Mail Access Protocol (IMAP) email service to Microsoft 365.</span></span> <span data-ttu-id="15523-106">I den här artikeln får du hjälp med uppgifterna för en IMAP-migrering av e-post med Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15523-106">This article walks you through the tasks for an email IMAP migration by using Exchange Online PowerShell.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="15523-107">Du kan också använda administrationscentret för Exchange för att utföra en IMAP-migrering.</span><span class="sxs-lookup"><span data-stu-id="15523-107">You can also use the Exchange admin center to perform an IMAP migration.</span></span> <span data-ttu-id="15523-108">Se [Migrera dina IMAP-postlådor.](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="15523-108">See [Migrate your IMAP mailboxes](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="15523-109">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="15523-109">What do you need to know before you begin?</span></span>

<span data-ttu-id="15523-110">Beräknad tid för att slutföra den här uppgiften: 2–5 minuter för att skapa en migreringsbatch.</span><span class="sxs-lookup"><span data-stu-id="15523-110">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="15523-111">När migreringsbatchen har startats varierar varaktigheten för migreringen beroende på antalet postlådor i batchen, storleken på varje postlåda och din tillgängliga nätverkskapacitet.</span><span class="sxs-lookup"><span data-stu-id="15523-111">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="15523-112">Information om andra faktorer som påverkar hur lång tid det tar att migrera postlådor till Microsoft 365 finns i [Migreringsprestanda.](/Exchange/mailbox-migration/office-365-migration-best-practices)</span><span class="sxs-lookup"><span data-stu-id="15523-112">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).</span></span>
  
<span data-ttu-id="15523-113">Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna.</span><span class="sxs-lookup"><span data-stu-id="15523-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="15523-114">Du kan se vilka behörigheter du behöver i migreringsposten i en tabell i [avsnittet Behörigheter för](/exchange/recipients-permissions-exchange-2013-help) mottagare.</span><span class="sxs-lookup"><span data-stu-id="15523-114">To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.</span></span>
  
<span data-ttu-id="15523-115">Om du vill använda Exchange Online PowerShell-cmdlets måste du logga in och importera cmdletarna till din lokala Windows PowerShell-session.</span><span class="sxs-lookup"><span data-stu-id="15523-115">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session.</span></span> <span data-ttu-id="15523-116">Instruktioner [finns i Ansluta till Exchange Online med fjärr-PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="15523-116">See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>
  
<span data-ttu-id="15523-117">En fullständig lista över migreringskommandon finns i [Flytta och migrera cmdlets.](/powershell/exchange/)</span><span class="sxs-lookup"><span data-stu-id="15523-117">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>
  
<span data-ttu-id="15523-118">Följande begränsningar gäller för IMAP-migreringar:</span><span class="sxs-lookup"><span data-stu-id="15523-118">The following restrictions apply to IMAP migrations:</span></span>
  
- <span data-ttu-id="15523-119">Endast objekt i en användares inkorg eller andra e-postmappar kan migreras.</span><span class="sxs-lookup"><span data-stu-id="15523-119">Only items in a user's inbox or other mail folders can be migrated.</span></span> <span data-ttu-id="15523-120">Du kan inte migrera kontakter, kalenderobjekt eller uppgifter.</span><span class="sxs-lookup"><span data-stu-id="15523-120">You can't migrate contacts, calendar items, or tasks.</span></span>
    
- <span data-ttu-id="15523-121">Maximalt 500 000 objekt kan migreras från en användares postlåda.</span><span class="sxs-lookup"><span data-stu-id="15523-121">A maximum of 500,000 items can be migrated from a user's mailbox.</span></span>
    
- <span data-ttu-id="15523-122">Maximal meddelandestorlek som kan migreras är 35 MB.</span><span class="sxs-lookup"><span data-stu-id="15523-122">The maximum message size that can be migrated is 35 MB.</span></span>
    
## <a name="migration-steps"></a><span data-ttu-id="15523-123">Migreringssteg</span><span class="sxs-lookup"><span data-stu-id="15523-123">Migration steps</span></span>

### <a name="step-1-prepare-for-an-imap-migration"></a><span data-ttu-id="15523-124">Steg 1: Förbereda en IMAP-migrering</span><span class="sxs-lookup"><span data-stu-id="15523-124">Step 1: Prepare for an IMAP migration</span></span>
<span data-ttu-id="15523-125"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="15523-125"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="15523-126">**Om du har en domän för din IMAP-organisation lägger du till den som en godkänd domän i din Microsoft 365-organisation.**</span><span class="sxs-lookup"><span data-stu-id="15523-126">**If you have a domain for you IMAP organization, add it as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="15523-127">Om du vill använda samma domän som du redan äger för dina Microsoft 365-postlådor måste du först lägga till den som en godkänd domän i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15523-127">If you want to use the same domain you already own for your Microsoft 365 mailboxes, you first have to add it as an accepted domain to Microsoft 365.</span></span> <span data-ttu-id="15523-128">När du har lagt till det kan du skapa dina användare i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15523-128">After you have added it, you can create your users in Microsoft 365.</span></span> <span data-ttu-id="15523-129">Mer information finns i[Verifiera din domän.](../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="15523-129">For more information, see[Verify your domain](../admin/setup/add-domain.md).</span></span>
    
- <span data-ttu-id="15523-130">**Lägg till alla användare i Microsoft 365 så att de har en postlåda.**</span><span class="sxs-lookup"><span data-stu-id="15523-130">**Add each user to Microsoft 365 so that they have a mailbox.**</span></span> <span data-ttu-id="15523-131">Anvisningar finns i Lägga[till användare i Microsoft 365 för företag.](../admin/add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="15523-131">For instructions, see[Add users to Microsoft 365 for business](../admin/add-users/add-users.md).</span></span>
    
- <span data-ttu-id="15523-132">**Hämta FQDN för IMAP-servern**.</span><span class="sxs-lookup"><span data-stu-id="15523-132">**Obtain the FQDN of the IMAP server**.</span></span> <span data-ttu-id="15523-133">Du måste ange det fullständiga kvalificerade domännamnet (FQDN) (det fullständiga datornamnet) för IMAP-servern som du ska migrera e-postdata från när du skapar en IMAP-migreringsslutpunkt.</span><span class="sxs-lookup"><span data-stu-id="15523-133">You need to provide the fully qualified domain name (FQDN) (also called the full computer name) of the IMAP server that you will migrate mailbox data from when you create an IMAP migration endpoint.</span></span> <span data-ttu-id="15523-134">Använd en IMAP-klient eller kommandot PING och kontrollera att du kan använda det fullständiga domännamnet för att kommunicera med IMAP-servern över Internet.</span><span class="sxs-lookup"><span data-stu-id="15523-134">Use an IMAP client or the PING command to verify that you can use the FQDN to communicate with the IMAP server over the Internet.</span></span>
    
- <span data-ttu-id="15523-135">**Konfigurera brandväggen så att IMAP-anslutningar tillåts.**</span><span class="sxs-lookup"><span data-stu-id="15523-135">**Configure the firewall to allow IMAP connections**.</span></span> <span data-ttu-id="15523-136">Du kanske måste öppna portar i brandväggen för den organisation som är värd för IMAP-servern så att nätverkstrafik som kommer från Microsoft-datacentret under migreringen tillåts att ange organisationen som är värd för IMAP-servern.</span><span class="sxs-lookup"><span data-stu-id="15523-136">You might have to open ports in the firewall of the organization that hosts the IMAP server so network traffic originating from the Microsoft datacenter during the migration is allowed to enter the organization that hosts the IMAP server.</span></span> <span data-ttu-id="15523-137">En lista över IP-adresser som används av Microsofts datacenter finns i [URL-adresser och IP-adressintervall för Exchange Online.](./urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="15523-137">For a list of IP addresses used by Microsoft datacenters, see [Exchange Online URLs and IP Address Ranges](./urls-and-ip-address-ranges.md).</span></span>
    
- <span data-ttu-id="15523-138">**Tilldela administratörskontobehörigheter för åtkomst till postlådor i din IMAP-organisation.**</span><span class="sxs-lookup"><span data-stu-id="15523-138">**Assign the administrator account permissions to access mailboxes in your IMAP organization**.</span></span> <span data-ttu-id="15523-139">Om du använder administratörsautentiseringsuppgifter i CSV-filen måste det konto som du använder ha nödvändig åtkomstbehörighet till de lokala postlådorna.</span><span class="sxs-lookup"><span data-stu-id="15523-139">If you use administrator credentials in the CSV file, the account that you use must have the necessary permissions to access the on-premises mailboxes.</span></span> <span data-ttu-id="15523-140">Vilka behörigheter som krävs för att få åtkomst till användarnas postlådor bestäms av den specifika IMAP-servern.</span><span class="sxs-lookup"><span data-stu-id="15523-140">The permissions required to access user mailboxes is determined by the particular IMAP server.</span></span> 
    
- <span data-ttu-id="15523-141">**Om du vill använda Exchange Online PowerShell-cmdlets** måste du logga in och importera cmdletarna till din lokala Windows PowerShell-session.</span><span class="sxs-lookup"><span data-stu-id="15523-141">**To use the Exchange Online PowerShell cmdlets**, you need to sign in and import the cmdlets into your local Windows PowerShell session.</span></span> <span data-ttu-id="15523-142">Instruktioner [finns i Ansluta till Exchange Online med fjärr-PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="15523-142">See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>
    
    <span data-ttu-id="15523-143">En fullständig lista över migreringskommandon finns i [Flytta och migrera cmdlets.](/powershell/exchange/)</span><span class="sxs-lookup"><span data-stu-id="15523-143">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>
    
- <span data-ttu-id="15523-144">**Kontrollera att du kan ansluta till din IMAP-server.**</span><span class="sxs-lookup"><span data-stu-id="15523-144">**Verify that you can connect to your IMAP server**.</span></span> <span data-ttu-id="15523-145">Kör följande kommando i Exchange Online PowerShell för att testa anslutningsinställningarna till din IMAP-server.</span><span class="sxs-lookup"><span data-stu-id="15523-145">Run the following command in Exchange Online PowerShell to test the connection settings to your IMAP server.</span></span>
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    <span data-ttu-id="15523-146">För parameterns  värde är det vanligt att använda 143 för okrypterade anslutningar eller TLS-anslutningar (Transport Layer Security) och att använda 993 för SSL-anslutningar.</span><span class="sxs-lookup"><span data-stu-id="15523-146">For the value of the **Port** parameter, it's typical to use 143 for unencrypted or Transport Layer Security (TLS) connections and to use 993 for SSL connections.</span></span>
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a><span data-ttu-id="15523-147">Steg 2: Skapa en CSV-fil för en IMAP-migreringsbatch</span><span class="sxs-lookup"><span data-stu-id="15523-147">Step 2: Create a CSV file for an IMAP migration batch</span></span>
<span data-ttu-id="15523-148"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="15523-148"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="15523-149">Identifiera den grupp användare vars postlådor du vill migrera i en IMAP-migreringsbatch.</span><span class="sxs-lookup"><span data-stu-id="15523-149">Identify the group of users whose mailboxes you want to migrate in an IMAP migration batch.</span></span> <span data-ttu-id="15523-150">Varje rad i CSV-filen innehåller information som behövs för att ansluta till en postlåda i IMAP-meddelandesystemet.</span><span class="sxs-lookup"><span data-stu-id="15523-150">Each row in the CSV file contains information necessary to connect to a mailbox in the IMAP messaging system.</span></span>
  
<span data-ttu-id="15523-151">Här är de obligatoriska attributen för varje användare:</span><span class="sxs-lookup"><span data-stu-id="15523-151">Here are the required attributes for each user:</span></span> 
  
- <span data-ttu-id="15523-152">**EmailAddress** anger användar-ID:t för användarens Microsoft 365-postlåda.</span><span class="sxs-lookup"><span data-stu-id="15523-152">**EmailAddress** specifies the user ID for the user's Microsoft 365 mailbox.</span></span>
    
- <span data-ttu-id="15523-153">**UserName** anger inloggningsnamnet för kontot som ska användas för att få åtkomst till postlådan på IMAP-servern.</span><span class="sxs-lookup"><span data-stu-id="15523-153">**UserName** specifies the logon name for the account to use to access the mailbox on the IMAP server.</span></span>
    
- <span data-ttu-id="15523-154">**Lösenord** anger lösenordet för kontot i **kolumnen Användarnamn.**</span><span class="sxs-lookup"><span data-stu-id="15523-154">**Password** specifies the password for the account in the **UserName** column.</span></span>
    
<span data-ttu-id="15523-155">Här följer ett exempel på CSV-filens format.</span><span class="sxs-lookup"><span data-stu-id="15523-155">Here's an example of the format for the CSV file.</span></span> <span data-ttu-id="15523-156">I det här exemplet migreras tre postlådor:</span><span class="sxs-lookup"><span data-stu-id="15523-156">In this example, three mailboxes are migrated:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

<span data-ttu-id="15523-157">För **attributet UserName** kan du, förutom användarnamnet, använda autentiseringsuppgifterna för ett konto som har tilldelats nödvändiga behörigheter för att komma åt postlådor på IMAP-servern. Nedan följer några av de specifika format som används för vissa IMAP-servrar:</span><span class="sxs-lookup"><span data-stu-id="15523-157">For the **UserName** attribute, in addition to the user name, you can use the credentials of an account that has been assigned the necessary permissions to access mailboxes on the IMAP server, the following are some of the specific formats used for some of the IMAP servers:</span></span>
  
 <span data-ttu-id="15523-158">**Microsoft Exchange:**</span><span class="sxs-lookup"><span data-stu-id="15523-158">**Microsoft Exchange:**</span></span>
  
<span data-ttu-id="15523-159">Om du migrerar e-post från IMAP-implementeringen för Microsoft Exchange använder du formatet **Domain/Admin_UserName/User_UserName** för attributet **UserName** i CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="15523-159">If you're migrating email from the IMAP implementation for Microsoft Exchange, use the format **Domain/Admin_UserName/User_UserName** for the **UserName** attribute in the CSV file.</span></span> <span data-ttu-id="15523-160">Säg att du migrerar e-post från Exchange för Terry Adams, Ann Beebe och Paul Cannon.</span><span class="sxs-lookup"><span data-stu-id="15523-160">Let's say you're migrating email from Exchange for Terry Adams, Ann Beebe, and Paul Cannon.</span></span> <span data-ttu-id="15523-161">Du har ett e-postadministratörskonto, där användarnamnet är **mailadmin** och lösenordet **är P \@ ssw0rd**.</span><span class="sxs-lookup"><span data-stu-id="15523-161">You have a mail administrator account, where the user name is **mailadmin** and the password is **P\@ssw0rd**.</span></span> <span data-ttu-id="15523-162">Så här skulle CSV-filen se ut:</span><span class="sxs-lookup"><span data-stu-id="15523-162">Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 <span data-ttu-id="15523-163">**Dovecot:**</span><span class="sxs-lookup"><span data-stu-id="15523-163">**Dovecot:**</span></span>
  
<span data-ttu-id="15523-164">För IMAP-servrar som stöder SASL (Simple Authentication and Security Layer), till exempel en Dovecot-IMAP-server, använder du formatet **User_UserName\*Admin_UserName**, där asterisken ( \* ) är ett konfigurerbart avgränsningstecken.</span><span class="sxs-lookup"><span data-stu-id="15523-164">For IMAP servers that support Simple Authentication and Security Layer (SASL), such as a Dovecot IMAP server, use the format **User_UserName\*Admin_UserName**, where the asterisk ( \* ) is a configurable separator character.</span></span> <span data-ttu-id="15523-165">Säg att du migrerar samma användares e-post från en Dovecot IMAP-server med administratörsautentiseringsuppgifterna **mailadmin** och **P \@ ssw0rd**.</span><span class="sxs-lookup"><span data-stu-id="15523-165">Let's say you're migrating those same users' email from a Dovecot IMAP server using the administrator credentials **mailadmin** and **P\@ssw0rd**.</span></span> <span data-ttu-id="15523-166">Så här skulle CSV-filen se ut:</span><span class="sxs-lookup"><span data-stu-id="15523-166">Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 <span data-ttu-id="15523-167">**Mirapoint:**</span><span class="sxs-lookup"><span data-stu-id="15523-167">**Mirapoint:**</span></span>
  
<span data-ttu-id="15523-168">Om du migrerar e-post från Mirapoint Message Server använder du formatet **#user \@ domän#Admin_UserName#** som administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="15523-168">If you're migrating email from Mirapoint Message Server, use the format **#user\@domain#Admin_UserName#** for the administrator credentials.</span></span> <span data-ttu-id="15523-169">Om du vill migrera e-post från Mirapoint med administratörsautentiseringsuppgifterna **mailadmin** och **P \@ ssw0rd** skulle CSV-filen se ut så här:</span><span class="sxs-lookup"><span data-stu-id="15523-169">To migrate email from Mirapoint using the administrator credentials **mailadmin** and **P\@ssw0rd**, your CSV file would look like this:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 <span data-ttu-id="15523-170">**Courier IMAP:**</span><span class="sxs-lookup"><span data-stu-id="15523-170">**Courier IMAP:**</span></span>
  
<span data-ttu-id="15523-171">Vissa käll-e-postsystem, till exempel Courier IMAP, stöder inte användning av autentiseringsuppgifter som administratör för postlådan för att migrera postlådor till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15523-171">Some source email systems, such as Courier IMAP, don't support using mailbox admin credentials to migrate mailboxes to Microsoft 365.</span></span> <span data-ttu-id="15523-172">I stället kan du konfigurera käll-e-postsystemet till att använda virtuella delade mappar.</span><span class="sxs-lookup"><span data-stu-id="15523-172">Instead, you can set up your source email system to use virtual shared folders.</span></span> <span data-ttu-id="15523-173">Genom att använda virtuella delade mappar kan du använda postlådans administratörsuppgifter för att få åtkomst till användarnas postlådor i käll-e-postsystemet.</span><span class="sxs-lookup"><span data-stu-id="15523-173">By using virtual shared folders, you can use the mailbox admin credentials to access user mailboxes on the source email system.</span></span> <span data-ttu-id="15523-174">Mer information om hur du konfigurerar virtuella delade mappar för Courier IMAP finns i [Delade mappar](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span><span class="sxs-lookup"><span data-stu-id="15523-174">For more information about how to configure virtual shared folders for Courier IMAP, see [Shared Folders](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span></span>
  
<span data-ttu-id="15523-175">Om du vill migrera postlådor när du har konfigurerat virtuella delade mappar på ditt käll-e-postsystem måste du ta med det valfria attributet **UserRoot** i migreringsfilen.</span><span class="sxs-lookup"><span data-stu-id="15523-175">To migrate mailboxes after you set up virtual shared folders on your source email system, you have to include the optional attribute **UserRoot** in the migration file.</span></span> <span data-ttu-id="15523-176">Attributet anger platsen för varje användares postlåda i strukturen med virtuella delade mappar på käll-e-postsystemet.</span><span class="sxs-lookup"><span data-stu-id="15523-176">This attribute specifies the location of each user's mailbox in the virtual shared folder structure on the source email system.</span></span> <span data-ttu-id="15523-177">Sökvägen till Terrys postlåda är till exempel /users/terry.adams.</span><span class="sxs-lookup"><span data-stu-id="15523-177">For example, the path to Terry's mailbox is /users/terry.adams.</span></span>
  
<span data-ttu-id="15523-178">Här är ett exempel på en CSV-fil som innehåller attributet **UserRoot**:</span><span class="sxs-lookup"><span data-stu-id="15523-178">Here's an example of a CSV file that contains the **UserRoot** attribute:</span></span>
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a><span data-ttu-id="15523-179">Steg 3: Skapa en IMAP-migreringsslutpunkt</span><span class="sxs-lookup"><span data-stu-id="15523-179">Step 3: Create an IMAP migration endpoint</span></span>
<span data-ttu-id="15523-180"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="15523-180"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="15523-181">För att e-post ska migreras måste Microsoft 365 ansluta till och kommunicera med käll-e-postsystemet.</span><span class="sxs-lookup"><span data-stu-id="15523-181">To migrate email successfully, Microsoft 365 needs to connect to and communicate with the source email system.</span></span> <span data-ttu-id="15523-182">För att göra det använder Microsoft 365 en migreringsslutpunkt.</span><span class="sxs-lookup"><span data-stu-id="15523-182">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="15523-183">Migreringsslutpunkten definierar också antalet postlådor som ska migreras samtidigt och antalet postlådor som ska synkroniseras samtidigt under stegvis synkronisering, som sker en gång per dygn.</span><span class="sxs-lookup"><span data-stu-id="15523-183">The migration endpoint also defines the number of mailboxes to migrate simultaneously and the number of mailboxes to synchronize simultaneously during incremental synchronization, which occurs once every 24 hours.</span></span> <span data-ttu-id="15523-184">Om du vill skapa en migreringsslutpunkt för IMAP-migrering [måste du först ansluta till Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="15523-184">To create a migration end point for IMAP migration, first [connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> 
  
<span data-ttu-id="15523-185">En fullständig lista över migreringskommandon finns i [Flytta och migrera cmdlets.](/powershell/exchange/)</span><span class="sxs-lookup"><span data-stu-id="15523-185">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>
  
<span data-ttu-id="15523-186">Om du vill skapa slutpunkten för IMAP-migrering som kallas "IMAPEndpoint" i Exchange Online PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="15523-186">To create the IMAP migration endpoint called "IMAPEndpoint" in Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

<span data-ttu-id="15523-187">Du kan också lägga till parametrar för att ange samtidig migrering, samtidig stegvis migrering och den port som ska användas.</span><span class="sxs-lookup"><span data-stu-id="15523-187">You can also add parameters to specify concurrent migrations, concurrent incremental migrations, and the port to use.</span></span> <span data-ttu-id="15523-188">Följande Exchange Online PowerShell-kommando skapar en IMAP-migreringsslutpunkt som kallas "IMAPEndpoint" som stöder 50 samtidiga migreringar och upp till 25 samtidiga stegvisa synkroniseringar.</span><span class="sxs-lookup"><span data-stu-id="15523-188">The following Exchange Online PowerShell command creates an IMAP migration endpoint called "IMAPEndpoint" that supports 50 concurrent migrations and up to 25 concurrent incremental synchronizations.</span></span> <span data-ttu-id="15523-189">Slutpunkten konfigureras också att använda port 143 för TLS-kryptering.</span><span class="sxs-lookup"><span data-stu-id="15523-189">It also configures the endpoint to use port 143 for TLS encryption.</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

<span data-ttu-id="15523-190">Mer information om **cmdleten New-MigrationEndpoint** finns i [New-MigrationEndpoint.](/powershell/module/exchange/new-migrationendpoint)</span><span class="sxs-lookup"><span data-stu-id="15523-190">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="15523-191">Kontrollera att det fungerade</span><span class="sxs-lookup"><span data-stu-id="15523-191">Verify it worked</span></span>

<span data-ttu-id="15523-192">Kör följande kommando i Exchange Online PowerShell för att visa information om "IMAPEndpoint":</span><span class="sxs-lookup"><span data-stu-id="15523-192">Run the following command in Exchange Online PowerShell to display information about the "IMAPEndpoint":</span></span>
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a><span data-ttu-id="15523-193">Steg 4: Skapa och starta en IMAP-migreringsbatch</span><span class="sxs-lookup"><span data-stu-id="15523-193">Step 4: Create and start an IMAP migration batch</span></span>
<span data-ttu-id="15523-194"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="15523-194"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="15523-195">Du kan använda cmdleten [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) för att skapa en migreringsbatch för en IMAP-migrering.</span><span class="sxs-lookup"><span data-stu-id="15523-195">You can use the [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) cmdlet to create a migration batch for an IMAP migration.</span></span> <span data-ttu-id="15523-196">Du kan skapa en migreringsbatch och starta den automatiskt genom att ta med _parametern AutoStart._</span><span class="sxs-lookup"><span data-stu-id="15523-196">You can create a migration batch and start it automatically by including the _AutoStart_ parameter.</span></span> <span data-ttu-id="15523-197">Alternativt kan du skapa migreringsbatchen och sedan starta den efteråt med hjälp av cmdleten[Start-MigrationBatch.](/powershell/module/exchange/start-migrationbatch)</span><span class="sxs-lookup"><span data-stu-id="15523-197">Alternatively, you can create the migration batch and then start it afterwards by using the[Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch) cmdlet.</span></span>
  
<span data-ttu-id="15523-198">Följande Exchange Online PowerShell-kommando startar automatiskt migreringsbatchen med namnet "IMAPBatch1" med hjälp av IMAP-slutpunkten som kallas "IMAPEndpoint":</span><span class="sxs-lookup"><span data-stu-id="15523-198">The following Exchange Online PowerShell command will automatically start the migration batch called "IMAPBatch1" using the IMAP endpoint called "IMAPEndpoint":</span></span>
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a><span data-ttu-id="15523-199">Kontrollera att det fungerade</span><span class="sxs-lookup"><span data-stu-id="15523-199">Verify it worked</span></span>

<span data-ttu-id="15523-200">Kör [cmdleten Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) för att visa information om "IMAPBatch1":</span><span class="sxs-lookup"><span data-stu-id="15523-200">Run the [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) cmdlet to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

<span data-ttu-id="15523-201">Du kan också kontrollera att batchen har startats genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="15523-201">You can also verify that the batch has started by running the following command:</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="15523-202">Steg 5: Dirigera din e-post till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="15523-202">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="15523-203"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="15523-203"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="15523-204">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span><span class="sxs-lookup"><span data-stu-id="15523-204">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="15523-205">Under e-postmigreringsprocessen pekade MX-posten på ditt käll-e-postsystem.</span><span class="sxs-lookup"><span data-stu-id="15523-205">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="15523-206">Nu när e-postmigrering till Microsoft 365 är klar är det dags att peka MX-posten på Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15523-206">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="15523-207">Då ser du till att e-posten levereras till dina Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="15523-207">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="15523-208">Genom att flytta MX-posten kan du också stänga av ditt gamla e-postsystem när du är redo.</span><span class="sxs-lookup"><span data-stu-id="15523-208">By moving the MX record, you can also turn off your old email system when you're ready.</span></span> 
  
<span data-ttu-id="15523-209">För många DNS-leverantörer finns det särskilda anvisningar för hur du ändrar MX-posten.</span><span class="sxs-lookup"><span data-stu-id="15523-209">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="15523-210">Om din DNS-leverantör inte finns med, eller om du bara [](https://go.microsoft.com/fwlink/?LinkId=397449) allmänt vill se hur anvisningarna ser ut, finns det även allmänna anvisningar för MX-posten.</span><span class="sxs-lookup"><span data-stu-id="15523-210">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions ](https://go.microsoft.com/fwlink/?LinkId=397449) are provided as well.</span></span>
  
<span data-ttu-id="15523-211">Det kan ta upp till 72 timmar innan dina kunder och partners e-postsystem känner igen den ändrade MX-posten.</span><span class="sxs-lookup"><span data-stu-id="15523-211">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record.</span></span> <span data-ttu-id="15523-212">Vänta i minst 72 timmar innan du går vidare till nästa uppgift: Steg 6: Ta bort IMAP-migreringsbatch.</span><span class="sxs-lookup"><span data-stu-id="15523-212">Wait at least 72 hours before you proceed to the next task: Step 6: Delete IMAP migration batch.</span></span> 
  
### <a name="step-6-delete-imap-migration-batch"></a><span data-ttu-id="15523-213">Steg 6: Ta bort IMAP-migreringsbatchen</span><span class="sxs-lookup"><span data-stu-id="15523-213">Step 6: Delete IMAP migration batch</span></span>
<span data-ttu-id="15523-214"><a name="BK_Step6"> </a></span><span class="sxs-lookup"><span data-stu-id="15523-214"><a name="BK_Step6"> </a></span></span>

<span data-ttu-id="15523-215">När du har ändrat MX-posten och verifierat att all e-post dirigeras till postlådor i Microsoft 365 informerar du användarna om att deras e-post kommer till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15523-215">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="15523-216">Därefter kan du ta bort IMAP-migreringsbatchen.</span><span class="sxs-lookup"><span data-stu-id="15523-216">After this, you can delete the IMAP migration batch.</span></span> <span data-ttu-id="15523-217">Kontrollera följande innan du tar bort migreringsbatchen.</span><span class="sxs-lookup"><span data-stu-id="15523-217">Verify the following before you delete the migration batch.</span></span>
  
- <span data-ttu-id="15523-218">Alla användare använder Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="15523-218">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="15523-219">När batchen har tagits bort kopieras inte e-post som skickas till postlådorna på den lokala Exchange Server till motsvarande Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="15523-219">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>
    
- <span data-ttu-id="15523-220">Microsoft 365-postlådor synkroniserades minst en gång efter att e-posten började skickas direkt till dem.</span><span class="sxs-lookup"><span data-stu-id="15523-220">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="15523-221">Det gör du genom att kontrollera att värdet i rutan Senaste synkronisering är senare än när e-posten började dirigeras direkt till Microsoft 365-postlådorna.</span><span class="sxs-lookup"><span data-stu-id="15523-221">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>
    
<span data-ttu-id="15523-222">Om du vill ta bort migreringsbatchen "IMAPBatch1" från Exchange Online PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="15523-222">To delete the "IMAPBatch1" migration batch from Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

<span data-ttu-id="15523-223">Mer information om cmdleten **Remove-MigrationBatch** finns i [Remove-MigrationBatch.](/powershell/module/exchange/remove-migrationbatch)</span><span class="sxs-lookup"><span data-stu-id="15523-223">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="15523-224">Kontrollera att det fungerade</span><span class="sxs-lookup"><span data-stu-id="15523-224">Verify it worked</span></span>

<span data-ttu-id="15523-225">Kör följande kommando i Exchange Online PowerShell för att visa information om "IMAPBatch1":</span><span class="sxs-lookup"><span data-stu-id="15523-225">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

<span data-ttu-id="15523-226">Kommandot returnerar antingen migreringsbatchen med statusen Ta **bort,** eller så returneras ett felmeddelande om att migreringsbatchen inte kunde hittas och verifierar att batchen har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="15523-226">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>
  
<span data-ttu-id="15523-227">Mer information om cmdleten **Get-MigrationBatch** finns i [Get-MigrationBatch.](/powershell/module/exchange/get-migrationbatch)</span><span class="sxs-lookup"><span data-stu-id="15523-227">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="15523-228">Se även</span><span class="sxs-lookup"><span data-stu-id="15523-228">See also</span></span>

[<span data-ttu-id="15523-229">Felsökare för IMAP-migrering</span><span class="sxs-lookup"><span data-stu-id="15523-229">IMAP Migration Troubleshooter</span></span>](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)