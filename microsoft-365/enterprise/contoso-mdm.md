---
title: Hantering av mobila enheter på Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå hur Contoso använder Microsoft Intune i Microsoft 365 för företag för att hantera dess enheter och programmen som körs på dem.
ms.openlocfilehash: d3f973827a9b05a415efe9225a2bdb3d83ccaf38
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649651"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="c5b02-103">Hantering av mobila enheter på Contoso</span><span class="sxs-lookup"><span data-stu-id="c5b02-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="c5b02-104">Microsoft 365 för Enterprise inkluderar Intune och en uppsättning Azure-tjänster som stöder mobila enheter och program hantering och-säkerhet.</span><span class="sxs-lookup"><span data-stu-id="c5b02-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="c5b02-105">Contoso har många mobila anställda.</span><span class="sxs-lookup"><span data-stu-id="c5b02-105">Contoso has many mobile-enabled employees.</span></span> <span data-ttu-id="c5b02-106">Vissa har kontor på Contoso-platser och vissa har inga kontor.</span><span class="sxs-lookup"><span data-stu-id="c5b02-106">Some have offices in Contoso locations, and some have no offices.</span></span> <span data-ttu-id="c5b02-107">Contoso ville ge medarbetarna möjlighet att arbeta effektivt och samtidigt skydda enheterna, företagsdata som lagras på dessa enheter och programmens funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="c5b02-107">Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="c5b02-108">Planera</span><span class="sxs-lookup"><span data-stu-id="c5b02-108">Plan</span></span>

<span data-ttu-id="c5b02-109">Contoso identifierade följande Intune användnings fall i hantering av mobila enheter för Microsoft 365 för företag:</span><span class="sxs-lookup"><span data-stu-id="c5b02-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="c5b02-110">Skydda Exchange Online-e-post och data så att de kan nås av mobila enheter på ett säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="c5b02-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="c5b02-111">Implementera ett BYOD-program för Contoso-anställda.</span><span class="sxs-lookup"><span data-stu-id="c5b02-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="c5b02-112">Ge organisationens ägda telefoner och begränsa-Använd delade surfplattor till contoso-anställda.</span><span class="sxs-lookup"><span data-stu-id="c5b02-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="c5b02-113">Contoso använder inte Intune för att:</span><span class="sxs-lookup"><span data-stu-id="c5b02-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="c5b02-114">Gör det möjligt för anställda att säkert komma åt Microsoft 365 från en ohanterad offentlig kiosk.</span><span class="sxs-lookup"><span data-stu-id="c5b02-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="c5b02-115">Skydda det lokala e-postmeddelandet och data så att det kan nås på ett säkert sätt via mobila enheter eftersom det inte finns några lokala Microsoft Exchange-servrar.</span><span class="sxs-lookup"><span data-stu-id="c5b02-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="c5b02-116">Distribuera</span><span class="sxs-lookup"><span data-stu-id="c5b02-116">Deploy</span></span>

<span data-ttu-id="c5b02-117">Så här konfigurerar Contoso infrastrukturen för hantering av mobila enheter:</span><span class="sxs-lookup"><span data-stu-id="c5b02-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="c5b02-118">Ange Intune som hanterings myndigheten för mobila enheter (MDM) och Använd Intune på Azure för att administrera innehåll och hantera enheterna</span><span class="sxs-lookup"><span data-stu-id="c5b02-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="c5b02-119">Skapade Azure Active Directory-grupper (Azure AD) för enheter för registrerings-och Intune-inställningar och enhetbaserade principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="c5b02-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="c5b02-120">Mer information finns i [principer för villkorsstyrd åtkomst via contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span><span class="sxs-lookup"><span data-stu-id="c5b02-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="c5b02-121">Aktiverat Apple-enheten för att stödja anställda med iPad, iMacs och iPhone och företagsägda iPhone</span><span class="sxs-lookup"><span data-stu-id="c5b02-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="c5b02-122">Contoso-specifika principer för villkor har skapats. Dessa visas under installationen av företagsportalen för Contoso på mobila enheter</span><span class="sxs-lookup"><span data-stu-id="c5b02-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="c5b02-123">För enheter som inte är registrerade, implementerade en uppsättning principer för MAM (Mobile Application Management) för att kräva åtkomst till Microsoft 365-tjänster</span><span class="sxs-lookup"><span data-stu-id="c5b02-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="c5b02-124">Intune-principer har skapats för att tillämpa:</span><span class="sxs-lookup"><span data-stu-id="c5b02-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="c5b02-125">Tillåtna appar.</span><span class="sxs-lookup"><span data-stu-id="c5b02-125">Allowed apps.</span></span>
  - <span data-ttu-id="c5b02-126">Enhets kryptering för att förhindra obehörig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="c5b02-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="c5b02-127">En sex eller ett fyrsiffrigt lösen ord.</span><span class="sxs-lookup"><span data-stu-id="c5b02-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="c5b02-128">En inaktivitet – tids gräns.</span><span class="sxs-lookup"><span data-stu-id="c5b02-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="c5b02-129">Skydd mot virus och skadlig program vara med Windows Defender på Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="c5b02-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="c5b02-130">Automatiska uppdateringar på Windows 10-enheter som innehåller de senaste säkerhets uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="c5b02-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="c5b02-131">Skicka certifikat till hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="c5b02-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="c5b02-132">En tydlig åtskillnad mellan företagsdata och personliga data.</span><span class="sxs-lookup"><span data-stu-id="c5b02-132">A clear separation of business and personal data.</span></span> <span data-ttu-id="c5b02-133">Användare och administratörer kan selektivt rensa företagsdata från enheten medan personliga data, till exempel bilder, personliga e-postkonton och personliga filer, bevaras.</span><span class="sxs-lookup"><span data-stu-id="c5b02-133">Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="c5b02-134">Contoso-registrerade distribuerade och ägda datorer och surfplattor genom att lägga till dem till rätt Intune-gruppgrupper.</span><span class="sxs-lookup"><span data-stu-id="c5b02-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="c5b02-135">De uppvisade också ett BYOD-program som de anställda kan registrera sina personliga enheter på.</span><span class="sxs-lookup"><span data-stu-id="c5b02-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="c5b02-136">Registrerade enheter tar emot Intune-principer, som leder till hanterade och skyddade enheter och deras program.</span><span class="sxs-lookup"><span data-stu-id="c5b02-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="c5b02-137">Enheter som inte har registrerats har MAM-principer (Mobile Application Management) som anger tillåtna program.</span><span class="sxs-lookup"><span data-stu-id="c5b02-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="c5b02-138">Här är distributions arkitekturen contoso Mobile Device Management.</span><span class="sxs-lookup"><span data-stu-id="c5b02-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Distributions infrastruktur för Contoso Mobile Device Management](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="c5b02-140">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c5b02-140">Next step</span></span>

<span data-ttu-id="c5b02-141">[Lär dig](contoso-info-protect.md) hur Contoso använder informations skydds funktionerna i Microsoft 365 för företag för att klassificera, identifiera och skydda viktiga digitala till gångar i sin organisation.</span><span class="sxs-lookup"><span data-stu-id="c5b02-141">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5b02-142">Se även</span><span class="sxs-lookup"><span data-stu-id="c5b02-142">See also</span></span>

[<span data-ttu-id="c5b02-143">Enhets hantering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c5b02-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="c5b02-144">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="c5b02-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c5b02-145">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="c5b02-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

