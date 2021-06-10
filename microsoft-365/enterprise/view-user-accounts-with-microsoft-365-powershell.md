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
description: Lär dig hur du visar, listar eller visar Microsoft 365-användarkonton på olika sätt med PowerShell.
ms.openlocfilehash: de91195afeb8480bf231d9536e4b3a94502a6da1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924654"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Visa Microsoft 365-användarkonton med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan använda Microsoft 365 administrationscenter för att visa kontona för Microsoft 365 klientorganisationen. PowerShell för Microsoft 365 detta men ger även ytterligare funktioner.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för Graph modul

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
### <a name="view-all-accounts"></a>Visa alla konton

Om du vill visa hela listan med användarkonton kör du det här kommandot:
  
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

Om du vill visa ett specifikt användarkonto kör du följande kommando. Fyll i inloggningskontonamnet för användarkontot, som också kallas huvudnamn (UPN). Ta bort tecknen "<" och ">".
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Här är ett exempel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Visa ytterligare egenskapsvärden för ett visst konto

Som standard visar **cmdlet:en Get-AzureADUser** endast egenskaperna *ObjectID,* *DisplayName* *och UserPrincipalName* för konton.

Om du vill vara mer selektiv när det gäller egenskaper som ska visas använder du cmdleten **Select** i kombination med cmdleten **Get-AzureADUser.** Om du vill kombinera de två cmdletarna använder du "pipe"-tecknet ("|"), som talar om för Azure Active Directory PowerShell för Graph att ta resultaten från ett kommando och skicka det till nästa kommando. Här är ett exempelkommando som visar *DisplayName,* *Department* och *UsageLocation* för varje användarkonto:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Det här kommandot instruerar PowerShell att:
  
1. Få all information om användarkontona **(Get-AzureADUser)** och skicka den till nästa kommando ( **|** ).
    
1.  Visa endast användarkontonamn, avdelning och användningsplats **(Välj Visningsnamn, Avdelning, Användningsplats).**
  
Om du vill visa alla egenskaper för  ett visst användarkonto använder du cmdleten Select och jokertecknet (*). Här är ett exempel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Ett annat exempel är att köra följande kommando för att kontrollera aktiverad status för ett visst användarkonto:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>Visa status för kontosynkronisering

Användarkonton har två källor: 

- Windows Server Active Directory (AD), som är konton som synkroniseras från lokal AD till molnet.

- Azure Active Directory (Azure AD) AD-konton, som skapas direkt i molnet.


Följande kommando instruerar PowerShell att få alla användare som har *attributet DirSyncEnabled* inställt på *Sant.* Du kan använda den för att hitta konton som synkroniseras från den lokala AD.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

Följande kommando instruerar PowerShell att få alla användare som har *attributet DirSyncEnabled* inställt på *Falskt.* Du kan använda det för att hitta konton som endast är molnbaserade.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>Visa konton baserat på en gemensam egenskap

Om du vill vara mer selektiv när det gäller listan med konton som ska visas kan du använda cmdleten **Where** i kombination med **cmdleten Get-AzureADUser.** Om du vill kombinera de två cmdletarna använder du "pipe"-tecknet ("|"), som talar om för Azure Active Directory PowerShell för Graph att ta resultaten från ett kommando och skicka det till nästa kommando. Här är ett exempelkommando som endast visar de användarkonton som har en ospecificerad användningsplats:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Det här kommandot instruerar Azure Active Directory PowerShell för Graph att:
  
1. Få all information om användarkontona **(Get-AzureADUser)** och skicka den till nästa kommando ( **|** ).
    
1. Hitta alla användarkonton som har en ospecificerad användningsplats (**Där {$ \_ . UsageLocation -eq $Null}**). Inom kparenteserna instruerar kommandot PowerShell att endast hitta den uppsättning konton som användarkontoegenskapen Användningslokalisering för (**$ \_ . Användningsbeläggning**) anges inte (**-eq $Null**).
    
