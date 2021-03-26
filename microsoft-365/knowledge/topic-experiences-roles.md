---
title: Roller i Microsoft Viva-ämnen
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
- m365initiative-viva-topics
localization_priority: None
description: Läs mer om användarroller i Viva-ämnen.
ms.openlocfilehash: e91eda6807634ad27bf6c15c2dd0d1c9434ce299
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222773"
---
# <a name="microsoft-viva-topics-roles"></a>Roller i Microsoft Viva-ämnen 

När du använder Viva Topics i din Microsoft 365-miljö kan användarna ha följande roller:
-   Visare för ämne
-   Ämnesdeltagare
-   Knowledge Manager
-   Kunskapsadministratör

## <a name="topic-viewer"></a>Visare för ämne

Ämnesvyer är användare i organisationen som kan visa ämnen som markerats på sin moderna SharePoint-webbplats, Microsoft Search via SharePoint och Office.com och ämnescentret. De kan visa mer information om ett ämne på ämnessidan. 

För att ämnespunkter och deras ämnessidor ska vara synliga för ett ämnesvisningsprogram måste användaren:
-   [Tilldelas en Viva Topics-licens](./set-up-topic-experiences.md#assign-licenses) av microsoft 365-administratören.
-   Tillåt att du har tillgång till ämnen. Den här uppgiften utförs av kunskapsadministratören på inställningssidan för Viva Ämnen i administrationscentret för Microsoft 365.


## <a name="topic-contributors"></a>Ämnesdeltagare

Ämnesdeltagare är användare i organisationen som inte bara har behörighet att visa ämnen, utan även kan redigera ett befintligt ämne eller skapa ett nytt ämne. De har en viktig roll i att manuellt "curating" av informationen på en ämnessida (både AI och manuellt tillhandahållna) för att säkerställa kvaliteten.

Användare som har behörighet för  ämnesdeltagare ser knappen Redigera på ämnessidor som gör att de kan uppdatera och publicera ett ämne.

En ämnesdeltagare kan också skapa och publicera ett nytt ämne via sitt ämnescenter.

För att skapa och redigera ett ämne måste användaren:

-   [Tilldelas en Viva Topics-licens](./set-up-topic-experiences.md#assign-licenses) av microsoft 365-administratören.
-   [Tilldelas behörighet att skapa och redigera ämnen](./topic-experiences-user-permissions.md). Den här uppgiften utförs av kunskapsadministratören på inställningssidan för Viva Ämnen i administrationscentret för Microsoft 365.

## <a name="knowledge-managers"></a>Kunskapsansvariga

Kunskapschefer är användare som hanterar ämnen i organisationen.  Ämneshanteringen utförs på sidan Hantera ämnen i ämnescentret och den är bara synlig för Kunskapshanterare.

På sidan Hantera ämnen kan kunskapshanterare göra följande:
-   Visa AI-föreslagna ämnen.
-   Läs avsnitt för att bekräfta att de är giltiga.
-   Ta bort ämnen som du inte vill ska visas för användarna.

En kunskapshanterare kan dessutom redigera befintliga ämnen eller skapa nya.

För att hantera ämnen måste användaren:
-   [Tilldelas en Viva Topics-licens](./set-up-topic-experiences.md#assign-licenses) av microsoft 365-administratören.
-   [Tilldelas behörigheter för att hantera ämnen](./topic-experiences-user-permissions.md)). Den här uppgiften utförs av kunskapsadministratören på inställningssidan för Viva Ämnen i administrationscentret för Microsoft 365.

Användare som har en bra övergripande kunskap om ditt företag kan vara bra på att ta rollen som knowledge manager. Sådana personer kanske inte bara har kunskap om ämnen som är giltiga eller inte, utan kanske också känner till personer inom företaget som är relaterade till dessa ämnen.


## <a name="knowledge-admins"></a>Kunskapsadministratörer

Kunskapsadministratörer är administratörer som konfigurerar Viva Topics i din Microsoft 365-miljö. De hanterar även Inställningarna för Viva Ämnen när inställningarna har slutförts. Rollen som kunskapsadministratör kräver att du är global Microsoft 365- eller SharePoint-administratör eftersom konfiguration och hantering utförs i administrationscentret för Microsoft 365.
Under installationen kan knowledge admins ställa in Viva Topics till:

-   Välj vilka SharePoint-webbplatser som ska crawlas för ämnen.
-   Välj vilka licensierade användare som kan visa ämnen (ämnesvisningsprogram).
-   Välj vilka ämnen som ska undantas från att identifieras.
-   Välj vilka licensierade användare som kan skapa och redigera ämnen (ämnesdeltagare).
-   Välj vilka licensierade användare som kan hantera ämnen (kunskapshanterare).
-   Namnge ämnescentret.

Kunskapschefer måste kunna samordna med alla Viva Topics-intressenter i organisationen för att ta reda på hur de ska konfigurera dem. Om till exempel ett nytt projekt har känslig information måste kunskapshanteraren informeras så att de kan se till att SharePoint-webbplatsen inte crawlas för ämnen, eller att specifika ämnesnamn ska undantas.


## <a name="see-also"></a>Se även