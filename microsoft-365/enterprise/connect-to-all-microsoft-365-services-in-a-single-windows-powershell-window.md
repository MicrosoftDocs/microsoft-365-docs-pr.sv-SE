---
title: Ansluta till alla Microsoft 365-tjänster i ett enda PowerShell-fönster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: 'Sammanfattning: Ansluta till alla Microsoft 365-tjänster i ett enda PowerShell-fönster.'
ms.openlocfilehash: 08d2f4c6ce67aa9fea196d56b2eb5f36a36d7943
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430052"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="9fd10-103">Ansluta till alla Microsoft 365-tjänster i ett enda PowerShell-fönster</span><span class="sxs-lookup"><span data-stu-id="9fd10-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="9fd10-104">När du använder PowerShell för att hantera Microsoft 365 går det att ha flera olika PowerShell-sessioner öppna samtidigt i olika PowerShell-fönster som hör till hanterade användarkonton, SharePoint Online, Exchange Online, Skype för företag – Online, Microsoft Teams och Säkerhets- &amp; efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="9fd10-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="9fd10-105">Du kan inte använda det här alternativet för att hantera Microsoft 365 eftersom du inte kan utbyta data mellan fönstren för hantering av flera tjänster.</span><span class="sxs-lookup"><span data-stu-id="9fd10-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="9fd10-106">I den här artikeln beskrivs hur du använder en enda instans av PowerShell, som du kan använda för att hantera Microsoft 365-konton, Skype för företag – Online, Exchange Online, SharePoint Online, Microsoft Teams och Säkerhets- &amp; efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="9fd10-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="9fd10-107">I den här artikeln finns för närvarande bara kommandon för att ansluta till molnet över hela världen (+GCC).</span><span class="sxs-lookup"><span data-stu-id="9fd10-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="9fd10-108">I kommentarerna finns länkar till artiklar med information om hur du ansluter till andra Microsoft 365-moln.</span><span class="sxs-lookup"><span data-stu-id="9fd10-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="9fd10-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="9fd10-109">Before you begin</span></span>

<span data-ttu-id="9fd10-110">Innan du kan hantera hela Microsoft 365 från en enda instans av PowerShell måste följande förutsättningar vara uppfyllda:</span><span class="sxs-lookup"><span data-stu-id="9fd10-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="9fd10-111">Det Microsoft 365-konto för arbete eller skola som du använder för de här procedurerna måste vara medlem i en administratörsroll för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9fd10-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="9fd10-112">Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="9fd10-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="9fd10-113">Det här är ett krav för PowerShell för Microsoft 365, inte nödvändigtvis för alla andra Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="9fd10-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="9fd10-114">Du kan använda följande 64-bitars versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="9fd10-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="9fd10-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="9fd10-115">Windows 10</span></span>
    
  - <span data-ttu-id="9fd10-116">Windows 8.1 eller Windows 8</span><span class="sxs-lookup"><span data-stu-id="9fd10-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="9fd10-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="9fd10-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="9fd10-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="9fd10-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="9fd10-119">Windows Server 2012 R2- eller Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="9fd10-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="9fd10-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="9fd10-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="9fd10-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="9fd10-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="9fd10-122">\* Du måste installera Microsoft .NET Framework 4.5.*x* och sedan antingen Windows Management Framework 3.0 eller Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="9fd10-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="9fd10-123">Mer information finns i [installera .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) och [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) eller [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span><span class="sxs-lookup"><span data-stu-id="9fd10-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="9fd10-124">Du måste använda en 64-bitars version av Windows på grund av kraven för Skype för företag – Online-modulen och en av Microsoft 365-modulerna.</span><span class="sxs-lookup"><span data-stu-id="9fd10-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="9fd10-125">Du måste installera de moduler som krävs för Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype för företag – Online och Teams:</span><span class="sxs-lookup"><span data-stu-id="9fd10-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="9fd10-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="9fd10-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="9fd10-127">SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="9fd10-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="9fd10-128">Skype för företag – Online, PowerShell-modul</span><span class="sxs-lookup"><span data-stu-id="9fd10-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="9fd10-129">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="9fd10-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="9fd10-130">Teams PowerShell översikt</span><span class="sxs-lookup"><span data-stu-id="9fd10-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="9fd10-131">PowerShell måste konfigureras för körning av signerade skript för Skype för företag – Online och Säkerhets- &amp; efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="9fd10-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="9fd10-132">Det gör du genom att köra följande kommando i en upphöjd PowerShell-session (ett PowerShell-fönster som du öppnar genom att välja **Kör som administratör**).</span><span class="sxs-lookup"><span data-stu-id="9fd10-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="9fd10-133">Exchange Online och Säkerhets &amp; Efterlevnadscenter med modulen Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="9fd10-133">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="9fd10-134">I den här artikeln används Exchange Online PowerShell V2-modulen för att ansluta till både Exchange Online och Säkerhets &amp; Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="9fd10-134">This article uses the Exchange Online PowerShell V2 module to connect to both Exchange Online and Security &amp; Compliance Center.</span></span> <span data-ttu-id="9fd10-135">Men för närvarande går det inte att ansluta till både Exchange Online och Säkerhets &amp; Efterlevnadscenter **i samma PowerShell-fönster**.</span><span class="sxs-lookup"><span data-stu-id="9fd10-135">However, at this time you cannot connect to both Exchange Online and the Security &amp; Compliance Center **in the same PowerShell window**.</span></span>

