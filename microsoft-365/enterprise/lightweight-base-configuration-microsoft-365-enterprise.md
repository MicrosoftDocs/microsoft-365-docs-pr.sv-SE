---
title: Enkel baskonfiguration
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Använd den här testlabbguiden för att skapa en lätt testmiljö för att testa Microsoft 365 för företag.
ms.openlocfilehash: 2de0760cef7339f62229575b1e0a54b3c67a4e9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909712"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="46045-103">Den enkla baskonfigurationen</span><span class="sxs-lookup"><span data-stu-id="46045-103">The lightweight base configuration</span></span>

<span data-ttu-id="46045-104">*Den här testlabbguiden kan användas för både Microsoft 365 för företag- och Office 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="46045-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="46045-105">I den här artikeln beskrivs hur du skapar en förenklad miljö med en Microsoft 365 E5-prenumeration och en dator med Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="46045-105">This article describes how to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span>

![Den förenklade testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="46045-107">Att skapa en lätt testmiljö omfattar fem faser:</span><span class="sxs-lookup"><span data-stu-id="46045-107">Creating a lightweight test environment involves five phases:</span></span>
- [<span data-ttu-id="46045-108">Steg 1: Skapa din Microsoft 365 E5-prenumeration</span><span class="sxs-lookup"><span data-stu-id="46045-108">Phase 1: Create your Microsoft 365 E5 subscription</span></span>](#phase-1-create-your-microsoft-365-e5-subscription)
- [<span data-ttu-id="46045-109">Fas 2: Konfigurera utvärderingsprenumerationen för Office 365</span><span class="sxs-lookup"><span data-stu-id="46045-109">Phase 2: Configure your Office 365 trial subscription</span></span>](#phase-2-configure-your-office-365-trial-subscription)
- [<span data-ttu-id="46045-110">Fas 3: Lägga till en utvärderingsprenumeration på Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="46045-110">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [<span data-ttu-id="46045-111">Fas 4: Skapa en Windows 10 Enterprise-dator</span><span class="sxs-lookup"><span data-stu-id="46045-111">Phase 4: Create a Windows 10 Enterprise computer</span></span>](#phase-4-create-a-windows-10-enterprise-computer)
- [<span data-ttu-id="46045-112">Fas 5: Ansluta Windows 10-datorn till Azure AD</span><span class="sxs-lookup"><span data-stu-id="46045-112">Phase 5: Join your Windows 10 computer to Azure AD</span></span>](#phase-5-join-your-windows-10-computer-to-azure-ad)

<span data-ttu-id="46045-113">Använd den resulterande miljön för att testa funktionerna i [Microsoft 365 för företag.](https://www.microsoft.com/microsoft-365/enterprise)</span><span class="sxs-lookup"><span data-stu-id="46045-113">Use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="46045-115">En visuell karta till alla artiklar i microsoft 365 för företag – testlabbguide stack finns i [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)testlabbguide stack.</span><span class="sxs-lookup"><span data-stu-id="46045-115">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, see [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

>[!NOTE]
><span data-ttu-id="46045-116">Det kan vara bra att skriva ut den här artikeln för att kunna skriva ned den specifika information som du behöver för den här miljön under de 30 dagar som Office 365-utvärderingsprenumerationen gäller.</span><span class="sxs-lookup"><span data-stu-id="46045-116">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="46045-117">Du kan enkelt utöka utvärderingsprenumerationen i ytterligare 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="46045-117">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="46045-118">För en permanent testmiljö skapar du en ny betald prenumeration med en separat Azure AD-klient och ett litet antal licenser.</span><span class="sxs-lookup"><span data-stu-id="46045-118">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="46045-119">Steg 1: Skapa din Microsoft 365 E5-prenumeration</span><span class="sxs-lookup"><span data-stu-id="46045-119">Phase 1: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="46045-120">Vi börjar med en utvärderingsprenumeration på Microsoft 365 E5 och lägger sedan till Microsoft 365 E5-prenumerationen i den.</span><span class="sxs-lookup"><span data-stu-id="46045-120">We start with an Microsoft 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

>[!NOTE]
><span data-ttu-id="46045-121">Vi rekommenderar att du skapar en utvärderingsprenumeration av Office 365 så att testmiljön har en separat Azure AD-klientorganisation från de betalprenumerationer du har för närvarande.</span><span class="sxs-lookup"><span data-stu-id="46045-121">We recommend that you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="46045-122">Den här separationen innebär att du kan lägga till och ta bort användare och grupper i testklientorganisationen utan att påverka produktionsprenumerationerna.</span><span class="sxs-lookup"><span data-stu-id="46045-122">This separation means that you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>

<span data-ttu-id="46045-123">För att starta utvärderingsprenumerationen på Microsoft 365 E5 måste du först ett fiktivt företagsnamn och ett nytt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="46045-123">To start your Microsoft 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="46045-124">Vi rekommenderar att du använder en variant av företagsnamnet Contoso som ditt företagsnamn, vilket är ett fiktivt företag som används i Microsoft-exempelinnehåll, men det är inget krav.</span><span class="sxs-lookup"><span data-stu-id="46045-124">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required.</span></span> <span data-ttu-id="46045-125">Skriv ditt fiktiva företagsnamn här:</span><span class="sxs-lookup"><span data-stu-id="46045-125">Record your fictitious company name here:</span></span> ![Rad](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="46045-127">Om du vill registrera dig för ett nytt Microsoft-konto går du till [https://outlook.com](https://outlook.com) och skapar ett konto med ett nytt e-postkonto och en ny e-postadress.</span><span class="sxs-lookup"><span data-stu-id="46045-127">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address.</span></span> <span data-ttu-id="46045-128">Du använder det här kontot för att registrera dig för Office 365.</span><span class="sxs-lookup"><span data-stu-id="46045-128">You will use this account to sign up for Office 365.</span></span>
    
    - <span data-ttu-id="46045-129">Skriv för- och efternamn för ditt nya konto här:</span><span class="sxs-lookup"><span data-stu-id="46045-129">Record the first and last name of your new account here:</span></span> ![Rad](../media/Common-Images/TableLine.png)
    
    - <span data-ttu-id="46045-131">Skriv den nya adressen för e-postkontot här:</span><span class="sxs-lookup"><span data-stu-id="46045-131">Record the new email account address here:</span></span> ![Rad](../media/Common-Images/TableLine.png)<span data-ttu-id="46045-133">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="46045-133">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="46045-134">Registrera dig för en utvärderingsprenumeration på Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="46045-134">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="46045-135">Öppna webbläsaren och gå till [https://aka.ms/e5trial](https://aka.ms/e5trial) .</span><span class="sxs-lookup"><span data-stu-id="46045-135">In your browser, go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="46045-136">I steg 1 på sidan **Tack för att du väljer Office 365 E5** anger du adressen till det nya e-postkontot.</span><span class="sxs-lookup"><span data-stu-id="46045-136">In step 1 of the **Thank you for choosing Office 365 E5** page, enter your new email account address.</span></span>
3. <span data-ttu-id="46045-137">I steg 2 i trail-prenumerationsprocessen anger du den begärda informationen och utför sedan verifieringen.</span><span class="sxs-lookup"><span data-stu-id="46045-137">In step 2 of the trail subscription process, enter the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="46045-138">I steg 3 anger du ett organisationsnamn och sedan ett kontonamn som blir global administratör för prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="46045-138">In step 3, enter an organization name and then an account name that will be the global admin for the subscription.</span></span>
5. <span data-ttu-id="46045-139">För steg 4 skriver du inloggningssidan här (markera och kopiera):</span><span class="sxs-lookup"><span data-stu-id="46045-139">For step 4, record the sign-in page here (select and copy):</span></span> ![Rad](../media/Common-Images/TableLine.png)
6. <span data-ttu-id="46045-141">Skriv användar-ID här: ![Rad](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="46045-141">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="46045-142">Registrera det lösenord som du angav på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="46045-142">Record the password that you entered in a secure location.</span></span>
   <span data-ttu-id="46045-143">Det här värdet kommer att kallas för det **globala administratörsnamnet**.</span><span class="sxs-lookup"><span data-stu-id="46045-143">This value will be referred to as the **global administrator name**.</span></span>
7. <span data-ttu-id="46045-144">Välj **Gå till installationsprogrammet.**</span><span class="sxs-lookup"><span data-stu-id="46045-144">Select **Go to Setup**.</span></span>
8. <span data-ttu-id="46045-145">I installationsprogrammet för Office 365 E5 väljer du Fortsätt använda din organisation **.onmicrosoft.com** för e-post och inloggning, och välj sedan **Avsluta och fortsätt senare.**</span><span class="sxs-lookup"><span data-stu-id="46045-145">In Office 365 E5 Setup, select **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then select **Exit and continue later**.</span></span>

<span data-ttu-id="46045-146">Du bör se administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="46045-146">You should see the Microsoft 365 admin center.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="46045-147">Fas 2: Konfigurera utvärderingsprenumerationen för Office 365</span><span class="sxs-lookup"><span data-stu-id="46045-147">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="46045-148">I den här fasen konfigurerar du prenumerationen med ytterligare användare och tilldelar dem Office 365 E5-licenser.</span><span class="sxs-lookup"><span data-stu-id="46045-148">In this phase, you configure your subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="46045-149">Om du vill ansluta till prenumerationen med Azure Active Directory PowerShell för Graph-modulen från datorn följer du anvisningarna i Ansluta till [Microsoft 365 med PowerShell.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="46045-149">To connect to your subscription with the Azure Active Directory PowerShell for Graph module from your computer, use the instructions in [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
    
<span data-ttu-id="46045-150">I dialogrutan **Begäran om autentiseringsuppgifter** för Windows PowerShell anger du namnet på den globala administratören (till exempel *jdoe@contosotoycompany.onmicrosoft.com*) och lösenord.</span><span class="sxs-lookup"><span data-stu-id="46045-150">In the **Windows PowerShell Credential Request** dialog box, enter the global administrator name (for example, *jdoe@contosotoycompany.onmicrosoft.com*) and password.</span></span>
  
<span data-ttu-id="46045-151">Fyll i ditt organisationsnamn (till exempel *contosotoycompany),* landskoden på två tecken för din plats, ett vanligt kontolösenord och kör sedan följande kommandon från PowerShell-kommandotolken:</span><span class="sxs-lookup"><span data-stu-id="46045-151">Fill in your organization name (for example, *contosotoycompany*), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> <span data-ttu-id="46045-152">Användningen av ett gemensamt lösenord här är för automatisering och enklare konfiguration för en testmiljö.</span><span class="sxs-lookup"><span data-stu-id="46045-152">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="46045-153">Självklart rekommenderas detta inte för produktionsprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="46045-153">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="46045-154">Skriv ned viktig information för framtida referens</span><span class="sxs-lookup"><span data-stu-id="46045-154">Record key information for future reference</span></span>

<span data-ttu-id="46045-155">Om du inte redan har spelat in dessa värden spelar du in dem nu:</span><span class="sxs-lookup"><span data-stu-id="46045-155">If you haven't already recorded these values, record them now:</span></span>
  
- <span data-ttu-id="46045-156">Global administratör:</span><span class="sxs-lookup"><span data-stu-id="46045-156">Global administrator name:</span></span> ![Rad](../media/Common-Images/TableLine.png)<span data-ttu-id="46045-158">.onmicrosoft.com (från steg 6 i fas 1)</span><span class="sxs-lookup"><span data-stu-id="46045-158">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="46045-159">Anteckna också lösenordet för det här kontot på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="46045-159">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="46045-160">Organisationens namn för utvärderingsprenumerationen:</span><span class="sxs-lookup"><span data-stu-id="46045-160">Your trial subscription organization name:</span></span> ![Rad](../media/Common-Images/TableLine.png) <span data-ttu-id="46045-162">(från steg 4 i fas 1)</span><span class="sxs-lookup"><span data-stu-id="46045-162">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="46045-163">Om du vill lista kontona för Användare 2, Användare 3, Användare 4 och Användare 5 kör du följande kommando från Windows Azure Active Directory-modulen för Windows PowerShell-prompten:</span><span class="sxs-lookup"><span data-stu-id="46045-163">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="46045-164">Skriv kontonamnen här:</span><span class="sxs-lookup"><span data-stu-id="46045-164">Record the account names here:</span></span>
    
  - <span data-ttu-id="46045-165">Kontonamn för Användare 2: användare2@</span><span class="sxs-lookup"><span data-stu-id="46045-165">User 2 account name: user2@</span></span>![Rad](../media/Common-Images/TableLine.png)<span data-ttu-id="46045-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="46045-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="46045-168">Kontonamn för Användare 3: användare3@</span><span class="sxs-lookup"><span data-stu-id="46045-168">User 3 account name: user3@</span></span>![Rad](../media/Common-Images/TableLine.png)<span data-ttu-id="46045-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="46045-170">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="46045-171">Kontonamn för Användare 4: användare4@</span><span class="sxs-lookup"><span data-stu-id="46045-171">User 4 account name: user4@</span></span>![Rad](../media/Common-Images/TableLine.png)<span data-ttu-id="46045-173">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="46045-173">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="46045-174">Kontonamn för Användare 5: användare5@</span><span class="sxs-lookup"><span data-stu-id="46045-174">User 5 account name: user5@</span></span>![Rad](../media/Common-Images/TableLine.png)<span data-ttu-id="46045-176">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="46045-176">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="46045-177">Anteckna också det gemensamma lösenordet för dessa konton på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="46045-177">Also record the common password for these accounts in a secure location.</span></span>
   
### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="46045-178">Använda en Office 365-testmiljö</span><span class="sxs-lookup"><span data-stu-id="46045-178">Using an Office 365 test environment</span></span>

<span data-ttu-id="46045-179">Om du bara behöver en Office 365-testmiljö behöver du inte läsa resten av den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="46045-179">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="46045-180">Fler testlabbguider som gäller för både Office 365 och Microsoft 365 finns i Testlabbguider för [Microsoft 365 för företag.](m365-enterprise-test-lab-guides.md)</span><span class="sxs-lookup"><span data-stu-id="46045-180">For additional Test Lab Guides that apply to both Office 365 and Microsoft 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="46045-181">Fas 3: Lägga till en utvärderingsprenumeration på Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="46045-181">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="46045-182">I den här fasen registrerar du dig för Microsoft 365 E5-utvärderingsprenumerationen och lägger till den i samma organisation som utvärderingsprenumerationen för Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="46045-182">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="46045-183">Lägg först till Microsoft 365 E5-utvärderingsprenumerationen och tilldela den nya licensen för Microsoft 365 till det globala administratörskontot.</span><span class="sxs-lookup"><span data-stu-id="46045-183">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="46045-184">Använd autentiseringsuppgifterna för ditt globala administratörskonto i ett privat webbläsarfönster för att logga in på administrationscentret för Microsoft 365 på [https://admin.microsoft.com](https://admin.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="46045-184">In an internet browser private window, use your global administrator account credentials to sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="46045-185">I det vänstra navigeringsfältet på sidan administrationscenter för **Microsoft 365** väljer **du Fakturering > Köptjänster.**</span><span class="sxs-lookup"><span data-stu-id="46045-185">On the **Microsoft 365 admin center** page, in the left navigation, select **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="46045-186">På sidan **Köp tjänster** väljer du **Microsoft 365 E5** och sedan Hämta **kostnadsfri utvärderingsversion.**</span><span class="sxs-lookup"><span data-stu-id="46045-186">On the **Purchase services** page, select **Microsoft 365 E5**, and then select **Get free trial**.</span></span>

4. <span data-ttu-id="46045-187">På sidan för utvärderingsversionen av **Microsoft 365 E5** väljer du att ta emot ett SMS eller ett telefonsamtal, anger ditt telefonnummer och väljer sedan **Sms:a** mig eller **Ring mig**.</span><span class="sxs-lookup"><span data-stu-id="46045-187">On the **Microsoft 365 E5 Trial** page, decide to receive a text message or a phone call, enter your phone number, and then select **Text me** or **Call me**.</span></span> <span data-ttu-id="46045-188">Utför verifieringen.</span><span class="sxs-lookup"><span data-stu-id="46045-188">Perform the verification.</span></span>

5. <span data-ttu-id="46045-189">På sidan **Bekräfta din beställning** väljer du Prova **nu.**</span><span class="sxs-lookup"><span data-stu-id="46045-189">On the **Confirm your order** page, select **Try now**.</span></span>

6. <span data-ttu-id="46045-190">På sidan **Orderkvitto** väljer du **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="46045-190">On the **Order receipt** page, select **Continue**.</span></span>

7. <span data-ttu-id="46045-191">I administrationscentret för Microsoft 365 väljer du **Användare > Aktiva användare.**</span><span class="sxs-lookup"><span data-stu-id="46045-191">In the Microsoft 365 admin center, select **Users > Active users**.</span></span>

8. <span data-ttu-id="46045-192">Välj **administratörskonto** i Aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="46045-192">In **Active users**, select your administrator account.</span></span>

9. <span data-ttu-id="46045-193">Välj **Licenser och appar.**</span><span class="sxs-lookup"><span data-stu-id="46045-193">Select **Licenses and apps**.</span></span>

10. <span data-ttu-id="46045-194">Inaktivera licensen för Office 365 Enterprise, E5 och aktivera licensen för Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="46045-194">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="46045-195">Välj **Spara ändringar** och stäng sedan informationsfönstret för användarkontot.</span><span class="sxs-lookup"><span data-stu-id="46045-195">Select **Save changes**, and then close the user account information pane.</span></span>

<span data-ttu-id="46045-196">Upprepa sedan steg 8 till 11 i föregående procedur för alla andra konton (Användare 2, Användare 3, Användare 4 och Användare 5).</span><span class="sxs-lookup"><span data-stu-id="46045-196">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="46045-197">Längden på utvärderingsprenumerationen på Microsoft 365 E5 är 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="46045-197">The length of the Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="46045-198">För en permanent testmiljö omvandlar du den här utvärderingsprenumeration till en betald prenumeration med ett litet antal licenser.</span><span class="sxs-lookup"><span data-stu-id="46045-198">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span>
  
<span data-ttu-id="46045-199">Din testmiljö har nu:</span><span class="sxs-lookup"><span data-stu-id="46045-199">Your test environment now has:</span></span>
  
- <span data-ttu-id="46045-200">En utvärderingsprenumeration på Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="46045-200">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="46045-201">Alla relevanta användarkonton (antingen bara det globala administratörskontot eller alla fem användarkonton) är aktiverade för att använda Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="46045-201">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="46045-202">Den resulterande konfigurationen, som lägger till Microsoft 365 E5, ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="46045-202">Your resulting configuration, which adds Microsoft 365 E5, looks like this:</span></span>
  
![Fas 3 av testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="46045-204">Fas 4: Skapa en Windows 10 Enterprise-dator</span><span class="sxs-lookup"><span data-stu-id="46045-204">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="46045-205">I den här fasen skapar du en fristående dator med Windows 10 Enterprise som en fysisk dator, en virtuell dator eller en virtuell Azure-dator.</span><span class="sxs-lookup"><span data-stu-id="46045-205">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="46045-206">Fysisk dator</span><span class="sxs-lookup"><span data-stu-id="46045-206">Physical computer</span></span>

<span data-ttu-id="46045-207">Installera Windows 10 Enterprise på en personlig dator.</span><span class="sxs-lookup"><span data-stu-id="46045-207">On a personal computer, install Windows 10 Enterprise.</span></span> <span data-ttu-id="46045-208">Du kan ladda ned utvärderingsversionen av Windows 10 Enterprise [här](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="46045-208">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="46045-209">Virtuell dator</span><span class="sxs-lookup"><span data-stu-id="46045-209">Virtual machine</span></span>

<span data-ttu-id="46045-210">Använd valfri hypervisor för att skapa en virtuell dator och installera sedan Windows 10 Enterprise på den.</span><span class="sxs-lookup"><span data-stu-id="46045-210">Use the hypervisor of your choice to create a virtual machine, and then install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="46045-211">Du kan ladda ned utvärderingsversionen av Windows 10 Enterprise [här](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="46045-211">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="46045-212">Virtuell dator i Azure</span><span class="sxs-lookup"><span data-stu-id="46045-212">Virtual machine in Azure</span></span>

<span data-ttu-id="46045-213">Om du vill skapa en virtuell Windows 10-dator i Microsoft Azure ***måste du ha en Visual Studio-baserad prenumeration***, som har åtkomst till avbildningen av Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="46045-213">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise.</span></span> <span data-ttu-id="46045-214">Andra typer av Azure-prenumerationer, t.ex. utvärderingsprenumerationer eller betalda prenumerationer, har inte åtkomst till den här avbildningen.</span><span class="sxs-lookup"><span data-stu-id="46045-214">Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image.</span></span> <span data-ttu-id="46045-215">Den senaste informationen finns i [Använda Windows-klienten i Azure för utvecklings-/testscenarier](/azure/virtual-machines/windows/client-images).</span><span class="sxs-lookup"><span data-stu-id="46045-215">For the latest information, see [Use Windows client in Azure for dev/test scenarios](/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="46045-216">Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46045-216">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="46045-217">Se [Kom igång med Azure PowerShell-cmdletar](/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="46045-217">See [Get started with Azure PowerShell cmdlets](/powershell/azureps-cmdlets-docs/).</span></span> <span data-ttu-id="46045-218">Med dessa kommandouppsättningar skapas en virtuell dator med Windows 10 Enterprise som heter WIN10 och all den infrastruktur som krävs, inklusive en resursgrupp, ett lagringskonto och ett virtuellt nätverk.</span><span class="sxs-lookup"><span data-stu-id="46045-218">These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network.</span></span> <span data-ttu-id="46045-219">Om du redan är bekant med Azure-infrastrukturtjänster kan du anpassa de här instruktionerna så att de passar din nuvarande använda infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="46045-219">If you are already familiar with Azure infrastructure services, adapt these instructions to suit your currently deployed infrastructure.</span></span>
  
<span data-ttu-id="46045-220">Starta först en Microsoft PowerShell-prompt.</span><span class="sxs-lookup"><span data-stu-id="46045-220">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="46045-221">Logga in på ditt Azure-konto med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="46045-221">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="46045-222">Skaffa namnet på din prenumeration med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="46045-222">Get your subscription name using this  command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="46045-223">Ange din Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="46045-223">Set your Azure subscription.</span></span> <span data-ttu-id="46045-224">Ersätt allt inom citattecknen, \< and > inklusive tecknen, med rätt namn.</span><span class="sxs-lookup"><span data-stu-id="46045-224">Replace everything within the quotation marks, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="46045-225">Skapa sedan en ny resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="46045-225">Next, create a new resource group.</span></span> <span data-ttu-id="46045-226">Använd det här kommandot för att lista dina befintliga resursgrupper när du ska fastställa ett unikt resursgruppnamn.</span><span class="sxs-lookup"><span data-stu-id="46045-226">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="46045-227">Skapa den nya resursgruppen med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="46045-227">Create your new resource group with these commands.</span></span> <span data-ttu-id="46045-228">Ersätt allt inom citattecknen, \< and > inklusive tecknen, med rätt namn.</span><span class="sxs-lookup"><span data-stu-id="46045-228">Replace everything within the quotation marks, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="46045-229">Skapa sedan ett nytt virtuellt nätverk och den virtuella WIN10-datorn med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="46045-229">Next, create a new virtual network and the WIN10 virtual machine with these commands.</span></span> <span data-ttu-id="46045-230">När du uppmanas till det anger du namnet och lösenordet för det lokala administratörskontot för WIN10 och sparar dessa på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="46045-230">When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="46045-231">Fas 5: Ansluta Windows 10-datorn till Azure AD</span><span class="sxs-lookup"><span data-stu-id="46045-231">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="46045-232">När du har skapat en fysisk eller virtuell dator med Windows 10 Enterprise loggar du in med ett lokalt administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="46045-232">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="46045-233">Använd de här anvisningarna för att ansluta  [till en virtuell](/azure/virtual-machines/windows/connect-logon) dator i Azure.</span><span class="sxs-lookup"><span data-stu-id="46045-233">For a virtual machine in Azure, use  [these instructions](/azure/virtual-machines/windows/connect-logon) to connect to it.</span></span>
  
<span data-ttu-id="46045-234">Anslut sedan WIN10-datorn till Azure AD-klienten för din Microsoft 365 E5-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="46045-234">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="46045-235">På skrivbordet på WIN10-datorn väljer du Starta > **inställningar >-> Åtkomst** till arbete eller > Connect.</span><span class="sxs-lookup"><span data-stu-id="46045-235">On the desktop of the WIN10 computer, select **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="46045-236">I dialogrutan **Konfigurera ett arbets- eller skolkonto väljer** du Anslut den här enheten till Azure Active **Directory.**</span><span class="sxs-lookup"><span data-stu-id="46045-236">In the **Set up a work or school account** dialog box, select **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="46045-237">I **arbets- eller skolkonto** anger du namnet på det globala administratörskontot för Microsoft 365 E5-prenumerationen och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="46045-237">In **Work or school account**, enter the global administrator account name of your Microsoft 365 E5 subscription, and then select **Next**.</span></span>
    
4. <span data-ttu-id="46045-238">I **Ange lösenord** anger du lösenordet för ditt globala administratörskonto och väljer sedan Logga **in.**</span><span class="sxs-lookup"><span data-stu-id="46045-238">In **Enter password**, enter the password for your global administrator account, and then select **Sign in**.</span></span>
    
5. <span data-ttu-id="46045-239">När du uppmanas att kontrollera att detta är din organisation väljer **du Anslut** och sedan **Klar**.</span><span class="sxs-lookup"><span data-stu-id="46045-239">When prompted to make sure that this is your organization, select **Join**, and then select **Done**.</span></span>
    
6. <span data-ttu-id="46045-240">Stäng inställningsfönstret.</span><span class="sxs-lookup"><span data-stu-id="46045-240">Close the settings window.</span></span>
    
<span data-ttu-id="46045-241">Installera sedan Microsoft 365-appar för företag på WIN10-datorn:</span><span class="sxs-lookup"><span data-stu-id="46045-241">Next, install Microsoft 365 Apps for enterprise on the WIN10 computer:</span></span>
  
1. <span data-ttu-id="46045-242">Öppna webbläsaren Microsoft Edge och logga in på administrationscentret för [Microsoft 365 med](https://admin.microsoft.com) dina autentiseringsuppgifter som global administratör.</span><span class="sxs-lookup"><span data-stu-id="46045-242">Open the Microsoft Edge browser and sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="46045-243">På fliken **Microsoft Office Home** väljer du Installera **Office**.</span><span class="sxs-lookup"><span data-stu-id="46045-243">On the **Microsoft Office Home** tab, select **Install Office**.</span></span>
    
3. <span data-ttu-id="46045-244">När du tillfrågas om vad du ska **göra väljer** du Kör och sedan **Ja** **för användarkontokontroll.**</span><span class="sxs-lookup"><span data-stu-id="46045-244">When prompted with what to do, select **Run**, and then select **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="46045-245">Vänta på att installationen av Office slutförs.</span><span class="sxs-lookup"><span data-stu-id="46045-245">Wait for Office to complete its installation.</span></span> <span data-ttu-id="46045-246">När du ser **Klart! väljer du** Stäng **två** gånger.</span><span class="sxs-lookup"><span data-stu-id="46045-246">When you see **You're all set!**, select **Close** twice.</span></span>
    
<span data-ttu-id="46045-247">Den resulterande miljön ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="46045-247">Your resulting environment looks like this:</span></span>

![Fas 5 av testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="46045-249">Det här omfattar den WIN10-dator som har:</span><span class="sxs-lookup"><span data-stu-id="46045-249">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="46045-250">Anslutit till Azure AD-klienten för din Microsoft 365 E5-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="46045-250">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="46045-251">Registrerats som en Azure AD-enhet i Microsoft Intune (EMS).</span><span class="sxs-lookup"><span data-stu-id="46045-251">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="46045-252">Microsoft 365-appar för företag installerade.</span><span class="sxs-lookup"><span data-stu-id="46045-252">Microsoft 365 Apps for enterprise installed.</span></span>
  
<span data-ttu-id="46045-253">Nu kan du experimentera med ytterligare funktioner i [Microsoft 365 för företag.](https://www.microsoft.com/microsoft-365/enterprise)</span><span class="sxs-lookup"><span data-stu-id="46045-253">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="46045-254">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="46045-254">Next steps</span></span>

<span data-ttu-id="46045-255">Utforska dessa ytterligare uppsättningar testlabbguider:</span><span class="sxs-lookup"><span data-stu-id="46045-255">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="46045-256">Identitet</span><span class="sxs-lookup"><span data-stu-id="46045-256">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="46045-257">Hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="46045-257">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="46045-258">Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="46045-258">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="46045-259">Se även</span><span class="sxs-lookup"><span data-stu-id="46045-259">See also</span></span>

[<span data-ttu-id="46045-260">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="46045-260">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="46045-261">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="46045-261">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="46045-262">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="46045-262">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)