---
title: Federerade identiteter i testmiljön för Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: 'Sammanfattning: Konfigurera federerad autentisering för Microsoft 365-testmiljön.'
ms.openlocfilehash: 0fb8c55f5b7291cdc6bcec636981a9d31015e723
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487690"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="014ac-103">Federerade identiteter i testmiljön för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="014ac-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="014ac-104">*Den här testlabbguiden kan användas för både Microsoft 365 för företag Office 365 Enterprise för testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="014ac-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="014ac-105">Microsoft 365 stöder federerade identiteter.</span><span class="sxs-lookup"><span data-stu-id="014ac-105">Microsoft 365 supports federated identity.</span></span> <span data-ttu-id="014ac-106">Det innebär att i stället för att Microsoft 365 validerar autentiseringsuppgifterna själv, hänvisas användaren som ansluter till en federerad autentiseringsserver som är betrodd av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="014ac-106">This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts.</span></span> <span data-ttu-id="014ac-107">Om användarens autentiseringsuppgifter är korrekta utfärdar den federerade autentiseringsservern en säkerhetstoken som klienten sedan skickar till Microsoft 365 som autentiseringsbevis.</span><span class="sxs-lookup"><span data-stu-id="014ac-107">If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication.</span></span> <span data-ttu-id="014ac-108">Federerade identiteter möjliggör avlastning och uppskalning av autentiseringen i en Microsoft 365-prenumeration, samt avancerade autentiserings- och säkerhetsscenarier.</span><span class="sxs-lookup"><span data-stu-id="014ac-108">Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="014ac-109">I den här artikeln beskrivs hur du konfigurerar federerad autentisering för Microsoft 365 testmiljö, vilket resulterar i följande:</span><span class="sxs-lookup"><span data-stu-id="014ac-109">This article describes how to configure federated authentication for your Microsoft 365 test environment, resulting in the following:</span></span>

