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
description: I den här artikeln förklarar vi hur du använder PowerShell till att blockera och avblockera åtkomst till Microsoft 365-konton.
ms.openlocfilehash: a9ade2f41fb601da00ca1c2d1905ca0cb003dcb3
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694561"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="900d2-103">Blockera Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="900d2-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="900d2-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="900d2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="900d2-105">Om du blockerar åtkomst till ett Microsoft 365-konto kan ingen använda kontot för att logga in och komma åt tjänsterna och informationen i din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="900d2-105">Blocking access to a Microsoft 365 account prevents anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="900d2-106">Du kan använda PowerShell för att blockera åtkomst till enskilda och flera användar konton.</span><span class="sxs-lookup"><span data-stu-id="900d2-106">You can use PowerShell to block access to individual and multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="900d2-107">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="900d2-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="900d2-108">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="900d2-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="900d2-109">Blockera åtkomst till enskilda användar konton</span><span class="sxs-lookup"><span data-stu-id="900d2-109">Block access to individual user accounts</span></span>

<span data-ttu-id="900d2-110">Använd följande syntax för att blockera ett enskilt användar konto:</span><span class="sxs-lookup"><span data-stu-id="900d2-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="900d2-111">Parametern-ObjectID i cmdleten Set-AzureAD accepterar antingen konto inloggnings namnet, även kallat användarens huvud namn, eller kontots objekt-ID.</span><span class="sxs-lookup"><span data-stu-id="900d2-111">The -ObjectID parameter in the Set-AzureAD cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span> 
  
<span data-ttu-id="900d2-112">Det här exemplet blockerar åtkomst till användar kontots fabricec@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="900d2-112">This example blocks access to the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="900d2-113">Om du vill häva blockeringen för det här användar kontot kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="900d2-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="900d2-114">För att Visa användar kontots UPN baserat på användarens visnings namn, Använd följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="900d2-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="900d2-115">I det här exemplet visas UPN för användar kontot för den användare som heter Caleb brädor.</span><span class="sxs-lookup"><span data-stu-id="900d2-115">This example displays the user account UPN for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="900d2-116">Om du vill blockera ett konto baserat på användarens visnings namn använder du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="900d2-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="900d2-117">Du kan när som helst kontrol lera den spärrade statusen för ett användar konto med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="900d2-117">At any time, you can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-access-to-multiple-user-accounts"></a><span data-ttu-id="900d2-118">Blockera åtkomst till flera användar konton</span><span class="sxs-lookup"><span data-stu-id="900d2-118">Block access to multiple user accounts</span></span>

<span data-ttu-id="900d2-119">Om du vill blockera åtkomst till flera användar konton skapar du en textfil som innehåller ett inloggnings namn för konto på varje rad, så här:</span><span class="sxs-lookup"><span data-stu-id="900d2-119">To block access to multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="900d2-120">I följande kommandon är exempel text filen C:\Mina Documents\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="900d2-120">In the following commands, the example text file is C:\My Documents\Accounts.txt.</span></span> <span data-ttu-id="900d2-121">Ersätt det med sökvägen och fil namnet för text filen.</span><span class="sxs-lookup"><span data-stu-id="900d2-121">Replace this with the path and file name of your text file.</span></span>
  
<span data-ttu-id="900d2-122">Om du vill blockera åtkomst till kontona i text filen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="900d2-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="900d2-123">Om du vill häva blockeringen för kontona i text filen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="900d2-123">To unblock the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="900d2-124">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="900d2-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="900d2-125">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="900d2-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="900d2-126">Blockera åtkomst till enskilda användar konton</span><span class="sxs-lookup"><span data-stu-id="900d2-126">Block access to individual user accounts</span></span>

<span data-ttu-id="900d2-127">Använd följande syntax för att blockera åtkomst till ett enskilt användar konto:</span><span class="sxs-lookup"><span data-stu-id="900d2-127">Use the following syntax to block access to an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="900d2-128">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** .</span><span class="sxs-lookup"><span data-stu-id="900d2-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="900d2-129">För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="900d2-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="900d2-130">Det här exemplet blockerar åtkomst till användar kontots fabricec@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="900d2-130">This example blocks access to the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="900d2-131">Om du vill häva blockeringen för användar kontot kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="900d2-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="900d2-132">Du kan när som helst kontrol lera den spärrade statusen för ett användar konto med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="900d2-132">At any time, you can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-to-multiple-user-accounts"></a><span data-ttu-id="900d2-133">Blockera åtkomst till flera användar konton</span><span class="sxs-lookup"><span data-stu-id="900d2-133">Block access to multiple user accounts</span></span>

<span data-ttu-id="900d2-134">Börja med att skapa en textfil som innehåller ett konto på varje rad, så här:</span><span class="sxs-lookup"><span data-stu-id="900d2-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="900d2-135">I följande kommandon är exempel text filen C:\Mina Documents\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="900d2-135">In the following commands, the example text file is C:\My Documents\Accounts.txt.</span></span> <span data-ttu-id="900d2-136">Ersätt det med sökvägen och fil namnet för text filen.</span><span class="sxs-lookup"><span data-stu-id="900d2-136">Replace this with the path and file name of your text file.</span></span>
    
<span data-ttu-id="900d2-137">Om du vill blockera åtkomst till kontona i text filen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="900d2-137">To block access to the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="900d2-138">Om du vill häva blockeringen för kontona i text filen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="900d2-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="900d2-139">Se även</span><span class="sxs-lookup"><span data-stu-id="900d2-139">See also</span></span>

[<span data-ttu-id="900d2-140">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="900d2-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="900d2-141">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="900d2-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="900d2-142">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="900d2-142">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
