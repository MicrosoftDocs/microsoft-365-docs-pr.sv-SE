---
title: Skydda SharePoint Online-webbplatser och filer
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
- SPO_Content
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: 'Sammanfattning: Konfigurationsrekommendationer för att skydda filer i SharePoint Online och Office 365.'
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 542cf1c899b0eee21b458cd8e9dd5fb8363cf1e9
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806040"
---
# <a name="secure-sharepoint-online-sites-and-files"></a>Skydda SharePoint Online-webbplatser och filer

I den här artikeln får du rekommendationer för att konfigurera SharePoint-gruppwebbplatser och filskydd som balanserar säkerhet med smidigt samarbete. I den här artikeln definieras fyra olika konfigurationer, och först ut är en offentlig webbplats i din organisation med de delningsprinciper som är mest öppna. Varje ytterligare konfiguration representerar en meningsfull upptrappning av skyddet, men möjligheten att komma åt och samarbeta med resurser är begränsad till den relevanta uppsättningen medlemmar. Använd de här rekommendationerna som utgångspunkt och justera konfigurationerna efter behoven i din organisation.

Konfigurationerna i den här artikeln överensstämmer med Microsofts rekommendationer för tre skyddsnivåer för data, identiteter och enheter:

- Grundskydd

- Känsligt skydd

- Strikt konfidentiellt skydd

Mer information om nivåerna och de funktioner som rekommenderas för varje nivå finns i följande resurser.

