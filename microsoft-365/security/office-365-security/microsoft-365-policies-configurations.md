---
title: Konfigurationer för identitets-och enhets åtkomst – Microsoft 365 för företag
description: Här beskrivs Microsofts rekommendationer och grundläggande koncept för distribution av säkra principer och konfigurationer för e-post, dokument och appar.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/29/2020
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-overview
ms.openlocfilehash: 993dd1ed66ca5bc6635c0eadf2dc7345ab84b57d
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356925"
---
# <a name="identity-and-device-access-configurations"></a>Konfigurationer av identiteter och enhetsåtkomst

Den moderna säkerhets omkretsen i din organisation utökas nu bortom ditt nätverk för att omfatta användare som har åtkomst till molnbaserade program från valfri plats med olika enheter. Din säkerhets infrastruktur måste avgöra om en viss åtkomstbegäran ska beviljas och under vilka omständigheter.

Denna bestämning bör baseras på användar kontot för inloggningen, den enhet som används, programmet som användaren använder för åtkomst, den plats där åtkomstbegäran görs och en bedömning av risken för begäran. Denna funktion hjälper till att säkerställa att endast godkända användare och enheter kan komma åt dina kritiska resurser.

I den här artikeln beskrivs en uppsättning nödvändiga konfigurationer för identitets-och enhets åtkomst och en uppsättning villkorliga åtkomst tjänster för Azure Active Directory (Azure AD), Microsoft Intune och andra principer för att skydda åtkomst till Microsoft 365 för företags moln program och tjänster, andra SaaS-tjänster och lokala program som publicerats med Azure AD Application Proxy.

Inställningar och principer för åtkomst till identiteter och enheter rekommenderas i tre nivåer: baseline-skydd, känsligt skydd och skydd för miljöer med mycket reglerade eller sekretessbelagda data. Dessa nivåer och deras motsvarande konfigurationer ger konsekventa skyddsnivåer för dina data, identiteter och enheter.

Dessa möjligheter och deras rekommendationer:

