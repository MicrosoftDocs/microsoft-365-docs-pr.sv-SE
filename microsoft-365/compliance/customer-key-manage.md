---
title: Hantera kundnyckel
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
description: När du har ställt in kundnyckeln, lär dig hur du hanterar den genom att återställa AKV-nycklar och hantera behörigheter och skapa och tilldela principer för datakryptering.
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345064"
---
# <a name="manage-customer-key"></a><span data-ttu-id="61d0f-103">Hantera kundnyckel</span><span class="sxs-lookup"><span data-stu-id="61d0f-103">Manage Customer Key</span></span>

<span data-ttu-id="61d0f-104">När du har konfigurerat kundnyckeln för Office 365, måste du skapa och tilldela en eller flera principer för datakryptering (DEP).</span><span class="sxs-lookup"><span data-stu-id="61d0f-104">After you've set up Customer Key for Office 365, you'll need to create and assign one or more data encryption policies (DEP).</span></span> <span data-ttu-id="61d0f-105">När du har tilldelat dep:erna kan du hantera dina nycklar enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="61d0f-105">Once you've assigned your DEPs, you can manage your keys as described in this article.</span></span> <span data-ttu-id="61d0f-106">Läs mer om kundnyckel i relaterade ämnen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-106">Learn more about Customer Key in the related topics.</span></span>

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a><span data-ttu-id="61d0f-107">Skapa en dep för användning med flera arbetsbelastningar för alla användare i klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="61d0f-107">Create a DEP for use with multiple workloads for all tenant users</span></span>

<span data-ttu-id="61d0f-108">Innan du börjar bör du kontrollera att du har slutfört de uppgifter som krävs för att konfigurera Kunden.</span><span class="sxs-lookup"><span data-stu-id="61d0f-108">Before you begin, ensure that you've completed the tasks required to set up Customer.</span></span> <span data-ttu-id="61d0f-109">Mer information finns i [Konfigurera kundnyckel.](customer-key-set-up.md)</span><span class="sxs-lookup"><span data-stu-id="61d0f-109">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="61d0f-110">För att skapa DEP behöver du URI:erna för nyckelvalvet som du fick under installationen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-110">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="61d0f-111">Mer information finns i [Hämta URI för varje Azure Key Vault-nyckel.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="61d0f-111">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="61d0f-112">Följ de här anvisningarna om du vill skapa en deP för flera arbetsbelastningar:</span><span class="sxs-lookup"><span data-stu-id="61d0f-112">To create a multi-workload DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="61d0f-113">Använd ett arbets- eller skolkonto som har globala administratörs- eller efterlevnadsadministratörsbehörigheter i din organisation på din lokala dator och anslut till [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) i ett Windows PowerShell fönster.</span><span class="sxs-lookup"><span data-stu-id="61d0f-113">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="61d0f-114">Om du vill skapa en DEP använder du New-M365DataAtRestEncryptionPolicy-cmdleten.</span><span class="sxs-lookup"><span data-stu-id="61d0f-114">To create a DEP, use the New-M365DataAtRestEncryptionPolicy cmdlet.</span></span>

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   <span data-ttu-id="61d0f-115">Var:</span><span class="sxs-lookup"><span data-stu-id="61d0f-115">Where:</span></span>

   - <span data-ttu-id="61d0f-116">*PolicyName* är det namn du vill använda för principen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-116">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="61d0f-117">Namn får inte innehålla blanksteg.</span><span class="sxs-lookup"><span data-stu-id="61d0f-117">Names can't contain spaces.</span></span> <span data-ttu-id="61d0f-118">Till exempel Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="61d0f-118">For example, Contoso_Global.</span></span>

   - <span data-ttu-id="61d0f-119">*KeyVaultURI1* är URI:t för den första nyckeln i principen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-119">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="61d0f-120">Till exempel <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span><span class="sxs-lookup"><span data-stu-id="61d0f-120">For example, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span></span>

   - <span data-ttu-id="61d0f-121">*KeyVaultURI2* är URI:t för den andra nyckeln i principen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-121">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="61d0f-122">Till exempel <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span><span class="sxs-lookup"><span data-stu-id="61d0f-122">For example, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span></span> <span data-ttu-id="61d0f-123">Avgränsa de två URI:erna med ett kommatecken och ett blanksteg.</span><span class="sxs-lookup"><span data-stu-id="61d0f-123">Separate the two URIs by a comma and a space.</span></span>

   - <span data-ttu-id="61d0f-124">*Principbeskrivning* är en användarvänlig beskrivning av principen som hjälper dig att komma ihåg vad principen gäller.</span><span class="sxs-lookup"><span data-stu-id="61d0f-124">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="61d0f-125">Du kan ta med blanksteg i beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-125">You can include spaces in the description.</span></span> <span data-ttu-id="61d0f-126">Till exempel "Rotprincip för flera arbetsbelastningar för alla användare i klientorganisationen".</span><span class="sxs-lookup"><span data-stu-id="61d0f-126">For example, "Root policy for multiple workloads for all users in the tenant.".</span></span>

<span data-ttu-id="61d0f-127">Exempel:</span><span class="sxs-lookup"><span data-stu-id="61d0f-127">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a><span data-ttu-id="61d0f-128">Tilldela princip för flera arbetsbelastningar</span><span class="sxs-lookup"><span data-stu-id="61d0f-128">Assign multi-workload policy</span></span>

<span data-ttu-id="61d0f-129">Tilldela dep genom att använda Set-M365DataAtRestEncryptionPolicyAssignment cmdleten.</span><span class="sxs-lookup"><span data-stu-id="61d0f-129">Assign the DEP by using the Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="61d0f-130">När du tilldelar principen Microsoft 365 krypteras data med den nyckel som identifieras i dep.</span><span class="sxs-lookup"><span data-stu-id="61d0f-130">Once you assign the policy, Microsoft 365 encrypts the data with the key identified in the DEP.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 <span data-ttu-id="61d0f-131">Där *PolicyName* är namnet på principen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-131">Where *PolicyName* is the name of the policy.</span></span> <span data-ttu-id="61d0f-132">Till exempel Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="61d0f-132">For example, Contoso_Global.</span></span>

