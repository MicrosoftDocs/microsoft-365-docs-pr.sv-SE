---
title: Rapportering av värdbrandvägg i Microsoft Defender för Endpoint
description: Vara värd för och visa brandväggsrapportering Microsoft 365 säkerhetscenter.
keywords: windows defender, brandvägg
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809342"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="6524f-104">Rapportering av värdbrandvägg i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6524f-104">Host firewall reporting in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6524f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6524f-105">**Applies to:**</span></span>
- [<span data-ttu-id="6524f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6524f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6524f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6524f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="6524f-108">Om du är administratör kan du nu hantera brandväggsrapportering till [Microsoft 365 säkerhetscenter.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="6524f-108">If you are an admin, you can now host firewall reporting to [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="6524f-109">Med den här funktionen kan du visa Windows 10 och Windows för Server 2019-brandväggen från en central plats.</span><span class="sxs-lookup"><span data-stu-id="6524f-109">This feature enables you to view Windows 10 and Windows Server 2019 firewall reporting from a centralized location.</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6524f-110">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="6524f-110">What do you need to know before you begin?</span></span> 

- <span data-ttu-id="6524f-111">Du måste köra Windows 10 eller Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6524f-111">You must be running Windows 10 or Windows Server 2019.</span></span>
- <span data-ttu-id="6524f-112">Information om hur du onboardar enheter till Microsoft Defender för slutpunktstjänsten finns [här](onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="6524f-112">To onboard devices to the Microsoft Defender for Endpoint service, see [here](onboard-configure.md).</span></span> 
- <span data-ttu-id="6524f-113">Om Microsoft 365 säkerhetscenter ska börja ta emot data måste du aktivera **granskningshändelser för** Windows Defender-brandväggen med avancerad säkerhet:</span><span class="sxs-lookup"><span data-stu-id="6524f-113">For Microsoft 365 security center to start receiving the data, you must enable **Audit Events** for Windows Defender Firewall with Advanced Security:</span></span> 
    - [<span data-ttu-id="6524f-114">Granskningsfiltrering av plattform för släpp</span><span class="sxs-lookup"><span data-stu-id="6524f-114">Audit Filtering Platform Packet Drop</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [<span data-ttu-id="6524f-115">Anslutning till granskningsfiltreringsplattform</span><span class="sxs-lookup"><span data-stu-id="6524f-115">Audit Filtering Platform Connection</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- <span data-ttu-id="6524f-116">Aktivera dessa händelser med hjälp av Grupprincipobjektredigeraren, Lokal säkerhetsprincip eller auditpol.exe säkerhetskommandon.</span><span class="sxs-lookup"><span data-stu-id="6524f-116">Enable these events by using Group Policy Object Editor, Local Security Policy, or the auditpol.exe commands.</span></span> <span data-ttu-id="6524f-117">Mer information finns i [här](/windows/win32/fwp/auditing-and-logging).</span><span class="sxs-lookup"><span data-stu-id="6524f-117">For more information, see [here](/windows/win32/fwp/auditing-and-logging).</span></span> 
    - <span data-ttu-id="6524f-118">De två PowerShell-kommandona är:</span><span class="sxs-lookup"><span data-stu-id="6524f-118">The two PowerShell commands are:</span></span>
        - <span data-ttu-id="6524f-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="6524f-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span></span> 
        - <span data-ttu-id="6524f-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="6524f-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span></span> 

## <a name="the-process"></a><span data-ttu-id="6524f-121">Processen</span><span class="sxs-lookup"><span data-stu-id="6524f-121">The process</span></span>
> [!NOTE]
> <span data-ttu-id="6524f-122">Se till att följa anvisningarna i avsnittet ovan och konfigurera dina enheter på rätt sätt inför förhandsdeltagandet.</span><span class="sxs-lookup"><span data-stu-id="6524f-122">Make sure to follow the instructions from the section above and properly configure your devices for the early preview participation.</span></span>

- <span data-ttu-id="6524f-123">När du har Microsoft 365 säkerhetscentret övervaka data.</span><span class="sxs-lookup"><span data-stu-id="6524f-123">After enabling the events, Microsoft 365 security center will start to monitor the data.</span></span>
    - <span data-ttu-id="6524f-124">Fjärr-IP, fjärrport, lokal port, lokal IP, datornamn, process för inkommande och utgående anslutningar.</span><span class="sxs-lookup"><span data-stu-id="6524f-124">Remote IP, Remote Port, Local Port, Local IP, Computer Name, Process across inbound and outbound connections.</span></span>
- <span data-ttu-id="6524f-125">Administratörer kan nu se Windows aktiviteten för värdbrandväggen [här](https://security.microsoft.com/firewall).</span><span class="sxs-lookup"><span data-stu-id="6524f-125">Admins can now see Windows host firewall activity [here](https://security.microsoft.com/firewall).</span></span>
    - <span data-ttu-id="6524f-126">Ytterligare rapportering kan underlättas genom att hämta skriptet [Anpassad](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) rapportering för att övervaka de Windows Defender-brandväggen som använder Power BI.</span><span class="sxs-lookup"><span data-stu-id="6524f-126">Additional reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 
    - <span data-ttu-id="6524f-127">Det kan ta upp till 12 timmar innan data visas.</span><span class="sxs-lookup"><span data-stu-id="6524f-127">It can take up to 12 hours before the data is reflected.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="6524f-128">Scenarier som stöds</span><span class="sxs-lookup"><span data-stu-id="6524f-128">Supported scenarios</span></span>
<span data-ttu-id="6524f-129">Följande scenarier stöds under förhandsversionen av Ring0.</span><span class="sxs-lookup"><span data-stu-id="6524f-129">The following scenarios are supported during Ring0 Preview.</span></span> 

### <a name="firewall-reporting-in-security-center"></a><span data-ttu-id="6524f-130">Brandväggsrapportering i säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="6524f-130">Firewall reporting in security center</span></span>

<span data-ttu-id="6524f-131">Här är några exempel på brandväggsrapportsidorna.</span><span class="sxs-lookup"><span data-stu-id="6524f-131">Here is a couple of examples of the firewall report pages.</span></span> <span data-ttu-id="6524f-132">Här hittar du en sammanfattning av inkommande, utgående och programaktivitet.</span><span class="sxs-lookup"><span data-stu-id="6524f-132">Here you will find a summary of inbound, outbound, and application activity.</span></span> <span data-ttu-id="6524f-133">Du kan komma åt den här sidan direkt genom att gå till https://security.microsoft.com/firewall .</span><span class="sxs-lookup"><span data-stu-id="6524f-133">You can access this page directly by going to https://security.microsoft.com/firewall.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6524f-134">![Rapportsida för värdbrandvägg](\images\host-firewall-reporting-page.png)</span><span class="sxs-lookup"><span data-stu-id="6524f-134">![Host firewall reporting page](\images\host-firewall-reporting-page.png)</span></span>

<span data-ttu-id="6524f-135">Du kommer åt de här rapporterna genom att gå till **Reports** Security Report Devices (avsnitt) längst ned på kortet  >    >   **Firewall Blocked Inbound Connections.**</span><span class="sxs-lookup"><span data-stu-id="6524f-135">These reports can also be accessed by going to **Reports** > **Security Report** > **Devices** (section) located at the bottom of the **Firewall Blocked Inbound Connections** card.</span></span>

### <a name="from-computers-with-a-blocked-connection-to-device"></a><span data-ttu-id="6524f-136">Från "Datorer med en blockerad anslutning" till en enhet</span><span class="sxs-lookup"><span data-stu-id="6524f-136">From "Computers with a blocked connection" to device</span></span>

<span data-ttu-id="6524f-137">Kort stöder interaktiva objekt.</span><span class="sxs-lookup"><span data-stu-id="6524f-137">Cards support interactive objects.</span></span> <span data-ttu-id="6524f-138">Du kan granska aktiviteten på en enhet genom att klicka på enhetens namn, som startas på en ny flik, och ta dig direkt https://securitycenter.microsoft.com till fliken Tidslinje **på** enheten.</span><span class="sxs-lookup"><span data-stu-id="6524f-138">You can drill into the activity of a device by clicking on the device name, which will launch https://securitycenter.microsoft.com in a new tab, and take you directly to the **Device Timeline** tab.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6524f-139">![Datorer med blockerad anslutning](\images\firewall-reporting-blocked-connection.png)</span><span class="sxs-lookup"><span data-stu-id="6524f-139">![Computers with a blocked connection](\images\firewall-reporting-blocked-connection.png)</span></span>

<span data-ttu-id="6524f-140">Nu kan du välja fliken **Tidslinje,** som ger dig en lista över händelser som är kopplade till den enheten.</span><span class="sxs-lookup"><span data-stu-id="6524f-140">You can now select the **Timeline** tab, which will give you a list of events associated with that device.</span></span> 

<span data-ttu-id="6524f-141">När du har **klickat på** knappen Filter i det övre högra hörnet i visningsfönstret väljer du den typ av händelse som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="6524f-141">After clicking on the **Filters** button on the upper right-hand corner of the viewing pane, select the type of event you want.</span></span> <span data-ttu-id="6524f-142">I det här fallet väljer **du Brandväggshändelser** så filtreras fönstret till brandväggshändelser.</span><span class="sxs-lookup"><span data-stu-id="6524f-142">In this case, select **Firewall events** and the pane will be filtered to Firewall events.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6524f-143">![Knappen Filter](\images\firewall-reporting-filters-button.png)</span><span class="sxs-lookup"><span data-stu-id="6524f-143">![Filters button](\images\firewall-reporting-filters-button.png)</span></span>

### <a name="drill-into-advanced-hunting-preview-refresh"></a><span data-ttu-id="6524f-144">Öka detalj detalj för avancerad sökning (uppdatera förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="6524f-144">Drill into advanced hunting (preview refresh)</span></span>

<span data-ttu-id="6524f-145">Med brandväggsrapporter går det att göra en sökning från kortet direkt **till Avancerad sökning** genom att klicka på knappen Öppna **avancerad** sökning.</span><span class="sxs-lookup"><span data-stu-id="6524f-145">Firewall reports support drilling from the card directly into **Advanced Hunting** by clicking the **Open Advanced hunting** button.</span></span> <span data-ttu-id="6524f-146">Frågan fylls i på förhand.</span><span class="sxs-lookup"><span data-stu-id="6524f-146">The query will be pre-populated.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6524f-147">![Knappen Öppna avancerad sökning](\images\firewall-reporting-advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="6524f-147">![Open Advanced hunting button](\images\firewall-reporting-advanced-hunting.png)</span></span>

<span data-ttu-id="6524f-148">Frågan kan nu utföras och alla relaterade brandväggshändelser från de senaste 30 dagarna kan undersökas.</span><span class="sxs-lookup"><span data-stu-id="6524f-148">The query can now be executed, and all related Firewall events from the last 30 days can be explored.</span></span> 

<span data-ttu-id="6524f-149">För ytterligare rapportering eller anpassade ändringar kan frågan exporteras till ett Power BI för vidare analys.</span><span class="sxs-lookup"><span data-stu-id="6524f-149">For additional reporting, or custom changes, the query can be exported into Power BI for further analysis.</span></span> <span data-ttu-id="6524f-150">Anpassad rapportering kan underlättas genom att hämta skriptet [Anpassad](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) rapportering för att övervaka de Windows Defender-brandväggen som använder Power BI.</span><span class="sxs-lookup"><span data-stu-id="6524f-150">Custom reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 

 