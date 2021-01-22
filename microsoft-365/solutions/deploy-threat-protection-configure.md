---
title: Steg för att konfigurera skyddsfunktioner för hot i Microsoft 365
description: Lär dig hur du distribuerar skyddstjänster för hot och funktioner i Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 492db78c9aea881ae05dbc66f5e84ad98629b923
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931992"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Konfigurera skyddsfunktioner för hot i Microsoft 365

Följ de här stegen för att konfigurera skydd mot hot i Microsoft 365.


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Steg 1: Konfigurera principer för multifaktorautentisering och villkorsstyrd åtkomst

[Multifaktorautentisering](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) kräver att användarna verifierar sin identitet med ett telefonsamtals- eller autentiseringsapp. [Villkorsstyrda åtkomstprinciper](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) definierar vissa krav som måste uppfyllas för att användare ska kunna komma åt appar och data i Microsoft 365. MFA- och villkorsstyrda åtkomstprinciper fungerar tillsammans för att skydda din organisation. Om någon till exempel försöker logga in från en mobil enhet med ett konto som inte är aktiverat för MFA, och en princip för villkorsstyrd åtkomst kräver att MFA används, hindras den användaren från att logga in.  

Microsoft har testat och rekommenderar en viss uppsättning villkorsstyrda åtkomst och relaterade principer för att skydda åtkomsten till alla dina SaaS-program, särskilt Microsoft 365. Principer rekommenderas för grundläggande, känsligt och starkt reglerat skydd. Börja med att implementera principerna för baslinjeskydd. 


