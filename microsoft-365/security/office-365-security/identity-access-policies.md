---
title: Vanliga principer för identitets- och enhetsåtkomst – Microsoft 365 för | Microsoft Docs
description: Här beskrivs rekommenderade principer och konfigurationer för gemensamma identiteter och enhetsåtkomst.
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
ms.openlocfilehash: 87f064627446a0e41f5ed864c2ae37a2f0e60ba4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286819"
---
# <a name="common-identity-and-device-access-policies"></a>Vanliga principer för identitets- och enhetsåtkomst

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- Azure

I den här artikeln beskrivs de vanligaste rekommenderade principerna för att skydda åtkomsten till Microsoft 365-molntjänster, inklusive lokala program som publicerats med Azure Active Directory-programproxy (Azure AD).

I den här vägledningen beskrivs hur du distribuerar rekommenderade principer i en nyetablerade miljö. Genom att konfigurera dessa principer i en separat labbmiljö kan du förstå och utvärdera de rekommenderade principerna innan du distribuerar dem till din förproduktion och produktionsmiljöer. Din nyligen etablerade miljö kan vara endast molnbaserad eller hybrid för att återspegla dina utvärderingsbehov.

## <a name="policy-set"></a>Principuppsättning

I följande diagram visas den rekommenderade uppsättningen principer. Den visar vilken nivå av skydd varje princip gäller för och om principerna gäller för datorer eller telefoner och surfplattor, eller båda kategorierna av enheter. Den visar också var du konfigurerar principerna.

