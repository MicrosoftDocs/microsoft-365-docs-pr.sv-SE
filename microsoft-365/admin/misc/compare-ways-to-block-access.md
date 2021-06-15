---
title: Jämföra olika sätt att blockera åtkomst
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: Lär dig hur du blockerar åtkomst Microsoft 365 när en anställd lämnar organisationen.
ms.openlocfilehash: 0c4b210f9802995a23acbf64241997b8924c00c0
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924773"
---
# <a name="compare-ways-to-block-access"></a><span data-ttu-id="c5dc9-103">Jämföra olika sätt att blockera åtkomst</span><span class="sxs-lookup"><span data-stu-id="c5dc9-103">Compare ways to block access</span></span>

<span data-ttu-id="c5dc9-104">När en anställd lämnar organisationen, på egen villkor eller får hjälp, måste du blockera deras åtkomst till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-104">When an employee leaves your organization, on good terms or bad, you need to block their access to Microsoft 365.</span></span> <span data-ttu-id="c5dc9-105">Det kan du göra på några olika sätt.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-105">Here are a few ways you can do that.</span></span>
  
|<span data-ttu-id="c5dc9-106">Olika sätt att blockera åtkomst</span><span class="sxs-lookup"><span data-stu-id="c5dc9-106">Way to block access</span></span>|<span data-ttu-id="c5dc9-107">Definition</span><span class="sxs-lookup"><span data-stu-id="c5dc9-107">Definition</span></span>|<span data-ttu-id="c5dc9-108">Metodtips</span><span class="sxs-lookup"><span data-stu-id="c5dc9-108">Best practice</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c5dc9-109">Blockera inloggning</span><span class="sxs-lookup"><span data-stu-id="c5dc9-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="c5dc9-110">Ett sätt att blockera en användare från Microsoft 365 att ändra deras inloggningsstatus till **Inloggning blockerad**.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-110">One way to block a user from accessing Microsoft 365 is to change their sign-in status to **Sign-in blocked**.</span></span> <span data-ttu-id="c5dc9-111">Det gör att de inte kan logga Microsoft 365 från sina datorer och mobila enheter, men de kan fortfarande visa tidigare nedladdad eller synkroniserad e-post och dokument.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-111">This prevents them from signing into Microsoft 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="c5dc9-112">Om du använder Blackberry Enterprise Service kan du inaktivera deras åtkomst där också.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-112">If you're using Blackberry Enterprise Service, you can disable their access there as well.</span></span>  <br/> |<span data-ttu-id="c5dc9-113">Använd den här metoden när en anställd planerar att lämna organisationen eller planerar att ha en lång ledighet.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="c5dc9-114">Återställa användarlösenord</span><span class="sxs-lookup"><span data-stu-id="c5dc9-114">Reset user password</span></span>  <br/> |<span data-ttu-id="c5dc9-115">Ett annat sätt att hindra en användare från att Microsoft 365 att återställa deras lösenord.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-115">Another way to prevent a user from accessing Microsoft 365 is to reset their password.</span></span> <span data-ttu-id="c5dc9-116">Det gör att de inte kan använda sitt konto, men de kan fortfarande visa tidigare nedladdad eller synkroniserad e-post och dokument.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-116">This prevents them from using their account though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="c5dc9-117">Du kan sedan logga in som dem och ändra lösenord till ett eget.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-117">You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="c5dc9-118">Använd den här metoden när en anställd slutar plötsligt och permanent, och du anser att det finns anledning att oroa sig för affärsdata.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="c5dc9-119">Ta bort alla tilldelade licenser</span><span class="sxs-lookup"><span data-stu-id="c5dc9-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="c5dc9-120">Ett annat alternativ är att ta Microsoft 365 licenser som tilldelats till användaren.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-120">Another option is to remove any Microsoft 365 licenses assigned to the user.</span></span> <span data-ttu-id="c5dc9-121">Det hindrar dem från att använda program och tjänster som Office-paketet, Office-appar för webben, Yammer och SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="c5dc9-122">De kan fortfarande logga in, men kan inte använda de här tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="c5dc9-123">Använd den här när du anser att användaren inte längre behöver åtkomst till specifika funktioner Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-123">Use when you feel this user no longer needs access to specific features in Microsoft 365.</span></span>  <br/> <br> <span data-ttu-id="c5dc9-124">**Viktigt!** När du tar bort en licens tas användarens postlåda bort efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="c5dc9-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="c5dc9-125">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="c5dc9-125">Related articles</span></span>

[<span data-ttu-id="c5dc9-126">Ta bort en användare från Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c5dc9-126">Offboard a user from Microsoft 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="c5dc9-127">Återställa en användares lösenord i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c5dc9-127">Reset a user's password in Microsoft 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="c5dc9-128">Tilldela användare licenser i Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="c5dc9-128">Assign licenses to users in Microsoft 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="c5dc9-129">Ta bort licenser från användare i Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="c5dc9-129">Remove licenses from users in Microsoft 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

