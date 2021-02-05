---
title: Microsoft Viva Topics-roller
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
description: Läs mer om användarroller i Viva-ämnen.
ms.openlocfilehash: e2975201124045574c516aad49bc5059db969b76
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107440"
---
# <a name="microsoft-viva-topics-roles"></a>Microsoft Viva Topics-roller 

När du använder Viva Topics i Microsoft 365-miljön kan användarna ha följande roller:
-   Ämnesläsare
-   Ämnesdeltagare
-   Knowledge Manager
-   Kunskapsadministratör

## <a name="topic-viewer"></a>Ämnesläsare

Ämnesvyer är användare i organisationen som kan visa ämnen som markerats på sin moderna SharePoint-webbplats, Microsoft Search via SharePoint och Office.com och ämnescentret. De kan visa mer information om ett ämne på ämnessidan. 

För att ämnes höjdpunkter och deras ämnessidor ska vara synliga för ett ämnesvisningsprogram måste användaren:
-   [Tilldelas en Viva Topics-licens](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) av Microsoft 365-administratören.
-   Se till att du har tillgång till olika ämnen. Den här uppgiften utförs av kunskapsadministratören på inställningssidan för Viva-ämnen i administrationscentret för Microsoft 365.


## <a name="topic-contributors"></a>Ämnesdeltagare

Ämnesdeltagare är användare i organisationen som inte bara har behörighet att visa ämnen, utan också kan redigera ett befintligt ämne eller skapa ett nytt ämne. De har en viktig roll i att manuellt "curating" av informationen på en ämnessida (både AI och manuellt tillhandahållna) för att säkerställa kvaliteten.

Användare som har behörighet för  ämnesdeltagare ser knappen Redigera på ämnessidor där de kan uppdatera och publicera ett ämne.

En ämnesdeltagare kan också skapa och publicera ett nytt ämne via sitt ämnescenter.

Om du vill skapa och redigera ett ämne måste användaren:

-   [Tilldelas en Viva Topics-licens](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) av Microsoft 365-administratören.
-   [Tilldelas behörigheter för att skapa och redigera ämnen.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center) Den här uppgiften utförs av kunskapsadministratören på inställningssidan för Viva-ämnen i administrationscentret för Microsoft 365.

## <a name="knowledge-managers"></a>Kunskapschefer

Kunskapshanterare är användare som hanterar ämnen i organisationen.  Ämneshanteringen görs via sidan Hantera ämnen i ämnescentret, och den visas bara för Knowledge-chefer.

På sidan Hantera ämnen kan kunskapshanterare göra följande:
-   Visa AI-föreslagna ämnen.
-   Läs avsnitt för att bekräfta att de är giltiga.
-   Ta bort ämnen som du inte vill ska visas för användarna.

En kunskapsansvarig kan dessutom redigera befintliga ämnen eller skapa nya.

För att hantera ämnen måste användaren:
-   [Tilldelas en Viva Topics-licens](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) av Microsoft 365-administratören.
-   [Tilldelas behörigheter för att hantera ämnen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center)). Den här uppgiften utförs av kunskapsadministratören på inställningssidan för Viva-ämnen i administrationscentret för Microsoft 365.

Användare som har goda kunskaper om ditt företag kan vara bra som kandidater till rollen som knowledge manager. Sådana personer kanske inte bara har den kunskap som krävs för att veta om ämnena är giltiga eller inte, utan kanske också känner personer inom företaget som är relaterade till dessa ämnen.


## <a name="knowledge-admins"></a>Kunskapsadministratörer

Kunskapsadministratörer är administratörer som konfigurerar Viva-ämnen i din Microsoft 365-miljö. De hanterar även Viva Topics-inställningarna när inställningarna är klara. Rollen som kunskapsadministratör kräver att du är global Microsoft 365- eller SharePoint-administratör eftersom konfigurationen och hanteringen utförs i administrationscentret för Microsoft 365.
Under installationen kan knowledge admins konfigurera Viva Topics till:

-   Välj vilka SharePoint-webbplatser som ska crawlas för ämnen.
-   Välj vilka licensierade användare som kan visa ämnen (ämnesvisningsprogram).
-   Välj vilka ämnen som ska undantas från att identifieras.
-   Välj vilka licensierade användare som kan skapa och redigera ämnen (ämnesdeltagare).
-   Välj vilka licensierade användare som kan hantera ämnen (kunskapshanterare).
-   Namnge ämnescentret.

Kunskapschefer måste kunna samordna med alla Viva Topics-intressenter i organisationen för att ta reda på hur de ska konfigurera den. Om ett nytt projekt till exempel innehåller känslig information måste den kunskapsansvarige informeras så att han eller hon kan se till att SharePoint-webbplatsen inte crawlas för ämnen, eller att specifika ämnesnamn ska uteslutas.


## <a name="see-also"></a>Se även

