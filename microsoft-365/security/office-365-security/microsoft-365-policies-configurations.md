---
title: Konfigurationer för identitets- och enhetsåtkomst – Microsoft 365 för företag
description: Här beskrivs Microsofts rekommendationer och kärnbegrepp för distribution av säkra principer och konfigurationer för e-post, dokument och appar.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.technology: mdo
ms.openlocfilehash: 9d7170ff261a53ba5755134973a912221363b3c8
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599813"
---
# <a name="identity-and-device-access-configurations"></a>Konfigurationer av identiteter och enhetsåtkomst

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)

Organisationens moderna säkerhets perimeter omfattar nu mer än nätverket så att användare kan komma åt molnbaserade appar från valfri plats med en mängd olika enheter. Säkerhetsinfrastrukturen måste avgöra om en viss åtkomstbegäran ska beviljas och under vilka förhållanden.

Det här avgörandet bör baseras på användarkontot för inloggningen, enheten som används, den app användaren använder för åtkomst, den plats som åtkomstbegäran görs från och en bedömning av risken med begäran. Denna funktion hjälper till att säkerställa att endast godkända användare och enheter kan komma åt dina kritiska resurser.

Den här serien med artiklar beskriver en uppsättning konfigurationer av krav på identitet och enhetsåtkomst och en uppsättning villkorsstyrda åtkomstsystem i Azure Active Directory (Azure AD), Microsoft Intune och andra principer för att skydda åtkomst till Microsoft 365 för företagsmolnappar och -tjänster, andra SaaS-tjänster och lokala program som publiceras med Azure AD-programproxy.

Inställningar och principer för identitet och enhetsåtkomst rekommenderas på tre nivåer: baslinjeskydd, känsligt skydd och skydd för miljöer med mycket reglerade eller klassificerade data. Dessa nivåer och deras motsvarande konfigurationer ger konsekventa skyddsnivåer för dina data, identiteter och enheter.

De här funktionerna och deras rekommendationer:

- Stöds i Microsoft 365 E3 och Microsoft 365 E5.
- Är i linje med [Microsoft Secure Score](../defender/microsoft-secure-score.md) samt [identitetspoäng i Azure AD](/azure/active-directory/fundamentals/identity-secure-score), och kommer att öka dessa resultat för din organisation.
- Kommer att hjälpa dig att implementera [de här fem stegen för att skydda din identitetsinfrastruktur.](/azure/security/azure-ad-secure-steps)

Om organisationen har unika miljökrav eller komplexitet kan du använda de här rekommendationerna som utgångspunkt. Men de flesta organisationer kan implementera de här rekommendationerna som bestämts.

Titta på den här videon för en snabb överblick över identitets- och enhetsåtkomstkonfigurationer för Microsoft 365 för företag.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxEDQ]

> [!NOTE]
> Microsoft säljer även Enterprise Mobility + Security-licenser (EMS) för Office 365-abonnemang. EMS E3- och EMS E5-funktionerna motsvarar funktionerna i Microsoft 365 E3 och Microsoft 365 E5. Mer [information finns i EMS-abonnemang.](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing)

## <a name="intended-audience"></a>Avsedd målgrupp

De här rekommendationerna är avsedda för företagsarkitekter och IT-personal som känner till Microsoft 365-molnproduktivitets- och säkerhetstjänsterna, som omfattar Azure AD (identitet), Microsoft Intune (enhetshantering) och Azure Information Protection (dataskydd).

### <a name="customer-environment"></a>Kundmiljö

De rekommenderade principerna gäller för företagsorganisationer som arbetar både helt i Microsoft-molnet och för kunder med hybrididentitetsinfrastruktur, som är en lokal AD DS-skog (Active Directory Domain Services) som synkroniseras med en Azure AD-klientorganisation.

Många av de medföljande rekommendationerna förlitar sig på tjänster som endast är tillgängliga med Microsoft 365 E5, Microsoft 365 E3 med licenserna Identity & Threat Protection, EMS E5 och Azure Premium P2.

För de organisationer som inte har dessa licenser rekommenderar [](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)Microsoft dig att åtminstone implementera säkerhetsstandarder , som ingår i alla Microsoft 365-abonnemang.

