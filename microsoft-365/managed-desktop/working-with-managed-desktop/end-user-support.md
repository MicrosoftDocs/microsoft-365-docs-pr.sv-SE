---
title: Få användarsupport för Microsoft Hanterat skrivbord
description: Hur användare kan få hjälp med tjänsten och enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362623"
---
# <a name="getting-help-for-users"></a>Få hjälp för användare

Om du har kommit till [](../service-description/user-support.md) den punkt i arbetsflödet där du behöver begära utökad enhetsåtkomst eller eskalering till Microsoft gör du så här:
 
>[!NOTE]
>De här supportalternativen är inte tillgängliga för enheter i testgruppen.

## <a name="elevation-requests"></a>Höjdbegäranden

Innan du begär utökad åtkomst till en enhet bör du kontrollera vilka åtgärder som passar bäst.

- **Vanliga åtgärder** är vad den här processen är avsedd för och som utförs regelbundet medan problem med e-Microsoft Hanterat skrivbord felsöks. Några exempel:
    - Höja upp inbyggda systemfelsökare, kommandotolken eller Windows PowerShell
    - Felsöka verksamhetsbaserade program
    - Använda en lösning för att korrigera något som ska fungera enligt design (t.ex. BitLocker-aktivering eller systemtid som inte uppdateras)
    - Elevating Device Manager to do things like update drivers, uninstall a device, or scan for new changes

- **Åtgärder som inte rekommenderas** är bland annat följande:
    - Installera programvara eller webbläsare
    - Installera drivrutiner utanför Windows, inklusive för kringutrustning
    - Installera .msi eller .exe filer
    - Installera Windows funktioner

- **Åtgärder som inte stöds** är bland annat följande:
    - Installera programvara eller funktioner som står i konflikt Microsoft Hanterat skrivbord säkerhets- eller hanteringsfunktioner eller -åtgärder
    - Inaktivera en Windows som krävs för Microsoft Hanterat skrivbord, till exempel BitLocker
    - Ändra inställningar som hanteras av din organisation

### <a name="to-request-elevation"></a>Begära höjd

1. Gå till portalen och [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) logga in med dina inloggningsuppgifter Azure Active Directory autentiseringsuppgifter.
2. Välj **Ny begäran om höjd**.
3. Ange följande information:
    - **Support ticket ID** from your own support ticketing system.
    - **Enhetsnamn**: ange enhetens serienummer och välj sedan enheten på menyn.
    - **Kategori:** Välj den kategori som bäst passar ditt problem. Om inget alternativ verkar vara nära väljer du **Annat** och ger mer information i **fälten** Rubrik och Plan **för** åtgärder. Det är bäst att välja en kategori om det är möjligt.
    - **Underkategori:** Välj den som passar bäst för problemet. Om inget alternativ verkar vara nära väljer du **Annat** och ger en kort beskrivning i **Rubrik**. Ange **de felsökningssteg** du planerar att vidta när höjd beviljas i Planera för åtgärd.
4. Välj **Skicka**.


## <a name="escalation-requests"></a>Eskaleringsförfrågningar


Om du behöver [eskalera ett](../service-description/user-support.md#escalation-portal) problem till Microsoft gör du så här:

1. Gå till portalen och [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) logga in med dina inloggningsuppgifter Azure Active Directory autentiseringsuppgifter.
2. Välj **Eskaleringsförfrågningar** och välj sedan **Ny eskaleringsbegäran**.
3. Ange följande information:
    - **Kategori:** Välj den kategori som bäst passar ditt problem.
    - **Rubrik**: Ge en mycket kort beskrivning.
    - **Beskrivning**: Lägg till ytterligare information som kan hjälpa vårt team att förstå problemet. Om du behöver bifoga filer kan du göra det genom att komma tillbaka till begäran efter att du skickat den.
    - **Primär kontaktinformation:** Ange information om hur du kontaktar huvudpersonen som ansvarar för att arbeta med vårt team.
4. Välj **Skicka**.
5. Gå tillbaka till biljetten i samma portal för att interagera med vårt team.

> [!NOTE]
> Endast problem med allvarlighetsgrad C kan eskaleras genom den här vägen. Om det är andra problem kontaktar du IT-administratören och arkiverar begäran via administratörsportalen.