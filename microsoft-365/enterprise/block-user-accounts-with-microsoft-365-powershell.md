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
description: Så här använder du PowerShell för att blockera och häva blockeringen av åtkomst Microsoft 365 konton.
ms.openlocfilehash: 90d712cdb6eb34d0588fc262e3a02673accfbd9e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287227"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="ed551-103">Blockera Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed551-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="ed551-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ed551-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ed551-105">När du blockerar åtkomst till ett Microsoft 365-konto hindrar du någon från att använda kontot för att logga in och få åtkomst till tjänster och data i Microsoft 365 organisation.</span><span class="sxs-lookup"><span data-stu-id="ed551-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="ed551-106">Du kan använda PowerShell för att blockera åtkomst till enskilda eller flera användarkonton.</span><span class="sxs-lookup"><span data-stu-id="ed551-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="ed551-107">Använda Azure Active Directory PowerShell för Graph modul</span><span class="sxs-lookup"><span data-stu-id="ed551-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="ed551-108">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ed551-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="ed551-109">Blockera åtkomst till enskilda användarkonton</span><span class="sxs-lookup"><span data-stu-id="ed551-109">Block access to individual user accounts</span></span>

<span data-ttu-id="ed551-110">Använd följande syntax för att blockera ett enskilt användarkonto:</span><span class="sxs-lookup"><span data-stu-id="ed551-110">Use the following syntax to block an individual user account:</span></span>

```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="ed551-111">Parametern *-ObjectID* i cmdleten **Set-AzureAD** accepterar antingen kontots inloggningsnamn, som även kallas användarens huvudnamn, eller kontots objekt-ID.</span><span class="sxs-lookup"><span data-stu-id="ed551-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>

<span data-ttu-id="ed551-112">I det här exemplet blockeras åtkomst till *användarkontot fabricec@litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="ed551-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="ed551-113">Om du vill häva blockeringen för det här användarkontot kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed551-113">To unblock this user account, run the following command:</span></span>

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="ed551-114">Om du vill visa UPN för användarkontot baserat på användarens visningsnamn använder du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="ed551-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>

```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="ed551-115">I det här exemplet visas ANVÄNDARKONTOTS UPN för *användaren Caleb Hansson.*</span><span class="sxs-lookup"><span data-stu-id="ed551-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>

```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="ed551-116">Använd följande kommandon för att blockera ett konto baserat på användarens visningsnamn:</span><span class="sxs-lookup"><span data-stu-id="ed551-116">To block an account based on the user's display name, use the following commands:</span></span>

```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="ed551-117">Om du vill kontrollera blockerad status för ett användarkonto använder du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed551-117">To check the blocked status of a user account use the following command:</span></span>

```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="ed551-118">Blockera flera användarkonton</span><span class="sxs-lookup"><span data-stu-id="ed551-118">Block multiple user accounts</span></span>

<span data-ttu-id="ed551-119">Om du vill blockera åtkomst för flera användarkonton skapar du en textfil som innehåller ett konto inloggningsnamn på varje rad så här:</span><span class="sxs-lookup"><span data-stu-id="ed551-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>

  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="ed551-120">I följande kommandon är exempeltextfilen *C:\Mina Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="ed551-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="ed551-121">Ersätt det här filnamnet med sökvägen och filnamnet för textfilen.</span><span class="sxs-lookup"><span data-stu-id="ed551-121">Replace this file name with the path and file name of your text file.</span></span>

<span data-ttu-id="ed551-122">Om du vill blockera åtkomst till de konton som visas i textfilen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed551-122">To block access to the accounts listed in the text file, run the following command:</span></span>

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $false}
```

<span data-ttu-id="ed551-123">Om du vill häva blockeringen av de konton som listas i textfilen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed551-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $true}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="ed551-124">Använda Microsoft Azure Active Directory för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed551-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="ed551-125">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="ed551-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="block-individual-user-accounts"></a><span data-ttu-id="ed551-126">Blockera enskilda användarkonton</span><span class="sxs-lookup"><span data-stu-id="ed551-126">Block individual user accounts</span></span>

<span data-ttu-id="ed551-127">Använd följande syntax för att blockera åtkomst för ett enskilt användarkonto:</span><span class="sxs-lookup"><span data-stu-id="ed551-127">Use the following syntax to block access for an individual user account:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="ed551-128">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell och cmdlets som har *Msol* i sitt namn.</span><span class="sxs-lookup"><span data-stu-id="ed551-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="ed551-129">Du måste köra dessa cmdlets från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed551-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="ed551-130">I det här exemplet blockeras åtkomst till *användarkontot och \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="ed551-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>

```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="ed551-131">Om du vill häva blockeringen av användarkontot kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed551-131">To unblock the user account, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="ed551-132">Om du vill kontrollera blockerad status för ett användarkonto kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed551-132">To check the blocked status of a user account run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="ed551-133">Blockera åtkomst för flera användarkonton</span><span class="sxs-lookup"><span data-stu-id="ed551-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="ed551-134">Skapa först en textfil som innehåller ett konto på varje rad så här:</span><span class="sxs-lookup"><span data-stu-id="ed551-134">First, create a text file that contains one account on each line like this:</span></span>

```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="ed551-135">I följande kommandon är exempeltextfilen *C:\Mina Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="ed551-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="ed551-136">Ersätt det här filnamnet med sökvägen och filnamnet för textfilen.</span><span class="sxs-lookup"><span data-stu-id="ed551-136">Replace this file name with the path and file name of your text file.</span></span>

<span data-ttu-id="ed551-137">Om du vill blockera åtkomst för de konton som visas i textfilen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed551-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="ed551-138">Om du vill häva blockeringen av de konton som visas i textfilen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed551-138">To unblock the accounts listed in the text file, run the following command:</span></span>

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="ed551-139">Se även</span><span class="sxs-lookup"><span data-stu-id="ed551-139">See also</span></span>

[<span data-ttu-id="ed551-140">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed551-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[<span data-ttu-id="ed551-141">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed551-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="ed551-142">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ed551-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
