---
title: Ansluta till alla Microsoft 365-tjänster i ett enda PowerShell-fönster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: 'Sammanfattning: Ansluta till alla Microsoft 365-tjänster i ett enda PowerShell-fönster.'
ms.openlocfilehash: e4cb3a10d14f6d4c16ef9323d6e5b3c500ebc0c5
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545980"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Ansluta till alla Microsoft 365-tjänster i ett enda PowerShell-fönster

När du använder PowerShell för att hantera Microsoft 365 går det att ha flera olika PowerShell-sessioner öppna samtidigt i olika PowerShell-fönster som hör till hanterade användarkonton, SharePoint Online, Exchange Online, Skype för företag – Online, Microsoft Teams och Säkerhets- &amp; efterlevnadscenter. 
  
Du kan inte använda det här alternativet för att hantera Microsoft 365 eftersom du inte kan utbyta data mellan fönstren för hantering av flera tjänster. I den här artikeln beskrivs hur du använder en enda instans av PowerShell, som du kan använda för att hantera Microsoft 365-konton, Skype för företag – Online, Exchange Online, SharePoint Online, Microsoft Teams och Säkerhets- &amp; efterlevnadscenter.

>[!Note]
>I den här artikeln finns för närvarande bara kommandon för att ansluta till molnet över hela världen (+GCC). I kommentarerna finns länkar till artiklar med information om hur du ansluter till andra Microsoft 365-moln.
>

## <a name="before-you-begin"></a>Innan du börjar

Innan du kan hantera hela Microsoft 365 från en enda instans av PowerShell måste följande förutsättningar vara uppfyllda:
  
- Det Microsoft 365-konto för arbete eller skola som du använder för de här procedurerna måste vara medlem i en administratörsroll för Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles). Det här är ett krav för PowerShell för Microsoft 365, inte nödvändigtvis för alla andra Microsoft 365-tjänster.
    
- Du kan använda följande 64-bitars versioner av Windows:
    
  - Windows 10
    
  - Windows 8.1 eller Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2- eller Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \* Du måste installera Microsoft .NET Framework 4.5.*x* och sedan antingen Windows Management Framework 3.0 eller Windows Management Framework 4.0. Mer information finns i [installera .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) och [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) eller [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).
    
    Du måste använda en 64-bitars version av Windows på grund av kraven för Skype för företag – Online-modulen och en av Microsoft 365-modulerna.
    
