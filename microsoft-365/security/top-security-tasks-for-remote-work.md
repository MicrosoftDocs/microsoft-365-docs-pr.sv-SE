---
title: De 12 främsta aktiviteterna för säkerhets team för att stödja arbete hemifrån
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- remotework
description: Skydda dina företags meddelanden och data från cyberterrorism hot, inklusive utpressnings tro Jan, nätfiske och illvilliga filer.
ms.openlocfilehash: f364b4100efb3d8b9ab4eda2e370794ca4f0f469
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547980"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>De 12 främsta aktiviteterna för säkerhets team för att stödja arbete hemifrån

Om du är nöjd med [Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) och plötsligt tycker att du har stöd för din egen hem arbets styrka kan vi hjälpa dig att se till att din organisation fungerar som den ska. I den här artikeln prioriteras uppgifter så att säkerhets grupper implementerar de viktigaste säkerhets funktionerna så snabbt som möjligt. 

Om du är en liten eller medels Tor organisation med en av Microsofts företags abonnemang kan du läsa följande resurser i stället:
- [De 10 viktigaste sätten att skydda Office 365 och Microsoft 365 för företag-abonnemang](../admin/security-and-compliance/secure-your-business-data.md) 
- [Microsoft 365 för kampanjer](https://docs.microsoft.com/microsoft-365/campaigns/?view=o365-worldwide) (innehåller en rekommenderad säkerhets konfiguration för Microsoft 365 Business)

  
För kunder som använder vårt företags abonnemang rekommenderar Microsoft att du utför de uppgifter som visas i följande tabell som gäller för din tjänst. Om du i stället för att köpa ett Microsoft 365 Enterprise-abonnemang kombinerar du abonnemang kan du tänka på följande:
- Microsoft 365 E3 inkluderar Enterprise Mobility + Security (EMS) E3 och Azure AD P1
- Microsoft 365 E5 inkluderar EMS E5 och Azure AD P2
  
||**Uppgift**| Alla Office 365 Enterprise-abonnemang|**Microsoft 365 E3** |**Microsoft 365 E5**|
|:-----|:-----|:-----|:-----|:-----|
|9.1      |[Aktivera Azure Multi-Factor inloggningsautentisering (MFA)](#1-enable-azure-multi-factor-authentication-mfa)   |   ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)  |![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)   | ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|två     | [Skydda mot hot](#2-protect-against-threats) |![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png) |  ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)       | ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)       | 
|amp;3D      |  [Konfigurera Office 365 Avancerat skydd](#3-configure-office-365-advanced-threat-protection)  |   |      |  ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)     | 
|9.4      | [Konfigurera Avancerat skydd för Azure (ATP)](#4-configure-azure-advanced-threat-protection)   |   |      |  ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)     | 
|T5     |   [Aktivera Microsoft Hotskydd](#5-turn-on-microsoft-threat-protection)  |  |      | ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|18.6      | [Konfigurera NAP-mobilappen för telefoner och surfplattor](#6-configure-intune-mobile-app-protection-for-phones-and-tablets) |    |  ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)       |  ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)       | 
|borttagning     | [Konfigurera MFA-och villkorlig åtkomst för gäster, inklusive program skydd från Intune](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)  |    |  ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)     | ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|8.2      |  [Registrera datorer i enhets hantering och kräva kompatibla datorer](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)   |  | ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)        | ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)        | 
|9      | [Optimera nätverket för moln anslutningar](#9-optimize-your-network-for-cloud-connectivity)  |  ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png) |![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)      |![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)        | 
|10.3   | [Utbilda användare](#10-train-users) |    ![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png) |![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)      |![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|Nr |[Komma igång med Microsoft Cloud App Security](#11-get-started-with-microsoft-cloud-app-security) |  |  |![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)   |
|12,5 |[Övervaka för hot och vidta åtgärder](#12-monitor-for-threats-and-take-action) |![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)   |![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)  |![Förts](../media/d238e041-6854-4a78-9141-049224df0795.png)  |
| | | |


   
Innan du börjar bör du kontrol lera din [microsoft 365 säkra Poäng](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) i Microsoft 365 säkerhets Center. Från en central instrument panel kan du övervaka och förbättra säkerheten för dina Microsoft 365-identiteter, data, appar, enheter och infrastruktur. Du får poäng för att konfigurera rekommenderade säkerhetsfunktioner, utföra säkerhetsrelaterade uppgifter (som att visa rapporter) eller adress rekommendationer med en tredje parts program eller program vara. De rekommenderade åtgärderna i den här artikeln ger poäng.
  
![Skärm bild av Microsofts säkra Poäng](../media/secure-score.png)
  
## <a name="1-enable-azure-multi-factor-authentication-mfa"></a>1: Aktivera Azure Multi-Factor inloggningsautentisering (MFA)
Det enda du kan göra för att förbättra säkerheten för anställda som arbetar hemifrån är att aktivera MFA. Om du inte redan har processer på plats kan du behandla detta som en nöd situations pilot och kontrol lera att du har stöd familjen redo att hjälpa anställda som är låsta. Eftersom du troligen inte kan distribuera maskin varu säkerhetsenheter kan du använda Windows Hello biometrik och smartphone-verifierings program som Microsoft Authenticator.

Vanligt vis rekommenderar Microsoft att du ger användarna 14 dagar att registrera sina enheter för multifaktorautentisering innan de kräver MFA. Men om din arbets styrka plötsligt arbetar hemifrån kan du börja med att kräva MFA som säkerhets prioritet och vara redo att hjälpa användare som behöver det. 

Det tar bara några minuter att tillämpa dessa principer, men var för beredda att stödja användarna under de närmaste dygnen.  


|Planera  |Rekommendation  |
|---------|---------|
|Microsoft 365-abonnemang (utan Azure AD P1 eller P2)     |[Aktivera standardinställningar för säkerhet i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Standardinställningar för säkerhet i Azure AD inkluderar MFA för användare och administratörer.   |
|Microsoft 365 E3 (med Azure AD P1)     | Använd [vanliga principer för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) för att konfigurera följande principer: <br>- [Kräv MFA för administratörer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Blockera äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (med Azure AD P2)     | Dra nytta av Azure AD Identity Protection och börja implementera Microsofts [rekommenderade uppsättning av villkorsstyrd åtkomst och relaterade principer](../enterprise/identity-access-policies.md) genom att skapa de två principerna:<br> - [Kräv MFA när inloggningsrisker är medel eller hög](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Blockera klienter som inte har stöd för modern autentisering](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [Användare med hög risk måste byta lösenord](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |


  
## <a name="2-protect-against-threats"></a>2: skydda mot hot

Alla Microsoft 365-abonnemang innehåller en mängd olika skydds funktioner. Det tar bara några minuter att öka skyddet för dessa funktioner.
- Skydd mot skadlig kod
- Skydda från skadliga URL-adresser och filer
- Skydd mot nätfiske
- Skydd mot skräppost

Se [skydda mot hot i Office 365](office-365-security/protect-against-threats.md) för vägledning som du kan använda som utgångs punkt.
    

## <a name="3-configure-office-365-advanced-threat-protection"></a>3: Konfigurera Office 365 Avancerat skydd

Office 365 Avancerat skydd (ATP), som ingår i Microsoft 365 E5 och Office 365 E5, skyddar din organisation mot hot via e-postmeddelanden, länkar (URL: er) och samarbets verktyg. Det kan ta flera timmar att konfigurera.

Office 365 ATP:
- Skyddar din organisation från okända e-posthoten i real tid genom att använda intelligenta system som kontrollerar bilagor och länkar för skadligt innehåll. Dessa automatiserade system inkluderar en robust plattform för sprängmedel, heuristik och maskin inlärnings modeller. 
- Skyddar organisationen när användare samarbetar och delar filer genom att identifiera och blockera skadliga filer på grupp webbplatser och dokument bibliotek. 
- Tillämpar dator utbildnings modeller och avancerade algoritmer för identifiering av personifieringstoken för AVERT nätfiske-attacker. 

En översikt, inklusive en sammanfattning av planerna, finns i [Office 365 Avancerat skydd för hot](office-365-security/office-365-atp.md).

Den globala administratören kan konfigurera följande skydd:
- [Konfigurera säkra säkerhets Länkar för ATP](office-365-security/set-up-atp-safe-links-policies.md)
- [Konfigurera ATP-principer för säkra bifogade filer](office-365-security/set-up-atp-safe-attachments-policies.md)
- [Konfigurera en anpassad lista med URL-adresser som inte ska skrivas om](office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
- [Konfigurera en anpassad lista med blockerade URL-adresser](office-365-security/set-up-a-custom-blocked-urls-list-atp.md)

Du måste arbeta med din Exchange Online-administratör och SharePoint Online-administratör för att konfigurera ATP för dessa arbets belastningar:
- [Aktivera ATP för SharePoint, OneDrive och Microsoft Teams](office-365-security/turn-on-atp-for-spo-odb-and-teams.md)

## <a name="4-configure-azure-advanced-threat-protection"></a>4: Konfigurera Avancerat Azure-skydd

[Azure Avancerat skydd](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) (Azure ATP) är en molnbaserad säkerhets lösning som använder dina lokala Active Directory-signaler för att identifiera, upptäcka och undersöka avancerade hot, kompromissade identiteter och illasinnade Insider-åtgärder på din organisation. Fokusera på den här nästa eftersom den skyddar din lokala och moln infrastrukturen inte har några beroenden eller förutsättningar och kan ge omedelbara fördelar.


- Se [snabb starts](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) guiderna för Azure ATP för att snabbt komma igång 
- Titta [på videoklippet: Introduktion till Azure ATP](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- Granska de [tre faserna i distributionen av Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-threat-protection"></a>5: Aktivera skydd mot Microsoft Threat

Nu när du har konfigurerat Office 365 ATP och Azure ATP kan du Visa de kombinerade signalerna från dessa funktioner på en instrument panel. [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) (MTP) sammanträder med aviseringar, händelser, automatiserade undersökningar och svar samt avancerad jakt i arbets belastning (Azure ATP, Office 365 ATP, Microsoft Defender ATP och Microsoft Cloud App Security) till en enda ruta på [Security.Microsoft.com](https://security.microsoft.com). 
<br>

![Bild av MTP-instrumentpanel](../media/top-ten-security-remote-work-mtp-dashboard.png)
<br><br>
När du har konfigurerat en eller flera av dina avancerade skydds tjänster aktiverar du MTP. Nya funktioner läggs till ständig till MTP; Tänk på vanligt om du vill ha funktioner för förhands granskning.

- [Lär dig mer om MTP](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)
- [Aktivera MTP](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide)
- [Välja för förhands gransknings funktioner](https://docs.microsoft.com/microsoft-365/security/mtp/preview?view=o365-worldwide)


## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: konfigurera NAP-mobilappen för telefoner och surfplattor

Med Microsoft Intune-MAM (Mobile Application Management) kan du hantera och skydda organisationens data på telefoner och surfplattor utan att hantera dessa enheter. Så här fungerar det:
- Du skapar en app Protection-princip (program) som avgör vilka appar på en enhet som hanteras och vilka funktioner som är tillåtna (till exempel förhindra att data från en hanterad app kopieras till en ohanterad app). Du skapar en princip för varje plattform (iOS, Android).
- När du har skapat skydds principer för appar verkställer du dessa genom att skapa en regel för villkorsstyrd åtkomst i Azure AD för att kräva godkända appar och program data skydd.

Skydds principer för appar innehåller många inställningar. Du behöver inte lära dig alla inställningar och väga alternativen. Microsoft gör det enkelt att tillämpa en konfiguration av inställningar genom att rekommendera start punkter. [Data skydds ramverket som använder program skydds principer](https://docs.microsoft.com/mem/intune/apps/app-protection-framework) inkluderar tre nivåer du kan välja bland. 

Ännu bättre, Microsoft samordnar detta program skydds ramverk med en uppsättning villkorsstyrd åtkomst och relaterade principer vi rekommenderar att alla organisationer använder sig av en utgångs punkt. Om du har implementerat MFA med hjälp av vägledningen i den här artikeln är det alldeles halva!

Konfigurera mobilappen genom att använda vägledning i [vanliga principer för identitets-och enhets åtkomst](../enterprise/identity-access-policies.md):
 1. Använd vägledning för användning av [data skydds principer](../enterprise/identity-access-policies.md#apply-app-data-protection-policies) för att skapa principer för iOS och Android. Nivå 2 (förbättrat data skydd) rekommenderas för baseline-skydd. 
 2. Skapa en regel för villkorsstyrd åtkomst för att [kräva godkända appar och program skydd](../enterprise/identity-access-policies.md#require-approved-apps-and-app-protection). 

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: Konfigurera MFA och villkorlig åtkomst för gäster, inklusive paket för NAP-mobilappen

Vi ser till att du kan fortsätta att samar beta och arbeta med gästerna. Om du använder Microsoft 365 E3-abonnemanget och du implementerat MFA för alla användare är det klart. 

Om du använder Microsoft 365 E5-abonnemanget och du utnyttjar Azure Identity Protection för riskabelt MFA måste du göra några justeringar (eftersom Azure AD Identity Protection inte förlängs med gästerna):
- Skapa en ny regel för villkorsstyrd åtkomst för att kräva MFA alltid för gäster och externa användare.
- Uppdatera den riskfyllda regeln för villkorsstyrd åtkomst för MFA för att exkludera gäster och externa användare.

Använd vägledningen i [Uppdatera vanliga principer för att tillåta och skydda gäst och extern åtkomst](../enterprise/identity-access-policies-guest-access.md) för att förstå hur gäst åtkomst fungerar med Azure AD och för att uppdatera de påverkade principerna. 

De program skydds principer för Intune som du skapade, tillsammans med regeln för villkorsstyrd åtkomst för att kräva godkända appar och program skydd, gäller för gäst konton och skyddar organisationens data. 

> [!NOTE]
> Om du redan har registrerat datorer i enhets hantering för att kräva kompatibla datorer måste du även exkludera gäst konton från regeln för villkorsstyrd åtkomst som används för att säkerställa att enheter efterlevs. 


## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: Registrera datorer i enhets hantering och Kräv kompatibla datorer

Det finns flera olika sätt att registrera din arbets styrkas enheter. Varje metod beror på enhetens ägandes Kap (personal eller företag), enhetens typ (iOS, Windows, Android) och hanterings krav (återställer, tillhörighet, låsning). Det kan ta en stund att sortera. Se: [registrera enheter i Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/). 

Det snabbaste sättet att komma igång är att [Konfigurera automatisk registrering för Windows 10-enheter](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment). 

Du kan också utnyttja dessa själv studie kurser:
- [Använda autopilot för att registrera Windows-enheter i Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Använda Apple-funktioner för företags enheter i Apple Business Manager (ABM) för att registrera iOS/iPad-enheter i Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

När du har registrerat enheter kan du använda vägledningen i [vanliga principer för identitets-och enhets åtkomst](../enterprise/identity-access-policies.md) för att skapa dessa principer:
- [Definiera principer för enhets efterlevnad](../enterprise/identity-access-policies.md#define-device-compliance-policies) – de rekommenderade inställningarna för Windows 10 inkluderar krav på Antivirus skydd. Om du har Microsoft 365 E5 kan du använda Microsoft Defender Avancerat skydd för att övervaka människors enheters hälsa. Kontrol lera att efterlevnadsprinciper för andra operativ system inkluderar skydd mot virus skydd och program vara för slut punkter. 
- [Kräv kompatibla datorer](../enterprise/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) – det här är regeln för villkorsstyrd åtkomst i Azure AD som tillämpar principer för efterlevnadsprinciper.

Endast en organisation kan hantera en enhet, så se till att exkludera gäst konton från regeln för villkorsstyrd åtkomst i Azure AD. Om du inte utesluter gäst-och externa användare från principer som kräver att enheter efterlevs blockerar dessa användare. Mer information finns i [Uppdatera gemensamma principer för att tillåta och skydda gäst och extern åtkomst](../enterprise/identity-access-policies-guest-access.md).

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: optimera nätverket för moln anslutningar

Om du snabbt gör det möjligt för dina anställda att arbeta hemifrån kan den här plötsliga anslutningen av anslutnings mönster påverka nätverkets infrastruktur avsevärt. Många nätverk har skalats och utformats innan moln tjänsterna antogs. I många fall är nätverken avsedda för fjärrarbetarna, men har inte utformats för att kunna användas av alla användare samtidigt.

Nätverks element som VPN-koncentratorer, centrala nätverks slut utrustning (till exempel proxyservrar och data förlust), central Internet bandbredd, bakgrunds MPLS kretsar, NAT-funktion och så vidare, anges plötsligt inte under enorma stammar på grund av hela företagets affärer. Slut resultatet är dålig prestanda och produktivitet tillsammans med en dåligt användar upplevelse för användare som håller på att anpassa sig till att arbeta hemifrån.

Vissa av de skydd som traditionellt har tillhandahållits genom att cirkulera trafiken tillbaka via ett företags nätverk tillhandahålls av de moln program som användarna har åtkomst till. Om du har nått det här steget i den här artikeln har du implementerat en uppsättning avancerade moln säkerhets kontroller för Microsoft 365-tjänster och-data. Med dessa kontroller på plats kan du behöva dirigera fjärran vändare-trafik direkt till Office 365. Om du fortfarande behöver en VPN-länk för att få till gång till andra program kan du förbättra prestanda och användar upplevelsen genom att implementera delade tunnlar. När du har gått med i din organisation kan du göra detta inom en dag av ett välkänt nätverks team.


Mer information finns i följande resurser:
- [Översikt: optimera anslutningen för fjärran vändare med delning av VPN](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Implementera VPN-fildelning för Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

Senaste blogg artiklarna i det här avsnittet:
- [Så här kan du snabbt optimera trafik för fjärranställda & minska belastningen på infrastrukturen](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [Alternativa sätt för säkerhetsexperter och för att få moderna säkerhets kontroller i dagens unika scenarier för fjärrarbete](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)


## <a name="10-train-users"></a>10: utbilda användare

Utbildning användare kan spara dina användare och säkerhets åtgärder för att få massor av tid och irritation. Smarta användare är mindre troligt att öppna bifogade filer eller klicka på länkar i tveksamma e-postmeddelanden och det är mer sannolikt att misstänkta webbplatser undviks. 

Det här är en utmärkt vägledning i Harvard Kennedy School [Cybersecurity-kampanjen](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) med att skapa en starkt kultur av säkerhets medvetenhet inom din organisation, inklusive utbildnings användare för att identifiera nätfiske-attacker. 

Microsoft 365 tillhandahåller följande resurser för att hjälpa användare i organisationen:

|Symboliserar konceptet  |Resurser  |
|---------|---------|
|Microsoft 365     |[Anpassningsbara Learning-vägar](https://docs.microsoft.com/office365/customlearning/) <p>De här resurserna hjälper dig att hålla ihop utbildning för slutanvändare i din organisation        |
|Microsoft 365 Säkerhetscenter |[Kodmodul: skydda din organisation med inbyggd, intelligent säkerhet från Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Med den här modulen kan du beskriva hur säkerhetsfunktionerna i Microsoft 365 fungerar tillsammans och för att Articulate fördelarna med de här säkerhetsfunktionerna. |
|Multifaktorautentisering     | [Tvåstegsverifiering: Vad är sidan för ytterligare verifiering?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Den här artikeln hjälper slutanvändarna att förstå vad multifaktorautentisering är och varför den används i din organisation.    |
| | |

Utöver den här vägledningen rekommenderar Microsoft att användarna vidtar åtgärderna som beskrivs i den här artikeln: [skydda ditt konto och dina enheter från hackare och skadlig program vara](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx). Dessa åtgärder inkluderar:
  
- Använda starka lösen ord
    
- Skydda enheter 
    
- Aktivera säkerhetsfunktioner på Windows 10-och Mac-datorer (för ohanterade enheter)
    
Microsoft rekommenderar också att användare skyddar sina privata e-postkonton genom att vidta åtgärder som rekommenderas i följande artiklar:
  
- [Skydda ditt Outlook.com-e-postkonto](https://support.microsoft.com/en-us/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
    
- [Skydda ditt Gmail-konto med tvåstegsverifiering](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)


## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11: komma igång med säkerhet för Microsoft Cloud App

[Säkerhet för Microsoft Cloud App](https://docs.microsoft.com/cloud-app-security) ger stor insyn, kontroll över data resor och avancerad analys för att identifiera och bekämpa Cyberthreats i alla dina moln tjänster. När du har börjat komma igång med Cloud App Security aktive RAS principer för avvikelse identifiering automatiskt, men Cloud App-säkerheten har en inledande utbildnings period på sju dagar då inte alla avvikelse varningar upphöjas.

Komma igång med Cloud App Security nu. Senare kan du ställa in mer sofistikerade övervakning och kontroller.

- [Snabb start: komma igång med Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
- [Få till gång till omedelbara beteende analyser och avvikelse identifiering](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)
- [Läs mer om Microsoft Cloud App-säkerhet](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Granska nya funktioner och möjligheter](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Se grundläggande konfigurations instruktioner](https://docs.microsoft.com/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: övervaka för hot och vidta åtgärder

Microsoft 365 innehåller flera olika sätt att övervaka status och vidta lämpliga åtgärder. Din bästa start punkt är Microsoft 365 säkerhets Center ( [https://security.microsoft.com](https://security.microsoft.com) ), där du kan visa organisationens [Microsoft säkra Poäng](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score?view=o365-worldwide)och eventuella varningar eller enheter som kräver din uppmärksamhet.

- [Komma igång med Microsoft 365 säkerhets Center](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center?view=o365-worldwide)
- [Övervaka och visa rapporter](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting?view=o365-worldwide)
- [Visa säkerhets portaler i Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="next-steps"></a>Nästa steg

Grattis! Du har snabbt implementerat de viktigaste säkerhets skydden och organisationen är mycket säkrare. Nu är du redo att gå vidare med skydds funktioner (inklusive Microsoft Defender Avancerat skydd), data klassificering och skydds funktioner samt skydda administratörs konton. En djupare, metodisk uppsättning säkerhets rekommendationer för Microsoft 365 finns i [microsoft 365 Security för Business besluts fattare (BDMs)](Microsoft-365-security-for-bdm.md). 

Besök också Microsofts nya säkerhets Center på [docs.Microsoft.com/Security](https://docs.microsoft.com/security). 
