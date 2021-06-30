---
title: Stänga eller ta bort ett ärende
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Ta reda på vad som händer när en undersökning eller ett juridiskt ärende som stöds Advanced eDiscovery ett ärende stängs eller tas bort.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: efbcbe34e6d7d8b564bcfa0cf9bbd8a1fbb59709
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194638"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Stänga eller ta bort ett Advanced eDiscovery ärende

Om det juridiska ärende eller den juridiska undersökningen som stöds Advanced eDiscovery slutföras kan du stänga eller ta bort ett ärende. Du kan också öppna ett stängt ärende igen.

## <a name="close-a-case"></a>Stänga ett ärende

Följande händer när du stänger ett Advanced eDiscovery ärende:

- Om ärendet innehåller platser där innehåll är spärrat inaktiveras de. När vänttiden är inaktiverad tillämpas en respitperiod på 30 dagar (kallas för *fördröjning)* på platser som var i väntläge. Det här förhindrar att innehåll tas bort omedelbart, och administratörer kan söka efter eller återställa innehåll som tas bort permanent efter att fördröjningsperioden förfaller. Mer information finns i Ta [bort innehållsplatser från en eDiscovery-plats.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)

- Om du stänger ett ärende inaktiveras bara det som är kopplat till det aktuella ärendet. Om andra innehåll sätts på en plats (t.ex. bevarande av juridiska skäl, bevarande av bas för eDiscovery eller ett bevarande från ett annat Advanced eDiscovery ärende) kommer de innehållna innehållet fortfarande att bibehållas.

- Ärendet finns fortfarande kvar på sidan eDiscovery i Microsoft 365 Efterlevnadscenter. Informationen, som sätts i spärrade fall, sökningar och medlemmar i ett stängt ärende bevaras.

- Du kan redigera ett ärende när det har stängts. Du kan till exempel lägga till eller ta bort medlemmar, skapa sökningar, exportera sökresultat och förbereda sökresultat för analys i Advanced eDiscovery. Den största skillnaden mellan aktiva och stängda ärenden är att kvarstad är inaktiverad när ett ärende stängs.

Så här stänger du ett ärende:

1. På **Advanced eDiscovery** sidan väljer du det ärende du vill stänga.

2. På fliken **Inställningar,** under **Ärendeinformation,** klickar du på **Välj**.

   ![Öppna den utfällingssidan med ärendeinformation i Advanced eDiscovery ärende](..\media\AeDSelectCaseInformation.png) 

3. Längst ned på den **utfällade** sidan Ärendeinformation klickar du **på Åtgärder** och sedan **på Stäng ärende.**

   Det kan ta upp till 60 minuter innan avslutsprocessen slutförs.

## <a name="reopen-a-closed-case"></a>Öppna ett stängt ärende igen

När du öppnar Advanced eDiscovery återöppnar ett ärende kommer eventuella kvarhåller som fanns när ärendet stängdes inte att återställas automatiskt. När ärendet har öppnats på nytt måste du gå till fliken **Spärrar** och aktivera tidigare kvartr. Om du vill aktivera ett väntande objekt markerar du det så att den utfäll sida visas och ställer sedan in **statusreglaget** på **På**.

Så här öppnar du ett stängt ärende:

1. På **Advanced eDiscovery** väljer du det ärende som du vill öppna igen.

2. På fliken **Inställningar,** under **Ärendeinformation,** klickar du på **Välj**.

3. Längst ned på den **utfällade sidan** Ärendeinformation klickar du på **Åtgärder** och sedan på **Öppna ärendet igen.**

   Det kan ta upp till 60 minuter innan återöppnandeprocessen slutförs.

## <a name="delete-a-case"></a>Ta bort ett ärende

Du kan ta bort både aktiva och stängda Advanced eDiscovery fall. När du tar bort ett ärende tas alla komponenter som är associerade med ärendet bort, till exempel listan över biblioteksarier, kommunikationer, sökningar, granskningsuppsättningar och exportjobb. Ärendet tas bort från listan med ärenden på **Advanced eDiscovery** i Microsoft 365 Efterlevnadscenter. Du kan inte återskapa eller öppna ett borttagna ärende.

> [!NOTE]
> Vid data spill är det enda sättet att ta bort objekt i en granskningsuppsättning att ta bort det Advanced eDiscovery fall. Andra "söknings- och rensningsmetoder" tar inte bort objekt från en granskningsuppsättning.

Innan du kan ta bort ett ärende (oavsett om det är aktivt eller stängt) måste du först ta bort *allt* som är kopplat till ärendet. Det omfattar borttagning av filer som har statusen **Av.**

Så här tar du bort spärrade objekt som är kopplade till ett ärende:

1. Gå till **fliken** Spärrar i det Advanced eDiscovery ärende som du vill ta bort.

2. Klicka på det håll du vill ta bort.

3. Klicka på Ta bort håll på den **utfällade sidan.**

Så här tar du bort ett ärende:

1. På **Advanced eDiscovery** väljer du det ärende du vill ta bort.

2. På fliken **Inställningar,** under **Ärendeinformation,** klickar du på **Välj**.

3. Längst ned på den **utfällade sidan** Ärendeinformation klickar du på **Åtgärder** och sedan på Ta **bort ärende.**

