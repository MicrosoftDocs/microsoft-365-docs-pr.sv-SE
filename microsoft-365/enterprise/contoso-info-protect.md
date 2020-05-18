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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå hur Contoso använder funktionerna för informationsskydd i Microsoft 365 Enterprise till att skydda sina digitala tillgångar i molnet.
ms.openlocfilehash: 137e6ff499ba8fb119c696dba9337307876ee0c2
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268416"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Informationsskydd för Contoso Corporation

Contoso tar informationssäkerhet och skydd på största allvar. Exempelvis kan läckage eller förstörelse av deras immateriella rättigheter, där produktutformning och tillverkarspecifika tillverkningstekniker beskrivs, vara negativt för konkurrensen.

Innan de flyttade känsliga och värdefulla digitala tillgångar till molnet, såg de till att deras lokala informationsklassificering och skyddskrav stöds och kan implementeras i de molnbaserade tjänsterna för Microsoft 365 Enterprise.

## <a name="contosos-data-security-classification"></a>Contosos datasäkerhetsklassificering

Contoso genomförde en analys av sina data och fastställde nedanstående nivåer.

||||
|:-------|:-----|:-----|
| **Nivå 1: Baslinje** | **Nivå 2: Känslig** | **Nivå 3: Strikt reglerad** |
| Datan krypteras och är endast tillgänglig för autentiserade användare. <BR> <BR> Detta gäller alla data som lagras lokalt och i molnbaserad lagring och arbetsbelastningar, till exempel Office 365. Datan krypteras när den lagras i tjänsten och överförs mellan tjänsten och klientenheterna. <BR><BR> Exempel på data på nivå 1 är normal företagskommunikation (e-post) och filer till administrations-, försäljnings- och supportpersonal. | Nivå 1 plus stark autentisering och dataförlustskydd. <BR> <BR> Stark autentisering inkluderar Azure Multi-Factor Authentication (MFA) med SMS-verifiering. Dataförlustskyddet säkerställer att känslig eller kritisk information inte hamnar utanför Microsoft Cloud. <BR><BR> Exempel på data på nivå 2 är ekonomisk och juridisk information, samt data vid forskning och utveckling av nya produkter. | Nivå 2 plus de högsta nivåerna för kryptering, autentisering och granskning. <BR> <BR>  Högsta krypteringsnivåerna för vilande data och data i molnet, kompatibla med regionala föreskrifter, kombinerade med MFA med smartkort, detaljerad granskning och aviseringar. <BR> <BR> Exempel på data på nivå 3 är personligt identifierbar information för kunder och partners, specifikationer för produktteknik samt tillverkarspecifika tillverkningstekniker.  |
||||

## <a name="contosos-information-policies"></a>Contosos informationsprinciper
Contosos informationsprinciper visas i nedanstående tabell.

|||||
|:-------|:-----|:-----|:-----|
|  | **Åtkomst** | **Datakvarhållning** | **Informationsskydd** |
| Lågt affärsvärde (Nivå 1: Baslinje) | Tillåt åtkomst till alla  | 6 månader | Använd kryptering. |
| Medelhögt affärsvärde (Nivå 2: Känslig) | Tillåt åtkomst till Contoso-anställda, underleverantörer och partners <BR> <BR> Använd MFA, TLS (Transport Layer Security) och hantering av mobilprogram (MAM). | 2 år  | Använd hashvärden för dataintegritet.  |
| Högt affärsvärde (Nivå 3: Strikt reglerad) | Tillåt åtkomst till chefer och ledare inom teknik och tillverkning. <BR> <BR> Endast RMS (Rights Management System) med hanterade nätverksenheter.  | 7 år  | Använd digitala signaturer för oavvislighet.  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-enterprise"></a>Contosos väg till informationsskydd med Microsoft 365 Enterprise

Contoso använde följande steg när de förberedde Microsoft 365 Enterprise på sina krav för informationsskydd:

1. Identifierade vilken information som ska skyddas

   Contoso genomförde en omfattande granskning av sina befintliga digitala tillgångar på lokala SharePoint-webbplatser och filresurser, samt klassificerade dem.

2. Fastställde åtkomst-, kvarhållnings- och informationsskyddsprinciper för datanivåer

   Baserat på datanivåerna fastställde Contoso detaljerade principkrav, som användes för att skydda befintliga digitala tillgångar när de flyttades till molnet.

3. Skapade känslighetsetiketter och inställningar för de olika informationsnivåerna

   Contoso skapade känslighetsetiketter för datanivåerna, där etiketten Strikt reglerad inkluderar kryptering, behörigheter och vattenstämplar.