- Du måste installera de moduler som krävs för Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype för företag – Online och Teams:
    
  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [Skype för företag – Online, PowerShell-modul](https://go.microsoft.com/fwlink/p/?LinkId=532439)
  - [Exchange Online PowerShell V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Teams PowerShell översikt](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  PowerShell måste konfigureras för körning av signerade skript för Skype för företag – Online och Säkerhets- &amp; efterlevnadscenter. Det gör du genom att köra följande kommando i en upphöjd PowerShell-session (ett PowerShell-fönster som du öppnar genom att välja **Kör som administratör**).
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a>Exchange Online och Säkerhets &amp; Efterlevnadscenter med modulen Exchange Online PowerShell V2

I den här artikeln används Exchange Online PowerShell V2-modulen för att ansluta till både Exchange Online och Säkerhets &amp; Efterlevnadscenter. Men för närvarande går det inte att ansluta till både Exchange Online och Säkerhets &amp; Efterlevnadscenter **i samma PowerShell-fönster**.

Därför måste du välja en anslutning med endera Exchange Online *eller* Säkerhets &amp; Efterlevnadscenter när du konfigurerar ett PowerShell-fönster för flera Microsoft 365-tjänster.

## <a name="connection-steps-when-using-just-a-password"></a>Anslutningssteg när du bara använder ett lösenord

Här är några steg för att ansluta till alla tjänster i ett enda PowerShell-fönster när du bara använder ett lösenord för inloggning.
  
1. Öppna Windows PowerShell.
    
2. Kör detta kommando och ange inloggningsuppgifter för ditt Microsoft 365-arbets-eller skolkonto.
    
   ```powershell
   $credential = Get-Credential
   ```

3. Kör det här kommandot för att ansluta till Azure AD med hjälp av Azure Active Directory PowerShell för Graph-modulen.
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   Om du använder modulen Microsoft Azure Active Directory-modul för Windows PowerShell kör du det här kommandot.
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet. Om du vill fortsätta använda dessa cmdlets måste du köra dem från PowerShell.

4. Kör dessa kommandon för att ansluta till SharePoint Online. Ange organisationsnamnet för din domän. Till exempel, för "litwareinc.onmicrosoft.com" är organisationensnamnet "litwareinc".
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. Kör dessa kommandon för att ansluta till Skype för företag – Online. Ett varningsmeddelande om att öka `WSMan NetworkDelayms` värdet förväntas första gången du ansluter och ska ignoreras.
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. Kör det här kommandot när du vill ansluta till Exchange Online.
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > Om du vill ansluta till Exchange Online för Microsoft 365-moln som inte är världsomspännande se [-Ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

7. Kör dessa kommandon för att ansluta till Säkerhets &amp; Efterlevnadscenter.
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > Om du vill ansluta till &amp; säkerhet- och efterlevnadscenter för Microsoft 365-moln, annat än världsomspännande läser du [Ansluta till Säkerhets- och efterlevnadscenter PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

8. Kör dessa kommandon för att ansluta till Teams PowerShell.
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Om du vill ansluta till Microsoft Teams-moln som inte är världsomspännande läser du [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).


### <a name="azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell för modulen Graph

Här följer kommandon för alla tjänster *, förutom Säkerhets &amp; Efterlevnadscenter* i ett enda block med hjälp av modulen Azure Active Directory PowerShell för modulen Graph. Ange namnet på domänvärden och kör alla samtidigt.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

Här följer kommandon för alla tjänster *, förutom Exchange Online * i ett enda block med hjälp av modulen Azure Active Directory PowerShell för modulen Graph. Ange namnet på domänvärden och UPN på din inloggning och kör alla samtidigt.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Microsoft Azure Active Directory-modulen för modulen Windows PowerShell

Här följer kommandon för alla tjänster *, förutom Säkerhets &amp; Efterlevnadscenter* i ett enda block med hjälp av modulen Microsoft Azure Active Directory för modulen PowerShell. Ange namnet på domänvärden och kör alla samtidigt.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

Här följer kommandon för alla tjänster *, förutom Exchange Online* i ett enda block med hjälp av modulen Microsoft Azure Active Directory för modulen Windows PowerShell. Ange namnet på domänvärden och UPN på din inloggning och kör alla samtidigt.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a>Anslutningssteg när du använder multifaktorautentisering

### <a name="azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell för modulen Graph

Här är alla kommandon i ett enda block för att ansluta till flera Microsoft 365-tjänster *förutom Säkerhets &amp; Efterlevnadscenter * med multifaktorautentisering med hjälp av Azure Active Directory PowerShell för modulen Graph.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
Här är alla kommandon i ett enda block för att ansluta till flera Microsoft 365-tjänster *förutom Exchange Online * med multifaktorautentisering med hjälp av Azure Active Directory PowerShell för modulen Graph.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Microsoft Azure Active Directory-modulen för modulen Windows PowerShell

Här är alla kommandon i ett enda block för att ansluta till flera Microsoft 365-tjänster *förutom Säkerhets &amp; Efterlevnadscenter* med multifaktorautentisering med hjälp av modulen Microsoft Azure Active Directory för modulen Windows PowerShell..

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
Här är alla kommandon i ett enda block för att ansluta till flera Microsoft 365-tjänster *förutom Exchange Online * med multifaktorautentisering med hjälp av modulen Microsoft Azure Active Directory för modulen Windows PowerShell.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>Stäng PowerShell-fönstret.

När du är redo att stänga PowerShell-fönstret kör du det här kommandot för att ta bort aktiva sessioner till Skype för företag – Online, SharePoint Online och Teams:
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```


## <a name="see-also"></a>Se även

- [Ansluta till Microsoft 365 med PowerShell](connect-to-microsoft-365-powershell.md)
- [Hantera SharePoint Online med PowerShell](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
