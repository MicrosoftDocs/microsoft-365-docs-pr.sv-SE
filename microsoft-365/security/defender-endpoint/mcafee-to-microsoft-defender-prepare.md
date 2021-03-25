---
title: McAfee till Microsoft Defender för Endpoint – förbereda
description: Det här är fas 1, Förbereda, för migrering från McAfee till Microsoft Defender ATP.
keywords: migrering, windows defender avancerat skydd, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: c87ed20dd1d0c959a9af52fd766d0a34232747b2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069673"
---
# <a name="migrate-from-mcafee---phase-1-prepare-for-your-migration"></a><span data-ttu-id="af8d3-104">Migrera från McAfee – fas 1: Förbereda migreringen</span><span class="sxs-lookup"><span data-stu-id="af8d3-104">Migrate from McAfee - Phase 1: Prepare for your migration</span></span>

<span data-ttu-id="af8d3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="af8d3-105">**Applies to:**</span></span>
- [<span data-ttu-id="af8d3-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="af8d3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="af8d3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af8d3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Fas 1: Förbereda](images/phase-diagrams/prepare.png)<br/><span data-ttu-id="af8d3-109">Fas 1: Förbereda</span><span class="sxs-lookup"><span data-stu-id="af8d3-109">Phase 1: Prepare</span></span> |<span data-ttu-id="af8d3-110">[![Fas 2: Konfigurera](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)</span><span class="sxs-lookup"><span data-stu-id="af8d3-110">[![Phase 2: Set up](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)</span></span><br/>[<span data-ttu-id="af8d3-111">Fas 2: Konfigurera</span><span class="sxs-lookup"><span data-stu-id="af8d3-111">Phase 2: Set up</span></span>](mcafee-to-microsoft-defender-setup.md) |<span data-ttu-id="af8d3-112">[![Fas 3: Introduktion](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)</span><span class="sxs-lookup"><span data-stu-id="af8d3-112">[![Phase 3: Onboard](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)</span></span><br/>[<span data-ttu-id="af8d3-113">Fas 3: Introduktion</span><span class="sxs-lookup"><span data-stu-id="af8d3-113">Phase 3: Onboard</span></span>](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
|<span data-ttu-id="af8d3-114">*Du är här!*</span><span class="sxs-lookup"><span data-stu-id="af8d3-114">*You are here!*</span></span>| | |


<span data-ttu-id="af8d3-115">**Välkommen till förberedelsefasen för [migrering från McAfee Endpoint Security (McAfee) till Microsoft Defender för Slutpunkt](mcafee-to-microsoft-defender-migration.md#the-migration-process)**.</span><span class="sxs-lookup"><span data-stu-id="af8d3-115">**Welcome to the Prepare phase of [migrating from McAfee Endpoint Security (McAfee) to Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)**.</span></span> 

<span data-ttu-id="af8d3-116">Den här migreringsfasen omfattar följande steg:</span><span class="sxs-lookup"><span data-stu-id="af8d3-116">This migration phase includes the following steps:</span></span>
1. [<span data-ttu-id="af8d3-117">Hämta och distribuera uppdateringar på organisationens enheter</span><span class="sxs-lookup"><span data-stu-id="af8d3-117">Get and deploy updates across your organization's devices</span></span>](#get-and-deploy-updates-across-your-organizations-devices)
2. <span data-ttu-id="af8d3-118">[Skaffa Microsoft Defender för Slutpunkt](#get-microsoft-defender-for-endpoint).</span><span class="sxs-lookup"><span data-stu-id="af8d3-118">[Get Microsoft Defender for Endpoint](#get-microsoft-defender-for-endpoint).</span></span>
3. <span data-ttu-id="af8d3-119">[Bevilja åtkomst till Microsoft Defender Säkerhetscenter.](#grant-access-to-the-microsoft-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="af8d3-119">[Grant access to the Microsoft Defender Security Center](#grant-access-to-the-microsoft-defender-security-center).</span></span>
4. <span data-ttu-id="af8d3-120">[Konfigurera enhetsproxy och internetanslutningsinställningar](#configure-device-proxy-and-internet-connectivity-settings).</span><span class="sxs-lookup"><span data-stu-id="af8d3-120">[Configure device proxy and internet connectivity settings](#configure-device-proxy-and-internet-connectivity-settings).</span></span>

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a><span data-ttu-id="af8d3-121">Hämta och distribuera uppdateringar på organisationens enheter</span><span class="sxs-lookup"><span data-stu-id="af8d3-121">Get and deploy updates across your organization's devices</span></span>

<span data-ttu-id="af8d3-122">Det är alltid bra att hålla organisationens enheter och slutpunkter uppdaterade.</span><span class="sxs-lookup"><span data-stu-id="af8d3-122">As a best practice, keep your organization's devices and endpoints up to date.</span></span> <span data-ttu-id="af8d3-123">Kontrollera att din McAfee Endpoint Security-lösning (McAfee) är uppdaterad och att operativsystemen och apparna som din organisation använder också har de senaste uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="af8d3-123">Make sure your McAfee Endpoint Security (McAfee) solution is up to date, and that the operating systems and apps your organization is also have the latest updates.</span></span> <span data-ttu-id="af8d3-124">Om du gör det här nu kan det förhindra problem senare när du migrerar till Microsoft Defender för Endpoint och Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="af8d3-124">Doing this now can help prevent problems later as you migrate to Microsoft Defender for Endpoint and Microsoft Defender Antivirus.</span></span>

### <a name="make-sure-your-mcafee-solution-is-up-to-date"></a><span data-ttu-id="af8d3-125">Kontrollera att din McAfee-lösning är uppdaterad</span><span class="sxs-lookup"><span data-stu-id="af8d3-125">Make sure your McAfee solution is up to date</span></span>

<span data-ttu-id="af8d3-126">Håll McAfee uppdaterat och se till att din organisations enheter har de senaste säkerhetsuppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="af8d3-126">Keep McAfee up to date, and make sure that your organization's devices have the latest security updates.</span></span> <span data-ttu-id="af8d3-127">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="af8d3-127">Need help?</span></span> <span data-ttu-id="af8d3-128">Här är några McAfee-resurser:</span><span class="sxs-lookup"><span data-stu-id="af8d3-128">Here are some McAfee resources:</span></span>

- [<span data-ttu-id="af8d3-129">Dokumentation om McAfee Enterprise-produkter: Så fungerar Endpoint Security</span><span class="sxs-lookup"><span data-stu-id="af8d3-129">McAfee Enterprise Product Documentation: How Endpoint Security Works</span></span>](https://docs.mcafee.com/bundle/endpoint-security-10.7.x-common-product-guide-windows/page/GUID-1207FF39-D1D2-481F-BBD9-E4079112A8DD.html)

- [<span data-ttu-id="af8d3-130">McAfee Knowledge Center teknisk artikel: Windows Säkerhetscenter rapporterar upprepade gånger felaktigt att Endpoint Security är inaktiverat när det körs på Windows 10</span><span class="sxs-lookup"><span data-stu-id="af8d3-130">McAfee Knowledge Center Technical Article: Windows Security Center intermittently incorrectly reports that Endpoint Security is disabled when running on Windows 10</span></span>](https://kc.mcafee.com/corporate/index?page=content&id=KB91830) 

- [<span data-ttu-id="af8d3-131">McAfee Knowledge Center technical article: Windows Security Center-rapporter Slutpunktssäkerhet är inaktiverad när Endpoint Security körs</span><span class="sxs-lookup"><span data-stu-id="af8d3-131">McAfee Knowledge Center Technical Article: Windows Security Center reports Endpoint Security is disabled when Endpoint Security is running</span></span>](https://kc.mcafee.com/corporate/index?page=content&id=KB91428)

- <span data-ttu-id="af8d3-132">Din McAfee support ServicePortal ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) )</span><span class="sxs-lookup"><span data-stu-id="af8d3-132">Your McAfee support ServicePortal ([http://mysupport.mcafee.com](http://mysupport.mcafee.com))</span></span>

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a><span data-ttu-id="af8d3-133">Kontrollera att din organisations enheter är uppdaterade</span><span class="sxs-lookup"><span data-stu-id="af8d3-133">Make sure your organization's devices are up to date</span></span>

<span data-ttu-id="af8d3-134">Behöver du hjälp med att uppdatera organisationens enheter?</span><span class="sxs-lookup"><span data-stu-id="af8d3-134">Need help updating your organization's devices?</span></span> <span data-ttu-id="af8d3-135">Se följande resurser:</span><span class="sxs-lookup"><span data-stu-id="af8d3-135">See the following resources:</span></span>

|<span data-ttu-id="af8d3-136">OS</span><span class="sxs-lookup"><span data-stu-id="af8d3-136">OS</span></span> | <span data-ttu-id="af8d3-137">Resurs</span><span class="sxs-lookup"><span data-stu-id="af8d3-137">Resource</span></span> |
|:--|:--|
|<span data-ttu-id="af8d3-138">Windows</span><span class="sxs-lookup"><span data-stu-id="af8d3-138">Windows</span></span> |[<span data-ttu-id="af8d3-139">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="af8d3-139">Microsoft Update</span></span>](https://www.update.microsoft.com) |
|<span data-ttu-id="af8d3-140">macOS</span><span class="sxs-lookup"><span data-stu-id="af8d3-140">macOS</span></span> | [<span data-ttu-id="af8d3-141">Uppdatera programvaran på din Mac</span><span class="sxs-lookup"><span data-stu-id="af8d3-141">How to update the software on your Mac</span></span>](https://support.apple.com/HT201541)|
|<span data-ttu-id="af8d3-142">iOS</span><span class="sxs-lookup"><span data-stu-id="af8d3-142">iOS</span></span> |[<span data-ttu-id="af8d3-143">Uppdatera din iPhone, iPad eller iPod touch</span><span class="sxs-lookup"><span data-stu-id="af8d3-143">Update your iPhone, iPad, or iPod touch</span></span>](https://support.apple.com/HT204204)|
|<span data-ttu-id="af8d3-144">Android</span><span class="sxs-lookup"><span data-stu-id="af8d3-144">Android</span></span> |[<span data-ttu-id="af8d3-145">Kontrollera & din Android-version</span><span class="sxs-lookup"><span data-stu-id="af8d3-145">Check & update your Android version</span></span>](https://support.google.com/android/answer/7680439) |
|<span data-ttu-id="af8d3-146">Linux</span><span class="sxs-lookup"><span data-stu-id="af8d3-146">Linux</span></span> | [<span data-ttu-id="af8d3-147">Linux 101: Uppdatera ditt system</span><span class="sxs-lookup"><span data-stu-id="af8d3-147">Linux 101: Updating Your System</span></span>](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a><span data-ttu-id="af8d3-148">Skaffa Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="af8d3-148">Get Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="af8d3-149">Nu när du har uppdaterat organisationens enheter är nästa steg att skaffa Microsoft Defender för Endpoint, tilldela licenser och se till att tjänsten är uppdaterad.</span><span class="sxs-lookup"><span data-stu-id="af8d3-149">Now that you've updated your organization's devices, the next step is to get Microsoft Defender for Endpoint, assign licenses, and make sure the service is provisioned.</span></span>

1. <span data-ttu-id="af8d3-150">Köp eller prova Microsoft Defender för Slutpunkt idag.</span><span class="sxs-lookup"><span data-stu-id="af8d3-150">Buy or try Microsoft Defender for Endpoint today.</span></span> <span data-ttu-id="af8d3-151">[Påbörja en kostnadsfri utvärderingsversion eller begär en offert](https://aka.ms/mdatp).</span><span class="sxs-lookup"><span data-stu-id="af8d3-151">[Start a free trial or request a quote](https://aka.ms/mdatp).</span></span> 

2. <span data-ttu-id="af8d3-152">Kontrollera att licenserna har etablerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="af8d3-152">Verify that your licenses are properly provisioned.</span></span> <span data-ttu-id="af8d3-153">[Kontrollera licenstillståndet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state).</span><span class="sxs-lookup"><span data-stu-id="af8d3-153">[Check your license state](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state).</span></span>

3. <span data-ttu-id="af8d3-154">Konfigurera den dedikerade molninstansen av Microsoft Defender för Slutpunkt som global administratör eller säkerhetsadministratör.</span><span class="sxs-lookup"><span data-stu-id="af8d3-154">As a global administrator or security administrator, set up your dedicated cloud instance of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="af8d3-155">Se [Konfiguration av Microsoft Defender för slutpunkt: Klientorganisationskonfiguration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration).</span><span class="sxs-lookup"><span data-stu-id="af8d3-155">See [Microsoft Defender for Endpoint setup: Tenant configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration).</span></span>

4. <span data-ttu-id="af8d3-156">Om slutpunkter (till exempel enheter) i organisationen använder en proxy för att komma åt Internet kan du gå till Microsoft Defender för [Konfiguration av slutpunkt: Nätverkskonfiguration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration).</span><span class="sxs-lookup"><span data-stu-id="af8d3-156">If endpoints (such as devices) in your organization use a proxy to access the internet, see [Microsoft Defender for Endpoint setup: Network configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration).</span></span>
 
<span data-ttu-id="af8d3-157">I det här läget är du redo att ge åtkomst till dina säkerhetsadministratörer och säkerhetsoperatorer som kommer att använda Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).</span><span class="sxs-lookup"><span data-stu-id="af8d3-157">At this point, you are ready to grant access to your security administrators and security operators who will use the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)).</span></span> 

> [!NOTE]
> <span data-ttu-id="af8d3-158">Microsoft Defender Säkerhetscenter kallas ibland för Microsoft Defender för Endpoint-portalen.</span><span class="sxs-lookup"><span data-stu-id="af8d3-158">The Microsoft Defender Security Center is sometimes referred to as the Microsoft Defender for Endpoint portal.</span></span> 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a><span data-ttu-id="af8d3-159">Bevilja åtkomst till Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="af8d3-159">Grant access to the Microsoft Defender Security Center</span></span>

<span data-ttu-id="af8d3-160">I Microsoft Defender Säkerhetscenter [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () får du åtkomst till och konfigurerar funktioner i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="af8d3-160">The Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) is where you access and configure features and capabilities of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="af8d3-161">Mer information finns i [Översikt över Microsoft Defender Säkerhetscenter.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)</span><span class="sxs-lookup"><span data-stu-id="af8d3-161">To learn more, see [Overview of the Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use).</span></span>

<span data-ttu-id="af8d3-162">Behörigheter till Microsoft Defender Säkerhetscenter kan beviljas med hjälp av grundläggande behörigheter eller rollbaserad åtkomstkontroll (RBAC).</span><span class="sxs-lookup"><span data-stu-id="af8d3-162">Permissions to the Microsoft Defender Security Center can be granted by using either basic permissions or role-based access control (RBAC).</span></span> <span data-ttu-id="af8d3-163">Vi rekommenderar att du använder RBAC så att du har mer detaljerad kontroll över behörigheter.</span><span class="sxs-lookup"><span data-stu-id="af8d3-163">We recommend using RBAC so that you have more granular control over permissions.</span></span>

1. <span data-ttu-id="af8d3-164">Planera rollerna och behörigheterna för dina säkerhetsadministratörer och säkerhetsoperatorer.</span><span class="sxs-lookup"><span data-stu-id="af8d3-164">Plan the roles and permissions for your security administrators and security operators.</span></span> <span data-ttu-id="af8d3-165">Se [Rollbaserad åtkomstkontroll](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control).</span><span class="sxs-lookup"><span data-stu-id="af8d3-165">See [Role-based access control](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control).</span></span>

2. <span data-ttu-id="af8d3-166">Konfigurera och konfigurera RBAC.</span><span class="sxs-lookup"><span data-stu-id="af8d3-166">Set up and configure RBAC.</span></span> <span data-ttu-id="af8d3-167">Vi rekommenderar att du använder [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) för att konfigurera RBAC, särskilt om organisationen använder en kombination av Windows 10-, macOS-, iOS- och Android-enheter.</span><span class="sxs-lookup"><span data-stu-id="af8d3-167">We recommend using [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) to configure RBAC, especially if your organization is using a combination of Windows 10, macOS, iOS, and Android devices.</span></span> <span data-ttu-id="af8d3-168">Se [konfigurera RBAC med Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).</span><span class="sxs-lookup"><span data-stu-id="af8d3-168">See [setting up RBAC using Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).</span></span>

    <span data-ttu-id="af8d3-169">Om din organisation kräver en annan metod än Intune väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="af8d3-169">If your organization requires a method other than Intune, choose one of the following options:</span></span>
    - [<span data-ttu-id="af8d3-170">Konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="af8d3-170">Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [<span data-ttu-id="af8d3-171">Avancerad grupprinciphantering</span><span class="sxs-lookup"><span data-stu-id="af8d3-171">Advanced Group Policy Management</span></span>](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [<span data-ttu-id="af8d3-172">Administrationscenter för Windows</span><span class="sxs-lookup"><span data-stu-id="af8d3-172">Windows Admin Center</span></span>](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)

3. <span data-ttu-id="af8d3-173">Bevilja åtkomst till Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="af8d3-173">Grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="af8d3-174">(Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="af8d3-174">(Need help?</span></span> <span data-ttu-id="af8d3-175">Se [Hantera portalåtkomst med RBAC](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)).</span><span class="sxs-lookup"><span data-stu-id="af8d3-175">See [Manage portal access using RBAC](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)).</span></span>

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="af8d3-176">Konfigurera proxy- och internetanslutningsinställningar för enheter</span><span class="sxs-lookup"><span data-stu-id="af8d3-176">Configure device proxy and internet connectivity settings</span></span>

<span data-ttu-id="af8d3-177">Om du vill aktivera kommunikation mellan dina enheter och Microsoft Defender för Endpoint konfigurerar du proxy- och Internetinställningar.</span><span class="sxs-lookup"><span data-stu-id="af8d3-177">To enable communication between your devices and Microsoft Defender for Endpoint, configure proxy and internet settings.</span></span> <span data-ttu-id="af8d3-178">Följande tabell innehåller länkar till resurser som du kan använda för att konfigurera proxy- och Internetinställningar för olika operativsystem och funktioner:</span><span class="sxs-lookup"><span data-stu-id="af8d3-178">The following table includes links to resources you can use to configure your proxy and internet settings for various operating systems and capabilities:</span></span>

|<span data-ttu-id="af8d3-179">Kapaciteter</span><span class="sxs-lookup"><span data-stu-id="af8d3-179">Capabilities</span></span>  | <span data-ttu-id="af8d3-180">Operativsystem</span><span class="sxs-lookup"><span data-stu-id="af8d3-180">Operating System</span></span> | <span data-ttu-id="af8d3-181">Resurser</span><span class="sxs-lookup"><span data-stu-id="af8d3-181">Resources</span></span> |
|--|--|--|
|<span data-ttu-id="af8d3-182">[Identifiering och svar av slutpunkt](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR)</span><span class="sxs-lookup"><span data-stu-id="af8d3-182">[Endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR)</span></span> |<span data-ttu-id="af8d3-183">- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information)</span><span class="sxs-lookup"><span data-stu-id="af8d3-183">- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information)</span></span> <br/><span data-ttu-id="af8d3-184">- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span><span class="sxs-lookup"><span data-stu-id="af8d3-184">- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span></span><br/><span data-ttu-id="af8d3-185">- [Windows Server 1803 eller senare](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)</span><span class="sxs-lookup"><span data-stu-id="af8d3-185">- [Windows Server 1803 or later](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)</span></span>  |[<span data-ttu-id="af8d3-186">Konfigurera datorproxy och internetanslutningsinställningar</span><span class="sxs-lookup"><span data-stu-id="af8d3-186">Configure machine proxy and internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|<span data-ttu-id="af8d3-187">EDR</span><span class="sxs-lookup"><span data-stu-id="af8d3-187">EDR</span></span> |<span data-ttu-id="af8d3-188">- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="af8d3-188">- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)</span></span> <br/><span data-ttu-id="af8d3-189">- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)</span><span class="sxs-lookup"><span data-stu-id="af8d3-189">- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)</span></span><br/><span data-ttu-id="af8d3-190">- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)</span><span class="sxs-lookup"><span data-stu-id="af8d3-190">- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)</span></span><br/><span data-ttu-id="af8d3-191">- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)</span><span class="sxs-lookup"><span data-stu-id="af8d3-191">- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)</span></span><br/><span data-ttu-id="af8d3-192">- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)</span><span class="sxs-lookup"><span data-stu-id="af8d3-192">- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)</span></span> |[<span data-ttu-id="af8d3-193">Konfigurera proxy- och Internetanslutningsinställningar</span><span class="sxs-lookup"><span data-stu-id="af8d3-193">Configure proxy and internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|<span data-ttu-id="af8d3-194">EDR</span><span class="sxs-lookup"><span data-stu-id="af8d3-194">EDR</span></span>  |<span data-ttu-id="af8d3-195">macOS:</span><span class="sxs-lookup"><span data-stu-id="af8d3-195">macOS:</span></span> <br/><span data-ttu-id="af8d3-196">- 10.15 (Catalina)</span><span class="sxs-lookup"><span data-stu-id="af8d3-196">- 10.15 (Catalina)</span></span><br/><span data-ttu-id="af8d3-197">- 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="af8d3-197">- 10.14 (Mojave)</span></span> <br/><span data-ttu-id="af8d3-198">- 10.13 (High Sierra)</span><span class="sxs-lookup"><span data-stu-id="af8d3-198">- 10.13 (High Sierra)</span></span>  |[<span data-ttu-id="af8d3-199">Microsoft Defender för Slutpunkt för Mac: Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="af8d3-199">Microsoft Defender for Endpoint for Mac: Network connections</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[<span data-ttu-id="af8d3-200">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="af8d3-200">Microsoft Defender Antivirus</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |<span data-ttu-id="af8d3-201">- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information)</span><span class="sxs-lookup"><span data-stu-id="af8d3-201">- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information)</span></span> <br/><span data-ttu-id="af8d3-202">- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span><span class="sxs-lookup"><span data-stu-id="af8d3-202">- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span></span><br/><span data-ttu-id="af8d3-203">- [Windows Server 1803 eller senare](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)</span><span class="sxs-lookup"><span data-stu-id="af8d3-203">- [Windows Server 1803 or later](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)</span></span> <br/><span data-ttu-id="af8d3-204">- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="af8d3-204">- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016)</span></span> |[<span data-ttu-id="af8d3-205">Konfigurera och validera nätverksanslutningar för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="af8d3-205">Configure and validate Microsoft Defender Antivirus network connections</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|<span data-ttu-id="af8d3-206">Antivirus</span><span class="sxs-lookup"><span data-stu-id="af8d3-206">Antivirus</span></span> |<span data-ttu-id="af8d3-207">macOS:</span><span class="sxs-lookup"><span data-stu-id="af8d3-207">macOS:</span></span> <br/><span data-ttu-id="af8d3-208">- 10.15 (Catalina)</span><span class="sxs-lookup"><span data-stu-id="af8d3-208">- 10.15 (Catalina)</span></span><br/><span data-ttu-id="af8d3-209">- 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="af8d3-209">- 10.14 (Mojave)</span></span> <br/><span data-ttu-id="af8d3-210">- 10.13 (High Sierra)</span><span class="sxs-lookup"><span data-stu-id="af8d3-210">- 10.13 (High Sierra)</span></span> |[<span data-ttu-id="af8d3-211">Microsoft Defender för Slutpunkt för Mac: Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="af8d3-211">Microsoft Defender for Endpoint for Mac: Network connections</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|<span data-ttu-id="af8d3-212">Antivirus</span><span class="sxs-lookup"><span data-stu-id="af8d3-212">Antivirus</span></span> |<span data-ttu-id="af8d3-213">Linux:</span><span class="sxs-lookup"><span data-stu-id="af8d3-213">Linux:</span></span> <br/><span data-ttu-id="af8d3-214">- RHEL 7,2+</span><span class="sxs-lookup"><span data-stu-id="af8d3-214">- RHEL 7.2+</span></span><br/><span data-ttu-id="af8d3-215">- CentOS Linux 7.2+</span><span class="sxs-lookup"><span data-stu-id="af8d3-215">- CentOS Linux 7.2+</span></span><br/><span data-ttu-id="af8d3-216">- Ubuntu 16 LTS, eller senare LTS</span><span class="sxs-lookup"><span data-stu-id="af8d3-216">- Ubuntu 16 LTS, or higher LTS</span></span><br/><span data-ttu-id="af8d3-217">- SLES 12+</span><span class="sxs-lookup"><span data-stu-id="af8d3-217">- SLES 12+</span></span><br/><span data-ttu-id="af8d3-218">- Till och med 9+</span><span class="sxs-lookup"><span data-stu-id="af8d3-218">- Debian 9+</span></span><br/><span data-ttu-id="af8d3-219">- Oracle Linux 7.2</span><span class="sxs-lookup"><span data-stu-id="af8d3-219">- Oracle Linux 7.2</span></span> |[<span data-ttu-id="af8d3-220">Microsoft Defender för Slutpunkt för Linux: Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="af8d3-220">Microsoft Defender for Endpoint for Linux: Network connections</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections) 

## <a name="next-step"></a><span data-ttu-id="af8d3-221">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="af8d3-221">Next step</span></span>

<span data-ttu-id="af8d3-222">**Grattis!**</span><span class="sxs-lookup"><span data-stu-id="af8d3-222">**Congratulations**!</span></span> <span data-ttu-id="af8d3-223">Du har slutfört **förberedelsefasen** av [migreringen från McAfee till Microsoft Defender för Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)!</span><span class="sxs-lookup"><span data-stu-id="af8d3-223">You have completed the **Prepare** phase of [migrating from McAfee to Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)!</span></span>

- <span data-ttu-id="af8d3-224">[Fortsätt att konfigurera Microsoft Defender för Slutpunkt](mcafee-to-microsoft-defender-setup.md).</span><span class="sxs-lookup"><span data-stu-id="af8d3-224">[Proceed to set up Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-setup.md).</span></span>