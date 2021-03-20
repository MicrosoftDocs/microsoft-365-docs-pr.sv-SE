---
title: Översikt över Basic Mobility and Security för Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Använd Basic Mobility and Security för att ange säkerhetsprinciper och åtkomstregler för enheter.
ms.openlocfilehash: e74a5df6d10f8f3fb7b420e428380af97ba75597
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906258"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a><span data-ttu-id="ff69b-103">Översikt över Basic Mobility and Security för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ff69b-103">Overview of Basic Mobility and Security for Microsoft 365</span></span>

<span data-ttu-id="ff69b-104">Du kan hantera och skydda mobila enheter när de är anslutna till din Microsoft 365-organisation med hjälp av Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="ff69b-104">You can manage and secure mobile devices when they're connected to your Microsoft 365 organization by using Basic Mobility and Security.</span></span> <span data-ttu-id="ff69b-105">Mobila enheter som smartphones och surfplattor som används för att komma åt arbets-e-post, kalender, kontakter och dokument spelar en stor roll för att säkerställa att anställda får jobbet gjort när som helst, var som helst.</span><span class="sxs-lookup"><span data-stu-id="ff69b-105">Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere.</span></span> <span data-ttu-id="ff69b-106">Därför är det viktigt att du hjälper till att skydda organisationens information när personer använder enheter.</span><span class="sxs-lookup"><span data-stu-id="ff69b-106">So it’s critical that you help protect your organization's information when people use devices.</span></span> <span data-ttu-id="ff69b-107">Du kan använda Grundläggande rörlighet och säkerhet för att ställa in säkerhetsprinciper och åtkomstregler för enheter, och för att rensa mobila enheter om de försvinner eller blir stulna.</span><span class="sxs-lookup"><span data-stu-id="ff69b-107">You can use Basic Mobility and Security to set device security policies and access rules, and to wipe mobile devices if they’re lost or stolen.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Grundläggande rörlighets- och säkerhetskonfiguration":::

## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="ff69b-109">Vilka typer av enheter kan du hantera?</span><span class="sxs-lookup"><span data-stu-id="ff69b-109">What types of devices can you manage?</span></span>

<span data-ttu-id="ff69b-110">Du kan använda Basic Mobility and Security för att hantera många typer av mobila enheter som Windows Phone, Android, iPhone och iPad.</span><span class="sxs-lookup"><span data-stu-id="ff69b-110">You can use Basic Mobility and Security to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad.</span></span> <span data-ttu-id="ff69b-111">För att hantera mobila enheter som används av personer i din organisation måste varje person ha en tillämplig Microsoft 365-licens och sin enhet måste vara registrerad i Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="ff69b-111">To manage mobile devices used by people in your organization, each person must have an applicable Microsoft 365 license and their device must be enrolled in Basic Mobility and Security.</span></span>

