---
title: Jämföra sätt att blockera åtkomst
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
description: Lär dig hur du blockerar åtkomsten till Microsoft 365 när en anställd lämnar organisationen.
ms.openlocfilehash: b913655065d4c57322aee6dc04e53f7a35cf5760
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399440"
---
# <a name="compare-ways-to-block-access"></a><span data-ttu-id="d4cd2-103">Jämföra sätt att blockera åtkomst</span><span class="sxs-lookup"><span data-stu-id="d4cd2-103">Compare ways to block access</span></span>

<span data-ttu-id="d4cd2-104">När en medarbetare lämnar organisationen, på gott villkor eller dåligt, måste du blockera deras åtkomst till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-104">When an employee leaves your organization, on good terms or bad, you need to block their access to Microsoft 365.</span></span> <span data-ttu-id="d4cd2-105">Det kan du göra på några olika sätt.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-105">Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="d4cd2-106">**Olika sätt att blockera åtkomst**</span><span class="sxs-lookup"><span data-stu-id="d4cd2-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="d4cd2-107">**Definition**</span><span class="sxs-lookup"><span data-stu-id="d4cd2-107">**Definition**</span></span> <br/> |<span data-ttu-id="d4cd2-108">**Bästa metod**</span><span class="sxs-lookup"><span data-stu-id="d4cd2-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="d4cd2-109">Blockera inloggning</span><span class="sxs-lookup"><span data-stu-id="d4cd2-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="d4cd2-110">Ett sätt att blockera en användare från att komma åt Microsoft 365 är att ändra sin inloggningsstatus till **Inloggning blockerad**.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-110">One way to block a user from accessing Microsoft 365 is to change their sign-in status to **Sign-in blocked**.</span></span> <span data-ttu-id="d4cd2-111">Detta förhindrar att de loggar in på Microsoft 365 från sina datorer och mobila enheter, även om de fortfarande kan visa tidigare nedladdad eller synkroniserad e-post och dokument.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-111">This prevents them from signing into Microsoft 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="d4cd2-112">Om du använder Blackberry Enterprise Service kan du inaktivera deras åtkomst där också.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-112">If you're using Blackberry Enterprise Service, you can disable their access there as well.</span></span>  <br/> |<span data-ttu-id="d4cd2-113">Använd den här metoden när en anställd planerar att lämna organisationen eller planerar att ha en lång ledighet.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="d4cd2-114">Återställa användarlösenord</span><span class="sxs-lookup"><span data-stu-id="d4cd2-114">Reset user password</span></span>  <br/> |<span data-ttu-id="d4cd2-115">Ett annat sätt att förhindra att en användare kommer åt Microsoft 365 är att återställa sitt lösenord.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-115">Another way to prevent a user from accessing Microsoft 365 is to reset their password.</span></span> <span data-ttu-id="d4cd2-116">Det gör att de inte kan använda sitt konto, men de kan fortfarande visa tidigare nedladdad eller synkroniserad e-post och dokument.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-116">This prevents them from using their account though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="d4cd2-117">Du kan sedan logga in som dem och ändra lösenord till ett eget.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-117">You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="d4cd2-118">Använd den här metoden när en anställd slutar plötsligt och permanent, och du anser att det finns anledning att oroa sig för affärsdata.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="d4cd2-119">Ta bort alla tilldelade licenser</span><span class="sxs-lookup"><span data-stu-id="d4cd2-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="d4cd2-120">Ett annat alternativ är att ta bort alla Microsoft 365-licenser som tilldelats användaren.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-120">Another option is to remove any Microsoft 365 licenses assigned to the user.</span></span> <span data-ttu-id="d4cd2-121">Detta förhindrar att de använder program och tjänster som Office-paketet, Office-program för webben, Yammer och SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="d4cd2-122">De kan fortfarande logga in, men kan inte använda de här tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="d4cd2-123">Använd när du känner att den här användaren inte längre behöver åtkomst till specifika funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-123">Use when you feel this user no longer needs access to specific features in Microsoft 365.</span></span>  <br/> <br> <span data-ttu-id="d4cd2-124">**Viktigt:** När du tar bort en licens tas användarens postlåda bort inom 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="d4cd2-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="d4cd2-125">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="d4cd2-125">Related articles</span></span>

[<span data-ttu-id="d4cd2-126">Offboard en användare från Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d4cd2-126">Offboard a user from Microsoft 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="d4cd2-127">Återställa en användares lösenord i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d4cd2-127">Reset a user's password in Microsoft 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="d4cd2-128">Tilldela licenser till användare i Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="d4cd2-128">Assign licenses to users in Microsoft 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="d4cd2-129">Ta bort licenser från användare i Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="d4cd2-129">Remove licenses from users in Microsoft 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

