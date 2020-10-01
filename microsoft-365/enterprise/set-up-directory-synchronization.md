---
title: Konfigurera profilsynkronisering för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: Lär dig hur du konfigurerar profilsynkronisering mellan Microsoft 365 och din lokala Active Directory.
ms.openlocfilehash: 308774dcdbaffc1096ab6ad144484e6920accdfa
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327099"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>Konfigurera profilsynkronisering för Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

I Microsoft 365 används en Azure Active Directory-klient (Azure AD) för att lagra och hantera identiteter för att få åtkomst till molnbaserade resurser. 

Om du har en lokal AD DS-domän (Active Directory Domain Services) eller en skog kan du synkronisera dina AD DS-användarkonton, grupper och kontakter med Azure AD-klient organisationen för din Microsoft 365-prenumeration. Det här är hybrid identitet för Microsoft 365. Här är dess komponenter.

![Komponenter i Active Directory-synkronisering för Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Connect körs på en lokal server och synkroniserar AD DS med Azure AD-klient organisationen. Tillsammans med profilsynkronisering kan du även ange följande autentiseringsalternativ:

- Lösenordssynkronisering för lösen ord (PHS)

  Azure AD utför själva autentiseringsprocessen.

- Direktautentisering (PTA)

  Azure AD har AD DS utför verifikationen.

- Federerad autentisering

  Azure AD refererar den klient dator som begär klientautentisering till en annan identitets leverantör.

Se [Hybrid identiteter](plan-for-directory-synchronization.md) för mer information.
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. granska förutsättningar för Azure AD Connect

Du får en gratis Azure AD-prenumeration med ditt Microsoft 365-abonnemang. När du ställer in profilsynkronisering kommer du att installera Azure AD Connect på en av dina lokala servrar.
  
För Microsoft 365 måste du:
  
- Verifiera din lokala domän. Guiden för Azure AD Connect hjälper dig med detta.
- Skaffa användar namn och lösen ord för administratörs kontona för din Microsoft 365-klient organisation och AD DS.

För den lokala server där du installerar Azure AD Connect behöver du:
  
|**Server OS**|**Annan program vara**|
|:-----|:-----|
|Windows Server 2012 R2 och senare | -PowerShell är installerat som standard, ingen åtgärd krävs.  <br> -NET 4.5.1 och senare versioner erbjuds via Windows Update. Kontrol lera att du har installerat de senaste uppdateringarna för Windows Server i kontroll panelen. |
|Windows Server 2008 R2 med Service Pack 1 (SP1) * * eller Windows Server 2012 | -Den senaste versionen av PowerShell finns i Windows Management Framework 4,0. Sök efter den i [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br> – .NET 4.5.1 och senare versioner finns på [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996). |
|Windows Server 2008 | -Den senaste versionen av PowerShell som stöds finns i Windows Management Framework 3,0, som är tillgänglig i [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br> – .NET 4.5.1 och senare versioner finns på [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996). |

Se [förutsättningar för Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites) för information om maskin vara, program vara, konto och behörigheter, SSL-certifikat, krav och objekt gränser för Azure AD Connect.
  
Du kan också kontrol lera [versions historiken](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) för Azure AD Connect för att se vad som ingår och åtgärdat i varje utgåva.

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. Installera Azure AD Connect och konfigurera Directory-synkronisering

Innan du börjar ska du kontrol lera att du har:

- Användar namn och lösen ord för en global administratör för Microsoft 365
- Användar namn och lösen ord för en AD DS-domän administratör
- Vilken autentiseringsmetod (PHS, PTA, federerad)
- Om du vill använda [Azure AD-sömlös enkel inloggning (SSO)](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)

Gör så här:

1. Logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com) ( https://admin.microsoft.com) och välj **användare** \> **aktiva användare** i det vänstra navigerings fältet.
2. Välj **fler** (tre punkter) katalog synkronisering på sidan **aktiva användare** \> **Directory synchronization**.
  
3. På sidan **Azure Active Directory-förberedelse** väljer du **gå till Download Center för att hämta länken för Azure AD Connect-verktyget** för att komma igång. 
4. Följ stegen i [översikten för installation av Azure AD Connect och Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap).

## <a name="3-finish-setting-up-domains"></a>3. Slutför konfigureringen av domäner

Följ stegen i [Skapa DNS-poster för Microsoft 365 när du hanterar dina DNS-poster](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) för att slutföra konfigurationen av dina domäner.

## <a name="next-step"></a>Nästa steg

[Tilldela licenser till användarkonton](assign-licenses-to-user-accounts.md)
