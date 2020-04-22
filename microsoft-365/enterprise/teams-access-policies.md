---
title: Principer för rekommenderade team – Microsoft 365 Enterprise | Microsoft-dokument
description: Beskriver policyerna för Microsofts rekommendationer om hur du skyddar Teams kommunikation och filåtkomst.
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
ms.openlocfilehash: f1a4a4ea69efc3c68bdc8ed66aa18833a28feb94
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636729"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Principrekommendationer för att skydda Teams-chattar, grupper och filer

I den här artikeln beskrivs hur du implementerar de rekommenderade principerna för identitet och enhetsåtkomst för att skydda Teams-chattar, grupper och innehåll som filer och kalendrar. Den här vägledningen bygger på principerna [för gemensam identitet och enhetsåtkomst](identity-access-policies.md), med ytterligare information som är Teams-specifik. Eftersom Teams integreras med våra andra produkter kan du även se [Policyrekommendationer för att skydda SharePoint-webbplatser och -filer](sharepoint-file-access-policies.md) och [policyrekommendationer för att skydda e-post.](secure-email-recommended-policies.md)

Dessa rekommendationer baseras på tre olika nivåer av säkerhet och skydd för teams som kan tillämpas baserat på dina behovs granularitet: baslinje, känslig och starkt reglerad. Du kan läsa mer om dessa säkerhetsnivåer och de rekommenderade principer som refereras av dessa rekommendationer i [konfigurationerna för identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md).

Ytterligare rekommendationer som är specifika för Teams-distributionen ingår i den här artikeln för att täcka specifika autentiseringsförhållanden, även för användare utanför organisationen. Du måste följa den här vägledningen för en fullständig säkerhetsupplevelse.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Komma igång med Teams före andra beroende tjänster

Du behöver inte aktivera beroende tjänster för att komma igång med Microsoft Teams. Dessa kommer alla "bara arbete." Du måste dock vara beredd att hantera följande:

- Microsoft 365-grupper
- SharePoint-gruppwebbplatser
- OneDrive för företag
- Postlådor
- Strömma videor och planerare (om dessa tjänster är aktiverade)

## <a name="updating-common-policies-to-include-teams"></a>Uppdatera gemensamma policyer så att de inkluderar teams

Följande diagram illustrerar uppsättningen rekommenderade principer för att skydda chatt, grupper och innehåll i Teams. Pennikonen anger vilka principer som måste ses över för att vara säker på att Teams och beroende tjänster ingår i tilldelningen av molnappar.

![Ett diagram som visar hur du använder Microsoft Teams på olika enheter.](../media/identity-access-ruleset-teams.png)

Det här är de beroende tjänsterna som ska inkluderas i tilldelningen av molnappar för Teams:

- Microsoft Teams
- SharePoint Online och OneDrive för företag
- Exchange Online
- Skype för företag – Online
- Microsoft Stream (mötesinspelningar)
- Microsoft Planner (Planeraruppgifter och planera data)

I den här tabellen visas de principer som måste ses över och länkar till varje princip i [principer för gemensam identitet och enhetsåtkomst](identity-access-policies.md), som har den bredare regeluppsättningen för alla Office-program.

