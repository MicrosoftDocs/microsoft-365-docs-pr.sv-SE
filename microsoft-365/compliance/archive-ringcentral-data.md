---
title: Konfigurera en koppling för att arkivera RingCentral-data i Microsoft 365
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
description: Administratörer kan konfigurera en koppling för att importera och arkivera RingCentral-data från Veritas till Microsoft 365. Med den här kopplingen kan du arkivera data från datakällor från tredje part i Microsoft 365. När du har arkiverat dessa data kan du använda efterlevnadsfunktioner som bevarande av juridiska regler, eDiscovery och bevarandeprinciper för att hantera data från tredje part.
ms.openlocfilehash: 57c993ce99556677c0161649254b5ab43caace0e
ms.sourcegitcommit: 5d3086da935d4ddc8caf79ff19e3afda812fd061
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2021
ms.locfileid: "53244022"
---
# <a name="set-up-a-connector-to-archive-ringcentral-data"></a>Konfigurera en koppling för att arkivera RingCentral-data

Använd en Veritas-koppling i Microsoft 365 Efterlevnadscenter om du vill importera och arkivera data från RingCentral-plattformen till användarpostlådor i Microsoft 365 organisation. Veritas tillhandahåller en [RingCentral-koppling](https://www.veritas.com/insights/merge1/ringcentral) som är konfigurerad för att hämta objekt från tredje parts datakälla och importera objekten till Microsoft 365. Kopplingen omvandlar innehåll som chattar, bifogade filer, uppgifter, anteckningar och inlägg från RingCentral till ett e-postmeddelandeformat och importerar sedan dessa objekt till användarnas postlådor i Microsoft 365.

När RingCentral-data har lagrats i användarnas postlådor kan du använda Microsoft 365 efterlevnadsfunktioner, till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter. Att använda en RingCentral-koppling för att importera och arkivera data i Microsoft 365 kan hjälpa din organisation att följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-ringcentral-data"></a>Översikt över arkivering av RingCentral-data

I följande översikt beskrivs hur du använder en koppling för att arkivera RingCentral-data i Microsoft 365.

![Arkivering av arbetsflöde för RingCentral-data](../media/RingCentralConnectorWorkflow.png)

1. Din organisation arbetar med RingCentral för att konfigurera och konfigurera en RingCentral-webbplats.

2. En gång per dygn kopieras RingCentral-objekt till Webbplatsen Veritas Merge1. Kopplingen konverterar även RingCentral-objekt till ett e-postmeddelandeformat.

3. Den RingCentral-koppling som du skapar i Microsoft 365 Efterlevnadscenter, ansluter till Veritas Merge1-webbplatsen varje dag och överför RingCentral-innehållet till en säker Azure Storage plats i Microsoft-molnet.

4. Kopplingen importerar de konverterade objekten till postlådorna  för specifika användare med värdet för egenskapen E-post för den automatiska användarmappningen enligt beskrivningen [i steg 3.](#step-3-map-users-and-complete-the-connector-setup) En undermapp i mappen Inkorg med namnet **RingCentral** skapas i användarnas postlådor och objekt importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Alla RingCentral-objekt innehåller den här egenskapen, som fylls i med e-postadressen för alla deltagare i objektet.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

- Skapa ett Merge1-konto för Microsoft-kopplingar. Om du vill skapa det här kontot [kontaktar du Veritas kundsupport.](https://www.veritas.com/form/requestacall/ms-connectors-contact) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Skapa ett RingCentral-program för att hämta data från ditt RingCentral-konto. Stegvisa instruktioner för hur du skapar programmet finns i [Användarhandbok för slå samman1 kopplingar från tredje part.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf)

- Den användare som skapar RingCentral-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-ringcentral-connector"></a>Steg 1: Konfigurera RingCentral-kopplingen

Det första steget är att komma åt **sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter och skapa en koppling för RingCentral-data.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar**  >  **RingCentral.**

2. På sidan **RingCentrals** produktbeskrivning klickar du på **Lägg till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-the-ringcentral-on-the-veritas-merge1-site"></a>Steg 2: Konfigurera RingCentral på Webbplatsen Veritas Merge1

Det andra steget är att konfigurera RingCentral-kopplingen på Veritas Merge1-webbplatsen. Mer information om hur du konfigurerar RingCentral-kopplingen finns i [Användarhandbok för slå samman1 kopplingar från tredje part.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf)

När du klickar **& på** Spara  och slutför visas sidan Användarmappning i kopplingsguiden Microsoft 365 Efterlevnadscenter objekt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Om du vill mappa användare och slutföra anslutningskonfigurationen i Microsoft 365 Efterlevnadscenter följer du dessa steg:

1. Aktivera automatisk **användarmappning på sidan Mappa RingCentral Microsoft 365 användarna.** RingCentral-objekten innehåller egenskapen *E-post,* som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Klicka **på** Nästa, granska dina inställningar och gå sedan till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-ringcentral-connector"></a>Steg 4: Övervaka RingCentral-kopplingen

När du har skapat RingCentral-kopplingen kan du visa kopplingsstatusen i Microsoft 365 Efterlevnadscenter.

1. Gå till <https://compliance.microsoft.com/> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan **RingCentral-koppling** för att visa den utfällliga sidan, som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.
