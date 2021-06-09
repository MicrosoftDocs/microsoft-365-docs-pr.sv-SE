---
title: Registrera din mobila enhet med Basic Mobility and Security
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
description: Innan du kan Microsoft 365 med din enhet kan du behöva registrera den i Basic Mobility and Security för Microsoft 365.
ms.openlocfilehash: 2ad0aac331969696bbf53d0b06c18ee5c0ee90f6
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706172"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="08082-103">Registrera din mobila enhet med Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="08082-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="08082-104">Om du använder en telefon, surfplatta eller andra mobila enheter för att arbeta är det enkelt att hålla sig informerad och arbeta med affärsprojekt när du inte är på kontoret.</span><span class="sxs-lookup"><span data-stu-id="08082-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="08082-105">Innan du kan Microsoft 365 med din enhet kan du behöva registrera den i Basic Mobility and Security för att Microsoft 365 använda Microsoft Intune Företagsportal.</span><span class="sxs-lookup"><span data-stu-id="08082-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="08082-106">Organisationer väljer Grundläggande rörlighet och säkerhet så att anställda kan använda sina mobila enheter för att säkert komma åt arbetse-post, kalendrar och dokument samtidigt som verksamheten skyddar viktiga data och uppfyller deras efterlevnadskrav.</span><span class="sxs-lookup"><span data-stu-id="08082-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="08082-107">Mer information finns i [Översikt över Grundläggande rörlighet och säkerhet för Microsoft 365.](overview.md)</span><span class="sxs-lookup"><span data-stu-id="08082-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="08082-108">Mer information finns i [Vilken information kan min organisation se när jag registrerar min enhet?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span><span class="sxs-lookup"><span data-stu-id="08082-108">For more info, see [What information can my organization see when I enroll my device?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="08082-109">När du registrerar enheten i Basic Mobility and Security för Microsoft 365 kan du behöva konfigurera ett lösenord och ge din arbetsorganisation möjlighet att rensa enheten.</span><span class="sxs-lookup"><span data-stu-id="08082-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="08082-110">Rensning av enheten kan till exempel utföras från administrationscentret i Microsoft 365 för att ta bort alla data från enheten om fel lösenord anges för många gånger eller om användningsvillkoren bryts.</span><span class="sxs-lookup"><span data-stu-id="08082-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="08082-111">Enheter som stöds</span><span class="sxs-lookup"><span data-stu-id="08082-111">Supported devices</span></span>

<span data-ttu-id="08082-112">Basic Mobility and Security Microsoft 365 hos Intune-tjänsten fungerar med de flesta, men inte alla, mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="08082-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="08082-113">Följande stöds med Basic Mobility och Security:</span><span class="sxs-lookup"><span data-stu-id="08082-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="08082-114">iOS 10.0 eller senare</span><span class="sxs-lookup"><span data-stu-id="08082-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="08082-115">Android 4.4 eller senare</span><span class="sxs-lookup"><span data-stu-id="08082-115">Android 4.4 or later</span></span>

- <span data-ttu-id="08082-116">Windows 8.1 och Windows 10 (Telefon och PC)</span><span class="sxs-lookup"><span data-stu-id="08082-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="08082-117">Om enheten inte finns med i listan ovan och du behöver använda den med Basic Mobility and Security kontaktar du din arbets- eller skoladministratör.</span><span class="sxs-lookup"><span data-stu-id="08082-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="08082-118">Om du har problem med att registrera din enhet kan du gå till [Felsöka grundläggande rörlighet och säkerhet.](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="08082-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="08082-119">Konfigurera din mobila enhet med Intune och Enkel rörlighet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="08082-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="08082-120">Med Intune-företagsportal enhet hanteras en enhet av grundläggande Microsoft 365 och grundläggande rörlighet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="08082-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="08082-121">iPhone eller iPad</span><span class="sxs-lookup"><span data-stu-id="08082-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="08082-122">Du kan inte skicka och ta emot e-post förrän du är klar med det här steget.</span><span class="sxs-lookup"><span data-stu-id="08082-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="08082-123">Gå till Apple App Store och ladda ned och installera Intune-företagsportal.</span><span class="sxs-lookup"><span data-stu-id="08082-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="08082-124">Information om hur du ansluter och konfigurerar din iOS-telefon eller iOS-surfplatta med företagsportalen för Office 365 finns i Konfigurera åtkomst till företagets resurser på [iOS-enheter.](/mem/intune/user-help/enroll-your-device-in-intune-ios)</span><span class="sxs-lookup"><span data-stu-id="08082-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](/mem/intune/user-help/enroll-your-device-in-intune-ios).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="08082-125">Android-telefon eller -surfplatta</span><span class="sxs-lookup"><span data-stu-id="08082-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="08082-126">Du kan inte skicka och ta emot e-post förrän du är klar med det här steget.</span><span class="sxs-lookup"><span data-stu-id="08082-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="08082-127">Gå till Google Play-butiken och ladda ned och installera Intune-företagsportal.</span><span class="sxs-lookup"><span data-stu-id="08082-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="08082-128">Information om hur du ansluter och konfigurerar din android-telefon eller -surfplatta med företagsportalen för Microsoft 365 finns i Registrera din [enhet med Företagsportal](/mem/intune/user-help/enroll-device-android-company-portal).</span><span class="sxs-lookup"><span data-stu-id="08082-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="08082-129">Windows 8.1 och Windows 10</span><span class="sxs-lookup"><span data-stu-id="08082-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="08082-130">Gå till Microsoft Store och ladda ned och installera Intune-företagsportal</span><span class="sxs-lookup"><span data-stu-id="08082-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="08082-131">Om du vill ansluta och Windows din telefon eller dator med företagsportalen för Microsoft 365 kan du Windows [enhetsregistrering i Intune-företagsportal](/intune-user-help/windows-enrollment-company-portal).</span><span class="sxs-lookup"><span data-stu-id="08082-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="08082-132">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="08082-132">Next steps</span></span>

<span data-ttu-id="08082-133">När enheten har registrerats för grundläggande rörlighet och säkerhet kan du börja använda Office-appar på din enhet för att arbeta med e-post, kalender, kontakter och dokument.</span><span class="sxs-lookup"><span data-stu-id="08082-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>