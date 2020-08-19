---
title: Hantera och övervaka prioriterade konton
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: Övervakar misslyckade och fördröjda meddelanden som skickas till eller från konton som har stor rörelse påverkan.
ms.openlocfilehash: 053246da7f57c46045bfc777bc4de981ce51c6e5
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794213"
---
# <a name="manage-and-monitor-priority-accounts"></a>Hantera och övervaka prioriterade konton

Som administratör för en Microsoft 365-organisation kan du nu övervaka misslyckade eller fördröjda e-postmeddelanden som skickas till dina användare med stor rörelse påverkan, till exempel din VD. Du kan aktivera det genom att lägga till användare i din lista med prioriterade konton. Prioritets konton är konton som är nödvändiga för att köra din organisation. Lägga till chefer, utfyllnadstecken, chefer eller andra användare som har till gång till känslig eller prioriterad information.

## <a name="access-priority-accounts"></a>Åtkomst till prioritets konton

De prioriterade konto funktioner som beskrivs i det här avsnittet är endast tillgängliga för organisationer som uppfyller följande krav:

- Office 365 E3 eller Microsoft 365 E3, eller Office 365 E5 eller Microsoft 365 E5.
- Minst 10 000 licenser och minst 50 månads aktiva Exchange Online-användare.

## <a name="add-priority-accounts-from-the-setup-page"></a>Lägga till prioritets konton från konfigurations Sidan

Lägga till prioritets konton från **inställnings sidan**.

1. Gå till administrations centret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Gå till **Konfigurera**  >  **organisationens kunskap**och välj **Visa** under **övervaka dina mest viktiga konton**.

3. Välj **komma igång** eller **Hantera**.

4. Skriv namnet eller e-postadressen för den person som du vill lägga till i listan prioritets konton i Sök fältet på sidan **Lägg till prioritets konton** . Du kan också ange din e-postgräns för misslyckade eller fördröjda e-postmeddelanden och få en vecko rapport om problem med prioritets konton.

5. Markera användaren och välj **Spara**.

Du kan också lägga till prioritets konton från sidan aktiva användare.

### <a name="add-priority-accounts-from-active-users-page"></a>Lägga till prioritets konton från sidan aktiva användare

Lägga till prioritets konton från sidan aktiva användare.

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Gå till **användare**  >  **aktiva användare**och välj **...** högst upp på sidan. Välj **Hantera prioritets konton**.

3. Välj **Lägg till konton**och skriv namnet på den person som du vill lägga till i listan med prioriterade konton i Sök fältet på sidan **Lägg till prioritets konton** .

4. Markera användaren och välj **Spara**.

## <a name="monitor-your-priority-accounts"></a>Övervaka dina prioriterade konton

Du kan övervaka e-poststatusen för dina prioriterade konton i administrations centret för Microsoft 365 på sidan **Inställningar** . Du kan aktivt övervaka upp till 250-konton.

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Välj **Inställningar** och välj sedan **Visa** bredvid **Premium Monitor** för att se status för dina prioritets konton.

## <a name="email-issues-for-priority-accounts"></a>E-postproblem för prioriterade konton

Du kan spåra e-postproblem för prioriterade konton genom att gå till rapporten **om e-postproblem för prioriterade konton** i administrations centret för Exchange. Mer information finns i [e-postproblem för prioriterade konton](https://review.docs.microsoft.com/en-us/Exchange/mail-flow-best-practices/mail-flow-insights/mfi-email-issues-for-priority-accounts?branch=Priority-chrisda).

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Ta bort en användare från listan med prioriterade konton

1. Gå till administrations centret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Gå till **Konfigurera**  >  **organisationens kunskap**och välj **Visa** under **övervaka dina mest viktiga konton**.

3. Välj **prioritets konton** under **hantera den här funktionen**på sidan **övervaka dina mest konton** .

4. På sidan **Priority Accounts** väljer du den eller de användare du vill ta bort från listan och väljer **ta bort konton**.