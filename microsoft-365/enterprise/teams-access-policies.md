---
title: Rekommenderade team policy-Microsoft 365 för företag | Microsoft-dok
description: Beskriver policyerna för Microsoft-rekommendationer om hur du skyddar Teams-kommunikation och fil åtkomst.
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 10/31/2019
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 41ead64a7a94dcd5afb22a311d7637326949fc7c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685660"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Policy rekommendationer för att skydda Teams, grupper och filer

I den här artikeln beskrivs hur du implementerar de rekommenderade identiteterna och enhets åtkomst principerna för att skydda Teams, grupper och innehåll som filer och kalendrar. Den här vägledningen bygger på [vanliga principer för identitets-och enhets åtkomst](identity-access-policies.md), med ytterligare information som Teams-specifika. Eftersom team integreras med våra andra produkter kan du även läsa [Policy rekommendationer för att skydda SharePoint-webbplatser och filer](sharepoint-file-access-policies.md) och [Policy rekommendationer för att skydda e-post](secure-email-recommended-policies.md).

Dessa rekommendationer är baserade på tre olika nivåer av säkerhet och skydd för team som kan användas baserat på hur dina behov fungerar: bas linje, känslig och högreglerad. Du kan läsa mer om de här säkerhets nivåerna och rekommenderade principer som refereras av av dessa rekommendationer i [konfigurationerna för identitets-och enhets åtkomst](microsoft-365-policies-configurations.md).

Ytterligare rekommendationer som är specifika för distribution av team ingår i den här artikeln för specifika autentiseringskrav, inklusive för användare utanför organisationen. Du måste följa den här vägledningen för att få en fullständig säkerhets upplevelse.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Komma igång med Teams innan andra beroende tjänster

Du behöver inte aktivera beroende tjänster för att komma igång med Microsoft Teams. Då kommer alla att "fungera". Du måste emellertid vara beredd på att hantera följande:

- Microsoft 365-grupper
- SharePoint-gruppwebbplatser
- OneDrive för företag
- Post lådor
- Ström-och planerings planer (om de här tjänsterna är aktiverade)

## <a name="updating-common-policies-to-include-teams"></a>Uppdatera gemensamma principer för att inkludera team

I följande diagram visas en uppsättning rekommenderade principer för att skydda chatt, grupper och innehåll i team. Penn ikonen anger vilka principer som måste återbesökas för att vara säker på att team och beroende tjänster ingår i tilldelningen av Cloud-appar.

![Ett diagram som visar hur du använder Microsoft Teams på olika enheter.](../media/identity-access-ruleset-teams.png)

Det här är de tjänster som är underordnade för tilldelning av moln program för grupper:

- Microsoft Teams
- SharePoint Online och OneDrive för företag
- Exchange Online
- Skype för företag – Online
- Microsoft Stream (Mötes inspelningar)
- Microsoft Planner (Planner-uppgifter och planera data)

I den här tabellen visas de principer som måste återanvändas och länkar till varje princip i [gemensamma principer för identitets-och enhets åtkomst](identity-access-policies.md), som har den bredare regel uppsättning för alla Office-program.

