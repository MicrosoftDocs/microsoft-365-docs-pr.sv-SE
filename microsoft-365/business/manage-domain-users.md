---
title: Synkronisera domänanvändare med Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Synkronisera domänstyrda användare med Microsoft 365 för företag.
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578416"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Synkronisera domänanvändare med Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Förbereda katalogsynkronisering 

Innan du synkroniserar användare och datorer från den lokala Active Directory-domänen bör du läsa Förbereda [katalogsynkronisering till Microsoft 365.](../enterprise/prepare-for-directory-synchronization.md) Framförallt:

   - Kontrollera att det inte finns några dubbletter i katalogen för följande attribut: **mail,** **proxyAddresses** och **userPrincipalName.** Dessa värden måste vara unika och eventuella dubbletter måste tas bort.
   
   - Vi rekommenderar att du konfigurerar **attributet userPrincipalName** (UPN) för varje lokalt användarkonto så att det matchar den primära e-postadress som motsvarar den licensierade Microsoft 365-användaren. Till exempel: *mary.shelley@contoso.com* inte *mary@contoso.local*
   
   - Om Active [Directory-domänen](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)slutar med ett icke-dirigerbart suffix som *.local* eller *.lan* i stället för ett dirigerbart internetsuffix, till exempel *.com* eller *.org,* justerar du UPN-suffixet för de lokala användarkontona först enligt beskrivningen i Förbereda en icke-dirigerbar domän för katalogsynkronisering. 

Med **Kör IdFix** i steg fyra (4) nedan ser du också till att din lokala Active Directory är redo för katalogsynkronisering.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Installera och konfigurera Azure AD Connect

Installera Azure Active Directory Connect och konfigurera katalogsynkronisering om du vill synkronisera användare, grupper och kontakter från den lokala Active Directory i Azure Active Directory. 

 1. I [administrationscentret väljer](https://go.microsoft.com/fwlink/p/?linkid=2024339)du **Inställningar i** det vänstra navigeringsfältet.

 2. Under **Inloggning och säkerhet väljer** du **Visa** under Synkronisera användare **från organisationens katalog.**

 3. På sidan **Synkronisera användare från organisationens katalog väljer** du Komma **igång.**

 4. I det första steget ska du köra IdFix-verktyget för att förbereda katalogsynkronisering.

 5. Följ anvisningarna i guiden för att ladda ned Azure AD Connect och använda det för att synkronisera dina domänstyrda användare till Microsoft 365.


Mer [information finns i Konfigurera katalogsynkronisering för Microsoft 365.](../enterprise/set-up-directory-synchronization.md)

När du konfigurerar alternativen för Azure AD Connect rekommenderar vi att du aktiverar  lösenordssynkronisering, sömlös enkel inloggning och återskrivningsfunktionen för lösenord, som också stöds i Microsoft 365 för företag.

> [!NOTE]
> Det finns några ytterligare steg för tillbakaskrivning av lösenord utöver kryssrutan i Azure AD Connect. Mer information finns i Så [här gör du för att: konfigurera tillbakaskrivning av lösenord.](/azure/active-directory/authentication/howto-sspr-writeback) 

Om du även vill hantera domänaktiverade Windows 10-enheter kan du gå till Aktivera domän anslutna [Windows 10-enheter](manage-windows-devices.md) så att de hanteras av Microsoft 365 Business Premium och konfigurera en Azure AD-hybridkoppling.