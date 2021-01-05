---
title: Microsoft 365-välinformerad nätverks dirigering
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365-välinformerad nätverks dirigering
ms.openlocfilehash: 367f83684a4a200e3ddd630e1412c756d7093da1
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749557"
---
# <a name="microsoft-365-informed-network-routing-preview"></a><span data-ttu-id="fe06d-103">Microsoft 365-välinformerad nätverks dirigering (för hands version)</span><span class="sxs-lookup"><span data-stu-id="fe06d-103">Microsoft 365 informed network routing (preview)</span></span>

<span data-ttu-id="fe06d-104">Underordnad nätverks dirigering är en funktion som integrerar olika Microsoft 365-program med tredjeparts-specifika (SD-WAN) lösningar för att optimera och förbättra nätverks anslutningen till Microsofts tjänst slut punkter.</span><span class="sxs-lookup"><span data-stu-id="fe06d-104">Informed network routing is a feature that integrates various Microsoft 365 applications with third party software defined network (SD-WAN) solutions in order to optimize and improve your network connectivity to Microsoft service endpoints.</span></span> <span data-ttu-id="fe06d-105">Optimerad SD-WAN-anslutning kan leda till förbättrad användar upplevelse och prestanda.</span><span class="sxs-lookup"><span data-stu-id="fe06d-105">Optimized SD-WAN connectivity may result in improved user experiences and performance.</span></span>

