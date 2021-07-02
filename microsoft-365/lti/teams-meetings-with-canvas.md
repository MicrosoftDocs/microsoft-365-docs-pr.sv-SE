---
title: Använda Microsoft Teams möten med Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrera Microsoft Teams möten med Canvas
ms.openlocfilehash: 946abaec52cb1c5060d5490b409758cf230a4e5a
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256885"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Använda Microsoft Teams möten med Canvas

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

Microsoft Teams möten är en Learning LTI-app (Tools Interoperability) som hjälper lärare och elever att enkelt navigera mellan sina LMS (Learning Management System) och Teams. Användare kan komma åt sina klassteam som är kopplade till kursen direkt från LMS.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Administratör

Innan du hanterar Microsoft Teams-integreringen i Instructure Canvas är det viktigt att ha Canvass **Microsoft-Teams-Sync-for-Canvas Azure-app** godkänd av din institutions Microsoft Office 365-administratör i Microsoft Azure-innehavaren innan du slutför Canvas-administratörskonfigurationen.

1. Logga in på Canvas.

2. Välj **adminlänken** i det globala navigeringsfältet och välj sedan ditt konto.

3. I administratörsnavigeringen väljer **Inställningar** och sedan **fliken** Integrationer.

4. Ange microsofts klientorganisationsnamn och inloggningsattribut.

   Attributet Login används för att associera Canvas-användaren med en Azure Active Directory användare.

5. Välj **Uppdatera Inställningar klar.**

6. Om du vill godkänna åtkomst för Canvas **microsoft-Teams-Sync-for-Canvas Azure-app** väljer du **länken Bevilja åtkomst för klientorganisation.** Du omdirigeras till slutpunkten för administratörsmedgivande för Microsoft-identitetsplattformen.

   ![behörigheter](media/permissions.png)

7. Välj **Acceptera**.

8. Aktivera Microsoft Teams genom att aktivera växlingsknappen.

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a>Canvas-administratör

Konfigurera integreringen Microsoft Teams LTI 1.3.

Som Canvas-administratör måste du lägga till LTI Microsoft Teams möten i din miljö. Anteckna LTI-klient-ID för appen.

 - Microsoft Teams -170000000000703

1. Access **Admin settings**  >  **Apps**.

2. Välj **+ App för** att lägga Teams LTI-appar.

   ![externa appar](media/external-apps.png)

3. Välj **Efter klient-ID** för konfigurationstyp.

   ![lägg till app](media/add-app.png)

4. Ange det klient-ID som tillhandahålls och välj sedan **Skicka.**

   Du ser namnet på det Microsoft Teams LTI-appnamnet för möten för klient-ID:t som bekräftelse.

5. Välj **Installera**.

   LTI Microsoft Teams möten läggs till i listan över externa appar.
