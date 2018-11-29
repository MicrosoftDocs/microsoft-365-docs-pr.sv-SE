---
title: Skydda Windows 10-enheter
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 'Mer information om standard och andra inställningar för att skydda Windows 10 enheter. '
ms.openlocfilehash: 0bdf6a56d880cb84f4a4f50550539d97c006ba49
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26983659"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="c4308-103">Skydda Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="c4308-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="c4308-p101">De inställningar som du konfigurerar här är en del av standardprincipen för Windows 10-enheter. Alla användare som ansluter en Windows 10-enhet, inklusive mobila enheter och datorer, genom att logga in med sitt arbetskonto får automatiskt de här inställningarna. Vi rekommenderar att du godkänner standardprincipen under installationen och senare lägger till principer som är riktad mot särskilda grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="c4308-p101">The settings that you configure here are part of the default device policy for Windows 10. All users that connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account, will automatically receive these settings. We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="c4308-107">Inställningar som skyddar Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="c4308-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="c4308-p102">Som standard är alla inställningar **På**. Följande inställningar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="c4308-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c4308-110">Inställning</span><span class="sxs-lookup"><span data-stu-id="c4308-110">Setting</span></span>  <br/> |<span data-ttu-id="c4308-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c4308-111">Description</span></span>  <br/> |
|<span data-ttu-id="c4308-112">Skydda PC-datorer mot virus och andra hot med Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="c4308-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="c4308-113">Kräver att antivirusprogrammet Windows Defender är aktiverat för att skydda datorer från fara vid uppkoppling till internet.</span><span class="sxs-lookup"><span data-stu-id="c4308-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="c4308-114">Skydda datorer från webbaserade hot i Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c4308-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="c4308-115">Aktiverar inställningarna Microsoft i Edge som hjälper till att skydda användare från skadliga webbplatser och nedladdningar.</span><span class="sxs-lookup"><span data-stu-id="c4308-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="c4308-116">Stäng av enhetens skärm efter en viss tids inaktivitet</span><span class="sxs-lookup"><span data-stu-id="c4308-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="c4308-p103">Säkerställer att företagsdata skyddas om en användare är inaktiv. En användare som befinner sig på en offentlig plats, till exempel ett café, kan göra ett ärende eller låter sig distraheras för ett ögonblick, vilket gör att obehöriga kan få tillgång till enheten. Med den här inställningen kan du bestämma hur länge användaren kan vara inaktiv innan skärmen stängs av.</span><span class="sxs-lookup"><span data-stu-id="c4308-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="c4308-120">Tillåt användare att hämta appar från Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="c4308-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="c4308-p104">Låter användare ladda ned och installera appar från Microsoft Store. Appar inbegriper allt från spel till produktivitetsverktyg, så vi lämnar den här inställningen **På**, men du kan inaktivera den för extra säkerhet.  </span><span class="sxs-lookup"><span data-stu-id="c4308-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="c4308-123">Tillåt användare att använda Cortana</span><span class="sxs-lookup"><span data-stu-id="c4308-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="c4308-p105">Cortana kan vara mycket användbar! Hon kan aktivera eller inaktivera inställningar åt dig, ge vägbeskrivningar och kontrollera att du håller avtalade tider, så vi lämnar inställningen **På** som standard.  </span><span class="sxs-lookup"><span data-stu-id="c4308-p105">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="c4308-126">Tillåt användare att ta emot Windows-tips och reklam från Microsoft</span><span class="sxs-lookup"><span data-stu-id="c4308-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="c4308-127">Windows-tips kan vara praktiskt eftersom de informerar användare när nya funktioner blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="c4308-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="c4308-128">Håll Windows 10-enheter uppdaterade automatiskt</span><span class="sxs-lookup"><span data-stu-id="c4308-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="c4308-129">Säkerställer att Windows 10-enheter automatiskt får de senaste uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="c4308-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

