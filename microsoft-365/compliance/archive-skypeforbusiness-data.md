---
title: Konfigurera en koppling för att arkivera Skype för företag data i Microsoft 365
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
description: Lär dig att konfigurera och använda en koppling i Microsoft 365 Efterlevnadscenter för att importera och arkivera data från Skype för företag till Microsoft 365.
ms.openlocfilehash: 93128af0c7f305cb2bef55efd5520de77555a222
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054870"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-data-preview"></a>Konfigurera en koppling för att arkivera Skype för företag data (förhandsgranskning)

Använd en Veritas-koppling i Microsoft 365 Efterlevnadscenter om du vill importera och arkivera data från Skype för företag-plattformen till användarpostlådor i Microsoft 365 organisation. Veritas innehåller [en Skype för företag-koppling](https://www.veritas.com/en/au/insights/merge1/skype-for-business) som har konfigurerats för att hämta objekt från tredje parts datakälla (regelbundet) och importera de objekten till Microsoft 365. Kopplingen konverterar innehåll, till exempel meddelanden mellan användare, fortlöpande chattar och konferensmeddelanden, från Skype för företag till ett e-postmeddelandeformat och importerar sedan objekten till användarens postlåda i Microsoft 365.

När Skype för företag data lagras i användarnas postlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter. Genom att Skype för företag en anslutare för att importera och arkivera data i Microsoft 365 kan detta hjälpa din organisation att följa myndighets- och regelpolicyn.

## <a name="overview-of-archiving-skype-for-business-data"></a>Översikt över arkivering Skype för företag data

I följande översikt beskrivs hur du använder en koppling för att arkivera Skype för företag data i Microsoft 365.

![Arkivering av arbetsflöde för Skype för företag data](../media/SkypeforBusinessConnectorWorkflow.png)

1. Din organisation arbetar med Skype för företag att konfigurera och konfigurera en Skype för företag webbplats.

2. En gång per dygn Skype för företag objekt till webbplatsen Veritas Merge1. Kopplingen konverterar också alla Skype för företag till ett e-postmeddelandeformat.

3. Den Skype för företag-koppling som du skapar i Microsoft 365 Efterlevnadscenter ansluter till Veritas Merge1-webbplatsen varje dag och överför Skype för företag-innehållet till en säker Azure Storage-plats i Microsoft-molnet.

4. Kopplingen importerar de konverterade objekten till postlådorna  för specifika användare med värdet för egenskapen E-post för den automatiska användarmappningen enligt beskrivningen [i steg 3.](#step-3-map-users-and-complete-the-connector-setup) En undermapp i mappen Inkorgen med **namnet Skype för företag** skapas i användarnas postlådor och objekt importeras till den mappen. Kopplingen gör detta med hjälp av värdet för egenskapen *E-post.* Alla Skype för företag innehåller den här egenskapen, som fylls i med e-postadresserna för varje deltagare i objektet.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

- Skapa ett Merge1-konto för Microsoft-kopplingar. Om du vill göra detta kontaktar [du Veritas kundsupport.](https://www.veritas.com/form/requestacall/ms-connectors-contact.html) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar Skype för företag-koppling i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-skype-for-business-connector"></a>Steg 1: Konfigurera Skype för företag koppling

Det första steget är att komma åt **sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter och skapa en koppling för Skype för företag data.

1. Gå till <https://compliance.microsoft.com> och klicka **på Datakopplingar**  >  **Skype för företag**.

2. På sidan **Skype för företag** produktbeskrivning klickar du på Lägg **till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-the-skype-for-business-on-the-veritas-merge1-site"></a>Steg 2: Konfigurera Skype för företag på Webbplatsen Veritas Merge1

Det andra steget är att konfigurera Skype för företag-kopplingen på Veritas Merge1-webbplatsen. Mer information om hur du konfigurerar Skype för företag-koppling finns i [Användarhandbok för slå samman1 kopplingar från tredje part.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf)

När du **klickar & på** Spara  eller slutför visas sidan Användarmappning i kopplingsguiden Microsoft 365 Efterlevnadscenter objekt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Om du vill mappa användare och slutföra anslutningskonfigurationen i Microsoft 365 Efterlevnadscenter följer du dessa steg:

1. På sidan **Mappa Skype för företag till användare Microsoft 365** aktiverar du automatisk användarmappning. I Skype för företag innehåller egenskapen *E-post,* som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Klicka **på** Nästa, granska dina inställningar och gå sedan till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-skype-for-business-connector"></a>Steg 4: Övervaka Skype för företag koppling

När du har Skype för företag en koppling kan du visa kopplingsstatusen i Microsoft 365 Efterlevnadscenter.

1. Gå till <https://compliance.microsoft.com/> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan fliken **Skype för företag** att visa den utfällade sidan, som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.
