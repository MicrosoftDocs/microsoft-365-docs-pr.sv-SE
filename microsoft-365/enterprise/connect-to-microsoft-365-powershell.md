---
title: Ansluta till Microsoft 365 med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Ansluta till Microsoft 365 klientorganisation med PowerShell för Microsoft 365 för att uppföra uppgifter i administrationscenter från kommandoraden.
ms.openlocfilehash: d1e347a13ca5c587fa544ef80a8e289a8dec0a59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694672"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>Ansluta till Microsoft 365 med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Med PowerShell för Microsoft 365 kan du hantera dina Microsoft 365-inställningar från kommandoraden. Det är enkelt att ansluta till PowerShell där du kan installera den programvara som krävs och sedan ansluta till din Microsoft 365-organisation. 

Det finns två versioner av PowerShell-modulen som du använder för att ansluta till Microsoft 365 och administrera användarkonton, grupper och licenser:

- Azure Active Directory PowerShell för Graph (cmdletar inkluderar **AzureAD** i namnet)
- Microsoft Azure Active Directory-modulen för Windows PowerShell (cmdlets innehåller**Msol** i namnet) 

Från och med datumet i den här artikeln ersätter Azure Active Directory PowerShell för Graph inte funktionaliteten i cmdletar för administration av Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen för användare, grupper och licenser. I vissa fall måste du använda båda versionerna. Du kan på ett säkert sätt installera båda versionerna på samma dator.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

Du kan använda följande versioner av Windows:
    
  - Windows 10, Windows 8.1, Windows 8 eller Windows 7 Service Pack 1 (SP1). 
    
  - Firefox Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 eller Windows Server 2008 R2 SP1

    > [!NOTE]
    > För Azure Active Directory PowerShell för Graph-modulen måste du använda PowerShell version 5.1 eller senare. För Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen måste du använda PowerShell version 5.1 eller senare upp till PowerShell version 6. Du kan inte använda PowerShell version 7. För Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 och Windows Server 2008 R2 SP1 laddar du ned och installerar [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616). 
    
    > [!NOTE]
    > Använd en 64-bitarsversion av Windows. Stöd för 32-bitarsversionen Microsoft Azure Active Directory-modulen för Windows PowerShell har utgått i oktober 2014.
    
