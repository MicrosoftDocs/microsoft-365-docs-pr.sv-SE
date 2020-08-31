---
title: Synkronisera domänanvändare med Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
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
description: Synkronisera domän kontrollerade användare med Microsoft 365 för företag.
ms.openlocfilehash: 9495d893eb6870ef7c417a78f921296bfc0e6705
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306458"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Synkronisera domänanvändare med Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. förbereda för Active Directory-synkronisering 

Innan du synkroniserar användare och datorer från den lokala Active Directory-domänen bör du kontrol lera [förbereda för Active Directory-synkronisering till Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization). Särskilt:

   - Kontrol lera att det inte finns några dubbletter i katalogen för följande attribut: **mail**, **proxyAddresses**och **userPrincipalName**. Dessa värden måste vara unika och dubbletter måste tas bort.
   
   - Vi rekommenderar att du konfigurerar **userPrincipalName** -attributet (UPN) för varje lokalt användar konto så att det stämmer överens med den primära e-postadressen som motsvarar den licensierade Microsoft 365-användaren. Till exempel: *Mary.Shelley@contoso.com* i stället för *Mary@contoso. local*
   
   - Om Active Directory-domänen slutar på ett icke-dirigerbart till exempel *. local* eller *. LAN*, kan du i stället för ett dirigerbart Internet *-suffix som. com* eller *. org*justera UPN-suffixet för de lokala användar kontona enligt beskrivningen i [förbereda en icke-dirigerbart domän för Active Directory-synkronisering](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

**Kör IdFix** i steg fyra (4) nedan kontrollerar också att den lokala Active Directory är klar för dir-synkronisering.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Installera och konfigurera Azure AD Connect

Om du vill synkronisera dina användare, grupper och kontakter från den lokala Active Directory i Azure Active Directory installerar du Azure Active Directory Connect och konfigurera katalog synkronisering. 

 1. I administrations centret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> Select **Setup** i det vänstra navigerings fältet.

 2. Under **inloggning och säkerhet**väljer du **Visa**  under **synkronisera användare i organisationens katalog**.

 3. På sidan **synkronisera användare från organisationens katalog** sida väljer du **komma igång**.

 4. I det första steget Kör IdFix verktyg för att förbereda för katalog synkronisering.

 5. Följ stegen i guiden för att ladda ned Azure AD Connect och Använd den för att synkronisera domän kontrollerade användare till Microsoft 365.


Mer information finns i [Konfigurera katalog-synkronisering för Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) .

När du konfigurerar alternativen för Azure AD Connect rekommenderar **vi att du aktiverar Lösenordssynkronisering**, **sömlös enkel inloggning**och funktionen för att ändra **lösen ord** , som också stöds i Microsoft 365 för företag.

> [!NOTE]
> Det finns ytterligare anvisningar för att ångra lösen ordet utöver kryss rutan i Azure AD Connect. Mer information finns i [så här konfigurerar du tillbakaskrivning av lösen ord](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

Om du vill hantera domänanslutna Windows 10-enheter kan du läsa [Aktivera domän anslutna Windows 10-enheter som hanteras av Microsoft 365 Business Premium](manage-windows-devices.md) för att konfigurera en hybrid Azure AD-anslutning. 