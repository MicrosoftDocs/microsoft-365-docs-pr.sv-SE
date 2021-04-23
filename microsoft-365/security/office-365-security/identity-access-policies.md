---
title: Vanliga principer för identitet och enhetsåtkomst – Microsoft 365 för företag | Microsoft Docs
description: Här beskrivs de rekommenderade gemensamma principerna och konfigurationerna för identitet och enhetsåtkomst.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
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
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 4b7315cbb8704b691ce4f3d6b96958f18248b478
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952638"
---
# <a name="common-identity-and-device-access-policies"></a>Vanliga principer för identitets- och enhetsåtkomst

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- Azure

I den här artikeln beskrivs de vanligaste rekommenderade principerna för att skydda åtkomsten till Microsoft 365-molntjänster, inklusive lokala program som publiceras med Azure Active Directory-programproxy (Azure Active Directory).

I den här vägledningen beskrivs hur du distribuerar de rekommenderade principerna i en nyetablerade miljö. Genom att konfigurera de här principerna i en separat labbmiljö kan du förstå och utvärdera de rekommenderade principerna innan du förinstallerar utrullningen till dina preproduktions- och produktionsmiljöer. Din nyligen etablerade miljö kan vara molnbaserad eller hybrid för att återspegla dina utvärderingsbehov.

## <a name="policy-set"></a>Principuppsättning

I följande diagram visas den rekommenderade uppsättningen principer. Den visar vilken nivå av skydd som varje princip gäller för och om principerna gäller för datorer eller telefoner och surfplattor, eller båda kategorierna av enheter. Den anger också var du konfigurerar de här principerna.

