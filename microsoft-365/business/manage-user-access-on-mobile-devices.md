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
description: Mer information om principer för skydd som kan hjälpa säker åtkomst till Office apps från mobila enheter.
ms.openlocfilehash: cade979635dd5d4a618537d544a7a76ef64a2963
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071539"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="dd1f2-103">Hantera hur användare kommer åt Office-dokument på mobila enheter</span><span class="sxs-lookup"><span data-stu-id="dd1f2-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="dd1f2-p101">Principinställningar som styr hur användare får åtkomst till Office-filer från sina mobila enheter är **Av** som standard. Vi rekommenderar att du godkänner standardvärdena vid installationen för att skapa programprinciper för alla användare i Android, iOS och Windows 10. Du kan skapa fler principer när installationen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="dd1f2-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="dd1f2-107">Inställningar som styr hur användare kommer åt Office-filer på mobila enheter</span><span class="sxs-lookup"><span data-stu-id="dd1f2-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="dd1f2-108">Följande inställningar är tillgängliga för att bestämma hur användare kan komma åt Office arbetsfiler:</span><span class="sxs-lookup"><span data-stu-id="dd1f2-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dd1f2-109">Inställning</span><span class="sxs-lookup"><span data-stu-id="dd1f2-109">Setting</span></span>  <br/> |<span data-ttu-id="dd1f2-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="dd1f2-110">Description</span></span>  <br/> |
|<span data-ttu-id="dd1f2-111">Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program</span><span class="sxs-lookup"><span data-stu-id="dd1f2-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="dd1f2-112">Om inställningen är **På** måste användare utöver användarnamn och lösenord, tillhandahålla annan autentisering innan de kan använda Office-programmen på sin mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="dd1f2-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="dd1f2-113">Återställ PIN-kod när inloggningen misslyckas så här många gånger</span><span class="sxs-lookup"><span data-stu-id="dd1f2-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="dd1f2-114">Om du vill förhindra att obehöriga användare slumpmässigt gissar en PIN-kod. PIN-koden återställs efter det antal felaktiga försök som du anger.</span><span class="sxs-lookup"><span data-stu-id="dd1f2-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="dd1f2-115">Kräv att användare loggar in igen efter att Office-appar har varit inaktiva</span><span class="sxs-lookup"><span data-stu-id="dd1f2-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="dd1f2-116">Den här inställningen bestämmer hur lång tid användare kan vara inaktiva innan de uppmanas att logga in igen.</span><span class="sxs-lookup"><span data-stu-id="dd1f2-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="dd1f2-117">Neka åtkomst till arbetsfiler på jailbroken eller rotade enheter</span><span class="sxs-lookup"><span data-stu-id="dd1f2-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="dd1f2-p102">Smarta användarna kanske har en jailbroken eller rotad enhet. Det innebär att användaren kan ändra operativsystemet, vilket gör enheten mer utsatt för skadlig programvara. De här enheterna är blockerade när den här inställningen är **På**.  </span><span class="sxs-lookup"><span data-stu-id="dd1f2-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="dd1f2-121">Tillåt inte användare att kopiera innehåll från Office apps till personliga appar</span><span class="sxs-lookup"><span data-stu-id="dd1f2-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="dd1f2-122">När inställningen är **aktiverad**, kan inte användaren kopiera information i en arbetsfil till en personlig fil.</span><span class="sxs-lookup"><span data-stu-id="dd1f2-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="dd1f2-123">Om inställningen är **Inaktiverad**, kan användaren kopiera information från en arbetsfil till en personlig app eller kontoinformation.</span><span class="sxs-lookup"><span data-stu-id="dd1f2-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

