---
title: Konfigurera en koppling för att arkivera Cisco Webex-data i Microsoft 365
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
description: Lär dig att konfigurera och använda en 17a-4 Cisco Webex DataParser-koppling för att importera och arkivera Cisco Webex-data i Microsoft 365.
ms.openlocfilehash: 055152f2d566f7cfc32dac132a70bbaf63ceb503
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097172"
---
# <a name="set-up-a-connector-to-archive-cisco-webex-data-preview"></a>Konfigurera en koppling för att arkivera Cisco Webex-data (förhandsversion)

Använd [Cisco Webex DataParser](https://www.17a-4.com/webex-dataparser/) från 17a-4 LLC för att importera och arkivera data från Cisco Cisco Webex-plattformen till användarpostlådor i Microsoft 365 organisation. DataParser innehåller en Cisco Webex-koppling som är konfigurerad för att hämta objekt från en datakälla från tredje part och importera objekten till Microsoft 365. Med Cisco Webex DataParser-kopplingen konverteras Cisco Webex-data till ett e-postmeddelandeformat och sedan importeras objekten till användarpostlådor i Microsoft 365.

När Cisco Webex-data lagras i användarpostlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad. Med en Cisco Webex-anslutning för att importera och arkivera data i Microsoft 365 kan hjälpa din organisation att följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-cisco-webex-data"></a>Översikt över arkivering av Cisco Webex-data

Följande översikt förklarar processen med att använda en datakoppling för att arkivera Cisco Webex-data i Microsoft 365.

![Arkivera arbetsflöde för Cisco Webex-data från 17a-4](../media/WebexTeamsDataParserConnectorWorkflow.png)

1. Din organisation arbetar med 17a-4 för att konfigurera och konfigurera Cisco Webex DataParser.

2. Cisco Webex-objekt samlas in regelbundet av DataParser. DataParser konverterar även innehållet i ett meddelande till ett e-postmeddelandeformat.

3. Den Cisco Webex DataParser-koppling som du skapar i Microsoft 365 Efterlevnadscenter ansluter till DataParser och överför meddelandena till en säker Azure Storage plats i Microsoft-molnet.

4. En undermapp i mappen Inkorgen med namnet **Cisco Webex DataParser** skapas i användarpostlådorna och Cisco Webex-objekten importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Varje Cisco Webex-objekt innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

- Skapa ett DataParser-konto för Microsoft-kopplingar. Det gör du genom att [kontakta 17a-4 LLC.](https://www.17a-4.com/contact/) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Användaren som skapar Cisco Webex DataParser-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-a-cisco-webex-dataparser-connector"></a>Steg 1: Konfigurera en Cisco Webex DataParser-koppling

Det första steget är att få åtkomst till sidan Datakopplingar i Microsoft 365 Efterlevnadscenter och skapa en 17a-4-koppling för Cisco Webex-data.

1. Gå till <https://compliance.microsoft.com> och klicka sedan på **Datakopplingar**  >  **Cisco Webex DataParser**.

2. På sidan **Cisco Webex DataParser produktbeskrivning** klickar du på Lägg **till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt 17a-4-konto och slutför stegen i anslutningsguiden för Cisco Webex DataParser.

## <a name="step-2-configure-the-cisco-webex-dataparser-connector"></a>Steg 2: Konfigurera Cisco Webex DataParser-kopplingen

Arbeta med 17a-4-stöd för att konfigurera Cisco Webex DataParser-kopplingen.

## <a name="step-3-map-users"></a>Steg 3: Mappa användare

Cisco Webex DataParser-kopplingen mappar automatiskt användare till sina Microsoft 365-postadresser innan de importerar data till Microsoft 365.

## <a name="step-4-monitor-the-cisco-webex-dataparser-connector"></a>Steg 4: Övervaka Cisco Webex DataParser-kopplingen

När du har skapat en Cisco Webex DataParser-koppling kan du visa anslutningsstatusen i Microsoft 365 Efterlevnadscenter.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan den Cisco Webex DataParser-koppling som du har skapat för att visa den utfällbar sida som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.
