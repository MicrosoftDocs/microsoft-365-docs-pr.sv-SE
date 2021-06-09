---
title: Förstå enhetsprofiler
description: De olika profiler som administratörer kan tilldela till enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
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
ms.openlocfilehash: 5b5421d2b4001b813d3bcc1e804cae7fb05d0fa7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842008"
---
# <a name="device-profiles"></a><span data-ttu-id="51e25-104">Enhetsprofiler</span><span class="sxs-lookup"><span data-stu-id="51e25-104">Device profiles</span></span>

<span data-ttu-id="51e25-105">Du kan tilldela olika förinställt konfigurationer ("enhetsprofiler") till enheter, som var och en är optimerad för specifika typer av användare.</span><span class="sxs-lookup"><span data-stu-id="51e25-105">You can assign different pre-set configurations ("device profiles") to devices, each optimized for the needs of specific types of users.</span></span> <span data-ttu-id="51e25-106">Det finns tre enhetsprofiler:</span><span class="sxs-lookup"><span data-stu-id="51e25-106">Three device profiles are available:</span></span>

- <span data-ttu-id="51e25-107">Standard</span><span class="sxs-lookup"><span data-stu-id="51e25-107">Standard</span></span>
- <span data-ttu-id="51e25-108">Känsliga data</span><span class="sxs-lookup"><span data-stu-id="51e25-108">Sensitive Data</span></span>
- <span data-ttu-id="51e25-109">Power user</span><span class="sxs-lookup"><span data-stu-id="51e25-109">Power user</span></span>

<span data-ttu-id="51e25-110">Du kan se enhetsprofiler som en del av en hierarki över konfigurationsalternativ för enheter.</span><span class="sxs-lookup"><span data-stu-id="51e25-110">You can think of device profiles as being part of a hierarchy of device configuration options.</span></span>

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Enhetskonfigurationer visas som en pyramid. Beskrivning följer":::

<span data-ttu-id="51e25-112">På ett grundläggande sätt Microsoft Hanterat skrivbord alla enheter en grund som innehåller en standardsäkerhetsbaslinje, efterlevnadsprinciper, Windows uppdatera inställningar och grupper.</span><span class="sxs-lookup"><span data-stu-id="51e25-112">Fundamentally, every Microsoft Managed Desktop device has a foundation that includes a standard security baseline, compliance policies, Windows Update settings, and groups.</span></span> <span data-ttu-id="51e25-113">Om du Microsoft Hanterat skrivbord arbeta med en enhet måste alla enheter innehålla alla dessa element, som inte kan ändras av administratörer utan en begäran att Microsoft Hanterat skrivbord.</span><span class="sxs-lookup"><span data-stu-id="51e25-113">To work with Microsoft Managed Desktop, every device must include all of these elements, which can't be changed by admins without a request to Microsoft Managed Desktop.</span></span>

<span data-ttu-id="51e25-114">Enhetsprofiler visas på nästa högre nivå.</span><span class="sxs-lookup"><span data-stu-id="51e25-114">Device profiles appear at the next higher level.</span></span> <span data-ttu-id="51e25-115">Varje Microsoft Hanterat skrivbord enhet måste ha en (och endast en) tilldelad profil.</span><span class="sxs-lookup"><span data-stu-id="51e25-115">Every Microsoft Managed Desktop device must have one (and only one) profile assigned.</span></span> <span data-ttu-id="51e25-116">Administratörer kan välja vilken profil en enhet ska tilldelas.</span><span class="sxs-lookup"><span data-stu-id="51e25-116">Admins can choose which profile a device is assigned.</span></span>

