---
title: Baskonfiguration för simulerat företag för Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
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
description: Använd den här testlabbguiden om du vill skapa en simulerad företagstestmiljö för Microsoft 365 för företag.
ms.openlocfilehash: 8df63e1a580b57aa263c11dccaed947f46f2cbb9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926050"
---
# <a name="the-simulated-enterprise-base-configuration"></a>Baskonfiguration för simulerat företag

*Den här testlabbguiden kan användas för både Microsoft 365 för företag Office 365 Enterprise för testmiljöer.*

I den här artikeln beskrivs hur du skapar en förenklad miljö för Microsoft 365 företag som innehåller:

- En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.
- Ett förenklat organisations intranät som är anslutet till internet och består av tre virtuella datorer i ett virtuellt Azure-nätverk (DC1, APP1 och CLIENT1).
 
![Baskonfiguration för simulerat företag](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

Att skapa en förenklad testmiljö omfattar två faser:
- [Fas 1: Skapa ett simulerat intranät](#phase-1-create-a-simulated-intranet)
- [Fas 2: Skapa en Microsoft 365 E5-prenumeration](#phase-2-create-your-microsoft-365-e5-subscription)

Du kan använda den resulterande miljön för att testa funktionerna i Microsoft 365 för företag [med](https://www.microsoft.com/microsoft-365/enterprise) ytterligare [testlabbguider](m365-enterprise-test-lab-guides.md) eller på egen hand.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i [Microsoft 365 för företags testlabbguide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-create-a-simulated-intranet"></a>Fas 1: Skapa ett simulerat intranät

I den här fasen ska du bygga ett simulerat intranät i Azure-infrastrukturtjänster som innehåller en AD DS-domänkontrollant (Active Directory Domain Services), en programserver och en klientdator.

Du kommer att använda dessa datorer i ytterligare [Microsoft 365 testlabbguider](m365-enterprise-test-lab-guides.md) för att konfigurera och visa hybrididentitet och andra funktioner.

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a>Metod 1: Skapa det simulerade intranätet med en Azure Resource Manager-mall

Med den här metoden använder du en Azure Resource Manager-mall för att bygga ut det simulerade intranätet. Azure Resource Manager-mallarna innehåller alla instruktioner för att skapa Azure-nätverksinfrastrukturen, virtuella maskinerna och deras konfiguration.

Innan du distribuerar mallen bör du läsa [igenom mallens LÄSME-sida](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) och ha följande information klar:

- Testmiljöns namn på den offentliga DNS-domänen (testlab.\<*your public domain*>) Du anger det här namnet i **fältet Domännamn** på sidan **Anpassad** distribution.
- Ett DNS-etikettprefix för URL:erna för de virtuella datorernas offentliga IP-adresser. Du måste ange det här namnet i fältet **Dns Label Prefix** (DNS-etikettprefix) på sidan **Custom deployment** (Anpassad distribution).

När du har läst anvisningarna väljer du **Distribuera till Azure** på [readme-sidan för att](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) komma igång.

>[!Note]
>Det simulerade intranätet som byggs med Azure Resurshanteraren-mallen kräver en betald Azure-prenumeration.

När mallen är klar ser konfigurationen ut så här:

![Det simulerade intranätet i Azure-infrastrukturtjänster](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a>Metod 2: Skapa det simulerade intranätet med Azure PowerShell

I den här metoden använder du Windows PowerShell och Azure PowerShell-modulen till att bygga upp nätverksinfrastrukturen, de virtuella datorerna och deras konfiguration.

Använd den här metoden om du vill skaffa dig erfarenhet av att skapa element i Azure-infrastrukturen ett steg i taget med PowerShell. Du kan sedan anpassa PowerShell-kommandoblocken för din egen distribution av andra virtuella datorer i Azure.

#### <a name="step-1-create-dc1"></a>Steg 1: Skapa DC1

I det här steget skapar du ett virtuellt Azure-nätverk och lägger till DC1, en virtuell dator som är en domänkontrollant för en AD DS-domän.

Starta först en Windows PowerShell-kommandotolk på din lokala dator.
  
> [!NOTE]
> Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell. Se [Kom igång med Azure PowerShell-cmdletar](/powershell/azureps-cmdlets-docs/). 
  
Logga in på ditt Azure-konto med följande kommando.
  
```powershell
Connect-AzAccount
```

Hämta ditt prenumerationsnamn med följande kommando.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Ange din Azure-prenumeration. Ersätt allt inom citattecknen, inklusive vinkelparenteserna ("<" och ">"), med rätt namn.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Skapa sedan en ny resursgrupp för det simulerade företagstestlabbet. Använd det är kommandot för att lista dina befintliga resursgrupper när du ska fastställa ett unikt resursgruppnamn.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Skapa den nya resursgruppen med dessa kommandon. Ersätt allt inom citattecknen, inklusive vinkelparenteserna, med rätt namn.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Skapa sedan det virtuella TestLab-nätverket som är värd för företagsnätverksundernätet i den simulerade företagsmiljön och skydda det med en nätverkssäkerhetsgrupp. Fyll i namnet på resursgruppen och kör dessa kommandon vid kommandotolken i PowerShell på din lokala dator.
  
```powershell
$rgName="<name of your new resource group>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

Nästa steg är att skapa den virtuella DC1-datorn och konfigurera den som domänkontrollant för **testlab.**\<your public domain> AD DS-domän och en DNS-server för de virtuella datorerna i TestLabs virtuella nätverk. Exempel: Om namnet på din offentliga domän är **<span>contoso</span>.com** blir den virtuella datorn DC1 domänkontrollant för domänen **<span>testlab</span>.contoso.com**.
  
Om du vill skapa en virtuell Azure-dator för DC1 fyller du i namnet på din resursgrupp och kör dessa kommandon vid kommandotolken i PowerShell på din lokala dator.
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC1-OS" -DiskSizeInGB 128 -CreateOption FromImage
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC1-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC1-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Du uppmanas att ange ett användarnamn och lösenord för det lokala administratörskontot på DC1. Använd ett starkt lösenord och spara både namnet och lösenordet på en säker plats.
  
Anslut sedan till den virtuella DC1-datorn:
  
1. Välj [Resursgrupper i](https://portal.azure.com) **Azure-portalen > <** namnet på den nya **_resursgruppen_ _ *> > _* DC1-Anslut**  >  .
    
2. I det öppna fönstret väljer du Ladda **ned RDP-fil**. Öppna DC1.rdp-filen som laddas ned och välj sedan **Anslut**.
    
3. Ange namnet på det lokala administratörskontot för DC1:
    
   - I Windows 7:
    
     I dialogrutan **Windows-säkerhet** väljer du Använd **ett annat konto**. I **Användarnamn anger du** namnet på det lokala **\\** < DC1-administratörskontot>.
    
   - För Windows 8 eller Windows 10:
    
     I **Windows-säkerhet** väljer du Fler **alternativ** och sedan Använd **ett annat konto.** I **Användarnamn anger du** namnet på det lokala **\\** < DC1-administratörskontot>.
    
4. I **Lösenord** anger du lösenordet för det lokala administratörskontot och väljer sedan **OK.**
    
5. Välj Ja när du uppmanas att **göra det.**
    
Lägg sedan till en extra datadisk som en ny volym med enhetsbokstaven F: med det här kommandot i Windows PowerShell-kommandotolk på administratörsnivå på DC1.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Konfigurera sedan DC1 som domänkontrollant och DNS-server för domänen **testlab.**\<*your public domain*> domän. Ange ditt offentliga domännamn, ta bort vinkelparenteserna och kör sedan dessa kommandon på en administratörsnivå Windows PowerShell kommandotolken i DC1.
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
Du måste ange ett administratörslösenord för felsäkert läge. Spara lösenordet på en säker plats.
  
Observera att dessa kommandon kan ta några minuter att slutföra.
  
När DC1 har startat om återansluter du till den virtuella datorn DC1.
  
1. I [Azure-portalen](https://portal.azure.com)väljer du **Resursgrupper > <** *resursgruppnamnet> >*   >  **DC1-Anslut.**
    
2. Kör DC1.rdp-filen som laddas ned och välj sedan **Anslut**.
    
3. I **Windows-säkerhet** väljer du **Använd ett annat konto**. I **Användarnamn anger** du **testLAB-administratörens \\** namn < *>.*
    
4. I rutan **Lösenord** anger du lösenordet för det lokala administratörskontot och väljer sedan **OK.**
    
5. Välj Ja när du uppmanas att **göra det.**
    
Skapa sedan ett användarkonto i Active Directory som ska användas när du loggar in på TESTLAB-domänmedlemsdatorer. Kör det här kommandot i en Windows PowerShell-kommandotolk på administratörsnivå.
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

Observera att du uppmanas att ange lösenordet för User1-kontot med detta kommando. Det här kontot används för fjärrskrivbordsanslutningar för alla TESTLAB-domänmedlemsdatorer, så välj ett starkt lösenord. Anteckna User1-kontots lösenord och spara det på en säker plats.
  
Konfigurera sedan det nya User1-kontot som en domän-, företags- och schemaadministratör. Kör det här kommandot i en Windows PowerShell-kommandotolk på administratörsnivå.
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

Stäng fjärrskrivbordssessionen med DC1 och återanslut sedan med TESTLAB\\User1-kontot.
  
För att sedan tillåta trafik för Ping-verktyget kör du det här kommandot i en Windows PowerShell-kommandotolk på administratörsnivå.
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

Din aktuella konfiguration ser ut så här:
  
![Steg 1 i baskonfiguration för simulerat företag](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a>Steg 2: Konfigurera APP1

I det här steget skapar och konfigurerar du APP1, som är en programserver som till en början tillhandahåller webb- och fildelningstjänster.

Om du vill skapa en virtuell Azure-dator för APP1 fyller du i namnet på din resursgrupp och kör dessa kommandon vid kommandotolken på din lokala dator.
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Anslut sedan till den virtuella datorn APP1 med namnet och lösenordet för det lokala administratörskontot för APP1 och öppna sedan en kommandotolk i Windows PowerShell.
  
Om du vill kontrollera namnmatchningen och nätverkskommunikationen mellan APP1 och DC1 kör **ping dc1.testlab.**\<*your public domain name*> kommandot och bekräfta att det finns fyra svar.
  
Anslut sedan den virtuella datorn APP1 till TESTLAB-domänen med dessa kommandon i Windows PowerShell-kommandotolken.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Observera att när du har kört kommandot **Add-Computer måste** du ange autentiseringsuppgifterna för TESTLAB \\ User1-domänkontot.
  
När APP1 har startat om ansluter du den med TESTLAB\\User1-kontot och öppnar sedan en Windows PowerShell-kommandotolk på administratörsnivå.
  
Gör sedan APP1 till webbserver med det här kommandot i en Windows PowerShell-kommandotolk på administratörsnivå på APP1.
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

Skapa sedan en delad mapp och en textfil i mappen på APP1 med dessa PowerShell-kommandon.
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

Din aktuella konfiguration ser ut så här:
  
![Steg 2 i baskonfiguration för simulerat företag](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a>Steg 3: Konfigurera CLIENT1

I det här steget skapar och konfigurerar du CLIENT1, som fungerar som en typisk bärbar dator, surfplatta eller stationär dator på intranätet.

> [!NOTE]  
> Med följande kommandouppsättning skapas CLIENT1 med Windows Server 2016 Datacenter, vilket kan göras för alla typer av Azure-prenumerationer. Om du har en Visual Studio-baserad Azure-prenumeration kan du skapa CLIENT1 med Windows 10 med hjälp av [Azure Portal](https://portal.azure.com).
  
Om du vill skapa en virtuell Azure-dator för CLIENT1 fyller du i namnet på resursgruppen och kör de här kommandona i kommandotolken på den lokala datorn.
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Anslut sedan till den virtuella datorn CLIENT1 med namnet och lösenordet för det lokala administratörskontot för CLIENT1 och öppna sedan en Windows PowerShell-kommandotolk på administratörsnivå.
  
Om du vill kontrollera namnmatchningen och nätverkskommunikationen mellan CLIENT1 och DC1 kör **ping dc1.testlab.**\<*your public domain name*> kommandot i Windows PowerShell kommandotolk och bekräfta att det finns fyra svar.
  
Anslut sedan den virtuella datorn CLIENT1 till TESTLAB-domänen med dessa kommandon i Windows PowerShell-kommandotolken.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Observera att du måste ange autentiseringsuppgifterna för TESTLAB\\User1-domänkontot när du har kört kommandot **Add-Computer**.
  
När CLIENT1 har startat om ansluter du den med TESTLAB\\User1-kontots namn och lösenord och öppnar sedan en Windows PowerShell-kommandotolk på administratörsnivå.
  
Verifiera sedan att du har åtkomst till webb- och fildelningsresurser på APP1 från CLIENT1.
  
1. Välj Lokal server i trädfönstret i **Serverhanteraren.**
    
2. I **Egenskaper för CLIENT1** väljer du **På** bredvid **IE Enhanced Security Configuration**.
    
3. I **Internet Explorer Enhanced Security Configuration** väljer du **Av** **för Administratörer** och **Användare** och sedan **OK.**
    
4. På Start-skärmen väljer du **Internet Explorer** och sedan **OK.**
    
5. I adressfältet anger du **http <span>://</span>app1.testab.** \<*your public domain name*> **/** och trycker sedan på **Retur.** Du bör se Internet Information Services-standardwebbsidan för APP1.
    
6. I aktivitetsfältet på skrivbordet väljer du ikonen för Utforskaren.
    
7. I adressfältet anger du **\\ \\ app1 \\ Filer** och trycker sedan på **Retur.** Du bör nu se ett mappfönster med innehållet i den delade mappen Filer.
    
8. I fönstret för den delade mappen **Filer** dubbelklickar du på filen **Example.txt**. Du bör se innehållet i filen Example.txt.
    
9. Stäng fönstren för **example.txt – Anteckningar** och den delade mappen **Filer**.
    
Din aktuella konfiguration ser ut så här:
  
![Steg 3 i baskonfiguration för simulerat företag](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a>Fas 2: Skapa en Microsoft 365 E5-prenumeration

I den här fasen skapar du en ny Microsoft 365 E5-prenumeration som använder en ny Azure AD-klientorganisation, en som är separat från din produktionsprenumeration. Du kan göra det på två olika sätt:

- Använd en utvärderingsprenumeration på Microsoft 365 E5.

  Utvärderingsprenumerationen på Microsoft 365 E5 är 30 dagar, som enkelt kan förlängas till 60 dagar. När utvärderingsprenumerationen går ut måste du göra om den till en betald prenumeration eller skapa en ny utvärderingsprenumeration. När du skapar nya utvärderingsprenumerationer lämnar du konfigurationen, som kan innehålla komplexa scenarier.  

- Använd en separat produktionsprenumeration på Microsoft 365 E5 med ett litet antal licenser.

  Detta är en extra kostnad, men ser till att du har en arbetstestmiljö som inte upphör att gälla. i den kan du prova funktioner, konfigurationer och scenarier. Du kan använda samma testmiljö på lång sikt för koncepttest, demonstration för kollegor och företagsledning samt utveckling och testning av program. Det är den rekommenderade metoden.

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registrera dig för en utvärderingsprenumeration på Office 365 E5

Från Azure-portalen ansluter du till CLIENT1 med CORP\User1-kontot.

Om du vill skapa en ny Office 365 E5-utvärderingsprenumeration följer du anvisningarna i [Fas 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) i den enkla baskonfigurationen i testlabbguiden.

Om du vill konfigurera den nya Office 365 E5-utvärderingsprenumeration följer du anvisningarna i [Fas 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) i den enkla baskonfigurationen i testlabbguiden.

#### <a name="using-an-office-365-e5-test-environment"></a>Använda en Office 365 E5-testmiljö

Om du bara behöver Office 365 en testmiljö behöver du inte läsa resten av den här artikeln.

Fler testlabbguider som gäller för både Microsoft 365 och Office 365 finns [i Microsoft 365 för testlabbguider för företag.](m365-enterprise-test-lab-guides.md)

### <a name="add-a-microsoft-365-e5-trial-subscription"></a>Lägga till en utvärderingsprenumeration på Microsoft 365 E5

Om du vill lägga Microsoft 365 E5 provprenumeration och konfigurera användarkonton med licenser utför du anvisningarna i Steg [3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) i testlabbguiden för enkel baskonfiguration.

  
## <a name="results"></a>Resultat

Din testmiljö har nu:
  
- Utvärderingsprenumeration på Microsoft 365 E5.
- Alla dina lämpliga användarkonton är aktiverade att använda Microsoft 365 E5.
- Ett simulerat och förenklat intranät.
    
Den slutliga konfigurationen ser ut så här:
  
![Fas 2 i baskonfiguration för simulerat företag](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
Du är nu redo att experimentera med ytterligare funktioner i [Microsoft 365 för företag.](https://www.microsoft.com/microsoft-365/enterprise)
  
## <a name="next-steps"></a>Nästa steg

Utforska dessa ytterligare uppsättningar testlabbguider:
  
- [Identitet](m365-enterprise-test-lab-guides.md#identity)
- [Hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Informationsskydd](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)