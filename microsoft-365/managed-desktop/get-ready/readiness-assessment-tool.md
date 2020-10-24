---
title: Verktyg för bedömning av beredskap
description: Förklarar vilka kontroller verktyget kör och innebörden av resultatet
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c574be6d171a230479d8b6c96e2e0a1dec8a87ac
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656158"
---
# <a name="readiness-assessment-tool"></a><span data-ttu-id="152c6-104">Verktyg för bedömning av beredskap</span><span class="sxs-lookup"><span data-stu-id="152c6-104">Readiness assessment tool</span></span>

<span data-ttu-id="152c6-105">För att du ska få den bästa möjliga upplevelsen när du registrerar dig på Microsoft Managed Desktop finns det ett antal inställningar och andra parametrar som du måste ange i förväg.</span><span class="sxs-lookup"><span data-stu-id="152c6-105">For the smoothest possible experience when you enroll in Microsoft Managed Desktop, there are a number of settings and other parameters you must set ahead of time.</span></span> <span data-ttu-id="152c6-106">Du kan använda det här verktyget för att kontrol lera dessa inställningar och få detaljerade anvisningar för att åtgärda något som inte är rätt.</span><span class="sxs-lookup"><span data-stu-id="152c6-106">You can use this tool to check those settings and receive detailed steps for fixing any that aren't right.</span></span>

<span data-ttu-id="152c6-107">Verktyget kontrollerar inställningar i Microsoft slut punkts hanteraren (specifikt, Microsoft Intune), Azure Active Directory (Azure AD) och Microsoft 365 för att säkerställa att de fungerar med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="152c6-107">The tool checks settings in Microsoft Endpoint Manager (specifically, Microsoft Intune), Azure Active Directory (Azure AD), and Microsoft 365 to ensure they will work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="152c6-108">Microsoft Managed Desktop behåller de data som är kopplade till dessa kontroller i 12 månader efter den senaste gången du kör en check i din Azure AD-organisation (klient organisationen).</span><span class="sxs-lookup"><span data-stu-id="152c6-108">Microsoft Managed Desktop retains the data associated with these checks for 12 months after the last time you run a check in your Azure AD organization (tenant).</span></span>  <span data-ttu-id="152c6-109">Efter 12 månader behåller vi det i det format som identifieras.</span><span class="sxs-lookup"><span data-stu-id="152c6-109">After 12 months, we retain it in de-identified form.</span></span>  <span data-ttu-id="152c6-110">Du kan välja att ta bort de data som samlas in.</span><span class="sxs-lookup"><span data-stu-id="152c6-110">You can choose to delete the data we collect.</span></span>
 
<span data-ttu-id="152c6-111">Utvärderings verktyget kontrollerar följande objekt:</span><span class="sxs-lookup"><span data-stu-id="152c6-111">The assessment tool checks these items:</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="152c6-112">Microsoft Intune-inställningar</span><span class="sxs-lookup"><span data-stu-id="152c6-112">Microsoft Intune settings</span></span>

