---
title: Konfigurera infrastrukturen för distansarbete med Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
- M365initiative-coredeploy
ms.custom: seo-marvel-jun2020
keywords: arbeta hemifrån, arbeta-hemifrån, distansarbetare, hybridarbete, distansmedarbetare, hybridanslutning, fjärråtkomst, distansarbete, distansarbeta, distansarbete, mobilt arbete, distansarbete, arbeta var som helst, flexibel arbetsplats
description: Gå igenom infrastrukturens delar så att distansmedarbetarna har säker åtkomst till lokala resurser samt resurser från Microsoft 365.
ms.openlocfilehash: 1a8cf471cf92e1301c231f395ed0238bb35359cb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246326"
---
# <a name="set-up-your-infrastructure-for-remote-work-with-microsoft-365"></a><span data-ttu-id="ba883-104">Konfigurera infrastrukturen för distansarbete med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ba883-104">Set up your infrastructure for remote work with Microsoft 365</span></span>

<span data-ttu-id="ba883-105">För att säkra och optimera distansarbetares produktivitet och samarbete måste du konfigurera IT- och molninfrastrukturen för att aktivera fjärrarbete och ge åtkomst till organisationens lokala och molnbaserade information, verktyg och resurser.</span><span class="sxs-lookup"><span data-stu-id="ba883-105">To secure and optimize your remote worker’s productivity and collaboration, you need to configure your IT and cloud infrastructure to enable remote work and to provide access to your organization's on-premises and cloud-based information, tools, and resources.</span></span> <span data-ttu-id="ba883-106">Den här lösningen går igenom distributionen av viktiga delar av infrastruktur som ger dina medarbetare möjlighet att arbeta på så bra som möjligt, oavsett var de befinner sig.</span><span class="sxs-lookup"><span data-stu-id="ba883-106">This solution steps through the deployment of key layers of infrastructure that empower your workers to do their best work, wherever they are.</span></span>

<span data-ttu-id="ba883-107">Att låta arbetarna arbeta utanför kontoret är viktigt för många organisationer för att:</span><span class="sxs-lookup"><span data-stu-id="ba883-107">Allowing workers to work away from the office is important for many organizations to:</span></span>

- <span data-ttu-id="ba883-108">Spara på kontorsutrymme.</span><span class="sxs-lookup"><span data-stu-id="ba883-108">Save on office space.</span></span>
- <span data-ttu-id="ba883-109">Anställa och behålla arbetare som inte vill omlokalisera.</span><span class="sxs-lookup"><span data-stu-id="ba883-109">Hire and retain workers who are unwilling to relocate.</span></span>
- <span data-ttu-id="ba883-110">Minska pendlingstid för arbetare vilket ger de mer tid att vara produktiva och kunna utföra stressminskande aktiviteter utanför arbetet.</span><span class="sxs-lookup"><span data-stu-id="ba883-110">Reduce worker commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.</span></span>

<span data-ttu-id="ba883-111">Microsoft 365 har förmågan att låta dina medarbetare att arbeta på distans.</span><span class="sxs-lookup"><span data-stu-id="ba883-111">Microsoft 365 has the capabilities to empower your workers to work remotely.</span></span>

