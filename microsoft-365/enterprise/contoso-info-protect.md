---
title: Informationsskydd för Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå hur Contoso använder funktionerna för informationsskydd i Microsoft 365 för företag för att skydda sina digitala tillgångar i molnet.
ms.openlocfilehash: 90a82fbd4dd77ff0f8faa024ced177a640a10b80
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911044"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Informationsskydd för Contoso Corporation

Contoso menar allvarligt på deras informationssäkerhet. Läckage eller marknadsföring av immateriell egendom som beskriver deras produktdesign och egenutvecklade tillverkningsteknik skulle placera dem i en konkurrensfördel.

Innan Contoso flyttar över känsliga digitala tillgångar till molnet ser han till att deras lokala informationsklassificerings- och skyddskrav stöds av de molnbaserade tjänsterna i Microsoft 365 för företag.

## <a name="contoso-data-security-classification"></a>Contoso-datasäkerhetsklassificering

Contoso utförde en analys av deras data och bestämde följande klassificeringsnivåer.

| Nivå 1: Baslinje | Nivå 2: Känslig | Nivå 3: Strikt reglerad |
|:-------|:-----|:-----|
| Datan krypteras och är endast tillgänglig för autentiserade användare.<BR> <BR> Tillhandahålls för alla data som lagras lokalt och i molnbaserad lagring och arbetsbelastning. Datan krypteras när den lagras i tjänsten och överförs mellan tjänsten och klientenheterna. <BR><BR>Exempel på data på nivå 1 är normal företagskommunikation (e-post) och filer till administrations-, försäljnings- och supportpersonal. | Nivå 1 plus stark autentisering och dataförlustskydd.<BR> <BR> Stark autentisering innehåller Azure AD Multi-Factor Authentication (MFA) med SMS-validering. Dataförlustskydd säkerställer att känslig eller kritisk information inte färdas utanför Microsoft-molnet.<BR><BR>Exempel på data på nivå 2 är ekonomisk och juridisk information, samt data vid forskning och utveckling av nya produkter. | Nivå 2 plus de högsta nivåerna för kryptering, autentisering och granskning.<BR><BR>Högsta krypteringsnivåerna för vilande data och data i molnet, kompatibla med regionala föreskrifter, kombinerade med MFA med smartkort, detaljerad granskning och aviseringar.<BR> <BR>Exempel på data på Nivå 3 är personlig information för kunder och partner, produktteknikspecifikationer och tillverkningsteknik.  |
||||

## <a name="contoso-information-policies"></a>Informationsprinciper för Contoso
I följande tabell finns informationsprinciperna för Contoso.


| Value | Åtkomst | Datakvarhållning | Informationsskydd |
|:-------|:-----|:-----|:-----|
| Lågt affärsvärde (Nivå 1: Baslinje) | Tillåt åtkomst till alla.  | 6 månader | Använd kryptering. |
| Medelhögt affärsvärde (Nivå 2: Känslig) | Ge åtkomst till Contoso-anställda, underleverantörer och partners. <BR><BR> Använd MFA, TLS (Transport Layer Security) och hantering av mobilprogram (MAM). | 2 år  | Använd hashvärden för dataintegritet.  |
| Högt affärsvärde (Nivå 3: Strikt reglerad) | Tillåt åtkomst till chefer och ledare inom teknik och tillverkning. <BR> <BR> Endast RMS (Rights Management System) med hanterade nätverksenheter.  | 7 år  | Använd digitala signaturer för oavvislighet.  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Contosos väg till informationsskydd med Microsoft 365 för företag

Contoso följde de här stegen för att förbereda Microsoft 365 för företag för sina krav på informationsskydd:

1. Identifiera vilken information du bör skydda

   Contoso har gjort en omfattande granskning av sina befintliga digitala tillgångar på lokala SharePoint-webbplatser och filresurser och klassificerade varje tillgång.

2. Fastställa åtkomst-, bevarande- och informationsskyddsprinciper för datanivåer

   Baserat på datanivåerna fastställde Contoso detaljerade principkrav, som användes för att skydda befintliga digitala tillgångar när de flyttades till molnet.

3. Skapa känslighetsetiketter och deras inställningar för olika informationsnivåer

   Contoso skapade känslighetsetiketter för datanivåerna, där etiketten Strikt reglerad inkluderar kryptering, behörigheter och vattenstämplar.

