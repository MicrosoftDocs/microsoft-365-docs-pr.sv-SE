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
description: Anslut till din Microsoft 365-klientorganisation med PowerShell för Microsoft 365 för att utföra uppgifter i administrationscenter från kommandoraden.
ms.openlocfilehash: 33f9af45418ae8a1f126d2b321e7246201bd1f6e
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002411"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="05670-103">Ansluta till Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="05670-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="05670-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="05670-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="05670-105">Med PowerShell för Microsoft 365 kan du hantera dina Microsoft 365-inställningar från kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="05670-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="05670-106">Om du vill ansluta till PowerShell installerar du bara den programvara som krävs och ansluter sedan till din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="05670-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="05670-107">Det finns två versioner av PowerShell-modulen som du kan använda för att ansluta till Microsoft 365 och administrera användarkonton, grupper och licenser:</span><span class="sxs-lookup"><span data-stu-id="05670-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="05670-108">Azure Active Directory PowerShell för Graph, vars cmdlets har *AzureAD* i namnet</span><span class="sxs-lookup"><span data-stu-id="05670-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="05670-109">Microsoft Azure Active Directory-modul för Windows PowerShell, vars cmdlets har *Msol* i namnet</span><span class="sxs-lookup"><span data-stu-id="05670-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="05670-110">För närvarande ersätter Azure Active Directory PowerShell för Graph-modulen inte helt funktionaliteten i Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen för användar-, grupp- och licensadministration.</span><span class="sxs-lookup"><span data-stu-id="05670-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="05670-111">I vissa fall måste du använda båda versionerna.</span><span class="sxs-lookup"><span data-stu-id="05670-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="05670-112">Du kan på ett säkert sätt installera båda versionerna på samma dator.</span><span class="sxs-lookup"><span data-stu-id="05670-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="05670-113">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="05670-113">What do you need to know before you begin?</span></span>


<span data-ttu-id="05670-114">**Operativsystem**</span><span class="sxs-lookup"><span data-stu-id="05670-114">**Operating system**</span></span>

<span data-ttu-id="05670-115">Du måste använda en 64-bitarsversion av Windows.</span><span class="sxs-lookup"><span data-stu-id="05670-115">You must use a 64-bit version of Windows.</span></span> <span data-ttu-id="05670-116">Stöd för 32-bitarsversionen av Microsoft Azure Active Directory-modulen för Windows PowerShell utgick i oktober 2014.</span><span class="sxs-lookup"><span data-stu-id="05670-116">Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="05670-117">Du kan använda följande versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="05670-117">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="05670-118">Windows 10, Windows 8.1, Windows 8 eller Windows 7 Service Pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="05670-118">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="05670-119">Firefox Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 eller Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="05670-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="05670-120">För Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 och Windows Server 2008 R2 SP1 laddar du ned och installerar [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="05670-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="05670-121">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="05670-121">**PowerShell**</span></span>

