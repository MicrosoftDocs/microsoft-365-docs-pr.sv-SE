---
title: Konfigurera Microsoft 365-klient organisationen för ökad säkerhet
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: I det här avsnittet får du hjälp med rekommenderad konfiguration för klient organisationens inställningar som påverkar säkerheten för din Microsoft 365-miljö.
ms.openlocfilehash: 9e36c85b74a237a8b14904839aad55ac676dcaf4
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326931"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Konfigurera Microsoft 365-klient organisationen för ökad säkerhet

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I det här avsnittet får du hjälp med rekommenderad konfiguration för klient organisationens inställningar som påverkar säkerheten för din Microsoft 365-miljö. Dina säkerhets behov kan kräva mer eller mindre säkerhet. Använd dessa rekommendationer som utgångs punkt.

## <a name="check-office-365-secure-score"></a>Kontrol lera säkert Poäng för Office 365

Med säkra Poäng för Office 365 analyseras organisationens säkerhet baserat på dina vanliga aktiviteter och säkerhets inställningar och du får en poäng. Börja med att anteckna ditt aktuella Poäng värde. Om du justerar vissa inställningar för hela klient organisationen ökar poängen. Målet är inte att få det högsta antalet poäng, men att vara medveten om möjligheter att skydda din miljö som inte negativt påverkar användarnas produktivitet. Se [Microsofts säkra Poäng](../mtp/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Finjustera principer för Threat Management i säkerhets Center för Microsoft 365

Säkerhets Center för Microsoft 365 inkluderar funktioner som skyddar din miljö. Det inkluderar också rapporter och instrument paneler som du kan använda för att övervaka och vidta åtgärder. Vissa områden levereras med standardkonfigurationer för principer. Vissa områden inkluderar inte standard principer eller regler. Besök dessa principer under Threat Management för att justera Threat Management inställningar för en säkrare miljö.

****

|Under|Innehåller en standard princip|Rekommendation|
|---|---|---|
|**Anti-nätfiske**|Ja|Om du har en egen domän konfigurerar du standard policyn för nätfiske för att skydda e-postkonton för dina mest värdefulla användare, till exempel VD: n och för att skydda din domän. Granska [anti-nätfiske-principer i office 365](set-up-anti-phishing-policies.md) och se [Konfigurera principer för nätfiske i EOP](configure-anti-phishing-policies-eop.md) eller [Konfigurera principer för ATP-nätfiske i Office 365](configure-atp-anti-phishing-policies.md).|
|**Skydd mot skadlig program vara**|Ja| Redigera standard policyn: <br/> &ensp;&ensp;* Filtret vanliga bilagor – Välj på <br/><br/> Du kan också skapa anpassade filter principer för skadlig kod och tillämpa dem på specifika användare, grupper eller domäner i organisationen. <br/><br/> Mer information: <br/> &ensp;&ensp;* [Skydd mot skadlig program vara](anti-malware-protection.md) <br/> &ensp;&ensp;* [Konfigurera principer för mot skadlig program vara](configure-anti-malware-policies.md)|
|**Säkra bifogade filer i Office 365 ATP**|Nej|På huvud sidan för säkra bifogade filer klickar du på **globala inställningar** och aktiverar den här inställningen: <br/> &ensp;&ensp;**Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** <br/><br/> Skapa en princip för bifogade filer med följande inställningar: <br/> &ensp;&ensp;* **Blockera**: Välj **block** som ett okänt svar på skadlig program vara. <br/> &ensp;&ensp;* **Aktivera omdirigera**: Markera den här rutan och ange en e-postadress, till exempel ett administratörs-eller karantän konto. <br/> &ensp;&ensp;* **Tillämpa ovanstående markering om genomsökning av skadlig kod för bifogade filer eller fel inträffar**: Markera den här rutan. <br/> &ensp;&ensp;* **Tillkopplat**: **mottagar domänen** \> väljer din domän. <br/><br/> Mer information: [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) och [Konfigurera principer för säkra bifogade filer](set-up-atp-safe-attachments-policies.md)|
|**Säkra länkar i Office 365 ATP**|Ja|Klicka på **globala inställningar**på huvud sidan för säkra länkar: <br/> &ensp;&ensp;* **Använda säkra länkar i: Office 365-program**: kontrol lera att den här inställningen är aktive rad. <br/> &ensp;&ensp;* **Spåra inte när användare klickar på säkra länkar**: inaktivera den här inställningen för att spåra användare.<br/><br/>Skapa en princip för säkra länkar med de här inställningarna: <br/> &ensp;&ensp;* **Välj åtgärd för okända URL-adresser i meddelanden**: kontrol lera att den här inställningen är **på**. <br/> &ensp;&ensp;* **Välj åtgärd för okända eller potentiellt skadliga URL-adresser i Microsoft Teams**: kontrol lera att den här inställningen är **på**. <br/> &ensp;&ensp;* **Använd URL-genomsökning i real tid för att få misstänkta länkar och länkar som pekar på filer**: Markera den här rutan. <br/> &ensp;&ensp;&ensp;&ensp;*  **Vänta på att URL-genomsökningen ska slutföras innan meddelandet levereras**: Markera den här rutan. <br/> &ensp;&ensp;* **Använd Safe Links för e-postmeddelanden som skickas inom organisationen**: Markera den här rutan. <br/> &ensp;&ensp;* **Tillåt inte att användare klickar genom till ursprunglig URL**: Markera den här rutan. <br/> &ensp;&ensp;* **Tillkopplat**: **mottagar domänen** \> väljer din domän. <br/><br/> Mer information: [Konfigurera principer för säkra länkar](set-up-atp-safe-links-policies.md).|
|**Skydd mot skräp post (e-postfilter)**|Ja| Vad du kan titta efter: <br/> &ensp;&ensp;* För mycket skräp post – Välj de anpassade inställningarna och redigera standard princip för skräp post filter. <br/> &ensp;&ensp;* Spoof intelligens – granska avsändare som har falska din domän. Blockera eller tillåta dessa avsändare. <br/><br/>Mer information: [skräp post skydd i Microsoft 365](anti-spam-protection.md).|
|***E-postauktorisering***|Ja|E-postidentifiering använder DNS (Domain Name System) för att lägga till verifierbar information i e-postmeddelanden om avsändaren av ett e-postmeddelande. I Microsoft 365 konfigureras e-postautentisering för standard domänen (onmicrosoft.com), men Microsoft 365-administratörer kan också använda e-postautentisering för egna domäner. Tre autentiseringsmetoder används: <br/><br/> &ensp;&ensp;* Avsändarens princip ramverk (eller SPF).<br/>&ensp;&ensp;&ensp;&ensp;-För konfiguration läser [du konfigurera SPF i Microsoft 365 för att förhindra förfalskningar](set-up-spf-in-office-365-to-help-prevent-spoofing.md). <br/> &ensp;&ensp;* DomainKeys identifieras (DKIM). <br/> &ensp;&ensp;&ensp;&ensp;-Se [använda DKIM för att verifiera utgående e-post som skickas från din egen domän](use-dkim-to-validate-outbound-email.md). <br/>&ensp;&ensp;&ensp;&ensp;-När du har konfigurerat DKIM kan du aktivera det i säkerhets Center.<br/> &ensp;&ensp;* Domänbaserad meddelandeautentisering, rapportering och omslutande (DMARC). <br/> &ensp;&ensp;&ensp;&ensp;-För DMARC Setup [Använd DMARC för att verifiera e-post i Microsoft 365](use-dmarc-to-validate-email.md).|
|

> [!NOTE]
> För icke-standardiserade distributioner av SPF, hybrid distributioner och fel sökning: [hur Microsoft 365 utnyttjar avsändarens princip ramverk (SPF) för att förhindra förfalskning](how-office-365-uses-spf-to-prevent-spoofing.md).

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>Visa instrument paneler och rapporter i Center för säkerhet och efterlevnad

Besök dessa rapporter och instrument paneler för att få mer information om miljön. Informationen i dessa rapporter blir bättre när din organisation använder Office 365-tjänster. Nu är det bekant med vad du kan övervaka och vidta åtgärder för. Mer information finns i: [rapporter i Microsoft 365 Security och Compliance Centers](../../compliance/reports-in-security-and-compliance.md).

****

|Instrumentpanelen|Beskrivning|
|---|---|
|[Instrument panel för Threat Management](security-dashboard.md)|I avsnittet **Threat Management** i säkerhets Center använder du den här instrument panelen för att Visa hot som redan har hanterats, och som ett praktiskt verktyg för att rapportera till besluts fattarna om hot undersökningen och svars funktionerna för att skydda ditt företag.|
|[Hotutforskaren (eller realtidsidentifieringar)](threat-explorer.md)|Det finns också i avsnittet **Threat Management** i säkerhets Center. Om du undersöker eller drabbas av en attack mot klient organisationen kan du använda Explorer (eller identifiering i real tid) för att analysera hot. Utforskaren (och rapporten om identifiering av real tid) visar hur mycket du har attacker med tid, och du kan analysera dessa data via hot familjer, angrepps infrastruktur och mycket mer. Du kan också markera misstänkt e-post för listan incidenter.|
|Rapporter – instrument panel|I avsnittet **rapporter** i säkerhets Center kan du läsa gransknings rapporter för SharePoint Online-och Exchange Online-organisationer. Du kan också komma åt Azure AD-användares inloggnings rapporter, användar aktivitets rapporter och Azure AD audit log från sidan **Visa rapporter** .|
|

![Instrument panel för säkerhets Center](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Konfigurera ytterligare Exchange Online-inställningar för klient organisationen

Många av kontrollerna för säkerhet och skydd i administrations centret för Exchange finns också i säkerhets Center. Du behöver inte konfigurera dessa på båda platserna. Här är några ytterligare inställningar som rekommenderas.

****

|Under|Innehåller en standard princip|Rekommendation|
|---|---|---|
|**E-postflöde** (regler för e-postflöde, kallas även transport regler)|Nej|Lägga till en regel för e-postflöde för att skydda mot utpressnings tro Jan program vara genom att blockera filtyper och Office-filtyper som innehåller makron Mer information finns i [använda regler för e-postflöde för att inspektera bifogade filer i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments). <br/><br/> Se följande avsnitt: <br/>* [Skydda mot utpressnings tro Jan](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)<br/>* [Skydd mot skadlig program vara och utpressnings Jan attack i Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-malware-and-ransomware-protection) <br/>* [Återställ från en utpressnings tro Jan attack i Office 365](recover-from-ransomware.md) <br/><br/> Skapa en regel för e-postflöde för att förhindra vidarebefordran av e-post till externa domäner automatiskt. Mer information finns i [begränsa regler för extern vidarebefordring med klienter med säkra Poäng](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score). <br/><br/> Mer information: [regler för e-postflöde (transport regler) i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Aktivera modern verifikation**|Nej|Modern verifiering är en förutsättning för att använda multifaktorautentisering. MFA rekommenderas för att skydda åtkomst till moln resurser, inklusive e-post. <br/><br/> Se följande avsnitt: <br/>* [Aktivera eller inaktivera modern lösenordsautentisering i Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) <br/>* [Skype för företag – online: aktivera din klient organisation för modern](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/><br/> Modern autentisering är aktive rad som standard för Office 2016-klienter, SharePoint Online och OneDrive för företag. <br/><br/> Mer information: [så här fungerar den moderna autentiseringsprocessen för office 2013-och office 2016-klient program](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Konfigurera delnings principer för hela klient organisationen i administrations centret för SharePoint

Microsoft-rekommendationer för konfiguration av SharePoint-gruppwebbplatser med ökande skydds nivåer, med start från grundläggande skydd. Mer information finns i [säkra SharePoint Online-webbplatser och-filer](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files)

SharePoint-gruppwebbplatser som har kon figurer ATS på bas nivå kan dela filer med externa användare med länkar för anonym åtkomst. Den här metoden rekommenderas istället för att skicka filer via e-post.

För att stödja målen för baseline-skydd ska du konfigurera delnings principer för hela klient organisationen enligt rekommendationer här. Delnings inställningar för enskilda webbplatser kan vara mer restriktiva än den här klient organisations principen, men inte mer tillåta.

****

|Under|Innehåller en standard princip|Rekommendation|
|---|---|---|
|**Delning** (SharePoint Online och OneDrive för företag)|Ja|Extern delning är aktiverat som standard. De här inställningarna rekommenderas: <br/>* Tillåt delning till autentiserade externa användare och Använd anonyma åtkomst länkar (standardinställningen). <br/> * Anonyma åtkomst länkar upphör om dagar. Ange ett nummer, om det behövs, till exempel 30 dagar. <br/>* Standard länktyp – Välj intern (endast personer i organisationen). Användare som vill dela med anonyma länkar måste välja det här alternativet från menyn delning. <br/><br/> Mer information: [Översikt över extern delning](https://docs.microsoft.com/sharepoint/external-sharing-overview)|
|

Administrations centret för SharePoint administrations Center och OneDrive för företag innehåller samma inställningar. Inställningarna i administrations centret gäller båda.

## <a name="configure-settings-in-azure-active-directory"></a>Konfigurera inställningar i Azure Active Directory

Se till att besöka dessa två områden i Azure Active Directory för att slutföra konfigurationen för hela klient organisationen för säkrare miljö.

### <a name="configure-named-locations-under-conditional-access"></a>Konfigurera namngivna platser (under villkorsstyrd åtkomst)

Om din organisation innehåller kontor med säker nätverks åtkomst lägger du till de betrodda IP-adressintervallet i Azure Active Directory som namngivna platser. Med den här funktionen kan du minska antalet rapporterade falsk identifierings händelser för inloggnings risker.

Se: [namngivna platser i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Blockera appar som inte stöder modern lösenordsautentisering

Multifaktorautentisering kräver appar som stöder modern lösenordsautentisering. Appar som inte stöder modern lösenordsautentisering kan inte blockeras med hjälp av regler för villkorlig åtkomst.

För säkra miljöer bör du se till att inaktivera inaktive ring av program som inte stöder modern. Du kan göra det i Azure Active Directory med en kontroll som kommer snart.

Under tiden kan du använda någon av följande metoder för att åstadkomma detta för SharePoint Online och OneDrive för företag:

- Använd PowerShell, se [blockera program som inte använder modern (ADAL)](https://docs.microsoft.com/mem/intune/protect/app-modern-authentication-block).

- Konfigurera det här i administrations centret för SharePoint på sidan "enhets åtkomst" – styr åtkomst från program som inte använder modern. Välj blockera.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Komma igång med Cloud App Security eller Office 365 Cloud App Security

Använd Office 365 Cloud App Security för att utvärdera riskerna, för att varna för misstänkt aktivitet, och för att automatiskt vidta åtgärder. Kräver Office 365 E5-abonnemang.

Du kan också använda säkerhets inställningar i Microsoft Cloud App för att få djupare insyn även efter åtkomst till, omfattande kontroller och förbättrat skydd för alla dina moln tillämpningar, inklusive Office 365.

Eftersom den här lösningen rekommenderar EMS-abonnemanget för SaaS rekommenderar vi att du börjar med att skydda Cloud app så att du kan använda det med andra-program i din miljö. Börja med standard principer och inställningar.

Mer information:

- [Distribuera Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [Mer information om Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [Vad är Cloud App-säkerhet?](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

![Instrumentpanelen i Cloud App Security](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Ytterligare resurser

De här artiklarna och guiderna ger ytterligare information om hur du skyddar din Microsoft 365-miljö:

- [Microsofts säkerhets guider för politisk kampanjer, icke-vinster och andra Agile-organisationer](https://docs.microsoft.com/microsoft-365/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o) (du kan använda den här rekommendationen i alla miljöer, särskilt molnbaserade miljöer)

- [Rekommenderade säkerhets principer och konfigurationer för identiteter och enheter](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations) (dessa rekommendationer inkluderar hjälp för AD FS-miljöer)
