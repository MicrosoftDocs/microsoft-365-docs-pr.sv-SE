---
title: Ta bort eller inaktivera hybrid modern autentisering från Skype för företag och Exchange
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
description: I den här artikeln förklaras hur du tar bort eller inaktiverar modern hybridautentisering Skype för företag och Exchange.
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927294"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Ta bort eller inaktivera hybrid modern autentisering från Skype för företag och Exchange

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Om du har aktiverat HMA (Hybrid Modern Authentication) för att hitta den olämplig i din aktuella miljö kan du inaktivera HMA. I den här artikeln förklaras hur.
  
## <a name="who-is-this-article-for"></a>Vem är den här artikeln till för?

Om du har aktiverat Modern autentisering i Skype för företag Online eller Lokalt och/eller Exchange Online eller Lokalt och upptäckt att du måste inaktivera HMA, är de här stegen för dig.

> [!IMPORTANT]
> Se artikeln[" Skype för företag topologier](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)som stöds med modern autentisering " om du är i Skype för företag Online eller lokalt, har en HMA med blandad topologi och behöver titta på topologier som stöds innan du börjar.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Inaktivera modern hybridautentisering (Exchange)

1. **Exchange lokalt:** Öppna Exchange Management Shell och kör följande kommandon: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online**: [Anslut att Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) med Remote PowerShell. Kör följande kommando för att sätta flaggan  *OAuth2ClientProfileEnabled*  till "false":

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Inaktivera modern hybridautentisering (Skype för företag)

1. **Skype för företag Lokalt:** Kör följande kommandon i Skype för företag Management Shell:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype för företag Online**: [Anslut att Skype för företag online med](manage-skype-for-business-online-with-microsoft-365-powershell.md) Remote PowerShell. Kör följande kommando för att inaktivera modern autentisering:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Länka tillbaka till översikten över Modern autentisering.](hybrid-modern-auth-overview.md) 
