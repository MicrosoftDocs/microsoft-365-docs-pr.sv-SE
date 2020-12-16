---
title: Ytterligare Azure Active Directory-information för migreringen från Microsoft Cloud Deutschland
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
description: 'Sammanfattning: ytterligare Azure Active Directory-information när du flyttar från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster i det nya tyska data centret.'
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688838"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Ytterligare Azure Active Directory-information för migreringen från Microsoft Cloud Deutschland

För att slutföra flytten från det tyska Azure-molnet till det offentliga Azure Cloud-molnet rekommenderar vi att du uppdaterar slut punkten för autentiseringscookien, Azure Active Directory (Azure AD) och MS Graph slut punkter för dina program uppdateras till de kommersiella molnen när OpenID Connect (OIDC)-slut punkten `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` börjar rapportera kommersiella moln slut punkter. 
 
**När ska jag göra den här ändringen?**

Du får ett meddelande i Azure/Office Portal när din klient organisation har migrerat från tyskt moln till det kommersiella molnet. Det har gått 30 dagar efter att du har fått detta meddelande för att slutföra dessa uppdateringar, så att din app fortsätter att fungera för klient organisationer som migreras från Azure Germany-molnet till det offentliga Azure-molnet.
 
Det finns tre villkor för att du ska kunna uppdatera inloggnings myndigheten:

 - OIDC identifierings slut punkt för din klient organisation `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returnerar slut punkter för Azure AD Public-moln.

 - Om klient organisationen har kon figurer ATS för Federation uppdateras AD FS (Active Directory Federation Services) så att den synkroniseras med Azure AD Public. Du kan följa anvisningarna för att uppdatera Azure AD Connect-inställningar för den här ändringen.

 - Resurs program som används av dina program ändras till att acceptera tokens som är signerade av både Azure AD Tyskland och Azure AD Public.
 
**Vilka program?**

Ett program kan vara något av följande:

- [En enda sida (SPA)](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [Webb program som loggar in i användare](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [Webb program som anropar webb-API](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [Skyddad webb-API](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [Webb-API som anropar webb-API](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [Skriv bords program](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [Daemon-app](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [Mobilapp](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> När ett program växlar till att använda `login.microsoftonline.com` som auktoritet kommer tokens att signeras av den här nya myndigheten. Om du har ett resurs program som andra appar ringer till måste du tillåta verifiering av lax-token. Det innebär att din app måste tillåta att tokens som är signerade av både Azure AD Germany och offentliga Azure AD-molnen. Denna lax krävs tills alla klient program som anropar tjänsten är fullständigt migrerade till det offentliga Azure AD-molnet. Efter migrering måste resurs programmet bara acceptera tokens som är signerade av Azure AD Public Cloud.

**Vad behöver jag uppdatera?**

1. Om du är värd för ett program i Azure Tyskland som används för att autentisera användare av Azure Tyskland eller Office 365 Germany kontrollerar du att `https://login.microsoftonline.com` används som auktoritet i verifierings kontexten.

    - Se kontext text för Azure AD.
    - Detta gäller både för att verifiera program varan och för att verifiera alla API: er som ditt program kan anropa (det vill säga Microsoft Graph, Azure AD Graph, Azure Resource Manager).

2. Uppdatera Azure AD Graph-slutpunkten så att den blir `https://graph.windows.net` .

3. Uppdatera slut punkten för MS Graph `https://graph.microsoft.com` .

4. Uppdatera eventuella tyska moln slut punkter (till exempel dem för Exchange Online och SharePoint Online) som används av dina program för att vara de som tillhör det offentliga molnet.

