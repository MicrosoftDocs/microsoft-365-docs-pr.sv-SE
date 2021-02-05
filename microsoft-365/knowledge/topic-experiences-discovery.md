---
title: Hantera identifiering av ämnen i Microsoft Viva-ämnen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Lär dig hur du administrerar ämnesidentifiering i Microsoft Viva-ämnen.
ms.openlocfilehash: 36b64433726479dc2a46c809ae9504c6f12f4ab8
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107771"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a>Hantera identifiering av ämnen i Microsoft Viva-ämnen

Du kan hantera inställningar för identifiering av ämnen i administrationscentret för [Microsoft 365.](https://admin.microsoft.com) Du måste vara global administratör eller SharePoint-administratör för att kunna utföra de här uppgifterna.

## <a name="to-access-topics-management-settings"></a>Så här kommer du åt inställningar för hantering av ämnen:

1. Klicka på Inställningar och sedan Organisationsinställningar i **administrationscentret** **för** Microsoft 365.
2. Klicka på **Ämnesupplevelser** på **fliken Tjänster.**

    ![Koppla samman personer med kunskap](../media/admin-org-knowledge-options-completed.png) 

3. Välj fliken **Ämnesidentifiering.** I följande avsnitt finns information om de olika inställningarna.

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>Välj SharePoint-ämneskällor

Du kan ändra vilka SharePoint-webbplatser i organisationen som ska crawlas för ämnen.

Om du vill ta med eller utesluta en viss lista med webbplatser kan du använda följande CSV-mall:

``` csv
Site name,URL
```

Om du lägger till webbplatser med hjälp av webbplatsväljaren läggs de till i den befintliga listan med webbplatser som ska inkluderas eller undantas. Om du laddar upp en CSV-fil kommer den att skriva över alla befintliga listor. Om du tidigare har tagit med eller uteslutit specifika webbplatser kan du ladda ned listan som en CSV-fil, göra ändringar och ladda upp den nya listan.

Välja webbplatser för ämnesidentifiering

1. Välj Redigera **under Välj** SharePoint-ämneskällor **på fliken** Ämnesidentifiering. 
2. På sidan **Välj SharePoint-ämneskällor** väljer du vilka SharePoint-webbplatser som ska crawlas som källor för ämnen under identifieringen. Det omfattar:
    - **Alla webbplatser**: Alla SharePoint-webbplatser i klientorganisationen. Detta fångar aktuella och framtida webbplatser.
    - **Alla, förutom valda webbplatser:** Skriv namnen på de webbplatser som du vill utesluta.  Du kan också ladda upp en lista över webbplatser som du vill avanmäla från identifiering. Webbplatser som skapas i framtiden kommer att ingå som källor för identifiering av ämnen. 
    - **Endast valda webbplatser:** Skriv namnen på de webbplatser som du vill ska ingå. Du kan också ladda upp en lista med webbplatser. Webbplatser som skapas i framtiden kommer inte att inkluderas som källor för identifiering av ämnen.
    - **Inga webbplatser:** Ämnen genereras eller uppdateras inte automatiskt med SharePoint-innehåll. Befintliga ämnen finns kvar i ämnescentret.

    ![Skärmbild av användargränssnittet för SharePoint-ämneskällor](../media/k-manage-select-topic-source.png)
   
3. Klicka på **Spara**.

## <a name="exclude-topics-by-name"></a>Utesluta ämnen efter namn

Du kan utesluta ämnen från identifiering genom att ladda upp en lista med hjälp av en CSV-fil. Om du tidigare har uteslutit ämnen kan du ladda ned CSV-filen, göra ändringar och ladda upp den igen.

1. Välj Redigera **under Exkludera ämnen** på fliken Ämnesidentifiering. 
2. Klicka **på Exkludera ämnen efter namn.**
3. Om du behöver skapa en lista laddar du ned CSV-mallen och lägger till de ämnen du vill utesluta (se Arbeta med *CSV-mallen* nedan). När filen är klar klickar du på **Bläddra** och laddar upp filen. Om det finns en befintlig lista kan du ladda ned CSV-filen som innehåller listan.
4. Klicka på **Spara**.

    ![Skärmbild av användargränssnittet för uteslutning av ämnen](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>Arbeta med CSV-mallen

Du kan kopiera CSV-mallen nedan:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

I CSV-mallen anger du följande information om de ämnen du vill utesluta:

- **Namn:** Skriv namnet på det ämne som du vill utesluta. Du kan göra det på två sätt:
    - Exakt matchning: Du kan ta med det exakta namnet eller förkortningen (till exempel *Contoso* eller *ATL).*
    - Delvis matchning: Du kan utesluta alla ämnen som innehåller ett visst ord.  En båge *utesluter* till exempel  alla ämnen där ordet båge finns, t.ex. arcuscirkel, arcus-arcus- eller *utbildningsbåge.*  Observera att den inte exkluderar ämnen där texten ingår som en del av ett ord, till exempel *arkitektur.*
- **Står för (valfritt)**: Om du vill utesluta en förkortning skriver du orden som förkortningen står för.
- **MatchType-Exact/Partial:** Ange om namnet du angav var en *exakt eller* *delvis* matchningstyp.

    ![Utesluta ämnen i CSV-mall](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>Se även

[Hantera synlighet för ämnen i Microsoft 365](topic-experiences-knowledge-rules.md)

[Hantera ämnesbehörigheter i Microsoft 365](topic-experiences-user-permissions.md)

[Ändra namnet på ämnescentret i Microsoft 365](topic-experiences-administration.md)
