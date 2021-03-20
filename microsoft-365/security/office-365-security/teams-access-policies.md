---
title: Rekommenderade principer för Teams – Microsoft 365 för | Microsoft Docs
description: Här beskrivs principer för Microsofts rekommendationer om hur du skyddar Teams kommunikation och filåtkomst.
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 51dec80c541cd77a1d4813505d82429487e8381c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916424"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Principrekommendationer för att skydda chattar, grupper och filer i Teams

I den här artikeln beskrivs hur du implementerar rekommenderade principer för identitet och enhetsåtkomst för att skydda chattar, grupper och innehåll i Microsoft Teams, till exempel filer och kalendrar. Den här vägledningen bygger på [de gemensamma principerna för identitet och enhetsåtkomst,](identity-access-policies.md)med ytterligare information som är Teams-specifik. Eftersom Teams är integrerat med våra andra produkter, se även policyrekommendationer för att skydda [SharePoint-webbplatser](sharepoint-file-access-policies.md) och -filer och [policyrekommendationer för att skydda e-post.](secure-email-recommended-policies.md)

Dessa rekommendationer baseras på tre olika nivåer av säkerhet och skydd för Teams som kan tillämpas utifrån detaljnivån för dina behov: baslinje, känslig och mycket reglerad. Du kan läsa mer om dessa säkerhetsnivåer och de rekommenderade principerna som refereras av dessa rekommendationer i konfigurationerna [för identitets- och enhetsåtkomst.](microsoft-365-policies-configurations.md)

Fler rekommendationer som är specifika för teams-distribution finns i den här artikeln för att täcka specifika autentiseringsförhållanden, även för användare utanför organisationen. Du måste följa den här vägledningen för en fullständig säkerhetsupplevelse.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Komma igång med Teams före andra beroende tjänster

Du behöver inte aktivera beroende tjänster för att komma igång med Microsoft Teams. De här tjänsterna kommer att "bara fungera". Du måste dock vara redo att hantera följande tjänstrelaterade element:

- Microsoft 365-grupper
- SharePoint-gruppwebbplatser
- OneDrive för företag
- Exchange-postlådor
- Strömma videor och Planner-planer (om de här tjänsterna är aktiverade)

## <a name="updating-common-policies-to-include-teams"></a>Uppdatera vanliga policyer så att de omfattar Teams

I följande diagram visas vilka principer som ska uppdateras från de gemensamma principerna för identitets- och enhetsåtkomst för att skydda chatt, grupper och innehåll i Teams. För varje princip som ska uppdateras ser du till att Teams och beroende tjänster inkluderas i tilldelningen av molnappar.

