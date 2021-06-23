---
title: Konfigurera en koppling för att arkivera Refinitiv Eikon Messenger-data i Microsoft 365
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
description: Lär dig att konfigurera och använda en 17a-4 Refinitiv DataParser-koppling för Eikon Messenger för att importera och arkivera Refinitiv Eikon Messenger-data i Microsoft 365.
ms.openlocfilehash: 59380695a6ade9a7dfc36c51ea4254e13a7fd03c
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097272"
---
# <a name="set-up-a-connector-to-archive-refinitiv-eikon-messenger-data-preview"></a>Konfigurera en koppling för att arkivera Refinitiv Eikon Messenger-data (förhandsversion)

Använd [Refinitiv Eikon Messenger-dataparser](https://www.17a-4.com/refinitiv-messenger-dataparser/) från 17a-4 LLC för att importera och arkivera data från Refinitiv Eikon Messenger till användarpostlådor i Microsoft 365 organisation. DataParser innehåller en Refinitiv Eikon Messenger-koppling som är konfigurerad för att hämta objekt från en datakälla från tredje part och importera objekten till Microsoft 365. Anslutningen Refinitiv Eikon Messenger DataParser omvandlar Refinitiv Eikon Messenger-data till ett e-postmeddelandeformat och importerar sedan dessa objekt till användarnas postlådor i Microsoft 365.

När Refinitiv Eikon Messenger-data har lagrats i användarpostlådor kan du använda efterlevnadsfunktioner för Microsoft 365, till exempel bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad. Om du importerar och arkiverar data i Microsoft 365 med en Refinitiv Eikon Messenger-anslutning kan detta hjälpa din organisation att följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-refinitiv-eikon-messenger-data"></a>Översikt över arkivering av Refinitiv Eikon Messenger-data

I följande översikt beskrivs hur du använder en dataanslutning för att arkivera Refinitiv Eikon Messenger-data i Microsoft 365.

![Arkivering av arbetsflöde för Refinitiv Eikon Messenger-data från 17a-4](../media/RefinitivMessengerDataParserConnectorWorkflow.png)

1. Din organisation använder 17a-4 för att konfigurera Refinitiv Eikon Messenger DataParser.

2. Regelbundet samlas Refinitiv Eikon Messenger-objekt in av DataParser. DataParser konverterar även innehållet i ett meddelande till ett e-postmeddelandeformat.

3. Anslutningen Refinitiv Eikon Messenger DataParser som du skapar i Microsoft 365 Efterlevnadscenter ansluter till DataParser och överför meddelandena till en säker Azure Storage plats i Microsoft-molnet.

4. En undermapp i mappen Inkorgen med namnet **Refinitiv Eikon Messenger DataParser** skapas i användarpostlådorna och Refinitiv Eikon Messenger-objekt importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Alla Refinitiv Eikon Messenger-objekt innehåller den här egenskapen, som fylls i med e-postadresserna för varje deltagare.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

- Skapa ett DataParser-konto för Microsoft-kopplingar. Det gör du genom att [kontakta 17a-4 LLC.](https://www.17a-4.com/contact/) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar anslutningen Refinitiv Eikon Messenger DataParser i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-a-refinitiv-eikon-messenger-dataparser-connector"></a>Steg 1: Konfigurera en Refinitiv DataParser-koppling för Eikon Messenger

Det första steget är att få åtkomst till sidan Datakopplingar i Microsoft 365 Efterlevnadscenter och skapa en 17a-4-koppling för Refinitiv Eikon Messenger-data.

1. Gå till <https://compliance.microsoft.com> och klicka sedan på **Datakopplingar**  >  **Refinitiv Eikon Messenger DataParser**.

2. På sidan **Refinitiv Eikon Messenger DataParser produktbeskrivning** klickar du på **Lägg till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt 17a-4-konto och slutför stegen i anslutningsguiden för Refinitiv Eikon Messenger DataParser.

## <a name="step-2-configure-the-refinitiv-eikon-messenger-dataparser-connector"></a>Steg 2: Konfigurera anslutningen Refinitiv Eikon Messenger DataParser

Arbeta med 17a-4 Support för att konfigurera anslutningen Refinitiv Eikon Messenger DataParser.

## <a name="step-3-map-users"></a>Steg 3: Mappa användare

Anslutningen Refinitiv Eikon Messenger DataParser mappar automatiskt användare till sina Microsoft 365-postadresser innan data importeras till Microsoft 365.

## <a name="step-4-monitor-the-refinitiv-eikon-messenger-dataparser-connector"></a>Steg 4: Övervaka kopplingen för Refinitiv Eikon Messenger-dataparser

När du har skapat en Refinitiv DataParser-koppling för Eikon Messenger kan du visa anslutningsstatusen i Microsoft 365 Efterlevnadscenter.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan anslutningen Refinitiv Eikon Messenger DataParser som du har skapat för att visa den utfällbar sidan, som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.
