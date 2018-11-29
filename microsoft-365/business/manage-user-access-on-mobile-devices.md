---
title: Hantera hur användare kommer åt Office-dokument på mobila enheter
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- 'O365E_BCSSetup4OfficeMobile '
ms.service: o365-administration
localization_priority: Normal
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
ms.openlocfilehash: 75dbe79acccabd851c43259a165e79bfe3c509c0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26983189"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="893bf-103">Hantera hur användare kommer åt Office-dokument på mobila enheter</span><span class="sxs-lookup"><span data-stu-id="893bf-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="893bf-p101">Principinställningar som styr hur användare får åtkomst till Office-filer från sina mobila enheter är **Av** som standard. Vi rekommenderar att du godkänner standardvärdena vid installationen för att skapa programprinciper för alla användare i Android, iOS och Windows 10. Du kan skapa fler principer när installationen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="893bf-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="893bf-107">Inställningar som styr hur användare kommer åt Office-filer på mobila enheter</span><span class="sxs-lookup"><span data-stu-id="893bf-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="893bf-108">Följande inställningar är tillgängliga för att bestämma hur användare kan komma åt Office arbetsfiler:</span><span class="sxs-lookup"><span data-stu-id="893bf-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="893bf-109">Inställning</span><span class="sxs-lookup"><span data-stu-id="893bf-109">Setting</span></span>  <br/> |<span data-ttu-id="893bf-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="893bf-110">Description</span></span>  <br/> |
|<span data-ttu-id="893bf-111">Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program</span><span class="sxs-lookup"><span data-stu-id="893bf-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="893bf-112">Om inställningen är **På** måste användare utöver användarnamn och lösenord, tillhandahålla annan autentisering innan de kan använda Office-programmen på sin mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="893bf-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="893bf-113">Återställ PIN-kod när inloggningen misslyckas så här många gånger</span><span class="sxs-lookup"><span data-stu-id="893bf-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="893bf-114">Om du vill förhindra att obehöriga användare slumpmässigt gissar en PIN-kod. PIN-koden återställs efter det antal felaktiga försök som du anger.</span><span class="sxs-lookup"><span data-stu-id="893bf-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="893bf-115">Kräv att användare loggar in igen efter att Office-appar har varit inaktiva</span><span class="sxs-lookup"><span data-stu-id="893bf-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="893bf-116">Den här inställningen bestämmer hur lång tid användare kan vara inaktiva innan de uppmanas att logga in igen.</span><span class="sxs-lookup"><span data-stu-id="893bf-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="893bf-117">Neka åtkomst till arbetsfiler på jailbroken eller rotade enheter</span><span class="sxs-lookup"><span data-stu-id="893bf-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="893bf-p102">Smarta användarna kanske har en jailbroken eller rotad enhet. Det innebär att användaren kan ändra operativsystemet, vilket gör enheten mer utsatt för skadlig programvara. De här enheterna är blockerade när den här inställningen är **På**.  </span><span class="sxs-lookup"><span data-stu-id="893bf-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="893bf-121">Tillåt användare att kopiera innehåll från Office-program till personliga program</span><span class="sxs-lookup"><span data-stu-id="893bf-121">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="893bf-p103">Vi tillåter inte detta som standard, men om inställningen är **På** kan användaren kopiera information i en arbetsfil till en privat fil. Om inställningen är **Av**, kan användaren inte kopiera information från en arbetsfil till ett privat program eller konto.  </span><span class="sxs-lookup"><span data-stu-id="893bf-p103">We allow this by default, but when the setting is **On**, the user can copy information in a work file to a personal file. If the setting is **Off**, the user can't copy information from a work file to a personal app or personal account.  </span></span><br/> |
   