|<span data-ttu-id="152c6-113">Check</span><span class="sxs-lookup"><span data-stu-id="152c6-113">Check</span></span>  |<span data-ttu-id="152c6-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="152c6-114">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="152c6-115">Distributions profil för autopilot</span><span class="sxs-lookup"><span data-stu-id="152c6-115">Autopilot deployment profile</span></span>     | <span data-ttu-id="152c6-116">Verifiera att tilldelningen av profilen för autopilot-distribution inte gäller för alla enheter (profilen ska *inte* kopplas till någon hanterad Microsoft-enhet.)</span><span class="sxs-lookup"><span data-stu-id="152c6-116">Verifies that assignment of the Autopilot deployment profile does not apply to all devices (The profile should *not* be assigned to any Microsoft Managed Desktop devices.)</span></span>       |
|<span data-ttu-id="152c6-117">Certifikat anslutningar</span><span class="sxs-lookup"><span data-stu-id="152c6-117">Certificate connectors</span></span>     | <span data-ttu-id="152c6-118">Kontrollerar statusen för certifikat anslutningar för att säkerställa att de är aktiva</span><span class="sxs-lookup"><span data-stu-id="152c6-118">Checks the state of certificate connectors to ensure they are active</span></span>   |
|<span data-ttu-id="152c6-119">Med villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="152c6-119">Conditional Access</span></span>     | <span data-ttu-id="152c6-120">Verifiera att principer för villkorlig åtkomst inte är tilldelade till alla användare (principer för villkorlig åtkomst ska *inte* tilldelas till Microsoft Managed Desktop Service-konton.)</span><span class="sxs-lookup"><span data-stu-id="152c6-120">Verifies that conditional access policies are not assigned to all users (Conditional access policies should *not* be assigned to Microsoft Managed Desktop service accounts.)</span></span>    |
|<span data-ttu-id="152c6-121">Principer för enhetskompatibilitet</span><span class="sxs-lookup"><span data-stu-id="152c6-121">Device Compliance policies</span></span>     | <span data-ttu-id="152c6-122">Kontrollerar att Intune-efterlevnadsprinciper inte är tilldelade till alla användare (policyn ska *inte* tilldelas till Microsoft Managed Station ära datorer).</span><span class="sxs-lookup"><span data-stu-id="152c6-122">Checks that Intune compliance policies are not assigned to all users (The policies should *not* be assigned to any Microsoft Managed Desktop devices.)</span></span>    |
|<span data-ttu-id="152c6-123">Profil profiler för enheter</span><span class="sxs-lookup"><span data-stu-id="152c6-123">Device Configuration profiles</span></span>     | <span data-ttu-id="152c6-124">Bekräftar att konfigurations profilerna inte är tilldelade till alla användare eller alla enheter (konfigurations profiler ska *inte* tilldelas till Microsoft Managed Station ära datorer.)</span><span class="sxs-lookup"><span data-stu-id="152c6-124">Confirms that configuration profiles are not assigned to all users or all devices (Configuration profiles should *not* be assigned to any Microsoft Managed Desktop devices.)</span></span>     |
|<span data-ttu-id="152c6-125">Begränsningar för enhets typer</span><span class="sxs-lookup"><span data-stu-id="152c6-125">Device type restrictions</span></span>     | <span data-ttu-id="152c6-126">Kontrollerar att Windows 10-enheter i din organisation tillåts registrera i Intune</span><span class="sxs-lookup"><span data-stu-id="152c6-126">Checks that Windows 10 devices in your organization are allowed to enroll in Intune</span></span>        |
|<span data-ttu-id="152c6-127">Sidan registrerings status</span><span class="sxs-lookup"><span data-stu-id="152c6-127">Enrollment Status Page</span></span>     | <span data-ttu-id="152c6-128">Bekräftar att registrerings status sidan inte är aktive rad</span><span class="sxs-lookup"><span data-stu-id="152c6-128">Confirms that Enrollment Status Page is not enabled</span></span>      |
|<span data-ttu-id="152c6-129">Intune-registrering</span><span class="sxs-lookup"><span data-stu-id="152c6-129">Intune enrollment</span></span>     | <span data-ttu-id="152c6-130">Verifierar att Windows 10-enheter i din Azure AD-organisation registreras automatiskt i Intune</span><span class="sxs-lookup"><span data-stu-id="152c6-130">Verifies that Windows 10 devices in your Azure AD organization are automatically enrolled in Intune</span></span>         |
|<span data-ttu-id="152c6-131">Microsoft Store för företag</span><span class="sxs-lookup"><span data-stu-id="152c6-131">Microsoft Store for Business</span></span>     | <span data-ttu-id="152c6-132">Bekräftar att Microsoft Store för företag är aktiverat och synkroniserat med Intune</span><span class="sxs-lookup"><span data-stu-id="152c6-132">Confirms that Microsoft Store for Business is enabled and synced with Intune</span></span>        |
|<span data-ttu-id="152c6-133">Multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="152c6-133">Multi-factor authentication</span></span> | <span data-ttu-id="152c6-134">Verifierar att multifaktorautentisering inte tillämpas på Microsoft Managed Desktop Service-konton.</span><span class="sxs-lookup"><span data-stu-id="152c6-134">Verifies that multi-factor authentication isn't applied to Microsoft Managed Desktop service accounts.</span></span>
|<span data-ttu-id="152c6-135">PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="152c6-135">PowerShell scripts</span></span>     | <span data-ttu-id="152c6-136">Kontrollerar att Windows PowerShell-skript *inte* är tilldelade på ett sätt som kan hantera Microsoft Managed Station ära enheter</span><span class="sxs-lookup"><span data-stu-id="152c6-136">Checks that Windows PowerShell scripts are *not* assigned in a way that would target Microsoft Managed Desktop devices</span></span>    |
|<span data-ttu-id="152c6-137">Region</span><span class="sxs-lookup"><span data-stu-id="152c6-137">Region</span></span>     | <span data-ttu-id="152c6-138">Kontrollerar att din region stöds av Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="152c6-138">Checks that your region is supported by Microsoft Managed Desktop</span></span>        |
|<span data-ttu-id="152c6-139">Säkerhets bas linjer</span><span class="sxs-lookup"><span data-stu-id="152c6-139">Security baselines</span></span>     | <span data-ttu-id="152c6-140">Kontrollerar att säkerhets bas profilen inte uppfyller alla användare eller alla enheter (principer för säkerhets bas linje ska *inte* vara riktad till Microsoft Managed Station ära datorer).</span><span class="sxs-lookup"><span data-stu-id="152c6-140">Checks that the security baseline profile doesn't target all users or all devices (Security baseline policies should *not* target any Microsoft Managed Desktop devices.)</span></span>       |
|<span data-ttu-id="152c6-141">Windows-appar</span><span class="sxs-lookup"><span data-stu-id="152c6-141">Windows apps</span></span>     | <span data-ttu-id="152c6-142">Granska vilka appar du vill tilldela Microsoft-hanterade Station ära enheter</span><span class="sxs-lookup"><span data-stu-id="152c6-142">Review which apps you want to assign to Microsoft Managed Desktop devices</span></span>      |
|<span data-ttu-id="152c6-143">Windows Hello för företag</span><span class="sxs-lookup"><span data-stu-id="152c6-143">Windows Hello for Business</span></span>     | <span data-ttu-id="152c6-144">Kontrollerar att Windows Hello för företag är aktiverat</span><span class="sxs-lookup"><span data-stu-id="152c6-144">Checks that Windows Hello for Business is enabled</span></span>        |
|<span data-ttu-id="152c6-145">Windows 10-uppdatera ring</span><span class="sxs-lookup"><span data-stu-id="152c6-145">Windows 10 update ring</span></span>     | <span data-ttu-id="152c6-146">Kontrollerar att Intune-principen "Windows 10 Update ring" inte riktar sig till alla användare eller alla enheter (principen ska *inte* vara riktad till Microsoft Managed Station ära enheter).</span><span class="sxs-lookup"><span data-stu-id="152c6-146">Checks that Intune's "Windows 10 update ring" policy doesn't target all users or all devices (The policy should *not* target any Microsoft Managed Desktop devices.)</span></span>     |