![Underlätta för distansarbetare med Microsoft 365](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

>[!Note]
><span data-ttu-id="ba883-113">Om du är ny på Microsoft 365, se [de här resurserna](https://www.microsoft.com/microsoft-365).</span><span class="sxs-lookup"><span data-stu-id="ba883-113">If you are new to Microsoft 365, see [these resources](https://www.microsoft.com/microsoft-365).</span></span>
>

<span data-ttu-id="ba883-114">Titta på den här videon för att få en översikt över distributionsprocessen.</span><span class="sxs-lookup"><span data-stu-id="ba883-114">Watch this video for an overview of the deployment process.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

<span data-ttu-id="ba883-115">För IT-proffs som hanterar plats- och molnbaserad infrastruktur för att möjliggöra arbetsproduktiviteten, erbjuder denna lösning följande viktiga funktioner:</span><span class="sxs-lookup"><span data-stu-id="ba883-115">For IT professionals managing onsite and cloud-based infrastructure to enable worker productivity, this solution provides these key capabilities:</span></span>

- <span data-ttu-id="ba883-116">Ansluten</span><span class="sxs-lookup"><span data-stu-id="ba883-116">Connected</span></span>

  <span data-ttu-id="ba883-117">Oavsett tid och plats kan distansarbetare komma åt:</span><span class="sxs-lookup"><span data-stu-id="ba883-117">From anywhere in the world and at any time, remote workers are able to access:</span></span> 

  - <span data-ttu-id="ba883-118">Molnbaserade tjänster och data i din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="ba883-118">Cloud-based services and data in your Microsoft 365 subscription.</span></span> 

  - <span data-ttu-id="ba883-119">Organisationsresurser av samma slag som finns att tillgå med programdatacentraler på plats.</span><span class="sxs-lookup"><span data-stu-id="ba883-119">Organization resources, such those offered by on-premises application datacenters.</span></span>

- <span data-ttu-id="ba883-120">Säker</span><span class="sxs-lookup"><span data-stu-id="ba883-120">Secure</span></span>

  <span data-ttu-id="ba883-121">Inloggningarna skyddas med multifaktorautentisering (MFA) och inbyggda säkerhetsfunktioner i Microsoft 365 och Windows 10 skyddar mot skadlig programvara, skadliga attacker och dataförluster.</span><span class="sxs-lookup"><span data-stu-id="ba883-121">Sign-ins are secured with multi-factor authentication (MFA) and built-in security features of Microsoft 365 and Windows 10 protect against malware, malicious attacks, and data loss.</span></span>

- <span data-ttu-id="ba883-122">Hanteras</span><span class="sxs-lookup"><span data-stu-id="ba883-122">Managed</span></span>

  <span data-ttu-id="ba883-123">Din distansarbetares enheter kan hanteras från molnet med säkerhetsinställningar, tillåtna appar och för att kräva överensstämmelse med systemsäkerheten.</span><span class="sxs-lookup"><span data-stu-id="ba883-123">Your remote worker's devices can be managed from the cloud with security settings, allowed apps, and to require compliance with system health.</span></span>

- <span data-ttu-id="ba883-124">Samarbetsvilliga och produktiva</span><span class="sxs-lookup"><span data-stu-id="ba883-124">Collaborative and productive</span></span>

  <span data-ttu-id="ba883-125">Dina distansarbetare kan vara lika produktiva som på plats på ett mycket samarbetande sätt med:</span><span class="sxs-lookup"><span data-stu-id="ba883-125">Your remote workers can be as productive as on-premises in a highly collaborative way with:</span></span>

  - <span data-ttu-id="ba883-126">Onlinemöten och chattsessioner med Teams.</span><span class="sxs-lookup"><span data-stu-id="ba883-126">Online meetings and chat sessions with Teams.</span></span> 

  - <span data-ttu-id="ba883-127">Delade arbetsytor för molnbaserad fillagring med global tillgänglighet och samarbete i realtid med SharePoint och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ba883-127">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration with SharePoint and OneDrive.</span></span>

  - <span data-ttu-id="ba883-128">Delade uppgifter och arbetsflöden för att dela upp arbetet och få saker gjorda.</span><span class="sxs-lookup"><span data-stu-id="ba883-128">Shared tasks and workflows to divide up the work and get things done.</span></span> 

<span data-ttu-id="ba883-129">För smidig inloggning lokalt bör dina användarkonton i Active Directory Domain Services (AD DS) synkroniseras med Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="ba883-129">For a seamless sign-in experience, your on-premises Active Directory Domain Services (AD DS) user accounts should be synchronized with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="ba883-130">För att skydda dina Windows 10-enheter bör de registreras i Intune.</span><span class="sxs-lookup"><span data-stu-id="ba883-130">To protect your Windows 10 devices, they should be enrolled in Intune.</span></span> <span data-ttu-id="ba883-131">Här är en övergripande vy över infrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="ba883-131">Here is a high-level view of the infrastructure.</span></span>

![Grundläggande infrastruktur för distansarbetare som använder Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

<span data-ttu-id="ba883-133">Använd de här Microsoft 365-funktionerna om du vill aktivera funktionerna i Microsoft 365 för dina distansarbetare.</span><span class="sxs-lookup"><span data-stu-id="ba883-133">To enable the capabilities of Microsoft 365 for your remote workers, use these Microsoft 365 features.</span></span>

| <span data-ttu-id="ba883-134">Resurs eller funktion</span><span class="sxs-lookup"><span data-stu-id="ba883-134">Capability or feature</span></span> | <span data-ttu-id="ba883-135">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ba883-135">Description</span></span> | <span data-ttu-id="ba883-136">Licensiering</span><span class="sxs-lookup"><span data-stu-id="ba883-136">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="ba883-137">MFA som förstärks med säkerhetsstandarder</span><span class="sxs-lookup"><span data-stu-id="ba883-137">MFA enforced with security defaults</span></span>   | <span data-ttu-id="ba883-138">Skydda er mot identitetsstölder och komprometterade enheter genom att kräva en andra form av autentisering vid inloggning. Säkerhetsstandarderna kräver MFA för alla användarkonton.</span><span class="sxs-lookup"><span data-stu-id="ba883-138">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="ba883-139">Microsoft 365 E3 eller E5</span><span class="sxs-lookup"><span data-stu-id="ba883-139">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="ba883-140">MFA som förstärks med villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="ba883-140">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="ba883-141">Använd villkorsstyrda åtkomstprinciper för att kräva MFA baserat på egenskaperna för inloggningen.</span><span class="sxs-lookup"><span data-stu-id="ba883-141">Require MFA based on the properties of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="ba883-142">Microsoft 365 E3 eller E5</span><span class="sxs-lookup"><span data-stu-id="ba883-142">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="ba883-143">MFA som förstärks med riskbaserad villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="ba883-143">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="ba883-144">Använd Microsoft Defender for Identity för att kräva MFA baserat på risken som är kopplad till användarens inloggning.</span><span class="sxs-lookup"><span data-stu-id="ba883-144">Require MFA based on the risk of the user sign-in with Microsoft Defender for Identity.</span></span> | <span data-ttu-id="ba883-145">Microsoft 365 E5 eller E3 med Azure AD Premium P2-licenser</span><span class="sxs-lookup"><span data-stu-id="ba883-145">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="ba883-146">Självbetjäning för återställning av lösenord (SSPR)</span><span class="sxs-lookup"><span data-stu-id="ba883-146">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="ba883-147">Låt användarna återställa eller låsa upp sina lösenord och konton.</span><span class="sxs-lookup"><span data-stu-id="ba883-147">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="ba883-148">Microsoft 365 E3 eller E5</span><span class="sxs-lookup"><span data-stu-id="ba883-148">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="ba883-149">Azure Active Directory Application Proxy</span><span class="sxs-lookup"><span data-stu-id="ba883-149">Azure AD Application Proxy</span></span>    | <span data-ttu-id="ba883-150">Tillhandahåll säker fjärråtkomst till webbaserade program som finns på intranätsservrar.</span><span class="sxs-lookup"><span data-stu-id="ba883-150">Provide secure remote access for web-based applications hosted on intranet servers.</span></span>   | <span data-ttu-id="ba883-151">För detta krävs en separat, betald Azure-prenumeration</span><span class="sxs-lookup"><span data-stu-id="ba883-151">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="ba883-152">Azure Point-to-Site VPN</span><span class="sxs-lookup"><span data-stu-id="ba883-152">Azure Point-to-Site VPN</span></span>   | <span data-ttu-id="ba883-153">Skapa en säker anslutning från en distansarbetares enhet till ert intranät via ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="ba883-153">Create a secure connection from a remote worker’s device to your intranet through an Azure virtual network.</span></span>   | <span data-ttu-id="ba883-154">För detta krävs en separat, betald Azure-prenumeration</span><span class="sxs-lookup"><span data-stu-id="ba883-154">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="ba883-155">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="ba883-155">Windows Virtual Desktop</span></span>   | <span data-ttu-id="ba883-156">Underlätta för distansarbetare som bara kan använda privata och ohanterade enheter med hjälp av virtuella skrivbord som körs i Azure.</span><span class="sxs-lookup"><span data-stu-id="ba883-156">Support remote workers who can only use their personal and unmanaged devices with virtual desktops running in Azure.</span></span> | <span data-ttu-id="ba883-157">För detta krävs en separat, betald Azure-prenumeration</span><span class="sxs-lookup"><span data-stu-id="ba883-157">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="ba883-158">Fjärrskrivbordstjänster (RDS)</span><span class="sxs-lookup"><span data-stu-id="ba883-158">Remote Desktop Services (RDS)</span></span> | <span data-ttu-id="ba883-159">Låt medarbetarna ansluta till Windows-baserade datorer på intranätet.</span><span class="sxs-lookup"><span data-stu-id="ba883-159">Allow employees to connect into Windows-based computers on your intranet.</span></span> | <span data-ttu-id="ba883-160">Microsoft 365 E3 eller E5</span><span class="sxs-lookup"><span data-stu-id="ba883-160">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="ba883-161">Gateway för fjärrskrivbordstjänster</span><span class="sxs-lookup"><span data-stu-id="ba883-161">Remote Desktop Services Gateway</span></span>   | <span data-ttu-id="ba883-162">Kryptera kommunikationen och hindra värddatorerna för fjärrskrivbordstjänsterna från att exponeras direkt på internet.</span><span class="sxs-lookup"><span data-stu-id="ba883-162">Encrypt communications and prevent the RDS hosts from being directly exposed to the Internet.</span></span> | <span data-ttu-id="ba883-163">För detta krävs separata Windows Server-licenser</span><span class="sxs-lookup"><span data-stu-id="ba883-163">Requires separate Windows Server licenses</span></span> |
| <span data-ttu-id="ba883-164">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ba883-164">Microsoft Intune</span></span> | <span data-ttu-id="ba883-165">Hantera enheter och program.</span><span class="sxs-lookup"><span data-stu-id="ba883-165">Manage devices and applications.</span></span>   | <span data-ttu-id="ba883-166">Microsoft 365 E3 eller E5</span><span class="sxs-lookup"><span data-stu-id="ba883-166">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="ba883-167">Konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="ba883-167">Configuration Manager</span></span> | <span data-ttu-id="ba883-168">Hantera programvaruinstallationer, uppdateringar och inställningar på dina enheter</span><span class="sxs-lookup"><span data-stu-id="ba883-168">Manage software installations, updates, and settings on your devices</span></span> | <span data-ttu-id="ba883-169">För detta krävs separata licenser för Konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="ba883-169">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="ba883-170">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="ba883-170">Desktop Analytics</span></span> | <span data-ttu-id="ba883-171">Avgör uppdateringsberedskapen hos dina Windows-klienter.</span><span class="sxs-lookup"><span data-stu-id="ba883-171">Determine the update readiness of your Windows clients.</span></span>   | <span data-ttu-id="ba883-172">För detta krävs separata licenser för Konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="ba883-172">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="ba883-173">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="ba883-173">Windows Autopilot</span></span> | <span data-ttu-id="ba883-174">Förinstallera och konfigurera nya Windows 10-enheter för effektiv användning.</span><span class="sxs-lookup"><span data-stu-id="ba883-174">Set up and pre-configure new Windows 10 devices for productive use.</span></span>   | <span data-ttu-id="ba883-175">Microsoft 365 E3 eller E5</span><span class="sxs-lookup"><span data-stu-id="ba883-175">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="ba883-176">Microsoft Teams, Exchange Online, SharePoint Online och OneDrive, Microsoft 365-applikationer, Microsoft Power Platform och Yammer</span><span class="sxs-lookup"><span data-stu-id="ba883-176">Microsoft Teams, Exchange Online, SharePoint Online and OneDrive, Microsoft 365 Apps, Microsoft Power Platform, and Yammer</span></span> | <span data-ttu-id="ba883-177">Skapa, kommunicera och samarbeta.</span><span class="sxs-lookup"><span data-stu-id="ba883-177">Create, communicate, and collaborate.</span></span> | <span data-ttu-id="ba883-178">Microsoft 365 E3 eller E5</span><span class="sxs-lookup"><span data-stu-id="ba883-178">Microsoft 365 E3 or E5</span></span> |
||||

<span data-ttu-id="ba883-179">För kriterier för säkerhet och efterlevnad, se [Distribuera säkerhet och efterlevnad för fjärrarbetare](empower-people-to-work-remotely-security-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="ba883-179">For security and compliance criteria, see [Deploy security and compliance for remote workers](empower-people-to-work-remotely-security-compliance.md).</span></span>

<a name="poster"></a><span data-ttu-id="ba883-180">För en 2-sidor sammanfattning av denna lösning, se[Stärk affischen för fjärrarbetare](../downloads/empower-remote-workers.pdf).</span><span class="sxs-lookup"><span data-stu-id="ba883-180">For a 2-page summary of this solution, see the [Empower remote workers poster](../downloads/empower-remote-workers.pdf).</span></span>

<span data-ttu-id="ba883-181">[![Ge distansarbetare goda förutsättningar (affisch)](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)</span><span class="sxs-lookup"><span data-stu-id="ba883-181">[![Empower remote workers poster](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)</span></span>

<span data-ttu-id="ba883-182">Du kan också ladda ned den här affischen i [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf)- eller [PowerPoint](https://download.microsoft.com/download/5/1/1/511b77a9-a34c-4ea7-af2a-32b07f20b780/empower-remote-workers.pptx)-format och skriva ut den i pappersstorleken letter, legal eller tabloid (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="ba883-182">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf) or  [PowerPoint](https://download.microsoft.com/download/5/1/1/511b77a9-a34c-4ea7-af2a-32b07f20b780/empower-remote-workers.pptx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

## <a name="provide-remote-working-for-all-of-your-workers"></a><span data-ttu-id="ba883-183">Tillhandahålla fjärråtkomst för alla dina medarbetare</span><span class="sxs-lookup"><span data-stu-id="ba883-183">Provide remote working for all of your workers</span></span>

<span data-ttu-id="ba883-184">Du kan göra så alla dina medarbetare kan vara produktiva var de än befinner sig med dessa enheter:</span><span class="sxs-lookup"><span data-stu-id="ba883-184">You can enable all of your workers to stay productive from anywhere with these devices:</span></span>

- <span data-ttu-id="ba883-185">En modern enhet, till exempel en Surface laptop och Windows 10, som har funktioner, säkerhet och prestanda för att få tillgång till Microsoft 365-molnprogram och -tjänster direkt över webben.</span><span class="sxs-lookup"><span data-stu-id="ba883-185">A modern device, such as a Surface laptop and Windows 10, which has the features, security, and performance to access Microsoft 365 cloud apps and services directly over the web.</span></span>

- <span data-ttu-id="ba883-186">Alla enheter, inklusive äldre laptops eller stationära datorer, som kan få tillgång till Microsoft 365-molnprogram och -tjänster indirekt via en snabb distribution av [Windows 10-baserade virtuella skrivbord](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices).</span><span class="sxs-lookup"><span data-stu-id="ba883-186">Any device including older laptops or desktops used from home, which can access Microsoft 365 cloud apps and services indirectly through a quickly deployed [Windows 10-based virtual desktop](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices).</span></span> <span data-ttu-id="ba883-187">Med det här alternativet får du hög prestanda, stark säkerhet och förenklad IT-hantering.</span><span class="sxs-lookup"><span data-stu-id="ba883-187">This option provides high performance, strong security, and simplified IT management.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ba883-188">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ba883-188">Next steps</span></span>

<span data-ttu-id="ba883-189">Följ dessa steg för att skydda och optimera åtkomsten till organisationens servrar och molntjänster, och maximera produktiviteten för distansarbetarna.</span><span class="sxs-lookup"><span data-stu-id="ba883-189">Use these steps to secure and optimize access to your organization's servers and cloud services and maximize your remote worker's productivity.</span></span>

1. [<span data-ttu-id="ba883-190">Öka inloggningssäkerheten med MFA</span><span class="sxs-lookup"><span data-stu-id="ba883-190">Increase sign-in security with MFA</span></span>](empower-people-to-work-remotely-secure-sign-in.md)
2. [<span data-ttu-id="ba883-191">Ge fjärråtkomst till lokala appar och tjänster</span><span class="sxs-lookup"><span data-stu-id="ba883-191">Provide remote access to on-premises apps and services</span></span>](empower-people-to-work-remotely-remote-access.md)
3. [<span data-ttu-id="ba883-192">Distribuera säkerhets- och efterlevnadstjänster</span><span class="sxs-lookup"><span data-stu-id="ba883-192">Deploy security and compliance services</span></span>](empower-people-to-work-remotely-security-compliance.md)
4. [<span data-ttu-id="ba883-193">Distribuera slutpunktshantering för enheter, datorer och andra slutpunkter</span><span class="sxs-lookup"><span data-stu-id="ba883-193">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>](empower-people-to-work-remotely-manage-endpoints.md)
5. [<span data-ttu-id="ba883-194">Distribuera produktivitetsappar och tjänster för distansarbetare</span><span class="sxs-lookup"><span data-stu-id="ba883-194">Deploy remote worker productivity apps and services</span></span>](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [<span data-ttu-id="ba883-195">Träna distansarbetare och få feedback om användningen</span><span class="sxs-lookup"><span data-stu-id="ba883-195">Train remote workers and address usage feedback</span></span>](empower-people-to-work-remotely-train-monitor-usage.md)

<span data-ttu-id="ba883-196">[![Steg för att konfigurera infrastrukturen för distansarbete med Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="ba883-196">[![The steps to set up your infrastructure for remote work with Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)</span></span>

<span data-ttu-id="ba883-197">För att se hur en fiktiv men representativ multinationell organisation har konfigurerat infrastrukturen för distansarbete, gå till [Contosos gensvar på COVID-19 och infrastruktur för distansarbete och arbete på plats](contoso-remote-onsite-work.md).</span><span class="sxs-lookup"><span data-stu-id="ba883-197">To see how a fictional but representative multi-national organization set up its infrastructure for remote work, see [Contoso's COVID-19 response and infrastructure for remote and onsite work](contoso-remote-onsite-work.md).</span></span>
