---
title: Konfigurera en koppling för att arkivera Jive-data i Microsoft 365
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
description: Administratörer kan konfigurera en koppling för att importera och arkivera Jive-data från Veritas i Microsoft 365. Med den här anslutningen kan du arkivera data från tredje part i Microsoft 365 så att du kan använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part i organisationen.
ms.openlocfilehash: 35e6d8ee75d14943ea07fc1f6bce82f826b91297
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162437"
---
# <a name="set-up-a-connector-to-archive-jive-data"></a>Konfigurera en koppling för att arkivera Jive-data

Använd en Veritas-koppling i Microsoft 365 efterlevnadscenter om du vill importera och arkivera data från samarbetsplattformen till användarpostlådor i Microsoft 365 organisation. Veritas tillhandahåller en [Jive-koppling](https://globanet.com/jive/) som har konfigurerats för att hämta objekt från tredje parts datakälla (regelbundet) och sedan importera de objekten till Microsoft 365. Kopplingen omvandlar innehåll som e-postmeddelanden, chattar och bifogade filer från en användares Jive-konto till ett e-postmeddelandeformat och importerar sedan objekten till användarens postlåda i Microsoft 365.

När Jive-data har lagrats i användarnas postlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad. Om du använder en Jive-anslutning för att importera och arkivera data i Microsoft 365 kan detta hjälpa din organisation att följa myndighets- och regleringsprinciperna.

## <a name="overview-of-archiving-jive-data"></a>Översikt över arkivering av Jive-data

I följande översikt beskrivs hur du använder en koppling för att arkivera Jive-data i Microsoft 365.

![Arkivering av arbetsflöde för Jive-data](../media/JiveConnectorWorkflow.png)

1. Din organisation arbetar med Jive för att konfigurera en Jive-webbplats.

2. En gång per dygn kopieras objekt från Jive till webbplatsen Veritas Merge1. Kopplingen konverterar även innehållet i Jive-objekt till ett e-postmeddelandeformat.

3. Den Jive-koppling som du skapar i kompatibilitetscentret för Microsoft 365 ansluter till Veritas Merge1-webbplatsen varje dag och överför innehållet till en säker Azure Storage plats i Microsoft-molnet.

4. Kopplingen importerar de konverterade objekten till postlådorna för  specifika användare med hjälp av värdet för egenskapen E-post för den automatiska användarmappningen enligt beskrivningen [i steg 3.](#step-3-map-users-and-complete-the-connector-setup) En ny undermapp i mappen Inkorgen med namnet **Jive** skapas i användarnas postlådor och objekten importeras till den mappen. Kopplingen gör detta med hjälp av värdet för egenskapen *E-post.* Alla Jive-objekt innehåller den här egenskapen, som fylls i med e-postadressen för alla deltagare i objektet.

## <a name="before-you-begin"></a>Innan du börjar

- Skapa ett Veritas Merge1-konto för Microsoft-kopplingar. Om du vill skapa det här kontot [kontaktar du Veritas kundsupport.](https://www.veritas.com/content/support/) Du loggar in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar Jive-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-jive-connector"></a>Steg 1: Konfigurera Jive-kopplingen

Det första steget är att komma åt sidan Datakopplingar i Microsoft 365 **kompatibilitetscenter** och skapa en koppling för Jive-data.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka sedan på **Datakopplingar**  >  **Jive.**

2. På sidan **Jive** produktbeskrivning klickar du på **Lägg till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-the-jive-connector"></a>Steg 2: Konfigurera Jive-kopplingen

Det andra steget är att konfigurera Jive-kopplingen på webbplatsen Merge1. Mer information om hur du konfigurerar Jive-kopplingen finns i [Användarhandbok för slå samman1 kopplingar från tredje part.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf)

När du har **klickat &**  på Spara eller & visas sidan Användarmappning i kopplingsguiden i Microsoft 365 kompatibilitetscenter.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Om du vill mappa användare och slutföra anslutningskonfigurationen i Microsoft 365 efterlevnadscenter följer du stegen nedan:

1. På sidan **Koppla Jive användare till Microsoft 365 aktiverar** du automatisk användarmappning. Jive-objekten innehåller egenskapen *E-post,* som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Klicka **på** Nästa , granska dina inställningar och gå till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-jive-connector"></a>Steg 4: Övervaka Jive-kopplingen

När du har skapat Jive-kopplingen kan du visa kopplingsstatusen Microsoft 365 kompatibilitetscentret.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan **Jive-kopplingen** för att visa den utfällbara sidan. Den här sidan innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller information om de data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.