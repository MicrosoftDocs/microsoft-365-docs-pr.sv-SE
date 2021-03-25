---
title: Översikt över Microsoft Defender ATP för iOS
ms.reviewer: ''
description: Här beskrivs hur du installerar och använder Microsoft Defender ATP för iOS
keywords: microsoft, defender, atp, ios, overview, installation, deploy, avinstallation, intune
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
ms.openlocfilehash: 6e5aae9dcb361caf9133c1270a16711fc43033bb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074322"
---
# <a name="microsoft-defender-for-endpoint-for-ios"></a><span data-ttu-id="aef0e-104">Microsoft Defender för slutpunkt för iOS</span><span class="sxs-lookup"><span data-stu-id="aef0e-104">Microsoft Defender for Endpoint for iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aef0e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="aef0e-105">**Applies to:**</span></span>
- [<span data-ttu-id="aef0e-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="aef0e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="aef0e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aef0e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="aef0e-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="aef0e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aef0e-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="aef0e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="aef0e-110">**Microsoft Defender för Endpoint för iOS** skyddar mot nätfiske och osäkra nätverksanslutningar från webbplatser, e-postmeddelanden och appar.</span><span class="sxs-lookup"><span data-stu-id="aef0e-110">**Microsoft Defender for Endpoint for iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="aef0e-111">Alla aviseringar är tillgängliga i ett enda fönster med fönster i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="aef0e-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="aef0e-112">Portalen ger säkerhetsteamen en centraliserad bild av hot på iOS-enheter samt andra plattformar.</span><span class="sxs-lookup"><span data-stu-id="aef0e-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="aef0e-113">Att köra andra produkter med slutpunktsskydd från tredje part tillsammans med Defender för Endpoint för iOS kan sannolikt orsaka prestandaproblem och oförutsägbara systemfel.</span><span class="sxs-lookup"><span data-stu-id="aef0e-113">Running other third-party endpoint protection products alongside Defender for Endpoint for iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="aef0e-114">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="aef0e-114">Pre-requisites</span></span>

<span data-ttu-id="aef0e-115">**För slutanvändare**</span><span class="sxs-lookup"><span data-stu-id="aef0e-115">**For End Users**</span></span>

- <span data-ttu-id="aef0e-116">Microsoft Defender för slutpunktslicens tilldelad till slutanvändare av programmet.</span><span class="sxs-lookup"><span data-stu-id="aef0e-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="aef0e-117">Se [Microsoft Defender för Slutpunktslicensieringskrav](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="aef0e-117">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="aef0e-118">Enheter registreras via [appen](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) Intune-företagsportal för att framtvinga Intune-efterlevnadsprinciper för enheter.</span><span class="sxs-lookup"><span data-stu-id="aef0e-118">Device(s) are [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="aef0e-119">Det kräver att användaren tilldelas en Microsoft Intune-licens.</span><span class="sxs-lookup"><span data-stu-id="aef0e-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="aef0e-120">Appen Intune-företagsportal kan laddas ned från [Apple App Store.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="aef0e-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="aef0e-121">Observera att Apple inte tillåter omdirigering av användare att ladda ned andra appar från app store, och därför måste detta steg utföras av användaren innan användaren börjar använda Microsoft Defender för slutpunktsappen.</span><span class="sxs-lookup"><span data-stu-id="aef0e-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="aef0e-122">Mer information om hur du tilldelar licenser finns i [Tilldela användare licenser.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="aef0e-122">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="aef0e-123">**För administratörer**</span><span class="sxs-lookup"><span data-stu-id="aef0e-123">**For Administrators**</span></span>

- <span data-ttu-id="aef0e-124">Åtkomst till Microsoft Defender Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="aef0e-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aef0e-125">Microsoft Intune är den enda mdm-lösning (Mobile Device Management) som stöds för distribution av Microsoft Defender för Slutpunkt för iOS.</span><span class="sxs-lookup"><span data-stu-id="aef0e-125">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint for iOS.</span></span> <span data-ttu-id="aef0e-126">För närvarande stöds endast registrerade enheter för tvingande Defender för Endpoint för iOS-relaterade efterlevnadsprinciper för enheter i Intune.</span><span class="sxs-lookup"><span data-stu-id="aef0e-126">Currently only enrolled devices are supported for enforcing Defender for Endpoint for iOS related device compliance policies in Intune.</span></span>

- <span data-ttu-id="aef0e-127">Åtkomst till [administrationscentret för Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)för att distribuera programmet till registrerade användargrupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="aef0e-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="aef0e-128">**Systemkrav**</span><span class="sxs-lookup"><span data-stu-id="aef0e-128">**System Requirements**</span></span>

- <span data-ttu-id="aef0e-129">iOS-enheter med iOS 11.0 och högre.</span><span class="sxs-lookup"><span data-stu-id="aef0e-129">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="aef0e-130">iPad-enheter stöds officiellt från och med version 1.1.15010101 och framåt.</span><span class="sxs-lookup"><span data-stu-id="aef0e-130">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="aef0e-131">Enheten är registrerad med appen [Intune-företagsportal.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="aef0e-131">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

> [!NOTE]
> <span data-ttu-id="aef0e-132">**Microsoft Defender ATP (Microsoft Defender för slutpunkt) för iOS är nu tillgängligt på [Apple App Store.](https://aka.ms/mdatpiosappstore)**</span><span class="sxs-lookup"><span data-stu-id="aef0e-132">**Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available on [Apple App Store](https://aka.ms/mdatpiosappstore).**</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="aef0e-133">Installationsanvisningar</span><span class="sxs-lookup"><span data-stu-id="aef0e-133">Installation instructions</span></span>

<span data-ttu-id="aef0e-134">Distribution av Microsoft Defender för Endpoint för iOS sker via Microsoft Intune (MDM) och både övervakade och ej övervakade enheter stöds.</span><span class="sxs-lookup"><span data-stu-id="aef0e-134">Deployment of Microsoft Defender for Endpoint for iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span>
<span data-ttu-id="aef0e-135">Mer information finns i Distribuera [Microsoft Defender för slutpunkt för iOS.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="aef0e-135">For more information, see [Deploy Microsoft Defender for Endpoint for iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="aef0e-136">Resurser</span><span class="sxs-lookup"><span data-stu-id="aef0e-136">Resources</span></span>

- <span data-ttu-id="aef0e-137">Håll dig informerad om kommande versioner genom att besöka vår [blogg](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span><span class="sxs-lookup"><span data-stu-id="aef0e-137">Stay informed about upcoming releases by visiting our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="aef0e-138">Ge feedback via feedbacksystem i appen eller via [SecOps-portalen](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="aef0e-138">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="aef0e-139">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="aef0e-139">Next steps</span></span>

- [<span data-ttu-id="aef0e-140">Distribuera Microsoft Defender för slutpunkt för iOS</span><span class="sxs-lookup"><span data-stu-id="aef0e-140">Deploy Microsoft Defender for Endpoint for iOS</span></span>](ios-install.md)
- [<span data-ttu-id="aef0e-141">Konfigurera Microsoft Defender för slutpunkt för iOS-funktioner</span><span class="sxs-lookup"><span data-stu-id="aef0e-141">Configure Microsoft Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)
