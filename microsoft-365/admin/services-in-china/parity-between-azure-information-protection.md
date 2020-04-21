---
title: Office 365 med 21Vianet
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
search.appverid:
- MET150
- GEU150
- GEA150
description: Läs mer om Azure Information Protection för Office 365 som drivs av 21Vianet och hur du konfigurerar det för kunder i Kina.
monikerRange: o365-21vianet
ms.openlocfilehash: 3d24b450cc9ba9a6427732d408e35af1394b4a34
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627660"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Paritet mellan Azure Information Protection for Office 365 som drivs av 21Vianet och kommersiella erbjudanden

Vårt mål är att leverera alla kommersiella funktioner och funktioner till kunder i Kina med vårt Azure Information Protection for Office 365 som drivs av 21Vianet-erbjudandet, men det finns vissa funktioner som saknas som vi vill lyfta fram.

Det här är de befintliga luckorna mellan Azure Information Protection for Office 365 som drivs av 21Vianet och våra kommersiella erbjudanden från och med juli 2019:

- IRM (Information Rights Management) stöds endast för Microsoft 365 Apps for enterprise (build 11731.10000 eller högre). Office 2010, Office 2013 och andra Office 2016-versioner stöds inte.

- Migrering från AD RMS (Active Directory Rights Management Services) till Azure Information Protection är inte tillgänglig för närvarande.
  
- Delning av skyddade e-postmeddelanden till användare i det kommersiella molnet stöds.
  
- Det är för närvarande inte tillgängligt att dela dokument och e-postbilagor till användare i det kommersiella molnet. Detta inkluderar Office 365 som drivs av 21Vianet-användare i det kommersiella molnet, icke-Office 365 som drivs av 21Vianet-användare i det kommersiella molnet och användare med en RMS for Individuals-licens.
  
- IRM med SharePoint (IRM-skyddade webbplatser och bibliotek) är inte tillgänglig för närvarande.
  
- Rights Management Connector är inte tillgänglig för närvarande.
  
- Tillägget för mobila enheter för AD RMS är inte tillgängligt för närvarande.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>Konfigurera Azure Information Protection för kunder i Kina

### <a name="enable-rights-management-for-the-tenant"></a>Aktivera rättighetshantering för klienten

För att krypteringen ska fungera korrekt måste RMS vara aktiverat för klienten.

- Kontrollera om RMS är aktiverat:
  1. Starta PowerShell som administratör.
  2. Om AIPService-modulen inte `Install-Module AipService`är installerad kör du .
  3. Importera modulen `Import-Module AipService`med .
  4. Anslut till tjänsten `Connect-AipService -environmentname azurechinacloud`med .
  5. Kör `(Get-AipServiceConfiguration).FunctionalState` och kontrollera om `Enabled`tillståndet är .

- Om funktionstillståndet `Disabled` `Enable-AipService`är kör du .

### <a name="dns-configuration-for-encryption-windows"></a>DNS-konfiguration för kryptering (Windows)

För att kryptering ska fungera korrekt måste Office-klientprogram ansluta till Kina-instansen av tjänsten och bootstrap därifrån. Om du vill omdirigera klientprogram till rätt tjänstinstans måste klientadministratören konfigurera en DNS SRV-post med information om Azure RMS-URL:en. Utan DNS SRV-posten försöker klientprogrammet som standard ansluta till den offentliga molninstansen och misslyckas.

Antagandet är också att användare ska logga in med ett användarnamn baserat `joe@contoso.cn`utanför den `onmschina` bostadsrättsägda domänen (till exempel ), och inte användarnamnet (till exempel `joe@contoso.onmschina.cn`). Domännamnet från användarnamnet används för DNS-omdirigering till rätt tjänstinstans.

- Hämta RMS-ID:
  1. Starta PowerShell som administratör.
  2. Om AIPService-modulen inte `Install-Module AipService`är installerad kör du .
  3. Anslut till tjänsten `Connect-AipService -environmentname azurechinacloud`med .
  4. Kör `(Get-AipServiceConfiguration).RightsManagementServiceId` för att hämta RMS-ID: et.

- Logga in på DNS-leverantören, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.
  - Tjänst = `_rmsredir`
  - Protokoll = `_http`
  - Namn = `_tcp`
  - Mål `[GUID].rms.aadrm.cn` = (där GUID är RMS-ID)
  - Prioritet, Vikt, Sekunder, TTL = standardvärden

- Associera den anpassade domänen med klienten i [Azure-portalen](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). Detta lägger till en post i DNS, vilket kan ta flera minuter att verifiera när du har lagt till värdet i DNS-inställningarna.

- Logga in i Microsoft 365-administrationscentret med motsvarande globala administratörsautentiseringsuppgifter och lägg till domänen (till `contoso.cn`exempel) för att skapa användare. I verifieringsprocessen kan ytterligare DNS-ändringar krävas. När verifieringen är klar kan användare skapas.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>DNS-konfiguration för kryptering (Mac, iOS, Android)

- Logga in på DNS-leverantören, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.
  - Tjänst = `_rmsdisco`
  - Protokoll = `_http`
  - Namn = `_tcp`
  - Mål = `api.aadrm.cn`
  - Port = `80`
  - Prioritet, Vikt, Sekunder, TTL = standardvärden