- <span data-ttu-id="05670-122">För Azure Active Directory PowerShell för Graph-modulen måste du använda PowerShell version 5.1 eller senare.</span><span class="sxs-lookup"><span data-stu-id="05670-122">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="05670-123">För Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen måste du använda PowerShell version 5.1 eller senare, upp till PowerShell version 6.</span><span class="sxs-lookup"><span data-stu-id="05670-123">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6.</span></span> <span data-ttu-id="05670-124">Du kan inte använda PowerShell version 7.</span><span class="sxs-lookup"><span data-stu-id="05670-124">You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="05670-125">De här procedurerna är avsedda för användaren som är medlemmar i en administratörs roll för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="05670-125">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="05670-126">Mer information finns i [Om administratörsroller](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span><span class="sxs-lookup"><span data-stu-id="05670-126">For more information, see [About admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="05670-127">Ansluta med Azure Active Directory Windows PowerShell för Graph-modulen</span><span class="sxs-lookup"><span data-stu-id="05670-127">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="05670-128">Kommandon i Azure Active Directory PowerShell för Graph-modulen har *AzureAD* i namnet på cmdleten.</span><span class="sxs-lookup"><span data-stu-id="05670-128">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="05670-129">Du kan installera [Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)-modulen eller [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="05670-129">You can install the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="05670-130">För procedurer som kräver nya cmdlets i Azure Active Directory PowerShell för Graph-modulen ska du använda följande steg för att installera modulen och ansluta till din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="05670-130">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="05670-131">Mer information om stödet för olika versioner av Microsoft Windows finns i [Azure Active Directory PowerShell för Graph-modul](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="05670-131">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="05670-132">Steg 1: Installera den programvara som krävs</span><span class="sxs-lookup"><span data-stu-id="05670-132">Step 1: Install the required software</span></span>

<span data-ttu-id="05670-133">De här stegen krävs bara en gång på din dator.</span><span class="sxs-lookup"><span data-stu-id="05670-133">These steps are required only one time on your computer.</span></span> <span data-ttu-id="05670-134">Men du måste troligen uppdatera programvaran regelbundet.</span><span class="sxs-lookup"><span data-stu-id="05670-134">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="05670-135">Öppna ett upphöjt PowerShell-kommandotolkfönster (kör Windows PowerShell som administratör).</span><span class="sxs-lookup"><span data-stu-id="05670-135">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="05670-136">Kör det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="05670-136">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

   <span data-ttu-id="05670-137">Om du uppmanas att installera en modul från en databas som inte är betrodd skriver du **Y** och trycker på Retur.</span><span class="sxs-lookup"><span data-stu-id="05670-137">If you're prompted to install a module from an untrusted repository, type **Y** and press Enter.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="05670-138">Steg 2: Ansluta till Azure AD för din Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="05670-138">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="05670-139">För att ansluta till Azure Active Directory (Azure AD) för din Microsoft 365-prenumeration med ett kontonamn och lösenord, eller med multifaktorautentisering (MFA), kör du ett av de här kommandona från en Windows PowerShell-kommandotolk.</span><span class="sxs-lookup"><span data-stu-id="05670-139">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="05670-140">(Det behöver inte vara upphöjt.)</span><span class="sxs-lookup"><span data-stu-id="05670-140">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="05670-141">Office 365 moln</span><span class="sxs-lookup"><span data-stu-id="05670-141">Office 365 cloud</span></span> | <span data-ttu-id="05670-142">Kommando</span><span class="sxs-lookup"><span data-stu-id="05670-142">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="05670-143">Office 365 över hela världen (+ GCC)</span><span class="sxs-lookup"><span data-stu-id="05670-143">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="05670-144">Office 365 genom 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="05670-144">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="05670-145">Office 365 Tyskland</span><span class="sxs-lookup"><span data-stu-id="05670-145">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="05670-146">Office 365 U.S. Government DoD och Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="05670-146">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="05670-147">Skriv ditt användarnamn och lösenord för ditt Microsoft 365-konto för arbetet eller skolan i dialogrutan **Logga in på ditt konto**, och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="05670-147">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="05670-148">Om du använder multifaktorautentisering, följ instruktionerna för att ange ytterligare autentiseringsinformation, till exempel en verifieringskod.</span><span class="sxs-lookup"><span data-stu-id="05670-148">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="05670-149">När du har anslutit kan du använda cmdlets för [Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/powershell/module/azuread).</span><span class="sxs-lookup"><span data-stu-id="05670-149">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="05670-150">Ansluta med Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05670-150">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="05670-151">Cmdlets i Microsoft Azure Active Directory-modulen för Windows PowerShell har *Msol* i namnet.</span><span class="sxs-lookup"><span data-stu-id="05670-151">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="05670-152">PowerShell version 7 och senare stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell modul och cmdlets med *Msol* i namnet.</span><span class="sxs-lookup"><span data-stu-id="05670-152">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="05670-153">För PowerShell version 7 eller senare måste du använda Azure Active Directory PowerShell för Graph-modulen eller Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05670-153">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="05670-154">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *Msol* i namnet.</span><span class="sxs-lookup"><span data-stu-id="05670-154">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="05670-155">Kör dessa cmdlets från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05670-155">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="05670-156">Steg 1: Installera den programvara som krävs</span><span class="sxs-lookup"><span data-stu-id="05670-156">Step 1: Install the required software</span></span>

<span data-ttu-id="05670-157">De här stegen krävs bara en gång på din dator.</span><span class="sxs-lookup"><span data-stu-id="05670-157">These steps are required only one time on your computer.</span></span> <span data-ttu-id="05670-158">Men du måste troligen uppdatera programvaran regelbundet.</span><span class="sxs-lookup"><span data-stu-id="05670-158">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="05670-159">Om du inte kör Windows 10, installera 64-bitarsversionen av Inloggningsassistenten för Microsoft Online Services: [Inloggningsassistenten för Microsoft Online Services för IT-experter RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="05670-159">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
    
2. <span data-ttu-id="05670-160">Följ de här stegen för att installera Microsoft Azure Active Directory-modulen för Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="05670-160">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="05670-161">Öppna en upphöjd PowerShell-kommandotolk i Windows (kör Windows PowerShell som administratör).</span><span class="sxs-lookup"><span data-stu-id="05670-161">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="05670-162">Kör kommandot **Installera-modul MSOnline**.</span><span class="sxs-lookup"><span data-stu-id="05670-162">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="05670-163">Om du uppmanas att installera NuGet-leverantören, skriv **Y** och tryck på Retur.</span><span class="sxs-lookup"><span data-stu-id="05670-163">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="05670-164">Om du uppmanas att installera modulen från PSGGallery, skriv **Y** och tryck på Retur.</span><span class="sxs-lookup"><span data-stu-id="05670-164">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="05670-165">Steg 2: Ansluta till Azure AD för din Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="05670-165">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="05670-166">För att ansluta till Azure AD för din Microsoft 365-prenumeration med ett kontonamn och lösenord eller med multifaktorautentisering (MFA), kör ett av de här kommandona från en Windows PowerShell-kommandotolk.</span><span class="sxs-lookup"><span data-stu-id="05670-166">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="05670-167">(Det behöver inte vara upphöjt.)</span><span class="sxs-lookup"><span data-stu-id="05670-167">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="05670-168">Office 365 moln</span><span class="sxs-lookup"><span data-stu-id="05670-168">Office 365 cloud</span></span> | <span data-ttu-id="05670-169">Kommando</span><span class="sxs-lookup"><span data-stu-id="05670-169">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="05670-170">Office 365 över hela världen (+ GCC)</span><span class="sxs-lookup"><span data-stu-id="05670-170">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="05670-171">Office 365 genom 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="05670-171">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="05670-172">Office 365 Tyskland</span><span class="sxs-lookup"><span data-stu-id="05670-172">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="05670-173">Office 365 U.S. Government DoD och Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="05670-173">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="05670-174">Skriv ditt användarnamn och lösenord för ditt Microsoft 365-konto för arbetet eller skolan i dialogrutan **Logga in på ditt konto**, och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="05670-174">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="05670-175">Om du använder multifaktorautentisering, följ instruktionerna för att ange ytterligare autentiseringsinformation, till exempel en verifieringskod.</span><span class="sxs-lookup"><span data-stu-id="05670-175">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="05670-176">Hur vet du om det har fungerat?</span><span class="sxs-lookup"><span data-stu-id="05670-176">How do you know it worked?</span></span>

<span data-ttu-id="05670-177">Om du inte får ett felmeddelande har du anslutit framgångsrikt.</span><span class="sxs-lookup"><span data-stu-id="05670-177">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="05670-178">Ett snabbt test är att köra en Microsoft 365-cmdlet, till exempel **Get-MsolUser** och se resultaten.</span><span class="sxs-lookup"><span data-stu-id="05670-178">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="05670-179">Om du får ett felmeddelande, kontrollera följande problem:</span><span class="sxs-lookup"><span data-stu-id="05670-179">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="05670-180">**Ett vanligt problem är ett felaktigt lösenord**.</span><span class="sxs-lookup"><span data-stu-id="05670-180">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="05670-181">Kör [Steg 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) igen och var uppmärksam på det användarnamn och lösenord som du anger.</span><span class="sxs-lookup"><span data-stu-id="05670-181">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="05670-182">**Microsoft Azure Active Directory-modulen för Windows PowerShell kräver att Microsoft .NET Framework 3.5.* x* är aktiverad på din dator**. Det är troligt att din dator har en nyare version installerad (till exempel 4 eller 4.5.* x*).</span><span class="sxs-lookup"><span data-stu-id="05670-182">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="05670-183">Men bakåtkompatibilitet med äldre versioner av .NET Framework kan aktiveras och inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="05670-183">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="05670-184">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="05670-184">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="05670-185">Mer information om Windows Server 2012 eller Windows Server 2012 R2 finns i[Aktivera .NET Framework 3.5 med hjälp av guiden Lägg till roller och funktioner](https://go.microsoft.com/fwlink/p/?LinkId=532368).</span><span class="sxs-lookup"><span data-stu-id="05670-185">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368).</span></span>
    
  - <span data-ttu-id="05670-186">För Windows 7 eller Windows Server 2008 R2 läser du [Det går inte att öppna Azure Active Directory-modulen för Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).</span><span class="sxs-lookup"><span data-stu-id="05670-186">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).</span></span>

  - <span data-ttu-id="05670-187">För Windows 10, Windows 8.1 och Windows 8 läser du [Installera .NET Framework 3.5 i Windows 10, Windows 8.1 och Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10).</span><span class="sxs-lookup"><span data-stu-id="05670-187">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="05670-188">**Din version av Microsoft Azure Active Directory-modulen för Windows PowerShell kanske är inaktuell.**</span><span class="sxs-lookup"><span data-stu-id="05670-188">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="05670-189">Om du vill kontrollera detta kör du följande kommando i PowerShell för Microsoft 365 eller Microsoft Azure Active Directory-modulen för Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="05670-189">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="05670-190">Om versionsnumret som returneras är lägre än *1.0.8070.2*, avinstallerar Microsoft Azure Active Directory-modulen för Windows PowerShell och installerar från [Steg 1](#step-1-install-the-required-software)ovan.</span><span class="sxs-lookup"><span data-stu-id="05670-190">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="05670-191">**Om du får ett anslutningsfelmeddelande**, se [Felet "Connect-MsolService: Undantag av typen" misslyckades](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span><span class="sxs-lookup"><span data-stu-id="05670-191">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
- <span data-ttu-id="05670-192">**Om du får felmeddelandet "Get-Item: Det går inte att hitta sökvägen"**, kör kommandot:</span><span class="sxs-lookup"><span data-stu-id="05670-192">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a><span data-ttu-id="05670-193">Se även</span><span class="sxs-lookup"><span data-stu-id="05670-193">See also</span></span>

- [<span data-ttu-id="05670-194">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="05670-194">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="05670-195">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="05670-195">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="05670-196">Ansluta till alla Microsoft 365-tjänster i ett enda Windows PowerShell-fönster</span><span class="sxs-lookup"><span data-stu-id="05670-196">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
