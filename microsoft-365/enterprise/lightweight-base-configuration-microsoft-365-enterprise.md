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
description: Använd den här testlabbguiden för att skapa en lätt testmiljö för Microsoft 365 för företag.
ms.openlocfilehash: 2de0760cef7339f62229575b1e0a54b3c67a4e9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909712"
---
# <a name="the-lightweight-base-configuration"></a>Den enkla baskonfigurationen

*Den här testlabbguiden kan användas för både Microsoft 365 för företag Office 365 Enterprise för testmiljöer.*

I den här artikeln beskrivs hur du skapar en förenklad miljö med en Microsoft 365 E5-prenumeration och en dator som kör Windows 10 Enterprise.

![Den förenklade testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Att skapa en lätt testmiljö omfattar fem faser:
- [Fas 1: Skapa din Microsoft 365 E5 prenumeration](#phase-1-create-your-microsoft-365-e5-subscription)
- [Fas 2: Konfigurera utvärderingsprenumerationen för Office 365](#phase-2-configure-your-office-365-trial-subscription)
- [Fas 3: Lägga till en utvärderingsprenumeration på Microsoft 365 E5](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [Fas 4: Skapa en Windows 10 Enterprise-dator](#phase-4-create-a-windows-10-enterprise-computer)
- [Fas 5: Ansluta Windows 10-datorn till Azure AD](#phase-5-join-your-windows-10-computer-to-azure-ad)

Använd den resulterande miljön för att testa funktionerna i Microsoft 365 [för företag.](https://www.microsoft.com/microsoft-365/enterprise)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i Microsoft 365 för [testlabbguide](../downloads/Microsoft365EnterpriseTLGStack.pdf)stack för företag.

>[!NOTE]
>Det kan vara bra att skriva ut den här artikeln för att kunna skriva ned den specifika information som du behöver för den här miljön under de 30 dagar som Office 365-utvärderingsprenumerationen gäller. Du kan enkelt utöka utvärderingsprenumerationen i ytterligare 30 dagar. För en permanent testmiljö skapar du en ny betald prenumeration med en separat Azure AD-klient och ett litet antal licenser.

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>Fas 1: Skapa din Microsoft 365 E5 prenumeration

Vi börjar med en Microsoft 365 E5-prenumeration och lägger sedan till Microsoft 365 E5-prenumerationen i den.

>[!NOTE]
>Vi rekommenderar att du skapar en utvärderingsprenumeration av Office 365 så att testmiljön har en separat Azure AD-klientorganisation från de betalprenumerationer du har för närvarande. Den här separationen innebär att du kan lägga till och ta bort användare och grupper i testklientorganisationen utan att påverka produktionsprenumerationerna.

För att starta Microsoft 365 E5 provprenumerationen behöver du först ett fiktivt företagsnamn och ett nytt Microsoft-konto.
  
1. Vi rekommenderar att du använder en variant av företagsnamnet Contoso som ditt företagsnamn, vilket är ett fiktivt företag som används i Microsoft-exempelinnehåll, men det är inget krav. Skriv ditt fiktiva företagsnamn här: ![Rad](../media/Common-Images/TableLine.png)
    
2. Om du vill registrera dig för ett nytt Microsoft-konto går du till [https://outlook.com](https://outlook.com) och skapar ett konto med ett nytt e-postkonto och en ny e-postadress. Du använder det här kontot för att registrera dig för Office 365.
    
    - Skriv för- och efternamn för ditt nya konto här: ![Rad](../media/Common-Images/TableLine.png)
    
    - Skriv den nya adressen för e-postkontot här: ![Rad](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registrera dig för en utvärderingsprenumeration på Office 365 E5

1. Öppna webbläsaren och gå till [https://aka.ms/e5trial](https://aka.ms/e5trial) .
    
2. I steg 1 på sidan **Tack för att du Office 365 E5** anger du adressen till det nya e-postkontot.
3. I steg 2 i trail-prenumerationsprocessen anger du den begärda informationen och utför sedan verifieringen.
4. I steg 3 anger du ett organisationsnamn och sedan ett kontonamn som blir global administratör för prenumerationen.
5. För steg 4 skriver du inloggningssidan här (markera och kopiera): ![Rad](../media/Common-Images/TableLine.png)
6. Skriv användar-ID här: ![Rad](../media/Common-Images/TableLine.png).onmicrosoft.com  
   Registrera det lösenord som du angav på en säker plats.
   Det här värdet kommer att kallas för det **globala administratörsnamnet**.
7. Välj **Gå till installationsprogrammet.**
8. I Office 365 E5 väljer du Fortsätt använda din organisation **.onmicrosoft.com** för e-post och inloggning och välj sedan **Avsluta och fortsätt senare.**

Du bör se administrationscentret för Microsoft 365.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Fas 2: Konfigurera utvärderingsprenumerationen för Office 365

I den här fasen konfigurerar du prenumerationen med ytterligare användare och tilldelar dem Office 365 E5-licenser.
  
Om du vill ansluta till din prenumeration med Azure Active Directory PowerShell för Graph-modulen från datorn följer du anvisningarna i [Anslut för Microsoft 365 med PowerShell.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
    
I **dialogrutan Windows PowerShell Begäran om autentiseringsuppgifter** anger du namnet på den globala administratören (till exempel *jdoe@contosotoycompany.onmicrosoft.com*) och lösenord.
  
Fyll i ditt organisationsnamn (till exempel *contosotoycompany),* landskoden på två tecken för din plats, ett vanligt kontolösenord och kör sedan följande kommandon från PowerShell-kommandotolken:

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

Om du inte redan har spelat in dessa värden spelar du in dem nu:
  
- Global administratör: ![Rad](../media/Common-Images/TableLine.png).onmicrosoft.com (från steg 6 i fas 1)
    
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

Om du bara behöver Office 365 en testmiljö behöver du inte läsa resten av den här artikeln.

Fler testlabbguider som gäller för både Office 365 och Microsoft 365 finns [i Microsoft 365 för testlabbguider för företag.](m365-enterprise-test-lab-guides.md)
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Fas 3: Lägga till en utvärderingsprenumeration på Microsoft 365 E5

I den här fasen registrerar du dig för Microsoft 365 E5-utvärderingsprenumerationen och lägger till den i samma organisation som utvärderingsprenumerationen för Office 365 E5.
  
Lägg först till Microsoft 365 E5-utvärderingsprenumerationen och tilldela den nya licensen för Microsoft 365 till det globala administratörskontot.
  
1. Använd dina autentiseringsuppgifter för ditt globala administratörskonto i ett privat webbläsarfönster för att logga in Microsoft 365 administrationscentret på [https://admin.microsoft.com](https://admin.microsoft.com) .
    
2. I det **Microsoft 365 navigeringsfältet** på sidan för administrationscentret väljer du **Fakturering > Köptjänster.**
    
3. På sidan **Köp tjänster** väljer du **Microsoft 365 E5** och sedan Hämta **kostnadsfri utvärderingsversion.**

4. På sidan **Microsoft 365 E5 utvärderingsversion** väljer du att ta emot ett SMS eller ett telefonsamtal, anger ditt telefonnummer och väljer sedan **Sms:a mig** eller Ring upp **mig.** Utför verifieringen.

5. På sidan **Bekräfta din beställning** väljer du Prova **nu.**

6. På sidan **Orderkvitto** väljer du **Fortsätt.**

7. I administrationscentret Microsoft 365 väljer du **Användare > Aktiva användare.**

8. Välj **administratörskonto** i Aktiva användare.

9. Välj **Licenser och appar.**

10. Inaktivera licensen för Office 365 Enterprise, E5 och aktivera licensen för Microsoft 365 E5.

11. Välj **Spara ändringar** och stäng sedan informationsfönstret för användarkontot.

Upprepa sedan steg 8 till 11 i föregående procedur för alla andra konton (Användare 2, Användare 3, Användare 4 och Användare 5).
  
> [!NOTE]
> Längden på utvärderingsprenumerationen på Microsoft 365 E5 är 30 dagar. För en permanent testmiljö omvandlar du den här utvärderingsprenumeration till en betald prenumeration med ett litet antal licenser.
  
Din testmiljö har nu:
  
- En utvärderingsprenumeration på Microsoft 365 E5.
- Alla relevanta användarkonton (antingen bara det globala administratörskontot eller alla fem användarkonton) är aktiverade för att använda Microsoft 365 E5.
    
Den resulterande konfigurationen, som lägger till Microsoft 365 E5, ser ut så här:
  
![Fas 3 av testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Fas 4: Skapa en Windows 10 Enterprise-dator

I den här fasen skapar du en fristående dator med Windows 10 Enterprise som en fysisk dator, en virtuell dator eller en virtuell Azure-dator.
  
### <a name="physical-computer"></a>Fysisk dator

Installera Windows 10 Enterprise på Windows 10 Enterprise. Du kan ladda ned utvärderingsversionen av Windows 10 Enterprise [här](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine"></a>Virtuell dator

Använd valfri hypervisor för att skapa en virtuell dator och installera Windows 10 Enterprise på den. Du kan ladda ned utvärderingsversionen av Windows 10 Enterprise [här](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine-in-azure"></a>Virtuell dator i Azure

Om du vill skapa en virtuell Windows 10-dator i Microsoft Azure ***måste du ha en Visual Studio-baserad prenumeration***, som har åtkomst till avbildningen av Windows 10 Enterprise. Andra typer av Azure-prenumerationer, t.ex. utvärderingsprenumerationer eller betalda prenumerationer, har inte åtkomst till den här avbildningen. Den senaste informationen finns i [Använda Windows-klienten i Azure för utvecklings-/testscenarier](/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell. Se [Kom igång med Azure PowerShell-cmdletar](/powershell/azureps-cmdlets-docs/). Med dessa kommandouppsättningar skapas en virtuell dator med Windows 10 Enterprise som heter WIN10 och all den infrastruktur som krävs, inklusive en resursgrupp, ett lagringskonto och ett virtuellt nätverk. Om du redan är bekant med Azure-infrastrukturtjänster kan du anpassa de här instruktionerna så att de passar din nuvarande använda infrastruktur.
  
Starta först en Microsoft PowerShell-prompt.
  
Logga in på ditt Azure-konto med det här kommandot.
  
```powershell
Connect-AzAccount
```

Skaffa namnet på din prenumeration med det här kommandot.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Ange din Azure-prenumeration. Ersätt allt inom citattecknen, \< and > inklusive tecknen, med rätt namn.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Skapa sedan en ny resursgrupp. Använd det här kommandot för att lista dina befintliga resursgrupper när du ska fastställa ett unikt resursgruppnamn.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Skapa den nya resursgruppen med dessa kommandon. Ersätt allt inom citattecknen, \< and > inklusive tecknen, med rätt namn.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Skapa sedan ett nytt virtuellt nätverk och den virtuella WIN10-datorn med dessa kommandon. När du uppmanas till det anger du namnet och lösenordet för det lokala administratörskontot för WIN10 och sparar dessa på en säker plats.
  
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
> Använd de här anvisningarna för att ansluta  [till en virtuell](/azure/virtual-machines/windows/connect-logon) dator i Azure.
  
Anslut sedan WIN10-datorn till Azure AD-klienten för din Microsoft 365 E5-prenumeration.
  
1. På skrivbordet på WIN10-datorn väljer du **Starta > Inställningar >-> Få åtkomst** till arbete eller > Anslut .
    
2. I dialogrutan **Konfigurera ett arbets- eller skolkonto väljer** du Anslut den här enheten för att **Azure Active Directory**.
    
3. I **arbets- eller skolkonto** anger du namnet på det globala administratörskontot för Microsoft 365 E5-prenumerationen och väljer **sedan Nästa**.
    
4. I **Ange lösenord** anger du lösenordet för ditt globala administratörskonto och väljer sedan Logga **in.**
    
5. När du uppmanas att kontrollera att detta är din organisation väljer **du Anslut** och sedan **Klar**.
    
6. Stäng inställningsfönstret.
    
Installera Microsoft 365-appar för företag WIN10-datorn:
  
1. Öppna webbläsaren Microsoft Edge logga in på administrationscentret Microsoft 365 [och logga](https://admin.microsoft.com) in med dina autentiseringsuppgifter som global administratör.
    
2. På Microsoft Office **Start** väljer du **Installera Office**.
    
3. När du tillfrågas om vad du ska **göra väljer** du Kör och sedan **Ja** **för användarkontokontroll.**
    
4. Vänta på att installationen av Office slutförs. När du ser **Klart! väljer du** Stäng **två** gånger.
    
Den resulterande miljön ser ut så här:

![Fas 5 av testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Det här omfattar den WIN10-dator som har:

- Anslutit till Azure AD-klienten för din Microsoft 365 E5-prenumeration.
- Registrerats som en Azure AD-enhet i Microsoft Intune (EMS).
- Microsoft 365-appar för företag installerat.
  
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