---
title: Lägga till en domän till en klient innehav med Windows PowerShell för DAP partners
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
description: 'Sammanfattning: Använd PowerShell för Microsoft 365 för att lägga till ett alternativt domän namn i en befintlig kund klient organisation.'
ms.openlocfilehash: 23137d2e2461e75a22d0403f9b8246a29e48019f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694897"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>Lägga till en domän i en klient innehav med Windows PowerShell för DAP-partners (delegerade åtkomst behörigheter)

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan skapa och koppla nya domäner till kundens innehav med PowerShell för Microsoft 365 snabbare än att använda administrations centret för Microsoft 365.
  
DAP-partners (delegerade åtkomst behörigheter) för syndikering och moln lösnings leverantörer. De är ofta nätverks-eller Telekom-leverantörer i andra företag. De fördelar Microsoft 365-abonnemang till sina kunder. När de säljer en Microsoft 365-prenumeration beviljas de automatiskt administration på uppdrag av (AOBO) behörigheter till kundens innehav så att de kan administrera och rapportera om kundens innehavare.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

Procedurerna i det här avsnittet kräver att du ansluter till [Microsoft 365 med PowerShell](connect-to-microsoft-365-powershell.md).
  
Du behöver också dina autentiseringsuppgifter för partner klient organisation.
  
Du behöver också följande information:
  
- Du behöver det fullständigt kvalificerade domän namnet (FQDN) som din kund önskar.
    
- Du behöver kundens **TenantId**.
    
- FQDN måste vara registrerat hos en DNS-registrator för Internet, till exempel GoDaddy. Mer information om hur du registrerar ett domän namn offentligt finns i [så här köper du ett domän namn](https://go.microsoft.com/fwlink/p/?LinkId=532541).
    
- Du måste veta hur du lägger till en TXT-post i den registrerade DNS-zonen för din DNS-registrator. Mer information om hur du lägger till en TXT-post finns i [lägga till DNS-poster för att ansluta din domän](https://go.microsoft.com/fwlink/p/?LinkId=532542). Om dessa procedurer inte fungerar för dig måste du hitta procedurerna för din DNS-registrator.
    
## <a name="create-domains"></a>Skapa domäner

 Kunderna uppmanas antagligen att skapa ytterligare domäner för att kopplas till deras innehavande, eftersom de inte vill använda standard <domain> domänen. onmicrosoft.com domain som representerar deras företags identitet för världen. Med den här proceduren får du hjälp med att skapa en ny domän som är kopplad till kundens innehav.
  
> [!NOTE]
> För att utföra vissa av dessa åtgärder måste partner administratörs kontot som du loggar in med vara inställt på **fullständig administration** för gruppen **tilldela administrativ åtkomst till företag som du** har 365 stöd för. Mer information om hur du hanterar roller för partner administratörer finns i [partners: tillhandahålla delegerad administration](https://go.microsoft.com/fwlink/p/?LinkId=532435). 
  
### <a name="create-the-domain-in-azure-active-directory"></a>Skapa domänen i Azure Active Directory

Det här kommandot skapar domänen i Azure Active Directory men associerar den inte med den offentligt registrerade domänen. Det kommer när du bevisa att du äger den offentligt registrerade domänen till Microsoft Microsoft 365 för företag.
  
```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** . För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.
>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>Hämta data för DNS TXT-verifierings posten

 Microsoft 365 kommer att skapa specifika data som du måste placera i DNS TXT-verifieringen. Kör det här kommandot för att hämta data.
  
```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

Då får du utdata som:
  
 `Label: domainname.com`
  
 `Text: MS=ms########`
  
 `Ttl: 3600`
  
> [!NOTE]
> Du behöver den här texten för att skapa TXT-posten i den offentligt registrerade DNS-zonen. Glöm inte att kopiera och spara den. 
  
### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a>Lägga till en TXT-post i den offentligt registrerade DNS-zonen

Innan Microsoft 365 kommer att börja acceptera trafik som dirigeras till det offentligt registrerade domän namnet måste du bevisa att du äger och har administratörs behörighet för domänen. Du bekräftar att du äger domänen genom att skapa en TXT-post i domänen. En TXT-post gör ingenting i din domän och kan tas bort när din domän är uppkopplad. Skapa TXT-posterna genom att följa anvisningarna i [lägga till DNS-poster för att ansluta din domän](https://go.microsoft.com/fwlink/p/?LinkId=532542). Om dessa procedurer inte fungerar för dig måste du hitta procedurerna för din DNS-registrator.
  
Bekräfta att TXT-posten har skapats via nslookup. Följ den här syntaxen.
  
```console
nslookup -type=TXT <FQDN of registered domain>
```

Då får du utdata som:
  
 `Non-authoritative answer:`
  
 `FQDN of the registered domain`
  
 `text=MS=ms########`
  
### <a name="validate-domain-ownership-in-microsoft-365"></a>Verifiera domän ägarskap i Microsoft 365

I det här förra steget validerar du till Microsoft 365 som du äger den offentligt registrerade domänen. Efter det här steget börjar Microsoft 365 att acceptera trafik som dirigeras till det nya domän namnet. Kör det här kommandot för att slutföra skapandet av domäner och registrering. 
  
```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Det här kommandot returnerar ingen utskrift, så du kan kontrol lera att det fungerade genom att köra det här kommandot.
  
```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Det här kommer att returnera ungefär så här

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

   
## <a name="see-also"></a>Se även

#### 

[Hjälp för partners](https://go.microsoft.com/fwlink/p/?LinkID=533477)

