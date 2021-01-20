---
title: 'Steg 5: Hantering av enheter och program för Microsoft 365 för företags klienter'
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
ms.custom:
- Ent_Solutions
description: Distribuera rätt alternativ för enhets-och program hantering för Microsoft 365-klient organisationer.
ms.openlocfilehash: a581af3ec2ec192112656f1919e27f5b05a41cb1
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908713"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="e5a9b-104">Steg 5:</span><span class="sxs-lookup"><span data-stu-id="e5a9b-104">Step 5.</span></span> <span data-ttu-id="e5a9b-105">Hantering av enheter och program för Microsoft 365 för företags klienter</span><span class="sxs-lookup"><span data-stu-id="e5a9b-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="e5a9b-106">Microsoft 365 för Enterprise innehåller funktioner för att hantera enheter och användning av appar på dessa enheter inom din organisation med hantering av mobila enheter (MDM) och mobil program hantering (MAM).</span><span class="sxs-lookup"><span data-stu-id="e5a9b-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="e5a9b-107">Du kan hantera iOS-, Android-, macOS-och Windows-enheter för att skydda åtkomsten till organisationens resurser, inklusive dina data.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="e5a9b-108">Du kan till exempel förhindra att e-postmeddelanden skickas till personer utanför organisationen eller att du isolerar organisations data från person uppgifter på din personliga persons enheter.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="e5a9b-109">Här är ett exempel på validering och hantering av användare, deras enheter och användning av lokala och moln produktivitets program som Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Validering och hantering av användare, enheter och appar](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="e5a9b-111">För att hjälpa dig att skydda och skydda organisationens resurser inkluderar Microsoft 365 för företag funktioner för att hantera enheter och deras åtkomst till program.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="e5a9b-112">Det finns två alternativ för enhets hantering:</span><span class="sxs-lookup"><span data-stu-id="e5a9b-112">There are two options for device management:</span></span>

- <span data-ttu-id="e5a9b-113">Microsoft Intune, som är en omfattande lösning för enhet och program hantering för företag.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="e5a9b-114">Grundläggande mobilitet och säkerhet, som är en delmängd Intune-tjänster som ingår i alla Microsoft 365-produkter för att hantera enheter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="e5a9b-115">Mer information finns i [grundläggande mobilitet och säkerhet](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities).</span><span class="sxs-lookup"><span data-stu-id="e5a9b-115">For more information, see [Capabilities of Basic Mobility and Security](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities).</span></span>

<span data-ttu-id="e5a9b-116">Om du har Microsoft 365 E3 eller E5 bör du använda Intune.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="e5a9b-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e5a9b-117">Microsoft Intune</span></span>

<span data-ttu-id="e5a9b-118">Du använder [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) för att hantera åtkomst till din organisation med MDM eller Mam.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-118">You use [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="e5a9b-119">MDM är när användare "registrerar" sina enheter i Intune.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="e5a9b-120">När en enhet har registrerats är den en hanterad enhet och kan ta emot organisationens principer, regler och inställningar.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="e5a9b-121">Du kan till exempel installera specifika appar, skapa en lösen ords princip, installera en VPN-anslutning m.m.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="e5a9b-122">Användare med egna personliga enheter kanske inte vill registrera sina enheter eller hanteras av Intune och organisationens principer.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="e5a9b-123">Men du måste ändå skydda organisationens resurser och data.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="e5a9b-124">I det här scenariot kan du skydda dina appar med MAM.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="e5a9b-125">Du kan till exempel använda en MAM policy som kräver att en användare anger en PIN-kod när jag öppnar SharePoint på enheten.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="e5a9b-126">Du bestämmer också hur du ska hantera personliga enheter och företagsägda enheter.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="e5a9b-127">Du kanske vill behandla enheter på olika sätt, beroende på hur de används.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="e5a9b-128">Konfigurationer av identiteter och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="e5a9b-128">Identity and device access configurations</span></span>

<span data-ttu-id="e5a9b-129">Microsoft tillhandahåller en uppsättning konfigurationer för [identitets-och enhets åtkomst](../security/office-365-security/microsoft-365-policies-configurations.md) för att säkerställa en säker och produktiv personal.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-129">Microsoft provides a set of configurations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="e5a9b-130">Dessa konfigurationer inkluderar användning av:</span><span class="sxs-lookup"><span data-stu-id="e5a9b-130">These configurations include the use of:</span></span>

- <span data-ttu-id="e5a9b-131">Principer för villkorsstyrd åtkomst i Azure AD</span><span class="sxs-lookup"><span data-stu-id="e5a9b-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="e5a9b-132">Microsoft Intune-enhetsupptäckning och skydds principer för appar</span><span class="sxs-lookup"><span data-stu-id="e5a9b-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="e5a9b-133">Användar risk principer för Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="e5a9b-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="e5a9b-134">Ytterligare principer för molnappar</span><span class="sxs-lookup"><span data-stu-id="e5a9b-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="e5a9b-135">Här är ett exempel på hur dessa inställningar och principer används för att verifiera och begränsa användare, deras enheter och deras användning av lokala och moln produktivitets program som Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Konfigurationer för identitets-och enhets åtkomst för krav och begränsningar för användare, deras enheter och deras användning av appar](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="e5a9b-137">Använd konfigurationerna i följande artiklar för enhets åtkomst och program hantering:</span><span class="sxs-lookup"><span data-stu-id="e5a9b-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="e5a9b-138">Krav</span><span class="sxs-lookup"><span data-stu-id="e5a9b-138">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="e5a9b-139">Vanliga principer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="e5a9b-139">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="e5a9b-140">Resultat av steg 5</span><span class="sxs-lookup"><span data-stu-id="e5a9b-140">Results of Step 5</span></span>

<span data-ttu-id="e5a9b-141">För hantering av enheter och program för din Microsoft 365-klient organisation har du fastställt Intune-inställningar och policyer för att verifiera och begränsa användare, deras enheter och deras användning av lokala och Cloud Productivity-appar.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="e5a9b-142">Här är ett exempel på en klient organisation med Intune-enhet och program hantering med de nya objekten markerade.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![Exempel på en klient organisation med Intune-enhet och program hantering](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="e5a9b-144">I den här bilden har klient organisationen:</span><span class="sxs-lookup"><span data-stu-id="e5a9b-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="e5a9b-145">Företagsägda enheter registrerade i Intune.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="e5a9b-146">Intune-enhet och program principer för registrerade och personliga enheter.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="e5a9b-147">Pågående underhåll av enhets-och program hantering</span><span class="sxs-lookup"><span data-stu-id="e5a9b-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="e5a9b-148">Kontinuerligt måste du kanske:</span><span class="sxs-lookup"><span data-stu-id="e5a9b-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="e5a9b-149">Hantera enhets registrering.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-149">Manage device enrollment.</span></span>
- <span data-ttu-id="e5a9b-150">Omarbeta inställningar och policyer för ytterligare appar, enheter och säkerhets krav.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>
