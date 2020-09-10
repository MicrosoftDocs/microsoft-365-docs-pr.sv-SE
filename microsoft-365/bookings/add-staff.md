---
title: Lägga till personal i bokningar
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 298c529b-407b-4a2b-b2c5-6e77a9d1f07f
description: Använd den här sidan för att skapa din personal lista och för att hantera personal uppgifter, till exempel namn, telefonnummer och e-postadress.
ms.openlocfilehash: cfd42eedb6e0bea08cdee1503fc373167996c75b
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420275"
---
# <a name="add-staff-to-bookings"></a>Lägga till personal i bokningar

På sidan personal i bokningar kan du skapa en bemannings lista och hantera personalens medlems uppgifter, till exempel namn, telefonnummer och e-postadress. Du kan också ange arbets tid för varje medlem i personalen.

> [!NOTE]
> Bokningar är som standard aktiverade för kunder som har Microsoft 365 Business Standard, Microsoft 365 a3 eller Microsoft 365 A5. Bokningar är också tillgängliga för kunder som har Office 365 Enterprise E3 och Office 365 Enterprise, E5, men det är inaktiverat som standard. Kom igång genom att läsa [få till gång till Microsoft-bokningar](get-access.md). Om du vill aktivera eller inaktivera uppslagning kan du läsa [Aktivera och inaktivera en organisation](turn-bookings-on-or-off.md).

## <a name="add-staff"></a>Lägga till personal

Även om det är en funktion i Microsoft 365, men alla dina anställda måste ha ett Microsoft 365-konto. Alla tjänste medlemmar måste ha en giltig e-postadress så att de kan ta emot bokningar och schemalägga ändringar.

Titta på den här videon eller följ stegen nedan för att lägga till din personal.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

1. Gå till [sidan hantera personal](https://outlook.office.com/bookings/staff) och välj **Lägg till personal**

2. Välj knappen **Lägg till personal** .

3. När du lägger till personal från klient organisationen skriver du deras namn i fältet **Lägg till personer** och markerar dem när de visas i den nedrullningsbara menyn. De övriga fälten fylls i automatiskt.

    När du har lagt till en personal medlem kan du redigera namnet som visas i alla bokförings kommunikationer genom att välja **x** bredvid personens namn och redigera fältet **Lägg till personer** . Det kan vara praktiskt om du vill att personalen ska ha en särskild titel eller ett namn som visas för kunder, till exempel att lista Adele Vance som "Dr. Vance, MD."

4. För att lägga till personal från en klient organisation, fyller du i deras e-post och annan information manuellt.

    > [!NOTE]
    > Personal utanför din klient organisation kan inte dela med dig av ledig/upptagen-information med bokningar.

5. För varje anställd väljer du en roll: administratör, visnings program eller gäst.
    - **Administratörer** kan redigera alla inställningar, lägga till och ta bort personal och skapa, redigera och ta bort bokningar.
    - **Visnings program** kan se alla kalendrar i kalendern, men de kan inte ändra eller ta bort dem. De har skrivskyddad åtkomst till inställningar.
    - **Gäster** kan tilldelas till bokningar, men de kan inte öppna post lådan.

6. Välj **meddela all personal via e-post när en bokning som har tilldelats till dem skapas eller ändras** för att aktivera e-postaviseringar. Följande är ett exempel på e-post:

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Skicka e-post från en avisering":::

7. Välj **händelser i Office 365-kalendern påverkar tillgänglighet** om du vill att ledig/upptagen-informationen från personal medlemmarnas kalendrar ska påverka tillgängligheten för boknings tjänster via bokningar.

    Om en anställd till exempel har ett grupp möte eller en personlig avtalad tid som är schemalagd för 3pm på en onsdag visar bokningarna att personal medlemmen inte är tillgänglig under den tiden. Den tiden visas som upptagen eller preliminärt i kalendervyn, enligt exemplet nedan.

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="En vy av kalendern i kalender":::

> [!IMPORTANT]
> Vi rekommenderar starkt att du lämnar den här inställningen (den är aktive rad som standard) för att undvika dubbel bokföring och för att optimera tillgänglighet för dina anställdas medlemmar.

8. Välj **Använd kontors tid** för att ställa in alla bookable tiden för att personalen bara ska vara inom den kontors tid som du har angett i avsnittet **Business-tid** på sidan företags information.

    Genom att avmarkera den här rutan kan personalen få anpassade timmar som är ytterligare begränsad när de kan bokas. Det här är användbart för scenarier där en anställds medlem bara kan finnas på webbplatsen tisdagar och Wednesdays, eller de är avvecklade sina morgon för en typ av avtalade tider och deras eftermiddagar för andra typer.
