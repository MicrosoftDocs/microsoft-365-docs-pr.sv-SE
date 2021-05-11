---
title: Stäng, öppna och ta bort core eDiscovery-ärenden
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: I den här artikeln beskrivs hur du hanterar grundläggande eDiscovery-ärenden. Det handlar bland annat om att stänga ett ärende, öppna ett stängt ärende och ta bort ett ärende.
ms.openlocfilehash: 251ca932954071cf949c45343130f122464dcf01
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310902"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a>Stäng, öppna och ta bort en eDiscovery-basfall

I den här artikeln beskrivs hur du stänger, öppnar och tar bort grundläggande eDiscovery-ärenden i Microsoft 365.

## <a name="close-a-case"></a>Stänga ett ärende

När det juridiska ärende eller den undersökning som stöds av en bas-eDiscovery-ärende har slutförts kan du stänga ärendet. Så här stänger du ett ärende:
  
- Om ärendet innehåller eDiscovery-innehåll kommer det att inaktiveras. När vänttiden är inaktiverad tillämpas en respitperiod på 30 dagar (kallas för *fördröjning)* på platser som var i väntläge. Det här förhindrar att innehåll tas bort omedelbart, och administratörer kan söka efter och återställa innehåll innan det tas bort permanent efter att undantaget fördröjts. Mer information finns i Ta [bort innehållsplatser från en eDiscovery-plats.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)

- Om du stänger ett ärende inaktiveras bara det som är kopplat till det aktuella ärendet. Om andra bevarande placeras på en plats för innehåll (t.ex. bevarande av juridiska skäl, en bevarandeprincip eller ett bevarande från ett annat bas-eDiscovery-ärende) kommer de kvarhållningen att bibehållas.

- Ärendet är fortfarande listat på sidan Bas-eDiscovery i Microsoft 365 efterlevnadscenter. Informationen, som sätts i spärrade fall, sökningar och medlemmar i ett stängt ärende bevaras.

- Du kan redigera ett ärende när det har stängts. Du kan till exempel lägga till eller ta bort medlemmar, skapa sökningar och exportera sökresultat. Den största skillnaden mellan aktiva och stängda ärenden är att eDiscovery-kvarhåller har inaktiverats när ett ärende stängs.

Så här stänger du ett ärende:
  
1. I kompatibilitetscentret Microsoft 365 du på **eDiscovery** Core för att visa listan över  >   core-eDiscovery-ärenden i organisationen.

2. Klicka på namnet på det ärende du vill stänga.

   ![Stänga ärende på startsidan för ärende](../media/eDiscoveryCaseHomePage.png)

3. Klicka på Stäng ärende under **Status** på **startsidan.**

    En varning visas om att det som är kopplat till ärendet har inaktiverats.

4. Stäng **ärendet genom** att klicka på Ja.

    Statusen på ärendehemsidan ändras från **Aktiv till** **Avslutande.**

5. På sidan **Bas-eDiscovery** klickar du på **Uppdatera** för att uppdatera statusen för det stängda ärendet. Det kan ta upp till 60 minuter innan avslutsprocessen slutförs.

    När processen är klar ändras statusen för ärendet till **Stängd på** sidan **Core eDiscovery.**

## <a name="reopen-a-closed-case"></a>Öppna ett stängt ärende igen

När du öppnar ett ärende på nytt återställs inte eventuella eDiscovery-kvarhåller som fanns när ärendet stängdes. När ärendet har öppnats på nytt måste du gå till sidan **med spärrade** sidor och aktivera tidigare insidor. Om du vill aktivera ett väntande objekt markerar du det så att den utfäll sida visas och ställer sedan in **statusreglaget** på **På**.
  
1. I kompatibilitetscentret Microsoft 365 du på **eDiscovery** Core för att visa listan över  >   core-eDiscovery-ärenden i organisationen.

2. Klicka på namnet på det ärende som du vill öppna igen.

   ![Öppna ett stängt ärende igen](../media/eDiscoveryCaseHomePageReopen.png)

3. Klicka på Öppna ärende igen under **Status** **på startsidan.**

    En varning visas om att det som var kopplat till ärendet när det stängdes inte aktiveras automatiskt.

4. Klicka **på Ja** om du vill öppna ärendet igen.

    Statusen på startsidans utfäll sida för ärende ändras från **Stängd** till **Aktiv**.

5. På sidan **Bas-eDiscovery** klickar du på **Uppdatera för** att uppdatera statusen för det öppnade ärendet. Det kan ta upp till 60 minuter innan återöppnandeprocessen slutförs. 

    När processen är klar ändras statusen för ärendet till **Aktiv** på sidan **Bas-eDiscovery.**

7. (Valfritt) Om du vill aktivera eventuella spärrade objekt  kopplade till det öppnade ärendet går du till fliken Spärrar, markerar ett ärende och markerar kryssrutan under **Status** på den utfällbordssidan för håll.
  
## <a name="delete-a-case"></a>Ta bort ett ärende

Du kan också ta bort aktiva och stängda Core eDiscovery-ärenden. När du tar bort ett ärende tas alla sökningar och exporter i ärendet bort och ärendet tas bort från listan över ärenden på sidan **Core eDiscovery** i Microsoft 365 efterlevnadscenter. Du kan inte öppna ett borttagna ärende igen.

Innan du kan ta bort ett ärende (oavsett om det är aktivt eller stängt) måste du först ta bort *alla* eDiscovery-objekt som är kopplade till ärendet. Det omfattar borttagning av filer som har statusen **Av.** 

Så här tar du bort en e-dataidentifierings hold:

1. Gå till **fliken** Spärrar för det ärende som du vill ta bort.

2. Markera det håll du vill ta bort.

3. Klicka på Ta bort på den utfällade **sidan.**

      ![Ta bort ett eDiscovery-håll](../media/DeleteeDiscoveryHold.png)

Så här tar du bort ett ärende:

1. I kompatibilitetscentret Microsoft 365 du på **eDiscovery** Core för att visa listan över  >   core-eDiscovery-ärenden i organisationen.

2. Klicka på namnet på det ärende du vill ta bort.

3. Klicka på Ta bort ärende under **Status** på **startsidan för ärendet.**

      ![Öppna ett stängt ärende igen](../media/eDiscoveryCaseHomePageDelete.png)

Om det ärende som du försöker ta bort fortfarande innehåller eDiscovery-innehåll får du ett felmeddelande. Du måste ta bort alla fodral som är kopplade till ärendet och sedan försöka ta bort ärendet igen.
