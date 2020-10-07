---
title: Steg 4. Distribuera slutpunktshantering för enheter, datorer och andra slutpunkter
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Använd Microsoft Endpoint Manager för att hantera dina hanteringsenheter, datorer och andra slutpunkter.
ms.openlocfilehash: 5c6e433918709a55f03d786891ec0fd7ac62a26b
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377241"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a><span data-ttu-id="3751b-104">Steg 4.</span><span class="sxs-lookup"><span data-stu-id="3751b-104">Step 4.</span></span> <span data-ttu-id="3751b-105">Distribuera slutpunktshantering för enheter, datorer och andra slutpunkter</span><span class="sxs-lookup"><span data-stu-id="3751b-105">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>

<span data-ttu-id="3751b-106">Med distansarbetare måste du ha stöd för ett ökande antal personliga enheter.</span><span class="sxs-lookup"><span data-stu-id="3751b-106">With remote workers, you need to support a growing number of personal devices.</span></span> <span data-ttu-id="3751b-107">Slutpunktshantering är en principbaserad metod för säkerhet som kräver att enheter följer specifika villkor innan de beviljas åtkomst till resurser.</span><span class="sxs-lookup"><span data-stu-id="3751b-107">Endpoint management is a policy-based approach to security that requires devices to comply with specific criteria before they are granted access to resources.</span></span> <span data-ttu-id="3751b-108">Microsoft Endpoint Manager tillhandahåller moderna hanteringsfunktioner för att skydda dina data i molnet och lokalt.</span><span class="sxs-lookup"><span data-stu-id="3751b-108">Microsoft Endpoint Manager delivers modern management capabilities to keep your data secure in the cloud and on-premises.</span></span> 

<span data-ttu-id="3751b-109">Microsoft Endpoint Manager tillhandhåller tjänster och verktyg för hantering av mobila enheter, stationära datorer, virtuella datorer, inbäddade enheter och servrar genom att kombinera följande tjänster som du kanske redan känner till och använder.</span><span class="sxs-lookup"><span data-stu-id="3751b-109">Endpoint Manager provides services and tools for managing mobile devices, desktop computers, virtual machines, embedded devices, and servers by combining the following services you may already know and be using.</span></span>

