---
title: Om utvärderingsversionen av Microsoft Defender Office 365
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
ms.openlocfilehash: 50060e36a0dd6d82ccbdf6d2bb8a00b2bf5e9d6d
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53195015"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>Om utvärderingsversionen av Microsoft Defender Office 365

Microsoft Defender för Office 365 skyddar organisationen mot skadliga hot som kan orsakas av e-postmeddelanden, länkar (URL:er) och samarbetsverktyg. Defender för Office 365 innehåller:

- **Principer för hotskydd**: Definiera skyddsprinciper för hot för att ange rätt skyddsnivå för din organisation.
- **Rapporter**: Visa rapporter i realtid och övervaka Defender för Office 365 prestanda i organisationen.
- **Funktioner för undersökning av hot och svar**: Använd verktygen för nya funktioner för att undersöka, förstå, simulera och förhindra hot.
- **Automatiserade funktioner för undersökning och svar**: Spara tid och ansträngning för att undersöka och mildra hot.

En utvärderingsversion av Microsoft Defender för Office 365 är det enklaste sättet att prova funktionerna i Defender för Office 365, och det tar bara några få klick att konfigurera den. När utvärderingsversionen är klar är alla Defender för Office 365 abonnemang 1 och abonnemang 2 tillgängliga i organisationen i upp till 90 dagar.

> [!NOTE]
> Den automatiska konfiguration som beskrivs i den här artikeln finns för närvarande i offentlig förhandsversion och kanske inte är tillgänglig på din plats.

## <a name="terms-and-conditions"></a>Villkor

Utvärderingsversionen av Defender Office 365 är tillgänglig i 90 dagar och kan initieras för alla dina användare. Mer information finns i [Microsoft Defender för Office 365 villkor för utvärderingsversion &](defender-for-office-365-trial-terms-and-conditions.md).

## <a name="set-up-a-defender-for-office-365-trial"></a>Konfigurera en Defender för Office 365 utvärderingsversion

Med en utvärderingsversion kan organisationer enkelt konfigurera och konfigurera Defender Office 365 funktioner. Under installationen används principer som är exklusiva för Defender för Office 365 (särskilt [Valv-bilagor,](safe-attachments.md) [Valv-länkar och personifieringsskydd](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)i principer för skräppostskydd) med standardmallen för förinställda [säkerhetsprinciper.](preset-security-policies.md) [](safe-links.md)

Som standard är de här principerna begränsade till alla användare i organisationen, men administratörer kan anpassa principerna under eller efter installationen så att de endast gäller för specifika användare.

Under installationen konfigureras Defender Office 365 svarsfunktioner (finns i Defender för Office 365 P2 eller motsvarande) också för hela organisationen. Det krävs ingen principomfång.

## <a name="licensing"></a>Licensiering

Som en del av utvärderingsversionen används licenserna Office 365 Defender för företag automatiskt för organisationen. Licenserna är kostnadsfria under de första 90 dagarna.

## <a name="permissions"></a>Behörigheter

För att starta eller avsluta utvärderingsversionen måste du vara medlem i rollerna **Global administratör** eller **Säkerhetsadministratör** i Azure Active Directory. Mer information finns i [Om administratörsroller.](../../admin/add-users/about-admin-roles.md)

## <a name="additional-information"></a>Ytterligare information

När du har registrerat dig för utvärderingsversionen kan det ta upp till 2 timmar innan ändringarna och uppdateringarna blir tillgängliga. Dessutom måste administratörer logga ut och logga in igen för att se ändringarna.

Administratörer kan inaktivera utvärderingsversionen när som helst genom att gå <> kort.

## <a name="availability"></a>Tillgänglighet

Utvärderingsversionen av Defender för Office 365 lanseras gradvis till befintliga kunder som uppfyller vissa villkor (inklusive geografi) och som inte har befintliga licenser för Defender för Office 365 abonnemang 1 eller abonnemang 2 (ingår i deras prenumeration eller som ett tillägg).

## <a name="learn-more-about-defender-for-office-365"></a>Läs mer om Defender för Office 365

Defender för Office 365 hjälper organisationer att skydda sitt företag genom att erbjuda ett omfattande utbud av funktioner.

Du kan också läsa mer om Defender för Office 365 i den här [interaktiva guiden.](https://techcommunity.microsoft.com/t5/video-hub/protect-your-organization-with-microsoft-365-defender/m-p/1671189)

![Konceptuellt diagram Office 365 Microsoft Defender](../../media/microsoft-defender-for-office-365.png)

### <a name="prevention"></a>Skydd

En robust filtreringsstack förhindrar ett brett utbud av volymbaserade och riktade angrepp, inklusive affärs-e-postkompromettering, autentiseringsuppgifter för nätfiske, utpressningstrojaner och avancerad skadlig programvara.

- [Principer för skydd mot nätfiske: exklusiva inställningar i Defender för Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
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
- Integrering med [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

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
