---
title: 'Steg 5: Enhet- och apphantering för Microsoft 365 för företagsklienter'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Distribuera rätt alternativ för enhet och programhantering för Microsoft 365-klientorganisationen.
ms.openlocfilehash: 96412cb52540e87341fa67e20382951db7becfbe
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406378"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="c6416-104">Steg 5:</span><span class="sxs-lookup"><span data-stu-id="c6416-104">Step 5.</span></span> <span data-ttu-id="c6416-105">Enhet- och apphantering för Microsoft 365 för företagsklienter</span><span class="sxs-lookup"><span data-stu-id="c6416-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="c6416-106">Microsoft 365 för företag innehåller funktioner för att hantera enheter och användning av appar på de enheterna i din organisation med hantering av mobila enheter (MDM) och hantering av mobila program (MAM).</span><span class="sxs-lookup"><span data-stu-id="c6416-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="c6416-107">Du kan hantera iOS-, Android-, macOS- och Windows-enheter för att skydda åtkomsten till organisationens resurser, inklusive dina data.</span><span class="sxs-lookup"><span data-stu-id="c6416-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="c6416-108">Du kan till exempel förhindra att e-postmeddelanden skickas till personer utanför organisationen eller isolera organisationsdata från personuppgifter på dina anställdas personliga enheter.</span><span class="sxs-lookup"><span data-stu-id="c6416-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="c6416-109">Här är ett exempel på validering och hantering av användare, deras enheter och användning av lokala appar och produktivitetsappar i molnet som Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6416-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Validering och hantering av användare, enheter och appar](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="c6416-111">För att hjälpa dig att skydda organisationens resurser innehåller Microsoft 365 för företag funktioner som hjälper dig att hantera enheter och deras åtkomst till appar.</span><span class="sxs-lookup"><span data-stu-id="c6416-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="c6416-112">Det finns två alternativ för enhetshantering:</span><span class="sxs-lookup"><span data-stu-id="c6416-112">There are two options for device management:</span></span>

- <span data-ttu-id="c6416-113">Microsoft Intune, som är en omfattande lösning för enhet- och apphantering för företag.</span><span class="sxs-lookup"><span data-stu-id="c6416-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="c6416-114">Basic Mobility and Security, som är en delmängd av Intune-tjänsterna som ingår i alla Microsoft 365-produkter för att hantera enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c6416-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="c6416-115">Mer information finns i [Funktionerna för grundläggande rörlighet och säkerhet.](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities)</span><span class="sxs-lookup"><span data-stu-id="c6416-115">For more information, see [Capabilities of Basic Mobility and Security](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities).</span></span>

<span data-ttu-id="c6416-116">Om du har Microsoft 365 E3 eller E5 bör du använda Intune.</span><span class="sxs-lookup"><span data-stu-id="c6416-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="c6416-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c6416-117">Microsoft Intune</span></span>