[![Vanliga principer för konfigurering av identitet och enhetsåtkomst](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

[Visa en större version av den här bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

Här är en PDF-sammanfattning på en sida med länkar till enskilda principer:

[![Thumb-bild för Identitet och enhetsskydd för Microsoft 365-handout](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [Visa som PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Ladda ned som PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

I resten av den här artikeln beskrivs hur du konfigurerar dessa principer.

> [!NOTE]
> Vi rekommenderar att du kräver multifaktorautentisering (MFA) innan du registrerar enheter i Intune för att försäkra dig om att enheten tillhör den avsedda användaren. Du måste registrera enheter i Intune innan du kan tillämpa principer för enhetsefterlevnad.

För att ge dig tid att utföra de här uppgifterna rekommenderar vi att du implementerar baslinjeprinciperna i den ordning som anges i den här tabellen. MFA-principerna för känsliga och högreglerade skyddsnivåer kan implementeras när som helst.

|Skyddsnivå|Principer|Mer information|
|---|---|---|
|**Grundläggande**|[Kräv MFA när inloggningsrisken är *medelhög* eller *hög*](#require-mfa-based-on-sign-in-risk)||
||[Blockera klienter som inte har stöd för modern autentisering](#block-clients-that-dont-support-multi-factor)|Klienter som inte använder modern autentisering kan åsidosätta villkorsstyrda åtkomstprinciper, så det är viktigt att blockera dessa.|
||[Användare med hög risk måste byta lösenord](#high-risk-users-must-change-password)|Tvingar användarna att ändra sitt lösenord när de loggar in om högriskaktivitet identifieras för deras konto.|
||[Använda principer för programdataskydd](#apply-app-data-protection-policies)|Appskyddsprincip för One Intune per plattform (Windows, iOS/iPadOS, Android).|
||[Kräv godkända appar och appskydd](#require-approved-apps-and-app-protection)|Tillämpar skydd för mobilappar för telefoner och surfplattor med iOS, iPadOS eller Android.|
||[Definiera principer för enhetsefterlevnad](#define-device-compliance-policies)|En princip för varje plattform.|
||[Kräv kompatibla PC-datorer](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Framtvingar Intune-hantering av PC-datorer med Windows eller MacOS.|
|**Känslig**|[Kräv MFA när inloggningsrisken *är låg,* *medel* eller *hög*](#require-mfa-based-on-sign-in-risk)||
||[Kräv kompatibla datorer *och* mobila enheter](#require-compliant-pcs-and-mobile-devices)|Framtvingar Intune-hantering för både PC-datorer (Windows eller MacOS) och telefoner och surfplattor (iOS, iPadOS eller Android).|
|**Strikt reglerad**|[*Kräv* alltid MFA](#require-mfa-based-on-sign-in-risk)|
|

## <a name="assigning-policies-to-groups-and-users"></a>Tilldela principer till grupper och användare

Innan du konfigurerar principer identifierar du de Azure AD-grupper du använder för varje skyddsnivå. Normalt gäller baslinjeskydd för alla i organisationen. En användare som ingår för både baslinje- och känsligt skydd kommer att tillämpa alla baslinjeprinciper plus de känsliga principerna. Skyddet ackumuleras och den mest restriktiva principen tillämpas.

En rekommenderad metod är att skapa en Azure AD-grupp för undantag i villkorsstyrd åtkomst. Lägg till den här gruppen i  alla **villkorsstyrda** åtkomstprinciper i inställningen Exkludera värdet för **användare och** grupper i avsnittet Tilldelningar. Det ger dig en metod för att ge åtkomst till en användare medan du felsöker åtkomstproblem. Det här rekommenderas endast som en tillfällig lösning. Övervaka den här gruppen efter ändringar och se till att undantagsgruppen endast används som avsett.

Här är ett exempel på grupptilldelning och undantag för krav på MFA.

![Exempel på grupptilldelning och undantag för MFA-principer](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Här är resultatet:

- Alla användare måste använda MFA när inloggningsrisken är medelstor eller hög.

- Medlemmar i ledningsgruppen måste använda MFA när inloggningsrisken är låg, medium eller hög.

  I det här fallet matchar medlemmar i ledningsgruppen både baslinjepolicyn och känsliga villkorsstyrda åtkomstprinciper. Åtkomstkontrollerna för båda principerna kombineras, vilket i det här fallet motsvarar den känsliga villkorsstyrda åtkomstprincipen.

- Medlemmar i den översta hemliga Project X-gruppen måste alltid använda MFA

  I det här fallet matchar medlemmar i den översta hemliga Project X-gruppen både principerna för baslinje och mycket reglerad villkorsstyrd åtkomst. Åtkomstkontroller för båda principerna kombineras. Eftersom åtkomstkontrollen för den villkorsstyrda villkorsstyrda principen är mer restriktiv används den.

Var försiktig när du använder högre skyddsnivåer för grupper och användare. Medlemmar i den översta hemliga project X-gruppen måste till exempel använda MFA varje gång de loggar in, även om de inte arbetar med det högreglerade innehållet för Project X.

Alla Azure AD-grupper som skapats som en del av dessa rekommendationer måste skapas som Microsoft 365-grupper. Detta är viktigt för distribution av känslighetsetiketter när du skyddar dokument i Microsoft Teams och SharePoint.

![Skärmdump för att skapa Microsoft 365-grupper](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>Kräv MFA baserat på inloggningsrisk

Du bör be användarna registrera sig för MFA innan de kräver att de används. Om du har Microsoft 365 E5, Microsoft 365 E3 med tillägget Identity & Threat Protection, Office 365 med EMS E5 eller enskilda Azure AD Premium P2-licenser kan du använda MFA-registreringsprincipen med Azure AD Identity Protection för att kräva att användare registrerar sig för MFA. Förutsättningarna [för detta](identity-access-prerequisites.md) är att registrera alla användare med MFA.

När användarna har registrerats kan du kräva MFA för inloggning med en ny villkorsstyrd åtkomstprincip.

1. Gå till [Azure Portal och](https://portal.azure.com)logga in med dina autentiseringsuppgifter.
2. Välj Azure Active Directory i listan **med Azure-tjänster.**
3. I listan **Hantera** väljer du **Säkerhet och** sedan **Villkorsstyrd åtkomst.**
4. Välj **Ny** princip och skriv namnet på den nya principen.

I följande tabeller beskrivs principinställningarna för villkorsstyrd åtkomst så att MFA krävs baserat på inloggningsrisker.

I **avsnittet Uppgifter:**

|Inställning|Egenskaper|Värden|Kommentarer|
|---|---|---|---|
|Användare och grupper|Inkludera|**Välj användare och grupper > användare och grupper:** Välj specifika grupper som innehåller riktade användarkonton.|Börja med den grupp som innehåller pilotanvändarkonton.|
||Undanta|**Användare och grupper:** Välj din undantagsgrupp för villkorsstyrd åtkomst; tjänstkonton (appidentiteter).|Medlemskapet ska ändras tillfälligt och efter behov.|
|Molnappar eller -åtgärder|**Molnappar > Inkludera**|**Välj appar:** Välj de appar som du vill att den här principen ska gälla för. Välj till exempel Exchange Online.||
|Villkor|||Konfigurera villkor som är specifika för din miljö och dina behov.|
||Inloggningsrisk||Se vägledningen i följande tabell.|
|

### <a name="sign-in-risk-condition-settings"></a>Villkorsinställningar för inloggningsrisker

Tillämpa inställningarna för risknivå baserat på den skyddsnivå som du riktar in.

|Skyddsnivå|Nödvändiga risknivåvärden|Åtgärd|
|---|---|---|
|Grundläggande|Hög, medel|Kontrollera båda.|
|Känslig|Hög, medel, låg|Markera alla tre.|
|Strikt reglerad||Låt alla alternativ vara avmarkerade för att alltid tillämpa MFA.|
|

I avsnittet **Access-kontroller:**

|Inställning|Egenskaper|Värden|Åtgärd|
|---|---|---|---|
|Bevilja|**Grant access**||Välj|
|||**Kräv multifaktorautentisering**|Check|
||**Kräv alla markerade kontroller**||Välj|
|

Välj **Välj för** att spara inställningarna **för** Bevilja.

Välj slutligen **På för** principen **Aktivera** och välj sedan **Skapa.**

Överväg även att använda [verktyget Vad händer](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) om för att testa principen.

## <a name="block-clients-that-dont-support-multi-factor"></a>Blockera klienter som inte har stöd för flera faktor

Använd inställningarna i de här tabellerna för en princip för villkorsstyrd åtkomst för att blockera klienter som inte har stöd för multifaktorautentisering.

I [den här artikeln](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md) finns en lista över klienter i Microsoft 365 som har stöd för multifaktorautentisering.

I **avsnittet Uppgifter:**

|Inställning|Egenskaper|Värden|Kommentarer|
|---|---|---|---|
|Användare och grupper|Inkludera|**Välj användare och grupper > användare och grupper:** Välj specifika grupper som innehåller riktade användarkonton.|Börja med den grupp som innehåller pilotanvändarkonton.|
||Undanta|**Användare och grupper:** Välj din undantagsgrupp för villkorsstyrd åtkomst; tjänstkonton (appidentiteter).|Medlemskapet ska ändras tillfälligt och efter behov.|
|Molnappar eller -åtgärder|**Molnappar > Inkludera**|**Välj appar:** Välj de program som motsvarar de klienter som inte stöder modern autentisering.||
|Villkor|**Klientappar**|Välj **Ja** för **Konfigurera** <p> Avmarkera bkryssmarkeringarna **för webbläsar-** och **mobilprogram och skrivbordsklienter**||
|

I avsnittet **Access-kontroller:**

|Inställning|Egenskaper|Värden|Åtgärd|
|---|---|---|---|
|Bevilja|**Blockera åtkomst**||Välj|
||**Kräv alla markerade kontroller**||Välj|
|

Välj **Välj för** att spara inställningarna **för** Bevilja.

Välj slutligen **På för** principen **Aktivera** och välj sedan **Skapa.**

Överväg att använda [verktyget Vad händer](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) om för att testa principen.

För Exchange Online kan du använda autentiseringsprinciper för att inaktivera [grundläggande](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)autentisering, vilket tvingar alla klientåtkomstförfrågningar att använda modern autentisering.

## <a name="high-risk-users-must-change-password"></a>Användare med hög risk måste byta lösenord

Du måste tillämpa följande princip för att säkerställa att alla högriskanvändares komprometterade konton tvingas utföra en lösenordsändring när du loggar in.

Logga in på [Microsoft https://portal.azure.com) Azure-portalen (med](https://portal.azure.com/) dina administratörsuppgifter och navigera sedan till **Azure AD Identity Protection > user risk policy.**

I **avsnittet Uppgifter:**

|Type (Typ)|Egenskaper|Värden|Åtgärd|
|---|---|---|---|
|Användare|Inkludera|**Alla användare**|Välj|
|Användarrisk|**Högsta**||Välj|
|

I det andra **avsnittet Om** uppgifter:

|Type (Typ)|Egenskaper|Värden|Åtgärd|
|---|---|---|---|
|Åtkomst|**Tillåt åtkomst**||Välj|
|||**Kräv lösenordsändring**|Check|
|

Välj **Klar** för att spara **Access-inställningarna.**

Välj slutligen **På för** **tillämpa-princip** och välj sedan **Spara.**

Överväg att använda [verktyget Vad händer](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) om för att testa principen.

Använd den här principen tillsammans med konfigurera lösenordsskydd i [Azure AD,](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)som identifierar och blockerar kända svaga lösenord och deras varianter och ytterligare svaga termer som är specifika för din organisation. Genom att använda azure AD-lösenordsskydd ser du till att ändrade lösenord är starka.

## <a name="apply-app-data-protection-policies"></a>Använda principer för APP-dataskydd

Appskyddsprinciper (APP) definierar vilka appar som tillåts och vilka åtgärder de kan vidta med din organisations data. Med alternativen i APP kan organisationer anpassa skyddet efter sina specifika behov. I vissa fall är det kanske inte uppenbart vilka principinställningar som krävs för att implementera ett fullständigt scenario. Microsoft har introducerat taxonomi för sitt ramverk för appdataskydd för iOS- och Android-mobilappar för att hjälpa organisationer att prioritera ändpunkt för mobila klienter.

Ramverket för APP-dataskydd är indelade i tre olika konfigurationsnivåer, där varje nivå bygger på den föregående nivån:

- **Enterprise Basic Data Protection** (Nivå 1) säkerställer att appar skyddas med en PIN-kod och krypteras, och utför selektiva rensningsåtgärder. För Android-enheter verifierar den här nivån attestation för Android-enheter. Det här är en konfiguration på inmatningsnivå som ger liknande dataskyddskontroll i Postlådeprinciper i Exchange Online och introducerar IT- och användarpopulationen i APP.
- **Med Företag förbättrat dataskydd** (nivå 2) introduceras mekanismer för att förhindra dataläckning i APP och lägsta OS-krav. Det här är den konfiguration som gäller för de flesta mobila användare som har åtkomst till arbets- eller skoldata.
- **Enterprise high data protection** (Level 3) introduces advanced data protection mechanisms, enhanced PIN configuration, and APP Mobile Threat Defense. Den här konfigurationen är ett bra sätt för användare som använder högriskdata.

Granska dataskyddsramarna med appskyddsprinciper om du vill se specifika rekommendationer för varje konfigurationsnivå och de lägsta program [som måste](https://docs.microsoft.com/mem/intune/apps/app-protection-framework)skyddas.

Med de principer som beskrivs i identitets- och enhetsåtkomstkonfigurationer mappas baslinje och nivå för känsligt skydd nära med de förbättrade [dataskyddsinställningarna](microsoft-365-policies-configurations.md)på Nivå 2 för företag. Nivånivån för hög nivå av skydd som regleras ligger nära de höga dataskyddsinställningarna på Nivå 3 för företag.

|Skyddsnivå|Appskyddsprincip|Mer information|
|---|---|---|
|Grundläggande|[Bättre dataskydd på Nivå 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Principinställningarna som tillämpas på nivå 2 innehåller alla principinställningar som rekommenderas för nivå 1 och lägger bara till eller uppdaterar nedanstående principinställningar för att implementera fler kontroller och en mer avancerad konfiguration än nivå 1.|
|Känslig|[Bättre dataskydd på Nivå 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Principinställningarna som tillämpas på nivå 2 innehåller alla principinställningar som rekommenderas för nivå 1 och lägger bara till eller uppdaterar nedanstående principinställningar för att implementera fler kontroller och en mer avancerad konfiguration än nivå 1.|
|Mycket reglerad|[Hög dataskyddsnivå 3 för företag](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|Principinställningarna som tillämpas på nivå 3 innehåller alla principinställningar som rekommenderas för nivå 1 och 2 och lägger bara till eller uppdaterar principinställningarna nedan för att implementera fler kontroller och en mer avancerad konfiguration än nivå 2.|
|

Om du vill skapa en ny princip för programskydd för varje plattform (iOS och Android) i Microsoft Endpoint Manager med hjälp av inställningarna för dataskyddsramverk kan du:

1. Skapa principerna manuellt genom att följa stegen i Skapa och distribuera principer [för programskydd med Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/app-protection-policies)
2. Importera [exempelmallarna för Intune App Protection Policy Configuration Framework JSON](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) [med Intunes PowerShell-skript.](https://github.com/microsoftgraph/powershell-intune-samples)

## <a name="require-approved-apps-and-app-protection"></a>Kräv godkända appar och APPskydd

Om du vill tillämpa APP-skyddsprinciper som du har tillämpat i Intune måste du skapa en villkorsstyrd åtkomstprincip för att kräva godkända klientappar och villkoren i APP-skyddsprinciperna.

Tillämpning av APP-skyddsprinciper kräver en uppsättning principer som beskrivs i [Kräv appskyddsprincip för molnbaserad appåtkomst med villkorsstyrd åtkomst.](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access) Dessa principer ingår var och en i den här rekommenderade uppsättningen principer för identitets- och åtkomstkonfiguration.

Följ "Steg 1: Konfigurera en villkorsstyrd åtkomstprincip för Azure AD för Microsoft 365" i Scenario 1 om du vill skapa en princip för villkorsstyrd åtkomst som kräver godkända appar och APPskydd i Scenario [1: Microsoft 365-appar](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)kräver godkända appar med appskyddsprinciper, vilket gör att Outlook för iOS och Android blockeras, men OAuth-kompatibla Exchange ActiveSync-klienter blockeras från att ansluta till Exchange Online.

   > [!NOTE]
   > Den här principen säkerställer att mobila användare kan komma åt alla Office-slutpunkter med hjälp av tillämpliga appar.

Om du aktiverar mobil åtkomst till Exchange Online implementerar du [Blockera ActiveSync-klienter,](secure-email-recommended-policies.md#block-activesync-clients)vilket förhindrar att Exchange ActiveSync-klienter utnyttjar grundläggande autentisering från att ansluta till Exchange Online. Den här principen visas inte i illustrationen högst upp i den här artikeln. Den beskrivs och visas i principrekommendationer för [att skydda e-post.](secure-email-recommended-policies.md)

Om du vill skapa principen för villkorsstyrd åtkomst som kräver Edge för iOS och Android följer du "Steg 2: Konfigurera en villkorsbaserad åtkomstprincip för Azure AD för Microsoft 365" i [Scenario 2:](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-2-browser-apps-require-approved-apps-with-app-protection-policies)Webbläsarappar kräver godkända appar med appskyddsprinciper, vilket gör att Edge för iOS och Android blockeras, men blockerar andra webbläsare för mobila enheter från att ansluta till Microsoft 365-slutpunkter.

 De här principerna utnyttjar grant-kontrollerna [Kräv godkänd klientapp](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) [och kräv programskyddsprincip.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)

Slutligen säkerställer blockering av äldre autentisering för andra klientappar på iOS- och Android-enheter att dessa klienter inte kan kringgå villkorsstyrda åtkomstprinciper. Om du följer vägledningen i den här artikeln har du redan konfigurerat [Blockeringsklienter som inte stöder modern autentisering.](#block-clients-that-dont-support-multi-factor)

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definiera principer för enhetsefterlevnad

Principer för enhetsefterlevnad definierar de krav som enheter måste uppfylla för att fastställas som kompatibla. Du skapar Intune-efterlevnadsprinciper för enheter från administrationscentret för Microsoft Endpoint Manager.

Du måste skapa en princip för varje dator, telefon eller pekplatta:

- Administratör för Android-enhet
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 och senare
- Windows 10 och senare

Om du vill skapa principer för enhetsefterlevnad loggar du in på administrationscentret för [Microsoft Endpoint Manager](https://endpoint.microsoft.com) med dina administratörsuppgifter och navigerar sedan till principer för  \> **enhetsefterlevnad.** \>  Välj **Skapa princip.**

För att principer för enhetsefterlevnad ska distribueras måste de tilldelas till användargrupper. Du tilldelar en princip när du har skapat och sparat den. I administrationscentret väljer du principen och sedan **Uppgifter.** När du har valt de grupper som du vill ska få principen väljer du **Spara** för att spara grupptilldelningen och distribuera principen.

Stegvisa instruktioner för hur du skapar efterlevnadsprinciper i Intune finns i Skapa en efterlevnadsprincip i [Microsoft Intune-dokumentationen.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)

### <a name="recommended-settings-for-windows-10-and-later"></a>Rekommenderade inställningar för Windows 10 och senare

Följande inställningar rekommenderas för datorer med Windows 10 och senare, enligt konfiguration i steg **2:** Efterlevnadsinställningar, för processen att skapa princip.

Information **om utvärderingsregler > för enhetshälsa för Windows Health-utvärderingstjänsten** finns i den här tabellen.

|Egenskaper|Value|Åtgärd|
|---|---|---|
|Kräv BitLocker|Kräv|Välj|
|Kräv säker uppstart för att vara aktiverat på enheten|Kräv|Välj|
|Kräv kodintegritet|Kräv|Välj|
|

För **enhetsegenskaper** anger du lämpliga värden för operativsystemsversioner baserat på IT- och säkerhetsprinciper.

Välj **Konfigurationshanteraren för** **regelefterlevnad.**

Information **om systemsäkerhet** finns i den här tabellen.

|Type (Typ)|Egenskaper|Value|Åtgärd|
|---|---|---|---|
|Lösenord|Kräv lösenord för att låsa upp mobila enheter|Kräv|Välj|
||Enkla lösenord|Blockera|Välj|
||Lösenordstyp|Standardenhet|Välj|
||Minsta lösenordslängd|6|Type (Typ)|
||Maximalt antal minuter av inaktivitet innan lösenord krävs|15|Type (Typ) <p> Den här inställningen stöds i Android versionerna 4.0 och senare, eller KNOX 4.0 och senare. För iOS-enheter stöds det för iOS 8.0 och högre.|
||Lösenords giltighetstid (dagar)|41|Type (Typ)|
||Antal tidigare lösenord för att förhindra återanvändning|5|Type (Typ)|
||Kräva lösenord när enheten återgår från inaktivt läge (mobil och holografi)|Kräv|Tillgängligt för Windows 10 och senare|
|Kryptering|Kryptering av datalagring på enhet|Kräv|Välj|
|Enhetssäkerhet|Brandvägg|Kräv|Välj|
||Antivirus|Kräv|Välj|
||Antispionprogram|Kräv|Välj <p> Den här inställningen kräver en lösning mot spionprogram som är registrerad på Windows säkerhetscenter.|
|Defender|Microsoft Defender Antimalware|Kräv|Välj|
||Minimiversion av Microsoft Defender Antimalware||Type (Typ) <p> Stöds endast för Windows 10 på datorn. Microsoft rekommenderar versioner som inte är längre än fem efter i den senaste versionen.|
||Microsoft Defender Antimalware-signatur uppdaterad|Kräv|Välj|
||Realtidsskydd|Kräv|Välj <p> Stöds endast för Windows 10 på datorn|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender för Endpoint

|Type (Typ)|Egenskaper|Value|Åtgärd|
|---|---|---|---|
|Microsoft Defender för slutpunktsregler|Kräv att enheten ligger på eller under maskinriskresultatet|Medel|Välj|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Kräv kompatibla datorer (men inte kompatibla telefoner och surfplattor)

Se till att registrera enheter för hantering i Intune innan du lägger till en princip som kräver kompatibla datorer. Användning av multifaktorautentisering rekommenderas innan enheter registreras i Intune för att säkerställa att enheten tillhör den avsedda användaren.

Så här kräver du kompatibla datorer:

1. Gå till [Azure Portal och](https://portal.azure.com)logga in med dina autentiseringsuppgifter.
2. Välj Azure Active Directory i listan **med Azure-tjänster.**
3. I listan **Hantera** väljer du **Säkerhet och** sedan **Villkorsstyrd åtkomst.**
4. Välj **Ny** princip och skriv namnet på den nya principen.

5. Under **Tilldelningar** väljer du **Användare och grupper** och tar med vem som principen ska gälla för. Exkludera även undantagsgruppen för villkorsstyrd åtkomst.

6. Välj **Molnappar** eller **-åtgärder under Uppgifter.**

7. För **Inkludera** väljer du **Välj > Välj** och sedan önskade appar i listan **Med** molnappar. Välj till exempel Exchange Online. Välj **Välj** när du är klar.

8. Om du vill kräva kompatibla datorer (men inte kompatibla telefoner och surfplattor) **väljer** du Villkor och > **enhetsplattformar.** Välj **Ja** för **Konfigurera.** Välj **Välj enhetsplattformar,** **välj Windows** och **macOS** och välj sedan **Klar.**

9. Välj **Bevilja under Access-kontroller.** 

10. Välj **Bevilja åtkomst** och kontrollera sedan **kräv att enheten markeras som kompatibel.** För flera kontroller väljer du **Kräv alla markerade kontroller.** Välj Välj när det är **klart.**

11. Välj **På** för **att aktivera** principen och välj sedan **Skapa.**

> [!NOTE]
> Kontrollera att enheten är kompatibel innan du aktiverar den här principen. Annars kan du bli utelåst och kommer inte att kunna ändra den här principen förrän användarkontot har lagts till i undantagsgruppen villkorsstyrd åtkomst.

## <a name="require-compliant-pcs-and-mobile-devices"></a>Kräv kompatibla datorer *och* mobila enheter

Så här kräver du efterlevnad för alla enheter:

1. Gå till [Azure Portal och](https://portal.azure.com)logga in med dina autentiseringsuppgifter.
2. Välj Azure Active Directory i listan **med Azure-tjänster.**
3. I listan **Hantera** väljer du **Säkerhet och** sedan **Villkorsstyrd åtkomst.**
4. Välj **Ny** princip och skriv namnet på den nya principen.

5. Under **Tilldelningar** väljer du **Användare och grupper** och tar med vem som principen ska gälla för. Exkludera även undantagsgruppen för villkorsstyrd åtkomst.

6. Välj **Molnappar** eller **-åtgärder under Uppgifter.**

7. För **Inkludera** väljer du **Välj > Välj** och sedan önskade appar i listan **Med** molnappar. Välj till exempel Exchange Online. Välj **Välj** när du är klar.

8. Välj **Bevilja under Access-kontroller.** 

9. Välj **Bevilja åtkomst** och kontrollera sedan **kräv att enheten markeras som kompatibel.** För flera kontroller väljer du **Kräv alla markerade kontroller.** Välj Välj när det är **klart.**

10. Välj **På** för **att aktivera** principen och välj sedan **Skapa.**

> [!NOTE]
> Kontrollera att enheten är kompatibel innan du aktiverar den här principen. Annars kan du bli utelåst och kommer inte att kunna ändra den här principen förrän användarkontot har lagts till i undantagsgruppen villkorsstyrd åtkomst.

## <a name="next-step"></a>Nästa steg

[![Steg 3: Principer för gästanvändare och externa användare](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Läs mer om principrekommendationer för gästanvändare och externa användare](identity-access-policies-guest-access.md)
