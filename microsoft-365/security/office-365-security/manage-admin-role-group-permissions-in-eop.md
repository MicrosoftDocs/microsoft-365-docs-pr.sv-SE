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
# <a name="manage-admin-role-group-permissions-in-eop"></a>Hantera administratörsrollgruppbehörigheter i EOP

I Microsoft Exchange Online Protection (EOP) kan du använda Administrationscentret för Exchange (EAC) för att göra en användare till medlem i en rollgrupp eller grupp för att tilldela dem behörighet att utföra specifika administrativa uppgifter. Du kan också ta bort en användare från en rollgrupp eller grupper med hjälp av EAC.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Beräknad tid för varje procedur: 5-10 minuter

- Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Om du vill se vilka behörigheter du behöver läser du posten "Användare, Kontakter och rollgrupper" i [funktionsbehörigheterna i EOP-avsnittet.](feature-permissions-in-eop.md)

- Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns i [Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i [exchange onlineskydd](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.

## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a>Använda EAC för att tilldela medlemmar till administratörsrollgrupper

1. Gå](../../media/ITPro-EAC-EditIcon.gif)till **behörighetsadministratörsroller** \> **Admin roles**i EAC, klicka på den rollgrupp som du vill lägga till användaren eller användarna i och klicka sedan på **Redigera** ![redigera.

2. Klicka på **Lägg** ![till](../../media/ITPro-EAC-AddIcon.gif)lägg till ikon under Medlemmar . Fönstret Välj medlemmar visas.

3. Sök efter den eller de användare som du vill lägga till eller markera dem i listan.

4. När du har valt den eller de användare som du vill lägga till klickar du på **Lägg till**och sedan på **OK**. Fönstret Välj medlemmar stängs.

5. Du ser att användaren har lagts till i **fönstret Medlemmar.** Klicka på **Spara**.

   > [!NOTE]
   > Användare kan behöva logga ut och logga in igen för att se ändringen av sina administrativa rättigheter när du har lagt till eller tagit bort medlemmar från rollgruppen.

## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a>Använda EAC för att ta bort medlemmar från administratörsrollgrupper

1. Gå till **Administratörsroller** \> **Admin Roles**för Behörigheter i EAC, klicka på den rollgrupp som du vill ta](../../media/ITPro-EAC-EditIcon.gif)bort en användare eller användare från och klicka sedan på **Redigera** ![redigera.

2. Under Medlemmar väljer du den eller de användare som](../../media/ITPro-EAC-RemoveIcon.gif)du vill ta bort och klickar på Ta **bort** ![ta bort .

3. Klicka på **Spara** om du vill spara ändringen i rollgruppen och gå tillbaka till sidan **Administratörsroller.** Kontrollera att du har tagit bort användaren från administratörsrollgruppen genom att se till att medlemmen inte längre visas under Medlemmar i informationsfönstret för den valda rollgruppen.

   > [!NOTE]
   > Användare kan behöva logga ut och logga in igen för att se ändringen av sina administrativa rättigheter när du har lagt till eller tagit bort medlemmar från rollgruppen.

## <a name="for-more-information"></a>Mer information

[Funktionsbehörigheter i EOP](feature-permissions-in-eop.md)
