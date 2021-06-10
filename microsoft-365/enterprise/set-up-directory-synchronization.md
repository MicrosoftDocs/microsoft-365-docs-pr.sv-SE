---
title: Konfigurera katalogsynkronisering för Microsoft 365
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
description: Lär dig konfigurera katalogsynkronisering mellan Microsoft 365 och din lokala Active Directory.
ms.openlocfilehash: 51cf52bd81004157606c884fd4f0b5d3604b877a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924910"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>Konfigurera katalogsynkronisering för Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Microsoft 365 använder en Azure Active Directory -klientorganisation (Azure AD) för att lagra och hantera identiteter för autentisering och behörigheter för åtkomst till molnbaserade resurser. 

Om du har en lokal AD DS-domän (Active Directory Domain Services) eller skog kan du synkronisera dina AD DS-användarkonton, grupper och kontakter med Azure AD-klientorganisationen för Microsoft 365-prenumerationen. Det här är hybrididentitet för Microsoft 365. Här är dess komponenter.

![Komponenter i katalogsynkronisering för Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Anslut på en lokal server och synkroniserar din AD DS med Azure AD-klientorganisationen. Tillsammans med katalogsynkronisering kan du också ange följande autentiseringsalternativ:

- Synkronisering av lösenordshashar (PHS)

  Azure AD utför själva autentiseringen.

- Direktautentisering (PTA)

  Azure AD har AD DS som utför autentiseringen.

- Federerad autentisering

  Azure AD refererar klientdatorn och begär autentisering till en annan identitetsleverantör.

Mer information [finns i Hybrididentiteter.](plan-for-directory-synchronization.md)
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. Granska kraven för Azure AD Anslut

Du får en kostnadsfri Azure AD-prenumeration med din Microsoft 365 prenumeration. När du installerar katalogsynkronisering installerar du Azure AD Anslut på någon av dina lokala servrar.
  
För Microsoft 365 behöver du:
  
- Verifiera din lokala domän. Guiden för Azure AD Anslut vägleder dig genom detta.
- Hämta användarnamn och lösenord för administratörskontona i din klientorganisation Microsoft 365 AD DS.

För den lokala server där du installerar Azure AD Anslut behöver du:
  
|**Serveroperativsystem**|**Annan programvara**|
|:-----|:-----|
|Windows Server 2012 R2 och senare | - PowerShell installeras som standard, ingen åtgärd krävs.  <br> - Net 4.5.1 och senare versioner erbjuds via Windows Update. Kontrollera att du har installerat de senaste uppdateringarna Windows server i Kontrollpanelen. |
|Windows Server 2008 R2 med Service Pack 1 (SP1)** eller Windows Server 2012 | – Den senaste versionen av PowerShell finns i Windows Management Framework 4.0. Sök efter den på [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br> - .Net 4.5.1 och senare versioner finns på [Microsoft Download Center.](https://go.microsoft.com/fwlink/p/?LinkId=717996) |
|Windows Server 2008 | - Den senaste versionen av PowerShell som stöds finns i Windows Management Framework 3.0, tillgänglig på [Microsoft Download Center.](https://go.microsoft.com/fwlink/p/?LinkId=717996)  <br> - .Net 4.5.1 och senare versioner finns på [Microsoft Download Center.](https://go.microsoft.com/fwlink/p/?LinkId=717996) |

Se Krav för Azure Active Directory Anslut information om maskinvara, programvara, konto- och [behörighetskrav,](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) SSL-certifikatkrav och objektbegränsningar för Azure AD Anslut.
  
Du kan också läsa historiken för Anslut versionen i Azure AD [om](/azure/active-directory/hybrid/reference-connect-version-history) du vill se vad som ingår och korrigerats i varje version.

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. Installera Azure AD Anslut och konfigurera katalogsynkronisering

Innan du börjar kontrollerar du att du har:

- Användarnamn och lösenord för en global Microsoft 365 administratör
- Användarnamnet och lösenordet för en AD DS-domänadministratör
- Vilken autentiseringsmetod (PHS, PTA, federerad)
- Om du vill använda [sömlös enkel inloggning (SSO) i Azure AD](/azure/active-directory/hybrid/how-to-connect-sso)

Gör så här:

1. Logga in på [Microsoft 365 (och](https://admin.microsoft.com) https://admin.microsoft.com) välj **Användare** \> **aktiva användare i** det vänstra navigeringsfältet.
2. På sidan **Aktiva användare** väljer du **Mer** (tre punkter) \> **Katalogsynkronisering**.
  
3. På **förberedelsesidan Azure Active Directory du** gå till Download Center för att komma igång genom Anslut Azure AD-Anslut-verktyget.  
4. Följ stegen i [Azure AD Anslut och Azure AD Anslut Health-installationsöversikten.](/azure/active-directory/hybrid/how-to-connect-install-roadmap)

## <a name="3-finish-setting-up-domains"></a>3. Slutföra domäninstallationen

Följ stegen i Skapa [DNS-poster för Microsoft 365 du hanterar dina DNS-poster för](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) att slutföra domänerna.

## <a name="next-step"></a>Nästa steg

[Tilldela licenser till användarkonton](assign-licenses-to-user-accounts.md)