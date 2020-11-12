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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig mer om multifaktorautentisering i Microsoft 365.
ms.openlocfilehash: cb425f3fd3d97dc0cd8815699bd22cb2540aed46
ms.sourcegitcommit: 09518b7c9146cda7fd42839ee644ad418d48491a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/12/2020
ms.locfileid: "49001519"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a>Multifaktorautentisering för Microsoft 365

Lösen ord är den vanligaste metoden för att autentisera en inloggning på en dator eller online tjänst, men de är också mest sårbara. Personer kan välja enkla lösen ord och använda samma lösen ord för flera inloggningar på olika datorer och tjänster.

För att tillhandahålla en ytterligare säkerhets nivå för inloggningar måste du använda multifaktorautentisering (MFA), som använder både ett lösen ord, som är starkt och en ytterligare verifierings metod baserat på:

- Något du har med dig som inte är lätt att hitta, till exempel en smart telefon.
- Något som är unikt och biologiskt har, till exempel finger avtryck, ansikte eller andra bio metriska attribut.

Den alternativa kontrollen används inte förrän användarens lösen ord har verifierats. Med MFA, även om ett starkt användar lösen ord äventyras, har angriparen inte din telefon eller ditt finger avtryck för att slutföra inloggningen.

## <a name="mfa-support-in-microsoft-365"></a>MFA-stöd i Microsoft 365

Som standard stöder både Microsoft 365 och Office 365 MFA för användar konton med:

- Ett textmeddelande som skickas till en telefon som kräver att användaren skriver en verifierings kod.
- Ett telefonsamtal.
- Programmet Microsoft Authenticator smart telefon.

I båda fallen använder MFA-inloggningen det "något du har med dig som inte är lätt att dubblera" för den ytterligare verifieringen. Det finns flera sätt att aktivera MFA för Microsoft 365 och Office 365:

- Med säkerhets standarder
- Med principer för villkorsstyrd åtkomst
- För varje enskilt användar konto (rekommenderas inte)

Dessa sätt baseras på ditt Microsoft 365-abonnemang.

|Planera|Rekommendation|Typ av kund|
|---|---|---|
|Alla Microsoft 365-abonnemang|Använd säkerhets standarder, som kräver MFA för alla användar konton. <p> Du kan också konfigurera användarspecifik MFA för enskilda användar konton, men det rekommenderas inte.|Småföretag|
|Microsoft 365 Business Premium <p> Microsoft 365 E3 <p> Azure Active Directory (Azure AD) Premium P1-licenser|Använd villkorsstyrda åtkomst principer för att kräva MFA för användar konton baserat på grupp medlemskap, appar eller andra villkor.|Småföretag till företag|
|Microsoft 365 E5 <p> Azure AD Premium P2-licenser|Använd Azure AD Identity Protection för att kräva MFA utifrån villkor för inloggnings risker.|Enterprise|
||||

### <a name="security-defaults"></a>Standardinställningar för säkerhet

Standardinställningar för säkerhet är en ny funktion för Microsoft 365 och Office 365, betalade eller utvärderingsprenumerationer skapade efter den 21 oktober 2019. Dessa abonnemang har aktiverat säkerhets inställningar, som:

- Kräver att alla dina användare använder MFA med Microsoft Authenticator-appen.
- Blockerar bakåtkompatibel-verifikation.

Användare har 14 dagar på sig att registrera sig för MFA med Microsoft Authenticator-appen från sina smartphones, som börjar från första gången de loggar in efter att standardinställningar för säkerhet har aktiverats. Efter 14 dagar kommer användaren inte att kunna logga in förrän MFA-registreringen är klar.

Standardinställningar för säkerhet säkerställer att alla organisationer har en grundläggande säkerhetsnivå för användarinloggning som är aktiverad som standard. Du kan avaktivera säkerhets standardvärden för MFA med principer för villkorsstyrd åtkomst.

Du aktiverar eller inaktiverar säkerhets standarder från fönstret **Egenskaper** för Azure AD i Azure-portalen.

