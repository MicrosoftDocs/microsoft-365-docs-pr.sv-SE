---
title: Ta bort eller inaktivera Hybrid från Skype för företag och Exchange
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln beskrivs hur du tar bort eller inaktiverar HYBRIDS ökning från Skype för företag och Exchange.
ms.openlocfilehash: da0887936f5def69ad80c8f04381bcb3a85c2349
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694390"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Ta bort eller inaktivera Hybrid från Skype för företag och Exchange

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Om du har aktiverat hybrid modern (HMA) endast för att hitta den olämplig för din nuvarande miljö kan du avaktivera HMA. I den här artikeln förklaras hur.
  
## <a name="who-is-this-article-for"></a>Vem är den här artikeln för?

Om du har aktiverat modern lösenordsautentisering i Skype för företag – Online eller lokalt och/eller via Exchange Online eller lokalt och hittat dig måste du inaktivera HMA, de här stegen är till för dig.

> [!IMPORTANT]
> Se "[Skype för företag-topologin som stöds med modern verifikation](https://technet.microsoft.com/library/mt803262.aspx)" om du är i Skype för företag – Online eller lokalt, har du en HMA och måste titta på topologier som stöds innan du börjar.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Så här inaktiverar du hybrid modern (Exchange)

1. **Lokal Exchange**: Öppna Exchange Management Shell och kör följande kommandon: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online**: [Anslut till Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) med Remote PowerShell. Kör följande kommando för att aktivera flaggan  *OAuth2ClientProfileEnabled*  till "false":

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Så här inaktiverar du hybrid modern (Skype för företag)

1. **Skype för företag – lokalt**: kör följande kommandon i Skype för företag Management Shell:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype för företag – Online**: [Anslut till Skype för företag – Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) med fjärr-PowerShell. Kör följande kommando för att inaktivera modern inloggningsautentisering:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Länka tillbaka till den moderna verifikations översikten](hybrid-modern-auth-overview.md) . 
  

