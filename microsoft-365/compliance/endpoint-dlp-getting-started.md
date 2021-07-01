---
title: Komma igång med dataförlustskydd för slutpunkter i Microsoft 365
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Konfigurera dataförlustskydd för slutpunkter i Microsoft 365 för att övervaka filaktiviteter och implementera skyddsåtgärder för dessa filer till slutpunkter.
ms.openlocfilehash: 8dc57bfe395ad76e6b8aef336aaadb2cb7e42f81
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226677"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="c2ef9-103">Komma igång med dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="c2ef9-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="c2ef9-104">Microsofts dataförlustskydd för slutpunkter (Endpoint DLP) är en del av DLP-funktionerna (Data Loss Prevention) i Microsoft 365 som du kan använda för att identifiera och skydda känsliga objekt i Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="c2ef9-105">Mer information om alla Microsofts DLP-erbjudanden finns i [Läs mer om skydd mot dataförlust](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="c2ef9-105">For more information about all of Microsoft’s DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span> <span data-ttu-id="c2ef9-106">Mer information om slutpunkts-DLP finns i [Läs mer om dataförlustskydd för slutpunkter](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="c2ef9-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="c2ef9-107">Med Microsofts dataförlustskydd för slutpunkter kan du övervaka Windows 10-enheter och identifiera när känsliga objekt används och delas.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="c2ef9-108">På så sätt får du den synlighet och kontroll som du behöver för att säkerställa att de används och skyddas på rätt sätt och för att förhindra riskfaktorer som kan avslöja dem.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c2ef9-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="c2ef9-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="c2ef9-110">Licensiering av SKU/prenumerationer</span><span class="sxs-lookup"><span data-stu-id="c2ef9-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="c2ef9-111">Innan du börjar med slutpunkts-DLP måste du bekräfta din [Microsoft 365-prenumeration](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) och eventuella tillägg.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="c2ef9-112">Om du vill komma åt och använda slutpunkts-DLP, måste du ha någon av dessa prenumerationer eller tillägg.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="c2ef9-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c2ef9-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="c2ef9-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="c2ef9-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="c2ef9-115">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="c2ef9-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="c2ef9-116">Microsoft 365 A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="c2ef9-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="c2ef9-117">Microsoft 365 E5 – Informationsskydd och styrning</span><span class="sxs-lookup"><span data-stu-id="c2ef9-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="c2ef9-118">Microsoft 365 A5 – Informationsskydd och styrning</span><span class="sxs-lookup"><span data-stu-id="c2ef9-118">Microsoft 365 A5 information protection and governance</span></span>

### <a name="permissions"></a><span data-ttu-id="c2ef9-119">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="c2ef9-119">Permissions</span></span>

<span data-ttu-id="c2ef9-120">För att aktivera enhetshantering måste det konto du använder vara medlem i någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="c2ef9-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="c2ef9-121">Global administratör</span><span class="sxs-lookup"><span data-stu-id="c2ef9-121">Global admin</span></span>
- <span data-ttu-id="c2ef9-122">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="c2ef9-122">Security admin</span></span>
- <span data-ttu-id="c2ef9-123">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="c2ef9-123">Compliance admin</span></span>

<span data-ttu-id="c2ef9-124">Om du vill använda ett anpassat konto för att visa inställningar för enhetshantering måste det ingå i någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="c2ef9-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="c2ef9-125">Global administratör</span><span class="sxs-lookup"><span data-stu-id="c2ef9-125">Global admin</span></span>
- <span data-ttu-id="c2ef9-126">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="c2ef9-126">Compliance admin</span></span>
- <span data-ttu-id="c2ef9-127">Administratör för efterlevnadsdata</span><span class="sxs-lookup"><span data-stu-id="c2ef9-127">Compliance data admin</span></span>
- <span data-ttu-id="c2ef9-128">Global läsare</span><span class="sxs-lookup"><span data-stu-id="c2ef9-128">Global reader</span></span>

<span data-ttu-id="c2ef9-129">Om du vill använda ett anpassat konto för att få åtkomst till sidan för registrering/avregistrering måste det ingå i någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="c2ef9-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="c2ef9-130">Global administratör</span><span class="sxs-lookup"><span data-stu-id="c2ef9-130">Global admin</span></span>
- <span data-ttu-id="c2ef9-131">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="c2ef9-131">Compliance admin</span></span>

<span data-ttu-id="c2ef9-132">Om du vill använda ett anpassat konto för att aktivera/inaktivera enhetsövervakning måste det ingå i någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="c2ef9-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="c2ef9-133">Global administratör</span><span class="sxs-lookup"><span data-stu-id="c2ef9-133">Global admin</span></span>
- <span data-ttu-id="c2ef9-134">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="c2ef9-134">Compliance admin</span></span>

<span data-ttu-id="c2ef9-135">Data från slutpunkts-DLP kan visas i [Aktivitetsutforskaren](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="c2ef9-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="c2ef9-136">Det finns fyra roller som ger behörighet till aktivitetsutforskaren och det konto som du använder för att komma åt data måste vara medlem i någon av dem.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="c2ef9-137">Global administratör</span><span class="sxs-lookup"><span data-stu-id="c2ef9-137">Global admin</span></span>
- <span data-ttu-id="c2ef9-138">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="c2ef9-138">Compliance admin</span></span>
- <span data-ttu-id="c2ef9-139">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="c2ef9-139">Security admin</span></span>
- <span data-ttu-id="c2ef9-140">Administratör för efterlevnadsdata</span><span class="sxs-lookup"><span data-stu-id="c2ef9-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="c2ef9-141">Förbered dina slutpunkter</span><span class="sxs-lookup"><span data-stu-id="c2ef9-141">Prepare your endpoints</span></span>

<span data-ttu-id="c2ef9-142">Kontrollera att de Windows 10-enheter som du planerar att distribuera slutpunkts-DLP till uppfyller de här kraven.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="c2ef9-143">Måste köra Windows 10 x64 version 1809 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-143">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="c2ef9-144">Klientversion för program mot skadlig kod version 4.18.2009.7 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-144">Antimalware Client Version is 4.18.2009.7 or newer.</span></span> <span data-ttu-id="c2ef9-145">Kontrollera din aktuella version genom att öppna Windows-säkerhet, välja ikonen Inställningar och sedan Om.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-145">Check your current version by opening Windows Security app, select the Settings icon, and then select About.</span></span> <span data-ttu-id="c2ef9-146">Versionsnumret visas under Klientversion för program mot skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-146">The version number is listed under Antimalware Client Version.</span></span> <span data-ttu-id="c2ef9-147">Uppdatera till den senaste klientversionen för program mot skadlig kod genom att installera Windows Update KB4052623.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-147">Update to the latest Antimalware Client Version by installing Windows Update KB4052623.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c2ef9-148">Ingen av Windows-säkerhetskomponenterna behöver vara aktiv. Du kan köra slutpunkts-DLP oberoende av Windows-säkerhetsstatus, men [Realtidsskydd och beteendeövervakning](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) måste vara aktiverat.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-148">None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status, but the [Real-time protection and Behavior monitor](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)) must be enabled.</span></span>

3. <span data-ttu-id="c2ef9-149">Följande Windows-uppdateringar installeras.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-149">The following Windows Updates are installed.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c2ef9-150">Dessa uppdateringar är inte en förutsättning för att en enhet ska kunna installeras i slutpunkt-DLP, men innehåller korrigeringar för viktiga problem som gör att de måste installeras innan produkten används.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-150">These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

   - <span data-ttu-id="c2ef9-151">För Windows 10 1809 – KB4559003, KB4577069, KB4580390</span><span class="sxs-lookup"><span data-stu-id="c2ef9-151">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
   - <span data-ttu-id="c2ef9-152">För Windows 10 1903 eller 1909 – KB4559004, KB4577062, KB4580386</span><span class="sxs-lookup"><span data-stu-id="c2ef9-152">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
   - <span data-ttu-id="c2ef9-153">För Windows 10 2004 – KB4568831, KB4577063</span><span class="sxs-lookup"><span data-stu-id="c2ef9-153">For Windows 10 2004 - KB4568831, KB4577063</span></span>
   - <span data-ttu-id="c2ef9-154">För enheter med Office 2016 (och inte någon annan Office-version) – KB4577063</span><span class="sxs-lookup"><span data-stu-id="c2ef9-154">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span>

4. <span data-ttu-id="c2ef9-155">Alla enheter måste vara någon av följande:</span><span class="sxs-lookup"><span data-stu-id="c2ef9-155">All devices must be one of these:</span></span>

   - [<span data-ttu-id="c2ef9-156">Azure Active Directory (AAD)-ansluten</span><span class="sxs-lookup"><span data-stu-id="c2ef9-156">Azure Active Directory (Azure AD) joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
   - [<span data-ttu-id="c2ef9-157">Hybrid Azure AD-ansluten</span><span class="sxs-lookup"><span data-stu-id="c2ef9-157">Hybrid Azure AD joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join-hybrid)
   - [<span data-ttu-id="c2ef9-158">AAD-registrerad</span><span class="sxs-lookup"><span data-stu-id="c2ef9-158">AAD registered</span></span>](/azure/active-directory/user-help/user-help-register-device-on-network)

5. <span data-ttu-id="c2ef9-159">Installera webbläsaren Microsoft Chromium Edge på slutpunktsenheten för att framtvinga principåtgärder för aktiviteten uppladdning till moln.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-159">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="c2ef9-160">Se [Ladda ned nya Microsoft Edge som baseras på Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="c2ef9-160">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="c2ef9-161">Om du använder Månadskanal för företag för versionerna 2004–2008 av Microsoft 365-appar finns det ett känt problem med klassificering av Office-innehåll med slutpunkts-DLP och du behöver uppdatera till version 2009 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-161">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later.</span></span> <span data-ttu-id="c2ef9-162">Se [Uppdateringshistorik för Microsoft 365-appar (visas efter datum)](/officeupdates/update-history-microsoft365-apps-by-date) för aktuella versioner.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-162">See [Update history for Microsoft 365 Apps (listed by date)](/officeupdates/update-history-microsoft365-apps-by-date) for current versions.</span></span> <span data-ttu-id="c2ef9-163">Mer information om det här problemet finns i avsnittet Office-programsviten i [Viktig information om aktuella kanalutgivningar under 2020](/officeupdates/current-channel#version-2010-october-27).</span><span class="sxs-lookup"><span data-stu-id="c2ef9-163">To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](/officeupdates/current-channel#version-2010-october-27).</span></span>

7. <span data-ttu-id="c2ef9-164">Om du har slutpunkter som använder en enhetsproxy för att ansluta till Internet följer du procedurerna i [Konfigurera enhetsproxy och Internetanslutningsinställningar för slutpunkts-DLP](endpoint-dlp-configure-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="c2ef9-164">If you have endpoints that use a device proxy to connect to the internet, follow the procedures in [Configure device proxy and internet connection settings for Endpoint DLP](endpoint-dlp-configure-proxy.md).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="c2ef9-165">Registrering av enheter i Enhetshantering</span><span class="sxs-lookup"><span data-stu-id="c2ef9-165">Onboarding devices into device management</span></span>

<span data-ttu-id="c2ef9-166">Du måste aktivera enhetsövervakning och registrera dina slutpunkter innan du kan övervaka och skydda känsliga objekt på en enhet.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-166">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="c2ef9-167">Båda dessa åtgärder utförs i portalen Microsoft 365 Efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-167">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="c2ef9-168">Om du vill registrera enheter som ännu inte har registrerats, laddar du ned rätt skript och distribuerar det till de enheterna.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-168">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="c2ef9-169">Följ [proceduren för att registrera enheter](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="c2ef9-169">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="c2ef9-170">Om du redan har enheter registrerade i [Microsoft Defender för Endpoint](/windows/security/threat-protection/) visas de redan i listan över hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-170">If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="c2ef9-171">Följ proceduren [Med enheter registrerade i Microsoft Defender för Endpoint](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span><span class="sxs-lookup"><span data-stu-id="c2ef9-171">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="c2ef9-172">Registrera enheter</span><span class="sxs-lookup"><span data-stu-id="c2ef9-172">Onboarding devices</span></span>

<span data-ttu-id="c2ef9-173">I det här distributionsscenariot kan du registrera enheter som ännu inte har registrerats, och du bara vill övervaka och skydda känsliga objekt från oavsiktlig delning på Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-173">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="c2ef9-174">Öppna [Microsoft Efterlevnadscenter](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c2ef9-174">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="c2ef9-175">Öppna inställningssidan för Efterlevnadscenter och välj **Registrera enheter**.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-175">Open the Compliance Center settings page and choose **Onboard devices**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2ef9-176">![aktivera enhetshantering](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="c2ef9-176">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="c2ef9-177">Det tar normalt ca 60 sekunder innan enhetsregistreringen är aktiverad, men du kan vänta upp till 30 minuter innan du kontaktar Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-177">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="c2ef9-178">Välj **Enhetshantering** för att öppna listan **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-178">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="c2ef9-179">Listan är tom tills du har registrerat enheter.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-179">The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="c2ef9-180">Välj **Registrering** för att starta registreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-180">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="c2ef9-181">Välj hur du vill distribuera till dessa ytterligare enheter i listan **Distributionsmetod** och **ladda sedan ned paketet**.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-181">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2ef9-182">![distributionsmetod](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="c2ef9-182">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>

6. <span data-ttu-id="c2ef9-183">Följ lämpliga instruktioner i [Registrera verktyg och metoder för Windows 10-datorer](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="c2ef9-183">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="c2ef9-184">Den här länken tar dig till en landningssida där du kan komma åt procedurer för Microsoft Defender för Endpoint som matchar distributionspaketet du valde i steg 5:</span><span class="sxs-lookup"><span data-stu-id="c2ef9-184">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="c2ef9-185">Registrera Windows 10-datorer med hjälp av grupprincip</span><span class="sxs-lookup"><span data-stu-id="c2ef9-185">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="c2ef9-186">Registrera Windows-datorer med Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c2ef9-186">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="c2ef9-187">Registrera Windows 10-datorer med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="c2ef9-187">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="c2ef9-188">Registrera Windows 10-datorer med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="c2ef9-188">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="c2ef9-189">Registrera icke beständiga VDI-datorer (Virtual Desktop Infrastructure) i enkelsessionsscenarion.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-189">Onboard non-persistent virtual desktop infrastructure (VDI) machines in single-session scenarios</span></span>

<span data-ttu-id="c2ef9-190">När du är klar och slutpunkten har registrerats ska den visas i listan över enheter och även börja rapportera granskningsaktivitetsloggar i Aktivitetsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-190">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="c2ef9-191">För den här funktionen tillämpas licensiering.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-191">This experience is under license enforcement.</span></span> <span data-ttu-id="c2ef9-192">Utan rätt licens kommer data inte att visas och inte vara tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-192">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="c2ef9-193">Med enheter registrerade i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c2ef9-193">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="c2ef9-194">I det här scenariot är Microsoft Defender för Endpoint redan distribuerat och det finns slutpunkter som rapporterar.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-194">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="c2ef9-195">Alla dessa slutpunkter visas i listan över hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-195">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="c2ef9-196">Du kan fortsätta registrera nya enheter i slutpunkts-DLP för att få ökad täckning med hjälp av [proceduren för att registrera enheter](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="c2ef9-196">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="c2ef9-197">Öppna [Microsoft Efterlevnadscenter](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c2ef9-197">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="c2ef9-198">Öppna inställningssidan för Efterlevnadscenter och välj **Aktivera enhetsövervakning**.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-198">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="c2ef9-199">Välj **Enhetshantering** för att öppna listan **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-199">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="c2ef9-200">Listan över enheter som redan rapporterar till Microsoft Defender för Endpoint visas.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-200">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2ef9-201">![enhetshantering](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="c2ef9-201">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>

4. <span data-ttu-id="c2ef9-202">Välj **Registrering** om du behöver registrera ytterligare enheter.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-202">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="c2ef9-203">Välj hur du vill distribuera till dessa ytterligare enheter i listan **Distributionsmetod** och **ladda sedan ned paketet**.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-203">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="c2ef9-204">Följ lämpliga instruktioner i [Registrera verktyg och metoder för Windows 10-datorer](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="c2ef9-204">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="c2ef9-205">Den här länken tar dig till en landningssida där du kan komma åt procedurer för Microsoft Defender för Endpoint som matchar distributionspaketet du valde i steg 5:</span><span class="sxs-lookup"><span data-stu-id="c2ef9-205">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="c2ef9-206">Registrera Windows 10-datorer med hjälp av grupprincip</span><span class="sxs-lookup"><span data-stu-id="c2ef9-206">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="c2ef9-207">Registrera Windows-datorer med Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c2ef9-207">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="c2ef9-208">Registrera Windows 10-datorer med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="c2ef9-208">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="c2ef9-209">Registrera Windows 10-datorer med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="c2ef9-209">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="c2ef9-210">Registrera icke beständiga VDI-datorer (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="c2ef9-210">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="c2ef9-211">När du är klar och slutpunkten har registrerats ska den visas under tabellen **Enheter** och även börja rapportera granskningsloggar till **Aktivitetsutforskaren**.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-211">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="c2ef9-212">För den här funktionen tillämpas licensiering.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-212">This experience is under license enforcement.</span></span> <span data-ttu-id="c2ef9-213">Utan rätt licens kommer data inte att visas och inte vara tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-213">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="c2ef9-214">Visa aviseringar för slutpunkts-DLP i instrumentpanelen för hantering av DLP-aviseringar</span><span class="sxs-lookup"><span data-stu-id="c2ef9-214">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="c2ef9-215">Öppna sidan Dataförlustskydd i Microsoft 365 Efterlevnadscenter och välj Varningar.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-215">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="c2ef9-216">Se metoderna i [Konfigurera och visa aviseringar för DLP-principer](dlp-configure-view-alerts-policies.md) om du vill se aviseringarna för slutpunkts-DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-216">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="c2ef9-217">Visa data för slutpunkts-DLP i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="c2ef9-217">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="c2ef9-218">Öppna [sidan Dataklassificering](https://compliance.microsoft.com/dataclassification?viewid=overview) för din domän i Microsoft 365 Efterlevnadscenter och välj Aktivitetsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-218">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="c2ef9-219">Se metoderna i [Kom igång med aktivitetsutforskaren](data-classification-activity-explorer.md) för att komma åt och filtrera alla data för slutpunktsenheterna.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-219">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2ef9-220">![aktivitetsutforskarens filter för slutpunktsenheter](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="c2ef9-220">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="c2ef9-221">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c2ef9-221">Next steps</span></span>

<span data-ttu-id="c2ef9-222">Nu när du har registrerat enheter och kan se aktivitetsdata i aktivitetsutforskaren, kan du gå vidare till nästa steg där du skapar DLP-principer som skyddar dina känsliga objekt.</span><span class="sxs-lookup"><span data-stu-id="c2ef9-222">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="c2ef9-223">Använda dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="c2ef9-223">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="c2ef9-224">Se även</span><span class="sxs-lookup"><span data-stu-id="c2ef9-224">See also</span></span>

- [<span data-ttu-id="c2ef9-225">Mer information om dataförlustskydd för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="c2ef9-225">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="c2ef9-226">Använda dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="c2ef9-226">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="c2ef9-227">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="c2ef9-227">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="c2ef9-228">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="c2ef9-228">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="c2ef9-229">Kom igång med aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="c2ef9-229">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="c2ef9-230">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c2ef9-230">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="c2ef9-231">Registreringsverktyg och metoder för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="c2ef9-231">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="c2ef9-232">Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="c2ef9-232">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="c2ef9-233">Azure AD-anslutna enheter</span><span class="sxs-lookup"><span data-stu-id="c2ef9-233">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="c2ef9-234">Ladda ned nya Microsoft Edge som baseras på Chromium</span><span class="sxs-lookup"><span data-stu-id="c2ef9-234">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
