---
title: Konfigurera en koppling för att arkivera taldata från röd sidor i Microsoft 365
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
description: Administratörer kan konfigurera en koppling för att importera och arkivera Tal-data från Red tail Speak från Veritas till Microsoft 365. Med den här kopplingen kan du arkivera data från datakällor från tredje part i Microsoft 365. När du har arkiverat dessa data kan du använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part.
ms.openlocfilehash: ee9540b4000387454eb177f864407e03abd25bc6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162433"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a>Konfigurera en koppling för arkivering av läs upp-data med röd detalj

Använd en Veritas-koppling i Microsoft 365 efterlevnadscenter om du vill importera och arkivera data från dialogrutan Detaljer till användarpostlådor i Microsoft 365 organisation. Veritas ger dig en [redtail speak-koppling](https://globanet.com/redtail/) som har konfigurerats för att hämta objekt från organisationens SFTP-server där objekten tas emot från Redtail. Kopplingen konverterar innehållet från Läs upp om till ett e-postmeddelandeformat och importerar sedan dessa objekt till användarens postlåda i Microsoft 365.

När data med funktionen Läs upp rödslåde har lagrats i användarnas postlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter. Om du importerar och arkiverar data i Microsoft 365 med hjälp av en koppling för tal i redtail kan det hjälpa organisationen att uppfylla myndighets- och regelprinciperna.

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Översikt över arkivering av data för beskrivning av omdetaljer

I följande översikt beskrivs hur du använder en koppling för att arkivera data i Microsoft 365.

![Arkiveringsarbetsflöde för data som läse upp i omdetaljer](../media/RedtailSpeakConnectorWorkflow.png)

1. Organisationen arbetar med Redtail Speak för att konfigurera och konfigurera en SMTP-gateway där meddelanden vidarebefordras från Redtail Speak till organisationens SFTP-server dagligen.

2. En gång per dygn kopieras objekten Läs upp igen till webbplatsen Veritas Merge1. Kopplingen konverterar också avse en redtail Speak-objekt till ett e-postmeddelandeformat.

3. Kopplingen Redtail Speak som du skapar i kompatibilitetscentret för Microsoft 365 ansluter till Veritas Merge1-webbplatsen varje dag och överför meddelandena till en säker Azure Storage plats i Microsoft-molnet.

4. Kopplingen importerar de konverterade objekten Med funktionen Beskrivning av omdetaljer till postlådorna för specifika användare med värdet för e-postegenskapen för den automatiska användarmappningen enligt beskrivningen [i steg 3.](#step-3-map-users-and-complete-the-connector-setup)  En undermapp i mappen Inkorgen med namnet **Taldetaljer** skapas i användarpostlådorna och objekten importeras till den mappen. Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.* Varje tal i redtail innehåller den här egenskapen, som fylls i med e-postadressen för varje deltagare i objektet.

## <a name="before-you-begin"></a>Innan du börjar

- Skapa ett Veritas Merge1-konto för Microsoft-kopplingar. Om du vill skapa ett konto kontaktar [du Veritas kundsupport.](https://www.veritas.com/content/support/) Du måste logga in på det här kontot när du skapar kopplingen i steg 1.

- I steg 2 måste du ange organisationens SFTP-server. Det här steget är nödvändigt så att Veritas Merge1 kan kontakta det och samla in data från Redtail Speak via SFTP.

- Den användare som skapar importverktyget för återdetaljer i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar på sidan Datakopplingar i Microsoft 365 kompatibilitetscenter. Den här rollen tilldelas inte till någon rollgrupp i Exchange Online som standard. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-set-up-the-redtail-speak-connector"></a>Steg 1: Konfigurera kopplingen För detaljer

Det första steget är att komma åt sidan Datakopplingar i **kompatibilitetscentret** Microsoft 365 och skapa en koppling för data av informationsdetaljer.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och välj **Datakopplingar** &gt; **Visa detaljer.**

2. På sidan **Beskrivning av detaljer väljer** du Lägg till ny **koppling**.

3. Välj **Acceptera på sidan** **Användningsvillkor.**

4. Ange ett unikt namn som identifierar kopplingen och välj sedan **Nästa**.

5. Logga in på ditt Merge1-konto för att konfigurera kopplingen.

## <a name="step-2-configure-the-redtail-speak-connector-on-the-veritas-merge1-site"></a>Steg 2: Konfigurera kopplingen För detaljer på webbplatsen Veritas Merge1

Det andra steget är att konfigurera kopplingen För detaljer på webbplatsen Merge1. Mer information om hur du konfigurerar anslutningen Visa detaljer finns i [Användarhandbok för](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf)koppling av koppling från tredje part .

När du **har & på Slutför** **visas** sidan Användarmappning i kopplingsguiden Microsoft 365 kompatibilitetscentret.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Om du vill mappa användare och slutföra anslutningskonfigurationen gör du så här:

1. Aktivera automatisk **användarmappning på sidan Visa Microsoft 365 för** användare på sidan Visa information om mappning. Objekten Med taldetaljer har egenskapen *E-post,* som innehåller e-postadresser för användare i organisationen. Om kopplingen kan associera den här adressen Microsoft 365 en användare importeras objekten till den användarens postlåda.

2. Välj **Nästa**, granska dina inställningar och gå till sidan **Datakopplingar** för att se förloppet för importen för den nya anslutningen.

## <a name="step-4-monitor-the-redtail-speak-connector"></a>Steg 4: Övervaka kopplingen För detaljer

När du har skapat kopplingen Visa detaljer kan du visa kopplingsstatusen i Microsoft 365 för efterlevnadscenter.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och välj **Datakopplingar i** det vänstra navigeringsfältet.

2. Välj fliken **Kopplingar och** välj sedan kopplingen Visa **detaljer** för att visa den utfällade sidan. På den här sidan visas egenskaper och information om kopplingen.

3. Under **Anslutningsstatus med källa** väljer du länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen. Den här loggen innehåller data som har importerats till Microsoft-molnet.

## <a name="known-issues"></a>Kända problem

- För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB. Stöd för större objekt blir tillgängligt vid ett senare tillfälle.