<span data-ttu-id="9fd10-136">Därför måste du välja en anslutning med endera Exchange Online *eller* Säkerhets &amp; Efterlevnadscenter när du konfigurerar ett PowerShell-fönster för flera Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="9fd10-136">Therefore, you must choose a connection with either Exchange Online *or* the Security &amp; Compliance Center when configuring a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="9fd10-137">Anslutningssteg när du bara använder ett lösenord</span><span class="sxs-lookup"><span data-stu-id="9fd10-137">Connection steps when using just a password</span></span>

<span data-ttu-id="9fd10-138">Här är några steg för att ansluta till alla tjänster i ett enda PowerShell-fönster när du bara använder ett lösenord för inloggning.</span><span class="sxs-lookup"><span data-stu-id="9fd10-138">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="9fd10-139">Öppna Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fd10-139">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="9fd10-140">Kör detta kommando och ange inloggningsuppgifter för ditt Microsoft 365-arbets-eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="9fd10-140">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="9fd10-141">Kör det här kommandot för att ansluta till Azure AD med hjälp av Azure Active Directory PowerShell för Graph-modulen.</span><span class="sxs-lookup"><span data-stu-id="9fd10-141">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="9fd10-142">Om du använder modulen Microsoft Azure Active Directory-modul för Windows PowerShell kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="9fd10-142">Alternately, if you are using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="9fd10-143">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="9fd10-143">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="9fd10-144">Om du vill fortsätta använda dessa cmdlets måste du köra dem från PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fd10-144">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="9fd10-145">Kör dessa kommandon för att ansluta till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9fd10-145">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="9fd10-146">Ange organisationsnamnet för din domän.</span><span class="sxs-lookup"><span data-stu-id="9fd10-146">Specify the organization name for your domain.</span></span> <span data-ttu-id="9fd10-147">Till exempel, för "litwareinc.onmicrosoft.com" är organisationensnamnet "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="9fd10-147">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="9fd10-148">Kör dessa kommandon för att ansluta till Skype för företag – Online.</span><span class="sxs-lookup"><span data-stu-id="9fd10-148">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="9fd10-149">Ett varningsmeddelande om att öka `WSMan NetworkDelayms` värdet förväntas första gången du ansluter och ska ignoreras.</span><span class="sxs-lookup"><span data-stu-id="9fd10-149">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="9fd10-150">Kör det här kommandot när du vill ansluta till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9fd10-150">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="9fd10-151">Om du vill ansluta till Exchange Online för Microsoft 365-moln som inte är världsomspännande se [-Ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9fd10-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="9fd10-152">Kör dessa kommandon för att ansluta till Säkerhets &amp; Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="9fd10-152">Alternately, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="9fd10-153">Om du vill ansluta till &amp; säkerhet- och efterlevnadscenter för Microsoft 365-moln, annat än världsomspännande läser du [Ansluta till Säkerhets- och efterlevnadscenter PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="9fd10-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="9fd10-154">Kör dessa kommandon för att ansluta till Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fd10-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="9fd10-155">Om du vill ansluta till Microsoft Teams-moln som inte är världsomspännande läser du [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span><span class="sxs-lookup"><span data-stu-id="9fd10-155">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="9fd10-156">Azure Active Directory PowerShell för modulen Graph</span><span class="sxs-lookup"><span data-stu-id="9fd10-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="9fd10-157">Här följer kommandon för alla tjänster *, förutom Säkerhets &amp; Efterlevnadscenter* i ett enda block med hjälp av modulen Azure Active Directory PowerShell för modulen Graph.</span><span class="sxs-lookup"><span data-stu-id="9fd10-157">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="9fd10-158">Ange namnet på domänvärden och kör alla samtidigt.</span><span class="sxs-lookup"><span data-stu-id="9fd10-158">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="9fd10-159">Här följer kommandon för alla tjänster \*, förutom Exchange Online \* i ett enda block med hjälp av modulen Azure Active Directory PowerShell för modulen Graph.</span><span class="sxs-lookup"><span data-stu-id="9fd10-159">Here are the commands for all of the services *except Exchange Online* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="9fd10-160">Ange namnet på domänvärden och UPN på din inloggning och kör alla samtidigt.</span><span class="sxs-lookup"><span data-stu-id="9fd10-160">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="9fd10-161">Microsoft Azure Active Directory-modulen för modulen Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fd10-161">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="9fd10-162">Här följer kommandon för alla tjänster *, förutom Säkerhets &amp; Efterlevnadscenter* i ett enda block med hjälp av modulen Microsoft Azure Active Directory för modulen PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fd10-162">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="9fd10-163">Ange namnet på domänvärden och kör alla samtidigt.</span><span class="sxs-lookup"><span data-stu-id="9fd10-163">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="9fd10-164">Här följer kommandon för alla tjänster *, förutom Exchange Online* i ett enda block med hjälp av modulen Microsoft Azure Active Directory för modulen Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fd10-164">Here are the commands for all of the services *except Exchange Online* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="9fd10-165">Ange namnet på domänvärden och UPN på din inloggning och kör alla samtidigt.</span><span class="sxs-lookup"><span data-stu-id="9fd10-165">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="9fd10-166">Anslutningssteg när du använder multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="9fd10-166">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="9fd10-167">Azure Active Directory PowerShell för modulen Graph</span><span class="sxs-lookup"><span data-stu-id="9fd10-167">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="9fd10-168">Här är alla kommandon i ett enda block för att ansluta till flera Microsoft 365-tjänster \*förutom Säkerhets &amp; Efterlevnadscenter \* med multifaktorautentisering med hjälp av Azure Active Directory PowerShell för modulen Graph.</span><span class="sxs-lookup"><span data-stu-id="9fd10-168">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="9fd10-169">Här är alla kommandon i ett enda block för att ansluta till flera Microsoft 365-tjänster \*förutom Exchange Online \* med multifaktorautentisering med hjälp av Azure Active Directory PowerShell för modulen Graph.</span><span class="sxs-lookup"><span data-stu-id="9fd10-169">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="9fd10-170">Microsoft Azure Active Directory-modulen för modulen Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fd10-170">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="9fd10-171">Här är alla kommandon i ett enda block för att ansluta till flera Microsoft 365-tjänster *förutom Säkerhets &amp; Efterlevnadscenter* med multifaktorautentisering med hjälp av modulen Microsoft Azure Active Directory för modulen Windows PowerShell..</span><span class="sxs-lookup"><span data-stu-id="9fd10-171">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="9fd10-172">Här är alla kommandon i ett enda block för att ansluta till flera Microsoft 365-tjänster \*förutom Exchange Online \* med multifaktorautentisering med hjälp av modulen Microsoft Azure Active Directory för modulen Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fd10-172">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* using multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="9fd10-173">Stäng PowerShell-fönstret.</span><span class="sxs-lookup"><span data-stu-id="9fd10-173">Close the PowerShell window</span></span>

<span data-ttu-id="9fd10-174">När du är redo att stänga PowerShell-fönstret kör du det här kommandot för att ta bort aktiva sessioner till Skype för företag – Online, SharePoint Online och Teams:</span><span class="sxs-lookup"><span data-stu-id="9fd10-174">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```


## <a name="see-also"></a><span data-ttu-id="9fd10-175">Se även</span><span class="sxs-lookup"><span data-stu-id="9fd10-175">See also</span></span>

- [<span data-ttu-id="9fd10-176">Ansluta till Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fd10-176">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="9fd10-177">Hantera SharePoint Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fd10-177">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="9fd10-178">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fd10-178">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
