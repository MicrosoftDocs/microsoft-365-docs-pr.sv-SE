---
title: De 12 viktigaste uppgifterna för säkerhetsteam att stödja arbetet hemifrån
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
description: Skydda din affärs-e-post och data från cyberhot, inklusive utpressningstrojaner, nätfiske och skadliga bifogade filer.
ms.openlocfilehash: 109ba05b21ce9c1355be73dbdfb000d6eb8c4e4d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930477"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>De 12 viktigaste uppgifterna för säkerhetsteam att stödja arbetet hemifrån

Om du är som [Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) och plötsligt upptäcker att du stöder en främst hembaserad arbetsstyrka, vill vi hjälpa dig att säkerställa att din organisation arbetar så säkert som möjligt. Den här artikeln prioriterar uppgifter som ska hjälpa säkerhetsgrupper att implementera de viktigaste säkerhetsfunktionerna så snabbt som möjligt.

![Utför de här vanliga uppgifterna om du vill ha stöd för att arbeta hemifrån.](../media/security/security-support-remote-work.png)

Om du är en liten eller medelstor organisation som använder ett av Microsofts företags planer, se följande resurser i stället:

- [De 10 bästa sätten att skydda Office 365 och Microsoft 365 för företag-abonnemang](../admin/security-and-compliance/secure-your-business-data.md)
- [Microsoft 365 för kampanjer](../campaigns/index.md) (innehåller en rekommenderad säkerhetskonfiguration för Microsoft 365 Business)

För kunder som använder våra enterprise-abonnemang rekommenderar Microsoft att du slutför de uppgifter som listas i följande tabell som gäller för ditt abonnemang. Om du kombinerar abonnemang Microsoft 365 företag i stället för att köpa ett företagsabonnemang bör du observera följande:

- Microsoft 365 E3 omfattar Enterprise Mobility + Security (EMS) E3 och Azure AD P1
- Microsoft 365 E5 innehåller EMS E5 och Azure AD P2

****

