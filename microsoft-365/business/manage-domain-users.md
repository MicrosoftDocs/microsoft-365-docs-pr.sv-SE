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
description: Synkronisera domänkontrollerade användare med Microsoft 365 för företag.
ms.openlocfilehash: af9cb7c9b2b639edc2375679a73ab41c4cf6de71
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080065"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Synkronisera domänanvändare med Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Förbered för katalogsynkronisering 

Innan du synkroniserar användare och datorer från den lokala Active Directory-domänen läser du [Förbered för katalogsynkronisering med Microsoft 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). I synnerhet gäller följande:

   - Kontrollera att det inte finns några dubbletter i katalogen för följande attribut: **e-post**, **proxyAdresser**och **userPrincipalName**. Dessa värden måste vara unika och eventuella dubbletter måste tas bort.
   
   - Vi rekommenderar att du konfigurerar attributet **userPrincipalName** (UPN) för varje lokalt användarkonto så att det matchar den primära e-postadressen som motsvarar den licensierade Microsoft 365-användaren. Till exempel: *mary.shelley@contoso.com* i stället *för mary@contoso.local*
   
   - Om Active Directory-domänen slutar i ett suffix som inte är dirigerbart som *.local* eller *.lan*i stället för ett internetrdigerbart suffix som *.com* eller *.org*justerar du UPN-suffixet för de lokala användarkontona först enligt beskrivningen i [Förbered en icke-dirigerbar domän för katalogsynkronisering](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

**Run IdFix** i steg fyra (4) nedan, kommer också att se till att din lokala Active Directory är redo för dir-synkronisering.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Installera och konfigurera Azure AD Connect

Om du vill synkronisera användare, grupper och kontakter från den lokala Active Directory till Azure Active Directory installerar du Azure Active Directory Connect och konfigurerar katalogsynkronisering. 

 1. Välj Inställningar i den vänstra navigeringscentralen i administrationscentret vid <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> administrationscentret. **Setup**

 2. Under **Logga in och säkerhet**väljer du **Visa** under Synkronisera användare **från organisationens katalog**.

 3. På **synkroniseringsanvändarna från organisationens katalogsida** väljer du **Kom igång**.

 4. I det första steget kör IdFix-verktyget för att förbereda för katalogsynkronisering.

 5. Följ guidestegen för att hämta Azure AD Connect och använda den för att synkronisera dina domänkontrollerade användare till Microsoft 365.


Mer information finns i [Konfigurera katalogsynkronisering för Microsoft 365.](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)

När du konfigurerar dina alternativ för Azure AD Connect rekommenderar vi att du aktiverar **lösenordssynkronisering**, **Sömlös enkel inloggning**och **tillbakaskrivningsfunktionen** för lösenord, som också stöds i Microsoft 365 för företag.

> [!NOTE]
> Det finns ytterligare några steg för återställning av lösenord utanför kryssrutan i Azure AD Connect. Mer information finns i [Så här konfigurerar du tillbaka lösenordet](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

Om du också vill hantera domänanslutna Windows 10-enheter läser du [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business Premium](manage-windows-devices.md) för att konfigurera en hybrid-Azure AD-koppling. 