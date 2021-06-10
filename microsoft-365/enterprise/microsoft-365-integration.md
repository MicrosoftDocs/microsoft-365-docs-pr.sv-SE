---
title: Microsoft 365 med lokala miljöer
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: I den här artikeln lär du dig att Microsoft 365 med befintliga katalogtjänster och lokala miljöer.
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923972"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Microsoft 365 med lokala miljöer

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan Microsoft 365 med din befintliga lokala AD DS (Active Directory Domain Services) och med lokala installationer av Exchange Server, Skype för företag – Server 2015 eller SharePoint Server.
  
 - När du integrerar AD DS kan du synkronisera och hantera användarkonton för båda miljöerna. Du kan också lägga till synkronisering av lösenordshashar (PHS) eller enkel inloggning (SSO) så att användarna kan logga in på båda miljöerna med sina lokala inloggningsuppgifter.
 - När du integrerar med lokala serverprodukter skapar du en hybridmiljö. En hybridmiljö kan vara till hjälp när du migrerar användare eller information till Microsoft 365, eller så kan du fortsätta att låta vissa användare eller viss information vara lokalt medan en del finns i molnet. Mer information om hybridmiljöer finns i [hybridmoln](../solutions/cloud-architecture-models.md#hybrid).

Du kan också använda Azure Active Directory-rådgivare (Azure AD) för anpassad konfigurationsvägledning i administrationscentret för Microsoft 365 (du måste vara inloggad på Microsoft 365):

- [Konfigurationsguide för Azure AD](https://aka.ms/aadpguidance)
- [Synkronisera användare från organisationens katalog](https://aka.ms/aadconnectpwsync)
- [Distributionsrådgivaren för AD FS (Active Directory Federation Services)](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>Innan du börjar

Innan du Microsoft 365 nätverksplanering och en lokal miljö måste du också planera [och finjustera nätverksprestanda.](network-planning-and-performance.md) Du bör också förstå vilka [identitetsmodeller som är tillgängliga.](about-microsoft-365-identity.md) 

I [Hantera Microsoft 365-konton](manage-microsoft-365-accounts.md) finns en lista över verktyg som du kan använda för Microsoft 365-användarkonton. 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>Integrera Microsoft 365 med AD DS

Om du har befintliga användarkonton i AD DS vill du inte skapa alla dessa konton på nytt i Microsoft 365 och riskera att introducera skillnader eller fel mellan miljöerna. Katalogsynkronisering hjälper dig att spegla dessa konton mellan dina lokala miljöer och onlinemiljöer. Med katalogsynkronisering behöver användarna inte komma ihåg ny information för varje miljö, och du behöver inte skapa eller uppdatera konton två gånger. Du måste förbereda [den lokala katalogen för katalogsynkronisering.](prepare-for-directory-synchronization.md)
  
![Använda katalogsynkronisering för att hålla lokal information synkroniserad med information för onlineanvändarkontot](../media/microsoft-365-integration/directory-synchronization.png)
  
Om du vill att användarna ska kunna logga in på Microsoft 365 med sina lokala autentiseringsuppgifter kan du också konfigurera SSO. Med SSO Microsoft 365 att lita på den lokala miljön för användarautentisering.
  
![Med enkel inloggning är samma konto tillgängligt i både lokal miljö och online](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>Katalogsynkronisering med eller utan synkronisering av lösenordshashar eller direktautentisering (PTA)

Användarna loggar in i den lokala miljön med sitt användarkonto (domän\användarnamn). När de går till Microsoft 365 måste de logga in igen med sitt arbets- eller skolkonto (user@domain.com). Användarnamnet är samma i båda miljöerna. När du lägger till PHS eller PTA har användaren samma lösenord för båda miljöerna, men kommer att behöva ange de uppgifterna igen när du loggar in på Microsoft 365. Katalogsynkronisering med PHS är den vanligaste katalogsynkroniseringen.

Om du vill konfigurera katalogsynkronisering använder du Azure AD Anslut. Anvisningar finns i Konfigurera [katalogsynkronisering för Microsoft 365](set-up-directory-synchronization.md) och [Azure AD Anslut med standardinställningar.](/azure/active-directory/hybrid/how-to-connect-install-express)

Läs mer om att [förbereda för katalogsynkronisering för Microsoft 365](prepare-for-directory-synchronization.md).

### <a name="directory-synchronization-with-sso"></a>Katalogsynkronisering med SSO

Användarna loggar in i den lokala miljön med sitt användarkonto. När de går till Microsoft 365 loggas de antingen in automatiskt eller så loggar de in med samma inloggningsuppgifter som de använder för den lokala miljön (domän\användarnamn).

Om du vill konfigurera SSO använder du även Azure AD Anslut. Anvisningar finns i Anpassad [installation av Azure AD Anslut.](/azure/active-directory/hybrid/how-to-connect-install-custom)

Mer information finns i [enkel inloggning](/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="azure-ad-connect"></a>Azure AD-Anslut

Azure AD Anslut äldre versioner av identitetsintegreringsverktyg, till exempel DirSync och Azure AD Sync. Om du vill uppdatera från Azure Active Directory till Azure AD Anslut följer [du uppgraderingsanvisningarna](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started). 

## <a name="see-also"></a>Se även

[Microsoft 365 Enterprise översikt](microsoft-365-overview.md)