![Bild av sidan katalog egenskaper.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

Du kan använda säkerhets standarder med alla Microsoft 365-abonnemang.

Mer information finns i den här [översikten över standardinställningar för säkerhet](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

### <a name="conditional-access-policies"></a>Principer för villkorsstyrd åtkomst

Principer för villkorsstyrd åtkomst är en uppsättning regler som anger villkoren under vilka inloggningar utvärderas och tillåts. Du kan till exempel skapa en princip för villkorsstyrd åtkomst som anger:

- Om namnet på användarkontot är medlem i en grupp för användare som är tilldelade rollerna Exchange, användare, lösenord, säkerhet, SharePoint eller global administratör krävs MFA innan åtkomst tillåts.

Med den här principen kan du kräva MFA baserat på gruppmedlemskap, i stället för att försöka konfigurera enskilda användarkonton för MFA när de tilldelas eller tas bort från dessa administratörsroller.

Du kan också använda villkorsstyrda åtkomst principer för mer avancerade funktioner, till exempel krav på MFA för specifika appar eller att inloggningen görs från en kompatibel enhet, till exempel din bärbara dator med Windows 10.

Du konfigurerar villkorsstyrda åtkomst principer från fönstret **säkerhet** för Azure AD i Azure-portalen.

![Bild av meny alternativet för villkorsstyrd åtkomst](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

Du kan använda villkorsstyrda åtkomst principer med:

- Microsoft 365 Business Premium
- Microsoft 365 E3 och E5
- Azure AD Premium P1-och Azure AD Premium P2-licenser

För småföretag med Microsoft 365 Business Premium kan du enkelt använda villkorsstyrda åtkomst principer med följande steg:

1. Skapa en grupp som innehåller de användar konton som kräver MFA.
2. Aktivera principen **KRÄV MFA för globala administratörer** .
3. Skapa en gruppbaserad princip för villkorsstyrd åtkomst med följande inställningar:
    - Uppgifter > användare och grupper: namnet på gruppen från steg 1 ovan.
    - Uppgifter > moln program eller-åtgärder: alla molnappar.
    - Åtkomst kontroll > tilldela > beviljar åtkomst > kräver multifaktorautentisering.
4. Aktivera policyn.
5. Lägga till ett användar konto i gruppen som skapades i steg 1 ovan och testa.
6. Om du vill kräva MFA för ytterligare användar konton lägger du till dem i gruppen som skapades i steg 1.

Med den här principen för villkorsstyrd åtkomst kan du lyfta fram behovet av MFA för användarna i din egen takt.

Företag bör använda [vanliga principer för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) för att konfigurera följande principer:

- [Kräv MFA för administratörer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Blockera äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

Mer information finns i den här [översikt över villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

Med Azure AD Identity Protection kan du skapa ytterligare principer för villkorsstyrd åtkomst för att [kräva MFA när en inloggnings risk är medel eller hög](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).

Du kan använda Azure AD Identity Protection och riskfyllda villkorsstyrda åtkomst principer med:

- Microsoft 365 E5
- Azure AD Premium P2-licenser

Mer information finns i den här [översikt över Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).

### <a name="legacy-per-user-mfa-not-recommended"></a>Legacy användarspecifik för användare (rekommenderas inte)

Du bör använda antingen säkerhets standarder eller villkorsstyrda åtkomst principer för att kräva MFA för inloggnings programmen för ditt användar konto. Om något av dessa inte kan användas rekommenderar Microsoft starkt MFA för användar konton som har administratörs roller, särskilt den globala administratörs rollen, för alla storleks abonnemang.

Du aktiverar MFA för enskilda användar konton i det **aktiva användar** fönstret i administrations centret för Microsoft 365.

![Bild av alternativet multifaktorautentisering på sidan aktiva användare](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

När användaren sedan loggar in uppmanas de att registrera sig för MFA och välja och testa den ytterligare verifierings metoden.

### <a name="using-these-methods-together"></a>Använda dessa metoder tillsammans

I den här tabellen visas resultatet av att aktivera MFA med standardinställningar för säkerhet, principer för villkorsstyrd åtkomst och användarspecifika kontoinställningar.

||Aktiverat|Inaktiverad|Metod för sekundär autentisering|
|---|---|---|---|
|**Standardinställningar för säkerhet**|Kan inte använda principer för villkorsstyrd åtkomst|Det går att använda principer för villkorsstyrd åtkomst|Microsoft Authenticator-appen|
|**Principer för villkorsstyrd åtkomst**|Om det finns några är det möjligt att du inte kan aktivera säkerhets standarder|Om alla är inaktiverade kan du aktivera standardinställningar för säkerhet|Användardefinierad under MFA-registrering|
|**Legacy användarspecifik för användare (rekommenderas inte)**|Åsidosätter säkerhets standarder och villkorsstyrda åtkomst principer som kräver MFA för varje inloggning|Åsidosatt av säkerhets standarder och villkorsstyrda åtkomst principer|Användardefinierad under MFA-registrering|
||||

Om säkerhets standarder är aktiverade ombeds alla nya användare om MFA-registrering och användning av Microsoft Authenticator-appen vid nästa inloggning.

## <a name="ways-to-manage-mfa-settings"></a>Olika sätt att hantera inställningar för MFA

Det finns två sätt att hantera MFA-inställningar.

I Azure-portalen kan du:

- Aktivera och inaktivera säkerhets standarder
- Konfigurera principer för villkorsstyrd åtkomst

I administrations centret för Microsoft 365 kan du konfigurera inställningar för MFA-användare och tjänster.

## <a name="your-next-step"></a>Nästa steg

[Konfigurera MFA för Microsoft 365](set-up-multi-factor-authentication.md)
