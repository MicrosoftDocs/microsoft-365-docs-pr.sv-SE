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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Använd den här testlabbguiden för att skapa en förenklad testmiljö för att testa Microsoft 365 Enterprise.
ms.openlocfilehash: 7a4800d374416a1e197536bc1a867d3fbc4b1243
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818759"
---
# <a name="the-lightweight-base-configuration"></a>Den enkla baskonfigurationen

*Den här testlabbguiden kan användas i både Microsoft 365 Enterprise- och Office 365 Enterprise-testmiljöer.*

I den här artikeln får du stegvisa instruktioner för hur du skapar en förenklad miljö med en Microsoft 365 E5-prenumeration och en dator med Windows 10 Enterprise. 

![Den förenklade testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Använd den resulterande miljön för att testa funktionerna och funktionaliteten i [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Klicka på [Samling med testlabbguider för Microsoft 365 för företag](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.

## <a name="phase-1-create-your-office-365-e5-subscription"></a>Fas 1: Skapa en Office 365 E5-prenumeration

Vi börjar med en utvärderingsprenumeration på Office 365 E5 och lägger sedan till Microsoft 365 E5-prenumerationen.

För att starta utvärderingsprenumerationen för Office 365 E5 behöver du först ett fiktivt företagsnamn och ett nytt Microsoft-konto.
  
1. Vi rekommenderar att du använder en variant av företagsnamnet Contoso som ditt företagsnamn, vilket är ett fiktivt företag som används i Microsoft-exempelinnehåll, men det är inget krav. Skriv ditt fiktiva företagsnamn här: ![Rad](../media/Common-Images/TableLine.png)
    
2. Om du vill registrera dig för ett nytt Microsoft-konto går du till [https://outlook.com](https://outlook.com) och skapar ett konto med ett nytt e-postkonto och en ny e-postadress. Du använder det här kontot för att registrera dig för Office 365.
    
  - Skriv för- och efternamn för ditt nya konto här: ![Rad](../media/Common-Images/TableLine.png)
    
  - Skriv den nya adressen för e-postkontot här: ![Rad](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registrera dig för en utvärderingsprenumeration på Office 365 E5

1. Öppna webbläsaren på datorn och gå till [https://aka.ms/e5trial](https://aka.ms/e5trial).
    
2. På sidan **Tack för att du väljer Office 365 E5** anger du den nya adressen för e-postkontot i steg 1.
3. I steg 2 av processen för utvärderingsprenumerationen skriver du den begärda informationen och utför sedan verifieringen.
4. I steg 3 skriver du ett organisationsnamn och sedan ett kontonamn som blir den globala administratören för prenumerationen. 
5. För steg 4 skriver du inloggningssidan här (markera och kopiera): ![Rad](../media/Common-Images/TableLine.png) 
6. Skriv användar-ID här: ![Rad](../media/Common-Images/TableLine.png).onmicrosoft.com  
   Anteckna lösenordet som du skrev ned på en säker plats.
   Det här värdet kommer att kallas för det **globala administratörsnamnet**.
8. Klicka på **Konfigurera**.
9. I Office 365 E5-konfigurationen klickar du på **Fortsätt använda *din organisation*.onmicrosoft.com för e-post och inloggning** och klicka sedan på **Avsluta och fortsätt senare**.

Du bör se administrationscentret för Microsoft 365.
  
Du skapar en utvärderingsprenumeration på Office 365 för att testmiljön ska ha en Azure AD-klient som är separerad från de betalda prenumerationer som du har för närvarande. Den här separationen innebär att du kan lägga till och ta bort användare och grupper i testklienten utan att påverka produktionsprenumerationerna.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Fas 2: Konfigurera utvärderingsprenumerationen för Office 365

I den här fasen konfigurerar du prenumerationen med ytterligare användare och tilldelar dem Office 365 E5-licenser.
  
Använd anvisningarna i [Ansluta till Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) för att ansluta till prenumerationen med Azure Active Directory PowerShell för Graph-modulen från datorn.
    
I dialogrutan **Begäran om autentiseringsuppgifter för Windows PowerShell** anger du det globala administratörsnamnet (t.ex. jdoe@contosotoycompany.onmicrosoft.com) och lösenordet.
  
Fyll i organisationens namn (t.ex. contosotoycompany), landskoden med två tecken för din plats, ett gemensamt kontolösenord och kör sedan följande kommandon från PowerShell-prompten:

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

Det kan vara bra att skriva ut den här artikeln för att kunna skriva ned den specifika information som du behöver för den här miljön under de 30 dagar som Office 365-utvärderingsprenumerationen gäller. Du kan enkelt utöka utvärderingsprenumerationen i ytterligare 30 dagar. För en permanent testmiljö skapar du en ny betald prenumeration med en separat Azure AD-klient och ett litet antal licenser.

Anteckna dessa värden:
  
- globalt administratörsnamn: ![Rad](../media/Common-Images/TableLine.png).onmicrosoft.com (från steg 6 i fas 1)
    
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

Om allt du behöver är en Office 365-testmiljö kan du stanna här. 

Se [Testlabbguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md) för ytterligare testlabbguider som gäller för både Office 365 och Microsoft 365.
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Fas 3: Lägga till en utvärderingsprenumeration på Microsoft 365 E5

I den här fasen registrerar du dig för Microsoft 365 E5-utvärderingsprenumerationen och lägger till den i samma organisation som utvärderingsprenumerationen för Office 365 E5.
  
Lägg först till Microsoft 365 E5-utvärderingsprenumerationen och tilldela den nya licensen för Microsoft 365 till det globala administratörskontot.
  
1. Med en privat instans av en webbläsare loggar du in i administrationscentret för Microsoft 365 på [https://admin.microsoft.com](https://admin.microsoft.com) med autentiseringsuppgifterna för det globala administratörskontot.
    
2. På sidan **Administrationscenter för Microsoft 365** klickar du på **Fakturering > Köp tjänster** i det vänstra navigeringsfältet.
    
3. På sidan **Köp tjänster** klickar du på **Microsoft 365 E5** och sedan på **Hämta en kostnadsfri utvärderingsversion**.

4. På sidan **Utvärderingsversion av Microsoft 365 E5** väljer du om du vill ta emot ett sms eller ett samtal, anger ditt telefonnummer och klickar på **Skicka sms** eller **Ring mig**. Utför verifieringen.

5. På sidan **Bekräfta din beställning** väljer du **Prova nu**.

6. På sidan **Beställningskvitto** klickar du på **Fortsätt**.

7. I administrationscentret för Microsoft 365 klickar du på **Användare > Aktiva användare**.

8. I **Aktiva användare** klickar du på administratörskontot.

9. Klicka på **Licenser och appar**.

10. Inaktivera licensen för Office 365 Enterprise, E5 och aktivera licensen för Microsoft 365 E5.

11. Klicka på **Spara ändringar** och stäng sedan fönstret med användarkontoinformation.

Upprepa sedan steg 8 till 11 i föregående procedur för alla andra konton (Användare 2, Användare 3, Användare 4 och Användare 5).
  
> [!NOTE]
> Utvärderingsprenumerationen på Microsoft 365 E5 gäller i 30 dagar. För en permanent testmiljö omvandlar du den här utvärderingsprenumeration till en betald prenumeration med ett litet antal licenser. 
  
Din testmiljö har nu:
  
- En utvärderingsprenumeration på Microsoft 365 E5.
- Alla relevanta användarkonton (antingen bara det globala administratörskontot eller alla fem användarkonton) är aktiverade för att använda Microsoft 365 E5.
    
Här är den resulterande konfigurationen som lägger till Microsoft 365 E5, där både Office 365 och Enterprise Security + Management (EMS) ingår.
  
![Fas 3 av testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Fas 4: Skapa en Windows 10 Enterprise-dator

I den här fasen skapar du en fristående dator med Windows 10 Enterprise som en fysisk dator, en virtuell dator eller en virtuell Azure-dator.
  
### <a name="physical-computer"></a>Fysisk dator

Skaffa en dator och installera Windows 10 Enterprise. Du kan ladda ned utvärderingsversionen av Windows 10 Enterprise [här](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine"></a>Virtuell dator

Skapa en virtuell dator med valfri hypervisor och installera Windows 10 Enterprise. Du kan ladda ned utvärderingsversionen av Windows 10 Enterprise [här](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine-in-azure"></a>Virtuell dator i Azure

Om du vill skapa en virtuell Windows 10-dator i Microsoft Azure ***måste du ha en Visual Studio-baserad prenumeration***, som har åtkomst till avbildningen av Windows 10 Enterprise. Andra typer av Azure-prenumerationer, t.ex. utvärderingsprenumerationer eller betalda prenumerationer, har inte åtkomst till den här avbildningen. Den senaste informationen finns i [Använda Windows-klienten i Azure för utvecklings-/testscenarier](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell. Se [Kom igång med Azure PowerShell-cmdletar](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Med dessa kommandouppsättningar skapas en virtuell dator med Windows 10 Enterprise som heter WIN10 och all den infrastruktur som krävs, inklusive en resursgrupp, ett lagringskonto och ett virtuellt nätverk. Om du redan är bekant med Azure-infrastrukturtjänster kan du anpassa de här anvisningarna så att de passar din aktuella distribuerade infrastruktur. 
  
Starta först en Microsoft PowerShell-prompt.
  
Logga in på ditt Azure-konto med följande kommando.
  
```powershell
Connect-AzAccount
```

Hämta ditt prenumerationsnamn med följande kommando.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Ange din Azure-prenumeration. Ersätt allt inom citattecknen, inklusive \< and >-tecknen med rätt namn.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Skapa sedan en ny resursgrupp. Använd det här kommandot för att lista dina befintliga resursgrupper när du ska fastställa ett unikt resursgruppnamn.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Skapa den nya resursgruppen med dessa kommandon. Ersätt allt inom citattecknen, inklusive \< and >-tecknen med de rätta namnen.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Nästa steg är att skapa ett nytt virtuellt nätverk och den virtuella WIN10-datorn med dessa kommandon. När du uppmanas till det anger du namnet och lösenordet för det lokala administratörskontot för WIN10 och sparar dessa på en säker plats.
  
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
> Anslut till en virtuell dator i Azure med hjälp av [dessa anvisningar](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).
  
Anslut sedan WIN10-datorn till Azure AD-klienten för din Microsoft 365 E5-prenumeration.
  
1. Gå till skrivbordet för WIN10-datorn och klicka på **Start > Inställningar > Konton > Åtkomst till arbete eller skola > Anslut**.
    
2. I dialogrutan **Konfigurera ett arbets- eller skolkonto** klickar du på **Anslut den här enheten till Azure Active Directory**.
    
3. I **Arbets- eller skolkonto** skriver du det globala administratörskontonamnet för Microsoft 365 E5-prenumerationen och klickar sedan på **Nästa**.
    
4. I **Ange lösenord** skriver du lösenordet för det globala administratörskontot och klickar sedan på **Logga in**.
    
5. När du uppmanas att kontrollera att det är din organisation klickar du på **Anslut**och sedan på **Klart**.
    
6. Stäng inställningsfönstret.
    
Installera sedan Microsoft 365-applikationer för företag på WIN10-datorn.
  
1. Öppna webbläsaren Microsoft Edge och logga in på Office-portalen med autentiseringsuppgifterna för ditt globala administratörskonto. Mer information finns i [Så här loggar du in i Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. På fliken **Microsoft Office Home** klickar du på **Installera Office**.
    
3. När du tillfrågas om vad du vill göra klickar du på **Kör** och klickar sedan på **Ja** för **User Account Control**.
    
4. Vänta på att installationen av Office slutförs. När du ser **Nu är du klar!** klickar du på **Stäng** två gånger.
    
Här är den resulterande miljön.

![Fas 5 av testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Det här omfattar den WIN10-dator som har:

- Anslutit till Azure AD-klienten för din Microsoft 365 E5-prenumeration.
- Registrerats som en Azure AD-enhet i Microsoft Intune (EMS).
- Har Microsoft 365-applikationer för företag installerat.
  
Nu är du redo att experimentera med fler funktioner i [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).
  
## <a name="next-steps"></a>Nästa steg

Utforska dessa ytterligare uppsättningar testlabbguider:
  
- [Identitet](m365-enterprise-test-lab-guides.md#identity)
- [Hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Informationsskydd](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>Snabbreferens

[Testlabbguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuera Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
