---
title: Identitets- och enhetsåtkomstprinciper för att tillåta gäst- och extern användares B2B-åtkomst – Microsoft 365 för | Microsoft Docs
description: Här beskrivs den rekommenderade villkorsstyrda åtkomsten och relaterade principer för att skydda åtkomsten för gäster och externa användare.
ms.prod: m365-security
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 9d3a47752efc86c8ced32905bda851b7d8157f82
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910664"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>Principer för att tillåta gäståtkomst och åtkomst för externa B2B-användare

I den här artikeln beskrivs hur du justerar de rekommenderade principerna för enhets- och identitetsåtkomst för att ge åtkomst till gäster och externa användare som har ett Azure Active Directory-konto (Azure AD) Business-to-Business (B2B). Den här vägledningen bygger på de [gemensamma principerna för identitet och enhetsåtkomst.](identity-access-policies.md)

Dessa rekommendationer är utformade för att gälla **baslinjenivån** för skydd. Men du kan också justera rekommendationerna utifrån dina specifika behov för **känsligt och** **starkt reglerat** skydd.

Att ange en sökväg för B2B-konton att autentisera med Din Azure AD-klientorganisation ger inte dessa konton åtkomst till hela miljön. B2B-användare och deras konton har åtkomst till tjänster och resurser, som filer, som delas med dem genom villkorsstyrd åtkomstprincip.

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>Uppdatera vanliga principer för att tillåta och skydda gäster och extern användaråtkomst

Det här diagrammet visar vilka principer som ska läggas till eller uppdateras bland vanliga identitets- och enhetsåtkomstprinciper, för B2B-gäståtkomst och extern användaråtkomst.

[![Sammanfattning av principuppdateringar för att skydda gäståtkomst](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

I följande tabell finns de principer som du antingen behöver skapa och uppdatera. De vanliga principerna länkar till de associerade konfigurationsanvisningarna i [artikeln Principer för enhetsåtkomst och identiteter.](identity-access-policies.md)

|Skyddsnivå|Principer|Mer information|
|---|---|---|
|**Grundläggande**|[Kräv MFA alltid för gäster och externa användare](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Skapa den här nya principen och konfigurera: <ul><li>För **Tilldelningar > Användare** och grupper > inkludera väljer du Välj användare **och** grupper och sedan **Alla gästanvändare och externa användare.**</li><li>Om **du vill > Villkor >** inloggning låter du alla alternativ vara avmarkerade för att alltid tillämpa multifaktorautentisering (MFA).</li></ul>|
||[Kräv MFA när inloggningsrisken är *medium* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ändra den här principen så att gäster och externa användare utesluts.|
||[Kräv kompatibla PC-datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Ändra den här principen så att gäster och externa användare utesluts.|

Om du vill inkludera eller exkludera gäster och externa användare i **villkorsstyrda** åtkomstprinciper ska uppgifter > användare och grupper > Inkludera eller Exkludera **,** markera Alla gästanvändare och **externa användare.**

![skärmdump med kontroller för att utesluta gäster och externa användare](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Mer information

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Åtkomst för gäster och externa användare med Microsoft Teams

Microsoft Teams definierar följande användare:

- **Gäståtkomst** använder ett Azure AD B2B-konto som kan läggas till som medlem i ett team och har åtkomst till teamets kommunikation och resurser.

- **Extern åtkomst** är för en extern användare som inte har ett B2B-konto. Extern användaråtkomst omfattar inbjudningar, samtal, chattar och möten, men omfattar inte teammedlemskap och åtkomst till teamets resurser.

Mer information finns i [jämförelsen mellan gäster och extern användaråtkomst för team.](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)

Mer information om hur du skyddar identitets- och enhetsåtkomstprinciper för Teams finns i Principrekommendationer för att skydda [Teams chattar, grupper och filer.](teams-access-policies.md)

### <a name="require-mfa-always-for-guest-and-external-users"></a>Kräv MFA alltid för gäst och externa användare

Med den här principen uppmanas gäster att registrera sig för MFA i klientorganisationen, oavsett om de är registrerade för MFA i sin hemklientorganisation. När du ska få åtkomst till resurser i klientorganisationen måste gäster och externa användare använda MFA för varje begäran.

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>Utesluta gäster och externa användare från riskbaserade MFA

Organisationer kan tillämpa riskbaserade principer för B2B-användare med Azure AD-identitetsskydd, men det finns begränsningar i implementeringen av Azure AD Identity Protection för B2B-samarbetsanvändare i en resurskatalog på grund av att de är befintliga i deras hemkatalog. På grund av dessa begränsningar rekommenderar Microsoft att du exkluderar gäster från riskbaserade MFA-principer och kräver att dessa användare alltid använder MFA.

Mer information finns i Begränsningar [av identitetsskydd för användare av B2B-samarbete.](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)

### <a name="excluding-guests-and-external-users-from-device-management"></a>Utesluta gäster och externa användare från enhetshantering

Det är bara en organisation som kan hantera en enhet. Om du inte exkluderar gäster och externa användare från principer som kräver enhetsefterlevnad blockeras dessa användare av de här principerna.

## <a name="next-step"></a>Nästa steg

![Steg 4: Principer för Microsoft 365-molnappar](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurera principer för villkorsstyrd åtkomst för:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)