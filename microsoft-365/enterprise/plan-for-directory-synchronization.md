---
title: Hybrid identitet och katalog synkronisering för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 06/09/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Beskriver profilsynkronisering med Microsoft 365, Active Directory Domain Services Cleanup och Azure Active Directory Connect Tool.
ms.openlocfilehash: 2d3161fb835073a22743ea4f3b00ac508479f0f2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694571"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a>Hybrid identitet och katalog synkronisering för Microsoft 365

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Beroende på företagets behov och tekniska krav är hybrid Identity Model och katalog synkronisering det vanligaste alternativet för företags kunder som använder Microsoft 365. Med katalog-synkronisering kan du hantera identiteter i AD DS (Active Directory Domain Services) och alla uppdateringar av användar konton, grupper och kontakter synkroniseras till Azure Active Directory (Azure AD)-klient organisationen för Microsoft 365-prenumerationen.

>[!Note]
>När AD DS-användarkonton synkroniseras för första gången är de inte automatiskt kopplade till en Microsoft 365-licens och kan inte använda Microsoft 365-tjänster, till exempel e-post. Du måste först tilldela dem en användnings plats. Tilldela sedan en licens till dessa användar konton antingen individuellt eller dynamiskt via grupp medlemskap.
>

## <a name="authentication-for-hybrid-identity"></a>Identifiering för Hybrid identitet

Det finns två typer av autentiseringsmetoder vid användning av hybrid identitets modellen:

- Hanterad verifikation

  Azure AD hanterar autentiseringsprocessen med en lokalt lagrad hash-version av lösen ordet eller skickar autentiseringsuppgifterna till en lokal program agent för att autentiseras av den lokala AD DS-tjänsten.

- Federerad autentisering

  Azure AD dirigerar om klient datorn till en annan identitets leverantör.

### <a name="managed-authentication"></a>Hanterad verifikation

Det finns två typer av hanterad verifikation:

- Lösenordssynkronisering för lösen ord (PHS)

  Azure AD utför själva autentiseringsprocessen.

- Direktautentisering (PTA)

  Azure AD har AD DS utför verifikationen.


#### <a name="password-hash-synchronization-phs"></a>Lösenordssynkronisering för lösen ord (PHS)

Med PHS synkroniserar du dina AD DS-användarkonton med Microsoft 365 och hanterar användarna lokalt. Hashar av användar lösen ord synkroniseras från AD DS till Azure AD så att användare har samma lösen ord och i molnet. Det är det enklaste sättet att aktivera auktorisering för AD DS-identiteter i Azure AD. 

