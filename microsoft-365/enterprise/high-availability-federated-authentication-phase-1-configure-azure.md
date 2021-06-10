---
title: Hög tillgänglighet federerad autentisering Fas 1 Konfigurera Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 91266aac-4d00-4b5f-b424-86a1a837792c
description: 'Sammanfattning: Konfigurera Microsoft Azure-infrastrukturen för federerad autentisering med hög tillgänglighet för Microsoft 365.'
ms.openlocfilehash: 7f9a935648fedd2c6235c443f7398f97c0a06e06
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929114"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a>Fas 1 med hög tillgänglighet för federerad autentisering: Konfigurera Azure

I den här fasen skapar du resursgrupper, virtuellt nätverk (VNet) och tillgänglighetsuppsättningar i Azure som ska vara värd för virtuella datorer i fas 2, 3 och 4. Du måste slutföra den här fasen innan du går vidare [till fas 2: Konfigurera domänkontrollanter](high-availability-federated-authentication-phase-2-configure-domain-controllers.md). Se [Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.
  
Azure måste tillhandahållas med följande grundläggande komponenter:
  
- Resursgrupper
    
- Ett virtuellt Azure-nätverk (VNet) på plats med undernät som värd för virtuella Azure-datorer
    
- Nätverkssäkerhetsgrupper för att utföra undernätsisolering
    
- Tillgänglighetsuppsättningar
    
## <a name="configure-azure-components"></a>Konfigurera Azure-komponenter

Innan du börjar konfigurera Azure-komponenter fyller du i följande tabeller. Skriv ut det här avsnittet och skriv ned den information som behövs eller kopiera avsnittet till ett dokument och fyll i det som behövs för att hjälpa dig med procedurerna för konfiguration av Azure. För inställningarna för VNet fyller du i Tabell V.
  
|**Objekt**|**Konfigurationsinställning**|**Beskrivning**|**Värde**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |VNet-namn  <br/> |Ett namn att tilldela till VNet (exempel FedAuthNet).  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |VNet-plats  <br/> |Det regionala Azure-datacenter som kommer att innehålla det virtuella nätverket.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |IP-adress för VPN-enhet  <br/> |Den offentliga IPv4-adressen till VPN-enhetens gränssnitt på Internet.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |VNet-adressutrymme  <br/> |Adressutrymmet för det virtuella nätverket. Ta reda på det här adressutrymmet tillsammans med IT-avdelningen.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|5.  <br/> |Delad IPsec-nyckel  <br/> |En slumpmässig alfanumerisk sträng med 32 tecken som används för att autentisera båda sidorna av VPN-anslutningen mellan webbplatser. Arbeta med IT- eller säkerhetsavdelningen för att fastställa det här nyckelvärdet. Alternativt kan du gå till [Skapa en slumpmässig sträng för en IPsec-fördelsnyckel](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabell V: Konfiguration av virtuellt nätverk på flera platser**
  
Fyll sedan i Tabell S för undernäten för den här lösningen. Alla adress blanksteg ska vara i CIDR-format (Classless Interdomain Routing), även kallat nätverksprefixformat. Ett exempel är 10.24.64.0/20.
  
För de första tre undernäten anger du ett namn och ett enda IP-adressutrymme baserat på det virtuella nätverksadressutrymmet. För gatewayundernätet bestämmer du 27-bitarsadressutrymmet (med prefixlängden /27) för Azure Gateway-undernätet med följande:
  
1. Ange de variabla bitarna i adressutrymmet för VNet till 1, upp till de bitar som används av gatewayundernätet, och ange sedan 0 för återstående bitar.
    
2. Konvertera de resulterande bitarna till decimalt och uttryck det som ett adressutrymme med prefixlängden inställd på storleken på gatewayundernätet.
    
Se [Adressutrymmeskalkylatorn för Azure Gateway-undernät](address-space-calculator-for-azure-gateway-subnets.md) för ett PowerShell-kommandoblock och C# eller Python-konsolprogram som utför den här beräkningen åt dig.
  
Arbeta med IT-avdelningen för att fastställa dessa adressutrymmen från det virtuella nätverksadressutrymmet.
  
|**Objekt**|**Undernätsnamn**|**Adressutrymme för undernät**|**Syfte**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |Undernätet som används av AD DS-domänkontrollanten (Active Directory Domain Services) och katalogsynkroniseringsserverns virtuella maskiner (VMs).  <br/> |
|2.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |Undernätet som används av AD FS VMs.  <br/> |
|3.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |Undernätet som används av virtuella proxyservrar för webbprogram.  <br/> |
|4.  <br/> |GatewaySubnet  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |Undernätet som används av virtuella maskiner för Azure Gateway.  <br/> |
   
 **Tabell S: Undernät i det virtuella nätverket**
  
Fyll sedan i tabell I för de statiska IP-adresserna som tilldelats virtuella maskiner och belastningsutjämningsinstanser.
  
|**Objekt**|**Syfte**|**IP-adress i undernätet**|**Värde**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Statisk IP-adress för den första domänkontrollanten  <br/> |Den fjärde möjliga IP-adressen för adressutrymmet för undernätet som definierats i objekt 1 i tabell S.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |Statisk IP-adress för den andra domänkontrollanten  <br/> |Den femte möjliga IP-adressen för adressutrymmet för undernätet som definieras i objekt 1 i Tabell S.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Statisk IP-adress för katalogsynkroniseringsservern  <br/> |Den sjätte möjliga IP-adressen för adressutrymmet för undernätet som definierats i objekt 1 i Tabell S.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |Statisk IP-adress för den interna belastningsutjämaren för AD FS-servrarna  <br/> |Den fjärde möjliga IP-adressen för adressutrymmet för undernätet som definieras i objekt 2 i tabell S.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|5.  <br/> |Statisk IP-adress för den första AD FS-servern  <br/> |Den femte möjliga IP-adressen för adressutrymmet för undernätet som definieras i objekt 2 i Tabell S.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|6.  <br/> |Statisk IP-adress för den andra AD FS-servern  <br/> |Den sjätte möjliga IP-adressen för adressutrymmet för undernätet som definierats i objekt 2 i Tabell S.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|7.  <br/> |Statisk IP-adress för den första proxyservern för webbprogrammet  <br/> |Den fjärde möjliga IP-adressen för adressutrymmet för undernätet som definieras i objekt 3 i Tabell S.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|8.  <br/> |Statisk IP-adress för den andra webbprogramproxyservern  <br/> |Den femte möjliga IP-adressen för adressutrymmet för undernätet som definieras i objekt 3 i Tabell S.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabell I: Statiska IP-adresser i det virtuella nätverket**
  
För två DNS-servrar (Domain Name System) i det lokala nätverket som du vill använda när du först bestäm om domänkontrollanterna i det virtuella nätverket fyller du i Tabell D. Ta reda på listan tillsammans med IT-avdelningen.
  
|**Objekt**|**Eget namn för DNS-server**|**IP-adress för DNS-server**|
|:-----|:-----|:-----|
|1.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabell D: Lokala DNS-servrar**
  
Om du vill dirigera paket från det lokala nätverket till organisationens nätverk via VPN-anslutningen mellan webbplatser måste du konfigurera det virtuella nätverket med ett lokalt nätverk som har en lista över adressplatserna (i CIDR-notation) för alla platser som kan nås i organisationens lokala nätverk. Listan med adressutrymmen som definierar ditt lokala nätverk måste vara unik och får inte överlappa det adressutrymme som används för andra virtuella nätverk eller andra lokala nätverk.
  
För de lokala nätverksadressutrymmena fyller du i Tabell L. Observera att tre tomma poster visas, men du behöver vanligtvis mer. Ta reda på listan med adressutrymmen tillsammans med IT-avdelningen.
  
|**Objekt**|**Lokalt nätverksadressutrymme**|
|:-----|:-----|
|1.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabell L: Adressprefix för det lokala nätverket**
  
Nu börjar vi bygga Azure-infrastrukturen för din externa autentisering för att Microsoft 365.
  
> [!NOTE]
> Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell. Se [Komma igång med Azure PowerShell](/powershell/azure/get-started-azureps). 
  
Börja med att Azure PowerShell och logga in på ditt konto.
  
```powershell
Connect-AzAccount
```

> [!TIP]
> Om du vill skapa PowerShell-kommandoblock som är färdiga att köra baserat på dina anpassade inställningar använder du den [här Microsoft Excel konfigurationsarbetsboken](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx). 

Hämta ditt prenumerationsnamn med följande kommando.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

För äldre versioner av Azure PowerShell ska du använda det här kommandot i stället.
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

Ange din Azure-prenumeration. Ersätt allt inom citattecknen, inklusive \< and >-tecknen med rätt namn.
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

Skapa sedan de nya resursgrupperna. Om du vill ta reda på en unik uppsättning namn på resursgrupper använder du det här kommandot för att lista de befintliga resursgrupperna.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Fyll i följande tabell för uppsättningen unika resursgruppnamn.
  
|**Objekt**|**Resursgruppnamn**|**Syfte**|
|:-----|:-----|:-----|
|1.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |Domänkontrollanter  <br/> |
|2.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |AD FS-servrar  <br/> |
|3.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |Proxyservrar för webbprogram  <br/> |
|4.  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |Infrastrukturelement  <br/> |
   
 **Tabell R: Resursgrupper**
  
Skapa de nya resursgrupperna med dessa kommandon.
  
```powershell
$locName="<an Azure location, such as West US>&quot;
$rgName=&quot;<Table R - Item 1 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
$rgName=&quot;<Table R - Item 2 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
$rgName=&quot;<Table R - Item 3 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
$rgName=&quot;<Table R - Item 4 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
```

Därefter skapar du det virtuella Azure-nätverket och dess undernät.
  
```powershell
$rgName=&quot;<Table R - Item 4 - Resource group name column>&quot;
$locName=&quot;<your Azure location>&quot;
$vnetName=&quot;<Table V - Item 1 - Value column>&quot;
$vnetAddrPrefix=&quot;<Table V - Item 4 - Value column>&quot;
$dnsServers=@( &quot;<Table D - Item 1 - DNS server IP address column>&quot;, &quot;<Table D - Item 2 - DNS server IP address column>" )
# Get the shortened version of the location
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the subnets
$subnet1Name="<Table S - Item 1 - Subnet name column>"
$subnet1Prefix="<Table S - Item 1 - Subnet address space column>"
$subnet1=New-AzVirtualNetworkSubnetConfig -Name $subnet1Name -AddressPrefix $subnet1Prefix
$subnet2Name="<Table S - Item 2 - Subnet name column>"
$subnet2Prefix="<Table S - Item 2 - Subnet address space column>"
$subnet2=New-AzVirtualNetworkSubnetConfig -Name $subnet2Name -AddressPrefix $subnet2Prefix
$subnet3Name="<Table S - Item 3 - Subnet name column>"
$subnet3Prefix="<Table S - Item 3 - Subnet address space column>"
$subnet3=New-AzVirtualNetworkSubnetConfig -Name $subnet3Name -AddressPrefix $subnet3Prefix
$gwSubnet4Prefix="<Table S - Item 4 - Subnet address space column>"
$gwSubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnet4Prefix

# Create the virtual network
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gwSubnet,$subnet1,$subnet2,$subnet3 -DNSServer $dnsServers

```

Därefter skapar du nätverkssäkerhetsgrupper för varje undernät som har virtuella datorer. Om du vill isolera undernät kan du lägga till regler för specifika typer av trafik som tillåts eller nekas till nätverkssäkerhetsgruppen för ett undernät.
  
```powershell
# Create network security groups
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName

New-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet1Name -AddressPrefix $subnet1Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet2Name -AddressPrefix $subnet2Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet3Name -AddressPrefix $subnet3Prefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

Använd sedan dessa kommandon för att skapa gateways för VPN-anslutningen mellan webbplatser.
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "GatewaySubnet"

# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -Subnet $subnet

# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig

# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix

# Define the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway

```

> [!NOTE]
> Federerad autentisering av enskilda användare är inte beroende av några lokala resurser. Men om den här VPN-anslutningen mellan webbplatser blir otillgänglig kommer domänkontrollanterna på VNet inte att få uppdateringar för användarkonton och grupper som gjorts i den lokala Active Directory Domain Services. Du kan säkerställa att det inte sker genom att konfigurera hög tillgänglighet för VPN-anslutningen mellan webbplatser. Mer information finns i [Mycket tillgänglig, tvärlokal anslutning och VNet-till-VNet-anslutning](/azure/vpn-gateway/vpn-gateway-highlyavailable)
  
Spela sedan in den offentliga IPv4-adressen för Azure VPN-gatewayen för ditt virtuella nätverk från visningen av det här kommandot:
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

Konfigurera sedan din lokala VPN-enhet för att ansluta till Azure VPN-gatewayen. Mer information finns i [Konfigurera din VPN-enhet.](/azure/vpn-gateway/vpn-gateway-about-vpn-devices)
  
För att konfigurera din lokala VPN-enhet behöver du följande:
  
- Den offentliga IPv4-adressen för Azure VPN-gatewayen.
    
- IPsec-fördelade nyckeln för VPN-anslutningen mellan webbplatser (Tabell V - Objekt 5 - Värdekolumnen).
    
Se sedan till att adressutrymmet i det virtuella nätverket kan nås från ditt lokala nätverk. Det görs vanligtvis genom att lägga till en route som motsvarar det virtuella nätverksadressutrymmet på din VPN-enhet och sedan annonsera den till resten av routningsinfrastrukturen i ditt organisations nätverk. Ta reda på hur du ska göra det med IT-avdelningen.
  
Definiera sedan namnen på tre tillgänglighetsuppsättningar. Fyll i Tabell A. 
  
|**Objekt**|**Syfte**|**Namn på tillgänglighetsuppsättning**|
|:-----|:-----|:-----|
|1.  <br/> |Domänkontrollanter  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |AD FS-servrar  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Proxyservrar för webbprogram  <br/> |![rad](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabell A: Tillgänglighetsuppsättningar**
  
Du behöver dessa namn när du skapar de virtuella maskinerna i faserna 2, 3 och 4.
  
Skapa de nya tillgänglighetsuppsättningarna med dessa Azure PowerShell kommandon.
  
```powershell
$locName="<the Azure location for your new resource group>"
$rgName="<Table R - Item 1 - Resource group name column>"
$avName="<Table A - Item 1 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 2 - Resource group name column>"
$avName="<Table A - Item 2 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 3 - Resource group name column>"
$avName="<Table A - Item 3 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
```

Det här är konfigurationen som är ett resultat av att den här fasen har slutförts.
  
**Fas 1: Azure-infrastrukturen för federerad autentisering med hög tillgänglighet för Microsoft 365**

![Fas 1 av hög tillgänglighet Microsoft 365 federerad autentisering i Azure med Azure-infrastrukturen](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a>Nästa steg

Använd [fas 2: Konfigurera domänkontrollanter så](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) att de kan fortsätta konfigurera den här arbetsbelastningen.
  
## <a name="see-also"></a>Se även

[Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Federerad identitet för din Microsoft 365 utvecklings-/testmiljö](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365-lösning och arkitekturcenter](../solutions/index.yml)

[Förstå Microsoft 365 identitet och Azure Active Directory](about-microsoft-365-identity.md)