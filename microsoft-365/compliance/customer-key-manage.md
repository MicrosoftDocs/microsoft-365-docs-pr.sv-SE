---
title: Hantera kundnyckel
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: När du har ställt in kundnyckeln, lär dig hur du hanterar den genom att återställa AKV-nycklar och hantera behörigheter och dina principer för datakryptering.
ms.openlocfilehash: 284a8ff24fef2f7e8b807477c99e20aaf593552e
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162546"
---
# <a name="manage-customer-key"></a><span data-ttu-id="f089f-103">Hantera kundnyckel</span><span class="sxs-lookup"><span data-stu-id="f089f-103">Manage Customer Key</span></span>

<span data-ttu-id="f089f-104">När du har ställt in kundnyckel för Office 365 kan du hantera dina nycklar enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f089f-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="f089f-105">Läs mer om kundnyckel i relaterade ämnen.</span><span class="sxs-lookup"><span data-stu-id="f089f-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="f089f-106">Återställa Azure-nyckelvalvsnycklar</span><span class="sxs-lookup"><span data-stu-id="f089f-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="f089f-107">Innan du utför en återställning använder du de återställningsfunktioner som tillhandahålls av mjuk borttagning.</span><span class="sxs-lookup"><span data-stu-id="f089f-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="f089f-108">Alla nycklar som används med kundnyckeln måste ha mjuk borttagning aktiverad.</span><span class="sxs-lookup"><span data-stu-id="f089f-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="f089f-109">Mjuk borttagning fungerar som en papperskorg och tillåter återställning i upp till 90 dagar utan att du behöver återställa den.</span><span class="sxs-lookup"><span data-stu-id="f089f-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="f089f-110">Återställning bör endast krävas i extrema eller ovanliga omständigheter, till exempel om nyckeln eller nyckelvalvet går förlorat.</span><span class="sxs-lookup"><span data-stu-id="f089f-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="f089f-111">Om du måste återställa en nyckel för användning med Azure PowerShell kör du cmdleten Restore-AzureKeyVaultKey följande:</span><span class="sxs-lookup"><span data-stu-id="f089f-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="f089f-112">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="f089f-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="f089f-113">Om nyckelns valv redan innehåller en nyckel med samma namn misslyckas återställningsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="f089f-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="f089f-114">Restore-AzKeyVaultKey alla viktiga versioner och alla metadata för nyckeln, inklusive nyckelnamnet.</span><span class="sxs-lookup"><span data-stu-id="f089f-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="f089f-115">Hantera behörigheter för nyckelvalv</span><span class="sxs-lookup"><span data-stu-id="f089f-115">Manage key vault permissions</span></span>

