---
title: Ge distansarbetare goda förutsättningar
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Konfigurera infrastrukturen och säkerheten som gör att dina anställda kan arbeta på distans på valfri plats och när som helst.
ms.openlocfilehash: b86071b7e5a6101c328b43177e965856f74995d5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809701"
---
# <a name="empower-remote-workers"></a>Ge distansarbetare goda förutsättningar

*Det här scenariot är obligatoriskt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

Att göra det möjligt för personalen att jobba på distans på ett smidigt och säkert sätt är viktigt för många organisationer för att spara på kontorsyta, rekrytera och behålla personal som inte kan eller vill flytta och minska personalen pendling, vilket ger de anställda mer tid att vara produktiva och till stressminskade aktiviteter utanför arbetet.

Distansarbete kan betyda flera olika saker, till exempel:

- Anställda som ibland är borta från kontoret på konferenser eller kundmöten.
- Vissa anställda som arbetar heltid på distans.
- En fullständigt fjärransluten organisation där det inte finns något kontor och alla medarbetare arbetar på distans.

En kombination av funktioner i Microsoft 365 Enterprise ger dina distansarbetare goda förutsättningar på ett mycket samarbetsinriktat sätt, till exempel:

- Onlinemöten och chattsessioner.
- Delade arbetsytor för molnbaserad fillagring med global tillgänglighet och samarbete i realtid.
- Delade uppgifter och arbetsflöden för att dela upp arbetet och få saker gjorda.

Microsoft 365 Enterprise innehåller följande starka säkerhetsfunktioner:

- Tvingande autentiseringskrav, identifiera och svara på högriskinloggningar och blockera valda appar och icke-kompatibla enheter.
- Krypterade anslutningar och digitala tillgångar i molnet.
- Behörigheter för att definiera vilka som kan göra vad med filer.
- Skydd mot dataförlust (DLP) för att förhindra läckage av strikt reglerade data.

För att möta dessa kriterier för distanspersonal använder du följande Microsoft 365 Enterprise-funktioner:

- Användaridentitet och inloggningssäkerhet
  - Användarkonton i Azure Active Directory (Azure AD) med multifaktorautentiering (MFA)
  - Principer för villkorsstyrd åtkomst för att kräva MFA för riskfyllda inloggningar
- Samarbetsplattformar
  - Microsoft Teams, SharePoint och OneDrive, med vilka distansarbetare kan schemalägga och delta i videobaserade onlinemöten och arbeta med samma dokument samtidigt
- Säker åtkomst till resurser
  - Grupper och behörigheter för Teams, SharePoint-webbplatser och OneDrive så att bara autentiserade och tillåtna användare har åtkomst
- Skydd mot läckta filer
  - Office 365 DLP-principer
  - Känslighetsetiketter för kryptering och behörigheter som följer med filer
- Enhetshantering och säkerhet med Microsoft Intune
  - Registrering för hanterade enheter
  - Appinställningar för personliga enheter
  - Enhets- och apprinciper
- Produktivitetsappar för enheter
  - Office 365 ProPlus-appar för samarbetsupplevelser med Teams, SharePoint och OneDrive 
- Windows 10 Enterprise
  - Omfattande säkerhetsfunktioner för att skydda mot cyberattacker och förhindra dataläckage
- Åtkomst till onlineappar
  - Organisationer som har hybrididentitet kan använda Azure AD-programproxy istället för VPN-anslutningar (virtuellt privat nätverk)

I följande faser får du stegvisa anvisningar om hur du distribuerar funktionen för Microsoft 365 Enterprise för fjärråtkomst och inför funktionen för distansarbetare. Om du redan har distribuerade element för dessa faser ser du till de uppfyller de angivna kraven innan du går vidare till nästa del.

<a name="poster"></a> En sammanfattning på sida av det här scenariot finns i [affischen Ge distansarbetare goda förutsättningar](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf).

