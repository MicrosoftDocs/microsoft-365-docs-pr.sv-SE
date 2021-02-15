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
description: Övervaka misslyckade och fördröjda e-postmeddelanden som skickas till eller från konton med stor inverkan på verksamheten.
ms.openlocfilehash: dbdd692a41d341564376960788054e70623daf5a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233368"
---
# <a name="manage-and-monitor-priority-accounts"></a>Hantera och övervaka prioriterade konton

I alla Microsoft 365-organisationer finns det personer som är viktiga, till exempel chefer, chefer eller andra användare som har tillgång till känslig information, äganderätt eller information med hög prioritet.

För att hjälpa din organisation att skydda dessa konton kan du nu ange specifika användare som prioriterade konton och utnyttja appspecifika funktioner som ger dem extra skydd. I framtiden kommer fler appar och funktioner att stödja prioriterade konton och till en början har vi meddelat två **funktioner:** prioriterat kontoskydd och övervakning av **premium e-postflöden.**

- **Skydd för prioriterade** konton – Microsoft Defender för Office 365 (tidigare Office 365 Advanced Threat Protection) stöder prioritetskonton som taggar som kan användas i filter i aviseringar, rapporter och undersökningar. Mer information finns i [Användartaggar i Microsoft Defender för Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags)
- **Övervakning av premium e-postflöde** – Ett felfritt e-postflöde kan vara viktigt för framgången i verksamheten, och leveransfördröjningar och fel kan ha en negativ inverkan på verksamheten. Du kan välja ett tröskelvärde för misslyckade eller fördröjda e-postmeddelanden, få aviseringar när tröskelvärdet överskrids och visa en rapport med e-postproblem för prioriterade konton. Mer information finns i rapporten [E-postproblem för prioritetskonton i moderna EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

Metodtips för säkerhet på prioriterade konton finns i [säkerhetsrekommendationer för prioriterade konton.](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts)

## <a name="before-you-begin"></a>Innan du börjar

Skyddsfunktionen **för prioritetskontot** som beskrivs i det här avsnittet är endast tillgänglig för organisationer som uppfyller följande krav:

- Microsoft Defender för Office 365 abonnemang 2, inklusive de med Office 365 E3, Office 365 E5, Microsoft 365 E5 eller Microsoft 365 E5 Security.

**Premium-funktionen** E-postflödesövervakning som beskrivs i det här avsnittet är endast tillgänglig för organisationer som uppfyller följande krav:

- Organisationen måste ha ett licensantal på minst 10 000, från någon av eller en kombination av följande produkter: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Din organisation kan till exempel ha 3 000 Office 365 E3-licenser och 8500 Microsoft 365 E5, sammanlagt 11 500 licenser från de kvalificerande produkterna.
- Din organisation måste ha minst 50 månatliga aktiva Exchange Online-användare.

> [!NOTE]
> Du kan övervaka upp till 250 prioriterade konton.

### <a name="add-priority-accounts-from-the-setup-page"></a>Lägga till prioritetskonton från sidan Inställningar

Lägg till prioritetskonton från **sidan Inställningar.**

1. Gå till administrationscentret för Microsoft 365 i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Gå till **Konfigurationen**  >  **av organisationens** kunskap och **välj Visa** under Övervaka dina **viktigaste konton.**

3. Välj **Komma igång** eller **Hantera.**

4. Skriv namnet **eller e-postadressen** till den person du vill lägga till i listan med prioriterade konton i sökfältet på sidan Lägg till prioritet-konton. Du kan också ange tröskelvärdet för e-post för misslyckade eller fördröjda e-postmeddelanden och få en veckorapport med problem för prioriterade konton.

5. Markera användaren och välj **Spara.**

Du kan också lägga till prioriterade konton på sidan Aktiva användare.

### <a name="add-priority-accounts-from-active-users-page"></a>Lägg till prioritetskonton från sidan Aktiva användare

Lägg till prioritetskonton från sidan Aktiva användare.

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Gå till **Användare**  >  **aktiva** användare och **välj ...** högst upp på sidan. Välj **Hantera prioritetskonton.**

3. Välj **Lägg till** konton  och skriv namnet på den person du vill lägga till i listan med prioriterade konton i sökfältet på sidan Lägg till prioritet-konton.

4. Markera användaren och välj **Spara.**

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Ta bort en användare från listan med prioriterade konton

1. Gå till administrationscentret för Microsoft 365 i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Gå till **Konfigurationen**  >  **av organisationens** kunskap och **välj Visa** under Övervaka dina **viktigaste konton.**

3. På sidan **Övervaka dina mest konton** väljer du **Prioritet-konton** under **Hantera den här funktionen.**

4. På sidan **Priority-konton** väljer du den eller de användare som du vill ta bort från listan och väljer Ta **bort konton.**

## <a name="related-topics"></a>Relaterade ämnen

[Använda prioritetskonton i Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)