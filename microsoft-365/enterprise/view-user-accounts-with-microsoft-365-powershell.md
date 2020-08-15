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
ms.openlocfilehash: ea631d12a95ca813ebf9da3286e36d724d51a2f7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696765"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Visa Microsoft 365-användarkonton med PowerShell

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Även om du kan använda administrations centret för Microsoft 365 för att Visa kontona för din Microsoft 365-klient organisation kan du också använda PowerShell för Microsoft 365 och göra vissa saker som administrations centret inte kan.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
### <a name="view-all-accounts"></a>Visa alla konton

Om du vill visa hela listan över användar konton kör du det här kommandot:
  
```powershell
Get-AzureADUser
```

Här visas information som liknar den här:
  
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

Om du vill visa ett specifikt användar konto fyller du i användar kontots namn för inloggnings konto, som även kallas UPN (User Principal Name), tar bort tecknen "<" och ">" och kör det här kommandot:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Här är ett exempel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Visa ytterligare egenskaps värden för ett visst konto

Som standard visar cmdleten **Get-AzureADUser** bara egenskaperna ObjectID, DisplayName och userPrincipalName för konton.

Om du vill veta mer om listan med egenskaper att Visa kan du använda **Select** -cmdleten i kombination med cmdleten **Get-AzureADUser** . Om du vill kombinera de två cmdletarna använder vi "pipe"-tecknet "|", som talar för att Azure Active Directory PowerShell for Graph tar ett kommando och skickar det till nästa kommando. Här visas ett exempel kommando som visar visnings namn, avdelning och UsageLocation för varje användar konto:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Det här kommandot instruerar PowerShell till att:
  
- Hämta all information om användar kontona ( **Get-AzureADUser** ) och skicka det till nästa kommando ( **|** ).
    
- Visa endast användar konto namn, avdelning och användnings plats ( **Välj DisplayName, avdelning, UsageLocation** ).
  
Om du vill se alla egenskaper för användar konton kan du använda **Välj** cmdlet och jokertecknet (*) för att visa alla för ett visst användar konto. Här är ett exempel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Du kan till exempel kontrol lera den aktiverade statusen för ett visst användar konto med följande kommando:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-some-accounts-based-on-a-common-property"></a>Visa vissa konton baserat på en gemensam egenskap

Om du vill veta mer om listan med konton som ska visas kan du använda **WHERE** -cmdleten tillsammans med cmdleten **Get-AzureADUser** . Om du vill kombinera de två cmdletarna använder vi "pipe"-tecknet "|", som talar för att Azure Active Directory PowerShell for Graph tar ett kommando och skickar det till nästa kommando. Här är ett exempel kommando som endast visar de användar konton som har en ospecificerad användnings plats:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Det här kommandot instruerar Azure Active Directory PowerShell för Graph till:
  
- Hämta all information om användar kontona ( **Get-AzureADUser** ) och skicka det till nästa kommando ( **|** ).
    
- Hitta alla användar konton som har en ospecificerad användnings plats ( **där {$ \_ . UsageLocation-EQ $Null}** ). Inom klammerparenteserna instruerar kommandot PowerShell till att endast hitta den uppsättning konton där egenskapen UsageLocation User Account ( ** $ \_ . UsageLocation** ) är inte angivet ( **-EQ $null** ).
    
Egenskapen **UsageLocation** är bara en av många egenskaper associerade med ett användar konto. Om du vill se alla egenskaper för användar konton kan du använda **Välj** cmdlet och jokertecknet (*) för att visa alla för ett visst användar konto. Här är ett exempel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

I den här listan är till exempel **ort** namnet på ett användar konto. Det innebär att du kan använda följande kommando för att visa en lista med alla användar konton för användare som bor i London:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  Syntaxen för **WHERE** -cmdleten som visas i dessa exempel är **{$ \_ .** [användar kontots egenskaps namn] [jämförelse operator] värdepar **}**. > [jämförelse operator] är **-EQ** för lika med, **-Ne** för inte lika med, **-lt** för mindre än, **-gt** för större än och andra.  [värde] är vanligt vis en sträng (en sekvens med bokstäver, siffror och andra tecken), ett numeriskt värde eller **$Null** för ospecificerad> se [var](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) du kan få mer information.
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="view-all-accounts"></a>Visa alla konton

Om du vill visa hela listan över användar konton kör du det här kommandot:
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** . För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.
>

Här visas information som liknar den här:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Cmdleten **Get-MsolUser** har också en uppsättning parametrar som filtrerar uppsättningen med användar konton. Om du till exempel vill visa en lista över ej licensierade användare (användare som har lagts till i Microsoft 365 men ännu inte har licensierats till att använda någon av tjänsterna) kör du det här kommandot.
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

Här visas information som liknar den här:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Mer information om ytterligare parametrar för att filtrera visningen av uppsättningen användar konton som visas finns i [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).
  
### <a name="view-a-specific-account"></a>Visa ett specifikt konto

