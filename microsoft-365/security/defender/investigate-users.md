---
title: Undersöka användare i Microsoft 365 Säkerhetscenter
description: undersöka användare i Säkerhetscenter för Microsoft 365
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, säkerhetscenter, bildskärm, rapport, identiteter, data, enheter, appar
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 68fc924ee14932ebdf92ef76306ba00e352b6030
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861279"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a>Undersöka användare i Microsoft 365 Säkerhetscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

En del av incidentundersökningen kan omfatta användarkonton. Börja med fliken **Användare** för ett incident från Incidenter **& aviseringar >** *incident* **> Användare.** 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exempel på en sida för användare för ett incident":::

Om du vill få en snabb sammanfattning av ett användarkonto för incidenten väljer du bockmarkeringen bredvid användarnamnet. Här är ett exempel.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Exempel på sammanfattningsfönstret för användarkontot för en incident i säkerhetscentret i Microsoft 365":::

Härifrån kan du välja Gå **till användarsida om** du vill visa information om ett användarkonto. Här är ett exempel.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Exempel på användarkontosidan för en incident i Säkerhetscenter för Microsoft 365":::

Du kan även visa den här sidan genom att välja namnet på användarkontot i listan på **sidan** Användare.

Användarsidan för Microsoft 365 säkerhetscenter kombinerar information från Microsoft Defender för Slutpunkt, Microsoft Defender för identitet och Microsoft Cloud App-säkerhet (beroende på vilka licenser du har). 

På den här sidan visas information som är specifik för säkerhetsrisken för ett användarkonto. Detta omfattar en poäng som hjälper till att utvärdera risker och nya händelser och varningar som bidragit till den totala risken för användaren.

Från den här sidan kan du utföra följande ytterligare åtgärder: 

- Markera användarkontot som komprometterat
- Kräv att användaren loggar in igen
- Stäng av användarkontot
- Se inställningar för användarkonton i Azure Active Directory (Azure AD)
- Visa de filer som ägs av användarkontot
- Visa filer som delats med den här användaren. 

Här är ett exempel.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Exempel på åtgärder för ett användarkonto för en händelse i Säkerhetscenter för Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över incidenter](incidents-overview.md)
- [Prioritera incidenter](incident-queue.md)
- [Hantera incidenter](manage-incidents.md)