![Den federerade autentiseringen för Microsoft 365-testmiljön](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="014ac-111">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="014ac-111">This configuration consists of:</span></span>
  
- <span data-ttu-id="014ac-112">En Microsoft 365 E5 provprenumeration eller produktionsprenumeration.</span><span class="sxs-lookup"><span data-stu-id="014ac-112">A Microsoft 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="014ac-113">Ett förenklat organisationsintranät som är anslutet till internet och består av fem virtuella datorer på ett undernät till ett virtuellt Azure-nätverk (DC1, APP1, CLIENT1, ADFS1 och PROXY1).</span><span class="sxs-lookup"><span data-stu-id="014ac-113">A simplified organization intranet connected to the internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1).</span></span> <span data-ttu-id="014ac-114">Azure AD Anslut på APP1 för att synkronisera listan över konton i Active Directory Domain Services-domänen till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="014ac-114">Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Microsoft 365.</span></span> <span data-ttu-id="014ac-115">PROXY1 tar emot inkommande autentiseringsbegäranden.</span><span class="sxs-lookup"><span data-stu-id="014ac-115">PROXY1 receives the incoming authentication requests.</span></span> <span data-ttu-id="014ac-116">ADFS1 validerar autentiseringsuppgifter med DC1 och utfärdar säkerhetstoken.</span><span class="sxs-lookup"><span data-stu-id="014ac-116">ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="014ac-117">För inställning av den här testmiljön ingår fem faser:</span><span class="sxs-lookup"><span data-stu-id="014ac-117">Setting up this test environment involves five phases:</span></span>
- [<span data-ttu-id="014ac-118">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="014ac-118">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="014ac-119">Fas 2: Skapa AD FS-servern</span><span class="sxs-lookup"><span data-stu-id="014ac-119">Phase 2: Create the AD FS server</span></span>](#phase-2-create-the-ad-fs-server)
- [<span data-ttu-id="014ac-120">Fas 3: Skapa webbproxyservern</span><span class="sxs-lookup"><span data-stu-id="014ac-120">Phase 3: Create the web proxy server</span></span>](#phase-3-create-the-web-proxy-server)
- [<span data-ttu-id="014ac-121">Fas 4: Skapa ett självsignerat certifikat och konfigurera ADFS1 och PROXY1.</span><span class="sxs-lookup"><span data-stu-id="014ac-121">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [<span data-ttu-id="014ac-122">Fas 5: Konfigurera Microsoft 365 för federerade identiteter</span><span class="sxs-lookup"><span data-stu-id="014ac-122">Phase 5: Configure Microsoft 365 for federated identity</span></span>](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> <span data-ttu-id="014ac-123">Du kan inte konfigurera den här testmiljön med en prenumeration på utvärderingsversionen av Azure.</span><span class="sxs-lookup"><span data-stu-id="014ac-123">You can't configure this test environment with an Azure Trial subscription.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="014ac-124">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="014ac-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="014ac-125">Följ anvisningarna i [synkronisering av lösenordshash för Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="014ac-125">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="014ac-126">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="014ac-126">Your resulting configuration looks like this:</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="014ac-128">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="014ac-128">This configuration consists of:</span></span>
  
- <span data-ttu-id="014ac-129">En Microsoft 365 E5 utvärderingsversion eller betalda prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="014ac-129">A Microsoft 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="014ac-130">Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="014ac-130">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="014ac-131">Azure AD Anslut körs på APP1 för att synkronisera AD DS-domänen (TESTLAB Active Directory Domain Services) med Azure AD-klientorganisationen för dina Microsoft 365-prenumerationer med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="014ac-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="014ac-132">Fas 2: Skapa AD FS-servern</span><span class="sxs-lookup"><span data-stu-id="014ac-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="014ac-133">En AD FS-server tillhandahåller federerad autentisering mellan Microsoft 365 och kontona på domänen corp.contoso.com som finns i DC1.</span><span class="sxs-lookup"><span data-stu-id="014ac-133">An AD FS server provides federated authentication between Microsoft 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="014ac-134">Om du vill skapa en virtuell Azure-dator för ADFS1, fyller du i namnet på prenumerationen, resursgruppen och Azure-platsen för baskonfigurationen. Kör sedan dessa kommandon i Azure PowerShell-kommandotolken på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="014ac-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="014ac-135">Använd sedan [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella ADFS1-datorn med det lokala administratörskontonamnet och lösenordet för ADFS1 och öppna en kommandotolk i Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="014ac-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="014ac-136">Om du vill kontrollera namnmatchningen och nätverkskommunikationen mellan ADFS1 och DC1, kör du kommandot **ping dc1.corp.contoso.com** och kontrollerar att det finns fyra svar.</span><span class="sxs-lookup"><span data-stu-id="014ac-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="014ac-137">Anslut sedan den virtuella ADFS1-datorn till CORP-domänen med dessa kommandon i Windows PowerShell-kommandotolken på ADFS1.</span><span class="sxs-lookup"><span data-stu-id="014ac-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="014ac-138">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="014ac-138">Your resulting configuration looks like this:</span></span>
  
![AD FS-servern har lagts till i DirSync för Microsoft 365-testmiljön](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="014ac-140">Fas 3: Skapa webbproxyservern</span><span class="sxs-lookup"><span data-stu-id="014ac-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="014ac-141">Med PROXY1 kan du använda proxy till autentiseringsmeddelanden mellan användare som försöker autentisera och ADFS1.</span><span class="sxs-lookup"><span data-stu-id="014ac-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="014ac-142">Om du vill skapa en virtuell Azure-dator för PROXY1 fyller du i namnet på din resursgrupp och Azure-plats och kör dessa kommandon i Azure PowerShell-kommandotolken på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="014ac-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="014ac-143">PROXY1 tilldelas en statisk offentlig IP-adress eftersom du skapar en offentlig DNS-post som pekar på den. Denna får inte ändras när du startar om den virtuella PROXY1-datorn.</span><span class="sxs-lookup"><span data-stu-id="014ac-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span>
  
<span data-ttu-id="014ac-144">Lägg sedan till en regel i nätverkssäkerhetsgruppen för CorpNet-undernätet för att tillåta oombedd inkommande trafik från internet till PROXY1s privata IP-adress och TCP-port 443.</span><span class="sxs-lookup"><span data-stu-id="014ac-144">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the internet to PROXY1's private IP address and TCP port 443.</span></span> <span data-ttu-id="014ac-145">Kör dessa kommandon i Azure PowerShell-kommandotolken på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="014ac-145">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="014ac-146">Använd sedan [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella PROXY1-datorn med det lokala administratörskontonamnet och lösenordet för PROXY1 och öppna en kommandotolk i Windows PowerShell för PROXY1.</span><span class="sxs-lookup"><span data-stu-id="014ac-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="014ac-147">Om du vill kontrollera namnmatchningen och nätverkskommunikationen mellan PROXY1 och DC1, kör du kommandot **ping dc1.corp.contoso.com** och kontrollerar att det finns fyra svar.</span><span class="sxs-lookup"><span data-stu-id="014ac-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="014ac-148">Anslut sedan den virtuella PROXY1-datorn till CORP-domänen med dessa kommandon i Windows PowerShell-kommandotolken på PROXY1.</span><span class="sxs-lookup"><span data-stu-id="014ac-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="014ac-149">Visa den offentliga IP-adressen för PROXY1 med dessa Azure PowerShell kommandon på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="014ac-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer.</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="014ac-150">Arbeta sedan med din offentliga DNS-leverantör och skapa en ny offentlig DNS A-post för **fs.testlab.**\<*your DNS domain name*></span><span class="sxs-lookup"><span data-stu-id="014ac-150">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<*your DNS domain name*></span></span> <span data-ttu-id="014ac-151">det löser att IP-adressen visas av kommandot **Write-Host**.</span><span class="sxs-lookup"><span data-stu-id="014ac-151">that resolves to the IP address displayed by the **Write-Host** command.</span></span> <span data-ttu-id="014ac-152">**fs.testlab.**\<*your DNS domain name*></span><span class="sxs-lookup"><span data-stu-id="014ac-152">The **fs.testlab.**\<*your DNS domain name*></span></span> <span data-ttu-id="014ac-153">kallas i fortsättningen för *federationstjänstens FQDN*.</span><span class="sxs-lookup"><span data-stu-id="014ac-153">is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="014ac-154">Använd sedan [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella DC1-datorn med hjälp av CORP\\User1-autentiseringsuppgifter och kör följande kommandon i en Windows PowerShell-kommandotolk på administratörsnivå:</span><span class="sxs-lookup"><span data-stu-id="014ac-154">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="014ac-155">Dessa kommandon skapar en intern DNS A-post så att virtuella datorer i det virtuella Azure-nätverket kan lösa den interna federationstjänstens FQDN till ADFS1s privata IP-adress.</span><span class="sxs-lookup"><span data-stu-id="014ac-155">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation service FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="014ac-156">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="014ac-156">Your resulting configuration looks like this:</span></span>
  
![Webbprogrammets proxyserver har lagts till i DirSync för Microsoft 365-testmiljön](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="014ac-158">Fas 4: Skapa ett självsignerat certifikat och konfigurera ADFS1 och PROXY1.</span><span class="sxs-lookup"><span data-stu-id="014ac-158">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="014ac-159">I den här fasen skapar du ett självsignerat digitalt certifikat för federationstjänstens FQDN. Därefter konfigurerar du ADFS1 och PROXY1 som en AD FS-servergrupp.</span><span class="sxs-lookup"><span data-stu-id="014ac-159">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="014ac-160">Först använder du [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella DC1-datorn med hjälp av CORP\\User1-autentiseringsuppgifterna och sedan öppnar du en Windows PowerShell-kommandotolk på administratörsnivå.</span><span class="sxs-lookup"><span data-stu-id="014ac-160">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="014ac-161">Skapa sedan ett AD FS-tjänstkonto med det här kommandot Windows PowerShell kommandotolken i DC1:</span><span class="sxs-lookup"><span data-stu-id="014ac-161">Next, create an AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="014ac-162">Observera att du uppmanas att ange lösenordet för kontot med detta kommando.</span><span class="sxs-lookup"><span data-stu-id="014ac-162">Note that this command prompts you to supply the account password.</span></span> <span data-ttu-id="014ac-163">Välj ett starkt lösenord och spara det på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="014ac-163">Choose a strong password and record it in a secured location.</span></span> <span data-ttu-id="014ac-164">Du behöver den för den här fasen och för fas 5.</span><span class="sxs-lookup"><span data-stu-id="014ac-164">You will need it for this phase and for Phase 5.</span></span>
  
<span data-ttu-id="014ac-165">Använd [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella ADFS1-datorn med hjälp av CORP\\User1-autentiseringsuppgifterna.</span><span class="sxs-lookup"><span data-stu-id="014ac-165">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials.</span></span> <span data-ttu-id="014ac-166">Öppna en Windows PowerShell-kommandotolk på administratörsnivå i ADFS1, fyll i FQDN för federationstjänsten och kör sedan följande kommandon för att skapa ett självsignerat certifikat:</span><span class="sxs-lookup"><span data-stu-id="014ac-166">Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="014ac-167">Följ sedan de här anvisningarna för att spara det nya självsignerade certifikatet som en fil.</span><span class="sxs-lookup"><span data-stu-id="014ac-167">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="014ac-168">Välj **Start**, **mmc.exe** och tryck sedan på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="014ac-168">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="014ac-169">Välj **Lägg**  >  **till/ta Fästa tillägg.**</span><span class="sxs-lookup"><span data-stu-id="014ac-169">Select **File** > **Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="014ac-170">In **Add or Remove Fästa-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="014ac-170">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="014ac-171">I **Välj dator** väljer du **Slutför** och sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="014ac-171">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="014ac-172">Öppna **Certifikat (lokal dator) > Personlig > Certifikat** i mapplistan.</span><span class="sxs-lookup"><span data-stu-id="014ac-172">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="014ac-173">Välj och håll ned (eller högerklicka på) certifikatet med din FQDN för federationstjänsten, välj **Alla** uppgifter och välj sedan **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="014ac-173">Select and hold (or right-click) the certificate with your federation service FQDN, select **All tasks**, and then select **Export**.</span></span>
    
7. <span data-ttu-id="014ac-174">På **välkomstsidan** väljer du **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-174">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="014ac-175">På sidan **Exportera privat** nyckel väljer du **Ja** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-175">On the **Export Private Key** page, select **Yes**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="014ac-176">På sidan **Exportera filformat väljer** du Exportera alla utökade **egenskaper** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-176">On the **Export File Format** page, select **Export all extended properties**, and then select **Next**.</span></span>
    
10. <span data-ttu-id="014ac-177">På sidan **Säkerhet** väljer du **Lösenord och** anger ett lösenord i **Lösenord** och **Bekräfta lösenord.**</span><span class="sxs-lookup"><span data-stu-id="014ac-177">On the **Security** page, select **Password** and enter a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="014ac-178">På sidan **Fil som ska exporteras** väljer du **Bläddra**.</span><span class="sxs-lookup"><span data-stu-id="014ac-178">On the **File to Export** page, select **Browse**.</span></span>
    
12. <span data-ttu-id="014ac-179">Bläddra till **mappen C: \\ Certs,** ange **SSL** **i filnamn** och välj sedan **Spara.**</span><span class="sxs-lookup"><span data-stu-id="014ac-179">Browse to the **C:\\Certs** folder, enter **SSL** in **File name**, and then select **Save.**</span></span>
    
13. <span data-ttu-id="014ac-180">Välj **Nästa på sidan** Fil som ska **exporteras.**</span><span class="sxs-lookup"><span data-stu-id="014ac-180">On the **File to Export** page, select **Next**.</span></span>
    
14. <span data-ttu-id="014ac-181">På sidan **Slutför guiden Exportera certifikat** väljer du **Slutför.**</span><span class="sxs-lookup"><span data-stu-id="014ac-181">On the **Completing the Certificate Export Wizard** page, select **Finish**.</span></span> <span data-ttu-id="014ac-182">Välj OK när du **uppmanas att göra det.**</span><span class="sxs-lookup"><span data-stu-id="014ac-182">When prompted, select **OK**.</span></span>
    
<span data-ttu-id="014ac-183">Installera sedan AD FS-tjänsten med detta kommando i Windows PowerShell-kommandotolken på ADFS1:</span><span class="sxs-lookup"><span data-stu-id="014ac-183">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="014ac-184">Vänta på att installationen slutförs.</span><span class="sxs-lookup"><span data-stu-id="014ac-184">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="014ac-185">Konfigurera sedan AD FS-tjänsten med följande steg:</span><span class="sxs-lookup"><span data-stu-id="014ac-185">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="014ac-186">Välj **Start** och sedan **serverhanterarens** ikon.</span><span class="sxs-lookup"><span data-stu-id="014ac-186">Select **Start**, and then select the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="014ac-187">I trädfönstret i Serverhanteraren väljer du **AD FS**.</span><span class="sxs-lookup"><span data-stu-id="014ac-187">In the tree pane of Server Manager, select **AD FS**.</span></span>
    
3. <span data-ttu-id="014ac-188">Välj den orange varningssymbolen i verktygsfältet högst upp och välj sedan **Konfigurera federationstjänsten på den här servern**.</span><span class="sxs-lookup"><span data-stu-id="014ac-188">In the tool bar at the top, select the orange caution symbol, and then select **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="014ac-189">På **välkomstsidan** i konfigurationsguiden Active Directory Federation Services väljer du **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-189">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="014ac-190">På sidan **Anslut till AD DS** väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="014ac-190">On the **Connect to AD DS** page, select **Next**.</span></span>
    
6. <span data-ttu-id="014ac-191">På sidan **Ange egenskaper för tjänst**:</span><span class="sxs-lookup"><span data-stu-id="014ac-191">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="014ac-192">För **SSL-certifikat** väljer du nedpilen och sedan certifikatet med namnet på din federationstjänsts FQDN.</span><span class="sxs-lookup"><span data-stu-id="014ac-192">For **SSL Certificate**, select the down arrow, and then select the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="014ac-193">I **Visningsnamn för federationstjänsten** anger du namnet på din fiktiva organisation.</span><span class="sxs-lookup"><span data-stu-id="014ac-193">In **Federation Service Display Name**, enter the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="014ac-194">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="014ac-194">Select **Next**.</span></span>
    
7. <span data-ttu-id="014ac-195">På sidan **Ange tjänstkonto** väljer du **Välj** för **kontonamn.**</span><span class="sxs-lookup"><span data-stu-id="014ac-195">On the **Specify Service Account** page, select **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="014ac-196">I **Välj användarkonto eller tjänstkonto** anger du **ADFS-Service**, väljer **Kontrollera** namn och väljer sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="014ac-196">In **Select User or Service Account**, enter **ADFS-Service**, select **Check Names**, and then select **OK**.</span></span>
    
9. <span data-ttu-id="014ac-197">I **Kontolösenord** anger du lösenordet för ADFS-Service och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="014ac-197">In **Account Password**, enter the password for the ADFS-Service account, and then select **Next**.</span></span>
    
10. <span data-ttu-id="014ac-198">På sidan **Ange konfigurationsdatabas** väljer du **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-198">On the **Specify Configuration Database** page, select **Next**.</span></span>
    
11. <span data-ttu-id="014ac-199">På sidan **Granskningsalternativ** väljer du **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-199">On the **Review Options** page, select **Next**.</span></span>
    
12. <span data-ttu-id="014ac-200">På sidan **Kontroller som krävs** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="014ac-200">On the **Pre-requisite Checks** page, select **Configure**.</span></span>

13. <span data-ttu-id="014ac-201">På sidan **Resultat** väljer du **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="014ac-201">On the **Results** page, select **Close**.</span></span>
    
14. <span data-ttu-id="014ac-202">Välj **Start**, välj strömikonen, välj **Starta om** och välj sedan **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="014ac-202">Select **Start**, select the power icon, select **Restart**, and then select **Continue**.</span></span>
    
<span data-ttu-id="014ac-203">I [Azure-portalen](https://portal.azure.com) kan du ansluta till PROXY1 med autentiseringsuppgifterna för CORP\\User1-kontot.</span><span class="sxs-lookup"><span data-stu-id="014ac-203">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="014ac-204">Följ sedan de här anvisningarna för att installera det självsignerade certifikatet på **både PROXY1 och APP1**.</span><span class="sxs-lookup"><span data-stu-id="014ac-204">Next, use these steps to install the self-signed certificate on **both PROXY1 and APP1**.</span></span>
  
1. <span data-ttu-id="014ac-205">Välj **Start**, **mmc.exe** och tryck sedan på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="014ac-205">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="014ac-206">Välj **Arkiv > Lägg till/Fästa tillägg.**</span><span class="sxs-lookup"><span data-stu-id="014ac-206">Select **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="014ac-207">In **Add or Remove Fästa-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="014ac-207">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="014ac-208">I **Välj dator** väljer du **Slutför** och sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="014ac-208">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="014ac-209">Öppna Personliga certifikat för **certifikat (lokal dator) i**  >    >  **trädfönstret.**</span><span class="sxs-lookup"><span data-stu-id="014ac-209">In the tree pane, open **Certificates (Local Computer)** > **Personal** > **Certificates**.</span></span>
    
6. <span data-ttu-id="014ac-210">Markera och håll ned (eller högerklicka på) **Personlig**, välj **Alla uppgifter** och välj sedan **Importera**.</span><span class="sxs-lookup"><span data-stu-id="014ac-210">Select and hold (or right-click) **Personal**, select **All tasks**, and then select **Import**.</span></span>
    
7. <span data-ttu-id="014ac-211">På **välkomstsidan** väljer du **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-211">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="014ac-212">På sidan **Fil för import** anger du **\\ \\ adfs1-certs \\ \\ ssl.pfx** och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="014ac-212">On the **File to Import** page, enter **\\\\adfs1\\certs\\ssl.pfx**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="014ac-213">På sidan **Private key protection** anger du certifikatlösenordet i **Lösenord** och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-213">On the **Private key protection** page, enter the certificate password in **Password**, and then select **Next.**</span></span>
    
10. <span data-ttu-id="014ac-214">På sidan **Certificate store** väljer du **Next.**</span><span class="sxs-lookup"><span data-stu-id="014ac-214">On the **Certificate store** page, select **Next.**</span></span>
    
11. <span data-ttu-id="014ac-215">På sidan **Slutför** väljer du **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="014ac-215">On the **Completing** page, select **Finish**.</span></span>
    
12. <span data-ttu-id="014ac-216">På sidan **Certificate Store** väljer du **Next**.</span><span class="sxs-lookup"><span data-stu-id="014ac-216">On the **Certificate Store** page, select **Next**.</span></span>
    
13. <span data-ttu-id="014ac-217">Välj OK när du **uppmanas att göra det.**</span><span class="sxs-lookup"><span data-stu-id="014ac-217">When prompted, select **OK**.</span></span>
    
14. <span data-ttu-id="014ac-218">Välj Certifikat i **trädfönstret.**</span><span class="sxs-lookup"><span data-stu-id="014ac-218">In the tree pane, select **Certificates**.</span></span>
    
15. <span data-ttu-id="014ac-219">Välj och håll ned (eller högerklicka på) certifikatet och välj sedan **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="014ac-219">Select and hold (or right-click) the certificate, and then select **Copy**.</span></span>
    
16. <span data-ttu-id="014ac-220">I trädfönstret öppnar du **Betrodda certifikat för rotcertifikatutfärdare.**  >  </span><span class="sxs-lookup"><span data-stu-id="014ac-220">In the tree pane, open **Trusted Root Certification Authorities** > **Certificates**.</span></span>
    
17. <span data-ttu-id="014ac-221">Flytta muspekaren nedanför listan med installerade certifikat, markera och håll ned (eller högerklicka) och välj sedan Klistra **in**.</span><span class="sxs-lookup"><span data-stu-id="014ac-221">Move your mouse pointer below the list of installed certificates, select and hold (or right-click), and then select **Paste**.</span></span>
    
<span data-ttu-id="014ac-222">Öppna en PowerShell-kommandotolk på administratörsnivå och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="014ac-222">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="014ac-223">Vänta på att installationen slutförs.</span><span class="sxs-lookup"><span data-stu-id="014ac-223">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="014ac-224">Använd följande steg för att konfigurera att tjänsten Webbprogramproxy ska använda ADFS1 som federationsserver:</span><span class="sxs-lookup"><span data-stu-id="014ac-224">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="014ac-225">Välj **Start** och sedan **Serverhanteraren.**</span><span class="sxs-lookup"><span data-stu-id="014ac-225">Select **Start**, and then select **Server Manager**.</span></span>
    
2. <span data-ttu-id="014ac-226">Välj Fjärråtkomst i **trädfönstret.**</span><span class="sxs-lookup"><span data-stu-id="014ac-226">In the tree pane, select **Remote Access**.</span></span>
    
3. <span data-ttu-id="014ac-227">Välj den orange varningssymbolen i verktygsfältet högst upp och välj sedan **Öppna proxyguiden för webbprogram.**</span><span class="sxs-lookup"><span data-stu-id="014ac-227">In the tool bar at the top, select the orange caution symbol, and then select **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="014ac-228">På **välkomstsidan** i konfigurationsguiden Proxykonfiguration för webbprogram väljer du **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-228">On the **Welcome** page of the Web Application Proxy Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="014ac-229">På sidan **Federationsserver**:</span><span class="sxs-lookup"><span data-stu-id="014ac-229">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="014ac-230">I rutan **Federationstjänstnamn** anger du FQDN för federationstjänsten.</span><span class="sxs-lookup"><span data-stu-id="014ac-230">In the **Federation service name** box, enter your federation service FQDN.</span></span>
    
  - <span data-ttu-id="014ac-231">I rutan **Användarnamn anger** du **CORP \\ Användare1**.</span><span class="sxs-lookup"><span data-stu-id="014ac-231">In the **User name** box, enter **CORP\\User1**.</span></span>
    
  - <span data-ttu-id="014ac-232">I rutan **Lösenord** anger du lösenordet för User1-kontot.</span><span class="sxs-lookup"><span data-stu-id="014ac-232">In the **Password** box, enter the password for the User1 account.</span></span>
    
  - <span data-ttu-id="014ac-233">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="014ac-233">Select **Next**.</span></span>
    
6. <span data-ttu-id="014ac-234">På sidan **AD FS-proxycertifikat** väljer du nedåtpilen, väljer certifikatet med federationstjänstens FQDN och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-234">On the **AD FS Proxy Certificate** page, select the down arrow, select the certificate with your federation service FQDN, and then select **Next**.</span></span>
    
7. <span data-ttu-id="014ac-235">På **bekräftelsesidan** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="014ac-235">On the **Confirmation** page, select **Configure**.</span></span>
    
8. <span data-ttu-id="014ac-236">På sidan **Resultat** väljer du **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="014ac-236">On the **Results** page, select **Close**.</span></span>
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a><span data-ttu-id="014ac-237">Fas 5: Konfigurera Microsoft 365 för federerade identiteter</span><span class="sxs-lookup"><span data-stu-id="014ac-237">Phase 5: Configure Microsoft 365 for federated identity</span></span>

<span data-ttu-id="014ac-238">Använd [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella APP1-datorn med hjälp av CORP\\User1-autentiseringsuppgifterna.</span><span class="sxs-lookup"><span data-stu-id="014ac-238">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="014ac-239">Använd följande steg för att konfigurera Azure AD Connect och din Microsoft 365-prenumeration för federerad autentisering:</span><span class="sxs-lookup"><span data-stu-id="014ac-239">Use these steps to configure Azure AD Connect and your Microsoft 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="014ac-240">Dubbelklicka på **Azure AD Connect** på skrivbordet.</span><span class="sxs-lookup"><span data-stu-id="014ac-240">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="014ac-241">På sidan **Välkommen till Azure AD Anslut** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="014ac-241">On the **Welcome to Azure AD Connect** page, select **Configure**.</span></span>
    
3. <span data-ttu-id="014ac-242">På sidan **Ytterligare uppgifter** väljer du Ändra inloggning **för användare** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-242">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="014ac-243">På sidan **Anslut till Azure AD** anger du namnet och lösenordet för ditt globala administratörskonto och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-243">On the **Connect to Azure AD** page, enter your global administrator account name and password, and then select **Next**.</span></span>
    
5. <span data-ttu-id="014ac-244">På **inloggningssidan för användaren** väljer du **Federation med AD FS** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-244">On the **User sign-in** page, select **Federation with AD FS**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="014ac-245">På **sidan AD FS-servergruppen** väljer du Använd en befintlig **AD FS-servergrupp**, anger **ADFS1** i rutan **Servernamn** och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-245">On the **AD FS farm** page, select **Use an existing AD FS farm**, enter **ADFS1** in the **Server Name** box, and then select **Next**.</span></span>
    
7. <span data-ttu-id="014ac-246">När du uppmanas att ange serverautentiseringsuppgifter anger du autentiseringsuppgifterna för CORP \\ User1-kontot och väljer sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="014ac-246">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then select **OK**.</span></span>
    
8. <span data-ttu-id="014ac-247">På sidan **Autentiseringsuppgifter för** domänadministratör anger  du **CORP \\ User1** i  rutan Användarnamn, anger lösenordet för kontot i rutan Lösenord och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-247">On the **Domain Administrator** credentials page, enter **CORP\\User1** in the **Username** box, enter the account password in the **Password** box, and then select **Next**.</span></span>
    
9. <span data-ttu-id="014ac-248">På sidan AD **FS-tjänstkonto** anger du **CORP \\ ADFS-Service** i rutan  **Domain Username,** anger lösenordet för kontot i rutan Domänanvändarlösenord och väljer **sedan Nästa**.</span><span class="sxs-lookup"><span data-stu-id="014ac-248">On the **AD FS service account** page, enter **CORP\\ADFS-Service** in the **Domain Username** box, enter the account password in the **Domain User Password** box, and then select **Next**.</span></span>
    
10. <span data-ttu-id="014ac-249">På sidan **Azure AD Domain,** i **Domain**, väljer du namnet på den domän som du tidigare skapade och lade till i din prenumeration i fas 1, och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="014ac-249">On the **Azure AD Domain** page, in **Domain**, select the name of the domain that you previously created and added to your subscription in Phase 1, and then select **Next**.</span></span>
    
11. <span data-ttu-id="014ac-250">På sidan **Är redo att konfigurera** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="014ac-250">On the **Ready to configure** page, select **Configure**.</span></span>
    
12. <span data-ttu-id="014ac-251">På sidan **Installationen är** klar väljer du **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="014ac-251">On the **Installation complete** page, select **Verify**.</span></span>
    
    <span data-ttu-id="014ac-252">Du bör se meddelanden som anger att både intranätet och Internetkonfigurationen har verifierats.</span><span class="sxs-lookup"><span data-stu-id="014ac-252">You should see messages indicating that both the intranet and internet configuration was verified.</span></span>
    
13. <span data-ttu-id="014ac-253">På sidan **Installationen är klar** väljer du **Avsluta.**</span><span class="sxs-lookup"><span data-stu-id="014ac-253">On the **Installation complete** page, select **Exit**.</span></span>
    
<span data-ttu-id="014ac-254">Visa att den federerade autentiseringen fungerar:</span><span class="sxs-lookup"><span data-stu-id="014ac-254">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="014ac-255">Öppna en ny privat instans av webbläsaren på din lokala dator och gå till [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="014ac-255">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="014ac-256">För inloggningsuppgifterna anger du **user1@** \<*the domain created in Phase 1*> .</span><span class="sxs-lookup"><span data-stu-id="014ac-256">For the sign-in credentials, enter **user1@**\<*the domain created in Phase 1*>.</span></span>
    
    <span data-ttu-id="014ac-257">Om testdomänen till exempel **är testlab.contoso.com** anger du "user1@testlab.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="014ac-257">For example, if your test domain is **testlab.contoso.com**, you would enter "user1@testlab.contoso.com".</span></span> <span data-ttu-id="014ac-258">Tryck på **Tabb eller** tillåt Microsoft 365 omdirigera dig automatiskt.</span><span class="sxs-lookup"><span data-stu-id="014ac-258">Press the **Tab** key or allow Microsoft 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="014ac-259">Nu bör du se sidan **Din anslutning är inte privat**.</span><span class="sxs-lookup"><span data-stu-id="014ac-259">You should now see a **Your connection is not private** page.</span></span> <span data-ttu-id="014ac-260">Du ser detta eftersom du har installerat ett själv signerat certifikat på ADFS1 som den stationära datorn inte kan verifiera.</span><span class="sxs-lookup"><span data-stu-id="014ac-260">You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer can't validate.</span></span> <span data-ttu-id="014ac-261">I en produktionsdistribution av federerad autentisering använder du ett certifikat från en betrodd certifikatutfärdare för att dina användare inte ska se den här sidan.</span><span class="sxs-lookup"><span data-stu-id="014ac-261">In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="014ac-262">På sidan **Din anslutning är inte privat** väljer du **Avancerat** och sedan **Fortsätt till \<*your federation service FQDN*>**.</span><span class="sxs-lookup"><span data-stu-id="014ac-262">On the **Your connection is not private** page, select **Advanced**, and then select **Proceed to \<*your federation service FQDN*>**.</span></span> 
    
4. <span data-ttu-id="014ac-263">Logga in med följande på sidan med namnet på din fiktiva organisation:</span><span class="sxs-lookup"><span data-stu-id="014ac-263">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="014ac-264">**CORP\\User1** som namn</span><span class="sxs-lookup"><span data-stu-id="014ac-264">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="014ac-265">Lösenordet för User1-kontot</span><span class="sxs-lookup"><span data-stu-id="014ac-265">The password for the User1 account</span></span>
    
    <span data-ttu-id="014ac-266">Du bör se **startsidan för Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="014ac-266">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="014ac-267">Proceduren visar att utvärderingsprenumerationen är federerad med AD DS corp.contoso.com-domänen som finns i DC1.</span><span class="sxs-lookup"><span data-stu-id="014ac-267">This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1.</span></span> <span data-ttu-id="014ac-268">Här följer grundläggande information om autentiseringsprocessen:</span><span class="sxs-lookup"><span data-stu-id="014ac-268">Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="014ac-269">När du använder den federerade domänen som du skapade i fas 1 i namnet på inloggningskontot, dirigerar Microsoft 365 webbläsaren till federationstjänstens FQDN och PROXY1.</span><span class="sxs-lookup"><span data-stu-id="014ac-269">When you use the federated domain that you created in Phase 1 within the sign-in account name, Microsoft 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="014ac-270">PROXY1 skickar din lokala dator till inloggningssidan för det fiktiva företaget.</span><span class="sxs-lookup"><span data-stu-id="014ac-270">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="014ac-271">När du skickar CORP\\User1 och lösenordet till PROXY1, vidarebefordras det till ADFS1.</span><span class="sxs-lookup"><span data-stu-id="014ac-271">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="014ac-272">ADFS1 validerar CORP\\User1 och lösenordet med DC1 och skickar en säkerhetstoken till din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="014ac-272">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="014ac-273">Din lokala dator skickar säkerhetstoken till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="014ac-273">Your local computer sends the security token to Microsoft 365.</span></span>
    
6. <span data-ttu-id="014ac-274">Microsoft 365 kontrollerar att denna säkerhetstoken har skapats av ADFS1 och tillåter åtkomst.</span><span class="sxs-lookup"><span data-stu-id="014ac-274">Microsoft 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="014ac-275">Utvärderingsprenumerationen har nu konfigurerats med federerad autentisering.</span><span class="sxs-lookup"><span data-stu-id="014ac-275">Your trial subscription is now configured with federated authentication.</span></span> <span data-ttu-id="014ac-276">Du kan använda den här utvecklings-/testmiljön för avancerade autentiseringsscenarier.</span><span class="sxs-lookup"><span data-stu-id="014ac-276">You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="014ac-277">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="014ac-277">Next step</span></span>

<span data-ttu-id="014ac-278">När du är redo att distribuera produktionsklar, federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure kan du gå till Distribuera [federerad](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)och Microsoft 365 hög tillgänglighet i Azure.</span><span class="sxs-lookup"><span data-stu-id="014ac-278">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 in Azure, see [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span></span>
  
