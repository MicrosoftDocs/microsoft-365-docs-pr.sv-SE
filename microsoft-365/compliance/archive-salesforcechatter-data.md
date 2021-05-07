---
title: Konfigurera en koppling för att arkivera Salesforce Chatter-data i Microsoft 365
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
description: Administratörer kan konfigurera en anslutare för att importera och arkivera Salesforce Chatter-data från Veritas till Microsoft 365. Med den här kopplingen kan du arkivera data från datakällor från tredje part i Microsoft 365. När du har arkiverat dessa data kan du använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part.
ms.openlocfilehash: c04dc3026eaa5abb23b332dbae826c052344da31
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162429"
---
# <a name="set-up-a-connector-to-archive-salesforce-chatter-data"></a>Konfigurera en koppling för att arkivera Salesforce Chatter-data

Använd en Veritas-koppling i Microsoft 365 efterlevnadscenter om du vill importera och arkivera data från Salesforce Chatter-plattformen till användarpostlådor i Microsoft 365 organisation. Veritas tillhandahåller en [Salesforce Chatter-koppling](http://globanet.com/chatter/) som fångar objekt från tredje parts datakälla och importerar dessa objekt till Microsoft 365. Kopplingen konverterar innehåll som chattar, bifogade filer och inlägg från Salesforce Chatter till ett e-postmeddelandeformat och importerar sedan dessa objekt till användarens postlåda i Microsoft 365.

När Salesforce Chatter-data har lagrats i användarpostlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter. Om du använder en Salesforce Chatter-koppling för att importera och arkivera data i Microsoft 365 kan din organisation följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-salesforce-chatter-data"></a>Översikt över arkivering av Salesforce Chatter-data

Följande översikt förklarar processen med att använda en koppling för att arkivera Salesforce Chatter-data i Microsoft 365.

![Arkivera arbetsflöde för Salesforce Chatter-data](../media/SalesforceChatterConnectorWorkflow.png)

1. Din organisation arbetar med Salesforce Chatter för att konfigurera och konfigurera en Salesforce Chatter-webbplats.

2. En gång per dygn kopieras Salesforce Chatter-objekt till webbplatsen Veritas Merge1. Kopplingen även Salesforce Chatt-objekt i ett e-postmeddelandeformat.

3. Den Salesforce Chatter-koppling som du skapar i kompatibilitetscentret för Microsoft 365, ansluter till Veritas Merge1-webbplatsen varje dag och överför chattinnehållet till en säker Azure Storage plats i Microsoft-molnet.

4. Kopplingen importerar de konverterade objekten till postlådorna  för specifika användare med värdet för egenskapen E-post för den automatiska användarmappningen enligt beskrivningen [i steg 3.](#step-3-map-users-and-complete-the-connector-setup) En undermapp i mappen Inkorg med namnet **Salesforce Chatter** skapas i användarnas postlådor och objekt importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Alla chattobjekt innehåller den här egenskapen, som fylls i med e-postadressen för alla deltagare i objektet.

## <a name="before-you-begin"></a>Innan du börjar

- Skapa ett Merge1-konto för Microsoft-kopplingar. Om du vill skapa ett konto kontaktar [du Veritas kundsupport.](https://www.veritas.com/content/support/) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- Skapa ett Salesforce-program och skaffa en token hos [https://salesforce.com](https://salesforce.com) . Du måste logga in på Salesforce-kontot som administratör och få en personlig token för användare för att importera data. Dessutom måste utlösare publiceras på chattwebbplatsen för att samla in uppdateringar, borttagningar och redigeringar. Dessa utlösare skapar ett inlägg på en kanal och Merge1 samlar in informationen från kanalen. Stegvisa instruktioner om hur du skapar programmet och hämtar token finns i Användarhandbok för Slå [samman1 tredjepartskopplingar.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf)

- Den användare som skapar Salesforce Chatter-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-salesforce-chatter-connector"></a>Steg 1: Konfigurera Salesforce Chatter-kopplingen

Det första steget är att komma åt **sidan Datakopplingar** i Microsoft 365 och skapa en anslutning för chattdata.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka sedan på **Datakopplingar**  >  **Salesforce Chatter**.

2. På **produktbeskrivningssidan för Salesforce Chatter** klickar du på **Lägg till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-the-salesforce-chatter-on-the-veritas-merge1-site"></a>Steg 2: Konfigurera Salesforce Chatter på webbplatsen Veritas Merge1

Det andra steget är att konfigurera Salesforce Chatter-kopplingen på Veritas Merge1-webbplatsen. Mer information om hur du konfigurerar Salesforce Chatter-koppling finns i [Användarhandbok för slå samman1 kopplingar från tredje part.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf)

När du klickar **& på** Spara  och slutför visas sidan Användarmappning i kopplingsguiden Microsoft 365 kompatibilitetscentret.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Om du vill mappa användare och slutföra anslutningskonfigurationen i Microsoft 365 efterlevnadscenter gör du så här:

1. Aktivera automatisk **användarmappning på sidan Mappa Salesforce Chatter Microsoft 365 användarna.** Salesforce Chatter-objekten innehåller egenskapen *E-post,* som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Klicka **på** Nästa, granska dina inställningar och gå sedan till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-salesforce-chatter-connector"></a>Steg 4: Övervaka Salesforce Chatter-kopplingen

När du har skapat Salesforce Chatter-kopplingen kan du visa anslutningsstatus i Microsoft 365 efterlevnadscenter.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och klicka sedan på **Salesforce Chatter-kopplingen** för att visa den utfällade sidan, som innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.