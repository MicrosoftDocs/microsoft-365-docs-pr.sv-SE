---
title: Konfigurera en koppling för att arkivera zoomdata i Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Lär dig att konfigurera och använda en 17a-4-zoomdataparserkoppling för att importera och arkivera zoomdata i Microsoft 365.
ms.openlocfilehash: dffececb0719999abf19ea58eab1a52afdb3daea
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097221"
---
# <a name="set-up-a-connector-to-archive-zoom-data-preview"></a>Konfigurera en koppling för att arkivera zoomdata (förhandsgranskning)

Använd [Zoomdataparser](https://www.17a-4.com/dataparser/) från 17a-4 LLC för att importera och arkivera data från zoomplattformen till användarpostlådor i Microsoft 365 organisation. DataParser har en zoomkoppling som är konfigurerad för att hämta objekt från en datakälla från tredje part och importera objekten till Microsoft 365. Kopplingen Zooma dataparser konverterar zoomdata till ett e-postmeddelandeformat och importerar sedan dessa objekt till användarnas postlådor i Microsoft 365.

När zoomdata har lagrats i användarnas postlådor kan du tillämpa efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad. Om du använder en Zoom-koppling för att importera och arkivera data i Microsoft 365 kan det hjälpa din organisation att följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-zoom-data"></a>Översikt över arkivering av zoomdata

I följande översikt beskrivs hur du använder en datakoppling för att arkivera zoomdata i Microsoft 365.

![Arkivering av arbetsflöde för att zooma data från 17a-4](../media/ZoomDataParserConnectorWorkflow.png)

1. Din organisation arbetar med 17a-4 för att konfigurera och konfigurera Zoomdataparser.

2. Regelbundet samlas zoomobjekt in av DataParser. DataParser konverterar även innehållet i ett meddelande till ett e-postmeddelandeformat.

3. Zoomdataparser-kopplingen som du skapar i Microsoft 365 Efterlevnadscenter ansluter till DataParser och överför meddelanden till en säker Azure Storage plats i Microsoft-molnet.

4. En undermapp i mappen Inkorgen med namnet **Zooma dataparser** skapas i användarnas postlådor och zoomobjekten importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Varje zoomobjekt innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

- Skapa ett DataParser-konto för Microsoft-kopplingar. Det gör du genom att [kontakta 17a-4 LLC.](https://www.17a-4.com/contact/) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar zoomdataparserkopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-a-zoom-dataparser-connector"></a>Steg 1: Konfigurera en zoomdataparserkoppling

Det första steget är att komma åt sidan Datakopplingar i Microsoft 365 Efterlevnadscenter och skapa en 17a-4-koppling för zoomdata.

1. Gå till <https://compliance.microsoft.com> och klicka sedan på **Datakopplingar**  >  **Zooma dataparser**.

2. På sidan **Zooma dataparser produktbeskrivning** klickar du på Lägg **till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt 17a-4-konto och utför stegen i guiden Zooma dataparser-anslutning.

## <a name="step-2-configure-the-zoom-dataparser-connector"></a>Steg 2: Konfigurera zoomdataparserkopplingen

Konfigurera zoomdataparser-kopplingen med stöd för 17a-4.

## <a name="step-3-map-users"></a>Steg 3: Mappa användare

Zoomdataparser-kopplingen mappar automatiskt användare till sina e Microsoft 365-postadresser innan de importerar data till Microsoft 365.

## <a name="step-4-monitor-the-zoom-dataparser-connector"></a>Steg 4: Övervaka zoomdataparserkopplingen

När du har skapat en zoomdataparserkoppling kan du visa kopplingsstatusen i Microsoft 365 Efterlevnadscenter.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan zoomdataparserkopplingen som du har skapat för att visa den utfällbar sidan, som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.
