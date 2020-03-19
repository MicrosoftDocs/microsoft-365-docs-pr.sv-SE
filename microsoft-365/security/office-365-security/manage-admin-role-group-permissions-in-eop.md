---
title: Hantera administratörsrollgruppbehörigheter i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Administratörer kan lära sig hur du tilldelar eller tar bort behörigheter i Administrationscentret för Exchange (EAC) i Exchange Online Protection.
ms.openlocfilehash: 01676fab3ed69120a35687d1c6939cb466b8d672
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809360"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="8d3d7-103">Hantera administratörsrollgruppbehörigheter i EOP</span><span class="sxs-lookup"><span data-stu-id="8d3d7-103">Manage admin role group permissions in EOP</span></span>

<span data-ttu-id="8d3d7-104">I Microsoft Exchange Online Protection (EOP) kan du använda Administrationscentret för Exchange (EAC) för att göra en användare till medlem i en rollgrupp eller grupp för att tilldela dem behörighet att utföra specifika administrativa uppgifter.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-104">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks.</span></span> <span data-ttu-id="8d3d7-105">Du kan också ta bort en användare från en rollgrupp eller grupper med hjälp av EAC.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-105">You can also remove a user from a role group or groups by using the EAC.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8d3d7-106">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="8d3d7-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8d3d7-107">Beräknad tid för varje procedur: 5-10 minuter</span><span class="sxs-lookup"><span data-stu-id="8d3d7-107">Estimated time to complete: 5-10 minutes</span></span>

- <span data-ttu-id="8d3d7-108">Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="8d3d7-108">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="8d3d7-109">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-109">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="8d3d7-110">Om du vill se vilka behörigheter du behöver läser du posten "Användare, Kontakter och rollgrupper" i [funktionsbehörigheterna i EOP-avsnittet.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="8d3d7-110">To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="8d3d7-111">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns i [Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="8d3d7-111">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="8d3d7-112">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="8d3d7-112">Having problems?</span></span> <span data-ttu-id="8d3d7-113">Be om hjälp i [exchange onlineskydd](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-113">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="8d3d7-114">Använda EAC för att tilldela medlemmar till administratörsrollgrupper</span><span class="sxs-lookup"><span data-stu-id="8d3d7-114">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="8d3d7-115">Gå](../../media/ITPro-EAC-EditIcon.gif)till **behörighetsadministratörsroller** \> **Admin roles**i EAC, klicka på den rollgrupp som du vill lägga till användaren eller användarna i och klicka sedan på **Redigera** ![redigera.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-115">In the EAC, go to **Permissions** \> **Admin roles**, click the role group that you want to add the user or users to, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="8d3d7-116">Klicka på **Lägg** ![till](../../media/ITPro-EAC-AddIcon.gif)lägg till ikon under Medlemmar .</span><span class="sxs-lookup"><span data-stu-id="8d3d7-116">Under Members, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="8d3d7-117">Fönstret Välj medlemmar visas.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-117">The Select Members window will appear.</span></span>

3. <span data-ttu-id="8d3d7-118">Sök efter den eller de användare som du vill lägga till eller markera dem i listan.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-118">Search for the user or users that you wish to add, or select them from the list.</span></span>

4. <span data-ttu-id="8d3d7-119">När du har valt den eller de användare som du vill lägga till klickar du på **Lägg till**och sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-119">When you have selected the user or users that you want to add, click **Add**, and then click **OK**.</span></span> <span data-ttu-id="8d3d7-120">Fönstret Välj medlemmar stängs.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-120">The Select Members window will close.</span></span>

5. <span data-ttu-id="8d3d7-121">Du ser att användaren har lagts till i **fönstret Medlemmar.**</span><span class="sxs-lookup"><span data-stu-id="8d3d7-121">You will see that the user has been added to the **Members** pane.</span></span> <span data-ttu-id="8d3d7-122">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-122">Click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8d3d7-123">Användare kan behöva logga ut och logga in igen för att se ändringen av sina administrativa rättigheter när du har lagt till eller tagit bort medlemmar från rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-123">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="8d3d7-124">Använda EAC för att ta bort medlemmar från administratörsrollgrupper</span><span class="sxs-lookup"><span data-stu-id="8d3d7-124">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="8d3d7-125">Gå till **Administratörsroller** \> **Admin Roles**för Behörigheter i EAC, klicka på den rollgrupp som du vill ta](../../media/ITPro-EAC-EditIcon.gif)bort en användare eller användare från och klicka sedan på **Redigera** ![redigera.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-125">In the EAC, go to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="8d3d7-126">Under Medlemmar väljer du den eller de användare som](../../media/ITPro-EAC-RemoveIcon.gif)du vill ta bort och klickar på Ta **bort** ![ta bort .</span><span class="sxs-lookup"><span data-stu-id="8d3d7-126">Under Members, select the user or users that you want to remove and click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="8d3d7-127">Klicka på **Spara** om du vill spara ändringen i rollgruppen och gå tillbaka till sidan **Administratörsroller.**</span><span class="sxs-lookup"><span data-stu-id="8d3d7-127">Click **Save** to save the change to the role group and return to the **Admin Roles** page.</span></span> <span data-ttu-id="8d3d7-128">Kontrollera att du har tagit bort användaren från administratörsrollgruppen genom att se till att medlemmen inte längre visas under Medlemmar i informationsfönstret för den valda rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-128">To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8d3d7-129">Användare kan behöva logga ut och logga in igen för att se ändringen av sina administrativa rättigheter när du har lagt till eller tagit bort medlemmar från rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-129">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="8d3d7-130">Mer information</span><span class="sxs-lookup"><span data-stu-id="8d3d7-130">For more information</span></span>

[<span data-ttu-id="8d3d7-131">Funktionsbehörigheter i EOP</span><span class="sxs-lookup"><span data-stu-id="8d3d7-131">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