### <a name="caveats"></a>Varningar

Din organisation kan omfattas av regelkrav eller andra efterlevnadskrav, bland annat specifika rekommendationer som kan innebära att du måste använda principer som skiljer sig från dessa rekommenderade konfigurationer. Dessa konfigurationer rekommenderar användningskontroller som inte har varit tillgängliga under en längre tid. Vi rekommenderar dessa kontroller eftersom vi tror att de står för en balans mellan säkerhet och produktivitet.

Vi har gjort vårt bästa för att ta hänsyn till en mängd olika krav på organisationsskydd, men vi kan inte ta med alla möjliga krav eller för alla unika aspekter av din organisation.

## <a name="three-tiers-of-protection"></a>Tre nivåer av skydd

De flesta organisationer har särskilda krav gällande säkerhet och dataskydd. Kraven varierar efter branschsegment och efter jobbfunktioner inom organisationer. Din juridiska avdelning och administratörer kan till exempel kräva ytterligare säkerhets- och informationsskyddskontroller kring sin e-postkorrespondens som inte krävs för andra affärsenheter.

Varje bransch har också en egen uppsättning särskilda bestämmelser. I stället för att ge en lista över alla möjliga säkerhetsalternativ eller en rekommendation per branschsegment eller jobbfunktion har rekommendationer lagts till för tre olika nivåer av säkerhet och skydd som kan tillämpas utifrån hur detaljerade dina behov är.

- **Baslinjeskydd:** Vi rekommenderar att du skapar en lägsta standard för att skydda data samt de identiteter och enheter som får åtkomst till dina data. Du kan följa de här baslinjerekommendationerna för att få ett starkt standardskydd som uppfyller många organisationers behov.
- **Känsligt** skydd: Vissa kunder har en delmängd av data som måste skyddas på högre nivåer, eller så kan alla data behöva skyddas på en högre nivå. Du kan tillämpa utökat skydd på alla eller vissa datauppsättningar i din Microsoft 365-miljö. Vi rekommenderar att du skyddar identiteter och enheter som använder känslig information med liknande säkerhetsnivåer.
- **Mycket reglerad:** Vissa organisationer kan ha en liten mängd data som klassificeras i hög grad, utgör affärshemligheter eller är reglerade data. Microsoft tillhandahåller funktioner som hjälper organisationer att uppfylla dessa krav, inklusive ytterligare skydd för identiteter och enheter.

