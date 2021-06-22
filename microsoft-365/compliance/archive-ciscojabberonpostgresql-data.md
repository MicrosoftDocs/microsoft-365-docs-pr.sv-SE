---
title: Konfigurera en koppling för att arkivera Cisco Jabber på PostgreSQL-data i Microsoft 365
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Lär dig att konfigurera och använda en koppling i Microsoft 365 Efterlevnadscenter för att importera och arkivera data från Cisco Jabber på PostgreSQL för att Microsoft 365.
ms.openlocfilehash: 7fca60df9d2c0378579d7700fb3dae9bbcdf619d
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054793"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-postgresql-data"></a>Konfigurera en koppling för att arkivera Cisco Jabber på PostgreSQL-data

Använd en Veritas-koppling i Microsoft 365 Efterlevnadscenter om du vill importera och arkivera data från Cisco Jabber-plattformen till användarpostlådor i Microsoft 365 organisation. Veritas tillhandahåller en [Cisco Jabber på PostgreSQL-koppling](https://www.veritas.com/insights/merge1/jabber) som är konfigurerad för att hämta objekt från tredjepartsdatakällan (regelbundet) och importera dessa objekt till Microsoft 365. Kopplingen omvandlar innehåll som meddelanden, chattar och delat innehåll från Cisco Jabber på PostgreSQL till ett e-postmeddelandeformat och importerar sedan de objekten till användarens postlåda i Microsoft 365.

När Cisco Jabber på PostgreSQL-data lagras i användarpostlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter. Genom att använda en Cisco Jabber på PostgreSQL-anslutning för att importera och arkivera data i Microsoft 365 kan din organisation följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-cisco-jabber-on-postgresql-data"></a>Översikt över arkivering av Cisco Jabber på PostgreSQL-data

Följande översikt förklarar processen med att använda en koppling för att arkivera Cisco Jabber på PostgreSQL-data i Microsoft 365.

![Arkivering av arbetsflöde för Cisco Jabber på PostgreSQL-data](../media/CiscoJabberonPostgreSQLConnectorWorkflow.png)

1. Din organisation arbetar med Cisco Jabber på PostgreSQL för att konfigurera en Cisco Jabber på PostgreSQL-webbplats.

2. En gång per dygn kopieras Cisco Jabber på PostgreSQL-objekt till Webbplatsen Veritas Merge1. Kopplingen konverterar även Cisco Jabber på PostgreSQL-objekt till ett e-postmeddelandeformat.

3. Den Cisco Jabber på PostgreSQL-koppling som du skapar i Microsoft 365 Efterlevnadscenter, ansluter till Veritas Merge1-webbplatsen varje dag och överför Jabber-innehållet till en säker Azure Storage plats i Microsoft-molnet.

4. Kopplingen importerar de konverterade objekten till postlådorna  för specifika användare med värdet för egenskapen E-post för den automatiska användarmappningen enligt beskrivningen [i steg 3.](#step-3-map-users-and-complete-the-connector-setup) En undermapp i mappen Inkorgen med namnet **Cisco Jabber på PostgreSQL** skapas i användarpostlådorna och objekt importeras till den mappen. Kopplingen gör detta med hjälp av värdet för egenskapen *E-post.* Alla Jabber-objekt innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare i objektet.

## <a name="before-you-begin"></a>Innan du börjar

- Skapa ett Merge1-konto för Microsoft-kopplingar. Om du vill göra detta kontaktar [du Veritas kundsupport.](https://www.veritas.com/content/support/en_US) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Användaren som skapar Cisco Jabber på PostgreSQL-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-on-postgresql-connector"></a>Steg 1: Konfigurera Cisco Jabber på PostgreSQL-koppling

Det första steget är att få åtkomst till sidan **Datakopplingar** i Microsoft 365 Efterlevnadscenter och skapa en koppling för Jabber-data.

1. Gå till <https://compliance.microsoft.com> och klicka sedan på **Datakopplingar** &gt; **Cisco Jabber på PostgreSQL**.

2. Klicka på **Lägg till koppling på sidan för Cisco Jabber på PostgreSQL-produktbeskrivning.** 

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-the-cisco-jabber-on-postgresql-on-the-veritas-merge1-site"></a>Steg 2: Konfigurera Cisco Jabber på PostgreSQL på Veritas Merge1-webbplatsen

Det andra steget är att konfigurera Cisco Jabber på PostgreSQL-kopplingen på Veritas Merge1-webbplatsen. Mer information om hur du konfigurerar Cisco Jabber på PostgreSQL-koppling finns i Användarhandbok för Slå [samman1 tredjepartskopplingar](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20PostgreSQL%20User%20Guide.pdf).

När du **klickar & på** Spara  eller slutför visas sidan Användarmappning i kopplingsguiden Microsoft 365 Efterlevnadscenter objekt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Om du vill mappa användare och slutföra anslutningskonfigurationen i Microsoft 365 Efterlevnadscenter följer du dessa steg:

1. På kartan **Cisco Jabber på PostgreSQL-användare** för Microsoft 365 att aktivera automatisk användarmappning. Cisco Jabber på PostgreSQL-objekt inkluderar en egenskap som kallas *Email*, som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Klicka **på** Nästa, granska dina inställningar och gå sedan till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-cisco-jabber-on-postgresql-connector"></a>Steg 4: Övervaka Cisco Jabber på PostgreSQL-koppling

När du har skapat Cisco Jabber på PostgreSQL-kopplingen kan du visa anslutningsstatusen i Microsoft 365 Efterlevnadscenter.

1. Gå till <https://compliance.microsoft.com/> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan Cisco Jabber på **PostgreSQL-kopplingen** för att visa den utfällbara sidan, som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.
