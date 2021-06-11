---
title: Användartaggar i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
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
ms.openlocfilehash: 105e927e50f7b1d1217587587b8d7ee3b7d6bd4c
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904110"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Användartaggar i Microsoft Defender för Office 365

> [!NOTE]
> Funktionen för användartaggar är inte tillgänglig för alla och kan komma att ändras. Mer information om lanseringsschemat finns i översikten [över Microsoft 365 .](https://www.microsoft.com/microsoft-365/roadmap)

Användartaggar är identifierare för specifika användargrupper i [Microsoft Defender för Office 365](defender-for-office-365.md). Det finns två typer av användartaggar:

- **Systemtaggar:** För närvarande [är Prioritet-konton](../../admin/setup/priority-accounts.md) den enda typen av systemtagg.
- **Anpassade taggar:** Du skapar de här användartaggarna själv.

Om din organisation har Defender för Office 365 abonnemang 2 (ingår i din prenumeration eller som ett tillägg) kan du skapa anpassade användartaggar utöver att använda taggen för prioritetskonton.

> [!NOTE]
> För närvarande kan du bara använda användartaggar för postlådeanvändare.

När du har tillämpat systemtaggar eller anpassade taggar för användare kan du använda de taggarna som filter i aviseringar, rapporter och undersökningar:

- [Varningar](alerts.md)
- [Anpassade aviseringsprinciper](../../compliance/alert-policies.md#viewing-alerts)
- [Hotutforskaren och identifiering i realtid](threat-explorer.md)
- [Sidan E-postenhet](mdo-email-entity-page.md#other-innovations)
- [Statusrapport för hotskydd](view-email-security-reports.md#threat-protection-status-report)
- [Kampanjvyer](campaigns.md)
- För prioritetskonton kan du använda rapporten [E-postproblem](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) för prioritetskonton Exchange administrationscenter (EAC).

I den här artikeln förklarar vi hur du konfigurerar användartaggar Microsoft 365 Defender-portalen. Det finns inga cmdlets i Microsoft 365 Defender-portalen för att hantera användartaggar.

Information om hur användartaggar ingår i strategin för att skydda användarkonton med hög effekt finns i Säkerhetsrekommendationer för [prioriterade konton i Microsoft 365.](security-recommendations-for-priority-accounts.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du öppnar Microsoft 365 Defender-portalen på <https://security.microsoft.com/> . Gå direkt till sidan **Användartaggar** genom att öppna <https://security.microsoft.com/securitysettings/userTags> .

- Du måste ha tilldelats behörigheter i Microsoft 365 Defender-portalen innan du kan utföra procedurerna i den här artikeln:
  - Om du vill skapa, ändra och ta bort användartaggar måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**
  - Om du vill lägga till och ta bort medlemmar från befintliga användartaggar måste du vara medlem i rollgrupperna Organisationshantering, **Säkerhetsadministratör** eller **Säkerhetsoperator**
  - För skrivskyddade åtkomst till användartaggar måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**

  Mer information finns i [Behörigheter i Microsoft 365 Defender-portalen.](permissions-in-the-security-and-compliance-center.md)

  > [!NOTE]
  >
  > - Om du lägger till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna  de behörigheter som krävs i Microsoft 365 Defender-portalen och behörigheter för andra funktioner Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  >
  > - Hantering av användartaggar styrs av **rollerna Taggläsare** **och Tagghanteraren.**

- Du kan också hantera och övervaka konton med prioritet Microsoft 365 administrationscentret. Anvisningar finns i Hantera [och övervaka prioritetskonton.](../../admin/setup/priority-accounts.md)

- Information om hur du skyddar _behöriga konton_ (administratörskonton) finns i det [här avsnittet.](/azure/architecture/framework/security/critical-impact-accounts)

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a>Använda Defender Microsoft 365 portalen för att skapa användartaggar

1. Gå till Microsoft 365-post och e-Inställningar och **&** \> **i** \> **Defender-portalen.**

2. Klicka på **Skapa taggikon** skapa ![ tagg på sidan ](../../media/m365-cc-sc-create-icon.png) **Användartaggar.**

3. Guiden **Skapa tagg** öppnas i en ny utfällbladstext. På sidan **Definiera tagg** konfigurerar du följande inställningar:
   - **Namn**: Ange ett unikt, beskrivande namn för taggen. Det här är det värde som du kommer att se och använda. Observera att du inte kan byta namn på en tagg när du har skapat den.
   - **Beskrivning**: Ange en valfri beskrivning för taggen.

   Klicka på **Nästa** när du är klar.

4. Gör **något av följande** på sidan Tilldela medlemmar:
   - Klicka på ![ ikonen Lägg till medlemmar Lägg till ](../../media/m365-cc-sc-create-icon.png) **medlemmar.** I den flygblad som visas gör du något av följande för att lägga till enskilda användare eller grupper:
     - Klicka i rutan och bläddra igenom listan för att välja en användare eller grupp.
     - Klicka i rutan och börja skriva för att filtrera listan och välj en användare eller grupp.
     - Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.
     - Om du vill ta bort enskilda poster klickar du på ![Ta bort post-ikon](../../media/m365-cc-sc-remove-selection-icon.png) bredvid posten i rutan.
     - Om du vill ta bort alla poster klickar du på ta bort postikonen i markerade ![ ](../../media/m365-cc-sc-remove-selection-icon.png) **nn-användare och nn-grupper** under rutan.

     När du är klar klickar du på Lägg **till**.

     På sidan **Tilldela medlemmar kan** du också ta bort poster genom att klicka på Ta ![ ](../../media/m365-cc-sc-delete-icon.png) bort-ikonen bredvid posten.

   - Klicka **på Importera** för att markera en textfil som innehåller e-postadresserna till användare eller grupper. Kontrollera att textfilen innehåller en post per rad.

   Klicka på **Nästa** när du är klar.

5. Granska **inställningarna på** taggsidan Granska som visas. Du kan välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet. Eller så kan du klicka på **Föregående** eller välj den specifika sidan i guiden.

   När du är klar klickar du på **Skicka** och sedan på **Klar**.

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a>Använda Defender Microsoft 365 portalen för att visa användartaggar

1. Gå till Microsoft 365-post och e-Inställningar och **&** \> **i** \> **Defender-portalen.**

2. På **sidan Användartaggar** visas följande egenskaper i listan med användartaggar:

   - **Tagg:** Namnet på användartaggen. Observera att detta inkluderar den inbyggda **systemtaggen för priority-kontot.**
   - **Applied to**: Antalet medlemmar
   - **Senast ändrad**
   - **Skapades**

3. När du väljer en användartagg genom att klicka på namnet visas informationen i en utfällbladstext.

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a>Använda Defender Microsoft 365 portalen för att ändra användartaggar

1. Gå till Microsoft 365-post och e-Inställningar och **&** \> **i** \> **Defender-portalen.**

2. På sidan **Användartaggar** väljer du användartaggen i listan och klickar sedan på Redigera ![ ](../../media/m365-cc-sc-edit-icon.png) **taggikonEn redigera-tagg.**

3. I den utfällklara informationen som visas är samma guide och inställningar tillgängliga enligt beskrivningen i [avsnittet använda Microsoft 365 Defender-portalen](#use-the-microsoft-365-defender-portal-to-create-user-tags) för att skapa användartaggar längre fram i den här artikeln.

   **Anmärkningar**:

   - Sidan **Definiera tagg** är inte tillgänglig för den inbyggda systemtaggen för **Priority-kontot,** så du kan inte byta namn på taggen eller ändra beskrivningen.
   - Du kan inte byta namn på en anpassad tagg, men du kan ändra beskrivningen.

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a>Använda Defender Microsoft 365 portalen för att ta bort användartaggar

> [!NOTE]
> Du kan inte ta bort systemtaggen för det **inbyggda prioritetskontot.**

1. Gå till Microsoft 365-post och e-Inställningar och **&** \> **i** \> **Defender-portalen.**

2. På sidan **Användartaggar** väljer du användartaggen i listan och klickar sedan på Ta bort ![ taggikon Ta ](../../media/m365-cc-sc-delete-icon.png) **bort tagg.**

3. Läs varningen i bekräftelsedialogrutan som visas och klicka sedan på **Ja, ta bort**.
