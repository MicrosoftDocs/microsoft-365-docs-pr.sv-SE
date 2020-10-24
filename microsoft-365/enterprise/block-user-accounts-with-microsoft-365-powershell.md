---
title: Blockera Microsoft 365-användarkonton med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: Använda PowerShell för att blockera och avblockera åtkomst till Microsoft 365-konton.
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754686"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="c2183-103">Blockera Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2183-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="c2183-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c2183-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c2183-105">När du blockerar åtkomst till ett Microsoft 365-konto kan du hindra andra från att använda kontot för att logga in och komma åt tjänsterna och informationen i din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="c2183-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="c2183-106">Du kan använda PowerShell för att blockera åtkomst till enskilda eller flera användar konton.</span><span class="sxs-lookup"><span data-stu-id="c2183-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c2183-107">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="c2183-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c2183-108">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="c2183-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="c2183-109">Blockera åtkomst till enskilda användar konton</span><span class="sxs-lookup"><span data-stu-id="c2183-109">Block access to individual user accounts</span></span>

<span data-ttu-id="c2183-110">Använd följande syntax för att blockera ett enskilt användar konto:</span><span class="sxs-lookup"><span data-stu-id="c2183-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="c2183-111">Parametern *-ObjectID* i cmdleten **set-AzureAD** accepterar antingen konto inloggnings namnet, även kallat användarens huvud namn, eller kontots objekt-ID.</span><span class="sxs-lookup"><span data-stu-id="c2183-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="c2183-112">Det här exemplet blockerar åtkomst till användar kontots *fabricec@litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="c2183-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="c2183-113">Om du vill häva blockeringen för det här användar kontot kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="c2183-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="c2183-114">För att Visa användar kontots UPN baserat på användarens visnings namn, Använd följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="c2183-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="c2183-115">I det här exemplet visas UPN för användar kontot för användaren  *Caleb brädor*.</span><span class="sxs-lookup"><span data-stu-id="c2183-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="c2183-116">Om du vill blockera ett konto baserat på användarens visnings namn använder du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="c2183-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="c2183-117">Använd följande kommando för att kontrol lera den spärrade statusen för ett användar konto:</span><span class="sxs-lookup"><span data-stu-id="c2183-117">To check the blocked status of a user account use the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="c2183-118">Blockera flera användar konton</span><span class="sxs-lookup"><span data-stu-id="c2183-118">Block multiple user accounts</span></span>

<span data-ttu-id="c2183-119">Om du vill blockera åtkomst för flera användar konton skapar du en textfil som innehåller ett inloggnings namn för konto på varje rad, så här:</span><span class="sxs-lookup"><span data-stu-id="c2183-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="c2183-120">I följande kommandon är exempel text filen *c:\mina Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="c2183-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="c2183-121">Ersätt fil namnet med text filens sökväg och fil namn.</span><span class="sxs-lookup"><span data-stu-id="c2183-121">Replace this file name with the path and file name of your text file.</span></span>
  
<span data-ttu-id="c2183-122">Om du vill blockera åtkomst till kontona i text filen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="c2183-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="c2183-123">Om du vill häva blockeringen för de konton som visas i text filen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="c2183-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="c2183-124">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2183-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="c2183-125">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="c2183-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-individual-user-accounts"></a><span data-ttu-id="c2183-126">Blockera enskilda användar konton</span><span class="sxs-lookup"><span data-stu-id="c2183-126">Block individual user accounts</span></span>

<span data-ttu-id="c2183-127">Använd följande syntax för att blockera åtkomst för ett enskilt användar konto:</span><span class="sxs-lookup"><span data-stu-id="c2183-127">Use the following syntax to block access for an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="c2183-128">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets som har *MSOL* i sitt namn.</span><span class="sxs-lookup"><span data-stu-id="c2183-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="c2183-129">Du måste köra de här cmdletarna från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2183-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="c2183-130">I det här exemplet blockeras åtkomst till användar kontot *fabricec \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="c2183-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="c2183-131">Om du vill häva blockeringen för användar kontot kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="c2183-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="c2183-132">Kör följande kommando för att kontrol lera den spärrade statusen för ett användar konto:</span><span class="sxs-lookup"><span data-stu-id="c2183-132">To check the blocked status of a user account run the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="c2183-133">Blockera åtkomst för flera användar konton</span><span class="sxs-lookup"><span data-stu-id="c2183-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="c2183-134">Börja med att skapa en textfil som innehåller ett konto på varje rad, så här:</span><span class="sxs-lookup"><span data-stu-id="c2183-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="c2183-135">I följande kommandon är exempel text filen *c:\mina Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="c2183-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="c2183-136">Ersätt fil namnet med text filens sökväg och fil namn.</span><span class="sxs-lookup"><span data-stu-id="c2183-136">Replace this file name with the path and file name of your text file.</span></span>
    
<span data-ttu-id="c2183-137">Om du vill blockera åtkomst för de konton som visas i text filen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="c2183-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="c2183-138">Om du vill häva blockeringen för kontona i text filen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="c2183-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="c2183-139">Se även</span><span class="sxs-lookup"><span data-stu-id="c2183-139">See also</span></span>

[<span data-ttu-id="c2183-140">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2183-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c2183-141">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2183-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c2183-142">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c2183-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
