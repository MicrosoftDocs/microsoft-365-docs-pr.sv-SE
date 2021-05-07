---
title: Konfigurera en koppling för att arkivera yieldbrokerdata i Microsoft 365
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
description: Administratörer kan konfigurera en anslutare för att importera och arkivera data från Veritas till Microsoft 365. Med den här kopplingen kan du arkivera data från datakällor från tredje part i Microsoft 365. När du har arkiverat dessa data kan du använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part.
ms.openlocfilehash: 1f2ca6850057112cc0a97b08811532961a213e89
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162409"
---
# <a name="set-up-a-connector-to-archive-yieldbroker-data"></a>Konfigurera en koppling för att arkivera yieldbrokerdata

Använd en Veritas-koppling i Microsoft 365 efterlevnadscenter om du vill importera och arkivera data från Yieldbroker till användarpostlådor i Microsoft 365 organisation. Veritas ger dig en [Yieldbroker-koppling](https://globanet.com/yieldbroker/) som är konfigurerad för att hämta objekt från datakällan från tredje part och importera de objekten till Microsoft 365. Kopplingen konverterar innehållet från Yieldbroker till ett e-postmeddelandeformat och importerar sedan dessa objekt till användarens postlåda i Microsoft 365.

När Yieldbroker har lagrats i användarpostlådor kan du använda efterlevnadsfunktioner för Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter. Om du använder en Yieldbroker-koppling för att importera och arkivera data i Microsoft 365 kan det hjälpa din organisation att följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-yieldbroker-data"></a>Översikt över arkivering av yieldbrokerdata

Följande översikt förklarar processen med att använda en koppling för att arkivera yieldbrokerdata i Microsoft 365.

![Arkivering av arbetsflöde för yieldbrokerdata](../media/YieldbrokerConnectorWorkflow.png)

1. Din organisation arbetar med Yieldbroker för att konfigurera en Yieldbroker-webbplats.

2. En gång per dygn kopieras Yieldbroker-objekt till webbplatsen Veritas Merge1. Kopplingen konverterar också innehållet till ett e-postmeddelandeformat.

3. Den Yieldbroker-koppling som du skapar i kompatibilitetscentret för Microsoft 365, ansluter till Veritas Merge1-webbplatsen varje dag och överför meddelandena till en säker Azure Storage plats i Microsoft-molnet.

4. Kopplingen importerar de konverterade yieldbrokerobjekten till postlådorna  för specifika användare med värdet för e-postegenskapen för den automatiska användarmappningen enligt beskrivningen [i steg 3.](#step-3-map-users-and-complete-the-connector-setup) En undermapp i mappen Inkorgen med namnet **Yieldbroker** skapas i användarpostlådorna och objekten importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Varje yieldbroker innehåller den här egenskapen, som fylls i med e-postadressen för alla deltagare i objektet.

## <a name="before-you-begin"></a>Innan du börjar

- Skapa ett Veritas Merge1-konto för Microsoft-kopplingar. Om du vill skapa ett konto kontaktar [du Veritas kundsupport.](https://www.veritas.com/content/support/) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar yieldbroker-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar på sidan Datakopplingar i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-yieldbroker-connector"></a>Steg 1: Konfigurera Yieldbroker-kopplingen

Det första steget är att komma åt sidan Datakopplingar i Microsoft 365 **kompatibilitetscenter** och skapa en koppling för Yieldbroker.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka sedan på **Datakopplingar** &gt; **Yieldbroker**.

2. På sidan **för produktbeskrivning av Yieldbroker** klickar du på **Lägg till ny koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-the-yieldbroker-connector-on-the-veritas-merge1-site"></a>Steg 2: Konfigurera kopplingen Yieldbroker på Webbplatsen Veritas Merge1

Det andra steget är att konfigurera Yieldbroker-kopplingen på webbplatsen Merge1. Mer information om hur du konfigurerar yieldbrokern finns i [Användarhandboken Slå samman1 tredjepartskopplingar.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf)

När du har **klickat &**  på Spara eller & visas sidan Användarmappning i kopplingsguiden i Microsoft 365 kompatibilitetscenter.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Om du vill mappa användare och slutföra anslutningskonfigurationen gör du så här:

1. Aktivera automatisk **användarmappning Microsoft 365 mappning** på sidan Map Yieldbroker-användare till . Yieldbroker-objekten innehåller en egenskap *som kallas E-post,* som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Klicka **på** Nästa , granska dina inställningar och gå till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-yieldbroker-connector"></a>Steg 4: Övervaka Yieldbroker-kopplingen

När du har skapat en Yieldbroker-koppling kan du visa kopplingsstatusen Microsoft 365 kompatibilitetscentret.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan **yieldbrokerkopplingen** för att visa den utfällade sidan, som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.