De här procedurerna är avsedda för användaren som är medlemmar i en administratörs roll för Microsoft 365. Mer information finns i [Om administratörsroller](https://go.microsoft.com/fwlink/p/?LinkId=532367).


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>Ansluta med Azure Active Directory Windows PowerShell för Graph-modulen

Kommandon i Azure Active Directory PowerShell för Graph-modulen har **AzureAD** i namnet på cmdleten. Du kan installera [Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory)-modulen eller [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-3.6.1).

För procedurer som kräver nya cmdletar i Azure Active Directory PowerShell för Graph-modulen ska du använda följande steg för att installera modulen och ansluta till din Microsoft 365-prenumeration.

>[!Note]
>Mer information om stödet för olika versioner av Microsoft Windows finns i [Azure Active Directory PowerShell för Graph modulen](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).
>

### <a name="step-1-install-required-software"></a>Steg 1: installera den programvara som krävs

De här stegen är nödvändiga en gång på datorn, inte varje gång du ansluter. Men du måste förmodligen installera nyare versioner av programvaran med jämna mellanrum.
  
1. Öppna en upphöjd PowerShell-kommandotolk i Windows (kör Windows PowerShell som administratör).
    
2. Kör det här kommandot i en **Windows PowerShell-kommandotolk på administratörsnivå**:
    
  ```powershell
  Install-Module -Name AzureAD
  ```

Om du uppmanas att installera en modul från en databas som inte är betrodd skriver du **Y** och trycker på RETUR.

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Steg 2: Ansluta till Azure AD för din Microsoft 365-prenumeration

Om du vill ansluta till Azure AD för din Microsoft 365-prenumeration med kontonamn och lösenord eller multifaktorautentisering (MFA) kör du ett av de här kommandona från en Windows PowerShell-kommandotolk (det behöver inte vara upphöjd).

| Office 365 moln | Kommando |
|:-------|:-----|
| Office 365 över hela världen (+ GCC) | `Connect-AzureAD` |
| Office 365 genom 21 Vianet | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Tyskland | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 U.S. Government DoD och Office 365 U.S. Government GCC High | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

Skriv ditt användarnamn och lösenord för ditt Microsoft 365-konto för arbetet eller skolan i **Logga in på ditt konto**, och klicka sedan på**OK**.

Om du använder MFA, följ anvisningarna i de andra dialogrutarna för att ange ytterligare autentiseringsinformation, till exempel en verifieringskod.

När du har anslutit kan du använda cmdletar för [Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).
  

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Ansluta med Azure Active Directory-modulen för Windows PowerShell

Kommandon Azure Active Directory-modul för Windows PowerShell innehåller **Msol** in cmdlet-namnet.

PowerShell version 7 och senare stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell modulen och-cmdlets med**MSOL** i namnet. För PowerShell version 7 eller senare måste du använda Azure Active Directory PowerShell för Graph-modulen eller Azure PowerShell.

PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet. Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell. 
    
### <a name="step-1-install-required-software"></a>Steg 1: installera den programvara som krävs

De här stegen är nödvändiga en gång på datorn, inte varje gång du ansluter. Men du måste förmodligen installera nyare versioner av programvaran med jämna mellanrum.
  
1.  Om du inte kör Windows 10, installera 64-bitarsversionen av Microsoft Online Services – inloggningsassistent: [Microsoft Online Services – inloggningsassistent för IT-experter RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).
    
2. Installera Microsoft Azure Active Directory-modulen för Windows PowerShell genom att följa de här stegen:
    
  - Öppna en upphöjd PowerShell-kommandotolk i Windows (kör Windows PowerShell som administratör).
  - Kör kommandot **Installera-modul MSOnline**.
  - Om du uppmanas att installera NuGet-leverantör skriver du **Y** och trycker på RETUR.
  - Om du uppmanas att installera modulen från PSGGallery, skriver du **Y** och trycker på RETUR.
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Steg 2: Ansluta till Azure AD för din Microsoft 365-prenumeration

Om du vill ansluta till Azure AD för din Microsoft 365-prenumeration med kontonamn och lösenord eller multifaktorautentisering (MFA) kör du ett av de här kommandona från en Windows PowerShell-kommandotolk (det behöver inte vara upphöjd).

| Office 365 moln | Kommando |
|:-------|:-----|
| Office 365 över hela världen (+ GCC) | `Connect-MsolService` |
| Office 365 genom 21 Vianet | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Tyskland | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 U.S. Government DoD och Office 365 U.S. Government GCC High | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

Skriv ditt användarnamn och lösenord för ditt Microsoft 365-konto för arbetet eller skolan i **Logga in på ditt konto**, och klicka sedan på**OK**.

Om du använder MFA, följ anvisningarna i de andra dialogrutarna för att ange ytterligare autentiseringsinformation, till exempel en verifieringskod.

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du inte får några felmeddelande kunde du ansluta. Ett snabb test är att köra en Microsoft 365-cmdlet, till exempel**get-MsolUser**och se resultatet.
  
Om du får felfelmeddelanden, kontrollera följande krav:
  
- **Ett vanligt problem är ett felaktigt lösenord**. Kör steg 2 igen. och var uppmärksam på det användarnamn och lösenord som du anger.
    
- **Microsoft Azure Active Directory-modulen för Windows PowerShell kräver att Microsoft .NET Framework 3.5.* funktionen x * är aktiverad på din dator * *. Det är troligt att datorn har en nyare version installerad (till exempel 4 eller 4.5*. x *), men bakåtkompatibilitet med äldre versioner av .NET Framework kan aktiveras eller inaktiveras. Mer information finns i följande avsnitt:
    
  - För mer information om Windows Server 2012 eller Windows Server 2012 R2 se[Aktivera .NET Framework 3.5 med hjälp av guiden Lägg till roller och funktioner](https://go.microsoft.com/fwlink/p/?LinkId=532368)
    
  - För Windows 7 eller Windows Server 2008 R2 se [Det går inte att öppna Azure Active Directory-modulen för Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370)

  - För Windows 10, Windows 8.1, och Windows 8, se [Installera .NET Framework 3.5 i Windows 10, Windows 8.1, och Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)

  
- **Din version av Microsoft Azure Active Directory-modulen för Windows PowerShell kanske är inaktuell.** Om du vill kontrollera detta kör du följande kommando i PowerShell för Microsoft 365 eller Microsoft Azure Active Directory-modulen för Windows PowerShell:
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    Om versionsnumret som returneras är lägre än värdet 1.0.8070.2, avinstallerar du Microsoft Azure Active Directory-modulen för Windows PowerShell och installerar från steg 1 ovan.

- **Om du får ett anslutningsfel se ämnet:** ["Ansluta-MsolService: ett undantag av typen har kastats" misslyckades](https://go.microsoft.com/fwlink/p/?LinkId=532377).
    
- **Om du får felmeddelandet "Hämta objekt: det går inte att hitta sökvägen" använder du följande kommando:** 

```powershell
  (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
```

## <a name="see-also"></a>Se även

- [Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
- [Ansluta till alla Microsoft 365-tjänster i ett enda Windows PowerShell-fönster](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
