---
title: Hantera lösen ord för Microsoft 365-användarkonto
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
description: Lär dig mer om hur du hanterar lösen ord för användar konton i Microsoft 365.
ms.openlocfilehash: af64002ad54b517a6e8f0b687a00d6bed9ab0214
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328543"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>Hantera lösen ord för Microsoft 365-användarkonto

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan hantera lösen ord för Microsoft 365-konto på flera olika sätt, beroende på din identitets konfiguration. Du kan hantera användar konton i [administrations centret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/), i AD DS (Active Directory Domain Services) eller i administrations centret för Azure Active Directory (Azure AD).

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>Planera var och hur du ska hantera lösen ord för ditt användar konto

Var och hur du kan hantera dina användar konton beror på vilken identitets modell du vill använda för Microsoft 365. De två modellerna är enbart molnbaserade och hybrid.
  
### <a name="cloud-only"></a>Endast molnet

Du hanterar lösen ord för användar konton i:

- [Administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- Administrations centret för Azure AD
    
### <a name="hybrid"></a>Hybrid

Med hybrid identitet lagras lösen ord i AD DS så du måste använda lokala AD DS-verktyg för att hantera lösen ord för användar konton. Även när du använder Lösenordssynkronisering (PHS), där Azure AD lagrar en hash-version av den redan hashade versionen i AD DS, måste du och användare hantera sina lösen ord i AD DS.

Med [Lösenordssynkronisering](#pw_writeback)kan användarna ändra sina AD DS-lösenord via Azure AD.

## <a name="prevent-bad-passwords"></a>Förhindra svaga lösenord

Alla dina användare bör följa [Microsofts lösenordsvägledning](https://www.microsoft.com/research/publication/password-guidance) när de skapar lösenord till sina användarkonton.

Hindra användarna från att skapa svaga lösenord genom att använda Azure AD-lösenordsskydd, som tillämpar både en global lista med blockerade lösenord och en valfri lista med blockerade lösenord som du väljer. Du kan till exempel välja ord som gäller specifikt för din organisation, som:

- Varumärken
- Produktnamn
- Platser (till exempel företagets huvudkontor)
- Företagsspecifik, intern terminologi
- Förkortningar med särskild betydelse för företaget

Du kan förbjuda Felaktiga lösen ord [i molnet](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) och för din [lokala AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).

## <a name="simplify-user-sign-in"></a>Enklare inloggning för användare

Azure AD-sömlös enkel inloggning (Azure AD sömlös SSO) fungerar med PHS och direktautentisering (PTA), så att användarna kan logga in på tjänster som använder Azure AD-användarkonton utan att behöva ange deras lösen ord, och i många fall, deras användar namn. Det gör att användarna lättare kommer åt molnbaserade program, till exempel Office 365, utan att behöva några ytterligare lokala komponenter som identitetsservrar.

Du konfigurerar Azure AD Seamless SSO med Azure AD Connect-verktyget. Se [anvisningarna för att konfigurera Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>Förenkla lösen ords uppdateringar till AD DS

Med lösen ords försök kan du tillåta att användare återställer sina lösen ord via Azure AD som sedan replikeras till AD DS. Användarna behöver inte komma åt sin lokala AD DS för att uppdatera sina lösen ord. Det här är värdefullt vid nätverksväxling och för fjärranvändare som inte har någon fjärråtkomstanslutning till det lokala nätverket.

Tillbakaskrivning av lösenord krävs för att fullt ut använda skyddsfunktioner för Azure AD, t. ex. för att begära att användare ska ändra sina lokala lösenord när en stor risk för kontointrång har upptäckts.

Mer information och anvisningar för konfiguration finns i [Azure AD SSPR med tillbakaskrivning av lösenord](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Uppgradera till den senaste versionen av Azure AD Connect för att säkerställa bästa möjliga upplevelse och nya funktioner när de släpps. Mer information finns i [Anpassad installation av Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

## <a name="simplify-password-resets"></a>Enklare återställning av lösenord

Med självbetjäning för återställning av lösen ord (SSPR) kan användarna återställa eller låsa upp sina lösen ord eller konton. Du kan få varningar om missbruk eller felanvändning genom att använda den detaljerade rapporteringen som spårar när användare har åtkomst till systemet, tillsammans med meddelanden. Du måste aktivera [Ångra lösen ord](#pw_writeback) innan du kan distribuera Återställ lösen ord.

Se [anvisningarna för att distribuera återställning av lösenord](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).

