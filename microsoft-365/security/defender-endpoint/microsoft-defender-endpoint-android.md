---
title: Microsoft Defender ATP för Android
ms.reviewer: ''
description: Beskriver hur du installerar och använder Microsoft Defender ATP för Android
keywords: microsoft, defender, atp, android, installation, distribuera, avinstallation, intune
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
ms.openlocfilehash: 6518b86861fd5d03533bb787d4ee005d7ace1a0c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076866"
---
# <a name="microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="88fb7-104">Microsoft Defender för slutpunkt för Android</span><span class="sxs-lookup"><span data-stu-id="88fb7-104">Microsoft Defender for Endpoint for Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="88fb7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="88fb7-105">**Applies to:**</span></span>
- [<span data-ttu-id="88fb7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="88fb7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="88fb7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88fb7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="88fb7-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="88fb7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="88fb7-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="88fb7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="88fb7-110">I det här avsnittet beskrivs hur du installerar, konfigurerar, uppdaterar och använder Defender för slutpunkt för Android.</span><span class="sxs-lookup"><span data-stu-id="88fb7-110">This topic describes how to install, configure, update, and use Defender for Endpoint for Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="88fb7-111">Att köra andra produkter med slutpunktsskydd från tredje part tillsammans med Defender för Slutpunkt för Android kan sannolikt orsaka prestandaproblem och oförutsägbara systemfel.</span><span class="sxs-lookup"><span data-stu-id="88fb7-111">Running other third-party endpoint protection products alongside Defender for Endpoint for Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="88fb7-112">Så här installerar du Microsoft Defender för slutpunkt för Android</span><span class="sxs-lookup"><span data-stu-id="88fb7-112">How to install Microsoft Defender for Endpoint for Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="88fb7-113">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="88fb7-113">Prerequisites</span></span>

-   <span data-ttu-id="88fb7-114">**För slutanvändare**</span><span class="sxs-lookup"><span data-stu-id="88fb7-114">**For end users**</span></span>

    -   <span data-ttu-id="88fb7-115">Microsoft Defender för slutpunktslicens tilldelad till slutanvändare av programmet.</span><span class="sxs-lookup"><span data-stu-id="88fb7-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="88fb7-116">Se [Licenskrav för Microsoft Defender för Slutpunkt](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="88fb7-116">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="88fb7-117">Appen Intune Company Portal kan laddas ned från [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) och är tillgänglig på Android-enheten.</span><span class="sxs-lookup"><span data-stu-id="88fb7-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="88fb7-118">Dessutom kan enheter registreras via [](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) appen Intune-företagsportal för att framtvinga Intune-enhetsefterlevnadsprinciper.</span><span class="sxs-lookup"><span data-stu-id="88fb7-118">Additionally, device(s) can be [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="88fb7-119">Det kräver att användaren tilldelas en Microsoft Intune-licens.</span><span class="sxs-lookup"><span data-stu-id="88fb7-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="88fb7-120">Mer information om hur du tilldelar licenser finns i [Tilldela användare licenser.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="88fb7-120">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="88fb7-121">**För administratörer**</span><span class="sxs-lookup"><span data-stu-id="88fb7-121">**For Administrators**</span></span>

    -   <span data-ttu-id="88fb7-122">Åtkomst till Microsoft Defender Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="88fb7-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="88fb7-123">Microsoft Intune är den enda mdm-lösning (Mobile Device Management) som stöds för distribution av Microsoft Defender för slutpunkt för Android.</span><span class="sxs-lookup"><span data-stu-id="88fb7-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint for Android.</span></span> <span data-ttu-id="88fb7-124">För närvarande stöds endast registrerade enheter för tvingande Defender för Endpoint för Android-relaterade efterlevnadsprinciper för enheter i Intune.</span><span class="sxs-lookup"><span data-stu-id="88fb7-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint for Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="88fb7-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431)för att distribuera appen till registrerade användargrupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="88fb7-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

### <a name="system-requirements"></a><span data-ttu-id="88fb7-126">Systemkrav</span><span class="sxs-lookup"><span data-stu-id="88fb7-126">System Requirements</span></span>

-   <span data-ttu-id="88fb7-127">Android-enheter med Android 6.0 och högre.</span><span class="sxs-lookup"><span data-stu-id="88fb7-127">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="88fb7-128">Appen Intune Company Portal laddas ned från [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) och installeras.</span><span class="sxs-lookup"><span data-stu-id="88fb7-128">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="88fb7-129">Enhetsregistrering krävs för att Intune-efterlevnadsprinciper för enheter ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="88fb7-129">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="88fb7-130">Installationsanvisningar</span><span class="sxs-lookup"><span data-stu-id="88fb7-130">Installation instructions</span></span>

<span data-ttu-id="88fb7-131">Microsoft Defender för slutpunkt för Android har stöd för installation i båda lägen för registrerade enheter – äldre enhetsadministratörs- och Android Enterprise-lägen.</span><span class="sxs-lookup"><span data-stu-id="88fb7-131">Microsoft Defender for Endpoint for Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="88fb7-132">**För närvarande stöds personligt ägda enheter med arbetsprofil och fullständigt hanterade företagsägda användare i Android Enterprise. Stöd för andra företagsläge i Android meddelas när du är klar.**</span><span class="sxs-lookup"><span data-stu-id="88fb7-132">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrolments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="88fb7-133">Distribution av Microsoft Defender för Slutpunkt för Android sker via Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="88fb7-133">Deployment of Microsoft Defender for Endpoint for Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="88fb7-134">Mer information finns i Distribuera [Microsoft Defender för slutpunkt för Android med Microsoft Intune.](android-intune.md)</span><span class="sxs-lookup"><span data-stu-id="88fb7-134">For more information, see [Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="88fb7-135">**Microsoft Defender för slutpunkt för Android är tillgängligt på [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) nu.**</span><span class="sxs-lookup"><span data-stu-id="88fb7-135">**Microsoft Defender for Endpoint for Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="88fb7-136">Du kan ansluta till Google Play från Intune för att distribuera Microsoft Defender för slutpunktsappen, över lägen för enhetsadministratör och Android Enterprise-registrering.</span><span class="sxs-lookup"><span data-stu-id="88fb7-136">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="88fb7-137">Konfigurera Microsoft Defender för slutpunkt för Android</span><span class="sxs-lookup"><span data-stu-id="88fb7-137">How to Configure Microsoft Defender for Endpoint for Android</span></span>

<span data-ttu-id="88fb7-138">Anvisningar om hur du konfigurerar Microsoft Defender för slutpunkt för Android-funktioner finns i [Konfigurera Microsoft Defender för slutpunkt för Android-funktioner.](android-configure.md)</span><span class="sxs-lookup"><span data-stu-id="88fb7-138">Guidance on how to configure Microsoft Defender for Endpoint for Android features is available in [Configure Microsoft Defender for Endpoint for Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="88fb7-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="88fb7-139">Related topics</span></span>
- [<span data-ttu-id="88fb7-140">Distribuera Microsoft Defender för Slutpunkt för med Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="88fb7-140">Deploy Microsoft Defender for Endpoint for with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="88fb7-141">Konfigurera funktioner i Microsoft Defender för Slutpunkt för Android</span><span class="sxs-lookup"><span data-stu-id="88fb7-141">Configure Microsoft Defender for Endpoint for Android features</span></span>](android-configure.md)

