---
title: Multifaktorautentisering för Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig mer om multifaktorautentisering i Microsoft 365.
ms.openlocfilehash: 128296b7dbc37ba5ebffb25a87bce589f8e5a904
ms.sourcegitcommit: 185d62f41f6b173894ba6e3e87b11b2b5d02db58
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/21/2020
ms.locfileid: "44340852"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a>Multifaktorautentisering för Microsoft 365

Lösenord är den vanligaste metoden för att autentisera en inloggning till en dator eller onlinetjänst, men de är också de mest sårbara. Människor kan välja enkla lösenord och använda samma lösenord för flera inloggningar till olika datorer och tjänster.

Om du vill ange ytterligare en säkerhetsnivå för inloggningar måste du använda MFA (Multifaktor authentication), som använder både ett lösenord, som ska vara starkt, och en ytterligare verifieringsmetod baserad på:

- Något du har med dig som inte är lätt dupliceras, till exempel en smart telefon.
- Något du unikt och biologiskt har, till exempel dina fingeravtryck, ansikte eller andra biometriska attribut.

Den ytterligare verifieringsmetoden används inte förrän användarens lösenord har verifierats. Med MFA, även om ett starkt användarlösenord äventyras, har angriparen inte din smarta telefon eller ditt fingeravtryck för att slutföra inloggningen.

## <a name="mfa-support-in-microsoft-365"></a>MFA-stöd i Microsoft 365
Som standard stöder både Microsoft 365 och Office 365 MFA för användarkonton med hjälp av:

- Ett sms som skickas till en telefon som kräver att användaren skriver en verifieringskod.
- Ett telefonsamtal.
- Microsoft Authenticator-appen för smarta telefoner.

I båda fallen använder MFA-inloggningen metoden "något du har med dig som inte är lätt att duplicera" för ytterligare verifiering.
Det finns flera sätt att aktivera MFA för Microsoft 365 och Office 365:

- Med säkerhet standardvärden
- Med principer för villkorlig åtkomst
- För varje enskilt användarkonto (rekommenderas inte)

De här sätten baseras på ditt Microsoft 365-abonnemang.
    
|Planera  |Rekommendation  | Typ av kund |
|---------|---------|----------|
| Alla Microsoft 365-abonnemang | Använd standardvärden för säkerhet, som kräver MFA för alla användarkonton. <br> Du kan också kräva MFA per användarkonto, men detta rekommenderas inte. | Småföretag |
| Microsoft 365 Business Premium <br><br> Microsoft 365 E3 <br><br> Azure Active Directory (Azure AD) Premium P1-licenser | Använd principer för villkorlig åtkomst för att kräva MFA för användarkonton baserat på gruppmedlemskap, appar eller andra villkor. | Små företag till företag |
| Microsoft 365 E5 <br><br> Azure AD Premium P2-licenser | Använd Azure AD Identity Protection för att kräva MFA baserat på inloggningsriskkriterier. |  Företag |
||||

### <a name="security-defaults"></a>Standardinställningar för säkerhet

Standardinställningar för säkerhet är en ny funktion för Microsoft 365 och Office 365, betalade eller utvärderingsprenumerationer skapade efter den 21 oktober 2019. Dessa prenumerationer har aktiverat säkerhetsstandarder, vilket:

- Kräver att alla användare använder MFA med Microsoft Authenticator-appen.
- Blockerar äldre autentisering.

Användare har 14 dagar på sig att registrera sig för MFA med Microsoft Authenticator-appen från sina smartphones, som börjar från första gången de loggar in efter att standardinställningar för säkerhet har aktiverats. Efter 14 dagar kommer användaren inte att kunna logga in förrän MFA-registreringen är klar.

Standardinställningar för säkerhet säkerställer att alla organisationer har en grundläggande säkerhetsnivå för användarinloggning som är aktiverad som standard. Du kan inaktivera säkerhetsstandarder till förmån för MFA med principer för villkorlig åtkomst.

Du aktiverar eller inaktiverar säkerhetsstandarder från **fönstret Egenskaper** för Azure AD i Azure-portalen.