5. Uppdatera miljöparametrar för att vara `AzurePublic` (i stället för `AzureGermany` ) i administrativa verktyg och skript för:

    - [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline)](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
**Vad händer med program som jag publicerar?**

Om du publicerar ett program som är tillgängligt för användare utanför din klient organisation kan du behöva ändra registreringen för att säkerställa kontinuitet. Andra klient organisationer som använder programmet kan flyttas vid en annan tidpunkt än din klient organisation. Om du inte vill att de ska förlora åtkomsten till ditt program måste du godkänna att ditt program synkroniseras från Azure Tyskland till Azure Public.

## <a name="additional-considerations"></a>Ytterligare överväganden

Här är några ytterligare saker du bör tänka på för Azure AD:

- För federerad inloggningsautentisering:

  - Du får inte skapa, befordra eller degradera en federerad domän när över gången till klient organisationen pågår. När migreringen till Azure AD-tjänsten är slutförd (klient organisationen är fullständigt fullständig) kan du återuppta hanteringen av federerade domäner.

  - Om du använder federerad trafik med AD FS (Active Directory Federation Services) bör du inte göra ändringar i de certifikat utfärdare som används för all identifiering med din lokala Active Directory Domain Services (AD DS) under migreringen. Ändring av utfärdares-URI: er leder till autentiserings fel för användare i domänen. Utfärdares-URI: er kan ändras direkt i AD FS eller när en domän konverteras från hanterad till federerad och vice versa. Microsoft rekommenderar att kunderna inte lägger till, tar bort eller konverterar en federerad domän i den Azure AD-klient som migreras. Utfärdares-URI: er kan ändras när migreringen är fullständigt fullständig.

- För nätverk:

  - Det går inte att skapa IPv6-namngivna nätverk i Azure-portalen `http://portal.microsoftazure.de/` . Använd Azure-portalen för `https://portal.azure.com` att skapa nätverk med IPv6-namn.
 
   - Du kan inte skapa betrodda IP-adressintervall för tjänste inställningar för Azure Multi-Factorion (MFA) från Microsoft Cloud Deutschland-portalen. Använd Azure AD-portalen för Office 365-tjänster för att skapa betrodda IP-adressintervall för Azure MFA.


- För villkorlig åtkomst: 

  - Principer för villkorsstyrd åtkomst med följande anslag-kontroller stöds inte förrän migreringen till Office 365-tjänster är slutförd (efter den [slutförda Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration-fasen):

    - Kräv kompatibel enhet
    - Kräv godkänt program
    - Kräv program skydds policy
    
  - Princip gränssnittet för villkorsstyrd åtkomst ger en falsk varning om säkerhets standarden aktive ras för klient organisationen även om den är inaktive rad och principer för villkorsstyrd åtkomst redan finns för klient organisationen. Du bör ignorera varningen eller använda Office 365-tjänst portalen för att hantera principer för villkorsstyrd åtkomst. 

- Det går endast att använda Intune-slutpunkter för slut punkter efter att klient migreringen har slutförts, inklusive alla migreringar av kontors belastning.

- Microsoft Cloud Deutschland användare som använder appen för mobilapp för MFA-begäranden se användarens ObjectId (ett GUID) i stället för användarens huvud namn (UPN) i Microsoft Authenticator-appen. När migreringen av Azure AD-innehavaren är färdig och finns i Office 365-tjänsterna visas användarens UPN-värden. Befintliga Microsoft Authenticator-konton kommer att fortsätta att Visa användaren ObjectId, men de fortsätter att arbeta med aviseringar om mobila appar. 

- För klient organisationer som skapas efter 22 oktober 2019 kan säkerhets standarden aktive ras automatiskt för klient organisationen när den migreras till Office 365-tjänsten. Klient organisationens administratörer kan välja att lämna säkerhets standarder aktiverat och registrera sig för MFA, eller så kan de inaktivera funktionen. Mer information finns i [inaktivera säkerhets inställningar](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults). 

  > [!NOTE]
  > Organisationer som inte är automatiskt aktiverade under migreringen kan ändå vara automatiskt uppdelade när funktionen för att aktivera säkerhets standarder är uppkopplad i Office 365-tjänsten. Administratörer som uttryckligen väljer att inaktivera eller aktivera säkerhets standarder kan göra det genom att uppdatera funktionen under **Azure Active Directory >-egenskaper**. När funktionen är aktive rad av administratören aktive ras den inte automatiskt.

- Det visas ett varnings meddelande om versionen av Azure AD Connect på Office 365 Germany-portalen samt på Office 365-portalen när klient organisationen migreras. Det här kan ignoreras om varningen inte längre visas när migreringen har slutförts. Om det finns en varning, antingen före eller efter migreringen, måste du uppdatera Azure AD Connect. Varnings meddelandet visar att du använder ett föråldrat katalog-Sync-verktyg. Vi rekommenderar att du går till Microsoft Download Center och skaffar den senaste versionen av Azure AD Connect. "

## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska Data Center-regionerna](ms-cloud-germany-transition.md)
- [Hjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kund upplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom över gången:

- [Åtgärder och påverkan i migreringsfaser](ms-cloud-germany-transition-phases.md)
- [Övrig för hands arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information för [Azure AD](ms-cloud-germany-transition-azure-ad.md), [enheter](ms-cloud-germany-transition-add-devices.md), [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS](ms-cloud-germany-transition-add-adfs.md).

Molnappar:

- [Information om programmet för Dynamics 365 migration](https://aka.ms/d365ceoptin)
- [Information om datamigreringshanteraren för Power BI](https://aka.ms/pbioptin)
- [Komma igång med din uppgradering av Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
