---
title: Komma igång med instrumentpanelen för dataförlustskyddsvarningar
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Kom igång med att definiera och hantera aviseringar för principer för dataförlustskydd.
ms.openlocfilehash: ad117eb0c5460b90c92c664f0c233b81d1882327
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843872"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a>Komma igång med instrumentpanelen för dataförlustskyddsvarningar

DLP-principer (Data Loss Prevention) kan vidta skyddsåtgärder för att förhindra oavsiktlig delning av känsliga objekt. När en åtgärd vidtas på ett känsligt objekt kan du få ett meddelande genom att konfigurera aviseringar för DLP. I den här artikeln beskrivs hur du definierar principer för avancerade aviseringar som är kopplade till DLP-principer (dataförlustskydd). Du får se hur du använder instrumentpanelen för hantering av [DLP-aviseringar](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) i [Microsoft 365 efterlevnadscenter](https://compliance.microsoft.com/) för att visa aviseringar, händelser och tillhörande metadata för DLP-principfel.

Om DLP-aviseringar är nytt för dig bör du läsa Mer om instrumentpanelen för skydd mot [dataförlust](dlp-alerts-dashboard-learn.md)

## <a name="before-you-begin"></a>Innan du börjar

Innan du börjar kontrollerar du att du har de krav som krävs:

-   Licensiering för Instrumentpanelen för hantering av DLP-aviseringar
-   Licensiering för alternativ för aviseringskonfiguration
-   Roller

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Licensiering för Instrumentpanelen för DLP-aviseringshantering

Alla kvalificerade klientorganisationar för Office 365 DLP kan komma åt Instrumentpanelen för DLP-aviseringshantering. För att komma igång bör du vara berättigad till DLP Office 365 för Exchange Online, SharePoint Online och OneDrive för företag. Mer information om licenskraven för Office 365 DLP finns i Vilka licenser tillhandahåller rättigheter som en användare kan dra [nytta av tjänsten?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)

Kunder som använder Slutpunkt DLP som är kvalificerade för [Teams DLP](dlp-microsoft-teams.md) ser deras DLP-principaviseringar och Teams DLP-principaviseringar på instrumentpanelen för hantering av DLP-aviseringar. [](endpoint-dlp-learn-about.md)

Funktionen **för förhandsgranskning** av innehåll är endast tillgänglig för följande licenser:

- Microsoft 365 (E5)
- Office 365 (E5)
- Advanced Compliance (E5) add on
- Microsoft 365 E5/A5 Informationsskydd och styrning
- Efterlevnad i Microsft 365 E5/A5

### <a name="licensing-for-alert-configuration-options"></a>Licensiering för alternativ för aviseringskonfiguration

**Aviseringskonfiguration** för enstaka händelser : Organisationer som har en E1-, F1- eller G1-prenumeration eller en E3- eller G3-prenumeration kan bara skapa aviseringsprinciper där en avisering utlöses varje gång en aktivitet inträffar.

**Aggregerad aviseringskonfiguration:** Om du vill konfigurera principer för aggregerad avisering baserat på ett tröskelvärde måste du en av följande licenskonfigurationer:

- En E5- eller G5-prenumeration
- En E1-, F1- eller G1-prenumeration eller en E3- eller G3-prenumeration som innehåller någon av följande funktioner:
    - Office 365 Advanced Threat Protection Plan 2
    - Microsoft 365 E5 Compliance
    - Microsoft 365 för eDiscovery- och Audit-tillägg

### <a name="roles"></a>Roller


Om du vill visa instrumentpanelen för hantering av DLP-aviseringar eller redigera alternativ för aviseringskonfiguration i en DLP-princip måste du vara medlem i någon av dessa rollgrupper:

- Efterlevnadsadministratör
- Dataadministratör för efterlevnad
- Säkerhetsadministratör
- Säkerhetsoperatör
- Säkerhetsläsare

För att komma åt Instrumentpanelen för hantering av DLP-aviseringar behöver du:

- Hantera varningar

och någon av följande två roller:

- DLP-efterlevnadshantering
- View-Only DLP-efterlevnadshantering

För att komma åt funktionen Förhandsgranskning av innehåll och funktioner för matchat känsligt innehåll och kontext måste du vara medlem i:

- Rollgruppen Innehållsvisare i Innehållsutforskaren

som har rollen dataklassificeringsinnehållsläsare för tilldelad.

## <a name="dlp-alert-configuration"></a>Konfiguration av DLP-avisering

Information om hur du konfigurerar en avisering i DLP-principen finns i Här kan [du börja med skydd mot dataförlust.](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)

### <a name="aggregate-event-alert-configuration"></a>Konfiguration av mängdhändelseavisering

Om din organisation har licens för [konfigurationsalternativ](#licensing-for-alert-configuration-options)för aggregerade aviseringar visas de här alternativen när du skapar eller redigerar en DLP-princip.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Skärmbild som visar alternativ för incidentrapporter för användare som är kvalificerade för konfigurationsalternativ för aggregerade aviseringar." border="false":::

Med den här konfigurationen kan du konfigurera en princip för att generera en avisering varje gång en aktivitet matchar principvillkoren eller när ett visst tröskelvärde överskrids, baserat på antalet aktiviteter eller baserat på mängden data som förts över.

### <a name="single-event-alert-configuration"></a>Konfiguration av en händelseavisering

Om din organisation har licens för konfigurationsalternativ för aviseringar för enstaka händelser visas de här alternativen när du skapar eller redigerar en [DLP-princip.](#licensing-for-alert-configuration-options) Använd det här alternativet om du vill skapa en avisering som höjs varje gång en DLP-regel matchar.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Skärmbild som visar alternativ för incidentrapporter för användare som är kvalificerade för konfigurationsalternativ för aviseringar för enstaka händelser." border="false":::

## <a name="investigate-a-dlp-alert"></a>Undersöka en DLP-avisering

Så här arbetar du med Instrumentpanelen för DLP-aviseringshantering:

1. Gå [till Microsoft 365 dataförlustskydd](https://www.compliance.microsoft.com)i **säkerhets- och efterlevnadscentret.**
2. Välj fliken **Aviseringar för** att visa instrumentpanelen för DLP-aviseringar.
3. Välj en avisering om du vill se mer information:

:::image type="content" source="../media/alert-details.png" alt-text="Skärmbild som visar aviseringsinformation på instrumentpanelen för hantering av DLP-aviseringar." border="false":::

4. Välj fliken **Händelser** om du vill visa alla händelser som är associerade med aviseringen. Du kan välja en viss händelse om du vill visa dess information. En lista över en del av den tillgängliga händelseinformationen finns i Läs mer om instrumentpanelen [för skydd mot dataförlust](dlp-alerts-dashboard-learn.md).
5. Välj **Information** för att öppna **sidan** Översikt för aviseringen. Översiktssidan ger en sammanfattning:
    1. av vad som hände
    1. vem som utförde de åtgärder som orsakade principmatchning
    1. information om den matchade principen och mycket mer 

6. Välj fliken **Händelser** för att komma åt:
    1. innehåll som ingår
    1. Matchning av känslig information
    1. metadata

7. Välj fliken **Typer av känslig information** om du vill visa information om de typer av känslig information som upptäckts i innehållet. I informationen ingår konfidens, antal och innehåll som matchar den typ av känslig information.

8. När du har undersökt aviseringen går du tillbaka till fliken Översikt där du kan hantera triangeln och hantera dispositionen av aviseringen och lägga till kommentarer. 

- Om du vill se historiken för arbetsflödeshantering väljer du **Hanteringslogg**.
- När du har vidta den åtgärd som krävs för aviseringen ställer du in statusen för aviseringen på **Matchad**.

## <a name="see-also"></a>Se även

- [Läs mer om varningar om skydd mot dataförlust och instrumentpanelen för aviseringar](dlp-alerts-dashboard-learn.md)
- [Skapa, testa och justera en DLP-princip](create-test-tune-dlp-policy.md)