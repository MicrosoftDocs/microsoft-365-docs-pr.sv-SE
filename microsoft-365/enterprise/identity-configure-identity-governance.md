---
title: 'Steg 7: Konfigurera identitetsstyrning'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och konfigurera identitetsstyrning för Azure AD-innehavaren.
ms.openlocfilehash: 5b7b1c91735611046133a0247ae028ed090106fd
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42812597"
---
# <a name="step-6-configure-identity-governance"></a>Step 6: Konfigurera identitetsstyrning

![Fas 2 – Identitet](../media/deploy-foundation-infrastructure/identity_icon-small.png)

Identitetsstyrning handlar om att skydda, övervaka och granska åtkomst till kritiska tillgångar och samtidigt säkerställa den anställdas produktivitet. Med identitetsstyrning kan du till exempel se till att rätt användare har rätt åtkomst till rätt resurser och fastställa om åtkomsten förändras med tiden.

Mer information om identitets styrning för Azure Active Directory (Azure AD) finns [den här artikeln](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).


*Det här är valfritt och gäller endast E5-versionen av Microsoft 365 Enterprise*


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a>Konfigurera Azure AD-åtkomstgranskningar

*Det här är valfritt och gäller endast E5-versionen av Microsoft 365 Enterprise*

I det här steget konfigurerar du Azure AD-åtkomstgranskningar, som gör att du kan granska en användares åtkomst för att säkerställa att bara rätt personer har fortsatt åtkomst. Till exempel:

- När en ny medarbetare ansluter sig till din organisation måste du se till att personen har rätt åtkomst för att kunna vara produktiv.
- När den anställde flyttar till andra team, platser eller avdelningar måste du se till att personens åtkomst till tidigare grupper, platser eller avdelningar tas bort efter behov.
- När den anställde eller en gäst lämnar din organisation måste du se till att åtkomsten tas bort.

Det här är särskilt viktigt om organisationen genomgår säkerhetsgranskningar för att avgöra om användarkonton har för mycket åtkomst, vilket kan resultera i böter om branschregler eller regionala föreskrifter överträds.

I [den här artikeln](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) finns mer information om Azure AD-åtkomstgranskningar.

Azure AD-privilegierad identitetshantering (PIM) tillhandahåller ytterligare kontroller som är anpassade för att skydda åtkomsträttigheter för resurser, på Azure AD, Azure och andra Microsoft-molntjänster. Med Azure AD PIM får du en omfattande uppsättning styrningskontroller som hjälper dig att skydda företagets resurser, till exempel Directory, Office 365 och Azure-resursroller. Precis som med andra former av åtkomst kan organisationer använda åtkomstgranskningar för att konfigurera återkommande åtkomst för alla användare i administratörsroller. Azure AD PIM finns bara i E5-versionen av Microsoft 365 Enterprise.

I följande artiklar beskrivs hur olika typer av åtkomstgranskningar konfigureras:

- [Grupper och appar](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD-roller](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure-resursroller](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-access-reviews) för det här avsnittet.

## <a name="next-step"></a>Nästa steg

[Avslutsvillkor för identitetsinfrastruktur](identity-exit-criteria.md)