4.  Flytta data från lokala SharePoint-webbplatser och filresurser till sina nya SharePoint-webbplatser

    De filer som migrerades till de nya SharePoint-webbplatserna, ärvde standardinställningen för de kvarhållningsetiketter som tilldelats till webbplatsen.

5.  Utbilda anställda hur de använder känslighetsetiketter för nya dokument, hur de interagerar med Contoso IT när de skapar nya SharePoint-webbplatser och alltid lagrar digitala tillgångar på SharePoint-webbplatser

    Att ändra informationslagringsvanor för dåliga medarbetare är ofta den svåraste delen av övergången till informationsskydd för molnet. Contosos IT- och hantering krävs för att få anställda att alltid märka och lagra sina digitala tillgångar i molnet, undvika att använda lokala filresurser och inte använda molnbaserade lagringstjänster eller USB-enheter från tredje part.

## <a name="conditional-access-policies-for-information-protection"></a>Principer för villkorlig åtkomst i informationsskydd

Som en del av utrullningen av Exchange Online och SharePoint konfigurerade Contoso följande uppsättning principer för villkorsstyrd åtkomst och tillämpade dem på rätt grupper:

- [Principer för hanterad och ohanterad programåtkomst på enheter](../security/office-365-security/identity-access-policies.md)
- [Principer för Exchange Online-åtkomst](../security/office-365-security/secure-email-recommended-policies.md)
- [Principer för SharePoint-åtkomst](../security/office-365-security/sharepoint-file-access-policies.md)

Här är den resulterande uppsättningen Contoso-principer för informationsskydd.

![Principer för villkorlig åtkomst för enheter, Exchange Online och SharePoint](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso har även konfigurerat ytterligare principer för villkorlig åtkomst till identitet och inloggning. Se [Contoso Corporations identitet](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Med dessa principer ser du till att:

- Appar som är tillåtna och de åtgärder de kan utföra med organisationens data definieras av principer för appskydd.
- Datorer och mobila enheter måste vara kompatibla.
- Exchange Online använder meddelandekryptering i Office 365 (OME) för Exchange Online.
- I SharePoint används apptvingade begränsningar.
- I SharePoint används åtkomstkontrollprinciper för att endast bevilja åtkomst via webbläsare och för att blockera åtkomst för ohanterade enheter.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>Mappa Microsoft 365 för företag-funktioner till Contoso-datanivåer

Följande tabell mappar Contosos datanivåer till informationsskyddsfunktionerna i Microsoft 365 för företag.

| Nivå | Microsoft 365-molntjänster | Windows 10 och  Microsoft 365-appar för företag | Säkerhet och efterlevnad |
|:-------|:-----|:-----|:-----|
| Nivå 1: Baslinje  | Principer för villkorlig åtkomst i SharePoint och Exchange Online <BR> Behörigheter på SharePoint-webbplatser | Känslighetsetiketter <BR> BitLocker <BR> Windows Information Protection | Principer för villkorlig åtkomst för enheter och hantering av mobilprogram |
| Nivå 2: Känslig | Nivå 1 plus: <BR> <BR> Markera som känsligt <BR> Microsoft 365-kvarhållningsetiketter på SharePoint-webbplatser <BR> Dataförlustskydd för SharePoint och Exchange Online <BR> Isolerade SharePoint-webbplatser  | Nivå 1 plus: <BR> <BR> Känslighetsetiketter för digitala tillgångar  | Nivå 1 |
| Nivå 3: Strikt reglerad | Nivå 2 plus: <BR><BR> Ta med din egen nyckelkryptering (BYOK) och skydd för affärshemlighetsinformation <BR> Azure Key Vault för verksamhetsbaserade program som interagerar med Microsoft 365-tjänster | Nivå 2 | Nivå 1 |
|||||

Här är den resulterande konfigureringen av Contoso informationsskydd.

![Contosos resulterande konfiguration av informationsskyddet](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Nästa steg

Lär dig hur Contoso använder säkerhetsfunktionerna i [Microsoft 365](contoso-security-summary.md) för företag för identitets- och åtkomsthantering, skydd mot hot, informationsskydd och säkerhetshantering.

## <a name="see-also"></a>Se även

[Säkerhetsöversikt](../security/office-365-security/security-roadmap.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)