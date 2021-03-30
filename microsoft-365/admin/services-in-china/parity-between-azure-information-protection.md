---
title: Stöd för Azure Information Protection för Office 365 som drivs av 21Vianet
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
ms.openlocfilehash: bddba69ecc8b7b80d2b2c7c48d820ec22d293362
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418038"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Stöd för Azure Information Protection för Office 365 som drivs av 21Vianet

Den här artikeln beskriver skillnaderna mellan Azure Information Protection-stöd (AIP) för Office 365 som drivs av 21Vianet och kommersiella erbjudanden, samt specifika instruktioner för att konfigurera AIP för kunder i Kina, inklusive hur du installerar den lokala AIP-skannern och hanterar jobb för &mdash; innehållssökning.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Skillnader mellan AIP för Office 365 som drivs av 21Vianet och kommersiella erbjudanden

Även om vårt mål är att tillhandahålla alla kommersiella funktioner till kunder i Kina med erbjudandet AIP för Office 365 som drivs av 21Vianet finns det några funktioner som vi vill lyfta fram.

Följande lista innehåller de befintliga luckorna mellan AIP för Office 365 som drivs av 21Vianet och våra kommersiella erbjudanden från och med januari 2021:

- IRM (Information Rights Management) stöds endast för Microsoft 365-program för företag (version 11731.10000 eller senare). Office 2010, Office 2013 och andra Office 2016-versioner stöds inte.

- Migrering från AD RMS (Active Directory Rights Management Services) till AIP är för närvarande inte tillgänglig.
  
- Delning av skyddade e-postmeddelanden med användare i det kommersiella molnet stöds.
  
- Det går för närvarande inte att dela dokument och e-postbilagor med användare i det kommersiella molnet. Detta omfattar Office 365 som drivs av 21Vianet-användare i det kommersiella molnet, icke-Office 365 som drivs av 21Vianet-användare i det kommersiella molnet och användare med en RMS för individer-licens.
  
- IRM med SharePoint (IRM-skyddade webbplatser och bibliotek) är för närvarande inte tillgängligt.
  
- Tillägget för mobila enheter för AD RMS är inte tillgängligt för närvarande.

- [Mobile Viewer stöds](/azure/information-protection/rms-client/mobile-app-faq) inte av Azure China 21Vianet.

- Området AIP i Azure Portal är inte tillgängligt för kunder i Kina. Använd [PowerShell-kommandon](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) i stället för att utföra åtgärder i portalen, till exempel installera den lokala skannern och hantera genomsökningsjobben.

## <a name="configure-aip-for-customers-in-china"></a>Konfigurera AIP för kunder i Kina