Egenskapen **Användningsbeläggning** är bara en av många egenskaper som är kopplade till ett användarkonto. Om du vill visa alla egenskaper för  ett visst användarkonto använder du cmdleten Select och jokertecknet (*). Här är ett exempel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Ort **är** till exempel namnet på en användarkontoegenskap. Du kan använda följande kommando för att lista alla konton för användare som bor i London:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  Syntaxen för  cmdleten Where i de här exemplen **är Where {$ \_ .** [användarnamn för användarkontoegenskap] [jämförelseoperator] [värde] **}**.> [jämförelseoperator] är **-eq** för lika med, **-ne** för inte lika med, **-lt** för mindre än, **-gt** för större än och andra.  [värde] är vanligtvis en sträng (en sekvens med bokstäver, siffror och andra tecken), ett numeriskt värde eller **$Null** ospecificerat värde. Mer information finns i [Var](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory för Windows PowerShell

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="view-all-accounts"></a>Visa alla konton

Om du vill visa hela listan med användarkonton kör du det här kommandot:
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *Msol* i namnet. Kör dessa cmdlets från Windows PowerShell.
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

**Cmdlet:en Get-MsolUser** har också en uppsättning parametrar för att filtrera uppsättningen användarkonton som visas. Kör följande kommando för listan över olicensierade användare (användare som har lagts till i Microsoft 365 men ännu inte har licensierats för att använda någon av tjänsterna):
  
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

Mer information om ytterligare parametrar för att filtrera den uppsättning användarkonton som visas finns i [Get-MsolUser.](/previous-versions/azure/dn194133(v=azure.100))
  
### <a name="view-a-specific-account"></a>Visa ett specifikt konto

Om du vill visa ett specifikt användarkonto kör du följande kommando. Fyll i inloggningsnamnet för användarkontot, som också kallas användarens huvudnamn (UPN). Ta bort tecknen "<" och ">".
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>Visa konton baserat på en gemensam egenskap

Om du vill vara mer selektiv när det gäller listan med konton som ska visas kan du använda cmdleten **Where** i kombination med cmdleten **Get-MsolUser.** Om du vill kombinera de två cmdletarna använder du "pipe"-tecknet ("|"), som säger till PowerShell att ta resultatet från ett kommando och skicka det till nästa kommando. Här är ett exempel som endast visar de användarkonton som har en ospecificerad användningsplats:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Det här kommandot instruerar PowerShell att:
  
1. Hämta all information om användarkontona **(Get-MsolUser)** och skicka den till nästa kommando ( **|** ).
    
1. Hitta alla användarkonton som har en ospecificerad användningsplats (**Där {$ \_ . UsageLocation -eq $Null}**). Inom kparenteserna instruerar kommandot PowerShell att endast hitta den uppsättning konton som användarkontoegenskapen Användningslokalisering för (**$ \_ . Användningsbeläggning**) anges inte (**-eq $Null**).
    
Du bör få information som liknar den här:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

Egenskapen *Användningsbeläggning* är bara en av många egenskaper som är kopplade till ett användarkonto. Om du vill visa alla egenskaper för användarkonton använder du cmdleten **Select** och jokertecknet (*) för att visa dem alla för ett visst användarkonto. Här är ett exempel:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Ort *är* till exempel namnet på en användarkontoegenskap. Du kan använda följande kommando för att visa alla användarkonton för användare som bor i London:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  Syntaxen för  cmdleten Where i de här exemplen **är Where {$ \_ .** [användarnamn för användarkontoegenskap] [jämförelseoperator] [värde] **}**.  [jämförelseoperator] är **-eq** för lika med, **-ne** för inte lika med, **-lt** för mindre än, **-gt för** större än och andra.  [värde] är vanligtvis en sträng (en sekvens med bokstäver, siffror och andra tecken), ett numeriskt värde eller **$Null** ospecificerat värde. Mer information finns i [Var](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).
  
Om du vill kontrollera blockerad status för ett användarkonto använder du följande kommando:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Visa ytterligare egenskapsvärden för konton

Som standard visar **cmdlet:en Get-MsolUser** dessa tre egenskaper för användarkonton:
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
Om du behöver ytterligare egenskaper, till exempel avdelningen där användaren arbetar och landet/regionen där de använder Microsoft 365-tjänster, kan du köra **Get-MsolUser** i kombination med cmdleten **Select** och ange listan med egenskaper för användarkonton. Här är ett exempel:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Det här kommandot instruerar PowerShell att:
  
1. Hämta all information om användarkontona **(Get-MsolUser)** och skicka det till nästa kommando ( **|** ).
    
1. Visa endast användarkontonamn, avdelning och användningsplats **(Välj Visningsnamn, Avdelning, Användningsplats).**
    
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

Med  cmdleten Select kan du välja vilka egenskaper som ska visas. Om du vill visa alla egenskaper för ett visst användarkonto använder du jokertecknet (*). Här är ett exempel:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Om du vill vara mer selektiv när det gäller  listan med konton som ska visas kan du också använda cmdleten Where. Här är ett exempelkommando som endast visar de användarkonton som har en ospecificerad användningsplats:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Det här kommandot instruerar PowerShell att:
  
1. Hämta all information om användarkontona **(Get-MsolUser)** och skicka det till nästa kommando ( **|** ).
    
1. Hitta alla användarkonton som har en ospecificerad användningsplats (**Där {$ \_ . UsageLocation -eq $Null} )** och skicka informationen till nästa kommando ( **|** ). Inom kparenteserna instruerar kommandot PowerShell att endast hitta den uppsättning konton som användarkontoegenskapen Användningslokalisering för (**$ \_ . Användningsbeläggning**) anges inte (**-eq $Null**).
    
1. Visa endast användarkontonamn, avdelning och användningsplats **(Välj Visningsnamn, Avdelning, Användningsplats).**
    
Du bör få information som liknar den här:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Om du använder katalogsynkronisering för att skapa och hantera dina Microsoft 365-användare kan du visa det lokala konto som en Microsoft 365-användare har projicerats från. I följande exempel antas att:

- Azure AD Anslut är konfigurerat att använda standardkällans fästpunkt för ObjectGUID. (Mer information om hur du konfigurerar en fästpunkt för källor finns [i Azure AD Anslut: Designkoncept](/azure/active-directory/hybrid/plan-connect-design-concepts)).
- Modulen Active Directory Domain Services för PowerShell har installerats (se [RSAT-verktyg](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)