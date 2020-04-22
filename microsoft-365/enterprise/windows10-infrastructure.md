---
title: Windows 10 Enterprise-infrastruktur för Microsoft 365 Enterprise
description: Ger vägledning på hög nivå om de steg du behöver för att distribuera Windows 10 Enterprise på datorer som en del av Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-dokumentation, Windows 10 Enterprise, distribution
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 53c38ba2e915cd439c8d7629bc7f9cd56ebc8647
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636681"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="fc581-104">Fas 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fc581-104">Phase 3: Windows 10 Enterprise</span></span>

![Fas 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="fc581-106">Microsoft 365 Enterprise innehåller Windows 10 Enterprise, som ger dig verktygen för att göra mer och vara säker.</span><span class="sxs-lookup"><span data-stu-id="fc581-106">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="fc581-107">Windows 10 Företag:</span><span class="sxs-lookup"><span data-stu-id="fc581-107">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="fc581-108">**Är integrerad för enkelhetens skull** - Utnyttja kraften i molnet för att minska komplexiteten i att hantera dagens moderna IT-enhetsmiljö, oavsett storlek.</span><span class="sxs-lookup"><span data-stu-id="fc581-108">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="fc581-109">**Har intelligent säkerhet** – Det är den säkraste versionen av Windows någonsin, med intelligenta säkerhetsfunktioner som är utformade för att fungera tillsammans för att bättre skydda din organisation.</span><span class="sxs-lookup"><span data-stu-id="fc581-109">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="fc581-110">**Möjliggör kreativitet och lagarbete** - Låser upp kreativitet och lagarbete för att leverera den mest produktiva upplevelsen som både användare och IT kommer att älska.</span><span class="sxs-lookup"><span data-stu-id="fc581-110">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="fc581-111">Du måste förstå olika sätt att distribuera operativsystemet Windows 10 och välja det rätta för din organisation.</span><span class="sxs-lookup"><span data-stu-id="fc581-111">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="fc581-112">Beroende på din Microsoft 365 Enterprise-prenumeration finns det också Windows 10-tjänster och säkerhetsfunktioner som du måste konfigurera för att få ut det mesta av Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fc581-112">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

>[!Note]
><span data-ttu-id="fc581-113">Information om hur du distribuerar både Windows 10 Enterprise och Microsoft 365 Apps för företag tillsammans och byter till ett [modernt skrivbord](https://www.microsoft.com/microsoft-365/modern-desktop)finns i [Modern Desktop Deployment Center](https://aka.ms/howtoshift).</span><span class="sxs-lookup"><span data-stu-id="fc581-113">To deploy both Windows 10 Enterprise and Microsoft 365 Apps for enterprise together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](https://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="fc581-114">Windows 10-distribution</span><span class="sxs-lookup"><span data-stu-id="fc581-114">Windows 10 deployment</span></span>

<span data-ttu-id="fc581-115">Det finns flera sätt att distribuera Windows 10 Enterprise för din organisation.</span><span class="sxs-lookup"><span data-stu-id="fc581-115">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="fc581-116">Här fokuserar vi på hur du kan konfigurera och distribuera en Windows 10 Enterprise-avbildning genom dessa moderna distributionsscenarier.</span><span class="sxs-lookup"><span data-stu-id="fc581-116">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="fc581-117">Distributionsscenario</span><span class="sxs-lookup"><span data-stu-id="fc581-117">Deployment scenario</span></span> | <span data-ttu-id="fc581-118">När du ska använda den</span><span class="sxs-lookup"><span data-stu-id="fc581-118">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="fc581-119">Använda Microsoft Endpoint Configuration Manager som en uppgradering på plats</span><span class="sxs-lookup"><span data-stu-id="fc581-119">Using Microsoft Endpoint Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="fc581-120">Välj det här alternativet om du behöver uppgradera Windows 7- eller Windows 8.1-datorer till den <a href="https://aka.ms/windows-10-release-information" target="_blank">aktuella versionen</a> av Windows 10 Enterprise och dina datorer för närvarande hanteras med <a href="https://docs.microsoft.com/configmgr/core/understand/introduction" target="_blank">Configuration Manager (aktuell gren).</a></span><span class="sxs-lookup"><span data-stu-id="fc581-120">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://docs.microsoft.com/configmgr/core/understand/introduction" target="_blank">Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="fc581-121">Använda Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="fc581-121">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="fc581-122">Välj det här alternativet om du konfigurerar nya Windows-datorer med Windows 10 Enterprise, version 1703 eller senare förinstallerat.</span><span class="sxs-lookup"><span data-stu-id="fc581-122">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="fc581-123">Slutanvändare initierar installationen med önskad konfiguration genom att ange sina autentiseringsuppgifter för arbets- eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="fc581-123">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="fc581-124">Om dessa distributionsscenarier inte passar organisationens behov kan du lära dig mer om andra scenarier och förstå funktionerna och begränsningarna för varje i [Windows 10-distributionsscenarier](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span><span class="sxs-lookup"><span data-stu-id="fc581-124">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="fc581-125">Du kan också <a href="https://aka.ms/planforwin10deployment" target="_blank">planera för distribution av Windows 10</a> på egen hand.</span><span class="sxs-lookup"><span data-stu-id="fc581-125">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="fc581-126">Du kan läsa mer om Windows 10 med följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="fc581-126">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="fc581-127">Produktsida för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fc581-127">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="fc581-128">Windows 10</span><span class="sxs-lookup"><span data-stu-id="fc581-128">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="fc581-129">Distribuera och uppdatera Windows 10</span><span class="sxs-lookup"><span data-stu-id="fc581-129">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="fc581-130">Ytterligare tjänster och funktioner</span><span class="sxs-lookup"><span data-stu-id="fc581-130">Additional services and features</span></span>
<span data-ttu-id="fc581-131">Som en del av distributionen av Windows 10 Enterprise kan du lägga till dessa ytterligare tjänster och funktioner.</span><span class="sxs-lookup"><span data-stu-id="fc581-131">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="fc581-132">Windows-analys</span><span class="sxs-lookup"><span data-stu-id="fc581-132">Windows Analytics</span></span>

<span data-ttu-id="fc581-133">Windows använder diagnostikdata för att tillhandahålla omfattande och användbar information som hjälper dig att få djup insikt i driftseffektivitet och hälsa för Windows 10-enheter i din miljö.</span><span class="sxs-lookup"><span data-stu-id="fc581-133">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="fc581-134">Uppgraderingsberedskap - Uppgraderingsberedskap hjälper dig att flytta till Windows 10 och hålla dig uppdaterad med nya windows 10-funktionsuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="fc581-134">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="fc581-135">Uppdateringsefterlevnad – Uppdateringsefterlevnad riktar sig till IT-administratören som vill få en helhetsbild av alla sina Windows 10-enheter, utan några ytterligare infrastrukturkrav.</span><span class="sxs-lookup"><span data-stu-id="fc581-135">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="fc581-136">Enhetshälsa – Du kan använda Enhetshälsa för att proaktivt identifiera och åtgärda problem med att påverka slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="fc581-136">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="fc581-137">Mer information finns i [Översikt över Windows Analytics.](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview)</span><span class="sxs-lookup"><span data-stu-id="fc581-137">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="fc581-138">Windows-säkerhet</span><span class="sxs-lookup"><span data-stu-id="fc581-138">Windows security</span></span>

<span data-ttu-id="fc581-139">Windows 10 innehåller funktioner som skyddar mot hot, hjälper dig att skydda dina enheter och hjälp med åtkomstkontroll.</span><span class="sxs-lookup"><span data-stu-id="fc581-139">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="fc581-140">Med Windows 10 får du viktiga säkerhetsfunktioner som skyddar din enhet redan från början.</span><span class="sxs-lookup"><span data-stu-id="fc581-140">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="fc581-141">Microsoft 365 E3 lägger till säkerhetsfunktioner som Windows Hello för företag, Windows Defender Application Control och Windows Information Protection.</span><span class="sxs-lookup"><span data-stu-id="fc581-141">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="fc581-142">Med Microsoft 365 E5 får du allt skydd från Microsoft 365 E3-säkerhet plus molnbaserade säkerhetsfunktioner och Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="fc581-142">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Microsoft Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="fc581-143">Mer information om de säkerhetsfunktioner som du får med Windows 10 Enterprise och få vägledning om hur du kan distribuera, hantera, konfigurera och felsöka tre viktiga säkerhetsfunktioner finns i [Steg 5: Distribuera säkerhetsfunktioner för Windows 10 Enterprise](windows10-enable-security-features.md).</span><span class="sxs-lookup"><span data-stu-id="fc581-143">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key security features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="fc581-144">Hur Microsoft använder Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fc581-144">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="fc581-145">Kika in i Microsoft och lär dig hur företaget [distribuerade Windows 10 Enterprise och använder stark autentisering, Intune och Microsoft Defender ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span><span class="sxs-lookup"><span data-stu-id="fc581-145">Peek inside Microsoft and learn how the company [deployed Windows 10 Enterprise and is using strong authentication, Intune, and Microsoft Defender ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="fc581-146">Så här använder Contoso Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fc581-146">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="fc581-147">Se hur Contoso Corporation, ett fiktivt men representativt multinationellt företag, [distribuerade Windows 10 Enterprise](contoso-win10.md).</span><span class="sxs-lookup"><span data-stu-id="fc581-147">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="fc581-149">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="fc581-149">Next step</span></span>

|||
|:-------|:-----|
|![Steg 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="fc581-151">Förbereda din organisation för Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fc581-151">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
