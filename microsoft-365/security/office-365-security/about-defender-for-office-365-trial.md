---
title: Om utvärderingsversionen av Microsoft Defender för Office 365
f1.keywords: ''
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
ROBOTS: NOINDEX
description: Administratörer kan läsa mer om utvärderingsläget för Microsoft Defender för Office 365
ms.openlocfilehash: c2c1e44741a8604ce60586a85a28d32851285403
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207460"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>Om utvärderingsversionen av Microsoft Defender för Office 365

Microsoft Defender för Office 365 skyddar organisationen mot skadliga hot som kan orsakas av e-postmeddelanden, länkar (URL:er) och samarbetsverktyg. Defender för Office 365 innehåller:

- **Principer för hotskydd**: Definiera skyddsprinciper för hot för att ange rätt skyddsnivå för din organisation.
- **Rapporter**: Visa rapporter i realtid för att övervaka prestandan för Defender för Office 365 i organisationen.
- **Funktioner för undersökning av hot och svar**: Använd verktygen för nya funktioner för att undersöka, förstå, simulera och förhindra hot.
- **Automatiserade funktioner för undersökning och svar**: Spara tid och ansträngning för att undersöka och mildra hot.

En utvärderingsversion av Microsoft Defender för Office 365 är det enklaste sättet att prova funktionerna i Defender för Office 365, och det krävs bara några få klick för att konfigurera den. När utvärderingsversionen är klar är alla Defender för Office 365 abonnemang 1 och Abonnemang 2 tillgängliga i organisationen i upp till 90 dagar.

> [!NOTE]
> Den automatiska konfiguration som beskrivs i den här artikeln finns för närvarande i offentlig förhandsversion och kanske inte är tillgänglig på din plats.

## <a name="terms-and-conditions"></a>Villkor

Utvärderingsversionen av Defender för Office 365 är tillgänglig i 90 dagar och kan initieras för alla användare. Mer information finns i [Utvärderingsvillkor för Microsoft Defender för Office 365 & .](defender-for-office-365-trial-terms-and-conditions.md)

## <a name="set-up-a-defender-for-office-365-trial"></a>Konfigurera en utvärderingsversion av Defender för Office 365

Med en utvärderingsversion kan organisationer enkelt konfigurera och konfigurera funktionerna i Defender för Office 365. Under installationen tillämpas principer som är exklusiva för Defender för Office [](safe-links.md)365 (specifikt säkra bifogade [filer,](safe-attachments.md)säkra länkar och personifieringsskydd i principer för [skräppostskydd)](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)med standardmallen för förinställda [säkerhetsprinciper.](preset-security-policies.md)

Som standard är de här principerna begränsade till alla användare i organisationen, men administratörer kan anpassa principerna under eller efter installationen så att de endast gäller för specifika användare.

Under installationen konfigureras även MDO-svarsfunktioner (finns i MDO P2 eller motsvarande) för hela organisationen. Det krävs ingen principomfång.

## <a name="licensing"></a>Licensiering

Som en del av utvärderingsversionen tillämpas licenserna för Defender för Office 365 automatiskt på organisationen. Licenserna är kostnadsfria under de första 90 dagarna.

## <a name="permissions"></a>Behörigheter

För att starta eller avsluta utvärderingsversionen måste du vara medlem i rollerna **global administratör** eller **säkerhetsadministratör** i Azure Active Directory. Mer information finns i [Om administratörsroller.](../../admin/add-users/about-admin-roles.md)

## <a name="additional-information"></a>Ytterligare information

När du har registrerat dig för utvärderingsversionen kan det ta upp till 2 timmar innan ändringarna och uppdateringarna blir tillgängliga. Dessutom måste administratörer logga ut och logga in igen för att se ändringarna.

Administratörer kan inaktivera utvärderingsversionen när som helst genom att gå <> kort.

## <a name="availability"></a>Tillgänglighet

Utvärderingsversionen av Defender för Office 365 lanseras gradvis till befintliga kunder som uppfyller specifika villkor (inklusive geografi) och som inte har befintliga licenser för Defender för Office 365 abonnemang 1 eller abonnemang 2 (ingår i deras prenumeration eller som ett tillägg).

## <a name="learn-more-about-defender-for-office-365"></a>Läs mer om Defender för Office 365

Defender för Office 365 hjälper organisationer att skydda sitt företag genom att erbjuda ett omfattande utbud av funktioner.

Du kan också läsa mer om Defender för Office 365 i den här [interaktiva guiden.](https://techcommunity.microsoft.com/t5/video-hub/protect-your-organization-with-microsoft-365-defender/m-p/1671189)

![Konceptuellt diagram för Microsoft Defender för Office 365](../../media/microsoft-defender-for-office-365.png)

### <a name="prevention"></a>Skydd

En robust filtreringsstack förhindrar ett brett utbud av volymbaserade och riktade angrepp, inklusive affärs-e-postkompromettering, autentiseringsuppgifter för nätfiske, utpressningstrojaner och avancerad skadlig programvara.

- [Principer för skydd mot nätfiske: Exklusiva inställningar i Defender för Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [Säkra bifogade filer](safe-attachments.md)
- [Säkra länkar](safe-links.md)

### <a name="detection"></a>Identifiering

Branschledande AI identifierar skadligt och misstänkt innehåll och korrelerar attackmönster för att identifiera kampanjer som utformats för att undvika skydd.

- [Kampanjvyer i Microsoft Defender för Office 365](campaigns.md)

### <a name="investigation-and-hunting"></a>Undersökning och fiske

Kraftfulla funktioner hjälper dig att identifiera, prioritera och undersöka hot, med avancerade sökfunktioner för att spåra attacker i Office 365.

- [Identifiering av hot i Utforskaren och i realtid](threat-explorer.md)
- [Realtidsrapporter i Defender för Office 365](view-reports-for-mdo.md)
- [Hotspårningar – nytt och värt att uppmärksamma](threat-trackers.md)
- Integrering med [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)

### <a name="response-and-remediation"></a>Svar och åtgärder

Omfattande incidentsvar och automatiseringsfunktioner förstärker säkerhetsteamets effektivitet och effektivitet.

- [Automatisk undersökning och svar (AIR) i Microsoft Defender för Office 365](office-365-air.md)

### <a name="awareness-and-training"></a>Information och utbildning

Avancerade simulerings- och utbildningsfunktioner tillsammans med integrerade upplevelser i klientprogram gör användarna mer medvetna.

- [Kom igång med Attack simuleringsträning](attack-simulation-training-get-started.md)

### <a name="secure-posture"></a>Säker säkerhet

Rekommenderade mallar och konfigurationsinformation hjälper kunderna att få och vara säkra.

- [Förinställda säkerhetsprinciper i EOP och Microsoft Defender för Office 365](preset-security-policies.md)
- [Konfigurationsanalys för skyddsprinciper i EOP och Microsoft Defender för Office 365.](configuration-analyzer-for-security-policies.md)

## <a name="give-feedback"></a>Ge feedback

Din feedback hjälper oss att bli bättre på att skydda miljön mot avancerade attacker. Dela din upplevelse och intryck av produktfunktioner och utvärderingsresultat.
