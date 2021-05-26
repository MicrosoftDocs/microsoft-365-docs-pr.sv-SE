---
title: Komma igång med dataförlustskydd för slutpunkter i Microsoft 365
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
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
ms.openlocfilehash: a6c0ec6f1248fdeecd8616b7eda000b7608d452d
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651014"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="28b49-103">Komma igång med dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="28b49-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="28b49-104">Microsofts dataförlustskydd för slutpunkter (Endpoint DLP) är en del av DLP-funktionerna (Data Loss Prevention) i Microsoft 365 som du kan använda för att identifiera och skydda känsliga objekt i Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="28b49-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="28b49-105">Mer information om alla Microsofts DLP-erbjudanden finns i [Läs mer om skydd mot dataförlust](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="28b49-105">For more information about all of Microsoft’s DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span> <span data-ttu-id="28b49-106">Mer information om slutpunkts-DLP finns i [Läs mer om dataförlustskydd för slutpunkter](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="28b49-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="28b49-107">Med Microsofts dataförlustskydd för slutpunkter kan du övervaka Windows 10-enheter och identifiera när känsliga objekt används och delas.</span><span class="sxs-lookup"><span data-stu-id="28b49-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="28b49-108">På så sätt får du den synlighet och kontroll som du behöver för att säkerställa att de används och skyddas på rätt sätt och för att förhindra riskfaktorer som kan avslöja dem.</span><span class="sxs-lookup"><span data-stu-id="28b49-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="28b49-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="28b49-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="28b49-110">Licensiering av SKU/prenumerationer</span><span class="sxs-lookup"><span data-stu-id="28b49-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="28b49-111">Innan du börjar med slutpunkts-DLP måste du bekräfta din [Microsoft 365-prenumeration](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) och eventuella tillägg.</span><span class="sxs-lookup"><span data-stu-id="28b49-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="28b49-112">Om du vill komma åt och använda slutpunkts-DLP, måste du ha någon av dessa prenumerationer eller tillägg.</span><span class="sxs-lookup"><span data-stu-id="28b49-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="28b49-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="28b49-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="28b49-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="28b49-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="28b49-115">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="28b49-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="28b49-116">Microsoft 365 A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="28b49-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="28b49-117">Microsoft 365 E5 – Informationsskydd och styrning</span><span class="sxs-lookup"><span data-stu-id="28b49-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="28b49-118">Microsoft 365 A5 – Informationsskydd och styrning</span><span class="sxs-lookup"><span data-stu-id="28b49-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="28b49-119">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="28b49-119">Permissions</span></span>

<span data-ttu-id="28b49-120">För att aktivera enhetshantering måste det konto du använder vara medlem i någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="28b49-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="28b49-121">Global administratör</span><span class="sxs-lookup"><span data-stu-id="28b49-121">Global admin</span></span>
- <span data-ttu-id="28b49-122">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="28b49-122">Security admin</span></span>
- <span data-ttu-id="28b49-123">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="28b49-123">Compliance admin</span></span>

<span data-ttu-id="28b49-124">Om du vill använda ett anpassat konto för att visa inställningar för enhetshantering måste det ingå i någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="28b49-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="28b49-125">Global administratör</span><span class="sxs-lookup"><span data-stu-id="28b49-125">Global admin</span></span>
- <span data-ttu-id="28b49-126">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="28b49-126">Compliance admin</span></span>
- <span data-ttu-id="28b49-127">Administratör för efterlevnadsdata</span><span class="sxs-lookup"><span data-stu-id="28b49-127">Compliance data admin</span></span>
- <span data-ttu-id="28b49-128">Global läsare</span><span class="sxs-lookup"><span data-stu-id="28b49-128">Global reader</span></span>

<span data-ttu-id="28b49-129">Om du vill använda ett anpassat konto för att få åtkomst till sidan för registrering/avregistrering måste det ingå i någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="28b49-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="28b49-130">Global administratör</span><span class="sxs-lookup"><span data-stu-id="28b49-130">Global admin</span></span>
- <span data-ttu-id="28b49-131">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="28b49-131">Compliance admin</span></span>

<span data-ttu-id="28b49-132">Om du vill använda ett anpassat konto för att aktivera/inaktivera enhetsövervakning måste det ingå i någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="28b49-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="28b49-133">Global administratör</span><span class="sxs-lookup"><span data-stu-id="28b49-133">Global admin</span></span>
- <span data-ttu-id="28b49-134">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="28b49-134">Compliance admin</span></span>

