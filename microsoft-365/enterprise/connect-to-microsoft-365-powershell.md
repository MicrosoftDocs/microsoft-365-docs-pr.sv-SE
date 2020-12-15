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
description: Anslut till din Microsoft 365-klientorganisation med PowerShell för Microsoft 365 för att utföra uppgifter i administrationscenter från kommandoraden.
ms.openlocfilehash: 33f9af45418ae8a1f126d2b321e7246201bd1f6e
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002411"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>Ansluta till Microsoft 365 med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Med PowerShell för Microsoft 365 kan du hantera dina Microsoft 365-inställningar från kommandoraden. Om du vill ansluta till PowerShell installerar du bara den programvara som krävs och ansluter sedan till din Microsoft 365-organisation.

Det finns två versioner av PowerShell-modulen som du kan använda för att ansluta till Microsoft 365 och administrera användarkonton, grupper och licenser:

- Azure Active Directory PowerShell för Graph, vars cmdlets har *AzureAD* i namnet
- Microsoft Azure Active Directory-modul för Windows PowerShell, vars cmdlets har *Msol* i namnet

För närvarande ersätter Azure Active Directory PowerShell för Graph-modulen inte helt funktionaliteten i Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen för användar-, grupp- och licensadministration. I vissa fall måste du använda båda versionerna. Du kan på ett säkert sätt installera båda versionerna på samma dator.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?


**Operativsystem**

Du måste använda en 64-bitarsversion av Windows. Stöd för 32-bitarsversionen av Microsoft Azure Active Directory-modulen för Windows PowerShell utgick i oktober 2014.

Du kan använda följande versioner av Windows:
    
  - Windows 10, Windows 8.1, Windows 8 eller Windows 7 Service Pack 1 (SP1). 
    
  - Firefox Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 eller Windows Server 2008 R2 SP1

>[!Note]
>För Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 och Windows Server 2008 R2 SP1 laddar du ned och installerar [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).

**PowerShell**

- För Azure Active Directory PowerShell för Graph-modulen måste du använda PowerShell version 5.1 eller senare.

- För Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen måste du använda PowerShell version 5.1 eller senare, upp till PowerShell version 6. Du kan inte använda PowerShell version 7.
       
