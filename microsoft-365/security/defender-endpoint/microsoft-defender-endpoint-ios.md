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
ms.openlocfilehash: cbe2fb39221bd9907a3d690503a392edb019d61b
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194859"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="15aa4-104">Microsoft Defender för Endpoint för iOS</span><span class="sxs-lookup"><span data-stu-id="15aa4-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="15aa4-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="15aa4-105">**Applies to:**</span></span>
- [<span data-ttu-id="15aa4-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="15aa4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="15aa4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15aa4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="15aa4-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="15aa4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="15aa4-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="15aa4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="15aa4-110">**Microsoft Defender för slutpunkt för iOS** ger skydd mot nätfiske och osäkra nätverksanslutningar från webbplatser, e-postmeddelanden och appar.</span><span class="sxs-lookup"><span data-stu-id="15aa4-110">**Microsoft Defender for Endpoint on iOS** offers protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="15aa4-111">Alla aviseringar är tillgängliga i ett enda fönster med Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="15aa4-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="15aa4-112">Portalen ger säkerhetsteamen en centraliserad bild av hot på iOS-enheter samt andra plattformar.</span><span class="sxs-lookup"><span data-stu-id="15aa4-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="15aa4-113">Att köra andra slutpunktsskyddsprodukter från tredje part tillsammans med Defender för Endpoint på iOS kan sannolikt orsaka prestandaproblem och oförutsägbara systemfel.</span><span class="sxs-lookup"><span data-stu-id="15aa4-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="15aa4-114">Förhandskrav</span><span class="sxs-lookup"><span data-stu-id="15aa4-114">Pre-requisites</span></span>

<span data-ttu-id="15aa4-115">**För slutanvändare**</span><span class="sxs-lookup"><span data-stu-id="15aa4-115">**For End Users**</span></span>

- <span data-ttu-id="15aa4-116">Microsoft Defender för slutpunktslicens tilldelad till slutanvändare av programmet.</span><span class="sxs-lookup"><span data-stu-id="15aa4-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="15aa4-117">Se [Microsoft Defender för Slutpunktslicensieringskrav](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="15aa4-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="15aa4-118">**För registrerade enheter:** Enheter registreras [](/mem/intune/user-help/enroll-your-device-in-intune-ios) via appen Intune-företagsportal för att tillämpa Intune-efterlevnadsprinciper för enheter.</span><span class="sxs-lookup"><span data-stu-id="15aa4-118">**For enrolled devices**: Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="15aa4-119">Det kräver att användaren tilldelas en Microsoft Intune licens.</span><span class="sxs-lookup"><span data-stu-id="15aa4-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="15aa4-120">Intune-företagsportal-appen kan laddas ned från [Apple App Store.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="15aa4-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="15aa4-121">Observera att Apple inte tillåter omdirigering av användare att ladda ned andra appar från app store, och därför måste detta steg utföras av användaren innan användaren börjar använda Microsoft Defender för slutpunktsappen.</span><span class="sxs-lookup"><span data-stu-id="15aa4-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="15aa4-122">**För oregistrerade enheter:** Enheter är registrerade med Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="15aa4-122">**For unenrolled devices**: Device(s) are registered with Azure Active Directory.</span></span> <span data-ttu-id="15aa4-123">För detta krävs att användaren är inloggad via [Microsoft Authenticator app.](https://apps.apple.com/app/microsoft-authenticator/id983156458)</span><span class="sxs-lookup"><span data-stu-id="15aa4-123">This requires end user to be signed in through [Microsoft Authenticator app](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

- <span data-ttu-id="15aa4-124">Mer information om hur du tilldelar licenser finns i [Tilldela användare licenser.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="15aa4-124">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="15aa4-125">**För administratörer**</span><span class="sxs-lookup"><span data-stu-id="15aa4-125">**For Administrators**</span></span>

- <span data-ttu-id="15aa4-126">Åtkomst till Microsoft Defender Säkerhetscenter portalen.</span><span class="sxs-lookup"><span data-stu-id="15aa4-126">Access to the Microsoft Defender Security Center portal.</span></span>

- <span data-ttu-id="15aa4-127">Åtkomst till [Microsoft Endpoint Manager ,](https://go.microsoft.com/fwlink/?linkid=2109431)för att distribuera programmet till registrerade användargrupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="15aa4-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

    > [!NOTE]
    > <span data-ttu-id="15aa4-128">Microsoft Intune är den enda UEM-lösning (Unified Endpoint Management) som stöds för att distribuera Microsoft Defender för Endpoint och tillämpa Defender för Slutpunktsrelaterade efterlevnadsprinciper för enheter i Intune.</span><span class="sxs-lookup"><span data-stu-id="15aa4-128">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

<span data-ttu-id="15aa4-129">**Systemkrav**</span><span class="sxs-lookup"><span data-stu-id="15aa4-129">**System Requirements**</span></span>

- <span data-ttu-id="15aa4-130">iOS-enhet med iOS 11.0 och högre.</span><span class="sxs-lookup"><span data-stu-id="15aa4-130">iOS device running iOS 11.0 and above.</span></span> <span data-ttu-id="15aa4-131">iPad officiellt från och med version 1.1.15010101.</span><span class="sxs-lookup"><span data-stu-id="15aa4-131">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="15aa4-132">Enheten är antingen registrerad med appen [Intune-företagsportal eller](https://apps.apple.com/us/app/intune-company-portal/id719171358) registrerad med Azure Active Directory via [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span><span class="sxs-lookup"><span data-stu-id="15aa4-132">Device is either enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358) or registered with Azure Active Directory through [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="15aa4-133">Installationsanvisningar</span><span class="sxs-lookup"><span data-stu-id="15aa4-133">Installation instructions</span></span>

<span data-ttu-id="15aa4-134">Distribution av Microsoft Defender för Slutpunkt på iOS kan göras via Microsoft Endpoint Manager (MEM) och både övervakade och ej övervakade enheter stöds.</span><span class="sxs-lookup"><span data-stu-id="15aa4-134">Deployment of Microsoft Defender for Endpoint on iOS can be done via Microsoft Endpoint Manager (MEM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="15aa4-135">Slutanvändare kan också installera appen direkt från [Apple App Store.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="15aa4-135">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="15aa4-136">Mer information finns i Distribuera [Microsoft Defender för slutpunkt i iOS.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="15aa4-136">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="15aa4-137">Resurser</span><span class="sxs-lookup"><span data-stu-id="15aa4-137">Resources</span></span>

- <span data-ttu-id="15aa4-138">Håll dig informerad om kommande versioner genom [att besöka Vad är nytt i Microsoft Defender för Endpoint i iOS](ios-whatsnew.md) eller vår [blogg](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span><span class="sxs-lookup"><span data-stu-id="15aa4-138">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="15aa4-139">Ge feedback via feedbacksystem i appen eller via [SecOps-portalen](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="15aa4-139">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="15aa4-140">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="15aa4-140">Next steps</span></span>

- [<span data-ttu-id="15aa4-141">Distribuera Microsoft Defender för Slutpunkt i iOS</span><span class="sxs-lookup"><span data-stu-id="15aa4-141">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="15aa4-142">Konfigurera Microsoft Defender för slutpunkt för iOS-funktioner</span><span class="sxs-lookup"><span data-stu-id="15aa4-142">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
