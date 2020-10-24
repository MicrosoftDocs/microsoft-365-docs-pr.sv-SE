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
ms.openlocfilehash: dea0f53ef1c3fdc2ea32256303c6120c614c904d
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754658"
---
# <a name="identity-for-the-contoso-corporation"></a>ID för Contoso Corporation

Microsoft tillhandahåller identitets tjänst (IDaaS) över dess moln tjänster via Azure Active Directory (Azure AD). För att kunna använda Microsoft 365 för företag måste lösningen contoso IDaaS ha använt sin lokala identitets leverantör och inkludera federerad identitet med sina befintliga betrodda tredjepartsleverantörer.

## <a name="the-contoso-active-directory-domain-services-forest"></a>Contoso Active Directory Domain Services-skogen

Contoso använder en enda AD DS-skog (Active Directory Domain Services) för Contoso \. com med sju under domäner, en för varje region i världen. Huvudkontoret, regionala navkontor och satellitkontor innehåller domänkontrollanter för lokal autentisering och verifiering.

Här är contoso-skogen med regionala domäner för de olika delar av världen som innehåller regionala hubbar.

![Contosos skogar och domäner över hela världen](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso bestämde sig för att använda kontona och grupperna i Contoso \. com-skog för autentisering och godkännande för dess Microsoft 365-arbets belastning och tjänster.

## <a name="the-contoso-federated-authentication-infrastructure"></a>Infrastrukturen contoso federerad Infrastructure

Med contoso kan:

- Kunderna kan använda sina Microsoft-, Facebook-eller Google Mail-konton för att logga in på företagets offentliga webbplats.
- Leverantörer och partners för att kunna använda sina LinkedIn-, Salesforce-eller Google Mail-konton för att logga in på företagets extra nät för partner.

Här är contoso-DMZ som innehåller en offentlig webbplats, ett extra nät för partner och en uppsättning AD FS-servrar (Active Directory Federation Services). DMZ är ansluten till Internet som innehåller kunder, partners och Internet tjänster.

![Contoso-support för extern inloggningsautentisering för kunder och partners](../media/contoso-identity/contoso-identity-fig2.png)
 
AD FS-servrar i DMZ underlättar autentisering av kund uppgifter genom sin identitets leverantör för åtkomst till den offentliga webbplatsen och partner uppgifterna för åtkomst till partner nätet.

Contoso bestämde sig för att behålla denna infrastruktur och tilldela den till kund-och partner-inloggningsautentisering. Contosos identitetsarkitekter undersöker konverteringen av den här infrastrukturen till Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations)- och [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles)-lösningar.

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Hybrididentitet med synkronisering av lösenordshash för molnbaserad autentisering

Contoso ville använda sin lokala AD DS-skog för att verifiera till Microsoft 365 Cloud Resources. Det beslutade att använda Lösenordssynkronisering (PHS).

PHS synkroniserar den lokala AD DS-skogen med Azure AD-innehavaren av sitt Microsoft 365 för företags prenumeration, kopierar användare och grupp konton och en hash-version av användar konto lösen ord.

Om du vill göra en katalog-synkronisering distribuerar contoso verktyget Azure AD Connect på en server i Paris data centret.

Här är den server som kör Azure AD Connect-avsökning av contoso AD DS-skogen för ändringar och sedan synkroniserar dessa ändringar med Azure AD-klienten.

![Infrastrukturen för Contoso PHS Directory-synkronisering](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Principer för villkorlig åtkomst för identitets- och enhetsåtkomst

Contoso skapade en uppsättning [principer för villkorlig åtkomst](identity-access-policies.md) för Azure AD och Intune för tre skyddsnivåer:

- *Grundläggande* skydd gäller för alla användar konton.
- *Känsliga* skydd gäller för chefens ledarskap och direktör.
- *Starkt reglerade* skydd gäller för specifika användare i ekonomi-, juridik-och forsknings avdelningar som har till gång till högreglerade data.

Här är den resulterande uppsättningen med principer för villkorsstyrd åtkomst via contoso och Device.

![Contosos principer för villkorlig åtkomst för identitet och enheterer](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Nästa steg

Lär dig hur Contoso använder sin Microsoft Endpoint Configuration Manager-infrastruktur för att [distribuera och hålla nuvarande Windows 10-företag](contoso-win10.md) i sin organisation.

## <a name="see-also"></a>Snabbreferens

[Identitets översikt för Microsoft 365](identity-roadmap-microsoft-365.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)