![Lösenordssynkronisering för lösen ord (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

När lösen ord ändras eller återställs lokalt synkroniseras de nya lösen ords-hasharna till Azure AD så att användarna kan alltid använda samma lösen ord för moln resurser och lokala resurser. Användarens lösen ord skickas aldrig till Azure AD eller lagras i en ren text i Azure AD. I vissa Premium-funktioner i Azure AD, till exempel identitets skydd, krävs PHS oavsett vilken autentiseringsmetod som är vald.
  
Se [välja rätt autentiseringsmetod](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) för att få mer information.
  
#### <a name="pass-through-authentication-pta"></a>Direktautentisering (PTA)

PTA ger enkel lösen ords verifiering för Azure AD Domain Domain Services med en program agent som körs på en eller flera lokala servrar för att verifiera användare direkt med AD DS. Med PTA synkroniserar du AD DS-användarkonton med Microsoft 365 och hanterar användarna lokalt. 

![Direktautentisering (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

Med PTA kan användarna logga in på både lokala och Microsoft 365-resurser och-program med sitt lokala konto och lösen ord. Denna konfiguration verifierar användarnas lösen ord direkt mot din lokala AD DS utan att lagra lösen ord-hashar i Azure AD. 

PTA är också för organisationer med ett säkerhets krav för att omedelbart upprätthålla lokala användar konto tillstånd, lösen ords principer och inloggnings tider. 
  
Se [välja rätt autentiseringsmetod](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) för att få mer information.
  
### <a name="federated-authentication"></a>Federerad autentisering

Federerad nätverksautentisering är främst avsedd för stora företags organisationer med mer komplexa autentiseringskrav. AD DS-identiteter synkroniseras med Microsoft 365-och användare-konton hanteras lokalt. Med federerad inloggningsautentisering har användare samma lösen ord lokalt och i molnet och de behöver inte logga in igen för att använda Microsoft 365. 

Federerad inloggningsautentisering har stöd för ytterligare autentiseringskrav, till exempel smartcard-baserad eller multifaktorautentisering, och krävs normalt när organisationer har ett autentiseringskrav som inte stöds av Azure AD.
 
Se [välja rätt autentiseringsmetod](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) för att få mer information.
  
#### <a name="third-party-authentication-and-identity-providers"></a>Tredjeparts-och identitets leverantörer

Lokala katalog objekt kan synkroniseras till Microsoft 365 och åtkomst till moln resurser hanteras främst av en tredjeparts identitets leverantör (IdP). Om din organisation använder en tredjeparts-lösning kan du konfigurera inloggning med den lösningen för Microsoft 365 förutsatt att den tredje partens Federations lösning är kompatibel med Azure AD.
  
Mer information finns i [listan över kompatibla Azure AD-listor](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) .
  
## <a name="ad-ds-preparation"></a>AD DS-förberedelse

För att säkerställa en smidig över gång till Microsoft 365 genom att använda synkronisering måste du förbereda AD DS-skogen innan du påbörjar distribution av Microsoft 365-katalog.
  
För att förbereda din katalog bör du fokusera på följande uppgifter:

- Ta bort dubblerade **proxyAddress** och **userPrincipalName** -attribut.
- Uppdatera tomma och ogiltiga **userPrincipalName** -attribut med giltiga **userPrincipalName** -attribut.
- Ta bort ogiltiga och ifrågasatta tecken i attributen **givenName**, efter namn ( **SN** ), **sAMAccountName**, **DisplayName**, **e-post**, **proxyAddresses**, **smek namn**och **userPrincipalName** . Information om hur du förbereder attribut finns i [lista över attribut som synkroniserats med Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).

    > [!NOTE]
    > Det här är samma attribut som Azure AD Connect-synkroniseringar. 
  
## <a name="multi-forest-deployment-considerations"></a>Överväganden vid distribution av flera skogar

För flera skogar och SSO-alternativ använder du en [anpassad installation av Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).
  
Om organisationen har flera skogar för inloggningsautentisering (inloggnings skogar) rekommenderar vi följande:
  
- **Överväg att konsolidera dina skogar.** Vanligt vis är det mer nödvändigt att underhålla flera skogar. Om inte din organisation har säkerhets begränsningar som avgör behovet av separata skogar, bör du förenkla din lokala miljö.
- **Använd endast i din primära inloggnings skog.** Överväg att bara distribuera Microsoft 365 i din primära inloggnings skog för din första installation av Microsoft 365. 

Om du inte kan konsolidera AD DS-distributionen med flera skogar eller använder andra katalog tjänster för att hantera identiteter kanske du kan synkronisera dessa med hjälp av Microsoft eller en partner.
  
Se [topologier för Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) för mer information.
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a>Funktioner som är beroende av profilsynkronisering
  
Katalog-synkronisering krävs för följande funktioner:
  
- Enkel inloggning (SSO) för Azure AD
- Skype-samexistens
- Exchange hybrid distribution, inklusive:
  - Fullständig delad global adress lista mellan den lokala Exchange-miljön och Microsoft 365.
  - Synkronisera GAL-information från olika e-postsystem.
  - Möjlighet att lägga till och ta bort användare från Microsoft 365-tjänst. Detta kräver följande:
  - Dubbelriktad synkronisering måste konfigureras under installationen av katalog synkronisering. Som standard skriver Directory-synkroniseringsfunktionen bara katalog information till molnet. När du konfigurerar dubbelriktad synkronisering kan du aktivera funktionen för att skriva tillbaka så att ett begränsat antal objektattribut kopieras från molnet och sedan skrivas tillbaka till din lokala AD DS. Åter Skriv tillbaka kallas även för Exchange hybrid-läge. 
  - En lokal Exchange hybrid distribution
  - Möjlighet att flytta vissa användar post lådor till Microsoft 365 samtidigt som du håller andra användar post lådor lokalt.
  - Betrodda avsändare och spärrade avsändare replikeras till Microsoft 365.
  - Grundläggande delegering och skicka med e-post.
  - Du har en integrerad lokal smart kort-eller Multi-Factor-autentiseringstjänst.
- Synkronisering av foton, miniatyrer, konferens rum och säkerhets grupper

## <a name="next-step"></a>Nästa steg

När du är redo att distribuera Hybrid identiteter läser du [förbereda för att etablera användare](prepare-for-directory-synchronization.md).
  
## <a name="see-also"></a>Se även

[Översikt över Microsoft 365 Enterprise](microsoft-365-overview.md)

