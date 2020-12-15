---
title: Få insikter genom att träna på attacksimulering
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Administratörer kan lära sig hur utbildning för attack simulering i Microsoft 365 Security Center påverkar anställda och kan få insikter från simulering och utbildning.
ms.openlocfilehash: 6fc109469f8a9a3cf6aa87e9b8f9e3a024fed6e3
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667609"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Få insikter genom att träna på attacksimulering

Med utbildning för att simulera attacker tillhandahåller Microsoft dig insikter baserade på resultat från simuleringar och utbildningar som de anställda gick igenom. Dessa insikter hjälper dig att hålla dig informerad om hur hotet utvecklas för dina anställda, samt att rekommendera nästa steg för att bättre förbereda dina anställda och din miljö för attacker.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Vi arbetar ständigt med att utöka de insikter som är tillgängliga för dig. Beteende effekter och rekommenderade åtgärder är för tillfället tillgängliga. För att börja, gå över till en [utbildning för angrepps simulering i Microsoft 365 Security Center](https://security.microsoft.com/attacksimulator?viewid=overview).

## <a name="behavior-impact-on-compromise-rate"></a>Beteendet påverkar kompromissen

På fliken **Översikt** under utbildning för ansöknings simulering visas **beteendet för kompromiss** kortet. Det här kortet visar hur anställda som samtycker till simuleringarna du körde i motsats till det **förutsagda kompromissade priset**. Du kan använda dessa insikter för att spåra framsteg i de anställdas hot genom att köra flera simuleringar mot samma grupper av anställda.

I diagrammet kan du se:

- **Förväntad kompromiss nivå** som återspeglar den genomsnittliga kompromiss frekvensen för simuleringar med samma typ av nytto last för andra Microsoft 365-klient organisationer som använder samtals simulerings utbildning.
- **Faktisk kompromiss hastighet** visar den andel av anställda som sjönk för simuleringen.

Dessutom visas `<number> less susceptible to phishing` skillnaden mellan det faktiska antalet anställda som äventyras av angreppet och det uppskattade kompromiss priset. Det här antalet anställda är mindre troligt att det äventyras genom liknande attacker i framtiden, samtidigt som `<percent%> better than predicted rate` det visar hur de anställda hade stor till gång till den förväntade kompromissen.

> [!div class="mx-imgBorder"]
> ![Kurs kort i Översikt över hantering av angrepp](../../media/attack-sim-preview-behavior-impact-card.png)

Om du vill se en mer detaljerad rapport klickar du på **Visa simuleringar och rapport om kurs utveckling**. Den här rapporten ger samma information som du kan använda för att simulera själva simuleringen (till exempel simulerings teknik och totalt antal användare).

## <a name="recommended-actions"></a>Rekommenderade åtgärder

På fliken [ **simuleringar**](https://security.microsoft.com/attacksimulator?viewid=simulations)kommer du till simulerings uppgifter där du hittar avsnittet **rekommenderade åtgärder** .

Rekommendationer för rekommenderade åtgärder som är tillgängliga i [Microsofts säkra Poäng](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score). Dessa rekommendationer är baserade på den nytto last som används i simuleringen och hjälper dig att skydda dina anställda och din miljö. Om du klickar på varje åtgärd för förbättring kommer du till dess uppgifter.

> [!div class="mx-imgBorder"]
> ![Avsnittet rekommendations åtgärder i utbildning för simulering av attacker](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Relaterade länkar

**Angrepps Simulator** [skapa en simulering av nätfiske-attack](attack-simulation-training.md) och [skapa en nytto last för utbildning av dina kontakter](attack-simulation-training-payloads.md)
