---
title: Hantera och övervaka prioritetskonton
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
description: Övervaka misslyckades och fördröjda e-postmeddelanden som skickas till eller från konton som har stor inverkan på verksamheten.
ms.openlocfilehash: 0bba1f87f80de9fea249ce2604e83ceeadfb79ee
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050648"
---
# <a name="manage-and-monitor-priority-accounts"></a>Hantera och övervaka prioritetskonton

I varje Microsoft 365-organisation finns det personer som är viktiga, t.ex. chefer, chefer eller andra användare som har tillgång till känslig, egenutvecklad eller högprioriterad information.

För att hjälpa din organisation att skydda dessa konton kan du nu ange specifika användare som prioriterade konton och utnyttja appspecifika funktioner som ger dem extra skydd. I framtiden kommer fler appar och funktioner att stödja prioritetskonton, och till en början har vi meddelat två **funktioner:** prioriterat kontoskydd och övervakning av **premium-e-postflöden.**

- **Skydd av prioriterade** konton – Microsoft Defender för Office 365 (tidigare Office 365 Advanced Threat Protection) har stöd för prioritetskonton som taggar som kan användas i filter i aviseringar, rapporter och undersökningar. Mer information finns i [Användartaggar i Microsoft Defender för Office 365.](../../security/defender-365-security/user-tags.md)
- **Premium övervakning av e-postflöde** – Felfritt e-postflöde kan vara viktigt för att verksamheten ska lyckas, och leveransfördröjningar och fel kan påverka verksamheten negativt. Du kan välja ett tröskelvärde för misslyckade eller fördröjda e-postmeddelanden, få aviseringar när tröskelvärdet överskrids och visa en rapport om e-postproblem för prioritetskonton. Mer information finns i rapporten [E-postproblem för prioritetskonton i den moderna EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

Information om metodtips för säkerhet på prioriterade konton finns i [Säkerhetsrekommendationer för prioritetskonton.](../../security/defender-365-security/security-recommendations-for-priority-accounts.md)

## <a name="before-you-begin"></a>Innan du börjar

Funktionen **för att skydda** ett Priority-konto som beskrivs i det här avsnittet är endast tillgänglig för organisationer som uppfyller följande krav:

- Microsoft Defender för Office 365 abonnemang 2, inklusive de med Office 365 E3, Office 365 E5, Microsoft 365 E5 eller Microsoft 365 E5 Security.

Den **premiumfunktion för e-postflödesövervakning** som beskrivs i det här avsnittet är endast tillgänglig för organisationer som uppfyller följande krav:

- Organisationen måste ha ett antal licenser på minst 10 000, från en av eller en kombination av följande produkter: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Din organisation kan till exempel ha 3 000 Office 365 E3-licenser och 8500 Microsoft 365 E5, sammanlagt 11 500 licenser från de kvalificerande produkterna.
- Din organisation måste ha minst 50 månatliga aktiva Exchange Online-användare.

> [!NOTE]
> Du kan övervaka upp till 250 prioriterade konton.

### <a name="add-priority-accounts-from-the-setup-page"></a>Lägg till prioritetskonton från sidan Inställningar

Lägg till prioritetskonton från **sidan Inställningar.**

1. Gå till administrationscentret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Gå till **Kunskap**  >  **om konfigurationen** av organisationen och välj **Visa** under Övervaka dina **viktigaste konton.**

3. Välj **Komma igång** eller **Hantera**.

4. På sidan **Lägg till prioritetskonton** skriver du namnet eller e-postadressen för den person du vill lägga till i listan med prioritetskonton i sökfältet. Du kan också ange tröskelvärdet för e-post för misslyckade eller fördröjda e-postmeddelanden och få en veckorapport med problem för prioritetskonton.

5. Markera användaren och välj **Spara**.

Du kan också lägga till prioritetskonton från sidan Aktiva användare.

### <a name="add-priority-accounts-from-active-users-page"></a>Lägg till prioritetskonton från sidan Aktiva användare

Lägg till prioritetskonton från sidan Aktiva användare.

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Gå **till Användare**  >  **aktiva** användare och **välj ...** högst upp på sidan. Välj **Hantera prioritetskonton.**

3. Välj **Lägg till** konton  och skriv namnet på den person du vill lägga till i listan prioritetskonton i sökfältet på sidan Lägg till prioritetskonton.

4. Markera användaren och välj **Spara**.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Ta bort en användare från listan med prioriterade konton

1. Gå till administrationscentret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Gå till **Kunskap**  >  **om konfigurationen** av organisationen och välj **Visa** under Övervaka dina **viktigaste konton.**

3. På sidan **Övervaka dina konton mest** väljer du **Prioritet-konton** under **Hantera den här funktionen.**

4. På sidan **Priority accounts** väljer du den eller de användare du vill ta bort från listan och väljer Ta **bort konton.**

## <a name="related-topics"></a>Relaterade ämnen

[Använda prioritetskonton i Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)