---
title: Lägga till en domän i ett klientföretag med Windows PowerShell för DAP-partner
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: Sammanfattning Använd PowerShell för Microsoft 365 för att lägga till ett alternativt domännamn i en befintlig kundklientorganisation.
ms.openlocfilehash: b6a40f387f9fc7e513137cda4253a62be2455aad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905578"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>Lägga till en domän i ett klientföretag med Windows PowerShell för DAP-partners (Delegerad åtkomstbehörighet)

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan skapa och koppla nya domäner till kundens innehavare med PowerShell för Microsoft 365 snabbare än med hjälp av administrationscentret för Microsoft 365.
  
DAP-partner (Delegerad åtkomstbehörighet) är syndicerings- och molnlösningsleverantörer (CSP). De är ofta nätverks- eller telekommunikationsleverantörer till andra företag. De buntar ihop Microsoft 365-prenumerationer till sina tjänsteerbjudanden till sina kunder. När de säljer en Microsoft 365-prenumeration tilldelas de automatiskt behörigheten Administrera för (AOBO) för kundens företag så att de kan administrera och rapportera om kundrelationerna.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

I procedurerna i det här avsnittet måste du ansluta [till Microsoft 365 med PowerShell.](connect-to-microsoft-365-powershell.md)
  
Du behöver också autentiseringsuppgifterna för partnerklientorganisationen.
  
Du behöver också följande information:
  
- Du behöver det fullständigt kvalificerade domännamnet (FQDN) som kunden vill ha.
    
- Du behöver kundens **Klientorganisations-ID.**
    
- FQDN måste vara registrerat med en DNS-registrator (Internet Domain Name Service), till exempel GoDaddy. Mer information om hur du registrerar ett domännamn offentligt finns i [Så här köper du ett domännamn.](../admin/get-help-with-domains/buy-a-domain-name.md)
    
- Du behöver veta hur du lägger till en TXT-post i den registrerade DNS-zonen för din DNS-registrator. Mer information om hur du lägger till en TXT-post finns i Lägga [till DNS-poster för att ansluta din domän.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) Om de procedurerna inte fungerar för dig måste du hitta procedurerna för din DNS-registrator.
    
## <a name="create-domains"></a>Skapa domäner

 Kunderna kommer antagligen att be dig skapa fler domäner att associera med deras innehavare eftersom de inte vill att standarddomänen .onmicrosoft.com ska vara den primära som representerar deras företagsidentiteter i <domain> världen. I den här proceduren får du hjälp med att skapa en ny domän som är kopplad till kundens innehavare.
  
> [!NOTE]
> För att några av de här åtgärderna ska kunna utföras måste partneradministratörskontot som du loggar in med vara inställt på Fullständig **administration** för inställningen Tilldela administrativ åtkomst till företag som du stöder i informationen för administratörskontot i administrationscentret för Microsoft 365.  Mer information om hur du hanterar partneradministratörsroller finns i [Partner: Erbjuda delegerad administration](https://go.microsoft.com/fwlink/p/?LinkId=532435). 
  
### <a name="create-the-domain-in-azure-active-directory"></a>Skapa domänen i Azure Active Directory

Med det här kommandot skapas domänen i Azure Active Directory, men den associeras inte med den offentligt registrerade domänen. När du bevisar att du äger den offentligt registrerade domänen för Microsoft Microsoft 365 för företag.
  
```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet. Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.
>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>Hämta data för verifieringsposten för DNS TXT

 Microsoft 365 genererar de specifika data som du behöver placera i DNS TXT-verifieringsposten. Kör det här kommandot för att hämta data.
  
```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

Det ger dig följande utdata:
  
 `Label: domainname.com`
  
 `Text: MS=ms########`
  
 `Ttl: 3600`
  
> [!NOTE]
> Du behöver den här texten för att skapa TXT-posten i den offentligt registrerade DNS-zonen. Se till att kopiera och spara den. 
  
### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a>Lägga till en TXT-post i den offentligt registrerade DNS-zonen

Innan Microsoft 365 börjar ta emot trafik som dirigeras till det offentligt registrerade domännamnet måste du bevisa att du äger och har administratörsbehörighet till domänen. Du bevisa att du äger domänen genom att skapa en TXT-post i domänen. En TXT-post gör inget i din domän och den kan tas bort när du har upprättat ägarskap för domänen. Om du vill skapa TXT-posterna följer du procedurerna [för att lägga till DNS-poster för att ansluta din domän.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) Om de procedurerna inte fungerar för dig måste du hitta procedurerna för din DNS-registrator.
  
Bekräfta att TXT-posten har skapats via nslookup. Följ denna syntax.
  
```console
nslookup -type=TXT <FQDN of registered domain>
```

Det ger dig följande utdata:
  
 `Non-authoritative answer:`
  
 `FQDN of the registered domain`
  
 `text=MS=ms########`
  
### <a name="validate-domain-ownership-in-microsoft-365"></a>Verifiera domänägarskap i Microsoft 365

I det sista steget verifierar du för Microsoft 365 att du äger den offentligt registrerade domänen. Efter det här steget börjar Microsoft 365 att acceptera trafik som dirigeras till det nya domännamnet. Kör det här kommandot för att slutföra processen för att skapa och registrera en domän. 
  
```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Det här kommandot returnerar inte några utdata, så kör det här kommandot för att bekräfta att det fungerade.
  
```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Detta returnerar något i den här

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

   
## <a name="see-also"></a>Se även

#### 

[Hjälp för partners](https://go.microsoft.com/fwlink/p/?LinkID=533477)