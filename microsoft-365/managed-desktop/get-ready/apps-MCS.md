---
title: Arbeta med Microsoft Consulting Services
description: förberedelser och steg att följa för att arbeta med MCS för att paketera dina appar
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation, appar, MCS, förpackning
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0cb4da85b5548ced757197a3af818e212b065b47
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810601"
---
# <a name="working-with-microsoft-consulting-services"></a>Arbeta med Microsoft Consulting Services

Du kan samarbeta med Microsoft Consulting Services (MCS) för att få dina appar paketerade för användning med Microsoft Managed Desktop. Om du vill ha exakt information kan du arbeta med din kontorepresentant för att kontakta MCS och begränsa ditt specifika apppaketeringsprojekt.

## <a name="roles-and-responsibilities"></a>Roller och ansvarsområden

Om du vill arbeta med MCS-appförpackningar **måste du ange följande element:**

- Källinstallationsfilerna (t.ex. setup.exe eller .msi).
- Installationsinstruktionerna som anger information om hur den slutliga installationen ska se ut. Till exempel, bör det finnas en genväg till skrivbordet till appen? Vad ska appens synlighet vara? Ska appen ansluta till en server och i så fall vilken? Mer information finns i [mallen för begäran om programpaketering](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).
- Du måste utföra dina egna acceptanstester för att verifiera att appen fungerar som du behöver den i din miljö.

**MCS kommer att ta hand om dessa åtgärder:**

- Kontrollera om appen är förbjuden eller begränsad i Microsoft Managed Desktop-miljön.
- Testning av installation, start och avinstallation av appen för att säkerställa kompatibilitet med Windows 10. Om MCS upptäcker ett kompatibilitetsproblem lämnar de ut appen till [Desktop App Assure-programmet](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) för reparation.
- Paketera appen efter din specifikation och testa sedan appdistribution med hjälp av Microsoft Intune.

## <a name="app-delivery-schedule"></a>Tidsplan för appleverans

Starta förpackningsprocessen genom att ladda upp appinformationen till Microsoft Managed Desktop-portalen. Förpackningsteamet granskar nya inlämningar varje torsdag. Efter granskning och förpackning levereras de förpackade apparna följande fredag. Upp till fem appar per vecka kan paketeras för att starta men tjänsten kan skalas efter dina behov.

![kalender som visar appinflöde på en torsdag (den 21: a i det här exemplet), media validering nästa dag, förpackning på följande måndag (den 25: e) och app leverans på den efterföljande fredagen (den 29: e)](../../media/MCS-cal.png)

Du får ett meddelande när appen har levererats. Då har du 21 dagar på dig att utföra acceptanstester och signera arbetet i Microsoft Managed Desktop-portalen. Om du upptäcker några problem med appen under acceptanstestningen avvisar du appen i Microsoft Managed Desktop-portalen så ansluts du via e-post med en MCS-paketerare för att förstå och lösa problemet.

## <a name="testing-accounts-and-environment"></a>Testa konton och miljö

För att paketeringsteamet ska kunna slutföra migreringen till Microsoft Intune rekommenderar vi att du anger vissa behörigheter:
 
-   Åtkomst till Microsoft Intunes funktioner för appdistribution för paketeraren att lägga till och tilldela appen 
-   Testgrupper, användarkonton och licenser för paketerarna för att kunna testa apparna

MCS använder dessa behörigheter för att utföra följande åtgärder:
 
-   Se till att appen fungerar på virtuell dator som konfigurerats för Microsoft Managed Desktop
-   Ladda upp appen till Microsoft Intune för distribution till användarna

Utan dessa behörigheter är det möjligt för MCS att gå vidare, men de kommer inte att kunna ladda upp programmen till din miljö.


