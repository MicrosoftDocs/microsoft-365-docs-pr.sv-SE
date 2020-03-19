---
title: Konfigurationer för identitet och enhetsåtkomst – Microsoft 365 Enterprise
description: Beskriver Microsofts rekommendationer och centrala koncept för distribution av principer och konfigurationer för säker e-post, dokument och appar.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/11/2018
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 8d7adda0ded3a118676a67d0446a5744233468f3
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42812216"
---
# <a name="identity-and-device-access-configurations"></a>Konfigurationer för identitet och enhetsåtkomst

I den här artikelserien beskrivs hur du konfigurerar säker åtkomst till molntjänster via EMS-produkter (Enterprise Mobility + Security) genom att implementera en rekommenderad miljö och konfiguration, inklusive en föreskriven uppsättning principer för villkorlig åtkomst och relaterade funktioner. EMS är en kärnkomponent i Microsoft 365. Du kan använda den här vägledningen för att skydda åtkomsten till alla tjänster som är integrerade med Azure Active Directory, inklusive Office 365-tjänster, andra SaaS-tjänster och lokala program som publiceras med Azure AD Application Proxy. 

Dessa rekommendationer är anpassade till Microsoft Secure Score samt [identitetspoäng i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score), och kommer att öka dessa poäng för din organisation. Dessa rekommendationer hjälper dig också att implementera dessa [fem steg för att skydda din identitetsinfrastruktur](https://docs.microsoft.com/azure/security/azure-ad-secure-steps). 

Microsoft förstår att vissa organisationer har unika miljökrav eller komplexitet. Om du är en av dessa organisationer använder du dessa rekommendationer som utgångspunkt. De flesta organisationer kan dock implementera dessa rekommendationer enligt vad som föreskrivs. 

## <a name="intended-audience"></a>Avsedd målgrupp

Dessa rekommendationer är avsedda för företagsarkitekter och IT-proffs som är bekanta med [Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx) och [Microsoft Enterprise Mobility + Security](https://microsoft.com/ems), som bland annat inkluderar Azure Active Directory (identitet), Microsoft Intune (enhetshantering) och Azure Information Protection (dataskydd).

### <a name="customer-environment"></a>Kundmiljö

De rekommenderade principerna gäller för företagsorganisationer som arbetar både helt inom Microsoft-molnet och för kunder med hybridinfrastruktur (distribueras både lokalt och Microsoft-molnet).

Många av de angivna rekommendationerna är endast beroende av tjänster som endast är tillgängliga med EMS-licenser (Enterprise Mobility + Security). Rekommendationer som presenteras förutsätter fullständiga EMS E5-licensfunktioner.

För de organisationer som inte har Enterprise Mobility + Security E5-licenser rekommenderar Microsoft dig att åtminstone implementera Azure AD-grundläggande skyddsfunktioner som ingår i alla abonnemang. Mer information finns i artikeln [What is baseline protection](/azure/active-directory/active-directory-conditional-access-baseline-protection), in the Azure AD library.

### <a name="caveats"></a>Varningar

Din organisation kan omfattas av lagstadgade eller andra efterlevnadskrav, inklusive specifika rekommendationer som kan kräva att du tillämpar principer som avviker från dessa rekommenderade konfigurationer. Dessa konfigurationer rekommenderar användningskontroller som inte har varit tillgängliga historiskt. Vi rekommenderar dessa kontroller, eftersom vi anser att de utgör en balans mellan säkerhet och produktivitet.  

Vi har gjort vårt bästa för att ta hänsyn till en mängd olika organisatoriska skyddskrav, men vi kan inte redogöra för alla möjliga krav eller för alla unika aspekter av din organisation.

## <a name="three-tiers-of-protection"></a>Tre nivåer av skydd

De flesta organisationer har särskilda krav på säkerhet och dataskydd. Dessa krav varierar beroende på branschsegment och jobbfunktioner inom organisationer. Din juridiska avdelning och Office 365-administratörer kan till exempel kräva ytterligare säkerhets- och informationsskyddskontroller runt sin e-postkorrespondens som inte krävs för andra affärsenhetsanvändare. 

Varje bransch har också sin egen uppsättning specialiserade regler. I stället för att tillhandahålla en lista över alla möjliga säkerhetsalternativ eller en rekommendation per branschsegment eller jobbfunktion har rekommendationer lämnats för tre olika nivåer av säkerhet och skydd som kan tillämpas baserat på granulariteten i dina behov .

- **Baslinjeskydd**: Vi rekommenderar att du fastställer en minimistandard för att skydda data samt de identiteter och enheter som kommer åt dina data. Du kan följa dessa originalrekommendationer för att ge ett starkt standardskydd som uppfyller behoven hos många organisationer.
- **Känsligt skydd**: Vissa kunder har en delmängd av data som måste skyddas på högre nivåer, eller så kan de kräva att alla data skyddas på en högre nivå. Du kan använda ökat skydd för alla eller specifika datauppsättningar i Office 365-miljön. Vi rekommenderar att du skyddar identiteter och enheter som får åtkomst till känsliga data med jämförbara säkerhetsnivåer.  
- **Mycket reglerad**: Vissa organisationer kan ha en liten mängd data som är högt klassificerade, consititutes affärshemligheter, eller är reglerade data. Microsoft tillhandahåller funktioner för att hjälpa organisationer att uppfylla dessa krav, inklusive extra skydd för identiteter och enheter.

![Säkerhetskon - Alla kunder > Vissa kunder > specifika kunder. Bred tillämpning på specifika program](../media/M365-idquality-threetiers.png)

Den här vägledningen visar hur du implementerar skydd för identiteter och enheter för var och en av dessa skyddsnivåer. Använd den här vägledningen som utgångspunkt för din organisation och justera principerna för att uppfylla organisationens specifika krav.

Det är viktigt att använda konsekventa skyddsnivåer för dina data, identiteter och enheter. Om du till exempel implementerar den här vägledningen måste du skydda dina data på jämförbara nivåer. Dessa arkitekturmodeller visar vilka funktioner som är jämförbara.

**Identitets- och enhetsskydd för Office 365**<br/>
![Miniatyr för affischen "Identitets- och enhetsskydd för Office 365"](../media/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Fler språk](https://www.microsoft.com/download/details.aspx?id=55032)

**Filskyddslösningar i Office 365**<br/>
![Miniatyr för affischen "Filskyddslösningar i Office 365"](../media/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](https://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](https://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>Kompromisser om säkerhet och produktivitet

För att genomföra en säkerhetsstrategi krävs kompromisser mellan säkerhet och produktivitet. Det är bra att utvärdera hur varje beslut påverkar balansen mellan säkerhet, funktionalitet och användarvänlighet.

![Säkerhet triaden balansera säkerhet, funktionalitet och användarvänlighet.](../media/policies-configurations/security-triad.png)

De rekommendationer som lämnas grundar sig på följande principer:

- Känna din målgrupp och vara flexibel till deras säkerhets- och funktionskrav.
- Tillämpa en säkerhetsprincip precis i tid och se till att den är meningsfull.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Tjänster och begrepp för skydd av identitets- och enhetsåtkomst

Microsoft 365 Enterprise är utformat för stora organisationer och integrerar Office 365 Enterprise, Windows 10 Enterprise och Enterprise Mobility + Security (EMS), så att alla kan vara kreativa och arbeta tillsammans på ett säkert sätt.

Det här avsnittet innehåller en översikt över Microsoft 365-tjänsterna och funktionerna som är viktiga för identitets- och enhetsåtkomst.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD tillhandahåller en fullständig uppsättning funktioner för identitetshantering. För att skydda åtkomst rekommenderar vi att du använder följande funktioner:

- **[Självbetjäning lösenordsåterställning (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)**: Låt användarna återställa sina lösenord på ett säkert och utan hjälpcentralingripande, genom att tillhandahålla verifiering av flera autentiseringsmetoder som administratören kan kontrollera.

- **[Multifaktorautentisering (MFA):](/azure/active-directory/authentication/concept-mfa-howitworks)** MFA kräver att användarna tillhandahåller två verifieringsformer, till exempel ett användarlösenord plus ett meddelande från Microsoft Authenticator-appen eller ett telefonsamtal. MFA minskar risken för att en stulen identitet kan användas för att komma åt din Office 365-miljö.

- **[Villkorlig åtkomst](/azure/active-directory/conditional-access/overview)**: Azure AD utvärderar villkoren för användarinloggningen och använder principer för villkorlig åtkomst som du skapar för att tillåta åtkomst. I den här vägledningen visar vi till exempel hur du skapar en princip för villkorlig åtkomst för att kräva enhetsefterlevnad för åtkomst till känsliga data. Detta minskar avsevärt risken för att en hackare med en stulen identitet kan komma åt dina känsliga data. Det skyddar också känsliga data på enheterna, eftersom enheterna uppfyller specifika krav på hälsa och säkerhet.

- **[Azure AD-grupper:](/azure/active-directory/fundamentals/active-directory-manage-groups)** Regler för villkorlig åtkomst, enhetshantering med Intune och till och med behörigheter till filer och webbplatser i organisationen förlitar sig på tilldelning till användar- och/eller Azure AD-grupper. Vi rekommenderar att du skapar Azure AD-grupper som motsvarar de skyddsnivåer du implementerar. Din verkställande personal är till exempel sannolikt högre värdemål för hackare. Därför är det vettigt att tilldela dessa medarbetare till en Azure AD-grupp och tilldela den här gruppen till principer för villkorlig åtkomst och andra principer som upprätthåller en högre skyddsnivå för åtkomst.

- **[Enhetsregistrering](/azure/active-directory/devices/overview)**: Du registrerar en enhet i Azure AD för att tillhandahålla en identitet till enheten. Den här identiteten används för att autentisera enheten när en användare loggar in och för att tillämpa regler för villkorlig åtkomst som kräver domänanslutna eller kompatibla datorer. För den här vägledningen använder vi enhetsregistrering för att automatiskt registrera domänanslutna Windows-datorer. Enhetsregistrering är en förutsättning för att hantera enheter med Intune. 

- **[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)**: Azure AD Identity Protection gör att du kan identifiera potentiella säkerhetsproblem som påverkar organisationens identiteter och konfigurera automatiserad reparationsprincip till låg, medelhög och hög inloggningsrisk och användarrisk. Den här vägledningen bygger på den här riskbedömningen för att tillämpa principer för villkorlig åtkomst för multifaktorautentisering. Den här vägledningen innehåller också en princip för villkorlig åtkomst som kräver att användarna ändrar sitt lösenord om högriskaktivitet upptäcks för sitt konto.

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) är Microsofts molnbaserade hanteringstjänst för mobila enheter. Den här vägledningen rekommenderar enhetshantering av Windows-datorer med Intune och rekommenderar konfigurationer av enhetsefterlevnad. Intune avgör om enheter är kompatibla och skickar dessa data till Azure AD för att använda när du tillämpar principer för villkorlig åtkomst.

#### <a name="intune-app-protection"></a>Intune-appskydd

[Intune-appskyddsprinciper](https://docs.microsoft.com/intune/app-protection-policy) kan användas för att skydda organisationens data i mobilappar, med eller utan att registrera enheter i hanteringen. Intune hjälper till att skydda Office 365-information, se till att dina anställda fortfarande kan vara produktiva och förhindra dataförlust. Genom att implementera principer på appnivå kan du begränsa åtkomsten till företagets resurser och hålla data inom it-avdelningens kontroll.

Den här vägledningen visar hur du skapar rekommenderade principer för att genomdriva användningen av godkända appar och för att avgöra hur dessa appar kan användas med dina affärsdata.

### <a name="office-365"></a>Office 365

Den här vägledningen visar hur du implementerar en uppsättning principer för att skydda åtkomsten till Office 365, inklusive Exchange Online, SharePoint Online och OneDrive för företag. Förutom att implementera dessa principer rekommenderar vi att du också höjer skyddsnivån för din Office 365-klient med hjälp av dessa resurser:

- [Konfigurera din Office 365-klient för ökad säkerhet](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355): De här rekommendationerna gäller för originalsäkerhets för din Office 365-klientorganisation.
- [Översikt över säkerhetsöversikt för Office 365: De viktigaste prioriteringarna för de första 30 dagarna, 90 dagarna och därefter](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352): Dessa rekommendationer omfattar loggning, datastyrning, administratörsåtkomst och hotskydd.


### <a name="windows-10-and-office-365-proplus"></a>Windows 10 och Office 365 ProPlus

Windows 10 och Office 365 ProPlus är den rekommenderade klientmiljön för datorer. Vi rekommenderar Windows 10, eftersom Azure är utformat för att ge den smidigaste upplevelsen möjligt för både lokala och Azure AD. Windows 10 innehåller också avancerade säkerhetsfunktioner som kan hanteras via Intune. Office 365 ProPlus innehåller de senaste versionerna av Office-program. Dessa använder modern autentisering, vilket är säkrare och ett krav för villkorlig åtkomst. Dessa appar innehåller också förbättrade säkerhets- och efterlevnadsverktyg.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Tillämpa dessa funktioner på de tre skyddsnivåerna

I följande tabell sammanfattas våra rekommendationer för att använda dessa funktioner på de tre skyddsnivåerna.

|Skyddsmekanism|Originalplan|Känsliga|Mycket reglerad|
|:-------------------|:-------|:--------|:---------------|
|**Tillämpa MFA**|På medellång eller högre inloggningsrisk|På låg eller högre inloggningsrisk|På alla nya sessioner|
|**Framtvinga lösenordsändring**|För högriskanvändare|För högriskanvändare|För högriskanvändare|
|**Framtvinga Intune-programskydd**|Ja|Ja|Ja|
|**Framtvinga Intune-registrering (COD)**|Kräv en kompatibel eller domänansluten dator, men tillåt BYOD-telefoner/surfplattor|Kräv en kompatibel eller domänansluten enhet|Kräv en kompatibel eller domänansluten enhet|

## <a name="device-ownership"></a>Enhetsägande

Tabellen ovan återspeglar trenden för många organisationer att stödja en blandning av företagsägda enheter, samt personliga eller bring-your-own-enheter (BYODs) för att möjliggöra mobil produktivitet i hela arbetskraften. Intune-appskyddsprinciper säkerställer att e-post skyddas från att exfiltrera från Outlook-mobilappen och andra Office-mobilappar, både på företagsägda enheter och BYOD:er.  

Vi rekommenderar att företagsägda enheter hanteras av Intune eller domänanslutna för att tillämpa ytterligare skydd och kontroll. Beroende på datakänslighet kan din organisation välja att inte tillåta BYOD:er för specifika användarpopulationer eller specifika appar.

## <a name="next-steps"></a>Nästa steg

[Förutsättningsarbete för att implementera identitets- och enhetsåtkomstprinciper](identity-access-prerequisites.md)
