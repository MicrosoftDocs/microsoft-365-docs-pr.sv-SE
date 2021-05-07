---
title: Konfigurera en koppling för att arkivera FX Anslut data i Microsoft 365
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
description: Administratörer kan konfigurera en anslutare för att importera och arkivera data från Veritas FX Anslut i Microsoft 365. Med den här kopplingen kan du arkivera data från datakällor från tredje part i Microsoft 365 så att du kan använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part i organisationen.
ms.openlocfilehash: 1efbe8d6d8cecdd8394b565abad4d33c8610398f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162439"
---
# <a name="set-up-a-connector-to-archive-fx-connect-data"></a>Konfigurera en koppling för att arkivera FX Anslut data

Använd en Veritas-koppling i efterlevnadscentret för Microsoft 365 för att importera och arkivera data från FX Anslut-samarbetsplattformen till användarpostlådor i Microsoft 365 organisation. Veritas tillhandahåller en [FX Anslut-koppling](https://globanet.com/fx-connect/) som är konfigurerad för att spara FX Anslut objekt och importera dessa objekt till Microsoft 365. Kopplingen omvandlar innehållet från FX Anslut, till exempel affärer, meddelanden och annan information från din organisations FX Anslut-konto, till ett e-postmeddelandeformat och importerar sedan dessa objekt till användarens postlåda i Microsoft 365.

När FX Anslut-data lagras i användarpostlådor kan du tillämpa efterlevnadsfunktioner i Microsoft 365, till exempel bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad. Om du använder en FX Anslut-anslutning för att importera och arkivera data i Microsoft 365 kan det hjälpa din organisation att följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-fx-connect-data"></a>Översikt över arkivering av FX Anslut data

I följande översikt beskrivs hur du använder en koppling för att arkivera FX-Anslut information i Microsoft 365.

![Arkivering av arbetsflöden för FX Anslut data](../media/FXConnectConnectorWorkflow.png)

1. Din organisation arbetar med FX Anslut att konfigurera och konfigurera en FX-Anslut webbplats.

2. En gång per dygn kopieras objekt från FX Anslut-konton till webbplatsen Veritas Merge1. Kopplingen omvandlar även FX-Anslut till ett e-postmeddelandeformat.

3. FX Anslut-kopplingen som du skapar i efterlevnadscentret för Microsoft 365, ansluter till Veritas Merge1-webbplatsen varje dag och överför FX Anslut-objekten till en säker Azure Storage-plats i Microsoft-molnet.

4. Kopplingen importerar objekt till specifika användares postlådor med  värdet för egenskapen E-post för den automatiska användarmappningen enligt beskrivningen [i steg 3.](#step-3-map-users-and-complete-the-connector-setup) En undermapp i mappen Inkorgen med namnet **FX Anslut** skapas i användarpostlådorna och objekten importeras till den mappen. Kopplingen gör detta med hjälp av värdet för egenskapen *E-post.* Varje FX Anslut-objekt innehåller den här egenskapen, som fylls i med e-postadressen till alla deltagare i objektet.

## <a name="before-you-begin"></a>Innan du börjar

- Skapa ett Veritas Merge1-konto för Microsoft-kopplingar.  Om du vill skapa ett konto kontaktar [du Veritas kundsupport.](https://globanet.com/ms-connectors-contact) Du loggar in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar FX Anslut-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-fx-connect-connector"></a>Steg 1: Konfigurera FX-Anslut kopplingen

Det första steget är att komma åt sidan Datakopplingar i Microsoft 365 **efterlevnadscenter** och skapa en koppling för FX Anslut data.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka sedan på **Datakopplingar**  >  **FX Anslut**.

2. På sidan **FX Anslut** produktbeskrivning klickar du på Lägg **till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-the-fx-connect-connector-on-the-veritas-merge1-site"></a>Steg 2: Konfigurera FX Anslut-kopplingen på Veritas Merge1-webbplatsen

Det andra steget är att konfigurera FX Anslut-kopplingen på Merge1-webbplatsen. Mer information om hur du konfigurerar FX Anslut-koppling finns i [Användarhandbok för](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf)kopplingar från tredje part.

När du har **klickat &**  på Spara eller & visas sidan Användarmappning i kopplingsguiden i Microsoft 365 kompatibilitetscenter.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Om du vill mappa användare och slutföra anslutningskonfigurationen i Microsoft 365 efterlevnadscenter gör du så här:

1. På sidan **Mappa FX Anslut att Microsoft 365 användarna** aktiverar du automatisk användarmappning. FX Anslut postobjekten omfattar egenskapen *Email,* som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Klicka **på** Nästa, granska dina inställningar och gå sedan till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-fx-connect-connector"></a>Steg 4: Övervaka FX-Anslut kopplingen

När du har skapat FX Anslut-kopplingen kan du visa anslutningsstatusen i Microsoft 365 kompatibilitetscenter.

1. Gå till <https://compliance.microsoft.com/> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan **fx-Anslut** för att visa den utfällade sidan. Den här sidan innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.