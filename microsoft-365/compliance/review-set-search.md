---
title: Skapa en fråga för innehållet i en granskningsuppsättning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Lär dig hur du skapar och kör en fråga i en granskningsuppsättning för att ordna innehåll för en effektivare granskning i Advanced eDiscovery ärende.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64dbeb8ad68f4188e5768a0a7e0e80ca6c22760b
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736457"
---
# <a name="query-and-filter-content-in-a-review-set"></a>Fråga och filtrera innehåll i en granskningsuppsättning

I de flesta fall kan det vara bra att gå djupare in på innehållet i en granskningsuppsättning och ordna den för att underlätta en effektivare granskning. Om du använder filter och frågor i en granskningsuppsättning kan du fokusera på en delmängd dokument som uppfyller villkoren för din granskning.

## <a name="default-filters"></a>Standardfilter

I en granskningsuppsättning finns det fem standardfilter som är förinstallerade i granskningsuppsättningen:

- Nyckelord
- Datum
- Avsändare/författare
- Ämne/rubrik
- Taggar

![Standardfiltertyper](../media/DefaultFilterTypes.png)

Klicka på varje filter för att expandera det och tilldela ett värde. Klicka utanför filtret så tillämpas filtret automatiskt på granskningsuppsättningen. Följande skärmbild visar det datumfilter som har konfigurerats för att visa dokument inom ett datumintervall.

![Standardfilter expanderat](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a>Lägga till eller ta bort filter

Om du vill lägga till eller ta  bort filter som visas för granskningsuppsättningen väljer du Filter för att öppna filterpanelen, som visas på en utfällbladssida. 

![Filterpanel](../media/FilterPanel.png)

De tillgängliga filtren är ordnade i fyra avsnitt:

- **Sök:** Filter som ger olika sökfunktioner.

- **Analys &** förutsägelsekodning: Filter för egenskaper som genereras och läggs till i dokument när du kör dokumentet & e-postanalysjobb eller använder prediktiv kodningsmodeller. 

- **ID:n:** Filter för alla ID-egenskaper för dokument.

- **Objektegenskaper:** Filter för dokumentegenskaper. 

Expandera varje avsnitt och markera eller avmarkera filter för att lägga till eller ta bort dem i filteruppsättningen. När du lägger till ett filter visas det i filteruppsättningen. 

![Lista över filteravsnitt och egenskaper i filterpanelen](../media/FilterPanel2.png)

> [!NOTE]
> När du expanderar ett avsnitt i filterpanelen märker du att standardfiltertyperna är markerade. Du kan behålla dessa markerade eller avmarkera dem och ta bort dem från filteruppsättningen. 

## <a name="filter-types"></a>Filtertyper

Alla sökbara fält i en granskningsuppsättning har ett motsvarande filter som du kan använda för att filtrera objekt baserat på ett visst fält.

Det finns flera typer av filter:

- **Fritext**: Ett fritextfilter används på textfält som exempelvis "Ämne". Du kan lista flera sökord genom att avgränsa dem med kommatecken.

- **Datum:** Ett datumfilter används för datumfält som "Senast ändrad, datum".

- **Sökalternativ:** Ett sökalternativfilter ger en lista med möjliga värden (varje värde visas med en kryssruta som du kan välja) för vissa fält i granskningen. Filtret används för fält, till exempel "Avsändare", där det finns ett ändlig antal möjliga värden i granskningsuppsättningen.

- **Nyckelord:** Ett nyckelordsvillkor är en specifik instans av fritextvillkor som du kan använda för att söka efter termer. Du kan också använda KQL-liknande frågespråk i den här typen av filter. Mer information finns i avsnitten Frågespråk och Avancerat frågeverktyg i det här avsnittet.

## <a name="include-and-exclude-filter-relationships"></a>Inkludera och exkludera filterrelationer

Du kan ändra inkludera- och exkludera-relationen för ett visst filter. I filtret Taggar kan du till exempel utesluta objekt som är märkta med en viss tagg genom att välja **Är lika** med inget av i listrutan. 

![Exkludera taggfilter](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a>Spara filter som frågor

När du är nöjd med dina filter kan du spara filterkombinationen som en filterfråga. Då kan du använda filtret i kommande granskningssessioner.

Om du vill spara ett filter **väljer du Spara frågan** och ge den ett namn. Du eller andra granskare kan köra tidigare sparade filterfrågor genom att välja listrutan Sparade filterfrågor och välja en filterfråga att tillämpa på dokument som **angetts.** 

![Spara en filterfråga](../media/SaveFilterQuery.png)

Om du vill ta bort en filterfråga öppnar du filterpanelen och väljer papperskorgsikonen bredvid frågan.

![Ta bort en filterfråga](../media/DeleteFilterQuery.png)

## <a name="query-language"></a>Frågespråk

Förutom att använda filter kan du också använda ett KQL-liknande frågespråk i filtret Nyckelord för att skapa din frågeuppsättning. Frågespråket för granskningsuppsättningsfrågor har stöd för booleska standardoperatorer som **AND,** **OR,** **NOT** och **NEAR.** Det har också stöd för ett jokertecken (?) och ett jokertecken (*).

## <a name="advanced-query-builder"></a>Avancerat frågeverktyg

Du kan också skapa mer avancerade frågor för att söka efter dokument i en granskningsuppsättning.

1. Öppna filterpanelen, välj **Filter** och expandera **avsnittet** Sök.

  ![Lägga till ett KQL-filter](../media/AddKQLFilter.png)

2. Välj **KQL-filtret** och klicka på **Öppna frågeverktyget**.

   I den här panelen kan du skapa komplexa KQL-frågor med hjälp av frågeverktyget. Du kan lägga till villkor eller villkorsgrupper som består av flera villkor som är logiskt sammankopplade av **OCH-** eller **ELLER-relationer.**

   ![Använda frågeverktyget för att konfigurera komplexa filterfrågor](../media/ComplexQuery.png)