Så här konfigurerar du AIP för kunder i Kina:
1. [Aktivera rättighetshantering för klientorganisationen.](#step-1-enable-rights-management-for-the-tenant)

2. [Konfigurera DNS-kryptering](#step-2-configure-dns-encryption).

3. [Installera och konfigurera AIP unified labeling-klienten.](#step-3-install-and-configure-the-aip-unified-labeling-client)

4. [Konfigurera AIP-appar i Windows.](#step-4-configure-aip-apps-on-windows)

5. [Installera den lokala AIP-skannern och hantera sökjobb för innehåll.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Steg 1: Aktivera rättighetshantering för klientorganisationen

För att krypteringen ska fungera måste RMS vara aktiverat för klientorganisationen.

1. Kontrollera om RMS är aktiverat:

    1. Starta PowerShell som administratör.
    2. Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .
    3. Importera modulen med `Import-Module AipService` .
    4. Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .
    5. Kör `(Get-AipServiceConfiguration).FunctionalState` och kontrollera om statusen är `Enabled` .

2. Om funktionstillståndet är `Disabled` kör du `Enable-AipService` .

### <a name="step-2-configure-dns-encryption"></a>Steg 2: Konfigurera DNS-kryptering

För att krypteringen ska fungera korrekt måste Office-klientprogrammen ansluta till Kina-instansen av tjänsten och bootstrap därifrån. Om klientprogrammen ska omdirigeras till rätt tjänstinstans måste innehavaradministratören konfigurera en DNS SRV-post med information om Azure RMS-URL: en. Utan DNS SRV-posten försöker klientprogrammet ansluta till den offentliga molninstansen som standard och kommer att misslyckas.

Antagandet är också att användare loggar in med ett användarnamn baserat på den klientorganisationsägda domänen (till exempel ), och inte `joe@contoso.cn` `onmschina` användarnamnet (till exempel `joe@contoso.onmschina.cn` ). Domännamnet från användarnamnet används för DNS-omdirigering till rätt tjänstinstans.

#### <a name="configure-dns-encryption---windows"></a>Konfigurera DNS-kryptering – Windows

1. Skaffa RMS-ID:

    1. Starta PowerShell som administratör.
    2. Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .
    3. Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .
    4. Kör `(Get-AipServiceConfiguration).RightsManagementServiceId` för att få RMS-ID: t.

2. Logga in på din DNS-leverantör, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.

    - Service = `_rmsredir`
    - Protocol = `_http`
    - Name = `_tcp`
    - Mål = `[GUID].rms.aadrm.cn` (där GUID är RMS-ID)
    - Prioritet, Vikt, Sekunder, TTL = standardvärden

3. Associera den anpassade domänen med klientorganisationen i [Azure Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). Då lägger du till en post i DNS, vilket kan ta flera minuter att verifieras när du har lagt till värdet i DNS-inställningarna.

4. Logga in på administrationscentret för Microsoft 365 med motsvarande autentiseringsuppgifter som global administratör och lägg till domänen (till exempel `contoso.cn` ) för att skapa användare. I verifieringsprocessen kan du behöva göra ytterligare DNS-ändringar. När verifieringen är klar kan användarna skapas.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Konfigurera DNS-kryptering – Mac, iOS, Android

Logga in på din DNS-leverantör, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.

- Service = `_rmsdisco`
- Protocol = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- Port = `80`
- Prioritet, Vikt, Sekunder, TTL = standardvärden

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>Steg 3: Installera och konfigurera den enhetliga AIP-etikettklienten

Ladda ned AIP Unified Labeling Client från [Microsoft Download Center.](https://www.microsoft.com/download/details.aspx?id=53018)

Mer information finns i:

- [AIP-dokumentation](/azure/information-protection/)
- [AIP-versionshistorik och supportpolicy](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Systemkrav för AIP](/azure/information-protection/requirements)
- [Snabbstart för AIP: Distribuera AIP-klienten](/azure/information-protection/quickstart-deploy-client)
- [AIP-administratörsguide](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP-användarhandbok](/azure/information-protection/rms-client/clientv2-user-guide)
- [Läs mer om känslighetsetiketter i Microsoft 365](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a>Steg 4: Konfigurera AIP-appar i Windows

AIP-appar i Windows behöver följande registernyckel för att de ska kunna peka på rätt suveränt moln för Azure Kina:

- Registernod = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- Värde = `6` (standard = 0)
- Skriv = `REG_DWORD`

> [!IMPORTANT]
> Se till att du inte tar bort registernyckeln efter en avinstallation. Om nyckeln är tom, felaktig eller inte finns fungerar funktionen som standardvärdet (standardvärdet = 0 för det kommersiella molnet). Om nyckeln är tom eller felaktig läggs även ett utskriftsfel till i loggen.

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Steg 5: Installera den lokala AIP-skannern och hantera jobb för innehållssökning

Installera den lokala AIP-skannern för att söka igenom nätverks- och innehållsresurser efter känsliga data och tillämpa klassificerings- och skyddsetiketter enligt organisationens policy.

- När du skapar och konfigurerar Azure AD-program för kommandot [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) visas i fönstret Begär **API-behörigheter** de **API:er** som min organisation använder flik i stället för fliken Microsoft-API:er.  Välj de **API:er som min organisation använder** för att sedan välja Azure Rights Management **Services.**

- När du installerar skannern och hanterar dina innehållssökningsjobb ska du använda följande cmdlets i stället för Azure Portal-gränssnittet som används av kommersiella erbjudanden:<br><br>

    | Cmdlet | Beskrivning |
    |--|--|
    | [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Lägger till en ny lagringsplats i genomsökningsjobbet för innehåll. |
    | [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Hämtar information om ditt innehållssökningsjobb. |
    | [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Hämtar information om lagringsplatsen som definierats för ditt genomsökningsjobb. |
    | [Remove-AIPScannerContentScan Job](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Tar bort ditt genomsökningsjobb. |
    | [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Tar bort en lagringsplats från innehållssökningsjobbet. |
    | [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Definierar inställningar för innehållssökningsjobbet. |
    | [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Definierar inställningar för en befintlig lagringsplats i genomsökningsjobbet för innehåll. |
    | | |

> [!TIP]
> När [du installerar skannern](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner)använder du samma klusternamn i kommandot [Install-AIP Scannerner](/powershell/module/azureinformationprotection/install-aipscanner) för att koppla flera skannernoder till samma kluster. Med samma kluster för flera skannernoder kan flera skannrar arbeta tillsammans för att utföra genomsökningarna.
> 
> Använd [cmdleten Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) för att returnera information om ditt kluster.
> 
Mer information finns i Vad [är en enhetlig skanner](/azure/information-protection/deploy-aip-scanner) för Azure Information Protection? och Hantera genomsökningsjobb med bara [PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)