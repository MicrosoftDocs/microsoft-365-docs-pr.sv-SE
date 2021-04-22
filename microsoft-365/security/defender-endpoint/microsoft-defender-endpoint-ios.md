---
title: Microsoft Defender för Endpoint för iOS
ms.reviewer: ''
description: Beskriver hur du installerar och använder Microsoft Defender för Slutpunkt i iOS
keywords: microsoft, defender, Microsoft Defender för slutpunkt, ios, översikt, installation, distribuera, avinstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cdf32e6daa26eb369d66a4b6c0ff3991093c67f9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935275"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="a78ae-104">Microsoft Defender för Endpoint för iOS</span><span class="sxs-lookup"><span data-stu-id="a78ae-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a78ae-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a78ae-105">**Applies to:**</span></span>
- [<span data-ttu-id="a78ae-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a78ae-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a78ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a78ae-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a78ae-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a78ae-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a78ae-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a78ae-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a78ae-110">**Microsoft Defender för Slutpunkt för iOS** skyddar mot nätfiske och osäkra nätverksanslutningar från webbplatser, e-postmeddelanden och appar.</span><span class="sxs-lookup"><span data-stu-id="a78ae-110">**Microsoft Defender for Endpoint on iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="a78ae-111">Alla aviseringar är tillgängliga i ett enda fönster med fönster i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="a78ae-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="a78ae-112">Portalen ger säkerhetsteamen en centraliserad bild av hot på iOS-enheter samt andra plattformar.</span><span class="sxs-lookup"><span data-stu-id="a78ae-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="a78ae-113">Att köra andra slutpunktsskyddsprodukter från tredje part tillsammans med Defender för Endpoint på iOS kan sannolikt orsaka prestandaproblem och oförutsägbara systemfel.</span><span class="sxs-lookup"><span data-stu-id="a78ae-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="a78ae-114">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="a78ae-114">Pre-requisites</span></span>

<span data-ttu-id="a78ae-115">**För slutanvändare**</span><span class="sxs-lookup"><span data-stu-id="a78ae-115">**For End Users**</span></span>

- <span data-ttu-id="a78ae-116">Microsoft Defender för slutpunktslicens tilldelad till slutanvändare av programmet.</span><span class="sxs-lookup"><span data-stu-id="a78ae-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="a78ae-117">Se [Microsoft Defender för Slutpunktslicensieringskrav](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="a78ae-117">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="a78ae-118">Enheter registreras via [appen](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) Intune-företagsportal för att framtvinga Intune-efterlevnadsprinciper för enheter.</span><span class="sxs-lookup"><span data-stu-id="a78ae-118">Device(s) are [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="a78ae-119">Det kräver att användaren tilldelas en Microsoft Intune-licens.</span><span class="sxs-lookup"><span data-stu-id="a78ae-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="a78ae-120">Appen Intune-företagsportal kan laddas ned från [Apple App Store.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="a78ae-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="a78ae-121">Observera att Apple inte tillåter omdirigering av användare att ladda ned andra appar från app store, och därför måste detta steg utföras av användaren innan användaren börjar använda Microsoft Defender för slutpunktsappen.</span><span class="sxs-lookup"><span data-stu-id="a78ae-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="a78ae-122">Mer information om hur du tilldelar licenser finns i [Tilldela användare licenser.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="a78ae-122">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="a78ae-123">**För administratörer**</span><span class="sxs-lookup"><span data-stu-id="a78ae-123">**For Administrators**</span></span>

- <span data-ttu-id="a78ae-124">Åtkomst till Microsoft Defender Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="a78ae-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a78ae-125">Microsoft Intune är den enda mdm-lösning (Mobile Device Management) som stöds för distribution av Microsoft Defender för slutpunkt i iOS.</span><span class="sxs-lookup"><span data-stu-id="a78ae-125">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="a78ae-126">För närvarande stöds endast registrerade enheter för tvingande Defender för Slutpunkt på iOS-relaterade efterlevnadsprinciper för enheter i Intune.</span><span class="sxs-lookup"><span data-stu-id="a78ae-126">Currently only enrolled devices are supported for enforcing Defender for Endpoint on iOS related device compliance policies in Intune.</span></span>

- <span data-ttu-id="a78ae-127">Åtkomst till [administrationscentret för Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)för att distribuera programmet till registrerade användargrupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a78ae-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="a78ae-128">**Systemkrav**</span><span class="sxs-lookup"><span data-stu-id="a78ae-128">**System Requirements**</span></span>

- <span data-ttu-id="a78ae-129">iOS-enheter med iOS 11.0 och högre.</span><span class="sxs-lookup"><span data-stu-id="a78ae-129">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="a78ae-130">iPad-enheter stöds officiellt från och med version 1.1.15010101 och framåt.</span><span class="sxs-lookup"><span data-stu-id="a78ae-130">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="a78ae-131">Enheten är registrerad med appen [Intune-företagsportal.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="a78ae-131">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

> [!NOTE]
> <span data-ttu-id="a78ae-132">**Microsoft Defender ATP (Microsoft Defender för slutpunkt) på iOS är nu tillgängligt på [Apple App Store.](https://aka.ms/mdatpiosappstore)**</span><span class="sxs-lookup"><span data-stu-id="a78ae-132">**Microsoft Defender ATP (Microsoft Defender for Endpoint) on iOS is now available on [Apple App Store](https://aka.ms/mdatpiosappstore).**</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="a78ae-133">Installationsanvisningar</span><span class="sxs-lookup"><span data-stu-id="a78ae-133">Installation instructions</span></span>

<span data-ttu-id="a78ae-134">Distribution av Microsoft Defender för Slutpunkt på iOS sker via Microsoft Intune (MDM) och både övervakade och ej övervakade enheter stöds.</span><span class="sxs-lookup"><span data-stu-id="a78ae-134">Deployment of Microsoft Defender for Endpoint on iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span>
<span data-ttu-id="a78ae-135">Mer information finns i Distribuera [Microsoft Defender för slutpunkt i iOS.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="a78ae-135">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="a78ae-136">Resurser</span><span class="sxs-lookup"><span data-stu-id="a78ae-136">Resources</span></span>

- <span data-ttu-id="a78ae-137">Håll dig informerad om kommande versioner genom [att besöka Vad är nytt i Microsoft Defender för Endpoint i iOS](ios-whatsnew.md) eller vår [blogg](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span><span class="sxs-lookup"><span data-stu-id="a78ae-137">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="a78ae-138">Ge feedback via feedbacksystem i appen eller via [SecOps-portalen](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a78ae-138">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="a78ae-139">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="a78ae-139">Next steps</span></span>

- [<span data-ttu-id="a78ae-140">Distribuera Microsoft Defender för Slutpunkt i iOS</span><span class="sxs-lookup"><span data-stu-id="a78ae-140">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="a78ae-141">Konfigurera Microsoft Defender för slutpunkt för iOS-funktioner</span><span class="sxs-lookup"><span data-stu-id="a78ae-141">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
