---
title: Azure Information Protection-support för Office 365 som drivs av 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Läs mer om Azure Information Protection (AIP) för Office 365 som drivs av 21Vianet och hur du konfigurerar det för kunder i Kina.
monikerRange: o365-21vianet
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099684"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Azure Information Protection-support för Office 365 som drivs av 21Vianet

I den här artikeln beskrivs skillnaderna mellan stöd för Azure Information Protection (AIP) för Office 365 som drivs av 21Vianet och kommersiella erbjudanden, samt specifika instruktioner för hur du konfigurerar AIP för kunder i Kina, inklusive hur du installerar en lokal AIP-skanner och hanterar snabbsökningsjobb för &mdash; innehåll.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Skillnader mellan AIP för Office 365 som drivs av 21Vianet och kommersiella erbjudanden

Även om vårt mål är att leverera alla kommersiella funktioner till kunder i Kina med AIP för Office 365 som drivs av 21Vianet-erbjudandet finns det några funktioner som vi vill lyfta fram.

Följande lista innehåller de befintliga luckorna mellan AIP för Office 365 som drivs av 21Vianet och våra kommersiella erbjudanden från och med januari 2021:

- IRM (Information Rights Management) stöds endast för Microsoft 365-program för företag (version 11731.10000 eller senare). Office 2010, Office 2013 och andra versioner av Office 2016 stöds inte.

- Migrering från AD RMS (Active Directory Rights Management Services) till AIP är för närvarande inte tillgänglig.
  
- Delning av skyddade e-postmeddelanden med användare i det kommersiella molnet stöds.
  
- Delning av dokument och e-postbilagor med användare i det kommersiella molnet är för närvarande inte tillgängligt. Detta omfattar Office 365 som drivs av 21Vianet-användare i kommersiella molnet, icke-Office 365 som drivs av 21Vianet-användare i kommersiella molnet och användare med en RMS för individer-licens.
  
- IRM med SharePoint (IRM-skyddade webbplatser och bibliotek) är för närvarande inte tillgängligt.
  
- Tillägget för mobila enheter för AD RMS är för närvarande inte tillgängligt.

- [Mobile Viewer stöds](/azure/information-protection/rms-client/mobile-app-faq) inte av Azure China 21Vianet.

- Området AIP på Azure-portalen är inte tillgängligt för kunder i Kina. Använd [PowerShell-kommandon](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) i stället för att utföra åtgärder i portalen, till exempel installera den lokala skannern och hantera sökjobben för innehåll.

## <a name="configure-aip-for-customers-in-china"></a>Konfigurera AIP för kunder i Kina

