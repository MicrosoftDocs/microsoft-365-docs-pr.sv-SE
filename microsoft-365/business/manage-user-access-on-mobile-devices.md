---
title: Hantera hur användare kommer åt Office-dokument på mobila enheter
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Lär dig mer om skyddsprinciper som kan skydda åtkomsten till Office-appar från mobila enheter.
ms.openlocfilehash: c24dae7e0eea777e728ebead9a2abcc3785763dd
ms.sourcegitcommit: 9a057e70637dcfe06d4f729a96c02be989cf9e25
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38633358"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="cd6f1-103">Hantera hur användare kommer åt Office-dokument på mobila enheter</span><span class="sxs-lookup"><span data-stu-id="cd6f1-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="cd6f1-104">Principinställningar som styr hur användare får åtkomst till Office-filer från sina mobila enheter är **Av** som standard.</span><span class="sxs-lookup"><span data-stu-id="cd6f1-104">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="cd6f1-105">Vi rekommenderar att du accepterar standardvärdena under installationen för att skapa användningsprinciper för Android, iOS och Windows 10 som gäller för alla användare.</span><span class="sxs-lookup"><span data-stu-id="cd6f1-105">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="cd6f1-106">Du kan skapa fler principer när installationen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="cd6f1-106">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="cd6f1-107">Inställningar som styr hur användare kommer åt Office-filer på mobila enheter</span><span class="sxs-lookup"><span data-stu-id="cd6f1-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="cd6f1-108">Följande inställningar är tillgängliga för att bestämma hur användare kan komma åt Office arbetsfiler:</span><span class="sxs-lookup"><span data-stu-id="cd6f1-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cd6f1-109">Inställning</span><span class="sxs-lookup"><span data-stu-id="cd6f1-109">Setting</span></span>  <br/> |<span data-ttu-id="cd6f1-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="cd6f1-110">Description</span></span>  <br/> |
|<span data-ttu-id="cd6f1-111">Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program</span><span class="sxs-lookup"><span data-stu-id="cd6f1-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="cd6f1-112">Om den här inställningen är **på**måste användare ange en annan form av autentisering, förutom användarnamn och lösenord, innan de kan använda Office-appar på sin mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="cd6f1-112">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="cd6f1-113">Återställ PIN-kod när inloggningen misslyckas så här många gånger</span><span class="sxs-lookup"><span data-stu-id="cd6f1-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="cd6f1-114">Om du vill förhindra att obehöriga användare slumpmässigt gissar en PIN-kod. PIN-koden återställs efter det antal felaktiga försök som du anger.</span><span class="sxs-lookup"><span data-stu-id="cd6f1-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="cd6f1-115">Kräv att användare loggar in igen efter att Office-appar har varit inaktiva</span><span class="sxs-lookup"><span data-stu-id="cd6f1-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="cd6f1-116">Den här inställningen avgör hur länge en användare kan vara inaktiv innan de uppmanas att logga in igen.</span><span class="sxs-lookup"><span data-stu-id="cd6f1-116">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="cd6f1-117">Neka åtkomst till arbetsfiler på jailbroken eller rotade enheter</span><span class="sxs-lookup"><span data-stu-id="cd6f1-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="cd6f1-118">Smarta användarna kanske har en jailbroken eller rotad enhet.</span><span class="sxs-lookup"><span data-stu-id="cd6f1-118">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="cd6f1-119">Detta innebär att användaren kan ändra operativsystemet, vilket kan göra enheten mer mottaglig för skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="cd6f1-119">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="cd6f1-120">De här enheterna är blockerade när den här inställningen är **På**.</span><span class="sxs-lookup"><span data-stu-id="cd6f1-120">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="cd6f1-121">Tillåt inte att användare kopierar innehåll från Office-appar till personliga appar</span><span class="sxs-lookup"><span data-stu-id="cd6f1-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="cd6f1-122">När inställningen är **på**kan användaren inte kopiera information i en arbetsfil till en personlig fil.</span><span class="sxs-lookup"><span data-stu-id="cd6f1-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="cd6f1-123">Om inställningen är **avstängd**kan användaren kopiera information från en arbetsfil till en personlig app eller ett personligt konto.</span><span class="sxs-lookup"><span data-stu-id="cd6f1-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

