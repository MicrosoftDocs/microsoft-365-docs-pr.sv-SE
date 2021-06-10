---
title: Se till att dina enheter är korrekt konfigurerade
description: Konfigurera enheter på rätt sätt för att öka den totala motståndskraften mot hot och förbättra din förmåga att identifiera och reagera på attacker.
keywords: onboard, Intune-hantering, Microsoft Defender för Slutpunkt, Microsoft Defender, Windows Defender, minskning av attackytan, ASR, säkerhetsbaslinje
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dccc623bfa6c3f5e8fe4d88ccfafd66d3e53482a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840904"
---
# <a name="ensure-your-devices-are-configured-properly"></a><span data-ttu-id="f7f52-104">Se till att dina enheter är korrekt konfigurerade</span><span class="sxs-lookup"><span data-stu-id="f7f52-104">Ensure your devices are configured properly</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f7f52-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f7f52-105">**Applies to:**</span></span>
- [<span data-ttu-id="f7f52-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f7f52-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f7f52-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7f52-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f7f52-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f7f52-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f7f52-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f7f52-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="f7f52-110">Med korrekt konfigurerade enheter kan du öka den totala motståndskraft mot hot och förbättra din förmåga att identifiera och reagera på attacker.</span><span class="sxs-lookup"><span data-stu-id="f7f52-110">With properly configured devices, you can boost overall resilience against threats and enhance your capability to detect and respond to attacks.</span></span> <span data-ttu-id="f7f52-111">Med hjälp av säkerhetskonfigurationshantering kan du säkerställa att dina enheter:</span><span class="sxs-lookup"><span data-stu-id="f7f52-111">Security configuration management helps ensure that your devices:</span></span>

- <span data-ttu-id="f7f52-112">Gå till Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f7f52-112">Onboard to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="f7f52-113">Möt eller överskrider konfiguration av säkerhetsbaslinje för Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f7f52-113">Meet or exceed the Defender for Endpoint security baseline configuration</span></span>
- <span data-ttu-id="f7f52-114">Gör åtgärder för strategiska attackytor på plats</span><span class="sxs-lookup"><span data-stu-id="f7f52-114">Have strategic attack surface mitigations in place</span></span>

<span data-ttu-id="f7f52-115">Klicka **på Konfigurationshantering** i navigeringsmenyn för att öppna sidan Hantering av enhetskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f7f52-115">Click **Configuration management** from the navigation menu to open the Device configuration management page.</span></span>

<span data-ttu-id="f7f52-116">![Sida för hantering av säkerhetskonfiguration](images/secconmgmt_main.png)</span><span class="sxs-lookup"><span data-stu-id="f7f52-116">![Security configuration management page](images/secconmgmt_main.png)</span></span><br>
<span data-ttu-id="f7f52-117">*Sida för hantering av enhetskonfiguration*</span><span class="sxs-lookup"><span data-stu-id="f7f52-117">*Device configuration management page*</span></span>

<span data-ttu-id="f7f52-118">Du kan spåra konfigurationsstatus på organisationsnivå och snabbt vidta åtgärder som svar på dålig täckning under onboarding, efterlevnadsproblem och dåligt optimerade minskningar av attackytan genom direkta, djupa länkar till sidor för enhetshantering på Microsoft Intune och Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="f7f52-118">You can track configuration status at an organizational level and quickly take action in response to poor onboarding coverage, compliance issues, and poorly optimized attack surface mitigations through direct, deep links to device management pages on Microsoft Intune and Microsoft 365 security center.</span></span>

<span data-ttu-id="f7f52-119">När du gör det har du nytta av följande:</span><span class="sxs-lookup"><span data-stu-id="f7f52-119">In doing so, you benefit from:</span></span>
- <span data-ttu-id="f7f52-120">Omfattande synlighet för händelser på dina enheter</span><span class="sxs-lookup"><span data-stu-id="f7f52-120">Comprehensive visibility of the events on your devices</span></span>
- <span data-ttu-id="f7f52-121">Robust information om hot och kraftfulla enhetsinlärningstekniker för bearbetning av rådata och identifiering av intrångsaktivitet och hotindikatorer</span><span class="sxs-lookup"><span data-stu-id="f7f52-121">Robust threat intelligence and powerful device learning technologies for processing raw events and identifying the breach activity and threat indicators</span></span>
- <span data-ttu-id="f7f52-122">En komplett hög med säkerhetsfunktioner som är konfigurerade för att effektivt stoppa installationen av skadliga program, kapning av systemfiler och systemfiler, datainfiltrering och andra hotaktiviteter</span><span class="sxs-lookup"><span data-stu-id="f7f52-122">A full stack of security features configured to efficiently stop the installation of malicious implants, hijacking of system files and process, data exfiltration, and other threat activities</span></span>
- <span data-ttu-id="f7f52-123">Optimerade minskningar av attackytor, maximera strategiska skydd mot hotaktivitet samtidigt som påverkan på produktiviteten minimeras</span><span class="sxs-lookup"><span data-stu-id="f7f52-123">Optimized attack surface mitigations, maximizing strategic defenses against threat activity while minimizing impact to productivity</span></span>

## <a name="enroll-devices-to-intune-management"></a><span data-ttu-id="f7f52-124">Registrera enheter till Intune-hantering</span><span class="sxs-lookup"><span data-stu-id="f7f52-124">Enroll devices to Intune management</span></span>

<span data-ttu-id="f7f52-125">Hantering av enhetskonfigurationer fungerar nära med intune enhetshantering för att upprätta inventeringen av enheterna i din organisation och den grundläggande säkerhetskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="f7f52-125">Device configuration management works closely with Intune device management to establish the inventory of the devices in your organization and the baseline security configuration.</span></span> <span data-ttu-id="f7f52-126">Du kommer att kunna spåra och hantera konfigurationsproblem på Intune-hanterade Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="f7f52-126">You will be able to track and manage configuration issues on Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="f7f52-127">Innan du kan se till att dina enheter har konfigurerats korrekt bör du registrera dem i Intune-hantering.</span><span class="sxs-lookup"><span data-stu-id="f7f52-127">Before you can ensure your devices are configured properly, enroll them to Intune management.</span></span> <span data-ttu-id="f7f52-128">Intune-registrering är robust och har flera registreringsalternativ för Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="f7f52-128">Intune enrollment is robust and has several enrollment options for Windows 10 devices.</span></span> <span data-ttu-id="f7f52-129">Mer information om intune-registreringsalternativ finns i om hur du [ställer in registrering för Windows enheter.](/intune/windows-enroll)</span><span class="sxs-lookup"><span data-stu-id="f7f52-129">For more information about Intune enrollment options, read about [setting up enrollment for Windows devices](/intune/windows-enroll).</span></span>

>[!NOTE]
><span data-ttu-id="f7f52-130">För att registrera Windows enheter till Intune måste administratörer redan ha tilldelats licenser.</span><span class="sxs-lookup"><span data-stu-id="f7f52-130">To enroll Windows devices to Intune, administrators must have already been assigned licenses.</span></span> <span data-ttu-id="f7f52-131">[Läs om hur du tilldelar licenser för enhetsregistrering](/intune/licenses-assign).</span><span class="sxs-lookup"><span data-stu-id="f7f52-131">[Read about assigning licenses for device enrollment](/intune/licenses-assign).</span></span>

>[!TIP] 
><span data-ttu-id="f7f52-132">Om du vill optimera enhetshantering via Intune [ansluter du Intune till Defender för Slutpunkt](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span><span class="sxs-lookup"><span data-stu-id="f7f52-132">To optimize device management through Intune, [connect Intune to Defender for Endpoint](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span>

## <a name="obtain-required-permissions"></a><span data-ttu-id="f7f52-133">Skaffa behörighet som krävs</span><span class="sxs-lookup"><span data-stu-id="f7f52-133">Obtain required permissions</span></span>
<span data-ttu-id="f7f52-134">Som standard kan endast användare som har tilldelats rollen Global administratör eller Intune-tjänstadministratör i Azure AD hantera och tilldela de enhetskonfigurationsprofiler som behövs för registrering av enheter och distribuera säkerhetsbaslinjen.</span><span class="sxs-lookup"><span data-stu-id="f7f52-134">By default, only users who have been assigned the Global Administrator or the Intune Service Administrator role on Azure AD can manage and assign the device configuration profiles needed for onboarding devices and deploying the security baseline.</span></span>

<span data-ttu-id="f7f52-135">Om du har tilldelats andra roller bör du kontrollera att du har rätt behörighet:</span><span class="sxs-lookup"><span data-stu-id="f7f52-135">If you have been assigned other roles, ensure you have the necessary permissions:</span></span>

- <span data-ttu-id="f7f52-136">Fullständig behörighet till enhetskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="f7f52-136">Full permissions to device configurations</span></span>
- <span data-ttu-id="f7f52-137">Fullständig behörighet till säkerhetsbaslinjer</span><span class="sxs-lookup"><span data-stu-id="f7f52-137">Full permissions to security baselines</span></span>
- <span data-ttu-id="f7f52-138">Läs behörigheter till principer för enhetsefterlevnad</span><span class="sxs-lookup"><span data-stu-id="f7f52-138">Read permissions to device compliance policies</span></span>
- <span data-ttu-id="f7f52-139">Läsbehörigheter för organisationen</span><span class="sxs-lookup"><span data-stu-id="f7f52-139">Read permissions to the organization</span></span>

<span data-ttu-id="f7f52-140">![Behörighet som krävs för intune](images/secconmgmt_intune_permissions.png)</span><span class="sxs-lookup"><span data-stu-id="f7f52-140">![Required permissions on intune](images/secconmgmt_intune_permissions.png)</span></span><br>
<span data-ttu-id="f7f52-141">*Behörigheter för enhetskonfiguration i Intune*</span><span class="sxs-lookup"><span data-stu-id="f7f52-141">*Device configuration permissions on Intune*</span></span>

>[!TIP] 
><span data-ttu-id="f7f52-142">Mer information om hur du tilldelar behörigheter för Intune finns [i Skapa anpassade roller.](/intune/create-custom-role#to-create-a-custom-role)</span><span class="sxs-lookup"><span data-stu-id="f7f52-142">To learn more about assigning permissions on Intune, [read about creating custom roles](/intune/create-custom-role#to-create-a-custom-role).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f7f52-143">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="f7f52-143">In this section</span></span>
<span data-ttu-id="f7f52-144">Ämne</span><span class="sxs-lookup"><span data-stu-id="f7f52-144">Topic</span></span> | <span data-ttu-id="f7f52-145">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f7f52-145">Description</span></span>
:---|:---
[<span data-ttu-id="f7f52-146">Få enheter onboarded till Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f7f52-146">Get devices onboarded to Defender for Endpoint</span></span>](configure-machines-onboarding.md)| <span data-ttu-id="f7f52-147">Spåra onboardingstatus för Intune-hanterade enheter och registrera fler enheter via Intune.</span><span class="sxs-lookup"><span data-stu-id="f7f52-147">Track onboarding status of Intune-managed devices and onboard more devices through Intune.</span></span> 
[<span data-ttu-id="f7f52-148">Öka efterlevnad för Defender för slutpunktens säkerhetsbaslinje</span><span class="sxs-lookup"><span data-stu-id="f7f52-148">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md) | <span data-ttu-id="f7f52-149">Spåra grundläggande efterlevnad och icke-efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="f7f52-149">Track baseline compliance and noncompliance.</span></span> <span data-ttu-id="f7f52-150">Distribuera säkerhetsbaslinjen till fler Intune-hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="f7f52-150">Deploy the security baseline to more Intune-managed devices.</span></span>
[<span data-ttu-id="f7f52-151">Optimera ASR-regeldistribution och identifiering</span><span class="sxs-lookup"><span data-stu-id="f7f52-151">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md) | <span data-ttu-id="f7f52-152">Granska regeldistribution och justera avkänningar med hjälp av effektanalysverktyg Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="f7f52-152">Review rule deployment and tweak detections using impact analysis tools in Microsoft 365 security center.</span></span>

><span data-ttu-id="f7f52-153">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f7f52-153">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f7f52-154">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f7f52-154">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
