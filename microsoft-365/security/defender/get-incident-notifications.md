---
title: Få incidentmeddelanden via e-post i Microsoft 365 Defender
description: Lär dig hur du skapar regler för att få e-postaviseringar för incidenter i Microsoft 365 Defender
keywords: incident, e-post, e-postmeddelanden, konfigurera, användare, postlåda, e-post, incidenter, analysera, svara
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7ba21e08f72760654993335764df00e78abc87b2
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939724"
---
# <a name="get-incident-notifications-by-email"></a>Få incidentaviseringar via e-post

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Du kan konfigurera Microsoft 365 Defender så att din personal får ett e-postmeddelande om nya incidenter eller uppdateringar av befintliga incidenter. Du kan välja att få aviseringar baserat på:

- Incidentens allvarlighetsgrad.
- Enhetsgrupp.
- Endast vid den första uppdateringen per incident.

E-postmeddelandet innehåller viktig information om incidenten, bland annat incidentens namn, allvarlighetsgrad och kategorier. Du kan också gå direkt till incidenten och börja analysera direkt. Mer information finns i [Analysera incidenter.](investigate-incidents.md)

Du kan lägga till eller ta bort mottagare i e-postaviseringarna. Nya mottagare får ett meddelande om incidenter när de har lagts till. 

>[!NOTE]
>Du behöver behörigheten Hantera säkerhetsinställningar för att konfigurera inställningar för e-postaviseringar. Om du har valt att använda grundläggande behörighetshantering kan användare med roller som säkerhetsadministratör eller global administratör konfigurera e-postaviseringar åt dig. <br> <br>
På samma sätt kan du, om din organisation använder rollbaserad åtkomstkontroll (RBAC), bara skapa, redigera, ta bort och ta emot meddelanden baserat på enhetsgrupper som du har behörighet att hantera.

## <a name="create-a-rule-for-email-notifications"></a>Skapa en regel för e-postaviseringar

Följ de här anvisningarna för att skapa en ny regel och anpassa inställningarna för e-postaviseringar.

1. I navigeringsfönstret väljer du Inställningar **> Microsoft 365 Defender och > e-postmeddelanden om incidenter**.
2. Välj **Lägg till objekt.**
3. Skriv **regelnamnet** och en beskrivning på sidan Grunder och välj sedan **Nästa.**
4. På sidan **Meddelandeinställningar** konfigurerar du:
    - **Aviserings allvarlighetsgrad** – Välj den aviserings allvarlighetsgrad som utlöser en incidentavisering. Om du till exempel bara vill informeras om incidenter med hög allvarlighetsgrad väljer du **Hög.**
    - **Enhetsgruppomfattning** – Du kan ange alla enhetsgrupper eller välja i listan över enhetsgrupper i klientorganisationen.
    - **Meddela endast vid första förekomsten per incident** – Välj om du bara vill ha en avisering på den första aviseringen som matchar dina andra val. Senare uppdateringar eller aviseringar relaterade till händelsen skickar inte ytterligare meddelanden.
    - **Inkludera organisationens namn i e-postmeddelandet** – Välj om du vill att organisationens namn ska visas i e-postmeddelandet.
    - **Inkludera klientspecifik portallänk** – välj om du vill lägga till en länk med klientorganisations-ID:t i e-postmeddelandet för åtkomst till en viss Microsoft 365-klient.

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Meddelandeinställningar för incidentmeddelanden":::

5. Välj **Nästa**. På sidan **Mottagare** lägger du till de e-postadresser som ska ta emot incidentaviseringarna. Välj **Lägg till** när du har skrivit varje ny e-postadress. Om du vill testa aviseringar och se till att mottagarna får dem i inkorgarna väljer du **Skicka test-e-post.** 
6. Välj **Nästa**. Granska **inställningarna för** regeln på sidan Granska regel och välj sedan **Skapa regel.** Mottagarna får incidentaviseringar via e-post baserat på inställningarna.

Om du vill redigera en befintlig regel väljer du den i listan med regler. I fönstret med regelnamnet väljer du **Redigera regel** och gör ändringarna på sidorna **Grunder,** **Meddelandeinställningar** **och** Mottagare.

Om du vill redigera en befintlig regel väljer du den i listan med regler. I fönstret med regelnamnet väljer du Ta **bort**.

## <a name="see-also"></a>Se även
- [Översikt över incidenter](incidents-overview.md)
- [Prioritera incidenter](incident-queue.md)
- [Analysera incidenter](investigate-incidents.md)
