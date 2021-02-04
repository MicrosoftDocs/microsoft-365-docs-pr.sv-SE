---
title: Ansluta till alla Microsoft 365-tjänster i ett enda PowerShell-fönster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/02/2021
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
ms.openlocfilehash: 390e2446737b4b85dfaba64974666fab4938a5dd
ms.sourcegitcommit: 4f40f5be140a23bacff6fd7b85536de14fc7d499
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084607"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="c35b9-103">Ansluta till alla Microsoft 365-tjänster i ett enda PowerShell-fönster</span><span class="sxs-lookup"><span data-stu-id="c35b9-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="c35b9-104">När du använder PowerShell för att hantera Microsoft 365 kan du ha flera PowerShell-sessioner öppna samtidigt.</span><span class="sxs-lookup"><span data-stu-id="c35b9-104">When you use PowerShell to manage Microsoft 365, you can have multiple PowerShell sessions open at the same time.</span></span> <span data-ttu-id="c35b9-105">Du kanske har olika PowerShell-fönster för att hantera användarkonton, SharePoint Online, Exchange Online, Skype för företag – Online, Microsoft Teams och Säkerhets- och &amp; efterlevnadscentret.</span><span class="sxs-lookup"><span data-stu-id="c35b9-105">You might have different PowerShell windows to manage user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance center.</span></span>
  
<span data-ttu-id="c35b9-106">Det här scenariot är inte optimalt för att hantera Microsoft 365 eftersom du inte kan utbyta data mellan fönstren för hantering av flera tjänster.</span><span class="sxs-lookup"><span data-stu-id="c35b9-106">This scenario isn't optimal for managing Microsoft 365, because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="c35b9-107">Den här artikeln beskriver hur du använder en enda instans av PowerShell för att hantera Microsoft 365-konton, Skype för Företag – Online, Exchange Online, SharePoint Online, Microsoft Teams och Säkerhets- och &amp; efterlevnadscentret.</span><span class="sxs-lookup"><span data-stu-id="c35b9-107">This article describes how to use a single instance of PowerShell to manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="c35b9-108">Den här artikeln innehåller för närvarande bara kommandon för att ansluta till det världsomfattande (+GCC) molnet.</span><span class="sxs-lookup"><span data-stu-id="c35b9-108">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="c35b9-109">I kommentarerna finns länkar till artiklar om anslutning till andra Microsoft 365-moln.</span><span class="sxs-lookup"><span data-stu-id="c35b9-109">Notes provide links to articles about connecting to the other Microsoft 365 clouds.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c35b9-110">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="c35b9-110">Before you begin</span></span>

