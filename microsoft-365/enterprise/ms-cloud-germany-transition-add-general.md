---
title: Ytterligare allmän information för migrering från Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: 'Sammanfattning: ytterligare allmän information om tjänster när du flyttar från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster i det nya tyska data centret.'
ms.openlocfilehash: 6fa09165f8aaa68e0f9fc567d96a4e53baaa594e
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551788"
---
# <a name="additional-general-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Ytterligare allmän information för migrering från Microsoft Cloud Deutschland

I följande avsnitt finns mer information om tjänster, för hands-arbete och kund upplevelse.

## <a name="azure-active-directory"></a>Azure Active Directory

För att slutföra flytten från det tyska Azure-molnet till det offentliga Azure Cloud-molnet rekommenderar vi att du uppdaterar slut punkten för autentiseringscookien, Azure Active Directory (Azure AD) och MS Graph slut punkter för dina program uppdateras till de kommersiella molnen när OpenID Connect (OIDC)-slut punkten `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` börjar rapportera kommersiella moln slut punkter. 
 
**När ska jag göra den här ändringen?**

Du får ett meddelande i Azure/Office Portal när din klient organisation har migrerat från tyskt moln till det kommersiella molnet. Det har gått 30 dagar efter att du har fått detta meddelande för att slutföra dessa uppdateringar, så att din app fortsätter att fungera för klient organisationer som migreras från Azure Germany-molnet till det offentliga Azure-molnet.
 
Det finns tre villkor för att du ska kunna uppdatera inloggnings myndigheten:

 - OIDC identifierings slut punkt för din klient organisation `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returnerar slut punkter för Azure AD Public-moln.

 - Om klient organisationen har kon figurer ATS för Federation uppdateras AD FS (Active Directory Federation Services) så att den synkroniseras med Azure AD Public. Du kan följa anvisningarna för att uppdatera Azure AD Connect-inställningar för den här ändringen.

 - Resurs program som används av dina program ändras till att acceptera tokens som är signerade av både Azure AD Tyskland och Azure AD Public.
 
**Vilka program?**

Ett program kan vara något av följande:

- En enda sida (SPA)
- Webb program som loggar in i användare
- Webb program som anropar webb-API
- Skyddad webb-API
- Webb-API som anropar webb-API
- Skriv bords program
- Daemon-app
- Mobilapp
 
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

    - Azure PowerShell
    - Azure AD PowerShell (MSOnline)
    - Azure AD PowerShell (AzureAD)
    - Azure CLI
 
**Vad händer med program som jag publicerar?**

Om du publicerar ett program som är tillgängligt för användare utanför din klient organisation kan du behöva ändra registreringen för att säkerställa kontinuitet. Andra klient organisationer som använder programmet kan flyttas vid en annan tidpunkt än din klient organisation. Om du inte vill att de ska förlora åtkomsten till ditt program måste du godkänna att ditt program synkroniseras från Azure Tyskland till Azure Public.

### <a name="additional-considerations"></a>Ytterligare överväganden

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

## <a name="exchange-online"></a>Exchange Online 

- `myaccount.msft.com` fungerar bara efter snabbmigrering av Office 365. Länkar ger fel meddelandet "något gick fel" till den tiden.

- Användare av Outlook Web App som har till gång till en delad post låda i den andra miljön (till exempel att en användare i Tyskland får åtkomst till en delad post låda i den globala miljön) uppmanas att verifiera en andra gång. Användaren måste först verifiera och komma åt post lådan i `outlook.office.de` och sedan öppna den delade post lådan `outlook.office365.com` . De måste verifiera en andra gång när de använder de delade resurserna som finns på den andra tjänsten.

- Om du har en delad post låda i Outlook genom att använda **fil > information > Lägg till konto**, kan det hända att det inte går att använda REST API för befintliga Microsoft Cloud-Deutschland kunder eller dem i över gången `https://outlook.office.de/api/v2.0/Me/Calendars` . Kunder som vill lägga till ett konto för att Visa kalender behörigheter kan lägga till register nyckel enligt beskrivningen i [användar miljö ändringar för att dela en kalender i Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) för att kontrol lera att åtgärden lyckas. Denna register nyckel kan distribueras till hela organisationen med hjälp av grup princip.

- Under migreringsprocessen kan du använda PowerShell-cmdleten **New-migrationEndpoint**, **set-migrationEndpoint** och **test-MigrationsServerAvailability** kan resultera i fel (fel på proxy). Det här inträffar om medlings post lådan har migrerats till över hela världen men administratörs post lådan inte har eller vice versa. Lös problemet genom att använda medlings post lådan som cirkulations fältet i **ConnectionUri** när du skapar klientens PowerShell-session. Till exempel: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Om du använder Exchange Online hybrid:

    - Du måste köra hybrid konfigurations guiden igen (HCW) för att uppdatera lokal konfiguration mot Microsoft Cloud Deutschland före över gången och sedan köra HCW vid rensning mot Office 365-tjänsterna. Ytterligare DNS-uppdateringar kan krävas om du använder anpassade domäner.

Om du vill ha mer information om åtgärder som krävs under migrations fasen av denna arbets belastning eller hur det påverkar administrationen eller användningen kan du läsa avsnittet om Exchange Online i [åtgärderna för migrering och påverkan](ms-cloud-germany-transition-phases.md#exchange-online).

## <a name="office-services"></a>Office-tjänster

Den senast använda tjänsten i Office är en snabbmigrering från Tyskland-tjänsten till Office 365-tjänster, inte en migrering. Endast MRU-länkar från Office 365-sidan visas efter migrering från Office.com-portalen. MRU-länkar från Tyskland-tjänsten visas inte som MRU-länkar i Office 365-tjänster. I Office 365 är MRU-länkar endast tillgängliga när klient migreringen har slutförts.

## <a name="sharepoint-online-and-onedrive"></a>SharePoint Online och OneDrive

- När SharePoint Online-migreringen har slutförts till tyska-regionen återskapas data indexet. Funktioner som är beroende av Sök index kan påverkas när Omindexering är klar.

- Om din organisation ändå använder SharePoint 2010-arbetsflöden fungerar de inte längre efter 31 december 2021. SharePoint 2013-arbets flöden fortsätter att fungera men är inaktiverat som standard för nya klient organisationer som börjar den 1 november 2020. När migreringen till SharePoint Online-tjänsten är klar rekommenderar vi att du går vidare till Power automatisering eller andra lösningar som stöds.

- När migreringen av OneDrive har genomförts till den tyska regionen återskapas data indexet. Funktioner som är beroende av Sök index kan påverkas under Omindexering.


## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska Data Center-regionerna](ms-cloud-germany-transition.md)
- [Hjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kund upplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom över gången:

- [Åtgärder och konsekvenser för migreringen](ms-cloud-germany-transition-phases.md)
- [Övrig för hands arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information om [tjänster](ms-cloud-germany-transition-add-general.md), [enheter](ms-cloud-germany-transition-add-devices.md), [erfarenheter](ms-cloud-germany-transition-add-experience.md)och [AD FS](ms-cloud-germany-transition-add-adfs.md).

Molnappar:

- [Information om programmet för Dynamics 365 migration](https://aka.ms/d365ceoptin)
- [Information om datamigreringshanteraren för Power BI](https://aka.ms/pbioptin)
- [Komma igång med din uppgradering av Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
