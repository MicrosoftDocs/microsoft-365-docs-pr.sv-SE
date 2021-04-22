---
title: Skapa och visa undantag för säkerhetsrekommendationer – hantering av hot och sårbarhet
description: Skapa och övervaka undantag för säkerhetsrekommendationer i hantering av hot och sårbarhet.
keywords: Microsoft Defender för Endpoint-tvm-åtgärd, Microsoft Defender för Slutpunkt-tvm, hantering av hot och sårbarhet, & sårbarhetshantering, & sårbarhetshantering, åtgärd för tvm-åtgärd intune, tvm remediation sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1af8e5ec9d3aef560c739de5212e8118cf89cd7a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933751"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a>Skapa och visa undantag för säkerhetsrekommendationer – hantering av hot och sårbarhet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Hantering av hot och sårbarhet](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Som ett alternativ till en begäran om åtgärd när en rekommendation inte är relevant för tillfället kan du skapa undantag för rekommendationer. Om din organisation har enhetsgrupper kan du begränsa undantaget till specifika enhetsgrupper. Undantag kan antingen skapas för valda enhetsgrupper eller för alla enhetsgrupper som är tidigare och finns.  

När ett undantag skapas för en rekommendation är rekommendationen inte aktiv förrän undantagets varaktighet är slut. Rekommendationstillståndet ändras till **Fullständigt undantag eller** Delvis **undantag** (efter enhetsgrupp).

## <a name="permissions"></a>Behörigheter

Endast användare med behörigheten "undantagshantering" kan hantera undantag (till exempel att skapa eller avbryta). [Läs mer om RBAC-roller.](user-roles.md)