<span data-ttu-id="c35b9-111">Innan du kan hantera hela Microsoft 365 från en enda instans av PowerShell måste följande förutsättningar vara uppfyllda:</span><span class="sxs-lookup"><span data-stu-id="c35b9-111">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="c35b9-112">Det Microsoft 365-kontot för arbete eller skola som du använder måste vara en medlem i en administratörsroll för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c35b9-112">The Microsoft 365 work or school account that you use must be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="c35b9-113">Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="c35b9-113">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="c35b9-114">Det här är ett krav för PowerShell för Microsoft 365, men inte nödvändigtvis för alla andra Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="c35b9-114">This is a requirement for PowerShell for Microsoft 365, but not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="c35b9-115">Du kan använda följande 64-bitars versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="c35b9-115">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="c35b9-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="c35b9-116">Windows 10</span></span>
    
  - <span data-ttu-id="c35b9-117">Windows 8.1 eller Windows 8</span><span class="sxs-lookup"><span data-stu-id="c35b9-117">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="c35b9-118">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c35b9-118">Windows Server 2019</span></span>
    
  - <span data-ttu-id="c35b9-119">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="c35b9-119">Windows Server 2016</span></span>
    
  - <span data-ttu-id="c35b9-120">Windows Server 2012 R2- eller Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="c35b9-120">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="c35b9-121">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="c35b9-121">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="c35b9-122">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="c35b9-122">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="c35b9-123">\* Du måste installera Microsoft .NET Framework 4,5.*x* och sedan Windows Management Framework 3,0 eller 4,0.</span><span class="sxs-lookup"><span data-stu-id="c35b9-123">\* You need to install Microsoft .NET Framework 4.5.*x* and then Windows Management Framework 3.0 or 4.0.</span></span> <span data-ttu-id="c35b9-124">Mer information finns i [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="c35b9-124">For more information, see [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview).</span></span>
    
    <span data-ttu-id="c35b9-125">Du måste använda en 64-bitars version av Windows på grund av kraven för Skype för företag – Online-modulen och en av Microsoft 365-modulerna.</span><span class="sxs-lookup"><span data-stu-id="c35b9-125">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="c35b9-126">Du måste installera de moduler som krävs för Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype för företag – Online och Teams:</span><span class="sxs-lookup"><span data-stu-id="c35b9-126">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="c35b9-127">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="c35b9-127">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="c35b9-128">SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="c35b9-128">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="c35b9-129">Skype för företag – Online, PowerShell-modul</span><span class="sxs-lookup"><span data-stu-id="c35b9-129">Skype for Business Online, PowerShell Module</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="c35b9-130">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="c35b9-130">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="c35b9-131">Teams PowerShell översikt</span><span class="sxs-lookup"><span data-stu-id="c35b9-131">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="c35b9-132">PowerShell måste konfigureras för körning av signerade skript för Skype för Företag – Online och Säkerhets- och &amp; efterlevnadscentret.</span><span class="sxs-lookup"><span data-stu-id="c35b9-132">PowerShell must be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="c35b9-133">Kör följande kommando i en upphöjd PowerShell-session (ett PowerShell-fönster som du **Kör som administratör**).</span><span class="sxs-lookup"><span data-stu-id="c35b9-133">Run the following command in an elevated PowerShell session (a PowerShell session that you **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="c35b9-134">Anslutningssteg vid användning av bara ett lösenord</span><span class="sxs-lookup"><span data-stu-id="c35b9-134">Connection steps when using just a password</span></span>

<span data-ttu-id="c35b9-135">Här är några steg för att ansluta till alla tjänster i ett enda PowerShell-fönster när du bara använder ett lösenord för inloggning.</span><span class="sxs-lookup"><span data-stu-id="c35b9-135">Follow these steps to connect to all the services in a single PowerShell window when you're using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="c35b9-136">Öppna Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c35b9-136">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="c35b9-137">Kör detta kommando och ange inloggningsuppgifter för ditt Microsoft 365-arbets-eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="c35b9-137">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="c35b9-138">Kör det här kommandot för att ansluta till Azure AD med hjälp av Azure Active Directory PowerShell för Graph-modulen.</span><span class="sxs-lookup"><span data-stu-id="c35b9-138">Run this command to connect to Azure AD by using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="c35b9-139">Om du använder Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen, kör det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="c35b9-139">Or if you're using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="c35b9-140">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *MSOL* i deras namn.</span><span class="sxs-lookup"><span data-stu-id="c35b9-140">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="c35b9-141">Du måste köra dessa cmdlets från PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c35b9-141">You must run these cmdlets from PowerShell.</span></span>

4. <span data-ttu-id="c35b9-142">Kör dessa kommandon för att ansluta till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c35b9-142">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="c35b9-143">Ange organisationsnamnet för din domän.</span><span class="sxs-lookup"><span data-stu-id="c35b9-143">Specify the organization name for your domain.</span></span> <span data-ttu-id="c35b9-144">Till exempel, för "litwareinc\.onmicrosoft.com" är organisationens namnvärdet "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="c35b9-144">For example, for "litwareinc\.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. <span data-ttu-id="c35b9-145">Kör dessa kommandon för att ansluta till Skype för Företag – Online.</span><span class="sxs-lookup"><span data-stu-id="c35b9-145">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="c35b9-146">En varning om att öka `WSMan NetworkDelayms` värdet visas första gången du ansluter.</span><span class="sxs-lookup"><span data-stu-id="c35b9-146">A warning about increasing the `WSMan NetworkDelayms` value will appear the first time that you connect.</span></span> <span data-ttu-id="c35b9-147">Ignorera det.</span><span class="sxs-lookup"><span data-stu-id="c35b9-147">Ignore it.</span></span>
     
   > [!Note]
   > <span data-ttu-id="c35b9-148">Skype för företag – Online-Connector är för närvarande en del av den senaste versionen av Teams PowerShell-modul.</span><span class="sxs-lookup"><span data-stu-id="c35b9-148">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="c35b9-149">Om du använder den senaste versionen av Teams PowerShell, behöver du inte installera Skype för företag – Online-Connector.</span><span class="sxs-lookup"><span data-stu-id="c35b9-149">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
   ```powershell
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="c35b9-150">Kör dessa kommandon för att ansluta till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c35b9-150">Run these commands to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="c35b9-151">Om du vill ansluta till Exchange Online för Microsoft 365-moln som inte är världsomspännande går du till [Ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c35b9-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="c35b9-152">Kör dessa kommandon för att ansluta till &amp; säkerhet- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="c35b9-152">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="c35b9-153">Om du vill ansluta till &amp; säkerhet- och efterlevnadscenter för Microsoft 365-moln, annat än världsomspännande läser du [Ansluta till Säkerhets- och efterlevnadscenter PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c35b9-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="c35b9-154">Kör dessa kommandon för att ansluta till Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c35b9-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```
  
   > [!Note]
   > <span data-ttu-id="c35b9-155">För att ansluta till Microsoft Teams-moln som inte är *världsomspännande*, se [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span><span class="sxs-lookup"><span data-stu-id="c35b9-155">To connect to Microsoft Teams clouds other than *Worldwide*, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c35b9-156">Azure Active Directory PowerShell för Graph-modulen</span><span class="sxs-lookup"><span data-stu-id="c35b9-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c35b9-157">Här följer kommandon för alla tjänster i ett enda textblock när du använder Azure Active Directory PowerShell för Graph-modulen.</span><span class="sxs-lookup"><span data-stu-id="c35b9-157">Here are the commands for all the services in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="c35b9-158">Ange namnet på din domänvärd och UPN på inloggning och kör alla samtidigt.</span><span class="sxs-lookup"><span data-stu-id="c35b9-158">Specify the name of your domain host and the UPN for the sign-in and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="c35b9-159">Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen</span><span class="sxs-lookup"><span data-stu-id="c35b9-159">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="c35b9-160">Här följer kommandon för alla tjänster i ett enda textblock när du använder Microsoft Azure Active Directory-modul för Windows PowerShell-modulen.</span><span class="sxs-lookup"><span data-stu-id="c35b9-160">Here are the commands for all the services in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="c35b9-161">Ange namnet på din domänvärd och UPN för din inloggning och kör alla samtidigt.</span><span class="sxs-lookup"><span data-stu-id="c35b9-161">Specify the name of your domain host and the UPN for the sign-in and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="c35b9-162">Anslutningssteg när du använder multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="c35b9-162">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c35b9-163">Azure Active Directory PowerShell för modulen Graph</span><span class="sxs-lookup"><span data-stu-id="c35b9-163">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c35b9-164">Här är alla kommandon i ett enda textblock för att ansluta till flera Microsoft 365-tjänster när du använder multifaktorautentisering med Azure Active Directory PowerShell för Graph-modulen.</span><span class="sxs-lookup"><span data-stu-id="c35b9-164">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="c35b9-165">Microsoft Azure Active Directory-modul för Windows PowerShell-modulen</span><span class="sxs-lookup"><span data-stu-id="c35b9-165">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="c35b9-166">Här är alla kommandon i ett enda textblock för att ansluta till flera Microsoft 365-tjänster när du använder multifaktorautentisering med Microsoft Azure Active Directory-modul för Windows PowerShell-modulen.</span><span class="sxs-lookup"><span data-stu-id="c35b9-166">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="c35b9-167">Stäng PowerShell-fönstret.</span><span class="sxs-lookup"><span data-stu-id="c35b9-167">Close the PowerShell window</span></span>

<span data-ttu-id="c35b9-168">När du är redo att stänga ner PowerShell-fönstret kör du det här kommandot för att ta bort aktiva sessioner på Skype för Företag – Online, SharePoint Online och Teams:</span><span class="sxs-lookup"><span data-stu-id="c35b9-168">To close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a><span data-ttu-id="c35b9-169">Se även</span><span class="sxs-lookup"><span data-stu-id="c35b9-169">See also</span></span>

- [<span data-ttu-id="c35b9-170">Ansluta till Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="c35b9-170">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="c35b9-171">Hantera SharePoint Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="c35b9-171">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c35b9-172">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="c35b9-172">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
