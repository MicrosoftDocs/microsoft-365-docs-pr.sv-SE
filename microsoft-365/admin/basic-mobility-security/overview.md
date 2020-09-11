---
title: Översikt över grundläggande mobilitet och säkerhet för Microsoft 365
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
description: Använd grundläggande mobilitet och säkerhet för att ange säkerhets principer och åtkomst regler för enheter.
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430321"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a><span data-ttu-id="2dad4-103">Översikt över grundläggande mobilitet och säkerhet för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2dad4-103">Overview of Basic Mobility and Security for Microsoft 365</span></span>

<span data-ttu-id="2dad4-104">Du kan hantera och skydda mobila enheter när de är anslutna till din Microsoft 365-organisation med grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="2dad4-104">You can manage and secure mobile devices when they're connected to your Microsoft 365 organization by using Basic Mobility and Security.</span></span> <span data-ttu-id="2dad4-105">Mobila enheter som smartphones och surfplattor som används för att komma åt e-post, kalender, kontakter och dokument spelar en stor del för att se till att anställda får jobbet gjort när som helst.</span><span class="sxs-lookup"><span data-stu-id="2dad4-105">Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere.</span></span> <span data-ttu-id="2dad4-106">Så det är viktigt att du skyddar organisationens information när personer använder enheter.</span><span class="sxs-lookup"><span data-stu-id="2dad4-106">So it’s critical that you help protect your organization's information when people use devices.</span></span> <span data-ttu-id="2dad4-107">Du kan använda grundläggande mobilitet och säkerhet för att ange säkerhets principer och åtkomst regler för enheter och för att rensa mobila enheter om de är förlorade eller stulna.</span><span class="sxs-lookup"><span data-stu-id="2dad4-107">You can use Basic Mobility and Security to set device security policies and access rules, and to wipe mobile devices if they’re lost or stolen.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Grundläggande mobilitet och säkerhets inställningar":::

## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="2dad4-109">Vilka typer av enheter kan du hantera?</span><span class="sxs-lookup"><span data-stu-id="2dad4-109">What types of devices can you manage?</span></span>

<span data-ttu-id="2dad4-110">Du kan använda grundläggande mobilitet och säkerhet för att hantera många typer av mobila enheter som Windows Phone, Android, iPhone och iPad.</span><span class="sxs-lookup"><span data-stu-id="2dad4-110">You can use Basic Mobility and Security to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad.</span></span> <span data-ttu-id="2dad4-111">För att hantera mobila enheter som används av personer i organisationen måste varje person ha en giltig Microsoft 365-licens och deras enheter måste vara registrerade i grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="2dad4-111">To manage mobile devices used by people in your organization, each person must have an applicable Microsoft 365 license and their device must be enrolled in Basic Mobility and Security.</span></span>

