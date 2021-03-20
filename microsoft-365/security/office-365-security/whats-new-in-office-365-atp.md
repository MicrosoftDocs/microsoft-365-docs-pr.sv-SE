---
title: Vad är nytt i Microsoft Defender för Office 365
description: Läs mer om de nya funktionerna som är tillgängliga i den senaste versionen av Microsoft Defender för Office 365.
keywords: vad är nytt i Office 365 atp, ga, allmänt tillgänglig, funktioner, tillgänglig, ny
search.appverid: met150
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.date: 01/12/2021
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e2885f4db67f1508f4e7a3f354e11fb361265a3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907958"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a>Vad är nytt i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Den här artikeln innehåller nya funktioner i den senaste versionen av Microsoft Defender för Office 365. Funktioner som för närvarande finns i förhandsgranskningsvyn betecknas med **(förhandsversion).**

> [!TIP]
> Har du inte Microsoft Defender för Office 365 än? [Kontakta försäljning för att påbörja en utvärderingsversion](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html).

## <a name="februarymarch-2021"></a>Februari/mars 2021 

- Integrering av aviserings-ID (sökning med aviserings-ID Alert-Explorer navigering) i [sökupplevelser](threat-explorer.md)
- Öka gränserna för export av poster från 9 990 till 200 000 i [upplevelser för söker](threat-explorer.md)
- Utöka datalagrings- och sökbegränsningen i Utforskaren (och Realtidsidentifiering) för utvärderingsklienter från 7 (föregående gräns) till 30 dagar i [sökning](threat-explorer.md)
- Nya pivoter  för sökning som  kallas personifierad domän och personifierad användare i Utforskaren (och identifieringar i realtid) för att söka efter personifieringsattacker mot skyddade användare eller domäner. Mer information finns i [.](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains) (Microsoft Defender för Office 365 abonnemang 1 eller abonnemang 2)

## <a name="december-2020"></a>December 2020

- [Skydda som standard i Office 365](secure-by-default.md)
- Automatiska undersökningsförbättringar för: allmänna varningar för manuellt utlösta e-postundersökningar, behandla postlådeändringar som en separat enhetskategori, ta bort redundanta URL-blockåtgärder och skapa utgående e-postkluster för användare komprometterade undersökningar.

## <a name="november-2020"></a>November 2020

- Uppdaterade exportbegränsningar i Granska > Åtgärdscenter > åtgärd från e-postinskickning och åtgärdslogg (Defender för Office 365 abonnemang 2)

## <a name="septemberoctober-2020"></a>September/oktober 2020

- [Kontrollera principer med hjälp av Configuration Analyzer](configuration-analyzer-for-security-policies.md)
- Utökade funktioner i Hotutforskaren, inklusive populära användare, transportregler och kopplingar (Defender för Office 365-information i [Threat Explorer](threat-explorer.md) (e-post [tillåts/blockerades](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) av klientorganisations-/användarprincip) (Defender för Office 365 abonnemang 2)
- Surfa med URL-hot i [Threat Explorer](threat-explorer.md#threats-in-urls) (skadlig kod, nättjänst, skräppost eller ingen) (Defender för Office 365 Abonnemang 2)
- [Förbättringar av Söka i Utforskaren](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming) med uppdateringar kring hot, ytterligare åtgärder, leveransplatser och uppdaterad tidslinjevy (Defender för Office 365 abonnemang 2)

## <a name="julyaugust-2020"></a>Juli/augusti 2020

- [Förbättringar av upplevelsen när det gäller jagning](threat-explorer.md#improvements-to-threat-hunting-experience) (Microsoft Defender för Office 365 abonnemang 1 eller abonnemang 2)
- [Använd enkelt rekommenderade inställningar med hjälp av förinställda säkerhetsprinciper](preset-security-policies.md)

## <a name="marchapril-2020"></a>Mars/april 2020

- Möjligheten att hantera [komprometterade användarkonton med automatiserad undersökning och svar är](address-compromised-users-quickly.md) nu allmänt tillgänglig. (Microsoft Defender för Office 365 abonnemang 2)

## <a name="januaryfebruary-2020"></a>Januari/februari 2020

- [Allmän tillgänglighet för kampanjvyer i Microsoft Defender för Office 365](campaigns.md) (Microsoft Defender för Office 365 abonnemang 2)
- Förbättringar av [Hotutforskaren](threat-explorer.md) för att tillåta grupper med [](investigate-malicious-email-that-was-delivered.md)säkerhetsåtgärder att söka och filtrera på flera fält medan de undersöker e-post: (Microsoft Defender för Office 365 abonnemang 2)
  - Leveransplats och specialåtgärder
  - Directionality (inkommande, utgående eller årsorganisation)
  - Avancerade NOT-filter (de här avancerade filtreringsalternativen innehåller inte, inkluderar inte osv.)
  - Granular time filters (day, hour, half-hour)

- **Widgeten** Incidenter är nu **widgeten Åtgärdscenter.** (Om du vill visa dina säkerhetswidgetar går du till & Säkerhets- och **efterlevnadscenter** \> **Granska**.) (Microsoft Defender för Office 365 abonnemang 2)

- [Säkra dokument i Microsoft 365](safe-docs.md) **(förhandsversion)**

## <a name="december-2019"></a>December 2019

- [Exportera URL klicka på data för offlineanalys](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) (Microsoft Defender för Office 365 abonnemang 1 eller abonnemang 2)

- [Använda kampanjvyer i Microsoft Defender för Office 365 **(förhandsversion)**](campaigns.md) (Microsoft Defender för Office 365 abonnemang 2)

## <a name="november-2019"></a>November 2019

- [Ta en titta på nya komprometterade](address-compromised-users-quickly.md) funktioner för användaridentifiering och svar **(förhandsversion)**(Microsoft Defender för Office 365 abonnemang 2)

## <a name="september-2019"></a>September 2019

- [Använd automatisk undersökning och svarsfunktioner](automated-investigation-response-office.md) (Microsoft Defender för Office 365 abonnemang 2)

- Integrera med Microsoft Defender för automatiserad undersökning och svarshändelser med API:t för hanteringsaktivitet i [Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) (Defender för Office 365 abonnemang 2)

- [Visa e-posthuvudena och ladda ned brödtexten](investigate-malicious-email-that-was-delivered.md) för e-post (Microsoft Defender för Office 365 abonnemang 1 eller abonnemang 2)

## <a name="august-2019"></a>Augusti 2019

- [Visa tidslinjen för e-post](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) (Microsoft Defender för Office 365 abonnemang 1 eller abonnemang 2)

## <a name="july-2019"></a>Juli 2019

- [Kontrollera leveransåtgärden och platsen för e-postmeddelanden](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) (Microsoft Defender för Office 365 abonnemang 1 eller 2)

## <a name="june-2019"></a>Juni 2019

- [Visa nätfiske-URL:er och klicka på bedömningsdata](threat-explorer.md#view-phishing-url-and-click-verdict-data) (Microsoft Defender för Office 365 abonnemang 1 eller abonnemang 2)

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2

Visste du att Microsoft Defender för Office 365 är tillgängligt i två abonnemang? [Läs mer om vad varje abonnemang inkluderar](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2).

## <a name="see-also"></a>Se även

[Översikt över Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap)

[Tjänstbeskrivning för Microsoft Defender för Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)