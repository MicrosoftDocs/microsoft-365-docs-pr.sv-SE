---
title: Ansluta till Microsoft 365 med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Ansluta till Microsoft 365 klientorganisation med PowerShell för Microsoft 365 för att uppföra uppgifter i administrationscenter från kommandoraden.
ms.openlocfilehash: d1e347a13ca5c587fa544ef80a8e289a8dec0a59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694672"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="ce247-103">Ansluta till Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce247-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="ce247-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ce247-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ce247-105">Med PowerShell för Microsoft 365 kan du hantera dina Microsoft 365-inställningar från kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="ce247-105">PowerShell for Microsoft 365 lets you manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="ce247-106">Det är enkelt att ansluta till PowerShell där du kan installera den programvara som krävs och sedan ansluta till din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="ce247-106">Connecting to PowerShell is a simple process where you install the required software and then connect to your Microsoft 365 organization.</span></span> 

<span data-ttu-id="ce247-107">Det finns två versioner av PowerShell-modulen som du använder för att ansluta till Microsoft 365 och administrera användarkonton, grupper och licenser:</span><span class="sxs-lookup"><span data-stu-id="ce247-107">There are two versions of the PowerShell module that you use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="ce247-108">Azure Active Directory PowerShell för Graph (cmdletar inkluderar **AzureAD** i namnet)</span><span class="sxs-lookup"><span data-stu-id="ce247-108">Azure Active Directory PowerShell for Graph (cmdlets include **AzureAD** in their name)</span></span>
- <span data-ttu-id="ce247-109">Microsoft Azure Active Directory-modulen för Windows PowerShell (cmdlets innehåller**Msol** i namnet)</span><span class="sxs-lookup"><span data-stu-id="ce247-109">Microsoft Azure Active Directory Module for Windows PowerShell (cmdlets include **MSol** in their name)</span></span> 

<span data-ttu-id="ce247-110">Från och med datumet i den här artikeln ersätter Azure Active Directory PowerShell för Graph inte funktionaliteten i cmdletar för administration av Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen för användare, grupper och licenser.</span><span class="sxs-lookup"><span data-stu-id="ce247-110">As of the date of this article, the Azure Active Directory PowerShell for Graph module does not completely replace the functionality in the cmdlets of Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="ce247-111">I vissa fall måste du använda båda versionerna.</span><span class="sxs-lookup"><span data-stu-id="ce247-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="ce247-112">Du kan på ett säkert sätt installera båda versionerna på samma dator.</span><span class="sxs-lookup"><span data-stu-id="ce247-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ce247-113">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="ce247-113">What do you need to know before you begin?</span></span>

<span data-ttu-id="ce247-114">Du kan använda följande versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="ce247-114">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="ce247-115">Windows 10, Windows 8.1, Windows 8 eller Windows 7 Service Pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="ce247-115">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="ce247-116">Firefox Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 eller Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="ce247-116">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce247-117">För Azure Active Directory PowerShell för Graph-modulen måste du använda PowerShell version 5.1 eller senare.</span><span class="sxs-lookup"><span data-stu-id="ce247-117">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span> <span data-ttu-id="ce247-118">För Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen måste du använda PowerShell version 5.1 eller senare upp till PowerShell version 6.</span><span class="sxs-lookup"><span data-stu-id="ce247-118">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later up to PowerShell version 6.</span></span> <span data-ttu-id="ce247-119">Du kan inte använda PowerShell version 7.</span><span class="sxs-lookup"><span data-stu-id="ce247-119">You cannot use PowerShell version 7.</span></span> <span data-ttu-id="ce247-120">För Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 och Windows Server 2008 R2 SP1 laddar du ned och installerar [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="ce247-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ce247-121">Använd en 64-bitarsversion av Windows.</span><span class="sxs-lookup"><span data-stu-id="ce247-121">Use a 64-bit version of Windows.</span></span> <span data-ttu-id="ce247-122">Stöd för 32-bitarsversionen Microsoft Azure Active Directory-modulen för Windows PowerShell har utgått i oktober 2014.</span><span class="sxs-lookup"><span data-stu-id="ce247-122">Support for the 32-bit version the Microsoft Azure Active Directory Module for Windows PowerShell was discontinued in October of 2014.</span></span>
    
