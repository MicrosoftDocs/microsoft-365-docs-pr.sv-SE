---
title: Hantera Microsoft 365 identitetsstyrning
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Läs mer om hur du Microsoft 365 funktioner för identitetsstyrning.
ms.openlocfilehash: 6a97ca24c609724a2cab93feec9e90f25d3361e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910960"
---
# <a name="manage-microsoft-365-identity-governance"></a>Hantera Microsoft 365 identitetsstyrning

Identitetsstyrning handlar om att skydda, övervaka och granska åtkomst till kritiska tillgångar och samtidigt säkerställa den anställdas produktivitet. Med identitetsstyrning kan du till exempel se till att rätt användare har rätt åtkomst till rätt resurser och fastställa om åtkomsten förändras med tiden.

Mer information finns i den här [översikten över identitetsstyrning för Azure Active Directory (Azure AD).](/azure/active-directory/governance/identity-governance-overview)

## <a name="set-up-azure-ad-access-reviews"></a>Konfigurera Azure AD-åtkomstgranskningar

Med granskningar av Azure AD-åtkomst kan du granska en användares åtkomst så att bara rätt personer har fortsatt åtkomst. Till exempel:

- När en ny medarbetare ansluter sig till din organisation måste du se till att personen har rätt åtkomst för att kunna vara produktiv.
- När den anställde flyttar till andra team, platser eller avdelningar måste du se till att personens åtkomst till tidigare grupper, platser eller avdelningar tas bort efter behov.
- När den anställde eller en gäst lämnar din organisation måste du se till att åtkomsten tas bort.

Det här är särskilt viktigt om organisationen genomgår säkerhetsgranskningar för att avgöra om användarkonton har för mycket åtkomst, vilket kan resultera i böter om branschregler eller regionala föreskrifter överträds.

Mer information finns i översikten [över åtkomstgranskningar](/azure/active-directory/governance/access-reviews-overview).

I följande artiklar beskrivs hur olika typer av åtkomstgranskningar konfigureras:

- [Grupper och appar](/azure/active-directory/governance/create-access-review)
- [Azure AD-roller](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure-resursroller](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Konfigurera hantering av Azure AD-berättiganden

Hantering av åtkomst via Azure AD kan du hantera livscykeln för identitet och åtkomst i skala genom att automatisera arbetsflöden för åtkomstförfrågningar, åtkomsttilldelningar, granskningar och förfallotid.

De anställda behöver åtkomst till olika grupper, program och webbplatser för att kunna utföra sitt jobb. Det kan vara svårt att hantera åtkomsten eftersom kraven ändras, nya program läggs till eller användare behöver ytterligare åtkomsträttigheter. När du samarbetar med andra organisationer kanske du inte vet vem i den andra organisationen som behöver åtkomst till organisationens resurser, och användare utanför organisationen vet inte vilka program, grupper eller webbplatser organisationen använder.

Hantering av Azure AD-berättigande kan hjälpa dig att hantera åtkomsten till grupper, program och SharePoint för interna och externa användare på ett effektivare sätt.
 
Mer information finns i översikten över [hantering av Azure AD-berättiganden.](/azure/active-directory/governance/entitlement-management-overview)