---
title: Konfigurera en anslutare för att arkivera ServiceNow-data i Microsoft 365
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
description: Administratörer kan konfigurera en anslutare för att importera och arkivera ServiceNow-data från Veritas till Microsoft 365. Med den här kopplingen kan du arkivera data från datakällor från tredje part i Microsoft 365. När du har arkiverat dessa data kan du använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part.
ms.openlocfilehash: 8f1f56f79d3cdd0e198f03d948837249d3e0ff3b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162424"
---
# <a name="set-up-a-connector-to-archive-servicenow-data"></a>Konfigurera en anslutare för att arkivera ServiceNow-data

Använd en Veritas-koppling i Microsoft 365 compliance center för att importera och arkivera data från ServiceNow-plattformen till användarpostlådor i Microsoft 365 organisation. Veritas tillhandahåller en [ServiceNow-anslutning](https://globanet.com/servicenow/) som samlar objekt från datakällan från tredje part och importerar dessa objekt till Microsoft 365. Anslutningen konverterar innehåll som livemeddelanden, bifogade filer och inlägg från ServiceNow till ett e-postmeddelandeformat och importerar sedan dessa objekt till användarnas postlådor i Microsoft 365.

När ServiceNow-data har lagrats i användarnas postlådor kan du använda efterlevnadsfunktioner för Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter. Genom att använda en ServiceNow-anslutning för att importera och arkivera data i Microsoft 365 kan hjälpa din organisation att följa myndighets- och regleringsprinciper.

## <a name="overview-of-archiving-servicenow-data"></a>Översikt över arkivering av ServiceNow-data

Följande översikt förklarar hur du använder en anslutare för att arkivera ServiceNow-data i Microsoft 365.

![Arkiveringsarbetsflöde för ServiceNow-data](../media/ServiceNowConnectorWorkflow.png)

1. Din organisation arbetar med ServiceNow för att konfigurera och konfigurera en ServiceNow-webbplats.

2. En gång per dygn kopieras ServiceNow-objekt till webbplatsen Veritas Merge1. Anslutningen konverterar även ServiceNow-objekt till ett e-postmeddelandeformat.

3. ServiceNow-anslutningen som du skapar i kompatibilitetscentret för Microsoft 365 ansluter till Veritas Merge1-webbplatsen varje dag och överför ServiceNow-innehållet till en säker Azure Storage plats i Microsoft-molnet.

4. Kopplingen importerar de konverterade objekten till postlådorna  för specifika användare med värdet för egenskapen E-post för den automatiska användarmappningen enligt beskrivningen [i steg 3.](#step-3-map-users-and-complete-the-connector-setup) En undermapp till mappen Inkorg med namnet **ServiceNow** skapas i användarnas postlådor och objekt importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* All ServiceNow-artikel innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare i objektet.

## <a name="before-you-begin"></a>Innan du börjar

- Skapa ett Merge1-konto för Microsoft-kopplingar. Om du vill skapa ett konto kontaktar [du Veritas kundsupport.](https://www.veritas.com/content/support/) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Skapa ett ServiceNow-program för att hämta data från ditt ServiceNow-konto. Stegvisa instruktioner för hur du skapar programmet finns i [Användarhandbok för slå samman1 kopplingar från tredje part.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf)

- Den användare som skapar ServiceNow-kopplingen i steg 1 (och slutför det i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-servicenow-connector"></a>Steg 1: Konfigurera ServiceNow-kopplingen

Det första steget är att komma åt **sidan Data connectors** i Microsoft 365 compliance center och skapa en anslutning för ServiceNow-data.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka sedan på Data **connectors**  >  **ServiceNow.**

2. Klicka på Lägg till koppling på sidan för produktbeskrivning **av** **ServiceNow.**

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-the-servicenow-on-the-veritas-merge1-site"></a>Steg 2: Konfigurera ServiceNow på webbplatsen Veritas Merge1

Det andra steget är att konfigurera ServiceNow-kopplingen på Veritas Merge1-webbplatsen. Mer information om hur du konfigurerar ServiceNow-anslutningen finns i [Användarhandbok för Merge1 Tredjepartsanslutningar.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf)

När du klickar **& på** Spara  och slutför visas sidan Användarmappning i kopplingsguiden Microsoft 365 kompatibilitetscentret.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Om du vill mappa användare och slutföra anslutningskonfigurationen i Microsoft 365 efterlevnadscenter gör du så här:

1. På sidan **Map ServiceNow-användare Microsoft 365 användarna** aktiverar du den automatiska användarmappningen. ServiceNow-objekten innehåller egenskapen *Email,* som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Klicka **på** Nästa, granska dina inställningar och gå sedan till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-servicenow-connector"></a>Steg 4: Övervaka ServiceNow-kopplingen

När du har skapat ServiceNow-anslutningen kan du visa anslutningsstatusen i Microsoft 365 kompatibilitetscenter.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan **ServiceNow-kopplingen** för att visa den utfällade sidan, som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.