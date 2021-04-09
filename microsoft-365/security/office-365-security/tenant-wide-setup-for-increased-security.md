---
title: Konfigurera Microsoft 365-klienten för ökad säkerhet
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: I det här avsnittet får du hjälp med rekommenderade inställningar för hela klientorganisationen som påverkar säkerheten för Microsoft 365-miljön.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: efcc468dc9b6a41af79ecf2f22a6ad58a410e08f
ms.sourcegitcommit: a46532bb422ee51331f478ff50cc5444586bf6a9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2021
ms.locfileid: "51650332"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Konfigurera Microsoft 365-klienten för ökad säkerhet

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I det här avsnittet får du hjälp med rekommenderade inställningar för hela klientorganisationen som påverkar säkerheten för Microsoft 365-miljön. Dina säkerhetsbehov kan kräva mer eller mindre säkerhet. Använd de här rekommendationerna som utgångspunkt.

## <a name="check-office-365-secure-score"></a>Kontrollera Office 365 Secure Score

Office 365 Secure Score analyserar organisationens säkerhet utifrån vanliga aktiviteter och säkerhetsinställningar och tilldelar ett poäng. Börja med att anteckna det aktuella resultatet. Om du justerar vissa inställningar för hela klientorganisationen ökar poängen. Målet är inte att uppnå maxresultatet, utan att vara medveten om möjligheter att skydda din miljö som inte negativt påverkar användarnas produktivitet. Se [Microsoft Secure Score](../defender/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Anpassa principer för hothantering i Säkerhetscenter för Microsoft 365

Säkerhetscentret i Microsoft 365 innehåller funktioner som skyddar din miljö. Den innehåller även rapporter och instrumentpaneler som du kan använda för att övervaka och vidta åtgärder. Vissa områden har standardprincipkonfigurationer. Vissa områden inkluderar inte standardprinciper eller regler. Besök de här principerna under hantering av hot för att anpassa inställningarna för hothantering för en säkrare miljö.

****

|Område|Innehåller en standardprincip|Rekommendation|
|---|---|---|
|**Skydd mot nätfiske**|Ja|Om du har en egen domän konfigurerar du standardprincipen för skydd mot nätfiske för att skydda dina mest värdefulla användares e-postkonton, till exempel din VD, och för att skydda din domän. <p> Läs Principer för skydd mot nätfiske i [Office 365](set-up-anti-phishing-policies.md) och läs Konfigurera principer för skydd mot nätfiske i [EOP](configure-anti-phishing-policies-eop.md) eller Konfigurera principer för nätfiske i [Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md)|
|**Anti-Malware Engine**|Ja| Redigera standardprincipen: <ul><li>Vanliga filter för bifogade filer: Välj på</li></ul> <p> Du kan också skapa egna principer för skadlig programvara och tillämpa dem på vissa användare, grupper eller domäner i organisationen. <p> Mer information: <ul><li>[Skydd mot skadlig kod](anti-malware-protection.md)</li><li>[Konfigurera principer för skydd mot skadlig kod](configure-anti-malware-policies.md)</li></ul>|
|**Säkra bifogade filer i Microsoft Defender för Office 365**|Nej|På huvudsidan för Säkra bifogade filer klickar du **på Globala inställningar** och aktiverar den här inställningen: <ul><li>**Aktivera Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams.**</li></ul> <p> Skapa en princip för säkra bifogade filer med följande inställningar: <ul><li> **Blockera:** Välj Blockera **som** det okända svaret på skadlig programvara.</li><li>**Aktivera omdirigering:** Markera den här rutan och ange en e-postadress, till exempel ett administratörs- eller karantänkonto.</li><li>**Använd ovanstående val om sökning efter bifogade filer med skadlig programvara inträffar:** Markera den här rutan.</li><li>**_Används för:_* **Mottagarens domän** \> är välj din domän.</li></ul> <p> Mer information: [Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams](mdo-for-spo-odb-and-teams.md) och Konfigurera principer för säkra bifogade [filer](set-up-safe-attachments-policies.md)|
|**Säkra länkar i Microsoft Defender för Office 365**|Ja|På huvudsidan för Säkra länkar klickar du på **Globala inställningar:** <ul><li>**Använda säkra länkar i: Office 365-program:** Kontrollera att den här inställningen är aktiverad.</li><li>**Spåra inte när användare klickar på Säkra länkar**: Inaktivera den här inställningen för att spåra användarklick.</li></ul> <p> Skapa en princip för säkra länkar med följande inställningar: <ul><li>**Välj åtgärden för okända potentiellt skadliga URL-adresser i meddelanden:** Kontrollera att den här inställningen är **På**.</li><li>**Välj åtgärden för okända eller potentiellt skadliga URL-adresser i Microsoft Teams:** Kontrollera att den här inställningen är **På**.</li><li>**Använd URL-skanning i realtid för misstänkta länkar och länkar som pekar på filer**: Markera den här rutan.</li><li>**Vänta tills URL-skanningen är klar innan du levererar meddelandet**: Markera den här rutan.</li><li>**Använda säkra länkar i e-postmeddelanden som skickas inom organisationen:** Markera den här rutan</li><li>**Tillåt inte användare att klicka sig fram till den ursprungliga URL:en:** Markera den här rutan.</li><li>**Används för:** **Mottagarens domän** \> är välj din domän.</li></ul> <p> Mer information: [Konfigurera principer för säkra länkar.](set-up-safe-links-policies.md)|
|**Skräppostskydd (e-postfiltrering)**|Ja| Vad du bör titta efter: <ul><li>För mycket skräppost – Välj Anpassade inställningar och redigera standardprincipen för skräppostfilter.</li><li>Förfalskningsinformation – Granska avsändare som förfalskning av din domän. Blockera eller tillåt dessa avsändare.</li></ul> <p> Mer information: [Skydd mot skräppost för e-post i Microsoft 365.](anti-spam-protection.md)|
|***E-postautentisering***|Ja|E-postautentisering använder ett DNS (Domain Name System) för att lägga till verifierbar information i e-postmeddelanden om avsändaren av ett e-postmeddelande. Microsoft 365 uppsättningar e-postautentisering för sin standarddomän (onmicrosoft.com), men Microsoft 365-administratörer kan också använda e-postautentisering för egna domäner. Tre autentiseringsmetoder används: <ul><li>Sender Policy Framework (eller SPF).</li><ul><li>Mer information om konfiguration [finns i Konfigurera SPF i Microsoft 365 för att förhindra förfalskning.](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</li></ul> <li>DKIM (DomainKeys Identified Mail).</li><ul><li>Se [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän.](use-dkim-to-validate-outbound-email.md)</li><li>När du har konfigurerat DKIM aktiverar du den i säkerhetscentret.</li></ul><li>DMARC (Domain-based Message Authentication, Reporting, and Conformance).</li><ul><li>För DMARC-konfiguration [Använd DMARC för att validera e-post i Microsoft 365.](use-dmarc-to-validate-email.md)</li></ul></ul>|
|

> [!NOTE]
> För icke-standarddistributioner av SPF, hybriddistributioner och felsökning: Hur [Microsoft 365 använder Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)för att förhindra förfalskning.

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>Visa instrumentpaneler och rapporter i säkerhets- och efterlevnadscenter

Besök de här rapporterna och instrumentpanelerna om du vill veta mer om din miljö. Data i de här rapporterna blir rikare när organisationen använder Office 365-tjänster. För tillfället bör du känna till vad du kan övervaka och vidta åtgärder för. Mer information finns i : Rapporter i Säkerhets- och [efterlevnadscenter för Microsoft 365.](../../compliance/reports-in-security-and-compliance.md)

****

|Instrumentpanelen|Beskrivning|
|---|---|
|[Instrumentpanel för hantering av hot](security-dashboard.md)|I avsnittet **Hantering** av hot på säkerhetscentret använder du den här instrumentpanelen för att se hot som redan har hanterats, och som ett praktiskt verktyg för att rapportera till beslutsfattare om vilka undersöknings- och svarsfunktioner för hot som redan har gjorts för att skydda ditt företag.|
|[Hotutforskaren (eller realtidsidentifieringar)](threat-explorer.md)|Det här är också i **avsnittet Hantering av** hot i säkerhetscentret. Om du undersöker eller upplever en attack mot din klientorganisation kan du använda Utforskaren (eller identifieringar i realtid) för att analysera hot. Utforskaren (och rapporten över identifieringar i realtid) visar antalet attacker över tid och du kan analysera dessa data med hjälp av hotfamiljer, attackersinfrastruktur med mera. Du kan också markera alla misstänkta e-postmeddelanden för listan Incidenter.|
|Rapporter – Instrumentpanel|I avsnittet **Rapporter** i säkerhetscenter kan du visa granskningsrapporter för SharePoint Online- och Exchange Online-organisationer. Du kan också öppna inloggningsrapporter för användare i Azure Active Directory (Azure AD), användaraktivitetsrapporter och Azure AD-granskningsloggen från **sidan Visa** rapporter.|
|

![Instrumentpanel för säkerhetscenter](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Konfigurera ytterligare inställningar för hela klientorganisationen i Exchange Online

Många av kontrollerna för säkerhet och skydd i administrationscentret för Exchange ingår också i säkerhetscentret. Du behöver inte konfigurera dessa på båda platserna. Här är några ytterligare inställningar som rekommenderas.

****

|Område|Innehåller en standardprincip|Rekommendation|
|---|---|---|
|**E-postflöde** (e-postflödesregler, kallas även transportregler)|Nej|Lägg till en e-postflödesregel som skyddar mot utpressningstrojaner genom att blockera körbara filtyper och Office-filtyper som innehåller makron. Mer information finns i Använda [e-postflödesregler för att kontrollera bifogade filer i meddelanden i Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments) <p> Se följande avsnitt: <ul><li>[Skydda mot utpressningstrojaner](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Skydd mot skadlig programvara och utpressningstrojaner i Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Återställa efter en utpressningstrojanattack i Office 365](recover-from-ransomware.md)</li></ul> <p> Skapa en e-postflödesregel för att förhindra automatisk vidarebefordran av e-post till externa domäner. Mer information finns i [Mitigating Client External Forwarding Rules med Secure Score.](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) <p> Mer information: [E-postflödesregler (transportregler) i Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Aktivera modern autentisering**|Nej|Modern autentisering krävs för användning av multifaktorautentisering (MFA). MFA rekommenderas för att skydda åtkomsten till molnresurser, inklusive e-post. <p> Se följande avsnitt: <ul><li>[Aktivera eller inaktivera modern autentisering i Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype för företag – Online: Aktivera klientorganisationen för modern autentisering](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> Modern autentisering är aktiverad som standard för Office 2016-klienter, SharePoint Online och OneDrive för företag. <p> Mer information: [Hur modern autentisering fungerar för Office 2013- och Office 2016-klientprogram](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Konfigurera principer för delning för hela klientorganisationen i administrationscentret för SharePoint

Microsoft-rekommendationer för konfigurering av SharePoint-gruppwebbplatser på ökande skyddsnivå, med början från grundläggande skydd. Mer information finns i Principrekommendationer [för att skydda SharePoint-webbplatser och -filer.](sharepoint-file-access-policies.md)

SharePoint-gruppwebbplatser som konfigurerats på baslinjenivå tillåter delning av filer med externa användare genom att använda anonyma åtkomstlänkar. Den här metoden rekommenderas i stället för att skicka filer via e-post.

För att stödja målen för baslinjeskydd konfigurerar du delningsprinciper för hela klientorganisationen enligt rekommendationen här. Delningsinställningar för enskilda webbplatser kan vara mer restriktiva än den här klientorganisationens princip, men inte mer tillåtande.

****

|Område|Innehåller en standardprincip|Rekommendation|
|---|---|---|
|**Delning** (SharePoint Online och OneDrive för företag)|Ja|Extern delning är aktiverat som standard. De här inställningarna rekommenderas: <ul><li>Tillåt delning till autentiserade externa användare och med anonyma åtkomstlänkar (standardinställning).</li><li>Länkar för anonym åtkomst upphör att gälla så här många dagar. Ange ett tal om du vill, till exempel 30 dagar.</li><li>Standardlänktyp – välj Intern (endast personer i organisationen). Användare som vill dela med anonyma länkar måste välja det här alternativet på delningsmenyn.</li></ul> <p> Mer information: [Översikt över extern delning](/sharepoint/external-sharing-overview)|
|

Administrationscentret för SharePoint och administrationscentret för OneDrive för företag har samma inställningar. Inställningarna i båda administrationscentret gäller för båda.

## <a name="configure-settings-in-azure-active-directory"></a>Konfigurera inställningar i Azure Active Directory

Se till att besöka dessa två områden i Azure Active Directory för att slutföra konfigurationen för hela klientorganisationen för säkrare miljöer.

### <a name="configure-named-locations-under-conditional-access"></a>Konfigurera namngivna platser (under villkorsstyrd åtkomst)

Om din organisation har kontor med säker nätverksåtkomst lägger du till de betrodda IP-adressintervallen i Azure Active Directory som namngivna platser. Den här funktionen hjälper till att minska antalet rapporterade falska positiva resultat för inloggningsriskhändelser.

Mer information: [Namngivna platser i Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Blockera appar som inte stöder modern autentisering

Multifaktorautentisering kräver appar som stöder modern autentisering. Program som inte stöder modern autentisering kan inte blockeras med hjälp av villkorsstyrda åtkomstregler.

För säkra miljöer måste du inaktivera autentisering för program som inte stöder modern autentisering. Det kan du göra i Azure Active Directory med en kontroll som kommer snart.

Under tiden kan du använda någon av följande metoder för att uppnå detta för SharePoint Online och OneDrive för företag:

- Använda PowerShell, se [Blockera appar som inte använder modern autentisering (ADAL)](/mem/intune/protect/app-modern-authentication-block).

- Konfigurera detta i administrationscentret för SharePoint på sidan "enhetsåtkomst" – "Styr åtkomsten från program som inte använder modern autentisering". Välj Blockera.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Komma igång med Cloud App Security eller Office 365 Cloud App Security

Använd Office 365 Cloud App Security för att utvärdera risker, för att varna om misstänkt aktivitet och för att automatiskt vidta åtgärder. Kräver Office 365 E5-abonnemang.

Du kan också använda Microsoft Cloud App Security för att få bättre insyn även när åtkomst beviljas, omfattande kontroller och förbättrat skydd för alla dina molnprogram, inklusive Office 365.

Eftersom den här lösningen rekommenderar EMS E5-abonnemanget rekommenderar vi att du börjar med Cloud App Security så att du kan använda det med andra SaaS-program i din miljö. Börja med standardprinciper och inställningar.

Mer information:

- [Distribuera Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)

- [Mer information om Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [Vad är molnappsäkerhet?](/cloud-app-security/what-is-cloud-app-security)

![Instrumentpanelen i Cloud App Security](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Ytterligare resurser

De här artiklarna och guiderna innehåller ytterligare information för att skydda Microsoft 365-miljön:

- [Microsofts säkerhetsvägledning för politiska kampanjer,](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) ideella organisationer och andra Agile-organisationer (du kan använda dessa rekommendationer i alla miljöer, särskilt i miljöer som bara är molnbaserade)

- [Rekommenderade säkerhetsprinciper och konfigurationer för identiteter och enheter](microsoft-365-policies-configurations.md) (dessa rekommendationer inkluderar hjälp för AD FS-miljöer)