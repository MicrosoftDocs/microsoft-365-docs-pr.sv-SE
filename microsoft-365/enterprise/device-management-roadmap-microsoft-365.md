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
ms.openlocfilehash: 1c5a06c75ede11697e2ecf17c47eb035e78dcd27
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694550"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="9151b-104">Enhets hanterings översikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9151b-104">Device management roadmap for Microsoft 365</span></span>


<span data-ttu-id="9151b-105">Microsoft 365 för Enterprise innehåller funktioner för att hantera enheter och deras appar i din organisation.</span><span class="sxs-lookup"><span data-stu-id="9151b-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="9151b-106">Genom att hantera mobila enheter kan du skydda din organisations resurser.</span><span class="sxs-lookup"><span data-stu-id="9151b-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="9151b-107">Det finns två alternativ för enhets hantering.</span><span class="sxs-lookup"><span data-stu-id="9151b-107">There are two options for device management.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="9151b-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9151b-108">Microsoft Intune</span></span>

<span data-ttu-id="9151b-109">Intune ger dig möjlighet att hantera åtkomst till din organisation med MDM (Mobile Device Management) eller MAM (Mobile Application Management).</span><span class="sxs-lookup"><span data-stu-id="9151b-109">Intune gives you options to manage access to your organization using Mobile Device Management (MDM) or Mobile Application Management (MAM).</span></span> <span data-ttu-id="9151b-110">MDM är när användare "registrerar" sina enheter i Intune.</span><span class="sxs-lookup"><span data-stu-id="9151b-110">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="9151b-111">När de har registrerats är de hanterade enheter och kan få alla principer, regler och inställningar som används av din organisation.</span><span class="sxs-lookup"><span data-stu-id="9151b-111">Once enrolled, they are managed devices, and can receive any policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="9151b-112">Du kan till exempel installera specifika appar, skapa en lösen ords princip, installera en VPN-anslutning m.m.</span><span class="sxs-lookup"><span data-stu-id="9151b-112">For example, you can install specifics apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="9151b-113">Användare med egna personliga enheter kanske inte vill registrera sina enheter eller hanteras av Intune och dina principer.</span><span class="sxs-lookup"><span data-stu-id="9151b-113">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your policies.</span></span> <span data-ttu-id="9151b-114">Men du måste ändå skydda organisationens resurser och data.</span><span class="sxs-lookup"><span data-stu-id="9151b-114">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="9151b-115">I det här scenariot kan du skydda dina appar med MAM.</span><span class="sxs-lookup"><span data-stu-id="9151b-115">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="9151b-116">Du kan till exempel använda en MAM policy som kräver att en användare anger en PIN-kod när jag öppnar SharePoint på enheten.</span><span class="sxs-lookup"><span data-stu-id="9151b-116">For example, you can use a MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="9151b-117">Du bestämmer också hur du ska hantera personliga eller företagsägda enheter.</span><span class="sxs-lookup"><span data-stu-id="9151b-117">You'll also determine how you're going to manage personal or organization-owned devices.</span></span> <span data-ttu-id="9151b-118">Du kanske vill behandla enheter på olika sätt, beroende på hur de används.</span><span class="sxs-lookup"><span data-stu-id="9151b-118">You may want to treat devices differently, depending on their use.</span></span> 

<span data-ttu-id="9151b-119">Börja [här](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span><span class="sxs-lookup"><span data-stu-id="9151b-119">Start [here](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="9151b-120">Grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="9151b-120">Basic Mobility and Security</span></span>
 
<span data-ttu-id="9151b-121">Den är inbyggd i Microsoft 365 och hjälper dig att skydda och hantera användares mobila enheter som iPhone, iPad, Android och Windows-telefoner.</span><span class="sxs-lookup"><span data-stu-id="9151b-121">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="9151b-122">Du kan skapa och hantera säkerhets principer för enheter, rensa en enhet och se detaljerade enhets rapporter.</span><span class="sxs-lookup"><span data-stu-id="9151b-122">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span> 

<span data-ttu-id="9151b-123">Börja [här](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span><span class="sxs-lookup"><span data-stu-id="9151b-123">Start [here](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="9151b-124">Rekommendationer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="9151b-124">Identity and device access recommendations</span></span>

<span data-ttu-id="9151b-125">Microsoft tillhandahåller en uppsättning rekommendationer för [identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md) för att säkerställa en säker och produktiv arbetsstyrka.</span><span class="sxs-lookup"><span data-stu-id="9151b-125">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="9151b-126">För enhets åtkomst använder du rekommendationer och inställningar i följande artiklar tillsammans med stegen i den här fasen:</span><span class="sxs-lookup"><span data-stu-id="9151b-126">For device access, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="9151b-127">Krav</span><span class="sxs-lookup"><span data-stu-id="9151b-127">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="9151b-128">Vanliga principer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="9151b-128">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-device-management-for-microsoft-365"></a><span data-ttu-id="9151b-129">Hur Microsoft hanterar enhets hantering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9151b-129">How Microsoft does device management for Microsoft 365</span></span>

<span data-ttu-id="9151b-130">Lär dig hur IT-experter på Microsoft [Hantera enheter med EMS](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8).</span><span class="sxs-lookup"><span data-stu-id="9151b-130">Learn how IT experts at Microsoft [manage devices with EMS](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8).</span></span>

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="9151b-131">Hur contoso hanterade enhets hantering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9151b-131">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="9151b-132">Se hur Contoso Corporation, en fiktiv men är representativ för flera nationella företag, [distribuera sin infrastruktur för mobila enheter](contoso-mdm.md) med Microsoft 365-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="9151b-132">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed their mobile device management infrastructure](contoso-mdm.md) with Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)
