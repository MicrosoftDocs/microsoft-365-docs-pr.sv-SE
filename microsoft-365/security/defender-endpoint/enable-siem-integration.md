---
title: Aktivera SIEM-integrering i Microsoft Defender för Slutpunkt
description: Aktivera SIEM-integrering för att ta emot identifieringar i din säkerhetsinformations- och händelsehanteringslösning (SIEM).
keywords: aktivera siem-koppling, siem, anslutare, säkerhetsinformation och händelser
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 87078bb7bfc6b38788fea2a6a4c3c9108be1d5b4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842968"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="f4ce0-104">Aktivera SIEM-integrering i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f4ce0-104">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f4ce0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f4ce0-105">**Applies to:**</span></span>
- [<span data-ttu-id="f4ce0-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f4ce0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


><span data-ttu-id="f4ce0-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f4ce0-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f4ce0-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

<span data-ttu-id="f4ce0-109">Aktivera integrering av säkerhetsinformation och händelsehantering (SIEM) så att du kan hämta identifieringar Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-109">Enable security information and event management (SIEM) integration so you can pull detections from Microsoft Defender Security Center.</span></span> <span data-ttu-id="f4ce0-110">Dra identifieringar med hjälp av din SIEM-lösning eller genom att ansluta direkt till identifieringarna REST API.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-110">Pull detections using your SIEM solution or by connecting directly to the detections REST API.</span></span>

>[!NOTE]
>- <span data-ttu-id="f4ce0-111">[Microsoft Defender för slutpunktsavisering](alerts.md) består av en eller flera identifieringar.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="f4ce0-112">[Microsoft Defender för identifiering av slutpunkt](api-portal-mapping.md) består av den misstänkta händelsen som inträffade på enheten och tillhörande aviseringsinformation.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
>- <span data-ttu-id="f4ce0-113">Microsoft Defender för slutpunktsaviserings-API är det senaste API:t för aviseringsanvändning och innehåller en detaljerad lista med relaterade bevis för varje avisering.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-113">The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="f4ce0-114">Mer information finns i [Aviseringsmetoder och egenskaper](alerts.md) och [Listaviseringar.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="f4ce0-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f4ce0-115">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="f4ce0-115">Prerequisites</span></span>

- <span data-ttu-id="f4ce0-116">Den användare som aktiverar inställningen måste ha behörighet att skapa en app i Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="f4ce0-116">The user who activates the setting must have permissions to create an app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="f4ce0-117">Det här är någon med följande roller:</span><span class="sxs-lookup"><span data-stu-id="f4ce0-117">This is someone with the following roles:</span></span> 

  - <span data-ttu-id="f4ce0-118">Säkerhetsadministratör och antingen global administratör</span><span class="sxs-lookup"><span data-stu-id="f4ce0-118">Security Administrator and either Global Administrator</span></span>
  - <span data-ttu-id="f4ce0-119">Administratör för molnprogram</span><span class="sxs-lookup"><span data-stu-id="f4ce0-119">Cloud Application Administrator</span></span>
  - <span data-ttu-id="f4ce0-120">Programadministratör</span><span class="sxs-lookup"><span data-stu-id="f4ce0-120">Application Administrator</span></span>
  - <span data-ttu-id="f4ce0-121">Ägaren till tjänstens huvudnamn</span><span class="sxs-lookup"><span data-stu-id="f4ce0-121">Owner of the service principal</span></span>

- <span data-ttu-id="f4ce0-122">Under den första aktiveringen visas en popup-skärm där du kan lägga till autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-122">During the initial activation, a pop-up screen is displayed for credentials to be entered.</span></span> <span data-ttu-id="f4ce0-123">Se till att du tillåter popup-fönster för den här webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-123">Make sure that you allow pop-ups for this site.</span></span>

## <a name="enabling-siem-integration"></a><span data-ttu-id="f4ce0-124">Aktivera SIEM-integrering</span><span class="sxs-lookup"><span data-stu-id="f4ce0-124">Enabling SIEM integration</span></span> 
1. <span data-ttu-id="f4ce0-125">I navigeringsfönstret väljer du **Inställningar**  >  **SIEM.**</span><span class="sxs-lookup"><span data-stu-id="f4ce0-125">In the navigation pane, select **Settings** > **SIEM**.</span></span>

    ![Bild av SIEM-integrering Inställningar meny1](images/enable_siem.png)

    >[!TIP]
    ><span data-ttu-id="f4ce0-127">Om det uppstår ett fel när du försöker aktivera SIEM-kopplingsprogrammet kontrollerar du inställningarna för blockering av popup-fönster i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-127">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="f4ce0-128">Det kan blockera det nya fönstret som öppnas när du aktiverar funktionen.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-128">It might be blocking the new window being opened when you enable the capability.</span></span> 

2. <span data-ttu-id="f4ce0-129">Välj **Aktivera SIEM-integrering.**</span><span class="sxs-lookup"><span data-stu-id="f4ce0-129">Select **Enable SIEM integration**.</span></span> <span data-ttu-id="f4ce0-130">Detta aktiverar **informationsavsnittet** för SIEM-koppling med ifyllda värden och ett program skapas under Azure Active Directory (Azure AD) klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-130">This activates the **SIEM connector access details** section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span>

    > [!WARNING]
    ><span data-ttu-id="f4ce0-131">Klienthemligheten visas bara en gång.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-131">The client secret is only displayed once.</span></span> <span data-ttu-id="f4ce0-132">Se till att spara en kopia av den på ett säkert ställe.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-132">Make sure you keep a copy of it in a safe place.</span></span><br>
     

    ![Bild av SIEM-integrering Inställningar meny2](images/siem_details.png)

3. <span data-ttu-id="f4ce0-134">Välj den SIEM-typ som du använder i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-134">Choose the SIEM type you use in your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f4ce0-135">Om du väljer HP ArcSight måste du spara de här två konfigurationsfilerna:</span><span class="sxs-lookup"><span data-stu-id="f4ce0-135">If you select HP ArcSight, you'll need to save these two configuration files:</span></span><br>
   > - <span data-ttu-id="f4ce0-136">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="f4ce0-136">WDATP-connector.jsonparser.properties</span></span>
   > - <span data-ttu-id="f4ce0-137">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="f4ce0-137">WDATP-connector.properties</span></span> <br>

   <span data-ttu-id="f4ce0-138">Om du vill ansluta direkt till identifieringarna REST API via programmatisk åtkomst väljer du **Allmänt API.**</span><span class="sxs-lookup"><span data-stu-id="f4ce0-138">If you want to connect directly to the detections REST API through programmatic access, choose **Generic API**.</span></span>

4. <span data-ttu-id="f4ce0-139">Kopiera de enskilda värdena eller välj **Spara information till fil om** du vill ladda ned en fil som innehåller alla värden.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-139">Copy the individual values or select **Save details to file** to download a file that contains all the values.</span></span>

5. <span data-ttu-id="f4ce0-140">Välj **Generera token för att** få en åtkomst- och uppdateringstoken.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-140">Select **Generate tokens** to get an access and refresh token.</span></span>
  
   > [!NOTE]
   > <span data-ttu-id="f4ce0-141">Du måste skapa en ny Uppdateringstoken var 90:e dag.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-141">You'll need to generate a new Refresh token every 90 days.</span></span> 

6. <span data-ttu-id="f4ce0-142">Följ instruktionerna för [att skapa en azure AD-appregistrering för Microsoft Defender](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) för Endpoint och tilldela rätt behörigheter till den för att läsa aviseringar.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-142">Follow the instructions for [creating an Azure AD app registration for Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) and assign the correct permissions to it to read alerts.</span></span>

<span data-ttu-id="f4ce0-143">Du kan nu fortsätta med att konfigurera din SIEM-lösning eller ansluta till identifieringen av REST API via programmeringsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-143">You can now proceed with configuring your SIEM solution or connecting to the detections REST API through programmatic access.</span></span> <span data-ttu-id="f4ce0-144">Du måste använda tokens när du konfigurerar din SIEM-lösning så att den kan ta emot identifieringar från Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-144">You'll need to use the tokens when configuring your SIEM solution to allow it to receive detections from Microsoft Defender Security Center.</span></span>

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a><span data-ttu-id="f4ce0-145">Integrera Microsoft Defender för slutpunkt med IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="f4ce0-145">Integrate Microsoft Defender for Endpoint with IBM QRadar</span></span> 
<span data-ttu-id="f4ce0-146">Du kan konfigurera IBM QRadar att samla in identifieringar från Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f4ce0-146">You can configure IBM QRadar to collect detections from Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f4ce0-147">Mer information finns i [IBM Knowledge Center.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)</span><span class="sxs-lookup"><span data-stu-id="f4ce0-147">For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

## <a name="see-also"></a><span data-ttu-id="f4ce0-148">Se även</span><span class="sxs-lookup"><span data-stu-id="f4ce0-148">See also</span></span>
- [<span data-ttu-id="f4ce0-149">Konfigurera HP ArcSight att hämta Microsoft Defender för identifiering av slutpunkter</span><span class="sxs-lookup"><span data-stu-id="f4ce0-149">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="f4ce0-150">Fälten Microsoft Defender för identifiering av slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f4ce0-150">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="f4ce0-151">Hämta Microsoft Defender för slutpunktsidentifiering med REST API</span><span class="sxs-lookup"><span data-stu-id="f4ce0-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="f4ce0-152">Felsöka problem med SIEM-verktygsintegrering</span><span class="sxs-lookup"><span data-stu-id="f4ce0-152">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
