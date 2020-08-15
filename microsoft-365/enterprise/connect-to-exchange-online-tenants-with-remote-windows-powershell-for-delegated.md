---
title: Ansluta till Exchange Online-klient organisationer med Windows PowerShell för DAP partners
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: ''
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
ms.assetid: ae5f1a87-8b77-4f93-a1b8-56f800aeb283
description: 'Sammanfattning: Använd Windows PowerShell för att ansluta till Exchange Online genom att använda DelegatedOrg-värdet.'
ms.openlocfilehash: 1351a6a6d19fac408b673796c1179bca0ede9c9f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694673"
---
# <a name="connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="b36f5-103">Ansluta till Exchange Online-klient organisationer med Windows PowerShell-partner för delegerade åtkomst behörigheter (DAP)</span><span class="sxs-lookup"><span data-stu-id="b36f5-103">Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="b36f5-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b36f5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b36f5-105">Procedurerna i det här avsnittet gäller endast för DAP-partners (delegerade åtkomst behörigheter).</span><span class="sxs-lookup"><span data-stu-id="b36f5-105">The procedures in this topic are only for Delegated Access Permission (DAP) partners.</span></span> <span data-ttu-id="b36f5-106">Om du inte är en DAP-partner, Använd inte procedurerna i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="b36f5-106">If you aren't a DAP partner, don't use the procedures in this topic.</span></span> 
  
<span data-ttu-id="b36f5-107">DAP partners är syndikerings-och Cloud solution providers (CSP)-partners.</span><span class="sxs-lookup"><span data-stu-id="b36f5-107">DAP partners are Syndication and Cloud Solution Providers (CSP) partners.</span></span> <span data-ttu-id="b36f5-108">De är ofta nätverks-eller Telekom-leverantörer i andra företag.</span><span class="sxs-lookup"><span data-stu-id="b36f5-108">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="b36f5-109">De kan skicka abonnemang till sina tjänster till sina kunder.</span><span class="sxs-lookup"><span data-stu-id="b36f5-109">They bundle subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="b36f5-110">De äger en partner innehavaren som automatiskt ges tillstånd att administrera (AOBO) till sina Microsoft 365-kund innehavare så att de kan administrera och rapportera om sina kund innehavare.</span><span class="sxs-lookup"><span data-stu-id="b36f5-110">They own a partner tenancy that is automatically granted Administer On Behalf Of (AOBO) permissions to their Microsoft 365 customer tenancies so they can administer and report on all of their customer tenancies.</span></span>

<span data-ttu-id="b36f5-111">DAP partners kan använda Exchange Online PowerShell för att hantera inställningar för kund Exchange Online och få Microsoft 365-rapporter från kommando raden.</span><span class="sxs-lookup"><span data-stu-id="b36f5-111">DAP partners can use Exchange Online PowerShell to manage customer Exchange Online settings and get Microsoft 365 reports from the command line.</span></span> <span data-ttu-id="b36f5-112">Du använder Windows PowerShell på din lokala dator för att skapa en fjärrsession för PowerShell till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b36f5-112">You use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online.</span></span> <span data-ttu-id="b36f5-113">Det är en enkel tre stegs process där du anger dina inloggnings uppgifter, ger nödvändiga anslutnings inställningar och importerar sedan Exchange Online-cmdlets till din lokala Windows PowerShell-session så att du kan använda dem.</span><span class="sxs-lookup"><span data-stu-id="b36f5-113">It's a simple three-step process where you enter your credentials, provide the required connection settings, and then import the Exchange Online cmdlets into your local Windows PowerShell session so that you can use them.</span></span>

