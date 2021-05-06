---
title: Mallar för Insider-riskhanteringsvarningar
description: Läs mer om mallar för insider-riskhanteringsmeddelande i Microsoft 365
keywords: Microsoft 365, insider-riskhantering, riskhantering, efterlevnad
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 3a74c62e84c1cb9e4c749a364c0e5b6da25a8af9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2020
ms.locfileid: "52161603"
---
# <a name="insider-risk-management-notice-templates"></a>Mallar för Insider-riskhanteringsvarningar

Med mallar för Insider-riskhantering kan du skicka e-postmeddelanden till användarna när deras aktiviteter genererar en matchning och avisering för principen. I de flesta fall är användaråtgärder som genererar aviseringar resultatet av misstag eller oavsiktliga aktiviteter utan för avsikt. Meddelanden fungerar som enkla påminnelser om att användarna ska vara mer noga, tillhandahålla länkar till information för uppdateringsutbildning eller till företagets policyresurser. Meddelanden kan vara en viktig del av det interna utbildningsprogrammet för efterlevnad och kan hjälpa till att skapa en dokumenterad granskningslogg för användare med återkommande riskaktiviteter.

Skapa meddelandemallar om du vill skicka en e-postpåminnelse till användarna för principmatchning som en del av processen för att lösa problem. Meddelanden kan endast skickas till användarens e-postadress som är kopplad till den specifika aviseringen som granskas. När du väljer en meddelandemall som ska tillämpas på en principmatchning kan du välja att acceptera fältvärdena som definierats i mallen eller skriva över fälten efter behov.

## <a name="notice-templates-dashboard"></a>Instrumentpanel för meddelandemallar

I **instrumentpanelen för mallar för** meddelanden visas en lista med konfigurerade meddelandemallar och du kan skapa nya meddelandemallar. Meddelandemallarna visas i omvänd datumordning med den senaste meddelandemallen först.

![Instrumentpanel för mallar för Insider-riskhantering](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a>HTML för meddelanden

Om du vill skapa mer än ett enkelt textbaserat e-postmeddelande för aviseringar kan du skapa ett mer detaljerat meddelande med hjälp av HTML i meddelandetextfältet i en meddelandemall. Följande exempel innehåller brödtexten för en grundläggande HTML-baserad e-postaviseringsmall:

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> Implementering av HTML href-attribut i mallar för Insider-riskhanteringsmeddelandet stöder för närvarande endast enkla citattecken i stället för dubbla citattecken för URL-referenser.

## <a name="create-a-new-notice-template"></a>Skapa en ny meddelandemall

Om du vill skapa en ny mall för insider-riskhantering använder du meddelandeguiden i Insider-riskhanteringslösningen i Microsoft 365 efterlevnadscenter. 

Gör så här för att skapa en ny mall för insider-riskhantering:

1. I Microsoft 365 [kompatibilitetscenter](https://compliance.microsoft.com)går du till **Insider-riskhantering** och väljer **fliken Meddelandemallar.**
2. Välj **Skapa meddelandemall för** att öppna meddelandeguiden.
3. Fyll i **följande fält på sidan** Skapa en ny meddelandemall:
    - **Mallnamn:** Ange ett eget namn för meddelandet. Det här namnet visas i listan över meddelanden på instrumentpanelen och i meddelandelistan när meddelanden skickas från ett ärende.
    - **Skicka från:** Ange avsändarens e-postadress för meddelandet. Den här adressen visas i fältet **Från:** i alla meddelanden som skickas till användare om de inte ändras när du skickar ett meddelande från ett ärende.
    - **Fälten Kopia och Hemlig** kopia: Valfria användare eller grupper som ska meddelas om principmatchning, som valts i Active Directory för din prenumeration.
    - **Ämne**: Information som visas i meddelandets ämnesrad har stöd för texttecken.
    - **Meddelandetext:** Information som visas i meddelandets brödtext har stöd för text eller HTML-värden.
4. Välj **Skapa** för att skapa och spara meddelandemallen eller välj **Avbryt** om du vill stänga utan att spara meddelandemallen.

## <a name="update-a-notice-template"></a>Uppdatera en meddelandemall

Så här uppdaterar du en befintlig meddelandemall för Insider-riskhantering:

1. I Microsoft 365 [kompatibilitetscenter](https://compliance.microsoft.com)går du till **Insider-riskhantering** och väljer **fliken Meddelandemallar.**
2. På instrumentpanelen för meddelanden väljer du den meddelandemall som du vill hantera.
3. På sidan med meddelandeinformation väljer du **Redigera**
4. På **sidan** Redigera kan du redigera följande fält:
    - **Mallnamn:** Ange ett nytt eget namn för meddelandet. Det här namnet visas i listan över meddelanden på instrumentpanelen och i meddelandelistan när meddelanden skickas från ett ärende.
    - **Skicka från:** Uppdatera avsändarens e-postadress för meddelandet. Den här adressen visas i fältet **Från:** i alla meddelanden som skickas till användare om de inte ändras när du skickar ett meddelande från ett ärende.
    - **Fälten Kopia och Hemlig kopia:** Uppdatera valfria användare eller grupper som ska meddelas om principmatchning, som valts i Active Directory för din prenumeration.
    - **Ämne**: Uppdateringsinformation som visas i meddelandets ämnesrad har stöd för texttecken.
    - **Meddelandetext:** Uppdatera information som visas i meddelandets brödtext, med stöd för text eller HTML-värden.
5. Välj **Spara om** du vill uppdatera och spara meddelandet eller välj Avbryt **om** du vill stänga utan att spara meddelandemallen.

## <a name="delete-a-notice-template"></a>Ta bort en meddelandemall

Så här tar du bort en befintlig meddelandemall för insider-riskhantering:

1. I Microsoft 365 [kompatibilitetscenter](https://compliance.microsoft.com)går du till **Insider-riskhantering** och väljer **fliken Meddelandemallar.**
2. På instrumentpanelen för meddelanden väljer du den meddelandemall som du vill ta bort.
3. Välj ikonen **Ta** bort i verktygsfältet.
4. Om du vill ta bort meddelandemallen väljer **du Ja** i dialogrutan Ta bort. Om du vill avbryta borttagningen väljer du **Avbryt**.
