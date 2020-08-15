---
title: ID för Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Hur Contoso använder sig av IDaaS (identitet som tjänst) och tillhandahåller molnbaserad autentisering för anställda och federerad autentisering för partner och kunder.
ms.openlocfilehash: 795fb7dcb886c792c80d3bb251c9cb5774f1bf97
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686040"
---
# <a name="identity-for-the-contoso-corporation"></a>ID för Contoso Corporation

Microsoft tillhandahåller IDaaS (identitet som tjänst) i molnet med Azure Active Directory (Azure AD). För att kunna använda Microsoft 365 för Enterprise, måste Contosos IDaaS-lösning utnyttja sin lokala identitets leverantör och ändå inkludera federerad identitet med sina befintliga betrodda tredjepartsleverantörer.

## <a name="contosos-active-directory-domain-services-forest"></a>Contosos Active Directory Domain Services-skog

Contoso använder en enda AD DS-skog (Active Directory Domain Services) för contoso.com med sju underdomäner, en för varje region i världen. Huvudkontoret, regionala navkontor och satellitkontor innehåller domänkontrollanter för lokal autentisering och verifiering.

Här är Contoso-skogen med regionala domäner för de olika delar av världen som innehåller regionala nav.

![Contosos skogar och domäner över hela världen](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso ville använda konton och grupper i contoso.com-skogen för autentisering och auktorisering för sina Microsoft 365-arbetsbelastningar och -tjänster.

## <a name="contosos-federated-authentication-infrastructure"></a>Contosos infrastruktur för federerad autentisering

Med contoso kan:

- Kunder använda Microsoft, Facebook eller Google Mail för att logga in på sina offentliga webbplatser.
- Leverantörer och partner använda sina LinkedIn-, Salesforce- eller Google Mail-konton för att logga in på partnerextranätet.

Här är Contosos DMZ som innehåller en offentlig webbplats, ett partnerextranät och en uppsättning AD FS-servrar (Active Directory Federation Services). DMZ är ansluten till Internet som innehåller tjänster för kunder, partner och Internet.

![Contoso-support för federerad autentisering för kunder och partner](../media/contoso-identity/contoso-identity-fig2.png)
 
AD FS-servrar i DMZ underlättar autentiseringen av kundens identitetsuppgifter via identitetsleverantörerna för åtkomst till den offentliga webbplatsen och partneruppgifter för åtkomst till partnerextranätet.

Contoso bestämde sig för att behålla denna infrastruktur och dedikera den till kund- och partnerautentiseringar. Contosos identitetsarkitekter undersöker konverteringen av den här infrastrukturen till Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations)- och [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles)-lösningar.

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Hybrididentitet med synkronisering av lösenordshash för molnbaserad autentisering

Contoso ville använda sin lokala AD DS-skog för autentisering för Microsoft 365-molnresurser. De bestämde sig för synkronisering av lösenordshash (PHS).

PHS synkroniserar den lokala AD DS-skogen med Azure AD-innehavaren av sitt Microsoft 365 för företags prenumeration, kopierar användare och grupp konton och en hash-version av användar konto lösen ord. 

För att utföra en pågående katalogsynkronisering har Contoso distribuerat Azure AD Connect-verktyget på en server i sitt datacenter i Paris. 

Här är den server som kör Azure AD Connect-omröstningen för Contoso AD DS-skogen när det gäller ändringar och sedan synkroniserar ändringarna med Azure AD-klienten.

![Contosos infrastruktur för PHS-katalogsynkronisering](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Principer för villkorlig åtkomst för identitets- och enhetsåtkomst

Contoso skapade en uppsättning [principer för villkorlig åtkomst](identity-access-policies.md) för Azure AD och Intune för tre skyddsnivåer:

- **Grundskydd** gäller för alla användarkonton
- **Känsliga** skydd gäller cheferna och ledningen
- **Strikt reglerat** skydd med gäller för vissa användare på ekonomi-, juridik- och forskningsavdelningarna som har tillgång till data som är mycket strikta

Här är Contosos resulterande uppsättning principer för villkorsstyrd åtkomst av identitets- och enhetsprinciper.

![Contosos principer för villkorlig åtkomst för identitet och enheterer](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Nästa steg

[Ta reda på mer](contoso-win10.md) om hur Contoso använder sin Microsoft Endpoint Configuration Manager-infrastruktur för att distribuera och hålla Windows 10 Enterprise uppdaterat i organisationen.

## <a name="see-also"></a>Snabbreferens

[Identitets översikt för Microsoft 365](identity-roadmap-microsoft-365.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)