Om du vill visa ett specifikt användar konto fyller du i inloggnings namnet för användar kontot för användar kontot, även kallat användarens huvud namn (UPN), tar bort tecknen "<" och ">" och kör det här kommandot:
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a>Visa vissa konton baserat på en gemensam egenskap

Om du vill veta mer om listan med konton som ska visas kan du använda **WHERE** -cmdleten tillsammans med cmdleten **Get-MsolUser** . Om du vill kombinera de två cmdletarna använder vi "pipe"-tecknet "|", vilket anger att PowerShell utför resultatet av ett kommando och skickar det till nästa kommando. Här är ett exempel kommando som endast visar de användar konton som har en ospecificerad användnings plats:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Det här kommandot instruerar PowerShell till att:
  
- Hämta all information om användar kontona ( **Get-MsolUser** ) och skicka det till nästa kommando ( **|** ).
    
- Hitta alla användar konton som har en ospecificerad användnings plats ( **där {$ \_ . UsageLocation-EQ $Null}** ). Inom klammerparenteserna instruerar kommandot PowerShell till att endast hitta den uppsättning konton där egenskapen UsageLocation User Account ( ** $ \_ . UsageLocation** ) är inte angivet ( **-EQ $null** ).
    
Här visas information som liknar den här:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

Egenskapen **UsageLocation** är bara en av många egenskaper associerade med ett användar konto. Om du vill se alla egenskaper för användar konton kan du använda **Välj** cmdlet och jokertecknet (*) för att visa alla för ett visst användar konto. Här är ett exempel:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

I den här listan är till exempel **ort** namnet på ett användar konto. Det innebär att du kan använda följande kommando för att visa en lista med alla användar konton för användare som bor i London:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  Syntaxen för **WHERE** -cmdleten som visas i dessa exempel är **{$ \_ .** [användar kontots egenskaps namn] [jämförelse operator] värdepar **}**.  [jämförelse operator] är **-EQ** för lika med, **-Ne** för inte lika med, **-** t för mindre än, **-gt** för större än och andra.  [värde] är vanligt vis en sträng (en sekvens med bokstäver, siffror och andra tecken), ett numeriskt värde eller **$Null** för ospecificerad. Se [var](https://technet.microsoft.com/library/hh849715.aspx) du kan få mer information.
  
Du kan kontrol lera den spärrade statusen för ett användar konto med följande kommando:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Visa ytterligare egenskaps värden för konton

Cmdleten **Get-MsolUser** med standard visar tre egenskaper för användar konton:
  
- UserPrincipalName
    
- DisplayName
    
- Ärlicensierad
    
Om du behöver ytterligare egenskaper, till exempel avdelningen som användaren arbetar med och landet/regionen där användaren använder Microsoft 365-tjänsterna, kan du köra **Get-MsolUser** i kombination med **Välj** cmdlet för att ange listan över användar konto egenskaper. Här är ett exempel:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Det här kommandot instruerar PowerShell till att:
  
- Hämta all information om användar kontona ( **Get-MsolUser** ) och skicka det till nästa kommando ( **|** ).
    
- Visa endast användar konto namn, avdelning och användnings plats ( **Välj DisplayName, avdelning, UsageLocation** ).
    
Här visas information som liknar den här:
  
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

Med **Välj** cmdlet kan du välja och välja vilka egenskaper du vill visa. Om du vill visa alla egenskaper för användar konton använder du jokertecknet (*) för att visa alla för ett visst användar konto. Här är ett exempel:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Om du vill veta mer om listan med konton som ska visas kan du även använda **WHERE** -cmdleten. Här är ett exempel kommando som endast visar de användar konton som har en ospecificerad användnings plats:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Det här kommandot instruerar PowerShell till att:
  
- Hämta all information om användar kontona ( **Get-MsolUser** ) och skicka det till nästa kommando ( **|** ).
    
- Hitta alla användar konton som har en ospecificerad användnings plats ( **där {$ \_ . UsageLocation-EQ $Null}** ) och skicka den resulterande informationen till nästa kommando ( **|** ). Inuti klamrarna anger kommandot PowerShell för att bara hitta den uppsättning konton där egenskapen UsageLocation User Account ( ** $ \_ . UsageLocation** ) är inte angivet ( **-EQ $null** ).
    
- Visa endast användar konto namn, avdelning och användnings plats ( **Välj DisplayName, avdelning, UsageLocation** ).
    
Här visas information som liknar den här:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Om du använder Directory-synkronisering för att skapa och hantera dina Microsoft 365-användare kan du Visa vilka lokala konton en Microsoft 365-användare har projicerat från. Följande förutsätter att Azure AD Connect är konfigurerat för att använda standard käll ankaret för ObjectGUID (mer information om hur du konfigurerar käll ankare finns i [Azure AD Connect: design koncept](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) och förutsätter att Active Directory Domain Services-modulen för PowerShell har installerats (se [rsat tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Komma igång med PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)

