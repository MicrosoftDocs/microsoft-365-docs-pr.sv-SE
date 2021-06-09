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
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a>Federerade identiteter i testmiljön för Microsoft 365

*Den här testlabbguiden kan användas för både Microsoft 365 för företag Office 365 Enterprise för testmiljöer.*

Microsoft 365 stöder federerade identiteter. Det innebär att i stället för att Microsoft 365 validerar autentiseringsuppgifterna själv, hänvisas användaren som ansluter till en federerad autentiseringsserver som är betrodd av Microsoft 365. Om användarens autentiseringsuppgifter är korrekta utfärdar den federerade autentiseringsservern en säkerhetstoken som klienten sedan skickar till Microsoft 365 som autentiseringsbevis. Federerade identiteter möjliggör avlastning och uppskalning av autentiseringen i en Microsoft 365-prenumeration, samt avancerade autentiserings- och säkerhetsscenarier.
  
I den här artikeln beskrivs hur du konfigurerar federerad autentisering för Microsoft 365 testmiljö, vilket resulterar i följande:

![Den federerade autentiseringen för Microsoft 365-testmiljön](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
Konfigurationen består av:
  
- En Microsoft 365 E5 provprenumeration eller produktionsprenumeration.
    
- Ett förenklat organisationsintranät som är anslutet till internet och består av fem virtuella datorer på ett undernät till ett virtuellt Azure-nätverk (DC1, APP1, CLIENT1, ADFS1 och PROXY1). Azure AD Anslut på APP1 för att synkronisera listan över konton i Active Directory Domain Services-domänen till Microsoft 365. PROXY1 tar emot inkommande autentiseringsbegäranden. ADFS1 validerar autentiseringsuppgifter med DC1 och utfärdar säkerhetstoken.
    
För inställning av den här testmiljön ingår fem faser:
- [Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fas 2: Skapa AD FS-servern](#phase-2-create-the-ad-fs-server)
- [Fas 3: Skapa webbproxyservern](#phase-3-create-the-web-proxy-server)
- [Fas 4: Skapa ett självsignerat certifikat och konfigurera ADFS1 och PROXY1.](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [Fas 5: Konfigurera Microsoft 365 för federerade identiteter](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> Du kan inte konfigurera den här testmiljön med en prenumeration på utvärderingsversionen av Azure.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön

Följ anvisningarna i [synkronisering av lösenordshash för Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Den resulterande konfigurationen ser ut så här:
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
Konfigurationen består av:
  
- En Microsoft 365 E5 utvärderingsversion eller betalda prenumerationer.
- Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk. Azure AD Anslut körs på APP1 för att synkronisera AD DS-domänen (TESTLAB Active Directory Domain Services) med Azure AD-klientorganisationen för dina Microsoft 365-prenumerationer med jämna mellanrum.

## <a name="phase-2-create-the-ad-fs-server"></a>Fas 2: Skapa AD FS-servern

En AD FS-server tillhandahåller federerad autentisering mellan Microsoft 365 och kontona på domänen corp.contoso.com som finns i DC1.
  
Om du vill skapa en virtuell Azure-dator för ADFS1, fyller du i namnet på prenumerationen, resursgruppen och Azure-platsen för baskonfigurationen. Kör sedan dessa kommandon i Azure PowerShell-kommandotolken på din lokala dator.
  
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

Använd sedan [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella ADFS1-datorn med det lokala administratörskontonamnet och lösenordet för ADFS1 och öppna en kommandotolk i Windows PowerShell.
  
Om du vill kontrollera namnmatchningen och nätverkskommunikationen mellan ADFS1 och DC1, kör du kommandot **ping dc1.corp.contoso.com** och kontrollerar att det finns fyra svar.
  
Anslut sedan den virtuella ADFS1-datorn till CORP-domänen med dessa kommandon i Windows PowerShell-kommandotolken på ADFS1.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

Den resulterande konfigurationen ser ut så här:
  
![AD FS-servern har lagts till i DirSync för Microsoft 365-testmiljön](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a>Fas 3: Skapa webbproxyservern

Med PROXY1 kan du använda proxy till autentiseringsmeddelanden mellan användare som försöker autentisera och ADFS1.
  
Om du vill skapa en virtuell Azure-dator för PROXY1 fyller du i namnet på din resursgrupp och Azure-plats och kör dessa kommandon i Azure PowerShell-kommandotolken på din lokala dator.
  
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
> PROXY1 tilldelas en statisk offentlig IP-adress eftersom du skapar en offentlig DNS-post som pekar på den. Denna får inte ändras när du startar om den virtuella PROXY1-datorn.
  
Lägg sedan till en regel i nätverkssäkerhetsgruppen för CorpNet-undernätet för att tillåta oombedd inkommande trafik från internet till PROXY1s privata IP-adress och TCP-port 443. Kör dessa kommandon i Azure PowerShell-kommandotolken på din lokala dator.
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

Använd sedan [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella PROXY1-datorn med det lokala administratörskontonamnet och lösenordet för PROXY1 och öppna en kommandotolk i Windows PowerShell för PROXY1.
  
Om du vill kontrollera namnmatchningen och nätverkskommunikationen mellan PROXY1 och DC1, kör du kommandot **ping dc1.corp.contoso.com** och kontrollerar att det finns fyra svar.
  
Anslut sedan den virtuella PROXY1-datorn till CORP-domänen med dessa kommandon i Windows PowerShell-kommandotolken på PROXY1.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

Visa den offentliga IP-adressen för PROXY1 med dessa Azure PowerShell kommandon på den lokala datorn.
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

Arbeta sedan med din offentliga DNS-leverantör och skapa en ny offentlig DNS A-post för **fs.testlab.**\<*your DNS domain name*> det löser att IP-adressen visas av kommandot **Write-Host**. **fs.testlab.**\<*your DNS domain name*> kallas i fortsättningen för *federationstjänstens FQDN*.
  
Använd sedan [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella DC1-datorn med hjälp av CORP\\User1-autentiseringsuppgifter och kör följande kommandon i en Windows PowerShell-kommandotolk på administratörsnivå:
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
Dessa kommandon skapar en intern DNS A-post så att virtuella datorer i det virtuella Azure-nätverket kan lösa den interna federationstjänstens FQDN till ADFS1s privata IP-adress.
  
Den resulterande konfigurationen ser ut så här:
  
![Webbprogrammets proxyserver har lagts till i DirSync för Microsoft 365-testmiljön](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a>Fas 4: Skapa ett självsignerat certifikat och konfigurera ADFS1 och PROXY1.

I den här fasen skapar du ett självsignerat digitalt certifikat för federationstjänstens FQDN. Därefter konfigurerar du ADFS1 och PROXY1 som en AD FS-servergrupp.
  
Först använder du [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella DC1-datorn med hjälp av CORP\\User1-autentiseringsuppgifterna och sedan öppnar du en Windows PowerShell-kommandotolk på administratörsnivå.
  
Skapa sedan ett AD FS-tjänstkonto med det här kommandot Windows PowerShell kommandotolken i DC1:
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
Observera att du uppmanas att ange lösenordet för kontot med detta kommando. Välj ett starkt lösenord och spara det på en säker plats. Du behöver den för den här fasen och för fas 5.
  
Använd [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella ADFS1-datorn med hjälp av CORP\\User1-autentiseringsuppgifterna. Öppna en Windows PowerShell-kommandotolk på administratörsnivå i ADFS1, fyll i FQDN för federationstjänsten och kör sedan följande kommandon för att skapa ett självsignerat certifikat:
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

Följ sedan de här anvisningarna för att spara det nya självsignerade certifikatet som en fil.
  
1. Välj **Start**, **mmc.exe** och tryck sedan på **Retur.**
    
2. Välj **Lägg**  >  **till/ta Fästa tillägg.**
    
3. In **Add or Remove Fästa-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.
    
4. I **Välj dator** väljer du **Slutför** och sedan **OK.**
    
5. Öppna **Certifikat (lokal dator) > Personlig > Certifikat** i mapplistan.
    
6. Välj och håll ned (eller högerklicka på) certifikatet med din FQDN för federationstjänsten, välj **Alla** uppgifter och välj sedan **Exportera**.
    
7. På **välkomstsidan** väljer du **Nästa.**
    
8. På sidan **Exportera privat** nyckel väljer du **Ja** och sedan **Nästa.**
    
9. På sidan **Exportera filformat väljer** du Exportera alla utökade **egenskaper** och sedan **Nästa.**
    
10. På sidan **Säkerhet** väljer du **Lösenord och** anger ett lösenord i **Lösenord** och **Bekräfta lösenord.**
    
11. På sidan **Fil som ska exporteras** väljer du **Bläddra**.
    
12. Bläddra till **mappen C: \\ Certs,** ange **SSL** **i filnamn** och välj sedan **Spara.**
    
13. Välj **Nästa på sidan** Fil som ska **exporteras.**
    
14. På sidan **Slutför guiden Exportera certifikat** väljer du **Slutför.** Välj OK när du **uppmanas att göra det.**
    
Installera sedan AD FS-tjänsten med detta kommando i Windows PowerShell-kommandotolken på ADFS1:
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

Vänta på att installationen slutförs.
  
Konfigurera sedan AD FS-tjänsten med följande steg:
  
1. Välj **Start** och sedan **serverhanterarens** ikon.
    
2. I trädfönstret i Serverhanteraren väljer du **AD FS**.
    
3. Välj den orange varningssymbolen i verktygsfältet högst upp och välj sedan **Konfigurera federationstjänsten på den här servern**.
    
4. På **välkomstsidan** i konfigurationsguiden Active Directory Federation Services väljer du **Nästa.**
    
5. På sidan **Anslut till AD DS** väljer du **Nästa**.
    
6. På sidan **Ange egenskaper för tjänst**:
    
  - För **SSL-certifikat** väljer du nedpilen och sedan certifikatet med namnet på din federationstjänsts FQDN.
    
  - I **Visningsnamn för federationstjänsten** anger du namnet på din fiktiva organisation.
    
  - Välj **Nästa**.
    
7. På sidan **Ange tjänstkonto** väljer du **Välj** för **kontonamn.**
    
8. I **Välj användarkonto eller tjänstkonto** anger du **ADFS-Service**, väljer **Kontrollera** namn och väljer sedan **OK.**
    
9. I **Kontolösenord** anger du lösenordet för ADFS-Service och väljer sedan **Nästa**.
    
10. På sidan **Ange konfigurationsdatabas** väljer du **Nästa.**
    
11. På sidan **Granskningsalternativ** väljer du **Nästa.**
    
12. På sidan **Kontroller som krävs** väljer du **Konfigurera**.

13. På sidan **Resultat** väljer du **Stäng**.
    
14. Välj **Start**, välj strömikonen, välj **Starta om** och välj sedan **Fortsätt**.
    
I [Azure-portalen](https://portal.azure.com) kan du ansluta till PROXY1 med autentiseringsuppgifterna för CORP\\User1-kontot.
  
Följ sedan de här anvisningarna för att installera det självsignerade certifikatet på **både PROXY1 och APP1**.
  
1. Välj **Start**, **mmc.exe** och tryck sedan på **Retur.**
    
2. Välj **Arkiv > Lägg till/Fästa tillägg.**
    
3. In **Add or Remove Fästa-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.
    
4. I **Välj dator** väljer du **Slutför** och sedan **OK.**
    
5. Öppna Personliga certifikat för **certifikat (lokal dator) i**  >    >  **trädfönstret.**
    
6. Markera och håll ned (eller högerklicka på) **Personlig**, välj **Alla uppgifter** och välj sedan **Importera**.
    
7. På **välkomstsidan** väljer du **Nästa.**
    
8. På sidan **Fil för import** anger du **\\ \\ adfs1-certs \\ \\ ssl.pfx** och väljer sedan **Nästa**.
    
9. På sidan **Private key protection** anger du certifikatlösenordet i **Lösenord** och väljer sedan **Nästa.**
    
10. På sidan **Certificate store** väljer du **Next.**
    
11. På sidan **Slutför** väljer du **Slutför**.
    
12. På sidan **Certificate Store** väljer du **Next**.
    
13. Välj OK när du **uppmanas att göra det.**
    
14. Välj Certifikat i **trädfönstret.**
    
15. Välj och håll ned (eller högerklicka på) certifikatet och välj sedan **Kopiera**.
    
16. I trädfönstret öppnar du **Betrodda certifikat för rotcertifikatutfärdare.**  >  
    
17. Flytta muspekaren nedanför listan med installerade certifikat, markera och håll ned (eller högerklicka) och välj sedan Klistra **in**.
    
Öppna en PowerShell-kommandotolk på administratörsnivå och kör följande kommando:
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

Vänta på att installationen slutförs.
  
Använd följande steg för att konfigurera att tjänsten Webbprogramproxy ska använda ADFS1 som federationsserver:
  
1. Välj **Start** och sedan **Serverhanteraren.**
    
2. Välj Fjärråtkomst i **trädfönstret.**
    
3. Välj den orange varningssymbolen i verktygsfältet högst upp och välj sedan **Öppna proxyguiden för webbprogram.**
    
4. På **välkomstsidan** i konfigurationsguiden Proxykonfiguration för webbprogram väljer du **Nästa.**
    
5. På sidan **Federationsserver**:
    
  - I rutan **Federationstjänstnamn** anger du FQDN för federationstjänsten.
    
  - I rutan **Användarnamn anger** du **CORP \\ Användare1**.
    
  - I rutan **Lösenord** anger du lösenordet för User1-kontot.
    
  - Välj **Nästa**.
    
6. På sidan **AD FS-proxycertifikat** väljer du nedåtpilen, väljer certifikatet med federationstjänstens FQDN och väljer sedan **Nästa.**
    
7. På **bekräftelsesidan** väljer du **Konfigurera**.
    
8. På sidan **Resultat** väljer du **Stäng**.
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a>Fas 5: Konfigurera Microsoft 365 för federerade identiteter

Använd [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella APP1-datorn med hjälp av CORP\\User1-autentiseringsuppgifterna.
  
Använd följande steg för att konfigurera Azure AD Connect och din Microsoft 365-prenumeration för federerad autentisering:
  
1. Dubbelklicka på **Azure AD Connect** på skrivbordet.
    
2. På sidan **Välkommen till Azure AD Anslut** väljer du **Konfigurera**.
    
3. På sidan **Ytterligare uppgifter** väljer du Ändra inloggning **för användare** och sedan **Nästa.**
    
4. På sidan **Anslut till Azure AD** anger du namnet och lösenordet för ditt globala administratörskonto och väljer sedan **Nästa.**
    
5. På **inloggningssidan för användaren** väljer du **Federation med AD FS** och sedan **Nästa.**
    
6. På **sidan AD FS-servergruppen** väljer du Använd en befintlig **AD FS-servergrupp**, anger **ADFS1** i rutan **Servernamn** och väljer sedan **Nästa.**
    
7. När du uppmanas att ange serverautentiseringsuppgifter anger du autentiseringsuppgifterna för CORP \\ User1-kontot och väljer sedan **OK.**
    
8. På sidan **Autentiseringsuppgifter för** domänadministratör anger  du **CORP \\ User1** i  rutan Användarnamn, anger lösenordet för kontot i rutan Lösenord och väljer sedan **Nästa.**
    
9. På sidan AD **FS-tjänstkonto** anger du **CORP \\ ADFS-Service** i rutan  **Domain Username,** anger lösenordet för kontot i rutan Domänanvändarlösenord och väljer **sedan Nästa**.
    
10. På sidan **Azure AD Domain,** i **Domain**, väljer du namnet på den domän som du tidigare skapade och lade till i din prenumeration i fas 1, och väljer sedan **Nästa.**
    
11. På sidan **Är redo att konfigurera** väljer du **Konfigurera**.
    
12. På sidan **Installationen är** klar väljer du **Verifiera**.
    
    Du bör se meddelanden som anger att både intranätet och Internetkonfigurationen har verifierats.
    
13. På sidan **Installationen är klar** väljer du **Avsluta.**
    
Visa att den federerade autentiseringen fungerar:
  
1. Öppna en ny privat instans av webbläsaren på din lokala dator och gå till [https://admin.microsoft.com](https://admin.microsoft.com).
    
2. För inloggningsuppgifterna anger du **user1@** \<*the domain created in Phase 1*> .
    
    Om testdomänen till exempel **är testlab.contoso.com** anger du "user1@testlab.contoso.com". Tryck på **Tabb eller** tillåt Microsoft 365 omdirigera dig automatiskt.
    
    Nu bör du se sidan **Din anslutning är inte privat**. Du ser detta eftersom du har installerat ett själv signerat certifikat på ADFS1 som den stationära datorn inte kan verifiera. I en produktionsdistribution av federerad autentisering använder du ett certifikat från en betrodd certifikatutfärdare för att dina användare inte ska se den här sidan.
    
3. På sidan **Din anslutning är inte privat** väljer du **Avancerat** och sedan **Fortsätt till \<*your federation service FQDN*>**. 
    
4. Logga in med följande på sidan med namnet på din fiktiva organisation:
    
  - **CORP\\User1** som namn
    
  - Lösenordet för User1-kontot
    
    Du bör se **startsidan för Microsoft Office**.
    
Proceduren visar att utvärderingsprenumerationen är federerad med AD DS corp.contoso.com-domänen som finns i DC1. Här följer grundläggande information om autentiseringsprocessen:
  
1. När du använder den federerade domänen som du skapade i fas 1 i namnet på inloggningskontot, dirigerar Microsoft 365 webbläsaren till federationstjänstens FQDN och PROXY1.
    
2. PROXY1 skickar din lokala dator till inloggningssidan för det fiktiva företaget.
    
3. När du skickar CORP\\User1 och lösenordet till PROXY1, vidarebefordras det till ADFS1.
    
4. ADFS1 validerar CORP\\User1 och lösenordet med DC1 och skickar en säkerhetstoken till din lokala dator.
    
5. Din lokala dator skickar säkerhetstoken till Microsoft 365.
    
6. Microsoft 365 kontrollerar att denna säkerhetstoken har skapats av ADFS1 och tillåter åtkomst.
    
Utvärderingsprenumerationen har nu konfigurerats med federerad autentisering. Du kan använda den här utvecklings-/testmiljön för avancerade autentiseringsscenarier.
  
## <a name="next-step"></a>Nästa steg

När du är redo att distribuera produktionsklar, federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure kan du gå till Distribuera [federerad](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)och Microsoft 365 hög tillgänglighet i Azure.
  
