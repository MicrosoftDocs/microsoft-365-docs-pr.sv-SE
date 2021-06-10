---
title: Konfigurera Micro Focus ArcSight för att hämta Microsoft Defender för identifiering av slutpunkter
description: Konfigurera Micro Focus ArcSight så att den tar emot och hämtar identifieringar Microsoft Defender Säkerhetscenter
keywords: konfigurera Micro Focus ArcSight, säkerhetsinformation och händelsehanteringsverktyg, arcsight
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166191"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a><span data-ttu-id="598a7-104">Konfigurera Micro Focus ArcSight för att hämta Defender för slutpunktsidentifiering</span><span class="sxs-lookup"><span data-stu-id="598a7-104">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="598a7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="598a7-105">**Applies to:**</span></span>
- [<span data-ttu-id="598a7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="598a7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="598a7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="598a7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="598a7-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="598a7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="598a7-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="598a7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

<span data-ttu-id="598a7-110">Du måste installera och konfigurera vissa filer och verktyg för att använda Micro Focus ArcSight så att Defender kan användas för identifiering av slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="598a7-110">You'll need to install and configure some files and tools to use Micro Focus ArcSight so that it can pull Defender for Endpoint detections.</span></span>

>[!Note]
>- <span data-ttu-id="598a7-111">[Defender för slutpunktsavisering](alerts.md) består av en eller flera identifieringar</span><span class="sxs-lookup"><span data-stu-id="598a7-111">[Defender for Endpoint Alert](alerts.md) is composed from one or more detections</span></span>
>- <span data-ttu-id="598a7-112">[Defender för identifiering av](api-portal-mapping.md) slutpunkt består av den misstänkta händelsen som inträffade på enheten och tillhörande aviseringsinformation.</span><span class="sxs-lookup"><span data-stu-id="598a7-112">[Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="598a7-113">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="598a7-113">Before you begin</span></span>

<span data-ttu-id="598a7-114">Konfigurering av verktyget Micro Focus ArcSight Connector kräver flera konfigurationsfiler för att dra och tolka identifieringar från programmet Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="598a7-114">Configuring the Micro Focus ArcSight Connector tool requires several configuration files for it to pull and parse detections from your Azure Active Directory (AAD) application.</span></span>

<span data-ttu-id="598a7-115">I det här avsnittet får du hjälp med att ställa in och använda de konfigurationsfiler som krävs.</span><span class="sxs-lookup"><span data-stu-id="598a7-115">This section guides you in getting the necessary information to set and use the required configuration files correctly.</span></span>

- <span data-ttu-id="598a7-116">Kontrollera att du har aktiverat SIEM-integreringsfunktionen på **Inställningar menyn.**</span><span class="sxs-lookup"><span data-stu-id="598a7-116">Make sure you have enabled the SIEM integration feature from the **Settings** menu.</span></span> <span data-ttu-id="598a7-117">Mer information finns i Aktivera [SIEM-integrering i Defender för slutpunkt.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="598a7-117">For more information, see [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="598a7-118">Se till att filen du sparade från att aktivera SIEM-integreringsfunktionen är klar.</span><span class="sxs-lookup"><span data-stu-id="598a7-118">Have the file you saved from enabling the SIEM integration feature ready.</span></span> <span data-ttu-id="598a7-119">Du måste få följande värden:</span><span class="sxs-lookup"><span data-stu-id="598a7-119">You'll need to get the following values:</span></span>
  - <span data-ttu-id="598a7-120">OAuth 2.0 Token refresh URL</span><span class="sxs-lookup"><span data-stu-id="598a7-120">OAuth 2.0 Token refresh URL</span></span>
  - <span data-ttu-id="598a7-121">OAuth 2.0 Klient-ID</span><span class="sxs-lookup"><span data-stu-id="598a7-121">OAuth 2.0 Client ID</span></span>
  - <span data-ttu-id="598a7-122">OAuth 2.0 Client secret</span><span class="sxs-lookup"><span data-stu-id="598a7-122">OAuth 2.0 Client secret</span></span>

- <span data-ttu-id="598a7-123">Ha följande konfigurationsfiler redo:</span><span class="sxs-lookup"><span data-stu-id="598a7-123">Have the following configuration files ready:</span></span>
  - <span data-ttu-id="598a7-124">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="598a7-124">WDATP-connector.properties</span></span>
  - <span data-ttu-id="598a7-125">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="598a7-125">WDATP-connector.jsonparser.properties</span></span>

    <span data-ttu-id="598a7-126">Du skulle ha sparat en .zip som innehåller de här två filerna när du valde Micro Focus ArcSight som den SIEM-typ du använder i organisationen.</span><span class="sxs-lookup"><span data-stu-id="598a7-126">You would have saved a .zip file which contains these two files when you chose Micro Focus ArcSight as the SIEM type you use in your organization.</span></span>

- <span data-ttu-id="598a7-127">Se till att du genererar följande token och har dem redo:</span><span class="sxs-lookup"><span data-stu-id="598a7-127">Make sure you generate the following tokens and have them ready:</span></span>
  - <span data-ttu-id="598a7-128">Åtkomsttoken</span><span class="sxs-lookup"><span data-stu-id="598a7-128">Access token</span></span>
  - <span data-ttu-id="598a7-129">Uppdatera token</span><span class="sxs-lookup"><span data-stu-id="598a7-129">Refresh token</span></span>

  <span data-ttu-id="598a7-130">Du kan generera de här tokenen från avsnittet konfiguration av **SIEM-integrering** i portalen.</span><span class="sxs-lookup"><span data-stu-id="598a7-130">You can generate these tokens from the **SIEM integration** setup section of the portal.</span></span>

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a><span data-ttu-id="598a7-131">Installera och konfigurera Micro Focus ArcSight FlexConnector</span><span class="sxs-lookup"><span data-stu-id="598a7-131">Install and configure Micro Focus ArcSight FlexConnector</span></span>

<span data-ttu-id="598a7-132">I följande anvisningar förutsätts att du har slutfört alla steg som krävs [i Innan du börjar](#before-you-begin).</span><span class="sxs-lookup"><span data-stu-id="598a7-132">The following steps assume that you have completed all the required steps in [Before you begin](#before-you-begin).</span></span>

1. <span data-ttu-id="598a7-133">Installera det senaste 32-bitarsinstallationsprogrammet Windows FlexConnector.</span><span class="sxs-lookup"><span data-stu-id="598a7-133">Install the latest 32-bit Windows FlexConnector installer.</span></span> <span data-ttu-id="598a7-134">Du hittar detta i HPE Software Center.</span><span class="sxs-lookup"><span data-stu-id="598a7-134">You can find this in the HPE Software center.</span></span> <span data-ttu-id="598a7-135">Verktyget installeras vanligtvis på följande standardplats: `C:\Program Files\ArcSightFlexConnectors\current\bin` .</span><span class="sxs-lookup"><span data-stu-id="598a7-135">The tool is typically installed in the following default location: `C:\Program Files\ArcSightFlexConnectors\current\bin`.</span></span></br></br><span data-ttu-id="598a7-136">Du kan välja var verktyget ska sparas, till exempel C: \\ *folder_location*\current\bin där *folder_location* representerar installationsplats.</span><span class="sxs-lookup"><span data-stu-id="598a7-136">You can choose where to save the tool, for example C:\\*folder_location*\current\bin where *folder_location* represents the installation location.</span></span>

2. <span data-ttu-id="598a7-137">Följ installationsguiden genom följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="598a7-137">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="598a7-138">Introduktion</span><span class="sxs-lookup"><span data-stu-id="598a7-138">Introduction</span></span>
   - <span data-ttu-id="598a7-139">Välj Installera mapp</span><span class="sxs-lookup"><span data-stu-id="598a7-139">Choose Install Folder</span></span>
   - <span data-ttu-id="598a7-140">Välj Installera uppsättning</span><span class="sxs-lookup"><span data-stu-id="598a7-140">Choose Install Set</span></span>
   - <span data-ttu-id="598a7-141">Välj Genvägsmapp</span><span class="sxs-lookup"><span data-stu-id="598a7-141">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="598a7-142">Sammanfattning före installationen</span><span class="sxs-lookup"><span data-stu-id="598a7-142">Pre-Installation Summary</span></span>
   - <span data-ttu-id="598a7-143">Installerar...</span><span class="sxs-lookup"><span data-stu-id="598a7-143">Installing...</span></span>

   <span data-ttu-id="598a7-144">Du kan behålla standardvärdena för var och en av dessa uppgifter eller ändra valet så att det passar dina behov.</span><span class="sxs-lookup"><span data-stu-id="598a7-144">You can keep the default values for each of these tasks or modify the selection to suit your requirements.</span></span>

3. <span data-ttu-id="598a7-145">Öppna Utforskaren och leta reda på de två konfigurationsfiler som du sparade när du aktiverade SIEM-integreringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="598a7-145">Open File Explorer and locate the two configuration files you saved when you enabled the SIEM integration feature.</span></span> <span data-ttu-id="598a7-146">Placera de två filerna på FlexConnector-installationsplatsen, till exempel:</span><span class="sxs-lookup"><span data-stu-id="598a7-146">Put the two files in the FlexConnector installation location, for example:</span></span>

   - <span data-ttu-id="598a7-147">WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="598a7-147">WDATP-connector.jsonparser.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   - <span data-ttu-id="598a7-148">WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="598a7-148">WDATP-connector.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   > [!NOTE]
   > 
   > <span data-ttu-id="598a7-149">Du måste placera konfigurationsfilerna på den här *platsen, folder_location* representerar den plats där du installerade verktyget.</span><span class="sxs-lookup"><span data-stu-id="598a7-149">You must put the configuration files in this location, where *folder_location* represents the location where you installed the tool.</span></span>

4. <span data-ttu-id="598a7-150">När installationen av kärnkopplingen är klar öppnas fönstret Kopplingskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="598a7-150">After the installation of the core connector completes, the Connector Setup window opens.</span></span> <span data-ttu-id="598a7-151">Välj Lägg till en koppling i **fönstret Konfiguration av koppling.**</span><span class="sxs-lookup"><span data-stu-id="598a7-151">In the Connector Setup window, select **Add a Connector**.</span></span>

5. <span data-ttu-id="598a7-152">Välj Typ: **ArcSight FlexConnector REST** och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="598a7-152">Select Type: **ArcSight FlexConnector REST** and click **Next**.</span></span>

6. <span data-ttu-id="598a7-153">Ange följande information i formuläret för parameterinformation.</span><span class="sxs-lookup"><span data-stu-id="598a7-153">Type the following information in the parameter details form.</span></span> <span data-ttu-id="598a7-154">Alla andra värden i formuläret är valfria och kan lämnas tomma.</span><span class="sxs-lookup"><span data-stu-id="598a7-154">All other values in the form are optional and can be left blank.</span></span>

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th><span data-ttu-id="598a7-155">Fält</span><span class="sxs-lookup"><span data-stu-id="598a7-155">Field</span></span></th>
    <th><span data-ttu-id="598a7-156">Värde</span><span class="sxs-lookup"><span data-stu-id="598a7-156">Value</span></span></th>
    </tr>
    <tr>
    <td><span data-ttu-id="598a7-157">Konfigurationsfil</span><span class="sxs-lookup"><span data-stu-id="598a7-157">Configuration File</span></span></td>
    <td><span data-ttu-id="598a7-158">Skriv namnet på egenskapsfilen för klienten.</span><span class="sxs-lookup"><span data-stu-id="598a7-158">Type in the name of the client property file.</span></span> <span data-ttu-id="598a7-159">Namnet måste matcha filen som angavs i .zip du hämtade.</span><span class="sxs-lookup"><span data-stu-id="598a7-159">The name must match the file provided in the .zip that you downloaded.</span></span>
<span data-ttu-id="598a7-160">Om konfigurationsfilen i flexagent-katalogen till exempel heter &quot; &quot;WDATP-Connector.js&quot; onparser.properties måste du skriva &quot; &quot; WDATP-Connector &quot; som namn på egenskapsfilen för klienten.</span><span class="sxs-lookup"><span data-stu-id="598a7-160">For example, if the configuration file in &quot;flexagent&quot; directory is named &quot;WDATP-Connector.jsonparser.properties&quot;, you must type &quot;WDATP-Connector&quot; as the name of the client property file.</span></span></td>
    </tr>
    <td><span data-ttu-id="598a7-161">URL för händelser</span><span class="sxs-lookup"><span data-stu-id="598a7-161">Events URL</span></span></td>
    <td><span data-ttu-id="598a7-162">Beroende på platsen för ditt datacenter väljer du antingen EU eller URL:en för USA:</span><span class="sxs-lookup"><span data-stu-id="598a7-162">Depending on the location of your datacenter, select either the EU or the US URL:</span></span> </br></br> <span data-ttu-id="598a7-163"><b>För EU:</b>https:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="598a7-163"><b>For EU</b>:  https://<i></i>wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br>
   </br><span data-ttu-id="598a7-164"><b>För USA:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="598a7-164"><b>For US:</b> https://<i></i>wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br> <br> <span data-ttu-id="598a7-165"><b>I Storbritannien</b>: https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="598a7-165"><b>For UK</b>:  https://<i></i>wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span></td>
    <tr>
    <td><span data-ttu-id="598a7-166">Autentiseringstyp</span><span class="sxs-lookup"><span data-stu-id="598a7-166">Authentication Type</span></span></td>
    <td><span data-ttu-id="598a7-167">OAuth 2</span><span class="sxs-lookup"><span data-stu-id="598a7-167">OAuth 2</span></span></td>
    </tr>
    <td><span data-ttu-id="598a7-168">OAuth 2 Client Properties-fil</span><span class="sxs-lookup"><span data-stu-id="598a7-168">OAuth 2 Client Properties file</span></span></td>
    <td><span data-ttu-id="598a7-169">Bläddra till platsen för <em>wdatp-connector.properties-filen.</em></span><span class="sxs-lookup"><span data-stu-id="598a7-169">Browse to the location of the <em>wdatp-connector.properties</em> file.</span></span> <span data-ttu-id="598a7-170">Namnet måste matcha filen som angavs i .zip du hämtade.</span><span class="sxs-lookup"><span data-stu-id="598a7-170">The name must match the file provided in the .zip that you downloaded.</span></span></td>
    <tr>
    <td><span data-ttu-id="598a7-171">Uppdatera token</span><span class="sxs-lookup"><span data-stu-id="598a7-171">Refresh Token</span></span></td>
    <td><span data-ttu-id="598a7-172">Du kan hämta en uppdateringstoken på två sätt: genom att generera en uppdateringstoken från sidan <b>SIEM-inställningar</b> eller använda restutil-verktyget.</span><span class="sxs-lookup"><span data-stu-id="598a7-172">You can obtain a refresh token in two ways: by generating a refresh token from the <b>SIEM settings</b> page or using the restutil tool.</span></span> <br><br> <span data-ttu-id="598a7-173">Mer information om att generera en uppdateringstoken från <b>inställningarna</b> finns i <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Aktivera SIEM-integrering i Defender för slutpunkt.</a></span><span class="sxs-lookup"><span data-stu-id="598a7-173">For more information on generating a refresh token from the <b>Preferences setup</b> , see <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>.</span></span> </br> </br><span data-ttu-id="598a7-174"><b>Hämta uppdateringstoken med verktyget restutil:</b> </span><span class="sxs-lookup"><span data-stu-id="598a7-174"><b>Get your refresh token using the restutil tool:</b> </span></span></br> <span data-ttu-id="598a7-175">a.</span><span class="sxs-lookup"><span data-stu-id="598a7-175">a.</span></span> <span data-ttu-id="598a7-176">Öppna en kommandotolk.</span><span class="sxs-lookup"><span data-stu-id="598a7-176">Open a command prompt.</span></span> <span data-ttu-id="598a7-177">Gå till C:\<em>folder_location</em>\current\bin <em>där folder_location</em> representerar den plats där du installerade verktyget.</span><span class="sxs-lookup"><span data-stu-id="598a7-177">Navigate to C:\<em>folder_location</em>\current\bin where <em>folder_location</em> represents the location where you installed the tool.</span></span> </br></br> <span data-ttu-id="598a7-178">b.</span><span class="sxs-lookup"><span data-stu-id="598a7-178">b.</span></span> <span data-ttu-id="598a7-179">Skriv: <code>arcsight restutil token -config</code> från fackkatalogen. Till exempel: <b>arcsight restutil boxtoken -proxy.location.hp.com:8080</b> ett webbläsarfönster öppnas.</span><span class="sxs-lookup"><span data-stu-id="598a7-179">Type: <code>arcsight restutil token -config</code> from the bin directory.For example: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> A Web browser window will open.</span></span> </br> </br><span data-ttu-id="598a7-180">c.</span><span class="sxs-lookup"><span data-stu-id="598a7-180">c.</span></span> <span data-ttu-id="598a7-181">Skriv in dina autentiseringsuppgifter och klicka sedan på lösenordsfältet för att låta sidan omdirigera.</span><span class="sxs-lookup"><span data-stu-id="598a7-181">Type in your credentials then click on the password field to let the page redirect.</span></span> <span data-ttu-id="598a7-182">I inloggningsupp frågan anger du dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="598a7-182">In the login prompt, enter your credentials.</span></span> </br> </br><span data-ttu-id="598a7-183">d.</span><span class="sxs-lookup"><span data-stu-id="598a7-183">d.</span></span> <span data-ttu-id="598a7-184">En uppdateringstoken visas i kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="598a7-184">A refresh token is shown in the command prompt.</span></span> </br></br> <span data-ttu-id="598a7-185">e.</span><span class="sxs-lookup"><span data-stu-id="598a7-185">e.</span></span> <span data-ttu-id="598a7-186">Kopiera och klistra in den i <b>fältet Uppdatera</b> token.</span><span class="sxs-lookup"><span data-stu-id="598a7-186">Copy and paste it into the <b>Refresh Token</b> field.</span></span>
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. <span data-ttu-id="598a7-187">Ett webbläsarfönster öppnas av kopplingen.</span><span class="sxs-lookup"><span data-stu-id="598a7-187">A browser window is opened by the connector.</span></span> <span data-ttu-id="598a7-188">Logga in med dina inloggningsuppgifter för programmet.</span><span class="sxs-lookup"><span data-stu-id="598a7-188">Login with your application credentials.</span></span> <span data-ttu-id="598a7-189">När du har loggat in uppmanas du att ge behörighet till din OAuth2-klient.</span><span class="sxs-lookup"><span data-stu-id="598a7-189">After you log in, you'll be asked to give permission to your OAuth2 Client.</span></span> <span data-ttu-id="598a7-190">Du måste ge behörighet till din OAuth 2-klient så att anslutningskonfigurationen kan autentiseras.</span><span class="sxs-lookup"><span data-stu-id="598a7-190">You must give permission to your OAuth 2 Client so that the connector configuration can authenticate.</span></span>

   <span data-ttu-id="598a7-191">Om det <code>redirect_uri</code> är en https-URL omdirigeras du till en URL på den lokala värden.</span><span class="sxs-lookup"><span data-stu-id="598a7-191">If the <code>redirect_uri</code> is a https URL, you'll be redirected to a URL on the local host.</span></span> <span data-ttu-id="598a7-192">En sida visas där du uppmanas att lita på det certifikat som tillhandahålls av anslutningen som körs på den lokala värden.</span><span class="sxs-lookup"><span data-stu-id="598a7-192">You'll see a page that requests for you to trust the certificate supplied by the connector running on the local host.</span></span> <span data-ttu-id="598a7-193">Du måste lita på certifikatet om det redirect_uri ett https.</span><span class="sxs-lookup"><span data-stu-id="598a7-193">You'll need to trust this certificate if the redirect_uri is a https.</span></span>
   
   <span data-ttu-id="598a7-194">Om du däremot anger en http-URL för redirect_uri-adress, behöver du inte ge ditt medgivande för att lita på certifikatet.</span><span class="sxs-lookup"><span data-stu-id="598a7-194">If however you specify a http URL for the redirect_uri, you do not need to provide consent in trusting the certificate.</span></span>

8. <span data-ttu-id="598a7-195">Fortsätt med anslutningskonfigurationen genom att gå tillbaka till installationsfönstret för Micro Focus ArcSight Connector.</span><span class="sxs-lookup"><span data-stu-id="598a7-195">Continue with the connector setup by returning to the Micro Focus ArcSight Connector Setup window.</span></span>

9. <span data-ttu-id="598a7-196">Välj **Hanteraren för ArcSight (krypterad)** som destination och klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="598a7-196">Select the **ArcSight Manager (encrypted)** as the destination and click **Next**.</span></span>

10. <span data-ttu-id="598a7-197">Skriv in mål-IP/hostname i **Manager Hostname** och dina autentiseringsuppgifter i formuläret för parametrar.</span><span class="sxs-lookup"><span data-stu-id="598a7-197">Type in the destination IP/hostname in **Manager Hostname** and your credentials in the parameters form.</span></span> <span data-ttu-id="598a7-198">Alla andra värden i formuläret bör behållas med standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="598a7-198">All other values in the form should be retained with the default values.</span></span> <span data-ttu-id="598a7-199">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="598a7-199">Click **Next**.</span></span>

11. <span data-ttu-id="598a7-200">Skriv ett namn på kopplingen i formuläret för kopplingsinformation.</span><span class="sxs-lookup"><span data-stu-id="598a7-200">Type in a name for the connector in the connector details form.</span></span> <span data-ttu-id="598a7-201">Alla andra värden i formuläret är valfria och kan lämnas tomma.</span><span class="sxs-lookup"><span data-stu-id="598a7-201">All other values in the form are optional and can be left blank.</span></span> <span data-ttu-id="598a7-202">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="598a7-202">Click **Next**.</span></span>

12. <span data-ttu-id="598a7-203">Fönstret för importcertifikat för ESM-hanteraren visas.</span><span class="sxs-lookup"><span data-stu-id="598a7-203">The ESM Manager import certificate window is shown.</span></span> <span data-ttu-id="598a7-204">Välj **Importera certifikatet till anslutningen från destinationen och** klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="598a7-204">Select **Import the certificate to connector from destination** and click **Next**.</span></span> <span data-ttu-id="598a7-205">Fönstret **Lägg till** kopplingssammanfattning visas och certifikatet importeras.</span><span class="sxs-lookup"><span data-stu-id="598a7-205">The **Add connector Summary** window is displayed and the certificate is imported.</span></span>

13. <span data-ttu-id="598a7-206">Kontrollera att informationen i fönstret Sammanfattning **av lägg till koppling** är korrekt och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="598a7-206">Verify that the details in the **Add connector Summary** window is correct, then click **Next**.</span></span>

14. <span data-ttu-id="598a7-207">Välj **Installera som tjänst och** klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="598a7-207">Select **Install as a service** and click **Next**.</span></span>

15. <span data-ttu-id="598a7-208">Skriv ett namn i fältet **Internt namn för** tjänsten.</span><span class="sxs-lookup"><span data-stu-id="598a7-208">Type a name in the **Service Internal Name** field.</span></span> <span data-ttu-id="598a7-209">Alla andra värden i formuläret kan behållas med standardvärdena eller lämnas tomma.</span><span class="sxs-lookup"><span data-stu-id="598a7-209">All other values in the form can be retained with the default values or left blank .</span></span> <span data-ttu-id="598a7-210">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="598a7-210">Click **Next**.</span></span>

16. <span data-ttu-id="598a7-211">Skriv in tjänstparametrarna och klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="598a7-211">Type in the service parameters and click **Next**.</span></span> <span data-ttu-id="598a7-212">Ett fönster med **sammanfattningen av installationen** av tjänsten visas.</span><span class="sxs-lookup"><span data-stu-id="598a7-212">A window with the **Install Service Summary** is shown.</span></span> <span data-ttu-id="598a7-213">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="598a7-213">Click **Next**.</span></span>

17. <span data-ttu-id="598a7-214">Avsluta installationen genom att välja **Avsluta** och **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="598a7-214">Finish the installation by selecting **Exit** and **Next**.</span></span>

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a><span data-ttu-id="598a7-215">Installera och konfigurera Konsolen Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="598a7-215">Install and configure the Micro Focus ArcSight console</span></span>

1. <span data-ttu-id="598a7-216">Följ installationsguiden genom följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="598a7-216">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="598a7-217">Introduktion</span><span class="sxs-lookup"><span data-stu-id="598a7-217">Introduction</span></span>
   - <span data-ttu-id="598a7-218">Licensavtal</span><span class="sxs-lookup"><span data-stu-id="598a7-218">License Agreement</span></span>
   - <span data-ttu-id="598a7-219">Specialmeddelande</span><span class="sxs-lookup"><span data-stu-id="598a7-219">Special Notice</span></span>
   - <span data-ttu-id="598a7-220">Välj installationskatalogen ArcSight</span><span class="sxs-lookup"><span data-stu-id="598a7-220">Choose ArcSight installation directory</span></span>
   - <span data-ttu-id="598a7-221">Välj Genvägsmapp</span><span class="sxs-lookup"><span data-stu-id="598a7-221">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="598a7-222">Sammanfattning före installationen</span><span class="sxs-lookup"><span data-stu-id="598a7-222">Pre-Installation Summary</span></span>

2. <span data-ttu-id="598a7-223">Klicka på **Installera**.</span><span class="sxs-lookup"><span data-stu-id="598a7-223">Click **Install**.</span></span> <span data-ttu-id="598a7-224">När installationen har slutförts öppnas konfigurationsguiden för ArcSight Console.</span><span class="sxs-lookup"><span data-stu-id="598a7-224">After the installation completes, the ArcSight Console Configuration Wizard opens.</span></span>

3. <span data-ttu-id="598a7-225">Skriv localhost i **Manager Host Name och** 8443 i Manager Port **och** klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="598a7-225">Type localhost in **Manager Host Name** and 8443 in **Manager Port** then click **Next**.</span></span>

4. <span data-ttu-id="598a7-226">Välj **Använd direktanslutning** och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="598a7-226">Select **Use direct connection**, then click **Next**.</span></span>

5. <span data-ttu-id="598a7-227">Välj **Lösenordsbaserad autentisering** och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="598a7-227">Select **Password Based Authentication**, then click **Next**.</span></span>

6. <span data-ttu-id="598a7-228">Välj **Det här är en installation för en enskild användare. (Rekommenderas)** och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="598a7-228">Select **This is a single user installation. (Recommended)**, then click **Next**.</span></span>

7. <span data-ttu-id="598a7-229">Avsluta **installationsprogrammet** genom att klicka på Klar.</span><span class="sxs-lookup"><span data-stu-id="598a7-229">Click **Done** to quit the installer.</span></span>

8. <span data-ttu-id="598a7-230">Logga in på konsolen Micro Focus ArcSight.</span><span class="sxs-lookup"><span data-stu-id="598a7-230">Login to the Micro Focus ArcSight console.</span></span>

9. <span data-ttu-id="598a7-231">Gå till **Aktiv kanal ange Ny** villkor  >    >    >  **enhetens enhet produkt**.</span><span class="sxs-lookup"><span data-stu-id="598a7-231">Navigate to **Active channel set** > **New Condition** > **Device** > **Device Product**.</span></span>

10. <span data-ttu-id="598a7-232">Ange **enhet produkt = Microsoft Defender ATP**.</span><span class="sxs-lookup"><span data-stu-id="598a7-232">Set **Device Product = Microsoft Defender ATP**.</span></span> <span data-ttu-id="598a7-233">När du har kontrollerat att händelser flödar till verktyget stoppar du processen igen och går till Windows Services och startar ArcSight FlexConnector REST.</span><span class="sxs-lookup"><span data-stu-id="598a7-233">When you've verified that events are flowing to the tool, stop the process again and go to Windows Services and start the ArcSight FlexConnector REST.</span></span>

<span data-ttu-id="598a7-234">Nu kan du köra frågor i konsolen Micro Focus ArcSight.</span><span class="sxs-lookup"><span data-stu-id="598a7-234">You can now run queries in the Micro Focus ArcSight console.</span></span>

<span data-ttu-id="598a7-235">Defender för slutpunktsidentifiering visas som fristående händelser, med "Microsoft" som leverantör och "atp Windows Defender" som enhetsnamn.</span><span class="sxs-lookup"><span data-stu-id="598a7-235">Defender for Endpoint detections will appear as discrete events, with "Microsoft” as the vendor and “Windows Defender ATP” as the device name.</span></span>


## <a name="troubleshooting-micro-focus-arcsight-connection"></a><span data-ttu-id="598a7-236">Felsöka anslutning för Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="598a7-236">Troubleshooting Micro Focus ArcSight connection</span></span>

<span data-ttu-id="598a7-237">**Problem:** Det gick inte att uppdatera token.</span><span class="sxs-lookup"><span data-stu-id="598a7-237">**Problem:** Failed to refresh the token.</span></span> <span data-ttu-id="598a7-238">Loggen finns på C: folder_location \\ \current\logs där *folder_location* representerar den plats där du installerade verktyget.</span><span class="sxs-lookup"><span data-stu-id="598a7-238">You can find the log located in C:\\*folder_location*\current\logs where *folder_location* represents the location where you installed the tool.</span></span> <span data-ttu-id="598a7-239">Öppna _agent.log_ och leta efter `ERROR/FATAL/WARN` .</span><span class="sxs-lookup"><span data-stu-id="598a7-239">Open _agent.log_ and look for `ERROR/FATAL/WARN`.</span></span>

<span data-ttu-id="598a7-240">**Symptom:** Du får följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="598a7-240">**Symptom:** You get the following error message:</span></span>

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

<span data-ttu-id="598a7-241">**Lösning:**</span><span class="sxs-lookup"><span data-stu-id="598a7-241">**Solution:**</span></span>

1. <span data-ttu-id="598a7-242">Stoppa processen genom att klicka på Ctrl + C i fönstret Koppling.</span><span class="sxs-lookup"><span data-stu-id="598a7-242">Stop the process by clicking Ctrl + C on the Connector window.</span></span> <span data-ttu-id="598a7-243">Klicka **på Y** när du tillfrågas om "Avbryt batchjobb Y/N?".</span><span class="sxs-lookup"><span data-stu-id="598a7-243">Click **Y** when asked "Terminate batch job Y/N?".</span></span>

2. <span data-ttu-id="598a7-244">Gå till mappen där du sparade FILEN WDATP-connector.properties och redigera den för att lägga till följande värde: `reauthenticate=true` .</span><span class="sxs-lookup"><span data-stu-id="598a7-244">Navigate to the folder where you stored the WDATP-connector.properties file and edit it to add the following value: `reauthenticate=true`.</span></span>

3. <span data-ttu-id="598a7-245">Starta om kopplingen genom att köra följande kommando: `arcsight.bat connectors` .</span><span class="sxs-lookup"><span data-stu-id="598a7-245">Restart the connector by running the following command: `arcsight.bat connectors`.</span></span>

   <span data-ttu-id="598a7-246">Ett webbläsarfönster visas.</span><span class="sxs-lookup"><span data-stu-id="598a7-246">A browser window appears.</span></span> <span data-ttu-id="598a7-247">Tillåt att den körs, den ska försvinna och kopplingen ska nu vara igång.</span><span class="sxs-lookup"><span data-stu-id="598a7-247">Allow it to run, it should disappear, and the connector should now be running.</span></span>

> [!NOTE]
> <span data-ttu-id="598a7-248">Kontrollera att kopplingen körs genom att stoppa processen igen.</span><span class="sxs-lookup"><span data-stu-id="598a7-248">Verify that the connector is running by stopping the process again.</span></span> <span data-ttu-id="598a7-249">Starta sedan kopplingen igen så visas inget webbläsarfönster.</span><span class="sxs-lookup"><span data-stu-id="598a7-249">Then start the connector again, and no browser window should appear.</span></span>

## <a name="related-topics"></a><span data-ttu-id="598a7-250">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="598a7-250">Related topics</span></span>
- [<span data-ttu-id="598a7-251">Aktivera SIEM-integrering i Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="598a7-251">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="598a7-252">Dra identifieringar till dina SIEM-verktyg</span><span class="sxs-lookup"><span data-stu-id="598a7-252">Pull detections to your SIEM tools</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [<span data-ttu-id="598a7-253">Hämta Defender för slutpunktsidentifiering med REST API</span><span class="sxs-lookup"><span data-stu-id="598a7-253">Pull Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="598a7-254">Felsöka problem med SIEM-verktygsintegrering</span><span class="sxs-lookup"><span data-stu-id="598a7-254">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
