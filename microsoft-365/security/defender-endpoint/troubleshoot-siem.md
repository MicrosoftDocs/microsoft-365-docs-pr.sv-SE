---
title: Felsöka problem med SIEM-verktygsintegrering i Microsoft Defender ATP
description: Felsöka problem som kan uppstå när du använder SIEM-verktyg med Microsoft Defender ATP.
keywords: felsökning, siem, klienthemlighet, hemlig
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 7a6bb0c455ed0406c941e9269b8b04b5cfe738be
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072874"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a><span data-ttu-id="6fe24-104">Felsöka problem med SIEM-verktygsintegrering</span><span class="sxs-lookup"><span data-stu-id="6fe24-104">Troubleshoot SIEM tool integration issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6fe24-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6fe24-105">**Applies to:**</span></span>
- [<span data-ttu-id="6fe24-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6fe24-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="6fe24-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6fe24-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="6fe24-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6fe24-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6fe24-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6fe24-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="6fe24-110">Du kan behöva felsöka problem när du drar identifieringar i dina SIEM-verktyg.</span><span class="sxs-lookup"><span data-stu-id="6fe24-110">You might need to troubleshoot issues while pulling detections in your SIEM tools.</span></span>

<span data-ttu-id="6fe24-111">På den här sidan finns detaljerade anvisningar för felsökning av problem som kan uppstå.</span><span class="sxs-lookup"><span data-stu-id="6fe24-111">This page provides detailed steps to troubleshoot issues you might encounter.</span></span>


## <a name="learn-how-to-get-a-new-client-secret"></a><span data-ttu-id="6fe24-112">Lär dig hur du får en ny klienthemlighet</span><span class="sxs-lookup"><span data-stu-id="6fe24-112">Learn how to get a new client secret</span></span>
<span data-ttu-id="6fe24-113">Om klienthemligheten går ut eller om du har tappat bort kopian som angavs när du aktiverar sieM-verktygsprogrammet måste du få en ny hemlig kopia.</span><span class="sxs-lookup"><span data-stu-id="6fe24-113">If your client secret expires or if you've misplaced the copy provided when you were enabling the SIEM tool application,  you'll need to get a new secret.</span></span>

1. <span data-ttu-id="6fe24-114">Logga in på [Azure-hanteringsportalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="6fe24-114">Login to the [Azure management portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="6fe24-115">Välj **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="6fe24-115">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="6fe24-116">Välj klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="6fe24-116">Select your tenant.</span></span>

4. <span data-ttu-id="6fe24-117">Klicka **på Appregistreringar.**</span><span class="sxs-lookup"><span data-stu-id="6fe24-117">Click **App registrations**.</span></span> <span data-ttu-id="6fe24-118">Välj sedan programmet i programlistan.</span><span class="sxs-lookup"><span data-stu-id="6fe24-118">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="6fe24-119">Välj  nyckelavsnittet, ange sedan en nyckelbeskrivning och ange hur lång nyckellängden ska vara.</span><span class="sxs-lookup"><span data-stu-id="6fe24-119">Select **Keys** section, then provide a key description and specify the key validity duration.</span></span>

6. <span data-ttu-id="6fe24-120">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6fe24-120">Click **Save**.</span></span> <span data-ttu-id="6fe24-121">Nyckelvärdet visas.</span><span class="sxs-lookup"><span data-stu-id="6fe24-121">The key value is displayed.</span></span>

7. <span data-ttu-id="6fe24-122">Kopiera värdet och spara det på ett säkert ställe.</span><span class="sxs-lookup"><span data-stu-id="6fe24-122">Copy the value and save it in a safe place.</span></span>


## <a name="error-when-getting-a-refresh-access-token"></a><span data-ttu-id="6fe24-123">Felmeddelande när en token för uppdateringsåtkomst visas</span><span class="sxs-lookup"><span data-stu-id="6fe24-123">Error when getting a refresh access token</span></span>
<span data-ttu-id="6fe24-124">Om du får ett felmeddelande när du försöker få en uppdateringstoken när du använder verktygen threat intelligence API eller SIEM måste du lägga till svars-URL för relevant program i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6fe24-124">If you encounter an error when trying to get a refresh token when using the threat intelligence API or SIEM tools, you'll need to add reply URL for relevant application in Azure Active Directory.</span></span>

1. <span data-ttu-id="6fe24-125">Logga in på [Azure-hanteringsportalen](https://ms.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="6fe24-125">Login to the [Azure management portal](https://ms.portal.azure.com).</span></span>

2. <span data-ttu-id="6fe24-126">Välj **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="6fe24-126">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="6fe24-127">Välj klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="6fe24-127">Select your tenant.</span></span>

4. <span data-ttu-id="6fe24-128">Klicka **på Appregistreringar.**</span><span class="sxs-lookup"><span data-stu-id="6fe24-128">Click **App Registrations**.</span></span> <span data-ttu-id="6fe24-129">Välj sedan programmet i programlistan.</span><span class="sxs-lookup"><span data-stu-id="6fe24-129">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="6fe24-130">Lägg till följande URL:</span><span class="sxs-lookup"><span data-stu-id="6fe24-130">Add the following URL:</span></span>
   - <span data-ttu-id="6fe24-131">För EU: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="6fe24-131">For the European Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="6fe24-132">För Storbritannien: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="6fe24-132">For the United Kingdom: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="6fe24-133">För USA:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .</span><span class="sxs-lookup"><span data-stu-id="6fe24-133">For the United States:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.</span></span>
 
6. <span data-ttu-id="6fe24-134">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6fe24-134">Click **Save**.</span></span>

## <a name="error-while-enabling-the-siem-connector-application"></a><span data-ttu-id="6fe24-135">Fel när DU aktiverar SIEM-kopplingsprogrammet</span><span class="sxs-lookup"><span data-stu-id="6fe24-135">Error while enabling the SIEM connector application</span></span>
<span data-ttu-id="6fe24-136">Om det uppstår ett fel när du försöker aktivera SIEM-kopplingsprogrammet kontrollerar du inställningarna för blockering av popup-fönster i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="6fe24-136">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="6fe24-137">Det kan blockera det nya fönstret som öppnas när du aktiverar funktionen.</span><span class="sxs-lookup"><span data-stu-id="6fe24-137">It might be blocking the new window being opened when you enable the capability.</span></span>




><span data-ttu-id="6fe24-138">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6fe24-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6fe24-139">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6fe24-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a><span data-ttu-id="6fe24-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6fe24-140">Related topics</span></span>
- [<span data-ttu-id="6fe24-141">Aktivera SIEM-integrering i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="6fe24-141">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="6fe24-142">Konfigurera ArcSight för att hämta Microsoft Defender för identifiering av slutpunkter</span><span class="sxs-lookup"><span data-stu-id="6fe24-142">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="6fe24-143">Dra identifieringar till dina SIEM-verktyg</span><span class="sxs-lookup"><span data-stu-id="6fe24-143">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="6fe24-144">Fälten Microsoft Defender för identifiering av slutpunkt</span><span class="sxs-lookup"><span data-stu-id="6fe24-144">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="6fe24-145">Hämta Microsoft Defender för slutpunktsidentifiering med REST API</span><span class="sxs-lookup"><span data-stu-id="6fe24-145">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)