## <a name="azure-active-directory-settings"></a><span data-ttu-id="152c6-147">Azure Active Directory-inställningar</span><span class="sxs-lookup"><span data-stu-id="152c6-147">Azure Active Directory settings</span></span>

|<span data-ttu-id="152c6-148">Check</span><span class="sxs-lookup"><span data-stu-id="152c6-148">Check</span></span>  |<span data-ttu-id="152c6-149">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="152c6-149">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="152c6-150">"Ad hoc"-abonnemang för företags status-roaming</span><span class="sxs-lookup"><span data-stu-id="152c6-150">"Ad hoc" subscriptions for Enterprise State Roaming</span></span>     | <span data-ttu-id="152c6-151">Här förklaras hur du kontrollerar en inställning som (om värdet är "falskt") kan hindra företags tillstånd från att fungera korrekt</span><span class="sxs-lookup"><span data-stu-id="152c6-151">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly</span></span>  |
|<span data-ttu-id="152c6-152">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="152c6-152">Enterprise State Roaming</span></span>     | <span data-ttu-id="152c6-153">Här får du information om hur du kontrollerar att nätverks tillstånd är aktiverat</span><span class="sxs-lookup"><span data-stu-id="152c6-153">Advises how to check that Enterprise State Roaming is enabled</span></span>       |
|<span data-ttu-id="152c6-154">Licenser</span><span class="sxs-lookup"><span data-stu-id="152c6-154">Licenses</span></span>     | <span data-ttu-id="152c6-155">Kontrollerar att du har skaffat de [licenser](prerequisites.md#more-about-licenses) du behöver</span><span class="sxs-lookup"><span data-stu-id="152c6-155">Checks that you have obtained the necessary [licenses](prerequisites.md#more-about-licenses)</span></span>         |
|<span data-ttu-id="152c6-156">Multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="152c6-156">Multi-factor authentication</span></span>     | <span data-ttu-id="152c6-157">Kontrollerar att multifaktorautentisering inte används för alla användare (multifaktorautentisering får inte oavsiktligt användas på Microsoft Managed Desktop Service-konton.)</span><span class="sxs-lookup"><span data-stu-id="152c6-157">Checks that multi-factor authentication is not applied to all users (Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.)</span></span>|
|<span data-ttu-id="152c6-158">Namn på säkerhets konton</span><span class="sxs-lookup"><span data-stu-id="152c6-158">Security account names</span></span>   | <span data-ttu-id="152c6-159">Kontrollerar att inga användar namn är i konflikt med att Microsoft Managed Desktop reserver för eget bruk</span><span class="sxs-lookup"><span data-stu-id="152c6-159">Checks that no user names conflict with ones that Microsoft Managed Desktop reserves for its own use</span></span>        |
|<span data-ttu-id="152c6-160">Säkerhets administratörs roller</span><span class="sxs-lookup"><span data-stu-id="152c6-160">Security administrator roles</span></span>     | <span data-ttu-id="152c6-161">Bekräftar att användare med rollen säkerhets läsare, säkerhets ansvarig eller global läsare har tilldelats roller i Microsoft Defender för slut punkten</span><span class="sxs-lookup"><span data-stu-id="152c6-161">Confirms that users with Security Reader, Security Operator, or Global Reader roles have been assigned those roles in Microsoft Defender for Endpoint</span></span>         |
|<span data-ttu-id="152c6-162">Standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="152c6-162">Security defaults</span></span> | <span data-ttu-id="152c6-163">Kontrollerar om din Azure AD-organisation har säkerhets standarder aktiverade i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="152c6-163">Checks whether your Azure AD organization has security defaults enabled in Azure Active Directory</span></span> |
|<span data-ttu-id="152c6-164">Självbetjäning för återställning av lösenord</span><span class="sxs-lookup"><span data-stu-id="152c6-164">Self-service password reset</span></span>     | <span data-ttu-id="152c6-165">Bekräftar att automatisk återställning av lösen ord är aktiverat</span><span class="sxs-lookup"><span data-stu-id="152c6-165">Confirms that self-service password reset is enabled</span></span>        |
|<span data-ttu-id="152c6-166">Standard användar roll</span><span class="sxs-lookup"><span data-stu-id="152c6-166">Standard user role</span></span>     | <span data-ttu-id="152c6-167">Verifierar att användare är standard användare och inte har lokal administratörs behörighet</span><span class="sxs-lookup"><span data-stu-id="152c6-167">Verifies that users are standard users and do not have local administrator rights</span></span>         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a><span data-ttu-id="152c6-168">Microsoft 365-appar för företags inställningar</span><span class="sxs-lookup"><span data-stu-id="152c6-168">Microsoft 365 Apps for enterprise settings</span></span>

|<span data-ttu-id="152c6-169">Check</span><span class="sxs-lookup"><span data-stu-id="152c6-169">Check</span></span>  |<span data-ttu-id="152c6-170">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="152c6-170">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="152c6-171">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="152c6-171">OneDrive for Business</span></span>     | <span data-ttu-id="152c6-172">Kontrollerar om OneDrive för företag använder inställningar som inte stöds.</span><span class="sxs-lookup"><span data-stu-id="152c6-172">Checks whether OneDrive for Business is using unsupported settings.</span></span>        |


<span data-ttu-id="152c6-173">För varje kontroll rapporteras ett av tre möjliga resultat:</span><span class="sxs-lookup"><span data-stu-id="152c6-173">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="152c6-174">Resultat</span><span class="sxs-lookup"><span data-stu-id="152c6-174">Result</span></span>  |<span data-ttu-id="152c6-175">Betydelse</span><span class="sxs-lookup"><span data-stu-id="152c6-175">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="152c6-176">Förbereder</span><span class="sxs-lookup"><span data-stu-id="152c6-176">Ready</span></span>     | <span data-ttu-id="152c6-177">Ingen åtgärd krävs innan du slutför registreringen.</span><span class="sxs-lookup"><span data-stu-id="152c6-177">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="152c6-178">Rådgivare</span><span class="sxs-lookup"><span data-stu-id="152c6-178">Advisory</span></span>    | <span data-ttu-id="152c6-179">Följ stegen i verktyget för att få den bästa upplevelsen med registrering och för användare.</span><span class="sxs-lookup"><span data-stu-id="152c6-179">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="152c6-180">Du *kan* slutföra registreringen, men du måste åtgärda dessa problem innan du distribuerar den första enheten.</span><span class="sxs-lookup"><span data-stu-id="152c6-180">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="152c6-181">Inte klart</span><span class="sxs-lookup"><span data-stu-id="152c6-181">Not ready</span></span> | <span data-ttu-id="152c6-182">*Registreringen Miss lyckas* om du inte åtgärdar dessa problem.</span><span class="sxs-lookup"><span data-stu-id="152c6-182">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="152c6-183">Följ stegen i verktyget för att åtgärda dem.</span><span class="sxs-lookup"><span data-stu-id="152c6-183">Follow the steps in the tool to resolve them.</span></span>        |