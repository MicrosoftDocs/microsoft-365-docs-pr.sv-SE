---
title: Skype IT-infrastruktur och företags behov
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
description: Förstå den grundläggande strukturen i den lokala IT-infrastrukturen för Contoso och hur företagets företags behov uppfylls av Microsoft 365 för företag.
ms.openlocfilehash: 767374097efa116f116cff6f6ddf96d075eb71ed
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754592"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a>Skype IT-infrastruktur och företags behov

Contoso övergår från en lokal, centraliserad IT-infrastruktur till en molnbaserade konfiguration som innehåller molnbaserade privat arbets belastning och applikationer.

## <a name="existing-contoso-it-infrastructure"></a>Befintlig infrastruktur för Contoso-IT

Contoso använder främst centraliserad IT-infrastruktur med datacenter i huvudkontoret i Paris.

Här är huvud kontoret för program Data Center, en DMZ och Internet.

![Befintlig infrastruktur för Contoso-IT](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

Det lokala programdatacentret är värd för: 

- Anpassade affärs program som använder SQL Server och andra Linux-databaser.
- En uppsättning äldre SharePoint-servrar.
- Servar på organisations- och teamnivå för fillagring.

Dessutom har varje regionalt navkontor stöd för en uppsättning servrar med en liknande uppsättning program. Dessa servrar styrs av regionala IT-avdelningar.

Sökbarheten i alla program och data i sådana separata flerspråkiga datacenter fortsätter att vara en utmaning.

I DMZ med contoso Headquarters kan du göra följande:

- Värd för den offentliga contoso-webbplatsen, där kunder kan beställa produkter, delar, tillbehör och tjänster.
- Värd för Contoso-partners extranät för kommunikation och samarbete mellan partner.
- VPN-baserad (virtuellt privat nätverk) fjärråtkomst till Contosos intranät och webbproxyn för medarbetare på Paris-huvudkontoret.

## <a name="contoso-business-needs"></a>Contoso företags behov

Contoso företags behov tillhör fem kategorier:

**Produktivitet**

- Förenkla samarbetet

  Byt ut samarbete via e-post och fildelning med en online-modell som möjliggör ändringar i real tid i dokument, enklare onlinemöten och fångade konversations trådar.
- Förbättra produktiviteten för distans- och mobila arbetare

  Med många anställda som arbetar hemifrån eller i fältet ersätter du den Flask halsbaserade VPN-lösningen med åtkomst till contoso-data och resurser i molnet.
- Öka kreativiteten och innovationen

  Dra nytta av de senaste utvecklingsmetoderna för visuell inlärning och idé,er t. ex. pennanteckningar och 3D-visualisering.

**Säkerhet**

- Identitets- och åtkomsthantering

  Tvinga högfaktaare och andra former av autentisering samt skydda användar-och administratörs konto uppgifter.

- Skydd mot hot

  Skydda mot externa säkerhetshot, inklusive e-post och operativsystem som är baserade på skadlig programvara.

- Informationsskydd

  Lås åtkomst till och kryptera digitala till gångar med höga värden, t. ex. kunddata, specifikationer för utformningen och tillverkningen samt information om medarbetare.

- Säkerhetshantering

  Övervaka säkerhets Posture och upptäcka och svara på hot i real tid.

**Fjärr- och mobilåtkomst för affärspartner**

- Förbättra säkerheten för fjärranslutna och mobila användare

  Implementera skaffa din egen enhet (BYOD) och företagets enhets hantering för att säkerställa skyddad åtkomst, korrekta program beteenden och företagets data skydd.

- Minska infrastrukturen för fjärråtkomst för medarbetare

  Reducera underhålls-och support kostnader och förbättra prestandan för fjärråtkomst genom att flytta vanliga resurser till molnet.

- Ge bättre anslutning och lägre omkostnader för B2B-transaktioner (Business-to-susiness)

  Ersätt en ålders fördelning och dyra partner nät med en molnbaserad lösning som använder federerad användning.

**Efterlevnad**

- Följa regionala efterlevnadskrav

  Säkerställa efterlevnad av bransch-och regionala regler för data lagring, kryptering, data integritet och personliga data regler, till exempel GDPR (General Data Protection reglemente) för Europa unionen.

**Hantering**

- Minska IT-kostnaderna för att hantera program vara som körs på klient datorer och enheter

  Automatisera installationen av uppdateringar av Windows operativ system och Microsoft 365-appar för företag i hela organisationen.

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>Mappa contoso företags behov till Microsoft 365 för företag

Contosos IT-avdelning har fastställt följande mappning av företags behov till Microsoft 365 E5-funktioner innan distribution:


| Kategori | Affärsbehov | Microsoft 365 för företags produkter eller funktioner |
|:-------|:-----|:-----|
| Produktivitet |  |  |
|  | Förenkla samarbetet | Microsoft Teams, SharePoint, OneDrive |
|  | Förbättra produktiviteten för distans- och mobila arbetare | Microsoft 365-arbetsbelastningar och molnbaserade data |
|  | Öka kreativiteten och innovationen | Windows Ink, Cortana at Work, PowerPoint |
| Säkerhet |  |  |
|  | Identitets- och åtkomsthantering | Dedikerade globala administratörs konton med Azure Multi-Factority (MFA) och Azure Active Directory-privilegierad identitets hantering (PIM) <BR> MFA för alla användarkonton <BR> Med villkorsstyrd åtkomst <BR> Windows Hello <BR> Windows Credential Guard |
|  | Skydd mot hot | Advanced Threat Analytics <BR> Windows Defender <BR> Avancerat skydd <BR> Office 365 Avancerat skydd <BR> Microsoft 365 hot undersökningar och svar <BR> |
|  | Informationsskydd | Azure Information Protection <BR> Skydd mot dataförlust (DLP) <BR> Windows Information Protection (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | Säkerhetshantering | Azure Security Center  <BR> Windows Defender Säkerhetscenter |
| Fjärr- och mobilåtkomst för affärspartner |  |  |
|  | Högre säkerhet för arbetare och distansarbetare | Microsoft Intune |
|  | Minska infrastrukturen för fjärråtkomst för medarbetare | Microsoft 365-arbetsbelastningar och molnbaserade data |
|  | Förbättra anslutningen och lägre omkostnader för B2B-transaktioner | Federerad autentisering och molnbaserade resurser |
| Efterlevnad |  |  |
|  | Följa regionala efterlevnadskrav | GDPR funktioner i Microsoft 365 |
| Hantering |  |  |
|  | Minska IT-omkostnader för installation av klient uppdateringar | Windows 10 Enterprise-uppdateringar <BR> Microsoft 365-applikationer för företag uppdateringar |
||||

## <a name="next-step"></a>Nästa steg

Lär dig mer om det [lokala nätverket](contoso-networking.md) Contoso Corporation och hur det optimerades för åtkomst och svars tider till Microsoft 365-molnbaserade resurser.

## <a name="see-also"></a>Se även

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)