<span data-ttu-id="2dad4-112">Om du vill se vilken grundläggande mobilitet och säkerhet som stöds för varje typ av enhet kan du läsa mer i [grundläggande mobilitet och säkerhet](capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="2dad4-112">To see what Basic Mobility and Security supports for each type of device, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>

## <a name="setup-steps-for-basic-mobility-and-security"></a><span data-ttu-id="2dad4-113">Konfigurations steg för grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="2dad4-113">Setup steps for Basic Mobility and Security</span></span>

<span data-ttu-id="2dad4-114">En global administratör för Microsoft 365 måste utföra följande steg för att aktivera och konfigurera grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="2dad4-114">A Microsoft 365 global admin must complete the following steps to activate and set up Basic Mobility and Security.</span></span> <span data-ttu-id="2dad4-115">Detaljerade anvisningar finns i [Konfigurera grundläggande mobilitet och säkerhet](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="2dad4-115">For detailed steps, follow the guidance in [Set up Basic Mobility and Security](set-up.md).</span></span> 

<span data-ttu-id="2dad4-116">Här är en sammanfattning av stegen:</span><span class="sxs-lookup"><span data-stu-id="2dad4-116">Here's a summary of the steps:</span></span>

<span data-ttu-id="2dad4-117">**Steg 1:** Aktivera grundläggande mobilitet och säkerhets inställningar genom att följa stegen i [installera grundläggande mobilitet och säkerhet](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="2dad4-117">**Step 1:** Activate Basic Mobility and Security by following steps in the [Set up Basic Mobility and Security](set-up.md).</span></span>

<span data-ttu-id="2dad4-118">**Steg 2:** Konfigurera grundläggande mobilitet och säkerhet genom att till exempel skapa ett APN-certifikat för att hantera iOS-enheter och lägga till en DNS-post (Domain Name System) för din domän för att stödja Windows-telefoner.</span><span class="sxs-lookup"><span data-stu-id="2dad4-118">**Step 2:** Set up Basic Mobility and Security by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>

<span data-ttu-id="2dad4-119">**Steg 3:** Skapa enhets principer och Använd dem för grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="2dad4-119">**Step 3:** Create device policies and apply them to groups of users.</span></span> <span data-ttu-id="2dad4-120">När du gör det får dina användare ett registrerings meddelande på sina enheter och när de har genomgått registrering begränsas deras enheter av de principer som du har angett för dem.</span><span class="sxs-lookup"><span data-stu-id="2dad4-120">When you do this, your users get an enrollment message on their device, and when they've completed enrollment, their devices are restricted by the policies you've set up for them.</span></span> <span data-ttu-id="2dad4-121">Mer information finns i [Registrera din mobila enhet med grundläggande mobilitet och säkerhet](enroll-your-mobile-device.md).</span><span class="sxs-lookup"><span data-stu-id="2dad4-121">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span> 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundläggande principer för säkerhet och mobilitet":::

## <a name="device-management-tasks"></a><span data-ttu-id="2dad4-123">Enhets hanterings uppgifter</span><span class="sxs-lookup"><span data-stu-id="2dad4-123">Device management tasks</span></span>

<span data-ttu-id="2dad4-124">Efter att du har grundläggande mobilitet och säkerhets inställningar och användarna har registrerat sina enheter kan du hantera enheter, blockera åtkomst eller rensa en enhet om det behövs.</span><span class="sxs-lookup"><span data-stu-id="2dad4-124">After you've got Basic Mobility and Security set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if necessary.</span></span> <span data-ttu-id="2dad4-125">Om du vill veta mer om några vanliga enhets hanterings uppgifter, till exempel var du ska utföra åtgärderna, läser du [Hantera enheter som är registrerade i hantering för mobila enheter för Microsoft 365](manage-enrolled-devices.md).</span><span class="sxs-lookup"><span data-stu-id="2dad4-125">To learn more about some common device management tasks, including where to complete the tasks, see [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md).</span></span>

## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="2dad4-126">Andra sätt att hantera enheter och appar</span><span class="sxs-lookup"><span data-stu-id="2dad4-126">Other ways to manage devices and apps</span></span>

<span data-ttu-id="2dad4-127">Om du bara behöver hantering av mobil program (MAM), till exempel för personer som uppdaterar arbets projekt på sina egna enheter, ger Intune ett annat alternativ förutom att registrera och hantera enheter.</span><span class="sxs-lookup"><span data-stu-id="2dad4-127">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices.</span></span> <span data-ttu-id="2dad4-128">Med en Intune-prenumeration kan du konfigurera MAM policys med Azure-portalen, även om personers enheter inte är registrerade i Intune.</span><span class="sxs-lookup"><span data-stu-id="2dad4-128">An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune.</span></span> <span data-ttu-id="2dad4-129">Mer information finns i [Översikt över program skydds principer](https://go.microsoft.com/fwlink/?LinkId=2132517).</span><span class="sxs-lookup"><span data-stu-id="2dad4-129">For more info, see [App protection policies overview](https://go.microsoft.com/fwlink/?LinkId=2132517).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2dad4-130">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2dad4-130">Related topics</span></span>

[<span data-ttu-id="2dad4-131">Konfigurera grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="2dad4-131">Set up Basic Mobility and Security</span></span>](set-up.md)

[<span data-ttu-id="2dad4-132">Registrera din mobila enhet med grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="2dad4-132">Enroll your mobile device using Basic Mobility and Security</span></span>](enroll-your-mobile-device.md)

[<span data-ttu-id="2dad4-133">Hantera enheter som är registrerade i hantering av mobila enheter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2dad4-133">Manage devices enrolled in Mobile Device Management for Microsoft 365</span></span>](manage-enrolled-devices.md)

[<span data-ttu-id="2dad4-134">Få information om enheter som hanteras av grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="2dad4-134">Get details about devices managed by Basic Mobility and Security</span></span>](get-details-about-managed-devices.md)