- [Identitets- och enhetsskydd för Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#identity-and-device-protection-for-office-365)

- [Lösningar för filskydd i Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#file-protection-solutions-in-office-365)

## <a name="capability-overview"></a>Översikt över funktioner

Rekommendationer för SharePoint Online-gruppwebbplatser berör en rad olika Microsoft 365-funktioner. Följande illustration visar de rekommenderade konfigurationerna för fyra SharePoint Online-gruppwebbplatser.

![Rekommenderad konfiguration för SharePoint-webbplatser](../../media/SharePoint-site-configurations.png)

Som framgår av följande:

- Grundläggande skydd omfattar två alternativ för SharePoint Online-gruppwebbplatser – en offentlig webbplats och en privat webbplats. Offentliga webbplatser kan upptäckas och användas av alla i organisationen. Privata webbplatser kan bara identifieras och användas av webbplatsens medlemmar. Båda dessa webbplatskonfigurationer tillåter delning utanför gruppen.

- Webbplatser för känsligt och strikt konfidentiellt skydd är privata webbplatser med åtkomst begränsad endast till medlemmar i vissa grupper.

- [Kvarhållningsetiketter](../../compliance/labels.md) ger ett sätt att klassificera filer inom webbplatserna. Alla SharePoint-gruppwebbplatser är konfigurerade för att automatiskt etikettera filer i dokumentbibliotek med en standardetikett för bevarande för webbplatsen. Etiketterna i det här exemplet motsvarar de fyra webbplatskonfigurationerna och är Intern offentlig, Privat, Känslig och Strikt konfidentiell. Användare kan ändra etiketterna, men den här konfigurationen ser till att alla filer får en standardetikett.

- Principer för [dataförlustskydd](../../compliance/data-loss-prevention-policies.md) (DLP) är konfigurerade för kvarhållningsetiketterna Känslig och Strikt konfidentiell för att antingen varna eller förhindra användare när de försöker skicka sådana typer av filer utanför organisationen.

- Om det behövs kan du använda [känslighetsetiketter](../../compliance/sensitivity-labels.md) för att skydda mycket konfidentiella filer med kryptering och behörigheter. För Azure Information Protection-kunder kan du använda märkning för Azure Information Protection i Microsoft 365 Efterlevnadscenter, och om du väljer att utföra ytterligare eller avancerad konfiguration synkroniseras dina etiketter med Azure-portalen. Märkning för Azure Information Protection och Office 365-känslighetsetiketter är helt kompatibla med varandra. Det innebär att om du till exempel har innehåll som tilldelats av Azure Information Protection, behöver du inte ändra klassificering eller etikett för innehållet. Alla kunder behöver inte den här skyddsnivån.

## <a name="tenant-wide-settings-for-sharepoint-online-and-onedrive-for-business"></a>Inställningar för hela klientorganisationen för SharePoint Online och OneDrive för företag

SharePoint Online och OneDrive för företag innehåller företagsomfattande inställningar som påverkar alla webbplatser och användare. Vissa av de här inställningarna kan också justeras på webbplatsnivå, så att de blir mer begränsande (men inte mindre). I det här avsnittet beskrivs inställningar för hela klientorganisationer som påverkar säkerhet och samarbete.

### <a name="sharing"></a>Delning

För den här lösningen rekommenderar vi följande inställningar för hela klientorganisationen:

- Behåll standardprincipen för delning som tillåter all delning med alla kontotyper, inklusive anonym delning.

- Om du vill kan du ange att anonyma länkar ska upphöra att gälla.

- Ändra standardlänktypen för delning till Intern. Det bidrar till att förhindra oavsiktligt dataläckage utanför din organisation.

Det kanske inte känns intuitivt att tillåta extern delning, men den här metoden ger mer kontroll över fildelningen jämfört med att skicka filer via e-post. SharePoint Online och Outlook samverkar för att ge säkert samarbete kring filer.

- Som standard delar Outlook en länk till en fil i stället för att skicka filen via e-post.

- Med SharePoint Online och OneDrive för företag blir det enkelt att dela länkar till filer med medarbetare som finns både inom och utanför organisationen

Det finns även kontroller som hjälper dig att styra extern delning. Du kan till exempel:

- Inaktivera en anonym gästlänk.

- Återkalla användares åtkomst till en webbplats.

- Visa vilka personer som har åtkomst till en viss webbplats eller ett visst dokument.

- Ange att länkar för anonym delning ska upphöra (klientorganisationsinställning).

- Begränsa vilka som får dela utanför organisationen (klientorganisationsinställning).

### <a name="use-external-sharing-together-with-data-loss-prevention-dlp"></a>Använda extern delning tillsammans med skydd mot dataförlust (DLP)

Om du inte tillåter extern delning kommer användare med affärsbehov att hitta alternativa verktyg och metoder. Microsoft rekommenderar att du kombinerar extern delning med DLP-principer för att skydda känsliga och mycket konfidentiella filer.

### <a name="device-access-settings"></a>Inställningar för enhetsåtkomst

Med inställningar för enhetsåtkomst för SharePoint Online och OneDrive för företag kan du avgöra om åtkomsten ska begränsas till endast webbläsare (filer kan inte laddas ned) eller om åtkomst ska blockeras. Mer information finns i [Styra åtkomsten från ohanterade enheter](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

Information om hur du använder inställningar för enhetsåtkomst med rekommenderade principer för villkorlig åtkomst i Azure Active Directory finns i [Principrekommendationer för att skydda SharePoint-webbplatser och filer](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).

### <a name="onedrive-for-business"></a>OneDrive för företag

Gå till de här inställningarna och välj om du vill ändra standardinställningarna för OneDrive för företag-webbplatser. För närvarande kopieras inställningarna för delning och enhetsåtkomst från administrationscentret för SharePoint Online och tillämpas på båda miljöerna.

## <a name="sharepoint-team-site-configuration"></a>Konfiguration av SharePoint-gruppwebbplatser

I tabellen nedan sammanfattas konfigurationen för varje gruppwebbplats som beskrivs tidigare i den här artikeln. Använd de här konfigurationerna som utgångspunkt och justera webbplatstyperna och konfigurationerna efter behoven i din organisation. Alla organisationer behöver inte alla typer av webbplatser. Bara ett litet antal organisationer kräver strikt konfidentiellt skydd.

||||||
|:-----|:-----|:-----|:-----|:-----|
||**Grundskydd nr 1**|**Grundskydd nr 2**|**Känsligt skydd**|**Strikt konfidentiellt**|
|Beskrivning|Öppen identifiering och samarbete inom organisationen.|Privat webbplats och grupp med delning tillåten utanför gruppen.|Privat webbplats med delning endast tillåten för webbplatsens medlemmar. DLP varnar användare vid försök att skicka filer utanför organisationen.|Privat webbplats och filkryptering samt behörigheter med känslighetsetiketter. DLP hindrar användarna från att skicka filer utanför organisationen.|
|Privat eller offentlig gruppwebbplats|Offentlig|Privat|Privat|Privat|
|Vem har åtkomst?|Alla i organisationen, inklusive B2B-användare och gästanvändare.|Endast webbplatsens medlemmar. Andra kan begära åtkomst.|Endast webbplatsens medlemmar. Andra kan begära åtkomst.|Endast medlemmar. Andra kan inte begära åtkomst.|
|Delningskontroller på webbplatsnivå|Delning med alla tillåts. Standardinställningar.|Delning med alla tillåts. Standardinställningar.|Medlemmar kan inte dela åtkomst till webbplatsen. <br/> Icke-medlemmar kan begära åtkomst till webbplatsen, men dessa förfrågningar måste behandlas av en webbplatsadministratör.|Medlemmar kan inte dela åtkomst till webbplatsen. <br/> Icke-medlemmar kan inte begära åtkomst till webbplatsen eller innehållet.|
|Kontroller för enhetsåtkomst på webbplatsnivå|Inga ytterligare kontroller.|Inga ytterligare kontroller.|Hindrar användarna från att ladda ned filer till enheter som inte är kompatibla eller icke-domänanslutna. Med det här alternativet tillåts endast webbläsaråtkomst från alla andra enheter.|Blockera nedladdning av filer till enheter som inte är kompatibla eller icke-domänanslutna.|
|Kvarhållningsetiketter|Intern offentlig|Privat|Känslig|Strikt konfidentiell|
|DLP-principer|||Varna användare när de skickar filer som är märkta som känsliga utanför organisationen. <br/> Om du vill blockera extern delning av känsliga datatyper, t.ex. kreditkortsnummer eller andra personliga data, kan du konfigurera ytterligare DLP-principer för dessa datatyper (inklusive anpassade datatyper som du konfigurerar).|Hindra användare från att skicka filer som är märkta som mycket konfidentiella utanför organisationen. Tillåta att användare kringgår detta genom att ange en motivering, t.ex. vem de delar filen med.|
|Känslighetsetiketter||||Använd känslighetsetiketter för att automatiskt kryptera och bevilja behörighet till filer. Skyddet överförs med filerna om de läcks ut. <br/> Office 365 kan inte läsa filer som krypterats med känslighetsetiketter. Dessutom kan DLP-principer bara användas med metadata (inklusive etiketter), men inte innehållet i de här filerna (t.ex. kreditkortsnummer i filer).|

Information om hur du distribuerar de fyra olika typerna av SharePoint Online-gruppwebbplatser i den här lösningen finns i [Distribuera SharePoint Online-webbplatser för tre skyddsnivåer](../../compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection.md).

## <a name="office-365-retention-labels"></a>Kvarhållningsetiketter för Office 365

Att använda kvarhållningsetiketter rekommenderas för miljöer med känsliga och strikt konfidentiella data. När du har konfigurerat och publicerat kvarhållningsetiketter:

- Du kan använda en standardetikett för ett dokumentbibliotek på en SharePoint Online-gruppwebbplats, så att alla dokument i biblioteket får standardetiketten.

- Du kan använda etiketter för innehåll automatiskt om det matchar vissa villkor.

- Du kan använda DLP-principer som baseras på kvarhållningsetiketter.

- Personer i organisationen kan använda en etikett manuellt för innehåll i Outlook på webben, Outlook 2010 och senare, OneDrive för företag, SharePoint Online och Office 365-grupper. Användare vet ofta bäst vilken typ av innehåll de arbetar med, så att de kan klassificera det och använda rätt DLP-princip.

![Rekommenderad konfiguration för SharePoint-webbplatser](../../media/7fed0126-ab4a-4480-922c-681970642339.png)

Som vi illustrerat innebär lösningen att följande kvarhållningsetiketter skapas:

- Strikt konfidentiell

- Känslig

- Privat

- Intern offentlig

Dessa etiketter mappas mot de rekommenderade webbplatserna på bilderna och diagrammen tidigare i den här artikeln. Lösningen rekommenderar att DLP-principer konfigureras för att förhindra läckage av filer som är märkta som känsliga och mycket konfidentiella.

Anvisningar för konfiguration av kvarhållningsetiketter och DLP-principer i den här lösningen finns i [Skydda SharePoint Online-filer med kvarhållningsetiketter och DLP](../../compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp.md).

## <a name="sensitivity-labels"></a>Känslighetsetiketter

Om du är berättigad till ditt säkerhetsscenario kan du använda känslighetsetiketter för att tillämpa skydd som följer filerna vart de än flyttas. Känslighetsetiketter i Microsoft 365 Efterlevnadscenter och etiketter för Azure Information Protection är identiska. För den här lösningen rekommenderar vi att du använder en känslighetsetikett eller en underetikett av känslighetsetiketten Strikt konfidentiell för att kryptera och bevilja behörighet till filer som måste skyddas med den högsta säkerhetsnivån.

Om din organisation inte har [aktiverat känslighetsetiketter för Office-filer i SharePoint och OneDrive (offentlig förhandsversion)](/microsoft-365/compliance/sensitivity-labels-sharepoint-onedrive-files): Tänk på att tjänsten inte kan bearbeta innehållet i de här filerna när kryptering av känsligt innehåll används för filer som lagras i Office 365. Samtidig redigering, eDiscovery, sökning, Delve och andra samarbetsfunktioner fungerar inte. DLP-principer kan bara användas med metadata (inklusive kvarhållningsetiketter), men inte innehållet i de här filerna (t.ex. kreditkortsnummer i filer).

Mer information finns i [Översikt över känslighetsetiketter](../../compliance/sensitivity-labels.md).

### <a name="adding-permissions-for-external-users"></a>Lägga till behörigheter för externa användare

Det finns två sätt som du kan använda för att ge externa användare tillgång till filer som skyddats med en känslighetsetikett. I båda fallen måste externa användare ha ett Azure AD-konto. Om externa användare inte är medlemmar i en organisation som använder Azure AD kan de skaffa ett Azure AD-konto som en individ genom att använda den här registreringssidan: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).

- Lägga till externa användare i en Azure AD-grupp som används för att konfigurera skydd för en etikett

  Du måste först lägga till kontot som B2B-användare i katalogen. Det kan ta några timmar för [cachelagring av gruppmedlemskap med Azure Rights Management](https://docs.microsoft.com/information-protection/plan-design/prepare). Med den här metoden beviljas behörigheter till alla befintliga filer som skyddats med etiketten (även filer som skyddats innan en användare läggs till i Azure AD-gruppen).

- Lägga till externa användare direkt i etikettskyddet

  Du kan lägga till alla användare från en organisation (t.ex. Fabrikam.com), en Azure AD-grupp (t.ex. en ekonomigrupp i en organisation) eller en enskild användare. Du kan till exempel lägga till ett externt team med tillsynsmyndigheter i skyddet för en etikett. Med den här metoden beviljas behörigheter endast till filer som skyddats med etiketten efter det att den externa entiteten lagts till i skyddet.

### <a name="deploying-and-using-a-sensitivity-label"></a>Distribuera och använda en känslighetsetikett

Information om hur du konfigurerar en känslighetsetikett i den här lösningen finns i [Skydda SharePoint Online-filer med en känslighetsetikett](../../compliance/protect-sharepoint-online-files-with-sensitivity-label.md).

## <a name="next-step"></a>Nästa steg

Bygg upp detta som en konceptvalidering med [Skydda SharePoint Online-webbplatser i en utvecklings-/testmiljö](secure-sharepoint-online-sites-in-a-dev-test-environment.md).

## <a name="see-also"></a>Se även

[Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra snabbrörliga organisationer](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[Införande av moln- och hybridlösningar](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
