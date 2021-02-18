---
title: Konfigurationer för identitets- och enhetsåtkomst – Microsoft 365 för företag
description: Här beskrivs Microsofts rekommendationer och kärnkoncept för distribution av säkra principer och konfigurationer för e-post, dokument och appar.
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
ms.openlocfilehash: e4b85091366927596a2c8f52c579c369fc9697c3
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290723"
---
# <a name="identity-and-device-access-configurations"></a>Konfigurationer av identiteter och enhetsåtkomst

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)

Organisationens moderna säkerhetsområde omfattar nu mer än nätverket och inkluderar användare som använder molnbaserade appar från valfri plats med olika enheter. Din säkerhetsinfrastruktur måste fastställa om en viss åtkomstbegäran ska beviljas och under vilka villkor.

Det här avgörandet bör baseras på inloggningens användarkonto, vilken enhet som används, vilken app som användaren använder för åtkomst, platsen som åtkomstbegäran görs från och en bedömning av risken för begäran. Denna funktion hjälper till att säkerställa att endast godkända användare och enheter kan komma åt dina kritiska resurser.

Den här serien med artiklar beskriver en uppsättning konfigurationer med identiteter och enhetsåtkomst, samt villkorsstyrd åtkomst i Azure Active Directory (Azure AD), Microsoft Intune och andra principer för säker åtkomst till Microsoft 365 för företagsmolnappar och -tjänster, andra SaaS-tjänster och lokala program som publiceras med Azure AD Application Proxy.

Inställningar och principer för åtkomst till identiteter och enheter rekommenderas på tre nivåer: baslinjeskydd, känsligt skydd och skydd för miljöer med mycket reglerade eller klassificerade data. Dessa nivåer och deras motsvarande konfigurationer ger konsekventa skyddsnivåer för dina data, identiteter och enheter.

Dessa funktioner och deras rekommendationer:

- Stöds i Microsoft 365 E3 och Microsoft 365 E5.
- Är i linje med [Microsoft Secure Score](../mtp/microsoft-secure-score.md) samt [identitetspoäng i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)och ökar dessa resultat för organisationen.
- Hjälper dig att implementera de här [fem stegen för att skydda din identitetsinfrastruktur.](https://docs.microsoft.com/azure/security/azure-ad-secure-steps)

Om organisationen har unika miljökrav eller komplexitet kan du använda de här rekommendationerna som utgångspunkt. Men de flesta organisationer kan implementera dessa rekommendationer som bestämts.

Titta på den här videon för en snabb överblick över identitets- och enhetsåtkomstkonfigurationer för Microsoft 365 för företag.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxEDQ]

> [!NOTE]
> Microsoft säljer även Enterprise Mobility + Security -licenser (EMS) för Office 365-abonnemang. EMS E3- och EMS E5-funktionerna motsvarar funktionerna i Microsoft 365 E3 och Microsoft 365 E5. Mer [information finns i EMS-abonnemang.](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing)

## <a name="intended-audience"></a>Avsedd målgrupp

De här rekommendationerna är avsedda för företagsarkitekter och IT-personal som känner till Produktivitets- och säkerhetstjänster i Microsoft 365 i molnet, som omfattar Azure AD (identitet), Microsoft Intune (enhetshantering) och Azure Information Protection (dataskydd).

### <a name="customer-environment"></a>Kundmiljö

De rekommenderade principerna gäller för företagsorganisationer som arbetar helt i Microsoft-molnet och för kunder med hybrididentitetsinfrastruktur, som är en skog för lokal Active Directory DS (AD DS) som synkroniseras med en Azure AD-klientorganisation.

Många av de rekommendationer som tillhandahålls förlitar sig på tjänster som endast är tillgängliga med Microsoft 365 E5, Microsoft 365 E3 med tillägget Identity & Threat Protection, EMS E5 eller Azure Premium P2.

För de organisationer som inte har dessa licenser rekommenderar [](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)Microsoft att du åtminstone implementerar säkerhetsstandarder, som ingår i alla Microsoft 365-abonnemang.