<span data-ttu-id="51e25-117">Det finns fler anpassningar på en [ännu högre nivå.](customizing.md)</span><span class="sxs-lookup"><span data-stu-id="51e25-117">At a still higher level are additional [customizations](customizing.md).</span></span> <span data-ttu-id="51e25-118">Varje enhet kan ha en eller flera anpassningar (eller ingen).</span><span class="sxs-lookup"><span data-stu-id="51e25-118">Each device can have one or more (or no) customizations.</span></span> <span data-ttu-id="51e25-119">De kan antingen ändra ett lager på lägre nivå (enhetsprofiler eller grundkonfigurationen) eller vara en helt ny begäran som ligger ovanpå standardkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="51e25-119">They can either modify a lower-level layer (Device profiles or the foundational configuration),  or be an entirely new request that’s layered on top of the standard configuration.</span></span>

<span data-ttu-id="51e25-120">Högst upp finns dina egna ändringar, till exempel nätverksinformation eller program.</span><span class="sxs-lookup"><span data-stu-id="51e25-120">At the top are your own modifications, such as network details or applications.</span></span> <span data-ttu-id="51e25-121">En enhet kan ha flera av dessa ändringar, som inte hanteras eller blockeras av Microsoft Hanterat skrivbord.</span><span class="sxs-lookup"><span data-stu-id="51e25-121">A device can have any number of these modifications, which aren't managed or blocked by Microsoft Managed Desktop.</span></span>


## <a name="device-profile-details"></a><span data-ttu-id="51e25-122">Profilinformation för enhet</span><span class="sxs-lookup"><span data-stu-id="51e25-122">Device profile details</span></span>

<span data-ttu-id="51e25-123">I följande tabell sammanfattas inställningarna och deras standardvärden för varje inställning som konfigurerats efter enhetsprofiler.</span><span class="sxs-lookup"><span data-stu-id="51e25-123">The following table summarizes the settings and their default values for each setting configured by device profiles.</span></span> <span data-ttu-id="51e25-124">(Bakom kulisserna konfigureras de här inställningarna med OMA-URIs av anpassade konfigurationsprofiler i Microsoft Endpoint Manager.)</span><span class="sxs-lookup"><span data-stu-id="51e25-124">(Behind the scenes, these settings are configured with OMA-URIs by using Custom Configuration Profiles in Microsoft Endpoint Manager.)</span></span>

<br>

****

