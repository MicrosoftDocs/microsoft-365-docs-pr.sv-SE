---
title: Jämföra olika sätt att blockera åtkomst till Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: Lär dig hur du blockerar åtkomsten till Office 365 när en anställd lämnar organisationen.
ms.openlocfilehash: 3aafef37a43747557ef9a3fcda8ffe0fe3713717
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807248"
---
# <a name="compare-ways-to-block-access-to-office-365"></a><span data-ttu-id="7bc1d-103">Jämföra olika sätt att blockera åtkomst till Office 365</span><span class="sxs-lookup"><span data-stu-id="7bc1d-103">Compare ways to block access to Office 365</span></span>

<span data-ttu-id="7bc1d-p101">När en anställd lämnar organisationen, på egen begäran eller får sparken, ska du blockera deras åtkomst till Office 365. Det kan du göra på några olika sätt.</span><span class="sxs-lookup"><span data-stu-id="7bc1d-p101">When an employee leaves your organization, on good terms or bad, you need to block their access to Office 365. Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="7bc1d-106">**Olika sätt att blockera åtkomst**</span><span class="sxs-lookup"><span data-stu-id="7bc1d-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="7bc1d-107">**Definition**</span><span class="sxs-lookup"><span data-stu-id="7bc1d-107">**Definition**</span></span> <br/> |<span data-ttu-id="7bc1d-108">**Bästa metod**</span><span class="sxs-lookup"><span data-stu-id="7bc1d-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="7bc1d-109">Blockera inloggning</span><span class="sxs-lookup"><span data-stu-id="7bc1d-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="7bc1d-p102">Ett sätt att blockera användare från att komma åt Office 365 är att ändra deras inloggningsstatus till **Inloggning blockerad**. Det gör att de inte kan logga in i Office 365 från sina datorer och mobila enheter, men de kan fortfarande visa tidigare nedladdad eller synkroniserad e-post och dokument. Om du använder Blackberry Enterprise Service kan du inaktivera deras åtkomst där också.  </span><span class="sxs-lookup"><span data-stu-id="7bc1d-p102">One way to block a user from accessing Office 365 is to change their sign-in status to **Sign-in blocked**. This prevents them from signing into Office 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents. If you're using Blackberry Enterprise Service, you can disable their access there as well.  </span></span><br/> |<span data-ttu-id="7bc1d-113">Använd den här metoden när en anställd planerar att lämna organisationen eller planerar att ha en lång ledighet.</span><span class="sxs-lookup"><span data-stu-id="7bc1d-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="7bc1d-114">Återställa användarlösenord</span><span class="sxs-lookup"><span data-stu-id="7bc1d-114">Reset user password</span></span>  <br/> |<span data-ttu-id="7bc1d-p103">Ett annat sätt att hindra användare att få åtkomst till Office 365 är att återställa deras lösenord. Det gör att de inte kan använda sitt konto, men de kan fortfarande visa tidigare nedladdad eller synkroniserad e-post och dokument. Du kan sedan logga in som dem och ändra lösenord till ett eget.</span><span class="sxs-lookup"><span data-stu-id="7bc1d-p103">Another way to prevent a user from accessing Office 365 is to reset their password. This prevents them from using their account though they can still view previously downloaded or synced email and documents. You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="7bc1d-118">Använd den här metoden när en anställd slutar plötsligt och permanent, och du anser att det finns anledning att oroa sig för affärsdata.</span><span class="sxs-lookup"><span data-stu-id="7bc1d-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="7bc1d-119">Ta bort alla tilldelade licenser</span><span class="sxs-lookup"><span data-stu-id="7bc1d-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="7bc1d-120">Ett annat alternativ är att ta bort alla Office 365-licenser som tilldelats till användaren.</span><span class="sxs-lookup"><span data-stu-id="7bc1d-120">Another option is to remove any Office 365 licenses assigned to the user.</span></span> <span data-ttu-id="7bc1d-121">Detta förhindrar att de använder program och tjänster som Office-paketet, Office-program för webben, Yammer och SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7bc1d-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="7bc1d-122">De kan fortfarande logga in, men kan inte använda de här tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="7bc1d-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="7bc1d-123">Använd den här metoden när du anser att användaren inte längre behöver åtkomst till specifika funktioner i Office 365.</span><span class="sxs-lookup"><span data-stu-id="7bc1d-123">Use when you feel this user no longer needs access to specific features in Office 365.</span></span>  <br/> <br> <span data-ttu-id="7bc1d-124">**Viktigt:** När du tar bort en licens tas användarens postlåda bort inom 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="7bc1d-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="7bc1d-125">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="7bc1d-125">Related articles</span></span>

[<span data-ttu-id="7bc1d-126">Ta bort en användare från Office 365</span><span class="sxs-lookup"><span data-stu-id="7bc1d-126">Offboard a user from Office 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="7bc1d-127">Återställa en användares lösenord i Office 365</span><span class="sxs-lookup"><span data-stu-id="7bc1d-127">Reset a user's password in Office 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="7bc1d-128">Tilldela användare licenser i Office 365 för företag</span><span class="sxs-lookup"><span data-stu-id="7bc1d-128">Assign licenses to users in Office 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="7bc1d-129">Ta bort licenser från användare i Office 365 för företag</span><span class="sxs-lookup"><span data-stu-id="7bc1d-129">Remove licenses from users in Office 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

