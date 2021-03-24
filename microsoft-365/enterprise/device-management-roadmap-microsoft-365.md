---
title: Översikt över enhetshantering för Microsoft 365
keywords: Microsoft 365, Microsoft 365 för företag, Microsoft 365-dokumentation, hantering av mobila enheter, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: Översikt över att konfigurera enhetshantering för Microsoft 365.
ms.openlocfilehash: ec284a96fc8e7285f89e8a909b76c782b4469ce1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051466"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="eae52-104">Översikt över enhetshantering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eae52-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="eae52-105">Microsoft 365 för företag innehåller funktioner som hjälper dig att hantera enheter och deras appar inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="eae52-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="eae52-106">Hantering av mobila enheter hjälper dig att skydda organisationens resurser.</span><span class="sxs-lookup"><span data-stu-id="eae52-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="eae52-107">Det finns två alternativ för enhetshantering:</span><span class="sxs-lookup"><span data-stu-id="eae52-107">There are two options for device management:</span></span>

- [<span data-ttu-id="eae52-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="eae52-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="eae52-109">Grundläggande Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="eae52-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="eae52-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="eae52-110">Microsoft Intune</span></span>

<span data-ttu-id="eae52-111">Du kan använda Microsoft Intune för att hantera åtkomsten till din organisation med hantering av mobila enheter eller hantering av mobilprogram.</span><span class="sxs-lookup"><span data-stu-id="eae52-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="eae52-112">Hantering av mobila enheter är när användarna "registrerar" sina enheter i Intune.</span><span class="sxs-lookup"><span data-stu-id="eae52-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="eae52-113">När en enhet har registrerats är det en hanterad enhet. Det innebär att organisationens principer, regler och inställningar kan visas.</span><span class="sxs-lookup"><span data-stu-id="eae52-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="eae52-114">Du kan till exempel installera specifika appar, skapa en lösenordsprincip, installera en VPN-anslutning med mera.</span><span class="sxs-lookup"><span data-stu-id="eae52-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="eae52-115">Användare med sina egna personliga enheter kanske inte vill registrera sina enheter eller hanteras av Intune och organisationens principer.</span><span class="sxs-lookup"><span data-stu-id="eae52-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="eae52-116">Men du måste fortfarande skydda organisationens resurser och data.</span><span class="sxs-lookup"><span data-stu-id="eae52-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="eae52-117">I det här scenariot kan du skydda dina appar med hantering av mobilprogram.</span><span class="sxs-lookup"><span data-stu-id="eae52-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="eae52-118">Du kan till exempel använda en princip för hantering av mobilprogram som kräver att användaren anger en PIN-kod när han eller hon öppnar SharePoint Online på enheten.</span><span class="sxs-lookup"><span data-stu-id="eae52-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="eae52-119">Du får också bestämma hur du ska hantera personliga enheter och organisationsägda enheter.</span><span class="sxs-lookup"><span data-stu-id="eae52-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="eae52-120">Du kanske vill behandla enheter olika beroende på hur de används.</span><span class="sxs-lookup"><span data-stu-id="eae52-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="eae52-121">Grundläggande Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="eae52-121">Basic Mobility and Security</span></span>

<span data-ttu-id="eae52-122">Det här är inbyggt i Microsoft 365 och hjälper dig att skydda och hantera dina användares mobila enheter, till exempel iPhone, iPad, Android och Windows-telefoner.</span><span class="sxs-lookup"><span data-stu-id="eae52-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="eae52-123">Du kan skapa och hantera säkerhetsprinciper för enheter, fjärradea enheter och visa detaljerade enhetsrapporter.</span><span class="sxs-lookup"><span data-stu-id="eae52-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="eae52-124">Välja mellan de två alternativen</span><span class="sxs-lookup"><span data-stu-id="eae52-124">Choose between the two options</span></span>

<span data-ttu-id="eae52-125">Mer information om vilka alternativ för enhetshantering som passar bäst för dig finns i [Välja mellan Basic Mobility Security och Intune.](/office365/securitycompliance/choose-between-mdm-and-intune)</span><span class="sxs-lookup"><span data-stu-id="eae52-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="eae52-126">Baserat på din utvärdering kan du komma igång med att hantera dina enheter med:</span><span class="sxs-lookup"><span data-stu-id="eae52-126">Based on your assessment, get started managing your devices with:</span></span>

- [<span data-ttu-id="eae52-127">Intune</span><span class="sxs-lookup"><span data-stu-id="eae52-127">Intune</span></span>](/mem/intune/fundamentals/planning-guide)
- [<span data-ttu-id="eae52-128">Grundläggande Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="eae52-128">Basic Mobility and Security</span></span>](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="eae52-129">Rekommendationer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="eae52-129">Identity and device access recommendations</span></span>

<span data-ttu-id="eae52-130">Microsoft tillhandahåller en uppsättning rekommendationer för [identitets- och enhetsåtkomst](../security/defender-365-security/microsoft-365-policies-configurations.md) för att säkerställa en säker och produktiv arbetsstyrka.</span><span class="sxs-lookup"><span data-stu-id="eae52-130">Microsoft provides a set of recommendations for [identity and device access](../security/defender-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="eae52-131">För enhetsåtkomst använder du rekommendationer och inställningar i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="eae52-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="eae52-132">Krav</span><span class="sxs-lookup"><span data-stu-id="eae52-132">Prerequisites</span></span>](../security/defender-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="eae52-133">Vanliga principer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="eae52-133">Common identity and device access policies</span></span>](../security/defender-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="eae52-134">Hur Contoso hanterade enheter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eae52-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="eae52-135">Mer information om hur en fiktiv men representativt multinationellt företag distribuerade sin infrastruktur för hantering av mobila enheter med Microsoft 365-molntjänster finns i [Mobile device management för Contoso.](contoso-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="eae52-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>