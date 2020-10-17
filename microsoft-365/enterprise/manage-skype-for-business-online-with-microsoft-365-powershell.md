---
title: Hantera Skype för företag – Online med PowerShell
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
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Använd PowerShell för Microsoft 365 om du vill hantera principer för Skype för företag – Online, principer för användare och mötesinställningar.
ms.openlocfilehash: ff35463dc0c2e16106432c393b10e31e6bf0a5d2
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477107"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>Hantera Skype för företag – Online med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Administratörer av Skype för företag – Online ansvarar för hantering av principer. Även om du kan utföra vissa av de här uppgifterna i administrationscentret för Microsoft 365, kan andra uppgifter vara enklare i PowerShell.

## <a name="before-you-start"></a>Innan du börjar

  > [!Note]
   > Skype för företag – Online-Connector är för närvarande en del av den senaste versionen av Teams PowerShell-modul. Om du använder den senaste versionen av Teams PowerShell, behöver du inte installera Skype för företag – Online-Connector.
   
Installera [Teams PowerShell-modul](https://docs.microsoft.com/microsoftteams/teams-powershell-install).


## <a name="connect-using-admin-credentials"></a>Anslut med administratörsuppgifter.

1. Öppna en Windows PowerShell kommandotolk och kör följande kommandon:
    
   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. I dialogrutan **Begäran om autentiseringsuppgifter för Windows PowerShell** anger du användarnamnet och lösenordet för ditt administratörskonto och välj **OK**.


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a>Ansluta med ett administratörskonto med multifaktorautentisering

1. Öppna en Windows PowerShell kommandotolk och kör följande kommandon:

   ```powershell
   Import-Module MicrosoftTeams
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. Skriv användarnamnet för ditt administratörskonto för Skype för företag – Online när du uppmanas av kommandot **New-CsOnlineSession**.

3. I dialogrutan **Logga in på ditt konto** skriver du ditt lösenordet för ditt administratörskonto för Skype för företag – Online och välj sedan **logga in**.

4. I dialogrutan **Logga in på ditt konto** följ anvisningarna för att lägga till autentiseringsinformation, till exempel en verifieringskod, och välj sedan **Verifiera**.

Mer information finns i:
  
- [Hantera Skype för företag – Onlineprinciper med PowerShell](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [Tilldela per användare Skype för företag – Onlineprinciper med PowerShell](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a>Se även

[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)

[PowerShell cmdlet-referenser för Skype för företag](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
