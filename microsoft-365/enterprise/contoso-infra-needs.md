---
title: Contosos IT-infrastruktur och affärsbehov
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå den grundläggande strukturen i Contosos lokala IT-infrastruktur och hur företagets behov uppfylldes av Microsoft 365 Enterprise.
ms.openlocfilehash: 3cee0f3e6cd20b0d93038595cdab9270c8eb30aa
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810026"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a>Contosos IT-infrastruktur och affärsbehov

Contoso har övergått från en lokal, centraliserad IT-infrastruktur till molnbaserade personliga arbetsbelastningar och program.

## <a name="contosos-existing-it-infrastructure"></a>Contosos befintliga IT-infrastruktur

Contoso använder främst centraliserad IT-infrastruktur med datacenter i huvudkontoret i Paris.

Bild 1 visar ett huvudkontor med datacenter, en DMZ och Internet.

![Contosos befintliga IT-infrastruktur](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

**Bild 1: Contosos befintliga IT-infrastruktur**
 
Det lokala programdatacentret är värd för: 

- Egna affärsprogram som använder SQL Server- och andra Linux-databaser.
- En uppsättning äldre SharePoint-servrar.
- Servar på organisations- och teamnivå för fillagring.

Dessutom har varje regionalt navkontor stöd för en uppsättning servrar med en liknande uppsättning program. Dessa servrar styrs av regionala IT-avdelningar.

Sökbarheten i alla program och data i sådana separata flerspråkiga datacenter fortsätter att vara en utmaning.

I Contosos huvudkvarters DMZ kan du använda olika uppsättningar av servrar:

- Värd för den offentliga Contoso-webbplatsen, där kunderna kan beställa produkter, delar, materiel och tjänster.
- Värd för Contoso-partners extranät för kommunikation och samarbete mellan partner.
- VPN-baserad (virtuellt privat nätverk) fjärråtkomst till Contosos intranät och webbproxyn för medarbetare på Paris-huvudkontoret.

## <a name="contosos-business-needs"></a>Contosos affärsbehov

Organisationens affärsbehov delas in i fem huvudkategorier.

Produktivitet:

- Förenkla samarbetet

  Ersätt e-post och dela dokument med hjälp av en onlinemodell som möjliggör ändringar i realtid i dokument, enklare onlinemöten och hämtade konversationstrådar.
- Förbättra produktiviteten för distans- och mobila arbetare

  Med många medarbetare som arbetar från hemmet eller ute på fältet ersätter du VPN-lösningens flaskhals med omfattande åtkomst till Contoso-data och -resurser i molnet.
- Öka kreativiteten och innovationen

  Dra nytta av de senaste utvecklingsmetoderna för visuell inlärning och idé,er t. ex. pennanteckningar och 3D-visualisering.

Säkerhet:

- Identitets- och åtkomsthantering

  Använd multifaktorautentisering och andra typer av autentisering och skydda användar- och administratörskontouppgifter.

- Skydd mot hot

  Skydda mot externa säkerhetshot, inklusive e-post och operativsystem som är baserade på skadlig programvara.

- Informationsskydd

  Lås åtkomst till och kryptera digitala till gångar med höga värden, t. ex. kunddata, specifikationer för utformningen och tillverkningen samt information om medarbetare.

- Säkerhetshantering

  Övervaka säkerheten så att du kan upptäcka och reagera på hot i realtid.

Fjärr- och mobilåtkomst för affärspartner:

- Högre säkerhet för arbetare och distansarbetare

  Upprätta BYOD (Bring Your Own Device) och företagsägd enhetshantering för att säkerställa skyddad åtkomst, korrekta programbeteenden och skydd av företagsdata.

- Minska infrastrukturen för fjärråtkomst för medarbetare

  Minska kostnader för underhåll och support och förbättra prestanda för lösningen för fjärråtkomst genom att flytta vanligt förekommande resurser till molnet.

- Ge bättre anslutningsbarhet och lägre kostnad för B2B-transaktioner (företag till företag)

  Ersätt föråldrade och dyra partnerextranät med en molnbaserad lösning som använder federerad autentisering.

Efterlevnad:

- Följa regionala efterlevnadskrav

  Bli och fortsätt att vara kompatibla med branscher och regionala föreskrifter för datalagring, kryptering, datasekretess och föreskrifter för personliga data, t.ex. GDPR (allmän dataskyddsförordning) för EU.

Hantering:

- Minska IT-omkostnaderna för hantering av programvara som körs på klientdatorer och -enheter

  Automatisera installationen av uppdateringar av Windows-operativsystemet och Microsoft Office ProPlus i hela organisationen.

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a>Koppla Contosos affärsbehov till Microsoft 365 Enterprise

Contosos IT-avdelning fastställde följande affärsbehov för Microsoft 365 E5 före distributionen:

||||
|:-------|:-----|:-----|
| **Kategori** | **Affärsbehov** | **Microsoft 365 Enterprise-produkter eller -funktioner** |
| Produktivitet |  |  |
|  | Förenkla samarbetet | Microsoft Teams, SharePoint, OneDrive |
|  | Förbättra produktiviteten för distans- och mobila arbetare | Microsoft 365-arbetsbelastningar och molnbaserade data |
|  | Öka kreativiteten och innovationen | Windows Ink, Cortana at Work, PowerPoint |
| Säkerhet |  |  |
|  | Identitets- och åtkomsthantering | Dedikerade globala administratörskonton med Azure Multi-Factor Authentication (MFA) och Azure AD Privileged Identity Management (PIM) <BR> MFA för alla användarkonton <BR> Med villkorsstyrd åtkomst <BR> Windows Hello <BR> Windows Credential Guard |
|  | Skydd mot hot | Advanced Threat Analytics <BR> Windows Defender <BR> Avancerat skydd <BR> Office 365 Avancerat skydd <BR> Office 365 undersökning av hot och svar <BR> |
|  | Informationsskydd | Azure Information Protection <BR> Dataförlustskydd i Office 365 (DLP) <BR> Windows Information Protection (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | Säkerhetshantering | Azure Security Center  <BR> Windows Defender Säkerhetscenter |
| Fjärr- och mobilåtkomst för affärspartner |  |  |
|  | Högre säkerhet för arbetare och distansarbetare | Microsoft Intune |
|  | Minska infrastrukturen för fjärråtkomst för medarbetare | Microsoft 365-arbetsbelastningar och molnbaserade data |
|  | Ge bättre anslutningsbarhet och lägre kostnad för B2B-transaktioner | Federerad autentisering och molnbaserade resurser |
| Efterlevnad |  |  |
|  | Följa regionala efterlevnadskrav | GDPR-funktioner i Office 365 |
| Hantering |  |  |
|  | Minska IT-omkostnaderna för installation av klientuppdateringar | Distributionsringar <BR> Windows 10 Enterprise-uppdateringar <BR> Office 365 ProPlus-uppdateringar |
||||

## <a name="next-step"></a>Nästa steg

[Läs](contoso-networking.md) om Contoso Corporations lokala nätverk och hur det optimerades för åtkomst och svarstider för molnbaserade resurser i Microsoft 365.

## <a name="see-also"></a>Se även

[Distributionsguide](deploy-microsoft-365-enterprise.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)
