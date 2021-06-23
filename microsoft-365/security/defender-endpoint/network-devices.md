---
title: Identifiering och hantering av säkerhetsrisker
description: Rekommendationer och identifiering av säkerhetsbrister är nu tillgängliga för operativsystem för switchar, routrar, WLAN-handkontroller och brandväggar.
keywords: nätverksenheter, nätverksenheter för sårbarhetsidentifiering, operativsystem för switchar, routrar, WLAN-styrenheter och brandväggar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 86b8a37fd6b2d6f9906321b5d74de0e21c45fca3
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062147"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="ca65f-104">Identifiering och hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="ca65f-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ca65f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ca65f-105">**Applies to:**</span></span>

- [<span data-ttu-id="ca65f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ca65f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="ca65f-107">Hot och hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="ca65f-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="ca65f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca65f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ca65f-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="ca65f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ca65f-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="ca65f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]  
> <span data-ttu-id="ca65f-111">Blogg [som](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) publicerats \( 2021-04-13-2021 med insikter om de nya funktionerna för identifiering av nätverksenhet i \) Defender för Slutpunkt. </span><span class="sxs-lookup"><span data-stu-id="ca65f-111">The [Network device discovery and vulnerability assessments](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) Blog \(published 04-13-2021\) provides insights into the new **Network device discovery** capabilities in Defender for Endpoint.</span></span> <span data-ttu-id="ca65f-112">Den här artikeln innehåller en översikt över utmaningen **som** upptäckten av nätverksenhet är utformad för att hantera och detaljerad information om hur du kommer igång med de här nya funktionerna.</span><span class="sxs-lookup"><span data-stu-id="ca65f-112">This article provides an overview of the challenge that **Network device discovery** is designed to address, and detailed information about how get started using these new capabilities.</span></span>

<span data-ttu-id="ca65f-113">Funktioner för nätverksidentifiering är tillgängliga i **avsnittet** Enhetsinventering Microsoft 365 säkerhetscenter och Microsoft Defender Säkerhetscenter konsoler.</span><span class="sxs-lookup"><span data-stu-id="ca65f-113">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="ca65f-114">En Microsoft Defender för Slutpunkt-enhet används på varje nätverkssegment för att utföra periodiska autentiserade genomsökningar av förkonfigurerade nätverksenheter.</span><span class="sxs-lookup"><span data-stu-id="ca65f-114">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="ca65f-115">När Den har identifierats tillhandahåller Defender för Endpoints Hantering av hot och säkerhetsrisker-funktioner integrerade arbetsflöden för att säkra identifierade switchar, routrar, WLAN-styrenheter, brandväggar och VPN-gatewayer.</span><span class="sxs-lookup"><span data-stu-id="ca65f-115">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="ca65f-116">När nätverksenheterna upptäcks och klassificeras kommer säkerhetsadministratörerna att kunna ta emot de senaste säkerhetsrekommendationerna och granska nyligen identifierade svagheter på nätverksenheter som distribuerats i deras organisationer.</span><span class="sxs-lookup"><span data-stu-id="ca65f-116">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="ca65f-117">Metod</span><span class="sxs-lookup"><span data-stu-id="ca65f-117">Approach</span></span>

<span data-ttu-id="ca65f-118">Nätverksenheter hanteras inte som standardslutpunkter eftersom Defender för Slutpunkt inte har någon sensor inbyggd i själva nätverksenheterna.</span><span class="sxs-lookup"><span data-stu-id="ca65f-118">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="ca65f-119">Den här typen av enheter kräver en agentlös metod där en fjärrsökning hämtar den information som behövs från enheterna.</span><span class="sxs-lookup"><span data-stu-id="ca65f-119">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="ca65f-120">Beroende på nätverkets topologi och egenskaper utför en enskild enhet eller några enheter som förs in i Microsoft Defender för Slutpunkt autentiserade genomsökningar av nätverksenheter med SNMP (skrivskyddat).</span><span class="sxs-lookup"><span data-stu-id="ca65f-120">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="ca65f-121">Det kommer att finnas två typer av enheter att tänka på:</span><span class="sxs-lookup"><span data-stu-id="ca65f-121">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="ca65f-122">**Utvärderingsenhet:** En enhet som redan är inbyggd och som du använder för att söka igenom nätverksenheterna.</span><span class="sxs-lookup"><span data-stu-id="ca65f-122">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="ca65f-123">**Nätverksenheter:** Nätverksenheterna som ska skannas och introduceras.</span><span class="sxs-lookup"><span data-stu-id="ca65f-123">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="ca65f-124">Sårbarhetshantering för nätverksenheter</span><span class="sxs-lookup"><span data-stu-id="ca65f-124">Vulnerability management for network devices</span></span> 

<span data-ttu-id="ca65f-125">När nätverksenheterna upptäcks och klassificeras kommer säkerhetsadministratörerna att kunna ta emot de senaste säkerhetsrekommendationerna och granska nyligen identifierade svagheter på nätverksenheter som distribuerats i deras organisationer.</span><span class="sxs-lookup"><span data-stu-id="ca65f-125">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="ca65f-126">Operativsystem som stöds</span><span class="sxs-lookup"><span data-stu-id="ca65f-126">Operating systems that are supported</span></span>

<span data-ttu-id="ca65f-127">Följande operativsystem stöds för närvarande:</span><span class="sxs-lookup"><span data-stu-id="ca65f-127">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="ca65f-128">Cisco IOS, IOS-XE, NX-OS</span><span class="sxs-lookup"><span data-stu-id="ca65f-128">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="ca65f-129">Juniper JURESTER</span><span class="sxs-lookup"><span data-stu-id="ca65f-129">Juniper JUNOS</span></span>
- <span data-ttu-id="ca65f-130">HPE ArubaOS, Procurve Switch Software</span><span class="sxs-lookup"><span data-stu-id="ca65f-130">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="ca65f-131">Palo Mobil Networks PAN-OS</span><span class="sxs-lookup"><span data-stu-id="ca65f-131">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="ca65f-132">Fler nätverksleverantörer och operativsystem läggs till med tiden, baserat på data som har samlats från kundanvändning.</span><span class="sxs-lookup"><span data-stu-id="ca65f-132">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="ca65f-133">Därför uppmanas du att konfigurera alla nätverksenheter, även om de inte anges i den här listan.</span><span class="sxs-lookup"><span data-stu-id="ca65f-133">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="ca65f-134">Komma igång</span><span class="sxs-lookup"><span data-stu-id="ca65f-134">How to get started</span></span>

<span data-ttu-id="ca65f-135">Det första steget är att välja en enhet som ska utföra autentiserade nätverkssökningar.</span><span class="sxs-lookup"><span data-stu-id="ca65f-135">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="ca65f-136">Bestäm dig för en Defender för slutpunktsbaserad enhet (klient eller server) som har en nätverksanslutning till hanteringsporten för de nätverksenheter du planerar att skanna.</span><span class="sxs-lookup"><span data-stu-id="ca65f-136">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="ca65f-137">SNMP-trafik mellan Defender för Endpoint-utvärderingsenheten och de riktade nätverksenheterna måste tillåtas (till exempel av brandväggen).</span><span class="sxs-lookup"><span data-stu-id="ca65f-137">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="ca65f-138">Bestäm vilka nätverksenheter som ska bedömas för säkerhetsproblem (till exempel: en Cisco switch eller en Palo Firewall Networks-brandvägg).</span><span class="sxs-lookup"><span data-stu-id="ca65f-138">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="ca65f-139">Kontrollera att SNMP skrivskyddat är aktiverat på alla konfigurerade nätverksenheter så att Defender för Endpoints utvärderingsenhet kan köra frågor mot konfigurerade nätverksenheter.</span><span class="sxs-lookup"><span data-stu-id="ca65f-139">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="ca65f-140">SNMP-skrivning behövs inte för att funktionen ska fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="ca65f-140">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="ca65f-141">Hämta IP-adresserna för de nätverksenheter som ska skannas (eller undernäten där dessa enheter är distribuerade).</span><span class="sxs-lookup"><span data-stu-id="ca65f-141">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="ca65f-142">Hämta SNMP-autentiseringsuppgifter för nätverksenheterna (till exempel: Community String, noAuthNoPriv, authNoPriv, authPriv).</span><span class="sxs-lookup"><span data-stu-id="ca65f-142">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="ca65f-143">Du måste ange autentiseringsuppgifterna när du konfigurerar ett nytt bedömningsjobb.</span><span class="sxs-lookup"><span data-stu-id="ca65f-143">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="ca65f-144">Proxyklientkonfiguration: Ingen extra konfiguration krävs förutom Defender för slutpunktens proxykrav.</span><span class="sxs-lookup"><span data-stu-id="ca65f-144">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="ca65f-145">Om du vill tillåta att nätverksskannern autentiseras och fungera korrekt måste du lägga till följande domäner/URL:er:</span><span class="sxs-lookup"><span data-stu-id="ca65f-145">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="ca65f-146">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="ca65f-146">login.windows.net</span></span>  
    - <span data-ttu-id="ca65f-147">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="ca65f-147">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="ca65f-148">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ca65f-148">login.microsoftonline.com</span></span>
    - <span data-ttu-id="ca65f-149">\*.blob.core.windows.net/networkscannerstable/ \*</span><span class="sxs-lookup"><span data-stu-id="ca65f-149">\*.blob.core.windows.net/networkscannerstable/ \*</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca65f-150">Inte alla URL:er anges i Defender för Slutpunkt-dokumenterad lista över tillåtna datainsamling.</span><span class="sxs-lookup"><span data-stu-id="ca65f-150">Not all URLs are specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="ca65f-151">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="ca65f-151">Permissions</span></span>

<span data-ttu-id="ca65f-152">För att konfigurera utvärderingsjobb krävs följande användarbehörighetsalternativ: **Hantera säkerhetsinställningar i Säkerhetscenter.**</span><span class="sxs-lookup"><span data-stu-id="ca65f-152">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="ca65f-153">Du hittar behörigheten genom att gå till **Inställningar**  >  **Roller.**</span><span class="sxs-lookup"><span data-stu-id="ca65f-153">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="ca65f-154">Mer information finns i [Skapa och hantera roller för rollbaserad åtkomstkontroll.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="ca65f-154">For more information, see [Create and manage roles for role-based access control](user-roles.md).</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="ca65f-155">Installera nätverksskannern</span><span class="sxs-lookup"><span data-stu-id="ca65f-155">Install the network scanner</span></span>

1. <span data-ttu-id="ca65f-156">Gå till **Microsoft 365 säkerhetsjobb**  >  **Inställningar**  >  **Endpoints**  >  **Assessment jobs** (under **Nätverksutvärderingar).**</span><span class="sxs-lookup"><span data-stu-id="ca65f-156">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under **Network assessments**).</span></span>
    1. <span data-ttu-id="ca65f-157">I Microsoft Defender Säkerhetscenter du till sidan Inställningar > Utvärderingsjobb.</span><span class="sxs-lookup"><span data-stu-id="ca65f-157">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="ca65f-158">Ladda ned nätverksskannern och installera den på den angivna Defender för Endpoint-utvärderingsenheten.</span><span class="sxs-lookup"><span data-stu-id="ca65f-158">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca65f-159">![Knappen Ladda ned skanner](images/assessment-jobs-download-scanner.png)</span><span class="sxs-lookup"><span data-stu-id="ca65f-159">![Download scanner button](images/assessment-jobs-download-scanner.png)</span></span>

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="ca65f-160">Installation av nätverksskanner & registrering</span><span class="sxs-lookup"><span data-stu-id="ca65f-160">Network scanner installation & registration</span></span>

<span data-ttu-id="ca65f-161">Inloggningsprocessen kan slutföras på den angivna utvärderingsenheten eller någon annan enhet (till exempel din personliga klientenhet).</span><span class="sxs-lookup"><span data-stu-id="ca65f-161">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="ca65f-162">Så här slutför du registreringen av nätverksskannern:</span><span class="sxs-lookup"><span data-stu-id="ca65f-162">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="ca65f-163">Kopiera och följ URL-adressen som visas på kommandoraden och använd den angivna installationskoden för att slutföra registreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="ca65f-163">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca65f-164">Du kan behöva ändra inställningarna för kommandotolken för att kunna kopiera URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="ca65f-164">You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="ca65f-165">Ange koden och logga in med ett Microsoft-konto som har Behörigheten Defender för slutpunkt som kallas "Hantera säkerhetsinställningar i Säkerhetscenter".</span><span class="sxs-lookup"><span data-stu-id="ca65f-165">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="ca65f-166">När du är klar visas ett meddelande om att du har loggat in.</span><span class="sxs-lookup"><span data-stu-id="ca65f-166">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="ca65f-167">Konfigurera ett nytt bedömningsjobb</span><span class="sxs-lookup"><span data-stu-id="ca65f-167">Configure a new assessment job</span></span>  

<span data-ttu-id="ca65f-168">På sidan Utvärderingsjobb i **Inställningar** väljer du Lägg **till nätverksutvärderingsjobb**.</span><span class="sxs-lookup"><span data-stu-id="ca65f-168">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="ca65f-169">Följ uppprocessen för att välja nätverksenheter som ska genomsökas regelbundet och läggas till i enhetsinventeringen.</span><span class="sxs-lookup"><span data-stu-id="ca65f-169">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="ca65f-170">För att förhindra duplicering av enheter i nätverkets enhetslager ska du se till att varje IP-adress bara är konfigurerad en gång på flera utvärderingsenheter.</span><span class="sxs-lookup"><span data-stu-id="ca65f-170">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca65f-171">![Knappen Lägg till nätverksutvärderingsjobb](images/assessment-jobs-add.png)</span><span class="sxs-lookup"><span data-stu-id="ca65f-171">![Add network assessment job button](images/assessment-jobs-add.png)</span></span>

<span data-ttu-id="ca65f-172">Lägga till steg för nätverksutvärderingsjobb:</span><span class="sxs-lookup"><span data-stu-id="ca65f-172">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="ca65f-173">Välj ett namn för utvärderingsjobbet och "Utvärderingsenheten" som nätverksskannern installerades på.</span><span class="sxs-lookup"><span data-stu-id="ca65f-173">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="ca65f-174">Den här enheten utför periodiska autentiserade genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="ca65f-174">This device will perform the periodic authenticated scans.</span></span>

2. <span data-ttu-id="ca65f-175">Lägg till IP-adresser för målnätverksenheter som ska skannas (eller undernäten där de här enheterna är distribuerade).</span><span class="sxs-lookup"><span data-stu-id="ca65f-175">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 

3. <span data-ttu-id="ca65f-176">Lägg till nödvändiga SNMP-autentiseringsuppgifter för målnätverksenheterna.</span><span class="sxs-lookup"><span data-stu-id="ca65f-176">Add required SNMP credentials of the target network devices.</span></span> 

4. <span data-ttu-id="ca65f-177">Spara det konfigurerade nätverksutvärderingsjobbet för att starta den periodiska nätverkssökningen.</span><span class="sxs-lookup"><span data-stu-id="ca65f-177">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="ca65f-178">Skanna och lägg till nätverksenheter</span><span class="sxs-lookup"><span data-stu-id="ca65f-178">Scan and add network devices</span></span>

<span data-ttu-id="ca65f-179">Under installationen kan du göra en testsökning en gång för att verifiera att:</span><span class="sxs-lookup"><span data-stu-id="ca65f-179">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="ca65f-180">Det finns anslutning mellan Defender för endpoint-utvärderingsenheten och de konfigurerade målnätverksenheterna.</span><span class="sxs-lookup"><span data-stu-id="ca65f-180">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="ca65f-181">De konfigurerade SNMP-autentiseringsuppgifterna är korrekta.</span><span class="sxs-lookup"><span data-stu-id="ca65f-181">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="ca65f-182">Varje utvärderingsenhet kan ha stöd för en lyckad ip-adresssökning på upp till 1 500.</span><span class="sxs-lookup"><span data-stu-id="ca65f-182">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="ca65f-183">Om du till exempel skannar 10 olika undernät där endast 100 IP-adresser returnerar lyckade resultat kan du söka igenom 1 400 IP-ytterligare adresser från andra undernät på samma utvärderingsenhet.</span><span class="sxs-lookup"><span data-stu-id="ca65f-183">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="ca65f-184">Om det finns flera IP-adressintervall/undernät att söka igenom tar det några minuter innan testsökningsresultatet visas.</span><span class="sxs-lookup"><span data-stu-id="ca65f-184">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="ca65f-185">En testsökning är tillgänglig för upp till 1 024 adresser.</span><span class="sxs-lookup"><span data-stu-id="ca65f-185">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="ca65f-186">När resultatet visas kan du välja vilka enheter som ska ingå i den periodiska genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="ca65f-186">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="ca65f-187">Om du hoppar över genomsökningsresultaten läggs alla konfigurerade IP-adresser till i nätverksutvärderingsjobbet (oavsett enhetens svar).</span><span class="sxs-lookup"><span data-stu-id="ca65f-187">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="ca65f-188">Genomsökningsresultatet kan också exporteras.</span><span class="sxs-lookup"><span data-stu-id="ca65f-188">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="ca65f-189">Enhetsinventering</span><span class="sxs-lookup"><span data-stu-id="ca65f-189">Device inventory</span></span>

<span data-ttu-id="ca65f-190">Nyligen identifierade enheter visas under den nya fliken **Nätverksenheter** på sidan **Enhetsinventering.**</span><span class="sxs-lookup"><span data-stu-id="ca65f-190">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="ca65f-191">Det kan ta upp till två timmar efter att du har lagt till ett utvärderingsjobb tills enheterna har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="ca65f-191">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca65f-192">![Avsnittet Nätverksenheter i inventeringen av enheter](images/assessment-jobs-device-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="ca65f-192">![Network devices section in the Device inventory](images/assessment-jobs-device-inventory.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ca65f-193">Felsökning</span><span class="sxs-lookup"><span data-stu-id="ca65f-193">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="ca65f-194">Installationen av nätverksskannern misslyckades</span><span class="sxs-lookup"><span data-stu-id="ca65f-194">Network scanner installation has failed</span></span>

<span data-ttu-id="ca65f-195">Kontrollera att obligatoriska URL:er läggs till i de tillåtna domänerna i brandväggsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="ca65f-195">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="ca65f-196">Kontrollera även att proxyinställningarna är konfigurerade enligt beskrivningen i Konfigurera [enhetsproxy och internetanslutningsinställningar.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="ca65f-196">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="ca65f-197">Webbsidan Microsoft.com/devicelogin inte visas</span><span class="sxs-lookup"><span data-stu-id="ca65f-197">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="ca65f-198">Kontrollera att de obligatoriska webbadresserna läggs till i de tillåtna domänerna i brandväggen.</span><span class="sxs-lookup"><span data-stu-id="ca65f-198">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="ca65f-199">Kontrollera även att proxyinställningarna är konfigurerade enligt beskrivningen i Konfigurera [enhetsproxy och internetanslutningsinställningar.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="ca65f-199">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="ca65f-200">Nätverksenheter visas inte i enhetsinventeringen efter flera timmar</span><span class="sxs-lookup"><span data-stu-id="ca65f-200">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="ca65f-201">Genomsökningsresultatet bör uppdateras några timmar efter den första genomsökning som ägde rum efter slutförande av konfigurationen av utvärderingsjobbet.</span><span class="sxs-lookup"><span data-stu-id="ca65f-201">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="ca65f-202">Om enheter fortfarande inte visas kontrollerar du att tjänsten "MdatpNetworkScanService" körs på dina utvärderingsenheter, där du installerade nätverksskannern, och utför en "Kör genomsökning" i den relevanta utvärderingsjobbskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="ca65f-202">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="ca65f-203">Om du fortfarande inte får några resultat efter fem minuter startar du om tjänsten.</span><span class="sxs-lookup"><span data-stu-id="ca65f-203">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="ca65f-204">Enheter som senast såg tiden är längre än 24 timmar</span><span class="sxs-lookup"><span data-stu-id="ca65f-204">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="ca65f-205">Kontrollera att skannern körs korrekt.</span><span class="sxs-lookup"><span data-stu-id="ca65f-205">Validate that the scanner is running properly.</span></span> <span data-ttu-id="ca65f-206">Gå sedan till genomsökningsdefinitionen och välj "Kör test".</span><span class="sxs-lookup"><span data-stu-id="ca65f-206">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="ca65f-207">Kontrollera vilka felmeddelanden som skickas tillbaka från relevanta IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="ca65f-207">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="ca65f-208">Obligatorisk Hantering av hot och säkerhetsrisker användarbehörighet</span><span class="sxs-lookup"><span data-stu-id="ca65f-208">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="ca65f-209">Registreringen har slutförts med ett fel: "Det verkar som att du inte har tillräcklig behörighet för att lägga till en ny agent.</span><span class="sxs-lookup"><span data-stu-id="ca65f-209">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="ca65f-210">Den behörighet som krävs är "Hantera säkerhetsinställningar i Säkerhetscenter".</span><span class="sxs-lookup"><span data-stu-id="ca65f-210">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="ca65f-211">Tryck på valfri tangent för att avsluta.</span><span class="sxs-lookup"><span data-stu-id="ca65f-211">Press any key to exit.</span></span>

<span data-ttu-id="ca65f-212">Be systemadministratören att tilldela dig de behörigheter som krävs.</span><span class="sxs-lookup"><span data-stu-id="ca65f-212">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="ca65f-213">Alternativt kan du be en annan relevant medlem att hjälpa dig med inloggningsprocessen genom att ange inloggningskoden och länken till honom/henne.</span><span class="sxs-lookup"><span data-stu-id="ca65f-213">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="ca65f-214">Registreringsprocessen misslyckas med den angivna länken i kommandoraden i registreringsprocessen</span><span class="sxs-lookup"><span data-stu-id="ca65f-214">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="ca65f-215">Prova en annan webbläsare eller kopiera inloggningslänken och koden till en annan enhet.</span><span class="sxs-lookup"><span data-stu-id="ca65f-215">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="ca65f-216">Texten är för liten eller det går inte att kopiera text från kommandoraden</span><span class="sxs-lookup"><span data-stu-id="ca65f-216">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="ca65f-217">Ändra kommandoradsinställningar på enheten så att textstorleken tillåts och ändras.</span><span class="sxs-lookup"><span data-stu-id="ca65f-217">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ca65f-218">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="ca65f-218">Related articles</span></span>

- [<span data-ttu-id="ca65f-219">Enhetsinventering</span><span class="sxs-lookup"><span data-stu-id="ca65f-219">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="ca65f-220">Konfigurera avancerade funktioner</span><span class="sxs-lookup"><span data-stu-id="ca65f-220">Configure advanced features</span></span>](advanced-features.md)