|Skydds nivå|Principerna|Ytterligare information om Team implementering|
|:---------------|:-------|:----------------|
|**Grundläggande**|[Kräv MFA när en inloggnings risk är *mellan* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Se till att team och beroende tjänster ingår i listan med program. Teams har gäst åtkomst och regler för extern åtkomst att överväga och mer information om dessa längre fram i den här artikeln.|
|        |[Blockera klienter som inte har stöd för modern autentisering](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Inkludera team och beroende tjänster i tilldelningen av Cloud-appar.|
|        |[Användare med hög risk måste byta lösenord](identity-access-policies.md#high-risk-users-must-change-password)|Tvingar team användare att ändra sitt lösen ord när de loggar in om en högrisk aktivitet identifieras för sitt konto. Se till att team och beroende tjänster ingår i listan med program.|
|        |[Tillämpa program data skydds policy](identity-access-policies.md#apply-app-data-protection-policies)|Se till att team och beroende tjänster ingår i listan med program. Uppdatera policyn för var och en av plattformarna (iOS, Android, Windows).|
|        |[Kräv godkända appar och program skydd](identity-access-policies.md#require-approved-apps-and-app-protection)|Inkludera team och tjänster i den här policyn.|
|        |[Definiera principer för efterlevnadsprinciper](identity-access-policies.md#define-device-compliance-policies)|Inkludera team och tjänster i den här policyn.|
|        |[Kräv kompatibla PC-datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Inkludera team och tjänster i den här policyn.|
|**Känslig**|[Kräv MFA när en inloggnings risk är *låg*, *medium* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams har gäst åtkomst och regler för extern åtkomst att överväga och mer information om dessa längre fram i den här artikeln. Inkludera team och tjänster i den här policyn.|
|         |[Kräv kompatibla datorer *och* mobila enheter](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Inkludera team och tjänster i den här policyn.|
|**Strikt reglerad**|[Kräv *alltid* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Oavsett användarens identitet används MFA av din organisation. Inkludera team och tjänster i den här policyn.
| | |

## <a name="teams-dependent-services-architecture"></a>Arkitektur för Teams beroende tjänster

Följande diagram visar att tjänsterna är bevarade för referens. Mer information och ytterligare illustrationer finns i [Microsoft Teams och relaterade produktivitets tjänster i microsoft 365 för IT-arkitekter](../solutions/productivity-illustrations.md).

![Diagram som visar team beroenden i SharePoint Online, OneDrive för företag och Exchange.](../media/identity-access-logical-architecture-teams.png)

## <a name="enabling-guest-and-external-access-for-teams"></a>Aktivera gäst och extern åtkomst till Teams

I Azure AD är gäst och externa användare desamma. Användar typen för båda dessa är gäster. Gäst användare är B2B-användare. Microsoft Teams skiljer mellan gäst användare och externa användare i appen. Det är viktigt att förstå hur var och en av dessa behandlas i Teams, men båda användar typerna är B2B-användare i Azure AD och rekommenderade principer för B2B-användare gäller båda. Rekommenderade principer för att tillåta gäst åtkomst finns i [principer för att tillåta gäst-och extern B2B-åtkomst](identity-access-policies-guest-access.md).

### <a name="guest-access-in-teams"></a>Gäst åtkomst i Teams

Utöver policyerna för användare som är interna för ditt företag eller din organisation kan administratörer aktivera gäst åtkomst för att tillåta att användare som är medlemmar i ditt företag eller din organisation får åtkomst till Teams-resurser och interagerar med interna personer, till exempel gruppkonversationer, chatt och möten. Du kan läsa mer om gäst åtkomst på följande länk: [gäst åtkomst för Teams](https://docs.microsoft.com/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Extern åtkomst i Teams

Extern åtkomst förväxlas ibland med gäst åtkomst, så det är viktigt att vara tydligt att dessa två icke-interna åtkomst funktioner faktiskt skiljer sig åt. När gäst åtkomst sker per användare (du lägger till en användare åt gången) när en administratör aktiverar extern åtkomst kan du lägga till alla användare av en extern domän samtidigt till Teams. Men de externa användarna har mindre åtkomst och funktionalitet än en person som har lagts till via gäst åtkomst. Externa Access-användare kan chatta med dina interna användare via Teams.

För mer information om extern åtkomst och hur du implementerar den om du behöver det, gå till [Hantera extern åtkomst i Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access)

## <a name="teams-policies"></a>Team policy

Utanför de gemensamma principer som anges ovan finns det teambaserade principer som kan och ska konfigureras för att hantera olika team funktioner.

### <a name="teams-and-channels-policies"></a>Principer för team och kanaler

Team och kanaler är två vanliga element i Microsoft Teams och det finns principer du kan ange för att styra vad användare kan och inte kan göra när du använder team och kanaler. Du kan skapa ett globalt team, om din organisation har 5000 användare eller mindre, men det är troligt att det är bra att ha mindre team och kanaler för speciella ändamål, online med dina organisations behov.

Att ändra standard princip eller skapa anpassade principer rekommenderas och du kan läsa mer om hur du hanterar dina principer på den här länken: [Hantera Teams-principer i Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).

### <a name="messaging-policies"></a>Meddelande principer

Meddelanden och chattar kan även hanteras via den globala standard principen eller via anpassade principer, och detta kan hjälpa användarna att kommunicera med varandra på ett sätt som passar din organisation. Den här informationen kan granskas när du [hanterar meddelande principer i Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).

### <a name="meeting-policies"></a>Mötes principer

Du behöver inte längre diskutera och implementera principer kring Teams-möten. Möten är en viktig komponent i Teams, så att folk kan möta och presentera för många användare samtidigt, samt dela innehåll som är relevanta för mötet. Det är viktigt att ange rätt principer för din organisation.

Mer information finns [i hantera Mötes principer i Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) .

### <a name="app-permission-policies"></a>Program behörighets principer

I Teams kan du också använda appar på olika platser, till exempel kanaler eller personliga chattar. Ha principer kring vilka appar som kan läggas till och användas, och var de är nödvändiga för att underhålla innehålls rika miljöer som också är säkra.

Mer information om behörighets principer för appar finns [i Hantera principer för programbehörigheter i Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).

## <a name="next-steps"></a>Nästa steg

[Lär dig hur du aktiverar villkorsstyrd åtkomst för Exchange Online](secure-email-recommended-policies.md)


