---
title: Konfigurera Microsoft Defender för distribution av Slutpunkt
description: Lär dig konfigurera distributionen för Microsoft Defender för Endpoint
keywords: distribuera, konfigurera, licensieringsverifiering, klientkonfiguration, nätverkskonfiguration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b49565c45c1f38d0d2ce71b097af079782ba4de
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636200"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a>Konfigurera Microsoft Defender för distribution av Slutpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Distribution av Defender för Endpoint är en process i tre steg:

| [![distributionsfas – förbereda](images/phase-diagrams/prepare.png)](prepare-deployment.md)<br>[Fas 1: Förbereda](prepare-deployment.md) | ![distributionsfas – konfiguration](images/phase-diagrams/setup.png)<br>Fas 2: Installation | [![distributionsfas – onboard](images/phase-diagrams/onboard.png)](onboarding.md)<br>[Fas 3: Introduktion](onboarding.md) |
| ----- | ----- | ----- |
| | *Du är här!*||

Du befinner dig för närvarande i set-up-fasen.

I det här distributionsscenariot vägleds du genom stegen om:
- Licensieringsverifiering
- Klientorganisationskonfiguration
- Nätverkskonfiguration


>[!NOTE]
>För att du ska kunna vägleda dig genom en vanlig distribution omfattar det här scenariot bara användningen av Microsoft Endpoint Configuration Manager. Defender för Endpoint stöder användning av andra onboarding-verktyg men täcker inte in de scenarierna i distributionsguiden. Mer information finns i Onboard [devices to Microsoft Defender for Endpoint](onboard-configure.md).

## <a name="check-license-state"></a>Kontrollera licenstillstånd

Kontroll av licenstillståndet och om den har etablerats korrekt kan göras via administrationscentret eller via **Microsoft Azure portalen.**

1. Du visar licenserna genom att gå **Microsoft Azure-portalen** och gå till [Microsoft Azure för portallicens.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)

   ![Bild av sidan Azure-licensiering](images/atp-licensing-azure-portal.png)

1. Du kan också gå till Faktureringsprenumerationer **i**  >  **administrationscentret.**

    På skärmen visas alla etablerade licenser och deras aktuella **status.**

    ![Bild på faktureringslicenser](images/atp-billing-subscriptions.png)


## <a name="cloud-service-provider-validation"></a>Validering av molntjänstleverantör

Om du vill få åtkomst till vilka licenser som tillhandahålls till ditt företag och kontrollera licenserna går du till administrationscentret.

1. I **partnerportalen** väljer du **Administrera tjänster > Office 365**.

2. Om du klickar på partnerportallänken **öppnas alternativet Admin för** din räkning och du får tillgång till kundadministrationscentret. 

   ![Bild på O365-administrationsportalen](images/atp-O365-admin-portal-customer.png)



## <a name="tenant-configuration"></a>Klientorganisationskonfiguration
Det är enkelt att komma igång med Microsoft Defender för Slutpunkt. I navigeringsmenyn väljer du ett objekt under Slutpunkter eller någon av Microsoft 365 Defender-funktioner som Incidenter, Ärenden, Ärenden, Åtgärdscenter eller Hotanalys för att påbörja introduktionsprocessen.

