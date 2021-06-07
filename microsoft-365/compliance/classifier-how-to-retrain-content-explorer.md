---
title: Så här tränar du en klassificerare i innehållsutforskaren på nytt
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Lär dig hur du ger feedback till en utbildare i Innehållsutforskaren.
ms.openlocfilehash: ef0539a3d474ffecaeac8633b4a58aa068a5c182
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793070"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Så här tränar du en klassificerare i innehållsutforskaren på nytt

En Microsoft 365 trainable classifier är ett verktyg som du kan träna för att känna igen olika typer av innehåll genom att ge det urval att titta på. När du har utbildat dig kan du använda den för att identifiera objekt för tillämpning Office av känslighetsetiketter, principer för kommunikationsefterlevnad och bevarandeetiketter.

I den här artikeln beskrivs hur du förbättrar prestanda för anpassade utbildare och vissa i förväg utbildade klassificerare genom att ge dem ytterligare feedback.

Mer information om de olika typerna av klassificerare finns i [Läs mer om utbildare.](classifier-learn-about.md)

I den här videon får du en snabb sammanfattning av justerings- och omtämtningsprocessen. Du måste fortfarande läsa den här fullständiga artikeln för att få mer information.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a>Behörigheter

Så här kommer du åt klassificerare i Microsoft 365 kompatibilitetscenter:

- Administratörsrollen för efterlevnad eller dataefterlevnad krävs för att utbilda en klassificerare

Du behöver konton med de här behörigheterna för att använda klassificerare i följande scenarier:

- Scenario för bevarandeprincip: Roller för arkiveringshantering och bevarandehantering 

## <a name="overall-workflow"></a>Övergripande arbetsflöde

> [!IMPORTANT]
> Du ger feedback i Innehållsutforskaren om att tillämpa bevarandeprinciper automatiskt Exchange objekt och använder klassificeraren som ett villkor. **Om du inte har någon bevarandeprincip som automatiskt tillämpar en bevarandeetikett på alla Exchange objekt och använder en klassificerare som villkor, slutar du här.**

När du använder dina klassificerare kanske du vill öka precisionen för klassificeringarna som de gör. Det gör du genom att utvärdera kvaliteten på klassificeringarna för objekt som den har identifierat som en matchning eller inte en matchning. När du har gör 30 utvärderingar för en klassificerare krävs den feedbacken och automatiskt omtämnande för sig själv.

Mer information om det övergripande arbetsflödet för att omtämna en klassificerare finns i Processflöde för att [omtämna en klassificerare.](classifier-learn-about.md#retraining-classifiers)

> [!NOTE]
> En klassificerare måste redan ha publicerats och användas innan den kan tränas om.

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Så här tränar du en klassificerare i innehållsutforskaren på nytt

1. Logga in på Microsoft 365 efterlevnadscenter med rollåtkomst för efterlevnadsadministratörer eller säkerhetsadministratörer och öppna **Microsoft 365 dataklassificeringscenter**  >  **för**  >  **innehållsutforskaren för dataklassificering.** 
2. Under listan **Filtrera på etiketter, informationstyper eller kategorier** **expanderar du Utbildande klassificerare.**

> [!IMPORTANT]
> Det kan ta upp till åtta dagar för aggregerade objekt att visas under rubriken för de utbildande klassificerarna.

3. Välj den utbildare som du använde i den automatiska bevarandeprincipen. Det här är den utbildande klassificerare som du kan ge feedback om.

> [!NOTE]
> Om ett objekt har en post i kolumnen **Bevarandeetikett** innebär det att objektet har klassificerats som ett `match` .  Om ett objekt inte har en post i kolumnen **Bevarandeetikett** innebär det att det klassificerades som ett `close match` . Du kan förbättra klassificerarprecisionen mest genom att ge feedback på `close match` objekt. 

4. Välj ett objekt och öppna det.
 
 > [!TIP]
> Du kan ge feedback på flera objekt samtidigt genom att välja alla och sedan välja **Förbättra klassificering** i kommandofältet.

5. Välj **Ge feedback.**
6. I fönstret **Detaljerad feedback** väljer du **Matcha** om objektet är positivt.  Om objektet är en falsk positiv inställning, att det är det som felaktigt inkluderades i kategorin, väljer **du Inte en matchning**.
7. Om det finns en annan klassificerare som är lämpligare för objektet kan du välja det i listan Föreslå andra klassificerare som **kan klassificeras.** Det här utlöser att den andra klassificeraren utvärderar objektet.
8. Välj **Skicka feedback** för att skicka din utvärdering av , `match` `not a match` klassificeringar och föreslå andra utbildare. När du har angett 30 instanser av feedback till en klassificerare kommer den automatiskt att tränas om. Omtämnad kan ta från en till fyra timmar. Klassificerare kan bara omtämnas två gånger per dag.

> [!IMPORTANT]
> Den här informationen går till klassificeraren i klientorganisationen, **den går inte tillbaka till Microsoft.**

9. Öppna **Utbildare som klassificerar**.
10. Den klassificerare som använts i efterlevnadsprincipen för kommunikation visas under **rubriken Omutbildning.**

![klassificerare i omtrainingsstatus](../media/classifier-retraining.png)

11. När du är klar med omtrainningen väljer du klassificeraren för att öppna översikten för omtraining.

![översikt över klassningsresultat](../media/classifier-retraining-overview.png)

12. Granska den rekommenderade åtgärden och förutsägelsejämförelserna för de omtämta och publicerade versionerna av klassificeraren.
13. Om du är nöjd med resultatet av uttröjningen väljer **du Publicera om.**
14. Om du inte är nöjd med resultatet av utträmningen kan du välja att ge ytterligare feedback till klassificeraren i gränssnittet för Innehållsutforskaren och starta en annan omtrainingscykel eller inte göra någonting. I sådant fall används den publicerade versionen av klassificeraren fortsatt. 

## <a name="details-on-republishing-recommendations"></a>Information om att publicera om rekommendationer

Här är lite information om hur vi sammanställer rekommendationen om att publicera om en omtämnad klassificerare eller föreslå ytterligare omtraining. För det krävs lite djupare förståelse för hur utbildande klassificerare fungerar.

Efter en omtrainning utvärderar vi klassificeraren prestanda för både objekten med feedback och de objekt som ursprungligen användes för att utbilda klassificeraren. 

- För inbyggda modeller är objekt som används för att utbilda klassificeraren de objekt som används av Microsoft för att skapa modellen.
- För anpassade modeller kommer objekt som används i den ursprungliga utbildningen som klassificeraren kommer från de webbplatser som du har lagt till för test och granskning.

Vi jämför prestandanumren för båda uppsättningarna med objekt för den omtämnad och publicerade klassificeraren för att ge en rekommendation om huruvida det fanns förbättring av publiceringen på nytt. 

## <a name="see-also"></a>Se även

- [Mer information om utbildningsbara klassificerare](classifier-learn-about.md)
- [Förvalda filnamnstillägg och filtyper som crawlas och analyseras i SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)