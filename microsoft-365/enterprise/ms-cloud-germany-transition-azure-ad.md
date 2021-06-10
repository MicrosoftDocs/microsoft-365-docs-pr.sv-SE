---
title: Ytterligare Azure Active Directory för migreringen från Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Sammanfattning: Azure Active Directory ytterligare information när du flyttar från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365 tjänster i den nya tyska datacenterregion.'
ms.openlocfilehash: 1e3871dc5a8a8a9ecbef29df21431aa3707871d0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923856"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Ytterligare Azure Active Directory för migreringen från Microsoft Cloud Deutschland

För att slutföra flytten från det tyska molnet i Azure till det offentliga Azure-molnet rekommenderar vi att autentiseringsslutpunkten, Azure Active Directory (Azure AD) Graph och MS Graph-slutpunkterna för dina program uppdateras till slutpunkterna för det kommersiella molnet när Slutpunkten för OpenID Anslut (OIDC) börjar rapportera slutpunkter för kommersiella `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` moln. 
 
**När ska jag göra den här ändringen?**

Du får ett meddelande i Azure/Office-portalen när klientorganisationen har slutfört migreringen från det tyska molnet till det kommersiella molnet. Du har 30 dagar efter att du fått det här meddelandet för att slutföra uppdateringarna så att appen fortsätter att fungera för klientorganisationen som migreras från Azure Germany-molnet till Det offentliga Azure-molnet.
 
Det finns tre ändringar av hur din inloggningsutfärdare uppdateras:

 - OIDC-identifieringsslutpunkten för klientorganisationen `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returnerar slutpunkter för offentliga Azure AD-moln.

 - Om klientorganisationen har ställts in för federation uppdateras AD FS (Active Directory Federation Services) så att den synkroniseras med Azure AD Public. Du kan följa anvisningarna för att uppdatera Azure AD Anslut inställningar för att göra den här ändringen.

 - Eventuella resursprogram som används av dina program ändras för att acceptera token som är signerade av både Azure AD Germany och Azure AD Public.
 
**Vilken typ av program?**

Ett program kan vara något av följande:

- [Ensidesapp (SPA)](/azure/active-directory/develop/scenario-spa-overview)
- [Webbapp som loggar in användare](/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [Webbapp som anropar webb-API:er](/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [Skyddat webb-API](/azure/active-directory/develop/scenario-protected-web-api-overview)
- [Webb-API som anropar webb-API:er](/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [Skrivbordsapp](/azure/active-directory/develop/scenario-desktop-overview)
- [Appen Daemon](/azure/active-directory/develop/scenario-daemon-overview)
- [Mobilapp](/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> När ett program växlar till att använda `login.microsoftonline.com` som din behörighet, signeras tokenen av den nya behörigheten. Om du är värd för ett resursprogram som andra appar ringer till måste du tillåta verifiering av token. Det innebär att appen måste tillåta token som har signerats av både offentliga Azure AD Germany- och Azure AD-moln. Den här tokenverifieringen krävs tills alla klientprogram som anropar tjänsten har migrerats helt till det offentliga Azure AD-molnet. Efter migreringen behöver resursprogrammet bara acceptera token som signerats av det offentliga Azure AD-molnet.

**Vad behöver jag uppdatera?**

1. Om du är värd för ett program i Azure Germany som används för att autentisera Azure Germany- eller Office 365 Germany-användare ska du se till att det används som behörighet i `https://login.microsoftonline.com` autentiseringssammanhanget.

    - Se Azure AD-autentiseringskontext.
    - Detta gäller både autentisering för programmet och autentisering på alla API:er som programmet anropar (det vill säga Microsoft Graph, Azure AD Graph, Azure Resource Manager).

2. Uppdatera Azure AD Graph slutpunkt till `https://graph.windows.net` .

3. Uppdatera MS Graph till `https://graph.microsoft.com` .

4. Uppdatera eventuella tyska molnslutpunkter (till exempel de för Exchange Online och SharePoint Online) som används av dina program för att vara de som gäller för det offentliga molnet.

5. Uppdatera miljöparametrar till `AzurePublic` att vara (i stället `AzureGermany` för ) i administrativa verktyg och skript för:

    - [Azure PowerShell](/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline)](/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD)](/powershell/azure/active-directory/install-adv2)
    - [Azure CLI](/cli/azure/install-azure-cli)
 
**Vad gäller för program som jag publicerar?**

Om du publicerar ett program som är tillgängligt för användare utanför klientorganisationen kan du behöva ändra programregistreringen för att säkerställa kontinuitet. Andra klientorganisationar som använder programmet kan flyttas vid en annan tidpunkt än klientorganisationen. Om du vill se till att de aldrig förlorar åtkomsten till ditt program måste du godkänna att appen synkroniseras från Azure Germany till azure public.

## <a name="additional-considerations"></a>Ytterligare överväganden

Här är några ytterligare överväganden för Azure AD:

