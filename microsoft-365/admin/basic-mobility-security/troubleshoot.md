---
title: Felsöka grundläggande mobilitet och säkerhet
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: Prova de här stegen för att spåra grundläggande problem med mobilitet och säkerhet
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876858"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="ede78-103">Felsöka grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="ede78-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="ede78-104">Om du stöter på problem när du försöker registrera en enhet i grundläggande mobilitet och säkerhet kan du prova stegen här för att spåra problemet.</span><span class="sxs-lookup"><span data-stu-id="ede78-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="ede78-105">Om de allmänna anvisningarna inte löser problemet kan du läsa en av de senare avsnitten med specifika anvisningar för din enhets typ.</span><span class="sxs-lookup"><span data-stu-id="ede78-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="ede78-106">Steg för att pröva först</span><span class="sxs-lookup"><span data-stu-id="ede78-106">Steps to try first</span></span>

<span data-ttu-id="ede78-107">Starta genom att kontrol lera följande:</span><span class="sxs-lookup"><span data-stu-id="ede78-107">To start, check the following:</span></span>

- <span data-ttu-id="ede78-108">Kontrol lera att enheten inte redan har registrerats hos en annan leverantör för hantering av mobila enheter, till exempel Intune.</span><span class="sxs-lookup"><span data-stu-id="ede78-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>

- <span data-ttu-id="ede78-109">Kontrol lera att enheten är inställd på rätt datum och tid.</span><span class="sxs-lookup"><span data-stu-id="ede78-109">Make sure that the device is set to the correct date and time.</span></span>

- <span data-ttu-id="ede78-110">Byt till ett annat WIFI-eller cellulärt nätverk på enheten.</span><span class="sxs-lookup"><span data-stu-id="ede78-110">Switch to a different WIFI or cellular network on the device.</span></span>

- <span data-ttu-id="ede78-111">För Android-eller iOS-enheter avinstallerar och installerar du om Intune-företagsportalsappen på enheten.</span><span class="sxs-lookup"><span data-stu-id="ede78-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="ede78-112">iOS-telefon eller-surfplatta</span><span class="sxs-lookup"><span data-stu-id="ede78-112">iOS phone or tablet</span></span>

- <span data-ttu-id="ede78-113">Se till att du har konfigurerat ett APN-certifikat.</span><span class="sxs-lookup"><span data-stu-id="ede78-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="ede78-114">Mer information finns i [skapa ett APN-certifikat för iOS-enheter](create-an-apns-certificate-for-ios-devices.md).</span><span class="sxs-lookup"><span data-stu-id="ede78-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>

- <span data-ttu-id="ede78-115">I **Inställningar** för   >  **allmän**   >  **profil (eller enhets hantering)** kontrollerar du att det inte redan finns en hanterings profil.</span><span class="sxs-lookup"><span data-stu-id="ede78-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="ede78-116">Om den är det tar du bort den.</span><span class="sxs-lookup"><span data-stu-id="ede78-116">If it is, remove it.</span></span>

- <span data-ttu-id="ede78-117">Om du får fel meddelandet "enheten kunde inte registreras", loggar du in på Microsoft 365 och kontrollerar att en licens som innehåller Exchange Online har tilldelats till den användare som är inloggad på enheten.</span><span class="sxs-lookup"><span data-stu-id="ede78-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="ede78-118">Om du får fel meddelandet "Det gick inte att installera profilen" kan du försöka med något av följande:</span><span class="sxs-lookup"><span data-stu-id="ede78-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>

    - <span data-ttu-id="ede78-119">Kontrol lera att Safari är standard webbläsaren på enheten och att cookies inte är inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="ede78-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>

    - <span data-ttu-id="ede78-120">Starta om enheten och navigera sedan till portal.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ede78-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="ede78-121">Logga in med ditt användar-ID och lösen ord för Microsoft 365 och försök installera profilen manuellt.</span><span class="sxs-lookup"><span data-stu-id="ede78-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>

## <a name="windows-rt"></a><span data-ttu-id="ede78-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="ede78-122">Windows RT</span></span>

- <span data-ttu-id="ede78-123">Kontrol lera att din domän är konfigurerad i Microsoft 365 för att fungera med grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="ede78-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="ede78-124">Mer information finns i [Konfigurera grundläggande mobilitet och säkerhet](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="ede78-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="ede78-125">Se till att användaren väljer **Aktivera**   i stället för att välja **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="ede78-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>

## <a name="windows-10-pc"></a><span data-ttu-id="ede78-126">Windows 10-dator</span><span class="sxs-lookup"><span data-stu-id="ede78-126">Windows 10 PC</span></span>

- <span data-ttu-id="ede78-127">Kontrol lera att din domän är konfigurerad i Microsoft 365 för att fungera med grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="ede78-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="ede78-128">Mer information finns i [Konfigurera grundläggande mobilitet och säkerhet](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="ede78-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="ede78-129">Om du inte har Azure Active Directory Premium bör du kontrol lera att användaren väljer **Registrera bara i enhets hanteringen** i   stället för att välja **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="ede78-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="ede78-130">Android-telefon eller-surfplatta</span><span class="sxs-lookup"><span data-stu-id="ede78-130">Android phone or tablet</span></span>

- <span data-ttu-id="ede78-131">Kontrol lera att enheten kör Android 4,4 eller senare.</span><span class="sxs-lookup"><span data-stu-id="ede78-131">Make sure the device is running Android 4.4 or later.</span></span>

- <span data-ttu-id="ede78-132">Kontrol lera att Chrome är uppdaterat och har angetts som standard webbläsare.</span><span class="sxs-lookup"><span data-stu-id="ede78-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>

- <span data-ttu-id="ede78-133">Om du får fel meddelandet "Det gick inte att registrera den här enheten", loggar du in på Microsoft 365 och kontrollerar att en licens som innehåller Exchange Online har tilldelats till den användare som är inloggad på enheten.</span><span class="sxs-lookup"><span data-stu-id="ede78-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="ede78-134">Kontrol lera meddelande fältet på enheten för att se om eventuella åtgärder för slutanvändare är väntande och om de är det, utför du åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="ede78-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>