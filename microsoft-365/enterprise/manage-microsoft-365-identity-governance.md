---
title: Hantera Microsoft 365 Identity styrelse
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
description: Lär dig mer om hur du använder Microsoft 365 Identity styrelse-funktioner.
ms.openlocfilehash: e4c537e7fa3ac099caf8b7dbc44327308751c8f5
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370352"
---
# <a name="manage-microsoft-365-identity-governance"></a>Hantera Microsoft 365 Identity styrelse

Identitetsstyrning handlar om att skydda, övervaka och granska åtkomst till kritiska tillgångar och samtidigt säkerställa den anställdas produktivitet. Med identitetsstyrning kan du till exempel se till att rätt användare har rätt åtkomst till rätt resurser och fastställa om åtkomsten förändras med tiden.

Mer information finns i den här [översikten över identitets styrning för Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).

## <a name="set-up-azure-ad-access-reviews"></a>Konfigurera Azure AD-åtkomstgranskningar

Med granskning av Azure AD Access kan du granska en användares åtkomst för att kontrol lera att endast rätt personer har fortsatt åtkomst. Till exempel:

- När en ny medarbetare ansluter sig till din organisation måste du se till att personen har rätt åtkomst för att kunna vara produktiv.
- När den anställde flyttar till andra team, platser eller avdelningar måste du se till att personens åtkomst till tidigare grupper, platser eller avdelningar tas bort efter behov.
- När den anställde eller en gäst lämnar din organisation måste du se till att åtkomsten tas bort.

Det här är särskilt viktigt om organisationen genomgår säkerhetsgranskningar för att avgöra om användarkonton har för mycket åtkomst, vilket kan resultera i böter om branschregler eller regionala föreskrifter överträds.

Mer information finns i [Översikt över Access-granskningar](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).

I följande artiklar beskrivs hur olika typer av åtkomstgranskningar konfigureras:

- [Grupper och appar](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD-roller](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure-resursroller](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Konfigurera hantering av Azure AD Management

Rummet Azure AD Management-hantering, du kan hantera livs cykeln för identitet och åtkomst i skalan genom att automatisera arbets flöden för åtkomst förfrågningar, få till gång till uppgifter, recensioner och förfallo datum.

Dina anställda behöver åtkomst till olika grupper, program och webbplatser för att utföra sina jobb. Det kan vara svårt att hantera den här åtkomsten eftersom kraven ändras, nya program läggs till eller att användare behöver ytterligare åtkomst rättigheter. När du samarbetar med andra organisationer kanske du inte vet vem som finns i den andra organisationen som behöver åtkomst till organisationens resurser, och användare som inte vet vilka program, grupper eller webbplatser som organisationen använder.

Hantering av Azure AD Management kan hjälpa dig att effektivt hantera åtkomst till grupper, program och SharePoint-webbplatser för interna och externa användare.
 
Mer information finns i [Översikt över hantering av Azure AD Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).
