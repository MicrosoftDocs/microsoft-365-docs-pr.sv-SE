---
title: Rekommenderade Teams – Microsoft 365 för | Microsoft Docs
description: Här beskrivs principer för Microsofts rekommendationer om hur du skyddar Teams och filåtkomst.
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.openlocfilehash: 52e6709d18bd5ecbc91755a6c0e7be336d346f0c
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599609"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Principrekommendationer för att skydda Teams, chattar, grupper och filer

I den här artikeln beskrivs hur du implementerar rekommenderade principer för identitet och enhetsåtkomst för att skydda Microsoft Teams, grupper och innehåll som filer och kalendrar. Den här vägledningen bygger på [de gemensamma identitets-](identity-access-policies.md)och enhetsåtkomstprinciperna, med ytterligare information som Teams specifika. Eftersom Teams är integrerat med våra andra produkter kan du även se [principrekommendationer](sharepoint-file-access-policies.md) för att skydda SharePoint-webbplatser och -filer och principrekommendationer för [att skydda e-post.](secure-email-recommended-policies.md)

Dessa rekommendationer baseras på tre olika nivåer av säkerhet och skydd för Teams som kan tillämpas utifrån dina behovs granularitet: baslinje, känslig och mycket reglerad. Du kan läsa mer om dessa säkerhetsnivåer och de rekommenderade principerna som refereras av dessa rekommendationer i konfigurationerna [för identitets- och enhetsåtkomst.](microsoft-365-policies-configurations.md)

Fler rekommendationer för specifika Teams-distribution finns i den här artikeln för att täcka specifika autentiseringsförhållanden, bland annat för användare utanför organisationen. Du måste följa den här vägledningen för en fullständig säkerhetsupplevelse.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Komma igång med Teams innan andra beroende tjänster

Du behöver inte aktivera beroende tjänster för att komma igång med Microsoft Teams. De här tjänsterna kommer att "bara fungera". Du måste dock vara redo att hantera följande tjänstrelaterade element:

- Microsoft 365-grupper
- SharePoint-gruppwebbplatser
- OneDrive för företag
- Exchange postlådor
- Strömma videor och Planner-planer (om de här tjänsterna är aktiverade)

## <a name="updating-common-policies-to-include-teams"></a>Uppdatera vanliga principer så att de omfattar Teams

I följande diagram visas vilka principer som ska uppdateras från de gemensamma principerna för identitets- och enhetsåtkomst för att skydda chatt, grupper och innehåll i Teams användare. För varje princip som ska uppdateras måste Teams och beroende tjänster inkluderas i tilldelningen av molnappar.

