---
title: Konfigurera en koppling för att arkivera Cisco Jabber på Oracle-data i Microsoft 365
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
description: Lär dig att konfigurera och använda en koppling i kompatibilitetscentret för Microsoft 365 för att importera och arkivera data från Cisco Jabber på Oracle till Microsoft 365.
ms.openlocfilehash: d8e1ba27c4277916614deaa042214ae592bceff2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842764"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-oracle-data-preview"></a>Konfigurera en koppling för att arkivera Cisco Jabber på Oracle-data (förhandsversion)

Använd en Veritas-koppling i efterlevnadscentret för Microsoft 365 för att importera och arkivera data från Cisco Jabber på Oracle-plattformen till användarpostlådor i Microsoft 365 organisation. Veritas tillhandahåller en [Cisco Jabber](https://www.veritas.com/insights/merge1/jabber) på Oracle-anslutning som är konfigurerad för att samla in objekt från datakällan från tredje part (regelbundet) och importera dessa objekt till Microsoft 365. Kopplingen konverterar innehåll som filåtgärder, kommentarer och delat innehåll från Cisco Jabber på Oracle till ett e-postmeddelandeformat och importerar sedan de objekten till användarens postlåda i Microsoft 365.

När Cisco Jabber på Oracle-data lagras i användarpostlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter. Med en Cisco Jabber på Oracle-anslutning kan du importera och arkivera data i Microsoft 365 för att hjälpa din organisation att följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-cisco-jabber-on-oracle-data"></a>Översikt över arkivering av Cisco Jabber på Oracle-data

Följande översikt förklarar processen med att använda en koppling för att arkivera Cisco Jabber på Oracle-data i Microsoft 365.

![Arkivering av arbetsflöde för Cisco Jabber på Oracle-data](../media/CiscoJabberOnOracleConnectorWorkflow.png)

1. Din organisation arbetar med Cisco Jabber på Oracle för att installera och konfigurera en Cisco Jabber på Oracle-webbplats.

2. En gång per dygn kopieras Cisco Jabber på Oracle-objekt till Webbplatsen Veritas Merge1. Kopplingen konverterar även Cisco Jabber på Oracle-objekt till ett e-postmeddelandeformat.

3. Cisco Jabber på Oracle-anslutning som du skapar i efterlevnadscentret för Microsoft 365, ansluter till Veritas Merge1-webbplatsen varje dag och överför Jabber-innehållet till en säker Azure Storage plats i Microsoft-molnet.

4. Kopplingen importerar de konverterade objekten till postlådorna  för specifika användare med värdet för egenskapen E-post för den automatiska användarmappningen enligt beskrivningen [i steg 3.](#step-3-map-users-and-complete-the-connector-setup) En undermapp i mappen Inkorgen med namnet **Cisco Jabber** på Oracle skapas i användarpostlådorna och objekt importeras till den mappen. Kopplingen gör detta med hjälp av värdet för egenskapen *E-post.* Alla Jabber-objekt innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare i objektet.

## <a name="before-you-begin"></a>Innan du börjar

- Skapa ett Merge1-konto för Microsoft-kopplingar. Om du vill göra detta kontaktar [du Veritas kundsupport.](https://www.veritas.com/content/support/en_US) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Användaren som skapar Cisco Jabber på Oracle-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-on-oracle-connector"></a>Steg 1: Konfigurera Cisco Jabber på Oracle-koppling

Det första steget är att få åtkomst till sidan **Datakopplingar** i Microsoft 365 och skapa en koppling för Jabber-data.

1. Gå till <https://compliance.microsoft.com> och klicka sedan på **Datakopplingar**  >  **Cisco Jabber på Oracle**.

2. På sidan **Cisco Jabber på Oracle-produktbeskrivning** klickar du på Lägg **till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-the-cisco-jabber-on-oracle-on-the-veritas-merge1-site"></a>Steg 2: Konfigurera Cisco Jabber på Oracle på Veritas Merge1-webbplatsen

Det andra steget är att konfigurera Cisco Jabber på Oracle-kopplingen på Veritas Merge1-webbplatsen. Mer information om hur du konfigurerar Cisco Jabber på Oracle-anslutning finns i [Användarhandbok för Merge1 Tredjepartskopplingar](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf).

När du har **klickat &**  på Spara eller & visas sidan Användarmappning i kopplingsguiden i Microsoft 365 kompatibilitetscenter.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Om du vill mappa användare och slutföra anslutningskonfigurationen i Microsoft 365 efterlevnadscenter gör du så här:

1. Aktivera automatisk **användarmappning på sidan Cisco Jabber** på Oracle Microsoft 365 till användare. Cisco Jabber på Oracle-objekt innehåller en egenskap som kallas *Email*, som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Klicka **på** Nästa, granska dina inställningar och gå sedan till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-cisco-jabber-on-oracle-connector"></a>Steg 4: Övervaka Cisco Jabber på Oracle-koppling

När du har skapat Cisco Jabber på Oracle-anslutning kan du visa anslutningsstatusen i Microsoft 365 kompatibilitetscenter.

1. Gå till <https://compliance.microsoft.com/> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan **Cisco Jabber** på Oracle-koppling för att visa den utfällade sidan, som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För närvarande stöder vi inte import av bifogade filer eller objekt som är större än 10 MB men stöd för större objekt kommer att vara tillgängligt vid ett senare tillfälle.
