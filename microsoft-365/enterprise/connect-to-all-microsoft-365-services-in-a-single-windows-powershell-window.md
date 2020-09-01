---
title: Ansluta till alla Microsoft 365-tjänster i ett enda PowerShell-fönster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/26/2020
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
ms.openlocfilehash: af676434017cbe7025baa5e8509e6203a5d59674
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307631"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="051a8-103">Ansluta till alla Microsoft 365-tjänster i ett enda PowerShell-fönster</span><span class="sxs-lookup"><span data-stu-id="051a8-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="051a8-104">När du använder PowerShell för att hantera Microsoft 365 går det att ha flera olika PowerShell-sessioner öppna samtidigt i olika PowerShell-fönster som hör till hanterade användarkonton, SharePoint Online, Exchange Online, Skype för företag – Online, Microsoft Teams och Säkerhets- &amp; efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="051a8-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="051a8-105">Du kan inte använda det här alternativet för att hantera Microsoft 365 eftersom du inte kan utbyta data mellan fönstren för hantering av flera tjänster.</span><span class="sxs-lookup"><span data-stu-id="051a8-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="051a8-106">I den här artikeln beskrivs hur du använder en enda instans av PowerShell, som du kan använda för att hantera Microsoft 365-konton, Skype för företag – Online, Exchange Online, SharePoint Online, Microsoft Teams och Säkerhets- &amp; efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="051a8-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="051a8-107">I den här artikeln finns för närvarande bara kommandon för att ansluta till molnet över hela världen (+GCC).</span><span class="sxs-lookup"><span data-stu-id="051a8-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="051a8-108">I kommentarerna finns länkar till artiklar med information om hur du ansluter till andra Microsoft 365-moln.</span><span class="sxs-lookup"><span data-stu-id="051a8-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="051a8-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="051a8-109">Before you begin</span></span>

<span data-ttu-id="051a8-110">Innan du kan hantera hela Microsoft 365 från en enda instans av PowerShell måste följande förutsättningar vara uppfyllda:</span><span class="sxs-lookup"><span data-stu-id="051a8-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="051a8-111">Det Microsoft 365-konto för arbete eller skola som du använder för de här procedurerna måste vara medlem i en administratörsroll för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="051a8-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="051a8-112">Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="051a8-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span> <span data-ttu-id="051a8-113">Det här är ett krav för PowerShell för Microsoft 365, inte nödvändigtvis för alla andra Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="051a8-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="051a8-114">Du kan använda följande 64-bitars versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="051a8-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="051a8-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="051a8-115">Windows 10</span></span>
    
  - <span data-ttu-id="051a8-116">Windows 8.1 eller Windows 8</span><span class="sxs-lookup"><span data-stu-id="051a8-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="051a8-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="051a8-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="051a8-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="051a8-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="051a8-119">Windows Server 2012 R2- eller Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="051a8-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="051a8-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="051a8-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="051a8-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="051a8-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="051a8-122">\* Du måste installera Microsoft .NET Framework 4.5.*x* och sedan antingen Windows Management Framework 3.0 eller Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="051a8-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="051a8-123">Mer information finns i [installera .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) och [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) eller [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span><span class="sxs-lookup"><span data-stu-id="051a8-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="051a8-124">Du måste använda en 64-bitars version av Windows på grund av kraven för Skype för företag – Online-modulen och en av Microsoft 365-modulerna.</span><span class="sxs-lookup"><span data-stu-id="051a8-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="051a8-125">Du måste installera de moduler som krävs för Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype för företag – Online och Teams:</span><span class="sxs-lookup"><span data-stu-id="051a8-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="051a8-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="051a8-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="051a8-127">SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="051a8-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="051a8-128">Skype för företag – Online, PowerShell-modul</span><span class="sxs-lookup"><span data-stu-id="051a8-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="051a8-129">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="051a8-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="051a8-130">Teams PowerShell översikt</span><span class="sxs-lookup"><span data-stu-id="051a8-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="051a8-131">PowerShell måste konfigureras för körning av signerade skript för Skype för företag – Online och Säkerhets- &amp; efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="051a8-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="051a8-132">Det gör du genom att köra följande kommando i en upphöjd PowerShell-session (ett PowerShell-fönster som du öppnar genom att välja **Kör som administratör**).</span><span class="sxs-lookup"><span data-stu-id="051a8-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="051a8-133">Anslutningssteg när du bara använder ett lösenord</span><span class="sxs-lookup"><span data-stu-id="051a8-133">Connection steps when using just a password</span></span>