[![Sammanfattning av principuppdateringar för att skydda åtkomsten Teams och dess beroende tjänster](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

De här tjänsterna är de beroende tjänster som ska ingå i tilldelningen av molnappar för Teams:

- Microsoft Teams
- SharePoint och OneDrive för företag
- Exchange Online
- Skype för företag – Online
- Microsoft Stream (mötesinspelningar)
- Microsoft Planner (uppgifter och plandata i Planner)

I den här tabellen visas de principer som behöver [](identity-access-policies.md)granskas igen och länkar till varje princip i de gemensamma principerna för identitets- och enhetsåtkomst, som har en större uppsättning principer för alla Office program.

|Skyddsnivå|Principer|Mer information för Teams implementering|
|---|---|---|
|**Grundläggande**|[Kräv MFA när inloggningsrisken är *medium* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Se till Teams och beroende tjänster ingår i listan med program. Teams har regler för gäståtkomst och extern åtkomst att ta hänsyn till får du mer information om dessa regler längre fram i den här artikeln.|
||[Blockera klienter som inte har stöd för modern autentisering](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Inkludera Teams och beroende tjänster i tilldelningen av molnappar.|
||[Användare med hög risk måste byta lösenord](identity-access-policies.md#high-risk-users-must-change-password)|Tvingar Teams användarna att ändra sitt lösenord vid inloggning om högriskaktivitet identifieras för deras konto. Se till Teams och beroende tjänster ingår i listan med program.|
||[Använda principer för APP-dataskydd](identity-access-policies.md#apply-app-data-protection-policies)|Se till Teams och beroende tjänster ingår i listan med program. Uppdatera principen för varje plattform (iOS, Android, Windows).|
||[Definiera principer för enhetsefterlevnad](identity-access-policies.md#define-device-compliance-policies)|Ta Teams och beroende tjänster i den här principen.|
||[Kräv kompatibla PC-datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Ta Teams och beroende tjänster i den här principen.|
|**Känslig**|[Kräv MFA när inloggningsrisken är *låg,* *medelstor* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams har regler för gäståtkomst och extern åtkomst att ta hänsyn till får du mer information om dessa regler längre fram i den här artikeln. Ta Teams och beroende tjänster i den här principen.|
||[Kräv kompatibla datorer *och* mobila enheter](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Ta Teams och beroende tjänster i den här principen.|
|**Strikt reglerad**|[*Kräv* alltid MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Oavsett användaridentitet används MFA av din organisation. Ta Teams och beroende tjänster i den här principen. |
|

## <a name="teams-dependent-services-architecture"></a>Teams arkitektur för beroende tjänster

Som referens illustrerar följande diagram de tjänster Teams använder. Mer information och illustrationer finns i Microsoft Teams [och relaterade produktivitetstjänster i Microsoft 365 för IT-arkitekter.](../../solutions/productivity-illustrations.md)

[![Diagram som Teams beroenden av SharePoint, OneDrive för företag och Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[Visa en större version av den här bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Gäståtkomst och extern åtkomst för Teams

Microsoft Teams definierar följande åtkomsttyper:

- **Gäståtkomst** använder ett Azure AD B2B-konto för en gäst eller extern användare som kan läggas till som medlem i ett team och har all behörighet till teamets kommunikation och resurser.

- **Extern åtkomst** är för en extern användare som inte har ett Azure AD B2B-konto. Extern åtkomst kan vara inbjudningar och deltagande i samtal, chattar och möten, men omfattar inte teammedlemskap och åtkomst till teamets resurser.

Villkorsstyrda åtkomstprinciper gäller endast för gäståtkomst Teams det finns ett motsvarande Azure AD B2B-konto.

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

Rekommenderade principer för att tillåta åtkomst för gästanvändare och externa användare med ett Azure AD B2B-konto finns i Principer för att tillåta åtkomst till gäst- och [externa B2B-konton.](identity-access-policies-guest-access.md)

### <a name="guest-access-in-teams"></a>Gäståtkomst i Teams

Förutom principerna för användare som är interna i företaget eller organisationen kan administratörer göra det möjligt för gäståtkomst att tillåta, per användare, personer som finns utanför företaget eller organisationen att få åtkomst till Teams-resurser och interagera med interna personer för saker som gruppkonversationer, chatt och möten.

Mer information om gäståtkomst och hur du implementerar den finns i Teams [gäståtkomst.](/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Extern åtkomst i Teams

Extern åtkomst förväxlas ibland med gäståtkomst, så det är viktigt att vara tydlig med att dessa två icke-interna åtkomstmekanismer är olika typer av åtkomst.

Extern åtkomst är ett sätt för Teams användare från en hel extern domän att hitta, ringa, chatta och konfigurera möten med användarna i Teams. Teams-administratörer konfigurerar extern åtkomst på organisationsnivå. Mer information finns i [Hantera extern åtkomst i Microsoft Teams](/microsoftteams/manage-external-access).

Externa åtkomstanvändare har mindre åtkomst och funktionalitet än en person som har lagts till via gäståtkomst. Externa användare kan till exempel chatta med interna användare med Teams men inte komma åt teamkanaler, filer eller andra resurser.

Extern åtkomst använder inte Azure AD B2B-användarkonton och använder därför inte villkorsstyrda åtkomstprinciper.

## <a name="teams-policies"></a>Teams principer

Förutom de vanliga principerna som anges ovan finns det Teams specifika principer som kan och bör konfigureras för att hantera Teams funktioner.

### <a name="teams-and-channels-policies"></a>Teams kanaler och kanaler

Teams och kanaler är två vanliga element i Microsoft Teams, och det finns principer som du kan använda för att styra vad användarna kan och inte kan göra när de använder team och kanaler. Du kan skapa ett globalt team, men om organisationen har 5 000 användare eller mindre är det troligt att det är bra att ha mindre team och kanaler för särskilda ändamål, i linje med organisationens behov.

Vi rekommenderar att du ändrar standardprincipen eller skapar anpassade principer och du kan läsa mer om hantering av principer på den här länken: Hantera [teamprinciper i Microsoft Teams.](/microsoftteams/teams-policies)

### <a name="messaging-policies"></a>Meddelandeprinciper

Meddelanden, eller chatt, kan också hanteras genom den globala standardprincipen eller med anpassade principer, och det kan hjälpa användarna att kommunicera med varandra på ett sätt som passar för din organisation. Den här informationen finns under Hantera [principer för meddelanden i Teams](/microsoftteams/messaging-policies-in-teams).

### <a name="meeting-policies"></a>Mötes principer

Ingen diskussion om Teams skulle vara fullständig utan planering och implementering av principer kring Teams möten. Möten är en viktig del av Teams, så att personer formellt kan träffas och presentera för många användare samtidigt, och för att dela innehåll som är relevant för mötet. Det är viktigt att ange rätt principer för organisationen kring möten.

Mer information finns i [Hantera mötes principer i Teams](/microsoftteams/meeting-policies-in-teams).

### <a name="app-permission-policies"></a>Appbehörighetsprinciper

Teams kan du även använda appar på olika platser, till exempel kanaler eller personliga chattar. Det är viktigt att ha principer för vilka appar som kan läggas till och användas och var, för att upprätthålla en innehållsrik miljö som också är säker.

Mer information om programbehörighetsprinciper finns i Hantera principer [för programbehörigheter i Microsoft Teams.](/microsoftteams/teams-app-permission-policies)

## <a name="next-steps"></a>Nästa steg

![Steg 4: Principer Microsoft 365 molnappar](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurera principer för villkorsstyrd åtkomst för:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)