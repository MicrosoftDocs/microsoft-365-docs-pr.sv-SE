---
title: Konfigurera en koppling för att arkivera textavgränsade data i Microsoft 365
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
description: Administratörer kan konfigurera en koppling för att importera och arkivera textavgränsade data från Veritas till Microsoft 365. Med den här kopplingen kan du arkivera data från datakällor från tredje part i Microsoft 365. När du har arkiverat dessa data kan du använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part.
ms.openlocfilehash: 9a8265766dd08a78c3f218710a3bc4b623f7f670
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162416"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data"></a>Konfigurera en koppling för att arkivera textavgränsade data

Använd en Veritas-koppling i Microsoft 365 efterlevnadscenter om du vill importera och arkivera textavgränsade data till användarpostlådor i Microsoft 365 organisation. Veritas är [](https://globanet.com/text-delimited) en textavgränsad koppling som har konfigurerats för att hämta objekt från en datakälla från tredje part (regelbundet) och importera dessa objekt till Microsoft 365. Kopplingen konverterar innehåll från den textavgränsade datakällan till ett e-postmeddelandeformat och importerar sedan objekten till användarens postlåda i Microsoft 365.

När textavgränsade data lagras i användarpostlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery och bevarandeprinciper och bevarandeetiketter. Genom att använda en textavgränsad datakoppling för att importera och arkivera data i Microsoft 365 kan organisationen följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-the-text-delimited-data"></a>Översikt över arkivering av textavgränsade data

I följande översikt beskrivs hur du använder en koppling för att arkivera textavgränsad källinformation i Microsoft 365.

![Arkivering av arbetsflöden för textavgränsade data](../media/TextDelimitedConnectorWorkflow.png)

1. Din organisation arbetar med en textavgränsad källa för att konfigurera och konfigurera en textavgränsad webbplats.

2. En gång per dygn kopieras chattmeddelanden från den textavgränsade källan till webbplatsen Veritas Merge1. Kopplingen konverterar också innehållet till ett e-postmeddelandeformat.

3. Den textavgränsade koppling som du skapar i kompatibilitetscentret för Microsoft 365 ansluter till Veritas Merge1-webbplatsen varje dag och överför meddelandena till en säker Azure Storage plats i Microsoft-molnet.

4. Kopplingen importerar de konverterade meddelandeobjekten till postlådorna  för specifika användare med värdet för e-postegenskapen för den automatiska användarmappningen enligt beskrivningen i steg 3. En ny undermapp i mappen Inkorg med namnet **Text-** Avgränsad skapas i användarnas postlådor och meddelandeobjekten importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Alla meddelanden innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare.

## <a name="before-you-begin"></a>Innan du börjar

- Skapa ett Veritas Merge1-konto för Microsoft-kopplingar. Om du vill skapa det här kontot [kontaktar du Veritas kundsupport.](https://globanet.com/ms-connectors-contact) Du loggar in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar den textavgränsade kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-text-delimited-connector"></a>Steg 1: Konfigurera den textavgränsade kopplingen

Det första steget är att komma åt sidan **Datakopplingar** i Microsoft 365 och skapa en koppling för textavgränsade data.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka sedan på **Textavgränsade**  >  **datakopplingar.**

2. På sidan **med en textavgränsad** produktbeskrivning klickar du på Lägg **till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-the-text-delimited-connector-on-the-veritas-merge1-site"></a>Steg 2: Konfigurera den textavgränsade kopplingen på Veritas Merge1-webbplatsen

Det andra steget är att konfigurera den textavgränsade kopplingen på webbplatsen Merge1. Mer information om hur du konfigurerar en textavgränsad koppling på webbplatsen Veritas Merge1 finns i Användarhandbok för Slå [samman1 tredjepartskopplingar.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf)

När du har **klickat &**  på Spara eller & visas sidan Användarmappning i kopplingsguiden i Microsoft 365 kompatibilitetscenter.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Om du vill mappa användare och slutföra anslutningskonfigurationen i Microsoft 365 efterlevnadscenter gör du så här:

1. På sidan **Mappa externa användare till Microsoft 365 aktiverar** du automatisk användarmappning. Objekten i den avgränsade källan text innehåller egenskapen *E-post,* som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Klicka **på** Nästa, granska dina inställningar och gå sedan till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-text-delimited-connector"></a>Steg 4: Övervaka den textavgränsade kopplingen

När du har skapat en textavgränsad koppling kan du visa kopplingsstatusen i Microsoft 365 för efterlevnadscenter.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan den textavgränsade **kopplingen för** att visa den utfällda sidan. Den här sidan innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller information om de data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.