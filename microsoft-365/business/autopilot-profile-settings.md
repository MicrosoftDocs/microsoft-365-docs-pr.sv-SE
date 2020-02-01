---
title: Om AutoPilot-profilinställningar
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot-profiler hjälper dig att styra hur Windows installeras på användarenheter. Profilerna innehåller standardinställningar och valfria inställningar som hoppa över Cortana-installationen.
ms.openlocfilehash: 1cc8a3171bbc4a1e5cb531b9364c7791586fc339
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593342"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="d2dc4-104">Om AutoPilot-profilinställningar</span><span class="sxs-lookup"><span data-stu-id="d2dc4-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="d2dc4-105">AutoPilot-profilinställningar</span><span class="sxs-lookup"><span data-stu-id="d2dc4-105">AutoPilot profile settings</span></span>

<span data-ttu-id="d2dc4-106">Du kan använda AutoPilot-profiler för att styra hur Windows är installerat på användarenheter.</span><span class="sxs-lookup"><span data-stu-id="d2dc4-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="d2dc4-107">Profilerna innehåller följande inställningar.</span><span class="sxs-lookup"><span data-stu-id="d2dc4-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="d2dc4-108">**Standardfunktioner för AutoPilot (obligatoriskt) som konfigureras automatiskt:**</span><span class="sxs-lookup"><span data-stu-id="d2dc4-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="d2dc4-109">**Inställning**</span><span class="sxs-lookup"><span data-stu-id="d2dc4-109">**Setting**</span></span>|<span data-ttu-id="d2dc4-110">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="d2dc4-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d2dc4-111">Hoppa över Cortana-, OneDrive- och OEM-registrering</span><span class="sxs-lookup"><span data-stu-id="d2dc4-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="d2dc4-112">Hoppar över installationen av konsumentappar som Cortana och personliga OneDrive-konton.</span><span class="sxs-lookup"><span data-stu-id="d2dc4-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="d2dc4-113">Enhetsanvändaren kan installera dessa senare så länge användaren är en lokal administratör på enheten.</span><span class="sxs-lookup"><span data-stu-id="d2dc4-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="d2dc4-114">OEM-registreringen hoppas över eftersom enheten hanteras av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="d2dc4-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="d2dc4-115">Inloggning med företagets varumärke</span><span class="sxs-lookup"><span data-stu-id="d2dc4-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="d2dc4-116">Om ditt företag har en [Lägg till ditt företags varumärke på inloggningssidan för Office 365](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)får enhetsanvändaren den upplevelsen när du loggar in.</span><span class="sxs-lookup"><span data-stu-id="d2dc4-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="d2dc4-117">Automatisk MDM-registrering med konfigurerade AAD-konton</span><span class="sxs-lookup"><span data-stu-id="d2dc4-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="d2dc4-118">Användaridentiteten hanteras av Azure Active Directory och användare loggar in på Windows och Office 365 med sina Microsoft 365 Business-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d2dc4-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="d2dc4-119">**Valfria inställningar**</span><span class="sxs-lookup"><span data-stu-id="d2dc4-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="d2dc4-120">**Inställning**</span><span class="sxs-lookup"><span data-stu-id="d2dc4-120">**Setting**</span></span>|<span data-ttu-id="d2dc4-121">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="d2dc4-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d2dc4-122">Hoppa över sekretessinställningar (av som standard)</span><span class="sxs-lookup"><span data-stu-id="d2dc4-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="d2dc4-123">Om alternativet **På** har valts ser enhetens användare inte licensavtalet för enheten och Windows när användaren loggar in första gången.</span><span class="sxs-lookup"><span data-stu-id="d2dc4-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="d2dc4-124">Tillåt inte användaren att bli lokal administratör</span><span class="sxs-lookup"><span data-stu-id="d2dc4-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="d2dc4-125">Om alternativet **På** har valts kan enhetens användare inte installera personliga appar som till exempel Cortana.</span><span class="sxs-lookup"><span data-stu-id="d2dc4-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
   
