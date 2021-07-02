---
title: Använda Microsoft Teams-klasser med Blackboard
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
description: Integrera Microsoft Teams klasser i ditt Learning Management System
ms.openlocfilehash: 3c574184c48ae064d425ed98dbc391b8f5bcf7e0
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53257057"
---
# <a name="use-microsoft-teams-classes-with-blackboard"></a>Använda Microsoft Teams-klasser med Blackboard

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

Microsoft Teams är en LTI Learning-app (Tools Interoperability) som hjälper lärare och elever att enkelt navigera mellan sina LMS (Learning Management System) och Teams. Användare kan komma åt sina klassteam som är kopplade till kursen direkt från LMS.

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a>Godkänna appen i Microsoft Azure klientorganisationen

Följande uppgifter slutförs av den Microsoft Office 365 och Blackboard Learn Ultra-administratören.

Innan du hanterar integreringen i Blackboard Learn Ultra måste Microsoft Office 365-administratören godkänna Blackboard **MSFT Teams** för Lär dig Ultra Azure-appen för institutionens Microsoft Azure klientorganisation.

1. Hitta ditt klientorganisations-ID för Microsoft. Ta [reda på hur du hittar klientorganisationen.](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)

2. Omdirigera slutpunkten för administratörsmedgivande för Microsoft-identitetsplattformen enligt följande exempel:

   `https://login.microsoftonline.com/{tenant}/adminconsent?client_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > Ersätt {tenant} med din organisations Microsoft-klientorganisations-ID.

## <a name="register-the-integration-apps"></a>Registrera integrationsapparna

Som Blackboard Learn Ultra-administratör måste du registrera 2 LTI 1.3-integreringsappar i testmiljön:

- Blackboard Learn Class Teams stöd för synkronisering av deltagarlistan

- LTI Microsoft Teams för klassteamet

1. Notera följande LTI-klient-ID för båda apparna:

    - Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41

    - Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89

2. Öppna administrationspanelen och leta upp **LTI-verktygsleverantörerna** under Integrations.

   ![det här är dialogrutan för LTI-verktygsleverantör som visar en lista över leverantörer](../media/lti-media/lti-tool-providers.png)

3. Välj **Registrera LTI1.3/Advantage-verktyget**.

4. Ange det första klient-IDt som tillhandahålls (antingen Blackboard eller Microsoft) och välj **Skicka**.

5. Granska de ifyllda inställningarna och kontrollera att verktygsstatusen har markerats som godkänd.

6. Bläddra längst ned och välj sedan **Skicka**.

7. Upprepa föregående steg för att registrera den andra av LTI-apparna i din miljö.

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a>Konfigurera resursdelning för REST-program och resursdelning mellan ursprung

Blackboard Learn Ultra-administratören måste också konfigurera konfigurationen REST-program och Resursdelning mellan ursprung.

Fyll i följande för att konfigurera REST-programmet

1. Öppna Lär dig administrationsverktyg och välj sedan **REST API-integrationer** i **avsnittet Integrationer.**

2. Välj **Skapa integrationer** och ange samma program-/klient-ID som du angav för Blackboard Learn Class Teams Integration LTI-verktyget.

3. Ange Läs in användare (det här kan vara ditt eget användarnamn för lär dig), eller välj **Bläddra och** leta reda på det.

4. Välj **Ja** för **slutanvändaråtkomst.**

5. Välj **Ja** för **Behörig att agera som användare**

6. Välj **Skicka när** du är klar.

## <a name="set-up-cross-origin-resource-sharing"></a>Konfigurera resursdelning mellan ursprung

1. Öppna Lär dig administrationsverktyg och välj **Resursdelning mellan ursprung** i **avsnittet Integreringar.**

2. Välj **Skapa konfiguration**.

3. Ange `https://bb-ms-teams-ultra-ext.api.blackboard.com` ursprunget.

4. Lägg till ordet **Auktorisering** **i Tillåtna rubriker.**

5. Ange **Tillgänglig** till **Ja.**

6. Välj **Skicka när** du är klar.

## <a name="enable-class-teams-in-blackboard-learn"></a>Aktivera Teams i Blackboard Learn

När du har aktiverat LTI-verktygen är nästa steg att konfigurera Microsoft Class Teams-integrering från din egen Microsoft Office 365 klientorganisation. Du kan göra det genom att följa de här stegen som Blackboard Learn Ultra-administratör.

1. I **Lär dig**  >  **administrationsverktyg och verktyg** väljer du Microsoft Teams Integration **Admin**.

   ![dialogrutan Verktyg och verktyg med en lista över tillgängliga verktyg](../media/lti-media/tools-utilities.png)

2. Markera kryssrutan för Aktivera **Microsoft Teams**.

3. Ange ditt klientorganisations-ID som det refereras till i avsnittet under Microsoft O365 Admin

 > [!NOTE]
 > Du kan inte spara inställningarna förrän appen har godkänts av O365-administratören. Se [Godkänna appen i Microsoft Azure klientorganisation.](#approve-the-app-in-the-microsoft-azure-tenant)

4. När den globala O365-administratören har godkänt Blackboard-Teams program i Microsoft-klientorganisationen väljer du **Skicka**.