|<span data-ttu-id="51e25-125">Funktion</span><span class="sxs-lookup"><span data-stu-id="51e25-125">Feature</span></span>|<span data-ttu-id="51e25-126">Känsliga data</span><span class="sxs-lookup"><span data-stu-id="51e25-126">Sensitive Data</span></span>|<span data-ttu-id="51e25-127">Power User</span><span class="sxs-lookup"><span data-stu-id="51e25-127">Power User</span></span>|<span data-ttu-id="51e25-128">Standard</span><span class="sxs-lookup"><span data-stu-id="51e25-128">Standard</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="51e25-129">**Blockera externa Storage**</span><span class="sxs-lookup"><span data-stu-id="51e25-129">**Block External Storage**</span></span>|<span data-ttu-id="51e25-130">Ja</span><span class="sxs-lookup"><span data-stu-id="51e25-130">Yes</span></span>|<span data-ttu-id="51e25-131">Ja</span><span class="sxs-lookup"><span data-stu-id="51e25-131">Yes</span></span>|<span data-ttu-id="51e25-132">Nej</span><span class="sxs-lookup"><span data-stu-id="51e25-132">No</span></span>|
|<span data-ttu-id="51e25-133">**[Molnblocksnivå](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**</span><span class="sxs-lookup"><span data-stu-id="51e25-133">**[Cloud Block Level](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**</span></span>|<span data-ttu-id="51e25-134">Högsta</span><span class="sxs-lookup"><span data-stu-id="51e25-134">High</span></span>|<span data-ttu-id="51e25-135">Högsta</span><span class="sxs-lookup"><span data-stu-id="51e25-135">High</span></span>|<span data-ttu-id="51e25-136">Högsta</span><span class="sxs-lookup"><span data-stu-id="51e25-136">High</span></span>|
|<span data-ttu-id="51e25-137">**Inaktivera Microsoft-konton**</span><span class="sxs-lookup"><span data-stu-id="51e25-137">**Disable Microsoft Accounts**</span></span>|<span data-ttu-id="51e25-138">Ja</span><span class="sxs-lookup"><span data-stu-id="51e25-138">Yes</span></span>|<span data-ttu-id="51e25-139">Ja</span><span class="sxs-lookup"><span data-stu-id="51e25-139">Yes</span></span>|<span data-ttu-id="51e25-140">Nej</span><span class="sxs-lookup"><span data-stu-id="51e25-140">No</span></span>|
|<span data-ttu-id="51e25-141">**Inaktivera personliga OneDrive**</span><span class="sxs-lookup"><span data-stu-id="51e25-141">**Disable personal OneDrive**</span></span>|<span data-ttu-id="51e25-142">Ja</span><span class="sxs-lookup"><span data-stu-id="51e25-142">Yes</span></span>|<span data-ttu-id="51e25-143">Ja</span><span class="sxs-lookup"><span data-stu-id="51e25-143">Yes</span></span>|<span data-ttu-id="51e25-144">Nej</span><span class="sxs-lookup"><span data-stu-id="51e25-144">No</span></span>|
|<span data-ttu-id="51e25-145">**Växla till ett säkert skrivbord för höjd**</span><span class="sxs-lookup"><span data-stu-id="51e25-145">**Switch to secure desktop for elevation**</span></span>|<span data-ttu-id="51e25-146">Nej</span><span class="sxs-lookup"><span data-stu-id="51e25-146">No</span></span>|<span data-ttu-id="51e25-147">Ja</span><span class="sxs-lookup"><span data-stu-id="51e25-147">Yes</span></span>|<span data-ttu-id="51e25-148">Nej</span><span class="sxs-lookup"><span data-stu-id="51e25-148">No</span></span>|
|<span data-ttu-id="51e25-149">**Microsoft Defender för endpoint-enhetstagg**</span><span class="sxs-lookup"><span data-stu-id="51e25-149">**Microsoft Defender for Endpoint Device Tag**</span></span>|<span data-ttu-id="51e25-150">M365Managed-SensitiveData</span><span class="sxs-lookup"><span data-stu-id="51e25-150">M365Managed-SensitiveData</span></span>|<span data-ttu-id="51e25-151">M365Managed-PowerUser</span><span class="sxs-lookup"><span data-stu-id="51e25-151">M365Managed-PowerUser</span></span>|<span data-ttu-id="51e25-152">M365Managed-Standard</span><span class="sxs-lookup"><span data-stu-id="51e25-152">M365Managed-Standard</span></span>|
|<span data-ttu-id="51e25-153">**Administratör på enheten?**</span><span class="sxs-lookup"><span data-stu-id="51e25-153">**Admin on the device?**</span></span>|<span data-ttu-id="51e25-154">Nej</span><span class="sxs-lookup"><span data-stu-id="51e25-154">No</span></span>|<span data-ttu-id="51e25-155">Ja</span><span class="sxs-lookup"><span data-stu-id="51e25-155">Yes</span></span>|<span data-ttu-id="51e25-156">Nej</span><span class="sxs-lookup"><span data-stu-id="51e25-156">No</span></span>|
|<span data-ttu-id="51e25-157">**Autopilot-profil**</span><span class="sxs-lookup"><span data-stu-id="51e25-157">**Autopilot Profile**</span></span>|<span data-ttu-id="51e25-158">MMD Standard</span><span class="sxs-lookup"><span data-stu-id="51e25-158">MMD Standard</span></span>|<span data-ttu-id="51e25-159">MMD Power User</span><span class="sxs-lookup"><span data-stu-id="51e25-159">MMD Power User</span></span>|<span data-ttu-id="51e25-160">MMD Standard</span><span class="sxs-lookup"><span data-stu-id="51e25-160">MMD Standard</span></span>|
|<span data-ttu-id="51e25-161">**AppLocker**</span><span class="sxs-lookup"><span data-stu-id="51e25-161">**AppLocker**</span></span>|<span data-ttu-id="51e25-162">Ja</span><span class="sxs-lookup"><span data-stu-id="51e25-162">Yes</span></span>|<span data-ttu-id="51e25-163">Nej</span><span class="sxs-lookup"><span data-stu-id="51e25-163">No</span></span>|<span data-ttu-id="51e25-164">Nej</span><span class="sxs-lookup"><span data-stu-id="51e25-164">No</span></span>|
|<span data-ttu-id="51e25-165">**Blockera offentlig lagring**</span><span class="sxs-lookup"><span data-stu-id="51e25-165">**Block Public Store**</span></span>|<span data-ttu-id="51e25-166">Ja</span><span class="sxs-lookup"><span data-stu-id="51e25-166">Yes</span></span>|<span data-ttu-id="51e25-167">Ja</span><span class="sxs-lookup"><span data-stu-id="51e25-167">Yes</span></span>|<span data-ttu-id="51e25-168">Nej</span><span class="sxs-lookup"><span data-stu-id="51e25-168">No</span></span>|
|

<span data-ttu-id="51e25-169">Varje enhetsprofil omfattar även följande objekt:</span><span class="sxs-lookup"><span data-stu-id="51e25-169">Each device profile also involves these items:</span></span>

- <span data-ttu-id="51e25-170">En AAD-Azure Active Directory (dynamiskt medlemskap)</span><span class="sxs-lookup"><span data-stu-id="51e25-170">A dynamic membership Azure Active Directory (AAD) device group</span></span>
- <span data-ttu-id="51e25-171">En statisk medlemskapsgrupp för AAD-enhet</span><span class="sxs-lookup"><span data-stu-id="51e25-171">A static membership AAD device group</span></span>
- <span data-ttu-id="51e25-172">En Microsoft Endpoint Manager konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="51e25-172">A Microsoft Endpoint Manager Configuration profile</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51e25-173">Ändra inte medlemskapet i de här grupperna direkt.</span><span class="sxs-lookup"><span data-stu-id="51e25-173">Don’t modify the membership of these groups directly.</span></span> <span data-ttu-id="51e25-174">Använd gränssnittet enligt beskrivningen i [Omtilldela profiler](../working-with-managed-desktop/change-device-profile.md).</span><span class="sxs-lookup"><span data-stu-id="51e25-174">Use the interface as described in [Reassign profiles](../working-with-managed-desktop/change-device-profile.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="51e25-175">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="51e25-175">Limitations</span></span>

<span data-ttu-id="51e25-176">Du kan begära undantag från enhetsprofiler och deras information på samma sätt som du skulle göra med andra policyer.</span><span class="sxs-lookup"><span data-stu-id="51e25-176">You can request exceptions to the device profiles and their details as you would with any other policy.</span></span> <span data-ttu-id="51e25-177">Kom ihåg att du bara kan ha en av varje enhetsprofil i din Azure Active Directory organisation ("klientorganisation").</span><span class="sxs-lookup"><span data-stu-id="51e25-177">Keep in mind that you can only have one of each device profile in your Azure Active Directory organization ("tenant").</span></span> <span data-ttu-id="51e25-178">Du kan till exempel inte begära att profilen för känsliga dataenhet inaktiverar AppLocker för endast en del användare.</span><span class="sxs-lookup"><span data-stu-id="51e25-178">For example, you can't request that the Sensitive data device profile disables AppLocker for only some of your users.</span></span> <span data-ttu-id="51e25-179">Alla enheter med profilen Känslig information måste ha samma konfiguration.</span><span class="sxs-lookup"><span data-stu-id="51e25-179">All devices with the Sensitive data profile must have the same configuration.</span></span>

<span data-ttu-id="51e25-180">Varje enhet kan bara ha en profil.</span><span class="sxs-lookup"><span data-stu-id="51e25-180">Each device can only have one profile.</span></span> <span data-ttu-id="51e25-181">Om en viss enhet används av fler än en användare får alla användare på enheten samma konfiguration.</span><span class="sxs-lookup"><span data-stu-id="51e25-181">If a given device is used by more than one user, all users on that device will have the same configuration.</span></span>
