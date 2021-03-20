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
description: Administratörer kan lära sig att identifiera särskilda grupper av användare med användartaggar i Microsoft Defender för Office 365 abonnemang 2. Taggfiltrering är tillgängligt i aviseringar, rapporter och undersökningar i Microsoft Defender för Office 365 för att snabbt identifiera de taggade användarna.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e9bb6a233f21268df860974549ecffbfd7154045
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916412"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Användartaggar i Microsoft Defender för Office 365

> [!NOTE]
> Funktionen för användartaggar är inte tillgänglig för alla och kan komma att ändras. Mer information om lanseringsschemat finns i Översikt över [Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)

Användartaggar är identifierare för specifika grupper av användare [i Microsoft Defender för Office 365.](office-365-atp.md) Det finns två typer av användartaggar:

- **Systemtaggar:** För närvarande [är Prioritet-konton](../../admin/setup/priority-accounts.md) den enda typen av systemtagg.
- **Anpassade taggar:** Du skapar de här användartaggarna själv.

Om din organisation har Defender för Office 365 abonnemang 2 (ingår i prenumerationen eller som ett tillägg) kan du skapa anpassade användartaggar utöver att använda taggen för prioritetskonton.

När du har tillämpat systemtaggar eller anpassade taggar för användare kan du använda de taggarna som filter i aviseringar, rapporter och undersökningar:

- [Varningar i Säkerhets- & Efterlevnadscenter](alerts.md)
- [Hotutforskaren och identifiering i realtid](threat-explorer.md)
- [Statusrapport för hotskydd](view-email-security-reports.md#threat-protection-status-report)
- [Kampanjvyer](campaigns.md)
- För prioritetskonton kan du använda rapporten [E-postproblem för prioritetskonton](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) i administrationscentret för Exchange (EAC).

I den här artikeln förklaras hur du konfigurerar användartaggar & Säkerhets- och efterlevnadscenter. Det finns inga cmdlets i Säkerhets- & för att hantera användartaggar.

Information om hur användartaggar är en del av strategin för att skydda användarkonton med hög effekt finns i Säkerhetsrekommendationer för [prioriterade konton i Microsoft 365.](security-recommendations-for-priority-accounts.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Gå direkt till sidan **Användartaggar** genom att öppna <https://protection.office.com/userTags> .

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill skapa, ändra och ta bort användartaggar måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**
  - Om du vill lägga till och ta bort medlemmar från befintliga användartaggar måste du vara medlem i rollgrupperna Organisationshantering, **Säkerhetsadministratör** eller **Säkerhetsoperator**
  - För skrivskyddade åtkomst till användartaggar måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  **Anmärkningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Hantering av användartaggar styrs av **rollerna Taggläsare** **och Tagghanteraren.**

- Du kan också hantera och övervaka konton med prioritet i administrationscentret för Microsoft 365. Anvisningar finns i Hantera [och övervaka prioritetskonton.](../../admin/setup/priority-accounts.md)

## <a name="use-the-security--compliance-center-to-create-user-tags"></a>Använda Säkerhets- & efterlevnadscenter för att skapa användartaggar

1. Gå till Användartaggar för & skydd mot **hothantering** \> **i Säkerhets- och efterlevnadscenter.**

2. På sidan **Användartaggar** som öppnas klickar du på **Skapa tagg.**

3. Guiden **Skapa tagg** öppnas i en ny farten. På sidan **Definiera tagg** konfigurerar du följande inställningar:
   - **Namn**: Ange ett unikt, beskrivande namn för taggen. Det här är det värde som du kommer att se och använda.
   - **Beskrivning**: Ange en valfri beskrivning för taggen.

   Klicka på Nästa när du är **klar.**

4. Gör **något av** följande på sidan Tilldela användare:

   - Klicka på **Lägg till användare.** I den flygblad som visas gör du något av följande för att lägga till enskilda användare eller grupper:
     - Klicka i rutan och bläddra igenom listan för att välja en användare eller grupp.
     - Klicka i rutan och börja skriva för att filtrera listan och välj en användare eller grupp.
     - Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.
     - Om du vill ta bort enskilda poster från rutan klickar du **på Ikonen** Ta bort för användaren eller gruppen ![ i ](../../media/scc-remove-icon.png) rutan.
     - Om du vill ta bort befintliga poster från listan under rutan klickar du på **Ta** ![ bort-ikonen ](../../media/scc-remove-icon.png) för posten.

     När du är klar klickar du på Lägg **till**.

   - Klicka **på Importera** för att markera en textfil som innehåller e-postadresserna till användare eller grupper. Kontrollera att textfilen innehåller en post per rad.

   Klicka på Nästa när du är **klar.**

5. Granska **inställningarna på** taggsidan Granska. Du kan klicka **på Redigera** i det specifika avsnittet för att göra ändringar.

   När du är klar klickar du på **Skicka.**

## <a name="use-the-security--compliance-center-to-view-user-tags"></a>Använda Säkerhets- & efterlevnadscenter för att visa användartaggar

1. Gå till Användartaggar för & skydd mot **hothantering** \> **i Säkerhets- och efterlevnadscenter.**

2. På sidan **Användartaggar** som öppnas väljer du den användartagg som du vill visa (klicka inte i kryssrutan).

3. Granska inställningarna i den skrivskyddade informationen som visas.

   Klicka på **Stäng** när du är klar.

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a>Använda Säkerhets- & efterlevnadscenter för att ändra användartaggar

1. Gå till Användartaggar för & skydd mot **hothantering** \> **i Säkerhets- och efterlevnadscenter.**

2. På sidan **Användartaggar** som öppnas väljer du den användartagg som du vill visa och klickar sedan på **Redigera tagg**.

3. Principguiden öppnas i en **utfälls fönster för** redigeringstagg. Klicka **på** Nästa för att granska och ändra inställningarna.

   När du är klar klickar du på **Skicka.**

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a>Använda Säkerhets- och & för att ta bort användartaggar

**Obs!** Du kan inte ta bort den inbyggda **prioritetskontotaggen.**

1. Gå till Användartaggar för & skydd mot **hothantering** \> **i Säkerhets- och efterlevnadscenter.**

2. På sidan **Användartaggar** som öppnas väljer du den användartagg du vill ta bort, klickar på Ta bort tagg och väljer sedan  **Ja,** ta bort i varningen som visas.