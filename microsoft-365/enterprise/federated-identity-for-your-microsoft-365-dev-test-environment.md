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
ms.openlocfilehash: c7ff838522c0bd97da4ffff5122454b128f97bf2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694859"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a>Federerade identiteter i testmiljön för Microsoft 365

*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*

Microsoft 365 stöder federerade identiteter. Det innebär att i stället för att Microsoft 365 validerar autentiseringsuppgifterna själv, hänvisas användaren som ansluter till en federerad autentiseringsserver som är betrodd av Microsoft 365. Om användarens autentiseringsuppgifter är korrekta utfärdar den federerade autentiseringsservern en säkerhetstoken som klienten sedan skickar till Microsoft 365 som autentiseringsbevis. Federerade identiteter möjliggör avlastning och uppskalning av autentiseringen i en Microsoft 365-prenumeration, samt avancerade autentiserings- och säkerhetsscenarier.
  
I den här artikeln beskrivs hur du kan konfigurera federerad inloggningsautentisering för test miljön för Microsoft 365, vilket leder till följande:

![Den federerade autentiseringen för Microsoft 365-testmiljön](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
Konfigurationen består av: 
  
- En utvärderings version av Microsoft 365 E5 eller Product.
    
- Ett förenklat företagsintranät som är anslutet till Internet. Det består av fem virtuella datorer i ett undernät i ett virtuellt Azure-nätverk (DC1, APP1, CLIENT1, ADFS1 och PROXY1). Azure AD Connect körs på APP1 för att synkronisera listan över konton i Active Directory Domain Services-domänen till Microsoft 365. PROXY1 tar emot inkommande autentiseringsbegäranden. ADFS1 validerar autentiseringsuppgifter med DC1 och utfärdar säkerhetstoken.
    
Konfigurationen av testmiljön består av fem faser:
  
1. Skapa testmiljön för det simulerade företaget med synkronisering av lösenordshash.
    
2. Skapa en AD FS-server (ADFS1).
    
3. Skapa webbproxyservern (PROXY1).
    
4. Skapa ett självsignerat certifikat och konfigurera ADFS1 och PROXY1.
    
5. Konfigurera Microsoft 365 för federerade identiteter.
    
> [!NOTE]
> Du kan inte konfigurera testmiljön med en Azure-utvärderingsprenumeration. 
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön

Följ anvisningarna i [synkronisering av lösenordshash för Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Här är konfigurationsresultatet.
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
Konfigurationen består av: 
  
- En utvärderings version av Microsoft 365 E5 eller betalda prenumerationer.
- Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk. Azure AD Connect körs på APP1 för att synkronisera TESTLAB AD DS-domänen med Azure AD-klientorganisationen för dina Microsoft 365-prenumerationer regelbundet.

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

Här är konfigurationsresultatet.
  
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
  
Lägg sedan till en regel i nätverkssäkerhetsgruppen för CorpNet-undernätet som tillåter oombedd inkommande trafik från Internet till den privata IP-adressen och TCP-porten 443 i PROXY1. Kör dessa kommandon i Azure PowerShell-kommandotolken på din lokala dator.
  
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

Visa den offentliga IP-adressen för PROXY1 med följande Azure PowerShell-kommandon på din lokala dator:
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

Arbeta sedan med din offentliga DNS-leverantör och skapa en ny offentlig DNS A-post för **fs.testlab.**\<your DNS domain name> det löser att IP-adressen visas av kommandot **Write-Host**. **fs.testlab.**\<your DNS domain name> kallas i fortsättningen för *federationstjänstens FQDN*.
  
Använd sedan [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella DC1-datorn med hjälp av CORP\\User1-autentiseringsuppgifter och kör följande kommandon i en Windows PowerShell-kommandotolk på administratörsnivå:
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
Med dessa kommandon skapar du en intern DNS-post för att virtuella datorer i det virtuella Azure-nätverket ska kunna matcha den interna federationens FQDN med den privata IP-adressen i ADFS1.
  
Här är konfigurationsresultatet.
  
![Webbprogrammets proxyserver har lagts till i DirSync för Microsoft 365-testmiljön](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a>Fas 4: Skapa ett självsignerat certifikat och konfigurera ADFS1 och PROXY1.

I den här fasen skapar du ett självsignerat digitalt certifikat för federationstjänstens FQDN. Därefter konfigurerar du ADFS1 och PROXY1 som en AD FS-servergrupp.
  
Först använder du [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella DC1-datorn med hjälp av CORP\\User1-autentiseringsuppgifterna och sedan öppnar du en Windows PowerShell-kommandotolk på administratörsnivå.
  
Skapa sedan AD FS-tjänstkontot med detta kommando i Windows PowerShell-kommandotolken på DC1:
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
Observera att du uppmanas att ange lösenordet för kontot med detta kommando. Välj ett starkt lösenord och spara det på en säker plats. Du behöver det i den här fasen och i fas 5.
  
Använd [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella ADFS1-datorn med hjälp av CORP\\User1-autentiseringsuppgifterna. Öppna en Windows PowerShell-kommandotolk på administratörsnivå i ADFS1, fyll i FQDN för federationstjänsten och kör sedan följande kommandon för att skapa ett självsignerat certifikat:
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

Följ sedan de här anvisningarna för att spara det nya självsignerade certifikatet som en fil.
  
1. Klicka på **Start**, skriv **mmc.exe** och tryck på **Retur**.
    
2. Klicka på **Arkiv > Lägg till/ta bort snapin-modul**.
    
3. I **Lägg till eller ta bort snapin-moduler** dubbelklickar du på **Certifikat** i listan med tillgängliga snapin-moduler. Klicka på **Datorkonto** och sedan på **Nästa**.
    
4. I **Välj dator** klickar du på **Slutför** och sedan på **OK**.
    
5. Öppna **Certifikat (lokal dator) > Personlig > Certifikat** i mapplistan.
    
6. Högerklicka på certifikatet med federationstjänstens FQDN, klicka på **Alla uppgifter** och sedan på **Exportera**.
    
7. På sidan **Välkommen** klickar du på **Nästa**.
    
8. Klicka på **Ja** på sidan **Exportera privat nyckel** och klicka sedan på **Nästa**.
    
9. Klicka på **Exportera alla utökade egenskaper** och sedan på **Nästa** på sidan **Exportera filformat**.
    
10. På sidan **Säkerhet** klickar du på **Lösenord** och anger ett lösenord i **Lösenord** och **Bekräfta lösenordet.**
    
11. På sidan **Fil att exportera** klickar du på **Bläddra**.
    
12. Bläddra till mappen **C:\\Certs**, skriv **SSL** i **Filnamn** och klicka sedan på **Spara.**
    
13. På sidan **Fil att exportera** klickar du på **Nästa**.
    
14. Klicka på **Slutför** på sidan **Slutför guiden Exportera certifikat**. Klicka på **OK** när du uppmanas att göra det.
    
Installera sedan AD FS-tjänsten med detta kommando i Windows PowerShell-kommandotolken på ADFS1:
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

Vänta på att installationen slutförs.
  
Konfigurera sedan AD FS-tjänsten med följande steg:
  
1. Klicka på **Start** och sedan på ikonen **Serverhanteraren**.
    
2. I mapplistan i Serverhanteraren klickar du på **AD FS**.
    
3. I verktygsfältet högst upp klickar du på den orange varningssymbolen och sedan på **Konfigurera federationstjänsten på den här servern**.
    
4. På sidan **Välkommen** i konfigurationsguiden för Active Directory Federation Services klickar du på **Nästa**.
    
5. På sidan **Anslut till AD DS** klickar du på **Nästa**.
    
6. På sidan **Ange egenskaper för tjänst**:
    
  - Om du vill använda **SSL-certifikat** klickar du på nedåtpilen och sedan på certifikatet med namnet på federationstjänstens FQDN.
    
  - I **Federationstjänstens visningsnamn** skriver du namnet på din fiktiva organisation.
    
  - Klicka på **Nästa**.
    
7. På sidan **Ange tjänstkonto** klickar du på **Välj** för **Kontonamn**.
    
8. I **Välj användar- eller tjänstkonto** skriver du **ADFS-Service**, klickar på **Kontrollera namn** och sedan på **OK**.
    
9. I **Kontolösenord** skriver du lösenordet för kontot ADFS-Service och klickar sedan på **Nästa**.
    
10. På sidan **Ange konfigurationsdatabas** klickar du på **Nästa**.
    
11. På sidan **Granskningsalternativ** klickar du på **Nästa**.
    
12. På sidan **Kravkontroller** klickar du på **Konfigurera**.
    
13. På sidan **Resultat** klickar du på **Stäng**.
    
14. Klicka på **Start**, klicka på strömbrytarikonen, klicka på **Starta om** och klicka sedan på **Fortsätt**.
    
I [Azure-portalen](https://portal.azure.com) kan du ansluta till PROXY1 med autentiseringsuppgifterna för CORP\\User1-kontot.
  
Följ sedan de här anvisningarna för att installera det självsignerade certifikatet på **både PROXY1 och APP1**.
  
1. Klicka på **Start**, skriv **mmc.exe** och tryck på **Retur**.
    
2. Klicka på **Arkiv > Lägg till/ta bort snapin-modul**.
    
3. I **Lägg till eller ta bort snapin-moduler** dubbelklickar du på **Certifikat** i listan med tillgängliga snapin-moduler. Klicka på **Datorkonto** och sedan på **Nästa**.
    
4. I **Välj dator** klickar du på **Slutför** och sedan på **OK**.
    
5. Öppna **Certifikat (lokal dator) > Personlig > Certifikat** i mapplistan.
    
6. Högerklicka på **Personlig**, klicka på **Alla uppgifter** och klicka sedan på **Importera**.
    
7. På sidan **Välkommen** klickar du på **Nästa**.
    
8. På sidan **Fil att importera** skriver du **\\\\adfs1\\certs\\ssl.pfx** och klickar sedan på **Nästa**.
    
9. På sidan **Skydd av privat nyckel** anger du lösenordet för certifikatet i **Lösenord** och klickar sedan på **Nästa.**
    
10. På sidan **Certifikatarkiv** klickar du på **Nästa.**
    
11. Klicka på **Slutför** på sidan **Slutför**.
    
12. På sidan **Certifikatarkiv** klickar du på **Nästa**.
    
13. Klicka på **OK** när du uppmanas att göra det.
    
14. Klicka på **Certifikat** i mapplistan.
    
15. Högerklicka på certifikatet och klicka sedan på **Kopiera**.
    
16. I mapplistan öppnar du **Betrodda rotcertifikatutfärdare > Certifikat**.
    
17. Flytta muspekaren nedanför listan med installerade certifikat, högerklicka och klicka sedan på **Klistra in**.
    
Öppna en PowerShell-kommandotolk på administratörsnivå och kör följande kommando:
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

Vänta på att installationen slutförs.
  
Använd följande steg för att konfigurera att tjänsten Webbprogramproxy ska använda ADFS1 som federationsserver:
  
1. Klicka på **Start** och sedan på **Serverhanteraren**.
    
2. I mapplistan klickar du på **Fjärråtkomst**.
    
3. I verktygsfältet högst upp klickar du på den orange varningssymbolen och sedan på **Öppna guiden Webbprogramproxy**.
    
4. På sidan **Välkommen** i guiden Webbprogramproxy klickar du på **Nästa**.
    
5. På sidan **Federationsserver**:
    
  - Skriv in federationstjänstens FQDN i **Federationstjänstens namn**.
    
  - Skriv **CORP\\User1** i **Användarnamn**.
    
  - Skriv in lösenordet för User1-kontot i **Lösenord**.
    
  - Klicka på **Nästa**.
    
6. På sidan **AD FS-proxycertifikat** klickar du på nedåtpilen och sedan på certifikatet med federationstjänstens FQDN. Klicka sedan på **Nästa**.
    
7. På sidan **Bekräftelse** klickar du på **Konfigurera**.
    
8. På sidan **Resultat** klickar du på **Stäng**.

    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a>Fas 5: Konfigurera Microsoft 365 för federerade identiteter

Använd [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella APP1-datorn med hjälp av CORP\\User1-autentiseringsuppgifterna.
  
Använd följande steg för att konfigurera Azure AD Connect och din Microsoft 365-prenumeration för federerad autentisering:
  
1. Dubbelklicka på **Azure AD Connect** på skrivbordet.
    
2. På sidan **Välkommen till Azure AD Connect** klickar du på **Konfigurera**.
    
3. På sidan **Ytterligare aktiviteter** klickar du på **Ändra användarinloggning** och sedan på **Nästa**.
    
4. På sidan **Anslut till Azure AD** skriver du kontonamn och lösenord för en global administratör. Klicka sedan på **Nästa**.
    
5. På sidan **Användarinloggning** klickar du på **Federation med AD FS** och sedan på **Nästa**.
    
6. På sidan **AD FS-servergrupp** klickar du på **Använd en befintlig AD FS-servergrupp**. Skriv **ADFS1** i **Servernamn** och klicka sedan på **Nästa**.
    
7. När du uppmanas att ange autentiseringsuppgifter för server anger du autentiseringsuppgifterna för kontot CORP\\User1. Klicka sedan på **OK**.
    
8. På sidan med autentiseringsuppgifter för **Domänadministratör** skriver du **CORP\\User1** i **Användarnamn** och lösenordet för kontot i **Lösenord**. Klicka sedan på **Nästa**.
    
9. På sidan **AD FS-tjänstekonto** skriver du **CORP\\ADFS-Service** i **Domänanvändarnamn** och lösenordet för kontot i **Lösenord för domänanvändare**. Klicka sedan på **Nästa**.
    
10. På sidan **Azure AD-domän** i **Domän** väljer du namnet på den domän som du tidigare skapade och lade till i din prenumeration i fas 1. Klicka sedan på **Nästa**.
    
11. Klicka på **Konfigurera** på sidan **Klart att konfigurera**.
    
12. På sidan **Installationen är slutförd** klickar du på **Verifiera**.
    
    Du bör se meddelanden som anger att konfigurationen av både intranät och Internet har verifierats.
    
13. På sidan **Installationen är slutförd** klickar du på **Avsluta**.
    
Visa att den federerade autentiseringen fungerar:
  
1. Öppna en ny privat instans av webbläsaren på din lokala dator och gå till [https://admin.microsoft.com](https://admin.microsoft.com).
    
2. För inloggningsuppgifterna skriver du **user1@**\<the domain created in Phase 1>. 
    
    Om din testdomän exempelvis är **testlab.contoso.com**skriver du ”user1@testlab.contoso.com”. Tryck på TABB-tangenten eller tillåt att Microsoft 365 omdirigerar dig automatiskt.
    
    Nu bör du se sidan **Din anslutning är inte privat**. Den visas eftersom du har installerat ett självsignerat certifikat på ADFS1 som din stationära dator inte kan verifiera. I en produktionsdistribution av federerad autentisering använder du ett certifikat från en betrodd certifikatutfärdare för att dina användare inte ska se den här sidan.
    
3. På sidan **Din anslutning inte är privat** klickar du på **Avancerat** och sedan på **Fortsätt till \<your federation service FQDN>**. 
    
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

När du är redo att distribuera produktion-redo, federerad för hög tillgänglighet för Microsoft 365 i Azure läser du [distribuera federerad auktorisering med hög tillgänglighet för microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).
  