<span data-ttu-id="ce247-123">De här procedurerna är avsedda för användaren som är medlemmar i en administratörs roll för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ce247-123">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="ce247-124">Mer information finns i [Om administratörsroller](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span><span class="sxs-lookup"><span data-stu-id="ce247-124">For more information, see [About admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="ce247-125">Ansluta med Azure Active Directory Windows PowerShell för Graph-modulen</span><span class="sxs-lookup"><span data-stu-id="ce247-125">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="ce247-126">Kommandon i Azure Active Directory PowerShell för Graph-modulen har **AzureAD** i namnet på cmdleten.</span><span class="sxs-lookup"><span data-stu-id="ce247-126">Commands in the Azure Active Directory PowerShell for Graph module have **AzureAD** in their cmdlet name.</span></span> <span data-ttu-id="ce247-127">Du kan installera [Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory)-modulen eller [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-3.6.1).</span><span class="sxs-lookup"><span data-stu-id="ce247-127">You can install the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) module or [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-3.6.1).</span></span>

<span data-ttu-id="ce247-128">För procedurer som kräver nya cmdletar i Azure Active Directory PowerShell för Graph-modulen ska du använda följande steg för att installera modulen och ansluta till din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="ce247-128">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, use these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="ce247-129">Mer information om stödet för olika versioner av Microsoft Windows finns i [Azure Active Directory PowerShell för Graph modulen](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span><span class="sxs-lookup"><span data-stu-id="ce247-129">See [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) for information about the support for different versions of Microsoft Windows.</span></span>
>

### <a name="step-1-install-required-software"></a><span data-ttu-id="ce247-130">Steg 1: installera den programvara som krävs</span><span class="sxs-lookup"><span data-stu-id="ce247-130">Step 1: Install required software</span></span>

<span data-ttu-id="ce247-131">De här stegen är nödvändiga en gång på datorn, inte varje gång du ansluter.</span><span class="sxs-lookup"><span data-stu-id="ce247-131">These steps are required once on your computer, not every time you connect.</span></span> <span data-ttu-id="ce247-132">Men du måste förmodligen installera nyare versioner av programvaran med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="ce247-132">However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1. <span data-ttu-id="ce247-133">Öppna en upphöjd PowerShell-kommandotolk i Windows (kör Windows PowerShell som administratör).</span><span class="sxs-lookup"><span data-stu-id="ce247-133">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="ce247-134">Kör det här kommandot i en **Windows PowerShell-kommandotolk på administratörsnivå**:</span><span class="sxs-lookup"><span data-stu-id="ce247-134">In the **Administrator: Windows PowerShell** command window, run this command:</span></span>
    
  ```powershell
  Install-Module -Name AzureAD
  ```

<span data-ttu-id="ce247-135">Om du uppmanas att installera en modul från en databas som inte är betrodd skriver du **Y** och trycker på RETUR.</span><span class="sxs-lookup"><span data-stu-id="ce247-135">If prompted about installing a module from an untrusted repository, type **Y** and press ENTER.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="ce247-136">Steg 2: Ansluta till Azure AD för din Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="ce247-136">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="ce247-137">Om du vill ansluta till Azure AD för din Microsoft 365-prenumeration med kontonamn och lösenord eller multifaktorautentisering (MFA) kör du ett av de här kommandona från en Windows PowerShell-kommandotolk (det behöver inte vara upphöjd).</span><span class="sxs-lookup"><span data-stu-id="ce247-137">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication (MFA), run one of these commands from a Windows PowerShell command prompt (it does not have to be elevated).</span></span>

| <span data-ttu-id="ce247-138">Office 365 moln</span><span class="sxs-lookup"><span data-stu-id="ce247-138">Office 365 cloud</span></span> | <span data-ttu-id="ce247-139">Kommando</span><span class="sxs-lookup"><span data-stu-id="ce247-139">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="ce247-140">Office 365 över hela världen (+ GCC)</span><span class="sxs-lookup"><span data-stu-id="ce247-140">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="ce247-141">Office 365 genom 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="ce247-141">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="ce247-142">Office 365 Tyskland</span><span class="sxs-lookup"><span data-stu-id="ce247-142">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="ce247-143">Office 365 U.S. Government DoD och Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="ce247-143">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="ce247-144">Skriv ditt användarnamn och lösenord för ditt Microsoft 365-konto för arbetet eller skolan i **Logga in på ditt konto**, och klicka sedan på**OK**.</span><span class="sxs-lookup"><span data-stu-id="ce247-144">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then click **OK**.</span></span>

<span data-ttu-id="ce247-145">Om du använder MFA, följ anvisningarna i de andra dialogrutarna för att ange ytterligare autentiseringsinformation, till exempel en verifieringskod.</span><span class="sxs-lookup"><span data-stu-id="ce247-145">If you are using MFA, follow the instructions in the additional dialog boxes to provide more authentication information, such as a verification code.</span></span>

<span data-ttu-id="ce247-146">När du har anslutit kan du använda cmdletar för [Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span><span class="sxs-lookup"><span data-stu-id="ce247-146">After connecting, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span></span>
  

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="ce247-147">Ansluta med Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce247-147">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="ce247-148">Kommandon Azure Active Directory-modul för Windows PowerShell innehåller **Msol** in cmdlet-namnet.</span><span class="sxs-lookup"><span data-stu-id="ce247-148">Commands in the Microsoft Azure Active Directory Module for Windows PowerShell have **Msol** in their cmdlet name.</span></span>

<span data-ttu-id="ce247-149">PowerShell version 7 och senare stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell modulen och-cmdlets med**MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="ce247-149">PowerShell version 7 and later do not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="ce247-150">För PowerShell version 7 eller senare måste du använda Azure Active Directory PowerShell för Graph-modulen eller Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce247-150">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="ce247-151">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="ce247-151">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="ce247-152">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce247-152">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span> 
    
### <a name="step-1-install-required-software"></a><span data-ttu-id="ce247-153">Steg 1: installera den programvara som krävs</span><span class="sxs-lookup"><span data-stu-id="ce247-153">Step 1: Install required software</span></span>

<span data-ttu-id="ce247-154">De här stegen är nödvändiga en gång på datorn, inte varje gång du ansluter.</span><span class="sxs-lookup"><span data-stu-id="ce247-154">These steps are required once on your computer, not every time you connect.</span></span> <span data-ttu-id="ce247-155">Men du måste förmodligen installera nyare versioner av programvaran med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="ce247-155">However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1.  <span data-ttu-id="ce247-156">Om du inte kör Windows 10, installera 64-bitarsversionen av Microsoft Online Services – inloggningsassistent: [Microsoft Online Services – inloggningsassistent för IT-experter RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="ce247-156">If you are not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
    
2. <span data-ttu-id="ce247-157">Installera Microsoft Azure Active Directory-modulen för Windows PowerShell genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="ce247-157">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>
    
  - <span data-ttu-id="ce247-158">Öppna en upphöjd PowerShell-kommandotolk i Windows (kör Windows PowerShell som administratör).</span><span class="sxs-lookup"><span data-stu-id="ce247-158">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
  - <span data-ttu-id="ce247-159">Kör kommandot **Installera-modul MSOnline**.</span><span class="sxs-lookup"><span data-stu-id="ce247-159">Run the **Install-Module MSOnline** command.</span></span>
  - <span data-ttu-id="ce247-160">Om du uppmanas att installera NuGet-leverantör skriver du **Y** och trycker på RETUR.</span><span class="sxs-lookup"><span data-stu-id="ce247-160">If prompted to install the NuGet provider, type **Y** and press ENTER.</span></span>
  - <span data-ttu-id="ce247-161">Om du uppmanas att installera modulen från PSGGallery, skriver du **Y** och trycker på RETUR.</span><span class="sxs-lookup"><span data-stu-id="ce247-161">If prompted to install the module from PSGallery, type **Y** and press ENTER.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="ce247-162">Steg 2: Ansluta till Azure AD för din Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="ce247-162">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="ce247-163">Om du vill ansluta till Azure AD för din Microsoft 365-prenumeration med kontonamn och lösenord eller multifaktorautentisering (MFA) kör du ett av de här kommandona från en Windows PowerShell-kommandotolk (det behöver inte vara upphöjd).</span><span class="sxs-lookup"><span data-stu-id="ce247-163">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication (MFA), run one of these commands from a Windows PowerShell command prompt (it does not have to be elevated).</span></span>

| <span data-ttu-id="ce247-164">Office 365 moln</span><span class="sxs-lookup"><span data-stu-id="ce247-164">Office 365 cloud</span></span> | <span data-ttu-id="ce247-165">Kommando</span><span class="sxs-lookup"><span data-stu-id="ce247-165">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="ce247-166">Office 365 över hela världen (+ GCC)</span><span class="sxs-lookup"><span data-stu-id="ce247-166">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="ce247-167">Office 365 genom 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="ce247-167">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="ce247-168">Office 365 Tyskland</span><span class="sxs-lookup"><span data-stu-id="ce247-168">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="ce247-169">Office 365 U.S. Government DoD och Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="ce247-169">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="ce247-170">Skriv ditt användarnamn och lösenord för ditt Microsoft 365-konto för arbetet eller skolan i **Logga in på ditt konto**, och klicka sedan på**OK**.</span><span class="sxs-lookup"><span data-stu-id="ce247-170">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then click **OK**.</span></span>

<span data-ttu-id="ce247-171">Om du använder MFA, följ anvisningarna i de andra dialogrutarna för att ange ytterligare autentiseringsinformation, till exempel en verifieringskod.</span><span class="sxs-lookup"><span data-stu-id="ce247-171">If you are using MFA, follow the instructions in the additional dialog boxes to provide more authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ce247-172">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="ce247-172">How do you know this worked?</span></span>

<span data-ttu-id="ce247-173">Om du inte får några felmeddelande kunde du ansluta.</span><span class="sxs-lookup"><span data-stu-id="ce247-173">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="ce247-174">Ett snabb test är att köra en Microsoft 365-cmdlet, till exempel**get-MsolUser**och se resultatet.</span><span class="sxs-lookup"><span data-stu-id="ce247-174">A quick test is to run a Microsoft 365 cmdlet—for example, **Get-MsolUser** —and see the results.</span></span>
  
<span data-ttu-id="ce247-175">Om du får felfelmeddelanden, kontrollera följande krav:</span><span class="sxs-lookup"><span data-stu-id="ce247-175">If you receive errors, check the following requirements:</span></span>
  
- <span data-ttu-id="ce247-176">**Ett vanligt problem är ett felaktigt lösenord**.</span><span class="sxs-lookup"><span data-stu-id="ce247-176">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="ce247-177">Kör steg 2 igen.</span><span class="sxs-lookup"><span data-stu-id="ce247-177">Run Step 2 again.</span></span> <span data-ttu-id="ce247-178">och var uppmärksam på det användarnamn och lösenord som du anger.</span><span class="sxs-lookup"><span data-stu-id="ce247-178">and pay close attention to the user name and password you enter.</span></span>
    
- <span data-ttu-id="ce247-179">\**Microsoft Azure Active Directory-modulen för Windows PowerShell kräver att Microsoft .NET Framework 3.5.* funktionen x \* är aktiverad på din dator \* *. Det är troligt att datorn har en nyare version installerad (till exempel 4 eller 4.5*. x \*), men bakåtkompatibilitet med äldre versioner av .NET Framework kan aktiveras eller inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="ce247-179">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that the Microsoft .NET Framework 3.5.* x* feature is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*), but backwards compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="ce247-180">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="ce247-180">For more information, see the following topics:</span></span>
    
  - <span data-ttu-id="ce247-181">För mer information om Windows Server 2012 eller Windows Server 2012 R2 se[Aktivera .NET Framework 3.5 med hjälp av guiden Lägg till roller och funktioner](https://go.microsoft.com/fwlink/p/?LinkId=532368)</span><span class="sxs-lookup"><span data-stu-id="ce247-181">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368)</span></span>
    
  - <span data-ttu-id="ce247-182">För Windows 7 eller Windows Server 2008 R2 se [Det går inte att öppna Azure Active Directory-modulen för Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370)</span><span class="sxs-lookup"><span data-stu-id="ce247-182">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370)</span></span>

  - <span data-ttu-id="ce247-183">För Windows 10, Windows 8.1, och Windows 8, se [Installera .NET Framework 3.5 i Windows 10, Windows 8.1, och Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span><span class="sxs-lookup"><span data-stu-id="ce247-183">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span></span>

  
- <span data-ttu-id="ce247-184">**Din version av Microsoft Azure Active Directory-modulen för Windows PowerShell kanske är inaktuell.**</span><span class="sxs-lookup"><span data-stu-id="ce247-184">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="ce247-185">Om du vill kontrollera detta kör du följande kommando i PowerShell för Microsoft 365 eller Microsoft Azure Active Directory-modulen för Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ce247-185">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="ce247-186">Om versionsnumret som returneras är lägre än värdet 1.0.8070.2, avinstallerar du Microsoft Azure Active Directory-modulen för Windows PowerShell och installerar från steg 1 ovan.</span><span class="sxs-lookup"><span data-stu-id="ce247-186">If the version number returned is lower than the value 1.0.8070.2, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from Step 1 above.</span></span>

- <span data-ttu-id="ce247-187">**Om du får ett anslutningsfel se ämnet:** ["Ansluta-MsolService: ett undantag av typen har kastats" misslyckades](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span><span class="sxs-lookup"><span data-stu-id="ce247-187">**If you receive a connection error, see this topic:** ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
- <span data-ttu-id="ce247-188">**Om du får felmeddelandet "Hämta objekt: det går inte att hitta sökvägen" använder du följande kommando:**</span><span class="sxs-lookup"><span data-stu-id="ce247-188">**If you receive a "Get-Item : Cannot find path" error, use this command:**</span></span> 

```powershell
  (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
```

## <a name="see-also"></a><span data-ttu-id="ce247-189">Se även</span><span class="sxs-lookup"><span data-stu-id="ce247-189">See also</span></span>

- [<span data-ttu-id="ce247-190">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce247-190">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="ce247-191">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ce247-191">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="ce247-192">Ansluta till alla Microsoft 365-tjänster i ett enda Windows PowerShell-fönster</span><span class="sxs-lookup"><span data-stu-id="ce247-192">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
