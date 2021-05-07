---
title: Konfigurera en koppling till Webex Teams data i Microsoft 365
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
description: Administratörer kan konfigurera en anslutare för att importera och arkivera data från Veritas Webex-Teams-koppling i Microsoft 365. Med den här kopplingen kan du arkivera data från datakällor från tredje part i Microsoft 365 så att du kan använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part i organisationen.
ms.openlocfilehash: 654ca53fd4cd7c6091ff74360545ba335f753ffd
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162415"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>Konfigurera en koppling för att arkivera Webex-Teams data

Använd en Veritas-koppling i kompatibilitetscentret för Microsoft 365 om du vill importera och arkivera data från Webex Teams till användarpostlådor i Microsoft 365 organisation. Veritas innehåller en [Webex Teams-anslutning](https://globanet.com/webex-teams/) som är konfigurerad för att spara Webex-Teams-kommunikationsobjekt och importera dem till Microsoft 365. Kopplingen omvandlar innehåll från Webex Teams, till exempel privata chattar, gruppkonversationer, kanalkonversationer och bifogade filer från organisationens Webex Teams-konto, till ett e-postmeddelandeformat och importerar sedan dessa objekt till användarens postlåda i Microsoft 365.

När Webex Teams data lagras i användarpostlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad. Genom att använda en Webex Teams anslutning för att importera och arkivera data i Microsoft 365 kan organisationen följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-webex-teams-data"></a>Översikt över arkivering av Webex Teams data

I följande översikt beskrivs hur du använder en koppling för att arkivera Webex-Teams data i Microsoft 365.

![Arkivering av arbetsflöde för Webex Teams data](../media/WebexTeamsConnectorWorkflow.png)

1. Din organisation arbetar med Webex Teams att konfigurera och konfigurera en Webex-Teams webbplats.

2. En gång per dygn Teams Webex-objekt till webbplatsen Veritas Merge1. Kopplingen konverterar även Webex-Teams till ett e-postmeddelandeformat.

3. Den Webex Teams-koppling som du skapar i Microsoft 365 efterlevnadscenter, ansluter till Veritas Merge1 varje dag och överför Webex Teams-objekt till en säker Azure Storage-plats i Microsoft-molnet.

4. Kopplingen importerar objekt till specifika användares postlådor med  värdet för egenskapen E-post för den automatiska användarmappningen enligt beskrivningen [i steg 3.](#step-3-map-users-and-complete-the-connector-setup) En undermapp i mappen Inkorgen med namnet **Webex Teams** skapas i användarnas postlådor och objekten importeras till den mappen. Kopplingen gör detta med hjälp av värdet för egenskapen *E-post.* Alla Webex Teams postobjekt innehåller den här egenskapen, som fylls i med e-postadresserna för varje deltagare i objektet.

## <a name="before-you-begin"></a>Innan du börjar

- Skapa ett Veritas Merge1-konto för Microsoft-kopplingar. Om du vill skapa det här kontot [kontaktar du Veritas kundsupport.](https://globanet.com/ms-connectors-contact) Du loggar in på det här kontot när du skapar kopplingen i steg 1.

- Skapa ett program för [https://developer.webex.com/](https://developer.webex.com) att hämta data från webex-Teams konto. Stegvisa instruktioner för hur du skapar programmet finns i [Användarhandbok för slå samman1 tredjepartskopplingar](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)

   När du skapar det här programmet genererar Webex-plattformen en uppsättning unika autentiseringsuppgifter. Dessa autentiseringsuppgifter används i steg 2 när du konfigurerar Webex Teams anslutningen på Global Merge1-webbplatsen.

- Den användare som skapar Webex Teams-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-webex-teams-connector"></a>Steg 1: Konfigurera Webex-Teams-

Det första steget är att få tillgång till **Datakopplingar** och konfigurera [Webex-Teams.](https://globanet.com/webex-teams/)

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka på **Datakopplingar**  >  **Webex Teams**.

2. På sidan **Webex Teams** produktbeskrivning klickar du på Lägg **till koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-the-webex-teams-connector-on-the-veritas-merge1-site"></a>Steg 2: Konfigurera Webex Teams-kopplingen på Veritas Merge1-webbplatsen

Det andra steget är att konfigurera Webex Teams-kopplingen på Merge1-webbplatsen. Mer information om hur du konfigurerar Webex Teams-koppling finns i [Användarhandbok för Slå samman1 tredjepartskopplingar.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)

När du har **klickat &**  på Spara eller & visas sidan Användarmappning i kopplingsguiden i Microsoft 365 kompatibilitetscenter.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Om du vill mappa användare och slutföra anslutningskonfigurationen i Microsoft 365 efterlevnadscenter gör du så här:

1. På sidan **Karta Webex Teams till användare Microsoft 365 aktiverar** du automatisk användarmappning. Webex-Teams innehåller en egenskap med namnet *E-post,* som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Klicka **på** Nästa, granska dina inställningar och gå sedan till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-webex-teams-connector"></a>Steg 4: Övervaka Webex-Teams kopplingen

När du har skapat Webex Teams-anslutningen kan du visa anslutningsstatusen i Microsoft 365 kompatibilitetscenter.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar** och välj sedan **webbex-Teams** att visa den utfällliga sidan. Den här sidan innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller information om de data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.