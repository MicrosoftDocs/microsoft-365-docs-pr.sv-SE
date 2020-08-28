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
description: Lär dig hur du konfigurerar inställningarna för den standard enhets princip som en Windows 10-enhet kommer att få när du loggar in på sitt arbets-eller skol konto.
ms.openlocfilehash: 85448507835b6310ca4136849be6a40caf6bb919
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289086"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="7c864-103">Skydda Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="7c864-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="7c864-104">Den här artikeln gäller Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="7c864-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="7c864-105">De inställningar som du konfigurerar här är en del av standardprincipen för Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="7c864-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="7c864-106">Alla användare som ansluter en Windows 10-enhet, inklusive mobila enheter och datorer, genom att logga in med sitt arbets konto får automatiskt dessa inställningar.</span><span class="sxs-lookup"><span data-stu-id="7c864-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="7c864-107">Vi rekommenderar att du godkänner standardprincipen under installationen och senare lägger till principer som är riktad mot särskilda grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="7c864-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="7c864-108">Inställningar som skyddar Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="7c864-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="7c864-p102">Som standard är alla inställningar **På**. Följande inställningar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="7c864-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7c864-111">Inställning</span><span class="sxs-lookup"><span data-stu-id="7c864-111">Setting</span></span>  <br/> |<span data-ttu-id="7c864-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7c864-112">Description</span></span>  <br/> |
|<span data-ttu-id="7c864-113">Skydda PC-datorer mot virus och andra hot med Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="7c864-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="7c864-114">Kräver att antivirusprogrammet Windows Defender är aktiverat för att skydda datorer från fara vid uppkoppling till internet.</span><span class="sxs-lookup"><span data-stu-id="7c864-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="7c864-115">Skydda datorer från webbaserade hot i Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7c864-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="7c864-116">Aktiverar inställningarna Microsoft i Edge som hjälper till att skydda användare från skadliga webbplatser och nedladdningar.</span><span class="sxs-lookup"><span data-stu-id="7c864-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="7c864-117">Skydda filer och mappar på PC-datorer från obehörig åtkomst med BitLocker</span><span class="sxs-lookup"><span data-stu-id="7c864-117">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="7c864-118">BitLocker skyddar data genom att kryptera datorhårddiskar samt skyddar mot exponering av data om en dator försvinner eller blir stulen.</span><span class="sxs-lookup"><span data-stu-id="7c864-118">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="7c864-119">Mer information finns i [vanliga frågor och svar om BitLocker](https://go.microsoft.com/fwlink/?linkid=871000).</span><span class="sxs-lookup"><span data-stu-id="7c864-119">For more information, see [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000).</span></span>  <br/> |
|<span data-ttu-id="7c864-120">Stäng av enhetens skärm efter en viss tids inaktivitet</span><span class="sxs-lookup"><span data-stu-id="7c864-120">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="7c864-p104">Säkerställer att företagsdata skyddas om en användare är inaktiv. En användare som befinner sig på en offentlig plats, till exempel ett café, kan göra ett ärende eller låter sig distraheras för ett ögonblick, vilket gör att obehöriga kan få tillgång till enheten. Med den här inställningen kan du bestämma hur länge användaren kan vara inaktiv innan skärmen stängs av.</span><span class="sxs-lookup"><span data-stu-id="7c864-p104">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|