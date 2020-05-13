---
title: Konfigurationer för identitets- och enhetsåtkomst – Microsoft 365 Enterprise
description: I artikeln beskrivs Microsofts rekommendationer och grundläggande begrepp för distribution av principer och konfigurationer för säker e-post, dokument och appar.
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
ms.openlocfilehash: 0512d51f2789383c7612c3dbd97c0a77c2c4c7fa
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214668"
---
# <a name="identity-and-device-access-configurations"></a>Konfigurationer av identiteter och enhetsåtkomst

I den här artikelserien beskrivs hur du konfigurerar säker åtkomst till molntjänster via EMS-produkter (Enterprise Mobility + Security) genom att implementera en rekommenderad miljö och konfiguration, inklusive en föreskriven uppsättning principer för villkorlig åtkomst och relaterade funktioner. EMS är en kärnkomponent i Microsoft 365. Du kan använda den här vägledningen för att skydda åtkomsten till alla tjänster som är integrerade med Azure Active Directory, inklusive Microsoft 365-tjänster, andra SaaS-tjänster och lokala program som publiceras med Azure AD Application Proxy. 

Dessa rekommendationer är anpassade till Microsoft Secure Score samt [identitetspoäng i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)och ökar dessa poäng för din organisation. Dessa rekommendationer hjälper dig också att implementera dessa [fem steg för att skydda din identitetsinfrastruktur.](https://docs.microsoft.com/azure/security/azure-ad-secure-steps) 

Microsoft förstår att vissa organisationer har unika miljökrav eller komplexitet. Om du är en av dessa organisationer använder du dessa rekommendationer som utgångspunkt. De flesta organisationer kan dock implementera dessa rekommendationer enligt ordination. 

## <a name="intended-audience"></a>Avsedd publik

Dessa rekommendationer är avsedda för företagsarkitekter och IT-proffs som är bekanta med [Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx) och [Microsoft Enterprise Mobility + Security](https://microsoft.com/ems), som bland annat omfattar Azure Active Directory (identitet), Microsoft Intune (enhetshantering) och Azure Information Protection (dataskydd).

### <a name="customer-environment"></a>Kundmiljö

De rekommenderade principerna gäller för företagsorganisationer som arbetar både helt inom Microsoft-molnet och för kunder med hybridinfrastruktur (distribueras både lokalt och Microsoft-molnet).

Många av de rekommendationer som tillhandahålls är endast beroende av tjänster som endast är tillgängliga med Ems-licenser (Enterprise Mobility + Security). Rekommendationer som presenteras förutsätter fullständiga EMS E5-licensfunktioner.

För de organisationer som inte har Enterprise Mobility + Security E5-licenser rekommenderar Microsoft att du åtminstone implementerar Azure AD-baslinjeskyddsfunktioner som ingår i alla planer. Mer information finns i artikeln, [Vad är baslinjeskydd](/azure/active-directory/active-directory-conditional-access-baseline-protection), i Azure AD-biblioteket.

### <a name="caveats"></a>Varningar

Din organisation kan omfattas av lagstadgade eller andra efterlevnadskrav, inklusive specifika rekommendationer som kan kräva att du tillämpar principer som avviker från dessa rekommenderade konfigurationer. Dessa konfigurationer rekommenderar användningskontroller som inte historiskt har varit tillgängliga. Vi rekommenderar dessa kontroller, eftersom vi anser att de utgör en balans mellan säkerhet och produktivitet.  

Vi har gjort vårt bästa för att ta hänsyn till en mängd olika organisatoriska skyddskrav, men vi kan inte ta hänsyn till alla möjliga krav eller för alla unika aspekter av din organisation.

## <a name="three-tiers-of-protection"></a>Tre skyddsnivåer

De flesta organisationer har specifika krav på säkerhet och dataskydd. Dessa krav varierar beroende på branschsegment och jobbfunktioner inom organisationer. Din juridiska avdelning och administratörer kan till exempel kräva ytterligare säkerhets- och informationsskyddskontroller runt sin e-postkorrespondens som inte krävs för andra affärsenhetsanvändare. 

Varje bransch har också sin egen uppsättning specialiserade regler. I stället för att tillhandahålla en lista över alla möjliga säkerhetsalternativ eller en rekommendation per branschsegment eller jobbfunktion har rekommendationer tillhandahållits för tre olika säkerhets- och skyddsnivåer som kan tillämpas baserat på dina behovs granularitet.

- **Baslinjeskydd**: Vi rekommenderar att du fastställer en minimistandard för att skydda data samt de identiteter och enheter som kommer åt dina data. Du kan följa dessa originalrekommendationer för att ge ett starkt standardskydd som uppfyller behoven hos många organisationer.
- **Känsligt skydd**: Vissa kunder har en delmängd av data som måste skyddas på högre nivåer, eller så kan de kräva att alla data skyddas på en högre nivå. Du kan använda ökat skydd för alla eller specifika datauppsättningar i microsoft 365-miljön. Vi rekommenderar att du skyddar identiteter och enheter som får åtkomst till känsliga data med jämförbara säkerhetsnivåer.  
- **Starkt reglerade**: Vissa organisationer kan ha en liten mängd data som är högt klassificerade, consititutes affärshemligheter, eller är reglerade data. Microsoft tillhandahåller funktioner som hjälper organisationer att uppfylla dessa krav, inklusive extra skydd för identiteter och enheter.

![Säkerhetskon - Alla kunder > Vissa kunder > specifika kunder. Bred tillämpning på specifik tillämpning](../media/M365-idquality-threetiers.png)

Den här vägledningen visar hur du implementerar skydd för identiteter och enheter för var och en av dessa skyddsnivåer. Använd den här vägledningen som utgångspunkt för din organisation och justera principerna så att de uppfyller organisationens specifika krav.

Det är viktigt att använda konsekventa skyddsnivåer för dina data, identiteter och enheter. Om du till exempel implementerar den här vägledningen måste du skydda dina data på jämförbara nivåer. Dessa arkitekturmodeller visar vilka funktioner som är jämförbara.

**Identitets- och enhetsskydd för Office 365**<br/>
![Miniatyr för affischen "Identitets- och enhetsskydd för Office 365"](../media/O365_Identity_device_protection_thumb.png)<br/>
[PDF-dokument](https://go.microsoft.com/fwlink/p/?linkid=841656)  |  [Visio (på sätt och vi)](https://go.microsoft.com/fwlink/p/?linkid=841657)  |  [Fler språk](https://www.microsoft.com/download/details.aspx?id=55032)

**Lösningar för filskydd i Office 365**<br/>
![Miniatyr för affischen "Filskyddslösningar i Office 365"](../media/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](https://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](https://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>Kompromisser om säkerhet och produktivitet

Genomförandet av en säkerhetsstrategi kräver kompromisser mellan säkerhet och produktivitet. Det är bra att utvärdera hur varje beslut påverkar balansen mellan säkerhet, funktionalitet och användarvänlighet.

![Säkerhet triad balansera säkerhet, funktionalitet och användarvänlighet.](../media/policies-configurations/security-triad.png)

Rekommendationerna bygger på följande principer:

- Lär känna din målgrupp och var flexibel till deras säkerhet och funktionella krav.
- Tillämpa en säkerhetsprincip precis i tid och se till att den är meningsfull.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Tjänster och koncept för skydd av identitets- och enhetsåtkomst

Microsoft 365 Enterprise är utformat för stora organisationer och integrerar Office 365 Enterprise, Windows 10 Enterprise och Enterprise Mobility + Security (EMS), så att alla kan vara kreativa och arbeta tillsammans på ett säkert sätt.

Det här avsnittet innehåller en översikt över de tjänster och funktioner för Microsoft 365 som är viktiga för identitets- och enhetsåtkomst.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD tillhandahåller en komplett uppsättning funktioner för identitetshantering. För att skydda åtkomst rekommenderar vi att du använder följande funktioner:

- **[Självbetjäningslösenordsåterställning (SSPR):](/azure/active-directory/authentication/concept-sspr-howitworks)** Tillåt användarna att återställa sina lösenord på ett säkert och utan hjälpåtgärder genom att tillhandahålla verifiering av flera autentiseringsmetoder som administratören kan kontrollera.

- **[MFA (Multifaktor authentication):](/azure/active-directory/authentication/concept-mfa-howitworks)** MFA kräver att användarna tillhandahåller två former av verifiering, till exempel ett användarlösenord plus ett meddelande från Microsoft Authenticator-appen eller ett telefonsamtal. MFA minskar kraftigt risken för att en stulen identitet kan användas för att komma åt din miljö.

- **[Villkorlig åtkomst](/azure/active-directory/conditional-access/overview)**: Azure AD utvärderar villkoren för användarinloggningen och använder principer för villkorlig åtkomst som du skapar för att tillåta åtkomst. I den här vägledningen visar vi till exempel hur du skapar en princip för villkorlig åtkomst för att kräva enhetsefterlevnad för åtkomst till känsliga data. Detta minskar kraftigt risken för att en hackare med en stulen identitet kan komma åt dina känsliga data. Det skyddar också känsliga data på enheterna, eftersom enheterna uppfyller särskilda krav för hälsa och säkerhet.

- **[Azure AD-grupper:](/azure/active-directory/fundamentals/active-directory-manage-groups)** Regler för villkorlig åtkomst, enhetshantering med Intune och till och med behörigheter till filer och platser i organisationen förlitar sig på tilldelning till användare- och/eller Azure AD-grupper. Vi rekommenderar att du skapar Azure AD-grupper som motsvarar de skyddsnivåer som du implementerar. Till exempel är din verkställande personal sannolikt högre värde mål för hackare. Därför är det vettigt att tilldela dessa anställda till en Azure AD-grupp och tilldela den här gruppen till principer för villkorlig åtkomst och andra principer som upprätthåller en högre skyddsnivå för åtkomst.

- **[Enhetsregistrering:](/azure/active-directory/devices/overview)** Du registrerar en enhet i Azure AD för att tillhandahålla en identitet till enheten. Den här identiteten används för att autentisera enheten när en användare loggar in och för att tillämpa regler för villkorlig åtkomst som kräver domänanslutna eller kompatibla datorer. För den här vägledningen använder vi enhetsregistrering för att automatiskt registrera domänanslutna Windows-datorer. Enhetsregistrering är en förutsättning för att hantera enheter med Intune. 

- **[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)**: Azure AD Identity Protection gör att du kan identifiera potentiella sårbarheter som påverkar organisationens identiteter och konfigurera automatisk reparationsprincip till låg, medelstor och hög inloggningsrisk och användarrisk. Den här vägledningen är beroende av den här riskbedömningen för att tillämpa principer för villkorlig åtkomst för multifaktorautentisering. Den här vägledningen innehåller också en princip för villkorlig åtkomst som kräver att användarna ändrar sitt lösenord om högriskaktivitet upptäcks för deras konto.

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) är Microsofts molnbaserade tjänst för hantering av mobila enheter. Den här vägledningen rekommenderar enhetshantering av Windows-datorer med Intune och rekommenderar konfigurationer av enhetsefterlevnadsprinciper. Intune avgör om enheter är kompatibla och skickar dessa data till Azure AD som ska användas vid tillämpning av principer för villkorlig åtkomst.

#### <a name="intune-app-protection"></a>Skydd av Intune-appar

[Intune-appskyddsprinciper](https://docs.microsoft.com/intune/app-protection-policy) kan användas för att skydda organisationens data i mobilappar, med eller utan att registrera enheter i hanteringen. Intune hjälper till att skydda informationen, se till att dina anställda fortfarande kan vara produktiva och förhindra dataförlust. Genom att implementera principer på appnivå kan du begränsa åtkomsten till företagets resurser och hålla data inom IT-avdelningens kontroll.

Den här vägledningen visar hur du skapar rekommenderade principer för att genomdriva användningen av godkända appar och avgöra hur dessa appar kan användas med dina affärsdata.

### <a name="microsoft-365"></a>Microsoft 365

Den här vägledningen visar hur du implementerar en uppsättning principer för att skydda åtkomsten till Office 365, inklusive Exchange Online, SharePoint Online och OneDrive för företag. Förutom att implementera dessa principer rekommenderar vi att du även höjer skyddsnivån för din klient med hjälp av dessa resurser:

- [Konfigurera din klient för ökad säkerhet](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355): Dessa rekommendationer gäller för originalsäkerhet för din klient.
- [Microsoft 365-säkerhetsfärdplan: De viktigaste prioriteringarna för de första 30 dagarna, 90 dagarna och därefter](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap): Dessa rekommendationer omfattar loggning, datastyrning, administratörsåtkomst och hotskydd.


### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 och  Microsoft 365-appar för företag

Windows 10 och Microsoft 365 Apps för företag är den rekommenderade klientmiljön för datorer. Vi rekommenderar Windows 10, eftersom Azure är utformat för att ge den smidigaste upplevelsen som möjligt för både lokala och Azure AD. Windows 10 innehåller även avancerade säkerhetsfunktioner som kan hanteras via Intune. Microsoft 365 Apps for Enterprise innehåller de senaste versionerna av Office-program. Dessa använder modern autentisering, vilket är säkrare och ett krav på villkorlig åtkomst. Dessa appar innehåller även förbättrade säkerhets- och efterlevnadsverktyg.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Tillämpa dessa funktioner på de tre skyddsnivåerna

I följande tabell sammanfattas våra rekommendationer för att använda dessa funktioner över de tre skyddsnivåerna.

|Skyddsmekanism|Grundläggande|Känslig|Strikt reglerad|
|:-------------------|:-------|:--------|:---------------|
|**Genomdriva MFA**|På medium eller över inloggningsrisk|På låg eller högre inloggningsrisk|På alla nya sessioner|
|**Framtvinga lösenordsändring**|För högriskanvändare|För högriskanvändare|För högriskanvändare|
|**Framtvinga intune-programskydd**|Ja|Ja|Ja|
|**Framtvinga Intune-registrering (COD)**|Kräv en kompatibel eller domänansluten dator, men tillåt BYOD-telefoner/surfplattor|Kräv en kompatibel eller domänansluten enhet|Kräv en kompatibel eller domänansluten enhet|

## <a name="device-ownership"></a>Ägande av enhet

Tabellen ovan återspeglar trenden för många organisationer att stödja en blandning av företagsägda enheter, samt personliga eller bring-your-own-enheter (BYODs) för att möjliggöra mobil produktivitet i hela arbetskraften. Intune-appskyddsprinciper säkerställer att e-post skyddas från att exfiltrating från Outlook-mobilappen och andra Office-mobilappar, på både företagsägda enheter och BYOD:er.  

Vi rekommenderar att företagsägda enheter hanteras av Intune eller domänkoppling för att tillämpa ytterligare skydd och kontroll. Beroende på datakänslighet kan din organisation välja att inte tillåta BYODs för specifika användargrupper eller specifika appar.

## <a name="next-steps"></a>Nästa steg

[Förutsättningsarbete för att implementera principer för identitets- och enhetsåtkomst](identity-access-prerequisites.md)