Från en webbläsare går du till Microsoft 365 [Säkerhetscenter](https://security.microsoft.com).

## <a name="network-configuration"></a>Nätverkskonfiguration
Om organisationen inte kräver att slutpunkterna använder en proxyserver för att få åtkomst till Internet kan du hoppa över det här avsnittet.

Microsoft Defender för slutpunkts sensoren kräver Microsoft Windows HTTP (WinHTTP) för att rapportera sensordata och kommunicera med Microsoft Defender för slutpunktstjänsten. Den inbäddade Microsoft Defender för slutpunkts sensoren körs i systemkontexten med localSystem-kontot. Sensorn använder Microsoft Windows HTTP-tjänster (WinHTTP) för att aktivera kommunikation med Microsoft Defender för slutpunktens molntjänst. WinHTTP-konfigurationsinställningen är oberoende av proxyinställningarna för internetsurfning på Windows Internet (WinINet) på Internet och kan bara identifiera en proxyserver med hjälp av följande identifieringsmetoder:

**Metoder för automatisk upptäckt:**

-   Transparent proxy

-   Web Proxy Autodiscovery Protocol (WPAD)

Om transparent proxy eller WPAD har implementerats i nätverkstopologin behöver du inte göra några särskilda konfigurationsinställningar. Mer information om undantag för slutpunkts-URL för slutpunkt i proxyn finns i avsnittet Url-adresser för [proxytjänsten](production-deployment.md#proxy-service-urls) i det här dokumentet för listan Tillåtna URL:er eller Konfigurera enhetsproxy och [Internetanslutningsinställningar.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

**Manuell konfiguration av statisk proxy:**

-   Registerbaserad konfiguration

-   WinHTTP konfigurerat med netsh-kommandot <br> Endast lämpligt för stationära datorer i en stabil topologi (t.ex. ett skrivbord i ett företagsnätverk bakom samma proxy)

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Konfigurera proxyservern manuellt med hjälp av en registerbaserad statisk proxy

Konfigurera en registerbaserad statisk proxy så att endast Microsoft Defender för slutpunkts sensor kan rapportera diagnostikdata och kommunicera med Microsoft Defender för Slutpunktstjänster om en dator inte har tillåtelse att ansluta till Internet. Den statiska proxyn kan konfigureras via en grupprincip. Grupprincipen finns under:

 - Administrativa mallar \> Windows datainsamlings- och förhandsversioner av komponenter Konfigurera autentiserad proxyanvändning för ansluten användarupplevelse och \> \> telemetritjänst
     - Ställ in den **på Aktiverad** och välj **Inaktivera autentiserad proxyanvändning**

1. Öppna konsolen Grupprinciphantering.
2. Skapa en princip eller redigera en befintlig princip utifrån organisationsrutinerna.
3. Redigera grupprincipen och gå till Administrativa mallar Windows datasamlings- och förhandsversions buildar Förkonfigurera autentiserad proxyanvändning för den anslutna användarupplevelsen och **\> \> \> telemetritjänsten.** 
    ![Bild av grupprincipkonfiguration](images/atp-gpo-proxy1.png)

4. Välj **Aktiverad**.
5. Välj **Inaktivera autentiserad proxyanvändning.**
   
6. Gå till **Administrativa mallar \> Windows datainsamlings- och förhandsversioner av komponenter \> Konfigurera anslutna \> användarupplevelser och telemetri.**
    ![Bild av grupprincipkonfigurationsinställning](images/atp-gpo-proxy2.png)
7. Välj **Aktiverad**.
8. Ange **proxyservernamnet**.

Principen anger två registervärden `TelemetryProxyServer` som REG_SZ och `DisableEnterpriseAuthProxy` som REG_DWORD under registernyckeln `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.

Registervärdet `TelemetryProxyServer` har följande strängformat:

```text
<server name or ip>:<port>
```

Till exempel: 10.0.0.6:8080

Registervärdet `DisableEnterpriseAuthProxy` anges till 1.

###  <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Konfigurera proxyservern manuellt med netsh-kommandot

Använd netsh för att konfigurera en systemomfattande statisk proxy.

> [!NOTE]
> - Detta påverkar alla program, inklusive Windows-tjänster som använder WinHTTP med standardproxyn.</br>
> - Bärbara datorer som ändrar topologi (till exempel från kontor till hem) fungerar inte på netsh. Använd den registerbaserade statiska proxykonfigurationen.

1. Öppna en upphöjd kommandorad:

    1. Gå till **Start** och skriv **cmd**.

    1. Högerklicka på **Kommandotolken** och välj **Kör som administratör**.

2. Skriv följande kommando och tryck på **Retur**:

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   Till exempel: netsh winhttp set proxy 10.0.0.6:8080


###  <a name="proxy-configuration-for-down-level-devices"></a>Proxykonfiguration för enheter på lägre nivå

Down-Level-enheter är bland annat Windows 7 SP1 och Windows 8.1 arbetsstationer samt Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 och versioner av Windows Server 2016 tidigare än Windows Server CB 1803. Proxyn konfigureras som en del av Microsoft Management Agent för att hantera kommunikation från slutpunkten till Azure. Mer information om hur en proxy konfigureras på dessa enheter finns i distributionsguiden för Microsoft Management Agent – snabb distribution.

### <a name="proxy-service-urls"></a>URL-adresser för proxytjänst
URL-adresser som innehåller v20 i dem behövs bara om du har Windows 10, version 1803 eller senare enheter. Till exempel ```us-v20.events.data.microsoft.com``` krävs endast om enheten finns på Windows 10, version 1803 eller senare.
 

Om en proxy eller brandvägg blockerar anonym trafik, som Microsoft Defender för Slutpunkts sensor ansluter från systemkontext, kontrollerar du att anonym trafik tillåts i de angivna webbadresserna.

I följande nedladdningsbara kalkylblad finns de tjänster och deras tillhörande URL:er som nätverket måste kunna ansluta till. Se till att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till dessa URL:er, eller så kan du behöva skapa en *tillåta-regel* specifikt för dem.

|**Kalkylblad med domänlista**|**Beskrivning**|
|:-----|:-----|
|![Miniatyrbild för Microsoft Defender för slutpunkts-URL:er-kalkylblad](images/mdatp-urls.png)<br/>  | Kalkylblad med specifika DNS-poster för tjänstplatser, geografiska platser och operativsystem. <br><br>[Ladda ned kalkylbladet här.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


###  <a name="microsoft-defender-for-endpoint-service-backend-ip-ranges"></a>IP-intervall för Microsoft Defender för slutpunktstjänstbackend

Om nätverksenheterna inte har stöd för DNS-baserade regler använder du IP-intervall i stället.

Defender för Endpoint är inbyggt i Azure Cloud och distribueras i följande regioner:

- AzureCloud.eastus
- AzureCloud.eastus2
- AzureCloud.westcentralus
- AzureCloud.northeurope
- AzureCloud.westeurope
- AzureCloud.uksouth
- AzureCloud.ukwest

Du hittar Azure IP-intervallen i [Azure IP-intervall och tjänsttaggar – Offentligt moln.](https://www.microsoft.com/download/details.aspx?id=56519)

> [!NOTE]
> Som en molnbaserad lösning kan IP-adressintervallen ändras. Vi rekommenderar att du går över till DNS-baserade regler.

> [!NOTE]
> Om du är myndighetskund i USA kan du se motsvarande avsnitt på sidan [Defender för slutpunkt för amerikanska](gov.md#service-backend-ip-ranges) myndigheter.

## <a name="next-step"></a>Nästa steg

![**Fas 3: Onboard**](images/onboard.png) <br>[Steg 3: Introduktion:](onboarding.md)Introducera enheter till tjänsten så att Microsoft Defender för Slutpunkt-tjänsten kan få sensordata från dem. 
