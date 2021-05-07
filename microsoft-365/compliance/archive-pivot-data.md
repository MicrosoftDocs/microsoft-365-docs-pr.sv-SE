---
title: Konfigurera en koppling för att arkivera pivotdata i Microsoft 365
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
description: Administratörer kan konfigurera en anslutare för att importera och arkivera pivotdata från Veritas i Microsoft 365. Med den här kopplingen kan du arkivera data från datakällor från tredje part i Microsoft 365 så att du kan använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part i organisationen.
ms.openlocfilehash: 8e88f5166ebcc4d1285a81e041b6d97be46786e3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162435"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a>Konfigurera en koppling för att arkivera pivotdata

Använd en Veritas-koppling i Microsoft 365 efterlevnadscenter om du vill importera och arkivera data från Pivot-plattformen till användarpostlådor i Microsoft 365 organisation. Veritas ger dig en [pivotkoppling](https://globanet.com/pivot/) som är konfigurerad för att hämta objekt från tredje parts datakälla (regelbundet) och sedan importera de objekten till Microsoft 365. Pivot är en snabbmeddelandeplattform som gör det möjligt att samarbeta med finansmarknadsdeltagare. Kopplingen konverterar exempelvis chattmeddelanden från en användares pivotkonton till ett e-postmeddelandeformat och importerar sedan objekten till användarnas postlådor i Microsoft 365.

När pivotdata har lagrats i användarnas postlådor kan du använda efterlevnadsfunktioner Microsoft 365 till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad. Om du använder en pivotkoppling för att importera och arkivera data i Microsoft 365 kan detta hjälpa din organisation att följa myndighets- och regleringsprinciper.

## <a name="overview-of-archiving-pivot-data"></a>Översikt över arkivering av pivotdata

I följande översikt beskrivs hur du använder en koppling för att arkivera pivotdata i Microsoft 365.

![Arkivera arbetsflöde för pivotdata](../media/PivotConnectorWorkflow.png)

1. Organisationen arbetar med Pivot för att konfigurera och konfigurera en pivotkällwebbplats.

2. En gång per dygn kopieras pivotobjekt till Webbplatsen Veritas Merge1. Kopplingen konverterar även pivotobjekt till ett e-postmeddelandeformat.

3. Den Pivot-koppling som du skapar i efterlevnadscentret för Microsoft 365, ansluter till Veritas Merge1-webbplatsen varje dag och överför pivotobjekten till en säker Azure Storage plats i Microsoft-molnet.

4. Kopplingen importerar Pivot-objekten till postlådorna för specifika  användare med hjälp av värdet för egenskapen E-post för den automatiska användarmappningen enligt beskrivningen [i steg 3.](#step-3-map-users-and-complete-the-connector-setup) En undermapp i mappen Inkorgen med namnet **Pivot** skapas i användarnas postlådor och objekten importeras till den mappen. Kopplingen gör detta med hjälp av värdet för egenskapen *E-post.* Alla pivotobjekt innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare i objektet.

## <a name="before-you-begin"></a>Innan du börjar

- Skapa ett Veritas Merge1-konto för Microsoft-kopplingar. Om du vill skapa det här kontot [kontaktar du Veritas kundsupport.](https://www.veritas.com/content/support/) Du loggar in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar pivotkopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar på sidan Datakopplingar i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-pivot-connector"></a>Steg 1: Konfigurera pivotkopplingen

Det första steget är att få åtkomst till **sidan Datakopplingar i Efterlevnadscenter** för Microsoft och skapa en koppling för pivotdata.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka sedan på **Datakopplingar**  >  **Pivot.**

2. På sidan **För pivotproduktbeskrivning** klickar du på **Lägg till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-the-pivot-connector-on-the-veritas-merge1-site"></a>Steg 2: Konfigurera Pivot-kopplingen på Webbplatsen Veritas Merge1

Det andra steget är att konfigurera Pivot-kopplingen på webbplatsen Merge1. Mer information om hur du konfigurerar Pivot-kopplingen på webbplatsen Veritas Merge1 finns i Användarhandbok för Slå [samman1 tredjepartskopplingar.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf)

När du har **klickat &**  på Spara eller & visas sidan Användarmappning i kopplingsguiden i Microsoft 365 kompatibilitetscenter.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Om du vill mappa användare och slutföra anslutningskonfigurationen i efterlevnadscentret för Microsoft 356 gör du så här:

1. På sidan **Mappa pivotanvändare till Microsoft 365 användarna** aktiverar du automatisk användarmappning. Pivotobjekten innehåller egenskapen *E-post,* som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Klicka **på** Nästa , granska dina inställningar och gå till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-pivot-connector"></a>Steg 4: Övervaka pivotkopplingen

När du har skapat pivotkopplingen kan du visa anslutningsstatusen i Microsoft 365 kompatibilitetscenter.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar och** välj sedan pivotkopplingen **för** att visa den utfällade sidan. Den här sidan innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.