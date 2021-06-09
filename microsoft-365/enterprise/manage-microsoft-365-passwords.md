---
title: Hantera Microsoft 365 lösenord för användarkonton
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
description: Läs mer om hur du Microsoft 365 lösenord för användarkonton.
ms.openlocfilehash: 2062da49310121ec18f7ce21f523531f10d6df9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905098"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>Hantera Microsoft 365 lösenord för användarkonton

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan hantera Microsoft 365 lösenord för användarkonton på flera olika sätt, beroende på din identitetskonfiguration. Du kan hantera användarkonton [i administrationscentret för Microsoft 365](../admin/add-users/index.yml), i AD DS (Active Directory Domain Services) eller i administrationscentret för Azure Active Directory (Azure AD).

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>Planera för var och hur du ska hantera lösenorden för ditt användarkonto

Var och hur du kan hantera användarkonton beror på vilken identitetsmodell du vill använda för ditt Microsoft 365. De två modellerna är bara molnbaserade och hybrider.
  
### <a name="cloud-only"></a>Endast molnet

Du hanterar lösenord för användarkonton i:

- [Administrationscentret för Microsoft 365](../admin/add-users/index.yml)
- Administrationscentret för Azure AD
    
### <a name="hybrid"></a>Hybrid

Med hybrididentitet lagras lösenord i AD DS så att du måste använda lokala AD DS-verktyg för att hantera lösenord för användarkonton. Även när du använder synkronisering av lösenordshashar (PHS), där Azure AD lagrar en hashtaggad version av den redan hashtaggade versionen i AD DS, måste du och användarna hantera sina lösenord i AD DS.

Med [tillbakaskrivning av](#pw_writeback)lösenord kan användarna ändra sina AD DS-lösenord via Azure AD.

## <a name="prevent-bad-passwords"></a>Förhindra svaga lösenord

Alla dina användare bör följa [Microsofts lösenordsvägledning](https://www.microsoft.com/research/publication/password-guidance) när de skapar lösenord till sina användarkonton.

Hindra användarna från att skapa svaga lösenord genom att använda Azure AD-lösenordsskydd, som tillämpar både en global lista med blockerade lösenord och en valfri lista med blockerade lösenord som du väljer. Du kan till exempel välja ord som gäller specifikt för din organisation, som:

- Varumärken
- Produktnamn
- Platser (till exempel företagets huvudkontor)
- Företagsspecifik, intern terminologi
- Förkortningar med särskild betydelse för företaget

Du kan förbjuda [dåliga lösenord i](/azure/active-directory/authentication/concept-password-ban-bad) molnet och för dina lokala AD [DS](/azure/active-directory/authentication/concept-password-ban-bad-on-premises).

## <a name="simplify-user-sign-in"></a>Enklare inloggning för användare

Sömlös enkel inloggning Sign-On i Azure AD (Azure AD Seamless SSO) fungerar med PHS och Pass-Through Authentication (PTA) så att dina användare kan logga in på tjänster som använder Azure AD-användarkonton utan att behöva ange sina lösenord, och i många fall sina användarnamn. Det gör att användarna lättare kommer åt molnbaserade program, till exempel Office 365, utan att behöva några ytterligare lokala komponenter som identitetsservrar.

Du konfigurerar Azure AD Seamless SSO med Azure AD Connect-verktyget. Se [anvisningarna för att konfigurera Azure AD Seamless SSO](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>Förenkla lösenordsuppdateringar för AD DS

Med tillbakaskrivning av lösenord kan du tillåta användare att återställa sina lösenord via Azure AD, som sedan replikeras till AD DS. Användarna behöver inte ha åtkomst till sina lokala AD DS för att uppdatera sina lösenord. Det här är värdefullt vid nätverksväxling och för fjärranvändare som inte har någon fjärråtkomstanslutning till det lokala nätverket.

Tillbakaskrivning av lösenord krävs för att fullt ut använda skyddsfunktioner för Azure AD, t. ex. för att begära att användare ska ändra sina lokala lösenord när en stor risk för kontointrång har upptäckts.

Mer information och anvisningar för konfiguration finns i [Azure AD SSPR med tillbakaskrivning av lösenord](/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Uppgradera till den senaste versionen av Azure AD Connect för att säkerställa bästa möjliga upplevelse och nya funktioner när de släpps. Mer information finns i [Anpassad installation av Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

## <a name="simplify-password-resets"></a>Enklare återställning av lösenord

Med självbetjäning för återställning av lösenord (SSPR) kan användare återställa eller låsa upp sina lösenord eller konton. Du kan få varningar om missbruk eller felanvändning genom att använda den detaljerade rapporteringen som spårar när användare har åtkomst till systemet, tillsammans med meddelanden. Du måste aktivera [tillbakaskrivning av lösenord](#pw_writeback) innan du kan distribuera återställningar av lösenord.

Se [anvisningarna för att distribuera återställning av lösenord](/azure/active-directory/authentication/howto-sspr-deployment).