[![Sammanfattning av principuppdateringar för att skydda åtkomsten till Teams och dess beroende tjänster](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

Dessa tjänster är de beroende tjänster som ska ingå i tilldelningen av molnappar för Teams:

- Microsoft Teams
- SharePoint och OneDrive för företag
- Exchange Online
- Skype för företag online
- Microsoft Stream (mötesinspelningar)
- Microsoft Planner (uppgifter och plandata i Planner)

I den här tabellen visas de principer som behöver [](identity-access-policies.md)granskas igen och länkar till varje princip i de gemensamma principerna för identitets- och enhetsåtkomst, som har en större uppsättning principer för alla Office-program.

|Skyddsnivå|Principer|Mer information om implementering av Teams|
|---|---|---|
|**Grundläggande**|[Kräv MFA när inloggningsrisken är *medium* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Se till att Teams och beroende tjänster ingår i listan med appar. Teams har även gäståtkomst- och externa åtkomstregler att ta hänsyn till. Du får lära dig mer om dessa regler längre fram i den här artikeln.|
||[Blockera klienter som inte har stöd för modern autentisering](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Inkludera Teams och beroende tjänster i tilldelningen av molnappar.|
||[Användare med hög risk måste byta lösenord](identity-access-policies.md#high-risk-users-must-change-password)|Tvingar Teams-användare att ändra sitt lösenord vid inloggning om högriskaktivitet identifieras för deras konto. Se till att Teams och beroende tjänster ingår i listan med appar.|
||[Använda principer för APP-dataskydd](identity-access-policies.md#apply-app-data-protection-policies)|Se till att Teams och beroende tjänster ingår i listan med appar. Uppdatera principen för varje plattform (iOS, Android, Windows).|
||[Definiera principer för enhetsefterlevnad](identity-access-policies.md#define-device-compliance-policies)|Inkludera Teams och beroende tjänster i denna policy.|
||[Kräv kompatibla PC-datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Inkludera Teams och beroende tjänster i denna policy.|
|**Känslig**|[Kräv MFA när inloggningsrisken är *låg,* *medelstor* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams har även gäståtkomst- och externa åtkomstregler att ta hänsyn till. Du får lära dig mer om dessa regler längre fram i den här artikeln. Inkludera Teams och beroende tjänster i denna policy.|
||[Kräv kompatibla datorer *och* mobila enheter](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Inkludera Teams och beroende tjänster i denna policy.|
|**Strikt reglerad**|[*Kräv* alltid MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Oavsett användaridentitet används MFA av din organisation. Inkludera Teams och beroende tjänster i denna policy. |
|

## <a name="teams-dependent-services-architecture"></a>Arkitektur för Teams-beroende tjänster

Som referens illustrerar följande diagram de tjänster Som Teams använder sig av. Mer information och illustrationer finns i [Microsoft Teams och relaterade produktivitetstjänster i Microsoft 365 för IT-arkitekter.](../../solutions/productivity-illustrations.md)

[![Diagram som visar Teams-beroenden för SharePoint, OneDrive för företag och Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[Visa en större version av den här bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Gäst och extern åtkomst för Teams

Microsoft Teams definierar följande åtkomsttyper:

- **Gäståtkomst** använder ett Azure AD B2B-konto för en gäst eller extern användare som kan läggas till som medlem i ett team och har all behörighet till teamets kommunikation och resurser.

- **Extern åtkomst** är för en extern användare som inte har ett Azure AD B2B-konto. Extern åtkomst kan vara inbjudningar och deltagande i samtal, chattar och möten, men omfattar inte teammedlemskap och åtkomst till teamets resurser.

Villkorsstyrda åtkomstprinciper gäller endast för gäståtkomst i Teams eftersom det finns ett motsvarande Azure AD B2B-konto.

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

Rekommenderade principer för att tillåta åtkomst för gästanvändare och externa användare med ett Azure AD B2B-konto finns i Principer för att tillåta åtkomst till gäst- och [externa B2B-konton.](identity-access-policies-guest-access.md)

### <a name="guest-access-in-teams"></a>Gäståtkomst i Teams

Förutom principerna för användare som är interna i företaget eller organisationen kan administratörer göra det möjligt för gäståtkomst att tillåta, per användare, personer som inte finns i företaget eller organisationen att komma åt Teams-resurser och interagera med interna personer för saker som gruppkonversationer, chatt och möten.

Mer information om gäståtkomst och hur du implementerar den finns i [Teams gäståtkomst.](/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Extern åtkomst i Teams

Extern åtkomst förväxlas ibland med gäståtkomst, så det är viktigt att vara tydlig med att dessa två icke-interna åtkomstmekanismer är olika typer av åtkomst.

Extern åtkomst är ett sätt för Teams-användare från en hel extern domän att hitta, ringa, chatta och konfigurera möten med dina användare i Teams. Teams-administratörer konfigurerar extern åtkomst på organisationsnivå. Mer information finns i [Hantera extern åtkomst i Microsoft Teams.](/microsoftteams/manage-external-access)

Externa åtkomstanvändare har mindre åtkomst och funktionalitet än en person som har lagts till via gäståtkomst. Till exempel kan externa användare chatta med interna användare med Teams men inte komma åt teamkanaler, filer eller andra resurser.

Extern åtkomst använder inte Azure AD B2B-användarkonton och använder därför inte villkorsstyrda åtkomstprinciper.

## <a name="teams-policies"></a>Principer för Teams

Förutom de vanliga principerna som anges ovan finns det Teams-specifika principer som kan och bör konfigureras för att hantera olika teams-funktioner.

### <a name="teams-and-channels-policies"></a>Principer för team och kanaler

Team och kanaler är två vanliga element i Microsoft Teams, och det finns principer som du kan använda för att styra vad användarna kan och inte kan göra när de använder team och kanaler. Du kan skapa ett globalt team, men om organisationen har 5 000 användare eller mindre är det troligt att det är bra att ha mindre team och kanaler för särskilda ändamål, i linje med organisationens behov.

Vi rekommenderar att du ändrar standardprincipen eller skapar anpassade principer, och du kan läsa mer om hur du hanterar principer på den här länken: Hantera [teampolicyer i Microsoft Teams](/microsoftteams/teams-policies).

### <a name="messaging-policies"></a>Meddelandeprinciper

Meddelanden, eller chatt, kan också hanteras genom den globala standardprincipen eller med anpassade principer, och det kan hjälpa användarna att kommunicera med varandra på ett sätt som passar för din organisation. Den här informationen kan granskas under [Hantera meddelandepolicyer i Teams.](/microsoftteams/messaging-policies-in-teams)

### <a name="meeting-policies"></a>Mötes principer

Ingen diskussion om Teams skulle vara fullständig utan planering och implementering av policyer kring Teams-möten. Möten är en viktig del av Teams, så att personer formellt kan träffas och presentera för många användare samtidigt, och för att dela innehåll som är relevant för mötet. Det är viktigt att ange rätt principer för organisationen kring möten.

Mer information finns i Hantera [mötesprinciper i Teams.](/microsoftteams/meeting-policies-in-teams)

### <a name="app-permission-policies"></a>Appbehörighetsprinciper

Med Teams kan du också använda appar på olika platser, till exempel kanaler eller personliga chattar. Det är viktigt att ha principer för vilka appar som kan läggas till och användas och var, för att upprätthålla en innehållsrik miljö som också är säker.

Mer information om appbehörighetsprinciper finns i Hantera [appbehörighetsprinciper i Microsoft Teams.](/microsoftteams/teams-app-permission-policies)

## <a name="next-steps"></a>Nästa steg

![Steg 4: Principer för Microsoft 365-molnappar](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurera principer för villkorsstyrd åtkomst för:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)