![Komponenter för slutpunktshantering](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a><span data-ttu-id="3751b-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3751b-111">Microsoft Intune</span></span>

<span data-ttu-id="3751b-112">Microsoft Intune är en molnbaserad tjänst som fokuserar på hantering av mobila enheter (MDM) och hantering av mobila program (MAM) som ingår i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3751b-112">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM) that is included with Microsoft 365.</span></span> 

- <span data-ttu-id="3751b-113">**MDM:** för enheter som ägs av organisationen kan du utnyttja fullständig kontroll, t. ex. inställningar, funktioner och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="3751b-113">**MDM:** For organization-owned devices, you can exercise full control including settings, features, and security.</span></span> <span data-ttu-id="3751b-114">Enheter "registreras" i Intune där de får Intune-principer med regler och inställningar.</span><span class="sxs-lookup"><span data-stu-id="3751b-114">Devices are "enrolled" in Intune where they receive Intune policies with rules and settings.</span></span> <span data-ttu-id="3751b-115">Du kan till exempel ange krav på lösenord och PIN-kod, skapa en VPN-anslutning, konfigurera skydd med hot och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="3751b-115">For example, you can set password and PIN requirements, create a VPN connection, set up threat protection, and more.</span></span>

- <span data-ttu-id="3751b-116">**MAM:** distansmedarbetare kanske inte vill att du ska ha fullständig kontroll över deras personliga enheter, även kallat bring-your-own device (BYOD).</span><span class="sxs-lookup"><span data-stu-id="3751b-116">**MAM:** Remote workers might not want you to have full control on their personal devices, also known as bring-your-own device (BYOD) devices.</span></span> <span data-ttu-id="3751b-117">Du kan erbjuda dina distansmedarbetare alternativ och fortfarande skydda din organisation.</span><span class="sxs-lookup"><span data-stu-id="3751b-117">You can give your remote workers options and still protect your organization.</span></span> <span data-ttu-id="3751b-118">Distansmedarbetare kan till exempel registrera sina enheter om de vill ha full tillgång till organisationens resurser.</span><span class="sxs-lookup"><span data-stu-id="3751b-118">For example, remote workers can enroll their devices if they want full access to your organization resources.</span></span> <span data-ttu-id="3751b-119">Om de här användarna bara vill ha tillgång till e-post eller Microsoft Teams kan du använda skyddsprinciper för appar som kräver multifaktorautentisering (MFA) för att använda de här apparna.</span><span class="sxs-lookup"><span data-stu-id="3751b-119">Or, if these users only want access to email or Microsoft Teams, then use app protection policies that require multi-factor authentication (MFA) to use these apps.</span></span>

<span data-ttu-id="3751b-120">Mer information finns i det här [översikt över Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="3751b-120">For more information, see this [overview of Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).</span></span>

## <a name="configuration-manager"></a><span data-ttu-id="3751b-121">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3751b-121">Configuration Manager</span></span>

<span data-ttu-id="3751b-122">Configuration Manager är en lokal hanteringslösning för hantering av stationära datorer, servrar och bärbara datorer som finns på nätverket eller är internet-baserade.</span><span class="sxs-lookup"><span data-stu-id="3751b-122">Configuration Manager is an on-premises management solution to manage desktops, servers, and laptops that are on your network or internet-based.</span></span> <span data-ttu-id="3751b-123">Använd Configuration Manager för att distribuera appar, programvaruuppdateringar och operativ system.</span><span class="sxs-lookup"><span data-stu-id="3751b-123">Use Configuration Manager to deploy apps, software updates, and operating systems.</span></span> <span data-ttu-id="3751b-124">Du kan också övervaka efterlevnad, läsa och åtgärda klienter i realtid och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="3751b-124">You can also monitor compliance, query and act on clients in real time, and much more.</span></span> <span data-ttu-id="3751b-125">Du kan moln-aktivera den för att integrera med Intune, Azure Active Directory, Microsoft Defender Avancerat skydd och andra molntjänster.</span><span class="sxs-lookup"><span data-stu-id="3751b-125">You can cloud-enable it to integrate with Intune, Azure AD, Microsoft Defender ATP, and other cloud services.</span></span> 

<span data-ttu-id="3751b-126">Mer information finns i den här [översikt över Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="3751b-126">For more information, see this [overview of Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span></span>

## <a name="co-management"></a><span data-ttu-id="3751b-127">Samhantering</span><span class="sxs-lookup"><span data-stu-id="3751b-127">Co-management</span></span>

<span data-ttu-id="3751b-128">Med hjälp av samhantering slås din befintliga lokala investeringar i Configuration Manager med molnet med hjälp av Intune och andra Microsoft 365-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="3751b-128">Co-management combines your existing on-premises Configuration Manager investment with the cloud using Intune and other Microsoft 365 cloud services.</span></span> <span data-ttu-id="3751b-129">Du kan välja om Configuration Manager eller Intune ska vara hanteringsauktoritet för olika arbetsbelastning.</span><span class="sxs-lookup"><span data-stu-id="3751b-129">You choose whether Configuration Manager or Intune is the management authority for different workload.</span></span> 

<span data-ttu-id="3751b-130">I Co-Management används Intune-baserade molnfunktioner, t. ex. villkorlig åtkomst och framtvingande av enhetskompatibilitet.</span><span class="sxs-lookup"><span data-stu-id="3751b-130">Co-management uses Intune-based cloud features, including Conditional Access and enforcing device compliance.</span></span> <span data-ttu-id="3751b-131">Du har kvar några uppgifter lokalt medan du kör andra uppgifter i molnet.</span><span class="sxs-lookup"><span data-stu-id="3751b-131">You keep some tasks on-premises, while running other tasks in the cloud.</span></span>

<span data-ttu-id="3751b-132">Mer information finns i den här [översikt över samhantering](https://docs.microsoft.com/mem/configmgr/comanage/overview).</span><span class="sxs-lookup"><span data-stu-id="3751b-132">For more information, see this [overview of co-management](https://docs.microsoft.com/mem/configmgr/comanage/overview).</span></span>

## <a name="desktop-analytics"></a><span data-ttu-id="3751b-133">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="3751b-133">Desktop Analytics</span></span>

<span data-ttu-id="3751b-134">Desktop Analytics är en molnbaserad tjänst som integreras med Configuration Manager och ger dig insyn och intelligens så att du kan fatta välgrundade beslut om dina Windows-klienter.</span><span class="sxs-lookup"><span data-stu-id="3751b-134">Desktop Analytics is a cloud-based service that integrates with Configuration Manager and provides you with insight and intelligence so you can make informed decisions about your Windows clients.</span></span> <span data-ttu-id="3751b-135">Den kombinerar data från din organisation med data aggregerade från miljontals enheter som är anslutna till Microsofts molntjänster.</span><span class="sxs-lookup"><span data-stu-id="3751b-135">It combines data from your organization with data aggregated from millions of devices connected to Microsoft cloud services.</span></span> 

<span data-ttu-id="3751b-136">Med Desktop Analytics kan du:</span><span class="sxs-lookup"><span data-stu-id="3751b-136">With Desktop Analytics, you can:</span></span>

- <span data-ttu-id="3751b-137">Skapa en inventering av appar som körs i din organisation.</span><span class="sxs-lookup"><span data-stu-id="3751b-137">Create an inventory of apps running in your organization.</span></span>
- <span data-ttu-id="3751b-138">Utvärdera apparnas kompatibilitet med de senaste funktionsuppdateringarna för Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3751b-138">Assess app compatibility with the latest Windows 10 feature updates.</span></span>
- <span data-ttu-id="3751b-139">Identifiera kompatibilitetsproblem och få förslag på problem med hjälp av molnbaserade datainsikter.</span><span class="sxs-lookup"><span data-stu-id="3751b-139">Identify compatibility issues, and receive mitigation suggestions based on cloud-enabled data insights.</span></span>
- <span data-ttu-id="3751b-140">Skapa pilotgrupper som representerar hela programmet och fastigheten i en minimal uppsättning enheter.</span><span class="sxs-lookup"><span data-stu-id="3751b-140">Create pilot groups that represent the entire application and driver estate across a minimal set of devices.</span></span>
- <span data-ttu-id="3751b-141">Distribuera Windows 10 till pilotprojekt och Production Managed-enheter.</span><span class="sxs-lookup"><span data-stu-id="3751b-141">Deploy Windows 10 to pilot and production-managed devices.</span></span>

<span data-ttu-id="3751b-142">Mer information finns i den här [översikt över Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)</span><span class="sxs-lookup"><span data-stu-id="3751b-142">For more information, see this [overview of Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)</span></span>

## <a name="windows-autopilot"></a><span data-ttu-id="3751b-143">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="3751b-143">Windows Autopilot</span></span>

<span data-ttu-id="3751b-144">Windows Autopilot är en plattform för Windows-driftsättning med låg vikt.</span><span class="sxs-lookup"><span data-stu-id="3751b-144">Windows Autopilot is a zero-touch, self-service Windows deployment platform.</span></span> <span data-ttu-id="3751b-145">Den innehåller en samling tekniker som används för att konfigurera och förinstallera nya enheter och för att förbereda för effektiv användning.</span><span class="sxs-lookup"><span data-stu-id="3751b-145">It includes a collection of technologies used to set up and pre-configure new devices, getting them ready for productive use.</span></span> <span data-ttu-id="3751b-146">Du kan också använda Windows Autopilot för att återställa, återanvända enheter.</span><span class="sxs-lookup"><span data-stu-id="3751b-146">You can also use Windows Autopilot to reset, repurpose and recover devices.</span></span> 

<span data-ttu-id="3751b-147">Windows Autopilot låter IT-avdelningen förkonfigurera enheter med liten till ingen infrastruktur för hantering, med en process som är enkel och lätt.</span><span class="sxs-lookup"><span data-stu-id="3751b-147">Windows Autopilot enables an IT department to pre-configure devices with little to no infrastructure to manage, with a process that's easy and simple.</span></span> 

- <span data-ttu-id="3751b-148">Från användarens perspektiv är det bara några få enkla åtgärder för att göra deras enhet redo för användning.</span><span class="sxs-lookup"><span data-stu-id="3751b-148">From the user's perspective, it only takes a few simple operations to make their device ready to use.</span></span> 
- <span data-ttu-id="3751b-149">Från IT-proffsens perspektiv är den enda interaktion som krävs för slutanvändarna att ansluta till ett nätverk och för att verifiera deras autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="3751b-149">From the IT pro's perspective, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span>

<span data-ttu-id="3751b-150">Mer information finns i den här [översikt över Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span><span class="sxs-lookup"><span data-stu-id="3751b-150">For more information, see this [overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

## <a name="admin-technical-resources-for-endpoint-management"></a><span data-ttu-id="3751b-151">Tekniska IT-resurser för slutpunktshantering</span><span class="sxs-lookup"><span data-stu-id="3751b-151">Admin technical resources for endpoint management</span></span>

- [<span data-ttu-id="3751b-152">Del 3-video om hur man hanterar Windows 10-enheter vid distansarbete</span><span class="sxs-lookup"><span data-stu-id="3751b-152">The Part 3 video on managing Windows 10 devices for remote workers</span></span>](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [<span data-ttu-id="3751b-153">Del 5-video om hur man hanterar användares skrivbord och webbläsare vid distansarbete</span><span class="sxs-lookup"><span data-stu-id="3751b-153">The Part 5 video on managing user desktops and browsers for remote workers</span></span>](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [<span data-ttu-id="3751b-154">Distribuera en infrastruktur för rörlighet med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3751b-154">Deploy a mobility infrastructure for Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [<span data-ttu-id="3751b-155">Registrera olika typer av enheter för hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="3751b-155">How to enroll different types of devices for mobile device management</span></span>](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [<span data-ttu-id="3751b-156">Hur du utbildar dina slutanvändare om Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3751b-156">How to educate your end users about Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a><span data-ttu-id="3751b-157">Resultat i steg 3</span><span class="sxs-lookup"><span data-stu-id="3751b-157">Results of Step 3</span></span>

<span data-ttu-id="3751b-158">Du använder paketet med Endpoint Manager-funktioner och -förmågor för att hantera mobila enheter, stationära datorer, virtuella datorer, inbäddade enheter och servrar.</span><span class="sxs-lookup"><span data-stu-id="3751b-158">You are using the suite of Endpoint Manager features and capabilities to manage mobile devices, desktop computers, virtual machines, embedded devices, and servers.</span></span>

## <a name="next-step"></a><span data-ttu-id="3751b-159">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="3751b-159">Next step</span></span>

<span data-ttu-id="3751b-160">Fortsätt med [Steg 5](empower-people-to-work-remotely-teams-productivity-apps.md) för att få dina distansmedarbetare att använda Microsoft 365 produktivitetsappar som Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3751b-160">Continue with [Step 5](empower-people-to-work-remotely-teams-productivity-apps.md) to get your remote workers using Microsoft 365 productivity apps such as Microsoft Teams.</span></span>
