---
title: Konfigurera Office 365-klientorganisationen för ökad säkerhet
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
description: Väg dig igenom rekommenderad konfiguration för klientomfattande inställningar som påverkar säkerheten i office 365-miljön. Dina säkerhetsbehov kan kräva mer eller mindre säkerhet. Använd dessa rekommendationer som utgångspunkt.
ms.openlocfilehash: 56b2dad90b15c1d084edaa4477301e8ac4d4442d
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529019"
---
# <a name="configure-your-office-365-tenant-for-increased-security"></a>Konfigurera Office 365-klientorganisationen för ökad säkerhet

I det här avsnittet får du hjälp med rekommenderad konfiguration för klientomfattande inställningar som påverkar säkerheten i Office 365-miljön. Dina säkerhetsbehov kan kräva mer eller mindre säkerhet. Använd dessa rekommendationer som utgångspunkt.

## <a name="check-office-365-secure-score"></a>Kontrollera säker poäng för Office 365

Office 365 Secure Score analyserar office 365-organisationens säkerhet baserat på dina vanliga aktiviteter och säkerhetsinställningar och tilldelar en poäng. Börja med att notera din nuvarande poäng. Om du justerar vissa inställningar för hela klienten ökar dina poäng. Målet är inte att uppnå maxpoäng, utan att vara medveten om möjligheter att skydda din miljö som inte negativt påverkar produktiviteten för dina användare. Se [Microsoft Secure Score](../mtp/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Justera principer för hothantering i Microsoft 365-säkerhetscentret

Microsoft 365-säkerhetscentret innehåller funktioner som skyddar din miljö. Den innehåller också rapporter och instrumentpaneler som du kan använda för att övervaka och vidta åtgärder. Vissa områden levereras med standardprincipkonfigurationer. Vissa områden innehåller inte standardprinciper eller standardregler. Besök dessa principer under hothantering för att justera hothanteringsinställningar för en säkrare miljö.

||||
|---|---|---|
|**Området**|**Innehåller en standardprincip**|**Rekommendation**|
|**Anti-phishing**|Ja|Om du har en anpassad domän konfigurerar du standardpolicyn mot nätfiske för att skydda e-postkonton för dina mest värdefulla användare, till exempel din VD, och för att skydda din domän. Granska [principer för nätfiske mot nätfiske i Office 365](set-up-anti-phishing-policies.md) och se [Konfigurera standardprincipen mot nätfiske i EOP](configure-anti-phishing-policies-eop.md) eller [Konfigurera ATP-principer för phishing i Office 365](configure-atp-anti-phishing-policies.md).|
|**Anti-Malware Motor**|Ja| Redigera standardprincipen: <br/> &ensp;&ensp;* Filter för vanliga typer av bifogade filer – Välj på <br/><br/> Du kan också skapa anpassade filterprinciper för skadlig kod och tillämpa dem på angivna användare, grupper eller domäner i organisationen. <br/><br/> Mer information: <br/> &ensp;&ensp;* [Skydd mot skadlig kod](anti-malware-protection.md) <br/> &ensp;&ensp;* [Konfigurera policyer mot skadlig kod](configure-anti-malware-policies.md)|
|**ATP säkra bilagor**|Nej| Skydda filer i SharePoint, OneDrive och Microsoft Teams på huvudsidan för säkra bifogade filer genom att markera den här rutan: <br/> &ensp;&ensp;* Aktivera ATP för SharePoint, OneDrive och Microsoft Teams <br/><br/> Lägg till en ny princip för säker bifogade filer med följande inställningar: <br/> &ensp;&ensp;* Blockera - Blockera nuvarande och framtida e-post och bilagor med upptäckt skadlig kod (välj det här alternativet) <br/> &ensp;&ensp;* Aktivera omdirigering – (Markera den här rutan och ange en e-postadress, till exempel ett administratörs- eller karantänkonto) <br/> &ensp;&ensp;* Använd ovanstående val om malware skanning för bilagor time out eller fel inträffar (markera den här rutan) <br/> &ensp;&ensp;* Tillämpad på - Mottagaren domänen är (välj din domän) <br/><br/>Mer information: [Konfigurera principer för betrodda bilagor i Office 365](set-up-atp-safe-attachments-policies.md)|
|**ATP säkra länkar**|Ja| Lägg till den här inställningen i standardprincipen för hela organisationen: <br/> &ensp;&ensp;* Använd säkra länkar i: Office 365 ProPlus, Office för iOS och Android (välj det här alternativet). <br/><br/>Rekommenderad princip för specifika mottagare: <br/> &ensp;&ensp;* Webbadresser kommer att skrivas om och kontrolleras mot en lista med kända skadliga länkar när användaren klickar på länken (välj det här alternativet). <br/> &ensp;&ensp;* Använd säkra bilagor för att skanna nedladdningsbart innehåll (markera den här rutan). <br/> &ensp;&ensp;* Tillämpad på - Mottagaren domänen är (välj din domän). <br/><br/> Mer information: [Safe Links för Office 365 ATP](atp-safe-links.md).|
|**Anti-Spam (E-postfiltrering)**|Ja| Vad du ska titta efter: <br/> &ensp;&ensp;* För mycket spam - Välj anpassade inställningar och redigera standard spam filter politik. <br/> &ensp;&ensp;* Spoof intelligens - Granska avsändare som förfalskar din domän. Blockera eller tillåt dessa avsändare. <br/><br/>Mer information: [Skydd mot skräppost i Office 365.](anti-spam-protection.md)|
|***Autentisering av e-post***|Ja|E-postautentisering använder ett DNS (Domain Name System) för att lägga till verifierbar information i e-postmeddelanden om avsändaren av ett e-postmeddelande. Office 365 konfigurerar e-postautentisering för standarddomänen (onmicrosoft.com), men Office 365-administratörer kan också använda e-postautentisering för anpassade domäner. Tre autentiseringsmetoder används: <br/><br/> &ensp;&ensp;* Avsändare policyram (eller SPF).<br/>&ensp;&ensp;&ensp;&ensp;- För installation finns [i Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md). <br/> &ensp;&ensp;* DomainKeys Identifierade Mail (DKIM). <br/> &ensp;&ensp;&ensp;&ensp;- Se [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän i Office 365](use-dkim-to-validate-outbound-email.md). <br/>&ensp;&ensp;&ensp;&ensp;- När du har konfigurerat DKIM aktiverar du det i säkerhetscentret.<br/> &ensp;&ensp;* Domänbaserad meddelandeautentisering, rapportering och överensstämmelse (DMARC). <br/> &ensp;&ensp;&ensp;&ensp;- För DMARC-konfiguration [Använd DMARC för att validera e-post i Office 365](use-dmarc-to-validate-email.md).|
|

> [!NOTE]
> För icke-standarddistributioner av SPF, hybriddistributioner och felsökning: [Så här använder Office 365 SPF (Sender Policy Framework) för att förhindra förfalskning](how-office-365-uses-spf-to-prevent-spoofing.md).

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>Visa instrumentpaneler och rapporter i säkerhets- och efterlevnadscentren

Besök dessa rapporter och instrumentpaneler om du vill veta mer om miljöns hälsa. Data i dessa rapporter blir rikare när din organisation använder Office 365-tjänster. För nu, vara bekant med vad du kan övervaka och vidta åtgärder på. Mer information finns i : [Rapporter i säkerhets- och efterlevnadscentren för Microsoft 365](../../compliance/reports-in-security-and-compliance.md).

|||
|---|---|
|**Instrumentpanelen**|**Beskrivning**|
|[Instrumentpanel för hothantering](security-dashboard.md)|I avsnittet **Hothantering** i säkerhetscentret använder du den här instrumentpanelen för att se hot som redan har hanterats och som ett praktiskt verktyg för att rapportera ut till beslutsfattare för företag om vilka hotutrednings- och svarsfunktioner som redan har gjorts för att skydda ditt företag.|
|[Hotutforskaren (eller realtidsidentifieringar)](threat-explorer.md)|Detta finns också i avsnittet **Hothantering** i säkerhetscentret. Om du undersöker eller upplever en attack mot din Office 365-klient kan du använda Explorer (eller realtidsidentifieringar) för att analysera hot. Explorer (och realtidsidentifieringsrapporten) visar mängden attacker över tid och du kan analysera dessa data efter hotfamiljer, angripares infrastruktur med mera. Du kan också markera misstänkt e-post för incidentlistan.|
|Rapporter – Instrumentpanel|I avsnittet **Rapporter i** säkerhetscentret visar du granskningsrapporter för dina SharePoint Online- och Exchange Online-organisationer. Du kan också komma åt Azure Active Directory (Azure AD) användarloggningsrapporter, användaraktivitetsrapporter och Azure AD-granskningsloggen från sidan **Visa rapporter.**|
|

![Instrumentpanel för säkerhetscenter](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Konfigurera ytterligare inställningar för Exchange Online för hela klienten

Många av kontrollerna för säkerhet och skydd i administrationscentret för Exchange ingår också i säkerhetscentret. Du behöver inte konfigurera dessa på båda ställena. Här är några ytterligare inställningar som rekommenderas.

||||
|---|---|---|
|**Området**|**Innehåller en standardprincip**|**Rekommendation**|
|**E-postflöde** (regler för e-postflöde, även kallade transportregler)|Nej|Lägg till en regel för e-postflöde för att skydda mot ransomware genom att blockera körbara filtyper och Office-filtyper som innehåller makron. Mer information finns i [Använda regler för e-postflöde för att granska bifogade filer i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments). <br/><br/> Se följande avsnitt: <br/>* [Skydda mot ransomware](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data?view=o365-worldwide#ransomware)<br/>* [Skydd mot skadlig programvara och ransomware i Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-malware-and-ransomware-protection) <br/>* [Återställ från en ransomware-attack i Office 365](recover-from-ransomware.md) <br/><br/> Skapa en regel för e-postflöde för att förhindra automatisk vidarebefordran av e-post till externa domäner. Mer information finns i [Förmildrande regler](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)för extern vidarebefordran av klienter med säker poäng . <br/><br/> Mer information: [Regler för e-postflöde (transportregler) i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Aktivera modern autentisering**|Nej|Modern autentisering i Office 365 är en förutsättning för att använda MFA (Multifaktor authentication). MFA rekommenderas för att skydda åtkomsten till molnresurser, inklusive e-post. <br/><br/> Se följande avsnitt: <br/>* [Aktivera eller inaktivera modern autentisering i Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) <br/>* [Skype för företag – Online: Aktivera din klient för modern autentisering](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/><br/> Modern autentisering är aktiverad som standard för Office 2016-klienter, SharePoint Online och OneDrive för företag. <br/><br/> Mer information: [Så här fungerar modern autentisering för Office 2013- och Office 2016-klientappar](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Konfigurera delningsprinciper för hela klienten i Administrationscentret för SharePoint

Microsofts rekommendationer för att konfigurera SharePoint-gruppwebbplatser på ökande skyddsnivåer, med början i baslinjeskyddet. Mer information finns i [Webbplatser och filer på Säker SharePoint Online](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files)

SharePoint-gruppwebbplatser som konfigurerats på baslinjenivå tillåter delning av filer med externa användare med hjälp av anonyma åtkomstlänkar. Den här metoden rekommenderas i stället för att skicka filer via e-post.

Konfigurera klientomfattande delningsprinciper som rekommenderas här om du vill stödja målen för baslinjeskydd. Delningsinställningar för enskilda webbplatser kan vara mer restriktiva än den här klientomfattande principen, men inte mer tillåtande.

||||
|---|---|---|
|**Området**|**Innehåller en standardprincip**|**Rekommendation**|
|**Delning** (SharePoint Online och OneDrive för företag)|Ja|Extern delning är aktiverat som standard. Dessa inställningar rekommenderas: <br/>* Tillåt delning till autentiserade externa användare och använda anonyma åtkomstlänkar (standardinställning). <br/> * Anonym åtkomst länkar löper ut i dessa många dagar. Ange ett tal, om så önskas, till exempel 30 dagar. <br/>* Standardlänktyp – välj Internt (endast personer i organisationen). Användare som vill dela med anonyma länkar måste välja det här alternativet på delningsmenyn. <br/><br/> Mer information: [Översikt över extern delning](https://docs.microsoft.com/sharepoint/external-sharing-overview)|
|

Administrationscentret för SharePoint och administrationscentret för OneDrive för företag innehåller samma inställningar. Inställningarna i båda administrationscentret gäller båda.

## <a name="configure-settings-in-azure-active-directory"></a>Konfigurera inställningar i Azure Active Directory

Var noga med att besöka dessa två områden i Azure Active Directory för att slutföra klientomfattande inställningar för säkrare miljöer.

### <a name="configure-named-locations-under-conditional-access"></a>Konfigurera namngivna platser (under villkorlig åtkomst)

Om din organisation innehåller kontor med säker nätverksåtkomst lägger du till de betrodda IP-adressintervallen i Azure Active Directory som namngivna platser. Den här funktionen bidrar till att minska antalet rapporterade falska positiva identifieringar för inloggningsriskhändelser.

Se: [Namngivna platser i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Blockera appar som inte stöder modern autentisering

Multifaktorautentisering kräver appar som stöder modern autentisering. Appar som inte stöder modern autentisering kan inte blockeras med hjälp av regler för villkorlig åtkomst.

För säkra miljöer, se till att inaktivera autentisering för appar som inte stöder modern autentisering. Du kan göra detta i Azure Active Directory med en kontroll som kommer snart.

Under tiden kan du använda någon av följande metoder för att åstadkomma detta för SharePoint Online och OneDrive för företag:

- Använd PowerShell, se [Blockera appar som inte använder modern autentisering](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication).

- Konfigurera detta i Administrationscentret för SharePoint på sidan "Enhetsåtkomst" – "Kontrollera åtkomst från appar som inte använder modern autentisering". Välj Blockera.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Komma igång med Cloud App Security eller Office 365 Cloud App Security

Använd Office 365 Cloud App Security för att utvärdera risker, för att varna för misstänkt aktivitet och för att automatiskt vidta åtgärder. Kräver Office 365 E5-abonnemang.

Du kan också använda Microsoft Cloud App Security för att få djupare synlighet även efter att åtkomst har beviljats, omfattande kontroller och förbättrat skydd för alla molnprogram, inklusive Office 365.

Eftersom den här lösningen rekommenderar EMS E5-abonnemanget rekommenderar vi att du börjar med Cloud App Security så att du kan använda detta med andra SaaS-program i din miljö. Börja med standardprinciper och inställningar.

Mer information:

- [Distribuera Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [Mer information om Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [Vad är Cloud App Security?](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

![Instrumentpanelen i Cloud App Security](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Ytterligare resurser

De här artiklarna och guiderna innehåller ytterligare beskrivande information för att skydda din Office 365-miljö:

- [Microsofts säkerhetsvägledning för politiska kampanjer, ideella organisationer och andra agila organisationer](https://docs.microsoft.com/microsoft-365/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o) (du kan använda den här rekommendationen i alla miljöer, särskilt molnmiljöer)

- [Rekommenderade säkerhetsprinciper och konfigurationer för identiteter och enheter](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations) (dessa rekommendationer inkluderar hjälp för AD FS-miljöer)