- För federerad autentisering:

  - Du får inte skapa, höja eller sänka en federerad domän under tiden övergången av klientorganisationen pågår. När migreringen till Azure AD-tjänsten är klar (klientorganisationen är helt klar) kan du fortsätta att hantera federerade domäner.

  - Om du använder federerad autentisering med AD FS (Active Directory Federation Services) bör du inte göra ändringar av utfärdare-URI:er som används för all autentisering med din lokala AD DS (Active Directory Domain Services) under migreringen. Att ändra utfärdare-URI:er leder till autentiseringsfel för användare i domänen. Utfärdares URI:er kan ändras direkt i AD FS eller när en domän konverteras från hanterad till federerad och tvärtom. Microsoft rekommenderar att kunder inte lägger till, tar bort eller konverterar en federerad domän i den Azure AD-klientorganisation som migreras. Uri:er för utfärdare kan ändras när migreringen är fullständig.

- För nätverk:

  - Det går inte att skapa IPv6-namngivna nätverk i Azure `http://portal.microsoftazure.de/` Portal. Använd Azure-portalen för `https://portal.azure.com` att skapa IPv6-namngivna nätverk.
 
   - Du kan inte skapa betrodda IP-adressintervall för Tjänstinställningar för Azure Multi-Factor Authentication (MFA) från Microsoft Cloud Deutschland-portalen. Använd Azure AD-portalen för att Office 365 tjänster för att skapa betrodda IP-adressintervall för Azure MFA.


- För villkorsstyrd åtkomst: 

  - Villkorsstyrda åtkomstprinciper med följande bevilja kontroller stöds inte förrän migreringen till Office 365 tjänster är slutförd (efter att Azure [AD-migreringsfasen](ms-cloud-germany-transition.md#how-is-the-migration-organized) slutförts):

    - Kräv kompatibel enhet
    - Kräv godkänd app
    - Kräv appskyddsprincip
    
  - I principgränssnittet för villkorsstyrd åtkomst visas en falsk varning om att säkerhetsstandarder aktiveras för klientorganisationen även om det är inaktiverat, och villkorsstyrda åtkomstprinciper finns redan för klientorganisationen. Du bör ignorera varningen eller använda portalen för Office 365-tjänster för att hantera villkorsstyrda åtkomstprinciper. 

- Intune-scenarier stöds endast mot globala slutpunkter när klientorganisationens migrering har slutförts, inklusive alla migreringar av Office-arbetsbelastningar.

- Microsoft Cloud Deutschland-användare som använder metoden Avisering för mobilappar för MFA-begäranden ser användarens ObjectId (en GUID) i stället för användarens huvudnamn (UPN) i Microsoft Authenticator-appen. När Azure AD-klientorganisationen har migrerats och Office 365 tjänster visas användarnas UPN Microsoft Authenticator av nya Microsoft Authenticator. Befintliga Microsoft Authenticator-konton fortsätter att visa användarens Objekt-ID, men de fortsätter att fungera för aviseringar i mobilappar. 

- För klientorganisationen som skapas efter den 22 oktober 2019 kan säkerhetsstandarder aktiveras automatiskt för innehavaren när den migreras till Office 365 tjänsten. Innehavaradministratörer kan välja att låta säkerhetsstandarder vara aktiverade och registrera sig för MFA, eller så kan de inaktivera funktionen. Mer information finns i [Inaktivera standardinställningar för säkerhet.](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults) 

  > [!NOTE]
  > Organisationer som inte har aktiverats automatiskt under migreringen kanske fortfarande registreras automatiskt i framtiden eftersom funktionen för att aktivera säkerhetsstandarder distribueras i Office 365 tjänsten. Administratörer som väljer att uttryckligen inaktivera eller aktivera säkerhetsstandarder kan göra det genom att uppdatera funktionen under **Azure Active Directory > Egenskaper.** När funktionen har aktiverats av administratören aktiveras den inte automatiskt.

- En varning visas om versionen av Azure AD Anslut i Office 365 Germany-portalen och i Office 365-portalen när klientorganisationen migreras. Det här kan ignoreras om versionsvarningen inte längre visar varningen när migreringen är slutförd. Om det finns en varning måste Azure AD-Anslut uppdateras, antingen före eller efter migreringen. Varningsmeddelandet säger: "Vi upptäckte att du använder ett inaktuellt katalogsynkroniseringsverktyg. Vi rekommenderar att du går till Microsoft Download Center för att hämta den senaste versionen av Azure AD Anslut".

## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365 i de nya tyska datacenterområdena](ms-cloud-germany-transition.md)
- [Migreringshjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du in för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kundupplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom övergången:

- [Åtgärder och påverkan i migreringsfaser](ms-cloud-germany-transition-phases.md)
- [Ytterligare arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Molnappar:

- [Information om Dynamics 365-migreringsprogram](/dynamics365/get-started/migrate-data-german-region)
- [Power BI i migreringsprogrammet](/power-bi/admin/service-admin-migrate-data-germany)
- [Komma igång med din Microsoft Teams uppgradering](/microsoftteams/upgrade-start-here)