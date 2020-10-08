---
title: Enhets hanterings översikt för Microsoft 365
keywords: Microsoft 365, Microsoft 365 för Enterprise, Microsoft 365-dokumentation, hantering av mobila enheter, Intune
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
description: Översikten för konfiguration av enhets hantering för Microsoft 365.
ms.openlocfilehash: 0efe7098f90064184f222acb671ae6f96c1b38d5
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384756"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="0cdd0-104">Enhets hanterings översikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0cdd0-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="0cdd0-105">Microsoft 365 för Enterprise innehåller funktioner för att hantera enheter och deras appar i din organisation.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="0cdd0-106">Genom att hantera mobila enheter kan du skydda din organisations resurser.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="0cdd0-107">Det finns två alternativ för enhets hantering:</span><span class="sxs-lookup"><span data-stu-id="0cdd0-107">There are two options for device management:</span></span>

- [<span data-ttu-id="0cdd0-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0cdd0-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="0cdd0-109">Grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="0cdd0-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="0cdd0-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0cdd0-110">Microsoft Intune</span></span>

<span data-ttu-id="0cdd0-111">Du kan använda Microsoft Intune för att hantera åtkomst till din organisation med hantering av mobila enheter och hantering av mobil program.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="0cdd0-112">Hantering av mobila enheter är när användarna "registrerar" sina enheter i Intune.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="0cdd0-113">När en enhet har registrerats är det en hanterad enhet; Därför kan det ta emot organisationens principer, regler och inställningar.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="0cdd0-114">Du kan till exempel installera specifika appar, skapa en lösen ords princip, installera en VPN-anslutning m.m.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="0cdd0-115">Användare med egna personliga enheter kanske inte vill registrera sina enheter eller hanteras av Intune och organisationens principer.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="0cdd0-116">Men du måste ändå skydda organisationens resurser och data.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="0cdd0-117">I det här scenariot kan du skydda dina appar med hantering av mobil program.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="0cdd0-118">Du kan till exempel använda en hanterings princip för mobila program som kräver att en användare anger en PIN-kod när jag öppnar SharePoint Online på enheten.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="0cdd0-119">Du bestämmer också hur du ska hantera personliga enheter och företagsägda enheter.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="0cdd0-120">Du kanske vill behandla enheter på olika sätt, beroende på hur de används.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="0cdd0-121">Grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="0cdd0-121">Basic Mobility and Security</span></span>

<span data-ttu-id="0cdd0-122">Den är inbyggd i Microsoft 365 och hjälper dig att skydda och hantera användares mobila enheter som iPhone, iPad, Android och Windows-telefoner.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="0cdd0-123">Du kan skapa och hantera säkerhets principer för enheter, rensa en enhet och se detaljerade enhets rapporter.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="0cdd0-124">Välj mellan de två alternativen</span><span class="sxs-lookup"><span data-stu-id="0cdd0-124">Choose between the two options</span></span>

<span data-ttu-id="0cdd0-125">För att hjälpa dig att bättre bedöma vilka enheter som hanteras bäst för dig kan du läsa mer i [välja mellan grundläggande mobilitets säkerhet och Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).</span><span class="sxs-lookup"><span data-stu-id="0cdd0-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="0cdd0-126">Baserat på din utvärdering kan du komma igång med att hantera dina enheter:</span><span class="sxs-lookup"><span data-stu-id="0cdd0-126">Based on your assessment, get started managing your devices with:</span></span>

- <span data-ttu-id="0cdd0-127">[Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span><span class="sxs-lookup"><span data-stu-id="0cdd0-127">[Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>
- <span data-ttu-id="0cdd0-128">[Grundläggande mobilitet och säkerhet](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span><span class="sxs-lookup"><span data-stu-id="0cdd0-128">[Basic Mobility and Security](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="0cdd0-129">Rekommendationer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="0cdd0-129">Identity and device access recommendations</span></span>

<span data-ttu-id="0cdd0-130">Microsoft tillhandahåller en uppsättning rekommendationer för [identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md) för att säkerställa en säker och produktiv arbetsstyrka.</span><span class="sxs-lookup"><span data-stu-id="0cdd0-130">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="0cdd0-131">Använd rekommendationer och inställningar i följande artiklar för att få åtkomst till enheter:</span><span class="sxs-lookup"><span data-stu-id="0cdd0-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="0cdd0-132">Krav</span><span class="sxs-lookup"><span data-stu-id="0cdd0-132">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="0cdd0-133">Vanliga principer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="0cdd0-133">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="0cdd0-134">Hur contoso hanterade enhets hantering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0cdd0-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="0cdd0-135">Mer information om hur du kan hitta en fiktiv men representativ organisation för hantering av mobila enheter med Microsoft 365-molntjänster finns i [Hantera mobila enheter för Contoso](contoso-mdm.md).</span><span class="sxs-lookup"><span data-stu-id="0cdd0-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>