<span data-ttu-id="ff69b-112">Information om vilka stöd för Basic Mobility och Security som stöds för varje typ av enhet [finns i Funktioner för grundläggande rörlighet och säkerhet.](capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="ff69b-112">To see what Basic Mobility and Security supports for each type of device, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>

## <a name="setup-steps-for-basic-mobility-and-security"></a><span data-ttu-id="ff69b-113">Konfigurationssteg för Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="ff69b-113">Setup steps for Basic Mobility and Security</span></span>

<span data-ttu-id="ff69b-114">En global Microsoft 365-administratör måste slutföra följande steg för att aktivera och konfigurera grundläggande rörlighet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="ff69b-114">A Microsoft 365 global admin must complete the following steps to activate and set up Basic Mobility and Security.</span></span> <span data-ttu-id="ff69b-115">Detaljerade instruktioner finns i Konfigurera grundläggande [rörlighet och säkerhet.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="ff69b-115">For detailed steps, follow the guidance in [Set up Basic Mobility and Security](set-up.md).</span></span> 

<span data-ttu-id="ff69b-116">Här följer en sammanfattning av stegen:</span><span class="sxs-lookup"><span data-stu-id="ff69b-116">Here's a summary of the steps:</span></span>

<span data-ttu-id="ff69b-117">**Steg 1:** Aktivera grundläggande rörlighet och säkerhet genom att följa stegen i  [Konfigurera grundläggande rörlighet och säkerhet.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="ff69b-117">**Step 1:** Activate Basic Mobility and Security by following steps in the [Set up Basic Mobility and Security](set-up.md).</span></span>

<span data-ttu-id="ff69b-118">**Steg 2:** Konfigurera grundläggande rörlighet och säkerhet genom att till exempel skapa ett APNs-certifikat för att hantera iOS-enheter och lägga till en DNS-post (Domain Name System) för din domän för att stödja Windows-telefoner.</span><span class="sxs-lookup"><span data-stu-id="ff69b-118">**Step 2:** Set up Basic Mobility and Security by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>

<span data-ttu-id="ff69b-119">**Steg 3:** Skapa enhetsprinciper och använd dem på grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="ff69b-119">**Step 3:** Create device policies and apply them to groups of users.</span></span> <span data-ttu-id="ff69b-120">När du gör det får användarna ett meddelande om registrering på sin enhet, och när registreringen är klar begränsas deras enheter av de principer du har angett för dem.</span><span class="sxs-lookup"><span data-stu-id="ff69b-120">When you do this, your users get an enrollment message on their device, and when they've completed enrollment, their devices are restricted by the policies you've set up for them.</span></span> <span data-ttu-id="ff69b-121">Mer information finns i [Registrera din mobila enhet med grundläggande rörlighet och säkerhet.](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="ff69b-121">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span> 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Principinställningar för grundläggande säkerhet och rörlighet":::

## <a name="device-management-tasks"></a><span data-ttu-id="ff69b-123">Uppgifter för enhetshantering</span><span class="sxs-lookup"><span data-stu-id="ff69b-123">Device management tasks</span></span>

<span data-ttu-id="ff69b-124">När du har konfigurerat Basic Mobility and Security och dina användare har registrerat sina enheter kan du hantera enheterna, blockera åtkomst eller rensa en enhet om det behövs.</span><span class="sxs-lookup"><span data-stu-id="ff69b-124">After you've got Basic Mobility and Security set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if necessary.</span></span> <span data-ttu-id="ff69b-125">Mer information om några vanliga uppgifter för enhetshantering, inklusive var du utför uppgifter, finns i Hantera enheter som är registrerade i Hantering av mobila enheter för [Microsoft 365.](manage-enrolled-devices.md)</span><span class="sxs-lookup"><span data-stu-id="ff69b-125">To learn more about some common device management tasks, including where to complete the tasks, see [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md).</span></span>

## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="ff69b-126">Andra sätt att hantera enheter och appar</span><span class="sxs-lookup"><span data-stu-id="ff69b-126">Other ways to manage devices and apps</span></span>

<span data-ttu-id="ff69b-127">Om du bara behöver hantering av mobilappar (MAM), kanske för personer som uppdaterar arbetsprojekt på sina egna enheter, tillhandahåller Intune ett annat alternativ än att registrera och hantera enheter.</span><span class="sxs-lookup"><span data-stu-id="ff69b-127">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices.</span></span> <span data-ttu-id="ff69b-128">Med en Intune-prenumeration kan du konfigurera MAM-principer med hjälp av Azure-portalen, även om personers enheter inte är registrerade i Intune.</span><span class="sxs-lookup"><span data-stu-id="ff69b-128">An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune.</span></span> <span data-ttu-id="ff69b-129">Mer information finns i Översikt [över principer för programskydd](/mem/intune/apps/app-protection-policy).</span><span class="sxs-lookup"><span data-stu-id="ff69b-129">For more info, see [App protection policies overview](/mem/intune/apps/app-protection-policy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ff69b-130">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="ff69b-130">Related topics</span></span>

[<span data-ttu-id="ff69b-131">Konfigurera grundläggande Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="ff69b-131">Set up Basic Mobility and Security</span></span>](set-up.md)

[<span data-ttu-id="ff69b-132">Registrera din mobila enhet med Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="ff69b-132">Enroll your mobile device using Basic Mobility and Security</span></span>](enroll-your-mobile-device.md)

[<span data-ttu-id="ff69b-133">Hantera enheter som registrerats i Hantering av mobila enheter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ff69b-133">Manage devices enrolled in Mobile Device Management for Microsoft 365</span></span>](manage-enrolled-devices.md)

[<span data-ttu-id="ff69b-134">Få information om enheter som hanteras av Basic Mobility och Security</span><span class="sxs-lookup"><span data-stu-id="ff69b-134">Get details about devices managed by Basic Mobility and Security</span></span>](get-details-about-managed-devices.md)