Så här konfigurerar du AIP för kunder i Kina:
1. [Aktivera rättighetshantering för klientorganisationen.](#step-1-enable-rights-management-for-the-tenant)

2. [Konfigurera DNS-kryptering.](#step-2-configure-dns-encryption)

3. [Installera och konfigurera klient för enhetliga etiketter i AIP.](#step-3-install-and-configure-the-aip-unified-labeling-client)

4. [Konfigurera AIP-appar i Windows.](#step-4-configure-aip-apps-on-windows)

5. [Installera den lokala AIP-skannern och hantera genomsökningsjobb för innehåll.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Steg 1: Aktivera rättighetshantering för klientorganisationen

För att krypteringen ska fungera korrekt måste RMS vara aktiverat för klientorganisationen.

1. Kontrollera om RMS är aktiverat:

    1. Starta PowerShell som administratör.
    2. Om AIPService-modulen inte är installerad kör `Install-Module AipService` du.
    3. Importera modulen med `Import-Module AipService` .
    4. Anslut till tjänsten med hjälp av `Connect-AipService -environmentname azurechinacloud` .
    5. Kör `(Get-AipServiceConfiguration).FunctionalState` och kontrollera om statusen är `Enabled` .

2. Om funktionstillståndet är `Disabled` , kör `Enable-AipService` .

### <a name="step-2-configure-dns-encryption"></a>Steg 2: Konfigurera DNS-kryptering

För att krypteringen ska fungera måste Office-klientprogrammen ansluta till Kina-instansen av tjänsten och bootstrap därifrån. För att omdirigera klientprogram till rätt tjänstinstans måste innehavaradministratören konfigurera en DNS SRV-post med information om Azure RMS URL. Utan DNS SRV-posten försöker klientprogrammet ansluta till den offentliga molninstansen som standard och kommer att misslyckas.

Antagandet är också att användare loggar in med ett användarnamn baserat på den klientägda domänen (t.ex. ) och inte `joe@contoso.cn` `onmschina` användarnamnet (t.ex. `joe@contoso.onmschina.cn` ). Domännamnet från användarnamnet används för DNS-omdirigering till rätt tjänstinstans.

#### <a name="configure-dns-encryption---windows"></a>Konfigurera DNS-kryptering – Windows

1. Skaffa RMS-ID:

    1. Starta PowerShell som administratör.
    2. Om AIPService-modulen inte är installerad kör `Install-Module AipService` du.
    3. Anslut till tjänsten med hjälp av `Connect-AipService -environmentname azurechinacloud` .
    4. Kör `(Get-AipServiceConfiguration).RightsManagementServiceId` för att få RMS-ID.

2. Logga in på din DNS-leverantör, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.

    - Service = `_rmsredir`
    - Protocol = `_http`
    - Namn = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (där GUID är RMS-ID)
    - Prioritet, Vikt, Sekunder, TTL = standardvärden

3. Koppla den anpassade domänen till klientorganisationen i [Azure Portal.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Då kommer en post i DNS att läggas till, vilket kan ta flera minuter att verifieras när du har lagt till värdet i DNS-inställningarna.

4. Logga in på administrationscentret för Microsoft 365 med motsvarande autentiseringsuppgifter som global administratör och lägg till domänen (till `contoso.cn` exempel) för att skapa användare. I verifieringsprocessen kan ytterligare DNS-ändringar krävas. När verifieringen är klar kan användarna skapas.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Konfigurera DNS-kryptering – Mac, iOS, Android

Logga in på din DNS-leverantör, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.

- Service = `_rmsdisco`
- Protocol = `_http`
- Namn = `_tcp`
- Target = `api.aadrm.cn`
- Port = `80`
- Prioritet, Vikt, Sekunder, TTL = standardvärden

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>Steg 3: Installera och konfigurera den enhetliga AIP-etikettklienten

Ladda ned AIP Unified Labeling Client från [Microsoft Download Center.](https://www.microsoft.com/download/details.aspx?id=53018)

Mer information finns i:

- [AIP-dokumentation](/azure/information-protection/)
- [AIP-versionshistorik och supportpolicy](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Systemkrav för AIP](/azure/information-protection/requirements)
- [Snabbstartsguide för AIP: Distribuera AIP-klienten](/azure/information-protection/quickstart-deploy-client)
- [AIP-administratörsguide](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Användarhandbok för AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Läs mer om känslighetsetiketter i Microsoft 365](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a>Steg 4: Konfigurera AIP-appar i Windows

AIP-appar i Windows behöver följande registernyckel för att kunna peka dem till rätt självständig moln för Azure China:

- Registernod = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Namn = `CloudEnvType`
- Värde = `6` (standard = 0)
- Typ = `REG_DWORD`

> [!IMPORTANT]
> Se till att du inte tar bort registernyckeln efter en avinstallation. Om nyckeln är tom, felaktig eller inte finns fungerar funktionen som standardvärdet (standardvärdet = 0 för det kommersiella molnet). Om nyckeln är tom eller felaktig läggs även ett utskriftsfel till i loggen.

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Steg 5: Installera den lokala AIP-skannern och hantera genomsökningsjobb för innehåll

Installera den lokala AIP-skannern för att söka igenom nätverks- och innehållsresurser efter känsliga data och tillämpa klassificerings- och skyddsetiketter enligt organisationens policy.

När du installerar skannern och hanterar genomsökningsjobben för innehåll ska du använda följande cmdlets i stället för Azure Portal-gränssnittet som används av kommersiella erbjudanden:<br><br>

| Cmdlet | Beskrivning |
|--|--|
| [Add-AIPDatabasnerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Lägger till en ny lagringsplats i genomsökningsjobbet för innehåll. |
| [Get-AIPKonventionnerContent Entledig](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Hämtar information om ditt genomsökningsjobb för innehåll. |
| [Get-AIPDatabasnerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Hämtar information om lagringsplatsen som definierats för genomsökningsjobbet för innehåll. |
| [Remove-AIPKonventionnerContent Entledig](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Tar bort genomsökningsjobbet för innehåll. |
| [Remove-AIPDatabaserRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Tar bort en lagringsplats från genomsökningsjobbet för innehåll. |
| [Set-AIP Det här är Set-AIPKonventionnerContentNyckel](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Definierar inställningar för genomsökningsjobbet för innehåll. |
| [Set-AIPDatabasnerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Definierar inställningar för en befintlig lagringsplats i genomsökningsjobbet för innehåll. |

Mer information finns i Vad är en enhetlig [azure Information Protection-skanner?](/azure/information-protection/deploy-aip-scanner) och Hantera sökjobben för innehåll [med endast PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)
