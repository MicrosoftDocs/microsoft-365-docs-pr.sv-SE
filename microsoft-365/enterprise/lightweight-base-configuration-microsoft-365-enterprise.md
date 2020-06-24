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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Använd den här testlabbguiden för att skapa en förenklad testmiljö för att testa Microsoft 365 Enterprise.
ms.openlocfilehash: 7a4800d374416a1e197536bc1a867d3fbc4b1243
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818759"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="b1ddf-103">Den enkla baskonfigurationen</span><span class="sxs-lookup"><span data-stu-id="b1ddf-103">The lightweight base configuration</span></span>

<span data-ttu-id="b1ddf-104">*Den här testlabbguiden kan användas i både Microsoft 365 Enterprise- och Office 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="b1ddf-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="b1ddf-105">I den här artikeln får du stegvisa instruktioner för hur du skapar en förenklad miljö med en Microsoft 365 E5-prenumeration och en dator med Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-105">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![Den förenklade testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="b1ddf-107">Använd den resulterande miljön för att testa funktionerna och funktionaliteten i [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="b1ddf-107">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="b1ddf-109">Klicka på [Samling med testlabbguider för Microsoft 365 för företag](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-109">Click [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="b1ddf-110">Fas 1: Skapa en Office 365 E5-prenumeration</span><span class="sxs-lookup"><span data-stu-id="b1ddf-110">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="b1ddf-111">Vi börjar med en utvärderingsprenumeration på Office 365 E5 och lägger sedan till Microsoft 365 E5-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-111">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="b1ddf-112">För att starta utvärderingsprenumerationen för Office 365 E5 behöver du först ett fiktivt företagsnamn och ett nytt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-112">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="b1ddf-113">Vi rekommenderar att du använder en variant av företagsnamnet Contoso som ditt företagsnamn, vilket är ett fiktivt företag som används i Microsoft-exempelinnehåll, men det är inget krav.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-113">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required.</span></span> <span data-ttu-id="b1ddf-114">Skriv ditt fiktiva företagsnamn här:</span><span class="sxs-lookup"><span data-stu-id="b1ddf-114">Record your fictitious company name here:</span></span> ![Rad](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="b1ddf-116">Om du vill registrera dig för ett nytt Microsoft-konto går du till [https://outlook.com](https://outlook.com) och skapar ett konto med ett nytt e-postkonto och en ny e-postadress.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-116">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address.</span></span> <span data-ttu-id="b1ddf-117">Du använder det här kontot för att registrera dig för Office 365.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-117">You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="b1ddf-118">Skriv för- och efternamn för ditt nya konto här:</span><span class="sxs-lookup"><span data-stu-id="b1ddf-118">Record the first and last name of your new account here:</span></span> ![Rad](../media/Common-Images/TableLine.png)
    
  - <span data-ttu-id="b1ddf-120">Skriv den nya adressen för e-postkontot här:</span><span class="sxs-lookup"><span data-stu-id="b1ddf-120">Record the new email account address here:</span></span> ![Rad](../media/Common-Images/TableLine.png)<span data-ttu-id="b1ddf-122">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="b1ddf-122">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="b1ddf-123">Registrera dig för en utvärderingsprenumeration på Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="b1ddf-123">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="b1ddf-124">Öppna webbläsaren på datorn och gå till [https://aka.ms/e5trial](https://aka.ms/e5trial).</span><span class="sxs-lookup"><span data-stu-id="b1ddf-124">Open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="b1ddf-125">På sidan **Tack för att du väljer Office 365 E5** anger du den nya adressen för e-postkontot i steg 1.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-125">On the **Thank you for choosing Office 365 E5** page, specify, your new email account address in step 1.</span></span>
3. <span data-ttu-id="b1ddf-126">I steg 2 av processen för utvärderingsprenumerationen skriver du den begärda informationen och utför sedan verifieringen.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-126">In step 2 of the trail subscription process, type the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="b1ddf-127">I steg 3 skriver du ett organisationsnamn och sedan ett kontonamn som blir den globala administratören för prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-127">In step 3, type an organization name and then an account name that will be the global admin for the subscription.</span></span> 
5. <span data-ttu-id="b1ddf-128">För steg 4 skriver du inloggningssidan här (markera och kopiera):</span><span class="sxs-lookup"><span data-stu-id="b1ddf-128">For step 4, record the sign-in page here (select and copy):</span></span> ![Rad](../media/Common-Images/TableLine.png) 
6. <span data-ttu-id="b1ddf-130">Skriv användar-ID här: ![Rad](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="b1ddf-130">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="b1ddf-131">Anteckna lösenordet som du skrev ned på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-131">Record the password that you typed in a secure location.</span></span>
   <span data-ttu-id="b1ddf-132">Det här värdet kommer att kallas för det **globala administratörsnamnet**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-132">This value will be referred to as the **global administrator name**.</span></span>
8. <span data-ttu-id="b1ddf-133">Klicka på **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-133">Click **Go to Setup**.</span></span>
9. <span data-ttu-id="b1ddf-134">I Office 365 E5-konfigurationen klickar du på **Fortsätt använda *din organisation*.onmicrosoft.com för e-post och inloggning** och klicka sedan på **Avsluta och fortsätt senare**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-134">In Office 365 E5 Setup, click **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then click **Exit and continue later**.</span></span>

<span data-ttu-id="b1ddf-135">Du bör se administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-135">You should see the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="b1ddf-136">Du skapar en utvärderingsprenumeration på Office 365 för att testmiljön ska ha en Azure AD-klient som är separerad från de betalda prenumerationer som du har för närvarande.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-136">We have you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="b1ddf-137">Den här separationen innebär att du kan lägga till och ta bort användare och grupper i testklienten utan att påverka produktionsprenumerationerna.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-137">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="b1ddf-138">Fas 2: Konfigurera utvärderingsprenumerationen för Office 365</span><span class="sxs-lookup"><span data-stu-id="b1ddf-138">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="b1ddf-139">I den här fasen konfigurerar du prenumerationen med ytterligare användare och tilldelar dem Office 365 E5-licenser.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-139">In this phase, you configure your subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="b1ddf-140">Använd anvisningarna i [Ansluta till Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) för att ansluta till prenumerationen med Azure Active Directory PowerShell för Graph-modulen från datorn.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-140">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your subscription with the Azure Active Directory PowerShell for Graph module from your computer.</span></span>
    
<span data-ttu-id="b1ddf-141">I dialogrutan **Begäran om autentiseringsuppgifter för Windows PowerShell** anger du det globala administratörsnamnet (t.ex. jdoe@contosotoycompany.onmicrosoft.com) och lösenordet.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-141">In the **Windows PowerShell Credential Request** dialog box, type the global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="b1ddf-142">Fyll i organisationens namn (t.ex. contosotoycompany), landskoden med två tecken för din plats, ett gemensamt kontolösenord och kör sedan följande kommandon från PowerShell-prompten:</span><span class="sxs-lookup"><span data-stu-id="b1ddf-142">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="b1ddf-143">Användningen av ett gemensamt lösenord här är för automatisering och enklare konfiguration för en testmiljö.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-143">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="b1ddf-144">Självklart rekommenderas detta inte för produktionsprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-144">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="b1ddf-145">Skriv ned viktig information för framtida referens</span><span class="sxs-lookup"><span data-stu-id="b1ddf-145">Record key information for future reference</span></span>

<span data-ttu-id="b1ddf-146">Det kan vara bra att skriva ut den här artikeln för att kunna skriva ned den specifika information som du behöver för den här miljön under de 30 dagar som Office 365-utvärderingsprenumerationen gäller.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-146">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="b1ddf-147">Du kan enkelt utöka utvärderingsprenumerationen i ytterligare 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-147">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="b1ddf-148">För en permanent testmiljö skapar du en ny betald prenumeration med en separat Azure AD-klient och ett litet antal licenser.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-148">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

<span data-ttu-id="b1ddf-149">Anteckna dessa värden:</span><span class="sxs-lookup"><span data-stu-id="b1ddf-149">Record these values:</span></span>
  
- <span data-ttu-id="b1ddf-150">globalt administratörsnamn:</span><span class="sxs-lookup"><span data-stu-id="b1ddf-150">global administrator name:</span></span> ![Rad](../media/Common-Images/TableLine.png)<span data-ttu-id="b1ddf-152">.onmicrosoft.com (från steg 6 i fas 1)</span><span class="sxs-lookup"><span data-stu-id="b1ddf-152">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="b1ddf-153">Anteckna också lösenordet för det här kontot på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-153">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="b1ddf-154">Organisationens namn för utvärderingsprenumerationen:</span><span class="sxs-lookup"><span data-stu-id="b1ddf-154">Your trial subscription organization name:</span></span> ![Rad](../media/Common-Images/TableLine.png) <span data-ttu-id="b1ddf-156">(från steg 4 i fas 1)</span><span class="sxs-lookup"><span data-stu-id="b1ddf-156">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="b1ddf-157">Om du vill lista kontona för Användare 2, Användare 3, Användare 4 och Användare 5 kör du följande kommando från Windows Azure Active Directory-modulen för Windows PowerShell-prompten:</span><span class="sxs-lookup"><span data-stu-id="b1ddf-157">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="b1ddf-158">Skriv kontonamnen här:</span><span class="sxs-lookup"><span data-stu-id="b1ddf-158">Record the account names here:</span></span>
    
  - <span data-ttu-id="b1ddf-159">Kontonamn för Användare 2: användare2@</span><span class="sxs-lookup"><span data-stu-id="b1ddf-159">User 2 account name: user2@</span></span>![Rad](../media/Common-Images/TableLine.png)<span data-ttu-id="b1ddf-161">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="b1ddf-161">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="b1ddf-162">Kontonamn för Användare 3: användare3@</span><span class="sxs-lookup"><span data-stu-id="b1ddf-162">User 3 account name: user3@</span></span>![Rad](../media/Common-Images/TableLine.png)<span data-ttu-id="b1ddf-164">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="b1ddf-164">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="b1ddf-165">Kontonamn för Användare 4: användare4@</span><span class="sxs-lookup"><span data-stu-id="b1ddf-165">User 4 account name: user4@</span></span>![Rad](../media/Common-Images/TableLine.png)<span data-ttu-id="b1ddf-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="b1ddf-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="b1ddf-168">Kontonamn för Användare 5: användare5@</span><span class="sxs-lookup"><span data-stu-id="b1ddf-168">User 5 account name: user5@</span></span>![Rad](../media/Common-Images/TableLine.png)<span data-ttu-id="b1ddf-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="b1ddf-170">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="b1ddf-171">Anteckna också det gemensamma lösenordet för dessa konton på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-171">Also record the common password for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="b1ddf-172">Använda en Office 365-testmiljö</span><span class="sxs-lookup"><span data-stu-id="b1ddf-172">Using an Office 365 test environment</span></span>

<span data-ttu-id="b1ddf-173">Om allt du behöver är en Office 365-testmiljö kan du stanna här.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-173">If all you need is an Office 365 test environment, you can stop here.</span></span> 

<span data-ttu-id="b1ddf-174">Se [Testlabbguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md) för ytterligare testlabbguider som gäller för både Office 365 och Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-174">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="b1ddf-175">Fas 3: Lägga till en utvärderingsprenumeration på Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b1ddf-175">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="b1ddf-176">I den här fasen registrerar du dig för Microsoft 365 E5-utvärderingsprenumerationen och lägger till den i samma organisation som utvärderingsprenumerationen för Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-176">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="b1ddf-177">Lägg först till Microsoft 365 E5-utvärderingsprenumerationen och tilldela den nya licensen för Microsoft 365 till det globala administratörskontot.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-177">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="b1ddf-178">Med en privat instans av en webbläsare loggar du in i administrationscentret för Microsoft 365 på [https://admin.microsoft.com](https://admin.microsoft.com) med autentiseringsuppgifterna för det globala administratörskontot.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-178">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="b1ddf-179">På sidan **Administrationscenter för Microsoft 365** klickar du på **Fakturering > Köp tjänster** i det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-179">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="b1ddf-180">På sidan **Köp tjänster** klickar du på **Microsoft 365 E5** och sedan på **Hämta en kostnadsfri utvärderingsversion**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-180">On the **Purchase services** page, click **Microsoft 365 E5**, and then click **Get free trial**.</span></span>

4. <span data-ttu-id="b1ddf-181">På sidan **Utvärderingsversion av Microsoft 365 E5** väljer du om du vill ta emot ett sms eller ett samtal, anger ditt telefonnummer och klickar på **Skicka sms** eller **Ring mig**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-181">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span> <span data-ttu-id="b1ddf-182">Utför verifieringen.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-182">Perform the verification.</span></span>

5. <span data-ttu-id="b1ddf-183">På sidan **Bekräfta din beställning** väljer du **Prova nu**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-183">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="b1ddf-184">På sidan **Beställningskvitto** klickar du på **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-184">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="b1ddf-185">I administrationscentret för Microsoft 365 klickar du på **Användare > Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-185">In the Microsoft 365 admin center, click **Users > Active users**.</span></span>

8. <span data-ttu-id="b1ddf-186">I **Aktiva användare** klickar du på administratörskontot.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-186">In **Active users**, click your administrator account.</span></span>

9. <span data-ttu-id="b1ddf-187">Klicka på **Licenser och appar**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-187">Click **Licenses and apps**.</span></span>

10. <span data-ttu-id="b1ddf-188">Inaktivera licensen för Office 365 Enterprise, E5 och aktivera licensen för Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-188">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="b1ddf-189">Klicka på **Spara ändringar** och stäng sedan fönstret med användarkontoinformation.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-189">Click **Save changes** and then close the user account information pane.</span></span>

<span data-ttu-id="b1ddf-190">Upprepa sedan steg 8 till 11 i föregående procedur för alla andra konton (Användare 2, Användare 3, Användare 4 och Användare 5).</span><span class="sxs-lookup"><span data-stu-id="b1ddf-190">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b1ddf-191">Utvärderingsprenumerationen på Microsoft 365 E5 gäller i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-191">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="b1ddf-192">För en permanent testmiljö omvandlar du den här utvärderingsprenumeration till en betald prenumeration med ett litet antal licenser.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-192">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="b1ddf-193">Din testmiljö har nu:</span><span class="sxs-lookup"><span data-stu-id="b1ddf-193">Your test environment now has:</span></span>
  
- <span data-ttu-id="b1ddf-194">En utvärderingsprenumeration på Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-194">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="b1ddf-195">Alla relevanta användarkonton (antingen bara det globala administratörskontot eller alla fem användarkonton) är aktiverade för att använda Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-195">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="b1ddf-196">Här är den resulterande konfigurationen som lägger till Microsoft 365 E5, där både Office 365 och Enterprise Security + Management (EMS) ingår.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-196">Here is your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Fas 3 av testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="b1ddf-198">Fas 4: Skapa en Windows 10 Enterprise-dator</span><span class="sxs-lookup"><span data-stu-id="b1ddf-198">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="b1ddf-199">I den här fasen skapar du en fristående dator med Windows 10 Enterprise som en fysisk dator, en virtuell dator eller en virtuell Azure-dator.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-199">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="b1ddf-200">Fysisk dator</span><span class="sxs-lookup"><span data-stu-id="b1ddf-200">Physical computer</span></span>

<span data-ttu-id="b1ddf-201">Skaffa en dator och installera Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-201">Obtain a personal computer and install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="b1ddf-202">Du kan ladda ned utvärderingsversionen av Windows 10 Enterprise [här](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="b1ddf-202">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="b1ddf-203">Virtuell dator</span><span class="sxs-lookup"><span data-stu-id="b1ddf-203">Virtual machine</span></span>

<span data-ttu-id="b1ddf-204">Skapa en virtuell dator med valfri hypervisor och installera Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-204">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="b1ddf-205">Du kan ladda ned utvärderingsversionen av Windows 10 Enterprise [här](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="b1ddf-205">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="b1ddf-206">Virtuell dator i Azure</span><span class="sxs-lookup"><span data-stu-id="b1ddf-206">Virtual machine in Azure</span></span>

<span data-ttu-id="b1ddf-207">Om du vill skapa en virtuell Windows 10-dator i Microsoft Azure ***måste du ha en Visual Studio-baserad prenumeration***, som har åtkomst till avbildningen av Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-207">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise.</span></span> <span data-ttu-id="b1ddf-208">Andra typer av Azure-prenumerationer, t.ex. utvärderingsprenumerationer eller betalda prenumerationer, har inte åtkomst till den här avbildningen.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-208">Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image.</span></span> <span data-ttu-id="b1ddf-209">Den senaste informationen finns i [Använda Windows-klienten i Azure för utvecklings-/testscenarier](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span><span class="sxs-lookup"><span data-stu-id="b1ddf-209">For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b1ddf-210">Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-210">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="b1ddf-211">Se [Kom igång med Azure PowerShell-cmdletar](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="b1ddf-211">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> <span data-ttu-id="b1ddf-212">Med dessa kommandouppsättningar skapas en virtuell dator med Windows 10 Enterprise som heter WIN10 och all den infrastruktur som krävs, inklusive en resursgrupp, ett lagringskonto och ett virtuellt nätverk.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-212">These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network.</span></span> <span data-ttu-id="b1ddf-213">Om du redan är bekant med Azure-infrastrukturtjänster kan du anpassa de här anvisningarna så att de passar din aktuella distribuerade infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-213">If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="b1ddf-214">Starta först en Microsoft PowerShell-prompt.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-214">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="b1ddf-215">Logga in på ditt Azure-konto med följande kommando.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-215">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="b1ddf-216">Hämta ditt prenumerationsnamn med följande kommando.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-216">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="b1ddf-217">Ange din Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-217">Set your Azure subscription.</span></span> <span data-ttu-id="b1ddf-218">Ersätt allt inom citattecknen, inklusive \< and >-tecknen med rätt namn.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-218">Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="b1ddf-219">Skapa sedan en ny resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-219">Next, create a new resource group.</span></span> <span data-ttu-id="b1ddf-220">Använd det här kommandot för att lista dina befintliga resursgrupper när du ska fastställa ett unikt resursgruppnamn.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-220">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="b1ddf-221">Skapa den nya resursgruppen med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-221">Create your new resource group with these commands.</span></span> <span data-ttu-id="b1ddf-222">Ersätt allt inom citattecknen, inklusive \< and >-tecknen med de rätta namnen.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-222">Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="b1ddf-223">Nästa steg är att skapa ett nytt virtuellt nätverk och den virtuella WIN10-datorn med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-223">Next, you create a new virtual network and the WIN10 virtual machine with these commands.</span></span> <span data-ttu-id="b1ddf-224">När du uppmanas till det anger du namnet och lösenordet för det lokala administratörskontot för WIN10 och sparar dessa på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-224">When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
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

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="b1ddf-225">Fas 5: Ansluta Windows 10-datorn till Azure AD</span><span class="sxs-lookup"><span data-stu-id="b1ddf-225">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="b1ddf-226">När du har skapat en fysisk eller virtuell dator med Windows 10 Enterprise loggar du in med ett lokalt administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-226">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b1ddf-227">Anslut till en virtuell dator i Azure med hjälp av [dessa anvisningar](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="b1ddf-227">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="b1ddf-228">Anslut sedan WIN10-datorn till Azure AD-klienten för din Microsoft 365 E5-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-228">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="b1ddf-229">Gå till skrivbordet för WIN10-datorn och klicka på **Start > Inställningar > Konton > Åtkomst till arbete eller skola > Anslut**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-229">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="b1ddf-230">I dialogrutan **Konfigurera ett arbets- eller skolkonto** klickar du på **Anslut den här enheten till Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-230">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="b1ddf-231">I **Arbets- eller skolkonto** skriver du det globala administratörskontonamnet för Microsoft 365 E5-prenumerationen och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-231">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="b1ddf-232">I **Ange lösenord** skriver du lösenordet för det globala administratörskontot och klickar sedan på **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-232">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="b1ddf-233">När du uppmanas att kontrollera att det är din organisation klickar du på **Anslut**och sedan på **Klart**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-233">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="b1ddf-234">Stäng inställningsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-234">Close the settings window.</span></span>
    
<span data-ttu-id="b1ddf-235">Installera sedan Microsoft 365-applikationer för företag på WIN10-datorn.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-235">Next, install Microsoft 365 Apps for enterprise on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="b1ddf-236">Öppna webbläsaren Microsoft Edge och logga in på Office-portalen med autentiseringsuppgifterna för ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-236">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="b1ddf-237">Mer information finns i [Så här loggar du in i Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="b1ddf-237">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="b1ddf-238">På fliken **Microsoft Office Home** klickar du på **Installera Office**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-238">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="b1ddf-239">När du tillfrågas om vad du vill göra klickar du på **Kör** och klickar sedan på **Ja** för **User Account Control**.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-239">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="b1ddf-240">Vänta på att installationen av Office slutförs.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-240">Wait for Office to complete its installation.</span></span> <span data-ttu-id="b1ddf-241">När du ser **Nu är du klar!** klickar du på **Stäng** två gånger.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-241">When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="b1ddf-242">Här är den resulterande miljön.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-242">Here is your resulting environment.</span></span>

![Fas 5 av testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="b1ddf-244">Det här omfattar den WIN10-dator som har:</span><span class="sxs-lookup"><span data-stu-id="b1ddf-244">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="b1ddf-245">Anslutit till Azure AD-klienten för din Microsoft 365 E5-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-245">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="b1ddf-246">Registrerats som en Azure AD-enhet i Microsoft Intune (EMS).</span><span class="sxs-lookup"><span data-stu-id="b1ddf-246">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="b1ddf-247">Har Microsoft 365-applikationer för företag installerat.</span><span class="sxs-lookup"><span data-stu-id="b1ddf-247">Has Microsoft 365 Apps for enterprise installed.</span></span>
  
<span data-ttu-id="b1ddf-248">Nu är du redo att experimentera med fler funktioner i [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="b1ddf-248">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="b1ddf-249">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b1ddf-249">Next steps</span></span>

<span data-ttu-id="b1ddf-250">Utforska dessa ytterligare uppsättningar testlabbguider:</span><span class="sxs-lookup"><span data-stu-id="b1ddf-250">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="b1ddf-251">Identitet</span><span class="sxs-lookup"><span data-stu-id="b1ddf-251">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="b1ddf-252">Hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="b1ddf-252">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="b1ddf-253">Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="b1ddf-253">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="b1ddf-254">Snabbreferens</span><span class="sxs-lookup"><span data-stu-id="b1ddf-254">See also</span></span>

[<span data-ttu-id="b1ddf-255">Testlabbguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b1ddf-255">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b1ddf-256">Distribuera Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b1ddf-256">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b1ddf-257">Microsoft 365 Enterprise-dokumentation</span><span class="sxs-lookup"><span data-stu-id="b1ddf-257">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
