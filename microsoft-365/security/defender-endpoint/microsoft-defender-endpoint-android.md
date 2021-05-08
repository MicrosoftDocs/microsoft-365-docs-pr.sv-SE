---
title: Microsoft Defender för Endpoint för Android
ms.reviewer: ''
description: Beskriver hur du installerar och använder Microsoft Defender för slutpunkt på Android
keywords: microsoft, defender, Microsoft Defender för slutpunkt, android, installation, distribuera, avinstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3f8a8c04f608096e5c226d6899fbbd983bd8d8c1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246434"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="e8ffe-104">Microsoft Defender för Endpoint för Android</span><span class="sxs-lookup"><span data-stu-id="e8ffe-104">Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e8ffe-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e8ffe-105">**Applies to:**</span></span>
- [<span data-ttu-id="e8ffe-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="e8ffe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e8ffe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8ffe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e8ffe-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e8ffe-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e8ffe-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e8ffe-110">I det här avsnittet beskrivs hur du installerar, konfigurerar, uppdaterar och använder Defender för slutpunkt på Android.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="e8ffe-111">Att köra andra produkter med slutpunktsskydd från tredje part tillsammans med Defender för Slutpunkt på Android kan sannolikt orsaka prestandaproblem och oförutsägbara systemfel.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-111">Running other third-party endpoint protection products alongside Defender for Endpoint on Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="e8ffe-112">Så här installerar du Microsoft Defender för slutpunkt på Android</span><span class="sxs-lookup"><span data-stu-id="e8ffe-112">How to install Microsoft Defender for Endpoint on Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e8ffe-113">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e8ffe-113">Prerequisites</span></span>

-   <span data-ttu-id="e8ffe-114">**För slutanvändare**</span><span class="sxs-lookup"><span data-stu-id="e8ffe-114">**For end users**</span></span>

    -   <span data-ttu-id="e8ffe-115">Microsoft Defender för slutpunktslicens tilldelad till slutanvändare av programmet.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="e8ffe-116">Se [Licenskrav för Microsoft Defender för Slutpunkt](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="e8ffe-116">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="e8ffe-117">Intune-företagsportal-appen kan laddas ned från [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) och finns på Android-enheten.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="e8ffe-118">Dessutom kan enheter registreras via appen [Intune-företagsportal](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) för att tillämpa Intune-enhetsefterlevnadsprinciper.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-118">Additionally, device(s) can be [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="e8ffe-119">Det kräver att användaren tilldelas en Microsoft Intune licens.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="e8ffe-120">Mer information om hur du tilldelar licenser finns i [Tilldela användare licenser.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="e8ffe-120">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="e8ffe-121">**För administratörer**</span><span class="sxs-lookup"><span data-stu-id="e8ffe-121">**For Administrators**</span></span>

    -   <span data-ttu-id="e8ffe-122">Åtkomst till Microsoft Defender Säkerhetscenter portalen.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="e8ffe-123">Microsoft Intune är den enda MDM-lösning (Mobile Device Management) som stöds för distribution av Microsoft Defender för slutpunkt på Android.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on Android.</span></span> <span data-ttu-id="e8ffe-124">För närvarande stöds endast registrerade enheter för tvingande Defender för Slutpunkt på Android-relaterade efterlevnadsprinciper för enheter i Intune.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint on Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="e8ffe-125">Access [Microsoft Endpoint Manager administrationscenter](https://go.microsoft.com/fwlink/?linkid=2109431)för att distribuera programmet till registrerade användargrupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>
        
### <a name="network-requirements"></a><span data-ttu-id="e8ffe-126">Nätverkskrav</span><span class="sxs-lookup"><span data-stu-id="e8ffe-126">Network Requirements</span></span>

- <span data-ttu-id="e8ffe-127">För att Microsoft Defender för slutpunkt på Android ska fungera när du är ansluten till ett nätverk måste brandväggen/proxyn konfigureras för att aktivera åtkomst till URL:er för [Microsoft Defender för slutpunktstjänsten.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="e8ffe-127">For Microsoft Defender for Endpoint on Android to function when connected to a network the firewall/proxy will need to be configured to [enable access to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="e8ffe-128">Systemkrav</span><span class="sxs-lookup"><span data-stu-id="e8ffe-128">System Requirements</span></span>

-   <span data-ttu-id="e8ffe-129">Android-enheter med Android 6.0 och högre.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-129">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="e8ffe-130">Intune-företagsportal laddas ned från [Google Play och](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) installeras.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-130">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="e8ffe-131">Enhetsregistrering krävs för att Intune-efterlevnadsprinciper för enheter ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-131">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="e8ffe-132">Installationsanvisningar</span><span class="sxs-lookup"><span data-stu-id="e8ffe-132">Installation instructions</span></span>

<span data-ttu-id="e8ffe-133">Microsoft Defender för slutpunkt på Android har stöd för installation i båda lägen för registrerade enheter – äldre enhetsadministratörs- och Android Enterprise-lägen.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-133">Microsoft Defender for Endpoint on Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="e8ffe-134">**För närvarande stöds personligt ägda enheter med arbetsprofil och företagsägd registrering av fullständigt hanterade användarenheter i Android Enterprise. Stöd för andra företagsläge i Android meddelas när du är klar.**</span><span class="sxs-lookup"><span data-stu-id="e8ffe-134">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrollments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="e8ffe-135">Distribution av Microsoft Defender för slutpunkt på Android sker via Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="e8ffe-135">Deployment of Microsoft Defender for Endpoint on Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="e8ffe-136">Mer information finns i Distribuera [Microsoft Defender för slutpunkt på Android med Microsoft Intune](android-intune.md).</span><span class="sxs-lookup"><span data-stu-id="e8ffe-136">For more information, see [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="e8ffe-137">**Microsoft Defender för slutpunkt på Android är tillgängligt på [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) nu.**</span><span class="sxs-lookup"><span data-stu-id="e8ffe-137">**Microsoft Defender for Endpoint on Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="e8ffe-138">Du kan ansluta till Google Play från Intune för att distribuera Microsoft Defender för slutpunktsappen, över lägen för enhetsadministratör och Android Enterprise-registrering.</span><span class="sxs-lookup"><span data-stu-id="e8ffe-138">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="e8ffe-139">Konfigurera Microsoft Defender för slutpunkt på Android</span><span class="sxs-lookup"><span data-stu-id="e8ffe-139">How to Configure Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="e8ffe-140">Anvisningar om hur du konfigurerar Microsoft Defender för slutpunkt på Android-funktioner finns i [Konfigurera Microsoft Defender för slutpunkt på Android-funktioner.](android-configure.md)</span><span class="sxs-lookup"><span data-stu-id="e8ffe-140">Guidance on how to configure Microsoft Defender for Endpoint on Android features is available in [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="e8ffe-141">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e8ffe-141">Related topics</span></span>
- [<span data-ttu-id="e8ffe-142">Distribuera Microsoft Defender för Endpoint för Android med Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e8ffe-142">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="e8ffe-143">Konfigurera Microsoft Defender för Endpoint för Android-funktioner</span><span class="sxs-lookup"><span data-stu-id="e8ffe-143">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)

