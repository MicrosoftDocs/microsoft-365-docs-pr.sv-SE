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
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a7997-103">Federerade identiteter i testmiljön för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a7997-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a7997-104">*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*</span><span class="sxs-lookup"><span data-stu-id="a7997-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a7997-105">Microsoft 365 stöder federerade identiteter.</span><span class="sxs-lookup"><span data-stu-id="a7997-105">Microsoft 365 supports federated identity.</span></span> <span data-ttu-id="a7997-106">Det innebär att i stället för att Microsoft 365 validerar autentiseringsuppgifterna själv, hänvisas användaren som ansluter till en federerad autentiseringsserver som är betrodd av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7997-106">This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts.</span></span> <span data-ttu-id="a7997-107">Om användarens autentiseringsuppgifter är korrekta utfärdar den federerade autentiseringsservern en säkerhetstoken som klienten sedan skickar till Microsoft 365 som autentiseringsbevis.</span><span class="sxs-lookup"><span data-stu-id="a7997-107">If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication.</span></span> <span data-ttu-id="a7997-108">Federerade identiteter möjliggör avlastning och uppskalning av autentiseringen i en Microsoft 365-prenumeration, samt avancerade autentiserings- och säkerhetsscenarier.</span><span class="sxs-lookup"><span data-stu-id="a7997-108">Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="a7997-109">I den här artikeln beskrivs hur du konfigurerar federerad inloggning för test miljön för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="a7997-109">This article describes how to configure federated authentication for your Microsoft 365 test environment, resulting in the following:</span></span>

