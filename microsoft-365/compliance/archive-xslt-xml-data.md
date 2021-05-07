---
title: Konfigurera en koppling för att arkivera XSLT-/XML-data i Microsoft 365
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
description: Administratörer kan konfigurera en koppling för att importera och arkivera XSLT-/XML-data från Veritas i Microsoft 365. Med den här kopplingen kan du arkivera data från datakällor från tredje part i Microsoft 365 så att du kan använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part i organisationen.
ms.openlocfilehash: 51b05f83c51626bc60dc19b5ec9a63750903281c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162410"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a>Konfigurera en koppling för att arkivera XSLT-/XML-data

Använd en Veritas-koppling i Microsoft 365 efterlevnadscenter om du vill importera och arkivera data från webbsidans källa till användarpostlådor i Microsoft 365 organisation. Veritas förser dig med en [XSLT/XML-koppling](https://globanet.com/xslt-xml) som möjliggör snabb utveckling av filer som skapas med hjälp av XSLT (Extensible Style sheet Language Transformations) för att omvandla XML-filer till andra filformat (till exempel HTML eller text) som kan importeras till Microsoft 365. Kopplingen konverterar innehållet i ett objekt från XSLT-/XML-källan till ett e-postmeddelandeformat och importerar sedan det konverterade objektet till Microsoft 365 postlådor.

När XSLT-/XML-data har lagrats i användarpostlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery och bevarandeprinciper och bevarandeetiketter. Om du använder en XSLT/XML-koppling för att importera och arkivera data i Microsoft 365 kan organisationen uppfylla regelverken och myndighetsprinciperna.

## <a name="overview-of-archiving-xsltxml-data"></a>Översikt över arkivering av XSLT/XML-data

I följande översikt beskrivs hur du använder en koppling för att arkivera XSLT-/XML-källdata i Microsoft 365.

![Arkivering av arbetsflöde för XSLT/XML-data](../media/XSLT-XMLConnectorWorkflow.png)

1. Din organisation arbetar med XSLT/XML-källan för att konfigurera och konfigurera en XSLT/XML-webbplats.

2. En gång per dygn kopieras chattmeddelanden från XSLT/XML-källan till Webbplatsen Veritas Merge1. Kopplingen konverterar också innehållet till ett e-postmeddelandeformat.

3. Den XSLT/XML-koppling som du skapar i kompatibilitetscentret för Microsoft 365, ansluter till Veritas Merge1-webbplatsen varje dag och överför meddelandena till en säker Azure Storage plats i Microsofts moln.

4. Kopplingen importerar de konverterade meddelandeobjekten till postlådorna  för specifika användare med värdet för e-postegenskapen för den automatiska användarmappningen enligt beskrivningen i steg 3. En ny undermapp i mappen Inkorgen med namnet **XSLT/XML** skapas i användarnas postlådor och meddelandeobjekten importeras till den mappen. Kopplingen gör detta med hjälp av värdet för egenskapen *E-post.* Alla meddelanden innehåller den här egenskapen, som fylls i med e-postadressen till alla deltagare i meddelandet.

## <a name="before-you-begin"></a>Innan du börjar

- Skapa ett Veritas Merge1-konto för Microsoft-kopplingar. Om du vill skapa det här kontot [kontaktar du Veritas kundsupport.](https://www.veritas.com/content/support/) Du loggar in på det här kontot när du skapar kopplingen i steg 1.

- Den användare som skapar XSLT/XML-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-an-xsltxml-connector"></a>Steg 1: Konfigurera en XSLT/XML-koppling

Det första steget är att få åtkomst till datakopplingarna i **kompatibilitetscentret** för Microsoft 365 och skapa en koppling för XSLT-/XML-data.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka sedan på **Datakopplingar**  >  **XSLT/XML.**

2. På **produktbeskrivningssidan för XSLT/XML** klickar du på **Lägg till ny koppling**.

3. Klicka på **Acceptera på** sidan **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-an-xsltxml-connector"></a>Steg 2: Konfigurera en XSLT/XML-koppling

Det andra steget är att konfigurera XSLT/XML-kopplingen på webbplatsen Merge1. Mer information om hur du konfigurerar XSLT/XML-kopplingen på Veritas Merge1-webbplatsen finns i Användarhandbok för Slå [samman1 kopplingar från tredje part.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)

När du har **klickat &**  på Spara eller & visas sidan Användarmappning i kopplingsguiden i Microsoft 365 kompatibilitetscenter.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

1. Om du vill mappa användare och slutföra anslutningskonfigurationen i Microsoft 365 efterlevnadscenter följer du stegen nedan:

2. På sidan **Mappa XSLT-/XML-användare Microsoft 365 användarna** aktiverar du automatisk användarmappning. XSLT/XML-objekten innehåller en egenskap med namnet *E-post,* som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

3. Klicka **på** Nästa , granska dina inställningar och gå till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-xsltxml-connector"></a>Steg 4: Övervaka XSLT/XML-kopplingen

När du har skapat XSLT/XML-kopplingen kan du visa kopplingsstatusen Microsoft 365 efterlevnadscenter.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. Klicka på **fliken Kopplingar och** välj sedan **XSLT/XML-kopplingen för** att visa den utfällade sidan. Den här sidan innehåller egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.