---
title: Användartaggar i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att identifiera specifika grupper av användare med användartaggar i Microsoft Defender för Office 365 abonnemang 2. Taggfiltrering är tillgängligt för aviseringar, rapporter och undersökningar i Microsoft Defender för Office 365 för att snabbt identifiera taggade användare.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 62d858fe5962b94f536d4ccbd712e21bdd5caa57
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290135"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Användartaggar i Microsoft Defender för Office 365

> [!NOTE]
> Funktionen med användartaggar är i förhandsversion, inte tillgänglig för alla och kan komma att ändras. Mer information om versionsschemat finns i Microsoft [365-översikten.](https://www.microsoft.com/microsoft-365/roadmap)

Användartaggar är identifierare för specifika användargrupper i [Microsoft Defender för Office 365.](office-365-atp.md) Det finns två typer av användartaggar:

- **Systemtaggar:** För närvarande [är Prioritet-konton](../../admin/setup/priority-accounts.md) den enda typen av systemtagg.
- **Anpassade taggar:** Du skapar dessa användartaggar själv.

Om din organisation har Defender för Office 365 Abonnemang 2 (ingår i din prenumeration eller som ett tillägg) kan du skapa anpassade användartaggar utöver att använda taggen för prioriterade konton.

När du har tillämpat systemtaggar eller anpassade taggar för användare kan du använda de taggarna som filter i aviseringar, rapporter och undersökningar:

- [Varningar i Säkerhets- & Efterlevnadscenter](alerts.md)
- [Hotutforskaren och identifieringar i realtid](threat-explorer.md)
- [Statusrapport för hotskydd](view-email-security-reports.md#threat-protection-status-report)
- [Kampanjvyer](campaigns.md)
- För prioriterade konton kan du använda rapporten [E-postproblem för prioritetskonton](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) i administrationscentret för Exchange (EAC).

I den här artikeln förklaras hur du konfigurerar användartaggar & Säkerhets- och efterlevnadscenter. Det finns inga cmdlets i Säkerhets- & för att hantera användartaggar.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Gå direkt till sidan **med användartaggar** genom att <https://protection.office.com/userTags> öppna.

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill skapa, ändra och ta bort användartaggar måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**
  - Om du vill lägga till och ta bort medlemmar från befintliga användartaggar måste du vara medlem i rollgrupperna Organisationshantering, Säkerhetsadministratör eller **Säkerhetsoperator**
  - För skrivskyddade åtkomst till användartaggar måste du vara medlem i rollgrupperna **Global Reader** **eller** Säkerhetsläsare.

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  **Anmärkningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Hantering av användartaggar styrs av **rollerna Taggläsare,** **Taggdeltagare** **och Tagghanteraren.**

- Du kan också hantera och övervaka prioriterade konton i administrationscentret för Microsoft 365. Instruktioner finns i Hantera [och övervaka prioriterade konton.](../../admin/setup/priority-accounts.md)

## <a name="use-the-security-center-to-create-user-tags"></a>Använda Säkerhetscenter för att skapa användartaggar

1. Gå till Användartaggar för hantering **av** hot i \> **Säkerhetscenter.**

2. Klicka på **Skapa tagg** på sidan Med **användartaggar som öppnas.**

3. Guiden **Skapa tagg** öppnas i en ny flyg utfällning. Konfigurera följande **inställningar** på sidan Definiera tagg:
   - **Namn:** Ange ett unikt, beskrivande namn för taggen. Det här är det värde som visas och används.
   - **Beskrivning:** Ange en valfri beskrivning för taggen.

   Klicka på Nästa när du är **klar.**

4. Gör något **av följande** på sidan Tilldela användare:

   - Klicka **på Lägg till användare.** I den utfälling som visas gör du något av följande för att lägga till enskilda användare eller grupper:
     - Klicka i rutan och bläddra igenom listan för att välja en användare eller grupp.
     - Klicka i rutan och börja skriva för att filtrera listan och välj en användare eller grupp.
     - Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.
     - Om du vill ta bort enskilda poster i rutan klickar du **på ikonen** Ta bort för användaren eller gruppen ![ i ](../../media/scc-remove-icon.png) rutan.
     - Om du vill ta bort befintliga poster från listan under rutan klickar du på **ta** ![ bort-ikonen ](../../media/scc-remove-icon.png) för posten.

     Klicka på Lägg till när du är **klar.**

   - Klicka **på Importera** för att markera en textfil som innehåller e-postadresserna till användare eller grupper. Kontrollera att textfilen innehåller en post per rad.

   Klicka på Nästa när du är **klar.**

5. Granska **inställningarna på taggsidan** Granska. Du kan klicka **på Redigera** i det specifika avsnittet för att göra ändringar.

   Klicka på Skicka när du är **klar.**

## <a name="use-the-security-center-to-view-user-tags"></a>Använda Säkerhetscenter för att visa användartaggar

1. Gå till Användartaggar för hantering **av** hot i \> **Säkerhetscenter.**

2. På sidan **med användartaggar** som öppnas väljer du den användartagg som du vill visa (klicka inte i kryssrutan).

3. Granska inställningarna i den skrivskyddade informationen som visas.

   Klicka på **Stäng** när du är klar.

## <a name="use-the-security-center-to-modify-user-tags"></a>Använda Säkerhetscenter för att ändra användartaggar

1. Gå till Användartaggar för hantering **av** hot i \> **Säkerhetscenter.**

2. På sidan **med användartaggar** som öppnas väljer du den användartagg som du vill visa och klickar sedan på **Redigera tagg.**

3. Principguiden öppnas i en **redigeringstagg.** Klicka **på** Nästa för att granska och ändra inställningarna.

   Klicka på Skicka när du är **klar.**

## <a name="use-the-security-center-to-remove-user-tags"></a>Använda Säkerhetscenter för att ta bort användartaggar

**Obs!** Du kan inte ta bort den inbyggda taggen **Priority-konto.**

1. Gå till Användartaggar för hantering **av** hot i \> **Säkerhetscenter.**

2. Markera den **användartagg du** vill ta bort på sidan med användartaggar som öppnas, klicka på Ta bort tagg och välj sedan **Ja,** ta bort i varningen som visas.