### <a name="caveats"></a>Varningar

Din organisation kan omfattas av föreskrifter eller andra efterlevnadskrav, inklusive specifika rekommendationer som kan innebära att du måste tillämpa principer som skiljer sig från dessa rekommenderade konfigurationer. De här konfigurationerna rekommenderar användningskontroller som inte har varit tillgängliga under en längre tid. Vi rekommenderar dessa kontroller eftersom vi tror att de representerar en balans mellan säkerhet och produktivitet.

Vi har gjort vårt bästa för att ta hänsyn till en mängd olika krav på organisationsskydd, men vi kan inte ta med alla möjliga krav eller för alla unika aspekter av din organisation.

## <a name="three-tiers-of-protection"></a>Tre skyddsnivåer

De flesta organisationer har särskilda krav gällande säkerhet och dataskydd. De här kraven varierar efter branschsegment och efter jobbfunktioner inom organisationer. Din juridiska avdelning och administratörer kan till exempel kräva ytterligare säkerhets- och informationsskyddskontroller kring sin e-postkorrespondens som inte krävs för andra affärsenheter.

Varje bransch har också en egen uppsättning särskilda bestämmelser. I stället för att ange en lista över alla möjliga säkerhetsalternativ eller en rekommendation per branschsegment eller jobbfunktion har rekommendationer lagts till för tre olika nivåer av säkerhet och skydd som kan tillämpas utifrån dina behovs granularitet.

- **Baslinjeskydd:** Vi rekommenderar att du upprättar en lägsta standard för att skydda data samt identiteter och enheter som har åtkomst till dina data. Du kan följa de här baslinjerekommendationerna för att få ett starkt standardskydd som uppfyller många organisationers behov.
- **Känsligt** skydd : Vissa kunder har en delmängd data som måste skyddas på högre nivåer, eller så kan de kräva att alla data skyddas på en högre nivå. Du kan tillämpa ett bättre skydd på alla eller vissa datauppsättningar i Din Microsoft 365-miljö. Vi rekommenderar att du skyddar identiteter och enheter som använder känsliga data med liknande säkerhetsnivåer.
- **Mycket reglerad**: Vissa organisationer kan ha en liten mängd data som klassificeras i hög grad, utgör affärshemligheter eller är reglerade data. Microsoft tillhandahåller funktioner som hjälper organisationer att uppfylla dessa krav, inklusive ytterligare skydd för identiteter och enheter.

