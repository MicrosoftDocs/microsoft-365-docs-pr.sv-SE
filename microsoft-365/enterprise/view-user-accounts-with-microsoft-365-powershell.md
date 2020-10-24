---
title: Visa Microsoft 365-användarkonton med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: Lär dig att visa, lista eller Visa dina Microsoft 365-användarkonton på olika sätt med PowerShell.
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754078"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Visa Microsoft 365-användarkonton med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan använda administrations centret för Microsoft 365 för att Visa kontona för din Microsoft 365-klient organisation. Med PowerShell för Microsoft 365 kan du även få ytterligare funktioner.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
### <a name="view-all-accounts"></a>Visa alla konton

Om du vill visa hela listan över användar konton kör du det här kommandot:
  
```powershell
Get-AzureADUser
```

Du bör få information som liknar den här:
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a>Visa ett specifikt konto

Om du vill visa ett specifikt användar konto kör du följande kommando. Fyll i namnet på användar kontots inloggnings konto, som även kallas användarens huvud namn (UPN). Ta bort tecknen "<" och ">".
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Här är ett exempel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Visa ytterligare egenskaps värden för ett visst konto

Som standard visar cmdleten **Get-AzureADUser** bara egenskaperna *ObjectID*, *DisplayName*och *userPrincipalName* för konton.

Om du vill veta mer om vilka egenskaper som ska visas använder du cmdleten **Select** i kombination med cmdleten **Get-AzureADUser** . Om du vill kombinera de två cmdletarna använder du "pipe"-tecknet ("|"), som talar om att Azure Active Directory PowerShell for Graph tar ett kommando och skickar det till nästa kommando. Här är ett exempel kommando som visar *visnings*namn, *avdelning*och *UsageLocation* för alla användar konton:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Det här kommandot instruerar PowerShell till att:
  
1. Få all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).
    
1.  Visa endast användar konto namn, avdelning och användnings plats (**Välj DisplayName, avdelning, UsageLocation**).
  
Om du vill visa alla egenskaper för ett visst användar konto använder du **Select** -cmdlet och jokertecknet (*). Här är ett exempel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

I ett annat exempel kör du följande kommando för att kontrol lera den aktiverade statusen för ett specifikt användar konto:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>Visa synkroniseringsstatus för kontot

Användar konton har två källor: 

- Windows Server Active Directory (AD), som är konton som synkroniserar från lokal annons till molnet.

- Azure Active Directory (Azure AD)-konton som skapas direkt i molnet.


Följande kommando instruerar PowerShell att hämta alla användare som har attributet *DirSyncEnabled* angivet till *True*. Du kan använda den för att hitta konton som synkroniserar från den lokala ANNONSen.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

Följande kommando instruerar PowerShell att hämta alla användare som har attributet *DirSyncEnabled* angivet till *false*. Du kan använda den för att söka efter moln-konton.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>Visa konton baserat på en gemensam egenskap

Om du vill veta mer om listan med konton som ska visas kan du använda **WHERE** -cmdleten tillsammans med cmdleten **Get-AzureADUser** . Om du vill kombinera de två cmdletarna använder du "pipe"-tecknet ("|"), som talar om att Azure Active Directory PowerShell for Graph tar ett kommando och skickar det till nästa kommando. Här är ett exempel kommando som endast visar de användar konton som har en ospecificerad användnings plats:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Det här kommandot instruerar Azure Active Directory PowerShell för Graph till:
  
1. Få all information om användar kontona (**Get-AzureADUser**) och skicka det till nästa kommando ( **|** ).
    
1. Hitta alla användar konton som har en ospecificerad användnings plats (**där {$ \_ . UsageLocation-EQ $Null}**). Inom klammerparenteserna instruerar kommandot PowerShell till att endast hitta den uppsättning konton som egenskapen UsageLocation User Account (** $ \_ . UsageLocation**) är inte angivet (**-EQ $null**).
    
