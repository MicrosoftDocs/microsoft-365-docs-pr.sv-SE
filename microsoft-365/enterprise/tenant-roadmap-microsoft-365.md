---
title: Klient organisations översikt för Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Översikten för konfiguration av klient organisationer för Microsoft 365.
ms.openlocfilehash: 0f1fa91bb81fd6cc87820f2b2d48e00e1b75a0c4
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446013"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Klient organisations översikt för Microsoft 365

Din Microsoft 365-klient är den uppsättning tjänster som är tilldelade till din organisation. Den här innehavaren är normalt kopplad till ett eller flera av dina DNS-domännamn och fungerar som en central behållare för olika prenumerationer och de licenser som du tilldelar användar konton.

När du skapar en Microsoft 365-klient organisation tilldelar du den till en specifik geografisk plats. Du kan också ha en innehavare med flera geografiska platser och flytta klient organisationen från en plats till en annan.

För att få klient organisationen redo för de grundläggande tjänsterna i nätverk och identitet är det viktigt att noggrant planera och köra klient konfigurationen.

## <a name="plan"></a>Planera

Så här planerar du för klient implementering:

- [Förstå abonnemang, licenser och Azure Active Directory (Azure AD)-klient organisationer](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Förstå hur du använder SSL-certifikat från tredje part](plan-for-third-party-ssl-certificates.md)
- [Förstå hur en Microsoft 365-klient är integrerad med Azure AD-tjänster](integrated-apps-and-azure-ads.md)
- [Planera stöd för klient program](microsoft-365-client-support-certificate-based-authentication.md)
- [Bestämma hur hybrid modern](hybrid-modern-auth-overview.md)
- [Planera för Office 2007-och Office 2010-uppgraderingar](plan-upgrade-previous-versions-office.md)
- [Förstå klient isolering](microsoft-365-tenant-isolation-overview.md)
- [Få information om Microsoft 365-tjänsten](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a>Distribuera

Om du vill distribuera din klient organisation [lägger du till DNS-domänerna](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) för organisationen och använder [installations guiderna i Microsoft 365 Admin Center](setup-guides-for-microsoft-365.md).

## <a name="tenants-with-multiple-geographic-locations"></a>Klient organisationer med flera geografiska platser

Med Microsoft 365 multi-geo kan din organisation utöka sin Microsoft 365-närvaro till flera geografiska regioner och/eller länder inom din befintliga klient organisation.

Information om Microsoft 365 multi-geo, inklusive hur du planerar, konfigurerar och administrerar den, finns [här](microsoft-365-multi-geo.md).

## <a name="move-a-tenants-geographic-locations"></a>Flytta en innehavares geografiska platser

Microsoft fortsätter att öppna nya data Center geografiska platser (geos) för Microsoft 365-tjänster. De här nya data Center geos lägger till kapacitet och kan beräkna resurser för att stödja kund behov och förbruknings tillväxt. Dessutom ger det nya data Center geos in-Geo data de för grundläggande kunddata.

[Börja här](moving-data-to-new-datacenter-geos.md)om du vill ha information om Microsoft 365 Data Center geo, inklusive hur du kan begära en Geo data flytt.

## <a name="next-step"></a>Nästa steg

Starta klient organisations planeringen med [abonnemang, licenser, konton och innehavare](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).

