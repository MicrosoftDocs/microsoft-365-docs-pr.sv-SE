---
title: Rulla eller rotera Customer Key eller en tillgänglighetsnyckel
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Lär dig hur du får kundens rotnycklar som lagras i Azure-nyckelvalvet som används med kundnyckeln. Tjänsterna omfattar Exchange Online, Skype för företag, SharePoint Online, OneDrive för företag och Teams filer.
ms.openlocfilehash: 892d77959bec1fb33b0ea6bcfaa8c530dd9b8911
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345124"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a><span data-ttu-id="387fb-104">Rulla eller rotera Customer Key eller en tillgänglighetsnyckel</span><span class="sxs-lookup"><span data-stu-id="387fb-104">Roll or rotate a Customer Key or an availability key</span></span>

> [!CAUTION]
> <span data-ttu-id="387fb-105">Använd bara en krypteringsnyckel som du använder med Kundnyckel när dina säkerhets- och efterlevnadskrav kräver att du ska rulla nyckeln.</span><span class="sxs-lookup"><span data-stu-id="387fb-105">Only roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key.</span></span> <span data-ttu-id="387fb-106">Dessutom ska du inte ta bort några nycklar som är eller har kopplats till principer.</span><span class="sxs-lookup"><span data-stu-id="387fb-106">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="387fb-107">När du använder tangenterna krypteras innehåll med tidigare nycklar.</span><span class="sxs-lookup"><span data-stu-id="387fb-107">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="387fb-108">Till exempel krypteras aktiva postlådor om ofta, inaktiva, frånkopplade och inaktiverade postlådor fortfarande krypteras med de tidigare nycklarna.</span><span class="sxs-lookup"><span data-stu-id="387fb-108">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="387fb-109">SharePoint Online säkerhetskopierar innehåll för återställnings- och återställningssyfte, så det kan fortfarande finnas arkiverat innehåll med hjälp av äldre nycklar.</span><span class="sxs-lookup"><span data-stu-id="387fb-109">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span>

## <a name="about-rolling-the-availability-key"></a><span data-ttu-id="387fb-110">Om att distribuera tillgänglighetsnyckeln</span><span class="sxs-lookup"><span data-stu-id="387fb-110">About rolling the availability key</span></span>

