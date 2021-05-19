---
title: Azure Information Protection-stöd för Office 365 som drivs av 21Vianet
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
description: Läs mer om AIP (Azure Information Protection) för Office 365 som drivs av 21Vianet och hur du konfigurerar det för kunder i Kina.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535848"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Azure Information Protection-stöd för Office 365 som drivs av 21Vianet

Den här artikeln beskriver skillnaderna mellan Azure Information Protection-stöd (AIP) för Office 365 som drivs av 21Vianet och kommersiella erbjudanden, samt specifika instruktioner för att konfigurera AIP för kunder i Kina, inklusive hur du installerar den lokala AIP-skannern och hanterar jobb för &mdash; innehållssökning.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Skillnader mellan AIP för Office 365 som drivs av 21Vianet och kommersiella erbjudanden

Även om vårt mål är att tillhandahålla alla kommersiella funktioner till kunder i Kina med vårt AIP för Office 365 som drivs av 21Vianet-erbjudandet finns det några funktioner som saknas och som vi vill lyfta fram.

Följande lista innehåller de befintliga luckorna mellan AIP för Office 365 som drivs av 21Vianet och våra kommersiella erbjudanden från och med januari 2021:

- IRM (Information Rights Management) stöds endast för Microsoft 365-appar för företag (version 11731.10000 eller senare). Office 2010, Office 2013 och andra Office 2016-versioner stöds inte.

- Migrering från Active Directory Rights Management Services (AD RMS) till AIP är inte tillgänglig för närvarande.
  
- Delning av skyddade e-postmeddelanden med användare i det kommersiella molnet stöds.
  
- Det går för närvarande inte att dela dokument och e-postbilagor med användare i det kommersiella molnet. Detta omfattar Office 365 som drivs av 21Vianet-användare i det kommersiella molnet, icke-Office 365 som drivs av 21Vianet-användare i det kommersiella molnet och användare med en RMS för individer-licens.
  
- IRM med SharePoint (IRM-skyddade webbplatser och bibliotek) är för närvarande inte tillgängligt.
  
- Tillägget för mobila enheter för AD RMS är inte tillgängligt för närvarande.

- [Mobile Viewer stöds](/azure/information-protection/rms-client/mobile-app-faq) inte av Azure China 21Vianet.

- Området AIP i Azure Portal är inte tillgängligt för kunder i Kina. Använd [PowerShell-kommandon](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) i stället för att utföra åtgärder i portalen, till exempel hantera och köra genomsökningsjobben för innehåll.

## <a name="configure-aip-for-customers-in-china"></a>Konfigurera AIP för kunder i Kina

