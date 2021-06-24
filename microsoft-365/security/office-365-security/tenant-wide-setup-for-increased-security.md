---
title: Konfigurera din Microsoft 365 för ökad säkerhet
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
description: I det här avsnittet får du hjälp med den rekommenderade konfigurationen för inställningar för hela klientorganisationen som påverkar säkerheten Microsoft 365 miljön.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b1bb3f9bf6507e41d8b927137a9ab9ea8803637c
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105530"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Konfigurera din Microsoft 365 för ökad säkerhet

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I det här avsnittet får du hjälp med den rekommenderade konfigurationen för inställningar för hela klientorganisationen som påverkar säkerheten Microsoft 365 miljön. Dina säkerhetsbehov kan kräva mer eller mindre säkerhet. Använd de här rekommendationerna som utgångspunkt.

## <a name="check-office-365-secure-score"></a>Kontrollera Office 365 Secure Score

Office 365 Secure Score analyserar organisationens säkerhet utifrån aktiviteter och säkerhetsinställningar samt tilldelar ett poäng. Börja med att anteckna det aktuella resultatet. Om du justerar vissa inställningar för hela klientorganisationen ökar poängen. Målet är inte att uppnå maxresultatet, utan att vara medveten om möjligheter att skydda din miljö som inte negativt påverkar användarnas produktivitet. Se [Microsoft Secure Score](../defender/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-defender-portal"></a>Anpassa principer för hothantering i Microsoft 365 Defender portalen

På Microsoft 365 Defender-portalen finns funktioner som skyddar din miljö. Den innehåller även rapporter och instrumentpaneler som du kan använda för att övervaka och vidta åtgärder. Vissa områden har standardprincipkonfigurationer. Vissa områden inkluderar inte standardprinciper eller regler. Besök de här principerna under **& för** samarbete \> **& regler** \> **Hotprinciper** för att anpassa inställningarna för hothantering för en säkrare miljö.

<br>

****

|Område|Standardprincip?|Rekommendation|
|---|---|---|
|**Skydd mot nätfiske**|Ja|Konfigurera standardprincipen för skydd mot nätfiske enligt beskrivningen här: Konfigurera inställningarna för skydd mot nätfiske i [EOP och Defender för Office 365](protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365). <p> Mer information: <ul><li>[Principer mot nätfiske i Microsoft 365](set-up-anti-phishing-policies.md)</li><li>[Rekommenderade inställningar för skydd mot nätfiske i Microsoft Defender för Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</li><li> [Imitationsinsikt](impersonation-insight.md)</li><li>[Falska intelligensinsikter i EOP](learn-about-spoof-intelligence.md)</li><li>[Hantera listan över tillåtna/blockerade klientorganisationen.](tenant-allow-block-list.md)</li></ul>|
|**Anti-Malware Engine**|Ja|Konfigurera standardprincipen för skadlig programvara enligt beskrivningen här: Konfigurera inställningarna för skydd [mot skadlig programvara i EOP.](protect-against-threats.md#part-1---anti-malware-protection-in-eop) <p> Mer information: <ul><li>[Skydd mot skadlig kod](anti-malware-protection.md)</li><li>[Rekommenderade principinställningar för skydd mot skadlig programvara](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)</li><li>[Konfigurera principer för skydd mot skadlig kod](configure-anti-malware-policies.md)</li></ul>|
|**Säkra bifogade filer i Defender för Office 365**|Nej|Konfigurera globala inställningar för att Valv bifogade filer och skapa en princip för Valv-bilagor enligt beskrivningen här: Konfigurera inställningarna för [Valv-bilagor](protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)i Microsoft Defender för Office 365. <p> Mer information: <ul><li>[Rekommenderade inställningar Valv för bifogade filer](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</li><li>[Valv Bifogade filer i Microsoft Defender för Office 365](safe-attachments.md)</li><li>[Konfigurera principer för Valv för bifogade filer](set-up-safe-attachments-policies.md)</li><li>[Säkra bilagor för SharePoint, OneDrive och Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Säkra dokument i Microsoft 365 E5](safe-docs.md)</li></ul>|
|**Valv Länkar i Microsoft Defender för Office 365**|Nej|Konfigurera globala inställningar för Valv länkar och skapa en princip för Valv-länkar enligt beskrivningen här: Konfigurera inställningarna [för Valv-länkar](protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)i Microsoft Defender för Office 365 . <p> Mer information: <ul><li>[Inställningar Valv Rekommenderade Valv länkar](recommended-settings-for-eop-and-office365.md#safe-links-settings)</li><li>[Konfigurera Valv länkar](set-up-safe-links-policies.md)</li><li>[Valv Länkar i Microsoft Defender för Office 365](safe-links.md)</li><li>[Konfigurera globala inställningar för Valv Länkar i Microsoft Defender för Office 365](configure-global-settings-for-safe-links.md)</li></ul>|
|**Skräppostskydd (e-postfiltrering)**|Ja|Konfigurera standardprincipen för skydd mot skräppost enligt beskrivningen här: Konfigurera inställningarna för skydd [mot skräppost i EOP](protect-against-threats.md#part-3---anti-spam-protection-in-eop) <p> Mer information: <ul><li>[Rekommenderade inställningar för skydd mot skräppost](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</li><li>[Skydd mot skräppost i EOP](anti-spam-protection.md)</li><li>[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)</li></ul>|
|***E-postautentisering***|Ja|E-postautentisering använder DNS-poster för att lägga till verifierbar information i e-postmeddelanden om meddelandekällan och avsändaren. Microsoft 365 e-postautentisering för sin standarddomän (onmicrosoft.com), men Microsoft 365-administratörer kan också konfigurera e-postautentisering för egna domäner. Tre autentiseringsmetoder används: <ul><li>Sender Policy Framework (eller SPF).</li><ul><li>Mer information om konfiguration [finns i Konfigurera SPF i Microsoft 365 för att förhindra förfalskning.](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</li></ul> <li>DKIM (DomainKeys Identified Mail).</li><ul><li>Se [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän.](use-dkim-to-validate-outbound-email.md)</li><li>När du har konfigurerat DKIM aktiverar du det på Microsoft 365 Defender portalen.</li></ul><li>DMARC (Domain-based Message Authentication, Reporting, and Conformance).</li><ul><li>För DMARC-konfiguration [Använder du DMARC för att verifiera e-Microsoft 365](use-dmarc-to-validate-email.md).</li></ul></ul>|
|

> [!NOTE]
> För distributioner av SPF som inte är standard, hybriddistributioner och felsökning: Hur [Microsoft 365 använder Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)för att förhindra förfalskning.

## <a name="view-dashboards-and-reports-in-the-microsoft-365-defender-portal"></a>Visa instrumentpaneler och rapporter i Microsoft 365 Defender portalen

Besök de här rapporterna och instrumentpanelerna om du vill veta mer om din miljö. Data i de här rapporterna blir rikare när organisationen använder Office 365 tjänster. För tillfället bör du känna till vad du kan övervaka och vidta åtgärder för.

<br>

****

|Instrumentpanelen|Beskrivning|
|---|---|
|Säkerhetsrapporter för e-post|De här rapporterna är tillgängliga i Exchange Online Protection. Mer information finns i Visa [säkerhetsrapporter för e-post i Microsoft 365 Defender portal](view-email-security-reports.md).|
|Defender för Office 365 rapporter|Rapporterna är endast tillgängliga i Defender för Office 365. Mer information finns i [Visa Defender för Office 365 i Microsoft 365 Defender portal.](view-reports-for-mdo.md)|
|Rapporter och insikter i e-postflöde|De här rapporterna och insikterna är tillgängliga Exchange administrationscenter (EAC). Mer information finns i [E-postflödesrapporter och](/exchange/monitoring/mail-flow-reports/mail-flow-reports) [E-postflödesinformation.](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|[Hotutforskaren (eller realtidsidentifieringar)](threat-explorer.md)|Om du undersöker eller upplever en attack mot din klientorganisation kan du använda Utforskaren (eller identifieringar i realtid) för att analysera hot. Utforskaren (och rapporten över identifieringar i realtid) visar antalet attacker över tid och du kan analysera dessa data med hjälp av hotfamiljer, attackersinfrastruktur med mera. Du kan också markera alla misstänkta e-postmeddelanden för listan Incidenter.|
|

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Konfigurera ytterligare Exchange Online inställningar för hela klientorganisationen

Här är några ytterligare inställningar som rekommenderas.

<br>

****

|Område|Rekommendation|
|---|---|
|**E-postflödesregler** (kallas även transportregler)|Lägg till en e-postflödesregel som skyddar mot utpressningstrojaner genom att blockera körbara filtyper Office filtyper som innehåller makron. Mer information finns i Använda [e-postflödesregler för att kontrollera bifogade filer i Exchange Online](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments). <p> Se följande avsnitt: <ul><li>[Skydda mot utpressningstrojaner](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Skydd mot skadlig programvara och utpressningstrojaner i Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Återställ från en utpressningstrojanattack i Office 365](recover-from-ransomware.md)</li></ul> <p> Skapa en e-postflödesregel för att förhindra automatisk vidarebefordran av e-post till externa domäner. Mer information finns i [Mitigating Client External Forwarding Rules med Secure Score.](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) <p> Mer information: [E-postflödesregler (transportregler) i Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Modern autentisering**|Modern autentisering krävs för användning av multifaktorautentisering (MFA). MFA rekommenderas för att skydda åtkomsten till molnresurser, inklusive e-post. <p> Se följande avsnitt: <ul><li>[Aktivera eller inaktivera modern autentisering i Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype för företag Online: Aktivera modern autentisering för klientorganisationen](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> Modern autentisering är aktiverad som standard för Office 2016-klienter, SharePoint Online och OneDrive för företag. <p> Mer information: [Hur modern autentisering fungerar för Office 2013- Office 2016-klientprogram](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Konfigurera principer för delning för hela klientorganisationen SharePoint administrationscenter

Microsoft-rekommendationer för SharePoint till gruppwebbplatser på ökande skyddsnivå, med början från grundläggande skydd. Mer information finns i [Principrekommendationer för att skydda SharePoint och filer.](sharepoint-file-access-policies.md)

SharePoint gruppwebbplatser som konfigurerats på baslinjenivån tillåter delning av filer med externa användare genom att använda anonyma åtkomstlänkar. Den här metoden rekommenderas i stället för att skicka filer via e-post.

För att stödja målen för baslinjeskydd konfigurerar du delningsprinciper för hela klientorganisationen enligt rekommendationen här. Delningsinställningar för enskilda webbplatser kan vara mer restriktiva än den här klientorganisationens princip, men inte mer tillåtande.

<br>

****

|Område|Innehåller en standardprincip|Rekommendation|
|---|---|---|
|**Delning** (SharePoint Online och OneDrive för företag)|Ja|Extern delning är aktiverat som standard. De här inställningarna rekommenderas: <ul><li>Tillåt delning till autentiserade externa användare och med anonyma åtkomstlänkar (standardinställning).</li><li>Länkar för anonym åtkomst upphör att gälla så här många dagar. Ange ett tal om du vill, till exempel 30 dagar.</li><li>Standardlänktyp – välj Intern (endast personer i organisationen). Användare som vill dela med anonyma länkar måste välja det här alternativet på delningsmenyn.</li></ul> <p> Mer information: [Översikt över extern delning](/sharepoint/external-sharing-overview)|
|

SharePoint administrationscenter och OneDrive för företag innehåller samma inställningar. Inställningarna i båda administrationscentret gäller för båda.

## <a name="configure-settings-in-azure-active-directory"></a>Konfigurera inställningar i Azure Active Directory

Se till att besöka dessa två områden i Azure Active Directory för att slutföra konfigurationen för hela klientorganisationen för säkrare miljöer.

### <a name="configure-named-locations-under-conditional-access"></a>Konfigurera namngivna platser (under villkorsstyrd åtkomst)

Om din organisation har kontor med säker nätverksåtkomst lägger du till de betrodda IP-adressintervallen i Azure Active Directory som namngivna platser. Den här funktionen hjälper till att minska antalet rapporterade falska positiva resultat för inloggningsriskhändelser.

Se: [Namngivna platser i Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Blockera appar som inte stöder modern autentisering

Multifaktorautentisering kräver appar som stöder modern autentisering. Program som inte stöder modern autentisering kan inte blockeras med hjälp av villkorsstyrda åtkomstregler.

För säkra miljöer måste du inaktivera autentisering för program som inte stöder modern autentisering. Du kan göra detta Azure Active Directory med en kontroll som kommer snart.

Under tiden kan du använda någon av följande metoder för att uppnå detta SharePoint Online och OneDrive för företag:

- Använda PowerShell, se [Blockera appar som inte använder modern autentisering (ADAL)](/mem/intune/protect/app-modern-authentication-block).
- Konfigurera detta i SharePoint på sidan "enhetsåtkomst" – "Styr åtkomsten från program som inte använder modern autentisering". Välj Blockera.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Komma igång med Cloud App Security eller Office 365 Cloud App Security

Använd Office 365 Cloud App Security för att utvärdera risker, för att varna om misstänkt aktivitet och för att automatiskt vidta åtgärder. Kräver Office 365 E5 plan.

Eller använd Microsoft Cloud App Security för att få bättre insyn även när åtkomst beviljas, omfattande kontroller och förbättrat skydd för alla dina molnprogram, inklusive Office 365.

Eftersom den här lösningen rekommenderar EMS E5-abonnemanget rekommenderar vi att du börjar med Cloud App Security så att du kan använda det med andra SaaS-program i din miljö. Börja med standardprinciper och inställningar.

Mer information:

- [Distribuera Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)
- [Mer information om Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [Vad är Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)

![Instrumentpanelen i Cloud App Security](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Ytterligare resurser

De här artiklarna och guiderna innehåller ytterligare information för att skydda din Microsoft 365 miljö:

- [Microsofts säkerhetsvägledning för politiska kampanjer,](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) ideella organisationer och andra Agile-organisationer (du kan använda dessa rekommendationer i alla miljöer, särskilt i miljöer som bara är molnbaserade)

- [Rekommenderade säkerhetsprinciper och konfigurationer för identiteter och enheter](microsoft-365-policies-configurations.md) (dessa rekommendationer inkluderar hjälp för AD FS-miljöer)
