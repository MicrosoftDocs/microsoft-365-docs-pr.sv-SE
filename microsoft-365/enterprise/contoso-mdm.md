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
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Ta reda på hur Contoso använder Microsoft Intune i Microsoft 365 Enterprise för att hantera enheter och apparna som körs på dem.
ms.openlocfilehash: 7232c89cc105525cc57facd5a1b9de06426adbca
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811813"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="08ce3-103">Hantering av mobila enheter på Contoso</span><span class="sxs-lookup"><span data-stu-id="08ce3-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="08ce3-104">Microsoft 365 Enterprise omfattar Intune och en uppsättning Azure-tjänster som stöder hantering av mobila enheter, appar och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="08ce3-104">Microsoft 365 Enterprise includes Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="08ce3-105">Det är många på Contoso som använder mobila enheter i jobbet. En del av dem arbetar på något av Contosos kontor och andra har inget kontor.</span><span class="sxs-lookup"><span data-stu-id="08ce3-105">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices.</span></span> <span data-ttu-id="08ce3-106">Contoso ville ge medarbetarna möjlighet att arbeta effektivt och samtidigt skydda enheterna, företagsdata som lagras på dessa enheter och programmens funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="08ce3-106">Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="08ce3-107">Planera</span><span class="sxs-lookup"><span data-stu-id="08ce3-107">Plan</span></span>

<span data-ttu-id="08ce3-108">När Contoso började analysera hanteringen av mobila enheter för Microsoft 365 Enterprise identifierades följande användningsfall för Intune:</span><span class="sxs-lookup"><span data-stu-id="08ce3-108">Early in the analysis of mobile device management for Microsoft 365 Enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="08ce3-109">Skydda Exchange Online-e-post och data så att de kan nås på ett säkert sätt med mobila enheter</span><span class="sxs-lookup"><span data-stu-id="08ce3-109">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="08ce3-110">Implementera ett BYOD-program (Bring Your Own Device) för Contosos anställda</span><span class="sxs-lookup"><span data-stu-id="08ce3-110">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="08ce3-111">Dela ut företagsägda telefoner och delade surfplattor med begränsad användning till Contosos anställda</span><span class="sxs-lookup"><span data-stu-id="08ce3-111">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="08ce3-112">Contoso använder inte Intune för att:</span><span class="sxs-lookup"><span data-stu-id="08ce3-112">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="08ce3-113">Ge anställda tillgång till Office 365 på ett säkert sätt från en ohanterad offentlig helskärmsenhet</span><span class="sxs-lookup"><span data-stu-id="08ce3-113">Allow employees to securely access Office 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="08ce3-114">Skydda lokala e-postmeddelanden och data så att de kan användas på ett säkert sätt på mobila enheter, eftersom det inte längre finns lokala Microsoft Exchange-servrar.</span><span class="sxs-lookup"><span data-stu-id="08ce3-114">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="08ce3-115">Distribuera</span><span class="sxs-lookup"><span data-stu-id="08ce3-115">Deploy</span></span>