>[!Note]
>De här procedurerna är avsedda för användaren som är medlemmar i en administratörs roll för Microsoft 365. Mer information finns i [Om administratörsroller](https://go.microsoft.com/fwlink/p/?LinkId=532367).


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>Ansluta med Azure Active Directory Windows PowerShell för Graph-modulen

Kommandon i Azure Active Directory PowerShell för Graph-modulen har *AzureAD* i namnet på cmdleten. Du kan installera [Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)-modulen eller [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).

För procedurer som kräver nya cmdlets i Azure Active Directory PowerShell för Graph-modulen ska du använda följande steg för att installera modulen och ansluta till din Microsoft 365-prenumeration.

> [!Note]
> Mer information om stödet för olika versioner av Microsoft Windows finns i [Azure Active Directory PowerShell för Graph-modul](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).

### <a name="step-1-install-the-required-software"></a>Steg 1: Installera den programvara som krävs

De här stegen krävs bara en gång på din dator. Men du måste troligen uppdatera programvaran regelbundet.
  
1. Öppna ett upphöjt PowerShell-kommandotolkfönster (kör Windows PowerShell som administratör).
    
2. Kör det här kommandot:
    
    ```powershell
    Install-Module -Name AzureAD
    ```

   Om du uppmanas att installera en modul från en databas som inte är betrodd skriver du **Y** och trycker på Retur.

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Steg 2: Ansluta till Azure AD för din Microsoft 365-prenumeration

För att ansluta till Azure Active Directory (Azure AD) för din Microsoft 365-prenumeration med ett kontonamn och lösenord, eller med multifaktorautentisering (MFA), kör du ett av de här kommandona från en Windows PowerShell-kommandotolk. (Det behöver inte vara upphöjt.)

| Office 365 moln | Kommando |
|:-------|:-----|
| Office 365 över hela världen (+ GCC) | `Connect-AzureAD` |
| Office 365 genom 21 Vianet | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Tyskland | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 U.S. Government DoD och Office 365 U.S. Government GCC High | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

Skriv ditt användarnamn och lösenord för ditt Microsoft 365-konto för arbetet eller skolan i dialogrutan **Logga in på ditt konto**, och välj sedan **OK**.

Om du använder multifaktorautentisering, följ instruktionerna för att ange ytterligare autentiseringsinformation, till exempel en verifieringskod.

När du har anslutit kan du använda cmdlets för [Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/powershell/module/azuread).

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Ansluta med Azure Active Directory-modulen för Windows PowerShell

>[!Note]
>Cmdlets i Microsoft Azure Active Directory-modulen för Windows PowerShell har *Msol* i namnet.

PowerShell version 7 och senare stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell modul och cmdlets med *Msol* i namnet. För PowerShell version 7 eller senare måste du använda Azure Active Directory PowerShell för Graph-modulen eller Azure PowerShell.

PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med *Msol* i namnet. Kör dessa cmdlets från Windows PowerShell.
    
### <a name="step-1-install-the-required-software"></a>Steg 1: Installera den programvara som krävs

De här stegen krävs bara en gång på din dator. Men du måste troligen uppdatera programvaran regelbundet.
  
1.  Om du inte kör Windows 10, installera 64-bitarsversionen av Inloggningsassistenten för Microsoft Online Services: [Inloggningsassistenten för Microsoft Online Services för IT-experter RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).
    
2. Följ de här stegen för att installera Microsoft Azure Active Directory-modulen för Windows PowerShell:
    
   1. Öppna en upphöjd PowerShell-kommandotolk i Windows (kör Windows PowerShell som administratör).
   1.  Kör kommandot **Installera-modul MSOnline**.
   1. Om du uppmanas att installera NuGet-leverantören, skriv **Y** och tryck på Retur.
   1. Om du uppmanas att installera modulen från PSGGallery, skriv **Y** och tryck på Retur.
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Steg 2: Ansluta till Azure AD för din Microsoft 365-prenumeration

För att ansluta till Azure AD för din Microsoft 365-prenumeration med ett kontonamn och lösenord eller med multifaktorautentisering (MFA), kör ett av de här kommandona från en Windows PowerShell-kommandotolk. (Det behöver inte vara upphöjt.)

| Office 365 moln | Kommando |
|:-------|:-----|
| Office 365 över hela världen (+ GCC) | `Connect-MsolService` |
| Office 365 genom 21 Vianet | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Tyskland | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 U.S. Government DoD och Office 365 U.S. Government GCC High | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

Skriv ditt användarnamn och lösenord för ditt Microsoft 365-konto för arbetet eller skolan i dialogrutan **Logga in på ditt konto**, och välj sedan **OK**.

Om du använder multifaktorautentisering, följ instruktionerna för att ange ytterligare autentiseringsinformation, till exempel en verifieringskod.

### <a name="how-do-you-know-it-worked"></a>Hur vet du om det har fungerat?

Om du inte får ett felmeddelande har du anslutit framgångsrikt. Ett snabbt test är att köra en Microsoft 365-cmdlet, till exempel **Get-MsolUser** och se resultaten.
  
Om du får ett felmeddelande, kontrollera följande problem:
  
- **Ett vanligt problem är ett felaktigt lösenord**. Kör [Steg 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) igen och var uppmärksam på det användarnamn och lösenord som du anger.
    
- **Microsoft Azure Active Directory-modulen för Windows PowerShell kräver att Microsoft .NET Framework 3.5.* x* är aktiverad på din dator**. Det är troligt att din dator har en nyare version installerad (till exempel 4 eller 4.5.* x*). Men bakåtkompatibilitet med äldre versioner av .NET Framework kan aktiveras och inaktiveras. Mer information finns i följande artiklar:
    
  - Mer information om Windows Server 2012 eller Windows Server 2012 R2 finns i[Aktivera .NET Framework 3.5 med hjälp av guiden Lägg till roller och funktioner](https://go.microsoft.com/fwlink/p/?LinkId=532368).
    
  - För Windows 7 eller Windows Server 2008 R2 läser du [Det går inte att öppna Azure Active Directory-modulen för Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).

  - För Windows 10, Windows 8.1 och Windows 8 läser du [Installera .NET Framework 3.5 i Windows 10, Windows 8.1 och Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10).

  
- **Din version av Microsoft Azure Active Directory-modulen för Windows PowerShell kanske är inaktuell.** Om du vill kontrollera detta kör du följande kommando i PowerShell för Microsoft 365 eller Microsoft Azure Active Directory-modulen för Windows PowerShell:
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    Om versionsnumret som returneras är lägre än *1.0.8070.2*, avinstallerar Microsoft Azure Active Directory-modulen för Windows PowerShell och installerar från [Steg 1](#step-1-install-the-required-software)ovan.

- **Om du får ett anslutningsfelmeddelande**, se [Felet "Connect-MsolService: Undantag av typen" misslyckades](https://go.microsoft.com/fwlink/p/?LinkId=532377).
    
- **Om du får felmeddelandet "Get-Item: Det går inte att hitta sökvägen"**, kör kommandot:


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a>Se även

- [Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
- [Ansluta till alla Microsoft 365-tjänster i ett enda Windows PowerShell-fönster](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