<span data-ttu-id="28b49-135">Data från slutpunkts-DLP kan visas i [Aktivitetsutforskaren](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="28b49-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="28b49-136">Det finns fyra roller som ger behörighet till aktivitetsutforskaren och det konto som du använder för att komma åt data måste vara medlem i någon av dem.</span><span class="sxs-lookup"><span data-stu-id="28b49-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="28b49-137">Global administratör</span><span class="sxs-lookup"><span data-stu-id="28b49-137">Global admin</span></span>
- <span data-ttu-id="28b49-138">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="28b49-138">Compliance admin</span></span>
- <span data-ttu-id="28b49-139">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="28b49-139">Security admin</span></span>
- <span data-ttu-id="28b49-140">Administratör för efterlevnadsdata</span><span class="sxs-lookup"><span data-stu-id="28b49-140">Compliance data admin</span></span>
- <span data-ttu-id="28b49-141">Global läsare</span><span class="sxs-lookup"><span data-stu-id="28b49-141">Global reader</span></span>
- <span data-ttu-id="28b49-142">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="28b49-142">Security reader</span></span>
- <span data-ttu-id="28b49-143">Rapportläsare</span><span class="sxs-lookup"><span data-stu-id="28b49-143">Reports reader</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="28b49-144">Förbered dina slutpunkter</span><span class="sxs-lookup"><span data-stu-id="28b49-144">Prepare your endpoints</span></span>

<span data-ttu-id="28b49-145">Kontrollera att de Windows 10-enheter som du planerar att distribuera slutpunkts-DLP till uppfyller de här kraven.</span><span class="sxs-lookup"><span data-stu-id="28b49-145">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="28b49-146">Måste köra Windows 10 x64 version 1809 eller senare.</span><span class="sxs-lookup"><span data-stu-id="28b49-146">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="28b49-147">Klientversion för program mot skadlig kod version 4.18.2009.7 eller senare.</span><span class="sxs-lookup"><span data-stu-id="28b49-147">Antimalware Client Version is 4.18.2009.7 or newer.</span></span> <span data-ttu-id="28b49-148">Kontrollera din aktuella version genom att öppna Windows-säkerhet, välja ikonen Inställningar och sedan Om.</span><span class="sxs-lookup"><span data-stu-id="28b49-148">Check your current version by opening Windows Security app, select the Settings icon, and then select About.</span></span> <span data-ttu-id="28b49-149">Versionsnumret visas under Klientversion för program mot skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="28b49-149">The version number is listed under Antimalware Client Version.</span></span> <span data-ttu-id="28b49-150">Uppdatera till den senaste klientversionen för program mot skadlig kod genom att installera Windows Update KB4052623.</span><span class="sxs-lookup"><span data-stu-id="28b49-150">Update to the latest Antimalware Client Version by installing Windows Update KB4052623.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="28b49-151">Ingen av Windows-säkerhetskomponenterna behöver vara aktiv. Du kan köra slutpunkts-DLP oberoende av Windows-säkerhetsstatus, men [Realtidsskydd och beteendeövervakning](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) måste vara aktiverat.</span><span class="sxs-lookup"><span data-stu-id="28b49-151">None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status, but the [Real-time protection and Behavior monitor](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)) must be enabled.</span></span>
 
3. <span data-ttu-id="28b49-152">Följande Windows-uppdateringar installeras.</span><span class="sxs-lookup"><span data-stu-id="28b49-152">The following Windows Updates are installed.</span></span> 
 
   > [!NOTE]
   > <span data-ttu-id="28b49-153">Dessa uppdateringar är inte en förutsättning för att en enhet ska kunna installeras i slutpunkt-DLP, men innehåller korrigeringar för viktiga problem som gör att de måste installeras innan produkten används.</span><span class="sxs-lookup"><span data-stu-id="28b49-153">These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="28b49-154">För Windows 10 1809 – KB4559003, KB4577069, KB4580390</span><span class="sxs-lookup"><span data-stu-id="28b49-154">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="28b49-155">För Windows 10 1903 eller 1909 – KB4559004, KB4577062, KB4580386</span><span class="sxs-lookup"><span data-stu-id="28b49-155">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="28b49-156">För Windows 10 2004 – KB4568831, KB4577063</span><span class="sxs-lookup"><span data-stu-id="28b49-156">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="28b49-157">För enheter med Office 2016 (och inte någon annan Office-version) – KB4577063</span><span class="sxs-lookup"><span data-stu-id="28b49-157">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="28b49-158">Alla enheter måste vara någon av följande:</span><span class="sxs-lookup"><span data-stu-id="28b49-158">All devices must be one of these:</span></span>