![Säkerhetskoner – Alla kunder > vissa > vissa kunder. Bred tillämpning på specifik applikation](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

Den här vägledningen visar hur du implementerar skydd för identiteter och enheter för var och en av dessa nivåer av skydd. Använd den här vägledningen som utgångspunkt för din organisation och justera principerna så att de uppfyller organisationens specifika krav.

Det är viktigt att använda konsekventa skyddsnivåer för dina data, identiteter och enheter. Om du till exempel implementerar den här vägledningen ska du se till att skydda dina data på ungefär samma nivåer.

**Identitets- och enhetsskyddet för Microsoft 365-arkitekturmodellen** visar vilka funktioner som kan jämföras.

[![Thumb-bild för identitet och enhetsskydd för Microsoft 365-affisch](../../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [Visa som PDF](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Ladda ned som PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Ladda ned som Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

Mer information finns i artikeln om [att distribuera informationsskydd för lösningen för datasekretessföreskrifter](../../solutions/information-protection-deploy.md) för att skydda information som lagras i Microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Byte av säkerhet och produktivitet

För att implementera en säkerhetsstrategi måste du byta mellan säkerhet och produktivitet. Det är bra att utvärdera hur varje beslut påverkar balans av säkerhet, funktion och enkelhet.

![Säkerhetstriadsutjämning av säkerhet, funktionalitet och användarvänlighet.](../../media/microsoft-365-policies-configurations/security-triad.png)

Rekommendationerna som ges baseras på följande principer:

- Känna till användarna och var flexibel när det gäller säkerhet och funktion.
- Tillämpa en säkerhetspolicy i tid och se till att den är relevant.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Tjänster och begrepp för identitets- och enhetsåtkomstskydd

Microsoft 365 för företag har utformats för stora organisationer för att alla ska kunna vara kreativa och arbeta tillsammans på ett säkert sätt.

Det här avsnittet innehåller en översikt över de Microsoft 365-tjänster och funktioner som är viktiga för identiteter och enhetsåtkomst.

### <a name="azure-ad"></a>Azure AD

Azure AD innehåller en komplett uppsättning identitetshanteringsfunktioner. Vi rekommenderar att du använder de här funktionerna för att skydda åtkomsten.

|Resurs eller funktion|Beskrivning|Licensiering|
|---|---|---|
|[Multifaktorautentisering (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA kräver att användarna anger två typer av verifiering, till exempel ett användarlösenord plus en avisering från Microsoft Authenticator-appen eller ett telefonsamtal. MFA minskar kraftigt risken för att stulna autentiseringsuppgifter kan användas för att komma åt din miljö. Microsoft 365 använder Azure AD Multi-Factor Authentication-tjänsten för MFA-baserade inloggningar.|Microsoft 365 E3 eller E5|
|[Villkorsstyrd åtkomst](/azure/active-directory/conditional-access/overview)|Azure AD utvärderar villkoren för användarens inloggning och använder villkorsstyrda åtkomstprinciper för att fastställa tillåten åtkomst. I den här vägledningen visar vi till exempel hur du skapar en princip för villkorsstyrd åtkomst för att kräva enhetsefterlevnad för åtkomst till känsliga data. Det här minskar kraftigt risken att en hackare med sin egen enhet och stulna autentiseringsuppgifter kan komma åt känsliga data. Den skyddar även känsliga data på enheterna, eftersom enheterna måste uppfylla särskilda hälso- och säkerhetskrav.|Microsoft 365 E3 eller E5|
|[Azure AD-grupper](/azure/active-directory/fundamentals/active-directory-manage-groups)|Villkorsstyrda åtkomstprinciper, enhetshantering med Intune och även behörigheter till filer och webbplatser i organisationen förlitar sig på tilldelning till användarkonton eller Azure AD-grupper. Vi rekommenderar att du skapar Azure AD-grupper som motsvarar de skyddsnivåer som du implementerar. Din chef kan exempelvis få högre värdemål för hackare. Därför är det vettigt att lägga till användarkonton för dessa anställda i en Azure AD-grupp och tilldela gruppen villkorsstyrda åtkomstprinciper och andra principer som upprätthåller en högre skyddsnivå för åtkomst.|Microsoft 365 E3 eller E5|
|[Enhetsregistrering](/azure/active-directory/devices/overview)|Du registrerar en enhet i Azure AD för att skapa en identitet för enheten. Den här identiteten används för att autentisera enheten när en användare loggar in och för att använda villkorsstyrda åtkomstprinciper som kräver domän- eller kompatibla datorer. För den här vägledningen använder vi enhetsregistrering för att automatiskt registrera domän sammanskrivna Windows-datorer. Enhetsregistrering krävs för att hantera enheter med Intune.|Microsoft 365 E3 eller E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|Gör att du kan upptäcka potentiella säkerhetsproblem som påverkar organisationens identiteter och konfigurera en automatiserad åtgärdsprincip på låg, medium och hög inloggningsrisk och användarrisk. Den här vägledningen förlitar sig på den här riskutvärderingen för att tillämpa villkorsstyrda åtkomstprinciper för multifaktorautentisering. Den här vägledningen innehåller även en princip för villkorsstyrd åtkomst som kräver att användarna ändrar sitt lösenord om högriskaktivitet identifieras för kontot.|Microsoft 365 E5, Microsoft 365 E3 med licenserna Identity & Threat Protection, EMS E5 eller Azure Premium P2|
|[Självbetjäning för återställning av lösenord (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|Låt användarna återställa sina lösenord på ett säkert sätt och utan åtgärder från supportavdelningen genom att tillhandahålla verifiering av flera autentiseringsmetoder som administratören kan kontrollera.|Microsoft 365 E3 eller E5|
|[Lösenordsskydd i Azure AD](/azure/active-directory/authentication/concept-password-ban-bad)|Identifiera och blockera kända svaga lösenord och deras varianter och ytterligare svaga termer som är specifika för din organisation. Standard globala förbjudna lösenordslistor tillämpas automatiskt på alla användare i en Azure AD-klient. Du kan definiera ytterligare poster i en anpassad förbjuden lösenordslista. När användare ändrar eller återställer sina lösenord kontrolleras dessa förbjudna lösenordslistor för att använda starka lösenord.|Microsoft 365 E3 eller E5|
|

Här är komponenterna för identitets- och enhetsåtkomst, inklusive Intune- och Azure AD-objekt, inställningar och undertjänster.

![Komponenter för identitet och enhetsåtkomst](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](/intune/introduction-intune) är Microsofts molnbaserade tjänst för hantering av mobila enheter. Den här vägledningen rekommenderar enhetshantering av Windows-datorer med Intune och rekommenderar konfigurationer av policyer för enhetsefterlevnad. Intune avgör om enheterna är kompatibla och skickar dessa data till Azure AD för användning när villkorsstyrd åtkomstprincip används.

#### <a name="intune-app-protection"></a>Intune-appskydd

[Appskyddsprinciperna för Intune](/intune/app-protection-policy) kan användas för att skydda organisationens data i mobilappar, med eller utan att registrera enheter i hantering. Intune hjälper till att skydda information, se till att dina anställda fortfarande är produktiva och förhindrar dataförlust. Genom att implementera principer på programnivå kan du begränsa åtkomsten till företagets resurser och hålla data inom it-avdelningens kontroll.

Den här vägledningen visar hur du skapar rekommenderade principer för att tillämpa användningen av godkända appar och för att avgöra hur apparna kan användas med dina affärsdata.

### <a name="microsoft-365"></a>Microsoft 365

I den här vägledningen visas hur du implementerar en uppsättning principer för att skydda åtkomsten till Microsoft 365-molntjänster, inklusive Microsoft Teams, Exchange Online, SharePoint Online och OneDrive för företag. Förutom att implementera dessa principer rekommenderar vi att du även höjer skyddsnivån för din klientorganisation med hjälp av följande resurser:

- [Konfigurera din klientorganisationen för bättre säkerhet](tenant-wide-setup-for-increased-security.md)

  Rekommendationer som gäller för baslinjesäkerhet för din klientorganisation.

- [Säkerhetsöversikt: Högsta prioritet för de första 30 dagarna, 90 dagarna och därefter](security-roadmap.md)

  Rekommendationer som omfattar loggning, datastyrning, administratörsåtkomst och skydd mot hot.

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 och  Microsoft 365-appar för företag

Windows 10 med Microsoft 365-appar för företag är den rekommenderade klientmiljön för PC-datorer. Vi rekommenderar Windows 10 eftersom Azure är utformat för att tillhandahålla så smidig upplevelse som möjligt för både lokal och Azure AD. Windows 10 innehåller även avancerade säkerhetsfunktioner som kan hanteras via Intune. Microsoft 365-appar för företag innehåller de senaste versionerna av Office-program. Dessa använder modern autentisering, som är säkrare och ett krav för villkorsstyrd åtkomst. De här apparna innehåller även förbättrade säkerhets- och efterlevnadsverktyg.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Tillämpa dessa funktioner på de tre skyddsnivåerna

I följande tabell sammanfattas våra rekommendationer för att använda dessa funktioner över de tre skyddsnivåerna.

|Skyddmekanism|Grundläggande|Känslig|Strikt reglerad|
|---|---|---|---|
|**Framtvinga MFA**|På medelhög eller över inloggningsrisk|Vid låg eller över inloggningsrisk|I alla nya sessioner|
|**Framtvinga lösenordsändring**|För högriskanvändare|För högriskanvändare|För högriskanvändare|
|**Tillämpa Intune-programskydd**|Ja|Ja|Ja|
|**Framtvinga Intune-registrering för en organisationsägd enhet**|Kräv en kompatibel eller domän ansluten dator, men tillåt att du tar med egna enheter (BYOD) telefoner och surfplattor|Kräv en kompatibel eller domän ansluten enhet|Kräv en kompatibel eller domän ansluten enhet|
|

## <a name="device-ownership"></a>Enhetsägarskap

Tabellen ovan återspeglar trenden för många organisationer att stödja en blandning av organisationer ägda enheter, samt personliga enheter eller BYOD för att möjliggöra mobil produktivitet för hela arbetsstyrkan. Appskyddsprinciperna för Intune säkerställer att e-post skyddas från att föra ut Outlook-mobilappen och andra Office-mobilappar, på både organisationsägda enheter och BYODs.

Vi rekommenderar att enheter som ägs av organisationen hanteras av Intune eller domän-ansluten för att tillämpa ytterligare skydd och kontroll. Beroende på datakänslighet kan organisationen välja att inte tillåta BYODs för specifika användargrupper eller specifika appar.

## <a name="deployment-and-your-apps"></a>Distribution och dina program

Innan du konfigurerar och distribuerar identitets- och enhetsåtkomstkonfiguration för Azure AD-integrerade appar måste du:

- Bestäm vilka appar som ska användas i din organisation.
- Analysera den här listan med appar för att fastställa vilka principer som ger tillräcklig skyddsnivå.

  Du bör inte skapa separata uppsättningar av principer för varje program eftersom det kan bli krångligt att hantera dem. Microsoft rekommenderar att du grupperar appar som har samma skyddskrav för samma användare.

  Du kan till exempel ha en uppsättning principer som innehåller alla Microsoft 365-program för alla dina användare för baslinjeskydd och en andra uppsättning principer för alla känsliga program, till exempel de som används av personal- eller ekonomiavdelningar, och tillämpa dem på dessa grupper.

När du har fastställt uppsättningen principer för de appar som du vill skydda distribuerar du principerna till användarna stegvis och tar itu med problem på vägen.

Konfigurera till exempel principerna som ska användas för alla Microsoft 365-appar för bara Exchange Online med de ytterligare ändringarna för Exchange. Distribuera de här principerna till användarna och gå igenom eventuella problem. Lägg sedan till Teams med de ytterligare ändringarna och distribuera det till dina användare. Lägg sedan till SharePoint med dess ytterligare ändringar. Fortsätt att lägga till resten av dina appar tills du kan tryggt konfigurera baslinjeprinciperna så att de omfattar alla Microsoft 365-appar.

På samma sätt kan du för känsliga appar skapa en uppsättning principer och lägga till en app i taget och gå igenom eventuella problem tills de alla har inkluderats i den känsliga programprincipuppsättningen.

Microsoft rekommenderar att du inte skapar principuppsättningar som gäller för alla appar eftersom det kan resultera i oavsiktliga konfigurationer. Principer som blockerar alla appar kan till exempel låsa administratörerna från Azure-portalen och undantag kan inte konfigureras för viktiga slutpunkter som Microsoft Graph.

## <a name="steps-in-the-process-of-configuring-identity-and-device-access"></a>Steg i processen med att konfigurera identitet och enhetsåtkomst

![Anvisningar för att konfigurera identitet och enhetsåtkomst.](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. Konfigurera nödvändiga identitetsfunktioner och deras inställningar.
2. Konfigurera principer för villkorsstyrd åtkomst och identitet.
3. Konfigurera villkorsstyrda åtkomstprinciper för gästanvändare och externa användare.
4. Konfigurera villkorsstyrda åtkomstprinciper för Microsoft 365-molnappar som Microsoft Teams, Exchange Online och SharePoint.

När du har konfigurerat identitets- och enhetsåtkomst kan du gå till distributionsguiden för [Azure AD-funktioner](/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2) för en fasad checklista med ytterligare funktioner att överväga och Azure AD-identitetsstyrning för att skydda, övervaka och granska åtkomst. [](/azure/active-directory/governance/)

## <a name="next-step"></a>Nästa steg

[Nödvändiga åtgärder för att implementera principer för identitets- och enhetsåtkomst](identity-access-prerequisites.md)