>[!IMPORTANT]
><span data-ttu-id="fe06d-106">Microsoft 365 informerat nätverks dirigering är för närvarande i förhands granskning.</span><span class="sxs-lookup"><span data-stu-id="fe06d-106">Microsoft 365 informed network routing is currently in preview status.</span></span> <span data-ttu-id="fe06d-107">Mer information om den här förhands granskningen inklusive vägledning för att få hjälp kan du läsa i [Microsoft 365 informerad nätverks dirigering](https://go.microsoft.com/fwlink/?linkid=2151565).</span><span class="sxs-lookup"><span data-stu-id="fe06d-107">For more information on this preview including guidance for receiving assistance, see [Microsoft 365 informed network routing Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).</span></span>

## <a name="overview"></a><span data-ttu-id="fe06d-108">Översikt</span><span class="sxs-lookup"><span data-stu-id="fe06d-108">Overview</span></span>

<span data-ttu-id="fe06d-109">Informerad nätverks dirigering tillhandahåller en dubbelriktad data delnings kanal mellan Microsoft och din SD-WAN-lösning.</span><span class="sxs-lookup"><span data-stu-id="fe06d-109">Informed network routing provides a bi-directional data sharing channel between Microsoft and your SD-WAN solution.</span></span> <span data-ttu-id="fe06d-110">För varje Office-plats och Internet-krets som du konfigurerar kan Microsoft regelbundet dela med dig av feedback med SD-WAN-lösningen på den valda Microsoft 365-program upplevelsen för nätverks trafik som är kopplad till varje specifik Internet krets.</span><span class="sxs-lookup"><span data-stu-id="fe06d-110">For every office location and Internet circuit that you configure, Microsoft periodically shares feedback with the SD-WAN solution on the quality of selected Microsoft 365 application experiences for network traffic associated with each specific Internet circuit.</span></span> <span data-ttu-id="fe06d-111">Genom att använda denna feedback kan du då och då vidta åtgärder för Smart återställning genom att routning Microsoft 365 program trafik via alternativa tillgängliga länkar.</span><span class="sxs-lookup"><span data-stu-id="fe06d-111">Using this feedback, the SD-WAN solution may then take smart recovery actions by routing Microsoft 365 application traffic through alternate available links.</span></span> 

<span data-ttu-id="fe06d-112">Kvaliteten på tjänstens försämring av sökvägen till en viss Internet krets såsom ökad svars tid eller hög paket förlust är svår att upptäcka fort löp ande.</span><span class="sxs-lookup"><span data-stu-id="fe06d-112">Quality of service degradations in the path of a particular Internet circuit such as increased latency or high packet loss are difficult to detect on a continuous basis.</span></span> <span data-ttu-id="fe06d-113">Dessa försämringar kan skada användar upplevelsen för program som Exchange Online, SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fe06d-113">These degradations may be detrimental to user experiences for applications such as Exchange Online, SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="fe06d-114">Vanliga symptom är en långsam sökning av Exchange-innehåll, höga överförings tider när det interagerar med SharePoint-eller OneDrive-dokumentbibliotek eller dålig ljud kvalitet i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fe06d-114">Common symptoms include slow search of Exchange content, high transfer times when interacting with SharePoint or OneDrive document libraries, or poor call or meeting quality in Microsoft Teams.</span></span>

<span data-ttu-id="fe06d-115">Med funktionen för feedback och återställning i nätverk med välinformerad routning kan du upptäcka sådana problem dynamiskt i nära real tid och informera den distribuerade SD-WAN-lösningen för att utföra automatiska återställnings åtgärder.</span><span class="sxs-lookup"><span data-stu-id="fe06d-115">The feedback and recovery mechanism within network informed routing seeks to dynamically detect such issues in near real time and informs the deployed SD-WAN solution to take automatic recovery actions.</span></span>

<span data-ttu-id="fe06d-116">Data delnings kanalen används också för att regelbundet få optisk data trafik från SD-WAN-lösningen, inklusive konfigurations information och användnings statistik som är kopplad till enheten och anslutna kretsar.</span><span class="sxs-lookup"><span data-stu-id="fe06d-116">The data sharing channel is also used to periodically receive network-level optics data from the SD-WAN solution, including configuration information and usage statistics associated with the device and attached circuits.</span></span> <span data-ttu-id="fe06d-117">Ingen personlig information samlas in eller lagras.</span><span class="sxs-lookup"><span data-stu-id="fe06d-117">No personal information is collected or stored.</span></span> <span data-ttu-id="fe06d-118">Alla insamlade uppgifter aggregeras till Office-platser och anslutna Internet kretsar.</span><span class="sxs-lookup"><span data-stu-id="fe06d-118">All collected information is aggregated to office locations and connected Internet circuits.</span></span> <span data-ttu-id="fe06d-119">Den här informationen kan hjälpa Microsoft att effektivt lösa rapporterade problem med användning av Microsoft 365-tjänster och-program.</span><span class="sxs-lookup"><span data-stu-id="fe06d-119">This information can help Microsoft more efficiently and effectively resolve reported issues with your use of Microsoft 365 services and applications.</span></span>

>[!NOTE]
><span data-ttu-id="fe06d-120">Microsoft 365 informerat nätverks dirigering stöder klient organisationer i WW kommersiellt moln men inte GCC medel för måttliga, GCC hög, DoD, Tyskland och Kina.</span><span class="sxs-lookup"><span data-stu-id="fe06d-120">Microsoft 365 informed network routing supports tenants in WW Commercial cloud but not the GCC Moderate, GCC High, DoD, Germany, or China clouds.</span></span>

## <a name="requirements"></a><span data-ttu-id="fe06d-121">Krav</span><span class="sxs-lookup"><span data-stu-id="fe06d-121">Requirements</span></span>

### <a name="integrated-sd-wan-solutions"></a><span data-ttu-id="fe06d-122">Integrerade SD-WAN-lösningar</span><span class="sxs-lookup"><span data-stu-id="fe06d-122">Integrated SD-WAN solutions</span></span>

<span data-ttu-id="fe06d-123">Microsoft samarbetar med olika partners för att möjliggöra integrering med Microsoft 365-välinformerade nätverks dirigering.</span><span class="sxs-lookup"><span data-stu-id="fe06d-123">Microsoft is working with various partners to enable integration with Microsoft 365 informed network routing.</span></span> <span data-ttu-id="fe06d-124">För närvarande aktiverade lösningar:</span><span class="sxs-lookup"><span data-stu-id="fe06d-124">Currently enabled solutions include the following:</span></span>

| <span data-ttu-id="fe06d-125">Enhets tillverkare</span><span class="sxs-lookup"><span data-stu-id="fe06d-125">Device Maker</span></span> | <span data-ttu-id="fe06d-126">Lösningens namn</span><span class="sxs-lookup"><span data-stu-id="fe06d-126">Solution Name</span></span> | <span data-ttu-id="fe06d-127">Minsta version</span><span class="sxs-lookup"><span data-stu-id="fe06d-127">Minimum Version</span></span> |
| --- | --- | --- |
| <span data-ttu-id="fe06d-128">Cisco</span><span class="sxs-lookup"><span data-stu-id="fe06d-128">Cisco</span></span> | [<span data-ttu-id="fe06d-129">IOS-XO SD – WAN</span><span class="sxs-lookup"><span data-stu-id="fe06d-129">IOS XE SD-WAN</span></span>](https://go.microsoft.com/fwlink/?linkid=2151460) | <span data-ttu-id="fe06d-130">20.4/17.4</span><span class="sxs-lookup"><span data-stu-id="fe06d-130">20.4/17.4</span></span> |

### <a name="network-topology"></a><span data-ttu-id="fe06d-131">Nätverkstopologi</span><span class="sxs-lookup"><span data-stu-id="fe06d-131">Network topology</span></span>

<span data-ttu-id="fe06d-132">Med Inlämnad nätverks dirigering identifieras trafik som är kopplad till en viss plats och Internet-kretsen baserat på den offentliga IP-adressen som används för att skicka nätverks trafik till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fe06d-132">Informed network routing currently identifies traffic associated with a specific office location and Internet circuit based on the public IP address used to send network traffic to Microsoft.</span></span> 

<span data-ttu-id="fe06d-133">Om det inte finns minst en nätverks krets som ger direkt Internet åtkomst på en filial plats kanske inte nätverkets informerade routning ger signifikanta priser.</span><span class="sxs-lookup"><span data-stu-id="fe06d-133">In the case where there is not at least one network circuit providing direct Internet access at a branch location, network informed routing may not provide significant value.</span></span>

### <a name="application-usage"></a><span data-ttu-id="fe06d-134">Program användning</span><span class="sxs-lookup"><span data-stu-id="fe06d-134">Application usage</span></span>

<span data-ttu-id="fe06d-135">Program miljö data samlas in genom användning av Microsoft Outlook på enheter med Windows, teams, SharePoint och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="fe06d-135">Application experience data (reflected through network quality metrics) is collected through usage of Microsoft Outlook on devices running Windows, Teams, SharePoint, and OneDrive.</span></span> <span data-ttu-id="fe06d-136">Annan program trafik beaktas inte vid utvärdering av hälso tillståndet hos en nätverks krets.</span><span class="sxs-lookup"><span data-stu-id="fe06d-136">Other application traffic is not considered when evaluating the health of a network circuit.</span></span>

## <a name="enabling-informed-network-routing"></a><span data-ttu-id="fe06d-137">Aktivera välinformerad nätverks dirigering</span><span class="sxs-lookup"><span data-stu-id="fe06d-137">Enabling informed network routing</span></span>

<span data-ttu-id="fe06d-138">För att aktivera informerad nätverks dirigering krävs flera steg som måste utföras i konfigurations gränssnittet för din SD-WAN-lösning.</span><span class="sxs-lookup"><span data-stu-id="fe06d-138">Enabling informed network routing requires multiple steps, some of which will need to be performed within the configuration interface of your SD-WAN solution.</span></span> <span data-ttu-id="fe06d-139">Läs mer om hur du kan använda din lösning för att aktivera nätverk med välinformerad routning i SD-WAN-lösningen innan du fortsätter med konfigurationen i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fe06d-139">Consult your SD-WAN solution vendor for guidance on how to initiate the process of enabling network informed routing within the SD-WAN solution before proceeding with configuration in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="fe06d-140">När du är redo att aktivera välinformerad nätverks dirigering i Microsoft 365 Admin Center kontrollerar du att du har nödvändig global administratörs behörighet.</span><span class="sxs-lookup"><span data-stu-id="fe06d-140">Once you are ready to enable informed network routing in the Microsoft 365 admin center, ensure you have the necessary global administrator permissions.</span></span>

>[!IMPORTANT]
><span data-ttu-id="fe06d-141">För att kunna tillhandahålla de behörigheter som krävs för den valda SD-WAN-lösningen för att få åtkomst till den välgrundade data delnings kanalen för nätverks dirigering måste du utföra följande steg som global administratör.</span><span class="sxs-lookup"><span data-stu-id="fe06d-141">In order to provide the necessary tenant-level applications permissions consent for the selected SD-WAN solution to access the informed network routing data sharing channel, you must perform the following steps as a global administrator.</span></span>


### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="fe06d-142">Steg 1: öppna konfigurations alternativ för SD-WAN-lösning</span><span class="sxs-lookup"><span data-stu-id="fe06d-142">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="fe06d-143">I [administrations centret för Microsoft 365](https://admin.microsoft.com/)väljer du **Health > nätverks anslutning** i det vänstra navigerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="fe06d-143">In the [Microsoft 365 admin center](https://admin.microsoft.com/), select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="fe06d-144">Den här delen av administrations centret tillhandahåller sammansatta nätverks anslutnings mått för din organisation och vägledning om hur du kan förbättra anslutningen.</span><span class="sxs-lookup"><span data-stu-id="fe06d-144">This section of the admin center provides aggregated network connectivity metrics for your organization and guidance on how to improve your connectivity.</span></span> <span data-ttu-id="fe06d-145">Se [nätverks anslutningar i Microsoft 365 Admin Center (för hands version)](office-365-network-mac-perf-overview.md) om du vill ha mer information om de här funktionerna i administrations centret.</span><span class="sxs-lookup"><span data-stu-id="fe06d-145">See [Network connectivity in the Microsoft 365 Admin Center (preview)](office-365-network-mac-perf-overview.md) for additional information on these features available within the admin center.</span></span>

<span data-ttu-id="fe06d-146">Välj **inställningar > SD-WAN-lösning** för att öppna den informerade konfigurations fönstret för nätverks dirigering.</span><span class="sxs-lookup"><span data-stu-id="fe06d-146">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span> <span data-ttu-id="fe06d-147">De andra alternativen som visas under **Inställningar** är tillämpliga för nätverks anslutnings vägledningen i administrations centret och är inte nödvändigt för att aktivera inskriven nätverks dirigering.</span><span class="sxs-lookup"><span data-stu-id="fe06d-147">The other options that appear under **Settings** are applicable to the general network connectivity guidance in the admin center and are not required to enable informed network routing.</span></span>

<span data-ttu-id="fe06d-148">I fönstret konfiguration väljer **du Lägg till din SD-WAN-lösning (för hands version)**.</span><span class="sxs-lookup"><span data-stu-id="fe06d-148">In the configuration pane, select **Add your SD-WAN solution (Preview)**.</span></span>

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a><span data-ttu-id="fe06d-149">Steg 2: Välj din SD-WAN-lösning och data lagrings plats</span><span class="sxs-lookup"><span data-stu-id="fe06d-149">Step 2: Select your SD-WAN solution and data storage location</span></span>

<span data-ttu-id="fe06d-150">I list rutorna väljer du den SD-WAN-lösning som du har distribuerat och den plats där du vill ha de data som är kopplade till nätverksansluten routning.</span><span class="sxs-lookup"><span data-stu-id="fe06d-150">In the drop-down boxes, select the SD-WAN solution you have deployed and the location where you wish to have the data associated with network informed routing stored.</span></span> <span data-ttu-id="fe06d-151">Mer information finns i avsnittet [data lagring](#data-storage) .</span><span class="sxs-lookup"><span data-stu-id="fe06d-151">See the [data storage](#data-storage) section for additional information.</span></span>

<span data-ttu-id="fe06d-152">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fe06d-152">Select **Next**.</span></span>

### <a name="step-3-accept-terms-for-sharing-of-data"></a><span data-ttu-id="fe06d-153">Steg 3: acceptera villkor för att dela data</span><span class="sxs-lookup"><span data-stu-id="fe06d-153">Step 3: Accept terms for sharing of data</span></span>

<span data-ttu-id="fe06d-154">Läs och bekräfta noggrant de angivna villkoren för att dela data mellan Microsoft och din valda SD-WAN-lösning och markera sedan kryss rutan.</span><span class="sxs-lookup"><span data-stu-id="fe06d-154">Carefully read and acknowledge the provided terms associated with sharing data between Microsoft and your selected SD-WAN solution, and then select the indicated checkbox.</span></span>

<span data-ttu-id="fe06d-155">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fe06d-155">Select **Next**.</span></span>

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a><span data-ttu-id="fe06d-156">Steg 4: bevilja behörigheter för SD-WAN-lösningen</span><span class="sxs-lookup"><span data-stu-id="fe06d-156">Step 4: Grant permissions to the SD-WAN solution</span></span>

<span data-ttu-id="fe06d-157">I det här steget initieras en begäran om behörighet med Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="fe06d-157">This step will initiate a permissions grant request with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="fe06d-158">Du kommer att tillfrågas om behörigheter på klient organisations nivå som tillåter att din valda SD-WAN-lösning får till gång till det underbyggda nätverks lagrings utrymmet och tjänst hälso informationen som är associerad med din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="fe06d-158">You will be requested to grant tenant-level permissions that allow your selected SD-WAN solution access to the informed network routing data storage and the service health information associated with your tenant.</span></span> <span data-ttu-id="fe06d-159">Den här åtgärden kräver globala administratörs behörigheter.</span><span class="sxs-lookup"><span data-stu-id="fe06d-159">This action requires global administrator role permissions.</span></span>

<span data-ttu-id="fe06d-160">Välj länken **ge behörighet till det här programmet** och följ Azure AD-begäranden.</span><span class="sxs-lookup"><span data-stu-id="fe06d-160">Select the **Give permission to this application** link and follow the Azure AD requests.</span></span>

<span data-ttu-id="fe06d-161">När du har slutfört behörighets tilldelningen väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fe06d-161">Once you have completed the permissions grant, select **Next**.</span></span>

### <a name="step-5-confirm-your-configuration-settings"></a><span data-ttu-id="fe06d-162">Steg 5: bekräfta dina konfigurations inställningar</span><span class="sxs-lookup"><span data-stu-id="fe06d-162">Step 5: Confirm your configuration settings</span></span>

<span data-ttu-id="fe06d-163">Det sista steget i att aktivera nätverkets informerade routning för din klient organisation är en bekräftelse sida som visar de inställningar du har angett.</span><span class="sxs-lookup"><span data-stu-id="fe06d-163">The final step in enabling network informed routing for your tenant is a confirmation page that displays the settings you've provided.</span></span> 

<span data-ttu-id="fe06d-164">Uppdelad nätverks dirigering är nu aktive rad för din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="fe06d-164">Informed network routing is now enabled for your tenant.</span></span>

<span data-ttu-id="fe06d-165">Välj **klar** och stäng sedan konfigurations fönstret för SD-WAN-lösning.</span><span class="sxs-lookup"><span data-stu-id="fe06d-165">Select **Done** and then close the SD-WAN solution configuration pane.</span></span>

## <a name="configuring-network-informed-routing"></a><span data-ttu-id="fe06d-166">Konfigurera nätverksansluten routning</span><span class="sxs-lookup"><span data-stu-id="fe06d-166">Configuring network informed routing</span></span>

<span data-ttu-id="fe06d-167">Du kommer att utföra en mycket av konfigurationen för välinformerad nätverks dirigering i din SD-WAN-lösning, till exempel hur du konfigurerar hur din trafik ska routas under normala omständigheter och vilka alternativa sökvägar som ska användas om problem upptäcks.</span><span class="sxs-lookup"><span data-stu-id="fe06d-167">You will perform much of the configuration for informed network routing within your SD-WAN solution, such as configuring how your traffic should be routed under normal circumstances and the alternate paths that should be used if issues are detected.</span></span> <span data-ttu-id="fe06d-168">Mer information om de här konfigurations stegen finns i leverantören för SD-WAN-lösning.</span><span class="sxs-lookup"><span data-stu-id="fe06d-168">Consult your SD-WAN solution provider for details on these configuration steps.</span></span>

<span data-ttu-id="fe06d-169">Varje Office-plats måste konfigureras i Microsoft 365 Admin Center så att inringda nätverks dirigeringar kan identifiera trafik som är kopplad till de nätverks kretsar som ger anslutning till dessa platser.</span><span class="sxs-lookup"><span data-stu-id="fe06d-169">Each office location must be configured in the Microsoft 365 admin center so that informed network routing can properly identify traffic associated with the network circuits providing connectivity to these locations.</span></span>

<span data-ttu-id="fe06d-170">Office-platser kan identifieras automatiskt som en del av Microsofts löpande samling av Nätverksdiagnostik.</span><span class="sxs-lookup"><span data-stu-id="fe06d-170">Office locations may be auto-detected as part of Microsoft's ongoing collection of network telemetry.</span></span> <span data-ttu-id="fe06d-171">Därför kan vissa platser vara ifyllda i administrations centret för din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="fe06d-171">As a result, some locations may be pre-populated in the admin center for your tenant.</span></span> 

<span data-ttu-id="fe06d-172">Om dessa platser är korrekta behöver du bara aktivera den informerade nätverks Dirigerings funktionen för varje plats och konfigurera Internet kretsar och deras offentliga IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="fe06d-172">If these locations are accurate, you will simply need to enable the informed network routing feature for each desired location and configure the Internet circuits and their public IP addresses.</span></span> 

<span data-ttu-id="fe06d-173">Om de automatiskt upptäckta platserna inte är korrekta, eller om det inte finns någon plats ifyllt i klient organisationen, måste du lägga till eller redigera platserna manuellt för att visa en korrekt topologi i organisationen.</span><span class="sxs-lookup"><span data-stu-id="fe06d-173">If the auto-detected locations are not accurate, or there are no locations pre-populated in your tenant, you will have to add or edit locations manually to reflect an accurate topology of your organization.</span></span>

### <a name="updating-locations"></a><span data-ttu-id="fe06d-174">Uppdatera platser</span><span class="sxs-lookup"><span data-stu-id="fe06d-174">Updating locations</span></span>

<span data-ttu-id="fe06d-175">Platser för klient organisationen finns på fliken **platser** . Platser kan redige ras direkt i listan eller uppdateras med en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="fe06d-175">Locations for your tenant can be found under the **Locations** tab. Locations may be edited directly in the list or updated using a CSV file.</span></span>

<span data-ttu-id="fe06d-176">Kontrol lera att varje Office-plats där du vill aktivera välinformerad nätverks dirigering finns i den här listan.</span><span class="sxs-lookup"><span data-stu-id="fe06d-176">Ensure that each office location where you wish to enable informed network routing is present in this list.</span></span>

>[!NOTE]
><span data-ttu-id="fe06d-177">Kolumnerna i **plats** listan för insamlade och andra utvärderings uppgifter är inte relaterade till den informerade nätverks dirigeringen.</span><span class="sxs-lookup"><span data-stu-id="fe06d-177">The columns in the **Locations** list for samples collected and other assessment-related information are not related to the informed network routing feature.</span></span>

### <a name="enabling-a-location-for-informed-network-routing"></a><span data-ttu-id="fe06d-178">Aktivera en plats för välinformerad nätverks dirigering</span><span class="sxs-lookup"><span data-stu-id="fe06d-178">Enabling a location for informed network routing</span></span>

1. <span data-ttu-id="fe06d-179">I listan **platser** väljer du **Redigera** från menyn snabb åtgärder för att öppna fönstret plats konfiguration.</span><span class="sxs-lookup"><span data-stu-id="fe06d-179">In the **Locations** list, select **Edit** from the quick actions menu to open the location configuration pane.</span></span>

2. <span data-ttu-id="fe06d-180">Välj **Använd Microsoft 365-välinformerad nätverks dirigering på den här platsen**.</span><span class="sxs-lookup"><span data-stu-id="fe06d-180">Select **Use Microsoft 365 informed network routing at this location**.</span></span>

3. <span data-ttu-id="fe06d-181">Lägg till alla nätverks kretsar som ger Internet anslutningen till den här platsen i det **här avsnittet IP-adressintervall på den här platsen** .</span><span class="sxs-lookup"><span data-stu-id="fe06d-181">Add all network circuits providing Internet connectivity to this office location in the **Egress IP Address ranges at this office location** section.</span></span> <span data-ttu-id="fe06d-182">Kontrol lera att varje krets är kopplad till de unika offentliga IP-adressundernät som representerar nätverks trafiken.</span><span class="sxs-lookup"><span data-stu-id="fe06d-182">Ensure that each circuit is associated with the unique public IP address subnets representing your network traffic.</span></span>

4. <span data-ttu-id="fe06d-183">Spara ändringarna genom att välja **Spara** .</span><span class="sxs-lookup"><span data-stu-id="fe06d-183">Select **Save** to save your changes.</span></span>

## <a name="disabling-network-informed-routing"></a><span data-ttu-id="fe06d-184">Inaktivera informerad routning av nätverk</span><span class="sxs-lookup"><span data-stu-id="fe06d-184">Disabling network informed routing</span></span>

<span data-ttu-id="fe06d-185">Den informerade nätverks dirigeringen kan vara inaktive rad för hela klient organisationen genom att återställa inställningarna för SD-WAN-lösningen.</span><span class="sxs-lookup"><span data-stu-id="fe06d-185">The informed network routing feature may be disabled for the entire tenant by resetting your SD-WAN solution settings.</span></span> <span data-ttu-id="fe06d-186">Det här kommer att stoppa all data behandling i Microsoft 365, men du bör också inaktivera upparbetad routning för nätverk i administrations centret.</span><span class="sxs-lookup"><span data-stu-id="fe06d-186">While this will stop all processing of data within Microsoft 365, you should also disable network informed routing within the admin center.</span></span>

### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="fe06d-187">Steg 1: öppna konfigurations alternativ för SD-WAN-lösning</span><span class="sxs-lookup"><span data-stu-id="fe06d-187">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="fe06d-188">I [administrations centret för Microsoft 365](https://admin.microsoft.com/) väljer du **hälso > nätverks anslutning** i det vänstra navigerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="fe06d-188">In the [Microsoft 365 admin center](https://admin.microsoft.com/) select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="fe06d-189">Välj **inställningar > SD-WAN-lösning** för att öppna den informerade konfigurations fönstret för nätverks dirigering.</span><span class="sxs-lookup"><span data-stu-id="fe06d-189">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span>

<span data-ttu-id="fe06d-190">I fönstret konfiguration visas en sammanfattning av din konfigurerade SD-WAN-lösning.</span><span class="sxs-lookup"><span data-stu-id="fe06d-190">The configuration pane shows a summary of your currently configured SD-WAN solution.</span></span>

### <a name="step-2-reset-your-configuration"></a><span data-ttu-id="fe06d-191">Steg 2: återställa din konfiguration</span><span class="sxs-lookup"><span data-stu-id="fe06d-191">Step 2: Reset your configuration</span></span>

<span data-ttu-id="fe06d-192">I fönstret konfiguration väljer **du Återställ dina inställningar för SD-WAN-lösning**.</span><span class="sxs-lookup"><span data-stu-id="fe06d-192">In the configuration pane, select **Reset your SD-WAN solution settings**.</span></span>

<span data-ttu-id="fe06d-193">Dina inställningar har nu återställts och ett underskrivet nätverks dirigering har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="fe06d-193">Your settings have now been reset and informed network routing has been disabled.</span></span> <span data-ttu-id="fe06d-194">Du kan återaktivera den när som helst genom att följa anvisningarna i [Aktivera välinformerad nätverks dirigering](#enabling-informed-network-routing).</span><span class="sxs-lookup"><span data-stu-id="fe06d-194">You can re-enable it at any time by following the steps in [Enabling informed network routing](#enabling-informed-network-routing).</span></span>

## <a name="data-storage"></a><span data-ttu-id="fe06d-195">Data lagring</span><span class="sxs-lookup"><span data-stu-id="fe06d-195">Data storage</span></span>

<span data-ttu-id="fe06d-196">Data som utbyts mellan Microsoft och leverantören för SD-WAN-lösning lagras på den data lagrings plats som marker ATS under den första inaktiverade nätverks informerade routning.</span><span class="sxs-lookup"><span data-stu-id="fe06d-196">Data exchanged between Microsoft and the SD-WAN solution provider is stored in the data storage location selected during the initial enablement of network informed routing.</span></span> <span data-ttu-id="fe06d-197">Alternativen för data lagrings plats representerar geografiska områden som innehåller Microsoft Azure-regioner där data lagras.</span><span class="sxs-lookup"><span data-stu-id="fe06d-197">The data storage location options represent geographical areas containing Microsoft Azure regions where the data is stored.</span></span>

>[!NOTE]
><span data-ttu-id="fe06d-198">Under för hands versions fasen är den enda tillgängliga data lagrings platsen **Nord Amerika**.</span><span class="sxs-lookup"><span data-stu-id="fe06d-198">During the Preview phase, the only available data storage location is **North America**.</span></span> <span data-ttu-id="fe06d-199">Ytterligare data lagrings platser blir tillgängliga innan den allmänna tillgängligheten för utskrivbar nätverks dirigering.</span><span class="sxs-lookup"><span data-stu-id="fe06d-199">Additional data storage locations will become available prior to the general availability of informed network routing.</span></span>

<span data-ttu-id="fe06d-200">Data behålls på den här platsen i upp till 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="fe06d-200">Data is retained in this location for up to 30 days.</span></span> <span data-ttu-id="fe06d-201">När den är inaktive rad tas alla återstående data bort inom det här 30-dagars periodiska fönstret.</span><span class="sxs-lookup"><span data-stu-id="fe06d-201">When disabled, all remaining data is removed within this 30-day retention window.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fe06d-202">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="fe06d-202">Related topics</span></span>

[<span data-ttu-id="fe06d-203">Nätverks anslutning i Microsoft 365 Admin Center (för hands version)</span><span class="sxs-lookup"><span data-stu-id="fe06d-203">Network connectivity in the Microsoft 365 admin center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="fe06d-204">Microsoft 365 nätverks anslutningar (för hands version)</span><span class="sxs-lookup"><span data-stu-id="fe06d-204">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
