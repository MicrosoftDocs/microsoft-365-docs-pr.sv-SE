---
title: Microsoft 365-moln-Only-identitet
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Här beskrivs hur du skapar användare och grupper när Microsoft 365-prenumerationen använder moln-Only-identitet.
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327933"
---
# <a name="microsoft-365-cloud-only-identity"></a>Microsoft 365-moln-Only-identitet

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Med endast Cloud-identitet lagras alla användare, grupper och kontakter i Azure Active Directory (Azure AD)-klient organisationen för Microsoft 365-prenumerationen. Här är de grundläggande komponenterna i moln-Only-identitet.
 
![Bas komponenterna i moln-Only-identitet](../media/about-microsoft-365-identity/cloud-only-identity.png)

Användare och användar konton i organisationer kan kategoriseras på flera olika sätt. Vissa är anställda och har permanent status. Vissa är leverantörer, entreprenörer eller partners med tillfällig status. Vissa är externa användare som inte har några användar konton men måste ändå beviljas åtkomst till specifika tjänster och resurser för att stödja samverkan och samarbete. Till exempel:

- Klient konton representerar användare inom din organisation som du licensierar för moln tjänster

- Konton för företag mot företag (B2B) representerar användare utanför organisationen som du bjuder in att delta i samarbete

Ta lager med olika typer av användare i organisationen. Vad är grupperingarna? Du kan till exempel gruppera användarna efter en hög nivå funktion eller ett syfte för din organisation.

Dessutom kan vissa moln tjänster delas med användare utanför organisationen utan några användar konton. Du behöver också identifiera dessa användar grupper.

Du kan använda grupper i Azure AD för att förenkla hanteringen av moln miljön. Med Azure AD-grupper kan du till exempel:

- Använd gruppbaserad licensiering för att tilldela licenser för Microsoft 365 till dina användar konton automatiskt när de läggs till som medlemmar.
- Lägga till användar konton i specifika grupper dynamiskt baserat på attribut för användar konton, till exempel avdelnings namn.
- Tillhandahålla automatiskt användare för program vara som tjänst program (SaaS) och för att skydda åtkomst till dessa program med multifaktorautentisering (MFA) och andra principer för villkorsstyrd åtkomst.
- Tillhandahåll behörigheter och åtkomst nivåer för SharePoint Online-gruppwebbplatser.

## <a name="next-steps-for-cloud-only-identity"></a>Nästa steg för moln identitet

- [Hantera användar konton](manage-microsoft-365-accounts.md)
- [Tilldela licenser till användarkonton](assign-licenses-to-user-accounts.md)
- [Hantera grupper och grupp medlemskap](manage-microsoft-365-groups.md)
- [Hantera lösen ord för användar konton](manage-microsoft-365-passwords.md)