<span data-ttu-id="051a8-134">Här är några steg för att ansluta till alla tjänster i ett enda PowerShell-fönster när du bara använder ett lösenord för inloggning.</span><span class="sxs-lookup"><span data-stu-id="051a8-134">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="051a8-135">Öppna Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="051a8-135">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="051a8-136">Kör detta kommando och ange inloggningsuppgifter för ditt Microsoft 365-arbets-eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="051a8-136">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="051a8-137">Kör det här kommandot för att ansluta till Azure AD med hjälp av Azure Active Directory PowerShell för Graph-modulen.</span><span class="sxs-lookup"><span data-stu-id="051a8-137">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="051a8-138">Om du däremot använder modulen Microsoft Azure Active Directory för PowerShell-moduler kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="051a8-138">Alternately, if you are using the Microsoft Azure Active Directory Module for PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="051a8-139">PowerShell Core stöder inte modulen Microsoft Azure Active Directory för PowerShell-moduler och -cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="051a8-139">PowerShell Core does not support the Microsoft Azure Active Directory Module for PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="051a8-140">Om du vill fortsätta använda dessa cmdlets måste du köra dem från PowerShell.</span><span class="sxs-lookup"><span data-stu-id="051a8-140">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="051a8-141">Kör dessa kommandon för att ansluta till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="051a8-141">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="051a8-142">Ange organisationsnamnet för din domän.</span><span class="sxs-lookup"><span data-stu-id="051a8-142">Specify the organization name for your domain.</span></span> <span data-ttu-id="051a8-143">Till exempel, för "litwareinc.onmicrosoft.com" är organisationensnamnet "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="051a8-143">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="051a8-144">Kör dessa kommandon för att ansluta till Skype för företag – Online.</span><span class="sxs-lookup"><span data-stu-id="051a8-144">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="051a8-145">Ett varningsmeddelande om att öka `WSMan NetworkDelayms` värdet förväntas första gången du ansluter och ska ignoreras.</span><span class="sxs-lookup"><span data-stu-id="051a8-145">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="051a8-146">Kör det här kommandot när du vill ansluta till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="051a8-146">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="051a8-147">Om du vill ansluta till Exchange Online för Microsoft 365-moln som inte är världsomspännande använder du **-ExchangeEnvironmentName** parameter.</span><span class="sxs-lookup"><span data-stu-id="051a8-147">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, use the **-ExchangeEnvironmentName** parameter.</span></span> <span data-ttu-id="051a8-148">Mer information finns i [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="051a8-148">See [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) for more information.</span></span>

7. <span data-ttu-id="051a8-149">Kör dessa kommandon för att ansluta till Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="051a8-149">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="051a8-150">Om du vill ansluta till Microsoft Teams-moln som inte är världsomspännande läser du [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="051a8-150">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span></span>

8. <span data-ttu-id="051a8-151">Kör dessa kommandon för att ansluta till &amp; säkerhet- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="051a8-151">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > <span data-ttu-id="051a8-152">Om du vill ansluta till &amp; säkerhet- och efterlevnadscenter för Microsoft 365-moln, annat än världsomspännande läser du [Ansluta till Säkerhets- och efterlevnadscenter PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="051a8-152">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="051a8-153">Här är alla kommandon i ett enda block när du använder Azure Active Directory PowerShell för Graph-moduler.</span><span class="sxs-lookup"><span data-stu-id="051a8-153">Here are all the commands in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="051a8-154">Ange namnet på domänvärden och kör alla samtidigt.</span><span class="sxs-lookup"><span data-stu-id="051a8-154">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="051a8-155">Alternativt finns här alla kommandon i ett enda block när du använder modulen Microsoft Azure Active Directory för PowerShell-moduler.</span><span class="sxs-lookup"><span data-stu-id="051a8-155">Alternately, here are all the commands in a single block when using the Microsoft Azure Active Directory Module for PowerShell module.</span></span> <span data-ttu-id="051a8-156">Ange namnet på domänvärden och kör alla samtidigt.</span><span class="sxs-lookup"><span data-stu-id="051a8-156">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="051a8-157">När du är redo att stänga PowerShell-fönstret kör du det här kommandot för att ta bort aktiva sessioner till Skype för företag – Online, SharePoint Online, Säkerhets- &amp; efterlevnadscenter och Teams:</span><span class="sxs-lookup"><span data-stu-id="051a8-157">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, the Security &amp; Compliance Center, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="051a8-158">Anslutningssteg när du använder multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="051a8-158">Connection steps when using multi-factor authentication</span></span>

<span data-ttu-id="051a8-159">Här är alla kommandon i ett enda block för att ansluta till Azure AD, SharePoint Online, Skype för företag, Exchange Online och Teams med multifaktorautentisering in ett enda fönster med hjälp av Azure Active Directory PowerShell för Graph-modul.</span><span class="sxs-lookup"><span data-stu-id="051a8-159">Here are all the commands in a single block to connect to Azure AD, SharePoint Online, Skype for Business, Exchange Online, and Teams using multi-factor authentication in a single window using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="051a8-160">Ange användarhuvudnamn (UPN) för ett användarkonto och domänvärdens namn och kör alla samtidigt.</span><span class="sxs-lookup"><span data-stu-id="051a8-160">Specify the user principal name (UPN) name of a user account and your domain host name, and then run them all at one time.</span></span>

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
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="051a8-161">Här finns annars alla kommandon när du använder modulen Microsoft Azure Active Directory för PowerShell-moduler.</span><span class="sxs-lookup"><span data-stu-id="051a8-161">Alternately, here are all the commands when using the Microsoft Azure Active Directory Module for PowerShell module.</span></span>

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
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="051a8-162">I &amp; säkerhet- och efterlevnadscenter hittar du information om [Ansluta till säkerhet- och efterlevnadscenter PowerShell med multifaktorautentisering](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) för att ansluta med multifaktorautentisering:</span><span class="sxs-lookup"><span data-stu-id="051a8-162">For the Security &amp; Compliance Center, see [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) to connect using multi-factor authentication:</span></span>

## <a name="see-also"></a><span data-ttu-id="051a8-163">Se även</span><span class="sxs-lookup"><span data-stu-id="051a8-163">See also</span></span>

- [<span data-ttu-id="051a8-164">Ansluta till Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="051a8-164">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="051a8-165">Hantera SharePoint Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="051a8-165">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="051a8-166">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="051a8-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
