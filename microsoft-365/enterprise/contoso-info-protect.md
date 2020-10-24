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
description: Förstå hur Contoso använder funktionerna för informations skydd i Microsoft 365 för företag för att skydda sina digitala till gångar i molnet.
ms.openlocfilehash: a1aa08a20d284d3a003f4a406c37f2107ce19bd1
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754611"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Informationsskydd för Contoso Corporation

Contoso är seriöst för sin informations säkerhet. Läckage och destruktion av immateriella rättigheter som beskriver produktens utformning och tillverkarspecifik tillverknings teknik skulle göra dem konkurrens kraftigare.

Innan du flyttar deras känsliga digitala till gångar till molnet har contoso säkerställt att sin lokala informations klassificering och säkerhets krav stöds av de molnbaserade tjänsterna i Microsoft 365 för företag.

## <a name="contoso-data-security-classification"></a>Säkerhets klassificering för Contoso-data

Contoso utförde en analys av sina uppgifter och fastställde följande klassificerings nivåer.

| Nivå 1: Baslinje | Nivå 2: Känslig | Nivå 3: Strikt reglerad |
|:-------|:-----|:-----|
| Datan krypteras och är endast tillgänglig för autentiserade användare.<BR> <BR> Tillhandahålls för alla data som lagrats lokalt och i Cloud-baserad lagring och arbets belastning. Datan krypteras när den lagras i tjänsten och överförs mellan tjänsten och klientenheterna. <BR><BR>Exempel på data på nivå 1 är normal företagskommunikation (e-post) och filer till administrations-, försäljnings- och supportpersonal. | Nivå 1 plus stark autentisering och dataförlustskydd.<BR> <BR> Stark autentisering inkluderar Azure Multi-Factor Authentication (MFA) med SMS-verifiering. Med förhindra data förlust ser du till att känslig eller viktig information inte reser utanför Microsofts moln.<BR><BR>Exempel på data på nivå 2 är ekonomisk och juridisk information, samt data vid forskning och utveckling av nya produkter. | Nivå 2 plus de högsta nivåerna för kryptering, autentisering och granskning.<BR><BR>Högsta krypteringsnivåerna för vilande data och data i molnet, kompatibla med regionala föreskrifter, kombinerade med MFA med smartkort, detaljerad granskning och aviseringar.<BR> <BR>Exempel på nivå 3-data är kund-och partner person uppgifter, produkt teknik specifikationer och tillverkarspecifik tillverknings teknik.  |
||||

## <a name="contoso-information-policies"></a>Contoso information policies
I följande tabell visas Contosos informations principer.


| Värde | Åtkomst | Datakvarhållning | Informationsskydd |
|:-------|:-----|:-----|:-----|
| Lågt affärsvärde (Nivå 1: Baslinje) | Tillåt åtkomst till alla.  | 6 månader | Använd kryptering. |
| Medelhögt affärsvärde (Nivå 2: Känslig) | Tillåt åtkomst till contoso-anställda, underleverantörer och partners. <BR><BR> Använd MFA, TLS (Transport Layer Security) och hantering av mobilprogram (MAM). | 2 år  | Använd hashvärden för dataintegritet.  |
| Högt affärsvärde (Nivå 3: Strikt reglerad) | Tillåt åtkomst till chefer och ledare inom teknik och tillverkning. <BR> <BR> Endast RMS (Rights Management System) med hanterade nätverksenheter.  | 7 år  | Använd digitala signaturer för oavvislighet.  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Contoso-sökvägen till informations skydd med Microsoft 365 för företag

Contoso Följ de här stegen för att förbereda Microsoft 365 för företag efter information om sina informations skydd:

1. Identifiera vilken information som ska skyddas

   Contoso gjorde en omfattande recension av sina befintliga digitala till gångar på lokala SharePoint-webbplatser och fildelning och klassificerade varje gång.

2. Bestämma åtkomst, bevarande och informations skydds principer för data nivåer

   Baserat på datanivåerna fastställde Contoso detaljerade principkrav, som användes för att skydda befintliga digitala tillgångar när de flyttades till molnet.

3. Skapa känslighets etiketter och deras inställningar för de olika informations nivåerna

   Contoso skapade känslighetsetiketter för datanivåerna, där etiketten Strikt reglerad inkluderar kryptering, behörigheter och vattenstämplar.

