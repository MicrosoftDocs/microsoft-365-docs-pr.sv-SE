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
ms.openlocfilehash: 1966fdec3de246ca54fd99ab018485b9ee817281
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399247"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Informationsskydd för Contoso Corporation

Contoso tar informationssäkerhet och skydd på största allvar. Exempelvis kan läckage eller förstörelse av deras immateriella rättigheter, där produktutformning och tillverkarspecifika tillverkningstekniker beskrivs, vara negativt för konkurrensen.

Innan du flyttar deras känsliga och mest värdefulla digitala till gångar till molnet, säkerställer de att sin lokala informations klassificering och säkerhets krav stöds och implementerades i molnbaserade tjänster i Microsoft 365 för företag.

## <a name="contosos-data-security-classification"></a>Contosos datasäkerhetsklassificering

Contoso genomförde en analys av sina data och fastställde nedanstående nivåer.

| Nivå 1: Baslinje | Nivå 2: Känslig | Nivå 3: Strikt reglerad |
|:-------|:-----|:-----|
| Datan krypteras och är endast tillgänglig för autentiserade användare. <BR> <BR> Tillhandahålls för alla data som lagrats lokalt och i Cloud-baserad lagring och arbets belastning. Datan krypteras när den lagras i tjänsten och överförs mellan tjänsten och klientenheterna. <BR><BR> Exempel på data på nivå 1 är normal företagskommunikation (e-post) och filer till administrations-, försäljnings- och supportpersonal. | Nivå 1 plus stark autentisering och dataförlustskydd. <BR> <BR> Stark autentisering inkluderar Azure Multi-Factor Authentication (MFA) med SMS-verifiering. Dataförlustskyddet säkerställer att känslig eller kritisk information inte hamnar utanför Microsoft Cloud. <BR><BR> Exempel på data på nivå 2 är ekonomisk och juridisk information, samt data vid forskning och utveckling av nya produkter. | Nivå 2 plus de högsta nivåerna för kryptering, autentisering och granskning. <BR> <BR>  Högsta krypteringsnivåerna för vilande data och data i molnet, kompatibla med regionala föreskrifter, kombinerade med MFA med smartkort, detaljerad granskning och aviseringar. <BR> <BR> Exempel på data på nivå 3 är personligt identifierbar information för kunder och partners, specifikationer för produktteknik samt tillverkarspecifika tillverkningstekniker.  |
||||

## <a name="contosos-information-policies"></a>Contosos informationsprinciper
Contosos informationsprinciper visas i nedanstående tabell.


| Value | Åtkomst | Datakvarhållning | Informationsskydd |
|:-------|:-----|:-----|:-----|
| Lågt affärsvärde (Nivå 1: Baslinje) | Tillåt åtkomst till alla  | 6 månader | Använd kryptering. |
| Medelhögt affärsvärde (Nivå 2: Känslig) | Tillåt åtkomst till Contoso-anställda, underleverantörer och partners <BR> <BR> Använd MFA, TLS (Transport Layer Security) och hantering av mobilprogram (MAM). | 2 år  | Använd hashvärden för dataintegritet.  |
| Högt affärsvärde (Nivå 3: Strikt reglerad) | Tillåt åtkomst till chefer och ledare inom teknik och tillverkning. <BR> <BR> Endast RMS (Rights Management System) med hanterade nätverksenheter.  | 7 år  | Använd digitala signaturer för oavvislighet.  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Contosos sökväg till informations skydd med Microsoft 365 för företag

Med contoso följer du stegen nedan för att förbereda Microsoft 365 för företag efter informations skydds kraven:

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

- [Principer för hanterad och ohanterad programåtkomst på enheter](../security/office-365-security/identity-access-policies.md)
- [Principer för Exchange Online-åtkomst](../security/office-365-security/secure-email-recommended-policies.md)
- [Principer för SharePoint-åtkomst](../security/office-365-security/sharepoint-file-access-policies.md)

Här är Contosos resulterande uppsättning med principer för informationsskydd.

![Principer för villkorlig åtkomst för enheter, Exchange Online och SharePoint](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso har även konfigurerat ytterligare principer för villkorlig åtkomst till identitet och inloggning. Se [Contoso Corporations identitet](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Med dessa principer ser du till att:

- Appar tillåts och de åtgärder som kan vidtas med dina organisationsdata definieras av appskyddsprinciper.
- Datorer och mobila enheter måste vara kompatibla.
- Exchange Online använder Office 365 Message Encryption (OME) för Exchange Online.
- I SharePoint används appframtvingade begränsningar.
- I SharePoint används åtkomstkontrollprinciper för att endast bevilja åtkomst via webbläsare och för att blockera åtkomst för ohanterade enheter.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contosos-data-levels"></a>Mappa Microsoft 365 för Enterprise-funktioner till organisationens data nivåer

I följande tabell mappas organisationens data nivåer till informations skydds funktioner i Microsoft 365 för företag.

| Graden | Microsoft 365-molntjänster | Windows 10 och  Microsoft 365-appar för företag | Säkerhet och efterlevnad |
|:-------|:-----|:-----|:-----|
| Nivå 1: Baslinje  | Principer för villkorlig åtkomst i SharePoint och Exchange Online <BR> Behörigheter på SharePoint-webbplatser | Känslighetsetiketter <BR> BitLocker <BR> Windows Information Protection | Principer för villkorlig åtkomst för enheter och hantering av mobilprogram |
| Nivå 2: Känslig | Nivå 1 plus: <BR> <BR> Markera som känsligt <BR> Microsoft 365-kvarhållningsetiketter på SharePoint-webbplatser <BR> Dataförlustskydd för SharePoint och Exchange Online <BR> Isolerade SharePoint-webbplatser  | Nivå 1 plus: <BR> <BR> Känslighetsetiketter för digitala tillgångar  | Nivå 1 |
| Nivå 3: Strikt reglerad | Nivå 2 plus: <BR><BR> BYOK-kryptering (Bring Your Own Key) och skydd av företagshemligheter <BR> Azure Key Vault för verksamhetskritiska affärsprogram som interagerar med Microsoft 365-tjänster | Nivå 2 | Nivå 1 |
|||||

Här är Contosos resulterande konfiguration av informationsskyddet.

![Contosos resulterande konfiguration av informationsskyddet](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Nästa steg

[Se](contoso-security-summary.md) hur contoso har använt säkerhetsfunktionerna i Microsoft 365 för företag för identitets-och åtkomst hantering, Hot skydd, informations skydd och säkerhets hantering.

## <a name="see-also"></a>Se även

[Säkerhetsöversikt](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)