Egenskapen **UsageLocation** är bara en av många egenskaper associerade med ett användar konto. Om du vill visa alla egenskaper för ett visst användar konto använder du **Select** -cmdlet och jokertecknet (*). Här är ett exempel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Till exempel är **ort** namnet på ett användar konto. Du kan använda följande kommando för att lista alla konton för användare som bor i London:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  Syntaxen för **WHERE** -cmdleten i dessa exempel är **{$ \_ .** [användar kontots egenskaps namn] [jämförelse operator] värdepar **}**. > [jämförelse operator] är **-EQ** för lika med, **-Ne** för inte lika med, **-lt** för mindre än, **-gt** för större än och andra.  [värde] är vanligt vis en sträng (en sekvens med bokstäver, siffror och andra tecken), ett numeriskt värde eller **$Null** för ospecificerad. Mer information finns i [var](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="view-all-accounts"></a>Visa alla konton

Om du vill visa hela listan över användar konton kör du det här kommandot:
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *MSOL* . Kör dessa cmdletar från Windows PowerShell.
>

Du bör få information som liknar den här:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Cmdleten **Get-MsolUser** har också en uppsättning parametrar som filtrerar uppsättningen med användar konton. Om du till exempel vill visa en lista över ej licensierade användare (användare som har lagts till i Microsoft 365 men ännu inte licensierats till att använda någon av tjänsterna) kör du det här kommandot:
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

Du bör få information som liknar den här:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Information om ytterligare parametrar för att filtrera uppsättningen användar konton som visas finns i [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).
  
### <a name="view-a-specific-account"></a>Visa ett specifikt konto

Om du vill visa ett specifikt användar konto kör du följande kommando. Fyll i inloggnings namnet för användar kontot, som även kallas UPN (User Principal Name). Ta bort tecknen "<" och ">".
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>Visa konton baserat på en gemensam egenskap

Om du vill veta mer om listan med konton som ska visas kan du använda **WHERE** -cmdleten tillsammans med cmdleten **Get-MsolUser** . Om du vill kombinera de två cmdletarna använder du "pipe"-tecknet ("|"), vilket gör att PowerShell utför resultatet från ett kommando och skickar det till nästa kommando. Här är ett exempel som bara visar de användar konton som har en ospecificerad användnings plats:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Det här kommandot instruerar PowerShell till att:
  
1. Få all information om användar kontona (**Get-MsolUser**) och skicka det till nästa kommando ( **|** ).
    
1. Hitta alla användar konton som har en ospecificerad användnings plats (**där {$ \_ . UsageLocation-EQ $Null}**). Inuti klamrarna anger kommandot PowerShell för att hitta den uppsättning konton för vilka egenskapen UsageLocation User Account (** $ \_ . UsageLocation**) är inte angivet (**-EQ $null**).
    
Du bör få information som liknar den här:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

Egenskapen *UsageLocation* är bara en av många egenskaper associerade med ett användar konto. Om du vill se alla egenskaper för användar konton kan du använda **Välj** cmdlet och jokertecknet (*) för att visa alla för ett visst användar konto. Här är ett exempel:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Till exempel är *ort* namnet på ett användar konto. Du kan använda följande kommando för att lista alla användar konton för användare som bor i London:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  Syntaxen för **WHERE** -cmdleten i dessa exempel är **{$ \_ .** [användar kontots egenskaps namn] [jämförelse operator] värdepar **}**.  [jämförelse operator] är **-EQ** för lika med, **-Ne** för inte lika med, **-** t för mindre än, **-gt** för större än och andra.  [värde] är vanligt vis en sträng (en sekvens med bokstäver, siffror och andra tecken), ett numeriskt värde eller **$Null** för ospecificerad. Mer information finns i [var](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).
  
Använd följande kommando för att kontrol lera den spärrade statusen för ett användar konto:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Visa ytterligare egenskaps värden för konton

Som standard visar cmdleten **Get-MsolUser** dessa tre egenskaper för användar konton:
  
- UserPrincipalName
    
- DisplayName
    
- Ärlicensierad
    
Om du behöver fler egenskaper, till exempel den avdelning där användaren arbetar och det land/den region där de använder Microsoft 365-tjänsterna, kan du köra **Get-MsolUser** i kombination med **Välj** cmdlet för att ange listan över användar konto egenskaper. Här är ett exempel:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Det här kommandot instruerar PowerShell till att:
  
1. Få all information om användar kontona (**Get-MsolUser**) och skicka det till nästa kommando ( **|** ).
    
1. Visa endast användar konto namn, avdelning och användnings plats (**Välj DisplayName, avdelning, UsageLocation**).
    
Du bör få information som liknar den här:
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

Med **Välj** cmdlet kan du välja vilka egenskaper du vill visa. Använd jokertecknet (*) om du vill visa alla egenskaper för ett visst användar konto. Här är ett exempel:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Om du vill veta mer om listan med konton som ska visas kan du även använda **WHERE** -cmdleten. Här är ett exempel kommando som endast visar de användar konton som har en ospecificerad användnings plats:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Det här kommandot instruerar PowerShell till att:
  
1. Få all information om användar kontona (**Get-MsolUser**) och skicka det till nästa kommando ( **|** ).
    
1. Hitta alla användar konton som har en ospecificerad användnings plats (**där {$ \_ . UsageLocation-EQ $Null}**) och skicka den resulterande informationen till nästa kommando ( **|** ). Inom klammerparenteserna instruerar kommandot PowerShell till att endast hitta den uppsättning konton som egenskapen UsageLocation User Account (** $ \_ . UsageLocation**) är inte angivet (**-EQ $null**).
    
1. Visa endast användar konto namn, avdelning och användnings plats (**Välj DisplayName, avdelning, UsageLocation**).
    
Du bör få information som liknar den här:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Om du använder Directory-synkronisering för att skapa och hantera dina Microsoft 365-användare kan du Visa det lokala kontot som en Microsoft 365-användare har projicerats från. Följande exempel förutsätter att:

- Azure AD Connect är konfigurerat för att använda standard käll ankaret för ObjectGUID. (Mer information om hur du konfigurerar käll ankare finns i [Azure AD Connect: design koncept](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).
- Active Directory Domain Services-modulen för PowerShell har installerats (se [RSAT-verktyg](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
