---
title: Hantera hur användare kommer åt Office-dokument på mobila enheter
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Läs mer om skyddsprinciper som gör att du kan hantera hur användare får åtkomst Office appar och arbetsfiler från mobila enheter.
ms.openlocfilehash: a48aa241c9e70cf087da3f1701e859dae7238024
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578396"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="095bf-103">Hantera hur användare kommer åt Office-dokument på mobila enheter</span><span class="sxs-lookup"><span data-stu-id="095bf-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="095bf-104">Den här artikeln gäller för Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="095bf-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="095bf-105">Principinställningar som styr hur användare får åtkomst till Office-filer från sina mobila enheter är **Av** som standard.</span><span class="sxs-lookup"><span data-stu-id="095bf-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="095bf-106">Vi rekommenderar att du godkänner standardvärdena vid installationen för att skapa programprinciper för Android, iOS och Windows 10 som gäller för alla användare.</span><span class="sxs-lookup"><span data-stu-id="095bf-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="095bf-107">Du kan skapa fler principer när installationen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="095bf-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="095bf-108">Inställningar som styr hur användare kommer åt Office-filer på mobila enheter</span><span class="sxs-lookup"><span data-stu-id="095bf-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="095bf-109">Följande inställningar är tillgängliga för att bestämma hur användare kan komma åt Office arbetsfiler:</span><span class="sxs-lookup"><span data-stu-id="095bf-109">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="095bf-110">Inställning</span><span class="sxs-lookup"><span data-stu-id="095bf-110">Setting</span></span>  <br/> |<span data-ttu-id="095bf-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="095bf-111">Description</span></span>  <br/> |
|<span data-ttu-id="095bf-112">Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program</span><span class="sxs-lookup"><span data-stu-id="095bf-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="095bf-113">Om den här inställningen **är På** måste användare utöver användarnamn och lösenord, tillhandahålla annan autentisering innan de kan använda Office på sina mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="095bf-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="095bf-114">Återställ PIN-kod när inloggningen misslyckas så här många gånger</span><span class="sxs-lookup"><span data-stu-id="095bf-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="095bf-115">Om du vill förhindra att obehöriga användare slumpmässigt gissar en PIN-kod. PIN-koden återställs efter det antal felaktiga försök som du anger.</span><span class="sxs-lookup"><span data-stu-id="095bf-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="095bf-116">Kräv att användare loggar in igen efter att Office-appar har varit inaktiva</span><span class="sxs-lookup"><span data-stu-id="095bf-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="095bf-117">Den här inställningen bestämmer hur länge en användare kan vara inaktiv innan de uppmanas att logga in igen.</span><span class="sxs-lookup"><span data-stu-id="095bf-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="095bf-118">Neka åtkomst till arbetsfiler på jailbroken eller rotade enheter</span><span class="sxs-lookup"><span data-stu-id="095bf-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="095bf-119">Smarta användarna kanske har en jailbroken eller rotad enhet.</span><span class="sxs-lookup"><span data-stu-id="095bf-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="095bf-120">Det innebär att användaren kan ändra operativsystemet, vilket kan göra enheten mer känslig för skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="095bf-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="095bf-121">De här enheterna är blockerade när den här inställningen är **På**.</span><span class="sxs-lookup"><span data-stu-id="095bf-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="095bf-122">Tillåt inte användare att kopiera innehåll från en Office till personliga appar</span><span class="sxs-lookup"><span data-stu-id="095bf-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="095bf-123">När inställningen är **På** kan användaren inte kopiera information i en arbetsfil till en personlig fil.</span><span class="sxs-lookup"><span data-stu-id="095bf-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="095bf-124">Om inställningen är **Av** kan användaren kopiera information från en arbetsfil till ett privat program eller personligt konto.</span><span class="sxs-lookup"><span data-stu-id="095bf-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

