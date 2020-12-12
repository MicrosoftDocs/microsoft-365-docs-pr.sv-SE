---
title: Användarmallar i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att identifiera specifika grupper med användare med användar koder i Microsoft Defender för Office 365 abonnemang 2. För att snabbt identifiera taggade användare kan du använda tagg filtrering för meddelanden, rapporter och undersökningar i Microsoft Defender för Office 365.
ms.openlocfilehash: ad06bf90f1ecb93d671bfcad6fad0b4f2a952cb2
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663613"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Användarmallar i Microsoft Defender för Office 365

> [!NOTE]
> Funktionen användar koder är i förhands granskning, inte tillgänglig för alla och kan komma att ändras. Information om versions schema finns i [Microsoft 365-översikten](https://www.microsoft.com/microsoft-365/roadmap).

User-taggar är identifierare för specifika grupper med användare i [Microsoft Defender för Office 365](office-365-atp.md). Det finns två typer av användar flaggor:

- **System märkning**: [prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) är för närvarande den enda typen av system märkning.
- **Anpassade taggar**: du skapar dem själv.

Om din organisation har Defender för Office 365 abonnemang 2 (ingår i ditt abonnemang eller som ett tillägg) kan du skapa anpassade användar flaggor förutom att använda taggen Priority accounts.

När du har använt system koder eller anpassade taggar för användare kan du använda taggarna som filter i aviseringar, rapporter och undersökningar:

- [Aviseringar i säkerhets & efterlevnad](alerts.md)
- [Threat Explorer och real tids identifiering](threat-explorer.md)
- [Statusrapport för hotskydd](view-email-security-reports.md#threat-protection-status-report)
- [Kampanjvyer](campaigns.md)
- För prioriterade konton kan du använda rapporten med [e-postproblem för prioriterade konton](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) i administrations centret för Exchange (UK).

I den här artikeln förklaras hur du konfigurerar användar koder i fältet säkerhets & efterlevnad. Det finns inga cmdletar i säkerhets & kompatibilitetstillstånd för att hantera användar koder.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Öppna för att gå direkt till sidan **User Tags** <https://protection.office.com/userTags> .

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill skapa, ändra och ta bort användar flaggor måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** .
  - För att lägga till och ta bort medlemmar från befintliga användar flaggor måste du vara medlem i roll grupperna **organisations ledning**, **säkerhets administratör** eller **säkerhets ansvarig**
  - För skrivskyddad åtkomst till användar flaggor måste du vara medlem i rollen **global läsare** eller **säkerhets läsare** .

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  **Anmärkningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Hantering av användar märkning styrs av rollerna **etikett läsare**, **tagga deltagare** och **taggredigerare** .

- Du kan också hantera och övervaka prioriterade konton i administrations centret för Microsoft 365. Anvisningar finns i [Hantera och övervaka prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).

## <a name="use-the-security-center-to-create-user-tags"></a>Använda säkerhets Center för att skapa användar flaggor

1. Gå till användar märkning för **Threat Management** i säkerhets Center \> .

2. På sidan med **användar Taggar** som öppnas klickar du på **skapa tagg**.

3. Guiden **skapa tagg** öppnas i ett nytt flyg ut. På sidan **definiera etikett** konfigurerar du följande inställningar:
   - **Name**: Ange ett unikt, beskrivande namn för taggen. Det här är det värde som du kommer att se och använda.
   - **Beskrivning**: Ange en valfri beskrivning för märket.

   När du är klar klickar du på **Nästa**.

4. Gör något av följande på sidan **tilldela användare** :

   - Klicka på **Lägg till användare**. Gör något av följande för att lägga till enskilda användare eller grupper i rutan Lägg på som visas:
     - Klicka i rutan och bläddra igenom listan för att välja en användare eller grupp.
     - Klicka i rutan och börja skriva för att filtrera listan och välja en användare eller grupp.
     - Om du vill lägga till fler värden klickar du i ett tomt område i rutan.
     - Om du vill ta bort enskilda poster från rutan klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) för användaren eller gruppen i rutan.
     - Om du vill ta bort befintliga poster från listan under rutan klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .

     När du är klar klickar du på **Lägg till**.

   - Klicka på **Importera** för att välja en textfil som innehåller e-postadresserna för användare eller grupper. Kontrol lera att text filen innehåller en post per rad.

   När du är klar klickar du på **Nästa**.

5. På sidan **Granska tagg** granskar du dina inställningar. Du kan klicka på **Redigera** i det specifika avsnittet för att göra ändringar.

   När du är klar klickar du på **Skicka**.

## <a name="use-the-security-center-to-view-user-tags"></a>Använda säkerhets Center för att Visa användar flaggor

1. Gå till användar märkning för **Threat Management** i säkerhets Center \> .

2. På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill visa (Klicka inte på kryss rutan).

3. I den skrivskyddade informationen, flyger ut som visas kontrollerar du inställningarna.

   Klicka på **Stäng** när du är klar.

## <a name="use-the-security-center-to-modify-user-tags"></a>Använda säkerhets Center för att ändra användar flaggor

1. Gå till användar märkning för **Threat Management** i säkerhets Center \> .

2. På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill visa och klickar sedan på **Redigera tagg**.

3. Princip guiden öppnas i en **Edit-tagg** . Klicka på **Nästa** för att granska och ändra inställningarna.

   När du är klar klickar du på **Skicka**.

## <a name="use-the-security-center-to-remove-user-tags"></a>Använda säkerhets Center för att ta bort taggar

**Obs!** du kan inte ta bort den inbyggda **prioritets konto** typen.

1. Gå till användar märkning för **Threat Management** i säkerhets Center \> .

2. På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill ta bort, klickar på **ta bort flagga** och väljer sedan **Ja, ta bort** i varningen som visas.