<span data-ttu-id="61d0f-133">Exempel:</span><span class="sxs-lookup"><span data-stu-id="61d0f-133">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a><span data-ttu-id="61d0f-134">Skapa en deP för användning Exchange Online postlådor</span><span class="sxs-lookup"><span data-stu-id="61d0f-134">Create a DEP for use with Exchange Online mailboxes</span></span>

<span data-ttu-id="61d0f-135">Innan du börjar bör du kontrollera att du har slutfört de uppgifter som krävs för att konfigurera Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="61d0f-135">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="61d0f-136">Mer information finns i [Konfigurera kundnyckel.](customer-key-set-up.md)</span><span class="sxs-lookup"><span data-stu-id="61d0f-136">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="61d0f-137">Du utför de här stegen genom att fjärransluta till ett Exchange Online med Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61d0f-137">You'll complete these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>

<span data-ttu-id="61d0f-138">En DEP är kopplad till en uppsättning nycklar som lagras i Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="61d0f-138">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="61d0f-139">Du tilldelar en dep till en postlåda i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61d0f-139">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="61d0f-140">Microsoft 365 kryptera postlådan med hjälp av de nycklar som identifieras i principen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-140">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="61d0f-141">För att skapa DEP behöver du URI:erna för nyckelvalvet som du fick under installationen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-141">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="61d0f-142">Mer information finns i [Hämta URI för varje Azure Key Vault-nyckel.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="61d0f-142">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="61d0f-143">Kom ihåg!</span><span class="sxs-lookup"><span data-stu-id="61d0f-143">Remember!</span></span> <span data-ttu-id="61d0f-144">När du skapar en DEP anger du två nycklar i två olika Azure-nyckelvalv.</span><span class="sxs-lookup"><span data-stu-id="61d0f-144">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="61d0f-145">Skapa de här nycklarna i två separata Azure-regioner för att säkerställa georedundans.</span><span class="sxs-lookup"><span data-stu-id="61d0f-145">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>

<span data-ttu-id="61d0f-146">Följ de här stegen om du vill skapa en deP för användning med en postlåda:</span><span class="sxs-lookup"><span data-stu-id="61d0f-146">To create a DEP to use with a mailbox, follow these steps:</span></span>
  
