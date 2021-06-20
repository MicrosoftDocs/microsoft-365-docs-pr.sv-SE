---
title: Använda en kvarhållningsetikett på en modell för dokumenttolkning i Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Diskutera hur man tillämpar en kvarhållningsetikett på en modell i SharePoint Syntex.
ms.openlocfilehash: ebcd398799e7c8addd96d5941427628d3db5ad43
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028949"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-sharepoint-syntex"></a>Använda en kvarhållningsetikett på en modell för dokumenttolkning i Microsoft SharePoint Syntex

Du kan enkelt använda en [känslighetsetikett](../compliance/sensitivity-labels.md) på modeller för dokumenttolkning i Microsoft SharePoint Syntex. Den här funktionen är inte tillgänglig ännu för modeller för formulärbearbetning.

Med känslighetsetiketter kan du tillämpa krypterings-, delnings- och villkorsstyrda principer på de dokument som modeller identifierar. Du vill till exempel att modellen inte bara ska identifiera finansiella dokument som innehåller bankkontonummer eller kreditkortsnummer som laddas upp till ditt dokumentbibliotek, utan även använda en *-krypteringsetikett* för att begränsa vem som kan komma åt innehållet och hur det kan användas. SharePoint Syntex-modeller följer [etikettordning](../compliance/apply-sensitivity-label-automatically.md?view=o365-worldwide#how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label) regler och skriver inte heller över en befintlig etikett som tillämpades manuellt av en användare i filen. 

Du kan använda en befintlig känslighetsetikett på modellen för dokumenttolkning i modellinställningarna på modellens startsida. Etiketten måste redan vara publicerad för att vara tillgänglig för val från modellinställningar.

> [!Important]
> För att känslighetsetiketterna ska vara tillgängliga att använda på din modell för innehållstolkning måste de [skapas och publiceras i Microsoft 365 Efterlevnadscenter](../business-video/create-sensitivity-labels.md).

## <a name="add-a-sensitivity-label-to-a-document-understanding-model"></a>Lägg till en känslighetsetikett på modeller för dokumenttolkning

1. På modellens startsida väljer du **Modellinställningar**.

   ![Skärmbild av sidan Modeller med alternativet Modellinställningar markerat.](../media/content-understanding/sensitivity-model-settings.png)

2. I fönstret **Modellinställningar**, i avsnittet **Efterlevnad**, väljer du menyn **Känslighetsetikett** för en lista över de känslighetsetiketter som finns tillgängliga att använda på modellen.

   ![Skärmbild av fönstret Modellinställningar med menyn för känslighetsetiketter.](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. Välj den känslighetsetikett som du vill använda för modellen och sedan **Spara**.

När du har tillämpat känslighetsetiketten på modellen kan du använda den på en:

- Ett nytt dokumentbibliotek
- Ett dokumentbibliotek som modellen redan används för
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Använd känslighetsetiketten på ett dokumentbibliotek som modellen redan används för

Om modellen för dokumenttolkning redan har använts på ett dokumentbibliotek kan du göra följande för att synkronisera din uppdatering av känslighetsetiketten så att den används på dokumentbiblioteket:

1. På modellens startsida, i avsnittet **Bibliotek med den här modellen** väljer du det dokumentbibliotek på vilket du vill använda uppdateringen av känslighetsetiketten.

2. Välj **Synkronisera**.

   ![Skärmbild som visar Bibliotek med den här modelldelen med Synkronisera markerat.](../media/content-understanding/sensitivity-libraries-sync.png)

Efter tillämpning av uppdateringen och synkronisering med modellen kan du kontrollera att den har använts genom att göra följande:

1. I innehållscentret går du till avsnittet **Bibliotek med den här modellen**. Välj det bibliotek där din uppdaterade modell används. 

2. I vyn dokumentbibliotek väljer du informationsikonen för att kontrollera modellens egenskaper.

3. I listan över **Aktiva modeller** väljer du den uppdaterade modellen.

4. I avsnittet **Känslighetsetikett** visas namnet på den använda känslighetsetiketten.

På modellens visningssida i dokumentbiblioteket visas en ny kolumn för **Känslighetsetikett**. Allt eftersom modellen klassificerar filer som tillhör dess innehållstyp och listar dem i biblioteksvyn, visar kolumnen **Känslighetsetikett** också namnet på den känslighetsetikett som har använts på den genom modellen.

Till exempel kommer alla finansiella dokument som din modell identifierar även att få en etikett för *Kryptering* och hindra dem från att användas av obehöriga personer. Om någon obehörig försöker komma åt filen från dokumentbiblioteket visas ett felmeddelande om att det inte är tillåtet eftersom känslighetsetiketten används.

<!---
## Add a sensitivity label to a form processing model

> [!Important]
> For sensitivity labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).

You can either apply a sensitivity label to a form processing model when you are creating a model, or apply it to an existing model.

### Add a sensitivity label when you create a form processing model

1. When you [create a new form processing model](create-a-form-processing-model.md), select **Advanced settings**.

2. In **Advanced settings**, in the **Sensitivity label** section, select the menu and then select the sensitivity label you want to apply to the model.

3.  After you've completed your remaining model settings, select **Create** to build your model.

### Add a sensitivity label to an existing form processing model

You can add a sensitivity label to an existing form processing model in different ways:

- Through the **Automate** menu in the document library
- Through the **Active model** settings in the document library 

#### Add a sensitivity label to an existing form processing model through the Automate menu

You can add a sensitivity label to an existing form processing model that you own through the **Automate** menu in the document library in which the model is applied.

1. In your document library to which the form processing model is applied, select the **Automate** menu, select **AI Builder**, and then select **View form processing model details**.

2. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

#### Add a sensitivity label to an existing form processing model in the active model settings

You can add a sensitivity label to an existing form processing model that you own through the **Active model** settings in the document library in which the model is applied.

1. In the SharePoint document library in which the model is applied, select the **View active models** icon, and then select **View active models**.

2. In **Active models**, select the form processing model to which you want to apply the sensitivity label.

3. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

   > [!NOTE]
   > You must be the model owner for the **Model settings** pane to be editable. 
--->

## <a name="see-also"></a>Se även

[Använda en kvarhållningsetikett](apply-a-retention-label-to-a-model.md)

[Skapa en klassificerare](create-a-classifier.md)

[Skapa en extraktor](create-an-extractor.md)

[Översikt av dokumenttolkning](document-understanding-overview.md)