4.  Flytta data från lokala SharePoint-webbplatser och fil resurser till deras nya SharePoint-webbplatser

    De filer som migrerades till de nya SharePoint-webbplatserna, ärvde standardinställningen för de kvarhållningsetiketter som tilldelats till webbplatsen.

5.  Utbilda anställda hur man använder känslighets etiketter för nya dokument, hur man interagerar med contoso när de skapar nya SharePoint-webbplatser och alltid lagrar digitala till gångar på SharePoint-webbplatser

    Ändring av dåligt anställd – lagrings vanor behandlas ofta som den hårda delen av över gången för informations skydd för molnet. Contoso IT and Management som behövs för att få anställda att alltid märka och lagra sina digitala till gångar i molnet, avstå från att använda lokala fil resurser och inte använda tredjeparts moln lagrings tjänster eller USB-enheter.

## <a name="conditional-access-policies-for-information-protection"></a>Principer för villkorlig åtkomst i informationsskydd

Som en del av sin installation av Exchange Online och SharePoint konfigurerade contoso följande uppsättning villkorsstyrda åtkomst principer och använde dem för lämpliga grupper:

- [Principer för hanterad och ohanterad programåtkomst på enheter](../security/office-365-security/identity-access-policies.md)
- [Principer för Exchange Online-åtkomst](../security/office-365-security/secure-email-recommended-policies.md)
- [Principer för SharePoint-åtkomst](../security/office-365-security/sharepoint-file-access-policies.md)

Här följer en uppsättning contoso-principer för informations skydd.

![Principer för villkorlig åtkomst för enheter, Exchange Online och SharePoint](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso har även konfigurerat ytterligare principer för villkorlig åtkomst till identitet och inloggning. Se [Contoso Corporations identitet](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Med dessa principer ser du till att:

- Appar som tillåts och vilka åtgärder de kan utföra med organisationens data definieras av program skydds principer.
- Datorer och mobila enheter måste vara kompatibla.
- Exchange Online använder Office 365 Message Encryption (OME) för Exchange Online.
- SharePoint använder Programbegränsningar.
- I SharePoint används åtkomstkontrollprinciper för att endast bevilja åtkomst via webbläsare och för att blockera åtkomst för ohanterade enheter.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>Mappa Microsoft 365 för Enterprise-funktioner till data nivåerna contoso

I följande tabell mappas contoso data nivåer till informations skydds funktioner i Microsoft 365 för företag.

| Graden | Microsoft 365-molntjänster | Windows 10 och  Microsoft 365-appar för företag | Säkerhet och efterlevnad |
|:-------|:-----|:-----|:-----|
| Nivå 1: Baslinje  | Principer för villkorlig åtkomst i SharePoint och Exchange Online <BR> Behörigheter på SharePoint-webbplatser | Känslighetsetiketter <BR> BitLocker <BR> Windows Information Protection | Principer för villkorlig åtkomst för enheter och hantering av mobilprogram |
| Nivå 2: Känslig | Nivå 1 plus: <BR> <BR> Markera som känsligt <BR> Microsoft 365-kvarhållningsetiketter på SharePoint-webbplatser <BR> Dataförlustskydd för SharePoint och Exchange Online <BR> Isolerade SharePoint-webbplatser  | Nivå 1 plus: <BR> <BR> Känslighetsetiketter för digitala tillgångar  | Nivå 1 |
| Nivå 3: Strikt reglerad | Nivå 2 plus: <BR><BR> Skapa en egen nyckel (BYOK) kryptering och skydd för information om bransch hemlighet <BR> Azure Key Vault för affärs program som interagerar med Microsoft 365-tjänster | Nivå 2 | Nivå 1 |
|||||

Här är den resulterande contoso-säkerhetskonfigurationen.

![Contosos resulterande konfiguration av informationsskyddet](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Nästa steg

Lär dig hur Contoso använder [säkerhetsfunktionerna i Microsoft 365 för företag](contoso-security-summary.md) för identitets-och åtkomst hantering, Hot skydd, informations skydd och säkerhets hantering.

## <a name="see-also"></a>Se även

[Säkerhetsöversikt](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)
