---
title: Säkra Office-appar på iOS
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du skyddar Office-appar på iOS med Microsoft 365 Business Premium.
ms.openlocfilehash: 197041a4eb9ada65f4b6046d93f2a856cbdfb40d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422117"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="67cdd-103">Säkra Office-appar på iOS</span><span class="sxs-lookup"><span data-stu-id="67cdd-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="67cdd-104">Du kan konfigurera en princip för användaråtkomst som kräver att mobila användare anger en PIN-kod eller ett fingeravtryck när de loggar in, och krypterar även arbetsfiler som lagras på deras enheter.</span><span class="sxs-lookup"><span data-stu-id="67cdd-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="67cdd-105">Prova!</span><span class="sxs-lookup"><span data-stu-id="67cdd-105">Try it!</span></span>

1. <span data-ttu-id="67cdd-106">Logga in på administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="67cdd-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="67cdd-107">Välj **Lägg till** princip under **Principer.**</span><span class="sxs-lookup"><span data-stu-id="67cdd-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="67cdd-108">I fönstret **Lägg till** princip anger du ett namn under **Principnamn** och väljer den principtyp som du vill använda under **Principtyp.**</span><span class="sxs-lookup"><span data-stu-id="67cdd-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="67cdd-109">Aktivera Hantera **hur användare kommer åt Office-filer på mobila** enheter och kontrollera att följande tre inställningar är aktiverat:</span><span class="sxs-lookup"><span data-stu-id="67cdd-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="67cdd-110">**Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program**</span><span class="sxs-lookup"><span data-stu-id="67cdd-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="67cdd-111">**Skydda arbetsfiler om enheter försvinner eller blir stulna**</span><span class="sxs-lookup"><span data-stu-id="67cdd-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="67cdd-112">**Kryptera arbetsfiler**</span><span class="sxs-lookup"><span data-stu-id="67cdd-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="67cdd-113">Under **Filer i de här apparna skyddas** markerar du de Office-program som du vill skydda på mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="67cdd-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="67cdd-114">Under **Vem får de här inställningarna?** är alla användare  valda som standard, men du kan välja Ändra om du vill välja säkerhetsgrupper som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="67cdd-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="67cdd-115">Välj Lägg till för att slutföra **principen.**</span><span class="sxs-lookup"><span data-stu-id="67cdd-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="67cdd-116">Välj Stäng **på sidan** Lägg till **princip.**</span><span class="sxs-lookup"><span data-stu-id="67cdd-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="67cdd-117">På startsidan för administrationscentret bekräftar du att den nya principen har lagts till genom att välja **Principer** och granska principen på **sidan** Principer.</span><span class="sxs-lookup"><span data-stu-id="67cdd-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>