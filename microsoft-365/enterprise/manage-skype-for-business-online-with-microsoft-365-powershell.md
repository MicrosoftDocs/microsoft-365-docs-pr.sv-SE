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
description: 'Sammanfattning: Använd PowerShell för Microsoft 365 om du vill hantera principer för Skype för företag – Online, principer för användare och mötesinställningar.'
ms.openlocfilehash: aea78d135a5d7ffbb5d8480c549d0fdee88f7d51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694773"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>Hantera Skype för företag – Online med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

En av de viktigaste aktiviteterna i valfri Skype för företag – Online-administratör är hantering av principer. Även om du kan utföra vissa av de här uppgifterna i administrationscentret för Microsoft 365, kan andra uppgifter vara mycket snabbare och enklare i PowerShell. 

## <a name="before-you-start"></a>Innan du börjar

Ladda ned och installera [ Anslutningsmodulen för Skype för företag – Online](https://www.microsoft.com/download/details.aspx?id=39366)och starta om datorn.


## <a name="connect-using-a-skype-for-business-online-administrator-account-name-and-password"></a>Ansluta med namnet och lösenordet för ditt administratörskonto för Skype för företag – Online

1. Öppna en Windows PowerShell kommandotolk och kör följande kommandon: 
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. I dialogrutan **Begäran om autentiseringsuppgifter för Windows PowerShell** anger du användarnamnet och lösenordet för ditt administratörskonto för Skype för företag – Online och klickar på **OK**.


## <a name="connect-using-a-skype-for-business-online-administrator-account-with-multi-factor-authentication"></a>Ansluta med ett namnet och lösenordet för ditt administratörskonto för Skype för företag – Online med multifaktorautentisering

1. Öppna en Windows PowerShell kommandotolk och kör följande kommandon:

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. Skriv användarnamnet för ditt administratörskonto för Skype för företag – Online när du uppmanas av kommandot **New-CsOnlineSession**.

3. I dialogrutan **Logga in på ditt konto** skriver du ditt lösenordet för ditt administratörskonto för Skype för företag – Online och klickar sedan på **logga in**.

4. Följ anvisningarna i dialogrutan **Logga in på ditt konto** för att ange ytterligare autentiseringsinformation, till exempel en verifieringskod, och klicka sedan på **Logga in**.

Mer information finns i följande avsnitt:
  
- [Hantera Skype för företag – Onlineprinciper med PowerShell](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [Tilldela per användare Skype för företag – Onlineprinciper med PowerShell](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a>Se även

[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)

[PowerShell cmdlet-referenser för Skype för företag](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)

