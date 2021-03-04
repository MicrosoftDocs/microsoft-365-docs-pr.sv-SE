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
description: Innan du kan använda Microsoft 365-tjänster med din enhet kan du behöva registrera den i Basic Mobility and Security för Microsoft 365.
ms.openlocfilehash: 2a9c0bd9faf670d7dca340d3bc4e9f6586bd6b66
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423207"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="c33d3-103">Registrera din mobila enhet med Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="c33d3-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="c33d3-104">Att använda en telefon, surfplatta och andra mobila enheter för att arbeta är ett bra sätt att hålla sig informerad och arbeta med affärsprojekt när du inte är på kontoret.</span><span class="sxs-lookup"><span data-stu-id="c33d3-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="c33d3-105">Innan du kan använda Microsoft 365-tjänster med din enhet kan du behöva registrera den i Basic Mobility and Security för Microsoft 365 med Microsoft Intune-företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="c33d3-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="c33d3-106">Organisationer väljer Basic Mobility and Security så att anställda kan använda sina mobila enheter för säker åtkomst till arbets-e-post, kalendrar och dokument medan verksamheten säkrar viktiga data och uppfyller efterlevnadskraven.</span><span class="sxs-lookup"><span data-stu-id="c33d3-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="c33d3-107">Mer information finns i [Översikt över Basic Mobility och Security för Microsoft 365.](overview.md)</span><span class="sxs-lookup"><span data-stu-id="c33d3-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="c33d3-108">Mer information finns i Vilken [information kan organisationen se när jag registrerar min enhet?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span><span class="sxs-lookup"><span data-stu-id="c33d3-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="c33d3-109">När du registrerar enheten i Basic Mobility and Security för Microsoft 365 kan du behöva konfigurera ett lösenord och ge organisationen där du arbetar möjlighet att rensa enheten.</span><span class="sxs-lookup"><span data-stu-id="c33d3-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="c33d3-110">Rensning av enheten kan utföras från administrationscentret för Microsoft 365, till exempel för att ta bort alla data från enheten om fel lösenord anges för många gånger eller om användningsvillkoren bryts.</span><span class="sxs-lookup"><span data-stu-id="c33d3-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="c33d3-111">Enheter som stöds</span><span class="sxs-lookup"><span data-stu-id="c33d3-111">Supported devices</span></span>

<span data-ttu-id="c33d3-112">Basic Mobility and Security för Microsoft 365 som finns på Intune-tjänsten fungerar med de flesta, men inte alla, mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="c33d3-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="c33d3-113">Följande stöds med Basic Mobility och Security:</span><span class="sxs-lookup"><span data-stu-id="c33d3-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="c33d3-114">iOS 10.0 eller senare</span><span class="sxs-lookup"><span data-stu-id="c33d3-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="c33d3-115">Android 4.4 eller senare</span><span class="sxs-lookup"><span data-stu-id="c33d3-115">Android 4.4 or later</span></span>

- <span data-ttu-id="c33d3-116">Windows 8.1 och Windows 10 (telefon och dator)</span><span class="sxs-lookup"><span data-stu-id="c33d3-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="c33d3-117">Om enheten inte finns med i listan ovan och du behöver använda den med Basic Mobility och Security, kontaktar du din arbets- eller skoladministratör.</span><span class="sxs-lookup"><span data-stu-id="c33d3-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="c33d3-118">Om du har problem med att registrera enheten kan du gå till [Felsöka Basic Mobility and Security.](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="c33d3-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="c33d3-119">Konfigurera din mobila enhet med Intune och Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="c33d3-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="c33d3-120">Intune-företagsportalen gör att en enhet kan hanteras av Microsoft 365 och Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="c33d3-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="c33d3-121">iPhone eller iPad</span><span class="sxs-lookup"><span data-stu-id="c33d3-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="c33d3-122">Du kommer inte att kunna skicka och ta emot e-post förrän du är klar med det här steget.</span><span class="sxs-lookup"><span data-stu-id="c33d3-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="c33d3-123">Gå till Apple App Store och ladda ned och installera Intune-företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="c33d3-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="c33d3-124">Information om hur du ansluter och konfigurerar en iOS-telefon eller iOS-surfplatta med företagsportalen för Office 365 finns i Konfigurera [iOS-enhetsåtkomst till företagets resurser.](https://go.microsoft.com/fwlink/?linkid=875316)</span><span class="sxs-lookup"><span data-stu-id="c33d3-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="c33d3-125">Android-telefon eller -surfplatta</span><span class="sxs-lookup"><span data-stu-id="c33d3-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="c33d3-126">Du kommer inte att kunna skicka och ta emot e-post förrän du är klar med det här steget.</span><span class="sxs-lookup"><span data-stu-id="c33d3-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="c33d3-127">Gå till Google Play-butiken och ladda ned och installera Intune-företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="c33d3-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="c33d3-128">Information om hur du ansluter och konfigurerar din Android-telefon eller -surfplatta med företagsportalen för Microsoft 365 finns i [Registrera enheten med företagsportalen.](https://go.microsoft.com/fwlink/?linkid=875317)</span><span class="sxs-lookup"><span data-stu-id="c33d3-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="c33d3-129">Windows 8.1 och Windows 10</span><span class="sxs-lookup"><span data-stu-id="c33d3-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="c33d3-130">Gå till Microsoft Store och ladda ned och installera Intune-företagsportalen</span><span class="sxs-lookup"><span data-stu-id="c33d3-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="c33d3-131">Om du vill ansluta och konfigurera din Windows-telefon eller dator med företagsportalen för Microsoft 365 kan du gå till Windows enhetsregistrering [i Intune-företagsportalen.](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal)</span><span class="sxs-lookup"><span data-stu-id="c33d3-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="c33d3-132">Hur går jag vidare?</span><span class="sxs-lookup"><span data-stu-id="c33d3-132">What's next?</span></span>

<span data-ttu-id="c33d3-133">När enheten är registrerad i Basic Mobility and Security kan du börja använda Office-appar på enheten för att arbeta med e-post, kalender, kontakter och dokument.</span><span class="sxs-lookup"><span data-stu-id="c33d3-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