![](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

Du kan använda säkerhetsstandarder med alla Microsoft 365-abonnemang.

Mer information finns i den här [översikten över standardinställningar för säkerhet](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). 

### <a name="conditional-access-policies"></a>Principer för villkorsstyrd åtkomst

Principer för villkorsstyrd åtkomst är en uppsättning regler som anger villkoren under vilka inloggningar utvärderas och tillåts. Du kan till exempel skapa en princip för villkorsstyrd åtkomst som anger:

- Om namnet på användarkontot är medlem i en grupp för användare som är tilldelade rollerna Exchange, användare, lösenord, säkerhet, SharePoint eller global administratör krävs MFA innan åtkomst tillåts.

Med den här principen kan du kräva MFA baserat på gruppmedlemskap, i stället för att försöka konfigurera enskilda användarkonton för MFA när de tilldelas eller tas bort från dessa administratörsroller.

Du kan också använda principer för villkorlig åtkomst för mer avancerade funktioner, till exempel att kräva MFA för specifika appar eller att inloggningen görs från en kompatibel enhet, till exempel din bärbara dator som kör Windows 10.

Du konfigurerar principer för villkorlig åtkomst från **säkerhetsfönstret** för Azure AD i Azure-portalen.

![](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

Du kan använda principer för villkorlig åtkomst med:

- Microsoft 365 Business Premium
- Microsoft 365 E3 och E5
- Azure AD Premium P1- och Azure AD Premium P2-licenser 

För småföretag med Microsoft 365 Business Premium kan du enkelt använda principer för villkorlig åtkomst med följande steg:

1. Skapa en grupp som innehåller användarkonton som kräver MFA.
2. Aktivera principen **Kräv MFA för globala administratörer.**
3. Skapa en gruppbaserad princip för villkorlig åtkomst med följande inställningar:
    - Tilldelningar > användare och grupper: Namnet på din grupp från steg 1 ovan.
    - Tilldelningar > Cloud-appar eller -åtgärder: Alla molnappar.
    - Åtkomstkontroller > bevilja > bevilja åtkomst > kräver multifaktorautentisering.
4. Aktivera principen.
5. Lägg till ett användarkonto i gruppen som skapats i steg 1 ovan och testa.
6. Om du vill kräva MFA för ytterligare användarkonton lägger du till dem i gruppen som skapats i steg 1.

Med den här principen för villkorlig åtkomst kan du distribuera MFA-kravet till användarna i din egen takt.

Företag bör använda [common conditional access-principer](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) för att konfigurera följande principer:

- [Kräv MFA för administratörer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Blockera äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

Mer information finns i den här [översikt över villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

Med Azure AD Identity Protection kan du skapa ytterligare en princip för villkorlig åtkomst för att [kräva MFA när inloggningsrisken är medelhög eller hög](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).

Du kan använda Azure AD Identity Protection och riskbaserade principer för villkorlig åtkomst med:

- Microsoft 365 E5
- Azure AD Premium P2-licenser

Mer information finns i den här [översikt över Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).

### <a name="mfa-for-an-individual-user-account-not-recommended"></a>MFA för ett enskilt användarkonto (rekommenderas inte)

Du bör använda antingen säkerhetsstandarder eller principer för villkorlig åtkomst för att kräva MFA för dina inloggningar för användarkontot. Om något av dessa inte kan användas rekommenderar Microsoft dock starkt MFA för användarkonton som har administratörsroller, särskilt den globala administratörsrollen, för alla storleksprenumerationer. 

Du aktiverar MFA för enskilda användarkonton från fönstret **Aktiv användare** i administrationscentret för Microsoft 365.

![](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

När användaren har aktiverats uppmanas de att registrera sig för MFA och att välja och testa den ytterligare verifieringsmetoden nästa gång användaren loggar in.

### <a name="using-these-methods-together"></a>Använda dessa metoder tillsammans

I den här tabellen visas resultatet av att aktivera MFA med standardinställningar för säkerhet, principer för villkorsstyrd åtkomst och användarspecifika kontoinställningar.

|| Aktiverat | Inaktiverad | Metod för sekundär autentisering |
|:-------|:-----|:-------|:-------|
| **Standardinställningar för säkerhet** | Det går inte att använda principer för villkorsstyrd åtkomst |   Det går att använda principer för villkorsstyrd åtkomst | Microsoft Authenticator-appen |
| **Principer för villkorsstyrd åtkomst** |Om några är aktiverade kan du inte aktivera standardinställningar för säkerhet | Om alla är inaktiverade kan du aktivera standardinställningar för säkerhet | Användardefinierad under MFA-registrering |
| **Inställning per användarkonto (rekommenderas inte)** | Åsidosätts av säkerhetsstandarder och principer för villkorlig åtkomst som kräver MFA | Åsidosätts efter säkerhetsstandarder och principer för villkorlig åtkomst | Användardefinierad under MFA-registrering|
||||

Om standardinställningarna för säkerhet är aktiverade uppmanas alla nya användare att registrera MFA och använda Microsoft Authenticator-appen vid nästa inloggning.

Om en användare har en äldre telefon som kan ta emot textmeddelanden men inte kan köra Microsoft Authenticator-appen kan du aktivera MFA på det specifika användarkontot och låta dem registrera sig med hjälp av ytterligare verifieringsmetod för textkod med följande steg:

1. Inaktivera säkerhetsstandarder i Azure-portalen.
2. Aktivera MFA för användarkontot i Microsoft 365-administrationscentret.
3. Låt användaren logga in och registrera sig för MFA och textkodautentiseringsmetoden.
4. När du är klar aktiverar du standardinställningar för säkerhet i Azure-portalen

## <a name="ways-to-manage-mfa-settings"></a>Olika sätt att hantera MFA-inställningar

Det finns två sätt att hantera MFA-inställningar.

I Azure-portalen kan du:

- Aktivera och inaktivera säkerhetsstandarder
- Konfigurera principer för villkorlig åtkomst

I administrationscentret för Microsoft 365 kan du konfigurera MFA-inställningar per användare och tjänst.

## <a name="your-next-step"></a>Nästa steg

[Konfigurera MFA för Microsoft 365](set-up-multi-factor-authentication.md)

