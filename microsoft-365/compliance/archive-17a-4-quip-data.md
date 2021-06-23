---
title: Konfigurera en koppling för att arkivera data avknapp i Microsoft 365
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
description: Lär dig att konfigurera och använda en 17a-4 Quip DataParser-koppling för att importera och arkivera data avkparent i Microsoft 365.
ms.openlocfilehash: 6db47d79cdab0f130d2b7b3483d37c08b267cdfd
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097291"
---
# <a name="set-up-a-connector-to-archive-quip-data-preview"></a>Konfigurera en koppling för att arkivera data avknappning (förhandsversion)

Använd [Quip DataParser](https://www.17a-4.com/quip-dataparser/) från 17a-4 LLC för att importera och arkivera data från Quip till användarpostlådor i Microsoft 365 organisation. DataParser har en Quip-koppling som är konfigurerad för att hämta objekt från en datakälla från tredje part och importera objekten till Microsoft 365. Kopplingen Quip DataParser konverterar Quip-data till ett e-postmeddelandeformat och importerar sedan dessa objekt till användarpostlådor i Microsoft 365.

När quip-data lagras i användarpostlådor kan du använda Microsoft 365-efterlevnadsfunktioner, till exempel bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad. Att använda en Quip-koppling för att importera och arkivera data i Microsoft 365 kan hjälpa din organisation att följa myndighets- och regleringsprinciper.

## <a name="overview-of-archiving-quip-data"></a>Översikt över arkivering av data

I följande översikt beskrivs hur du använder en datakoppling för att arkivera data av data i Microsoft 365.

![Arkivering av arbetsflöde för data från 17a-4](../media/QuipDataParserConnectorWorkflow.png)

1. Organisationen arbetar med 17a-4 för att konfigurera Quip DataParser.

2. Den här regeln samlas in regelbundet av DataParser. DataParser konverterar även innehållet i ett meddelande till ett e-postmeddelandeformat.

3. Den Quip DataParser-koppling som du skapar i Microsoft 365 Efterlevnadscenter ansluter till DataParser och överför meddelanden till en säker Azure Storage plats i Microsoft-molnet.

4. En undermapp i mappen Inkorgen med namnet **Quip DataParser** skapas i användarpostlådorna och objekten Quip importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Varje objekt avkavser innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

- Skapa ett DataParser-konto för Microsoft-kopplingar. Det gör du genom att [kontakta 17a-4 LLC.](https://www.17a-4.com/contact/) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar Quip DataParser-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-a-quip-dataparser-connector"></a>Steg 1: Konfigurera en Quip DataParser-koppling

Det första steget är att få åtkomst till sidan Datakopplingar i Microsoft 365 Efterlevnadscenter och skapa en 17a-4-koppling för Data avkn.

1. Gå till <https://compliance.microsoft.com> och klicka sedan på **Datakopplingar**  >  **Quip DataParser**.

2. På sidan **Ta fram dataparser produktbeskrivning** klickar du på Lägg **till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt 17a-4-konto och slutför stegen i anslutningsguiden Quip DataParser.

## <a name="step-2-configure-the-quip-dataparser-connector"></a>Steg 2: Konfigurera kopplingen Quip DataParser

Konfigurera kopplingen Quip DataParser med 17a-4 Support.

## <a name="step-3-map-users"></a>Steg 3: Mappa användare

Kopplingen Quip DataParser mappar automatiskt användare till sina e Microsoft 365 adresser innan data importeras till Microsoft 365.

## <a name="step-4-monitor-the-quip-dataparser-connector"></a>Steg 4: Övervaka kopplingen För att ta dataparser

När du har skapat en Quip DataParser-koppling kan du visa kopplingsstatusen i Microsoft 365 Efterlevnadscenter.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan kopplingen Skärmdataparser som du har skapat för att visa den utfällbar sidan, som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.
