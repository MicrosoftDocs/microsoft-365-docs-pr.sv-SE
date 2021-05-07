---
title: Skydda användar- och enhetsåtkomst
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Lär dig hur du skyddar användare och enheters åtkomst Microsoft 365 data och tjänster och skyddar mot dataförlust.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ff7bd2ff8b4b333eb30a6cc82797a8968941e0b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "52162337"
---
# <a name="protect-user-and-device-access"></a>Skydda användar- och enhetsåtkomst

Att skydda åtkomsten Microsoft 365 data och tjänster är avgörande för att försvara sig mot cyberattacker och bevaka dataförlust. Samma skydd kan tillämpas på andra SaaS-program i din miljö och även på lokala program som publiceras med Azure Active Directory Programproxy.
  
## <a name="step-1-review-recommendations"></a>Steg 1: Granska rekommendationer

Rekommenderade funktioner för att skydda identiteter och enheter som kommer åt Office 365, andra SaaS-tjänster och lokala program som publicerats med Azure AD-programproxy.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656)  |  [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657)  |  [Fler språk](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>Steg 2: Skydda administratörskonton och åtkomst
De administratörskonton du använder för att administrera Microsoft 365-miljön inkluderar förhöjda behörigheter. Det här är värdefulla mål för hackare och cyberattacker. 

Börja med att bara använda administratörskonton för administration. Administratörer bör ha ett separat användarkonto för normal, icke-administrativ användning och bara använda sitt administratörskonto när det behövs för att slutföra en uppgift som är kopplad till jobbfunktionen.

Skydda dina administratörskonton med multifaktorautentisering och villkorlig åtkomst. Mer information finns i Skydda [administratörskonton](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts). 

Konfigurera sedan hantering av behörighet i Office 365. Med hantering av behörighetsbehörighet kan du få detaljerad åtkomstkontroll över administrativa uppgifter med Office 365. Det kan skydda organisationen från överträdelser som kan använda befintliga behöriga administratörskonton med stående åtkomst till känsliga data eller åtkomst till viktiga konfigurationsinställningar.

- [Översikt över hantering av privilegierad åtkomst](privileged-access-management-overview.md)
- [Konfigurera hantering av privilegierad åtkomst](privileged-access-management-configuration.md)

En annan rekommendation är att använda arbetsstationer som är särskilt konfigurerade för administrativt arbete. Det här är dedikerade enheter som bara används för administrativa uppgifter. Se [Skydda privilegierad åtkomst.](/windows-server/identity/securing-privileged-access/securing-privileged-access)

Slutligen kan du minimera effekterna av oavsiktlig brist på administrativ åtkomst genom att skapa två eller flera konton för nödåtkomst i klientorganisationen. Se [Hantera konton för nödsamtal i Azure AD.](/azure/active-directory/users-groups-roles/directory-emergency-access) 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>Steg 3: Konfigurera rekommenderade principer för identitet och enhetsåtkomst
Multifaktorautentisering (MFA) och villkorsstyrda åtkomstprinciper är kraftfulla verktyg för att minska skydd mot komprometterade konton och obehörig åtkomst. Vi rekommenderar att du implementerar en uppsättning principer som har testats tillsammans. Mer information, inklusive distributionssteg, finns i [Konfigurationer för identitets- och enhetsåtkomst.](../security/defender-365-security/microsoft-365-policies-configurations.md)

 Dessa principer implementerar följande funktioner:
- Multifaktorautentisering
- Villkorlig åtkomst
- Intune-appskydd (app- och dataskydd för enheter)
- Intune enhetsefterlevnad
- Azure AD Identity Protection

För implementering av Intune enhetsefterlevnad krävs enhetsregistrering. Om du hanterar enheter kan du säkerställa att de är felfria och kompatibla innan du ger dem åtkomst till resurser i din miljö. Se [Registrera enheter för hantering i Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>Steg 4: Konfigurera SharePoint för enhetsåtkomst

Microsoft rekommenderar att du skyddar innehåll på SharePoint webbplatser med känsligt och starkt reglerat innehåll med enhetsåtkomstkontroller. Mer information finns i [Principrekommendationer för att skydda SharePoint och filer.](../security/defender-365-security/sharepoint-file-access-policies.md)



