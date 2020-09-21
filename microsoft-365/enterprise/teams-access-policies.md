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
ms.date: 09/18/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 570ef098a3989bf42d641b78e325414350b8e5a5
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132118"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Policy rekommendationer för att skydda Teams, grupper och filer

I den här artikeln beskrivs hur du implementerar de rekommenderade identiteterna och enhets åtkomst principer för att skydda Microsoft Teams-chattar, grupper och innehåll som filer och kalendrar. Den här vägledningen bygger på [vanliga principer för identitets-och enhets åtkomst](identity-access-policies.md), med ytterligare information som Teams-specifika. Eftersom team integreras med våra andra produkter kan du även läsa [Policy rekommendationer för att skydda SharePoint-webbplatser och filer](sharepoint-file-access-policies.md) och [Policy rekommendationer för att skydda e-post](secure-email-recommended-policies.md).

Dessa rekommendationer är baserade på tre olika nivåer av säkerhet och skydd för team som kan användas baserat på hur dina behov fungerar: bas linje, känslig och högreglerad. Du kan läsa mer om de här säkerhets nivåerna och rekommenderade principer som refereras av av dessa rekommendationer i [konfigurationerna för identitets-och enhets åtkomst](microsoft-365-policies-configurations.md).

Ytterligare rekommendationer som är specifika för distribution av team ingår i den här artikeln för specifika autentiseringskrav, inklusive för användare utanför organisationen. Du måste följa den här vägledningen för att få en fullständig säkerhets upplevelse.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Komma igång med Teams innan andra beroende tjänster

Du behöver inte aktivera beroende tjänster för att komma igång med Microsoft Teams. Då kommer alla att "fungera". Du måste emellertid vara beredd på att hantera följande:

- Microsoft 365-grupper
- SharePoint-gruppwebbplatser
- OneDrive för företag
- Exchange-postlådor
- Ström-och planerings planer (om de här tjänsterna är aktiverade)

## <a name="updating-common-policies-to-include-teams"></a>Uppdatera gemensamma principer för att inkludera team

För att skydda chatt, grupper och innehåll i team visar följande diagram vilka principer som ska uppdateras från principer för åtkomst för identitet och enheter. För varje princip som ska uppdateras bör du kontrol lera att team och beroende tjänster ingår i tilldelningen av Cloud-appar.

[![Sammanfattning av princip uppdateringar för att skydda åtkomst till team och dess beroende tjänster](../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

[Visa en större version av bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

Det här är de tjänster som är underordnade för tilldelning av moln program för grupper:

- Microsoft Teams
- SharePoint och OneDrive för företag
- Exchange Online
- Skype för företag online
- Microsoft Stream (Mötes inspelningar)
- Microsoft Planner (Planner-uppgifter och planera data)

I den här tabellen visas de principer som måste återanvändas och länkar till varje princip i den [allmänna principer för identitets-och enhets åtkomst](identity-access-policies.md), som har den bredare princip som är inställd för alla Office-program.

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
|**Strikt reglerad**|[Kräv *alltid* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Oavsett användarens identitet används MFA av din organisation. Inkludera team och tjänster i den här policyn. |
| | |

## <a name="teams-dependent-services-architecture"></a>Arkitektur för Teams beroende tjänster

Följande diagram visar att tjänsterna är bevarade för referens. Mer information och ytterligare illustrationer finns i [Microsoft Teams och relaterade produktivitets tjänster i microsoft 365 för IT-arkitekter](../solutions/productivity-illustrations.md).

[![Diagram som visar team beroenden på SharePoint, OneDrive för företag och Exchange](../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[Visa en större version av bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Gäst och extern åtkomst till Teams

Microsoft Teams definierar följande:

- **Gäst åtkomst** använder ett Azure AD B2B-konto för en gäst eller extern användare som kan läggas till som medlem i ett team och få åtkomst till kommunikationen och resurserna i teamet.

- **Extern åtkomst** är för en extern användare som inte har ett Azure AD B2B-konto. Extern åtkomst kan inkludera inbjudningar och deltagande i samtal, chattar och möten, men inte grupp medlemskap och åtkomst till teamens resurser.

Principer för villkorsstyrd åtkomst gäller endast för gäst åtkomst i Teams eftersom det finns ett motsvarande Azure AD B2B-konto.

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both. 

--> 

Information om rekommenderade principer för att tillåta åtkomst för gäst och externa användare med ett Azure AD B2B-konto finns i [principer för att tillåta gäst-och externt B2B-konto åtkomst](identity-access-policies-guest-access.md).

### <a name="guest-access-in-teams"></a>Gäst åtkomst i Teams

Utöver policyerna för användare som är interna för ditt företag eller din organisation kan administratörer aktivera gäst åtkomst för att tillåta att användare som är medlemmar i ditt företag eller din organisation får åtkomst till Teams-resurser och interagerar med interna personer, till exempel gruppkonversationer, chatt och möten. 

Mer information om gäst åtkomst och hur du implementerar det finns i  [Teams gäst åtkomst](https://docs.microsoft.com/microsoftteams/guest-access).

### <a name="external-access-in-teams"></a>Extern åtkomst i Teams

Extern åtkomst förväxlas ibland med gäst åtkomst, så det är viktigt att vara tydligt att dessa två icke-interna åtkomst funktioner faktiskt skiljer sig åt. 

Extern åtkomst är ett sätt för team användare från en hel extern domän att hitta, ringa, chatta och konfigurera möten med användarna i Teams. Teams-administratörer konfigurerar extern åtkomst på organisations nivå. Mer information finns i [Hantera extern åtkomst i Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access).

Externa Access-användare har mindre åtkomst till och funktionalitet jämfört med en person som har lagts till via gäst åtkomst. Externa Access-användare kan till exempel chatta med dina interna användare med Teams, men inte komma åt grupp kanaler, filer eller andra resurser.

Extern åtkomst använder inte Azure AD B2B-användarkonton och använder därför inte principer för villkorsstyrd åtkomst. 

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

![Steg 4: principer för Microsoft 365-molnappar](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurera principer för villkorsstyrd åtkomst för:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](secure-email-recommended-policies.md)

