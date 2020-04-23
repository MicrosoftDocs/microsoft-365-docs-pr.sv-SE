---
title: 'Fas 3: Avslutsvillkor för Windows 10 Enterprise-infrastruktur'
f1.keywords:
- NOCSH
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Kontrollera att din konfiguration uppfyller Microsoft 365 Enterprise villkor för Windows 10 Enterprise.
ms.openlocfilehash: cf4a813a6cf89029eebde8e5947caf7b3c2ea553
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636693"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a><span data-ttu-id="7d4fe-103">Fas 3: Avslutsvillkor för Windows 10 Enterprise-infrastruktur</span><span class="sxs-lookup"><span data-stu-id="7d4fe-103">Phase 3: Windows 10 Enterprise infrastructure exit criteria</span></span>

![Fas 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="7d4fe-105">Kontrollera att din Windows 10 Enterprise-infrastruktur uppfyller följande krav och överväg om du vill använda de valfria alternativen.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-105">Make sure your Windows 10 Enterprise infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="7d4fe-106">Obligatoriskt: Dina Microsoft 365-domäner har lagts till och verifierats</span><span class="sxs-lookup"><span data-stu-id="7d4fe-106">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="7d4fe-107">Azure AD-klienten för dina Office 365- och Intune-prenumerationer har konfigurerats med dina Internetdomännamn (till exempel contoso.com), i stället för bara ett domännamn som innehåller ”onmicrosoft.com”.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-107">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="7d4fe-108">Om du inte gör det begränsas autentiseringsmetoderna som du kan konfigurera.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-108">If you do not do so, you will be limited in the authentication methods that you can configure.</span></span> <span data-ttu-id="7d4fe-109">Direktautentisering och federerad autentisering kan till exempel inte använda domännamnet ”onmicrosoft.com”.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-109">For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="7d4fe-110">Vid behov kan [Steg 1](windows10-prepare-your-org.md) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-110">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this requirement.</span></span>

## <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="7d4fe-111">Valfritt: Användarna har lagts till och fått licenser</span><span class="sxs-lookup"><span data-stu-id="7d4fe-111">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="7d4fe-112">Dina användares konton har lagts till, antingen direkt till din Azure AD-klient för dina Office 365- och Intune-prenumerationer, eller från katalogsynkronisering från din lokala AD DS (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="7d4fe-112">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Active Directory Domain Services (AD DS).</span></span>

<span data-ttu-id="7d4fe-113">När användarna har lagts till kan du tilldela dem Microsoft 365 Enterprise-licenser, antingen direkt som global administratör eller användaradministratör, eller automatiskt via gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-113">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="7d4fe-114">Vid behov kan [Steg 1](windows10-prepare-your-org.md) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-114">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

## <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="7d4fe-115">Valfritt: Diagnostik har aktiverats</span><span class="sxs-lookup"><span data-stu-id="7d4fe-115">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="7d4fe-116">Du har aktiverat inställningar för diagnostikdata med hjälp av grupprincip, Microsoft Intune, Registereditorn eller i kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-116">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="7d4fe-117">Vid behov kan [Steg 1](windows10-prepare-your-org.md) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-117">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="7d4fe-118">Obligatoriskt för uppgradering på plats: En aktivitetssekvens för 
Configuration Manager har skapats för distribution av operativsystem</span><span class="sxs-lookup"><span data-stu-id="7d4fe-118">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="7d4fe-119">Om du vill starta en aktivitetssekvens för Configuration Manager för att göra en uppgradering på plats på en enhet som kör Windows 7 eller Windows 8.1 måste du ha:</span><span class="sxs-lookup"><span data-stu-id="7d4fe-119">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="7d4fe-120">Konfigurerat rätt nivå för Windows-diagnostikdata.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-120">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="7d4fe-121">Verifierat att enheten är redo för Windows-uppgradering.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-121">Verified the readiness to upgrade Windows</span></span>
- <span data-ttu-id="7d4fe-122">Skapat en aktivitetssekvens för Configuration Manager som omfattar en enhetssamling och en distribution av operativsystem med en Windows 10 OS-avbildning.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-122">Created a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="7d4fe-123">När det är klart kan du utföra uppgraderingar på plats på enheter som är redo för Windows-uppgradering.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-123">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows.</span></span> <span data-ttu-id="7d4fe-124">För att få ut så mycket som möjligt av Microsoft 365 Enterprise kan du uppgradera så många enheter som kör Windows 7 och Windows 8.1 som möjligt.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-124">To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="7d4fe-125">Enheter som kör Windows 10 Enterprise kan få tillgång till fördelarna med den integrerade lösningen Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-125">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="7d4fe-126">Andra enheter som kör Windows 7 eller Windows 8.1 kan inte använda den molnbaserade tekniken eller de avancerade säkerhetsfunktionerna i Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-126">The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="7d4fe-127">Vid behov kan [Steg 2](windows10-deploy-inplaceupgrade.md) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-127">If needed, [Step 2](windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="7d4fe-128">Obligatoriskt för nya enheter: Konfigurerad Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="7d4fe-128">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="7d4fe-129">Om du vill distribuera och anpassa Windows 10 Enterprise på en ny enhet med Windows Autopilot måste du ha:</span><span class="sxs-lookup"><span data-stu-id="7d4fe-129">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="7d4fe-130">Konfigurerat rätt nivå för Windows-diagnostikdata.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-130">Configured the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="7d4fe-131">Konfigurerat förutsättningarna för Windows Autopilot, som:</span><span class="sxs-lookup"><span data-stu-id="7d4fe-131">Configured the prerequisites for Windows Autopilot, which include:</span></span>
   - <span data-ttu-id="7d4fe-132">Enhetsregistrering och OOBE-anpassning.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-132">Device registration and OOBE customization</span></span>
   - <span data-ttu-id="7d4fe-133">Företagsanpassning för OOBE.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-133">Company branding for OOBE</span></span>
   - <span data-ttu-id="7d4fe-134">Automatisk MDM-registrering i Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-134">MDM auto-enrollment in Microsoft Intune</span></span>
   - <span data-ttu-id="7d4fe-135">Nätverksanslutning till molntjänster som används av Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-135">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="7d4fe-136">Enheter som har Windows 10, version 1703 eller senare förinstallerat.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-136">Devices that are pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="7d4fe-137">Valt distributionsprogrammet Windows Autopilot för organisationen.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-137">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="7d4fe-138">När Windows Autopilot-konfigurationen har gjorts kan du använda den för att konfigurera och anpassa Windows 10 Enterprise för välkomstupplevelsen (OOBE) för:</span><span class="sxs-lookup"><span data-stu-id="7d4fe-138">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="7d4fe-139">Nya enheter.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-139">New devices</span></span>
- <span data-ttu-id="7d4fe-140">Enheter som redan har slutfört en OOBE-konfiguration i din organisation.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-140">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="7d4fe-141">Windows Autopilot konfigurerar enheten och ansluter den till Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-141">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="7d4fe-142">Utan Windows Autopilot måste du manuellt konfigurera nya enheter, även anslutningen till Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-142">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="7d4fe-143">Vid behov kan [Steg 3](windows10-deploy-autopilot.md) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-143">If needed, [Step 3](windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="7d4fe-144">Valfritt: Du övervakar Windows 10 Enterprise-baserade enheter med enhetshälsotillstånd i Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="7d4fe-144">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="7d4fe-145">Du har använt informationen från övervakningen av enheternas hälsotillstånd för att identifiera och åtgärda problem som påverkar slutanvändarna.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-145">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users.</span></span> <span data-ttu-id="7d4fe-146">Genom att snabbt åtgärda problem för slutanvändare kan du minska supportkostnaderna och visa dina användare IT-åtagandet för Windows 10 Enterprise. Det kan stödja införandet i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-146">Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="7d4fe-147">Vid behov kan [Steg 4](windows10-enable-windows-analytics.md) hjälpa dig med detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-147">If needed, [Step 4](windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="7d4fe-148">Obligatoriskt: Du använder Windows Defender Antivirus eller din egen lösning mot skadlig kod</span><span class="sxs-lookup"><span data-stu-id="7d4fe-148">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="7d4fe-149">Du har distribuerat Windows Defender Antivirus eller din egen antiviruslösning för att skydda dina enheter som kör Windows 10 Enterprise mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-149">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software.</span></span> <span data-ttu-id="7d4fe-150">Om du har distribuerat Windows Defender Antivirus har du implementerat en rapporteringsmetod, t.ex. Microsoft Endpoint Configuration Manager eller Microsoft Intune, för att övervaka antivirushändelser och aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-150">If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as Microsoft Endpoint Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="7d4fe-151">Vid behov kan [Steg 5](windows10-enable-security-features.md#windows10-sec-av) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-151">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="7d4fe-152">Obligatoriskt: Du använder Windows Defender Exploit Guard</span><span class="sxs-lookup"><span data-stu-id="7d4fe-152">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="7d4fe-153">Du har distribuerat Windows Defender Exploit Guard för att skydda dina enheter som kör Windows 10 Enterprise mot intrång och har implementerat en rapporteringsmetod, t.ex. Configuration Manager eller Microsoft Intune, för att övervaka intrångshändelser och aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-153">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="7d4fe-154">Vid behov kan [Steg 5](windows10-enable-security-features.md#windows10-sec-eg) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-154">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a><span data-ttu-id="7d4fe-155">Obligatoriskt: Du använder Microsoft Defender Avancerat skydd (endast Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="7d4fe-155">Required: You are using Microsoft Defender Advanced Threat Protection (Microsoft 365 E5 only)</span></span>

<span data-ttu-id="7d4fe-156">Du har distribuerat Microsoft Defender Avancerat skydd (ATP) för att identifiera, undersöka och åtgärda avancerade hot mot ditt nätverk och enheter som kör Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-156">You deployed Microsoft Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="7d4fe-157">Du kan även ha integrerat Microsoft Defender ATP med andra verktyg för att utöka funktionerna.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-157">Optionally, you have integrated Microsoft Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="7d4fe-158">Vid behov kan [Steg 5](windows10-enable-security-features.md#windows10-sec-atp) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-158">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="7d4fe-159">Resultat och nästa steg</span><span class="sxs-lookup"><span data-stu-id="7d4fe-159">Results and next steps</span></span>

<span data-ttu-id="7d4fe-160">Windows 10 Enterprise-infrastruktur har förberetts för att påbörja installationen på nya enheter och uppgraderingar på plats på enheter som kör tidigare versioner av Windows, och du använder huvudfunktionerna för säkerhet i Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7d4fe-160">Your Windows 10 Enterprise infrastructure is ready to begin installation on new devices and upgrades-in-place on devices running previous versions of Windows, and you are using the key security features of Windows 10 Enterprise.</span></span>

|||
|:-------|:-----|
|![Fas 4: Microsoft 365 Apps för företag](../media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| <span data-ttu-id="7d4fe-162">Om du följer stegen för komplett distribution av Microsoft 365 Enterprise så är nästa fas [Microsoft 365 Apps för företag](office365proplus-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="7d4fe-162">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md).</span></span> |