[![Ge distansarbetare goda förutsättningar (affisch)](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)

Du kan också ladda ned den här affischen i [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)- eller [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/empower-people-to-work-remotely/Empower-Remote-Workers-Poster.pptx)-format och skriva ut den i pappersstorleken letter, legal eller tabloid (11 x 17).


## <a name="phase-1-deploy-microsoft-365-features-and-capabilities-for-remote-workers"></a>Fas 1: Distribuera Microsoft 365-funktioner för distansarbetare

På grund av bredden och antalet funktioner som krävs för det här scenariot går vi igenom de olika stegen för de element som krävs i avsnitten för grundinfrastrukturen och arbetsbelastningar i [distributionsguiden för Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).

### <a name="step-1-foundation-infrastructure-requirements-for-remote-workers"></a>Steg 1: Krav på grundinfrastrukturen för distansarbetare

I det här steget går vi igenom faserna för [grundinfrastrukturen](deploy-foundation-infrastructure.md) och listar de element som krävs för att möjliggöra distansarbetare.

För [Fas 2: identitet](identity-infrastructure.md) distribuerar du följande användaridentitet:

- För hybrididentitet, användarkonton och grupper synkroniserade från lokal Active Directory Domain Services (AD DS).
- För tilldelning av behörigheter, synkroniserade grupper eller Azure AD-grupper med rätt medlemmar.
- Autentiseringsinställningar, till exempel att kräva MFA.
- Principer för villkorsstyrd åtkomst för att kräva MFA för riskfyllda inloggningar och blockera klienter som inte stöder modern autentisering.

Här är konfigurationsresultatet med de nya identitetselementen markerade.

![Identitetselement för distansarbetare](../media/empower-people-to-work-remotely/remote-workers-id-phase.png)
 
Distribuera följande för [Fas 3: Windows 10 Enterprise](windows10-infrastructure.md):

- Infrastrukturen för att distribuera nya enheter med Windows 10 Enterprise och för att uppgradera dina Windows 7- eller Windows 8.1-enheter till Windows 10 Enterprise
- Aktivera omfattande säkerhetsfunktioner för identitet, hot och informationsskydd

Här är konfigurationsresultatet med Windows 10 Enterprise-enheter.

![Windows 10 Enterprise-element för distansarbetare](../media/empower-people-to-work-remotely/remote-workers-win10-phase.png)
 
För [Fas 4: Office 365 ProPlus](office365proplus-infrastructure.md) distribuerar du infrastrukturen för att installera Office 365 ProPlus eller uppgradera ditt nuvarande Office-paket, till exempel Office 2010 eller Office 2013, till Office 365 ProPlus på organisationens enheter. Det här ger dina användare de bästa säkerhets- och samarbetsfunktionerna.

Här är konfigurationsresultatet med Office 365 ProPlus installerat på enheterna.

![Office 365 ProPlus-element för distansarbetare](../media/empower-people-to-work-remotely/remote-workers-proplus-phase.png)
 
För [Fas 5: Hantering av mobila enheter](mobility-infrastructure.md) distribuerar du enhets- och apphantering med Intune för:

- Registrering av Windows 10 Enterprise-, iOS-, macOS-, Android- och Android Enterprise-enheter så att de får funktioner och säkerhetsinställningar som definieras av organisationen.
- Appinställningar för extra säkerhet och för att tillåta eller blockera appar, även på de anställdas personliga enheter.
- Efterlevnadsprinciper med villkorsstyrd åtkomst för att förhindra anslutning av enheter som inte följer standard.

Här är konfigurationsresultatet med Intune-registrerade enheter och principer markerade.

![Element för hantering av mobila enheter för distansarbetare](../media/empower-people-to-work-remotely/remote-workers-mdm-phase.png)
 
För [Fas 6: Informationsskydd](infoprotect-infrastructure.md) utformat och konfigurera skydd för dina digitala enheter med:

- Office 365 DLP-principer.
- Office 365-känslighetsetiketter för kryptering och behörigheter som följer med filer.

Här är konfigurationsresultatet DLP-principer och känslighetsetiketter markerade.

![Informationsskyddselement för distansarbetare](../media/empower-people-to-work-remotely/remote-workers-ip-phase.png)
 
För åtkomst till lokala appar kan du använda [Azure AD-programproxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy), som kräver en hybrididentitetsmiljö.

Här är konfigurationsresultatet med komponenterna för programproxy markerade.

![Programproxyelement för distansarbetare](../media/empower-people-to-work-remotely/remote-workers-app-proxy.png)
 
### <a name="step-2-workloads-for-remote-workers"></a>Steg 2: Arbetsbelastningar för distansarbetare

För [Exchange Online](exchangeonline-workload.md) distribuerar du Exchange Online-postlådor till var och en av dina användare.

För [Teams](teams-workload.md) distribuerar du Teams till dina användare och grupper.

För [SharePoint och OneDrive](sharepoint-online-onedrive-workload.md) distribuerar du SharePoint-gruppwebbplatser eller kommunikationswebbplatser och OneDrive-mappar.

Här är konfigurationsresultatet med arbetsbelastningar markerade.

![Microsoft 365-arbetsbelastningar för distansarbetare](../media/empower-people-to-work-remotely/remote-workers-workloads.png)
 
### <a name="deployment-results"></a>Distributionsresultat

Efter distribution av grundinfrastrukturen och arbetsbelastningar och rullat ut Windows 10 Enterprise och Office 365 ProPlus gäller följande för distansarbetare:

- De omfattas av starkt autentiserings- och identitetsskydd.
- De har de senaste och säkraste versionen av Windows på sina Windows-enheter.
- De har den senaste produktversionen av Office-paketet på sina enheter.
- De omfattas av principer för apphantering och enhetsefterlevnad.
- De omfattas av DLP-principer och begränsningar.
- De kan tilldela känslighetsetiketter för kryptering och behörigheter som följer med filer och e-post.
- De kan komma åt lokala appar utan en VPN-anslutning.
- De kan utföra eget arbete och delta i realtidssamarbete med kollegor via chattar, möten och filer i Teams och filer i SharePoint och OneDrive.

När distansarbetarna är offline (inte anslutna till Internet) kan de ändra lokala kopior av filer. När de ansluter till Internet igen synkroniserar OneDrive lokala kopior med de filer som lagras i din Microsoft 365-prenumeration. 

Här är konfigurationsresultatet för distansarbetare i organisationen om du använder hybrididentitet.

![Slutlig konfiguration för distansarbetare i en organisation med hybrididentitet](../media/empower-people-to-work-remotely/remote-workers-hybrid.png) 
 
Här är konfigurationsresultatet för distansarbetare i organisationen om du använder helt molnbaserad identitet.

![Konfiguration för distansarbetare i en organisation med helt molnbaserad identitet](../media/empower-people-to-work-remotely/remote-workers-cloud-only.png)

## <a name="phase-2-drive-user-adoption-for-remote-workers"></a>Fas 2: Driva på distansarbetares användning

Nu när grundinfrastrukturen och arbetsbelastningarna är på plats är det dags att driva på den pågående användningen av de här funktionerna för dina distansarbetare så att de kan vara produktiva var som helst och när som helst.

### <a name="step-1-train-your-users"></a>Steg 1: Utbilda dina användare

Utbilda distansarbetare i följande:

- Lämpliga inloggningssätt, till exempel MFA-registrering, och hur inloggningar kan utmanas när en risk upptäcks.
- Användningen av enheter och hur principer kan användas för att blockera åtkomsten för enheter som inte följer standard.
- Användningen av tillåtna appar och hur Intune-apprinciper kan användas för att blockera appar.
- Windows 10 Enterprise-säkerhetsfunktioner.
- Hur Outlook ska användas för e-post och kalenderfunktioner.
- Hur [Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) ska användas för chatt, videobaserade konferenser, dokumentdelning och trådade konversationer.
- Hur SharePoint-gruppwebbplatser eller -kommunikationswebbplatser och OneDrive-mappar ska användas för att bläddra bland filer i en användares bibliotek och sådana som tillhör en grupp.
- Hur känslighetsetiketter ska användas och tillämpas för filer som innehåller känsliga eller strikt reglerade data, för båda lokala och onlineversioner av filer.

I den här utbildningen ska det ingå praktiska övningar så att dina elever kan uppleva funktionerna och deras resultat.

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-worker-feedback"></a>Steg 2: Utföra regelbundna granskningar av användning och hantera feedback för medarbetare

I veckorna efter utbildningen:

- Snabbt hantera feedback för distansarbetare och finjustera principer och konfigurationer.
- Analysera användning för team, SharePoint-webbplatser, och OneDrive-mappar och jämföra den med användarförväntningar.
- Kontrollera att känsliga eller strikt reglerade filer har etiketterats korrekt med lämplig känslighetsetikett.

Utbilda dina användare efter behov.

### <a name="user-adoption-results"></a>Användningsresultat

Dina distansarbetare kan använda sina Windows 10 Enterprise-enheter eller andra enheter och Office 365 ProPlus för att komma åt och arbeta med delade Microsoft 365 Enterprise-molntjänster och -resurser i en säker miljö, där de möts, skapar och samarbetar i realtid.

## <a name="see-also"></a>Se även

[Arbetsbelastningar och scenarier](deploy-workloads.md)

[Produktivitetsbiblioteket för Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)

[Distributionsguide](deploy-microsoft-365-enterprise.md)