> [!NOTE]
> <span data-ttu-id="b36f5-114">DAP partners kan inte använda proceduren i [ansluta till Exchange Online PowerShell med multifaktorautentisering](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) för att ansluta till deras kund klient organisationer i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b36f5-114">DAP partners can't use the procedures in [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) to connect to their customer tenant organizations in Exchange Online PowerShell.</span></span> <span data-ttu-id="b36f5-115">MFA och Exchange Online Remote PowerShell-modulen fungerar inte med delegerad auktorisering.</span><span class="sxs-lookup"><span data-stu-id="b36f5-115">MFA and the Exchange Online Remote PowerShell Module don't work with delegated authentication.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b36f5-116">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="b36f5-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b36f5-117">Beräknad tid: 5 minuter</span><span class="sxs-lookup"><span data-stu-id="b36f5-117">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="b36f5-118">Du kan använda följande versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="b36f5-118">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="b36f5-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b36f5-119">Windows 10</span></span>

  - <span data-ttu-id="b36f5-120">Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="b36f5-120">Windows 8.1</span></span>

  - <span data-ttu-id="b36f5-121">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b36f5-121">Windows Server 2016</span></span>

  - <span data-ttu-id="b36f5-122">Windows Server 2012 eller Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b36f5-122">Windows Server 2012 or Windows Server 2012 R2</span></span>

  - <span data-ttu-id="b36f5-123">Windows 7 Service Pack 1 (SP1)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b36f5-123">Windows 7 Service Pack 1 (SP1)<sup>\*</sup></span></span>

  - <span data-ttu-id="b36f5-124">Windows Server 2008 R2 SP1<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b36f5-124">Windows Server 2008 R2 SP1<sup>\*</sup></span></span>

    <span data-ttu-id="b36f5-125"><sup>\*</sup> Om du har en äldre version av Windows måste du installera Microsoft.NET Framework 4,5 eller senare och sedan en uppdaterad version av Windows Management Framework: 3,0, 4,0 eller 5,1 (endast en).</span><span class="sxs-lookup"><span data-stu-id="b36f5-125"><sup>\*</sup> For older versions of Windows, you need to install the Microsoft.NET Framework 4.5 or later and then an updated version of the Windows Management Framework: 3.0, 4.0, or 5.1 (only one).</span></span> <span data-ttu-id="b36f5-126">Mer information finns i [Installera .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [windows Management Framework 3,0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/p/?LinkId=391344)och [Windows Management Framework 5,1](https://aka.ms/wmf5download).</span><span class="sxs-lookup"><span data-stu-id="b36f5-126">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344), and [Windows Management Framework 5.1](https://aka.ms/wmf5download).</span></span>

- <span data-ttu-id="b36f5-127">Windows PowerShell måste konfigureras för att köra skript och som standard är det inte.</span><span class="sxs-lookup"><span data-stu-id="b36f5-127">Windows PowerShell needs to be configured to run scripts, and by default, it isn't.</span></span> <span data-ttu-id="b36f5-128">Du får följande fel meddelande när du försöker ansluta:</span><span class="sxs-lookup"><span data-stu-id="b36f5-128">You'll get the following error when you try to connect:</span></span>

  `Files cannot be loaded because running scripts is disabled on this system. Provide a valid certificate with which to sign the files.`

  <span data-ttu-id="b36f5-129">Om du vill att alla PowerShell-skript som du laddar ned från Internet är signerade av en betrodd utgivare kör du följande kommando i ett förhöjdt fönster i Windows PowerShell (ett fönster i Windows PowerShell som du öppnar genom att välja **Kör som administratör**):</span><span class="sxs-lookup"><span data-stu-id="b36f5-129">To require all PowerShell scripts that you download from the internet are signed by a trusted publisher, run the following command in an elevated Windows PowerShell window (a Windows PowerShell window you open by selecting **Run as administrator**):</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

  <span data-ttu-id="b36f5-130">Du behöver bara konfigurera den här inställningen en gång på datorn, inte varje gång du ansluter.</span><span class="sxs-lookup"><span data-stu-id="b36f5-130">You need to configure this setting only once on your computer, not every time you connect.</span></span>

- <span data-ttu-id="b36f5-131">Information om kortkommandon som kan gälla procedurerna i det här avsnittet finns i kortkommandon [i administrations centret för Exchange](https://go.microsoft.com/fwlink/p/?LinkId=534017).</span><span class="sxs-lookup"><span data-stu-id="b36f5-131">For information about keyboard shortcuts that might apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkId=534017).</span></span>

## <a name="connect-to-exchange-online-for-customer-organizations"></a><span data-ttu-id="b36f5-132">Ansluta till Exchange Online för kund organisationer</span><span class="sxs-lookup"><span data-stu-id="b36f5-132">Connect to Exchange Online for customer organizations</span></span>

1. <span data-ttu-id="b36f5-133">Öppna Windows PowerShell på din lokala dator och kör följande kommando.</span><span class="sxs-lookup"><span data-stu-id="b36f5-133">On your local computer, open Windows PowerShell and run the following command.</span></span>
    
    ```
    $UserCredential = Get-Credential
    ```

    <span data-ttu-id="b36f5-134">I dialog rutan **begäran om autentiseringsuppgifter för Windows PowerShell** anger du DAP administratörs namn och lösen ord och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b36f5-134">In the **Windows PowerShell Credential Request** dialog box, enter your DAP administrator user name and password, and then click **OK**.</span></span>
    
2. <span data-ttu-id="b36f5-135">Ersätt _\<customer tenant domain name\>_ med namnet på den klient organisation som du vill ansluta till och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b36f5-135">Replace _\<customer tenant domain name\>_ with the name of the tenant domain that you want to connect to, and run the following command:</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid?DelegatedOrg=<customer tenant domain name> -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

    <span data-ttu-id="b36f5-136">Huvud steget i det här kommandot anger vilken kund som får åtkomst till rapporterings informationen.</span><span class="sxs-lookup"><span data-stu-id="b36f5-136">The key step in this command is specifying which customer to access for the reporting information.</span></span> <span data-ttu-id="b36f5-137">Det gör du i parametern  _ConnectionURI_ där du anger FQDN för det ursprungliga domän namnet som värde för `?DelegatedOrg=` .</span><span class="sxs-lookup"><span data-stu-id="b36f5-137">You do this in the  _ConnectionURI_ parameter, where you provide the FQDN of the initial domain name as the value for `?DelegatedOrg=`.</span></span> <span data-ttu-id="b36f5-138">Det här värdet anger korrekt PowerShell-slutpunkt för Exchange Online för att ansluta till.</span><span class="sxs-lookup"><span data-stu-id="b36f5-138">This value indicates the correct Exchange Online PowerShell endpoint to connect to.</span></span> <span data-ttu-id="b36f5-139">Fjärrpowershell måste ansluta till Microsoft 365 repor ting i kontexten för en viss kund varje gång en rapport körs.</span><span class="sxs-lookup"><span data-stu-id="b36f5-139">Remote PowerShell must connect to Microsoft 365 reporting in the context of a specific customer each time a report is run.</span></span> <span data-ttu-id="b36f5-140">När du har anslutit till Exchange Online PowerShell körs alla efterföljande kommandon i kontexten för kunden, vilket ger dig till gång till alla tillgängliga rapporter för kunden.</span><span class="sxs-lookup"><span data-stu-id="b36f5-140">After you connect to Exchange Online PowerShell, all subsequent commands are run in the context of the customer, which gives you access to all of the available reports for the customer.</span></span>
    
3. <span data-ttu-id="b36f5-141">Kör följande kommando.</span><span class="sxs-lookup"><span data-stu-id="b36f5-141">Run the following command.</span></span>
    
    ```
    Import-PSSession $Session
    ```

> [!NOTE]
> <span data-ttu-id="b36f5-142">Det finns en gräns på tre samtidiga sessioner som kan köras under ett konto.</span><span class="sxs-lookup"><span data-stu-id="b36f5-142">There's a limit of three simultaneous sessions that can run under one account.</span></span> <span data-ttu-id="b36f5-143">Koppla bort fjärrsessionen för PowerShell när du är klar.</span><span class="sxs-lookup"><span data-stu-id="b36f5-143">Be sure to disconnect the remote PowerShell session when you're finished.</span></span> <span data-ttu-id="b36f5-144">Om du stänger Windows PowerShell-fönstret utan att koppla bort sessionen kan du använda upp alla fjärrsessioner som är tillgängliga för dig och du måste vänta tills sessionerna upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="b36f5-144">If you close the Windows PowerShell window without disconnecting the session, you can use up all the remote PowerShell sessions available to you, and you'll need to wait for the sessions to expire.</span></span> <span data-ttu-id="b36f5-145">Om du vill koppla bort fjärrsessionen från PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b36f5-145">To disconnect the remote PowerShell session, run the following command:</span></span>

```
Remove-PSSession $Session
```
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b36f5-146">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="b36f5-146">How do you know this worked?</span></span>

<span data-ttu-id="b36f5-147">Efter steg 3 importeras Exchange Online-cmdlets till din lokala Windows PowerShell-session som spåras av en förlopps indikator.</span><span class="sxs-lookup"><span data-stu-id="b36f5-147">After Step 3, the Exchange Online cmdlets are imported into your local Windows PowerShell session as tracked by a progress bar.</span></span> <span data-ttu-id="b36f5-148">Om du inte får några problem har du lyckats ansluta.</span><span class="sxs-lookup"><span data-stu-id="b36f5-148">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="b36f5-149">En snabb test är att köra en Exchange Online-cmdlet (till exempel **Get-postlåda**) och se resultatet.</span><span class="sxs-lookup"><span data-stu-id="b36f5-149">A quick test is to run an Exchange Online cmdlet (for example, **Get-Mailbox**) and see the results.</span></span>
  
<span data-ttu-id="b36f5-150">Om du får fel meddelanden bör du kontrol lera följande:</span><span class="sxs-lookup"><span data-stu-id="b36f5-150">If you receive errors, check the following requirements:</span></span>
  
- <span data-ttu-id="b36f5-151">Ett vanligt problem är felaktigt lösen ord.</span><span class="sxs-lookup"><span data-stu-id="b36f5-151">A common problem is an incorrect password.</span></span> <span data-ttu-id="b36f5-152">Kör de tre stegen igen och betala nära till det användar namn och lösen ord som du angav i steg 1.</span><span class="sxs-lookup"><span data-stu-id="b36f5-152">Run the three steps again and pay close attention to the user name and password you enter in Step 1.</span></span>
    
- <span data-ttu-id="b36f5-153">Det konto som du använder för att ansluta till Exchange Online måste vara aktiverat för fjärr-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b36f5-153">The account you use to connect to Exchange Online must be enabled for remote PowerShell.</span></span> <span data-ttu-id="b36f5-154">Mer information finns i [Aktivera eller inaktivera åtkomst till Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534018).</span><span class="sxs-lookup"><span data-stu-id="b36f5-154">For more information, see [Enable or disable access to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534018).</span></span>
    
- <span data-ttu-id="b36f5-155">TCP-port 80-trafik måste vara öppen mellan din lokala dator och Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b36f5-155">TCP port 80 traffic needs to be open between your local computer and Exchange Online.</span></span> <span data-ttu-id="b36f5-156">Det är troligt men det är något att överväga om din organisation har en begränsad Internet åtkomst policy.</span><span class="sxs-lookup"><span data-stu-id="b36f5-156">It's probably open, but it's something to consider if your organization has a restrictive Internet access policy.</span></span>
    
## <a name="call-the-cmdlet-directly-with-invoke-command"></a><span data-ttu-id="b36f5-157">Anropa cmdlet direkt med kommandot Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="b36f5-157">Call the cmdlet directly with Invoke-Command</span></span>

<span data-ttu-id="b36f5-158">Det kan vara en lång tids krävande att importera en fjärrsession i PowerShell (steg 3) eftersom den kommer med i _alla_ Exchange Online-cmdletar.</span><span class="sxs-lookup"><span data-stu-id="b36f5-158">Importing a remote PowerShell session (Step 3) can be a lengthy process because it brings in _all_ Exchange Online cmdlets.</span></span> <span data-ttu-id="b36f5-159">Detta kan vara ett problem i grupp bearbetning (till exempel när du kör rapporter eller skapar Mass ändringar för olika innehavare).</span><span class="sxs-lookup"><span data-stu-id="b36f5-159">This can be an issue in batch processing (for example, when you're running reports or making bulk changes for different tenants).</span></span> <span data-ttu-id="b36f5-160">Som ett alternativ till att använda **import-PSSession**kan du ringa cmdletar som du vill använda direkt med **kommandot Invoke-**.</span><span class="sxs-lookup"><span data-stu-id="b36f5-160">As an alternative to using **Import-PSSession**, you can call cmdlets you want to use directly with **Invoke-Command**.</span></span> <span data-ttu-id="b36f5-161">Om du till exempel vill anropa cmdleten **Get-Milbox** ersätter du `Import-PSSession $Session` kommandot i steg 3:</span><span class="sxs-lookup"><span data-stu-id="b36f5-161">For example, to call the **Get-Milbox** cmdlet, substitute this syntax for the `Import-PSSession $Session` command in Step 3:</span></span>
  
```
Invoke-Command -Session $Session -ScriptBlock {Get-Mailbox}
```

## <a name="more-reporting-cmdlets"></a><span data-ttu-id="b36f5-162">Fler cmdlets för rapportering</span><span class="sxs-lookup"><span data-stu-id="b36f5-162">More reporting cmdlets</span></span>

<span data-ttu-id="b36f5-163">De cmdlets som du använde i det här avsnittet är Windows PowerShell-cmdletar.</span><span class="sxs-lookup"><span data-stu-id="b36f5-163">The cmdlets that you used in this topic are Windows PowerShell cmdlets.</span></span> <span data-ttu-id="b36f5-164">Mer information om dessa cmdletar finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="b36f5-164">For more information about these cmdlets, see the following topics:</span></span>
  
- [<span data-ttu-id="b36f5-165">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="b36f5-165">Get-Credential</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389618)
    
- [<span data-ttu-id="b36f5-166">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="b36f5-166">New-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389621)
    
- [<span data-ttu-id="b36f5-167">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="b36f5-167">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389619)
    
- [<span data-ttu-id="b36f5-168">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="b36f5-168">Remove-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389620)
    
- [<span data-ttu-id="b36f5-169">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="b36f5-169">Set-ExecutionPolicy</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389623)
    

