---
title: Undersök användare i Microsoft 365 Defender
description: Undersök användare för en incident i Microsoft 365 säkerhetscenter.
keywords: säkerhet, skadlig kod, Microsoft 365, M365, säkerhetscenter, övervaka, rapportera, identiteter, data, enheter, appar, incident, analysera, svar
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
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572807"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>Undersök användare i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

En del av din incidentutredning kan innehålla användarkonton. Börja med fliken **Användare** för en incident från **incidenter & aviseringar >** *incident* **> användare**. 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exempel på en användarsida för en incident":::

Om du vill få en snabb sammanfattning av ett användarkonto för incidenten markerar du kryssrutan bredvid användarkontots namn. Här är ett exempel.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Exempel på sammanfattningsfönstret för användarkonto för en incident i Microsoft 365 säkerhetscenter":::

> [!NOTE]
> På sidan Användare visas Azure Active Directory (Azure AD) samt grupper, vilket hjälper dig att förstå de grupper och behörigheter som är associerade med en användare.

På den här utfällningssidan kan du granska information om användarhot, inklusive aktuella incidenter, aktiva aviseringar och risknivå samt användarexponering, konton, enheter med mera.

Dessutom kan du vidta åtgärder direkt i Microsoft 365 säkerhetscenter för att adressera en komprometterad användare, bekräfta att användaren komprometteras eller kräva att de loggar in igen.

Härifrån kan du välja Gå **till användarsidan för** att se information om ett användarkonto. Här är ett exempel.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Exempel på användarkontosidan för en incident i Microsoft 365 säkerhetscenter":::

Du kan också se den här sidan genom att välja namnet på användarkontot i listan på **sidan** Användare.

Användarsidan Microsoft 365 Säkerhetscenter kombinerar information från Microsoft Defender för slutpunkt, Microsoft Defender för identitet och Microsoft Cloud App Security (beroende på vilka licenser du har). 

Den här sidan visar information som är specifik för säkerhetsrisken för ett användarkonto. Detta inkluderar en poäng som hjälper till att bedöma risker och senaste händelser och aviseringar som bidrog till användarens totala risk.

På den här sidan kan du göra följande ytterligare åtgärder: 

- Markera användarkontot som komprometterat
- Kräv att användaren loggar in igen
- Stänga av användarkontot
- Se Azure Active Directory (Azure AD) användarkontoinställningar
- Visa de filer som ägs av användarkontot
- Visa filer som delas med den här användaren. 

Här är ett exempel.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Exempel på åtgärder på ett användarkonto för en incident i Microsoft 365 säkerhetscenter":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>Nästa steg

Om det behövs för incidenter i processen fortsätter du [din undersökning](investigate-incidents.md).

## <a name="see-also"></a>Se även

- [Översikt över incidenter](incidents-overview.md)
- [Prioritera incidenter](incident-queue.md)
- [Hantera incidenter](manage-incidents.md)