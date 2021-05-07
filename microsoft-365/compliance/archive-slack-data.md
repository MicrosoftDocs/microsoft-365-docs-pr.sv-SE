---
title: Konfigurera en koppling för att arkivera slack-eDiscovery-data i Microsoft 365
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
description: Administratörer kan konfigurera en koppling för att importera och arkivera data från Veritas Slack eDiscovery till Microsoft 365. Med den här kopplingen kan du arkivera data från datakällor från tredje part i Microsoft 365. När du har arkiverat dessa data kan du använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part.
ms.openlocfilehash: 48b0a6d4d5e8f6eafaaf900aa5c773cf4f99fe72
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162417"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data"></a>Konfigurera en koppling för att arkivera slack-eDiscovery-data

Använd en Veritas-koppling i efterlevnadscentret för Microsoft 365 om du vill importera och arkivera data från tredje part från sociala medier, snabbmeddelanden och plattformar för dokumentsamarbete till postlådor i Microsoft 365 organisation. Veritas tillhandahåller en [slackkoppling](https://globanet.com/slack/) som har konfigurerats för att hämta objekt från tredje parts datakälla (regelbundet) och sedan importera de objekten till Microsoft 365. Slack hämtar meddelanden och filer från Slack API och konverterar dem till ett e-postmeddelandeformat och importerar sedan objektet till användarnas postlådor.

När slack eDiscovery-data har lagrats i användarpostlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad. Genom att använda en slackkoppling för att importera och arkivera data i Microsoft 365 kan det hjälpa din organisation att följa myndighets- och regleringsprinciper.

## <a name="overview-of-archiving-slack-ediscovery-data"></a>Översikt över arkivering av slack-eDiscovery-data

I följande översikt beskrivs hur du använder en koppling för att arkivera slackinformationen i Microsoft 365.

![Slack arkivering av arbetsflöde](../media/SlackConnectorWorkflow.png)

1. Organisationen arbetar med slack när du konfigurerar och konfigurerar en slackwebbplats.

2. En gång per dygn kopieras chattmeddelanden från Slack eDiscovery till webbplatsen Veritas Merge1. Kopplingen omvandlar också innehållet i ett chattmeddelande till ett e-postmeddelandeformat.

3. Den Slack eDiscovery-koppling som du skapar i kompatibilitetscentret för Microsoft 365, ansluter till Veritas Merge1-webbplatsen varje dag och överför chattmeddelandena till en säker Azure Storage plats i Microsoft-molnet.

4. Kopplingen importerar de konverterade chattmeddelandeobjekten till postlådorna  för specifika användare med värdet för egenskapen E-post och automatisk användarmappning, enligt beskrivningen i steg 3. En ny undermapp i mappen Inkorgen med namnet **Slack eDiscovery** skapas i användarnas postlådor och chattmeddelandeobjekten importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Alla chattmeddelanden innehåller den här egenskapen, som fylls i med e-postadressen för alla deltagare i chattmeddelandet.

## <a name="before-you-begin"></a>Innan du börjar

- Skapa ett Veritas Merge1-konto för Microsoft-kopplingar. Om du vill skapa ett konto kontaktar [du Veritas kundsupport.](https://globanet.com/ms-connectors-contact) Du loggar in på det här kontot när du skapar kopplingen i steg 1.

- Hämta användarnamnet och lösenordet för organisationens Slack-företagskonto. Du måste logga in på det här kontot i steg 2 när du konfigurerar slack.

- Den användare som skapar slack-eDiscovery-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-slack-ediscovery-connector"></a>Steg 1: Konfigurera slack-eDiscovery-kopplingen

Det första steget är att komma åt sidan Datakopplingar i Microsoft 365 **kompatibilitetscenter** och skapa en koppling för slackdata.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka på **Datakopplingar**  >  **Slack eDiscovery**.

2. Klicka på Lägg till koppling på sidan Slack för **eDiscovery-produktbeskrivning.** 

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-slack-ediscovery"></a>Steg 2: Konfigurera slack för eDiscovery

Det andra steget är att konfigurera den slacka eDiscovery-kopplingen på webbplatsen Merge1. Mer information om hur du konfigurerar slacket för eDiscovery-koppling på Webbplatsen Veritas Merge1 finns i Användarhandbok för Slå [samman1 tredjepartskopplingar.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf)

När du har **klickat &**  på Spara eller & visas sidan Användarmappning i kopplingsguiden i Microsoft 365 kompatibilitetscenter.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

1. På sidan **Mappa externa användare till Microsoft 365 aktiverar** du automatisk användarmappning.

   Slack eDiscovery-objekt omfattar en egenskap *med namnet E-post,* som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Klicka **på** Nästa , granska dina inställningar och gå till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a>Steg 4: Övervaka den slacka eDiscovery-kopplingen

När du har skapat slack-eDiscovery-kopplingen kan du visa kopplingsstatusen Microsoft 365 efterlevnadscenter.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar och** välj sedan den slacka **eDiscovery-kopplingen** för att visa den utfällade sidan. Den här sidan innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller information om de data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.