<span data-ttu-id="08ce3-116">Så här konfigurerar Contoso infrastrukturen för hantering av mobila enheter:</span><span class="sxs-lookup"><span data-stu-id="08ce3-116">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="08ce3-117">Intune har angetts som utfärdare av mobilenhetshantering och Intune används på Azure för att administrera innehåll och hantera enheterna</span><span class="sxs-lookup"><span data-stu-id="08ce3-117">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="08ce3-118">Azure AD-grupper har skapats för enheter för registrering, och Intune-inställningar och enhetsbaserade principer för villkorsstyrd åtkomst har angetts</span><span class="sxs-lookup"><span data-stu-id="08ce3-118">Created Azure AD groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="08ce3-119">Mer information finns i [Principer för villkorlig åtkomst](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span><span class="sxs-lookup"><span data-stu-id="08ce3-119">See [Contoso's Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="08ce3-120">Apples enhetsplattform har aktiverats för att stödja medarbetare med egen iPad, iMac och iPhone, och även företagsägda iPhone-telefoner</span><span class="sxs-lookup"><span data-stu-id="08ce3-120">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="08ce3-121">Contoso-specifika principer för villkor har skapats. Dessa visas under installationen av företagsportalen för Contoso på mobila enheter</span><span class="sxs-lookup"><span data-stu-id="08ce3-121">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="08ce3-122">För enheter som inte är registrerade finns en uppsättning principer för hantering av mobila program (MAM) som kräver autentisering för åtkomst till Office 365-tjänster</span><span class="sxs-lookup"><span data-stu-id="08ce3-122">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Office 365 services</span></span>
- <span data-ttu-id="08ce3-123">Intune-principer har skapats för att tillämpa:</span><span class="sxs-lookup"><span data-stu-id="08ce3-123">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="08ce3-124">Tillåtna appar</span><span class="sxs-lookup"><span data-stu-id="08ce3-124">Allowed apps</span></span>
  - <span data-ttu-id="08ce3-125">Enhetskryptering för att förhindra obehörig åtkomst</span><span class="sxs-lookup"><span data-stu-id="08ce3-125">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="08ce3-126">PIN-kod eller lösenord med sex siffror</span><span class="sxs-lookup"><span data-stu-id="08ce3-126">A six-digit PIN or password</span></span>
  - <span data-ttu-id="08ce3-127">En tidsgräns för inaktivitet</span><span class="sxs-lookup"><span data-stu-id="08ce3-127">An inactivity timeout period</span></span>
  - <span data-ttu-id="08ce3-128">Antivirusskydd, skydd mot skadlig kod och signaturuppdateringar med Windows Defender på Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="08ce3-128">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="08ce3-129">Automatiska uppdateringar för Windows 10-enheter som innehåller de senaste säkerhetsuppdateringarna</span><span class="sxs-lookup"><span data-stu-id="08ce3-129">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="08ce3-130">Push-överföring av certifikat till hanterade enheter</span><span class="sxs-lookup"><span data-stu-id="08ce3-130">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="08ce3-131">En tydlig åtskillnad mellan företagsdata och personliga data.</span><span class="sxs-lookup"><span data-stu-id="08ce3-131">A clear separation of business and personal data.</span></span> <span data-ttu-id="08ce3-132">Användare och administratörer kan selektivt rensa företagsdata från enheten medan personliga data, till exempel bilder, personliga e-postkonton och personliga filer, bevaras.</span><span class="sxs-lookup"><span data-stu-id="08ce3-132">Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="08ce3-133">Efter distributionen registrerade Contoso datorer och företagsägda telefoner och surfplattor genom att lägga till dem i lämpliga Intune-enhetsgrupper, och Contoso distribuerade ett BYOD-program så att medarbetarna kunde registrera sina personliga enheter.</span><span class="sxs-lookup"><span data-stu-id="08ce3-133">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="08ce3-134">De registrerade enheterna fick Intune-principer, vilket innebär att dessa enheter och tillhörande appar nu är hanterade och skyddade.</span><span class="sxs-lookup"><span data-stu-id="08ce3-134">Enrolled devices received Intune policies, resulting in managed and secured devices and their applications.</span></span> <span data-ttu-id="08ce3-135">För enheter som inte har registrerats används principer för hantering av mobila program (MAM) som anger vilka appar som är tillåtna.</span><span class="sxs-lookup"><span data-stu-id="08ce3-135">Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="08ce3-136">Här är Contosos distributionsarkitektur för hantering av mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="08ce3-136">Here is Contoso's mobile device management deployment architecture.</span></span>

![Contosos distributionsarkitektur för hantering av mobila enheter.](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="08ce3-138">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="08ce3-138">Next step</span></span>

<span data-ttu-id="08ce3-139">[Lär dig](contoso-info-protect.md) hur Contoso använder funktioner för informationsskydd i Microsoft 365 Enterprise för att klassificera, identifiera och skydda viktiga digitala tillgångar i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="08ce3-139">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 Enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="08ce3-140">Se även</span><span class="sxs-lookup"><span data-stu-id="08ce3-140">See also</span></span>

[<span data-ttu-id="08ce3-141">Hantering av mobila enheter för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="08ce3-141">Mobile device management for Microsoft 365 Enterprise</span></span>](mobility-infrastructure.md)

[<span data-ttu-id="08ce3-142">Distributionsguide</span><span class="sxs-lookup"><span data-stu-id="08ce3-142">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="08ce3-143">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="08ce3-143">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

