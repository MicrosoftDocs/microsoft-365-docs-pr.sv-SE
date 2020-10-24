---
title: Klient organisations översikt för Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Översikten för konfiguration av klient organisationer för Microsoft 365.
ms.openlocfilehash: 038d9b0d94b84d184f0d9d9b250d0ee4d2c19de9
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753972"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Klient organisations översikt för Microsoft 365

Din Microsoft 365-klient är den uppsättning tjänster som är tilldelade till din organisation. Vanligt vis är denna klient organisation kopplad till ett eller flera av dina offentliga DNS-domännamn och fungerar som en central och isolerad behållare för olika prenumerationer och de licenser som du tilldelar användar konton. Mer information finns i [prenumerationer, licenser, konton och innehavare för Microsofts moln tjänster](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).

När du skapar en Microsoft 365-klient organisation tilldelar du den till en specifik geografisk plats. Du kan också ha en innehavare med flera geografiska platser och flytta klient organisationen från en plats till en annan.

För att förbereda klient organisationen för användare, grupper, licenser och Cloud-appar är det viktigt att noggrant planera och köra klient konfigurationen.

## <a name="set-up-your-microsoft-365-tenant"></a>Konfigurera din Microsoft 365-klient organisation

När du har kontrollerat att nätverket är optimerat för åtkomst till Microsoft 365 för både lokala och fjärranställda, kan dina kommande stora uppgifter planera för och sedan konfigurera din Microsoft 365-klient för DNS Domain Names, common Services och för den identitets infrastrukturen som stöder säker inloggning.

### <a name="plan"></a>Planera

Så här planerar du för klient implementering:

- [Förstå abonnemang, licenser och Azure Active Directory (Azure AD)-klient organisationer](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Förstå hur du använder SSL-certifikat från tredje part](plan-for-third-party-ssl-certificates.md)
- [Förstå hur en Microsoft 365-klient är integrerad med Azure AD-tjänster](integrated-apps-and-azure-ads.md)
- [Planera stöd för klient program](microsoft-365-client-support-certificate-based-authentication.md)
- [Bestämma hur hybrid modern](hybrid-modern-auth-overview.md)
- [Planera för Office 2007-och Office 2010-uppgraderingar](plan-upgrade-previous-versions-office.md)
- [Förstå klient isolering](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>Distribuera

Så här distribuerar du klient organisationen: 

- Lägga till [DNS-domäner](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) för din organisation.
- Använd [installations guiderna i administrations centret för Microsoft 365](setup-guides-for-microsoft-365.md).
- Bygg upp din [identitets infrastruktur](identity-roadmap-microsoft-365.md) och [skydda dina inloggnings program](microsoft-365-secure-sign-in.md).

### <a name="move-a-tenants-geographic-locations"></a>Flytta en innehavares geografiska platser

Microsoft fortsätter att öppna nya data Center geografiska platser (geos) för Microsoft 365-tjänster. De här nya data Center geos lägger till kapacitet och kan beräkna resurser för att stödja kund behov och förbruknings tillväxt. Dessutom ger det nya data Center geos in-Geo data de för grundläggande kunddata.

Mer information finns i [Flytta grundläggande data till nya Microsoft 365 Data Center-geos](moving-data-to-new-datacenter-geos.md).


## <a name="deploy-microsoft-365-multi-geo"></a>Distribuera Microsoft 365 multi-geo

Med Microsoft 365 multi-geo kan din organisation utöka sin Microsoft 365-närvaro till flera geografiska regioner och/eller länder inom din befintliga klient organisation.

Mer information finns i [Microsoft 365 multi-geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenant"></a>Hantera flera Microsoft 365-klient organisationer 

Trots att en enda klient organisation för din oganization är idealisk kan du vara en av många organisationer som har flera innehavare. Det kan vara bra att inkludera fusioner och förvärv, du vill ha en administrativ isolering eller ett avcentraliserat.

Om du har flera Microsoft 365-klient organisationer kan du läsa de här artiklarna om du vill ha mer information om:

- [Samarbete mellan klientorganisationer](microsoft-365-inter-tenant-collaboration.md)
- [Migrering av postlådor mellan klientorganisationer](cross-tenant-mailbox-migration.md)
- [Migrering mellan klientorganisationer](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Nästa steg

Starta klient organisations planeringen med [abonnemang, licenser, konton och innehavare](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).
