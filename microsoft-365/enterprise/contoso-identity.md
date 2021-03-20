---
title: ID för Contoso Corporation
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
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Hur Contoso använder sig av IDaaS (identitet som tjänst) och tillhandahåller molnbaserad autentisering för anställda och federerad autentisering för partner och kunder.
ms.openlocfilehash: accd60f6699e7ebf04963213128d1ca1ffc8f7fe
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911078"
---
# <a name="identity-for-the-contoso-corporation"></a>ID för Contoso Corporation

Microsoft tillhandahåller identitet som en tjänst (IDaaS) i sina molntjänster via Azure Active Directory (Azure AD). För att använda Microsoft 365 för företag var Contoso IDaaS-lösningen tvungen att använda deras lokala identitetsprovider och inkludera federerad autentisering med sina befintliga betrodda tredjepartsidentitetsproviders.

## <a name="the-contoso-active-directory-domain-services-forest"></a>Contoso Active Directory Domain Services-skogen

Contoso använder en enda AD DS-skog (Active Directory Domain Services) för contoso com med sju underdomäner, en för varje \. region i världen. Huvudkontoret, regionala navkontor och satellitkontor innehåller domänkontrollanter för lokal autentisering och verifiering.

Här är Contoso-skogen med regionala domäner för olika delar av världen som innehåller regionala nav.

![Contosos skogar och domäner över hela världen](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso beslutade att använda konton och grupper i Contoso com-skogen för autentisering och auktorisering för sina \. Microsoft 365-arbetsbelastningar och -tjänster.

## <a name="the-contoso-federated-authentication-infrastructure"></a>Infrastrukturen för contoso-federerad autentisering

Med contoso kan:

- Kunder kan använda sina Microsoft-, Facebook- eller Google Mail-konton för att logga in på företagets offentliga webbplats.
- Leverantörer och partner kan använda sina LinkedIn-, Salesforce- eller Google Mail-konton för att logga in på företagets partnerextranät.

Här är Contoso DMZ som innehåller en offentlig webbplats, ett extranät för partner och en uppsättning AD FS-servrar (Active Directory Federation Services). DMZ är anslutet till internet som innehåller kunder, partners och internettjänster.

![Contoso stöd för federerad autentisering för kunder och partner](../media/contoso-identity/contoso-identity-fig2.png)
 
AD FS-servrar i DMZ underlättar autentisering av kunduppgifter genom deras identitetsproviders för åtkomst till den offentliga webbplatsen och partnerautentiseringsuppgifter för åtkomst till partnerextranätet.

Contoso beslutade att behålla den här infrastrukturen och avsätta den till autentisering för kunder och partner. Contosos identitetsarkitekter undersöker konverteringen av den här infrastrukturen till Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations)- och [B2C](/azure/active-directory-b2c/solution-articles)-lösningar.

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Hybrididentitet med synkronisering av lösenordshash för molnbaserad autentisering

Contoso ville använda sin lokala AD DS-skog för autentisering på Microsoft 365-molnresurser. Den valde att använda synkronisering av lösenordshashar (PHS).

PHS synkroniserar den lokala AD DS-skogen med Azure AD-klientorganisationen för deras Microsoft 365 för företag-prenumeration, kopiering av användar- och gruppkonton och en hash-version av lösenord för användarkonton.

För att göra katalogsynkronisering distribuerade Contoso Azure AD Connect-verktyget på en server i sitt Paris-datacenter.

Här är servern som kör Azure AD Connect och avsöker Contoso AD DS-skogen efter ändringar och synkroniserar sedan dessa ändringar med Azure AD-klientorganisationen.

![Infrastrukturen för Contoso PHS-katalogsynkronisering](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Principer för villkorlig åtkomst för identitets- och enhetsåtkomst

Contoso skapade en uppsättning [principer för villkorlig åtkomst](../security/office-365-security/identity-access-policies.md) för Azure AD och Intune för tre skyddsnivåer:

- *Baslinjeskydd* gäller för alla användarkonton.
- *Känsliga* skydd gäller för ledningsgruppen och ledningsgruppen.
- *Starkt reglerade* skydd gäller för specifika användare på ekonomi-, juridik- och forskningsavdelningen som har tillgång till högreglerade data.

Här är den resulterande uppsättningen principer för Contoso-identitet och villkorsstyrd åtkomst på enheter.

![Contosos principer för villkorlig åtkomst för identitet och enheterer](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Nästa steg

Lär dig hur Contoso använder sin infrastruktur för Microsoft Endpoint Configuration Manager för att distribuera [och behålla aktuella Windows 10 Enterprise](contoso-win10.md) i organisationen.

## <a name="see-also"></a>Se även

[Identitets översikt för Microsoft 365](identity-roadmap-microsoft-365.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)