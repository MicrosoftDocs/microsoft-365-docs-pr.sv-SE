---
title: Windows 10-platstjänst
description: Så här har du Windows platstjänster påslagna för dina enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929527"
---
# <a name="windows-10-location-service"></a><span data-ttu-id="3984b-104">Windows 10-platstjänst</span><span class="sxs-lookup"><span data-stu-id="3984b-104">Windows 10 location service</span></span>

<span data-ttu-id="3984b-105">Enheter i Microsoft Managed Desktop registreras med Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3984b-105">Devices in Microsoft Managed Desktop are registered by using Windows Autopilot.</span></span> <span data-ttu-id="3984b-106">Med den här processen kan vi hantera dem med Azure Active Directory och Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="3984b-106">This process lets us manage them with Azure Active Directory and Microsoft Intune.</span></span> <span data-ttu-id="3984b-107">Som standard är platstjänsten i Windows 10 inaktiverad när en enhet aktiveras för första gången om inte den här funktionen är aktiverad i sekretessinställningarna under "standardinställningen".</span><span class="sxs-lookup"><span data-stu-id="3984b-107">By default, the Windows 10 location service is disabled when a device is turned on for the first time unless this feature is enabled in the Privacy settings during the "out of box experience."</span></span> <span data-ttu-id="3984b-108">De här inställningarna är dolda under Autopilot-registrering i Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="3984b-108">These settings are hidden during Autopilot enrollment in Microsoft Managed Desktop.</span></span> <span data-ttu-id="3984b-109">Mer information om hur Autopilot är konfigurerad finns i [First-run-upplevelsen med Autopilot och registreringsstatussidan.](esp-first-run.md)</span><span class="sxs-lookup"><span data-stu-id="3984b-109">For more information about how Autopilot is set up, see [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).</span></span>

<span data-ttu-id="3984b-110">Därför kan inte Microsoft Managed Desktop-enheter få sin enhetsplats, vilket begränsar funktionaliteten i flera Windows-funktioner, till exempel tidszoner.</span><span class="sxs-lookup"><span data-stu-id="3984b-110">For this reason, Microsoft Managed Desktop devices can't obtain their device location, which limits the functionality of several Windows features, such as time zones.</span></span> <span data-ttu-id="3984b-111">Mer information om platstjänsten för Windows 10 finns i Windows [10 platstjänst och sekretess.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="3984b-111">For more information about the Windows 10 location service, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="3984b-112">Du behöver inte använda platstjänsten för att kunna delta i Microsoft Managed Desktop, men användarupplevelsen är begränsad.</span><span class="sxs-lookup"><span data-stu-id="3984b-112">You don't have to use the location service in order to participate in Microsoft Managed Desktop, but the user experience will be restricted.</span></span> <span data-ttu-id="3984b-113">Enheter kan till exempel inte automatiskt ta reda på vilken tidszon de är i när användarna arbetar i en annan tidszon.</span><span class="sxs-lookup"><span data-stu-id="3984b-113">For example, devices won't be able to automatically determine the time zone they're in when your users work in a different time zone.</span></span>

## <a name="enable-the-location-service"></a><span data-ttu-id="3984b-114">Aktivera platstjänsten</span><span class="sxs-lookup"><span data-stu-id="3984b-114">Enable the location service</span></span>

<span data-ttu-id="3984b-115">Du kan välja att använda platstjänsten när du registrerar enheter i tjänsten Microsoft Managed Desktop eller så kan du aktivera eller inaktivera tjänsten efter registreringen.</span><span class="sxs-lookup"><span data-stu-id="3984b-115">You can either opt in to using the location service when you enroll devices into the Microsoft Managed Desktop service or you can turn the service on or off after enrollment.</span></span>

### <a name="opt-in-during-enrollment"></a><span data-ttu-id="3984b-116">Registrera dig under registrering</span><span class="sxs-lookup"><span data-stu-id="3984b-116">Opt in during enrollment</span></span>

<span data-ttu-id="3984b-117">Du kan aktivera platstjänsten för Microsoft Managed Desktop-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="3984b-117">You can have the Microsoft Managed Desktop service enable the location service.</span></span> <span data-ttu-id="3984b-118">Under registreringssekvensen uppmanas du att välja om du vill tillåta att Windows 10-platstjänsten aktiveras på enheter.</span><span class="sxs-lookup"><span data-stu-id="3984b-118">During the enrollment sequence, you'll be asked to select whether you want to allow the Windows 10 location service to be enabled on devices.</span></span>

### <a name="control-the-location-service-after-enrollment"></a><span data-ttu-id="3984b-119">Kontrollera platstjänsten efter registrering</span><span class="sxs-lookup"><span data-stu-id="3984b-119">Control the location service after enrollment</span></span>

<span data-ttu-id="3984b-120">Du kan få platstjänsten aktiverad (eller inaktiverad) när som helst genom att skicka en [supportbegäran](../working-with-managed-desktop/admin-support.md) via [administratörsportalen.](access-admin-portal.md)</span><span class="sxs-lookup"><span data-stu-id="3984b-120">You can have the location service turned on (or off) at any time by submitting a [support request](../working-with-managed-desktop/admin-support.md) through the [Admin portal](access-admin-portal.md).</span></span>

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a><span data-ttu-id="3984b-121">Hur Microsoft Hanterat skrivbord konfigurerar platstjänsten för Windows 10</span><span class="sxs-lookup"><span data-stu-id="3984b-121">How Microsoft Managed Desktop configures the Windows 10 location service</span></span>

<span data-ttu-id="3984b-122">Om du väljer att använda platstjänsten använder vi de minsta nödvändiga inställningarna utan att påverka användarnas sekretess.</span><span class="sxs-lookup"><span data-stu-id="3984b-122">If you opt in to using the location service, we use the minimum settings necessary without affecting users' privacy.</span></span> <span data-ttu-id="3984b-123">Mer information finns i Windows [10 platstjänst och sekretess.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="3984b-123">For more information, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="3984b-124">Microsoft Hanterat skrivbord aktiverar **sekretessinställningen för Plats i** **Windows till** Tillåt åtkomst till position på den **här enheten.**</span><span class="sxs-lookup"><span data-stu-id="3984b-124">Microsoft Managed Desktop enables the **Location privacy** setting in **Windows settings** to **Allow access to location on this device**.</span></span> <span data-ttu-id="3984b-125">Användargränssnittet ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="3984b-125">The user interface looks like this:</span></span>

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Platsinställningar i Windows-inställningar":::

> [!NOTE]
> <span data-ttu-id="3984b-127">Om du väljer att använda platstjänsten gäller detta endast för själva Windows-operativsystemet.</span><span class="sxs-lookup"><span data-stu-id="3984b-127">If you opt in to using the location service, this applies only to the Windows operating system itself.</span></span> <span data-ttu-id="3984b-128">Appar får inte använda platstjänster.</span><span class="sxs-lookup"><span data-stu-id="3984b-128">Apps are not allowed to use location services.</span></span> <span data-ttu-id="3984b-129">Varje användare kan välja om de vill tillåta att appar kommer åt sin plats.</span><span class="sxs-lookup"><span data-stu-id="3984b-129">Each user can choose whether to allow apps to access their location.</span></span>