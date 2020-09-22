---
title: Användar flaggor
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
description: Administratörer kan lära sig att identifiera specifika grupper med användare med User-Taggar i Oiffce 365 ATP 2. Filtrering av märkningar är tillgängligt för aviseringar, rapporter och undersökningar i Office 365 ATP för att snabbt identifiera taggade användare.
ms.openlocfilehash: d47c5c00e3cf0362c44aebc18d11db4bba68a149
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48210036"
---
# <a name="user-tags-in-the-microsoft-security-center"></a>Användar koder i Microsoft säkerhets Center

User-taggar är identifierare för specifika grupper med användare i [Office 365 Avancerat skydd (ATP)](office-365-atp.md). [Prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) är en typ av användar märkning. Om din organisation har Office 365 ATP-abonnemang 2 (ingår i ditt abonnemang eller som ett tillägg) kan du skapa anpassade användar flaggor förutom att använda taggen för prioritets konton.

När du har använt taggar för specifika användare kan du använda taggarna som filter i aviseringar, rapporter och undersökningar:

- [Aviseringar i säkerhets & efterlevnad](alerts.md)
- [Threat Explorer och real tids identifiering](threat-explorer.md)
- [Statusrapport för hotskydd](view-email-security-reports.md#threat-protection-status-report)
- [Kampanjvyer](campaigns.md)

I den här artikeln förklaras hur du konfigurerar användar koder i säkerhets Center.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du öppnar säkerhets Center på <https://security.microsoft.com/> . Öppna för att gå direkt till sidan **User Tags** <https://security.microsoft.com/securitysettings/userTags> .

- Om du vill skapa, ändra eller ta bort användar flaggor måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** i säkerhets & Compliance Center. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

- Du kan också hantera och övervaka prioriterade konton i administrations centret för Microsoft 365. Anvisningar finns i [Hantera och övervaka prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).

## <a name="use-the-security-center-to-create-user-tags"></a>Använda säkerhets Center för att skapa användar flaggor

1. I säkerhets Center går du till **Inställningar** \> **e-&** \> **användar märkning**för samarbete.

2. På sidan med **användar Taggar** som öppnas klickar du på **skapa tagg**.

3. Guiden **skapa tagg** öppnas i ett nytt flyg ut. På sidan **definiera etikett** konfigurerar du följande inställningar:

   - **Name**: Ange ett unikt, beskrivande namn för taggen. Det här är det värde som du kommer att se och använda.

   - **Beskrivning**: Ange en valfri beskrivning för märket.

   När du är klar klickar du på **Nästa**.

4. Gör något av följande på sidan **tilldela post lådor** :

   - Klicka på **Lägg till post lådor**. Gör något av följande för att lägga till enskilda användare eller grupper i rutan Lägg på som visas:

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

1. I säkerhets Center går du till **Inställningar** \> **e-&** \> **användar märkning**för samarbete.

2. På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill visa (Klicka inte på kryss rutan).

3. I den skrivskyddade informationen, flyger ut som visas kontrollerar du inställningarna.

   Klicka på **Stäng** när du är klar.

## <a name="use-the-security-center-to-modify-user-tags"></a>Använda säkerhets Center för att ändra användar flaggor

1. I säkerhets Center går du till **Inställningar** \> **e-&** \> **användar märkning**för samarbete.

2. På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill visa och klickar sedan på **Redigera tagg**.

3. Princip guiden öppnas i en **Edit-tagg** . Klicka på **Nästa** för att granska och ändra inställningarna.

   När du är klar klickar du på **Skicka**.

## <a name="use-the-security-center-to-remove-user-tags"></a>Använda säkerhets Center för att ta bort taggar

**Obs!** du kan inte ta bort den inbyggda **prioritets konto** typen.

1. I säkerhets Center går du till **Inställningar** \> **e-&** \> **användar märkning**för samarbete.

2. På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill ta bort, klickar på **ta bort flagga**och väljer sedan **Ja, ta bort** i varningen som visas.