[![Vanliga principer för konfiguration av identitet och enhetsåtkomst](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

Här är en PDF-sammanfattning på en sida med länkar till de enskilda principerna:

[![Thumb-bild för identitets- och enhetsskydd för Microsoft 365-handout](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [Visa som PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Ladda ned som PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

I resten av den här artikeln beskrivs hur du konfigurerar de här principerna.

> [!NOTE]
> Du bör kräva multifaktorautentisering (MFA) innan du registrerar enheter i Intune för att försäkra dig om att enheten ligger hos den avsedda användaren. Du måste registrera enheter i Intune innan du kan tillämpa principer för enhetsefterlevnad.

För att ge dig tid att utföra dessa uppgifter rekommenderar vi att du implementerar baslinjeprinciperna i den ordning som anges i den här tabellen. Men MFA-principerna för känsliga och starkt reglerade skyddsnivåer kan implementeras när som helst.

|Skyddsnivå|Principer|Mer information|Licensiering|
|---|---|---|---|
|**Grundläggande**|[Kräv MFA när inloggningsrisken är *medium* eller *hög*](#require-mfa-based-on-sign-in-risk)||Microsoft 365 E5 eller Microsoft 365 E3 med E5-säkerhets tillägg|
||[Blockera klienter som inte har stöd för modern autentisering](#block-clients-that-dont-support-multi-factor)|Klienter som inte använder modern autentisering kan åsidosätta villkorsstyrda åtkomstprinciper, så det är viktigt att blockera dessa.|Microsoft 365 E3 eller E5|
||[Användare med hög risk måste byta lösenord](#high-risk-users-must-change-password)|Tvingar användarna att ändra sitt lösenord vid inloggning om högriskaktivitet identifieras för deras konto.|Microsoft 365 E5 eller Microsoft 365 E3 med E5-säkerhets tillägg|
||[Tillämpa programskyddsprinciper (APP)-dataskydd](#apply-app-data-protection-policies)|Appskyddsprincipen för One Intune per plattform (Windows, iOS/iPadOS, Android).|Microsoft 365 E3 eller E5|
||[Kräv godkända appar och programskydd](#require-approved-apps-and-app-protection)|Tillämpar mobil appskydd för telefoner och surfplattor med iOS, iPadOS eller Android.|Microsoft 365 E3 eller E5|
||[Definiera principer för enhetsefterlevnad](#define-device-compliance-policies)|En princip för varje plattform.|Microsoft 365 E3 eller E5|
||[Kräv kompatibla PC-datorer](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Framtvingar Intune-hantering av PC-datorer med Windows eller MacOS.|Microsoft 365 E3 eller E5|
|**Känslig**|[Kräv MFA när inloggningsrisken *är låg,* *medel* eller *hög*](#require-mfa-based-on-sign-in-risk)||Microsoft 365 E5 eller Microsoft 365 E3 med E5-säkerhets tillägg|
||[Kräv kompatibla datorer *och* mobila enheter](#require-compliant-pcs-and-mobile-devices)|Framtvingar Intune-hantering för både PC-datorer (Windows eller MacOS) och telefoner och surfplattor (iOS, iPadOS eller Android).|Microsoft 365 E3 eller E5|
|**Strikt reglerad**|[*Kräv* alltid MFA](#assigning-policies-to-groups-and-users)||Microsoft 365 E3 eller E5|
|

## <a name="assigning-policies-to-groups-and-users"></a>Tilldela principer till grupper och användare

Innan du konfigurerar principer identifierar du de Azure AD-grupper du använder för varje skyddsnivå. Normalt gäller baslinjeskydd för alla i organisationen. En användare som ingår för både baslinje- och känsligt skydd kommer att tillämpa alla baslinjeprinciper plus känsliga principer. Skyddet ackumuleras och den mest restriktiva principen tillämpas.

En rekommenderad metod är att skapa en Azure AD-grupp för undantag för villkorsstyrd åtkomst. Lägg till den här gruppen i  alla **villkorsstyrda** åtkomstprinciper i inställningen Exkludera värdet **för** inställningen Användare och grupper i avsnittet Tilldelningar. Det ger dig en metod för att ge åtkomst till en användare medan du felsöker åtkomstproblem. Det här rekommenderas endast som en tillfällig lösning. Övervaka den här gruppen efter ändringar och se till att undantagsgruppen endast används som avsett.

Här är ett exempel på grupptilldelning och undantag som kräver MFA.

![Exempel på grupptilldelning och undantag för MFA-principer](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Här är resultaten:

- Alla användare måste använda MFA när inloggningsrisken är medium eller hög.

- Medlemmar i ledningsgruppen måste använda MFA när inloggningsrisken är låg, medium eller hög.

  I det här fallet matchar medlemmarna i gruppen Ledningspersonal både baslinjeprincipen och känsliga villkorsstyrda åtkomstprinciper. Åtkomstkontrollerna för båda principerna kombineras, vilket i det här fallet motsvarar den känsliga villkorsstyrda åtkomstprincipen.

- Medlemmar i gruppen Top Secret Project X måste alltid använda MFA

  I det här fallet matchar medlemmarna i gruppen Top Secret Project X både baslinjeprincipen och starkt reglerade villkorsstyrda villkorsstyrda åtkomstprinciper. Åtkomstkontrollerna för båda principerna kombineras. Eftersom åtkomstkontrollen för den högst reglerade villkorsstyrda principen är mer restriktiv används den.

Var försiktig när du använder högre skyddsnivåer för grupper och användare. Medlemmar i gruppen Top Secret Project X måste till exempel använda MFA varje gång de loggar in, även om de inte arbetar med det högreglerade innehållet för Project X.

Alla Azure AD-grupper som skapats som en del av dessa rekommendationer måste skapas som Microsoft 365-grupper. Detta är viktigt för distribution av känslighetsetiketter när du skyddar dokument i Microsoft Teams och SharePoint.

![Exempel på hur du skapar en Microsoft 365-grupp](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>Kräv MFA baserat på inloggningsrisk

Du bör be användarna registrera sig för MFA innan de behöver använda den. Om du har Microsoft 365 E5, Microsoft 365 E3 med tillägget E5-säkerhet, Office 365 med EMS E5 eller enskilda Azure AD Premium P2-licenser kan du använda MFA-registreringsprincipen med Azure AD Identity Protection för att kräva att användare registrerar sig för MFA. Det [nödvändiga arbetet omfattar](identity-access-prerequisites.md) registrering av alla användare med MFA.

När användarna har registrerats kan du kräva MFA för inloggning med en ny princip för villkorsstyrd åtkomst.

1. Gå till [Azure Portal och](https://portal.azure.com)logga in med dina autentiseringsuppgifter.
2. I listan över Azure-tjänster väljer du **Azure Active Directory.**
3. I listan **Hantera** väljer du **Säkerhet och** sedan **Villkorsstyrd åtkomst.**
4. Välj **Ny princip** och skriv namnet på den nya principen.

I följande tabeller beskrivs inställningarna för villkorsstyrd åtkomst-princip så att MFA krävs baserat på inloggningsrisker.

I **avsnittet** Uppgifter:

|Inställning|Egenskaper|Värden|Kommentarer|
|---|---|---|---|
|Användare och grupper|Inkludera|**Välj användare och grupper > användare och grupper**: Välj specifika grupper som innehåller riktade användarkonton.|Börja med den grupp som innehåller pilotanvändarkonton.|
||Undanta|**Användare och grupper:** Välj din undantagsgrupp för villkorsstyrd åtkomst; tjänstkonton (appidentiteter).|Medlemskapet bör ändras tillfälligt och efter behov.|
|Molnappar eller -åtgärder|**Molnappar > Inkludera**|**Välj appar:** Välj de appar som du vill att principen ska gälla för. Välj till exempel Exchange Online.||
|Villkor|||Konfigurera villkor som är specifika för din miljö och dina behov.|
||Inloggningsrisk||Se vägledning i följande tabell.|
|

### <a name="sign-in-risk-condition-settings"></a>Inställningar för inloggningsriskvillkor

Tillämpa inställningarna för risknivå baserat på vilken skyddsnivå du ska rikta.

|Skyddsnivå|Nödvändiga risknivåvärden|Åtgärd|
|---|---|---|
|Grundläggande|Hög, medium|Kontrollera båda.|
|Känslig|Hög, medel, låg|Markera alla tre.|
|Strikt reglerad||Låt alla alternativ vara avmarkerade om du alltid vill använda MFA.|
|

I avsnittet **Access-kontroller:**

|Inställning|Egenskaper|Värden|Åtgärd|
|---|---|---|---|
|Grant|**Grant access**||Välj|
|||**Kräv multifaktorautentisering**|Check|
||**Kräva alla markerade kontroller**||Välj|
|

Välj **Välj** för att spara **inställningarna för** Bevilja.

Välj slutligen **På för** Aktivera **princip** och välj sedan **Skapa**.

Överväg även att använda [verktyget Vad händer](/azure/active-directory/active-directory-conditional-access-whatif) om för att testa principen.

## <a name="block-clients-that-dont-support-multi-factor"></a>Blockera klienter som inte har stöd för flera faktorer

Använd inställningarna i de här tabellerna för en villkorsstyrd åtkomstprincip för att blockera klienter som inte har stöd för multifaktorautentisering.

I [den här artikeln](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md) finns en lista över klienter i Microsoft 365 som har stöd för multifaktorautentisering.

I **avsnittet** Uppgifter:

|Inställning|Egenskaper|Värden|Kommentarer|
|---|---|---|---|
|Användare och grupper|Inkludera|**Välj användare och grupper > användare och grupper**: Välj specifika grupper som innehåller riktade användarkonton.|Börja med den grupp som innehåller pilotanvändarkonton.|
||Undanta|**Användare och grupper:** Välj din undantagsgrupp för villkorsstyrd åtkomst; tjänstkonton (appidentiteter).|Medlemskapet bör ändras tillfälligt och efter behov.|
|Molnappar eller -åtgärder|**Molnappar > Inkludera**|**Välj appar:** Välj de program som motsvarar de klienter som inte stöder modern autentisering.||
|Villkor|**Klientappar**|Välj **Ja** för **Konfigurera** <p> Avmarkera bkryssmarkeringarna **för webbläsar-** och **mobilprogram och skrivbordsklienter**||
|

I avsnittet **Access-kontroller:**

|Inställning|Egenskaper|Värden|Åtgärd|
|---|---|---|---|
|Grant|**Blockera åtkomst**||Välj|
||**Kräva alla markerade kontroller**||Välj|
|

Välj **Välj** för att spara **inställningarna för** Bevilja.

Välj slutligen **På för** Aktivera **princip** och välj sedan **Skapa**.

Överväg att använda [verktyget Vad händer](/azure/active-directory/active-directory-conditional-access-whatif) om för att testa principen.

För Exchange Online kan du använda autentiseringsprinciper för att [inaktivera grundläggande](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)autentisering, som tvingar alla klientåtkomstförfrågningar att använda modern autentisering.

## <a name="high-risk-users-must-change-password"></a>Användare med hög risk måste byta lösenord

För att säkerställa att alla högriskanvändares komprometterade konton tvingas utföra en lösenordsändring vid inloggning måste du använda följande princip.

Logga in på [Microsoft https://portal.azure.com) Azure-portalen (](https://portal.azure.com/) med dina administratörsautentiseringsuppgifter och gå sedan till **Azure AD Identity Protection > Användarriskprincip.**

I **avsnittet** Uppgifter:

|Skriv|Egenskaper|Värden|Åtgärd|
|---|---|---|---|
|Användare|Inkludera|**Alla användare**|Välj|
|Användarrisk|**Hög**||Välj|
|

I det andra **avsnittet uppgifter:**

|Skriv|Egenskaper|Värden|Åtgärd|
|---|---|---|---|
|Åtkomst|**Tillåt åtkomst**||Välj|
|||**Kräv lösenordsändring**|Check|
|

Spara **Access-inställningarna** genom att **välja** Klar.

Välj slutligen **På för** **Framtvinga** princip och välj sedan **Spara**.

Överväg att använda [verktyget Vad händer](/azure/active-directory/active-directory-conditional-access-whatif) om för att testa principen.

Använd den här principen tillsammans med [Konfigurera Lösenordsskydd](/azure/active-directory/authentication/concept-password-ban-bad)i Azure AD som identifierar och blockerar kända svaga lösenord och deras varianter samt ytterligare svaga termer som är specifika för din organisation. Genom att använda Lösenordsskydd i Azure AD säkerställs att ändrade lösenord är starka.

## <a name="apply-app-data-protection-policies"></a>Använda principer för APP-dataskydd

APP:er definierar vilka appar som tillåts och vilka åtgärder de kan vidta med organisationens data. De val som finns tillgängliga i APP gör det möjligt för organisationer att anpassa skyddet efter sina specifika behov. För vissa är det kanske inte uppenbart vilka principinställningar som krävs för att implementera ett fullständigt scenario. För att hjälpa organisationer att prioritera klientslutpunktens hårdnande har Microsoft introducerat taxonomi för sitt APP-dataskyddsramverk för hantering av iOS- och Android-mobilappar.

Ramverket för APP-dataskydd är indelade i tre distinkta konfigurationsnivåer, med varje nivå som bygger på den föregående nivån:

- **Enterprise Basic Data Protection** (Nivå 1) garanterar att appar skyddas med en PIN-kod och krypteras samt utför selektiva rensningsåtgärder. För Android-enheter verifierar den här nivån Android-enhetsanningar. Det här är en konfiguration på postnivå som ger liknande dataskyddskontroll i Postlådeprinciper i Exchange Online och introducerar IT- och användarens population till APP.
- **Enterprise enhanced data protection** (Level 2) introduces APP dataläckningsskyddmekanismer och minimikraven för OS. Det här är den konfiguration som gäller för de flesta mobila användare med åtkomst till arbets- eller skoldata.
- **Enterprise high data protection** (Level 3) introduces advanced data protection mechanisms, enhanced PIN configuration, and APP Mobile Threat Defense. Den här konfigurationen är ett bra sätt för användare som har åtkomst till data med hög risk.

Om du vill se specifika rekommendationer för varje konfigurationsnivå och de lägsta program som måste skyddas, granskar du Ramverk för dataskydd [med programskyddsprinciper.](/mem/intune/apps/app-protection-framework)

Med de principer som beskrivs i [identitets-](microsoft-365-policies-configurations.md)och enhetsåtkomstkonfigurationer mappas baslinje- och känsligt skyddsnivå nära de förbättrade inställningarna för dataskydd på Nivå 2 för företag. Nivånivån hög nivå för skydd av hög nivå 3 är mappad till de höga dataskyddsinställningarna på Nivå 3.

|Skyddsnivå|Programskyddsprincip|Mer information|
|---|---|---|
|Grundläggande|[Nivå 2 förbättrat dataskydd](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Principinställningarna på nivå 2 innehåller alla principinställningar som rekommenderas för nivå 1 och lägger till eller uppdaterar nedanstående principinställningar för att implementera fler kontroller och en mer avancerad konfiguration än nivå 1.|
|Känslig|[Nivå 2 förbättrat dataskydd](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Principinställningarna på nivå 2 innehåller alla principinställningar som rekommenderas för nivå 1 och lägger till eller uppdaterar nedanstående principinställningar för att implementera fler kontroller och en mer avancerad konfiguration än nivå 1.|
|Mycket reglerad|[Hög dataskyddsnivå 3 för företag](/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|Principinställningarna på nivå 3 innehåller alla principinställningar som rekommenderas för nivå 1 och 2 och lägger bara till eller uppdaterar nedanstående principinställningar för att implementera fler kontroller och en mer avancerad konfiguration än nivå 2.|
|

Om du vill skapa en ny programskyddsprincip för varje plattform (iOS och Android) i Microsoft Endpoint Manager med inställningarna för dataskyddsramverk kan du:

1. Skapa principerna manuellt genom att följa stegen i Skapa [och distribuera principer för programskydd med Microsoft Intune.](/mem/intune/apps/app-protection-policies)
2. Importera [exempelmallarna för Intune App Protection Policy Configuration Framework JSON-mallar](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) [med Intunes PowerShell-skript](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-approved-apps-and-app-protection"></a>Kräv godkända appar och appskydd

Om du vill tillämpa appskyddsprinciperna som du tillämpade i Intune måste du skapa en princip för villkorsstyrd åtkomst så att godkända klientappar krävs och villkoren i APPskyddsprinciperna.

Tvingande APP-skyddsprinciper kräver en uppsättning principer som beskrivs i [Kräv appskyddsprincip för molnbaserad åtkomst med villkorsstyrd åtkomst.](/azure/active-directory/conditional-access/app-protection-based-conditional-access) Dessa principer ingår i den här rekommenderade uppsättningen principer för identitets- och åtkomstkonfiguration.

Följ "Steg 1: Konfigurera en villkorsstyrd åtkomstprincip för Azure AD för Microsoft 365" i [Scenario 1: Microsoft 365-appar](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)kräver godkända appar med appskyddsprinciper så att Outlook för iOS och Android blockeras, men OAuth-kompatibla Exchange ActiveSync-klienter blockeras från att ansluta till Exchange Online för att skapa principen för villkorsstyrd åtkomst som kräver godkända appar och APPskydd.

   > [!NOTE]
   > Med den här principen kan mobila användare komma åt alla Office-slutpunkter med hjälp av tillämpliga appar.

Om du aktiverar mobil åtkomst till Exchange Online implementerar du Blockera [ActiveSync-klienter,](secure-email-recommended-policies.md#block-activesync-clients)vilket förhindrar att Exchange ActiveSync-klienter utnyttjar grundläggande autentisering från att ansluta till Exchange Online. Den här principen visas inte i illustrationen högst upp i den här artikeln. Den beskrivs och visas i Principrekommendationer [för att skydda e-post.](secure-email-recommended-policies.md)

Om du vill skapa principen för villkorsstyrd åtkomst som kräver Edge för iOS och Android följer du "Steg 2: Konfigurera en villkorsbaserad åtkomstprincip för Azure AD för Microsoft 365" i [Scenario 2:](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-2-browser-apps-require-approved-apps-with-app-protection-policies)Webbläsarappar kräver godkända appar med appskyddsprinciper, vilket gör att Edge för iOS och Android blockeras, men blockerar andra mobila enhetswebbläsare från att ansluta till Microsoft 365-slutpunkter.

 De här principerna använder bevilja kontroller [Kräv godkänd klientapp](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) och [Kräv appskyddsprincip.](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)

Slutligen säkerställer blockering av äldre autentisering för andra klientappar på iOS- och Android-enheter att dessa klienter inte kan åsidosätta villkorsstyrda åtkomstprinciper. Om du följer vägledning i den här artikeln har du redan konfigurerat Blockera klienter [som inte stöder modern autentisering.](#block-clients-that-dont-support-multi-factor)

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definiera principer för enhetsefterlevnad

Principer för enhetsefterlevnad definierar de krav som enheter måste uppfylla för att fastställas som kompatibla. Du skapar Intune-policyer för enhetsefterlevnad i administrationscentret för Microsoft Endpoint Manager.

Du måste skapa en princip för varje dator, telefon eller pekplatta:

- Administratör för Android-enhet
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 och senare
- Windows 10 och senare

Om du vill skapa principer för enhetsefterlevnad loggar du in på [Administrationscenter](https://endpoint.microsoft.com) för Microsoft Endpoint Manager med dina administratörsautentiseringsuppgifter och går sedan **till Principer för** \> **enhetsefterlevnad.** \>  Välj **Skapa princip**.

För att principer för enhetsefterlevnad ska distribueras måste de tilldelas till användargrupper. Du tilldelar en princip när du har skapat och sparat den. Välj principen i administrationscentret och välj sedan **Uppgifter.** När du har valt de grupper du vill få principen väljer du Spara **för** att spara grupptilldelningen och distribuera principen.

Stegvisa instruktioner för hur du skapar efterlevnadsprinciper i Intune finns i Skapa en efterlevnadsprincip i [Microsoft Intune](/mem/intune/protect/create-compliance-policy) i Intune-dokumentationen.

### <a name="recommended-settings-for-windows-10-and-later"></a>Rekommenderade inställningar för Windows 10 och senare

Följande inställningar rekommenderas för datorer med Windows 10 och senare, enligt konfiguration i **steg 2: Efterlevnadsinställningar**, i processen för att skapa principen.

Information **om utvärderingsregler för > för Enhetshälsa för Windows Health-tjänsten** finns i den här tabellen.

|Egenskaper|Värde|Åtgärd|
|---|---|---|
|Kräv BitLocker|Kräv|Välj|
|Kräv att säker start aktiveras på enheten|Kräv|Välj|
|Kräv kodintegritet|Kräv|Välj|
|

För **Enhetsegenskaper** anger du lämpliga värden för operativsystemsversioner baserat på din IT och dina säkerhetsprinciper.

För **Konfigurationshanterarens efterlevnad** väljer du **Kräv**.

Information **om Systemsäkerhet** finns i den här tabellen.

|Skriv|Egenskaper|Värde|Åtgärd|
|---|---|---|---|
|Lösenord|Kräv lösenord för att låsa upp mobila enheter|Kräv|Välj|
||Enkla lösenord|Blockera|Välj|
||Lösenordstyp|Standardenhet|Välj|
||Minsta lösenordslängd|6|Skriv|
||Maximalt antal minuter av inaktivitet innan lösenord krävs|15|Skriv <p> Den här inställningen stöds för Android-versionerna 4.0 och senare eller KNOX 4.0 och senare. För iOS-enheter stöds det för iOS 8.0 och högre.|
||Lösenords giltighetstid (dagar)|41|Skriv|
||Antal tidigare lösenord för att förhindra återanvändning|5|Skriv|
||Kräv lösenord när enheten återgår från inaktivt läge (Mobile och Holographic)|Kräv|Tillgängligt för Windows 10 och senare|
|Kryptering|Kryptering av datalagring på enheten|Kräv|Välj|
|Enhetssäkerhet|Brandvägg|Kräv|Välj|
||Antivirus|Kräv|Välj|
||Antispionprogram|Kräv|Välj <p> Den här inställningen kräver en lösning mot spionprogram som är registrerad på Windows säkerhetscenter.|
|Defender|Microsoft Defender Antimalware|Kräv|Välj|
||Lägsta version av Microsoft Defender Antimalware||Skriv <p> Stöds endast för Windows 10-datorer. Microsoft rekommenderar versioner som inte har fler än fem versioner från den senaste versionen.|
||Microsoft Defender Antimalware-signatur uppdaterad|Kräv|Välj|
||Realtidsskydd|Kräv|Välj <p> Stöds endast för Windows 10 för skrivbordet|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender för Endpoint

|Skriv|Egenskaper|Värde|Åtgärd|
|---|---|---|---|
|Microsoft Defender för slutpunktsregler i administrationscentret för Microsoft Endpoint Manager|[Kräv att enheten ligger på eller under maskinriskresultatet](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#create-and-assign-compliance-policy-to-set-device-risk-level)|Medel|Välj|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Kräv kompatibla datorer (men inte kompatibla telefoner och surfplattor)

Innan du lägger till en princip för att kräva kompatibla datorer måste du registrera dina enheter för hantering i Intune. Användning av multifaktorautentisering rekommenderas innan enheter registreras i Intune för att säkerställa att enheten ligger hos den avsedda användaren.

Så här kräver du kompatibla datorer:

1. Gå till [Azure Portal och](https://portal.azure.com)logga in med dina autentiseringsuppgifter.
2. I listan över Azure-tjänster väljer du **Azure Active Directory.**
3. I listan **Hantera** väljer du **Säkerhet och** sedan **Villkorsstyrd åtkomst.**
4. Välj **Ny princip** och skriv namnet på den nya principen.

5. Under **Tilldelningar** väljer du **Användare och grupper** och tar med dem du vill att principen ska gälla för. Exkludera även undantagsgruppen för villkorsstyrd åtkomst.

6. Under **Uppgifter väljer** du **Molnappar eller åtgärder**.

7. Under **Inkludera** väljer du **Välj > Välj** och sedan önskade appar i listan **Molnappar.** Välj till exempel Exchange Online. Välj **Välj** när du är klar.

8. Om du vill ha kompatibla datorer (men inte kompatibla telefoner och surfplattor) **väljer** du Under Uppgifter väljer du **> enhetsplattformar.** Välj **Ja** för **Konfigurera**. Välj  **Välj enhetsplattformar**, **välj Windows** och **macOS** och välj sedan **Klar**.

9. Under **Access-kontroller** väljer du **Bevilja** .

10. Välj **Bevilja åtkomst** och markera sedan **Kräv att enheten markeras som kompatibel.** För flera kontroller markerar du **Kräv alla markerade kontroller**. Välj Välj när du är **klar.**

11. Välj **På** för **aktivera princip** och välj sedan **Skapa**.

> [!NOTE]
> Kontrollera att enheten är kompatibel innan du aktiverar den här principen. Annars kan du bli utelåst och kommer inte att kunna ändra den här principen förrän användarkontot har lagts till i undantagsgruppen Villkorsstyrd åtkomst.

## <a name="require-compliant-pcs-and-mobile-devices"></a>Kräv kompatibla datorer *och* mobila enheter

Så här kräver du efterlevnad för alla enheter:

1. Gå till [Azure Portal och](https://portal.azure.com)logga in med dina autentiseringsuppgifter.
2. I listan över Azure-tjänster väljer du **Azure Active Directory.**
3. I listan **Hantera** väljer du **Säkerhet och** sedan **Villkorsstyrd åtkomst.**
4. Välj **Ny princip** och skriv namnet på den nya principen.

5. Under **Tilldelningar** väljer du **Användare och grupper** och tar med dem du vill att principen ska gälla för. Exkludera även undantagsgruppen för villkorsstyrd åtkomst.

6. Under **Uppgifter väljer** du **Molnappar eller åtgärder**.

7. Under **Inkludera** väljer du **Välj > Välj** och sedan önskade appar i listan **Molnappar.** Välj till exempel Exchange Online. Välj **Välj** när du är klar.

8. Under **Access-kontroller** väljer du **Bevilja** .

9. Välj **Bevilja åtkomst** och markera sedan **Kräv att enheten markeras som kompatibel.** För flera kontroller markerar du **Kräv alla markerade kontroller**. Välj Välj när du är **klar.**

10. Välj **På** för **aktivera princip** och välj sedan **Skapa**.

> [!NOTE]
> Kontrollera att enheten är kompatibel innan du aktiverar den här principen. Annars kan du bli utelåst och kommer inte att kunna ändra den här principen förrän användarkontot har lagts till i undantagsgruppen Villkorsstyrd åtkomst.

## <a name="next-step"></a>Nästa steg

[![Steg 3: Principer för gästanvändare och externa användare](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Läs mer om principrekommendationer för gästanvändare och externa användare](identity-access-policies-guest-access.md)