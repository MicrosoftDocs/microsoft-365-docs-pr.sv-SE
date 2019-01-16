---
title: Om AutoPilot-profilinställningar
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot profiler hjälper dig att styra hur Windows installeras på användarens enheter. Profilerna innehåller standard och valfria inställningar som att hoppa över installationen av Cortana.
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982249"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="b6dd1-104">Om AutoPilot-profilinställningar</span><span class="sxs-lookup"><span data-stu-id="b6dd1-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="b6dd1-105">AutoPilot-profilinställningar</span><span class="sxs-lookup"><span data-stu-id="b6dd1-105">AutoPilot profile settings</span></span>

<span data-ttu-id="b6dd1-p102">Du kan styra hur Windows installeras på användarenheter med hjälp av AutoPilot-profiler. Profilerna innehåller följande inställningar.</span><span class="sxs-lookup"><span data-stu-id="b6dd1-p102">You can control how Windows gets installed on user devices by using the AutoPilot profiles. The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="b6dd1-108">**Standardfunktioner för AutoPilot (obligatoriskt) som konfigureras automatiskt:**</span><span class="sxs-lookup"><span data-stu-id="b6dd1-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="b6dd1-109">**Inställning**</span><span class="sxs-lookup"><span data-stu-id="b6dd1-109">**Setting**</span></span>|<span data-ttu-id="b6dd1-110">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="b6dd1-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6dd1-111">Hoppa över Cortana, OneDrive och OEM-registrering</span><span class="sxs-lookup"><span data-stu-id="b6dd1-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="b6dd1-p103">Hoppar över installationen av konsumentappar som Cortana och personliga OneDrive-konton. Enhetens användare kan installera dem senare om användaren är lokal administratör på enheten. OEM-registreringen hoppas över eftersom enheten hanteras av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="b6dd1-p103">Skips the installation of consumer apps like Cortana and personal OneDrive. The device user can install these later as long as he or she is a local admin on the device. The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="b6dd1-115">Inloggning med företagets varumärke</span><span class="sxs-lookup"><span data-stu-id="b6dd1-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="b6dd1-116">Om ditt företag har en [Lägg till företagets varumärke till sidan Office 365 Logga In](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), få enhet användare som erfarenheter när du loggar in.</span><span class="sxs-lookup"><span data-stu-id="b6dd1-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="b6dd1-117">Automatisk MDM-registrering med konfigurerade AAD-konton</span><span class="sxs-lookup"><span data-stu-id="b6dd1-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="b6dd1-118">Användaridentiteten hanteras av Azure Active Directory och användarna loggar in i Windows och Office 365 med sina autentiseringsuppgifter för Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="b6dd1-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="b6dd1-119">**Valfria inställningar**</span><span class="sxs-lookup"><span data-stu-id="b6dd1-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="b6dd1-120">**Inställning**</span><span class="sxs-lookup"><span data-stu-id="b6dd1-120">**Setting**</span></span>|<span data-ttu-id="b6dd1-121">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="b6dd1-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6dd1-122">Hoppa över sekretessinställningar (av som standard)</span><span class="sxs-lookup"><span data-stu-id="b6dd1-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="b6dd1-123">Om alternativet **På** har valts ser enhetens användare inte licensavtalet för enheten och Windows när användaren loggar in första gången.</span><span class="sxs-lookup"><span data-stu-id="b6dd1-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="b6dd1-124">Tillåt inte användaren att bli lokal administratör</span><span class="sxs-lookup"><span data-stu-id="b6dd1-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="b6dd1-125">Om alternativet **På** har valts kan enhetens användare inte installera personliga appar som till exempel Cortana.</span><span class="sxs-lookup"><span data-stu-id="b6dd1-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
