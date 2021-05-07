---
title: Konfigurera och visa varningar för principer för dataförlustskydd
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
description: Lär dig att definiera och hantera varningar för principer för skydd mot dataförlust.
ms.openlocfilehash: ee04f6080edcde86dc39c7f4aa43130223fee8bf
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "52162654"
---
# <a name="configure-and-view-alerts-for-data-loss-prevention-polices"></a>Konfigurera och visa varningar för dataförlustskydd

Skydd mot dataförlust (DLP) kan vidta skyddsåtgärder för att förhindra oavsiktlig delning av känsliga objekt. När en åtgärd vidtas på ett känsligt objekt kan du få ett meddelande genom att konfigurera aviseringar för DLP. I den här artikeln beskrivs hur du definierar principer för avancerade aviseringar som är kopplade till DLP-principer (dataförlustskydd). Du får se hur du använder den nya instrumentpanelen för hantering av DLP-aviseringar i [Microsoft 365 efterlevnadscenter](https://compliance.microsoft.com/) för att visa aviseringar, händelser och tillhörande metadata för DLP-principfel.

<!-- LEFT OFF HERE-->

## <a name="features"></a>Funktioner

Följande funktioner är en del av detta:

-   **Instrumentpanelen för** DLP-aviseringshantering: [I Microsoft 365](https://compliance.microsoft.com/)efterlevnadscenter visar den här instrumentpanelen aviseringar för DLP-principer som tillämpas på följande arbetsbelastningar:

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   Enheter
-   **Avancerade alternativ för aviseringskonfiguration:** De här alternativen är en del av redigeringsflödet för DLP-principen. Använd dem för att skapa avancerade aviseringskonfigurationer. Du kan skapa en avisering med bara en händelse eller en aggregerad avisering, baserat på antalet händelser eller storleken på de läckta data.

## <a name="before-you-begin"></a>Innan du börjar

Innan du börjar kontrollerar du att du har de krav som krävs:

-   Licensiering för Instrumentpanelen för hantering av DLP-aviseringar
-   Licensiering för alternativ för aviseringskonfiguration
-   Roller

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Licensiering för Instrumentpanelen för DLP-aviseringshantering

Alla berättigade klientorganisationar för Office 365 DLP kan komma åt den nya Instrumentpanelen för DLP-aviseringshantering. För att komma igång bör du vara berättigad till DLP Office 365 för Exchange Online, SharePoint Online och OneDrive för företag. Mer information om licenskraven för Office 365 DLP finns i Vilka licenser tillhandahåller rättigheter som en användare kan dra [nytta av tjänsten?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)

Kunder som använder Slutpunkt DLP som är kvalificerade för [Teams DLP](dlp-microsoft-teams.md) ser deras DLP-principaviseringar och Teams DLP-principaviseringar på instrumentpanelen för hantering av DLP-aviseringar. [](endpoint-dlp-learn-about.md)

### <a name="licensing-for-alert-configuration-options"></a>Licensiering för alternativ för aviseringskonfiguration

-   **Aviseringskonfiguration** för enstaka händelser : Organisationer som har en E1-, F1- eller G1-prenumeration eller en E3- eller G3-prenumeration kan bara skapa aviseringsprinciper där en avisering utlöses varje gång en aktivitet inträffar.
-   **Aggregerad aviseringskonfiguration:** Om du vill konfigurera principer för aggregerad avisering baserat på ett tröskelvärde måste du ha någon av följande konfigurationer:
    -   En E5- eller G5-prenumeration
    -   En E1-, F1- eller G1-prenumeration eller en E3- eller G3-prenumeration som innehåller någon av följande funktioner:
        -   Office 365 Advanced Threat Protection Plan 2
        -   Microsoft 365 E5 Compliance
        -   Microsoft 365 för eDiscovery- och Audit-tillägg

### <a name="roles"></a>Roller

Om du vill visa instrumentpanelen för hantering av DLP-aviseringar eller redigera alternativ för aviseringskonfiguration i en DLP-princip måste du vara medlem i någon av dessa rollgrupper:

-   Efterlevnadsadministratör
-   Dataadministratör för efterlevnad
-   Säkerhetsadministratör
-   Säkerhetsoperatör
-   Säkerhetsläsare

För att komma åt Instrumentpanelen för hantering av DLP-aviseringar behöver du rollen Hantera aviseringar och någon av följande roller:

-   DLP-efterlevnadshantering
-   View-Only DLP-efterlevnadshantering

## <a name="alert-configuration-experience"></a>Avisering om konfiguration

Om du är berättigad till [konfigurationsalternativ](#licensing-for-alert-configuration-options)för aggregerade aviseringar visas följande infogade alternativ i redigeringsupplevelsen för DLP-principen.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Skärmbild som visar alternativ för incidentrapporter för användare som är kvalificerade för konfigurationsalternativ för aggregerade aviseringar." border="false":::

Du kan använda de här konfigurationsalternativen för aviseringar om du vill konfigurera en inställning som definierar hur ofta en matchning av DLP-regler kan uppstå innan en avisering utlöses. Med den här konfigurationen kan du konfigurera en princip för att generera en avisering varje gång en aktivitet matchar principvillkoren eller när ett visst tröskelvärde överskrids, baserat på antalet aktiviteter eller baserat på mängden data som förts över.

Om du är berättigad till konfigurationsalternativ för aviseringar för enstaka händelser visas följande alternativ för aviseringskonfiguration i [DLP-principens](#licensing-for-alert-configuration-options)redigeringsupplevelse. Använd det här alternativet om du vill skapa en avisering som skapas varje gång en DLP-regelmatchning sker på grund av en användaraktivitet.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Skärmbild som visar alternativ för incidentrapporter för användare som är kvalificerade för konfigurationsalternativ för aviseringar för enstaka händelser." border="false":::

## <a name="dlp-alert-management-dashboard"></a>Instrumentpanelen för DLP-aviseringshantering

Så här arbetar du med Instrumentpanelen för DLP-aviseringshantering:

1.  Gå [till Microsoft 365 dataförlustskydd](https://www.compliance.microsoft.com)i **säkerhets- och efterlevnadscentret.**

2.  Välj fliken **Aviseringar för** att visa instrumentpanelen för DLP-aviseringar.

    -   Välj filter för att förfina listan med aviseringar. Välj **Anpassa kolumner** för att visa de egenskaper du vill se. Du kan också välja att sortera aviseringarna i stigande eller fallande ordning i en kolumn.
    -   Välj en avisering om du vill se mer information:

        :::image type="content" source="../media/alert-details.png" alt-text="Skärmbild som visar aviseringsinformation på instrumentpanelen för hantering av DLP-aviseringar." border="false":::

1.  Välj fliken **Händelser** om du vill visa alla händelser som är associerade med aviseringen. Du kan välja en viss händelse om du vill visa dess information.
    I följande tabell visas en del av händelseinformationen.
    
    | Kategori          | Egenskapsnamn                 | Beskrivning                                                                | Tillämpliga händelsetyper                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*Händelseinformation*||
    |      | ID                            | Unikt ID som är kopplat till händelsen                                        | Alla händelser                               |
    |                   | Plats                      | Arbetsbelastning där händelsen identifierades                                      | Alla händelser                               |
    |                   | Tid för aktivitet              | Tid för användaraktiviteten som orsakade DLP-överträdelse                    | Alla händelser                               |
    |*Berörda enheter*||
    |  | Användare                          | Användare som orsakade DLP-överträdelse                                          | Alla händelser                               |
    |                   | Hostname                      | Värdnamn för datorn där DLP-intrånget upptäcktes              | Enheter-händelser                           |
    |                   | IP-adress                    | DATORNs IP-adress                                                  | Enheter-händelser                           |
    |                   | Sökväg                     | Absolut sökväg till filen som är involverad i intrånget                        | SharePoint, OneDrive och enheter |
    |                   | E-postmottagare              | Mottagare av e-postmeddelandet som bryter mot DLP-principen                       | Exchange händelser                          |
    |                   | Ämne för e-post                 | E-postmeddelandets ämne som bryter mot DLP-principen                          | Exchange händelser                          |
    |                   | E-postbilagor             | Namnen på de bifogade filerna i e-postmeddelandet som bryter mot DLP-principen         | Exchange händelser                          |
    |                   | Webbplatsägare                    | Namnet på webbplatsägaren                                                     | SharePoint och OneDrive händelser           |
    |                   | Webbplats-URL                      | Fullständig URL för webbplatsen SharePoint eller OneDrive webbplats                                | SharePoint och OneDrive händelser           |
    |                   | Fil skapad                  | Tidpunkt då filen skapades                                                      | SharePoint och OneDrive händelser           |
    |                   | Fil som senast ändrades            | Tidpunkten för den senaste ändringen av filen                                  | SharePoint och OneDrive händelser           |
    |                   | Filstorlek                     | Storlek på filen                                                           | SharePoint och OneDrive händelser           |
    |                   | Filägare                    | Filens ägare                                                          | SharePoint och OneDrive händelser           |
    |*Principinformation*||
    |     | Matchad DLP-princip            | Namn på den DLP-princip som matchades                                    | Alla händelser                               |
    |                   | Regelmatchad                  | Namnet på DLP-regeln i den DLP-princip som matchades                    | Alla händelser                               |
    |                   | Känsliga informationstyper har upptäckts | Typer av känslig information som identifierats som en del av DLP-principen | Alla händelser                               |
    |                   | Åtgärder som vidtas                 | Åtgärder som vidtas som en del av den matchande DLP-principen                          | Alla händelser                               |
    |                   | Användarprincip överrode          | Om användaren ska overrode principen via principtipset                | Alla händelser                               |
    |                   | Åsidosätt justeringstext   | Justering som angetts för att åsidosätta principtipset                          | Alla händelser                               |
    
1.  Välj fliken **Typer av känslig information** om du vill visa information om de typer av känslig information som upptäckts i innehållet. Information som ingår är förtroende och antal.

2.  När du har undersökt aviseringen väljer **du Hantera avisering** för att ändra status (**Aktiv**, **Undersöker,** **Avvisad** eller **Löst**). Du kan också lägga till kommentarer och tilldela aviseringen till någon i organisationen.

    -   Om du vill se historiken för arbetsflödeshantering väljer du **Hanteringslogg**.
    -   När du har vidta den åtgärd som krävs för aviseringen ställer du in statusen för aviseringen på **Matchad**.