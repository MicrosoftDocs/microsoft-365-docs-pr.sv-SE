---
title: Konfigurera en koppling för att arkivera InvestEdge-data i Microsoft 365
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
description: Läs om hur du konfigurera och använder en 17a-4 InvestEdge DataParser-koppling för att importera och arkivera InvestEdge-data i Microsoft 365.
ms.openlocfilehash: fd384cb25486c4fa072dc17283c5b73e26e514a6
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097306"
---
# <a name="set-up-a-connector-to-archive-investedge-data-preview"></a>Konfigurera en koppling för att arkivera InvestEdge-data (förhandsversion)

Använd [InvestEdge DataParser](https://www.17a-4.com/investedge-dataparser/) från 17a-4 LLC för att importera och arkivera data från InvestEdge till användarpostlådor i Microsoft 365 organisation. DataParser innehåller en InvestEdge-koppling som är konfigurerad för att hämta objekt från en datakälla från tredje part och importera dessa objekt till Microsoft 365. Kopplingen InvestEdge DataParser konverterar InvestEdge-data till ett e-postmeddelandeformat och importerar sedan dessa objekt till användarnas postlådor i Microsoft 365.

När InvestEdge-data lagrats i användarnas postlådor kan du använda Microsoft 365-efterlevnadsfunktioner, till exempel bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad. Genom att använda en InvestEdge-koppling för att importera och arkivera data i Microsoft 365 kan detta hjälpa din organisation att följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-investedge-data"></a>Översikt över arkivering av InvestEdge-data

Följande översikt förklarar processen med att använda en dataanslutning för att arkivera InvestEdge-data i Microsoft 365.

![Arkivering av arbetsflöde för InvestEdge-data från 17a-4](../media/InvestEdgeDataParserConnectorWorkflow.png)

1. Din organisation använder 17a-4 för att konfigurera och konfigurera InvestEdge DataParser.

2. InvestEdge-objekt samlas in regelbundet av DataParser. DataParser konverterar även innehållet i ett meddelande till ett e-postmeddelandeformat.

3. Den InvestEdge DataParser-koppling som du skapar i Microsoft 365 Efterlevnadscenter ansluter till DataParser och överför meddelandena till en säker Azure Storage plats i Microsoft-molnet.

4. En undermapp i mappen Inkorgen med namnet **InvestEdge DataParser** skapas i användarnas postlådor och InvestEdge-objekten importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Varje InvestEdge-objekt innehåller den här egenskapen, som fylls i med alla deltagares e-postadresser.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

- Skapa ett DataParser-konto för Microsoft-kopplingar. Det gör du genom att [kontakta 17a-4 LLC.](https://www.17a-4.com/contact/) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar InvestEdge DataParser-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-a-investedge-dataparser-connector"></a>Steg 1: Konfigurera en InvestEdge DataParser-koppling

Det första steget är att få åtkomst till sidan Datakopplingar i Microsoft 365 Efterlevnadscenter och skapa en 17a-4-koppling för InvestEdge-data.

1. Gå till <https://compliance.microsoft.com> och klicka sedan på **Data-kopplingar**  >  **InvestEdge DataParser**.

2. På sidan **för produktbeskrivning av InvestEdge DataParser** klickar du på **Lägg till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt 17a-4-konto och utför stegen i anslutningsguiden InvestEdge DataParser.

## <a name="step-2-configure-the-investedge-dataparser-connector"></a>Steg 2: Konfigurera Koppling för InvestEdge DataParser

Konfigurera kopplingen InvestEdge DataParser med 17a-4 Support.

## <a name="step-3-map-users"></a>Steg 3: Mappa användare

Anslutningen InvestEdge DataParser mappar automatiskt användare till sina Microsoft 365-postadresser innan data importeras till Microsoft 365.

## <a name="step-4-monitor-the-investedge-dataparser-connector"></a>Steg 4: Övervaka InvestEdge DataParser-kopplingen

När du har skapat en InvestEdge DataParser-koppling kan du visa kopplingsstatusen i Microsoft 365 Efterlevnadscenter.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan den InvestEdge DataParser-koppling som du har skapat för att visa den utfällbar sida som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.