Så här konfigurerar du AIP för kunder i Kina:
1. [Aktivera rättighetshantering för klientorganisationen.](#step-1-enable-rights-management-for-the-tenant)

1. [Lägg till Microsoft Information Protection Sync Service-tjänstens huvudnamn.](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)

1. [Konfigurera DNS-kryptering](#step-3-configure-dns-encryption).

1. [Installera och konfigurera AIP unified labeling-klienten.](#step-4-install-and-configure-the-aip-unified-labeling-client)

1. [Konfigurera AIP-appar på Windows](#step-5-configure-aip-apps-on-windows).

1. [Installera den lokala AIP-skannern och hantera sökjobb för innehåll.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Steg 1: Aktivera rättighetshantering för klientorganisationen

För att krypteringen ska fungera måste RMS vara aktiverat för klientorganisationen.

1. Kontrollera om RMS är aktiverat:

    1. Starta PowerShell som administratör.
    2. Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .
    3. Importera modulen med `Import-Module AipService` .
    4. Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .
    5. Kör `(Get-AipServiceConfiguration).FunctionalState` och kontrollera om statusen är `Enabled` .

2. Om funktionstillståndet är `Disabled` kör du `Enable-AipService` .

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a>Steg 2: Lägg till microsofts huvudnamn för synkroniseringstjänsten för informationsskydd

Microsoft **Information Protection-synkroniseringstjänstens** huvudnamn är inte tillgängligt i Azure China-klientorganisationen som standard och krävs för Azure Information Protection.

1. Skapa den här tjänstens huvudnamn manuellt med cmdleten [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) och program-ID:t `870c4f2e-85b6-4d43-bdda-6ed9a579b725` för Synkroniseringstjänsten för Microsoft Information Protection. 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. När du har lagt till tjänstens huvudnamn lägger du till de relevanta behörigheter som krävs för tjänsten.

### <a name="step-3-configure-dns-encryption"></a>Steg 3: Konfigurera DNS-kryptering

För att krypteringen ska fungera Office måste klientprogrammen ansluta till Kina-instansen av tjänsten och bootstrap därifrån. Om klientprogrammen ska omdirigeras till rätt tjänstinstans måste innehavaradministratören konfigurera en DNS SRV-post med information om Azure RMS-URL: en. Utan DNS SRV-posten försöker klientprogrammet ansluta till den offentliga molninstansen som standard och kommer att misslyckas.

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

4. Logga in på Microsoft 365-administrationscentret med motsvarande autentiseringsuppgifter som global administratör och lägg till domänen (till exempel `contoso.cn` ) för att skapa användare. I verifieringsprocessen kan du behöva göra ytterligare DNS-ändringar. När verifieringen är klar kan användarna skapas.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Konfigurera DNS-kryptering – Mac, iOS, Android

Logga in på din DNS-leverantör, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.

- Service = `_rmsdisco`
- Protocol = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- Port = `80`
- Prioritet, Vikt, Sekunder, TTL = standardvärden


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a>Steg 4: Installera och konfigurera den enhetliga AIP-etikettklienten

Ladda ned och installera AIP Unified Labeling-klienten från [Microsoft Download Center.](https://www.microsoft.com/download/details.aspx?id=53018)

Mer information finns i:

- [AIP-dokumentation](/azure/information-protection/)
- [AIP-versionshistorik och supportpolicy](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Systemkrav för AIP](/azure/information-protection/requirements)
- [Snabbstart för AIP: Distribuera AIP-klienten](/azure/information-protection/quickstart-deploy-client)
- [AIP-administratörsguide](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP-användarhandbok](/azure/information-protection/rms-client/clientv2-user-guide)
- [Läs mer Microsoft 365 känslighetsetiketter](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a>Steg 5: Konfigurera AIP-appar på Windows

AIP-appar Windows behöver följande registernyckel för att de ska kunna peka på rätt suveränt moln för Azure Kina:

- Registernod = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- Värde = `6` (standard = 0)
- Skriv = `REG_DWORD`

> [!IMPORTANT]
> Se till att du inte tar bort registernyckeln efter en avinstallation. Om nyckeln är tom, felaktig eller inte finns fungerar funktionen som standardvärdet (standardvärdet = 0 för det kommersiella molnet). Om nyckeln är tom eller felaktig läggs även ett utskriftsfel till i loggen.

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Steg 6: Installera den lokala AIP-skannern och hantera genomsökningsjobb

Installera den lokala AIP-skannern för att söka igenom nätverks- och innehållsresurser efter känsliga data och tillämpa klassificerings- och skyddsetiketter enligt organisationens policy.

När du konfigurerar och hanterar innehållssökningsjobben ska du använda följande procedur i stället för [det Azure Portal-gränssnitt](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) som används av de kommersiella erbjudandena.

Mer information finns i Vad [är en enhetlig skanner](/azure/information-protection/deploy-aip-scanner) för Azure Information Protection? och Hantera genomsökningsjobb med bara [PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)

**Installera och konfigurera skannern:**

1. Logga in på Windows Server-datorn som kör skannern. Använd ett konto med lokala administratörsrättigheter och som har behörighet att skriva till SQL Server huvuddatabasen.

1. Börja med att stänga PowerShell. Om du tidigare har installerat AIP-klienten och skannern ska du kontrollera att **AIP Scannerner-tjänsten** stoppas.

1. Öppna Windows PowerShell en session med **alternativet Kör som** administratör.

1. Kör cmdleten [Install-AIP Scannerner,](/powershell/module/azureinformationprotection/Install-AIPScanner) ange din SQL Server-instans där du ska skapa en databas för Azure Information Protection-skannern och ett beskrivande namn på skannerkluster.

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > Du kan använda samma klusternamn i kommandot [Install-AIP Scannerner för](/powershell/module/azureinformationprotection/install-aipscanner) att koppla flera skannernoder till samma kluster. Med samma kluster för flera skannernoder kan flera skannrar arbeta tillsammans för att utföra genomsökningarna.
    > 

1. Kontrollera att tjänsten nu är installerad med hjälp av  >  **Administrationsverktygstjänster.**

    Den installerade tjänsten heter **Azure Information Protection Scanner och** är konfigurerad att köras med hjälp av det skannertjänstkonto som du har skapat.

1. Hämta en Azure-token som ska användas med skannern. Med en Azure AD-token kan skannern autentiseras i Azure Information Protection-tjänsten, vilket gör att skannern kan köras icke-interaktivt. 

    1. Öppna Azure-portalen och skapa ett Azure AD-program för att ange en åtkomsttoken för autentisering. Mer information finns i Så [här märks filer icke-interaktivt för Azure Information Protection.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)
    
        > [!TIP]
        > När du skapar och konfigurerar Azure AD-program för kommandot [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) visas i fönstret Begär **API-behörigheter** de **API:er** som min organisation använder flik i stället för fliken Microsoft-API:er.  Välj de **API:er som min organisation använder** för att sedan välja Azure Rights Management **Services.** 
        >

    1. Från Windows-serverdatorn loggar du in med det här  kontot och startar en PowerShell-session om ditt skannertjänstkonto har beviljats logga in lokalt direkt för installationen. 
    
        Om ditt skannertjänstkonto  inte kan beviljas logga in lokalt direkt för installationen använder du parametern *OnBehalfOf* med [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)enligt beskrivningen i Så här etiketterar du filer icke-interaktivt för [Azure Information Protection.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)

    1. Kör [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), ange värden som kopieras från Ditt Azure AD-program:

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      Till exempel:

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    Skannern har nu en token som autentiseras i Azure AD. Denna token är giltig i ett år, två år eller aldrig, enligt konfigurationen av webbappen **/API-klienthemligheten** i Azure AD. När token går ut måste du upprepa proceduren.

1. Kör [cmdleten Set-AIP ScannernerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) för att ställa in skannern så att den fungerar i offlineläge. Kör:

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. Kör [cmdleten Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) för att skapa ett standardjobb för innehållssökning.

    Den enda obligatoriska parametern i **cmdleten Set-AIPScannerContentJob är** **Enforce**. Men du kanske vill definiera andra inställningar för genomsökningsjobbet för innehåll just nu. Till exempel:

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    Syntaxen ovan konfigurerar följande inställningar när du fortsätter konfigurationen:

    - Gör så att schemaläggningen av skannern körs *manuellt*
    - Anger vilka informationstyper som ska identifieras utifrån känslighetsetiketts princip
    - Tillämpar *inte* en princip för känslighetsetiketter
    - Automatiskt etiketterar filer baserat på innehåll med hjälp av standardetiketten som definierats för känslighetsetikettsprincipen
    - Tillåter  inte att filer relabels
    - Bevarar filinformation vid genomsökning och automatisk etikettering, inklusive *senast ändrad,* *senast ändrad* och *ändrad av* värden
    - Ställer in skannern till att utesluta .msg- och .tmp-filer när den körs
    - Anger standardägaren till det konto som du vill använda när skannern körs

1. Använd cmdleten [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) till att definiera de lagringsgränser du vill söka igenom i genomsökningsjobbet för innehåll. Kör till exempel:

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    Använd någon av följande syntaxer, beroende på vilken typ av lagringsplats du lägger till:

    - För en nätverksresurs använder du `\\Server\Folder` .
    - För ett SharePoint använder du `http://sharepoint.contoso.com/Shared%20Documents/Folder` .
    - För en lokal sökväg: `C:\Folder`
    - För en UNC-sökväg: `\\Server\Folder`

    > [!NOTE]
    > Jokertecken stöds inte och WebDav-platser stöds inte.
    >
    > Om du vill ändra lagringsplatsen senare använder du cmdleten [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) i stället. 


Fortsätt med följande steg efter behov:

- [Köra en identifieringscykel och visa rapporter för skannern](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [Använda PowerShell för att konfigurera skannern att tillämpa klassificering och skydd](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [Använda PowerShell för att konfigurera en DLP-princip med skannern](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

I följande tabell visas PowerShell-cmdlets som är relevanta för installation av skannern och hantering av innehållssökningsjobb:

| Cmdlet | Beskrivning |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Lägger till en ny lagringsplats i genomsökningsjobbet för innehåll. |
| [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|Returnerar information om klustret. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Hämtar information om ditt innehållssökningsjobb. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Hämtar information om lagringsplatsen som definierats för ditt genomsökningsjobb. |
| [Remove-AIPScannerContentScan Job](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Tar bort ditt genomsökningsjobb. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Tar bort en lagringsplats från innehållssökningsjobbet. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Definierar inställningar för innehållssökningsjobbet. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Definierar inställningar för en befintlig lagringsplats i genomsökningsjobbet för innehåll. |
| | |

Mer information finns i:

- [Vad är en enhetlig azure Information Protection-skanner?](/azure/information-protection/deploy-aip-scanner)
- [Konfigurera och installera en enhetlig AIP-skanner (Azure Information Protection)](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- [Hantera genomsökningsjobb med bara PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)
