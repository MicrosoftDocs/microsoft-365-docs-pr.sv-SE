---
title: Växla till Microsoft Defender för slutpunkt – förbereda
description: Det här är fas 1, Förbereda, för migrering till Microsoft Defender för Endpoint.
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
- m365solution-migratetomdatp
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: d5339ce795bff1451d6f4caaf37de39f996890be
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185533"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a><span data-ttu-id="75645-104">Byt till Microsoft Defender för slutpunkt – fas 1: Förbereda</span><span class="sxs-lookup"><span data-stu-id="75645-104">Switch to Microsoft Defender for Endpoint - Phase 1: Prepare</span></span>

<span data-ttu-id="75645-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="75645-105">**Applies to:**</span></span>
- [<span data-ttu-id="75645-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="75645-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="75645-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75645-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![Fas 1: Förbereda](images/phase-diagrams/prepare.png)<br/><span data-ttu-id="75645-109">Fas 1: Förbereda</span><span class="sxs-lookup"><span data-stu-id="75645-109">Phase 1: Prepare</span></span> | <span data-ttu-id="75645-110">[![Fas 2: Konfigurera](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)</span><span class="sxs-lookup"><span data-stu-id="75645-110">[![Phase 2: Set up](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)</span></span><br/>[<span data-ttu-id="75645-111">Fas 2: Konfigurera</span><span class="sxs-lookup"><span data-stu-id="75645-111">Phase 2: Set up</span></span>](switch-to-microsoft-defender-setup.md) | <span data-ttu-id="75645-112">[![Fas 3: Introduktion](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)</span><span class="sxs-lookup"><span data-stu-id="75645-112">[![Phase 3: Onboard](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)</span></span><br/>[<span data-ttu-id="75645-113">Fas 3: Introduktion</span><span class="sxs-lookup"><span data-stu-id="75645-113">Phase 3: Onboard</span></span>](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
|<span data-ttu-id="75645-114">*Du är här!*</span><span class="sxs-lookup"><span data-stu-id="75645-114">*You are here!*</span></span>| | |

<span data-ttu-id="75645-115">**Välkommen till förberedelsefasen för [att byta till Microsoft Defender för slutpunkt.](switch-to-microsoft-defender-migration.md#the-migration-process)**</span><span class="sxs-lookup"><span data-stu-id="75645-115">**Welcome to the Prepare phase of [switching to Microsoft Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)**.</span></span> 

<span data-ttu-id="75645-116">Den här migreringsfasen omfattar följande steg:</span><span class="sxs-lookup"><span data-stu-id="75645-116">This migration phase includes the following steps:</span></span>
1. [<span data-ttu-id="75645-117">Hämta och distribuera uppdateringar på organisationens enheter</span><span class="sxs-lookup"><span data-stu-id="75645-117">Get and deploy updates across your organization's devices</span></span>](#get-and-deploy-updates-across-your-organizations-devices)
2. <span data-ttu-id="75645-118">[Skaffa Microsoft Defender för Slutpunkt](#get-microsoft-defender-for-endpoint).</span><span class="sxs-lookup"><span data-stu-id="75645-118">[Get Microsoft Defender for Endpoint](#get-microsoft-defender-for-endpoint).</span></span>
3. <span data-ttu-id="75645-119">[Bevilja åtkomst till Microsoft Defender Säkerhetscenter.](#grant-access-to-the-microsoft-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="75645-119">[Grant access to the Microsoft Defender Security Center](#grant-access-to-the-microsoft-defender-security-center).</span></span>
4. <span data-ttu-id="75645-120">[Konfigurera enhetsproxy och internetanslutningsinställningar](#configure-device-proxy-and-internet-connectivity-settings).</span><span class="sxs-lookup"><span data-stu-id="75645-120">[Configure device proxy and internet connectivity settings](#configure-device-proxy-and-internet-connectivity-settings).</span></span>

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a><span data-ttu-id="75645-121">Hämta och distribuera uppdateringar på organisationens enheter</span><span class="sxs-lookup"><span data-stu-id="75645-121">Get and deploy updates across your organization's devices</span></span>

<span data-ttu-id="75645-122">Det är alltid bra att hålla organisationens enheter och slutpunkter uppdaterade.</span><span class="sxs-lookup"><span data-stu-id="75645-122">As a best practice, keep your organization's devices and endpoints up to date.</span></span> <span data-ttu-id="75645-123">Kontrollera att din befintliga slutpunktsskydd och antiviruslösning är uppdaterade och att operativsystemen och apparna som din organisation använder också har de senaste uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="75645-123">Make sure your existing endpoint protection and antivirus solution is up to date, and that the operating systems and apps your organization is also have the latest updates.</span></span> <span data-ttu-id="75645-124">Om du gör det här nu kan det förhindra problem senare när du migrerar till Microsoft Defender för Endpoint och Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="75645-124">Doing this now can help prevent problems later as you migrate to Microsoft Defender for Endpoint and Microsoft Defender Antivirus.</span></span>

### <a name="make-sure-your-existing-solution-is-up-to-date"></a><span data-ttu-id="75645-125">Kontrollera att din befintliga lösning är uppdaterad</span><span class="sxs-lookup"><span data-stu-id="75645-125">Make sure your existing solution is up to date</span></span>

<span data-ttu-id="75645-126">Håll din befintliga lösning för slutpunktsskydd uppdaterad och kontrollera att din organisations enheter har de senaste säkerhetsuppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="75645-126">Keep your existing endpoint protection solution up to date, and make sure that your organization's devices have the latest security updates.</span></span> 

<span data-ttu-id="75645-127">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="75645-127">Need help?</span></span> <span data-ttu-id="75645-128">Se din lösningsleverantörs dokumentation.</span><span class="sxs-lookup"><span data-stu-id="75645-128">See your solution provider's documentation.</span></span>

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a><span data-ttu-id="75645-129">Kontrollera att din organisations enheter är uppdaterade</span><span class="sxs-lookup"><span data-stu-id="75645-129">Make sure your organization's devices are up to date</span></span>

<span data-ttu-id="75645-130">Behöver du hjälp med att uppdatera organisationens enheter?</span><span class="sxs-lookup"><span data-stu-id="75645-130">Need help updating your organization's devices?</span></span> <span data-ttu-id="75645-131">Se följande resurser:</span><span class="sxs-lookup"><span data-stu-id="75645-131">See the following resources:</span></span>

|<span data-ttu-id="75645-132">OS</span><span class="sxs-lookup"><span data-stu-id="75645-132">OS</span></span> | <span data-ttu-id="75645-133">Resurs</span><span class="sxs-lookup"><span data-stu-id="75645-133">Resource</span></span> |
|:--|:--|
|<span data-ttu-id="75645-134">Windows</span><span class="sxs-lookup"><span data-stu-id="75645-134">Windows</span></span> |[<span data-ttu-id="75645-135">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="75645-135">Microsoft Update</span></span>](https://www.update.microsoft.com) |
|<span data-ttu-id="75645-136">macOS</span><span class="sxs-lookup"><span data-stu-id="75645-136">macOS</span></span> | [<span data-ttu-id="75645-137">Uppdatera programvaran på din Mac</span><span class="sxs-lookup"><span data-stu-id="75645-137">How to update the software on your Mac</span></span>](https://support.apple.com/HT201541)|
|<span data-ttu-id="75645-138">iOS</span><span class="sxs-lookup"><span data-stu-id="75645-138">iOS</span></span> |[<span data-ttu-id="75645-139">Uppdatera din iPhone, iPad eller iPod touch</span><span class="sxs-lookup"><span data-stu-id="75645-139">Update your iPhone, iPad, or iPod touch</span></span>](https://support.apple.com/HT204204)|
|<span data-ttu-id="75645-140">Android</span><span class="sxs-lookup"><span data-stu-id="75645-140">Android</span></span> |[<span data-ttu-id="75645-141">Kontrollera & din Android-version</span><span class="sxs-lookup"><span data-stu-id="75645-141">Check & update your Android version</span></span>](https://support.google.com/android/answer/7680439) |
|<span data-ttu-id="75645-142">Linux</span><span class="sxs-lookup"><span data-stu-id="75645-142">Linux</span></span> | [<span data-ttu-id="75645-143">Linux 101: Uppdatera ditt system</span><span class="sxs-lookup"><span data-stu-id="75645-143">Linux 101: Updating Your System</span></span>](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a><span data-ttu-id="75645-144">Skaffa Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="75645-144">Get Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="75645-145">Nu när du har uppdaterat organisationens enheter är nästa steg att skaffa Microsoft Defender för Endpoint, tilldela licenser och se till att tjänsten är uppdaterad.</span><span class="sxs-lookup"><span data-stu-id="75645-145">Now that you've updated your organization's devices, the next step is to get Microsoft Defender for Endpoint, assign licenses, and make sure the service is provisioned.</span></span>

1. <span data-ttu-id="75645-146">Köp eller prova Microsoft Defender för Slutpunkt idag.</span><span class="sxs-lookup"><span data-stu-id="75645-146">Buy or try Microsoft Defender for Endpoint today.</span></span> <span data-ttu-id="75645-147">[Påbörja en kostnadsfri utvärderingsversion eller begär en offert](https://aka.ms/mdatp).</span><span class="sxs-lookup"><span data-stu-id="75645-147">[Start a free trial or request a quote](https://aka.ms/mdatp).</span></span> 
2. <span data-ttu-id="75645-148">Kontrollera att licenserna har etablerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="75645-148">Verify that your licenses are properly provisioned.</span></span> <span data-ttu-id="75645-149">[Kontrollera licenstillståndet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state).</span><span class="sxs-lookup"><span data-stu-id="75645-149">[Check your license state](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state).</span></span>
3. <span data-ttu-id="75645-150">Konfigurera den dedikerade molninstansen av Microsoft Defender för Slutpunkt som global administratör eller säkerhetsadministratör.</span><span class="sxs-lookup"><span data-stu-id="75645-150">As a global administrator or security administrator, set up your dedicated cloud instance of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="75645-151">Se [Konfiguration av Microsoft Defender för slutpunkt: Klientorganisationskonfiguration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration).</span><span class="sxs-lookup"><span data-stu-id="75645-151">See [Microsoft Defender for Endpoint setup: Tenant configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration).</span></span>
4. <span data-ttu-id="75645-152">Om slutpunkter (till exempel enheter) i organisationen använder en proxy för att komma åt Internet kan du gå till Microsoft Defender för [Konfiguration av slutpunkt: Nätverkskonfiguration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration).</span><span class="sxs-lookup"><span data-stu-id="75645-152">If endpoints (such as devices) in your organization use a proxy to access the internet, see [Microsoft Defender for Endpoint setup: Network configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration).</span></span>
 
<span data-ttu-id="75645-153">I det här läget är du redo att ge åtkomst till dina säkerhetsadministratörer och säkerhetsoperatorer som kommer att använda Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).</span><span class="sxs-lookup"><span data-stu-id="75645-153">At this point, you are ready to grant access to your security administrators and security operators who will use the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)).</span></span> 

> [!NOTE]
> <span data-ttu-id="75645-154">Microsoft Defender Säkerhetscenter kallas ibland för Microsoft Defender för Endpoint-portalen och kan nås på [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) .</span><span class="sxs-lookup"><span data-stu-id="75645-154">The Microsoft Defender Security Center is sometimes referred to as the Microsoft Defender for Endpoint portal, and can be accessed at [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal).</span></span> 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a><span data-ttu-id="75645-155">Bevilja åtkomst till Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="75645-155">Grant access to the Microsoft Defender Security Center</span></span>

<span data-ttu-id="75645-156">I Microsoft Defender Säkerhetscenter [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () får du åtkomst till och konfigurerar funktioner i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="75645-156">The Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) is where you access and configure features and capabilities of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="75645-157">Mer information finns i [Översikt över Microsoft Defender Säkerhetscenter.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)</span><span class="sxs-lookup"><span data-stu-id="75645-157">To learn more, see [Overview of the Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use).</span></span>

<span data-ttu-id="75645-158">Behörigheter till Microsoft Defender Säkerhetscenter kan beviljas med hjälp av grundläggande behörigheter eller rollbaserad åtkomstkontroll (RBAC).</span><span class="sxs-lookup"><span data-stu-id="75645-158">Permissions to the Microsoft Defender Security Center can be granted by using either basic permissions or role-based access control (RBAC).</span></span> <span data-ttu-id="75645-159">Vi rekommenderar att du använder RBAC så att du har mer detaljerad kontroll över behörigheter.</span><span class="sxs-lookup"><span data-stu-id="75645-159">We recommend using RBAC so that you have more granular control over permissions.</span></span>

1. <span data-ttu-id="75645-160">Planera rollerna och behörigheterna för dina säkerhetsadministratörer och säkerhetsoperatorer.</span><span class="sxs-lookup"><span data-stu-id="75645-160">Plan the roles and permissions for your security administrators and security operators.</span></span> <span data-ttu-id="75645-161">Se [Rollbaserad åtkomstkontroll](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control).</span><span class="sxs-lookup"><span data-stu-id="75645-161">See [Role-based access control](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control).</span></span>
2. <span data-ttu-id="75645-162">Konfigurera och konfigurera RBAC.</span><span class="sxs-lookup"><span data-stu-id="75645-162">Set up and configure RBAC.</span></span> <span data-ttu-id="75645-163">Vi rekommenderar att du använder [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) för att konfigurera RBAC, särskilt om organisationen använder en kombination av Windows 10-, macOS-, iOS- och Android-enheter.</span><span class="sxs-lookup"><span data-stu-id="75645-163">We recommend using [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) to configure RBAC, especially if your organization is using a combination of Windows 10, macOS, iOS, and Android devices.</span></span> <span data-ttu-id="75645-164">Se [konfigurera RBAC med Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).</span><span class="sxs-lookup"><span data-stu-id="75645-164">See [setting up RBAC using Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).</span></span>
    <span data-ttu-id="75645-165">Om din organisation kräver en annan metod än Intune väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="75645-165">If your organization requires a method other than Intune, choose one of the following options:</span></span>
    - [<span data-ttu-id="75645-166">Konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="75645-166">Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [<span data-ttu-id="75645-167">Avancerad grupprinciphantering</span><span class="sxs-lookup"><span data-stu-id="75645-167">Advanced Group Policy Management</span></span>](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [<span data-ttu-id="75645-168">Administrationscenter för Windows</span><span class="sxs-lookup"><span data-stu-id="75645-168">Windows Admin Center</span></span>](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)
3. <span data-ttu-id="75645-169">Bevilja åtkomst till Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="75645-169">Grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="75645-170">(Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="75645-170">(Need help?</span></span> <span data-ttu-id="75645-171">Se [Hantera portalåtkomst med RBAC](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)).</span><span class="sxs-lookup"><span data-stu-id="75645-171">See [Manage portal access using RBAC](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)).</span></span>

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="75645-172">Konfigurera proxy- och internetanslutningsinställningar för enheter</span><span class="sxs-lookup"><span data-stu-id="75645-172">Configure device proxy and internet connectivity settings</span></span>

<span data-ttu-id="75645-173">Om du vill aktivera kommunikation mellan dina enheter och Microsoft Defender för Endpoint konfigurerar du proxy- och Internetinställningar.</span><span class="sxs-lookup"><span data-stu-id="75645-173">To enable communication between your devices and Microsoft Defender for Endpoint, configure proxy and internet settings.</span></span> <span data-ttu-id="75645-174">Följande tabell innehåller länkar till resurser som du kan använda för att konfigurera proxy- och Internetinställningar för olika operativsystem och funktioner:</span><span class="sxs-lookup"><span data-stu-id="75645-174">The following table includes links to resources you can use to configure your proxy and internet settings for various operating systems and capabilities:</span></span>

|<span data-ttu-id="75645-175">Kapaciteter</span><span class="sxs-lookup"><span data-stu-id="75645-175">Capabilities</span></span>  | <span data-ttu-id="75645-176">Operativsystem</span><span class="sxs-lookup"><span data-stu-id="75645-176">Operating System</span></span> | <span data-ttu-id="75645-177">Resurser</span><span class="sxs-lookup"><span data-stu-id="75645-177">Resources</span></span> |
|--|--|--|
|<span data-ttu-id="75645-178">[Identifiering och svar av slutpunkt](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR)</span><span class="sxs-lookup"><span data-stu-id="75645-178">[Endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR)</span></span> |<span data-ttu-id="75645-179">- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information)</span><span class="sxs-lookup"><span data-stu-id="75645-179">- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information)</span></span> <br/><span data-ttu-id="75645-180">- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span><span class="sxs-lookup"><span data-stu-id="75645-180">- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span></span><br/><span data-ttu-id="75645-181">- [Windows Server 1803 eller senare](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)</span><span class="sxs-lookup"><span data-stu-id="75645-181">- [Windows Server 1803 or later](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)</span></span>  |[<span data-ttu-id="75645-182">Konfigurera datorproxy och internetanslutningsinställningar</span><span class="sxs-lookup"><span data-stu-id="75645-182">Configure machine proxy and internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|<span data-ttu-id="75645-183">EDR</span><span class="sxs-lookup"><span data-stu-id="75645-183">EDR</span></span> |<span data-ttu-id="75645-184">- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="75645-184">- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)</span></span> <br/><span data-ttu-id="75645-185">- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)</span><span class="sxs-lookup"><span data-stu-id="75645-185">- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)</span></span><br/><span data-ttu-id="75645-186">- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)</span><span class="sxs-lookup"><span data-stu-id="75645-186">- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)</span></span><br/><span data-ttu-id="75645-187">- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)</span><span class="sxs-lookup"><span data-stu-id="75645-187">- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)</span></span><br/><span data-ttu-id="75645-188">- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)</span><span class="sxs-lookup"><span data-stu-id="75645-188">- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)</span></span> |[<span data-ttu-id="75645-189">Konfigurera proxy- och Internetanslutningsinställningar</span><span class="sxs-lookup"><span data-stu-id="75645-189">Configure proxy and internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|<span data-ttu-id="75645-190">EDR</span><span class="sxs-lookup"><span data-stu-id="75645-190">EDR</span></span>  |<span data-ttu-id="75645-191">macOS:</span><span class="sxs-lookup"><span data-stu-id="75645-191">macOS:</span></span> <br/><span data-ttu-id="75645-192">- 10.15 (Catalina)</span><span class="sxs-lookup"><span data-stu-id="75645-192">- 10.15 (Catalina)</span></span><br/><span data-ttu-id="75645-193">- 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="75645-193">- 10.14 (Mojave)</span></span> <br/><span data-ttu-id="75645-194">- 10.13 (High Sierra)</span><span class="sxs-lookup"><span data-stu-id="75645-194">- 10.13 (High Sierra)</span></span>  |[<span data-ttu-id="75645-195">Microsoft Defender för Slutpunkt för Mac: Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="75645-195">Microsoft Defender for Endpoint for Mac: Network connections</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[<span data-ttu-id="75645-196">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="75645-196">Microsoft Defender Antivirus</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |<span data-ttu-id="75645-197">- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information)</span><span class="sxs-lookup"><span data-stu-id="75645-197">- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information)</span></span> <br/><span data-ttu-id="75645-198">- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span><span class="sxs-lookup"><span data-stu-id="75645-198">- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span></span><br/><span data-ttu-id="75645-199">- [Windows Server 1803 eller senare](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)</span><span class="sxs-lookup"><span data-stu-id="75645-199">- [Windows Server 1803 or later](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)</span></span> <br/><span data-ttu-id="75645-200">- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="75645-200">- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016)</span></span> |[<span data-ttu-id="75645-201">Konfigurera och validera nätverksanslutningar för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="75645-201">Configure and validate Microsoft Defender Antivirus network connections</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|<span data-ttu-id="75645-202">Antivirus</span><span class="sxs-lookup"><span data-stu-id="75645-202">Antivirus</span></span> |<span data-ttu-id="75645-203">macOS:</span><span class="sxs-lookup"><span data-stu-id="75645-203">macOS:</span></span> <br/><span data-ttu-id="75645-204">- 10.15 (Catalina)</span><span class="sxs-lookup"><span data-stu-id="75645-204">- 10.15 (Catalina)</span></span><br/><span data-ttu-id="75645-205">- 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="75645-205">- 10.14 (Mojave)</span></span> <br/><span data-ttu-id="75645-206">- 10.13 (High Sierra)</span><span class="sxs-lookup"><span data-stu-id="75645-206">- 10.13 (High Sierra)</span></span> |[<span data-ttu-id="75645-207">Microsoft Defender för Slutpunkt för Mac: Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="75645-207">Microsoft Defender for Endpoint for Mac: Network connections</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|<span data-ttu-id="75645-208">Antivirus</span><span class="sxs-lookup"><span data-stu-id="75645-208">Antivirus</span></span> |<span data-ttu-id="75645-209">Linux:</span><span class="sxs-lookup"><span data-stu-id="75645-209">Linux:</span></span> <br/><span data-ttu-id="75645-210">- RHEL 7,2+</span><span class="sxs-lookup"><span data-stu-id="75645-210">- RHEL 7.2+</span></span><br/><span data-ttu-id="75645-211">- CentOS Linux 7.2+</span><span class="sxs-lookup"><span data-stu-id="75645-211">- CentOS Linux 7.2+</span></span><br/><span data-ttu-id="75645-212">- Ubuntu 16 LTS, eller senare LTS</span><span class="sxs-lookup"><span data-stu-id="75645-212">- Ubuntu 16 LTS, or higher LTS</span></span><br/><span data-ttu-id="75645-213">- SLES 12+</span><span class="sxs-lookup"><span data-stu-id="75645-213">- SLES 12+</span></span><br/><span data-ttu-id="75645-214">- Till och med 9+</span><span class="sxs-lookup"><span data-stu-id="75645-214">- Debian 9+</span></span><br/><span data-ttu-id="75645-215">- Oracle Linux 7.2</span><span class="sxs-lookup"><span data-stu-id="75645-215">- Oracle Linux 7.2</span></span> |[<span data-ttu-id="75645-216">Microsoft Defender för Slutpunkt för Linux: Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="75645-216">Microsoft Defender for Endpoint for Linux: Network connections</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections) |

## <a name="next-step"></a><span data-ttu-id="75645-217">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="75645-217">Next step</span></span>

<span data-ttu-id="75645-218">**Grattis!**</span><span class="sxs-lookup"><span data-stu-id="75645-218">**Congratulations**!</span></span> <span data-ttu-id="75645-219">Du har slutfört **förberedelsefasen** för [att byta till Microsoft Defender för slutpunkt!](switch-to-microsoft-defender-migration.md#the-migration-process)</span><span class="sxs-lookup"><span data-stu-id="75645-219">You have completed the **Prepare** phase of [switching to Microsoft Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)!</span></span>

- <span data-ttu-id="75645-220">[Fortsätt att konfigurera Microsoft Defender för Slutpunkt](switch-to-microsoft-defender-setup.md).</span><span class="sxs-lookup"><span data-stu-id="75645-220">[Proceed to set up Microsoft Defender for Endpoint](switch-to-microsoft-defender-setup.md).</span></span>