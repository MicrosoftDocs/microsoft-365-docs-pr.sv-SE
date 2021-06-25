---
title: Använda Microsoft Teams-klasser med Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrera Microsoft Teams klasser med Canvas
ms.openlocfilehash: 8e28cc8401dbf37d6e780b8f56dc300982abd0cc
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137685"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Använda Microsoft Teams-klasser med Canvas

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

Microsoft Teams är en LTI Learning-app (Tools Interoperability) som hjälper lärare och elever att enkelt navigera mellan sina LMS (Learning Management System) och Teams. Användare kan komma åt sina klassteam som är kopplade till kursen direkt från LMS.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Administratör

Innan du hanterar Microsoft Teams-integreringen i Instructure Canvas är det viktigt att ha Canvass **Microsoft-Teams-Sync-for-Canvas Azure-app** godkänd av din institutions Microsoft Office 365-administratör i Microsoft Azure-innehavaren innan du slutför Canvas-administratörskonfigurationen.

1. Logga in på Canvas.
 
2. Välj **adminlänken** i det globala navigeringsfältet och välj sedan ditt konto.

3. I administratörsnavigeringen väljer **Inställningar** och sedan **fliken** Integrationer. 

4. Aktivera Microsoft Teams genom att aktivera växlingsknappen.

   ![teams-sync](media/teams-sync.png)

5. Ange microsofts klientorganisationsnamn och inloggningsattribut. 

   Attributet Login används för att associera Canvas-användaren med en Azure Active Directory användare. 

6. Välj **Uppdatera Inställningar klar.**

7. Om du vill godkänna åtkomst för Canvas **microsoft-Teams-Sync-for-Canvas Azure-app** väljer du **länken Bevilja åtkomst för klientorganisation.** Du omdirigeras till slutpunkten för administratörsmedgivande för Microsoft-identitetsplattformen.

   ![behörigheter](media/permissions.png)

8. Välj **Acceptera**.
 
## <a name="canvas-admin"></a>Canvas-administratör

Konfigurera integreringen Microsoft Teams LTI 1.3.

Som Canvas-administratör måste du lägga till LTI Microsoft Teams klassappen i din miljö. Anteckna LTI-klient-ID för appen.

 - Microsoft Teams - 170000000000570

1. Access **Admin settings**  >  **Apps**.

2. Välj **+ App för** att lägga Teams LTI-appar. 
 
   ![externa appar](media/external-apps.png)

3. Välj **Efter klient-ID** för konfigurationstyp.

   ![lägg till app](media/add-app.png)

4. Ange det klient-ID som tillhandahålls och välj sedan **Skicka.**
   
   Du ser namnet på Microsoft Teams-klassens LTI-app för klient-ID:t som bekräftelse. 

5. Välj **Installera**.

   Appen Microsoft Teams klasserna LTI läggs till i listan över externa appar.