[ ![ Vanliga principer för konfigurering av identitet och enhetsåtkomst](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [Visa en större version av den här bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Så här implementerar du baslinjeskydd för Microsoft 365

![Process för distribution av baslinjeskydd](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [Konfigurera förutsättningar, inklusive Azure Identity Protection.](../security/office-365-security/identity-access-prerequisites.md)
2. [Konfigurera vanliga principer för identitets- och enhetsåtkomst](../security/office-365-security/identity-access-policies.md) för grundläggande skydd.
3. Konfigurera principer för [gästanvändare,](../security/office-365-security/identity-access-policies-guest-access.md) [Microsoft Teams,](../security/office-365-security/teams-access-policies.md) [Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)och [SharePoint Online och OneDrive.](../security/office-365-security/sharepoint-file-access-policies.md)

### <a name="more-information-about-protecting-identities"></a>Mer information om hur du skyddar identiteter

- [Konfigurationer för identitets- och enhetsåtkomst](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Säkerhetsvägledning för Azure MFA](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>Steg 2: Konfigurera Microsoft Defender för identitet

[Microsoft Defender för](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) identitet är en molnbaserad säkerhetslösning som fungerar med dina lokala [Azure Active Directory-signaler](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) för att identifiera, identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga Insider-åtgärder riktade till din organisation.

Microsoft Defender för identitet aktiverar säkerhetsåtgärder (SecOps) analytiker och säkerhetsexperter som har svårt att identifiera avancerade attacker i hybridmiljöer för att:
- Övervaka användare, entitetsbeteende och aktiviteter med utbildningsbaserade analyser.
- Skydda användaridentiteter och inloggningsuppgifter som lagras i Active Directory.
- Identifiera och undersök misstänkta användaraktiviteter och avancerade attacker under alla attackfaserna.
- Ge tydlig information om incidenten på en enkel tidslinje för snabb prioritering.

### <a name="to-set-up-microsoft-defender-for-identity"></a>Konfigurera Microsoft Defender för identitet

![Process för distribution av Microsoft Defender för identitet](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [Konfigurera Microsoft Defender för identitet för](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) att skydda dina primära miljöer.
2. Skydda alla dina [domänkontrollanter](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) och [skogar.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)
3. Integrera [Microsoft Defender för identitetsaviseringar](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) i ditt säkerhetsarbetsflöde (SecOps).

### <a name="more-information-about-microsoft-defender-for-identity"></a>Mer information om Microsoft Defender för identitet

- [Vad är Microsoft Defender for Identity?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Video: Introduktion till Microsoft Defender för identitet](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Distribution av Microsoft Defender för identitet](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>Steg 3: Aktivera Microsoft 365 Defender

[Microsoft 365 Defender kombinerar](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) signaler och teknikfunktioner till en enda lösning. Med den integrerade Microsoft 365 Defender-lösningen kan säkerhetspersonal samlas ihop de hotsignaler som var och en av dessa produkter får och fastställa hotens fullständiga omfattning och påverkan. hur den angavs i miljön, vad den påverkades och hur den för närvarande påverkar organisationen. Microsoft 365 Defender vidtar automatisk åtgärd för att förhindra eller stoppa attacken och självdådande postlådor, slutpunkter och användaridentiteter.

Microsoft 365 Defender ger en enhetlig lösning för aviseringar, incidenter, automatisk undersökning och svar samt avancerad sökning i olika arbetsbelastningar (Microsoft Defender för identitet, Microsoft Defender för Office 365, Microsoft Defender för slutpunkt och Microsoft Cloud App-säkerhet) i en enda fönsterruta. När du har konfigurerat en eller flera av dina Defender för Office 365-tjänster aktiverar du Microsoft 365 Defender. Nya funktioner läggs kontinuerligt till i Microsoft 365 Defender. överväg att registrera dig för att få förhandsgranskningsfunktioner.

### <a name="to-set-up-microsoft-365-defender"></a>Konfigurera Microsoft 365 Defender

![Process för distribution av Microsoft 365 Defender](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [Granska förutsättningarna.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)
2. [Aktivera Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)
3. [Registrera dig för förhandsgranskningsfunktioner.](https://docs.microsoft.com/microsoft-365/security/mtp/preview)

### <a name="more-information-about-microsoft-365-defender"></a>Mer information om Microsoft 365 Defender

- [Vad är Microsoft 365 Defender?](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Nyheter i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>Steg 4: Konfigurera Microsoft Defender för Office 365

[Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) skyddar organisationen mot skadliga hot i e-postmeddelanden (bifogade filer och URL-adresser), Office-dokument och samarbetsverktyg. I följande tabell visas funktioner och funktioner i Microsoft Defender för Office 365 som ingår i Microsoft 365 E5:

|Funktioner för konfiguration, skydd och identifiering|Funktioner för automatisering, undersökning, åtgärd och utbildning|
|---|---|
|[Säkra bifogade filer](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[Säkra länkar](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[Säkra dokument](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[ATP för SharePoint, OneDrive och Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[Skydd mot nätfiske i Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[Hotspårare](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[Hotutforskaren](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[Automatiska undersökningar och svar](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[Attacksimulator](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

Med Microsoft Defender för Office 365 kan personer i hela organisationen kommunicera och samarbeta säkrare med hotskydd för e-postinnehåll och Office-dokument.

### <a name="to-set-up-microsoft-defender-for-office-365"></a>Konfigurera Microsoft Defender för Office 365

![Process för distribution av Microsoft Defender för Office 365](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [Konfigurera och konfigurera principer för Microsoft Defender för Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)
2. [Visa och använda dina Microsoft Defender för Office 365-rapporter.](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)
3. [Använd funktioner för hotundersökning och -svar.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Mer information om Microsoft Defender för Office 365

- [Översikt över Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Vad är nytt i Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>Steg 5: Konfigurera Microsoft Defender för slutpunkt

[Microsoft Defender för Slutpunkt](https://docs.microsoft.com/windows/security/threat-protection) skyddar organisationens enheter (kallas även slutpunkter) från cyberhot, avancerade attacker och databrott. Säkerhetsteam kan bli effektivare när det gäller att hantera säkerheten för slutpunkterna. Robusta verktyg hjälper organisationer att hålla koll på system som inte fungerar med hjälp av sårbarhetsidentifiering [med hantering av hot och sårbarhet.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Automatiserade funktioner för identifiering och åtgärder, till exempel minskning av [attackytan,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)nästa [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) [generations](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) [skydd,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)slutpunktsidentifiering och -svar, samt automatiserad undersökning och åtgärd hjälper till att skydda dina enheter från skadlig programvara. Utöver dessa funktioner kan kunder få proaktiva meddelanden och rådgöra med Microsoft Threat Experts på begäran, som en del av den hanterade söktjänsten. 


### <a name="set-up-microsoft-defender-for-endpoint"></a>Konfigurera Microsoft Defender för Slutpunkt

![Process för distribution av Microsoft Defender för slutpunkt](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [Förbereda Microsoft Defender för slutpunktsdistribution.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases)
2. [Konfigurera Microsoft Defender för slutpunktsdistribution](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [Introducera till Microsoft Defender för slutpunktstjänsten.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding)
4. [Utför de viktigaste administrativa säkerhetsuppgifterna.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Mer information om Microsoft Defender för Slutpunkt

- [Läs mer om Microsoft Defender för Slutpunkt.](https://docs.microsoft.com/windows/security/threat-protection)
- [Prova Microsoft Defender för utvärderingslabb med slutpunkt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab)

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Steg 6: Konfigurera Microsoft Cloud App Security

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) är en Cloud Access Security Broker som har stöd för logginsamling, API-kopplingar och omvänd proxy. Microsoft Cloud App Security ger full insyn, kontroll över dataresa och avancerad analys för att identifiera och bekämpa cyberhot i alla dina molntjänster. Med Microsoft Cloud App Security kan dina säkerhetsåtgärder skydda organisationens känsliga information, skydda mot cyberhot, upptäcka och övervaka appar som har åtkomst till organisationens data samt se till att organisationens molnappar uppfyller efterlevnadskrav.

### <a name="set-up-microsoft-cloud-app-security"></a>Konfigurera Microsoft Cloud App Security

![Process för distribution av Microsoft Cloud App Security](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [Konfigurera portalen och andra grundläggande krav.](https://docs.microsoft.com/cloud-app-security/general-setup)
2. [Konfigurera identifiering av molnet och](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) anslut [appar.](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)
3. [Distribuera programkontroll för villkorsstyrd åtkomst för aktuella program.](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)
4. [Använd undersökningsverktygen och instrumentpanelerna.](https://docs.microsoft.com/cloud-app-security/investigate)

### <a name="more-information-about-microsoft-cloud-app-security"></a>Mer information om Microsoft Cloud App Security

- [Granska nya funktioner.](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Läs mer om Microsoft Cloud App Security.](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

## <a name="step-7-monitor-status-and-take-actions"></a>Steg 7: Övervaka status och vidta åtgärder

När du har konfigurerat och distribuerat dina skyddstjänster och funktioner för hot är nästa steg att övervaka identifiering av hot och vidta lämpliga åtgärder. Den bästa utgångspunkten är Microsoft 365 säkerhetscenter ( ), där du kan övervaka och hantera säkerhet i [https://security.microsoft.com](https://security.microsoft.com) dina Microsoft-identiteter, data, enheter, appar och infrastruktur. 

![Microsoft 365 Säkerhetscenter](../media/solutions-architecture-center/m365-security-center.png)

Microsoft 365 Säkerhetscenter är specifikt avsett för säkerhetsadministratörer och säkerhetsteam. I Säkerhetscenter för Microsoft 365 kan du:
- Visa organisationens övergripande säkerhetshälsa med [Secure Score.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)
- [Övervaka och visa rapporter](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) om status för dina identiteter, data, enheter, appar och infrastruktur.
- Koppla punkterna i aviseringar via [incidenter.](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- Använd [automatisk undersökning och åtgärd för](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) att hantera hot.
- [Proaktivt leta efter hot, till exempel intrångsförsök](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)eller intrångsaktivitet som påverkar e-post, data, enheter och identiteter.
- [Förstå de senaste attackkampanjerna](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) och teknikerna med hotanalyser.
- ... med mera!

### <a name="more-information-about-the-microsoft-365-security-center"></a>Mer information om Säkerhetscenter för Microsoft 365

- [Kom igång med Säkerhetscenter för Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)
- [Övervaka och visa rapporter.](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)
- [Se säkerhetsportalerna i Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="step-8-train-users"></a>Steg 8: Utbilda användare

Utbildning av användare kan spara dina användare och säkerhetsåtgärder team mycket tid och frustration. Smarta användare har mindre chans att öppna bifogade filer eller klicka på länkar i tveksama e-postmeddelanden, och det är troligare att de undviker misstänkta webbplatser. 

The Harvard School [Cybersecurity Campaign Handbook är](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) en utmärkt vägledning om att etablera en stark säkerhetskultur i organisationen, inklusive utbildning av användare för att identifiera nätfiskeattacker. 

I Microsoft 365 finns följande resurser för att informera användarna i organisationen:

|Begrepp  |Resurser  |
|---------|---------|
|Microsoft 365     |[Anpassningsbara utbildningsvägar](https://docs.microsoft.com/office365/customlearning/) <p>De här resurserna kan hjälpa dig att samla utbildning för slutanvändarna i organisationen        |
|Microsoft 365-säkerhet |[Learning module: Secure your organization with built-in, intelligent security from Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>I den här modulen kan du beskriva hur Säkerhetsfunktioner i Microsoft 365 fungerar tillsammans och att uttrycka fördelarna med dessa säkerhetsfunktioner. |
|Multifaktorautentisering     | [Tvåstegsverifiering: Vad är ytterligare verifieringssida?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Den här artikeln hjälper slutanvändarna att förstå vad multifaktorautentisering är och varför den används i organisationen.    |

Förutom den här vägledningen rekommenderar Microsoft att dina användare gör som beskrivs i den här artikeln: Skydda ditt konto och dina [enheter från hackare och skadlig programvara.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) Dessa åtgärder omfattar:
- Använda starka lösenord
- Skydda enheter 
- Aktivera säkerhetsfunktioner på PC-datorer med Windows 10 och Mac (för ohanterade enheter)
    
Microsoft rekommenderar även att användare skyddar sina personliga e-postkonton genom att vidta de åtgärder som rekommenderas i följande artiklar:
- [Skydda ditt Outlook.com e-postkonto](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Skydda ditt Gmail-konto med tvåstegsverifiering](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