1. <span data-ttu-id="61d0f-147">Använd ett arbets- eller skolkonto som har global administratörs- eller Exchange Online-administratörsbehörighet i din organisation på din lokala dator och anslut [till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) i ett Windows PowerShell fönster.</span><span class="sxs-lookup"><span data-stu-id="61d0f-147">On your local computer, using a work or school account that has global administrator or Exchange Online admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="61d0f-148">Om du vill skapa en DEP använder du New-DataEncryptionPolicy-cmdleten genom att skriva följande kommando.</span><span class="sxs-lookup"><span data-stu-id="61d0f-148">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="61d0f-149">Var:</span><span class="sxs-lookup"><span data-stu-id="61d0f-149">Where:</span></span>

   - <span data-ttu-id="61d0f-150">*PolicyName* är det namn du vill använda för principen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-150">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="61d0f-151">Namn får inte innehålla blanksteg.</span><span class="sxs-lookup"><span data-stu-id="61d0f-151">Names can't contain spaces.</span></span> <span data-ttu-id="61d0f-152">Till exempel USA_mailboxes.</span><span class="sxs-lookup"><span data-stu-id="61d0f-152">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="61d0f-153">*Principbeskrivning* är en användarvänlig beskrivning av principen som hjälper dig att komma ihåg vad principen gäller.</span><span class="sxs-lookup"><span data-stu-id="61d0f-153">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="61d0f-154">Du kan ta med blanksteg i beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-154">You can include spaces in the description.</span></span> <span data-ttu-id="61d0f-155">Till exempel "Rotnyckel för postlådor i USA och dess territorier".</span><span class="sxs-lookup"><span data-stu-id="61d0f-155">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="61d0f-156">*KeyVaultURI1* är URI:t för den första nyckeln i principen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-156">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="61d0f-157">Till exempel <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span><span class="sxs-lookup"><span data-stu-id="61d0f-157">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="61d0f-158">*KeyVaultURI2* är URI:t för den andra nyckeln i principen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-158">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="61d0f-159">Till exempel <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span><span class="sxs-lookup"><span data-stu-id="61d0f-159">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="61d0f-160">Avgränsa de två URI:erna med ett kommatecken och ett blanksteg.</span><span class="sxs-lookup"><span data-stu-id="61d0f-160">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="61d0f-161">Exempel:</span><span class="sxs-lookup"><span data-stu-id="61d0f-161">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="61d0f-162">Detaljerad information om syntax och parametrar finns i [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span><span class="sxs-lookup"><span data-stu-id="61d0f-162">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="61d0f-163">Tilldela en dep till en postlåda</span><span class="sxs-lookup"><span data-stu-id="61d0f-163">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="61d0f-164">Tilldela dep till en postlåda med hjälp av Set-Mailbox-cmdleten.</span><span class="sxs-lookup"><span data-stu-id="61d0f-164">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="61d0f-165">När du tilldelar principen Microsoft 365 kryptera postlådan med nyckeln som identifieras i dep.</span><span class="sxs-lookup"><span data-stu-id="61d0f-165">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key identified in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="61d0f-166">Där *MailboxIdParameter* anger en användarpostlåda.</span><span class="sxs-lookup"><span data-stu-id="61d0f-166">Where *MailboxIdParameter* specifies a user mailbox.</span></span> <span data-ttu-id="61d0f-167">Mer information om Set-Mailbox-cmdleten finns [i Set-Mailbox](/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="61d0f-167">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="61d0f-168">I hybridmiljöer kan du tilldela en dep till de lokala e-postlådedata som synkroniseras till Exchange Online klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="61d0f-168">In hybrid environments, you can assign a DEP to the on-premises mailbox data that is synchronized into your Exchange Online tenant.</span></span> <span data-ttu-id="61d0f-169">Om du vill tilldela en DEP till denna synkroniserade postlådedata använder du cmdleten Set-MailUser postlådan.</span><span class="sxs-lookup"><span data-stu-id="61d0f-169">To assign a DEP to this synchronized mailbox data, you'll use the Set-MailUser cmdlet.</span></span> <span data-ttu-id="61d0f-170">Mer information om e-postdata i hybridmiljön finns i lokala postlådor med Outlook för iOS och [Android med modern hybridautentisering.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)</span><span class="sxs-lookup"><span data-stu-id="61d0f-170">For more information about mailbox data in the hybrid environment, see [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="61d0f-171">Där *MailUserIdParameter* anger en e-postanvändare (kallas även e-postaktiverad användare).</span><span class="sxs-lookup"><span data-stu-id="61d0f-171">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="61d0f-172">Mer information om Set-MailUser-cmdleten finns [i Set-MailUser.](/powershell/module/exchange/set-mailuser)</span><span class="sxs-lookup"><span data-stu-id="61d0f-172">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="61d0f-173">Skapa en deP för användning SharePoint Online OneDrive för företag och Teams filer</span><span class="sxs-lookup"><span data-stu-id="61d0f-173">Create a DEP for use with SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="61d0f-174">Innan du börjar bör du kontrollera att du har slutfört de uppgifter som krävs för att konfigurera Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="61d0f-174">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="61d0f-175">Mer information finns i [Konfigurera kundnyckel.](customer-key-set-up.md)</span><span class="sxs-lookup"><span data-stu-id="61d0f-175">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span>
  
<span data-ttu-id="61d0f-176">Om du vill konfigurera kundnyckeln för SharePoint Online-, OneDrive för företag- och Teams-filer utför du de här stegen genom att fjärransluta till SharePoint Online med Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61d0f-176">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you complete these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
<span data-ttu-id="61d0f-177">Du kopplar en DEP till en uppsättning nycklar som lagras i Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="61d0f-177">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="61d0f-178">Du använder en DEP för alla dina data på en geografisk plats, även kallad geo.</span><span class="sxs-lookup"><span data-stu-id="61d0f-178">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="61d0f-179">Om du använder multi-geofunktionen i Office 365 kan du skapa en DEP per geo med möjlighet att använda olika nycklar per geo.</span><span class="sxs-lookup"><span data-stu-id="61d0f-179">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="61d0f-180">Om du inte använder multi-geo kan du skapa en deP i organisationen för användning med SharePoint Online, OneDrive för företag och Teams filer.</span><span class="sxs-lookup"><span data-stu-id="61d0f-180">If you aren't using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="61d0f-181">Microsoft 365 använder nycklar som identifieras i DATAkod för att kryptera data i geoinformationen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-181">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="61d0f-182">För att skapa DEP behöver du URI:erna för nyckelvalvet som du fick under installationen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-182">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="61d0f-183">Mer information finns i [Hämta URI för varje Azure Key Vault-nyckel.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="61d0f-183">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>
  
<span data-ttu-id="61d0f-184">Kom ihåg!</span><span class="sxs-lookup"><span data-stu-id="61d0f-184">Remember!</span></span> <span data-ttu-id="61d0f-185">När du skapar en DEP anger du två nycklar i två olika Azure-nyckelvalv.</span><span class="sxs-lookup"><span data-stu-id="61d0f-185">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="61d0f-186">Skapa de här nycklarna i två separata Azure-regioner för att säkerställa georedundans.</span><span class="sxs-lookup"><span data-stu-id="61d0f-186">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="61d0f-187">Om du vill skapa en DEP måste du fjärransluta till SharePoint Online med hjälp av Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61d0f-187">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="61d0f-188">Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation på din lokala [dator Anslut att SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="61d0f-188">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span></span>

2. <span data-ttu-id="61d0f-189">I Microsoft Office SharePoint Online Management Shell kör du cmdleten Register-SPODataEncryptionPolicy följande:</span><span class="sxs-lookup"><span data-stu-id="61d0f-189">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="61d0f-190">Exempel:</span><span class="sxs-lookup"><span data-stu-id="61d0f-190">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="61d0f-191">När du registrerar DEP börjar krypteringen på data i geo.</span><span class="sxs-lookup"><span data-stu-id="61d0f-191">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="61d0f-192">Kryptering kan ta lite tid.</span><span class="sxs-lookup"><span data-stu-id="61d0f-192">Encryption can take some time.</span></span> <span data-ttu-id="61d0f-193">Mer information om hur du använder den här parametern [finns i Register-SPODataEncryptionPolicy.](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="61d0f-193">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a><span data-ttu-id="61d0f-194">Visa de DEP:er som du har skapat Exchange Online postlådor</span><span class="sxs-lookup"><span data-stu-id="61d0f-194">View the DEPs you've created for Exchange Online mailboxes</span></span>

<span data-ttu-id="61d0f-195">Om du vill visa en lista över alla DEPs du har skapat för postlådor använder du PowerShellGet-DataEncryptionPolicy-cmdleten.</span><span class="sxs-lookup"><span data-stu-id="61d0f-195">To view a list of all the DEPs you've created for mailboxes, use the Get-DataEncryptionPolicy PowerShell cmdlet.</span></span>

1. <span data-ttu-id="61d0f-196">Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation [och anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="61d0f-196">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="61d0f-197">Om du vill returnera alla DEP:er i organisationen kör du Get-DataEncryptionPolicy-cmdleten utan några parametrar.</span><span class="sxs-lookup"><span data-stu-id="61d0f-197">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="61d0f-198">Mer information om Get-DataEncryptionPolicy cmdlet finns i [Get-DataEncryptionPolicy.](/powershell/module/exchange/get-dataencryptionpolicy)</span><span class="sxs-lookup"><span data-stu-id="61d0f-198">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="61d0f-199">Tilldela en DEP innan du migrerar en postlåda till molnet</span><span class="sxs-lookup"><span data-stu-id="61d0f-199">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="61d0f-200">När du tilldelar Microsoft 365 krypteras innehållet i postlådan med den tilldelade dataleverantören under migreringen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-200">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="61d0f-201">Den här processen är mer effektiv än att migrera postlådan, tilldela DEP och sedan vänta på att krypteringen sker, som kan ta timmar eller möjligt dagar.</span><span class="sxs-lookup"><span data-stu-id="61d0f-201">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="61d0f-202">Om du vill tilldela en DEP till en postlåda innan du migrerar Office 365 den kör du cmdleten Set-MailUser i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="61d0f-202">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="61d0f-203">Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation [och anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="61d0f-203">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="61d0f-204">Kör Set-MailUser cmdlet.</span><span class="sxs-lookup"><span data-stu-id="61d0f-204">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="61d0f-205">Där *GeneralMailboxOrMailUserIdParameter* anger en postlåda, och *DataEncryptionPolicyIdParameter* är ID för DEP.</span><span class="sxs-lookup"><span data-stu-id="61d0f-205">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="61d0f-206">Mer information om Set-MailUser-cmdleten finns [i Set-MailUser.](/powershell/module/exchange/set-mailuser)</span><span class="sxs-lookup"><span data-stu-id="61d0f-206">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="61d0f-207">Fastställa dep som tilldelats en postlåda</span><span class="sxs-lookup"><span data-stu-id="61d0f-207">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="61d0f-208">Ta reda på vilken DEP som tilldelats en postlåda med Get-MailboxStatistics cmdlet.</span><span class="sxs-lookup"><span data-stu-id="61d0f-208">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="61d0f-209">Cmdleten returnerar en unik identifierare (GUID).</span><span class="sxs-lookup"><span data-stu-id="61d0f-209">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="61d0f-210">Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation [och anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="61d0f-210">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="61d0f-211">Där *GeneralMailboxOrMailUserIdParameter* anger en postlåda och DataEncryptionPolicyID returnerar GUID för DEP.</span><span class="sxs-lookup"><span data-stu-id="61d0f-211">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="61d0f-212">Mer information om Get-MailboxStatistics-cmdlet finns i [Get-MailboxStatistics.](/powershell/module/exchange/get-mailboxstatistics)</span><span class="sxs-lookup"><span data-stu-id="61d0f-212">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="61d0f-213">Kör Get-DataEncryptionPolicy för att ta reda på eget namn på den dep som postlådan är tilldelad till.</span><span class="sxs-lookup"><span data-stu-id="61d0f-213">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="61d0f-214">Där *GUID* är det GUID som returneras av Get-MailboxStatistics-cmdleten i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="61d0f-214">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="61d0f-215">Kontrollera att kundnyckeln har slutfört krypteringen</span><span class="sxs-lookup"><span data-stu-id="61d0f-215">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="61d0f-216">Oavsett om du har rullat en kundnyckel, tilldelat en ny DEP eller migrerat en postlåda kan du följa stegen i det här avsnittet för att säkerställa att krypteringen slutförs.</span><span class="sxs-lookup"><span data-stu-id="61d0f-216">Whether you've rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a><span data-ttu-id="61d0f-217">Verifiera att krypteringen är Exchange Online postlådor</span><span class="sxs-lookup"><span data-stu-id="61d0f-217">Verify encryption completes for Exchange Online mailboxes</span></span>

<span data-ttu-id="61d0f-218">Det kan ta lite tid att kryptera en postlåda.</span><span class="sxs-lookup"><span data-stu-id="61d0f-218">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="61d0f-219">För första gången som kryptering måste postlådan också helt flytta från en databas till en annan innan tjänsten kan kryptera postlådan.</span><span class="sxs-lookup"><span data-stu-id="61d0f-219">For first time encryption, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span>
  
<span data-ttu-id="61d0f-220">Använd Get-MailboxStatistics för att avgöra om en postlåda är krypterad.</span><span class="sxs-lookup"><span data-stu-id="61d0f-220">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="61d0f-221">Egenskapen IsEncrypted returnerar värdet **True** om postlådan är krypterad och värdet **false** om postlådan inte krypteras.</span><span class="sxs-lookup"><span data-stu-id="61d0f-221">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox isn't encrypted.</span></span> <span data-ttu-id="61d0f-222">Tiden för att slutföra postlådeflyttningar beror på antalet postlådor som du tilldelar en deP för första gången och storleken på postlådorna.</span><span class="sxs-lookup"><span data-stu-id="61d0f-222">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, and the size of the mailboxes.</span></span> <span data-ttu-id="61d0f-223">Om postlådorna inte har krypterats efter en vecka från den tidpunkt då du tilldelade dep:et ska du kontakta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="61d0f-223">If the mailboxes haven't been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="61d0f-224">Cmdleten New-MoveRequest inte längre tillgänglig för lokala postlådeflyttningar.</span><span class="sxs-lookup"><span data-stu-id="61d0f-224">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="61d0f-225">Mer information [finns i](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) det här meddelandet.</span><span class="sxs-lookup"><span data-stu-id="61d0f-225">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="61d0f-226">Verifiera krypteringen är klar för SharePoint Online, OneDrive för företag och Teams filer</span><span class="sxs-lookup"><span data-stu-id="61d0f-226">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="61d0f-227">Kontrollera status för kryptering genom att köra cmdleten Get-SPODataEncryptionPolicy följande:</span><span class="sxs-lookup"><span data-stu-id="61d0f-227">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="61d0f-228">Utdata från den här cmdleten innehåller:</span><span class="sxs-lookup"><span data-stu-id="61d0f-228">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="61d0f-229">Primärnyckelns URI.</span><span class="sxs-lookup"><span data-stu-id="61d0f-229">The URI of the primary key.</span></span>

- <span data-ttu-id="61d0f-230">Den sekundära nyckelns URI.</span><span class="sxs-lookup"><span data-stu-id="61d0f-230">The URI of the secondary key.</span></span>

- <span data-ttu-id="61d0f-231">Krypteringsstatus för geo.</span><span class="sxs-lookup"><span data-stu-id="61d0f-231">The encryption status for the geo.</span></span> <span data-ttu-id="61d0f-232">Möjliga tillstånd är:</span><span class="sxs-lookup"><span data-stu-id="61d0f-232">Possible states include:</span></span>

  - <span data-ttu-id="61d0f-233">**Avregistrerade:** Kryptering av kundnyckel har ännu inte tillämpats.</span><span class="sxs-lookup"><span data-stu-id="61d0f-233">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="61d0f-234">**Registrerar:** Kundnyckelkryptering har tillämpats och dina filer håller på att krypteras.</span><span class="sxs-lookup"><span data-stu-id="61d0f-234">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="61d0f-235">Om nyckeln för geo registrerar dig visas även information om vilken procentandel av webbplatserna i geo som är slutförda så att du kan övervaka krypteringsförloppet.</span><span class="sxs-lookup"><span data-stu-id="61d0f-235">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="61d0f-236">**Registrerad:** Customer Key-kryptering har använts och alla filer på alla webbplatser har krypterats.</span><span class="sxs-lookup"><span data-stu-id="61d0f-236">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="61d0f-237">**Rullande:** En viktig roll är under utveckling.</span><span class="sxs-lookup"><span data-stu-id="61d0f-237">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="61d0f-238">Om nyckeln för geo distribueras visas även information om vilken procentandel av webbplatserna som har slutfört nyckelrullningen så att du kan övervaka förloppet.</span><span class="sxs-lookup"><span data-stu-id="61d0f-238">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a><span data-ttu-id="61d0f-239">Få information om de du använder med flera arbetsbelastningar</span><span class="sxs-lookup"><span data-stu-id="61d0f-239">Get details about DEPs you use with multiple workloads</span></span>

<span data-ttu-id="61d0f-240">Gör så här för att få information om alla de de du har skapat för att använda med flera arbetsbelastningar:</span><span class="sxs-lookup"><span data-stu-id="61d0f-240">To get details about all of the DEPs you've created to use with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="61d0f-241">Använd ett arbets- eller skolkonto som har globala administratörs- eller efterlevnadsadministratörsbehörigheter i din organisation på din lokala dator och anslut till [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) i ett Windows PowerShell fönster.</span><span class="sxs-lookup"><span data-stu-id="61d0f-241">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

   - <span data-ttu-id="61d0f-242">Kör det här kommandot om du vill returnera listan över alla dep:er med flera arbetsbelastningar i organisationen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-242">To return the list of all multi-workload DEPs in the organization, run this command.</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - <span data-ttu-id="61d0f-243">Kör det här kommandot om du vill returnera information om en viss DEP.</span><span class="sxs-lookup"><span data-stu-id="61d0f-243">To return details about a specific DEP, run this command.</span></span> <span data-ttu-id="61d0f-244">Det här exemplet returnerar detaljerad information för den deP som heter "Contoso_Global".</span><span class="sxs-lookup"><span data-stu-id="61d0f-244">This example returns detailed information for the DEP named "Contoso_Global".</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a><span data-ttu-id="61d0f-245">Hämta information om dep-tilldelning med flera arbetsbelastningar</span><span class="sxs-lookup"><span data-stu-id="61d0f-245">Get multi-workload DEP assignment information</span></span>

<span data-ttu-id="61d0f-246">Följ de här stegen för att ta reda på vilken DEP som är tilldelad till din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="61d0f-246">To find out which DEP is currently assigned to your tenant, follow these steps.</span></span> 

1. <span data-ttu-id="61d0f-247">Använd ett arbets- eller skolkonto som har globala administratörs- eller efterlevnadsadministratörsbehörigheter i din organisation på din lokala dator och anslut till [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) i ett Windows PowerShell fönster.</span><span class="sxs-lookup"><span data-stu-id="61d0f-247">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="61d0f-248">Skriv det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="61d0f-248">Type this command.</span></span>

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a><span data-ttu-id="61d0f-249">Inaktivera en dep för flera arbetsbelastningar</span><span class="sxs-lookup"><span data-stu-id="61d0f-249">Disable a multi-workload DEP</span></span>

<span data-ttu-id="61d0f-250">Innan du inaktiverar en dep för flera arbetsbelastningar tar du bort dep från arbetsbelastningar i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-250">Before you disable a multi-workload DEP, unassign the DEP from workloads in your tenant.</span></span> <span data-ttu-id="61d0f-251">Inaktivera en deP som används med flera arbetsbelastningar genom att utföra följande steg:</span><span class="sxs-lookup"><span data-stu-id="61d0f-251">To disable a DEP used with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="61d0f-252">Använd ett arbets- eller skolkonto som har globala administratörs- eller efterlevnadsadministratörsbehörigheter i din organisation på din lokala dator och anslut till [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) i ett Windows PowerShell fönster.</span><span class="sxs-lookup"><span data-stu-id="61d0f-252">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="61d0f-253">Kör Set-M365DataAtRestEncryptionPolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="61d0f-253">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

<span data-ttu-id="61d0f-254">Där *PolicyName* är namnet på eller ett unikt ID för principen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-254">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="61d0f-255">Till exempel Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="61d0f-255">For example, Contoso_Global.</span></span>

<span data-ttu-id="61d0f-256">Exempel:</span><span class="sxs-lookup"><span data-stu-id="61d0f-256">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="61d0f-257">Återställa Azure-nyckelvalvsnycklar</span><span class="sxs-lookup"><span data-stu-id="61d0f-257">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="61d0f-258">Innan du utför en återställning använder du de återställningsfunktioner som tillhandahålls av mjuk borttagning.</span><span class="sxs-lookup"><span data-stu-id="61d0f-258">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="61d0f-259">Alla nycklar som används med kundnyckeln måste ha mjuk borttagning aktiverad.</span><span class="sxs-lookup"><span data-stu-id="61d0f-259">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="61d0f-260">Mjuk borttagning fungerar som en papperskorg och tillåter återställning i upp till 90 dagar utan att du behöver återställa den.</span><span class="sxs-lookup"><span data-stu-id="61d0f-260">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="61d0f-261">Återställning bör endast krävas i extrema eller ovanliga omständigheter, till exempel om nyckeln eller nyckelvalvet går förlorat.</span><span class="sxs-lookup"><span data-stu-id="61d0f-261">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="61d0f-262">Om du måste återställa en nyckel för användning med Azure PowerShell kör du cmdleten Restore-AzureKeyVaultKey följande:</span><span class="sxs-lookup"><span data-stu-id="61d0f-262">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="61d0f-263">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="61d0f-263">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="61d0f-264">Om nyckelns valv redan innehåller en nyckel med samma namn misslyckas återställningsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="61d0f-264">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="61d0f-265">Restore-AzKeyVaultKey alla viktiga versioner och alla metadata för nyckeln, inklusive nyckelnamnet.</span><span class="sxs-lookup"><span data-stu-id="61d0f-265">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="61d0f-266">Hantera behörigheter för nyckelvalv</span><span class="sxs-lookup"><span data-stu-id="61d0f-266">Manage key vault permissions</span></span>

<span data-ttu-id="61d0f-267">Flera cmdlets är tillgängliga som gör att du kan visa och, om det behövs, ta bort behörigheter för nyckelvalv.</span><span class="sxs-lookup"><span data-stu-id="61d0f-267">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="61d0f-268">Du kan behöva ta bort behörigheter, till exempel när en anställd lämnar gruppen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-268">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="61d0f-269">För var och en av dessa uppgifter använder du Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61d0f-269">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="61d0f-270">Mer information om Azure PowerShell finns i [Översikt över Azure PowerShell](/powershell/azure/).</span><span class="sxs-lookup"><span data-stu-id="61d0f-270">For information about Azure PowerShell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="61d0f-271">Om du vill visa behörigheter för nyckelvalv kör du Get-AzKeyVault-cmdleten.</span><span class="sxs-lookup"><span data-stu-id="61d0f-271">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="61d0f-272">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="61d0f-272">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="61d0f-273">Om du vill ta bort en administratörs behörigheter kör du Remove-AzKeyVaultAccessPolicy cmdleten:</span><span class="sxs-lookup"><span data-stu-id="61d0f-273">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="61d0f-274">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="61d0f-274">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a><span data-ttu-id="61d0f-275">Återställ från kundnyckel till Microsoft-hanterade nycklar</span><span class="sxs-lookup"><span data-stu-id="61d0f-275">Roll back from Customer Key to Microsoft managed Keys</span></span>

<span data-ttu-id="61d0f-276">Om du behöver återgå till nycklar som hanteras av Microsoft kan du göra det.</span><span class="sxs-lookup"><span data-stu-id="61d0f-276">If you need to revert to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="61d0f-277">När du offboard krypteras dina data på samma sätt med standardkryptering som stöds av varje enskild arbetsbelastning.</span><span class="sxs-lookup"><span data-stu-id="61d0f-277">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="61d0f-278">Till exempel Exchange Online standardkryptering med microsoft-hanterade nycklar.</span><span class="sxs-lookup"><span data-stu-id="61d0f-278">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61d0f-279">Offboarding är inte samma sak som datarensning.</span><span class="sxs-lookup"><span data-stu-id="61d0f-279">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="61d0f-280">En data tar bort permanent crypto-deletes din organisations data från Microsoft 365, offboarding gör det inte.</span><span class="sxs-lookup"><span data-stu-id="61d0f-280">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="61d0f-281">Du kan inte rensa data för principen för flera arbetsbelastningar.</span><span class="sxs-lookup"><span data-stu-id="61d0f-281">You can't perform a data purge for a multiple workload policy.</span></span>

<span data-ttu-id="61d0f-282">Om du bestämmer dig för att inte använda kundnyckel för att tilldela dep-adresser för flera arbetsbelastningar längre, måste du kontakta Microsofts support med en förfrågan om att "offboard" från kundnyckel.</span><span class="sxs-lookup"><span data-stu-id="61d0f-282">If you decide not to use Customer Key for assigning multi-workload DEPs anymore then you'll need to reach out to Microsoft support with a request to “offboard” from Customer Key.</span></span> <span data-ttu-id="61d0f-283">Be supportteamet att skicka en servicebegäran mot Microsoft 365 teamet med kundnyckel.</span><span class="sxs-lookup"><span data-stu-id="61d0f-283">Ask the support team to file a service request against Microsoft 365 Customer Key team.</span></span> <span data-ttu-id="61d0f-284">Kontakta m365-ck@service.microsoft.com om du har frågor.</span><span class="sxs-lookup"><span data-stu-id="61d0f-284">Reach out to m365-ck@service.microsoft.com if you have any questions.</span></span>

<span data-ttu-id="61d0f-285">Om du inte längre vill kryptera enskilda postlådor med dep-adresser på postlådenivå kan du ta bort dep-adresser på postlådenivå från alla dina postlådor.</span><span class="sxs-lookup"><span data-stu-id="61d0f-285">If you do not want to encrypt individual mailboxes using mailbox level DEPs anymore, then you can unassign mailbox level DEPs from all your mailboxes.</span></span>

<span data-ttu-id="61d0f-286">Om du vill ta bort postlåde-DEP:er använder Set-Mailbox PowerShell-cmdleten.</span><span class="sxs-lookup"><span data-stu-id="61d0f-286">To unassign mailbox DEPs, use the Set-Mailbox PowerShell cmdlet.</span></span>

1. <span data-ttu-id="61d0f-287">Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation [och anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="61d0f-287">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="61d0f-288">Kör Set-Mailbox cmdlet.</span><span class="sxs-lookup"><span data-stu-id="61d0f-288">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

<span data-ttu-id="61d0f-289">När du kör den här cmdleten kopplas den tilldelade DEP:n bort och postlådan krypteras på nytt med den DEP som är kopplad till standardnycklar som hanteras av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="61d0f-289">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft-managed keys.</span></span> <span data-ttu-id="61d0f-290">Du kan inte ta bort dep som används av Microsoft-hanterade nycklar.</span><span class="sxs-lookup"><span data-stu-id="61d0f-290">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="61d0f-291">Om du inte vill använda microsoft-hanterade nycklar kan du tilldela en annan kundnyckel DEP till postlådan.</span><span class="sxs-lookup"><span data-stu-id="61d0f-291">If you don't want to use Microsoft-managed keys, you can assign another Customer Key DEP to the mailbox.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="61d0f-292">Återkalla dina nycklar och starta datarensningssökvägen</span><span class="sxs-lookup"><span data-stu-id="61d0f-292">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="61d0f-293">Du styr återkallelsen av alla rotnycklar, inklusive tillgänglighetsnyckeln.</span><span class="sxs-lookup"><span data-stu-id="61d0f-293">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="61d0f-294">Kundnyckel ger dig kontroll över olika aspekter av utgångsplaneringen av kraven på regler.</span><span class="sxs-lookup"><span data-stu-id="61d0f-294">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="61d0f-295">Om du bestämmer dig för att återkalla dina nycklar för att tömma data och avsluta tjänsten tar tjänsten bort tillgänglighetsnyckeln när datarensningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="61d0f-295">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span> <span data-ttu-id="61d0f-296">Detta stöds för kundnyckel-DEP som tilldelas till enskilda postlådor.</span><span class="sxs-lookup"><span data-stu-id="61d0f-296">This is supported for Customer Key DEPs that are assigned to individual mailboxes.</span></span>

<span data-ttu-id="61d0f-297">Microsoft 365 granskar och verifierar datarensningssökvägen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-297">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="61d0f-298">Mer information finns i SSAE 18 SOC 2-rapporten som finns på [Service Trust Portal](https://servicetrust.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="61d0f-298">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="61d0f-299">Dessutom rekommenderar Microsoft följande dokument:</span><span class="sxs-lookup"><span data-stu-id="61d0f-299">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="61d0f-300">Guide för riskbedömning och efterlevnad för finansiella institutioner i Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="61d0f-300">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="61d0f-301">Att tänka på när det gäller att avsluta planeringen i O365</span><span class="sxs-lookup"><span data-stu-id="61d0f-301">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="61d0f-302">Rensning av DEP för flera arbetsbelastningar stöds inte för Microsoft 365 kundnyckel.</span><span class="sxs-lookup"><span data-stu-id="61d0f-302">Purging of multi-workload DEP is not supported for Microsoft 365 Customer Key.</span></span> <span data-ttu-id="61d0f-303">Data i flera arbetsbelastningar används för att kryptera data över flera arbetsbelastningar för alla klientanvändare.</span><span class="sxs-lookup"><span data-stu-id="61d0f-303">The multi-workload DEP is used to encrypt data across multiple workloads across all tenant users.</span></span> <span data-ttu-id="61d0f-304">Att tömma en sådan DEP kunde resultera i data från flera arbetsbelastningar blir otillgängliga.</span><span class="sxs-lookup"><span data-stu-id="61d0f-304">Purging such DEP would result into data from across multiple workloads become inaccessible.</span></span> <span data-ttu-id="61d0f-305">Om du bestämmer dig för att Microsoft 365 tjänster helt och hållet skulle du kunna följa den väg där klientorganisationen tas bort genom den dokumenterade processen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-305">If you decide to exit Microsoft 365 services altogether then you could pursue the path of tenant deletion per the documented process.</span></span> <span data-ttu-id="61d0f-306">Se [hur du tar bort en klientorganisation i Azure Active Directoy.](/azure/active-directory/enterprise-users/directory-delete-howto)</span><span class="sxs-lookup"><span data-stu-id="61d0f-306">See [how to delete a tenant in Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="61d0f-307">Återkalla dina kundnycklar och tillgänglighetsnyckeln för Exchange Online och Skype för företag</span><span class="sxs-lookup"><span data-stu-id="61d0f-307">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="61d0f-308">När du initierar datarensningssökvägen för Exchange Online och Skype för företag kan du ange en permanent begäran om datarensning för en DEP.</span><span class="sxs-lookup"><span data-stu-id="61d0f-308">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="61d0f-309">Om du gör det tas krypterade data i postlådorna som deP har tilldelats permanent bort.</span><span class="sxs-lookup"><span data-stu-id="61d0f-309">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="61d0f-310">Eftersom du bara kan köra PowerShell-cmdleten mot en DEP i taget bör du överväga att tilldela en enda dep till alla dina postlådor innan du påbörjar datarensningssökvägen.</span><span class="sxs-lookup"><span data-stu-id="61d0f-310">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="61d0f-311">Använd inte datarensningssökvägen för att ta bort en delmängd av dina postlådor.</span><span class="sxs-lookup"><span data-stu-id="61d0f-311">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="61d0f-312">Den här processen är endast avsedd för kunder som avslutar tjänsten.</span><span class="sxs-lookup"><span data-stu-id="61d0f-312">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="61d0f-313">Så här påbörjar du datarensningen:</span><span class="sxs-lookup"><span data-stu-id="61d0f-313">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="61d0f-314">Ta bort radbytes- och borttagningsbehörigheter för "O365 Exchange Online" från Azure-nyckelvalv.</span><span class="sxs-lookup"><span data-stu-id="61d0f-314">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="61d0f-315">Använd ett arbets- eller skolkonto med global administratörsbehörighet i din organisation och [anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="61d0f-315">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="61d0f-316">För varje DEP som innehåller postlådor som du vill ta bort kör du cmdleten [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) enligt följande.</span><span class="sxs-lookup"><span data-stu-id="61d0f-316">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="61d0f-317">Om kommandot inte fungerar bör du kontrollera att du har tagit bort behörigheterna Exchange Online båda nycklarna i Azure Key Vault enligt tidigare i den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="61d0f-317">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="61d0f-318">När du har ställt in bytet PermanentDataPurgeRequested med cmdleten Set-DataEncryptionPolicy kan du inte längre tilldela den här DEP till postlådor.</span><span class="sxs-lookup"><span data-stu-id="61d0f-318"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="61d0f-319">Kontakta Microsofts support och begär Data Purge eDocument.</span><span class="sxs-lookup"><span data-stu-id="61d0f-319">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="61d0f-320">Microsoft skickar ett juridiskt dokument till dig på din begäran för att bekräfta och auktorisera databorttagning.</span><span class="sxs-lookup"><span data-stu-id="61d0f-320">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="61d0f-321">Den person i din organisation som registrerat sig som godkännare i FastTrack-erbjudandet under introduktionen måste signera dokumentet.</span><span class="sxs-lookup"><span data-stu-id="61d0f-321">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="61d0f-322">Normalt är det här en chef eller annan utsedd person i ditt företag som har en laglig behörighet att signera arbetet för din organisations räkning.</span><span class="sxs-lookup"><span data-stu-id="61d0f-322">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="61d0f-323">När din representant har signerat den juridiska dokumentet ska du skicka tillbaka den till Microsoft (vanligtvis via en eDoc-signatur).</span><span class="sxs-lookup"><span data-stu-id="61d0f-323">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="61d0f-324">När Microsoft har tagit emot det juridiska dokumentet kör Microsoft cmdlets för att starta datarensningen som först tar bort principen, markerar postlådorna för permanent borttagning och tar sedan bort tillgänglighetsnyckeln.</span><span class="sxs-lookup"><span data-stu-id="61d0f-324">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="61d0f-325">När datarensningen har slutförts har data rensats bort, är otillgängliga för Exchange Online och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="61d0f-325">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="61d0f-326">Återkalla dina kundnycklar och tillgänglighetsnyckeln för online SharePoint, OneDrive för företag och Teams filer</span><span class="sxs-lookup"><span data-stu-id="61d0f-326">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="61d0f-327">Så här påbörjar du datarensningen för SharePoint Online, OneDrive för företag och Teams genom att utföra följande steg:</span><span class="sxs-lookup"><span data-stu-id="61d0f-327">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="61d0f-328">Återkalla Azure-nyckelvalvsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="61d0f-328">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="61d0f-329">Alla nyckelvalvsadministratörer måste godkänna att återkalla åtkomsten.</span><span class="sxs-lookup"><span data-stu-id="61d0f-329">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="61d0f-330">Du tar inte bort Azure Key Vault för SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="61d0f-330">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="61d0f-331">Nyckelvalv kan delas mellan flera olika SharePoint Online-klientorganisation och DEP:er.</span><span class="sxs-lookup"><span data-stu-id="61d0f-331">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="61d0f-332">Kontakta Microsoft om du vill ta bort tillgänglighetsnyckeln.</span><span class="sxs-lookup"><span data-stu-id="61d0f-332">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="61d0f-333">När du kontaktar Microsoft för att ta bort tillgänglighetsnyckeln skickar vi ett juridiskt dokument till dig.</span><span class="sxs-lookup"><span data-stu-id="61d0f-333">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="61d0f-334">Den person i din organisation som registrerat sig som godkännare i FastTrack-erbjudandet under introduktionen måste signera dokumentet.</span><span class="sxs-lookup"><span data-stu-id="61d0f-334">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="61d0f-335">Normalt är det här en chef eller annan person i företaget som har en laglig behörighet att signera arbetet åt din organisation.</span><span class="sxs-lookup"><span data-stu-id="61d0f-335">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="61d0f-336">När din representant signerar det juridiska dokumentet bör du skicka tillbaka det till Microsoft (oftast via en eDoc-signatur).</span><span class="sxs-lookup"><span data-stu-id="61d0f-336">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="61d0f-337">När Microsoft får det juridiska dokumentet kör vi cmdlets för att utlösa datarensningen som utför kryptoborttagning av klientnyckeln, webbplatsnyckeln och alla enskilda nycklar per dokument, vilket oåterkalleligen bryter nyckelhierarkin.</span><span class="sxs-lookup"><span data-stu-id="61d0f-337">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="61d0f-338">När cmdletarna för datarensning är klara har dina data rensats bort.</span><span class="sxs-lookup"><span data-stu-id="61d0f-338">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="61d0f-339">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="61d0f-339">Related articles</span></span>

- [<span data-ttu-id="61d0f-340">Tjänst kryptering med kundnyckel</span><span class="sxs-lookup"><span data-stu-id="61d0f-340">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="61d0f-341">Läs mer om tillgänglighetsnyckeln</span><span class="sxs-lookup"><span data-stu-id="61d0f-341">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="61d0f-342">Konfigurera kundnyckel</span><span class="sxs-lookup"><span data-stu-id="61d0f-342">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="61d0f-343">Rulla eller rotera Customer Key eller en tillgänglighetsnyckel</span><span class="sxs-lookup"><span data-stu-id="61d0f-343">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="61d0f-344">Customer Lockbox</span><span class="sxs-lookup"><span data-stu-id="61d0f-344">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="61d0f-345">Tjänstkryptering</span><span class="sxs-lookup"><span data-stu-id="61d0f-345">Service Encryption</span></span>](office-365-service-encryption.md)