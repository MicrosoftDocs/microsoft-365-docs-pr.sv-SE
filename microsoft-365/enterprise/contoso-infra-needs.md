---
title: Contosos IT-infrastruktur och affärsbehov
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå den grundläggande strukturen i Contosos lokala IT-infrastruktur och hur företagets affärsbehov uppfylls av Microsoft 365 för företag.
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558412"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a>Contosos IT-infrastruktur och affärsbehov

Contoso går över från en lokal, centraliserad IT-infrastruktur till en molnomfattande installation med molnbaserade arbetsbelastningar och program för personlig produktivitet.

## <a name="existing-contoso-it-infrastructure"></a>Befintlig IT-infrastruktur i Contoso

Contoso använder främst centraliserad IT-infrastruktur med datacenter i huvudkontoret i Paris.

Här är huvudkontoret med programdatacenter, en DMZ och internet.

![Befintlig IT-infrastruktur i Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

Det lokala programdatacentret är värd för: 

- Anpassade affärsprogram som använder SQL Server och andra Linux-databaser.
- En uppsättning äldre SharePoint-servrar.
- Servar på organisations- och teamnivå för fillagring.

Dessutom har varje regionalt navkontor stöd för en uppsättning servrar med en liknande uppsättning program. Dessa servrar styrs av regionala IT-avdelningar.

Sökbarheten i alla program och data i sådana separata flerspråkiga datacenter fortsätter att vara en utmaning.

I Contoso huvudkontor DMZ tillhandahåller olika uppsättningar av servrar:

- Värd för den offentliga Contoso-webbplatsen, där kunderna kan beställa produkter, delar, varor och tjänster.
- Värd för Contoso-partners extranät för kommunikation och samarbete mellan partner.
- VPN-baserad (virtuellt privat nätverk) fjärråtkomst till Contosos intranät och webbproxyn för medarbetare på Paris-huvudkontoret.

## <a name="contoso-business-needs"></a>Affärsbehov i Contoso

Contosos affärsbehov indelar i fem huvudkategorier:

**Produktivitet**

- Förenkla samarbetet

  Ersätt e-post- och filresursbaserat samarbete med en onlinemodell som tillåter ändringar i realtid i dokument, enklare onlinemöten och tagna konversationstrådar.
- Förbättra produktiviteten för distans- och mobila arbetare

  När många anställda arbetar hemifrån eller i fältet ersätter du den flaskhalsade VPN-lösningen med direktåtkomst till Contosos data och resurser i molnet.
- Öka kreativiteten och innovationen

  Dra nytta av de senaste utvecklingsmetoderna för visuell inlärning och idé,er t. ex. pennanteckningar och 3D-visualisering.

**Säkerhet**

- Identitets- och åtkomsthantering

  Använda multifaktorer och andra typer av autentisering och skydda autentiseringsuppgifter för användar- och administratörskonto.

- Skydd mot hot

  Skydda mot externa säkerhetshot, inklusive e-post och operativsystem som är baserade på skadlig programvara.

- Informationsskydd

  Lås åtkomst till och kryptera digitala till gångar med höga värden, t. ex. kunddata, specifikationer för utformningen och tillverkningen samt information om medarbetare.

- Säkerhetshantering

  Övervaka säkerheten och identifiera och reagera på hot i realtid.

**Fjärr- och mobilåtkomst för affärspartner**

- Förbättra säkerheten för fjärranslutna och mobila medarbetare

  Implementera få din egen enhet (BYOD) och företagsägd enhetshantering för att säkerställa säker åtkomst, korrekt programbeteende och företagsdataskydd.

- Minska infrastrukturen för fjärråtkomst för medarbetare

  Minska kostnader för underhåll och support och förbättra prestandan för lösningen för fjärråtkomst genom att flytta resurser som ofta används till molnet.

- Bättre anslutning och lägre overhead för B2B-transaktioner (företag till företag)

  Ersätt ett föråldrings och dyr partnerextranät med en molnbaserad lösning som använder federerad autentisering.

**Efterlevnad**

- Följa regionala efterlevnadskrav

  Säkerställa efterlevnad av bransch- och regionala bestämmelser för datalagring, kryptering, datasekretess och bestämmelser om personliga data, t.ex. dataskyddsförordningen (GDPR) för Europeiska unionen.

**Hantering**

- Lägre IT-kostnader vid hantering av programvara som körs på klientdatorer och -enheter

  Automatisera installationen av uppdateringar Windows operativsystem och Microsoft 365-appar för företag i organisationen.

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>Mappa Contosos affärsbehov till Microsoft 365 för företag

Contosos IT-avdelning har fastställt följande mappning av affärsbehoven Microsoft 365 E5 funktioner före distributionen:


| Kategori | Affärsknr | Microsoft 365 för företagsprodukter eller -funktioner |
|:-------|:-----|:-----|
| Produktivitet |  |  |
|  | Förenkla samarbetet | Microsoft Teams, SharePoint, OneDrive |
|  | Förbättra produktiviteten för distans- och mobila arbetare | Microsoft 365-arbetsbelastningar och molnbaserade data |
|  | Öka kreativiteten och innovationen | Windows Ink, Cortana at Work, PowerPoint |
| Säkerhet |  |  |
|  | Identitets- och åtkomsthantering | Dedikerade globala administratörskonton med Azure AD Multi-Factor Authentication (MFA) och Azure AD Privileged Identity Management (PIM) <BR> MFA för alla användarkonton <BR> Med villkorsstyrd åtkomst <BR> Windows Hello <BR> Windows Credential Guard |
|  | Skydd mot hot | Advanced Threat Analytics <BR> Windows Defender <BR> Defender förr Office 365 <BR> Microsoft Defender för Office 365 <BR> Microsoft 365 undersökning av hot och svar <BR> |
|  | Informationsskydd | Azure Information Protection <BR> Skydd mot dataförlust (DLP) <BR> Windows Information Protection (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | Säkerhetshantering | Azure Defender  <BR> Windows Defender Säkerhetscenter |
| Fjärr- och mobilåtkomst för affärspartner |  |  |
|  | Högre säkerhet för arbetare och distansarbetare | Microsoft Intune |
|  | Minska infrastrukturen för fjärråtkomst för medarbetare | Microsoft 365-arbetsbelastningar och molnbaserade data |
|  | Förbättra anslutningen och lägre overhead för B2B-transaktioner | Federerad autentisering och molnbaserade resurser |
| Efterlevnad |  |  |
|  | Följa regionala efterlevnadskrav | GDPR-funktioner i Microsoft 365 |
| Hantering |  |  |
|  | Lägre IT-kostnader vid installation av klientuppdateringar | Windows 10 Enterprise-uppdateringar <BR> Microsoft 365-applikationer för företag uppdateringar |
||||

## <a name="next-step"></a>Nästa steg

Läs mer om det lokala Contoso [Corporation-nätverket](contoso-networking.md) och hur det optimerades för åtkomst och svarstid till Microsoft 365 molnbaserade resurser.

## <a name="see-also"></a>Se även

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)
