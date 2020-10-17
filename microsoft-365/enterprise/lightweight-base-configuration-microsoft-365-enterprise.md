---
title: Enkel baskonfiguration
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
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
description: Använd den här test laboratorie guiden för att skapa en lätt test miljö för att testa Microsoft 365 för företag.
ms.openlocfilehash: 2b8505e142c3c1b87578db7342ed299b95d8c049
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487394"
---
# <a name="the-lightweight-base-configuration"></a>Den enkla baskonfigurationen

*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*

I den här artikeln beskrivs hur du skapar en förenklad miljö med ett Microsoft 365 E5-abonnemang och en dator med Windows 10 Enterprise.

![Den förenklade testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Att skapa en lättviktig test miljö omfattar fem faser:
- [Fas 1: skapa ditt Microsoft 365 E5-abonnemang](#phase-1-create-your-microsoft-365-e5-subscription)
- [Fas 2: Konfigurera utvärderingsprenumerationen för Office 365](#phase-2-configure-your-office-365-trial-subscription)
- [Fas 3: Lägga till en utvärderingsprenumeration på Microsoft 365 E5](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [Fas 4: Skapa en Windows 10 Enterprise-dator](#phase-4-create-a-windows-10-enterprise-computer)
- [Fas 5: Ansluta Windows 10-datorn till Azure AD](#phase-5-join-your-windows-10-computer-to-azure-ad)

Använd den resulterande miljön för att testa funktionerna i [Microsoft 365 för företag](https://www.microsoft.com/microsoft-365/enterprise).

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> En visuell karta till alla artiklar i en test laboratorie guide för Microsoft 365 för Enterprise-testlabb finns i [gruppen microsoft 365 for the Enterprise Test Lab](../downloads/Microsoft365EnterpriseTLGStack.pdf).

>[!NOTE]
>Det kan vara bra att skriva ut den här artikeln för att kunna skriva ned den specifika information som du behöver för den här miljön under de 30 dagar som Office 365-utvärderingsprenumerationen gäller. Du kan enkelt utöka utvärderingsprenumerationen i ytterligare 30 dagar. För en permanent testmiljö skapar du en ny betald prenumeration med en separat Azure AD-klient och ett litet antal licenser.

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>Fas 1: skapa ditt Microsoft 365 E5-abonnemang

Vi börjar med ett Microsoft 365 E5-prov abonnemang och lägger sedan till Microsoft 365 E5-abonnemanget.

>[!NOTE]
>Vi rekommenderar att du skapar en utvärderings version av Office 365 så att test miljön har en särskild Azure AD-klient organisation från alla betalda prenumerationer som du för närvarande har. Denna separation innebär att du kan lägga till och ta bort användare och grupper i test innehavaren utan att påverka dina produktions abonnemang.

För att starta ett Microsoft 365 E5-prov abonnemang behöver du först ett fiktivt företags namn och ett nytt Microsoft-konto.
  
1. Vi rekommenderar att du använder en variant av företagsnamnet Contoso som ditt företagsnamn, vilket är ett fiktivt företag som används i Microsoft-exempelinnehåll, men det är inget krav. Skriv ditt fiktiva företagsnamn här: ![Rad](../media/Common-Images/TableLine.png)
    
2. Om du vill registrera dig för ett nytt Microsoft-konto går du till [https://outlook.com](https://outlook.com) och skapar ett konto med ett nytt e-postkonto och en ny e-postadress. Du använder det här kontot för att registrera dig för Office 365.
    
    - Skriv för- och efternamn för ditt nya konto här: ![Rad](../media/Common-Images/TableLine.png)
    
    - Skriv den nya adressen för e-postkontot här: ![Rad](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registrera dig för en utvärderingsprenumeration på Office 365 E5

1. I webbläsaren går du till [https://aka.ms/e5trial](https://aka.ms/e5trial) .
    
2. I steg 1 i det här steget **för att välja Office 365 E5** -sidan anger du din e-postadress.
3. I steg 2 i arbets abonnemangs processen anger du den begärda informationen och utför sedan verifieringen.
4. I steg 3 anger du ett organisations namn och sedan ett konto namn som kommer att vara den globala administratören för abonnemanget.
5. För steg 4 skriver du inloggningssidan här (markera och kopiera): ![Rad](../media/Common-Images/TableLine.png)
6. Skriv användar-ID här: ![Rad](../media/Common-Images/TableLine.png).onmicrosoft.com  
   Spela in lösen ordet du angav på en säker plats.
   Det här värdet kommer att kallas för det **globala administratörsnamnet**.
7. Välj **gå till installations programmet**.
8. I inställningar för Office 365 E5 väljer du **Fortsätt använda *organisationen*. onmicrosoft.com för e-post och logga in**och välj sedan **Avsluta och fortsätt senare**.

Du bör se administrationscentret för Microsoft 365.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Fas 2: Konfigurera utvärderingsprenumerationen för Office 365

I den här fasen konfigurerar du prenumerationen med ytterligare användare och tilldelar dem Office 365 E5-licenser.
  
Om du vill ansluta till din prenumeration med Azure Active Directory PowerShell för Graph-moduler från datorn kan du använda anvisningarna i [ansluta till Microsoft 365 med PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
    
I dialog rutan **begäran om autentiseringsuppgifter för Windows PowerShell** anger du det globala administratörs namnet (till exempel *jdoe@contosotoycompany.onmicrosoft.com*) och lösen ord.
  
Fyll i organisationens namn (till exempel *contosotoycompany*), lands koden med två tecken för platsen, ett gemensamt konto lösen ord och kör sedan följande kommandon från PowerShell-uppmaningen:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> Användningen av ett gemensamt lösenord här är för automatisering och enklare konfiguration för en testmiljö. Självklart rekommenderas detta inte för produktionsprenumerationer. 

### <a name="record-key-information-for-future-reference"></a>Skriv ned viktig information för framtida referens

Om du inte redan har spelat in dessa värden kan du spela in dem nu:
  
- Namn på global administratör: ![Rad](../media/Common-Images/TableLine.png).onmicrosoft.com (från steg 6 i fas 1)
    
    Anteckna också lösenordet för det här kontot på en säker plats.
    
- Organisationens namn för utvärderingsprenumerationen: ![Rad](../media/Common-Images/TableLine.png) (från steg 4 i fas 1)
    
- Om du vill lista kontona för Användare 2, Användare 3, Användare 4 och Användare 5 kör du följande kommando från Windows Azure Active Directory-modulen för Windows PowerShell-prompten:
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    Skriv kontonamnen här:
    
  - Kontonamn för Användare 2: användare2@![Rad](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Kontonamn för Användare 3: användare3@![Rad](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Kontonamn för Användare 4: användare4@![Rad](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Kontonamn för Användare 5: användare5@![Rad](../media/Common-Images/TableLine.png).onmicrosoft.com
    
    Anteckna också det gemensamma lösenordet för dessa konton på en säker plats.
   
### <a name="using-an-office-365-test-environment"></a>Använda en Office 365-testmiljö

Om du bara behöver en test miljö för Office 365 behöver du inte läsa resten av den här artikeln.

Ytterligare test labb guider som gäller både Office 365 och Microsoft 365 finns i [Microsoft 365 för Enterprise Test Lab-guider](m365-enterprise-test-lab-guides.md).
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Fas 3: Lägga till en utvärderingsprenumeration på Microsoft 365 E5

I den här fasen registrerar du dig för Microsoft 365 E5-utvärderingsprenumerationen och lägger till den i samma organisation som utvärderingsprenumerationen för Office 365 E5.
  
Lägg först till Microsoft 365 E5-utvärderingsprenumerationen och tilldela den nya licensen för Microsoft 365 till det globala administratörskontot.
  
1. I en webbläsares privata fönster använder du dina globala administratörs konto uppgifter för att logga in på administrations centret för Microsoft 365 på [https://admin.microsoft.com](https://admin.microsoft.com) .
    
2. I det vänstra navigerings fältet på sidan **administrations Center för Microsoft 365** väljer du **fakturerings > Köp tjänster**.
    
3. På sidan **Köp tjänster** väljer du **Microsoft 365 E5**och sedan **Hämta gratis prov**.

4. På **utvärderings sidan för Microsoft 365 E5** kan du välja att ta emot ett textmeddelande eller ett telefonsamtal, ange ditt telefonnummer och sedan välja **SMS** eller **Ring mig**. Utför verifieringen.

5. På sidan **Bekräfta din beställning** väljer du **prova nu**.

6. På sidan **order kvitto** väljer du **Fortsätt**.

7. Välj **användare > aktiva användare**i administrations centret för Microsoft 365.

8. I **aktiva användare**väljer du ditt administratörs konto.

9. Välj **licenser och appar**.

10. Inaktivera licensen för Office 365 Enterprise, E5 och aktivera licensen för Microsoft 365 E5.

11. Välj **Spara ändringar**och stäng sedan fönstret användar konto information.

Upprepa sedan steg 8 till 11 i föregående procedur för alla andra konton (Användare 2, Användare 3, Användare 4 och Användare 5).
  
> [!NOTE]
> Längden på Microsoft 365 E5 prov prenumerationen är 30 dagar. För en permanent testmiljö omvandlar du den här utvärderingsprenumeration till en betald prenumeration med ett litet antal licenser.
  
Din testmiljö har nu:
  
- En utvärderingsprenumeration på Microsoft 365 E5.
- Alla relevanta användarkonton (antingen bara det globala administratörskontot eller alla fem användarkonton) är aktiverade för att använda Microsoft 365 E5.
    
Din resulterande konfiguration, som lägger till Microsoft 365 E5, ser ut så här:
  
![Fas 3 av testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Fas 4: Skapa en Windows 10 Enterprise-dator

I den här fasen skapar du en fristående dator med Windows 10 Enterprise som en fysisk dator, en virtuell dator eller en virtuell Azure-dator.
  
### <a name="physical-computer"></a>Fysisk dator

Installera Windows 10 Enterprise på en dator. Du kan ladda ned utvärderingsversionen av Windows 10 Enterprise [här](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine"></a>Virtuell dator

Använd hypervisor-programmet för att skapa en virtuell dator och installera sedan Windows 10 Enterprise på det. Du kan ladda ned utvärderingsversionen av Windows 10 Enterprise [här](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine-in-azure"></a>Virtuell dator i Azure

Om du vill skapa en virtuell Windows 10-dator i Microsoft Azure ***måste du ha en Visual Studio-baserad prenumeration***, som har åtkomst till avbildningen av Windows 10 Enterprise. Andra typer av Azure-prenumerationer, t.ex. utvärderingsprenumerationer eller betalda prenumerationer, har inte åtkomst till den här avbildningen. Den senaste informationen finns i [Använda Windows-klienten i Azure för utvecklings-/testscenarier](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell. Se [Kom igång med Azure PowerShell-cmdletar](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Med dessa kommandouppsättningar skapas en virtuell dator med Windows 10 Enterprise som heter WIN10 och all den infrastruktur som krävs, inklusive en resursgrupp, ett lagringskonto och ett virtuellt nätverk. Om du redan är bekant med Azure Infrastructure-tjänsterna kan du anpassa dessa instruktioner för att passa din distribuerade infrastruktur.
  
Starta först en Microsoft PowerShell-prompt.
  
Logga in på ditt Azure-konto med det här kommandot.
  
```powershell
Connect-AzAccount
```

Skaffa ditt prenumerations namn med det här kommandot.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Ange din Azure-prenumeration. Ersätt allting inom citat tecknen, inklusive \< and > tecknen, med rätt namn.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Skapa sedan en ny resursgrupp. Använd det här kommandot för att lista dina befintliga resursgrupper när du ska fastställa ett unikt resursgruppnamn.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Skapa den nya resursgruppen med dessa kommandon. Ersätt allting inom citat tecknen, inklusive \< and > tecknen, med rätt namn.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Skapa sedan ett nytt virtuellt nätverk och WIN10 virtuella dator med dessa kommandon. När du uppmanas till det anger du namnet och lösenordet för det lokala administratörskontot för WIN10 och sparar dessa på en säker plats.
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a>Fas 5: Ansluta Windows 10-datorn till Azure AD

När du har skapat en fysisk eller virtuell dator med Windows 10 Enterprise loggar du in med ett lokalt administratörskonto.
  
> [!NOTE]
> Använd  [dessa instruktioner](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) för att ansluta till en virtuell dator i Azure.
  
Anslut sedan WIN10-datorn till Azure AD-klienten för din Microsoft 365 E5-prenumeration.
  
1. På Skriv bordet på WIN10-datorn väljer du **Start > inställningar > konton > åtkomst till arbets-eller skol > Anslut**.
    
2. I dialog rutan **Konfigurera ett arbets-eller skol konto** väljer **du Anslut den här enheten till Azure Active Directory**.
    
3. I **arbets-eller skol konto**anger du det globala administratörs konto namnet på ditt Microsoft 365 E5-abonnemang och väljer sedan **Nästa**.
    
4. Ange lösen ordet för ditt globala administratörs konto i **Ange lösen ord**och välj sedan **Logga in**.
    
5. När du uppmanas att kontrol lera att det här är din organisation väljer du **Anslut**och väljer sedan **klar**.
    
6. Stäng inställningsfönstret.
    
Installera sedan Microsoft 365-appar för företag på WIN10 dator:
  
1. Öppna webbläsaren Microsoft Edge och logga in i [administrations centret för microsoft 365](https://admin.microsoft.com) med dina globala administratörs konto uppgifter.
    
2. På fliken **Microsoft Office Home** väljer du **installera Office**.
    
3. När du uppmanas att göra det väljer du **Kör**och väljer sedan **Ja** för **kontroll av användar konto**.
    
4. Vänta på att installationen av Office slutförs. När du ser **allt! väljer du** **Stäng** två gånger.
    
Den resulterande miljön ser ut så här:

![Fas 5 av testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Det här omfattar den WIN10-dator som har:

- Anslutit till Azure AD-klienten för din Microsoft 365 E5-prenumeration.
- Registrerats som en Azure AD-enhet i Microsoft Intune (EMS).
- Microsoft 365-appar för företag installerat.
  
Nu kan du experimentera med fler funktioner i [Microsoft 365 för företag](https://www.microsoft.com/microsoft-365/enterprise).
  
## <a name="next-steps"></a>Nästa steg

Utforska dessa ytterligare uppsättningar testlabbguider:
  
- [Identitet](m365-enterprise-test-lab-guides.md#identity)
- [Hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Informationsskydd](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