![Den federerade autentiseringen för Microsoft 365-testmiljön](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="a7997-111">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="a7997-111">This configuration consists of:</span></span>
  
- <span data-ttu-id="a7997-112">En utvärderings version av Microsoft 365 E5 eller Product.</span><span class="sxs-lookup"><span data-stu-id="a7997-112">A Microsoft 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="a7997-113">En förenklad organisations intranät som är ansluten till Internet, bestående av fem virtuella datorer i ett undernät för ett Azure-virtuellt nätverk (DC1, APP1, KLIENT1, ADFS1 och PROXY1).</span><span class="sxs-lookup"><span data-stu-id="a7997-113">A simplified organization intranet connected to the internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1).</span></span> <span data-ttu-id="a7997-114">Azure AD Connect körs på APP1 för att synkronisera listan över konton i Active Directory Domain Services-domänen till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7997-114">Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Microsoft 365.</span></span> <span data-ttu-id="a7997-115">PROXY1 tar emot inkommande autentiseringsbegäranden.</span><span class="sxs-lookup"><span data-stu-id="a7997-115">PROXY1 receives the incoming authentication requests.</span></span> <span data-ttu-id="a7997-116">ADFS1 validerar autentiseringsuppgifter med DC1 och utfärdar säkerhetstoken.</span><span class="sxs-lookup"><span data-stu-id="a7997-116">ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="a7997-117">Att konfigurera den här test miljön inkluderar fem faser:</span><span class="sxs-lookup"><span data-stu-id="a7997-117">Setting up this test environment involves five phases:</span></span>
- [<span data-ttu-id="a7997-118">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="a7997-118">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="a7997-119">Fas 2: Skapa AD FS-servern</span><span class="sxs-lookup"><span data-stu-id="a7997-119">Phase 2: Create the AD FS server</span></span>](#phase-2-create-the-ad-fs-server)
- [<span data-ttu-id="a7997-120">Fas 3: Skapa webbproxyservern</span><span class="sxs-lookup"><span data-stu-id="a7997-120">Phase 3: Create the web proxy server</span></span>](#phase-3-create-the-web-proxy-server)
- [<span data-ttu-id="a7997-121">Fas 4: Skapa ett självsignerat certifikat och konfigurera ADFS1 och PROXY1.</span><span class="sxs-lookup"><span data-stu-id="a7997-121">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [<span data-ttu-id="a7997-122">Fas 5: Konfigurera Microsoft 365 för federerade identiteter</span><span class="sxs-lookup"><span data-stu-id="a7997-122">Phase 5: Configure Microsoft 365 for federated identity</span></span>](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> <span data-ttu-id="a7997-123">Du kan inte konfigurera den här test miljön med en Azure-testprenumeration.</span><span class="sxs-lookup"><span data-stu-id="a7997-123">You can't configure this test environment with an Azure Trial subscription.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a7997-124">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="a7997-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a7997-125">Följ anvisningarna i [synkronisering av lösenordshash för Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a7997-125">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="a7997-126">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="a7997-126">Your resulting configuration looks like this:</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="a7997-128">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="a7997-128">This configuration consists of:</span></span>
  
- <span data-ttu-id="a7997-129">En utvärderings version av Microsoft 365 E5 eller betalda prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="a7997-129">A Microsoft 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="a7997-130">En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network.</span><span class="sxs-lookup"><span data-stu-id="a7997-130">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="a7997-131">Azure AD Connect körs på APP1 för att synkronisera TESTLAB-domänen (Active Directory Domain Services) till Azure AD-klient organisationen för dina Microsoft 365-abonnemang med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="a7997-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="a7997-132">Fas 2: Skapa AD FS-servern</span><span class="sxs-lookup"><span data-stu-id="a7997-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="a7997-133">En AD FS-server tillhandahåller federerad autentisering mellan Microsoft 365 och kontona på domänen corp.contoso.com som finns i DC1.</span><span class="sxs-lookup"><span data-stu-id="a7997-133">An AD FS server provides federated authentication between Microsoft 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="a7997-134">Om du vill skapa en virtuell Azure-dator för ADFS1, fyller du i namnet på prenumerationen, resursgruppen och Azure-platsen för baskonfigurationen. Kör sedan dessa kommandon i Azure PowerShell-kommandotolken på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="a7997-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="a7997-135">Använd sedan [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella ADFS1-datorn med det lokala administratörskontonamnet och lösenordet för ADFS1 och öppna en kommandotolk i Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7997-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="a7997-136">Om du vill kontrollera namnmatchningen och nätverkskommunikationen mellan ADFS1 och DC1, kör du kommandot **ping dc1.corp.contoso.com** och kontrollerar att det finns fyra svar.</span><span class="sxs-lookup"><span data-stu-id="a7997-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="a7997-137">Anslut sedan den virtuella ADFS1-datorn till CORP-domänen med dessa kommandon i Windows PowerShell-kommandotolken på ADFS1.</span><span class="sxs-lookup"><span data-stu-id="a7997-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="a7997-138">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="a7997-138">Your resulting configuration looks like this:</span></span>
  
![AD FS-servern har lagts till i DirSync för Microsoft 365-testmiljön](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="a7997-140">Fas 3: Skapa webbproxyservern</span><span class="sxs-lookup"><span data-stu-id="a7997-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="a7997-141">Med PROXY1 kan du använda proxy till autentiseringsmeddelanden mellan användare som försöker autentisera och ADFS1.</span><span class="sxs-lookup"><span data-stu-id="a7997-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="a7997-142">Om du vill skapa en virtuell Azure-dator för PROXY1 fyller du i namnet på din resursgrupp och Azure-plats och kör dessa kommandon i Azure PowerShell-kommandotolken på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="a7997-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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
> <span data-ttu-id="a7997-143">PROXY1 tilldelas en statisk offentlig IP-adress eftersom du skapar en offentlig DNS-post som pekar på den. Denna får inte ändras när du startar om den virtuella PROXY1-datorn.</span><span class="sxs-lookup"><span data-stu-id="a7997-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span>
  
<span data-ttu-id="a7997-144">Lägg sedan till en regel i nätverks säkerhets gruppen för CorpNet-under nätet för att tillåta oombedd inkommande trafik från Internet till PROXY1's privat IP-adress och TCP-port 443.</span><span class="sxs-lookup"><span data-stu-id="a7997-144">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the internet to PROXY1's private IP address and TCP port 443.</span></span> <span data-ttu-id="a7997-145">Kör dessa kommandon i Azure PowerShell-kommandotolken på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="a7997-145">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="a7997-146">Använd sedan [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella PROXY1-datorn med det lokala administratörskontonamnet och lösenordet för PROXY1 och öppna en kommandotolk i Windows PowerShell för PROXY1.</span><span class="sxs-lookup"><span data-stu-id="a7997-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="a7997-147">Om du vill kontrollera namnmatchningen och nätverkskommunikationen mellan PROXY1 och DC1, kör du kommandot **ping dc1.corp.contoso.com** och kontrollerar att det finns fyra svar.</span><span class="sxs-lookup"><span data-stu-id="a7997-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="a7997-148">Anslut sedan den virtuella PROXY1-datorn till CORP-domänen med dessa kommandon i Windows PowerShell-kommandotolken på PROXY1.</span><span class="sxs-lookup"><span data-stu-id="a7997-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="a7997-149">Visa den offentliga IP-adressen för PROXY1 med dessa Azure PowerShell-kommandon på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="a7997-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer.</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="a7997-150">Arbeta sedan med din offentliga DNS-leverantör och skapa en ny offentlig DNS A-post för **fs.testlab.**\<*your DNS domain name*></span><span class="sxs-lookup"><span data-stu-id="a7997-150">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<*your DNS domain name*></span></span> <span data-ttu-id="a7997-151">det löser att IP-adressen visas av kommandot **Write-Host**.</span><span class="sxs-lookup"><span data-stu-id="a7997-151">that resolves to the IP address displayed by the **Write-Host** command.</span></span> <span data-ttu-id="a7997-152">**fs.testlab.**\<*your DNS domain name*></span><span class="sxs-lookup"><span data-stu-id="a7997-152">The **fs.testlab.**\<*your DNS domain name*></span></span> <span data-ttu-id="a7997-153">kallas i fortsättningen för *federationstjänstens FQDN*.</span><span class="sxs-lookup"><span data-stu-id="a7997-153">is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="a7997-154">Använd sedan [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella DC1-datorn med hjälp av CORP\\User1-autentiseringsuppgifter och kör följande kommandon i en Windows PowerShell-kommandotolk på administratörsnivå:</span><span class="sxs-lookup"><span data-stu-id="a7997-154">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="a7997-155">De här kommandona skapar en intern DNS-post så att virtuella datorer i Azure Virtual Network kan matcha den interna Federations tjänstens FQDN till ADFS1's privata IP-adress.</span><span class="sxs-lookup"><span data-stu-id="a7997-155">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation service FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="a7997-156">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="a7997-156">Your resulting configuration looks like this:</span></span>
  
![Webbprogrammets proxyserver har lagts till i DirSync för Microsoft 365-testmiljön](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="a7997-158">Fas 4: Skapa ett självsignerat certifikat och konfigurera ADFS1 och PROXY1.</span><span class="sxs-lookup"><span data-stu-id="a7997-158">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="a7997-159">I den här fasen skapar du ett självsignerat digitalt certifikat för federationstjänstens FQDN. Därefter konfigurerar du ADFS1 och PROXY1 som en AD FS-servergrupp.</span><span class="sxs-lookup"><span data-stu-id="a7997-159">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="a7997-160">Först använder du [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella DC1-datorn med hjälp av CORP\\User1-autentiseringsuppgifterna och sedan öppnar du en Windows PowerShell-kommandotolk på administratörsnivå.</span><span class="sxs-lookup"><span data-stu-id="a7997-160">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="a7997-161">Skapa sedan ett AD FS-tjänstkonto med det här kommandot i kommando tolken för Windows PowerShell på DC1:</span><span class="sxs-lookup"><span data-stu-id="a7997-161">Next, create an AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="a7997-162">Observera att du uppmanas att ange lösenordet för kontot med detta kommando.</span><span class="sxs-lookup"><span data-stu-id="a7997-162">Note that this command prompts you to supply the account password.</span></span> <span data-ttu-id="a7997-163">Välj ett starkt lösenord och spara det på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="a7997-163">Choose a strong password and record it in a secured location.</span></span> <span data-ttu-id="a7997-164">Du behöver den för den här fasen och för steg 5.</span><span class="sxs-lookup"><span data-stu-id="a7997-164">You will need it for this phase and for Phase 5.</span></span>
  
<span data-ttu-id="a7997-165">Använd [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella ADFS1-datorn med hjälp av CORP\\User1-autentiseringsuppgifterna.</span><span class="sxs-lookup"><span data-stu-id="a7997-165">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials.</span></span> <span data-ttu-id="a7997-166">Öppna en Windows PowerShell-kommandotolk på administratörsnivå i ADFS1, fyll i FQDN för federationstjänsten och kör sedan följande kommandon för att skapa ett självsignerat certifikat:</span><span class="sxs-lookup"><span data-stu-id="a7997-166">Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="a7997-167">Följ sedan de här anvisningarna för att spara det nya självsignerade certifikatet som en fil.</span><span class="sxs-lookup"><span data-stu-id="a7997-167">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="a7997-168">Välj **Start**, Skriv **mmc.exe**och tryck sedan på **RETUR**.</span><span class="sxs-lookup"><span data-stu-id="a7997-168">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="a7997-169">Välj **File**  >  **Lägg till/ta bort snapin-modul**.</span><span class="sxs-lookup"><span data-stu-id="a7997-169">Select **File** > **Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="a7997-170">I **Lägg till eller ta bort snapin-moduler**dubbelklickar du på **certifikat** i listan över tillgängliga snapin-moduler, väljer **dator konto**och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-170">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="a7997-171">I **Välj dator**väljer du **Slutför**och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7997-171">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="a7997-172">Öppna **Certifikat (lokal dator) > Personlig > Certifikat** i mapplistan.</span><span class="sxs-lookup"><span data-stu-id="a7997-172">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="a7997-173">Markera och håll (eller högerklicka på certifikatet med Federations tjänstens FQDN-namn) och **Välj sedan** **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="a7997-173">Select and hold (or right-click) the certificate with your federation service FQDN, select **All tasks**, and then select **Export**.</span></span>
    
7. <span data-ttu-id="a7997-174">Välj **Nästa**på **välkomst** sidan.</span><span class="sxs-lookup"><span data-stu-id="a7997-174">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="a7997-175">På sidan **Exportera privat** sida väljer du **Ja**och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-175">On the **Export Private Key** page, select **Yes**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="a7997-176">På sidan **Exportera fil format** väljer du **Exportera alla utökade egenskaper**och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-176">On the **Export File Format** page, select **Export all extended properties**, and then select **Next**.</span></span>
    
10. <span data-ttu-id="a7997-177">Välj **lösen** ord på sidan **säkerhet** och ange lösen ord i **lösen** ord och **Bekräfta lösen ord.**</span><span class="sxs-lookup"><span data-stu-id="a7997-177">On the **Security** page, select **Password** and enter a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="a7997-178">På sidan **fil att exportera väljer du** **Bläddra**.</span><span class="sxs-lookup"><span data-stu-id="a7997-178">On the **File to Export** page, select **Browse**.</span></span>
    
12. <span data-ttu-id="a7997-179">Bläddra till mappen **C: \\ certifikat** , ange **SSL** i **fil namn**och välj sedan **Spara.**</span><span class="sxs-lookup"><span data-stu-id="a7997-179">Browse to the **C:\\Certs** folder, enter **SSL** in **File name**, and then select **Save.**</span></span>
    
13. <span data-ttu-id="a7997-180">På sidan **fil att exportera väljer du** **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-180">On the **File to Export** page, select **Next**.</span></span>
    
14. <span data-ttu-id="a7997-181">På sidan för att **Exportera certifikat** klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="a7997-181">On the **Completing the Certificate Export Wizard** page, select **Finish**.</span></span> <span data-ttu-id="a7997-182">Välj **OK**när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="a7997-182">When prompted, select **OK**.</span></span>
    
<span data-ttu-id="a7997-183">Installera sedan AD FS-tjänsten med detta kommando i Windows PowerShell-kommandotolken på ADFS1:</span><span class="sxs-lookup"><span data-stu-id="a7997-183">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="a7997-184">Vänta på att installationen slutförs.</span><span class="sxs-lookup"><span data-stu-id="a7997-184">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="a7997-185">Konfigurera sedan AD FS-tjänsten med följande steg:</span><span class="sxs-lookup"><span data-stu-id="a7997-185">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="a7997-186">Välj **Start**och välj sedan **Server hanteraren** .</span><span class="sxs-lookup"><span data-stu-id="a7997-186">Select **Start**, and then select the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="a7997-187">I träd fönstret i Server hanteraren väljer du **AD FS**.</span><span class="sxs-lookup"><span data-stu-id="a7997-187">In the tree pane of Server Manager, select **AD FS**.</span></span>
    
3. <span data-ttu-id="a7997-188">I verktygsfältet högst upp väljer du den orange varnings symbolen och väljer sedan **Konfigurera Federations tjänsten på den här servern**.</span><span class="sxs-lookup"><span data-stu-id="a7997-188">In the tool bar at the top, select the orange caution symbol, and then select **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="a7997-189">Välj **Nästa**på **välkomst** sidan i konfigurations guiden för Active Directory Federation Services.</span><span class="sxs-lookup"><span data-stu-id="a7997-189">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="a7997-190">På sidan **Anslut till AD DS** väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-190">On the **Connect to AD DS** page, select **Next**.</span></span>
    
6. <span data-ttu-id="a7997-191">På sidan **Ange egenskaper för tjänst**:</span><span class="sxs-lookup"><span data-stu-id="a7997-191">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="a7997-192">För **SSL-certifikat**väljer du nedpilen och väljer sedan certifikatet med namnet på ditt FQDN för Federations tjänsten.</span><span class="sxs-lookup"><span data-stu-id="a7997-192">For **SSL Certificate**, select the down arrow, and then select the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="a7997-193">Ange namnet på din fiktiva organisation i **visnings namn för Federations tjänsten**.</span><span class="sxs-lookup"><span data-stu-id="a7997-193">In **Federation Service Display Name**, enter the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="a7997-194">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-194">Select **Next**.</span></span>
    
7. <span data-ttu-id="a7997-195">På sidan **Ange tjänst konto** väljer du **Välj** för **konto namn**.</span><span class="sxs-lookup"><span data-stu-id="a7997-195">On the **Specify Service Account** page, select **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="a7997-196">I **Select User or service account**anger du **ADFS-service**, väljer **kontrol lera namn**och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7997-196">In **Select User or Service Account**, enter **ADFS-Service**, select **Check Names**, and then select **OK**.</span></span>
    
9. <span data-ttu-id="a7997-197">Ange lösen ordet för ADFS-Service kontot i **konto lösen ord**och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-197">In **Account Password**, enter the password for the ADFS-Service account, and then select **Next**.</span></span>
    
10. <span data-ttu-id="a7997-198">På sidan **Ange konfigurations databas** väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-198">On the **Specify Configuration Database** page, select **Next**.</span></span>
    
11. <span data-ttu-id="a7997-199">På sidan **gransknings alternativ** väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-199">On the **Review Options** page, select **Next**.</span></span>
    
12. <span data-ttu-id="a7997-200">På sidan **nödvändiga kontroller** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="a7997-200">On the **Pre-requisite Checks** page, select **Configure**.</span></span>

13. <span data-ttu-id="a7997-201">På sidan **resultat** väljer du **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="a7997-201">On the **Results** page, select **Close**.</span></span>
    
14. <span data-ttu-id="a7997-202">Välj **Start**, Välj Power Icon, Välj **restart**och välj sedan **Continue**.</span><span class="sxs-lookup"><span data-stu-id="a7997-202">Select **Start**, select the power icon, select **Restart**, and then select **Continue**.</span></span>
    
<span data-ttu-id="a7997-203">I [Azure-portalen](https://portal.azure.com) kan du ansluta till PROXY1 med autentiseringsuppgifterna för CORP\\User1-kontot.</span><span class="sxs-lookup"><span data-stu-id="a7997-203">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="a7997-204">Följ sedan de här anvisningarna för att installera det självsignerade certifikatet på **både PROXY1 och APP1**.</span><span class="sxs-lookup"><span data-stu-id="a7997-204">Next, use these steps to install the self-signed certificate on **both PROXY1 and APP1**.</span></span>
  
1. <span data-ttu-id="a7997-205">Välj **Start**, Skriv **mmc.exe**och tryck sedan på **RETUR**.</span><span class="sxs-lookup"><span data-stu-id="a7997-205">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="a7997-206">Välj **arkiv > Lägg till/ta bort snapin-modul**.</span><span class="sxs-lookup"><span data-stu-id="a7997-206">Select **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="a7997-207">I **Lägg till eller ta bort snapin-moduler**dubbelklickar du på **certifikat** i listan över tillgängliga snapin-moduler, väljer **dator konto**och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-207">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="a7997-208">I **Välj dator**väljer du **Slutför**och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7997-208">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="a7997-209">Öppna **certifikat (lokal dator)** i träd fönstret  >  **Personal**  >  **Certificates**.</span><span class="sxs-lookup"><span data-stu-id="a7997-209">In the tree pane, open **Certificates (Local Computer)** > **Personal** > **Certificates**.</span></span>
    
6. <span data-ttu-id="a7997-210">Markera och håll ned (eller högerklicka på) **personligt**, Välj **alla uppgifter**och välj sedan **Importera**.</span><span class="sxs-lookup"><span data-stu-id="a7997-210">Select and hold (or right-click) **Personal**, select **All tasks**, and then select **Import**.</span></span>
    
7. <span data-ttu-id="a7997-211">Välj **Nästa**på **välkomst** sidan.</span><span class="sxs-lookup"><span data-stu-id="a7997-211">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="a7997-212">På sidan **fil som ska importeras** anger du \*\* \\ \\ ADFS1- \\ certifikat för \\ SSL. pfx\*\*och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-212">On the **File to Import** page, enter **\\\\adfs1\\certs\\ssl.pfx**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="a7997-213">Ange lösen ordet för certifikatet i **lösen ord**på sidan skydd mot den **privata knappen** och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="a7997-213">On the **Private key protection** page, enter the certificate password in **Password**, and then select **Next.**</span></span>
    
10. <span data-ttu-id="a7997-214">På sidan **certifikat lagring** väljer du **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="a7997-214">On the **Certificate store** page, select **Next.**</span></span>
    
11. <span data-ttu-id="a7997-215">På sidan **Slutför** väljer du **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="a7997-215">On the **Completing** page, select **Finish**.</span></span>
    
12. <span data-ttu-id="a7997-216">På sidan **certifikat lagring** väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-216">On the **Certificate Store** page, select **Next**.</span></span>
    
13. <span data-ttu-id="a7997-217">Välj **OK**när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="a7997-217">When prompted, select **OK**.</span></span>
    
14. <span data-ttu-id="a7997-218">Välj **certifikat**i träd fönstret.</span><span class="sxs-lookup"><span data-stu-id="a7997-218">In the tree pane, select **Certificates**.</span></span>
    
15. <span data-ttu-id="a7997-219">Markera och håll ned (eller högerklicka på) certifikatet och välj sedan **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="a7997-219">Select and hold (or right-click) the certificate, and then select **Copy**.</span></span>
    
16. <span data-ttu-id="a7997-220">Öppna certifikat för **betrodda rot certifikat utfärdare**i träd fönstret  >  **Certificates**.</span><span class="sxs-lookup"><span data-stu-id="a7997-220">In the tree pane, open **Trusted Root Certification Authorities** > **Certificates**.</span></span>
    
17. <span data-ttu-id="a7997-221">Placera mus pekaren nedanför listan över installerade certifikat, markera och håll (eller högerklicka) och välj sedan **Klistra in**.</span><span class="sxs-lookup"><span data-stu-id="a7997-221">Move your mouse pointer below the list of installed certificates, select and hold (or right-click), and then select **Paste**.</span></span>
    
<span data-ttu-id="a7997-222">Öppna en PowerShell-kommandotolk på administratörsnivå och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="a7997-222">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="a7997-223">Vänta på att installationen slutförs.</span><span class="sxs-lookup"><span data-stu-id="a7997-223">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="a7997-224">Använd följande steg för att konfigurera att tjänsten Webbprogramproxy ska använda ADFS1 som federationsserver:</span><span class="sxs-lookup"><span data-stu-id="a7997-224">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="a7997-225">Välj **Start**och välj sedan **Server Manager**.</span><span class="sxs-lookup"><span data-stu-id="a7997-225">Select **Start**, and then select **Server Manager**.</span></span>
    
2. <span data-ttu-id="a7997-226">I träd fönstret väljer du **fjärråtkomst**.</span><span class="sxs-lookup"><span data-stu-id="a7997-226">In the tree pane, select **Remote Access**.</span></span>
    
3. <span data-ttu-id="a7997-227">I verktygsfältet högst upp väljer du den orange varnings symbolen och väljer sedan **Öppna guiden**webbprogramproxy.</span><span class="sxs-lookup"><span data-stu-id="a7997-227">In the tool bar at the top, select the orange caution symbol, and then select **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="a7997-228">På **välkomst** sidan i guiden Konfiguration av Webbprogramproxy väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-228">On the **Welcome** page of the Web Application Proxy Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="a7997-229">På sidan **Federationsserver**:</span><span class="sxs-lookup"><span data-stu-id="a7997-229">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="a7997-230">Ange ditt Federations tjänst-FQDN i rutan **namn på Federations tjänst** .</span><span class="sxs-lookup"><span data-stu-id="a7997-230">In the **Federation service name** box, enter your federation service FQDN.</span></span>
    
  - <span data-ttu-id="a7997-231">I rutan **användar namn** anger du **Corp \\ Användare1**.</span><span class="sxs-lookup"><span data-stu-id="a7997-231">In the **User name** box, enter **CORP\\User1**.</span></span>
    
  - <span data-ttu-id="a7997-232">I rutan **lösen ord** anger du lösen ordet för user1-kontot.</span><span class="sxs-lookup"><span data-stu-id="a7997-232">In the **Password** box, enter the password for the User1 account.</span></span>
    
  - <span data-ttu-id="a7997-233">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-233">Select **Next**.</span></span>
    
6. <span data-ttu-id="a7997-234">På sidan **AD FS-proxyskript** väljer du nedåtpilen, väljer certifikatet med FQDN-namnet på Federations tjänsten och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-234">On the **AD FS Proxy Certificate** page, select the down arrow, select the certificate with your federation service FQDN, and then select **Next**.</span></span>
    
7. <span data-ttu-id="a7997-235">På **bekräftelse** sidan väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="a7997-235">On the **Confirmation** page, select **Configure**.</span></span>
    
8. <span data-ttu-id="a7997-236">På sidan **resultat** väljer du **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="a7997-236">On the **Results** page, select **Close**.</span></span>
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a><span data-ttu-id="a7997-237">Fas 5: Konfigurera Microsoft 365 för federerade identiteter</span><span class="sxs-lookup"><span data-stu-id="a7997-237">Phase 5: Configure Microsoft 365 for federated identity</span></span>

<span data-ttu-id="a7997-238">Använd [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella APP1-datorn med hjälp av CORP\\User1-autentiseringsuppgifterna.</span><span class="sxs-lookup"><span data-stu-id="a7997-238">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="a7997-239">Använd följande steg för att konfigurera Azure AD Connect och din Microsoft 365-prenumeration för federerad autentisering:</span><span class="sxs-lookup"><span data-stu-id="a7997-239">Use these steps to configure Azure AD Connect and your Microsoft 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="a7997-240">Dubbelklicka på **Azure AD Connect** på skrivbordet.</span><span class="sxs-lookup"><span data-stu-id="a7997-240">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="a7997-241">På sidan **Välkommen till Azure AD Connect** väljer du **Configure**.</span><span class="sxs-lookup"><span data-stu-id="a7997-241">On the **Welcome to Azure AD Connect** page, select **Configure**.</span></span>
    
3. <span data-ttu-id="a7997-242">På sidan **Ytterligare aktiviteter** väljer du **ändra användar inloggning**och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-242">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="a7997-243">På sidan **Anslut till Azure AD** anger du ditt globala administratörs konto namn och lösen ord och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-243">On the **Connect to Azure AD** page, enter your global administrator account name and password, and then select **Next**.</span></span>
    
5. <span data-ttu-id="a7997-244">På **inloggnings** sidan för användare väljer du **Federation med AD FS**och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-244">On the **User sign-in** page, select **Federation with AD FS**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="a7997-245">Välj **Använd en befintlig AD FS-servergrupp**på sidan **AD FS-servergrupp** och ange **ADFS1** i rutan **Server namn** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-245">On the **AD FS farm** page, select **Use an existing AD FS farm**, enter **ADFS1** in the **Server Name** box, and then select **Next**.</span></span>
    
7. <span data-ttu-id="a7997-246">När du uppmanas att ange autentiseringsuppgifter för servern anger du autentiseringsuppgifterna för företags \\ -Användare1 user1-kontot och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7997-246">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then select **OK**.</span></span>
    
8. <span data-ttu-id="a7997-247">Ange lösen ordet i rutan **lösen ord** i \*\*rutan \\ \*\* **användar namn** på sidan **domän administratörs** inloggningar och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-247">On the **Domain Administrator** credentials page, enter **CORP\\User1** in the **Username** box, enter the account password in the **Password** box, and then select **Next**.</span></span>
    
9. <span data-ttu-id="a7997-248">På sidan **AD FS** -tjänstkonto anger du **Corp \\ ADFS-service** i rutan **domain username** , anger lösen ordet i rutan **Domain User Password** och väljer sedan **Next**.</span><span class="sxs-lookup"><span data-stu-id="a7997-248">On the **AD FS service account** page, enter **CORP\\ADFS-Service** in the **Domain Username** box, enter the account password in the **Domain User Password** box, and then select **Next**.</span></span>
    
10. <span data-ttu-id="a7997-249">På sidan **Azure AD-domän** i **domän**väljer du namnet på den domän som du har skapat och lagt till i din prenumeration i steg 1 och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a7997-249">On the **Azure AD Domain** page, in **Domain**, select the name of the domain that you previously created and added to your subscription in Phase 1, and then select **Next**.</span></span>
    
11. <span data-ttu-id="a7997-250">På sidan **redo att konfigurera** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="a7997-250">On the **Ready to configure** page, select **Configure**.</span></span>
    
12. <span data-ttu-id="a7997-251">Välj **Verifiera**på sidan **installationen är klar** .</span><span class="sxs-lookup"><span data-stu-id="a7997-251">On the **Installation complete** page, select **Verify**.</span></span>
    
    <span data-ttu-id="a7997-252">Du bör se meddelanden som indikerar att både intranät-och Internet konfigurationen verifierades.</span><span class="sxs-lookup"><span data-stu-id="a7997-252">You should see messages indicating that both the intranet and internet configuration was verified.</span></span>
    
13. <span data-ttu-id="a7997-253">På sidan **installationen är klar** väljer du **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="a7997-253">On the **Installation complete** page, select **Exit**.</span></span>
    
<span data-ttu-id="a7997-254">Visa att den federerade autentiseringen fungerar:</span><span class="sxs-lookup"><span data-stu-id="a7997-254">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="a7997-255">Öppna en ny privat instans av webbläsaren på din lokala dator och gå till [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a7997-255">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="a7997-256">Ange **user1@** för inloggnings uppgifterna \<*the domain created in Phase 1*> .</span><span class="sxs-lookup"><span data-stu-id="a7997-256">For the sign-in credentials, enter **user1@**\<*the domain created in Phase 1*>.</span></span>
    
    <span data-ttu-id="a7997-257">Om test domänen är **testlab.contoso.com**skriver du till exempel "user1@testlab.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="a7997-257">For example, if your test domain is **testlab.contoso.com**, you would enter "user1@testlab.contoso.com".</span></span> <span data-ttu-id="a7997-258">Tryck på **TABB** -tangenten eller låt Microsoft 365 automatiskt omdirigera dig.</span><span class="sxs-lookup"><span data-stu-id="a7997-258">Press the **Tab** key or allow Microsoft 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="a7997-259">Nu bör du se sidan **Din anslutning är inte privat**.</span><span class="sxs-lookup"><span data-stu-id="a7997-259">You should now see a **Your connection is not private** page.</span></span> <span data-ttu-id="a7997-260">Du ser det här eftersom du har installerat ett självsignerat certifikat på ADFS1 att din station ära dator inte kan verifiera.</span><span class="sxs-lookup"><span data-stu-id="a7997-260">You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer can't validate.</span></span> <span data-ttu-id="a7997-261">I en produktionsdistribution av federerad autentisering använder du ett certifikat från en betrodd certifikatutfärdare för att dina användare inte ska se den här sidan.</span><span class="sxs-lookup"><span data-stu-id="a7997-261">In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="a7997-262">På sidan **anslutningen är inte privat** väljer du **Avancerat**och väljer sedan \*\*gå vidare till \<*your federation service FQDN*> \*\*.</span><span class="sxs-lookup"><span data-stu-id="a7997-262">On the **Your connection is not private** page, select **Advanced**, and then select **Proceed to \<*your federation service FQDN*>**.</span></span> 
    
4. <span data-ttu-id="a7997-263">Logga in med följande på sidan med namnet på din fiktiva organisation:</span><span class="sxs-lookup"><span data-stu-id="a7997-263">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="a7997-264">**CORP\\User1** som namn</span><span class="sxs-lookup"><span data-stu-id="a7997-264">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="a7997-265">Lösenordet för User1-kontot</span><span class="sxs-lookup"><span data-stu-id="a7997-265">The password for the User1 account</span></span>
    
    <span data-ttu-id="a7997-266">Du bör se **startsidan för Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="a7997-266">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="a7997-267">Proceduren visar att utvärderingsprenumerationen är federerad med AD DS corp.contoso.com-domänen som finns i DC1.</span><span class="sxs-lookup"><span data-stu-id="a7997-267">This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1.</span></span> <span data-ttu-id="a7997-268">Här följer grundläggande information om autentiseringsprocessen:</span><span class="sxs-lookup"><span data-stu-id="a7997-268">Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="a7997-269">När du använder den federerade domänen som du skapade i fas 1 i namnet på inloggningskontot, dirigerar Microsoft 365 webbläsaren till federationstjänstens FQDN och PROXY1.</span><span class="sxs-lookup"><span data-stu-id="a7997-269">When you use the federated domain that you created in Phase 1 within the sign-in account name, Microsoft 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="a7997-270">PROXY1 skickar din lokala dator till inloggningssidan för det fiktiva företaget.</span><span class="sxs-lookup"><span data-stu-id="a7997-270">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="a7997-271">När du skickar CORP\\User1 och lösenordet till PROXY1, vidarebefordras det till ADFS1.</span><span class="sxs-lookup"><span data-stu-id="a7997-271">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="a7997-272">ADFS1 validerar CORP\\User1 och lösenordet med DC1 och skickar en säkerhetstoken till din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="a7997-272">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="a7997-273">Din lokala dator skickar säkerhetstoken till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7997-273">Your local computer sends the security token to Microsoft 365.</span></span>
    
6. <span data-ttu-id="a7997-274">Microsoft 365 kontrollerar att denna säkerhetstoken har skapats av ADFS1 och tillåter åtkomst.</span><span class="sxs-lookup"><span data-stu-id="a7997-274">Microsoft 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="a7997-275">Utvärderingsprenumerationen har nu konfigurerats med federerad autentisering.</span><span class="sxs-lookup"><span data-stu-id="a7997-275">Your trial subscription is now configured with federated authentication.</span></span> <span data-ttu-id="a7997-276">Du kan använda den här utvecklings-/testmiljön för avancerade autentiseringsscenarier.</span><span class="sxs-lookup"><span data-stu-id="a7997-276">You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="a7997-277">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="a7997-277">Next step</span></span>

<span data-ttu-id="a7997-278">När du är redo att distribuera produktion-redo, federerad för hög tillgänglighet för Microsoft 365 i Azure läser du [distribuera federerad auktorisering med hög tillgänglighet för microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span><span class="sxs-lookup"><span data-stu-id="a7997-278">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 in Azure, see [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span></span>
  
