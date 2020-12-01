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
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477619"
---
# <a name="manage-and-monitor-priority-accounts"></a>Hantera och övervaka prioriterade konton

I alla Microsoft 365-organisationer finns det personer som är nödvändiga, till exempel chefer, ledare, chefer eller andra användare som har till gång till känslig, tillverkarspecifik eller hög prioritets information.

För att hjälpa din organisation att skydda dessa konton kan du nu ange specifika användare som prioriterade konton och använda programspecifika funktioner som ger dem extra skydd. I framtiden stöder fler appar och funktioner prioritets konton och för att börja med, har vi meddelat två möjligheter: **prioriterat konto skydd** och **övervakning av e-postflöde**.

- **Prioriterat konto skydd** -Microsoft Defender för Office 365 (tidigare Office 365 Avancerat skydd) stöder prioriterade konton som taggar som kan användas i filter i aviseringar, rapporter och undersökningar. Mer information finns [i användar koder i Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).
- **Premium-flödet för e-postflöden** kan vara kritiskt för företags framgångar och leverans fördröjningar och problem kan påverka verksamheten negativt. Du kan välja ett tröskelvärde för misslyckade eller fördröjda e-postmeddelanden, få aviseringar när tröskelvärdet överskrids och se en rapport om e-postproblem för prioriterade konton. För mer information, se [e-postproblem för rapport med prioriterade konton i moderna UK](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).

## <a name="before-you-begin"></a>Innan du börjar

Funktionen **prioriterat konto skydd** som beskrivs i det här avsnittet är endast tillgänglig för organisationer som uppfyller följande krav:

- Microsoft Defender för Office 365 abonnemang 2, inklusive de som har Office 365 E3, Office 365 E5, Microsoft 365 E5 eller Microsoft 365 E5 Security.

Övervaknings funktionen för **Premium mail-flöde** som beskrivs i det här avsnittet är endast tillgänglig för organisationer som uppfyller följande krav:

- Din organisation måste ha ett licens antal på minst 10 000, antingen från en av eller en kombination av följande produkter: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Din organisation kan till exempel ha 3000 Office 365 E3-licenser och 8500 Microsoft 365 E5, för totalt antal 11 500 licenser från kvalificerings produkterna.
- Din organisation måste ha minst 50 månads aktiva Exchange Online-användare.

> [!NOTE]
> Du kan övervaka upp till 250 prioritets konton.

### <a name="add-priority-accounts-from-the-setup-page"></a>Lägga till prioritets konton från konfigurations Sidan

Lägga till prioritets konton från **inställnings sidan**.

1. Gå till administrations centret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Gå till **Konfigurera**  >  **organisationens kunskap** och välj **Visa** under **övervaka dina mest viktiga konton**.

3. Välj **komma igång** eller **Hantera**.

4. Skriv namnet eller e-postadressen för den person som du vill lägga till i listan prioritets konton i Sök fältet på sidan **Lägg till prioritets konton** . Du kan också ange din e-postgräns för misslyckade eller fördröjda e-postmeddelanden och få en vecko rapport om problem med prioritets konton.

5. Markera användaren och välj **Spara**.

Du kan också lägga till prioritets konton från sidan aktiva användare.

### <a name="add-priority-accounts-from-active-users-page"></a>Lägga till prioritets konton från sidan aktiva användare

Lägga till prioritets konton från sidan aktiva användare.

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Gå till **användare**  >  **aktiva användare** och välj **...** högst upp på sidan. Välj **Hantera prioritets konton**.

3. Välj **Lägg till konton** och skriv namnet på den person som du vill lägga till i listan med prioriterade konton i Sök fältet på sidan **Lägg till prioritets konton** .

4. Markera användaren och välj **Spara**.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Ta bort en användare från listan med prioriterade konton

1. Gå till administrations centret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Gå till **Konfigurera**  >  **organisationens kunskap** och välj **Visa** under **övervaka dina mest viktiga konton**.

3. Välj **prioritets konton** under **hantera den här funktionen** på sidan **övervaka dina mest konton** .

4. På sidan **Priority Accounts** väljer du den eller de användare du vill ta bort från listan och väljer **ta bort konton**.

## <a name="related-topics"></a>Relaterade ämnen

[Använda prioriterade konton i Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)