|Skyddsnivå|Politik|Ytterligare information för Teams implementation|
|:---------------|:-------|:----------------|
|**Grundläggande**|[Kräv MFA när inloggningsrisken är *medelhög* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Se till att Teams och beroende tjänster ingår i listan över appar. Team har regler för gäståtkomst och extern åtkomst att ta hänsyn till också, du lär dig mer om dessa senare i den här artikeln.|
|        |[Blockera klienter som inte har stöd för modern autentisering](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Inkludera Teams och beroende tjänster i tilldelningen av molnappar.|
|        |[Högriskanvändare måste ändra lösenord](identity-access-policies.md#high-risk-users-must-change-password)|Tvingar Teams-användare att ändra sitt lösenord när de loggar in om högriskaktivitet upptäcks för deras konto. Se till att Teams och beroende tjänster ingår i listan över appar.|
|        |[Tillämpa APP-dataskyddsprinciper](identity-access-policies.md#apply-app-data-protection-policies)|Se till att Teams och beroende tjänster ingår i listan över appar. Uppdatera principen för varje plattform (iOS, Android, Windows).|
|        |[Kräv godkända appar och APP-skydd](identity-access-policies.md#require-approved-apps-and-app-protection)|Inkludera teams och beroende tjänster i den här principen.|
|        |[Definiera principer för enhetsefterlevnad](identity-access-policies.md#define-device-compliance-policies)|Inkludera teams och beroende tjänster i den här principen.|
|        |[Kräv kompatibla PC-datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Inkludera teams och beroende tjänster i den här principen.|
|**Känslig**|[Kräv MFA när inloggningsrisken är *låg,* *medelhög* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Team har regler för gäståtkomst och extern åtkomst att ta hänsyn till också, du lär dig mer om dessa senare i den här artikeln. Inkludera teams och beroende tjänster i den här principen.|
|         |[Kräv kompatibla datorer *och* mobila enheter](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Inkludera teams och beroende tjänster i den här principen.|
|**Strikt reglerad**|[*Kräver alltid* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Oavsett användaridentitet kommer MFA att användas av din organisation. Inkludera teams och beroende tjänster i den här principen.
| | |

## <a name="teams-dependent-services-architecture"></a>Team beroende tjänster arkitektur

Som referens illustrerar följande diagram de tjänster som Teams förlitar sig på. Mer information och ytterligare illustrationer finns [i Microsoft Teams och relaterade produktivitetstjänster i Microsoft 365 för IT-arkitekter](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects).

![Diagram som visar Teams beroenden på SharePoint Online, OneDrive för företag och Exchange.](../media/identity-access-logical-architecture-teams.png)

## <a name="enabling-guest-and-external-access-for-teams"></a>Aktivera gäståtkomst och extern åtkomst för teams

I Azure AD är gäst- och externa användare desamma. Användartypen för båda dessa är Gäst. Gästanvändare är B2B-användare. Microsoft Teams skiljer mellan gästanvändare och externa användare i appen. Det är viktigt att förstå hur var och en av dessa behandlas i Teams, men båda typerna av användare är B2B-användare i Azure AD och de rekommenderade principerna för B2B-användare gäller för båda. Rekommenderade principer för att ge gäståtkomst finns i [Principer för att tillåta gäståtkomst och extern B2B-åtkomst](identity-access-policies-guest-access.md).

### <a name="guest-access-in-teams"></a>Gäståtkomst i teams

Utöver principerna för användare som är interna i ditt företag eller din organisation kan administratörer tillåta gäståtkomst att, användare för användare, tillåta personer som är utanför ditt företag eller din organisation att komma åt Teams-resurser och interagera med interna personer för saker som gruppkonversationer, chatt och möten. Du kan läsa mer om Gäståtkomst på följande länk: [Teams gäståtkomst](https://docs.microsoft.com/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Extern åtkomst i team

Extern åtkomst förväxlas ibland med gäståtkomst, så det är viktigt att vara tydlig med att dessa två icke-interna åtkomstmekanismer faktiskt är helt olika. Gäståtkomst sker per användare (du lägger till en användare i taget), men när en administratör aktiverar extern åtkomst kan du lägga till alla användare av en extern domän samtidigt i Teams. Men de externa användarna har mindre tillgång och funktionalitet än en person som har lagts till via gäståtkomst skulle ha. Användare av extern åtkomst kan chatta med dina interna användare via Teams.

Mer information om extern åtkomst och hur du implementerar den om du behöver kan du läsa [Hantera extern åtkomst i Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access)

## <a name="teams-policies"></a>Policyer för team

Utanför de gemensamma principerna ovan finns teams-specifika principer som kan och bör konfigureras för att hantera olika Teams-funktioner.

### <a name="teams-and-channels-policies"></a>Policyer för team och kanaler

Team och kanaler är två vanliga element i Microsoft Teams, och det finns policyer som du kan införa för att styra vad användare kan och inte kan göra när du använder team och kanaler. Du kan skapa ett globalt team, men om din organisation har 5000 användare eller mindre, är det troligt att det är bra att ha mindre team och kanaler för specifika ändamål, i linje med dina organisationsbehov.

Du kan ändra standardprincipen eller skapa anpassade principer och du kan läsa mer om hur du hanterar dina principer på den här länken: [Hantera teamprinciper i Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).

### <a name="messaging-policies"></a>Principer för meddelanden

Meddelanden eller chatt kan också hanteras via standardprincipen för globala principer, eller via anpassade principer, och det kan hjälpa användarna att kommunicera med varandra på ett sätt som är lämpligt för din organisation. Den här informationen kan granskas på [Hantera meddelandepolicyer i Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).

### <a name="meeting-policies"></a>Mötespolicyer

Ingen diskussion om Teams skulle vara fullständig utan planering och genomförande av policyer kring Teams-möten. Möten är en viktig del av Teams, så att människor kan träffas formellt och presentera för många användare samtidigt, samt dela innehåll som är relevant för mötet. Det är viktigt att ställa in rätt principer för organisationen kring möten.

Läs [Hantera mötespolicyer i Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) för mer information.

### <a name="app-permission-policies"></a>Principer för appbehörighet

Med Team kan du också använda appar på olika platser, till exempel kanaler eller personliga chattar. Att ha principer kring vilka appar som kan läggas till och användas, och var, är viktigt för att upprätthålla en innehållsrik miljö som också är säker.

Mer information om principer för appbehörighet finns [i Hantera appbehörighetsprinciper i Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).

## <a name="next-steps"></a>Nästa steg

[Läs om hur du aktiverar villkorlig åtkomst för Exchange Online](secure-email-recommended-policies.md)