![Säkerhetskoner – alla kunder > vissa > specifika kunder. Bred tillämpning på ett visst program](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

Den här vägledningen visar hur du implementerar skydd för identiteter och enheter för var och en av dessa nivåer av skydd. Använd den här vägledningen som utgångspunkt för din organisation och justera principerna så att de uppfyller organisationens specifika krav.

Det är viktigt att använda konsekventa skyddsnivåer för dina data, identiteter och enheter. Om du till exempel implementerar den här vägledningen ska du se till att skydda dina data på liknande nivåer.

**Identitets- och enhetsskyddet för Microsoft 365-arkitekturmodellen** visar vilka funktioner som kan jämföras.

[![Thumb-bild för Identitet och enhetsskydd för Microsoft 365-affisch](../../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [Visa som PDF](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Ladda ned som PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Ladda ned som Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

Läs även artikeln Distribuera [informationsskydd för lösningen för datasekretessföreskrifter](../../solutions/information-protection-deploy.md) för att skydda information som lagras i Microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Avslut av säkerhet och produktivitet

För att implementera en säkerhetsstrategi krävs förseningar mellan säkerhet och produktivitet. Det är bra att utvärdera hur varje beslut påverkar balans i säkerhet, funktion och enkelhet.

![Säkerhetstriadsutjämning av säkerhet, funktionalitet och användarvänlighet.](../../media/microsoft-365-policies-configurations/security-triad.png)

Rekommendationerna baseras på följande principer:

- Känna till användarna och var flexibel när det gäller säkerhet och funktion.
- Tillämpa en säkerhetspolicy i tid och se till att den är relevant.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Tjänster och koncept för identitets- och enhetsåtkomstskydd

Microsoft 365 för företag har utformats för stora organisationer för att alla ska kunna vara kreativa och arbeta säkert tillsammans.

Det här avsnittet innehåller en översikt över De Microsoft 365-tjänster och -funktioner som är viktiga för identiteter och enhetsåtkomst.

### <a name="azure-ad"></a>Azure AD

Azure AD ger en komplett uppsättning identitetshanteringsfunktioner. Vi rekommenderar att du använder de här funktionerna för säker åtkomst.

|Resurs eller funktion|Beskrivning|Licensiering|
|---|---|---|
|[Multifaktorautentisering (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA kräver att användare anger två typer av verifiering, till exempel ett användarlösenord plus en avisering från Microsoft Authenticator-appen eller ett telefonsamtal. MFA minskar kraftigt risken för att stulna autentiseringsuppgifter kan användas för att komma åt din miljö. Microsoft 365 använder Tjänsten Azure AD Multi-Factor Authentication för MFA-baserade inloggningar.|Microsoft 365 E3 eller E5|
|[Villkorsstyrd åtkomst](/azure/active-directory/conditional-access/overview)|Azure AD utvärderar villkoren för användarens inloggning och använder villkorsstyrda åtkomstprinciper för att fastställa tillåten åtkomst. I den här vägledningen visar vi till exempel hur du skapar en princip för villkorsstyrd åtkomst för att kräva enhetsefterlevnad för åtkomst till känsliga data. Det här minskar kraftigt risken att en hackare med sin egen enhet och stulna autentiseringsuppgifter kan komma åt känsliga data. Den skyddar även känslig information på enheterna, eftersom enheterna måste uppfylla särskilda hälso- och säkerhetskrav.|Microsoft 365 E3 eller E5|
|[Azure AD-grupper](/azure/active-directory/fundamentals/active-directory-manage-groups)|Villkorsstyrda åtkomstprinciper, enhetshantering med Intune och till och med behörigheter till filer och webbplatser i organisationen är beroende av tilldelning till användarkonton eller Azure AD-grupper. Vi rekommenderar att du skapar Azure AD-grupper som motsvarar de skyddsnivåer som du implementerar. Din personal har till exempel sannolikt högre värdemål för hackare. Därför är det vettigt att lägga till användarkonton för dessa anställda i en Azure AD-grupp och tilldela den här gruppen till villkorsstyrda åtkomstprinciper och andra principer som upprätthåller en högre skyddsnivå för åtkomst.|Microsoft 365 E3 eller E5|
|[Enhetsregistrering](/azure/active-directory/devices/overview)|Du registrerar en enhet i Azure AD för att skapa en identitet för enheten. Den här identiteten används för att autentisera enheten när en användare loggar in och för att använda villkorsstyrda åtkomstprinciper som kräver en domän ansluten eller kompatibel dator. För den här vägledningen använder vi enhetsregistrering för att automatiskt registrera domän sammanskrivna Windows-datorer. Enhetsregistrering krävs för att hantera enheter med Intune.|Microsoft 365 E3 eller E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|Gör att du kan upptäcka potentiella svagheter som påverkar organisationens identiteter och konfigurera en automatiserad åtgärdspolicy till låg, medelstor och hög inloggningsrisk och användarrisk. Det här vägledningen bygger på den här riskutvärderingen för att tillämpa villkorsstyrda åtkomstprinciper för multifaktorautentisering. Den här vägledningen innehåller också en princip för villkorsstyrd åtkomst som kräver att användarna ändrar sitt lösenord om högriskaktivitet identifieras för deras konto.|Microsoft 365 E5, Microsoft 365 E3 med licenserna Identity & Threat Protection, EMS E5 eller Azure Premium P2|
|[Självbetjäning för återställning av lösenord (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|Låt användarna återställa sina lösenord på ett säkert sätt och utan hjälpåtgärd genom att tillhandahålla verifiering av flera autentiseringsmetoder som administratören kan kontrollera.|Microsoft 365 E3 eller E5|
|[Lösenordsskydd i Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)|Identifiera och blockera kända svaga lösenord och deras varianter och ytterligare svaga termer som är specifika för din organisation. Standard globala förbjudna lösenordslistor tillämpas automatiskt på alla användare i en Azure AD-klient. Du kan definiera ytterligare poster i en anpassad förbjuden lösenordslista. När användare ändrar eller återställer sina lösenord kontrolleras dessa förbjudna lösenordslistor för att använda starka lösenord.|Microsoft 365 E3 eller E5|
|

Här är komponenterna för identitets- och enhetsåtkomst, inklusive Intune- och Azure AD-objekt, inställningar och undertjänster.

![Komponenter för identitets- och enhetsåtkomst](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) är Microsofts molnbaserade tjänst för hantering av mobila enheter. Den här vägledningen rekommenderar enhetshantering av Windows-datorer med Intune och rekommenderar konfigurationer av efterlevnadsprinciper för enheter. Intune avgör om enheterna är kompatibla och skickar dessa data till Azure AD för användning av villkorsstyrda åtkomstprinciper.

#### <a name="intune-app-protection"></a>Intune-appskydd

[Appskyddsprinciperna för Intune](https://docs.microsoft.com/intune/app-protection-policy) kan användas för att skydda organisationens data i mobilappar, med eller utan att registrera enheter i hantering. Intune skyddar informationen och ser till att dina anställda fortfarande kan vara produktiva och förhindrar dataförlust. Genom att implementera principer på programnivå kan du begränsa åtkomsten till företagets resurser och hålla data inom IT-avdelningens kontroll.

I den här vägledningen visas hur du skapar rekommenderade principer för att framtvinga användningen av godkända appar och för att avgöra hur apparna kan användas med affärsdata.

### <a name="microsoft-365"></a>Microsoft 365

I den här vägledningen visas hur du implementerar en uppsättning principer för att skydda åtkomsten till Microsoft 365-molntjänster, inklusive Microsoft Teams, Exchange Online, SharePoint Online och OneDrive för företag. Förutom att implementera de här principerna rekommenderar vi att du även höjer skyddsnivån för klientorganisationen med hjälp av dessa resurser:

- [Konfigurera din klientorganisationen för bättre säkerhet](tenant-wide-setup-for-increased-security.md)

  Rekommendationer som gäller för baslinjesäkerhet för klientorganisationen.

- [Säkerhetsöversikt: Främsta prioriteringar för de första 30 dagarna, 90 dagarna och därefter](security-roadmap.md)

  Rekommendationer som omfattar loggning, datastyrning, administratörsåtkomst och skydd mot hot.

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 och  Microsoft 365-appar för företag

Windows 10 med Microsoft 365-appar för företag är den rekommenderade klientmiljön för DATORER. Vi rekommenderar Windows 10 eftersom Azure har utformats för att ge bästa möjliga upplevelse för både lokal och Azure AD. Windows 10 innehåller också avancerade säkerhetsfunktioner som kan hanteras via Intune. Microsoft 365-appar för företag innehåller de senaste versionerna av Office-programmen. De använder modern autentisering, som är säkrare och ett krav för villkorsstyrd åtkomst. De här apparna innehåller även förbättrade säkerhets- och efterlevnadsverktyg.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Tillämpa de här funktionerna på de tre skyddsnivåerna

I följande tabell sammanfattas våra rekommendationer om hur du använder de här funktionerna över de tre skyddsnivåerna.

|Skyddmekanism|Grundläggande|Känslig|Strikt reglerad|
|---|---|---|---|
|**Framtvinga MFA**|På medelhög eller över inloggningsrisk|Vid låg eller över inloggningsrisk|På alla nya sessioner|
|**Tillämpa lösenordsändring**|För högriskanvändare|För högriskanvändare|För högriskanvändare|
|**Tillämpa Intune-programskydd**|Ja|Ja|Ja|
|**Framtvinga Intune-registrering för organisationsägda enheter**|Kräv en kompatibel eller domän ansluten dator, men tillåt ta med egna enheter (BYOD) telefoner och surfplattor|Kräv en kompatibel eller domän ansluten enhet|Kräv en kompatibel eller domän ansluten enhet|
|

## <a name="device-ownership"></a>Enhetsägarskap

Tabellen ovan återspeglar trenden för många organisationer att stödja en blandning av enheter som ägs av organisationen samt personliga enheter eller BYOD för att möjliggöra mobil produktivitet i hela arbetsstyrkan. Appskyddsprinciperna för Intune säkerställer att e-post skyddas från att föra ut från Outlook-mobilappen och andra Office-mobilappar, på både organisationsägda enheter och BYOD.

Vi rekommenderar att enheter som ägs av organisationen hanteras av Intune eller domän ansluten för att tillämpa ytterligare skydd och kontroll. Beroende på datakänslighet kan organisationen välja att inte tillåta BYOD för specifika användargrupper eller specifika appar.

## <a name="deployment-and-your-apps"></a>Distribution och dina appar

Innan du konfigurerar och distribuerar identitets- och enhetsåtkomstkonfiguration för Azure AD-integrerade appar måste du:

- Bestäm vilka appar som ska användas i din organisation.
- Analysera den här listan med appar för att fastställa vilka uppsättningar principer som ger tillräcklig skyddsnivå.

  Du bör inte skapa separata uppsättningar med principer för varje program eftersom det kan bli krångligt att hantera dem. Microsoft rekommenderar att du grupperar appar som har samma säkerhetskrav för samma användare.

  Du kan till exempel ha en uppsättning principer som innehåller alla Microsoft 365-program för alla dina användare för grundläggande skydd och en andra uppsättning principer för alla känsliga program, till exempel de som används av personalavdelningen eller ekonomiavdelningen, och tillämpa dem på de grupperna.

När du har fastställt uppsättningen principer för de appar du vill skydda distribuerar du principerna stegvis till användarna och tar itu med problem på vägen.

Konfigurera till exempel principerna som ska användas för alla Microsoft 365-appar för just Exchange Online med de ytterligare ändringarna för Exchange. Distribuera de här principerna till användarna och gå igenom eventuella problem. Lägg sedan till Teams med dess ytterligare ändringar och distribuera det till dina användare. Lägg sedan till SharePoint med dess ytterligare ändringar. Fortsätt att lägga till resten av apparna tills du kan konfigurera baslinjeprinciperna så att de inkluderar alla Microsoft 365-appar.

På samma sätt skapar du för känsliga appar en uppsättning principer och lägger till en app i taget och går igenom eventuella problem tills de alla tas med i den känsliga appprincipuppsättningen.

Microsoft rekommenderar att du inte skapar principuppsättningar som gäller för alla appar eftersom det kan leda till vissa oavsiktliga konfigurationer. Principer som blockerar alla appar kan till exempel låsa administratörerna från Azure-portalen och undantag kan inte konfigureras för viktiga slutpunkter som Microsoft Graph.

## <a name="steps-in-the-process-of-configuring-identity-and-device-access"></a>Steg i processen med att konfigurera identitet och enhetsåtkomst

![Steg för att konfigurera identitet och enhetsåtkomst.](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. Konfigurera nödvändiga identitetsfunktioner och deras inställningar.
2. Konfigurera principer för villkorsstyrd åtkomst och identitet.
3. Konfigurera villkorsstyrda åtkomstprinciper för gästanvändare och externa användare.
4. Konfigurera villkorsstyrda åtkomstprinciper för Microsoft 365-molnappar som Microsoft Teams, Exchange Online och SharePoint.

När du har konfigurerat identitets- och enhetsåtkomst kan du gå till distributionsguiden för [Azure AD-funktioner](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2) för en fasad checklista med ytterligare funktioner att överväga och Azure AD-identitetsstyrning för att skydda, övervaka och granska åtkomst. [](https://docs.microsoft.com/azure/active-directory/governance/)

## <a name="next-step"></a>Nästa steg

[Krav på att implementera principer för identitets- och enhetsåtkomst](identity-access-prerequisites.md)
