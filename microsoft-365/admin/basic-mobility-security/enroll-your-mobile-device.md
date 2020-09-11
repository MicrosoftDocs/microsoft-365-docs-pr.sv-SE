---
title: Registrera din mobila enhet med grundläggande mobilitet och säkerhet
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
description: Innan du kan använda Microsoft 365-tjänster med din enhet kan du behöva registrera den i grundläggande mobilitet och säkerhet för Microsoft 365.
ms.openlocfilehash: e31054621ba44a4d5f08de9b366fa0978b738cd9
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430333"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="64d1d-103">Registrera din mobila enhet med grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="64d1d-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="64d1d-104">Att använda telefon, surfplatta och andra mobila enheter för arbete är ett bra sätt att hålla dig informerad och arbeta med affärs projekt medan du är borta från kontoret.</span><span class="sxs-lookup"><span data-stu-id="64d1d-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="64d1d-105">Innan du kan använda Microsoft 365-tjänster med din enhet kan du behöva registrera den i grundläggande mobilitet och säkerhet för Microsoft 365 med Microsoft Intune företags portalen.</span><span class="sxs-lookup"><span data-stu-id="64d1d-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="64d1d-106">Organisationer väljer grundläggande mobilitet så att de anställda kan använda sina mobila enheter för att säkert komma åt e-post, kalendrar och dokument medan verksamheten skyddar viktiga data och uppfyller deras efterföljandekrav.</span><span class="sxs-lookup"><span data-stu-id="64d1d-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="64d1d-107">Mer information finns i [Översikt över grundläggande mobilitet och säkerhet för Microsoft 365](overview.md).</span><span class="sxs-lookup"><span data-stu-id="64d1d-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="64d1d-108">Mer information finns i [vilken information kan min organisation se när jag registrerar min enhet?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span><span class="sxs-lookup"><span data-stu-id="64d1d-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="64d1d-109">När du registrerar enheten i grundläggande mobilitet och säkerhet för Microsoft 365 kanske du måste konfigurera ett lösen ord, samt tillåta att arbets organisationen rensar enheten.</span><span class="sxs-lookup"><span data-stu-id="64d1d-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="64d1d-110">En enhets rensning kan utföras från administrations centret för Microsoft 365, till exempel för att ta bort alla data från enheten om lösen ordet har angetts felaktigt för många gånger eller om användnings villkoren är felaktiga.</span><span class="sxs-lookup"><span data-stu-id="64d1d-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="64d1d-111">Enheter som stöds</span><span class="sxs-lookup"><span data-stu-id="64d1d-111">Supported devices</span></span>

<span data-ttu-id="64d1d-112">Grundläggande mobilitet och säkerhet för Microsoft 365 som hanteras av Intune-tjänsten fungerar med de flesta, men inte alla, mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="64d1d-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="64d1d-113">Följande stöds med grundläggande mobilitet och säkerhet:</span><span class="sxs-lookup"><span data-stu-id="64d1d-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="64d1d-114">iOS 10,0 eller senare</span><span class="sxs-lookup"><span data-stu-id="64d1d-114">iOS 10.0 or later</span></span>
    
- <span data-ttu-id="64d1d-115">Android 4,4 eller senare</span><span class="sxs-lookup"><span data-stu-id="64d1d-115">Android 4.4 or later</span></span>
    
- <span data-ttu-id="64d1d-116">Windows 8,1 och Windows 10 (telefon och dator)</span><span class="sxs-lookup"><span data-stu-id="64d1d-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>
    
<span data-ttu-id="64d1d-117">Om enheten inte visas ovan, och du behöver använda den med grundläggande mobilitet och säkerhet, kontaktar du din arbets-eller skol administratör.</span><span class="sxs-lookup"><span data-stu-id="64d1d-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP] 
><span data-ttu-id="64d1d-118">Om du har problem med att registrera enheten kan du läsa mer i [Felsöka grundläggande mobilitet och säkerhet](troubleshoot.md).</span><span class="sxs-lookup"><span data-stu-id="64d1d-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="64d1d-119">Konfigurera din mobila enhet med Intune och grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="64d1d-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="64d1d-120">Med Intune företags portalen kan en enhet hanteras av Microsoft 365 och grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="64d1d-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="64d1d-121">iPhone eller iPad</span><span class="sxs-lookup"><span data-stu-id="64d1d-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="64d1d-122">Du kommer inte att kunna skicka och ta emot e-post förrän du slutför det här steget.</span><span class="sxs-lookup"><span data-stu-id="64d1d-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="64d1d-123">Gå till Apple App Store och ladda ned och installera Intune företags portalen.</span><span class="sxs-lookup"><span data-stu-id="64d1d-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="64d1d-124">Om du vill ansluta till och konfigurera din iOS-telefon eller-surfplatta med företags portalen till Office 365 läser du [Konfigurera åtkomst till iOS-enheter till dina företags resurser](https://go.microsoft.com/fwlink/?linkid=875316).</span><span class="sxs-lookup"><span data-stu-id="64d1d-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="64d1d-125">Android-telefon eller-surfplatta</span><span class="sxs-lookup"><span data-stu-id="64d1d-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="64d1d-126">Du kommer inte att kunna skicka och ta emot e-post förrän du slutför det här steget.</span><span class="sxs-lookup"><span data-stu-id="64d1d-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="64d1d-127">Gå till Google Play Store och ladda ned och installera Intune företags Portal.</span><span class="sxs-lookup"><span data-stu-id="64d1d-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="64d1d-128">Information om hur du ansluter och konfigurerar din Android-telefon eller-surfplatta med företags portalen till Microsoft 365 finns i [Registrera enheten med företags Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span><span class="sxs-lookup"><span data-stu-id="64d1d-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="64d1d-129">Windows 8,1 och Windows 10</span><span class="sxs-lookup"><span data-stu-id="64d1d-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="64d1d-130">Gå till Microsoft Store och ladda ned och installera Intune företags Portal</span><span class="sxs-lookup"><span data-stu-id="64d1d-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="64d1d-131">För att ansluta och konfigurera din Windows Phone eller PC med företags portalen till Microsoft 365, se [Windows enhets registrering i Intune-företagsportalsappen](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span><span class="sxs-lookup"><span data-stu-id="64d1d-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="64d1d-132">Hur går jag vidare?</span><span class="sxs-lookup"><span data-stu-id="64d1d-132">What's next?</span></span>

<span data-ttu-id="64d1d-133">När din enhet har registrerats i grundläggande mobilitet kan du börja använda Office-appar på din enhet för att arbeta med e-post, kalender, kontakter och dokument.</span><span class="sxs-lookup"><span data-stu-id="64d1d-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>