|Steg|Uppgift|Alla Office 365 Enterprise abonnemang|Microsoft 365 E3|Microsoft 365 E5|
|---|---|---|---|---|
|1|[Aktivera Azure AD Multi-Factor Authentication (MFA)](#1-enable-azure-ad-multi-factor-authentication-mfa)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2|[Skydda mot hot](#2-protect-against-threats)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[Konfigurera Microsoft Defender för Office 365](#3-configure-microsoft-defender-for-office-365)|||![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4|[Konfigurera Microsoft Defender för identitet](#4-configure-microsoft-defender-for-identity)|||![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5|[Aktivera Microsoft 365 Defender](#5-turn-on-microsoft-365-defender)|||![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6|[Konfigurera skydd för Intune-mobilappen för telefoner och surfplattor](#6-configure-intune-mobile-app-protection-for-phones-and-tablets)||![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7|[Konfigurera MFA och villkorsstyrd åtkomst för gäster, inklusive intune-appskydd](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)||![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8|[Registrera datorer i enhetshantering och kräv kompatibla datorer](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)||![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9|[Optimera nätverket för molnanslutning](#9-optimize-your-network-for-cloud-connectivity)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10|[Utbilda användare](#10-train-users)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|11|[Komma igång med Microsoft Cloud App Security](#11-get-started-with-microsoft-cloud-app-security)|||![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|12|[Övervaka hot och vidta åtgärder](#12-monitor-for-threats-and-take-action)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

Innan du börjar kontrollerar du [Microsoft 365 Secure Score](./defender/microsoft-secure-score.md) i Microsoft 365 säkerhetscenter. Från en centraliserad instrumentpanel kan du övervaka och förbättra säkerheten för Microsoft 365 identiteter, data, appar, enheter och infrastruktur. Du får poäng för att konfigurera rekommenderade säkerhetsfunktioner, utföra säkerhetsrelaterade uppgifter (till exempel visa rapporter) eller åtgärda rekommendationer med ett program eller en programvara från tredje part. De rekommenderade uppgifterna i den här artikeln kommer att höja din poäng.

![Skärmbild av Microsoft Secure Score](../media/secure-score.png)

## <a name="1-enable-azure-ad-multi-factor-authentication-mfa"></a>1: Aktivera Azure AD Multi-Factor Authentication (MFA)

Det enda bästa du kan göra för att förbättra säkerheten för anställda som arbetar hemifrån är att aktivera MFA. Om du inte redan har processer på plats kan du behandla det som ett nödpilottest och se till att du har support så att du kan hjälpa anställda som fastnar. Eftersom du förmodligen inte kan distribuera maskinvarusäkerhetsenheter kan du använda Windows Hello-autentiseringsappar och smartphone-autentiseringsappar som Microsoft Authenticator.

Normalt rekommenderar Microsoft att du ger användarna 14 dagar på sig att registrera sin enhet för multifaktorautentisering innan de kräver MFA. Men om din arbetsstyrka plötsligt arbetar hemifrån kan du fortsätta och kräva MFA som säkerhetsprioritet och vara beredd på att hjälpa användare som behöver det.

Att tillämpa de här principerna tar bara några minuter, men är beredd på att ge support till användarna under de kommande dagarna.

****

|Planera|Rekommendation|
|---|---|
|Microsoft 365 -abonnemang (utan Azure AD P1 eller P2)|[Aktivera standardinställningar för säkerhet i Azure AD](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Standardinställningar för säkerhet i Azure AD inkluderar MFA för användare och administratörer.|
|Microsoft 365 E3 (med Azure AD P1)|Använd [vanliga principer för villkorsstyrd åtkomst](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) för att konfigurera följande principer: <br/>- [Kräv MFA för administratörer](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br/>- [Kräv MFA för alla användare](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br/> - [Blockera äldre autentisering](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)|
|Microsoft 365 E5 (med Azure AD P2)|Dra nytta av Azure AD Identity Protection och börja implementera Microsofts [rekommenderade uppsättning av villkorsstyrd åtkomst och relaterade principer](./office-365-security/identity-access-policies.md) genom att skapa de två principerna:<br/> - [Kräv MFA när inloggningsrisker är medel eller hög](./office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br/>- [Blockera klienter som inte har stöd för modern autentisering](./office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br/>- [Användare med hög risk måste byta lösenord](./office-365-security/identity-access-policies.md#high-risk-users-must-change-password)|
|

## <a name="2-protect-against-threats"></a>2: Skydda mot hot

Alla Microsoft 365-abonnemang har en mängd olika skyddsfunktioner för hot. Det tar bara några minuter att få ett skydd för dessa funktioner.

- Skydd mot skadlig kod
- Skydd mot skadliga URL:er och filer
- Skydd mot nätfiske
- Skydd mot skräppost

Se [Skydda mot hot i Office 365](office-365-security/protect-against-threats.md) information om att du kan använda som utgångspunkt.

## <a name="3-configure-microsoft-defender-for-office-365"></a>3: Konfigurera Microsoft Defender för Office 365

Microsoft Defender för Office 365, som ingår i Microsoft 365 E5 och Office 365 E5, skyddar organisationen mot skadliga hot som kan orsakas av e-postmeddelanden, länkar och samarbetsverktyg. Det kan ta flera timmar att konfigurera.

Microsoft Defender för Office 365:

- Skyddar organisationen mot okända e-posthot i realtid genom att använda intelligenta system för att kontrollera bifogade filer och länkar för skadligt innehåll. Dessa automatiserade system har en robust detonationplattform, heuristics och maskininlärningsmodeller.
- Skyddar organisationen när användare samarbetar och delar filer genom att identifiera och blockera skadliga filer på gruppwebbplatser och dokumentbibliotek.
- Tillämpar maskininlärningsmodeller och avancerade algoritmer för personifiering för att av invertera nätfiskeattacker.

En översikt, inklusive en sammanfattning av abonnemangen, finns [i Defender för Office 365](./office-365-security/defender-for-office-365.md).

Din globala administratör kan konfigurera dessa skydd:

- [Konfigurera Valv länkar](office-365-security/set-up-safe-links-policies.md)
- [Konfigurera globala inställningar för Valv Länkar](office-365-security/configure-global-settings-for-safe-links.md)
- [Konfigurera principer för Valv för bifogade filer](office-365-security/set-up-safe-attachments-policies.md)

Du måste arbeta med din administratör Exchange Online och SharePoint Online för att konfigurera Defender Office 365 för dessa arbetsbelastningar:

- [Microsoft Defender för Endpoint för SharePoint, OneDrive och Microsoft Teams](office-365-security/mdo-for-spo-odb-and-teams.md)

## <a name="4-configure-microsoft-defender-for-identity"></a>4: Konfigurera Microsoft Defender för identitet

[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) är en molnbaserad säkerhetslösning som utnyttjar dina lokala Active Directory-signaler för att identifiera, upptäcka och undersöka avancerade hot, komprometterade identiteter och illasinnade insider-åtgärder som riktas mor organisationen. Fokusera på detta härnäst eftersom det skyddar din lokala och molnbaserad infrastruktur, har inga beroenden eller krav och kan ge omedelbar nytta.

- Se [Snabbstartsguider för Microsoft Defender för identitet](/azure-advanced-threat-protection/install-atp-step1) för att snabbt komma igång med konfigurationen
- Titta [på videoklippet: Introduktion till Microsoft Defender för identitet](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- Granska de [tre faserna i Microsoft Defender för identitetsdistribution](/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-365-defender"></a>5: Aktivera Microsoft 365 Defender

Nu när du har konfigurerat Microsoft Defender för Office 365 och Microsoft Defender för identitet kan du visa de kombinerade signalerna från dessa funktioner på en instrumentpanel. [i Microsoft 365 Defender](./defender/microsoft-365-defender.md) sammanförs aviseringar, incidenter, automatisk undersökning och svar och avancerad sökning i olika arbetsbelastningar (Microsoft Defender för identitet, Defender för Office 365, Microsoft Defender för Slutpunkt och Microsoft Cloud App Security) i en enda ruta [security.microsoft.com](https://security.microsoft.com).

![MTP-instrumentpanelsbild](../media/top-ten-security-remote-work-mtp-dashboard.png)

När du har konfigurerat en eller flera av Dina Defender Office 365 tjänster aktiverar du MTP. Nya funktioner läggs till kontinuerligt i MTP. Överväg att registrera dig för att få förhandsgranskningsfunktioner.

- [Läs mer om MTP](./defender/microsoft-365-defender.md)
- [Aktivera MTP](./defender/m365d-enable.md)
- [Registrera dig för förhandsgranskningsfunktioner](./defender/preview.md)

## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: Konfigurera skydd för Intune-mobilappen för telefoner och surfplattor

Microsoft Intune Med hantering av mobilprogram (MAM) kan du hantera och skydda organisationens data på telefoner och surfplattor utan att hantera de här enheterna. Så här fungerar det:

- Du skapar en appskyddsprincip (APP) som avgör vilka appar på en enhet som hanteras och vilka beteenden som är tillåtna (till exempel att förhindra att data från ett hanterat program kopieras till ett ohanterat program). Du skapar en princip för varje plattform (iOS, Android).
- När du har skapat appskyddsprinciperna tillämpar du dessa genom att skapa en villkorsstyrd åtkomstregel i Azure AD för att kräva godkända appar och APP-dataskydd.

APPskyddsprinciper innehåller många inställningar. Som tur är behöver du inte lära dig mer om alla inställningar och väga alternativen. Microsoft gör det enkelt att använda en inställningskonfiguration genom att rekommendera utgångspunkter. Ramverket [för dataskydd som använder principer för appskydd](/mem/intune/apps/app-protection-framework) omfattar tre nivåer som du kan välja bland.

Ännu bättre koordinerar Microsoft det här ramverket för appskydd med en uppsättning villkorsstyrda åtkomst och relaterade principer som vi rekommenderar att alla organisationer använder som utgångspunkt. Om du har implementerat MFA med hjälp av vägs i den här artikeln är du halvvägs dit!

Om du vill konfigurera skydd för mobilappar använder du vägledningen i [Vanliga principer för identitet och enhetsåtkomst:](./office-365-security/identity-access-policies.md)

 1. Använd [vägledning av appdataskyddsprinciper](./office-365-security/identity-access-policies.md#apply-app-data-protection-policies) för att skapa principer för iOS och Android. Nivå 2 (förbättrat dataskydd) rekommenderas för grundläggande skydd.
 2. Skapa en regel för villkorsstyrd åtkomst [så att godkända appar och APPskydd krävs.](./office-365-security/identity-access-policies.md#require-approved-apps-and-app-protection)

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: Konfigurera MFA och villkorsstyrd åtkomst för gäster, inklusive intune-mobilappsskydd

Nu ska vi se till att du kan fortsätta att samarbeta och arbeta med gäster. Om du använder Microsoft 365 E3-abonnemanget och har implementerat MFA för alla användare är du redo.

Om du använder Microsoft 365 E5-abonnemanget och du utnyttjar Azure Identity Protection för riskbaserad MFA måste du göra några justeringar (eftersom Azure AD Identity Protection inte omfattar gäster):

- Skapa en ny regel för villkorsstyrd åtkomst så att MFA alltid krävs för gäster och externa användare.
- Uppdatera den riskbaserade MFA-regeln för villkorsstyrd åtkomst för att utesluta gäster och externa användare.

Använd vägledning [i Uppdatera vanliga principer](./office-365-security/identity-access-policies-guest-access.md) för att tillåta och skydda gäst- och extern åtkomst för att förstå hur gäståtkomst fungerar med Azure AD och för att uppdatera de aktuella principerna.

De principer för skydd av Intune-mobilappar som du har skapat, tillsammans med regeln för villkorsstyrd åtkomst som kräver godkända appar och appskydd, gäller för gästkonton och hjälper till att skydda dina organisationsdata.

> [!NOTE]
> Om du redan har registrerat datorer i enhetshantering för att kräva kompatibla datorer måste du även utesluta gästkonton från regeln för villkorsstyrd åtkomst som framtvingar enhetsefterlevnad.

## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: Registrera datorer i enhetshantering och kräv kompatibla datorer

Det finns flera metoder för att registrera arbetsstyrkans enheter. Varje metod beror på enhetens ägarskap (privat eller företag), enhetstyp (iOS, Windows, Android) och hanteringskrav (återställningar, tillhörigheter, låsning). Det kan ta lite tid att reda ut det. Mer information: [Registrera enheter i Microsoft Intune](/mem/intune/enrollment/).

Det snabbaste sättet att komma igång är att [konfigurera automatisk registrering för Windows 10 enheter.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

Du kan också dra nytta av de här självstudiekurserna:

- [Använda Autopilot för att registrera Windows enheter i Intune](/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Använd Apples funktioner för enhetsregistrering för företag i Apple Business Manager (ABM) för att registrera iOS-/iPadOS-enheter i Intune](/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

När du har registrerat enheter kan du använda vägledningen i Principer för [gemensamma identiteter och enhetsåtkomst för](./office-365-security/identity-access-policies.md) att skapa dessa principer:

- [Definiera policyer för enhetsefterlevnad](./office-365-security/identity-access-policies.md#define-device-compliance-policies) – De rekommenderade inställningarna för Windows 10 att kräva antivirusskydd. Om du har Microsoft 365 E5 kan du använda Microsoft Defender för Slutpunkt för att övervaka hälsotillståndet för de anställdas enheter. Se till att efterlevnadsprinciper för andra operativsystem innehåller antivirusprogram och skyddsprogram för ändpunkt.
- [Kräv kompatibla datorer –](./office-365-security/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) Det här är regeln för villkorsstyrd åtkomst i Azure AD som tillämpar efterlevnadsprinciper för enheter.

Bara en organisation kan hantera en enhet, så se till att utesluta gästkonton från regeln för villkorsstyrd åtkomst i Azure AD. Om du inte exkluderar gäst- och externa användare från principer som kräver enhetsefterlevnad blockeras dessa användare av dessa principer. Mer information finns i Uppdatera [vanliga principer för att tillåta och skydda gäst och extern åtkomst.](./office-365-security/identity-access-policies-guest-access.md)

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: Optimera nätverket för molnanslutning

Om du snabbt gör det möjligt för många anställda att arbeta hemifrån kan detta plötsligt byte av anslutningsmönster ha stor inverkan på företagets nätverksinfrastruktur. Många nätverk skalades och utformades innan molntjänster införskalades. I många fall är nätverk nätverk av fjärranslutna medarbetare, men har inte utformats för att användas på distans av alla användare samtidigt.

Nätverkselement som VPN-koncentratorer, central egressutrustning för nätverk (t.ex. proxyenheter och skyddsenheter för dataförlust), central internetbandbredd, backhaul MPLS-kretsar, NAT-funktioner och så vidare kommer plötsligt att drabbas av enorm belastning på grund av belastningen på hela företaget som använder dem. Resultatet är dålig prestanda och produktivitet tillsammans med en dålig användarupplevelse för användare som anpassar sig till att arbeta hemifrån.

En del av de skydd som tidigare tillhandahållits genom att dirigera trafik tillbaka genom ett företagsnätverk tillhandahålls av de molnappar användarna använder. Om du har kommit till det här steget i den här artikeln har du implementerat en uppsättning avancerade molnsäkerhetskontroller för Microsoft 365 tjänster och data. Med de här kontrollerna kan du vara redo att dirigera fjärranvändares trafik direkt till Office 365. Om du fortfarande kräver en VPN-länk för åtkomst till andra program kan du förbättra prestanda och användarupplevelse avsevärt genom att implementera delade tunnlar. När ni har uppnått ett avtal i organisationen kan det åstadkommas inom en dag av ett väl samordnat nätverksteam.

Mer information finns i följande resurser i Dokument:

- [Översikt: Optimera anslutningen för fjärranvändare med VPN-delade tunnlar](/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Implementera VPN-delade tunnlar för Office 365](/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

Senaste bloggartiklar om det här avsnittet:

- [Hur du snabbt optimerar trafiken för fjärranslutna personal & minska belastningen på infrastrukturen](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [Alternativa sätt för säkerhetsexperter och IT-personal för att uppnå moderna säkerhetskontroller i dagens unika fjärrarbetesscenarier](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

## <a name="10-train-users"></a>10: Utbilda användare

Utbildningsanvändare kan spara dina användare och säkerhetsåtgärder genom att lägga mycket tid och bli frustrerad. Smarta användare har mindre chans att öppna bifogade filer eller klicka på länkar i tveksamma e-postmeddelanden, och risken är större att de undviker misstänkta webbplatser.

Nu finns en handbok om [cybersäkerhet från](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) Harvard School som ger utmärkt vägledning om att etablera en stark säkerhetskultur inom organisationen, bland annat utbildningsanvändare för att identifiera nätfiskeattacker.

Microsoft 365 följande resurser för att informera användarna i organisationen:

****

|Begrepp|Resurser|
|---|---|
|Microsoft 365|[Anpassningsbara utbildningsvägar](/office365/customlearning/) <p>De här resurserna kan hjälpa dig att sätta ihop utbildning för slutanvändarna i organisationen|
|Microsoft 365-säkerhet|[Utbildningsmodul: Skydda organisationen med inbyggd och intelligent säkerhet från Microsoft 365](/learn/modules/security-with-microsoft-365) <p>I den här modulen kan du beskriva hur Microsoft 365 fungerar tillsammans och att formulera fördelarna med dessa säkerhetsfunktioner.|
|Multifaktorautentisering|[Tvåstegsverifiering: Vad är den ytterligare verifieringssidan?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Den här artikeln hjälper slutanvändarna att förstå vad multifaktorautentisering är och varför det används i organisationen.|
|

Förutom den här vägledningen rekommenderar Microsoft att dina användare gör som beskrivs i den här artikeln: Skydda ditt konto och dina enheter [från hackare och skadlig programvara.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) Dessa åtgärder omfattar:

- Använda starka lösenord
- Skydda enheter
- Aktivera säkerhetsfunktioner på Windows 10 och Mac-datorer (för ohanterade enheter)

Microsoft rekommenderar även att användare skyddar sina personliga e-postkonton genom att vidta de åtgärder som rekommenderas i följande artiklar:

- [Skydda ditt Outlook.com-konto](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Skydda ditt Gmail-konto med tvåstegsverifiering](https://go.microsoft.com/fwlink/p/?linkid=2015688)

## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11: Komma igång med Microsoft Cloud App Security

[Microsoft Cloud App Security](/cloud-app-security) får bra synlighet, kontroll över dataresa och avancerad analys för att identifiera och bekämpa cyberhot i alla dina molntjänster. När du börjar med Cloud App Security aktiveras avvikande identifieringsprinciper automatiskt, men Cloud App Security har en inledande utbildningsperiod på sju dagar då inte alla varningar för avvikande identifiering upphöjs.

Kom igång med Cloud App Security nu. Senare kan du konfigurera mer avancerad övervakning och kontroller.

- [Snabbstart: Komma igång med Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)
- [Få omedelbar funktionsanalys och avvikande identifiering](/cloud-app-security/anomaly-detection-policy)
- [Läs mer om Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Granska nya funktioner](/cloud-app-security/release-notes)
- [Visa grundläggande konfigurationsanvisningar](/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: Övervaka hot och vidta åtgärder

Microsoft 365 flera olika sätt att övervaka status och vidta lämpliga åtgärder. Den bästa utgångspunkten är Microsoft 365 säkerhetscenter ( ), där du kan se din organisations Microsoft Secure Score och eventuella aviseringar eller enheter som [https://security.microsoft.com](https://security.microsoft.com) kräver din uppmärksamhet. [](./defender/microsoft-secure-score.md)

- [Komma igång med Microsoft 365 säkerhetscenter](./defender/overview-security-center.md)
- [Övervaka och visa rapporter](./defender/overview-security-center.md)
- [Se säkerhetsportalerna i Microsoft 365](./defender/portals.md)

## <a name="next-steps"></a>Nästa steg

Grattis! Du har snabbt implementerat några av de viktigaste säkerhetsskyddet och din organisation är mycket säkrare. Nu kan du gå ännu längre med funktioner för skydd mot hot (inklusive Microsoft Defender för Endpoint), funktioner för dataklassificering och skydd och skydd av administrativa konton. En djupare, metodisk uppsättning säkerhetsrekommendationer för Microsoft 365 finns i Microsoft 365 Säkerhet för företag [beslutsfattare ..](Microsoft-365-security-for-bdm.md)

Besök även Microsofts nya säkerhetscenter på [docs.microsoft.com/security](/security).