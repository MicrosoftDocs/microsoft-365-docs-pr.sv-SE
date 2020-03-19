---
title: Principer för rekommenderade team – Microsoft 365 Enterprise | Microsoft Dokument
description: I artikeln beskrivs policyerna för Microsoft-rekommendationer om hur du skyddar Teams kommunikation och filåtkomst.
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
ms.openlocfilehash: 4c72e340092bbd366277114a56aae7574d43dab5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810759"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Principrekommendationer för att skydda teams-chattar, grupper och filer

I den här artikeln beskrivs hur du implementerar de rekommenderade identitets- och enhetsåtkomstprinciperna för att skydda teams-chattar, grupper och innehåll som filer och kalendrar. Den här vägledningen bygger på principerna [för gemensam identitet och enhetsåtkomst](identity-access-policies.md)med ytterligare information som är Teams-specifik. Eftersom teams integreras med våra andra produkter kan du också se [Principrekommendationer för att skydda SharePoint-webbplatser och filer](sharepoint-file-access-policies.md) och [principrekommendationer för att skydda e-post](secure-email-recommended-policies.md).

Dessa rekommendationer baseras på tre olika nivåer av säkerhet och skydd för team som kan tillämpas baserat på granulariteten hos dina behov: baslinje, känslig och mycket reglerad. Du kan läsa mer om dessa säkerhetsnivåer och de rekommenderade principer som refereras av dessa rekommendationer i [identitets- och enhetsåtkomstkonfigurationerna](microsoft-365-policies-configurations.md).

Ytterligare rekommendationer som är specifika för teams-distributionen ingår i den här artikeln för att täcka specifika autentiseringsomständigheter, även för användare utanför organisationen. Du måste följa den här vägledningen för en fullständig säkerhetsupplevelse.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Komma igång med Teams innan andra beroende tjänster

Du behöver inte aktivera beroende tjänster för att komma igång med Microsoft Teams. Dessa kommer alla "bara arbete." Du måste dock vara beredd att hantera följande:

- Office 365-grupper
- SharePoint-gruppwebbplatser
- OneDrive för företag
- Postlådor
- Strömma videor och planerare (om dessa tjänster är aktiverade)

## <a name="updating-common-policies-to-include-teams"></a>Uppdatera gemensamma principer för att inkludera team

Följande diagram illustrerar uppsättningen rekommenderade principer för att skydda chatt, grupper och innehåll i Teams. Pennikonen anger vilka principer som behöver ses över för att vara säker på att teams och beroende tjänster ingår i tilldelningen av molnappar.

![Ett diagram som visar hur du använder Microsoft Teams på olika enheter.](../media/identity-access-ruleset-teams.png)

Dessa är de beroende tjänster som ska ingå i tilldelningen av molnappar för teams:

- Microsoft Teams
- SharePoint Online och OneDrive för företag
- Exchange Online
- Skype för företag - Online
- Microsoft Stream (mötesinspelningar)
- Microsoft Planner (Planner-uppgifter och plandata)

I den här tabellen visas de principer som behöver ses över och länkar till varje princip i [principer för gemensam identitet och enhetsåtkomst](identity-access-policies.md), som har den bredare regeluppsättningen för alla Office-program.

