---
title: Kom igång med utbildningsbara klassificerare
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: En Microsoft 365 är ett verktyg som du kan utbilda dig för att identifiera olika typer av innehåll genom att ge den exempel att titta på. I den här artikeln beskrivs hur du skapar och utbildar en anpassad klassificerare och hur du utbildar dem för ökad precision.
ms.openlocfilehash: 90e47ec94528bbadeb98dc9eb590929e25ae6ff1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162018"
---
# <a name="get-started-with-trainable-classifiers"></a>Kom igång med utbildningsbara klassificerare

En Microsoft 365 trainable classifier är ett verktyg som du kan träna för att känna igen olika typer av innehåll genom att ge det urval att titta på. När du har utbildat dig kan du använda den för att identifiera objektet för tillämpning av Office känslighetsetiketter, principer för kommunikationsefterlevnad och bevarandeetiketter.

Om du skapar en egen utbildare för att klassificera den först ingår att ge det urval som människor har valt och som matchar kategorin positivt. När de har bearbetats testar du sedan möjligheten att förutsäga klassificerarna genom att ge den en blandning av positiva och negativa prover. I den här artikeln beskrivs hur du skapar och utbildar en anpassad klassificerare och hur du förbättrar prestanda för anpassade utbildare och föranpassade klassificerare under deras livstid genom omsämring.

Mer information om de olika typerna av klassificerare finns i [Läs mer om utbildare.](classifier-learn-about.md)

Titta på den här videon för en snabb sammanfattning av hur du skapar en utbildande klassificerare. Du måste fortfarande läsa den här fullständiga artikeln för att få mer information.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a>Förutsättningar

### <a name="licensing-requirements"></a>Licenskrav

Klassificerare är en funktion Microsoft 365 E5 regelefterlevnad eller E5-efterlevnad. Du måste ha en av dessa prenumerationer för att kunna använda dem.

### <a name="permissions"></a>Behörigheter

Så här kommer du åt klassificerare i användargränssnittet: 

- Den globala administratören måste registrera sig för klientorganisationen för att skapa anpassade klassificerare.
- Efterlevnadsadministratörsroll krävs för att utbilda en klassificerare.

Du behöver konton med de här behörigheterna för att använda klassificerare i följande scenarier:

- Scenario för bevarandeprincip: Roller för arkiveringshantering och bevarandehantering 
- Scenario för känslighetsetikettsprincip: Säkerhetsadministratör, efterlevnadsadministratör, efterlevnadsdataadministratör
- Scenario: Scenario för kommunikationsefterlevnadspolicy: Insider-riskhanteringsadministratör, övervakande granskningsadministratör 

> [!IMPORTANT]
> Som standard kan endast den användare som skapar en anpassad klassificerare utbilda och granska prognoser som gjorts av den klassificeraren.

## <a name="prepare-for-a-custom-trainable-classifier"></a>Förbereda en egen utbildare 

Det är bra att förstå vad som ingår i att skapa en egen utbildare innan du dyker ned. 

### <a name="timeline"></a>Tidslinje

Den här tidslinjen återspeglar ett exempel på distribution av utbildande klassificerare.

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> Avanmälning krävs första gången för utbildare. Det tar tolv dagar Microsoft 365 att slutföra en baslinjeutvärdering av organisationens innehåll. Kontakta din globala administratör för att starta processen med att anmäla dig.

### <a name="overall-workflow"></a>Övergripande arbetsflöde

Mer information om det övergripande arbetsflödet för att skapa anpassade utbildare finns i Processflöde för att skapa anpassade klassificerare som [kan klassificeras av kunder.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)

### <a name="seed-content"></a>Startinnehåll

När du vill att en utbildare ska klassificera ett objekt oberoende av varandra och korrekt identifiera det som en viss kategori av innehåll måste du först presentera det med många exempel på den typ av innehåll som ingår i kategorin. Denna matning av prover till den utbildande klassificeraren kallas för *ifogning*. Lägga till innehåll väljs av en person och ska nu representera innehållskategorin.

> [!TIP]
> Du måste ha minst 50 positiva tal och upp till 500. Den utbildande klassificeraren bearbetar upp till de 500 senaste skapade exemplen (som skapas av filen som skapats med datum- och tidsstämpeln). Ju fler exempel du anger, desto mer exakta är de prognoser som klassificeraren gör.

### <a name="testing-content"></a>Testa innehåll

När den utbildande klassificeraren har hanterat tillräckligt positiva prover för att skapa en prognosmodell måste du testa de prognoser som den gör för att se om klassificeraren på ett korrekt sätt kan skilja mellan objekt som matchar kategorin och objekt som inte har det. Det gör du genom att välja en annan, förhoppningsvis större, uppsättning människor som har hämtats innehåll som består av prover som bör gå in i kategorin och exempel som inte kommer att det. Du bör testa med andra data än de ursprungliga startdata som du angav först. När de har hanterats går du manuellt igenom resultatet och kontrollerar om varje prognos är korrekt, felaktig eller osäker. Den utbildande klassificeraren använder den här feedbacken för att förbättra sin prognosmodell.

