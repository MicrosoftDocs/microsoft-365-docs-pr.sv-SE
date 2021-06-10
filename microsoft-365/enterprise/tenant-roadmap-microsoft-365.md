---
title: Klientorganisationsöversikt för Microsoft 365
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
description: Översikt över hur du organisationsklienter ska Microsoft 365.
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909460"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Klientorganisationsöversikt för Microsoft 365

Din Microsoft 365 är den uppsättning tjänster som tilldelats din organisation. Den här klientorganisationen är vanligtvis kopplad till ett eller flera offentliga DNS-domännamn och fungerar som en central och isolerad behållare för olika prenumerationer och de licenser inom dem som du tilldelar användarkonton. Mer information finns i [Prenumerationer, licenser, konton och klientorganisation för Microsofts molntjänster.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)

När du skapar en Microsoft 365 tilldelar du den till en specifik geografisk plats. Du kan också ha en klientorganisation med flera geografiska platser och flytta klientorganisationen från en plats till en annan.

För att klientorganisationen ska bli redo för användare, grupper, licenser och molnappar är det viktigt att planera och genomföra konfigurationen av klientorganisationen noggrant.

## <a name="set-up-your-microsoft-365-tenant"></a>Konfigurera din Microsoft 365 klientorganisation

När du har säkerställt att ditt nätverk är optimerat för åtkomst till Microsoft 365 för både lokala medarbetare och fjärranslutna medarbetare planerar du och sedan konfigurerar din Microsoft 365-klientorganisation för DNS-domännamn, vanliga tjänster och för den identitetsinfrastruktur som stöder säker användarregistrering.

### <a name="plan"></a>Planera

Så här planerar du implementering av klientorganisationen:

- [Förstå prenumerationer, licenser och Azure Active Directory -klienter (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Förstå hur du använder SSL-certifikat från tredje part](plan-for-third-party-ssl-certificates.md)
- [Förstå hur en klientorganisation Microsoft 365 integreras med Azure AD-tjänster](integrated-apps-and-azure-ads.md)
- [Planera för support för klientprogram](microsoft-365-client-support-certificate-based-authentication.md)
- [Avgöra hur du använder modern hybridautentisering](hybrid-modern-auth-overview.md)
- [Planera för Office 2007 och Office 2010](plan-upgrade-previous-versions-office.md)
- [Förstå innehavarisolering](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>Distribuera

Så här distribuerar du klientorganisationen: 

- Lägg till [DNS-domänerna](../admin/setup/add-domain.md) för din organisation.
- Använd [installationsguiderna i Microsoft 365 administrationscenter.](setup-guides-for-microsoft-365.md)
- Bygg ut din [identitetsinfrastruktur](identity-roadmap-microsoft-365.md) [och säkra användarnas inloggningar.](microsoft-365-secure-sign-in.md)

### <a name="move-a-tenants-geographic-locations"></a>Flytta en klientorganisations geografiska platser

Microsoft fortsätter att öppna nya geografiska platser i datacentret (geos) Microsoft 365 tjänster. Dessa nya datacenter geos lägger till kapacitet och beräknar resurser för att stödja kundbehov och användningstillväxt. Det nya datacentret geos erbjuder dessutom geodata som används för basdata.

Mer information finns i Flytta [basdata till det nya Microsoft 365 datacentrets geos.](moving-data-to-new-datacenter-geos.md)


## <a name="deploy-microsoft-365-multi-geo"></a>Distribuera Microsoft 365 Multi-Geo

Med Microsoft 365 Multi-Geo kan organisationen utöka sin närvaro Microsoft 365 till flera geografiska regioner och/eller länder inom din befintliga klientorganisation.

Mer information finns i [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenants"></a>Hantera flera Microsoft 365 klientorganisation 

Även om det är bra att ha en enda klientorganisation för din organisation, kan du vara en av många organisationer som har flera klientorganisationer. Orsaker kan vara sammanslagningar och förvärv, du vill ha administrativ avgränsning eller om du har en decentraliserad IT.

Om du har flera Microsoft 365 klientorganisation finns mer information i följande artiklar:

- [Samarbete mellan klientorganisationer](microsoft-365-inter-tenant-collaboration.md)
- [Migrering av postlådor mellan klientorganisationer](cross-tenant-mailbox-migration.md)
- [Migrering mellan klientorganisationer](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Nästa steg

Börja planera för klientorganisationen [med prenumerationer, licenser, konton och klientorganisation.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)