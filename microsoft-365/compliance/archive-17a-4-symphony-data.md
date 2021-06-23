---
title: Konfigurera en Dataparser-koppling för att arkivera data i Microsoft 365
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
description: Lär dig att konfigurera och använda en 17a-4 DataParser-koppling för att importera och arkivera data från Arkiv i Microsoft 365.
ms.openlocfilehash: da947c80a296aa4fee8ccabb9bb82eecc1d9b103
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097181"
---
# <a name="set-up-a-connector-to-archive-symphony-data-preview"></a>Konfigurera en koppling för att arkivera data i data för arkivering (förhandsgranskning)

Använd [Dataparser](https://www.17a-4.com/Symphony-dataparser/) från 17a-4 LLC för att importera och arkivera kommunikationsdata till användarpostlådor i Microsoft 365 organisation. DataParser innehåller en Connector för Connector som är konfigurerad för att hämta objekt från en datakälla från tredje part och importera objekten till Microsoft 365. Kopplingen För sedan dataparser konverterar Hansson data till ett e-postmeddelandeformat och importerar sedan objekten till användarnas postlådor i Microsoft 365.

När Du har lagrat data i användarpostlådor kan du använda Microsoft 365 efterlevnadsfunktioner som Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad. Genom att använda en Connector-koppling för att importera och arkivera data i Microsoft 365 kan det hjälpa din organisation att följa myndighets- och regleringsprinciperna.

## <a name="overview-of-archiving-symphony-data"></a>Översikt över arkivering av data i Datablad

I följande översikt beskrivs hur du använder en datakoppling för att arkivera data i Microsoft 365.

![Arkivering av arbetsflöde för data i arkivering av data från 17a-4](../media/SymphonyDataParserConnectorWorkflow.png)

1. Organisationen använder 17a-4 för att konfigurera Och konfigurera Dataparser.

2. Objekten samlas in regelbundet av DataParser. DataParser konverterar även innehållet i ett meddelande till ett e-postmeddelandeformat.

3. Kopplingen DataParser som du skapar i Microsoft 365 Efterlevnadscenter ansluter till DataParser och överför meddelandena till en säker Azure Storage plats i Microsoft-molnet.

4. En undermapp till mappen Inkorgen med namnet **Dataparser** för användare skapas i användarnas postlådor och objekten Förnamn importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Varje Objekt i han/hon innehåller den här egenskapen, som fylls i med alla deltagares e-postadresser.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

- Skapa ett DataParser-konto för Microsoft-kopplingar. Det gör du genom att [kontakta 17a-4 LLC.](https://www.17a-4.com/contact/) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar Licensdataparser-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-a-symphony-dataparser-connector"></a>Steg 1: Konfigurera en Dataparser-koppling för Dataparser

Det första steget är att få åtkomst till sidan Datakopplingar i Microsoft 365 Efterlevnadscenter och skapa en 17a-4-koppling för Gör-data.

1. Gå till <https://compliance.microsoft.com> och klicka sedan på **Datakopplingar**  >  **Dataparser.**

2. Klicka på Lägg till **koppling** på produktbeskrivningssidan **Dataparser.**

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt 17a-4-konto och utför stegen i Anslutningsguiden Förnster DataParser.

## <a name="step-2-configure-the-symphony-dataparser-connector"></a>Steg 2: Konfigurera kopplingen Dataparser

Konfigurera kopplingen Dataparser med 17a-4 Support.

## <a name="step-3-map-users"></a>Steg 3: Mappa användare

Kopplingen För dataparser mappar automatiskt användare till sina e Microsoft 365 adresser innan data importeras till Microsoft 365.

## <a name="step-4-monitor-the-symphony-dataparser-connector"></a>Steg 4: Övervaka Kopplingen För dataparser

När du har skapat en Så här bra dataparserkoppling kan du visa kopplingsstatusen i Microsoft 365 Efterlevnadscenter.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan kopplingen Dataparser som du har skapat för att visa den utfällbar sida som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.