- [<span data-ttu-id="28b49-159">Azure Active Directory (AAD)-ansluten</span><span class="sxs-lookup"><span data-stu-id="28b49-159">Azure Active Directory (Azure AD) joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- <span data-ttu-id="28b49-160">AD-ansluten</span><span class="sxs-lookup"><span data-stu-id="28b49-160">AD joined</span></span>
- [<span data-ttu-id="28b49-161">Hybrid Azure AD-ansluten</span><span class="sxs-lookup"><span data-stu-id="28b49-161">Hybrid Azure AD joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join-hybrid)
- [<span data-ttu-id="28b49-162">AAD-registrerad</span><span class="sxs-lookup"><span data-stu-id="28b49-162">AAD registered</span></span>](/azure/active-directory/user-help/user-help-register-device-on-network)

5. <span data-ttu-id="28b49-163">Installera webbläsaren Microsoft Chromium Edge på slutpunktsenheten för att framtvinga principåtgärder för aktiviteten uppladdning till moln.</span><span class="sxs-lookup"><span data-stu-id="28b49-163">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="28b49-164">Se [Ladda ned nya Microsoft Edge som baseras på Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="28b49-164">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="28b49-165">Om du använder Månadskanal för företag för versionerna 2004–2008 av Microsoft 365-appar finns det ett känt problem med klassificering av Office-innehåll med slutpunkts-DLP och du behöver uppdatera till version 2009 eller senare.</span><span class="sxs-lookup"><span data-stu-id="28b49-165">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later.</span></span> <span data-ttu-id="28b49-166">Se [Uppdateringshistorik för Microsoft 365-appar (visas efter datum)](/officeupdates/update-history-microsoft365-apps-by-date) för aktuella versioner.</span><span class="sxs-lookup"><span data-stu-id="28b49-166">See [Update history for Microsoft 365 Apps (listed by date)](/officeupdates/update-history-microsoft365-apps-by-date) for current versions.</span></span> <span data-ttu-id="28b49-167">Mer information om det här problemet finns i avsnittet Office-programsviten i [Viktig information om aktuella kanalutgivningar under 2020](/officeupdates/current-channel#version-2010-october-27).</span><span class="sxs-lookup"><span data-stu-id="28b49-167">To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](/officeupdates/current-channel#version-2010-october-27).</span></span>

7. <span data-ttu-id="28b49-168">Om du har slutpunkter som använder en enhetsproxy för att ansluta till Internet följer du procedurerna i [Konfigurera enhetsproxy och Internetanslutningsinställningar för slutpunkts-DLP](endpoint-dlp-configure-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="28b49-168">If you have endpoints that use a device proxy to connect to the internet, follow the procedures in [Configure device proxy and internet connection settings for Endpoint DLP](endpoint-dlp-configure-proxy.md).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="28b49-169">Registrering av enheter i Enhetshantering</span><span class="sxs-lookup"><span data-stu-id="28b49-169">Onboarding devices into device management</span></span>

<span data-ttu-id="28b49-170">Du måste aktivera enhetsövervakning och registrera dina slutpunkter innan du kan övervaka och skydda känsliga objekt på en enhet.</span><span class="sxs-lookup"><span data-stu-id="28b49-170">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="28b49-171">Båda dessa åtgärder utförs i portalen Microsoft 365 Efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="28b49-171">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="28b49-172">Om du vill registrera enheter som ännu inte har registrerats, laddar du ned rätt skript och distribuerar det till de enheterna.</span><span class="sxs-lookup"><span data-stu-id="28b49-172">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="28b49-173">Följ [proceduren för att registrera enheter](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="28b49-173">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="28b49-174">Om du redan har enheter registrerade i [Microsoft Defender för Endpoint](/windows/security/threat-protection/) visas de redan i listan över hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="28b49-174">If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="28b49-175">Följ proceduren [Med enheter registrerade i Microsoft Defender för Endpoint](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span><span class="sxs-lookup"><span data-stu-id="28b49-175">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="28b49-176">Registrera enheter</span><span class="sxs-lookup"><span data-stu-id="28b49-176">Onboarding devices</span></span>

<span data-ttu-id="28b49-177">I det här distributionsscenariot kan du registrera enheter som ännu inte har registrerats, och du bara vill övervaka och skydda känsliga objekt från oavsiktlig delning på Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="28b49-177">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="28b49-178">Öppna [Microsoft Efterlevnadscenter](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="28b49-178">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="28b49-179">Öppna inställningssidan för Efterlevnadscenter och välj **Registrera enheter**.</span><span class="sxs-lookup"><span data-stu-id="28b49-179">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="28b49-180">![aktivera enhetshantering](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="28b49-180">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="28b49-181">Det tar normalt ca 60 sekunder innan enhetsregistreringen är aktiverad, men du kan vänta upp till 30 minuter innan du kontaktar Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="28b49-181">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="28b49-182">Välj **Enhetshantering** för att öppna listan **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="28b49-182">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="28b49-183">Listan är tom tills du har registrerat enheter.</span><span class="sxs-lookup"><span data-stu-id="28b49-183">The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="28b49-184">Välj **Registrering** för att starta registreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="28b49-184">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="28b49-185">Välj hur du vill distribuera till dessa ytterligare enheter i listan **Distributionsmetod** och **ladda sedan ned paketet**.</span><span class="sxs-lookup"><span data-stu-id="28b49-185">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="28b49-186">![distributionsmetod](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="28b49-186">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="28b49-187">Följ lämpliga instruktioner i [Registrera verktyg och metoder för Windows 10-datorer](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="28b49-187">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="28b49-188">Den här länken tar dig till en landningssida där du kan komma åt procedurer för Microsoft Defender för Endpoint som matchar distributionspaketet du valde i steg 5:</span><span class="sxs-lookup"><span data-stu-id="28b49-188">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="28b49-189">Registrera Windows 10-datorer med hjälp av grupprincip</span><span class="sxs-lookup"><span data-stu-id="28b49-189">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="28b49-190">Registrera Windows-datorer med Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="28b49-190">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="28b49-191">Registrera Windows 10-datorer med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="28b49-191">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="28b49-192">Registrera Windows 10-datorer med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="28b49-192">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="28b49-193">Registrera icke beständiga VDI-datorer (Virtual Desktop Infrastructure) i enkelsessionsscenarion.</span><span class="sxs-lookup"><span data-stu-id="28b49-193">Onboard non-persistent virtual desktop infrastructure (VDI) machines in single-session scenarios</span></span>

<span data-ttu-id="28b49-194">När du är klar och slutpunkten har registrerats ska den visas i listan över enheter och även börja rapportera granskningsaktivitetsloggar i Aktivitetsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="28b49-194">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="28b49-195">För den här funktionen tillämpas licensiering.</span><span class="sxs-lookup"><span data-stu-id="28b49-195">This experience is under license enforcement.</span></span> <span data-ttu-id="28b49-196">Utan rätt licens kommer data inte att visas och inte vara tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="28b49-196">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="28b49-197">Med enheter registrerade i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="28b49-197">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="28b49-198">I det här scenariot är Microsoft Defender för Endpoint redan distribuerat och det finns slutpunkter som rapporterar.</span><span class="sxs-lookup"><span data-stu-id="28b49-198">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="28b49-199">Alla dessa slutpunkter visas i listan över hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="28b49-199">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="28b49-200">Du kan fortsätta registrera nya enheter i slutpunkts-DLP för att få ökad täckning med hjälp av [proceduren för att registrera enheter](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="28b49-200">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="28b49-201">Öppna [Microsoft Efterlevnadscenter](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="28b49-201">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="28b49-202">Öppna inställningssidan för Efterlevnadscenter och välj **Aktivera enhetsövervakning**.</span><span class="sxs-lookup"><span data-stu-id="28b49-202">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="28b49-203">Välj **Enhetshantering** för att öppna listan **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="28b49-203">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="28b49-204">Listan över enheter som redan rapporterar till Microsoft Defender för Endpoint visas.</span><span class="sxs-lookup"><span data-stu-id="28b49-204">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="28b49-205">![enhetshantering](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="28b49-205">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="28b49-206">Välj **Registrering** om du behöver registrera ytterligare enheter.</span><span class="sxs-lookup"><span data-stu-id="28b49-206">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="28b49-207">Välj hur du vill distribuera till dessa ytterligare enheter i listan **Distributionsmetod** och **ladda sedan ned paketet**.</span><span class="sxs-lookup"><span data-stu-id="28b49-207">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="28b49-208">Följ lämpliga instruktioner i [Registrera verktyg och metoder för Windows 10-datorer](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="28b49-208">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="28b49-209">Den här länken tar dig till en landningssida där du kan komma åt procedurer för Microsoft Defender för Endpoint som matchar distributionspaketet du valde i steg 5:</span><span class="sxs-lookup"><span data-stu-id="28b49-209">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="28b49-210">Registrera Windows 10-datorer med hjälp av grupprincip</span><span class="sxs-lookup"><span data-stu-id="28b49-210">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="28b49-211">Registrera Windows-datorer med Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="28b49-211">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="28b49-212">Registrera Windows 10-datorer med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="28b49-212">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="28b49-213">Registrera Windows 10-datorer med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="28b49-213">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="28b49-214">Registrera icke beständiga VDI-datorer (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="28b49-214">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="28b49-215">När du är klar och slutpunkten har registrerats ska den visas under tabellen **Enheter** och även börja rapportera granskningsloggar till **Aktivitetsutforskaren**.</span><span class="sxs-lookup"><span data-stu-id="28b49-215">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="28b49-216">För den här funktionen tillämpas licensiering.</span><span class="sxs-lookup"><span data-stu-id="28b49-216">This experience is under license enforcement.</span></span> <span data-ttu-id="28b49-217">Utan rätt licens kommer data inte att visas och inte vara tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="28b49-217">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="28b49-218">Visa aviseringar för slutpunkts-DLP i instrumentpanelen för hantering av DLP-aviseringar</span><span class="sxs-lookup"><span data-stu-id="28b49-218">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="28b49-219">Öppna sidan Dataförlustskydd i Microsoft 365 Efterlevnadscenter och välj Varningar.</span><span class="sxs-lookup"><span data-stu-id="28b49-219">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="28b49-220">Se metoderna i [Konfigurera och visa aviseringar för DLP-principer](dlp-configure-view-alerts-policies.md) om du vill se aviseringarna för slutpunkts-DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="28b49-220">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="28b49-221">Visa data för slutpunkts-DLP i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="28b49-221">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="28b49-222">Öppna [sidan Dataklassificering](https://compliance.microsoft.com/dataclassification?viewid=overview) för din domän i Microsoft 365 Efterlevnadscenter och välj Aktivitetsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="28b49-222">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="28b49-223">Se metoderna i [Kom igång med aktivitetsutforskaren](data-classification-activity-explorer.md) för att komma åt och filtrera alla data för slutpunktsenheterna.</span><span class="sxs-lookup"><span data-stu-id="28b49-223">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="28b49-224">![aktivitetsutforskarens filter för slutpunktsenheter](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="28b49-224">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="28b49-225">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="28b49-225">Next steps</span></span>
<span data-ttu-id="28b49-226">Nu när du har registrerat enheter och kan se aktivitetsdata i aktivitetsutforskaren, kan du gå vidare till nästa steg där du skapar DLP-principer som skyddar dina känsliga objekt.</span><span class="sxs-lookup"><span data-stu-id="28b49-226">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="28b49-227">Använda dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="28b49-227">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="28b49-228">Se även</span><span class="sxs-lookup"><span data-stu-id="28b49-228">See also</span></span>

- [<span data-ttu-id="28b49-229">Mer information om dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="28b49-229">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="28b49-230">Använda dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="28b49-230">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="28b49-231">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="28b49-231">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="28b49-232">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="28b49-232">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="28b49-233">Kom igång med aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="28b49-233">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="28b49-234">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="28b49-234">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="28b49-235">Registreringsverktyg och metoder för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="28b49-235">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="28b49-236">Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="28b49-236">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="28b49-237">Azure AD-anslutna enheter</span><span class="sxs-lookup"><span data-stu-id="28b49-237">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="28b49-238">Ladda ned nya Microsoft Edge som baseras på Chromium</span><span class="sxs-lookup"><span data-stu-id="28b49-238">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
