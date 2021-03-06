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
ms.openlocfilehash: 53e304dc69ccf2ca6fe01d29f0997c539406b0fe
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768980"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a>Hantera identifiering av ämnen i Microsoft Viva-ämnen

Du kan hantera inställningar för identifiering av ämnen [Microsoft 365 administrationscentret.](https://admin.microsoft.com) Du måste vara global administratör SharePoint administratör för att utföra de här uppgifterna.

## <a name="to-access-topics-management-settings"></a>Så här kommer du åt inställningar för hantering av ämnen:

1. I Microsoft 365 klickar du på **Inställningar** och sedan **på Organisationsinställningar.**
2. Klicka på **Ämnesupplevelser** på **fliken Tjänster.**

    ![Anslut att få kunskap](../media/admin-org-knowledge-options-completed.png) 

3. Välj fliken **Ämnesidentifiering.** I följande avsnitt finns information om de olika inställningarna.

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>Välj SharePoint ämneskällor

Du kan ändra SharePoint webbplatser i organisationen som ska crawlas för ämnen.

Om du vill ta med eller utesluta en viss lista över webbplatser kan du använda följande .csv mall:

``` csv
Site name,URL
```

Om du lägger till webbplatser med hjälp av webbplatsväljaren läggs de till i den befintliga listan över webbplatser som ska inkluderas eller exkluderas. Om du laddar .csv över en befintlig lista kommer den att skriva över alla befintliga listor. Om du tidigare har lagt till eller uteslutit specifika webbplatser kan du och ladda ned listan .csv en fil, göra ändringar och ladda upp den nya listan.

Välja webbplatser för att hitta ämnen

1. På fliken **Ämnesidentifiering** under **Välj SharePoint väljer** du **Redigera**.
2. På sidan **Välj SharePoint ämneskällor** väljer du vilka SharePoint ska crawlas som källor för ämnen under identifieringen. Detta omfattar följande:
    - **Alla webbplatser:** alla SharePoint i klientorganisationen. Då fångar vi aktuella och framtida webbplatser.
    - **Alla, förutom valda webbplatser:** Skriv namnen på de webbplatser som du vill utesluta.  Du kan också ladda upp en lista över webbplatser som du vill avanmäla från identifiering. Webbplatser som skapas i framtiden kommer att ingå som källor för upptäckt av ämnen. 
    - **Endast valda webbplatser**: Skriv namnen på de webbplatser som du vill ska ingå. Du kan också ladda upp en lista med webbplatser. Webbplatser som skapas i framtiden inkluderas inte som källor för ämnesidentifiering.
    - **Inga webbplatser:** Ämnen genereras inte automatiskt eller uppdateras inte med SharePoint innehåll. Befintliga ämnen finns kvar i ämnescentret.

    ![Skärmbild av SharePoint i användargränssnittet för ämneskällor](../media/k-manage-select-topic-source.png)
   
3. Klicka på **Spara**.

## <a name="exclude-topics-by-name"></a>Utesluta ämnen efter namn

Du kan utesluta ämnen från identifiering genom att ladda upp en lista med hjälp av .csv fil. Om du tidigare har uteslutit ämnen kan du ladda ned .csv, göra ändringar och ladda upp det igen.

1. På fliken **Ämnesidentifiering** under **Exkludera ämnen** väljer du **Redigera.**
2. Klicka **på Exkludera ämnen efter namn.**
3. Om du behöver skapa en lista laddar du ned .csv-mallen och lägger till de avsnitt som du inte vill ta med (se Arbeta med *.csv mallen* nedan). När filen är klar klickar du på **Bläddra** och laddar upp filen. Om det finns en befintlig lista kan du ladda ned .csv som innehåller listan.
4. Klicka på **Spara**.

    ![Skärmbild av exkludera ämnen användargränssnittet för ämnen](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>Arbeta med .csv mall

Du kan kopiera CSV-mallen nedan:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

I CSV-mallen anger du följande information om de ämnen som du inte vill ska ingå:

- **Namn**: Skriv namnet på det ämne som du vill utesluta. Du kan göra det på två sätt:
    - Exakt matchning: Du kan utesluta det exakta namnet eller förkortningen (till exempel *Contoso* eller *ATL*).
    - Delvis matchning: Du kan utesluta alla avsnitt som innehåller ett visst ord.  En båge *utesluter* till exempel  alla ämnen som innehåller ordet båge, t.ex. arcuscirkel,  *Arcus* arcus- eller *utbildningsbåge.* Observera att den inte exkluderar ämnen där texten ingår i ett ord, till exempel *Arkitektur.*
- **Står för (valfritt)**: Om du vill utesluta en förkortning skriver du orden förkortningen står för.
- **MatchType-Exact/Partial**: Ange om namnet du angav var en *exakt eller* *delvis* matchningstyp.

    ![Utesluta ämnen i CSV-mallen](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>Se även

[Hantera synligheten för ämnen i Microsoft 365](topic-experiences-knowledge-rules.md)

[Hantera ämnesbehörigheter i Microsoft 365](topic-experiences-user-permissions.md)

[Ändra namnet på ämnescentret i Microsoft 365](topic-experiences-administration.md)