|Skyddsnivå|Politik|Ytterligare information för teams implementation|
|:---------------|:-------|:----------------|
|**Originalplan**|[Kräv MFA när inloggningsrisken är *medelhög* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Se till att teams och beroende tjänster ingår i listan över appar. Team har regler för gäståtkomst och extern åtkomst att tänka på också, du får också veta mer om dessa senare i den här artikeln.|
|        |[Blockera klienter som inte stöder modern autentisering](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Inkludera teams och beroende tjänster i tilldelningen av molnappar.|
|        |[Högriskanvändare måste byta lösenord](identity-access-policies.md#high-risk-users-must-change-password)|Tvingar teams-användare att ändra sitt lösenord när de loggar in om högriskaktivitet upptäcks för sitt konto. Se till att teams och beroende tjänster ingår i listan över appar.|
|        |[Definiera principer för appskydd](identity-access-policies.md#define-app-protection-policies)|Se till att teams och beroende tjänster ingår i listan över appar. Uppdatera principen för varje plattform (iOS, Android, Windows).|
|        |[Kräv godkända appar](identity-access-policies.md#require-approved-apps)|Inkludera teams och beroende tjänster i den här principen.|
|        |[Definiera principer för enhetsefterlevnad](identity-access-policies.md#define-device-compliance-policies)|Inkludera teams och beroende tjänster i den här principen.|
|        |[Kräv kompatibla datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Inkludera teams och beroende tjänster i den här principen.|
|**Känsliga**|[Kräv MFA när inloggningsrisken är *låg,* *medelhög* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Team har regler för gäståtkomst och extern åtkomst att tänka på också, du får också veta mer om dessa senare i den här artikeln. Inkludera teams och beroende tjänster i den här principen.|
|         |[Kräv kompatibla datorer *och* mobila enheter](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Inkludera teams och beroende tjänster i den här principen.|
|**Mycket reglerad**|[*Kräver alltid* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Oavsett användaridentitet används MFA av din organisation. Inkludera teams och beroende tjänster i den här principen.
| | |

## <a name="teams-dependent-services-architecture"></a>Arkitektur för teamberoende tjänster

Som referens illustrerar följande diagram de tjänster som teams förlitar sig på. Mer information och ytterligare illustrationer finns [i Microsoft Teams och relaterade produktivitetstjänster i Microsoft 365 för IT-arkitekter](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects).

![Diagram som visar teams-beroenden på SharePoint Online, OneDrive för företag och Exchange.](../media/identity-access-logical-architecture-teams.png)

## <a name="enabling-guest-and-external-access-for-teams"></a>Aktivera gäst och extern åtkomst för teams

I Azure AD är gäst och externa användare desamma. Användartypen för båda dessa är Gäst. Gästanvändare är B2B-användare. Microsoft Teams skiljer mellan gästanvändare och externa användare i appen. Det är viktigt att förstå hur var och en av dessa behandlas i Teams, men båda typerna av användare är B2B-användare i Azure AD och de rekommenderade principerna för B2B-användare gäller för båda. Rekommenderade principer för att tillåta gäståtkomst finns i [Principer för att tillåta gäst och extern B2B-åtkomst](identity-access-policies-guest-access.md).

### <a name="guest-access-in-teams"></a>Gäståtkomst i team

Utöver policyerna för användare som är interna för ditt företag eller din organisation kan administratörer göra det möjligt för gäståtkomst att på användarbasis tillåta personer som är externa till ditt företag eller din organisation för att komma åt Teams resurser och interagera med interna personer för saker som gruppkonversationer, chatt och möten. Du kan läsa mer om Gäståtkomst på följande länk: [Teams gäståtkomst](https://docs.microsoft.com/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Extern åtkomst i team

Extern åtkomst förväxlas ibland med gäståtkomst, så det är viktigt att vara tydlig med att dessa två icke-interna åtkomstmekanismer faktiskt är helt annorlunda. Medan gäståtkomst sker per användare (du lägger till en användare i taget), när en administratör aktiverar extern åtkomst kan du lägga till alla användare av en extern domän samtidigt i Teams. Men dessa externa användare har mindre åtkomst och funktionalitet än en person som har lagts till via gäståtkomst skulle ha. Användare av extern åtkomst kan chatta med dina interna användare via Teams.

Om du vill läsa mer om extern åtkomst och hur du implementerar den om du behöver läser du [Hantera extern åtkomst i Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access)

## <a name="teams-policies"></a>Principer för team

Utanför de gemensamma principerna ovan finns det teamsspecifika principer som kan och bör konfigureras för att hantera olika teams-funktioner.

### <a name="teams-and-channels-policies"></a>Policyer för team och kanaler

Team och kanaler är två vanliga element i Microsoft Teams, och det finns principer som du kan införa för att styra vad användare kan och inte kan göra när de använder team och kanaler. Du kan skapa ett globalt team, men om din organisation har 5000 användare eller mindre, kommer du sannolikt att tycka att det är bra att ha mindre team och kanaler för specifika ändamål, i linje med dina organisatoriska behov.

Det är bra att ändra standardprincipen eller skapa anpassade principer och du kan läsa mer om hur du hanterar dina policyer på den här länken: [Hantera teamprinciper i Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).

### <a name="messaging-policies"></a>Meddelandeprinciper

Meddelanden, eller chatt, kan också hanteras via standardpolicyn för global policy eller genom anpassade principer, och detta kan hjälpa användarna att kommunicera med varandra på ett sätt som är lämpligt för din organisation. Den här informationen kan granskas på [Hantera meddelandeprinciper i Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).

### <a name="meeting-policies"></a>Mötesprinciper

Ingen diskussion om Teams skulle vara fullständig utan planering och genomförande av policyer kring teams möten. Möten är en viktig del av Teams, så att människor formellt kan träffas och presentera för många användare på en gång, samt dela innehåll som är relevant för mötet. Det är viktigt att ange rätt principer för din organisation kring möten.

Läs [Hantera mötespolicyer i Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) för mer information.

### <a name="app-permission-policies"></a>Principer för appbehörighet

Med team kan du också använda appar på olika platser, till exempel kanaler eller personliga chattar. Att ha principer kring vilka appar som kan läggas till och användas, och var, är viktigt för att upprätthålla en innehållsrik miljö som också är säker.

Mer information om principer för appbehörighet finns i [Hantera principer för appbehörighet i Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).

## <a name="next-steps"></a>Nästa steg

[Läs om hur du aktiverar villkorlig åtkomst för Exchange Online](secure-email-recommended-policies.md)