4.  Data flyttades från lokala SharePoint-webbplatser och filresurser till de nya SharePoint-webbplatserna

    De filer som migrerades till de nya SharePoint-webbplatserna, ärvde standardinställningen för de kvarhållningsetiketter som tilldelats till webbplatsen.

5.  Utbildade personalen i att använda känslighetsetiketter för nya dokument, hur man interagerar med Contoso IT när nya SharePoint-webbplatser skapas, samt att alltid lagra digitala tillgångar på SharePoint-webbplatser

    Med tanke på den svåraste delen i överföringen av informationsskydd i molnet, behövde Contoso IT och ledningen ändra den bristfälliga informationslagringen hos organisationens anställda till att alltid märka och lagra sina digitala tillgångar i molnet, att avstå från att använda lokala filresurser och att aldrig använda molnlagringstjänster från tredje part eller USB-enheter.

## <a name="conditional-access-policies-for-information-protection"></a>Principer för villkorlig åtkomst i informationsskydd

Förutom infrastrukturen för identitet och hantering av mobilenheter, och som en del av sin distribution av Exchange Online och SharePoint, konfigurerade Contoso följande uppsättning med principer för villkorlig åtkomst och använde dem i lämpliga grupper:

- [Principer för hanterad och ohanterad programåtkomst på enheter](identity-access-policies.md)
- [Principer för Exchange Online-åtkomst](secure-email-recommended-policies.md)
- [Principer för SharePoint-åtkomst](sharepoint-file-access-policies.md)

Här är Contosos resulterande uppsättning med principer för informationsskydd.

![Principer för villkorlig åtkomst för enheter, Exchange Online och SharePoint](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso har även konfigurerat ytterligare principer för villkorlig åtkomst till identitet och inloggning. Se [Contoso Corporations identitet](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Med dessa principer ser du till att:

- Appar tillåts och de åtgärder som kan vidtas med dina organisationsdata definieras av appskyddsprinciper.
- Datorer och mobila enheter måste vara kompatibla.
- Exchange Online använder meddelandekrypteringen i Office 365.
- I SharePoint används appframtvingade begränsningar.
- I SharePoint används åtkomstkontrollprinciper för att endast bevilja åtkomst via webbläsare och för att blockera åtkomst för ohanterade enheter.

## <a name="mapping-microsoft-365-enterprise-features-to-contosos-data-levels"></a>Microsoft 365 Enterprise-funktionerna mappas till Contosos datanivåer

I följande tabell mappas Contosos datanivåer till informationsskyddsfunktionerna i Microsoft 365 Enterprise.

|||||
|:-------|:-----|:-----|:-----|
| | **Office 365** | **Windows 10 och  Microsoft 365-appar för företag** | **EMS** |
| Nivå 1: Baslinje  | Principer för villkorlig åtkomst i SharePoint och Exchange Online <BR> Behörigheter på SharePoint-webbplatser | Känslighetsetiketter <BR> BitLocker <BR> Windows Information Protection | Principer för villkorlig åtkomst för enheter och hantering av mobilprogram |
| Nivå 2: Känslig | Nivå 1 plus: <BR> <BR> Markera som känsligt <BR> Microsoft 365-kvarhållningsetiketter på SharePoint-webbplatser <BR> Dataförlustskydd för SharePoint och Exchange Online <BR> Isolerade SharePoint-webbplatser  | Nivå 1 plus: <BR> <BR> Känslighetsetiketter för digitala tillgångar  | Nivå 1 |
| Nivå 3: Strikt reglerad | Nivå 2 plus: <BR><BR> BYOK-kryptering (Bring Your Own Key) och skydd av företagshemligheter <BR> Azure Key Vault för verksamhetskritiska affärsprogram som interagerar med Microsoft 365-tjänster | Nivå 2 | Nivå 1 |
|||||

Här är Contosos resulterande konfiguration av informationsskyddet.

![Contosos resulterande konfiguration av informationsskyddet](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Nästa steg

[Se](contoso-security-summary.md) hur Contoso använder säkerhetsfunktionerna i Microsoft 365 Enterprise för identitets- och åtkomsthantering, skydd mot hot, informationsskydd och säkerhetshantering.

## <a name="see-also"></a>Se även

[Informationsskydd för Microsoft 365 Enterprise](infoprotect-infrastructure.md)

[Distributionsguide](deploy-microsoft-365-enterprise.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)