<span data-ttu-id="c6416-118">Du använder [Microsoft Intune för](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) att hantera åtkomsten till din organisation med MDM eller MAM.</span><span class="sxs-lookup"><span data-stu-id="c6416-118">You use [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="c6416-119">MDM är när användare "registrerar" sina enheter i Intune.</span><span class="sxs-lookup"><span data-stu-id="c6416-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="c6416-120">När en enhet har registrerats är det en hanterad enhet och kan ta emot organisationens principer, regler och inställningar.</span><span class="sxs-lookup"><span data-stu-id="c6416-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="c6416-121">Du kan till exempel installera specifika appar, skapa en lösenordsprincip, installera en VPN-anslutning och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="c6416-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="c6416-122">Användare med egna personliga enheter kanske inte vill registrera sina enheter eller hanteras av Intune och organisationens principer.</span><span class="sxs-lookup"><span data-stu-id="c6416-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="c6416-123">Men du måste fortfarande skydda organisationens resurser och data.</span><span class="sxs-lookup"><span data-stu-id="c6416-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="c6416-124">I det här scenariot kan du skydda dina program med mam.</span><span class="sxs-lookup"><span data-stu-id="c6416-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="c6416-125">Du kan till exempel använda en MAM-princip som kräver att användaren anger en PIN-kod när han eller hon använder SharePoint på enheten.</span><span class="sxs-lookup"><span data-stu-id="c6416-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="c6416-126">Du får också bestämma hur du ska hantera personliga enheter och enheter som ägs av organisationen.</span><span class="sxs-lookup"><span data-stu-id="c6416-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="c6416-127">Du kanske vill behandla enheter olika beroende på hur de används.</span><span class="sxs-lookup"><span data-stu-id="c6416-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="c6416-128">Konfigurationer av identiteter och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="c6416-128">Identity and device access configurations</span></span>

<span data-ttu-id="c6416-129">Microsoft tillhandahåller en uppsättning konfigurationer för identitet [och enhetsåtkomst för](../security/office-365-security/microsoft-365-policies-configurations.md) att säkerställa en säker och produktiv arbetsstyrka.</span><span class="sxs-lookup"><span data-stu-id="c6416-129">Microsoft provides a set of configurations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="c6416-130">De här konfigurationerna omfattar användning av:</span><span class="sxs-lookup"><span data-stu-id="c6416-130">These configurations include the use of:</span></span>

- <span data-ttu-id="c6416-131">Principer för villkorsstyrd åtkomst i Azure AD</span><span class="sxs-lookup"><span data-stu-id="c6416-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="c6416-132">Microsoft Intune-policyer för enhetsefterlevnad och appskydd</span><span class="sxs-lookup"><span data-stu-id="c6416-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="c6416-133">Användarriskprinciper för Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="c6416-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="c6416-134">Ytterligare principer för molnappar</span><span class="sxs-lookup"><span data-stu-id="c6416-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="c6416-135">Här är ett exempel på hur de här inställningarna och principerna används för att verifiera och begränsa användare, deras enheter och användning av lokala appar och produktivitetsappar i molnet, till exempel Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6416-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Konfigurationer av identitets- och enhetsåtkomst för krav och begränsningar för användare, deras enheter och deras användning av appar](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="c6416-137">För enhetsåtkomst och apphantering använder du konfigurationerna i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="c6416-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="c6416-138">Krav</span><span class="sxs-lookup"><span data-stu-id="c6416-138">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="c6416-139">Vanliga principer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="c6416-139">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="c6416-140">Resultat av steg 5</span><span class="sxs-lookup"><span data-stu-id="c6416-140">Results of Step 5</span></span>

<span data-ttu-id="c6416-141">För enhet- och apphantering för Microsoft 365-klienten har du fastställt Intune-inställningarna och principerna för att verifiera och begränsa användare, deras enheter och deras användning av lokala appar och appar för moln produktivitet.</span><span class="sxs-lookup"><span data-stu-id="c6416-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="c6416-142">Här är ett exempel på en klientorganisation med Intune-enhet och apphantering med de nya elementen markerade.</span><span class="sxs-lookup"><span data-stu-id="c6416-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![Exempel på en klientorganisation med Intune-enhet och apphantering](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="c6416-144">I den här bilden har klientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="c6416-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="c6416-145">Organisationsägda enheter som registrerats i Intune.</span><span class="sxs-lookup"><span data-stu-id="c6416-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="c6416-146">Intune-enhet och appprinciper för registrerade och personliga enheter.</span><span class="sxs-lookup"><span data-stu-id="c6416-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="c6416-147">Löpande underhåll för enhet och apphantering</span><span class="sxs-lookup"><span data-stu-id="c6416-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="c6416-148">Du kan kontinuerligt behöva:</span><span class="sxs-lookup"><span data-stu-id="c6416-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="c6416-149">Hantera enhetsregistrering.</span><span class="sxs-lookup"><span data-stu-id="c6416-149">Manage device enrollment.</span></span>
- <span data-ttu-id="c6416-150">Ändra inställningarna och principerna för ytterligare appar, enheter och säkerhetskrav.</span><span class="sxs-lookup"><span data-stu-id="c6416-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>