- Stöds i Microsoft 365 E3 och Microsoft 365 E5.
- Är justerade med [Microsofts säkra Poäng](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) och [identitets poängen i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)och ökar poängen för din organisation.
- Hjälper dig att implementera dessa [fem steg för att skydda din identitets infrastruktur](https://docs.microsoft.com/azure/security/azure-ad-secure-steps).

Om din organisation har unika miljö krav eller komplexa, Använd dessa rekommendationer som utgångs punkt. De flesta organisationer kan använda dessa rekommendationer enligt anvisningarna.

>[!Note]
>Microsoft säljer också Enterprise Mobility + Security (EMS) för Office 365-prenumerationer. EMS-och EMS-funktioner är likvärdiga med Microsoft 365 E3 och Microsoft 365 E5. Se [EMS-abonnemang](https://www.microsoft.com/en-us/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) för mer information.
>

## <a name="intended-audience"></a>Avsedd mål grupp

Dessa rekommendationer är avsedda för företags arkitekter och IT-proffs som är bekanta med Microsoft 365 Cloud Productivity och säkerhets tjänster, vilka inkluderar Azure AD (identitet), Microsoft Intune (enhets hantering) och Azure information Protection (data skydd).

### <a name="customer-environment"></a>Kund miljö

Rekommenderade principer är tillämpliga för företags organisationer som både fungerar i Microsofts moln och för kunder med hybrid identitets infrastruktur, som är en lokal Active Directory Domain Services-skog som synkroniseras med en Azure AD-klient.

Många av de medföljande rekommendationerna är bara tillgängliga med Microsoft 365 E5, Microsoft 365 E3 med identitets & hot Protection-tillägg, EMS-och Azure Premium P2-licenser.

För de organisationer som inte har dessa licenser rekommenderar Microsoft att du minst implementerar [säkerhets standarder](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), som ingår i alla Microsoft 365-abonnemang.

### <a name="caveats"></a>Villkor

Din organisation kan vara föremål för regler eller andra krav på efterlevnad, inklusive specifika rekommendationer som kan kräva att du tillämpar principer som går vidare från dessa rekommenderade konfigurationer. Dessa konfigurationer rekommenderar användnings kontroller som inte tidigare varit tillgängliga. Vi rekommenderar de här kontrollerna eftersom vi tror att de representerar en avvägning mellan säkerhet och produktivitet.

Vi har gjort vårt bästa för att få ett stort utbud av organisationens skydds krav, men vi kan inte uppfylla alla möjliga krav eller för alla unika aspekter av organisationen.

## <a name="three-tiers-of-protection"></a>Tre skydds nivåer

De flesta organisationer har särskilda krav på säkerhet och data skydd. De här kraven varierar beroende på bransch och efter jobb funktioner inom organisationer. Din juridiska avdelning och administratörer kan till exempel behöva ytterligare säkerhets-och informations skydds kontroller kring deras e-postkorrespondens som inte behövs för andra affär senheter.

Varje bransch har också sin egen uppsättning specialiserade regler. I stället för att visa en lista över alla möjliga säkerhets alternativ eller en rekommendation per bransch eller arbets gångs funktion har rekommendationer gjorts för tre olika typer av säkerhet och skydd som kan användas baserat på hur detaljerad dina behov är.

- **Grundläggande skydd**: Vi rekommenderar att du fastställer en minsta standard för att skydda data samt identiteter och enheter som har åtkomst till dina data. Du kan följa dessa rikt linjer för att tillhandahålla starkt standard skydd som uppfyller behoven hos många organisationer.
- **Känsligt skydd**: vissa kunder har en delmängd data som måste skyddas på högre nivåer, eller så kan de kräva att alla data skyddas på en högre nivå. Du kan använda ökat skydd för alla eller specifika data uppsättningar i din Microsoft 365-miljö. Vi rekommenderar att du skyddar identiteter och enheter som använder känsliga data med jämförbara säkerhets nivåer.
- **Mycket reglerad**: vissa organisationer kan ha en mindre mängd data som är starkt klassificerade, utgör bransch hemligheter eller är reglerade data. Microsoft tillhandahåller funktioner för att hjälpa organisationer att möta dessa krav, inklusive ökat skydd för identiteter och enheter.

![Säkerhets kon – alla kunder > vissa kunder > specifika kunder. Brett program för specifika program](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

Den här vägledningen visar hur du implementerar skydd för identiteter och enheter för var och en av de här skydds nivåerna. Använd den här vägledningen som utgångs punkt för organisationen och justera principerna för att uppfylla organisationens specifika krav.

Det är viktigt att använda konsekventa skyddsnivåer för dina data, identiteter och enheter. Om du till exempel implementerar den här vägledningen bör du se till att skydda dina data på jämförbara nivåer.

Arkitekturen **för identiteter och enheter för Microsoft 365** -arkitekturer visar vilka funktioner som är jämförbara.

[![Bild av knapp för identitet och enhets skydd för Microsoft 365-affisch](../../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br/>  [Visa som en PDF-fil](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Ladda ned som PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Ladda ned som Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

Se dessutom artikeln [distribuera informations skydd för data integritets regler](../../solutions/information-protection-deploy.md) för att skydda information som lagras i Microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Handel med säkerhet och produktivitet

Införandet av säkerhets strategin kräver handel mellan säkerhet och produktivitet. Det är bra att utvärdera hur ett beslut påverkar säkerheten, funktionerna och användar vänligheten.

![Säkerhet Triad balansering, funktioner och användar vänlighet.](../../media/microsoft-365-policies-configurations/security-triad.png)

Rekommendationerna bygger på följande principer:

- Bekanta dig med användarna och vara flexibla till deras säkerhets-och funktions krav.
- Tillämpa en säkerhets princip när som helst och se till att den är meningsfull.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Tjänster och koncept för åtkomst skydd för identiteter och enheter

Microsoft 365 för företag är utformat för stora organisationer för att ge alla möjlighet att vara kreativa och samar beta på ett säkert sätt.

Det här avsnittet innehåller en översikt över de Microsoft 365-tjänster och-funktioner som är viktiga för åtkomst till identiteter och enheter.

### <a name="azure-ad"></a>Azure AD

Azure AD tillhandahåller en full uppsättning funktioner för identitets hantering. Vi rekommenderar att du använder de här funktionerna för att skydda åtkomst.

|Resurs eller funktion|Beskrivning|Licensiering|
|---|---|---|
|[Multifaktorautentisering (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA kräver att användare tillhandahåller två former av verifiering, till exempel ett användar lösen ord samt ett meddelande från programmet Microsoft Authenticator eller ett telefonsamtal. MFA minskar risken att stulna uppgifter kan användas för att komma åt din miljö. Microsoft 365 använder Azure Multi-Factor autentiseringstjänst-tjänsten för MFA-baserade inloggnings program.|Microsoft 365 E3 eller E5|
|[Med villkorsstyrd åtkomst](/azure/active-directory/conditional-access/overview)|Azure AD utvärderar villkoren för användarens inloggning och använder principer för villkorsstyrd åtkomst för att fastställa tillåten åtkomst. I den här vägledningen visar vi dig hur du skapar en princip för villkorsstyrd åtkomst så att du måste ha nödvändig åtkomst till känslig information. Detta minskar risken för att en hackare med sin egen enhet och stulna autentiseringsuppgifter kan komma åt dina känsliga data. Det skyddar också känslig information på enheterna, eftersom enheterna måste uppfylla specifika krav på hälsa och säkerhet.|Microsoft 365 E3 eller E5|
|[Azure AD-grupper](/azure/active-directory/fundamentals/active-directory-manage-groups)|Principer för villkorsstyrd åtkomst, enhets hantering med Intune och till och med behörigheter till filer och webbplatser i din organisation är beroende av tilldelningen till användar konton eller Azure AD-grupper. Vi rekommenderar att du skapar Azure AD-grupper som motsvarar den skydds nivå du implementerar. Din exekutiva personal är till exempel troligen högre värde mål för hackare. Därför är det bra att lägga till användar konton för dessa anställda i en Azure AD-grupp och tilldela den här gruppen till principer för villkorlig åtkomst och andra principer som tvingar fram en högre skydds nivå för Access.|Microsoft 365 E3 eller E5|
|[Enhets registrering](/azure/active-directory/devices/overview)|Du registrerar en enhet i Azure AD för att skapa en identitet för enheten. Denna identitet används för att autentisera enheten när en användare loggar in och för att tillämpa villkorsstyrda åtkomst principer som kräver domänanslutna eller kompatibla datorer. För den här vägledningen använder vi enhets registrering för att automatiskt registrera domänanslutna Windows-datorer. Enhets registrering är en förutsättning för att hantera enheter med Intune.|Microsoft 365 E3 eller E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|Gör det möjligt att upptäcka potentiella säkerhets problem som påverkar organisationens identitet och konfigurera automatisk reparations princip för att Visa riskerna med låg, medelhög och stor inloggning och användare. Den här vägledningen är beroende av denna riskbedömning för att tillämpa principer för villkorsstyrd åtkomst för multifaktorautentisering. Den här vägledningen innehåller även en policy för villkorsstyrd åtkomst som kräver att användare ändrar sitt lösen ord om en aktivitet med hög risk identifieras för deras konto.|Microsoft 365 E5, Microsoft 365 E3 med tillägget identitets & hot Protection, EMS E5 eller Azure Premium P2-licenser|
|[Självbetjäning för återställning av lösen ord (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|Tillåt att dina användare återställer sina lösen ord på ett säkert sätt och utan hjälp genom att kontrol lera flera autentiseringsmetoder som administratören kan kontrol lera.|Microsoft 365 E3 eller E5|
|[Lösen ords skydd i Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)|Identifiera och blockera kända svaga lösen ord och deras varianter och ytterligare svaga termer som är specifika för din organisation. Standard globala förbjudna lösenordslistor tillämpas automatiskt på alla användare i en Azure AD-klient. Du kan definiera ytterligare poster i en anpassad förbjuden lösenordslista. När användare ändrar eller återställer sina lösenord kontrolleras dessa förbjudna lösenordslistor för att använda starka lösenord.|Microsoft 365 E3 eller E5|
|

Här är komponenterna i identitets-och enhets åtkomst, inklusive Intune och Azure AD-objekt, inställningar och under tjänster.

![Komponenter i åtkomst till identiteter och enheter](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) är Microsofts molnbaserade tjänst för mobila enheter. De här anvisningarna rekommenderar att du hanterar Windows-datorer med Intune och rekommenderar konfigurering av principer för efterlevnadsprinciper. Intune avgör om enheter är kompatibla och skickar dessa data till Azure AD för användning när principer för villkorsstyrd åtkomst tillämpas.

#### <a name="intune-app-protection"></a>Program skydd i Intune

[Intune](https://docs.microsoft.com/intune/app-protection-policy) -principer för appar kan användas för att skydda organisationens data i mobilappar, med eller utan att registrera enheter i hanteringen. Intune skyddar informationen och säkerställer att dina anställda kan arbeta produktivt och förhindra data förlust. Genom att implementera principer för program nivå kan du begränsa åtkomsten till företags resurserna och hålla informationen i kontrollen över din IT-avdelning.

Den här vägledningen visar hur du skapar rekommenderade principer för att använda godkända appar och för att bestämma hur dessa appar ska kunna användas med dina affärs data.

### <a name="microsoft-365"></a>Microsoft 365

Den här vägledningen visar hur du implementerar en uppsättning principer för att skydda åtkomst till Microsoft 365-moln tjänster, inklusive Microsoft Teams, Exchange Online, SharePoint Online och OneDrive för företag. Förutom att implementera dessa principer rekommenderar vi att du också höjer skydds nivån för klient organisationen med följande resurser:

- [Konfigurera din klientorganisationen för bättre säkerhet](tenant-wide-setup-for-increased-security.md)

  Rekommendationer som gäller för din klient organisations säkerhet.

- [Säkerhets översikt: Top prioriteringar för de första 30 dagarna, 90 dagar och senare](security-roadmap.md)

  Rekommendationer som inkluderar loggning, data styrning, administratörs åtkomst och skydd mot hot.

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 och  Microsoft 365-appar för företag

Windows 10 med Microsoft 365-appar för företag är den rekommenderade klient miljön för datorer. Vi rekommenderar Windows 10 eftersom Azure är utformat för att erbjuda den bästa möjliga upplevelsen för både lokala och Azure-annonser. Windows 10 inkluderar också avancerade säkerhetsfunktioner som kan hanteras via Intune. Microsoft 365-appar för företag innehåller de senaste versionerna av Office-programmen. Dessa används för modern lösenordsautentisering, som är säkrare och ett krav för villkorlig åtkomst. Dessa program inkluderar också förbättrade säkerhets-och efterföljandekrav.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Hur de här funktionerna tillämpas på de tre skydds nivåerna

I följande tabell sammanfattas våra rekommendationer för att använda de här funktionerna på de tre skydds nivåerna.

|Skydds funktion|Grundläggande|Känslig|Strikt reglerad|
|---|---|---|---|
|**Påtvinga MFA**|På medium eller över inloggnings risker|På låg eller över inloggnings risker|För alla nya sessioner|
|**Tvinga lösen ords ändring**|För användare med hög risk|För användare med hög risk|För användare med hög risk|
|**Genomdriva Intune-programskydd**|Ja|Ja|Ja|
|**Tvinga Intune-registrering för företagsägda enheter**|Kräv en kompatibel eller domänansluten dator, men tillåt fasta enheter (BYOD) telefoner och surfplattor|Kräv en kompatibel eller domänansluten enhet|Kräv en kompatibel eller domänansluten enhet|
|

## <a name="device-ownership"></a>Enhetens ägarskap

Tabellen ovan visar trenden för många organisationer för att stödja en blandning av organisations ägda enheter, samt personligt och BYODs, för att möjliggöra mobil produktivitet. Intune-principer för appar säkerställer att e-post skyddas från exfiltrating av Outlook-mobilappen och andra Office-mobilappar, på både företagsägda enheter och BYODs.

Vi rekommenderar att organisations enheter hanteras av Intune eller domänbaserad domän för att tillämpa ytterligare skydd och kontroll. Beroende på data känslighet kan din organisation välja att inte tillåta BYODs för specifika användar populationer eller särskilda appar.

## <a name="deployment-and-your-apps"></a>Distribution och dina appar

Innan du konfigurerar och har konfigurerat identitets-och enhets åtkomst för Azure AD-integrerade appar måste du:

- Bestäm vilka program som ska användas i organisationen som du vill skydda.
- Analysera den här listan med program för att fastställa uppsättningar med principer som ger lämpliga skydds nivåer.

  Du bör inte skapa separata uppsättningar principer för program, eftersom hanteringen av dem kan bli besvärlig. Microsoft rekommenderar att du grupperar dina appar som har samma skydds krav för samma användare.

  Du kan till exempel ha en uppsättning principer som inkluderar alla Microsoft 365-appar för alla dina användare om original planens skydd och en andra uppsättning principer för alla känsliga appar, till exempel de som används av Human Resources eller ekonomi avdelningar, och tillämpa dem på dessa grupper.

När du har fastställt en uppsättning principer för de program som du vill säkra kan du lyfta bort principerna till användarna stegvist, adresserings problem på vägen.

Konfigurera till exempel de principer som ska användas för alla Microsoft 365-appar för bara Exchange Online med de ytterligare ändringarna för Exchange. Slå på dessa principer till användarna och arbeta igenom eventuella problem. Sedan lägger du till Teams och ändrar dem till dina användare. Lägg sedan till SharePoint med de ytterligare ändringarna. Fortsätt lägga till resten av dina program tills du säkert kan konfigurera dessa rikt linjer för alla Microsoft 365-appar.

För dina känsliga appar kan du till och med skapa en uppsättning principer och lägga till en app i taget och arbeta igenom eventuella problem tills de tas med i den känsliga program princip uppsättningen.

Microsoft rekommenderar att du inte skapar princip uppsättningar som gäller för alla program, eftersom det kan leda till vissa oavsiktliga konfigurationer. Principer som blockerar alla appar kan till exempel låsa dina administratörer från Azure-portalen och undantagen kan inte konfigureras för viktiga slut punkter som Microsoft Graph.

## <a name="steps-in-the-process-of-configuring-identity-and-device-access"></a>Steg i processen med att konfigurera åtkomst för identitet och enhet

![Anvisningar för hur du konfigurerar åtkomst till identitet och enheter.](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. Konfigurera nödvändiga identitets funktioner och deras inställningar.
2. Konfigurera principer för villkorsstyrd åtkomst för den gemensamma identiteten och åtkomsten.
3. Konfigurera villkorsstyrda åtkomst principer för gäster och externa användare.
4. Konfigurera villkorsstyrd åtkomst policy för Microsoft 365-molnappar som Microsoft Teams, Exchange Online och SharePoint.

Efter att du har konfigurerat identitets-och enhets åtkomst kan du läsa mer i [Azure AD Feature Deployment Guide](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2) för en stegvis check lista över ytterligare funktioner för att överväga och konfigurera [Azure AD Identity](https://docs.microsoft.com/azure/active-directory/governance/) för att skydda, övervaka och granska åtkomst.

## <a name="next-step"></a>Nästa steg

[Nödvändigt arbete för implementering av identitets-och enhets åtkomst principer](identity-access-prerequisites.md)
