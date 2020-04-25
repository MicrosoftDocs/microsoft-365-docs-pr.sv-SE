---
title: Topp 12 uppgifter för säkerhetsteam att stödja att arbeta hemifrån
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: o365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- remotework
description: Skydda företagets e-post och data från cyberhot, inklusive utpressningsartiklar, nätfiske och skadliga bilagor.
ms.openlocfilehash: f2d76fd92ac6d439fd6400a0478028c99ae935eb
ms.sourcegitcommit: 481fb95d8b80cf2102a9c73b21e7effa79e594e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/24/2020
ms.locfileid: "43808841"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>Topp 12 uppgifter för säkerhetsteam att stödja att arbeta hemifrån

Om du är som [Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) och plötsligt får stöd för en i första hand hembaserad arbetsstyrka vill vi hjälpa dig att se till att din organisation arbetar så säkert som möjligt. Den här artikeln prioriterar uppgifter för att hjälpa säkerhetsteam att implementera de viktigaste säkerhetsfunktionerna så snabbt som möjligt. 

Om du är en liten eller medelstor organisation som använder någon av Microsofts affärsplaner läser du dessa resurser i stället:
- [De 10 bästa sätten att skydda Office 365- och Microsoft 365 för företag-abonnemang](../admin/security-and-compliance/secure-your-business-data.md) 
- [Microsoft 365 for Campaigns](https://docs.microsoft.com/microsoft-365/campaigns/?view=o365-worldwide) (innehåller en rekommenderad säkerhetskonfiguration för Microsoft 365 Business)

  
För kunder som använder våra företagsplaner rekommenderar Microsoft att du slutför uppgifterna i följande tabell som gäller för din serviceplan. Om du i stället för att köpa ett Microsoft 365-företagsprogram kombinerar du prenumerationer bör du tänka på följande:
- Microsoft 365 E3 innehåller EMS-E3 och Azure AD P1 (Enterprise Mobility + Security) E3 och Azure AD P1
- Microsoft 365 E5 innehåller EMS E5 och Azure AD P2
  
||**Uppgift**| Alla Office 365 Enterprise-abonnemang|**Microsoft 365 E3** |**Microsoft 365 E5**|
|:-----|:-----|:-----|:-----|:-----|
|1      |[Aktivera MFA (Azure Multi Factor Authentication)](#1-enable-azure-multi-factor-authentication-mfa)   |   ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)  |![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)   | ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|2     | [Skydda mot hot](#2-protect-against-threats) |![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png) |  ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)       | ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)       | 
|3      |  [Konfigurera avancerat hotskydd för Office 365](#3-configure-office-365-advanced-threat-protection)  |   |      |  ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)     | 
|4      | [Konfigurera Azure Advanced Threat Protection (ATP)](#4-configure-azure-advanced-threat-protection)   |   |      |  ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)     | 
|5     |   [Aktivera Microsoft Advanced Threat Protection](#5-turn-on-microsoft-advanced-threat-protection)  |  |      | ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|6      | [Konfigurera Intune-skydd för mobilappar för telefoner och surfplattor](#6-configure-intune-mobile-app-protection-for-phones-and-tablets) |    |  ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)       |  ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)       | 
|7     | [Konfigurera MFA och villkorlig åtkomst för gäster, inklusive Intune-appskydd](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)  |    |  ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)     | ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|8      |  [Registrera datorer i enhetshantering och kräver kompatibla datorer](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)   |  | ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)        | ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)        | 
|9      | [Optimera nätverket för molnanslutning](#9-optimize-your-network-for-cloud-connectivity)  |  ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png) |![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)      |![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)        | 
|10   | [Utbilda användare](#10-train-users) |    ![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png) |![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)      |![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|11 |[Komma igång med Microsoft Cloud App Security](#11-get-started-with-microsoft-cloud-app-security) |![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)   |![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)   |![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)   |
|12 |[Övervaka hot och vidta åtgärder](#12-monitor-for-threats-and-take-action) |![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)   |![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)  |![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)  |
| | | |


   
Innan du börjar kontrollerar du ditt [Microsoft 365 Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) i microsoft 365-säkerhetscentret. Från en centraliserad instrumentpanel kan du övervaka och förbättra säkerheten för dina Microsoft 365-identiteter, data, appar, enheter och infrastruktur. Du får poäng för att konfigurera rekommenderade säkerhetsfunktioner, utföra säkerhetsrelaterade uppgifter (till exempel visa rapporter) eller hantera rekommendationer med ett program eller en programvara från tredje part. De rekommenderade uppgifterna i den här artikeln höjer din poäng.
  
![Skärmbild av Microsoft Secure Score](../media/secure-score.png)
  
## <a name="1-enable-azure-multi-factor-authentication-mfa"></a>1: Aktivera Azure Multi-Factor Authentication (MFA)
Det bästa du kan göra för att förbättra säkerheten för anställda som arbetar hemifrån är att slå på MFA. Om du inte redan har processer på plats, behandla detta som en nödsituation pilot och se till att du har stöd folk redo att hjälpa anställda som fastnar. Eftersom du förmodligen inte kan distribuera maskinvarusäkerhetsenheter använder du Windows Hello-biometri och smartphone-autentiseringsappar som Microsoft Authenticator.

Normalt rekommenderar Microsoft att du ger användarna 14 dagar på dig att registrera sin enhet för multifaktorautentisering innan du behöver MFA. Men om din personal plötsligt arbetar hemifrån, gå vidare och kräver MFA som en säkerhetsprioritet och vara beredd att hjälpa användare som behöver det. 

Det tar bara några minuter att tillämpa dessa principer, men var beredd att stödja användarna under de närmaste dagarna.  


|Planera  |Rekommendation  |
|---------|---------|
|Microsoft 365-abonnemang (utan Azure AD P1 eller P2)     |[Aktivera säkerhetsstandarder i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Som standard i Azure AD ingår MFA för användare och administratörer.   |
|Microsoft 365 E3 (med Azure AD P1)     | Använd [vanliga principer för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) för att konfigurera följande principer: <br>- [Kräv MFA för administratörer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Blockera äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (med Azure AD P2)     | Dra nytta av Azure AD Identity Protection och börja implementera Microsofts [rekommenderade uppsättning principer för villkorlig åtkomst och relaterade principer](../enterprise/identity-access-policies.md) genom att skapa följande två principer:<br> - [Kräv MFA när inloggningsrisken är medelhög eller hög](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Blockera klienter som inte stöder modern autentisering](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [Högriskanvändare måste ändra lösenord](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |


  
## <a name="2-protect-against-threats"></a>2: Skydda mot hot

Alla Microsoft 365-abonnemang innehåller en mängd olika hotskyddsfunktioner. Att stöta upp skyddet för dessa funktioner tar bara några minuter.
- Skydd mot skadlig kod
- Skydd mot skadliga webbadresser och filer
- Skydd mot nätfiske
- Skydd mot skräppost

Se [Skydda mot hot i Office 365](office-365-security/protect-against-threats.md) för vägledning som du kan använda som utgångspunkt.
    

## <a name="3-configure-office-365-advanced-threat-protection"></a>3: Konfigurera avancerat hotskydd för Office 365

Office 365 Advanced Threat Protection (ATP), som ingår i Microsoft 365 E5 och Office 365 E5, skyddar din organisation mot skadliga hot från e-postmeddelanden, länkar (URL:er) och samarbetsverktyg. Detta kan ta flera timmar att konfigurera.

Office 365 ATP:
- Skyddar din organisation från okända e-posthot i realtid med hjälp av intelligenta system som granskar bilagor och länkar för skadligt innehåll. Dessa automatiserade system inkluderar en robust detonationsplattform, heuristik och maskininlärningsmodeller. 
- Skyddar din organisation när användare samarbetar och delar filer genom att identifiera och blockera skadliga filer på gruppwebbplatser och dokumentbibliotek. 
- Tillämpar maskininlärningsmodeller och avancerade algoritmer för identifiering av personifiering för att förhindra nätfiskeattacker. 

En översikt, inklusive en sammanfattning av abonnemang, finns i [Office 365 Advanced Threat Protection](office-365-security/office-365-atp.md).

Den globala administratören kan konfigurera följande skydd:
- [Konfigurera ATP-säkra länkar](office-365-security/set-up-atp-safe-links-policies.md)
- [Konfigurera ATP-principer för säkra bifogade filer](office-365-security/set-up-atp-safe-attachments-policies.md)
- [Konfigurera en anpassad lista med URL-adresser som inte ska skrivas om](office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
- [Konfigurera en anpassad lista med blockerade URL-adresser](office-365-security/set-up-a-custom-blocked-urls-list-wtih-atp.md)

Du måste arbeta med Exchange Online-administratören och SharePoint Online-administratören för att konfigurera ATP för dessa arbetsbelastningar:
- [Aktivera ATP för SharePoint, OneDrive och Microsoft Teams](office-365-security/turn-on-atp-for-spo-odb-and-teams.md)

## <a name="4-configure-azure-advanced-threat-protection"></a>4: Konfigurera Azure Advanced Threat Protection

[Azure Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) (Azure ATP) är en molnbaserad säkerhetslösning som utnyttjar dina lokala Active Directory-signaler för att identifiera, identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga insideråtgärder som riktas till din organisation. Fokusera på detta nästa eftersom det skyddar din on-prem och din molninfrastruktur, har inga beroenden eller förutsättningar och kan ge omedelbar nytta.


- Se [Azure ATP Quickstarts](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) för att få installation snabbt 
- Titta [på video: Introduktion till Azure ATP](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- Granska de [tre faserna i Azure ATP-distributionen](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-advanced-threat-protection"></a>5: Aktivera Microsoft Advanced Threat Protection

Nu när du har konfigurerat Office 365 ATP och Azure ATP kan du visa de kombinerade signalerna från dessa funktioner på en instrumentpanel. [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) (MTP) samlar aviseringar, incidenter, automatisk undersökning och svar och avancerad jakt över arbetsbelastningar (Azure ATP, Office 365 ATP, Microsoft Defender ATP och Microsoft Cloud App Security) i en enda ruta [security.microsoft.com](https://security.microsoft.com). 
<br>

![Bild av MTP-instrumentpanelen](../media/top-ten-security-remote-work-mtp-dashboard.png)
<br><br>
När du har konfigurerat en eller flera av dina avancerade hotskyddstjänster aktiverar du MTP. Nya funktioner läggs kontinuerligt till MTP; överväga att anmäla sig för att ta emot förhandsgranskningsfunktioner.

- [Läs mer om MTP](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)
- [Aktivera MTP](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide)
- [Anmäl dig för förhandsgranskningsfunktioner](https://docs.microsoft.com/microsoft-365/security/mtp/preview?view=o365-worldwide)


## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: Konfigurera Intune-skydd för mobilappar för telefoner och surfplattor

Med Microsoft Intune Mobile Application Management (MAM) kan du hantera och skydda organisationens data på telefoner och surfplattor utan att hantera dessa enheter. Så här fungerar det:
- Du skapar en APP (App) som avgör vilka appar på en enhet som hanteras och vilka beteenden som tillåts (till exempel förhindra att data från en hanterad app kopieras till en ohanterad app). Du skapar en princip för varje platorm (iOS, Android).
- När du har skapat appskyddsprinciperna tillämpar du dessa genom att skapa en regel för villkorlig åtkomst i Azure AD för att kräva godkända appar och APP-dataskydd.

APP-skyddsprinciper innehåller många inställningar. Lyckligtvis behöver du inte lära dig om varje inställning och väga alternativen. Microsoft gör det enkelt att tillämpa en konfiguration av inställningar genom att rekommendera startpunkter. [Ramverket för dataskydd med hjälp av appskyddsprinciper](https://docs.microsoft.com/mem/intune/apps/app-protection-framework) innehåller tre nivåer du kan välja mellan. 

Ännu bättre, Microsoft samordnar denna app skydd ram med en uppsättning villkorlig åtkomst och relaterade principer rekommenderar vi alla organisationer använder som utgångspunkt. Om du har implementerat MFA med hjälp av vägledningen i den här artikeln är du halvvägs dit!

Om du vill konfigurera skydd av mobilappar använder du vägledningen i [common identity and device access policies](../enterprise/identity-access-policies.md):
 1. Använd vägledningen [använd APP-principer](../enterprise/identity-access-policies.md#apply-app-data-protection-policies) för att skapa principer för iOS och Android. Nivå 2 (förbättrat dataskydd) rekommenderas för grundläggande skydd. 
 2. Skapa en regel för villkorlig åtkomst för att [kräva godkända appar och APP-skydd](../enterprise/identity-access-policies.md#require-approved-apps-and-app-protection). 

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: Konfigurera MFA och villkorlig åtkomst för gäster, inklusive Skydd för Mobilappar i Intune

Låt oss sedan se till att du kan fortsätta att samarbeta och arbeta med gäster. Om du använder Microsoft 365 E3-abonnemanget och implementerade MFA för alla användare är du inställd. 

Om du använder Microsoft 365 E5-planen och utnyttjar Azure Identity Protection för riskbaserad MFA måste du göra ett par justeringar (eftersom Azure AD Identity-skyddet inte omfattar gäster):
- Skapa en ny regel för villkorlig åtkomst för att kräva MFA alltid för gäster och externa användare.
- Uppdatera den riskbaserade MFA-regeln för villkorlig åtkomst för att utesluta gäster och externa användare.

Använd vägledningen i [Uppdatera de gemensamma principerna för att tillåta och skydda gäståtkomst och extern åtkomst](../enterprise/identity-access-policies-guest-access.md) för att förstå hur gäståtkomst fungerar med Azure AD och för att uppdatera de berörda principerna. 

Intune-principerna för skydd av mobilappar som du har skapat, tillsammans med regeln om villkorlig åtkomst för att kräva godkända appar och APP-skydd, gäller för gästkonton och hjälper till att skydda dina organisationsdata. 

**Om**du redan har registrerat datorer i enhetshantering för att kräva kompatibla datorer måste du också utesluta gästkonton från regeln om villkorlig åtkomst som tillämpar enhetsefterlevnad. 


## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: Registrera datorer i enhetshantering och kräver kompatibla datorer

Det finns flera metoder för att registrera din arbetsstyrkas enheter. Varje metod beror på enhetens ägarskap (personliga eller företags), enhetstyp (iOS, Windows, Android) och hanteringskrav (återställningar, tillhörighet, låsning). Detta kan ta lite tid att reda ut. Se: [Registrera enheter i Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/). 

Det snabbaste sättet att komma igång är att [ställa in automatisk registrering för Windows 10-enheter](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment). 

Du kan också dra nytta av dessa tutorials:
- [Använda Autopilot för att registrera Windows-enheter i Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Använda Apples registreringsfunktioner för företagsenhet i Apple Business Manager (ABM) för att registrera iOS/iPadOS-enheter i Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

När du har registrerat enheter använder du vägledningen i principer för [gemensam identitet och enhetsåtkomst](../enterprise/identity-access-policies.md) för att skapa följande principer:
- Definiera principer för [enhetsefterlevnad](../enterprise/identity-access-policies.md#define-device-compliance-policies) – De rekommenderade inställningarna för Windows 10 omfattar krav på antivirusskydd. Om du har Microsoft 365 E5 använder du Microsoft Defender Advanced Threat Protection för att övervaka hälsotillståndet för medarbetarenheter. Se till att efterlevnadsprinciper för andra operativsystem omfattar antivirusskydd och slutpunktsskydd. 
- [Kräv kompatibla datorer](../enterprise/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) – Det här är regeln om villkorlig åtkomst i Azure AD som tillämpar principerna för enhetsefterlevnad.

Endast en organisation kan hantera en enhet, så se till att utesluta gästkonton från regeln om villkorlig åtkomst i Azure AD. Om du inte utesluter gästanvändare och externa användare från principer som kräver enhetsefterlevnad blockerar dessa principer dessa användare. Mer information finns i [Uppdatera de gemensamma principerna för att tillåta och skydda gäståtkomst och extern åtkomst](../enterprise/identity-access-policies-guest-access.md).

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: Optimera nätverket för molnanslutning

Om du snabbt gör det möjligt för huvuddelen av dina anställda att arbeta hemifrån kan den här plötsliga växeln av anslutningsmönster ha en betydande inverkan på företagets nätverksinfrastruktur. Många nätverk skalades och utformades innan molntjänster antogs. I många fall är nätverk toleranta mot distansarbetare, men har inte utformats för att användas på distans av alla användare samtidigt.

Nätverkselement som VPN-koncentratorer, central nätverksutgående utrustning (t.ex. proxyservrar och dataförlustskydd), central internetbandbredd, backhaul MPLS-kretsar, NAT-kapacitet och så vidare utsätts plötsligt för enorma påfrestningar på grund av belastningen på hela verksamheten som använder dem. Slutresultatet är dålig prestanda och produktivitet i kombination med en dålig användarupplevelse för användare som anpassar sig till att arbeta hemifrån.

Vissa av de skydd som traditionellt har tillhandahållits genom att dirigera trafik tillbaka via ett företagsnätverk tillhandahålls av molnapparna som användarna har åtkomst till. Om du har nått det här steget i den här artikeln har du implementerat en uppsättning avancerade molnsäkerhetskontroller för Microsoft 365-tjänster och data. Med dessa kontroller på plats kan du vara redo att dirigera fjärranvändares trafik direkt till Office 365. Om du fortfarande behöver en VPN-länk för åtkomst till andra program kan du avsevärt förbättra din prestanda och användarupplevelse genom att implementera delad tunnel. När du uppnår enighet i din oganization, kan detta ske inom en dag av en väl samordnad nätverk team.


Mer information finns i de här resurserna för dokument:
- [Översikt: Optimera anslutningen för fjärranvändare med VPN-delad tunnel](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Implementera DELAD VPN-tunnel för Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

Senaste blogg artiklar om detta ämne:
- [Så här optimerar du snabbt trafiken för fjärrpersonal & minskar belastningen på infrastrukturen](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [Alternativa sätt för säkerhetspersonal och IT att uppnå moderna säkerhetskontroller i dagens unika fjärrarbetsscenarier](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)


## <a name="10-train-users"></a>10: Utbilda användare

Utbildningsanvändare kan spara användarna och säkerhetsoperationsteamet mycket tid och frustration. Kunniga användare är mindre benägna att öppna bilagor eller klicka på länkar i tvivelaktiga e-postmeddelanden, och de är mer benägna att undvika misstänkta webbplatser. 

Harvard Kennedy School [Cybersecurity Campaign Handbook](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) ger utmärkt vägledning om hur du skapar en stark kultur av säkerhetsmedvetenhet inom din organisation, inklusive utbildning användare att identifiera phishing-attacker. 

Microsoft 365 innehåller följande resurser för att informera användare i organisationen:

|Koncept  |Resurser  |
|---------|---------|
|Microsoft 365     |[Anpassningsbara utbildningsvägar](https://docs.microsoft.com/office365/customlearning/) <p>Dessa resurser kan hjälpa dig att sätta ihop utbildning för slutanvändare i din organisation        |
|Microsoft 365 Säkerhetscenter |[Utbildningsmodul: Skydda din organisation med inbyggd, intelligent säkerhet från Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Med den här modulen kan du beskriva hur Microsoft 365-säkerhetsfunktioner fungerar tillsammans och formulera fördelarna med dessa säkerhetsfunktioner. |
|Multifaktorautentisering     | [Tvåstegsverifiering: Vad är den ytterligare verifieringssidan?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Den här artikeln hjälper slutanvändarna att förstå vad multifaktorautentisering är och varför den används i din organisation.    |
| | |

Utöver den här vägledningen rekommenderar Microsoft att användarna vidtar de åtgärder som beskrivs i den här artikeln: [Skydda ditt konto och dina enheter från hackare och skadlig kod](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx). Dessa åtgärder omfattar:
  
- Använda starka lösenord
    
- Skydda enheter 
    
- Aktivera säkerhetsfunktioner på Windows 10- och Mac-datorer (för ohanterade enheter)
    
Microsoft rekommenderar också att användarna skyddar sina personliga e-postkonton genom att vidta de åtgärder som rekommenderas i följande artiklar:
  
- [Skydda ditt Outlook.com e-postkonto](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba.aspx)
    
- [Skydda ditt Gmail-konto med tvåstegsverifiering](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)


## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11: Komma igång med Microsoft Cloud App Security

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) ger omfattande synlighet, kontroll över dataresor och sofistikerade analyser för att identifiera och bekämpa cyberhot i alla dina molntjänster. När du har börjat med Cloud App Security aktiveras principer för avvikelseidentifiering automatiskt, men Cloud App Security har en inledande inlärningsperiod på sju dagar under vilken inte alla avvikelseidentifieringsaviseringar utlöses.

Kom igång med Cloud App Security nu. Senare kan du ställa in mer sofistikerade övervakning och kontroller.

- [Snabbstart: Kom igång med Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
- [Få omedelbar beteendeanalys och avvikelseidentifiering](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)
- [Läs mer om Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Granska nya funktioner och funktioner](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Se grundläggande installationsinstruktioner](https://docs.microsoft.com/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: Övervaka för hot och vidta åtgärder

Microsoft 365 innehåller flera sätt att övervaka status och vidta lämpliga åtgärder. Den bästa utgångspunkten är Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)), där du kan visa organisationens Microsoft Secure [Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score?view=o365-worldwide)och alla aviseringar eller entiteter som kräver din uppmärksamhet.

- [Komma igång med säkerhetscentret Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center?view=o365-worldwide)
- [Övervaka och visa rapporter](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting?view=o365-worldwide)
- [Se säkerhetsportalerna i Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="next-steps"></a>Nästa steg

Grattis! Du har snabbt implementerat några av de viktigaste säkerhetsskydden och din organisation är mycket säkrare. Nu är du redo att gå ännu längre med hotskyddsfunktioner (inklusive Microsoft Defender Advanced Threat Protection), dataklassificering och skydd samt säkra administrativa konton. En djupare metodisk uppsättning säkerhetsrekommendationer för Microsoft 365 finns i [Microsoft 365 Security for Business Decision Makers (BDMs)](Microsoft-365-security-for-bdm.md). 

Besök även Microsofts nya säkerhetscenter på [docs.microsoft.com/security](https://docs.microsoft.com/security). 
