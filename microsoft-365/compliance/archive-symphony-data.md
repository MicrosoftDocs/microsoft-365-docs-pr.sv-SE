---
title: Konfigurera en koppling för att arkivera data i Microsoft 365
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
description: Administratörer kan konfigurera en anslutare för att importera och arkivera data från Veritas Administrations i Microsoft 365. Med den här kopplingen kan du arkivera data från datakällor från tredje part i Microsoft 365. När du har arkiverat dessa data kan du använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part.
ms.openlocfilehash: b3ddb6826f7ef68808a819ee1d860b020efea98a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162418"
---
# <a name="set-up-a-connector-to-archive-symphony-data"></a>Konfigurera en koppling för arkivering av data

Använd en Veritas-koppling i Microsoft 365 kompatibilitetscenter om du vill importera och arkivera Data Från för användares postlådor i Microsoft 365 organisation. In är en meddelande- och samarbetsplattform som används inom finansiella tjänster. Veritas tillhandahåller [](https://globanet.com/symphony) en Sånledes-datakoppling i Microsoft 365 efterlevnadscenter som du kan konfigurera för att hämta objekt från tredje parts datakälla (regelbundet) och sedan importera objekten till användarnas postlådor. Kopplingen konverterar innehållet i ett objekt från Det första kontot till ett e-postmeddelandeformat och importerar sedan objektet till en postlåda i Microsoft 365.

När Communications Communications har lagrats i användarnas postlådor kan du använda Microsoft 365 efterlevnadsfunktioner, till exempel bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad. Genom att använda en Connector-koppling för att importera och arkivera data i Microsoft 365 kan det hjälpa din organisation att följa myndighets- och regleringsprinciperna.

## <a name="overview-of-archiving-symphony-data"></a>Översikt över arkivering av data i Datablad

I följande översikt beskrivs hur du använder en dataanslutning för att arkivera Kommunikationsarkiv i Microsoft 365.

![Arkivering av arkivering av arkivering](../media/SymphonyConnectorWorkflow.png)

1. Organisationen arbetar med Görn för att konfigurera och konfigurera en webbplats för en webbplats.

2. En gång per dygn kopieras chattmeddelanden frånLjud till webbplatsen Veritas Merge1. Kopplingen omvandlar också innehållet i ett chattmeddelande till ett e-postmeddelandeformat.

3. Kopplingen Som du skapar i efterlevnadscentret i Microsoft 365, ansluter till Veritas Merge1-webbplatsen varje dag och överför meddelandena till en säker Azure Storage plats i Microsoft-molnet.

4. Kopplingen importerar de konverterade meddelandeobjekten till postlådorna  för specifika användare med värdet för e-postegenskapen för den automatiska användarmappningen enligt beskrivningen i steg 3. En ny undermapp i mappen Inkorgen med namnet **Överse** skapas i användarnas postlådor och meddelandeobjekten importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Alla chattmeddelanden innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare.

## <a name="before-you-begin"></a>Innan du börjar

- Skapa ett Veritas Merge1-konto för Microsoft-kopplingar. Om du vill skapa ett konto kontaktar [du Veritas kundsupport.](https://globanet.com/ms-connectors-contact) Du loggar in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar Koppling för postlådor i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-symphony-connector"></a>Steg 1: Konfigurera Kopplingen

Det första steget är att få åtkomst till sidan Datakopplingar i Microsoft 365 för **efterlevnadscenter** och skapa en koppling för Datakällor.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka sedan på **Datakopplingar**  >  **Försett**.

2. På sidan **För produktbeskrivning** klickar du på **Lägg till koppling.**

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="configure-the-symphony-connector-on-the-veritas-merge1-site"></a>Konfigurera kopplingskopplingen på Webbplatsen Veritas Merge1

Det andra steget är att konfigurera Kopplingar på webbplatsen Merge1. Mer information om hur du konfigurerar kopplingskopplingen på Webbplatsen Veritas Merge1 finns i Användarhandbok för Slå [samman1 tredjepartskopplingar.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf)

När du har **klickat &**  på Spara eller & visas sidan Användarmappning i kopplingsguiden i Microsoft 365 kompatibilitetscenter.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Om du vill mappa användare och slutföra anslutningskonfigurationen i Microsoft 365 efterlevnadscenter gör du så här:

1. På sidan **Mappa externa användare till Microsoft 365 aktiverar** du automatisk användarmappning. Objekten till exempel egenskapen *E-post,* som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Klicka **på** Nästa, granska dina inställningar och gå sedan till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-symphony-connector"></a>Steg 4: Övervaka kopplingskopplingen

När du har skapat Kopplingen kan du visa kopplingsstatusen i Microsoft 365 efterlevnadscenter.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar och** välj sedan Koppling för **att** visa den utfällade sidan. Den här sidan innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller information om de data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.