> [!TIP]
> För bästa resultat bör du ha minst 200 objekt i testuppsättningen med en jämn fördelning av positiva och negativa matchningar.

## <a name="how-to-create-a-trainable-classifier"></a>Så här skapar du en utbildare

1. Samla in mellan 50–500 startinnehållsobjekt. Det får endast vara exempel som verkligen representerar den typ av innehåll som du vill att den utbildande klassificeraren ska identifiera som i klassificeringskategorin. Se [Filnamnstillägg och filtyper som crawlas som](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) standard i SharePoint server för filtyper som stöds.

   > [!IMPORTANT]
   > Start- och testobjekt får inte krypteras och måste vara på engelska.

   > [!IMPORTANT]
   > Kontrollera att elementen i startuppsättningen **är starka** exempel på kategorin. Den utbildande klassificeraren skapar först sin modell baserat på vad du tillskriver den. Klassificeraren antar att alla startprov är starka positiva tal och det går inte att se om ett sampel är en svag eller negativ matchning för kategorin.

2. Placera startinnehållet i en SharePoint Online-mapp som är avsedd att endast *hålla startinnehåll.* Notera URL-adressen till webbplatsen, biblioteket och mappen.

   > [!TIP]
   > Om du skapar en ny webbplats och mapp för dina startdata bör du tillåta minst en timme för indexeringen av platsen innan du skapar den trainable-klassificerare som använder dessa tillåtna data.

3. Logga in på Microsoft 365 efterlevnadscenter med rollåtkomst för efterlevnadsadministratörer eller säkerhetsadministratörer och öppna **Microsoft 365** eller **Microsoft 365 säkerhetscenter**  >  **Dataklassificering.**

4. Välj **fliken Utbildare.**

5. Välj **Skapa utbildare .**

6. Fyll i lämpliga värden för och fälten för kategorin objekt som du vill att den här `Name` `Description` utbildande klassificeraren ska identifiera.

7. Välj URL SharePoint för onlinewebbplats, bibliotek och mapp för startinnehållswebbplatsen från steg 2. Välj `Add` .

8. Granska inställningarna och välj `Create trainable classifier` .

9. Inom 24 timmar bearbetar den utbildande klassificeraren startdata och skapar en prognosmodell. Klassificerarstatusen är när `In progress` den bearbetar startdata. När klassificeraren har bearbetat startdata ändras statusen till `Need test items` .

10. Du kan nu visa informationssidan genom att välja klassificeraren.

    > [!div class="mx-imgBorder"]
    > ![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)

11. Samla in minst 200 testinnehållsobjekt (10 000 max) för bästa resultat. Det bör vara en blandning av objekt som är starka positiva, starka negativa och vissa som till sin natur är lite mindre uppenbara. Se [Filnamnstillägg och filtyper som crawlas som](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) standard i SharePoint server för filtyper som stöds.

    > [!IMPORTANT]
    > Exempelobjekten får inte krypteras och måste vara på engelska.

12. Placera testinnehållet i en mapp SharePoint online som endast ska användas för *att hålla testinnehållet.* Notera URL-adressen SharePoint Online, bibliotek och mapp.

    > [!TIP]
    > Om du skapar en ny webbplats och mapp för dina testdata ska det ta minst en timme innan den platsen indexeras innan du skapar den trainable-klassificerare som använder dessa startdata.

13. Välj `Add items to test` .

14. Välj URL SharePoint för webbplatsen, biblioteket och mappen Online för testinnehållswebbplatsen från steg 12. Välj `Add` .

15. Slutför guiden genom att välja `Done` . Det tar upp till en timme innan testfilerna bearbetas med din utbildare.

16. När den utbildande klassificeraren har bearbetat dina testfiler ändras statusen på informationssidan till `Ready to review` . Om du behöver öka testprovstorleken väljer och tillåter du att den utbildande `Add items to test` klassificeraren bearbetar de ytterligare objekten.

    > [!div class="mx-imgBorder"]
    > ![skärmbild som är klar att granskas](../media/classifier-trainable-ready-to-review-detail.png)

17. Välj `Tested items to review` flik för att granska objekt.

18. Microsoft 365 med 30 objekt åt gången. Granska dem och välj ett `We predict this item is "Relevant". Do you agree?` eller `Yes` eller i `No` `Not sure, skip to next item` rutan. Modellprecisionen uppdateras automatiskt efter var 30:e post.

    > [!div class="mx-imgBorder"]
    > ![rutan granska objekt](../media/classifier-trainable-review-detail.png)

19. Granska *minst* 200 objekt. När korrekthetsresultatet har visats blir **publiceringsalternativet** tillgängligt och det visas som klassificerares `Ready to use` status.

    > [!div class="mx-imgBorder"]
    > ![precisionspoäng och redo att publiceras](../media/classifier-trainable-review-ready-to-publish.png)

20. Publicera klassificeraren.

21. När du publicerat din klassificerare blir tillgänglig som ett villkor [i Office](apply-sensitivity-label-automatically.md)automatisk märkning med känslighetsetiketter [tillämpar](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) du bevarandeprincip automatiskt utifrån ett villkor och i [kommunikationsefterlevnad.](communication-compliance.md)