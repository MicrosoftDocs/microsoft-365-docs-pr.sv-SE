---
title: Konfigurera en koppling för att arkivera SQL data i Microsoft 365
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
ROBOTS: noindex,nofollow
description: Lär dig att konfigurera och använda en 17a-4-SQL DataParser-koppling för att importera och arkivera SQL data i Microsoft 365.
ms.openlocfilehash: 17e7da9e064e6d149ebdca0436f9180c8d17ca41
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097202"
---
# <a name="set-up-a-connector-to-archive-sql-data-preview"></a>Konfigurera en koppling för att arkivera SQL data (förhandsgranskning)

Använd [SQL-dataparser](https://www.17a-4.com/sql-dataparser/) från 17a-4 LLC för att importera och arkivera data från en SQL-databas till användarnas postlådor i Microsoft 365 organisation. DataParser innehåller en SQL-koppling som är konfigurerad för att hämta objekt från en datakälla från tredje part och importera objekten till Microsoft 365. Med SQL DataParser-koppling konverteras data SQL till ett e-postmeddelandeformat och sedan importeras objekten till användarpostlådor i Microsoft 365.

När SQL data har lagrats i användarnas postlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad. Genom att SQL en anslutare för att importera och arkivera data i Microsoft 365 kan detta hjälpa din organisation att följa myndighets- och regelpolicyn.

## <a name="overview-of-archiving-sql-data"></a>Översikt över arkivering SQL data

I följande översikt beskrivs hur du använder en datakoppling för att arkivera SQL data i Microsoft 365.

![Arkivering av arbetsflöde för SQL data från 17a-4](../media/SQLDatabaseDataParserConnectorWorkflow.png)

1. Din organisation använder 17a-4 för att konfigurera och konfigurera SQL DataParser.

2. Regelbundet samlas SQL objekt in av DataParser. DataParser konverterar även innehållet i ett meddelande till ett e-postmeddelandeformat.

3. Den SQL DataParser-koppling som du skapar i Microsoft 365 Efterlevnadscenter ansluter till DataParser och överför meddelandena till en säker Azure Storage i Microsoft-molnet.

4. En undermapp i mappen Inkorgen **med namnet SQL DataParser** skapas i användarnas postlådor och SQL importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Alla SQL innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

- Skapa ett DataParser-konto för Microsoft-kopplingar. Det gör du genom att [kontakta 17a-4 LLC.](https://www.17a-4.com/contact/) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar SQL DataParser-koppling i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-a-sql-dataparser-connector"></a>Steg 1: Konfigurera en SQL DataParser-koppling

Det första steget är att få åtkomst till sidan Datakopplingar i Microsoft 365 Efterlevnadscenter och skapa en 17a-4-koppling för SQL data.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar**  >  **SQL DataParser**.

2. På sidan **SQL DataParser produktbeskrivning** klickar du på Lägg **till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt 17a-4-konto och slutför stegen SQL i guiden DataParser-anslutning.

## <a name="step-2-configure-the-sql-dataparser-connector"></a>Steg 2: Konfigurera SQL DataParser-koppling

Arbeta med 17a-4 Support för att konfigurera SQL DataParser-koppling.

## <a name="step-3-map-users"></a>Steg 3: Mappa användare

Med SQL DataParser-koppling mappas användare automatiskt till sina e Microsoft 365 adresser innan data importeras till Microsoft 365.

## <a name="step-4-monitor-the-sql-dataparser-connector"></a>Steg 4: Övervaka SQL med DataParser-kopplingen

När du har SQL en DataParser-koppling kan du visa kopplingsstatusen i Microsoft 365 Efterlevnadscenter.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan den SQL DataParser-koppling som du har skapat för att visa den utfällbar sida som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.