<span data-ttu-id="f089f-116">Flera cmdlets är tillgängliga som gör att du kan visa och, om det behövs, ta bort behörigheter för nyckelvalv.</span><span class="sxs-lookup"><span data-stu-id="f089f-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="f089f-117">Du kan behöva ta bort behörigheter, till exempel när en anställd lämnar gruppen.</span><span class="sxs-lookup"><span data-stu-id="f089f-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="f089f-118">För var och en av dessa uppgifter använder du Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f089f-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="f089f-119">Mer information om Azure Powershell finns i [Översikt över Azure PowerShell](/powershell/azure/).</span><span class="sxs-lookup"><span data-stu-id="f089f-119">For information about Azure Powershell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="f089f-120">Om du vill visa behörigheter för nyckelvalv kör du Get-AzKeyVault-cmdleten.</span><span class="sxs-lookup"><span data-stu-id="f089f-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="f089f-121">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="f089f-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="f089f-122">Om du vill ta bort en administratörs behörigheter kör du Remove-AzKeyVaultAccessPolicy cmdleten:</span><span class="sxs-lookup"><span data-stu-id="f089f-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="f089f-123">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="f089f-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="f089f-124">Hantera datakrypteringsprinciper (DEP) med kundnyckel</span><span class="sxs-lookup"><span data-stu-id="f089f-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="f089f-125">Kundnyckel hanterar DEP:er olika mellan de olika tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="f089f-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="f089f-126">Du kan till exempel skapa olika antal DEP för de olika tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="f089f-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="f089f-127">**Exchange Online och Skype för företag:** Du kan skapa upp till 50 dep.</span><span class="sxs-lookup"><span data-stu-id="f089f-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="f089f-128">Instruktioner finns i Skapa [en datakrypteringsprincip (DEP) för användning med Exchange Online och Skype för företag.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="f089f-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="f089f-129">**SharePoint Online, OneDrive för företag och Teams filer:** En dep gäller data på en geografisk plats, som även kallas _geo._</span><span class="sxs-lookup"><span data-stu-id="f089f-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="f089f-130">Om du använder multi-geofunktionen i Office 365 kan du skapa en DEP per geo.</span><span class="sxs-lookup"><span data-stu-id="f089f-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="f089f-131">Om du inte använder multi-geo kan du skapa en DEP.</span><span class="sxs-lookup"><span data-stu-id="f089f-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="f089f-132">Normalt skapar du DEP när du anger kundnyckel.</span><span class="sxs-lookup"><span data-stu-id="f089f-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="f089f-133">Anvisningar finns i Skapa [en datakrypteringsprincip (DEP) för varje data SharePoint Online OneDrive för företag geo.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)</span><span class="sxs-lookup"><span data-stu-id="f089f-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="f089f-134">Visa de DEP:er som du har skapat för Exchange Online och Skype för företag</span><span class="sxs-lookup"><span data-stu-id="f089f-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="f089f-135">Om du vill visa en lista över alla DEP:er som du har skapat för Exchange Online och Skype för företag med PowerShell-cmdleten Get-DataEncryptionPolicy slutför du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="f089f-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="f089f-136">Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation [och anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="f089f-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f089f-137">Om du vill returnera alla DEP:er i organisationen kör du Get-DataEncryptionPolicy-cmdleten utan några parametrar.</span><span class="sxs-lookup"><span data-stu-id="f089f-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="f089f-138">Mer information om Get-DataEncryptionPolicy cmdlet finns i [Get-DataEncryptionPolicy.](/powershell/module/exchange/get-dataencryptionpolicy)</span><span class="sxs-lookup"><span data-stu-id="f089f-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="f089f-139">Tilldela en DEP innan du migrerar en postlåda till molnet</span><span class="sxs-lookup"><span data-stu-id="f089f-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="f089f-140">När du tilldelar Microsoft 365 krypteras innehållet i postlådan med den tilldelade dataleverantören under migreringen.</span><span class="sxs-lookup"><span data-stu-id="f089f-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="f089f-141">Den här processen är mer effektiv än att migrera postlådan, tilldela DEP och sedan vänta på att krypteringen sker, som kan ta timmar eller möjligt dagar.</span><span class="sxs-lookup"><span data-stu-id="f089f-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="f089f-142">Om du vill tilldela en DEP till en postlåda innan du migrerar Office 365 den kör du cmdleten Set-MailUser i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f089f-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="f089f-143">Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation [och anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="f089f-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f089f-144">Kör Set-MailUser cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f089f-144">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="f089f-145">Där *GeneralMailboxOrMailUserIdParameter* anger en postlåda, och *DataEncryptionPolicyIdParameter* är ID för DEP.</span><span class="sxs-lookup"><span data-stu-id="f089f-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="f089f-146">Mer information om Set-MailUser-cmdleten finns [i Set-MailUser.](/powershell/module/exchange/set-mailuser)</span><span class="sxs-lookup"><span data-stu-id="f089f-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="f089f-147">Fastställa dep som tilldelats en postlåda</span><span class="sxs-lookup"><span data-stu-id="f089f-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="f089f-148">Ta reda på vilken DEP som tilldelats en postlåda med Get-MailboxStatistics cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f089f-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="f089f-149">Cmdleten returnerar en unik identifierare (GUID).</span><span class="sxs-lookup"><span data-stu-id="f089f-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="f089f-150">Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation [och anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="f089f-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="f089f-151">Där *GeneralMailboxOrMailUserIdParameter* anger en postlåda och DataEncryptionPolicyID returnerar GUID för DEP.</span><span class="sxs-lookup"><span data-stu-id="f089f-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="f089f-152">Mer information om Get-MailboxStatistics-cmdlet finns i [Get-MailboxStatistics.](/powershell/module/exchange/get-mailboxstatistics)</span><span class="sxs-lookup"><span data-stu-id="f089f-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="f089f-153">Kör Get-DataEncryptionPolicy för att ta reda på eget namn på den dep som postlådan är tilldelad till.</span><span class="sxs-lookup"><span data-stu-id="f089f-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="f089f-154">Där *GUID* är det GUID som returneras av Get-MailboxStatistics-cmdleten i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="f089f-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="f089f-155">Kontrollera att kundnyckeln har slutfört krypteringen</span><span class="sxs-lookup"><span data-stu-id="f089f-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="f089f-156">Oavsett om du precis har rullat en kundnyckel, tilldelat en ny DEP eller migrerat en postlåda kan du följa stegen i det här avsnittet för att säkerställa att krypteringen slutförs.</span><span class="sxs-lookup"><span data-stu-id="f089f-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="f089f-157">Verifiera krypteringen är klar för Exchange Online och Skype för företag</span><span class="sxs-lookup"><span data-stu-id="f089f-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="f089f-158">Det kan ta lite tid att kryptera en postlåda.</span><span class="sxs-lookup"><span data-stu-id="f089f-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="f089f-159">Vi rekommenderar att du väntar 72 timmar innan du försöker verifiera krypteringen efter att du har ändrat en DEP eller första gången du tilldelar en dep till en postlåda.</span><span class="sxs-lookup"><span data-stu-id="f089f-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="f089f-160">Använd Get-MailboxStatistics för att avgöra om en postlåda är krypterad.</span><span class="sxs-lookup"><span data-stu-id="f089f-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="f089f-161">Egenskapen IsEncrypted returnerar värdet **true** om postlådan är krypterad och värdet **false** om postlådan inte krypteras.</span><span class="sxs-lookup"><span data-stu-id="f089f-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="f089f-162">Tiden för att slutföra postlådeflyttningar beror på storleken på postlådan.</span><span class="sxs-lookup"><span data-stu-id="f089f-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="f089f-163">Om kundnyckeln inte helt har krypterat postlådan efter 72 timmar från det att du tilldelar en ny dep kontaktar du Microsofts support för att få hjälp.</span><span class="sxs-lookup"><span data-stu-id="f089f-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="f089f-164">Cmdleten New-MoveRequest inte längre tillgänglig för lokala postlådeflyttningar.</span><span class="sxs-lookup"><span data-stu-id="f089f-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="f089f-165">Mer information [finns i](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) det här meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f089f-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="f089f-166">Verifiera krypteringen är klar för SharePoint Online, OneDrive för företag och Teams filer</span><span class="sxs-lookup"><span data-stu-id="f089f-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="f089f-167">Kontrollera status för kryptering genom att köra cmdleten Get-SPODataEncryptionPolicy följande:</span><span class="sxs-lookup"><span data-stu-id="f089f-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="f089f-168">Utdata från den här cmdleten innehåller:</span><span class="sxs-lookup"><span data-stu-id="f089f-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="f089f-169">Primärnyckelns URI.</span><span class="sxs-lookup"><span data-stu-id="f089f-169">The URI of the primary key.</span></span>

- <span data-ttu-id="f089f-170">Den sekundära nyckelns URI.</span><span class="sxs-lookup"><span data-stu-id="f089f-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="f089f-171">Krypteringsstatus för geo.</span><span class="sxs-lookup"><span data-stu-id="f089f-171">The encryption status for the geo.</span></span> <span data-ttu-id="f089f-172">Möjliga tillstånd är:</span><span class="sxs-lookup"><span data-stu-id="f089f-172">Possible states include:</span></span>

  - <span data-ttu-id="f089f-173">**Avregistrerade:** Kryptering av kundnyckel har ännu inte tillämpats.</span><span class="sxs-lookup"><span data-stu-id="f089f-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="f089f-174">**Registrerar:** Kundnyckelkryptering har tillämpats och dina filer håller på att krypteras.</span><span class="sxs-lookup"><span data-stu-id="f089f-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="f089f-175">Om nyckeln för geo registrerar dig visas även information om vilken procentandel av webbplatserna i geo som är slutförda så att du kan övervaka krypteringsförloppet.</span><span class="sxs-lookup"><span data-stu-id="f089f-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="f089f-176">**Registrerad:** Customer Key-kryptering har använts och alla filer på alla webbplatser har krypterats.</span><span class="sxs-lookup"><span data-stu-id="f089f-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="f089f-177">**Rullande:** En viktig roll är under utveckling.</span><span class="sxs-lookup"><span data-stu-id="f089f-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="f089f-178">Om nyckeln för geo distribueras visas även information om vilken procentandel av webbplatserna som har slutfört nyckelrullningen så att du kan övervaka förloppet.</span><span class="sxs-lookup"><span data-stu-id="f089f-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a><span data-ttu-id="f089f-179">Återställ från kundnyckel till Microsoft-hanterade nycklar</span><span class="sxs-lookup"><span data-stu-id="f089f-179">Roll back from Customer Key to Microsoft managed Keys</span></span>

<span data-ttu-id="f089f-180">För kundnyckel på klientorganisationsnivå måste du kontakta Microsoft med en förfrågan om att "ta bort" från kundnyckeln.</span><span class="sxs-lookup"><span data-stu-id="f089f-180">For Customer Key at the tenant level, you'll need to reach out to Microsoft with a request for “offboarding” from Customer Key.</span></span> <span data-ttu-id="f089f-181">Begäran hanteras av teknikteamet för samtal.</span><span class="sxs-lookup"><span data-stu-id="f089f-181">The request will be handled by the On Call Engineering team.</span></span>

<span data-ttu-id="f089f-182">För Kundnyckel på programnivå gör du det genom att ta bort en DEP från postlådor med PowerShell-cmdleten Set-mailbox och ange `DataEncryptionPolicy` till `$NULL` .</span><span class="sxs-lookup"><span data-stu-id="f089f-182">For Customer Key at the application level, you do this by unassigning a DEP from mailboxes using the Set-mailbox PowerShell cmdlet and setting the `DataEncryptionPolicy` to `$NULL`.</span></span> <span data-ttu-id="f089f-183">När du kör den här cmdleten kopplas den tilldelade DEP:n bort och postlådan krypteras på nytt med den DEP som är kopplad till standardnycklar från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f089f-183">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft managed keys.</span></span> <span data-ttu-id="f089f-184">Du kan inte ta bort dep som används av Microsoft-hanterade nycklar.</span><span class="sxs-lookup"><span data-stu-id="f089f-184">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="f089f-185">Om du inte vill använda Microsoft hanterade nycklar kan du tilldela en annan kundnyckel DEP till postlådan.</span><span class="sxs-lookup"><span data-stu-id="f089f-185">If you don't want to use Microsoft managed keys, you can assign another Customer Key DEP to the mailbox.</span></span>

<span data-ttu-id="f089f-186">Om du vill ta bort dep från en postlåda med hjälp Set-Mailbox PowerShell-cmdleten slutför du de här stegen.</span><span class="sxs-lookup"><span data-stu-id="f089f-186">To unassign the DEP from a mailbox using the Set-Mailbox PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="f089f-187">Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation [och anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="f089f-187">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f089f-188">Kör Set-Mailbox cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f089f-188">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="f089f-189">Återkalla dina nycklar och starta datarensningssökvägen</span><span class="sxs-lookup"><span data-stu-id="f089f-189">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="f089f-190">Du styr återkallelsen av alla rotnycklar, inklusive tillgänglighetsnyckeln.</span><span class="sxs-lookup"><span data-stu-id="f089f-190">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="f089f-191">Kundnyckel ger dig kontroll över olika aspekter av utgångsplaneringen av kraven på regler.</span><span class="sxs-lookup"><span data-stu-id="f089f-191">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="f089f-192">Om du bestämmer dig för att återkalla dina nycklar för att tömma data och avsluta tjänsten tar tjänsten bort tillgänglighetsnyckeln när datarensningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="f089f-192">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span> <span data-ttu-id="f089f-193">Du kan inte utföra datarensning för en princip på klientorganisationsnivå.</span><span class="sxs-lookup"><span data-stu-id="f089f-193">You can't perform a data purge for a tenant-level policy.</span></span>

<span data-ttu-id="f089f-194">Microsoft 365 granskar och verifierar datarensningssökvägen.</span><span class="sxs-lookup"><span data-stu-id="f089f-194">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="f089f-195">Mer information finns i SSAE 18 SOC 2-rapporten som finns på [Service Trust Portal](https://servicetrust.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f089f-195">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="f089f-196">Dessutom rekommenderar Microsoft följande dokument:</span><span class="sxs-lookup"><span data-stu-id="f089f-196">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="f089f-197">Guide för riskbedömning och efterlevnad för finansiella institutioner i Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="f089f-197">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="f089f-198">Att tänka på när det gäller att avsluta planeringen i O365</span><span class="sxs-lookup"><span data-stu-id="f089f-198">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="f089f-199">Sökvägen för datarensning skiljer sig något mellan de olika tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="f089f-199">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="f089f-200">Återkalla dina kundnycklar och tillgänglighetsnyckeln för Exchange Online och Skype för företag</span><span class="sxs-lookup"><span data-stu-id="f089f-200">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="f089f-201">När du initierar datarensningssökvägen för Exchange Online och Skype för företag kan du ange en permanent begäran om datarensning för en DEP.</span><span class="sxs-lookup"><span data-stu-id="f089f-201">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="f089f-202">Om du gör det tas krypterade data i postlådorna som deP har tilldelats permanent bort.</span><span class="sxs-lookup"><span data-stu-id="f089f-202">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="f089f-203">Eftersom du bara kan köra PowerShell-cmdleten mot en DEP i taget bör du överväga att tilldela en enda dep till alla dina postlådor innan du påbörjar datarensningssökvägen.</span><span class="sxs-lookup"><span data-stu-id="f089f-203">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="f089f-204">Använd inte datarensningssökvägen för att ta bort en delmängd av dina postlådor.</span><span class="sxs-lookup"><span data-stu-id="f089f-204">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="f089f-205">Den här processen är endast avsedd för kunder som avslutar tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f089f-205">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="f089f-206">Så här påbörjar du datarensningen:</span><span class="sxs-lookup"><span data-stu-id="f089f-206">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="f089f-207">Ta bort radbytes- och borttagningsbehörigheter för "O365 Exchange Online" från Azure-nyckelvalv.</span><span class="sxs-lookup"><span data-stu-id="f089f-207">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="f089f-208">Använd ett arbets- eller skolkonto med global administratörsbehörighet i din organisation och [anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="f089f-208">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="f089f-209">För varje DEP som innehåller postlådor som du vill ta bort kör du cmdleten [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) enligt följande.</span><span class="sxs-lookup"><span data-stu-id="f089f-209">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="f089f-210">Om kommandot inte fungerar bör du kontrollera att du har tagit bort behörigheterna Exchange Online båda nycklarna i Azure Key Vault enligt tidigare i den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="f089f-210">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="f089f-211">När du har ställt in bytet PermanentDataPurgeRequested med cmdleten Set-DataEncryptionPolicy kan du inte längre tilldela den här DEP till postlådor.</span><span class="sxs-lookup"><span data-stu-id="f089f-211"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="f089f-212">Kontakta Microsofts support och begär Data Purge eDocument.</span><span class="sxs-lookup"><span data-stu-id="f089f-212">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="f089f-213">Microsoft skickar ett juridiskt dokument till dig på din begäran för att bekräfta och auktorisera databorttagning.</span><span class="sxs-lookup"><span data-stu-id="f089f-213">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="f089f-214">Den person i din organisation som registrerat sig som godkännare i FastTrack-erbjudandet under introduktionen måste signera dokumentet.</span><span class="sxs-lookup"><span data-stu-id="f089f-214">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="f089f-215">Normalt är det här en chef eller annan utsedd person i ditt företag som har en laglig behörighet att signera arbetet för din organisations räkning.</span><span class="sxs-lookup"><span data-stu-id="f089f-215">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="f089f-216">När din representant har signerat den juridiska dokumentet ska du skicka tillbaka den till Microsoft (vanligtvis via en eDoc-signatur).</span><span class="sxs-lookup"><span data-stu-id="f089f-216">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="f089f-217">När Microsoft har tagit emot det juridiska dokumentet kör Microsoft cmdlets för att starta datarensningen som först tar bort principen, markerar postlådorna för permanent borttagning och tar sedan bort tillgänglighetsnyckeln.</span><span class="sxs-lookup"><span data-stu-id="f089f-217">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="f089f-218">När datarensningen har slutförts har data rensats bort, är otillgängliga för Exchange Online och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="f089f-218">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="f089f-219">Återkalla dina kundnycklar och tillgänglighetsnyckeln för online SharePoint, OneDrive för företag och Teams filer</span><span class="sxs-lookup"><span data-stu-id="f089f-219">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="f089f-220">Så här påbörjar du datarensningen för SharePoint Online, OneDrive för företag och Teams genom att utföra följande steg:</span><span class="sxs-lookup"><span data-stu-id="f089f-220">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="f089f-221">Återkalla Azure-nyckelvalvsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="f089f-221">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="f089f-222">Alla nyckelvalvsadministratörer måste godkänna att återkalla åtkomsten.</span><span class="sxs-lookup"><span data-stu-id="f089f-222">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="f089f-223">Du tar inte bort Azure Key Vault för SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f089f-223">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="f089f-224">Nyckelvalv kan delas mellan flera olika SharePoint Online-klientorganisation och DEP:er.</span><span class="sxs-lookup"><span data-stu-id="f089f-224">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="f089f-225">Kontakta Microsoft om du vill ta bort tillgänglighetsnyckeln.</span><span class="sxs-lookup"><span data-stu-id="f089f-225">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="f089f-226">När du kontaktar Microsoft för att ta bort tillgänglighetsnyckeln skickar vi ett juridiskt dokument till dig.</span><span class="sxs-lookup"><span data-stu-id="f089f-226">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="f089f-227">Den person i din organisation som registrerat sig som godkännare i FastTrack-erbjudandet under introduktionen måste signera dokumentet.</span><span class="sxs-lookup"><span data-stu-id="f089f-227">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="f089f-228">Normalt är det här en chef eller annan person i företaget som har en laglig behörighet att signera arbetet åt din organisation.</span><span class="sxs-lookup"><span data-stu-id="f089f-228">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="f089f-229">När din representant signerar det juridiska dokumentet bör du skicka tillbaka det till Microsoft (oftast via en eDoc-signatur).</span><span class="sxs-lookup"><span data-stu-id="f089f-229">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="f089f-230">När Microsoft får det juridiska dokumentet kör vi cmdlets för att utlösa datarensningen som utför kryptoborttagning av klientnyckeln, webbplatsnyckeln och alla enskilda nycklar per dokument, vilket oåterkalleligen bryter nyckelhierarkin.</span><span class="sxs-lookup"><span data-stu-id="f089f-230">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="f089f-231">När cmdletarna för datarensning är klara har dina data rensats bort.</span><span class="sxs-lookup"><span data-stu-id="f089f-231">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f089f-232">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="f089f-232">Related articles</span></span>

- [<span data-ttu-id="f089f-233">Tjänstkryptering med kundnyckel</span><span class="sxs-lookup"><span data-stu-id="f089f-233">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="f089f-234">Läs mer om tillgänglighetsnyckeln</span><span class="sxs-lookup"><span data-stu-id="f089f-234">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="f089f-235">Konfigurera kundnyckel</span><span class="sxs-lookup"><span data-stu-id="f089f-235">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="f089f-236">Rulla eller rotera Customer Key eller en tillgänglighetsnyckel</span><span class="sxs-lookup"><span data-stu-id="f089f-236">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="f089f-237">Customer Lockbox</span><span class="sxs-lookup"><span data-stu-id="f089f-237">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="f089f-238">Tjänstkryptering</span><span class="sxs-lookup"><span data-stu-id="f089f-238">Service Encryption</span></span>](office-365-service-encryption.md)