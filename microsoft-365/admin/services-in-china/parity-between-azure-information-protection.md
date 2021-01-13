---
title: Paritet mellan Azure information Protection för Office 365 som drivs av 21Vianet och kommersiella offerter
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
manager: scotv
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
description: Lär dig mer om Azure information Protection (AIP) för Office 365 som drivs av 21Vianet och hur du konfigurerar den för kunder i Kina.
monikerRange: o365-21vianet
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840307"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Paritet mellan Azure information Protection för Office 365 som drivs av 21Vianet och kommersiella offerter

När vårt mål är att leverera alla kommersiella funktioner och funktioner till kunder i Kina med vårt Azure information Protection (AIP) för Office 365 som drivs av 21Vianet-bud finns det en del funktioner som vi vill framhäva.

Följande lista innehåller befintliga luckor mellan Azure information Protection for Office 365 som drivs av 21Vianet och våra kommersiella bud per den 2021 januari:

- IRM (Information Rights Management) stöds endast för Microsoft 365-program för företag (version 11731,10000 eller senare). Office 2010, Office 2013 och andra Office 2016-versioner stöds inte.

- Migrering från AD RMS (Active Directory Rights Management Services) till Azure information Protection är för närvarande inte tillgänglig.
  
- Det går att dela skyddade e-postmeddelanden till användare i det kommersiella molnet.
  
- Det går för närvarande inte att dela dokument och e-postbilagor till användare i det kommersiella molnet. Detta inkluderar Office 365 som drivs av 21Vianet-användare i det kommersiella molnet, icke-Office 365 som drivs av 21Vianet-användare i det kommersiella molnet och användare med en licens för en person.
  
- IRM med SharePoint (IRM-skyddade webbplatser och bibliotek) är för närvarande inte tillgängligt.
  
- Mobil enhets tillägget för AD RMS är för närvarande inte tillgängligt.

- [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) stöds inte av Azure Kina 21Vianet.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>Konfigurera Azure information Protection för kunder i Kina

### <a name="enable-rights-management-for-the-tenant"></a>Aktivera rättighets hantering för klient organisationen

För att krypteringen ska fungera korrekt måste RMS vara aktiverat för innehavaren.

- Kontrol lera om RMS är aktiverat:
  1. Starta PowerShell som administratör.
  2. Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .
  3. Importera modulen med `Import-Module AipService` .
  4. Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .
  5. Kör `(Get-AipServiceConfiguration).FunctionalState` och kontrol lera om tillståndet är `Enabled` .

- Kör om det funktionella läget är `Disabled` `Enable-AipService` .

### <a name="dns-configuration-for-encryption-windows"></a>DNS-konfiguration för kryptering (Windows)

För att krypteringen ska fungera korrekt måste Office-klientprogrammet ansluta till Kina-instansen av tjänsten och starta därifrån. För att omdirigera klient program till den högra tjänst instansen måste klient organisationens administratör konfigurera en DNS SRV-post med information om URL-adressen för Azure RMS. Utan DNS SRV-posten försöker klient programmet ansluta till den offentliga moln instansen som standard och kommer inte att fungera.

Dessutom är antagandet att användare loggar in med ett användar namn som baseras på den klient organisationens domän (till exempel `joe@contoso.cn` ) och inte `onmschina` användar namnet (till exempel `joe@contoso.onmschina.cn` ). Domän namnet från username används för DNS-omdirigering till rätt tjänst instans.

- Hämta RMS-ID:
  1. Starta PowerShell som administratör.
  2. Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .
  3. Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .
  4. Kör `(Get-AipServiceConfiguration).RightsManagementServiceId` för att hämta RMS-ID.

- Logga in på din DNS-leverantör, gå till DNS-inställningarna för domänen och Lägg sedan till en ny SRV-post.
  - Tjänst = `_rmsredir`
  - Protokoll = `_http`
  - Namn = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` (där GUID är ett RMS-ID)
  - Prioritet, vikt, sekunder, TTL = standardvärden

- Koppla den anpassade domänen till klient organisationen i [Azure-portalen](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). Detta lägger till en post i DNS som kan ta flera minuter att verifiera när du har lagt till värdet i DNS-inställningarna.

- Logga in i administrations centret för Microsoft 365 med motsvarande globala administratörs behörighet och Lägg till domänen (till exempel `contoso.cn` ) för att skapa användare. I verifierings processen kanske ytterligare DNS-ändringar krävs. När verifieringen är klar kan du skapa användare.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>DNS-konfiguration för kryptering (Mac, iOS, Android)

Logga in på din DNS-leverantör, gå till DNS-inställningarna för domänen och Lägg sedan till en ny SRV-post.

- Tjänst = `_rmsdisco`
- Protokoll = `_http`
- Namn = `_tcp`
- Target = `api.aadrm.cn`
- Port = `80`
- Prioritet, vikt, sekunder, TTL = standardvärden

### <a name="aip-client-configuration"></a>AIP klient konfiguration

Den enhetliga AIP-klienten kan hämtas från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).

Mer information finns i:

- [Dokumentation för Azure information Protection](/azure/information-protection/)
- [Versions historik och support policy för AIP](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [System krav för AIP](/azure/information-protection/requirements)
- [AIP snabb start: Distribuera AIP-klienten](/azure/information-protection/quickstart-deploy-client)
- [AIP administratörs guide](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP användar guide](/azure/information-protection/rms-client/clientv2-user-guide)
- [Lär dig mer om Microsoft 365-känslighets etiketter](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a>Konfiguration av AIP-appar (endast enhetlig etikett klient)

För den enhetliga etikett lösningen behöver AIP-apparna i Windows följande register nyckel för att peka dem på rätt kraft-moln för Azure Kina:

- Registry Node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Namn = `CloudEnvType`
- Värde = `6` (standardvärde = 0)
- Skriv = `REG_DWORD`

> [!IMPORTANT]
> Se till att du inte tar bort register nyckel efter en avinstallation. Om knappen är tom, felaktig eller inte finns, fungerar funktionerna som standardvärde (standardvärde = 0 för det kommersiella molnet). Om tangenten är tom eller felaktig läggs ett utskrifts fel till i loggen.

### <a name="manage-azure-information-protection-content-scan-jobs"></a>Hantera innehålls skannings jobb för Azure information Protection

Om du vill hantera dina Sök jobb för Azure information Protection-innehåll med en Azure Kina-skanner Server använder du följande cmdlet i stället för Azure-portalen:<br><br>

| Cmdlet | Beskrivning |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Lägger till en ny lagrings plats i innehålls genomsökningen. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Hämtar information om ditt innehålls genomsöknings jobb. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Hämtar information om databaserna som har definierats för innehålls genomsökningen. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Tar bort ditt innehålls genomsöknings jobb. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Tar bort en databas från ditt innehålls genomsöknings jobb. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Definierar inställningar för innehålls genomsöknings jobbet. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Definierar inställningar för en befintlig databas i innehålls genomsökningen. |

Mer information finns i [Hantera dina innehålls genomsöknings jobb endast med PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).