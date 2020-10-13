---
title: Paritet mellan Azure information Protection för Office 365 som drivs av 21Vianet och kommersiella offerter
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Läs mer om Azure information Protection för Office 365 som drivs av 21Vianet och hur du konfigurerar den för kunder i Kina.
monikerRange: o365-21vianet
ms.openlocfilehash: ca30811e77f686b92b8cdd13d624182eb0d3039e
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445585"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Paritet mellan Azure information Protection för Office 365 som drivs av 21Vianet och kommersiella offerter

När vårt mål är att leverera alla kommersiella funktioner och funktioner till kunder i Kina med vårt Azure information Protection för Office 365 som drivs av 21Vianet-bud, finns det en del funktioner som vi vill framhäva.

Följande lista innehåller befintliga luckor mellan Azure information Protection for Office 365 som drivs av 21Vianet och våra kommersiella bud från och med den 2019 juli:

- IRM (Information Rights Management) stöds endast för Microsoft 365-program för företag (version 11731,10000 eller senare). Office 2010, Office 2013 och andra Office 2016-versioner stöds inte.

- Migrering från AD RMS (Active Directory Rights Management Services) till Azure information Protection är för närvarande inte tillgänglig.
  
- Det går att dela skyddade e-postmeddelanden till användare i det kommersiella molnet.
  
- Det går för närvarande inte att dela dokument och e-postbilagor till användare i det kommersiella molnet. Detta inkluderar Office 365 som drivs av 21Vianet-användare i det kommersiella molnet, icke-Office 365 som drivs av 21Vianet-användare i det kommersiella molnet och användare med en licens för en person.
  
- IRM med SharePoint (IRM-skyddade webbplatser och bibliotek) är för närvarande inte tillgängligt.
  
- Rights Management Connector är för närvarande inte tillgängligt.
  
- Mobil enhets tillägget för AD RMS är för närvarande inte tillgängligt.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>Konfigurera Azure information Protection för kunder i Kina

### <a name="enable-rights-management-for-the-tenant"></a>Aktivera rättighets hantering för klient organisationen

För att krypteringen ska fungera korrekt måste RMS vara aktiverat för innehavaren.

- Kontrol lera om RMS är aktiverat:
  1. Starta PowerShell som administratör.
  2. Om AIPService-modulen inte är installerad kör du  `Install-Module AipService` .
  3. Importera modulen med `Import-Module AipService` .
  4. Anslut till tjänsten med  `Connect-AipService -environmentname azurechinacloud` .
  5. Kör  `(Get-AipServiceConfiguration).FunctionalState`   och kontrol lera om tillståndet är  `Enabled` .

- Kör om det funktionella läget är  `Disabled`  `Enable-AipService` .

### <a name="dns-configuration-for-encryption-windows"></a>DNS-konfiguration för kryptering (Windows)

För att krypteringen ska fungera korrekt måste Office-klientprogrammet ansluta till Kina-instansen av tjänsten och starta därifrån. För att omdirigera klient program till den högra tjänst instansen måste klient organisationens administratör konfigurera en DNS SRV-post med information om URL-adressen för Azure RMS. Utan DNS SRV-posten försöker klient programmet ansluta till den offentliga moln instansen som standard och kommer inte att fungera.

Dessutom är antagandet att användare loggar in med ett användar namn som baseras på den klient organisationens domän (till exempel `joe@contoso.cn` ) och inte `onmschina` användar namnet (till exempel `joe@contoso.onmschina.cn` ). Domän namnet från username används för DNS-omdirigering till rätt tjänst instans.

- Hämta RMS-ID:
  1. Starta PowerShell som administratör.
  2. Om AIPService-modulen inte är installerad kör du  `Install-Module AipService` .
  3. Anslut till tjänsten med  `Connect-AipService -environmentname azurechinacloud` .
  4. Kör  `(Get-AipServiceConfiguration).RightsManagementServiceId`   för att hämta RMS-ID.

- Logga in på din DNS-leverantör, gå till DNS-inställningarna för domänen och Lägg sedan till en ny SRV-post.
  - Tjänst = `_rmsredir`
  - Protokoll = `_http`
  - Namn = `_tcp`
  - Target =  `[GUID].rms.aadrm.cn`   (där GUID är ett RMS-ID)
  - Prioritet, vikt, sekunder, TTL = standardvärden

- Koppla den anpassade domänen till klient organisationen i [Azure-portalen](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). Detta lägger till en post i DNS som kan ta flera minuter att verifiera när du har lagt till värdet i DNS-inställningarna.

- Logga in i administrations centret för Microsoft 365 med motsvarande globala administratörs behörighet och Lägg till domänen (till exempel `contoso.cn` ) för att skapa användare. I verifierings processen kanske ytterligare DNS-ändringar krävs. När verifieringen är klar kan du skapa användare.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>DNS-konfiguration för kryptering (Mac, iOS, Android)

- Logga in på din DNS-leverantör, gå till DNS-inställningarna för domänen och Lägg sedan till en ny SRV-post.
  - Tjänst = `_rmsdisco`
  - Protokoll = `_http`
  - Namn = `_tcp`
  - Target = `api.aadrm.cn`
  - Port = `80`
  - Prioritet, vikt, sekunder, TTL = standardvärden