<span data-ttu-id="387fb-111">Microsoft visar inte direkt kontroll över tillgänglighetsnyckeln för kunder.</span><span class="sxs-lookup"><span data-stu-id="387fb-111">Microsoft does not expose direct control of the availability key to customers.</span></span> <span data-ttu-id="387fb-112">Du kan till exempel bara rulla (rotera) de nycklar som du äger i Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="387fb-112">For example, you can only roll (rotate) the keys that you own in Azure Key Vault.</span></span> <span data-ttu-id="387fb-113">Microsoft 365 att samla tillgänglighetsnycklarna i ett internt definierat schema.</span><span class="sxs-lookup"><span data-stu-id="387fb-113">Microsoft 365 rolls the availability keys on an internally-defined schedule.</span></span> <span data-ttu-id="387fb-114">Det finns inget serviceavtal på servicenivå (SLA) för dessa nyckelrullningar.</span><span class="sxs-lookup"><span data-stu-id="387fb-114">There is no customer-facing, service-level agreement (SLA) for these key rolls.</span></span> <span data-ttu-id="387fb-115">Microsoft 365 roterar tillgänglighetsnyckeln med hjälp Microsoft 365 en automatiserad och icke-manuell process.</span><span class="sxs-lookup"><span data-stu-id="387fb-115">Microsoft 365 rotates the availability key using Microsoft 365 service code in an automated, non-manual process.</span></span> <span data-ttu-id="387fb-116">Microsoft-administratörer kan starta processen.</span><span class="sxs-lookup"><span data-stu-id="387fb-116">Microsoft administrators may initiate the roll process.</span></span> <span data-ttu-id="387fb-117">Nyckeln förs över med automatiserade mekanismer utan direkt åtkomst till nyckellagret.</span><span class="sxs-lookup"><span data-stu-id="387fb-117">The key is rolled using automated mechanisms without direct access to the key store.</span></span> <span data-ttu-id="387fb-118">Åtkomst till den hemliga lagret för tillgänglighetsnyckeln tillhandahålls inte till Microsoft-administratörer.</span><span class="sxs-lookup"><span data-stu-id="387fb-118">Access to the availability key secret store is not provisioned to Microsoft administrators.</span></span> <span data-ttu-id="387fb-119">Rullning av tillgänglighetsnyckel utnyttjar samma mekanism som användes för att först generera nyckeln.</span><span class="sxs-lookup"><span data-stu-id="387fb-119">Availability key rolling leverages the same mechanism used to initially generate the key.</span></span> <span data-ttu-id="387fb-120">Mer information om tillgänglighetsnyckeln finns i [Förstå tillgänglighetsnyckeln](customer-key-availability-key-understand.md).</span><span class="sxs-lookup"><span data-stu-id="387fb-120">For more information about the availability key, see [Understand the availability key](customer-key-availability-key-understand.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="387fb-121">Exchange Online och Skype för företag av tillgänglighetsnycklar kan distribueras effektivt av kunder som skapar en ny dep, eftersom en unik tillgänglighetsnyckel genereras för varje deP du skapar.</span><span class="sxs-lookup"><span data-stu-id="387fb-121">Exchange Online and Skype for Business availability keys can be effectively rolled by customers creating a new DEP, since a unique availability key is generated for each DEP you create.</span></span> <span data-ttu-id="387fb-122">Tillgänglighetsnycklar för SharePoint Online-, OneDrive för företag- och Teams-filer finns på skogsnivå och delas mellan DEP:er och kunder, vilket innebär att rullning bara sker enligt ett internt definierat schema hos Microsoft.</span><span class="sxs-lookup"><span data-stu-id="387fb-122">Availability keys for SharePoint Online, OneDrive for Business, and Teams files exist at the forest level and are shared across DEPs and customers, which means rolling only occurs at a Microsoft internally defined schedule.</span></span> <span data-ttu-id="387fb-123">För att minimera risken för att inte rullande tillgänglighetsnyckeln varje gång en ny DEP skapas, rullar SharePoint, OneDrive och Teams klientorganisationens mellanliggande nyckel (TIK), nyckeln radbruten av kundens rotnycklar och tillgänglighetsnyckel varje gång en ny DEP skapas.</span><span class="sxs-lookup"><span data-stu-id="387fb-123">To mitigate the risk of not rolling the availability key each time a new DEP is created, SharePoint, OneDrive, and Teams roll the tenant intermediate key (TIK), the key wrapped by the customer root keys and availability key, each time a new DEP is created.</span></span>

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a><span data-ttu-id="387fb-124">Begära en ny version av varje befintlig rotnyckel som du vill slå upp</span><span class="sxs-lookup"><span data-stu-id="387fb-124">Request a new version of each existing root key you want to roll</span></span>

<span data-ttu-id="387fb-125">När du rullar en nyckel begär du en ny version av en befintlig nyckel.</span><span class="sxs-lookup"><span data-stu-id="387fb-125">When you roll a key, you request a new version of an existing key.</span></span> <span data-ttu-id="387fb-126">Om du vill begära en ny version av en befintlig nyckel använder du samma cmdlet [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey)med samma syntax som du använde för att skapa nyckeln från början.</span><span class="sxs-lookup"><span data-stu-id="387fb-126">To request a new version of an existing key, you use the same cmdlet, [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey), with the same syntax that you used to create the key in the first place.</span></span> <span data-ttu-id="387fb-127">När du har distribuerat en nyckel som är kopplad till en datakrypteringsprincip (DEP) kör du en annan cmdlet för att säkerställa att Kundnyckel börjar använda den nya nyckeln.</span><span class="sxs-lookup"><span data-stu-id="387fb-127">After you've finished rolling any key associated with a Data Encryption Policy (DEP), you run another cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="387fb-128">Gör detta steg i varje Azure Key Vault (AKV).</span><span class="sxs-lookup"><span data-stu-id="387fb-128">Do this step in each Azure Key Vault (AKV).</span></span>

<span data-ttu-id="387fb-129">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="387fb-129">For example:</span></span>

1. <span data-ttu-id="387fb-130">Logga in på din Azure-prenumeration med Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="387fb-130">Sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="387fb-131">Anvisningar finns i [Logga in med Azure PowerShell](/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="387fb-131">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="387fb-132">Kör Add-AzKeyVaultKey cmdleten enligt följande exempel:</span><span class="sxs-lookup"><span data-stu-id="387fb-132">Run the Add-AzKeyVaultKey cmdlet as shown in the following example:</span></span>

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   <span data-ttu-id="387fb-133">I det här exemplet finns, eftersom en nyckel som heter **Contoso-CK-EX-NA-VaultA1-Key001** finns i **valvet Contoso-CK-EX-NA-VaultA1,** skapar cmdleten en ny version av nyckeln.</span><span class="sxs-lookup"><span data-stu-id="387fb-133">In this example, since a key named **Contoso-CK-EX-NA-VaultA1-Key001** exists in the **Contoso-CK-EX-NA-VaultA1** vault, the cmdlet creates a new version of the key.</span></span> <span data-ttu-id="387fb-134">Den här åtgärden bevarar de tidigare nyckelversionerna i versionshistoriken för nyckeln.</span><span class="sxs-lookup"><span data-stu-id="387fb-134">This operation preserves the previous key versions in the version history for the key.</span></span> <span data-ttu-id="387fb-135">Du behöver den föregående nyckelversionen för att dekryptera data som fortfarande krypteras.</span><span class="sxs-lookup"><span data-stu-id="387fb-135">You need the previous key version to decrypt the data that it still encrypts.</span></span> <span data-ttu-id="387fb-136">När du har rullat alla nycklar som är associerade med en DEP kör du en extra cmdlet för att säkerställa att kundnyckeln börjar använda den nya nyckeln.</span><span class="sxs-lookup"><span data-stu-id="387fb-136">Once you complete rolling any key associated with a DEP,  run an extra cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="387fb-137">I följande avsnitt beskrivs cmdlet:arna i detalj.</span><span class="sxs-lookup"><span data-stu-id="387fb-137">The following sections describe the cmdlets in more detail.</span></span>
  
## <a name="update-the-keys-for-multi-workload-deps"></a><span data-ttu-id="387fb-138">Uppdatera nycklar för dep:er med flera arbetsbelastningar</span><span class="sxs-lookup"><span data-stu-id="387fb-138">Update the keys for multi-workload DEPs</span></span>

<span data-ttu-id="387fb-139">När du rullar en av Azure Key Vault-tangenterna som är kopplade till en DEP som används med flera arbetsbelastningar, måste du uppdatera DEP så att de pekar på den nya nyckeln.</span><span class="sxs-lookup"><span data-stu-id="387fb-139">When you roll either of the Azure Key Vault keys associated with a DEP used with multiple workloads, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="387fb-140">Den här processen roterar inte tillgänglighetsnyckeln.</span><span class="sxs-lookup"><span data-stu-id="387fb-140">This process does not rotate the availability key.</span></span>

<span data-ttu-id="387fb-141">För att instruera kundnyckeln att använda den nya nyckeln för att kryptera flera arbetsbelastningar slutför du följande steg:</span><span class="sxs-lookup"><span data-stu-id="387fb-141">To instruct Customer Key to use the new key to encrypt multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="387fb-142">Använd ett arbets- eller skolkonto som har globala administratörs- eller efterlevnadsadministratörsbehörigheter i din organisation på din lokala dator och anslut till [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) i ett Windows PowerShell fönster.</span><span class="sxs-lookup"><span data-stu-id="387fb-142">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="387fb-143">Kör Set-M365DataAtRestEncryptionPolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="387fb-143">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

<span data-ttu-id="387fb-144">Där *PolicyName* är namnet på eller ett unikt ID för principen.</span><span class="sxs-lookup"><span data-stu-id="387fb-144">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="387fb-145">Till exempel Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="387fb-145">For example, Contoso_Global.</span></span>

<span data-ttu-id="387fb-146">Exempel:</span><span class="sxs-lookup"><span data-stu-id="387fb-146">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a><span data-ttu-id="387fb-147">Uppdatera nycklar för Exchange Online DEP</span><span class="sxs-lookup"><span data-stu-id="387fb-147">Update the keys for Exchange Online DEPs</span></span>

<span data-ttu-id="387fb-148">När du rullar en av Azure Key Vault-tangenterna som är kopplade till en DEP som används med Exchange Online och Skype för företag måste du uppdatera DEP:en så att den pekar på den nya nyckeln.</span><span class="sxs-lookup"><span data-stu-id="387fb-148">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="387fb-149">Detta roterar inte tillgänglighetsnyckeln.</span><span class="sxs-lookup"><span data-stu-id="387fb-149">This does not rotate the availability key.</span></span>

<span data-ttu-id="387fb-150">Om du vill instruera kundnyckeln att använda den nya nyckeln för att kryptera postlådor kör du cmdleten Set-DataEncryptionPolicy följande:</span><span class="sxs-lookup"><span data-stu-id="387fb-150">To instruct Customer Key to use the new key to encrypt mailboxes, run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>

1. <span data-ttu-id="387fb-151">Kör Set-DataEncryptionPolicy cmdleten Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="387fb-151">Run the Set-DataEncryptionPolicy cmdlet in Azure PowerShell:</span></span>
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. <span data-ttu-id="387fb-152">Om du vill kontrollera värdet för egenskapen DataEncryptionPolicyID för postlådan använder du stegen i Avgöra vilken DEP som [tilldelats en postlåda.](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="387fb-152">To check the value for the DataEncryptionPolicyID property for the mailbox, use the steps in [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span></span> <span data-ttu-id="387fb-153">Värdet för den här egenskapen ändras när tjänsten tillämpar den uppdaterade nyckeln.</span><span class="sxs-lookup"><span data-stu-id="387fb-153">The value for this property changes once the service applies the updated key.</span></span>
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="387fb-154">Uppdatera nycklar för SharePoint Online, OneDrive för företag och Teams filer</span><span class="sxs-lookup"><span data-stu-id="387fb-154">Update the keys for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="387fb-155">SharePoint Med Online kan du bara rulla en tangent i taget.</span><span class="sxs-lookup"><span data-stu-id="387fb-155">SharePoint Online only allows you to roll one key at a time.</span></span> <span data-ttu-id="387fb-156">Om du vill återställa båda tangenterna i ett nyckelvalv väntar du tills den första åtgärden har slutförts.</span><span class="sxs-lookup"><span data-stu-id="387fb-156">If you want to roll both keys in a key vault, wait for the first operation to complete.</span></span> <span data-ttu-id="387fb-157">Microsoft rekommenderar att du sprider dina åtgärder för att undvika det här problemet.</span><span class="sxs-lookup"><span data-stu-id="387fb-157">Microsoft recommends that you stagger your operations to avoid this issue.</span></span> <span data-ttu-id="387fb-158">När du rullar en av Azure Key Vault-tangenterna som är kopplade till en DEP som används med SharePoint Online och OneDrive för företag måste du uppdatera DEP:en så att den pekar på den nya nyckeln.</span><span class="sxs-lookup"><span data-stu-id="387fb-158">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="387fb-159">Detta roterar inte tillgänglighetsnyckeln.</span><span class="sxs-lookup"><span data-stu-id="387fb-159">This does not rotate the availability key.</span></span>

1. <span data-ttu-id="387fb-160">Kör Update-SPODataEncryptionPolicy cmdleten så här:</span><span class="sxs-lookup"><span data-stu-id="387fb-160">Run the Update-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   <span data-ttu-id="387fb-161">När den här cmdleten startar nyckelrullningsåtgärden för SharePoint Online och OneDrive för företag slutförs inte åtgärden direkt.</span><span class="sxs-lookup"><span data-stu-id="387fb-161">While this cmdlet starts the key roll operation for SharePoint Online and OneDrive for Business, the action doesn't complete immediately.</span></span>

2. <span data-ttu-id="387fb-162">Om du vill se förloppet för nyckelrullningsåtgärden kör du Get-SPODataEncryptionPolicy cmdlet så här:</span><span class="sxs-lookup"><span data-stu-id="387fb-162">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a><span data-ttu-id="387fb-163">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="387fb-163">Related articles</span></span>

- [<span data-ttu-id="387fb-164">Tjänstkryptering med kundnyckel för Office 365</span><span class="sxs-lookup"><span data-stu-id="387fb-164">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="387fb-165">Konfigurera Customer Key för Office 365</span><span class="sxs-lookup"><span data-stu-id="387fb-165">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="387fb-166">Hantera Customer Key för Office 365</span><span class="sxs-lookup"><span data-stu-id="387fb-166">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="387fb-167">Läs mer om tillgänglighetsnyckeln</span><span class="sxs-lookup"><span data-stu-id="387fb-167">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)