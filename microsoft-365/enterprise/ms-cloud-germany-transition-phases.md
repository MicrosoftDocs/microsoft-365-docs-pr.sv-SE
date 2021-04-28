---
title: Åtgärder i migreringsfaser och påverkan på migreringen från Microsoft Cloud Deutschland)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/05/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: Sammanfattning Förstå åtgärderna i migreringsfaserna och hur de påverkar flytten från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterområdet.
ms.openlocfilehash: 354ca55bae7704c011af5a76a1112e4d2ecb47ca
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073931"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland"></a>Åtgärder i migreringsfaser och påverkan på migreringen från Microsoft Cloud Deutschland

Klientmigrering från Microsoft Cloud Deutschland (MCD) till regionen "Tyskland" av Microsofts globala Office 365-tjänster körs som en uppsättning faser och deras konfigurerade åtgärder för varje arbetsbelastning. I den här bilden visas de tio faserna av migreringen till de nya tyska datacenteren.

[![De tio migreringsfaserna till de nya Tyskland-datacenter ](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)](../media/ms-cloud-germany-migration-opt-in/migration-organization.png#lightbox)

Migreringsprocessen slutförs under många veckor beroende på organisationens totala storlek och komplexitet. Under tiden migreringen pågår kan användare och administratörer fortsätta använda tjänsterna med märkbara ändringar i den här dokumentationen. Grafiken och tabellen definierar faser och steg under migreringen.

|Steg|Varaktighet|Ansvarig part|Beskrivning|
|:--------|:--------|:--------|:--------|
|Opt-In|Tider|Kund|Välj din organisation för migreringen.|
|Före arbete|dagar|Kund|Slutför arbetet som krävs för att förbereda användare, arbetsstationer och nätverk för migrering.|
|Azure Active Directory (Azure AD)|1–2 dagar|Microsoft|Migrera Azure AD-organisationen till hela världen.|
|Azure|Veckor|Kund|Skapa nya globala Azure-prenumerationer och övergång Azure-tjänster.|
|Övergången & prenumerationslicens|1–2 dagar|Microsoft|Köp globala prenumerationer, avbryt Microsoft Cloud Deutschland-prenumerationer och gå över användarlicenser.|
|SharePoint och OneDrive|15+ dagar|Microsoft|Migrera innehåll i SharePoint och OneDrive för företag, men sharepoint.de URL:er.|
|Exchange Online|15+ dagar|Microsoft|Migrera Exchange Online-innehåll och gå över till globala URL:er.|
|Säkerhets- & efterlevnad|1–2 dagar|Microsoft|Säkerhet och & och innehåll för övergång.|
|Skype för företag|1–2 dagar|Microsoft|Gå över från Skype för företag till Microsoft Teams.|
|Power BI & Dynamics 365|15+ dagar|Microsoft|Migrera innehåll i Power BI och Dynamics 365.|
|Slutför Azure AD|1–2 dagar|Microsoft|Slutför klientuppeställningen till hela världen.|
|Clean-Up|1–2 dagar|Kund|Rensa upp äldre anslutningar till Microsoft Cloud Deutschland, till exempel AD FS (Active Directory Federation Services) Relying Party Trust, Azure AD Connect och Office-klienten startar om.|
|Slutpunkter inaktiverade|30 dagar|Microsoft|30 dagar efter slutförande av Azure AD kommer Microsoft Cloud Deutschland Azure AD-tjänsten att stoppa slutpunktsåtkomst för den övergångs organisationen. Slutpunktsbegäranden, till exempel autentisering, kommer att misslyckas från och med nu mot Microsoft Cloud Deutschland-tjänsten. |


Faserna och deras åtgärder säkerställer att kritiska data och upplevelser migreras till globala Office 365-tjänster. När klientorganisationen har lagts till i migreringskön slutförs varje arbetsbelastning som en uppsättning steg som körs på backend-tjänsten. Vissa arbetsbelastningar kan kräva åtgärder av administratören (eller användaren), eller så kan migreringen påverka användningen för faserna som körs och diskuteras i Hur [organiseras migreringen?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Följande avsnitt innehåller åtgärder och effekter för arbetsbelastningen medan de går igenom olika faser av migreringen. Granska tabellerna och bestäm vilka åtgärder eller effekter som gäller för din organisation. Se till att du är redo att utföra stegen i respektive fas efter behov. Om du inte kan slutföra de nödvändiga stegen kan det leda till avbrott i tjänsten och kan fördröja migreringen till Office 365-tjänsterna.

## <a name="phase-opt-in"></a>Fas: Opt-In

**Gäller för:** Alla kunder med en Office 365-klientorganisation som finns på Microsoft Cloud Deutschland (MCD) Microsoft kan inte migrera Office 365-klientorganisationen på MCD-webbplatsen utan medgivande.

| Steg | Beskrivning | Påverkan |
|:-------|:-----|:-------|
|**Kunduppgift:** Ge medgivande för migrering| Kunden beviljar medgivande för migreringen så att Microsoft får rätt att migrera och hantera övergången av data och tjänster till den globala Office 365-tjänstinstansen. Det finns två sätt <ol><li>Office 365-innehavaradministratören väljer den Microsoft-drivna migreringen. </li><li> Kunder har förnyat alla prenumerationer på Sin MCD Office 365-klientorganisation efter den 1 maj 2020. Microsoft meddelar dessa kunder om migreringen varje månad, väntar i 30 dagar för att ge kunder möjlighet att avbryta och sedan direkt välja till.</li></ol> | <ul><li>Klientorganisationen markeras som bekräftad för migrering och admincentret visar en bekräftelse. </li><li>Bekräftelsen publiceras i Meddelandecenter för Office 365-klientorganisationen. Tjänstkonfigurationen fortsätter från Microsoft Cloud Deutschland-slutpunkter. </li><li> </li></ul>
|**Klientorganisationens administratör:** Övervaka meddelanden|Innehavaradministratören måste övervaka Office 365 Meddelandecenter för uppdateringar om status för migreringsfasen från och med nu.|Kunden kan utföra nödvändiga uppgifter i tid.
||||

## <a name="phase-1-before-the-migration-starts"></a>Fas 1: Innan migreringen startar

Kontrollera att du känner till stegen för [migreringsförberedelser som gäller för alla kunder.](ms-cloud-germany-transition-add-pre-work.md)

Om du har angett dns-CNAME med namnet _msoid_ i ett eller flera DNS-namnområden som du äger, måste du ta bort CNAME-namnet till slutet av fas 8 senast. Du kan ta bort _CNAME-msoid_ när som helst före slutet av fas 8. Se [förarbetet med DNS.](ms-cloud-germany-transition-add-pre-work.md#dns-entries-for-custom-domains)

Om du använder enkel inloggning för Office 365 och Azure i Microsoft Cloud Deutschland-instansen måste du förbereda och schemalägga migreringen av Din Azure-prenumeration i enlighet med detta. Se till att du förstår [förarbetet med Microsoft Azure.](ms-cloud-germany-transition-add-pre-work.md#microsoft-azure)

### <a name="azure-ad-connect-with-ad-fs-federation"></a>Azure AD Connect med AD FS-federation
**Gäller för:** Kunder med AD FS-federation

**Vid start:** Innan fas 2 startar

Om du använder Active Directory Federation Services (AD FS) bör du era [ADFS-konfigurationer](ms-cloud-germany-transition-azure-ad.md) före och efter  det att du har lagt till det beroende partens förtroende för den globala Office 365-tjänsten innan fas 2 börjar.

## <a name="phase-2-azure-ad-migration"></a>Fas 2: Azure AD-migrering
I den här fasen kommer Azure Active Directory att migreras till den nya datacenterområdet och aktiveras. De gamla Azure AD-slutpunkterna är fortfarande tillgängliga.

### <a name="exchange-online-hybrid---modify-authserver-on-premises"></a>Exchange Online-hybrid – ändra authServer lokalt
**Gäller för:** Alla kunder som använder en aktiv Exchange-hybridkonfiguration med Exchange-servrar lokalt

**När den används:** Efter att fas 2 har avslutats

AuthServer lokalt måste peka på global STS (Security Token Service) för autentisering när Azure AD-migreringen har slutförts.
Detta säkerställer att autentiseringsförfrågningar för Exchange-tillgänglighetsförfrågningar från användare i migreringstillstånd som är mål för den lokala hybridmiljön autentiseras för åtkomst till den lokala tjänsten. På samma sätt säkerställer detta autentisering av förfrågningar från lokala till globala slutpunkter för Office 365-tjänster. När Azure AD-migrering (fas 2) har slutförts måste administratören för den lokala Exchange-topologin (hybrid) lägga till en ny autentiseringstjänstslutpunkt för globala Office 365-tjänster. Med det här kommandot från Exchange PowerShell ersätter du med `<TenantID>` organisationens klientorganisations-ID som finns på Azure-portalen i Azure Active Directory.

```powershell
New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantID>/metadata/json/1
```

Om uppgiften inte slutförs kan det leda till hybridförfrågningar om ledig/upptagen-information som inte kan tillhandahålla information för postlådeanvändare som har migrerats från Microsoft Cloud Deutschland till Office 365-tjänster.

## <a name="phase-3-subscription-transfer"></a>Steg 3: Abonnemangsöverföring

**Gäller för:** Alla kunder med en Office 365-klientorganisation som finns på Microsoft Cloud Deutschland (MCD)

Partner Microsoft Cloud Deutschland-klientorganisationen kommer inte att migreras. Kunder som använder CSP migreras till Office 365-tjänster under den nya Office 365-tjänstklientorganisationen hos samma partner. Efter kundmigrering kan partnern bara hantera den här kunden från Office 365-tjänstklientorganisationen.

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Prenumerationer överförs| Microsoft Cloud Deutschland-prenumerationen migreras till motsvarande prenumeration på globala Office 365-tjänster. <ul><li>Erbjudandet om globala Office 365-tjänster för prenumerationen definieras av Microsoft (kallas även _offermappning)._</li><li> Motsvarande prenumerationer på globala Office 365-tjänster köps i den globala Office 365-instansen för de överförda Microsoft Cloud Deutschland-prenumerationerna.</li><li>Äldre Microsoft Cloud Deutschland-prenumerationer tas bort från Office 365-tjänstklientorganisationen när den är klar.</li></ul>| <ul><li>Ändringar av befintliga prenumerationer kommer att blockeras (t.ex. inga ändringar av nya prenumerationer eller antal platser) under den här fasen.</li><li>Ändringar av licenstilldelning blockeras.</li><li>När prenumerationsmigrering är slutförd visas både Office 365-tjänster och Microsoft Cloud Deutschland-prenumerationer i administrationsportalen för Office 365, med statusen Microsoft Cloud Deutschland-prenumerationer som _återkallade._ </li><li>Alla kundprocesser som är beroende av Microsoft Cloud Deutschland-prenumerationer eller SKU GUID kommer att brytas och måste revideras med Office 365-tjänsterbjudanden. </li><li>Nya prenumerationer i Office 365-tjänsterna köps med den nya perioden (per månad/kvartal/år) och kunden får en prorrerad återbetalning för det oanvända saldot i Microsoft Cloud Deutschland-prenumerationen. </li></ul> |
|Licenser omtilldeeras|Användare med tilldelade Microsoft Cloud Deutschland-licenser tilldelas licenser i den globala Office 365-instansen.|<ul><li>Användare kommer att omtilldelas licenser som är kopplade till de nya Office 365-tjänstprenumerationer. Användarlicenserna för alla användare tilldelas automatiskt de nya funktionerna.</li><li>Antalet funktioner (tjänstplaner) som erbjuds av Office 365-tjänster kan vara större än det ursprungliga Microsoft Cloud Deutschland-erbjudandet. Användarlicenser i Office 365-tjänster tilldelas likvärdigt med liknande Microsoft Cloud Deutschland-funktioner (tjänstplaner). </li></ul> 
|**Administratörsuppgift** Inaktivera funktioner|Administratören måste vidta en uttrycklig åtgärd för att inaktivera funktionerna om det behövs. |<ul><li>Användarna ser nya okända tjänster i portalen</li><li>Fler funktioner är tillgängliga (till exempel Microsoft Planner och Microsoft Flow), om de inte inaktiveras av administratören för klientorganisationen. Mer information om hur du inaktiverar tjänstplaner som är tilldelade till användarnas licenser finns i Inaktivera åtkomst till [Microsoft 365-tjänster medan du tilldelar användarlicenser.](disable-access-to-services-while-assigning-user-licenses.md)</li></ul>
|**Administratörsuppgift**|Revidera alla kundprocesser som är beroende av Microsoft Cloud Deutschland-prenumerationer eller SKU GUID med Office 365-tjänster|Kundprocesser fortsätter att fungera.
||||

**Gäller för:** Microsoft-partner som använder Office 365-partnerportalen

Mellan fas 2 och fas 3 är partnerportalen kanske inte tillgänglig. Under tiden kanske partnern inte kan komma åt klientorganisationens information på partnerportalen. Eftersom varje migrering är olika kan varaktigheten för tillgänglighet vara i timmar.


## <a name="phase-4-sharepoint-online"></a>Fas 4: SharePoint Online

**Gäller för:** Alla kunder som använder SharePoint Online

Om du fortfarande använder SharePoint 2013-arbetsflöden begränsar du användningen av SharePoint 2013-arbetsflöden under SharePoint Online-migreringen.

| Steg | Beskrivning | Påverkan |
|:-------|:-----|:-------|
| SharePoint och OneDrive har övergångar | SharePoint Online och OneDrive för företag migreras från Microsoft Cloud Deutschland till globala Office 365-tjänster i den här fasen.<br><ul><li>Befintliga Microsoft Cloud Deutschland-WEBBADRESSer bevaras (till exempel `contoso.sharepoint.de` ).</li><li>Befintliga webbplatser bevaras.</li><li>Klientbaserade autentiseringstoken som utfärdats av STS (Security Token Service) i Microsoft Cloud Deutschland eller Office 365 Global Services-instansen är giltiga under övergången.</li></ul>|<ul><li>Innehållet kommer att vara skrivskyddat under två korta perioder under migreringen. Under tiden kan du förvänta dig en banderoll i SharePoint som säger att du inte kan redigera innehåll.</li><li>Sökindexet bevaras inte, och det kan ta upp till tio dagar att återskapa det.</li><li>SharePoint Online- och OneDrive för företag-innehåll kommer att vara skrivskyddat under två korta perioder under migreringen. Under den här tiden visas en banderoll som säger att du inte kan redigera innehåll.</li><li>När SharePoint Online-migreringen slutförts kanske sökresultaten för SharePoint Online- och OneDrive för företag-innehåll inte är tillgängliga medan indexet återskapas. Under den här perioden kan det hända att sökfrågor inte returnerar fullständiga resultat. Funktioner som är beroende av sökindex, till exempel SharePoint Online Nyheter, kan påverkas när indexeringen slutförs.</li><li>SharePoint 2013-arbetsflöden bryts under migreringen och måste publiceras på nytt efter migreringen.</li></ul>
|**SPO-administratör:** Publicera om SharePoint 2013-arbetsflöden| En SharePoint Online-administratör publicerar sharePoint 2013-arbetsflödena på nytt efter migreringen.|SharePoint 2013-arbetsflöden är tillgängliga.
|**PowerShell-användare:** Uppdatera till ny modul| Alla användare av SharePoint Online PowerShell-modulen måste uppdatera modulen/Microsoft.SharePointOnline.CSOM till version 16.0.20717.12000 eller senare när SharePoint Online-migreringen är slutförd. Slutförande meddelas i meddelandecentret.| SharePoint Online via PowerShell eller klientobjektmodellen kommer inte längre att misslyckas.
||||

Ytterligare överväganden:

- Om din organisation fortfarande använder SharePoint 2010-arbetsflöden kommer de inte längre att fungera efter den 31 december 2021. SharePoint 2013-arbetsflöden kommer att fortsätta stödjas, även om det är inaktiverat som standard för nya klientorganisationar som startar den 1 november 2020. När migreringen till SharePoint Online-tjänsten är klar rekommenderar vi att du flyttar till Power Automate eller andra lösningar som stöds.
 - Microsoft Cloud Deutschland-kunder vars SharePoint Online-instans ännu inte migrerats måste vara kvar på SharePoint Online PowerShell-modulen/Microsoft.SharePointOnline.CSOM version 16.0.20616.12000 eller senare. I annat fall går det inte att använda anslutningar till SharePoint Online via PowerShell eller objektmodellen på klientsidan.
- Under den här fasen kommer IP-adresserna som ligger bakom SharePoint-webbadresserna att ändras. Efter övergången till globala Office 365-tjänster ändras adresserna för de bevaras klientorganisations-URL:er (till exempel och ) till url-adresser och `contoso.sharepoint.de` `contoso-my.sharepoint.de` [IP-adressintervall för Microsoft 365 (SharePoint Online](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#sharepoint-online-and-onedrive-for-business)och OneDrive för företag).

> [!NOTE]
> Om du använder eDiscovery ska du kontrollera att du är medveten om [eDiscovery-migreringsupplevelsen.](ms-cloud-germany-transition-add-scc.md)

## <a name="phase-5-exchange-online"></a>Fas 5: Exchange Online 
Från och med fas 5 flyttas Exchange Online-postlådor från Microsoft Cloud Deutschland till globala Office 365-tjänster.

Region för globala Office 365-tjänster har angetts som standard, vilket gör att den interna belastningsutjämningstjänsten kan distribuera om postlådor till rätt standardområde i Office 365-tjänsterna. I den här övergången finns användarna på vardera sidan (MCD eller globala tjänster) i samma organisation och kan använda antingen URL-slutpunkten.

Den nya regionen "Tyskland" läggs till i organisationens konfiguration. Exchange Online-konfigurationen lägger till den nya lokala tyska regionen i övergången.

- Gå över användare och tjänster från äldre MCD-URL:er () till nya URL-adresser för `https://outlook.office.de` Office 365-tjänster ( `https://outlook.office365.com` ).
-  Exchange Online-tjänsterna (Outlook Web Access och Administrationscenter för Exchange) för den nya tyska datacenterområdet kommer att vara tillgängliga från den här fasen, de kommer inte att vara tillgängliga tidigare.
- Användarna kan fortsätta att få åtkomst till tjänsten via äldre MCD-URL:er under migreringen, men de måste sluta använda de äldre webbadresserna när migreringen slutförts.
- Användarna bör gå över till att använda den globala Office-portalen för Office Online-funktionerna (Kalender, E-post, Kontakter). Navigering till tjänster som ännu inte har migrerats till Office 365-tjänster fungerar inte förrän de migreras. 
- Den här begränsningen gäller även för bakgrundstjänster som Mitt konto. Mitt konto för globala tjänster blir tillgängligt när fas 9 är klar. Tills dess måste användarna använda MCD-portalen för att hantera sina kontoinställningar.
- Outlook Web App tillhandahåller inte de gemensamma mapparna under migreringen.

Om du vill ändra användarfoton under fas 5 kan du gå till [Exchange Online PowerShell – Set-UserPhoto under fas 5.](#exchange-online-powershell)

### <a name="dns-record-for-autodiscover-in-exchange-online"></a>DNS-post för automatisk upptäckt i Exchange Online
**Gäller för:** Kunder som använder Exchange Online med en egen domän

Customer-managed DNS settings for Autodiscover that currently point to Microsoft Cloud Deutschland need to be updated to refer to the Office 365 Global endpoint on completion of the Exchange Online phase (phase 5). <br> Befintliga DNS-poster med CNAME som pekar autodiscover-outlook.office.de måste uppdateras så att de pekar på **autodiscover.outlook.com.**

Kunder som inte utför de här DNS-uppdateringarna vid slutförande av migreringsfasen **9** kan uppleva tjänstproblem när migreringen slutförs.

> [!NOTE]
> Verifieringsfel i administrationscentret för anpassade domäner för posten Automatisk upptäckt kan ignoreras. Tjänsterna fungerar korrekt endast när CNAME-posten har ändrats till autodiscover.outlook.com.

### <a name="exchange-online-powershell"></a>Exchange Online PowerShell
**Gäller för:** Exchange Online-administratörer med Exchange Online PowerShell

Under migreringsfasen kan användning av **PowerShell-cmdlets New-MigrationEndpoint,** **Set-MigrationEndpoint** och **Test-MigrationsServerAvailability** resultera i fel (fel på proxy). Det här inträffar när skiljebrevlådan har migrerats till hela världen men administratörspostlådan inte har det eller vice versa. Du kan lösa problemet genom att använda skiljepostlådan som tips om routning i **ConnectionUri** när du skapar PowerShell-klientsessionen. Till exempel:

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@<tenant>.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```
Om du använder PowerShell-cmdleten **Set-UserPhoto** uppstår ett fel om en användarpostlåda har migrerats, men en administratörspostlåda inte har migrerats, eller tvärtom. I det här fallet måste en administratör överföra e-post-ID för den användare vars foto behöver ändras när `ConnectionUri` du skapar PowerShell-klienten: 
```powershell
-ConnectionUri "https://outlook.office.de/powershell-liveid?email=<user_email>" 
```
 där `<user_email>` är platshållaren för användarens e-post-ID. 

Ytterligare överväganden:
- Användare av Outlook Web App som har åtkomst till en delad postlåda i en annan miljö (till exempel en användare i MCD-miljön får åtkomst till en delad postlåda i den globala miljön) uppmanas att autentisera en andra gång. Användaren måste först autentisera och komma åt sin postlåda i `outlook.office.de` och sedan öppna den delade postlådan som finns i `outlook.office365.com` . De måste autentiseras en andra gång när de får åtkomst till de delade resurser som finns i den andra tjänsten.
- För befintliga Microsoft Cloud Deutschland-kunder eller användare som är under övergång kan det hända att en delad postlåda läggs till i Outlook med Arkiv **> Info >** Lägg till konto och kalenderbehörigheter kan misslyckas (Outlook-klienten försöker använda Rest `https://outlook.office.de/api/v2.0/Me/Calendars` API). Kunder som vill lägga till ett konto för att visa kalenderbehörigheter kan lägga till registernyckeln enligt beskrivningen i Ändringar i användarupplevelsen för delning av en kalender i [Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) för att säkerställa att den här åtgärden lyckas. Den här registernyckeln kan distribueras i hela organisationen med hjälp av Grupprincip.
- Alla kunder som använder en aktiv Exchange-hybridkonfiguration kan inte flytta postlådor från en lokal Exchange Server till Exchange Online, varken till Microsoft Cloud Deutschland eller till den nya datacenterområdet i Tyskland. Kunder måste säkerställa att löpande postlådeflyttningar har slutförts före fas 5 och återupptas efter den här fasen.
- Se till att alla användare som använder äldre protokoll (POP3/IMAP4/SMTP) för sina enheter är redo att ändra slutpunkterna i sin klient när [Exchange-postlådan](ms-cloud-germany-transition-add-pre-work.md#exchange-online)har flyttats till den nya tyska datacenterområdet enligt anvisningarna före migreringen för Exchange Online.
- Schemaläggning av Skype för företag-möten i Outlook Web App är inte längre tillgängligt efter att postlådan har migrerats. Om det behövs måste användarna använda Outlook i stället.

Om du vill veta mer om skillnaderna för organisationer i migrering och när Exchange Online-resurser har migrerats kan du läsa informationen i Kundupplevelse under migreringen till [Office 365-tjänster](ms-cloud-germany-transition-experience.md)i de nya tyska datacenterområdena.

## <a name="phase-6-exchange-online-protection--security-and-compliance"></a>Fas 6: Exchange Online Protection/Säkerhet och efterlevnad

**Gäller för:** Alla kunder som använder Exchange Online<br>

EOP-funktioner (Back-end Exchange Online Protection) kopieras till den nya regionen "Tyskland". Exchange Online möjliggör routning från externa värdar till Office 365 och historisk information om klientorganisationen migreras, vilket även inkluderar servertjänster för funktioner för säkerhet och efterlevnad.

Kunder som använder endast Exchange Online-funktioner (icke-hybrid) behöver inte vara uppmärksamma i det här skedet.

### <a name="exchange-online-hybrid-deployments"></a>Exchange Online-hybriddistributioner
**Gäller för:** Alla kunder som använder en aktiv Exchange-hybridkonfiguration med Exchange-servrar lokalt

Kontrollera att [Exchange-förarbetet](ms-cloud-germany-transition-add-pre-work.md#exchange-online-hybrid-customers) har tillämpats **innan migrering steg 5 börjar.** Exchange Online-hybridkunder måste köra den senaste versionen av hybridkonfigurationsguiden för Exchange (HCW) i läget "Office 365 Germany" för att förbereda den lokala konfigurationen för migreringen till globala Office 365-tjänster.

**Administrativa åtgärder:**
- Från början av migreringsfasen 6 till slutförande av migreringsfasen 9 (när meddelandecentret publiceras) måste du köra HCW igen med hjälp av de globala inställningarna för Office 365 så att dina lokala system pekar på de globala Office 365-tjänsterna. Om du inte slutför den här uppgiften före fas 9 [Migreringen är slutförd] kan det resultera i NDR-meddelanden för e-post som dirigeras mellan din lokala Exchange-distribution och Office 365.
- Stoppa eller ta bort alla flyttningar av onboarding- eller offboarding-postlådor– de flyttar inte inkorgarna mellan Exchange lokalt och Exchange Online.  Det säkerställer att flyttningsförfrågningar för postlådor inte misslyckas och att det inte uppstår ett fel. Om du inte gör det kan det leda till att tjänsten eller Office-klienterna misslyckas.
- Ytterligare Send-Connectors som har skapats förutom kopplingen som skapats av HCW och som är rikta till Exchange Online måste uppdateras i den här fasen direkt efter att HCW-körningen har körts, annars slutar de att fungera. TLS-domänen måste uppdateras för dessa Skicka-kopplingar. <br> Om du vill uppdatera TLS-domänen använder du följande PowerShell-kommando i Exchange Server-miljön:
```powershell
Set-SendConnector -Identity <SendConnectorName> -TlsDomain "mail.protection.outlook.com"
```

## <a name="phase-7-skype-for-business-online"></a>Steg 7: Skype för företag – Online

**Gäller för:** Alla kunder som använder Skype för företag – Online

Gå igenom [stegen före migreringen av Skype för företag – Online](ms-cloud-germany-transition-add-pre-work.md#skype-for-business-online) och kontrollera att du har slutfört alla steg.
I den här fasen kommer Skype för företag att migreras till Microsoft Teams. Befintliga Skype för företag-kunder migreras till globala Office 365-tjänster i Europa och flyttas sedan över till Microsoft Teams i regionen "Tyskland" för Office 365-tjänster.

- Användarna kan inte logga in på Skype för företag på migreringsdatumet. Tio dagar före migreringen får kunden ett meddelande i administrationscentret som meddelar när migreringen sker, och igen när migreringen påbörjas.
- Principkonfigurationen migreras.
- Användare migreras till Teams och har inte längre åtkomst till Skype för företag efter migreringen.
- Användarna måste ha Microsoft Teams-skrivbordsklienten installerad. Installationen sker under tio dagar via policyn för Skype för företag-infrastrukturen, men om det misslyckas måste användarna fortfarande hämta klienten eller ansluta med en webbläsare som stöds.
- Kontakter och möten migreras till Microsoft Teams.
- Användarna kan inte logga in i Skype för företag mellan tidstjänstens övergångar till Office 365-tjänster och inte förrän DNS-posterna för kunder har slutförts.
- Kontakter och befintliga möten fortsätter att fungera som Skype för företag-möten.
- Webbläsarversionen av Microsoft Teams fungerar inte förrän fas 9 har slutförts.

Om du måste ansluta till Skype för företag – Online med PowerShell efter att migreringsfasen 9 har slutförts använder du följande PowerShell-kod för att ansluta:

```powershell
Import-Module MicrosoftTeams
$userCredential = Get-Credential
Connect-MicrosoftTeams -Credential $userCredential -OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"
```

## <a name="phase-8-dynamics-365"></a>Fas 8: Dynamics 365

**Gäller för:** Alla kunder som använder Microsoft Dynamics 365

Kontrollera att du är bekant med [förarbetet med installationen av Microsoft Dynamics 365.](ms-cloud-germany-transition-add-pre-work.md#dynamics365)

Kunder med Dynamics 365 kräver ytterligare engagemang för att migrera organisationens Dynamics-organisationer oberoende av varandra.

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Microsoft Dynamics-resurser | Kunder med Microsoft Dynamics kommer att anlitas av Microsoft Engineering eller Microsoft FastTrack för att övergå Microsoft Dynamics 365 till den globala Office 365-tjänstinstansen.* |<ul><li>Efter migreringen validerar administratören organisationen. <</li><li>Administratören ändrar arbetsflöden efter behov. </li><li>Administratören tar bort AdminOnly-läget efter behov.</li><li>Administratören ändrar organisationstypen från begränsat _läge_ efter behov</li><li>Meddela slutanvändarna om den nya URL-adressen för åtkomst till instansen (org).</li><li>Uppdatera alla inkommande anslutningar till den nya slutpunkts-URL:en. </li><li>Dynamics-tjänsten kommer inte att vara tillgänglig för användarna under övergången. </li><li>Användarna måste validera organisationens hälsa och funktioner efter migreringen av varje organisation.</li></ul>|
||||

\* (i) Kunder med Microsoft Dynamics 365 måste vidta åtgärder i det här migreringsscenariot som definierats av den angivna migreringsprocessen. (ii) Om kunden inte kan vidta någon åtgärd kommer Microsoft inte att kunna slutföra migreringen. (iii) När Microsoft inte kan slutföra migreringen på grund av kundens inaktivitet upphör kundens prenumeration den 29 oktober 2021.

## <a name="phase-8-power-bi"></a>Fas 8: Power BI

**Gäller för:** Alla kunder som använder Microsoft Power BI (PBI)

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Migrering av Power BI-resurser | Kunder med Microsoft Power BI (PBI) kommer att vara engagerade av Microsoft Engineering eller Microsoft FastTrack efter att manuellt ha utlöst ett befintligt PBI-migreringsverktyg för att gå över Power BI till den globala tjänstinstansen för Office 365.\*\* |<ul><li>Följande Power _BI-objekt_ kommer inte att gå över och de måste skapas på ny sätt: <</li><li>Realtidsdatamängder (till exempel strömmande datamängder eller push-datauppsättningar). </li><li>Konfiguration och datakälla för lokal datagateway i Power BI. </li><li>Rapporter som bygger på realtidsdatamängderna blir inte tillgängliga efter migreringen och de måste återskapas. </li><li>Under övergången kommer inte användarna att kunna använda Power BI-tjänsterna. Tillgängligheten för tjänsten bör inte vara mer än 24 timmar.</li><li>Användare måste konfigurera om datakällor och deras lokala datagateway med Power BI-tjänsten efter migreringen.  Fram till dess kan användarna inte använda dessa datakällor för att utföra schemalagda uppdateringar och/eller direkta frågor mot dessa datakällor. </li><li>Kapaciteter och premiumarbetsytor kan inte migreras. Kunder måste ta bort alla kapaciteter före migreringen och skapa dem igen efter migreringen. Flytta arbetsytor tillbaka till kapaciteterna efter behov.</li></ul>  |
||||

\*\* (i) Kunder med Microsoft Power BI måste vidta åtgärder i det här migreringsscenariot som definierats av den migreringsprocess som tillhandahålls. (ii) Om kunden inte kan vidta någon åtgärd kommer Microsoft inte att kunna slutföra migreringen. (iii) När Microsoft inte kan slutföra migreringen på grund av kundens inaktivitet upphör kundens prenumeration den 29 oktober 2021.

## <a name="phase-9-office-apps"></a>Fas 9: Office-program

**Gäller för:** Alla kunder som använder Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook, OneDrive ...)

I den här fasen utför alla klientprogram och Office Online klientuppeställningen. Azure AD slutför klientorganisationens omfattning så att den pekar på Office 365-tjänsterna och de relaterade slutpunkterna.

För klientorganisationen av Office 365 under övergången till regionen "Tyskland" måste alla användare stänga, logga ut från Office 365 och tillbaka in för alla Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook osv.) och OneDrive för företag-klienten när klientorganisationens migrering har nått fas 9. Genom att logga ut och in kan Office-tjänsterna hämta nya autentiseringstoken från den globala Azure AD-tjänsten.

Om Office-skrivbordsprogrammen inte fungerar när de har loggat ut och loggat in från programmen rekommenderar vi starkt att du kör [Office Client Cutover Tool (SÅDD)](https://github.com/microsoft/OCCT) på den aktuella datorn för att åtgärda problemet.

Om [OFFICE CLIENT Cutover Tool (SÅ HÄR)](https://github.com/microsoft/OCCT) har distribuerats och schemalagts på Windows-klienter i förväg krävs ingen ut-/inloggningsprocedur.

Den bästa användarupplevelsen kan säkerställas genom att använda de senaste Office-programmen. Företag bör överväga att använda Månadskanal för företag.

Kontrollera att du har slutfört [proceduren för mobila](ms-cloud-germany-transition-add-pre-work.md#mobile-device-management) enheter.

Ytterligare överväganden:
- Meddela användarna att stänga alla Office-program och logga in igen (eller tvinga klienter att starta om och användarna att logga in) för att aktivera Office-klienter för att hämta ändringen.
- Meddela användare och supportpersonal att användarna kan se en Office-banderoll som uppmanar dem att återaktivera Office-program inom 72 timmar efter övergången.
- Alla Office-program på persondatorer måste vara stängda och användarna måste logga ut och sedan logga in igen. I det gula aktiveringsfältet loggar du in för att återaktivera mot Office 365-tjänster.
- Delade datorer kräver åtgärder som liknar personliga maskiner och kräver ingen särskild procedur.
- På mobila enheter måste användarna logga ut från appar, stänga dem och sedan logga in igen.

## <a name="phase-9-line-of-business-apps"></a>Fas 9: Verksamhetsbaserade appar

**Gäller för:** Alla kunder som använder verksamhetsbaserade appar anslutna till Office 365

Om du har verksamhetsbaserade appar ska du kontrollera [](ms-cloud-germany-transition-add-pre-work.md#line-of-business-apps) att du har slutfört förarbetet med proceduren för verksamhetsbaserade appar.

## <a name="phase-9--10-azure-ad-finalization"></a>Fas 9 & 10: Azure AD-slutförande

**Gäller för:** Alla kunder

När Office 365-klientorganisationen har slutfört det sista steget av migreringen (Azure AD-slutförande (fas 9)) är alla tjänster över hela världen. Inga program eller användare ska ha åtkomst till resurser för klientorganisationen mot någon av Microsoft Cloud Deutschland-slutpunkterna. Efter 30 dagar efter att slutförandet kommer Microsoft Cloud Deutschland Azure AD-tjänsten att stoppa slutpunktsåtkomst för den övergångde klientorganisationen. Slutpunktsbegäranden, till exempel autentisering, kommer att misslyckas från och med nu mot Microsoft Cloud Deutschland-tjänsten. 

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Uppdatera användarslutpunkter | Se till att alla användare får åtkomst till tjänsten med hjälp av rätt globala Microsoft-slutpunkter |Efter migreringen 30 dagar slutar Microsoft Cloud Deutschland-slutpunkterna att respektera förfrågningar. klient- eller programtrafiken misslyckas.  |
| Uppdatera Slutpunkter för Azure AD-program | Du måste uppdatera slutpunkter för autentisering, Azure Active Directory (Azure AD) Graph och MS Graph för dina program till slutpunkterna för Microsofts globala tjänst. | Efter migreringen 30 dagar slutar Microsoft Cloud Deutschland-slutpunkterna att respektera förfrågningar. klient- eller programtrafiken misslyckas. |
||||

### <a name="azure-ad-connect"></a>Azure AD Connect
**Gäller för:** Alla kunder synkroniserar identiteter med Azure AD Connect

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Uppdatera Azure AD Connect. | Efter att användningen av Azure AD har slutförts använder organisationen alla Office 365-tjänster och är inte längre ansluten till Microsoft Cloud Deutschland. I det här läget måste kunden säkerställa att deltasynkroniseringsprocessen har slutförs och sedan ändra strängvärdet från `AzureInstance` 3 (Microsoft Cloud Deutschland) till 0 i `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` registersökvägen. | Ändra `AzureInstance` registernyckelns värde. Om du inte gör det kommer objekten inte att synkroniseras efter att Microsoft Cloud Deutschland-slutpunkterna inte längre är tillgängliga. |
|||||

## <a name="post-migration"></a>Efter migreringen

Läs artikeln om aktiviteter [efter migreringen](ms-cloud-germany-transition-add-experience.md) och kör dem i enlighet med detta.
