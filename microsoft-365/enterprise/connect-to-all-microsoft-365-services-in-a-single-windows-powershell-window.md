---
title: Ansluta till alla Microsoft 365-tjänster i ett enda PowerShell-fönster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/02/2021
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
ms.openlocfilehash: 18ff8e1789242b4dde3b4b31aaccf2462e4c5d74
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905134"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Ansluta till alla Microsoft 365-tjänster i ett enda PowerShell-fönster

När du använder PowerShell för att hantera Microsoft 365 kan du ha flera PowerShell-sessioner öppna samtidigt. Du kanske har olika PowerShell-fönster för att hantera användarkonton, SharePoint Online, Exchange Online, Skype för företag – Online, Microsoft Teams och Säkerhets- och &amp; efterlevnadscentret.
  
Det här scenariot är inte optimalt för att hantera Microsoft 365 eftersom du inte kan utbyta data mellan fönstren för hantering av flera tjänster. Den här artikeln beskriver hur du använder en enda instans av PowerShell för att hantera Microsoft 365-konton, Skype för Företag – Online, Exchange Online, SharePoint Online, Microsoft Teams och Säkerhets- och &amp; efterlevnadscentret.

>[!Note]
>Den här artikeln innehåller för närvarande bara kommandon för att ansluta till det världsomfattande (+GCC) molnet. I kommentarerna finns länkar till artiklar om anslutning till andra Microsoft 365-moln.

## <a name="before-you-begin"></a>Innan du börjar

Innan du kan hantera hela Microsoft 365 från en enda instans av PowerShell måste följande förutsättningar vara uppfyllda:
  
- Det Microsoft 365-kontot för arbete eller skola som du använder måste vara en medlem i en administratörsroll för Microsoft 365. Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md). Det här är ett krav för PowerShell för Microsoft 365, men inte nödvändigtvis för alla andra Microsoft 365-tjänster.
    
- Du kan använda följande 64-bitars versioner av Windows:
    
  - Windows 10
    
  - Windows 8.1 eller Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2- eller Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \* Du måste installera Microsoft .NET Framework 4,5.*x* och sedan Windows Management Framework 3,0 eller 4,0. Mer information finns i [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview).
    
    Du måste använda en 64-bitars version av Windows på grund av kraven för Skype för företag – Online-modulen och en av Microsoft 365-modulerna.
    
- Du måste installera de moduler som krävs för Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype för företag – Online och Teams:
    
  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [Skype för företag – Online, PowerShell-modul](/microsoftteams/teams-powershell-overview)
  - [Exchange Online PowerShell V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Teams PowerShell översikt](/microsoftteams/teams-powershell-overview)
    
-  PowerShell måste konfigureras för körning av signerade skript för Skype för Företag – Online och Säkerhets- och &amp; efterlevnadscentret. Kör följande kommando i en upphöjd PowerShell-session (ett PowerShell-fönster som du **Kör som administratör**).
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a>Anslutningssteg vid användning av bara ett lösenord

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
  
   Om du använder Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen, kör det här kommandot.
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *MSOL* i deras namn. Du måste köra dessa cmdlets från PowerShell.

4. Kör dessa kommandon för att ansluta till SharePoint Online. Ange organisationsnamnet för din domän. Till exempel, för "litwareinc\.onmicrosoft.com" är organisationens namnvärdet "litwareinc".
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. Kör dessa kommandon för att ansluta till Skype för Företag – Online. En varning om att öka `WSMan NetworkDelayms` värdet visas första gången du ansluter. Ignorera det.
     
   > [!Note]
   > Skype för företag – Online-Connector är för närvarande en del av den senaste versionen av Teams PowerShell-modul. Om du använder den senaste versionen av Teams PowerShell, behöver du inte installera Skype för företag – Online-Connector.
   
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

6. Kör dessa kommandon för att ansluta till Exchange Online.
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > Om du vill ansluta till Exchange Online för Microsoft 365-moln som inte är världsomspännande går du till [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

7. Kör dessa kommandon för att ansluta till &amp; säkerhet- och efterlevnadscenter.
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > Om du vill ansluta till &amp; säkerhet- och efterlevnadscenter för Microsoft 365-moln, annat än världsomspännande läser du [Ansluta till Säkerhets- och efterlevnadscenter PowerShell](/powershell/exchange/connect-to-scc-powershell).

8. Kör dessa kommandon för att ansluta till Teams PowerShell.
    
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > För att ansluta till Microsoft Teams-moln som inte är *världsomspännande*, se [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams).
  



### <a name="azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell för Graph-modulen

Här följer kommandon för alla tjänster i ett enda textblock när du använder Azure Active Directory PowerShell för Graph-modulen. Ange namnet på din domänvärd och UPN på inloggning och kör alla samtidigt.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen

Här följer kommandon för alla tjänster i ett enda textblock när du använder Microsoft Azure Active Directory-modul för Windows PowerShell-modulen. Ange namnet på din domänvärd och UPN för din inloggning och kör alla samtidigt.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>Anslutningssteg när du använder multifaktorautentisering

### <a name="azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell för modulen Graph

Här är alla kommandon i ett enda textblock för att ansluta till flera Microsoft 365-tjänster när du använder multifaktorautentisering med Azure Active Directory PowerShell för Graph-modulen.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Microsoft Azure Active Directory-modul för Windows PowerShell-modulen

Här är alla kommandon i ett enda textblock för att ansluta till flera Microsoft 365-tjänster när du använder multifaktorautentisering med Microsoft Azure Active Directory-modul för Windows PowerShell-modulen.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>Stäng PowerShell-fönstret.

När du är redo att stänga ner PowerShell-fönstret kör du det här kommandot för att ta bort aktiva sessioner på Skype för Företag – Online, SharePoint Online och Teams:
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a>Se även

- [Ansluta till Microsoft 365 med PowerShell](connect-to-microsoft-365-powershell.md)
- [Hantera SharePoint Online med PowerShell](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)