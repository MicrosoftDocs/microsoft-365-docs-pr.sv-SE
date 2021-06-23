---
title: Konfigurera en koppling för att arkivera ICE Anslut av chattdata i Microsoft 365
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
description: Lär dig att konfigurera och använda en 17a-4 ICE Anslut-anslutning för chattdataparser för att importera och arkivera ICE-Anslut-chattdata i Microsoft 365.
ms.openlocfilehash: 2c9eb6524e4f5e131603b5998d215e0b2d8111d3
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097318"
---
# <a name="set-up-a-connector-to-archive-ice-connect-chat-data-preview"></a>Konfigurera en koppling för att arkivera ICE Anslut av chattdata (förhandsgranskning)

Använd [ICE DataParser](https://www.17a-4.com/ice-dataparser/) från 17a-4 LLC för att importera och arkivera data från ICE Anslut Chat till användarnas postlådor i Microsoft 365 organisation. DataParser innehåller en ICE-chattkoppling som är konfigurerad för att hämta objekt från en datakälla från tredje part och importera objekten till Microsoft 365. Med ICE DataParser-kopplingen konverteras ICE Anslut-chattdata till ett e-postmeddelandeformat och sedan importeras objekten till användarnas postlådor i Microsoft 365.

När ICE Anslut-chattdata lagras i användarnas postlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad. Om du använder en ICE DataParser-koppling för att importera och arkivera data i Microsoft 365 kan din organisation följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-ice-chat-data"></a>Översikt över arkivering av ICE-chattdata

Följande översikt förklarar hur du använder en dataanslutning för att arkivera ICE-Anslut chattdata i Microsoft 365.

![Arkivering av arbetsflöde för ICE Anslut av chattdata från 17a-4](../media/ICEChatDataParserConnectorWorkflow.png)

1. Din organisation använder 17a-4 för att konfigurera och konfigurera ICE DataParser.

2. Ice-chattobjekt Anslut regelbundet samlas in av DataParser. DataParser konverterar även innehållet i ett meddelande till ett e-postmeddelandeformat.

3. ICE DataParser-kopplingen som du skapar i Microsoft 365 Efterlevnadscenter ansluter till DataParser och överför meddelanden till en säker Azure Storage plats i Microsoft-molnet.

4. En undermapp i mappen Inkorgen med namnet **ICE DataParser** skapas i användarpostlådorna och ICE-Anslut-chattobjekt importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Alla ICE Anslut chattobjekt innehåller den här egenskapen, som fylls i med alla deltagares e-postadresser.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

- Skapa ett DataParser-konto för Microsoft-kopplingar. Det gör du genom att [kontakta 17a-4 LLC.](https://www.17a-4.com/contact/) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar ICE DataParser-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-an-ice-dataparser-connector"></a>Steg 1: Konfigurera en ICE DataParser-koppling

Det första steget är att få åtkomst till sidan Datakopplingar i Microsoft 365 Efterlevnadscenter och skapa en 17a-4-koppling för ICE Anslut chattdata.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar**  >  **ICE DataParser.**

2. På sidan **ICE DataParser produktbeskrivning** klickar du på Lägg **till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt 17a-4-konto och utför stegen i anslutningsguiden ICE DataParser.

## <a name="step-2-configure-the-ice-dataparser-connector"></a>Steg 2: Konfigurera ICE DataParser-kopplingen

Konfigurera ICE DataParser-kopplingen med 17a-4-stöd.

## <a name="step-3-map-users"></a>Steg 3: Mappa användare

ICE DataParser-kopplingen mappar automatiskt användare till sina Microsoft 365-postadresser innan data importeras till Microsoft 365.

## <a name="step-4-monitor-the-ice-dataparser-connector"></a>Steg 4: Övervaka ICE DataParser-kopplingen

När du har skapat en ICE DataParser-koppling kan du visa kopplingsstatusen i Microsoft 365 Efterlevnadscenter.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan den ICE DataParser-koppling som du har skapat för att visa den utfällbar sida som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.