![Vy över behörighet för undantagshantering.](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a>Skapa ett undantag

Välj en säkerhetsrekommendationer som du vill skapa ett undantag för och välj sedan **Alternativ för undantag** och fyll i formuläret.  

![Visar var knappen för "undantagsalternativ" är platsen i en utfällsalternativ för säkerhetsrekommendationer.](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a>Undantag efter enhetsgrupp

Använd undantaget för alla aktuella enhetsgrupper eller välj specifika enhetsgrupper. Framtida enhetsgrupper inkluderas inte i undantaget. Enhetsgrupper som redan har ett undantag visas inte i listan. Om du bara väljer vissa enhetsgrupper ändras rekommendationstillståndet från "aktiv" till "delvis undantag". Statusen ändras till "fullständigt undantag" om du markerar alla enhetsgrupper.

![Visar listrutan enhetsgrupp.](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a>Filtrerade vyer

Om du har filtrerat efter enhetsgrupp på någon av sidorna för hot och sårbarhetshantering visas bara de filtrerade enhetsgrupper som alternativ.

Det här är knappen för att filtrera efter enhetsgrupp på någon av sidorna för hot och sårbarhetshantering: 

![Visar filter för valda enhetsgrupper.](images/tvm-selected-device-groups.png)

Undantagsvy med filtrerade enhetsgrupper:

![Visar listrutan Filtrerad enhetsgrupp.](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a>Stort antal enhetsgrupper

Om din organisation har fler än 20 enhetsgrupper väljer **du Redigera** bredvid alternativet för filtrerad enhetsgrupp.

![Visar hur du redigerar ett stort antal grupper.](images/tvm-exception-edit-groups.png)

En utfälling visas där du kan söka efter och välja enhetsgrupper som du vill ta med. Markera bockikonen under Sök för att markera/avmarkera alla.

![Visar den stora utfälloenheten för enhetsgrupp.](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a>Globala undantag

Om du har global administratörsbehörighet kan du skapa och avbryta ett globalt undantag. Det påverkar **alla** nuvarande och framtida enhetsgrupper i organisationen, och endast en användare med liknande behörighet skulle kunna ändra den. Rekommendationstillståndet ändras från "aktiv" till "fullständigt undantag".

![Visar alternativet globalt undantag.](images/tvm-exception-global.png)

Några saker att tänka på:

- Om en rekommendation ligger under globalt undantag inaktiveras de nyligen skapade undantagen för enhetsgrupper tills det globala undantaget har upphört att gälla eller avbrutits. Därefter börjar de nya enhetsgruppundantagen att gälla tills de upphör att gälla.
- Om en rekommendation redan har undantag för vissa enhetsgrupper och ett globalt undantag skapas inaktiveras enhetsgruppundantaget tills det upphör att gälla eller tills det globala undantaget avbryts innan det förfaller.

### <a name="justification"></a>Justering

Välj justeringen för det undantag du behöver spara i stället för att åtgärda den säkerhetsrekommendationer som gäller. Fyll i justeringskontexten och ange sedan varaktighet för undantaget.

I följande lista visas detaljerad information om justeringarna bakom undantagsalternativen:

- **Kontroll från tredje part** – en produkt eller programvara från tredje part som redan tar den här rekommendationen – Om du väljer den här justeringstypen sänks exponeringsresultatet och det säkra resultatet ökar eftersom risken minskar
- **Alternativ minskning** – Ett internt verktyg behandlar redan den här rekommendationen – Om du väljer den här justeringstypen sänks exponeringsresultatet och det säkra resultatet ökar eftersom risken minskar
- **Accepterad** risk – Det kan vara en låg risk och/eller att implementera rekommendationen är för dyr
- **Planerad åtgärd (respit) –** Redan planerat, men väntar på körning eller auktorisering

## <a name="view-all-exceptions"></a>Visa alla undantag

Gå till **fliken** Undantag **på sidan** Åtgärd. Du kan filtrera efter justering, typ och status.

 Välj ett undantag för att öppna en utfällblad med mer information. Undantag per enhetsgrupp har en lista över alla enhetsgrupper som undantaget omfattar, som du kan exportera. Du kan också visa den relaterade rekommendationen eller avbryta undantaget.

![Visar fliken "Undantag" på sidan Åtgärd.](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a>Avbryta ett undantag

Om du vill avbryta ett undantag går **du till** fliken Undantag **på sidan** Åtgärd. Markera undantaget.

Om du vill avbryta undantaget för alla enhetsgrupper eller för ett globalt undantag väljer du **knappen Avbryt undantag för alla enhetsgrupper.** Du kan bara avbryta undantag för enhetsgrupper som du har behörighet för.

![Knappen Avbryt.](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a>Avbryta undantaget för en viss enhetsgrupp

Markera den specifika enhetsgruppen om du vill avbryta undantaget för den. En utfälling visas för enhetsgruppen och du kan välja **Avbryt undantag**.

![Visar hur du väljer en specifik enhetsgrupp.](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a>Visa påverkan efter att undantag har tillämpats

På sidan Säkerhetsrekommendationer väljer du **Anpassa kolumner** och markerar kryssrutorna för exponerade enheter **(efter undantag)** **och Påverkan (efter undantag).**

![Visar alternativ för anpassa kolumner.](images/tvm-after-exceptions.png)

I kolumnen exponerade enheter (efter undantag) visas återstående enheter som fortfarande exponeras för säkerhetsproblem när undantag tillämpas. Justering av undantag som påverkar exponering inkluderar "kontroll från tredje part" och "alternativ minskning". Andra justeringar minskar inte exponering av en enhet och de anses fortfarande vara exponerade.

Effekterna (efter undantag) visar återstående påverkan på exponeringsresultat eller säker poäng efter att undantag har tillämpats. Justering av undantag som påverkar resultat är bland annat "kontroll från tredje part" och "alternativ minskning". Andra justeringar minskar inte exponeringen för en enhet och därför ändras inte exponeringsresultatet och det säkra resultatet.

![Visar kolumnerna i tabellen.](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över hot- och sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)
- [Åtgärda säkerhetsproblem](tvm-remediation.md)
- [Säkerhetsrekommendationer](tvm-security-recommendation.md)
- [Exponeringsvärde](tvm-exposure-score.md)
- [Microsoft Secure Score för enheter](tvm-microsoft-secure-score-devices.md)
