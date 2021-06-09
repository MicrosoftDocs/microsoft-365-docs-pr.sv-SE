---
title: Hantering av mobila enheter på Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå hur Contoso använder Microsoft Intune i Microsoft 365 för företag för att hantera dess enheter och program som körs på dem.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754003"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="ef9fc-103">Hantering av mobila enheter på Contoso</span><span class="sxs-lookup"><span data-stu-id="ef9fc-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="ef9fc-104">Microsoft 365 för företag inkluderar Intune och en uppsättning Azure-tjänster som stöder hantering och säkerhet för mobila enheter och program.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="ef9fc-105">Contoso har många anställda med mobilaktiverad personal.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-105">Contoso has many mobile-enabled employees.</span></span> <span data-ttu-id="ef9fc-106">Vissa har kontor i Contoso-platser och vissa har inga kontor.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-106">Some have offices in Contoso locations, and some have no offices.</span></span> <span data-ttu-id="ef9fc-107">Contoso ville ge medarbetarna möjlighet att arbeta effektivt och samtidigt skydda enheterna, företagsdata som lagras på dessa enheter och programmens funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-107">Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="ef9fc-108">Planera</span><span class="sxs-lookup"><span data-stu-id="ef9fc-108">Plan</span></span>

<span data-ttu-id="ef9fc-109">Contoso har identifierat följande Intune-användningsfall för hantering av mobila enheter Microsoft 365 för företag:</span><span class="sxs-lookup"><span data-stu-id="ef9fc-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="ef9fc-110">Skydda Exchange Online e-post och data så att de kan nås säkert av mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="ef9fc-111">Implementera ett BYOD-program (bring-your-own-device) för Contoso-anställda.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="ef9fc-112">Utfärda telefoner som ägs av organisationen och delade surfplattor med begränsad användning till Contoso-anställda.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="ef9fc-113">Contoso använder inte Intune för att:</span><span class="sxs-lookup"><span data-stu-id="ef9fc-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="ef9fc-114">Tillåt anställda att på ett säkert sätt Microsoft 365 från en ohanterad offentlig kiosk.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="ef9fc-115">Skydda lokal e-post och data så att de kan nås säkert av mobila enheter, eftersom det inte finns några Microsoft Exchange lokala servrar.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="ef9fc-116">Distribuera</span><span class="sxs-lookup"><span data-stu-id="ef9fc-116">Deploy</span></span>

<span data-ttu-id="ef9fc-117">Så här konfigurerar Contoso infrastrukturen för hantering av mobila enheter:</span><span class="sxs-lookup"><span data-stu-id="ef9fc-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="ef9fc-118">Ange Intune som MDM-myndighet (Mobile Device Management) och använd Intune i Azure för att administrera innehåll och hantera enheter</span><span class="sxs-lookup"><span data-stu-id="ef9fc-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="ef9fc-119">Skapat Azure Active Directory (Azure AD) för enheter för registrering och Intune-inställningar och enhetsbaserade villkorsstyrda åtkomstprinciper</span><span class="sxs-lookup"><span data-stu-id="ef9fc-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="ef9fc-120">Mer information finns i [Contosos villkorsstyrda åtkomstpolicyer.](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)</span><span class="sxs-lookup"><span data-stu-id="ef9fc-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="ef9fc-121">Apple-enhetsplattformen aktiverades för att ge stöd för anställda med iPad, iMacs och iPhone samt företagsägda iPhone</span><span class="sxs-lookup"><span data-stu-id="ef9fc-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="ef9fc-122">Contoso-specifika principer för villkor har skapats. Dessa visas under installationen av företagsportalen för Contoso på mobila enheter</span><span class="sxs-lookup"><span data-stu-id="ef9fc-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="ef9fc-123">För enheter som inte är registrerade har implementerat en uppsättning principer för hantering av mobilprogram (MAM) för att kräva autentisering för åtkomst till Microsoft 365-tjänster</span><span class="sxs-lookup"><span data-stu-id="ef9fc-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="ef9fc-124">Intune-principer har skapats för att tillämpa:</span><span class="sxs-lookup"><span data-stu-id="ef9fc-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="ef9fc-125">Tillåtna appar.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-125">Allowed apps.</span></span>
  - <span data-ttu-id="ef9fc-126">Enhetskryptering för att förhindra obehörig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="ef9fc-127">En sexsiffrig PIN-kod eller ett lösenord.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="ef9fc-128">En tidsgräns för inaktivitet.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="ef9fc-129">Skydd mot antivirusprogram och skadlig programvara samt signaturuppdateringar med Windows Defender på Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="ef9fc-130">Automatiska uppdateringar på Windows 10 enheter som innehåller de senaste säkerhetsuppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="ef9fc-131">Trycker på certifikat till hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="ef9fc-132">En tydlig åtskillnad mellan företagsdata och personliga data.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-132">A clear separation of business and personal data.</span></span> <span data-ttu-id="ef9fc-133">Användare och administratörer kan selektivt rensa företagsdata från enheten medan personliga data, till exempel bilder, personliga e-postkonton och personliga filer, bevaras.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-133">Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="ef9fc-134">Contoso registrerade distribuerade datorer och företagsägda smartphones och handdatorer genom att lägga till dem i lämpliga Intune-enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="ef9fc-135">De upprättade även ett BYOD-program för anställda för att registrera sina personliga enheter.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="ef9fc-136">Registrerade enheter får Intune-principer, vilket resulterar i hanterade och skyddade enheter och deras program.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="ef9fc-137">Enheter som inte är registrerade har principer för hantering av mobilprogram (MAM) som anger tillåtna program.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="ef9fc-138">Här är distributionsarkitekturen för hantering av mobila enheter i Contoso.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Distributionsinfrastrukturen för hantering av mobila enheter i Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="ef9fc-140">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ef9fc-140">Next step</span></span>

<span data-ttu-id="ef9fc-141">Lär dig hur Contoso använder funktionerna för [informationsskydd](contoso-info-protect.md) i Microsoft 365 för företag för att klassificera, identifiera och skydda viktiga digitala tillgångar i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ef9fc-141">Learn how Contoso uses the [information protection capabilities](contoso-info-protect.md) of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef9fc-142">Se även</span><span class="sxs-lookup"><span data-stu-id="ef9fc-142">See also</span></span>

[<span data-ttu-id="ef9fc-143">Enhetshantering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ef9fc-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="ef9fc-144">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="ef9fc-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ef9fc-145">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="ef9fc-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

