---
title: Skydda Windows 10-enheter
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Läs mer om hur du konfigurerar inställningarna för standardenhetsprincipen som alla Windows 10-enheter får när de loggar in på sitt arbets- eller skolkonto.
ms.openlocfilehash: 03ae86861ddb0cb83cd39b7834f19e01bf3e99e2
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470636"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="76ddf-103">Skydda Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="76ddf-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="76ddf-104">Den här artikeln gäller Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="76ddf-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="76ddf-105">De inställningar som du konfigurerar här är en del av standardprincipen för Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="76ddf-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="76ddf-106">Alla användare som ansluter en Windows 10-enhet, inklusive mobila enheter och datorer, genom att logga in med sitt arbetskonto får automatiskt dessa inställningar.</span><span class="sxs-lookup"><span data-stu-id="76ddf-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="76ddf-107">Vi rekommenderar att du godkänner standardprincipen under installationen och senare lägger till principer som är riktad mot särskilda grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="76ddf-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="76ddf-108">Inställningar som skyddar Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="76ddf-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="76ddf-p102">Som standard är alla inställningar **På**. Följande inställningar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="76ddf-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="76ddf-111">Inställning</span><span class="sxs-lookup"><span data-stu-id="76ddf-111">Setting</span></span>  <br/> |<span data-ttu-id="76ddf-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="76ddf-112">Description</span></span>  <br/> |
|<span data-ttu-id="76ddf-113">Skydda PC-datorer mot virus och andra hot med Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="76ddf-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="76ddf-114">Kräver att antivirusprogrammet Windows Defender är aktiverat för att skydda datorer från fara vid uppkoppling till internet.</span><span class="sxs-lookup"><span data-stu-id="76ddf-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="76ddf-115">Skydda datorer från webbaserade hot i Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="76ddf-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="76ddf-116">Aktiverar inställningarna Microsoft i Edge som hjälper till att skydda användare från skadliga webbplatser och nedladdningar.</span><span class="sxs-lookup"><span data-stu-id="76ddf-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="76ddf-117">Stäng av enhetens skärm efter en viss tids inaktivitet</span><span class="sxs-lookup"><span data-stu-id="76ddf-117">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="76ddf-p103">Säkerställer att företagsdata skyddas om en användare är inaktiv. En användare som befinner sig på en offentlig plats, till exempel ett café, kan göra ett ärende eller låter sig distraheras för ett ögonblick, vilket gör att obehöriga kan få tillgång till enheten. Med den här inställningen kan du bestämma hur länge användaren kan vara inaktiv innan skärmen stängs av.</span><span class="sxs-lookup"><span data-stu-id="76ddf-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="76ddf-121">Tillåt användare att hämta appar från Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="76ddf-121">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="76ddf-p104">Låter användare ladda ned och installera appar från Microsoft Store. Appar inbegriper allt från spel till produktivitetsverktyg, så vi lämnar den här inställningen **På**, men du kan inaktivera den för extra säkerhet.  </span><span class="sxs-lookup"><span data-stu-id="76ddf-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="76ddf-124">Tillåt användare att använda Cortana</span><span class="sxs-lookup"><span data-stu-id="76ddf-124">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="76ddf-125">Cortana kan vara mycket användbar!</span><span class="sxs-lookup"><span data-stu-id="76ddf-125">Cortana can be very helpful!</span></span> <span data-ttu-id="76ddf-126">Cortana kan aktivera eller inaktivera inställningar åt dig, ge vägbeskrivningar och se till att du är i tid för avtalade tider, så vi behåller den här inställningen **På** som standard.</span><span class="sxs-lookup"><span data-stu-id="76ddf-126">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="76ddf-127">Tillåt användare att ta emot Windows-tips och reklam från Microsoft</span><span class="sxs-lookup"><span data-stu-id="76ddf-127">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="76ddf-128">Windows-tips kan vara praktiskt eftersom de informerar användare när nya funktioner blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="76ddf-128">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="76ddf-129">Håll Windows 10-enheter uppdaterade automatiskt</span><span class="sxs-lookup"><span data-stu-id="76ddf-129">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="76ddf-130">Säkerställer att Windows 10-enheter automatiskt får de senaste uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="76ddf-130">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

