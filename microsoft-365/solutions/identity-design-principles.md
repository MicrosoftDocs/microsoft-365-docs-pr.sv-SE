---
title: Till identitet och bortom - En arkitekt synvinkel
description: Beskrivning.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.custom:
- M365solutions
f1.keywords: NOCSH
ms.openlocfilehash: 0b0d79906093df544dc501dd5fff7638833ea54c
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003539"
---
# <a name="to-identity-and-beyond--one-architects-viewpoint"></a>Till identitet och bortom - En arkitekt synvinkel

I den här artikeln diskuterar [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/), Principal Technical Architect på Microsoft, de bästa designstrategierna för företagsorganisationer som använder Microsoft 365 och andra Microsoft-molntjänster.

## <a name="about-the-author"></a>Om författaren

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg" alt-text="Alex Shteynberg foto":::

Jag är en rektor teknisk arkitekt på New York [Microsoft Technology Center](https://www.microsoft.com/mtc?rtc=1). Jag arbetar mest med stora kunder och komplexa krav. Min synpunkt och åsikter bygger på dessa interaktioner och kanske inte gäller för varje situation. Men enligt min erfarenhet, om vi kan hjälpa kunder med de mest komplexa utmaningarna, kan vi hjälpa alla kunder. 

Jag arbetar vanligtvis med 100 + kunder varje år. Även om varje organisation har unika egenskaper, är det intressant att se trender och likheter. Till exempel är en trend branschövergripande intresse för många kunder. När allt kommer om kan en bankfilial också vara ett kafé och ett allaktivitetshus. 

I min roll fokuserar jag på att hjälpa kunder att komma fram till den bästa tekniska lösningen för att ta itu med sina unika affärsmål. Officiellt fokuserar jag på identitet, säkerhet, sekretess och efterlevnad. Jag älskar det faktum att dessa berör allt vi gör. Det ger mig en möjlighet att få vara med i de flesta projekt. Detta håller mig ganska upptagen och njuta av denna roll. 

Jag bor i New York City (den bästa!) och verkligen njuta av mångfalden i sin kultur, mat och människor (inte trafik). Jag älskar att resa när jag kan och hoppas att se större delen av världen i min livstid. Jag forskar för närvarande en resa till Afrika för att lära mig om vilda djur.

## <a name="guiding-principles"></a>Riktlinjer 

- **Enkelt är ofta bättre** - Du kan göra (nästan) vad som helst med teknik. Det betyder inte att du ska. Särskilt i säkerhetsutrymmet, många kunder overengineer lösningar. Jag gillar [den här videon](https://www.youtube.com/watch?v=SOQgABDSYZE) från Googles Stripe konferens för att understryka denna punkt.
- **Människor, process, teknik** - [Design för människor](https://en.wikipedia.org/wiki/Human-centered_design) att förbättra processen, inte tech först. Det finns inga "perfekta" lösningar. Vi måste balansera olika riskfaktorer och beslut kommer att vara olika för varje företag. Alltför många kunder utformar en metod som användarna senare undviker.
- **Fokusera på "varför" först och "hur" senare** - Var irriterande 7 år gammal unge med en miljon frågor. Vi kan inte komma fram till rätt svar om vi inte vet de rätta frågorna att ställa. Massor av kunder gör antaganden om hur saker och ting måste fungera istället för att definiera affärsproblemet. Det finns alltid flera sökvägar som kan tas.
- **Lång svans av tidigare bästa praxis** - Inse att bästa praxis förändras med ljushastighet. Om du har tittat på Azure AD för mer än 3 månader sedan är du troligen inaktuella. Allt här kan komma att ändras efter publicering. "Bästa" alternativet idag kan inte vara samma 6 månader från nu.

## <a name="baseline-concepts"></a>Baslinjebegrepp

Hoppa inte över det här avsnittet. Jag tycker ofta att jag måste ta ett steg tillbaka till dessa ämnen, även för kunder som har använt molntjänster i flera år.
Tyvärr är språket inte ett exakt verktyg. Vi använder ganska ofta samma ord för att betyda olika begrepp eller olika ord för att betyda samma koncept. Jag använder ofta det här diagrammet nedan för att fastställa några baslinjeterminologi och "hierarkimodell".
<br><br>

![Illustration av klient, prenumeration, tjänst och data](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

När du lär dig att simma är det bättre att börja i poolen och inte mitt i havet. Jag försöker inte vara tekniskt korrekt med detta diagram. Det är en modell för att diskutera några grundläggande begrepp. 

I diagrammet:
- Klient = en instans av Azure AD. Det är högst upp i en hierarki, eller nivå 1 i diagrammet. Vi kan betrakta detta som "[gränsen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-directory-independence)" där allt annat inträffar[(Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) åt sidan). Alla Microsoft enterprise-molntjänster är en del av en av dessa klienter. Konsumenttjänsterna är separata. "Klient" visas i dokumentation som Office 365-klientorganisation, Azure-klientorganisation, WVD-klient, etc. Jag tycker ofta att dessa variationer orsakar förvirring för kunderna.
- Tjänster/prenumerationer, nivå 2 i diagrammet, tillhör en och endast en klient. De flesta SaaS-tjänster är 1:1 och kan inte röra sig utan migrering. Azure är annorlunda, du kan [flytta fakturering](https://docs.microsoft.com/azure/cost-management-billing/manage/billing-subscription-transfer) och/eller en [prenumeration](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) till en annan klient. Det finns många kunder som behöver flytta Azure-prenumerationer. Detta har olika konsekvenser. Objekt som finns utanför prenumerationen (till exempel RBAC- och Azure AD-objekt, inklusive grupper, appar, principer osv.) flyttas inte. Dessutom flyttas vissa tjänster (Azure Key Vault, Data Bricks, etc.) i ett icke-funktionellt tillstånd. Migrera inte tjänster utan ett bra affärsbehov. Vissa skript som kan vara till hjälp för migreringen [delas på GitHub](https://github.com/lwajswaj/azure-tenant-migration). 
- En viss tjänst har vanligtvis någon form av "sub-nivå" gräns, eller nivå 3 (L3). Detta är användbart att förstå för segregering av säkerhet, politik, styrning, etc. Tyvärr finns det inget enhetligt namn som jag känner till. Några exempelnamn för L3 är: Azure Subscription = [resurs](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [instans](https://docs.microsoft.com/dynamics365/admin/new-instance-management); Power BI = [arbetsyta](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces); Power Apps = [miljö](https://docs.microsoft.com/power-platform/admin/environments-overview); Etc.
- Nivå 4 är där de faktiska uppgifterna finns. Detta "dataplan" är ett komplext ämne. Vissa tjänster använder Azure AD för RBAC, andra inte. Jag ska diskutera det lite när vi kommer till delegation ämnen.

Några ytterligare begrepp som jag tycker att många kunder (och Microsoft-anställda) är förvirrade över eller har frågor om inkluderar följande:


- Vem som helst kan [skapa](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) många klienter [utan kostnad.](https://azure.microsoft.com/pricing/details/active-directory/) Du behöver inte en tjänst som är etablerad i den. Jag har dussintals. Varje klientnamn är unikt i Microsofts globala molntjänst (dvs. inga två klienter kan ha samma namn). De är alla i form av TenantName.onmicrosoft.com. Det finns också processer som skapar klienter automatiskt ([ohanterade klienter](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup)). Detta kan till exempel inträffa när en användare registrerar sig för en företagstjänst med en e-postdomän som inte finns i någon annan klientorganisation. 
- I en hanterad klient kan många [DNS-domäner](https://docs.microsoft.com/azure/active-directory/fundamentals/add-custom-domain) registreras i den. Detta ändrar inte det ursprungliga klientnamnet. Det finns för närvarande inget enkelt sätt att byta namn på en klient (annat än migrering). Även om klientens namn är tekniskt inte kritisk i dessa dagar, kan vissa tycker att detta är begränsande.
- Du bör reservera ett klientnamn för din organisation även om du ännu inte planerar att distribuera några tjänster. Annars kan någon ta det från dig och det finns ingen enkel process för att ta tillbaka det (samma problem som DNS-namn). Jag hör detta sätt alltför ofta från kunder. Vad din hyresgäst namn bör vara är en debatt ämne också.
- Om du äger DNS-namnområden bör du lägga till alla dessa i din klientorganisation.If you own DNS namespace(s), you should add all of these to your tenant(s). Annars kan man skapa en [ohanterad klient](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) med det här namnet som sedan orsakar störningar för att [göra den hanterad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover).
- DNS-namnområde (t.ex. contoso.com) kan tillhöra en och endast en klient. Detta har konsekvenser för olika scenarier (till exempel dela en e-postdomän under en sammanslagning eller förvärv, etc.) Det finns ett sätt att registrera en DNS-under (t.ex. div.contoso.com) i en annan klient, men det bör undvikas. Genom att registrera ett domännamn på den högsta nivån antas alla underdomäner tillhöra samma klient. I scenarier med flera innehavare (se nedan) skulle jag normalt rekommendera att använda ett annat domännamn på toppnivå (t.ex. contoso.ch eller ch-contoso.com).
- Vem ska "äga" en hyresgäst? Jag ser ofta kunder som inte vet vem som för närvarande äger deras hyresgäst. Det här är en stor röd flagga. Ring Microsoft-support ASAP. Lika problematiskt är när en tjänstägare (ofta en Exchange-administratör) har utsetts att hantera en klient. Klienten kommer att innehålla alla tjänster som du kanske vill ha i framtiden. Hyresgästen bör vara en grupp som kan fatta beslut för aktivering av alla molntjänster i en organisation. Ett annat problem är när en bostadsrättsgrupp uppmanas att hantera alla tjänster. Detta skalar inte för stora organisationer.
- Det finns inget begrepp om en sub / super hyresgäst. Av någon anledning fortsätter denna myt att upprepa sig. Detta gäller [även Azure AD B2C-klienter.](https://docs.microsoft.com/azure/active-directory-b2c/) Jag hör för många gånger: "Min B2C-miljö finns i min XYZ-klientorganisation" eller "Hur flyttar jag min Azure-klient till min Office 365-klientorganisation?"
- Detta dokument fokuserar främst på den kommersiella världsomspännande moln eftersom detta är vad de flesta kunder använder. Det är ibland bra att veta om [suveräna moln](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud). Suveräna moln har ytterligare konsekvenser för att diskutera vilka som inte är i fråga om denna diskussion.


## <a name="baseline-identity-topics"></a>Information om baslinjeidentitet

Det finns mycket dokumentation om Microsofts identitetsplattform – Azure Active Directory (Azure AD). För dem som just har börjat, känns det ofta överväldigande. Även efter att du lär dig om det, hålla jämna steg med ständig innovation och förändring kan vara en utmaning. I min kundinteraktioner jag ofta befinner mig fungerar som "översättare" mellan affärsmål och "Bra, bättre, bästa" metoder för att ta itu med dessa (liksom mänskliga "klippa anteckningar" för dessa ämnen). Det finns sällan ett perfekt svar och "rätt" beslut är en balans mellan olika riskfaktorer. Nedan är några av de vanligaste frågorna och områden förvirring jag tenderar att diskutera med kunder.

### <a name="provisioning"></a>Etableringen
Azure AD löser inte på grund av bristande styrning i din identitetsvärld! [Identitetsstyrning](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) bör vara en viktig del som är oberoende av eventuella molnbeslut. Styrningskraven ändras med tiden och därför är det ett program och inte ett verktyg. 

[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect) [vs. Microsoft Identity Manager](https://docs.microsoft.com/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) jämfört med något annat (tredje part eller anpassad)? Spara dig själv mycket huvudvärk nu och i framtiden och gå med Azure AD Connect. Det finns alla typer av smarts i detta verktyg för att ta itu med märkliga kundkonfigurationer och pågående innovationer. 

Vissa kantfall som kan köra mot en mer komplex arkitektur:
- Jag har flera AD-skogar utan nätverksanslutning mellan dessa. Det finns ett nytt alternativ som heter [CloudTableing](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning).
- Jag har inte Active Directory, inte heller vill jag installera det. Azure AD Connect kan konfigureras för synkronisering [från LDAP](https://docs.microsoft.com/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (partner kan krävas).
- Jag måste etablera samma objekt till flera klienter. Detta stöds inte tekniskt men beror på definitionen av "samma".

Ska jag anpassa standardsynkroniseringsregler[(filterobjekt,](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering) [ändra attribut,](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) [alternativt inloggnings-ID,](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-userprincipalname)etc.)? Undvik det! En identitetsplattform är bara lika värdefull som de tjänster som använder den. Även om du kan göra alla typer av nötaktig konfigurationer, för att svara på denna fråga måste du titta på effekten på program. Om du filtrerar e-postaktiverade objekt kommer GAL för onlinetjänster att vara ofullständiga. Om programmet är beroende av specifika attribut, kommer filtrering av dessa att ha oförutsägbar effekt. Etc. Det är inte ett identitetsteam beslut.

XYZ SaaS stöder JUST-in-Time (JIT) etablering, varför kräver du att jag synkroniserar? Se ovan. Många program behöver "profil" information för funktionalitet. Du kan inte ha en GAL om alla e-postaktiverade objekt inte är tillgängliga. Detsamma gäller [för användaretablering](https://docs.microsoft.com/azure/active-directory/app-provisioning/user-provisioning) i program som är integrerade med Azure AD.


### <a name="authentication"></a>Autentisering

[SYNKRONISERING av lösenord hash](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (PHS) jämfört med [genomströmningsautentisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) jämfört med [federation](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

Vanligtvis finns det en passionerad [debatt](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) kring federationen. Enklare är oftast bättre och därför använda PHS om du inte har en bra anledning att inte. Det är också möjligt att konfigurera olika autentiseringsmetoder för olika DNS-domäner i samma klient. 

Vissa kunder möjliggör federation + PHS främst för:
- Ett alternativ för att [återgå](https://docs.microsoft.com/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) till (för haveriberedskap) om federationstjänsten inte är tillgänglig.
- Ytterligare funktioner (t.ex.: [Azure AD DS)](https://docs.microsoft.com/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)och säkerhetstjänster (t.ex. [läckta autentiseringsuppgifter)](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials)
- Stöd för tjänster i Azure som inte förstår federerad autentisering (t.ex. [Azure Files](https://docs.microsoft.com/azure/storage/files/storage-files-active-directory-overview)

Jag går ofta kunder genom klientautentisering flöde för att klargöra några missuppfattningar. Resultatet ser ut som bilden nedan, vilket inte är lika bra som den interaktiva processen att komma dit.

:::image type="content" source="../media/solutions-architecture-center/identity-beyond-whiteboard-example.png" alt-text="exempel whiteboard konversation":::

Den här typen av whiteboardritning illustrerar var säkerhetsprinciper tillämpas inom flödet för en autentiseringsbegäran. I det här exemplet tillämpas principer som tillämpas via AD FS (Active Directory Federation Service) på den första tjänstbegäran, men inte efterföljande tjänstbegäranden. Detta är minst en anledning att flytta säkerhetskontroller till molnet så mycket som möjligt.

Vi har jagat drömmen om [enkel sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) (SSO) så länge jag kan minnas. Vissa kunder tror att de kan uppnå detta genom att välja "rätt" federation (STS) leverantör. Azure AD kan bidra avsevärt till att [aktivera SSO-funktioner,](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-sso-deployment) men ingen STS är magisk. Det finns för många "äldre" autentiseringsmetoder som fortfarande används för kritiska program. Utöka Azure AD med [partnerlösningar](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) kan ta itu med många av dessa scenarier. SSO är en strategi och en resa. Du kan inte komma dit utan att gå mot [standarder för applikationer](https://docs.microsoft.com/azure/active-directory/develop/v2-app-types). Relaterat till detta ämne är en resa till [lösenordslös](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) autentisering som inte heller har ett magiskt svar. 

[Multifaktorautentisering](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) är viktigt idag[(här](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) för mer). Lägg till [användarbeteendeanalys och](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) du har en lösning som förhindrar de flesta vanliga cyberattacker. Även konsumenttjänster går över till att kräva makroekonomiskt stöd. Ändå träffar jag fortfarande många kunder som inte vill flytta till [moderna autentiseringsmetoder.](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) Det största argumentet jag hör är att det kommer att påverka användare och äldre program. Ibland kan en bra kick hjälpa kunderna att gå vidare - Exchange Online [meddelade ändringar](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282). Många Azure [AD-rapporter](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) finns nu tillgängliga för att hjälpa kunder med den här övergången.



### <a name="authorization"></a>Tillstånd

Per [Wikipedia](https://en.wikipedia.org/wiki/Authorization), "att godkänna" är att definiera en åtkomstpolitik. Många människor ser på det som möjligheten att definiera åtkomstkontroller till ett objekt (fil, tjänst, etc.). I den nuvarande världen av cyberhot utvecklas detta koncept snabbt till en dynamisk politik som kan reagera på olika hotvektorer och snabbt justera åtkomstkontroller som svar på dessa. Om jag till exempel öppnar mitt bankkonto från en ovanlig plats får jag ytterligare bekräftelsesteg. För att närma oss detta måste vi inte bara beakta själva politiken utan ekosystemet för metoder för att upptäcka hot och signalera korrelation.

Principmotorn för Azure AD implementeras med principer [för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Detta system är beroende av information från en mängd andra system för att upptäcka hot för att fatta dynamiska beslut. En enkel vy skulle vara ungefär som följande illustration.

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-illustration-3.png" alt-text="Principmotor i Azure AD":::

Genom att kombinera alla dessa signaler tillsammans kan dynamiska principer som dessa:
- Om ett hot upptäcks på enheten reduceras åtkomsten till data till webben endast utan att du kan hämta dem.
- Om du laddar ner en ovanligt hög mängd data, allt du laddar ner kommer att krypteras och begränsas.
- Om du öppnar en tjänst från en ohanterade enhet blockeras du från mycket känsliga data men får komma åt icke-begränsade data utan möjlighet att kopiera den till en annan plats.

Om du håller med om den här utökade definitionen av auktorisering måste du implementera ytterligare lösningar. Vilka lösningar du implementerar beror på hur dynamisk du vill att principen ska vara och vilka hot du vill prioritera. Några exempel på sådana system är:
- [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/) 
- [Avancerat hotskydd](https://docs.microsoft.com/azure-advanced-threat-protection/) i Azure (Azure ATP)
- [Avancerat hotskydd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för Microsoft Defender (Microsoft Defender ATP)
- [Microsoft 365 Avancerat skydd mot hot](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Microsoft 365 ATP)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) (MCAS)
- [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide) (MTP)
- [Microsoft Intune](https://docs.microsoft.com/mem/intune/)
- [Microsoft InformationSskydd](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) (MIP)
- [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/) 

Förutom Azure AD har naturligtvis olika tjänster och program sina egna specifika auktoriseringsmodeller. Några av dessa diskuteras senare i delegationssektionen.

### <a name="audit"></a>Revision
Azure AD har detaljerade [gransknings- och](https://docs.microsoft.com/azure/active-directory/reports-monitoring/) rapporteringsfunktioner. Detta är dock vanligtvis inte den enda informationskälla som behövs för att fatta säkerhetsbeslut. Se mer diskussion om detta i delegeringssektionen.

## <a name="there-is-no-exchange"></a>Det finns ingen Exchange

Få inte panik! Detta betyder inte att Exchange är föråldrad (eller SharePoint, etc.) Det är fortfarande en kärntjänst. Vad jag menar är, ganska länge nu, teknikleverantörer har övergången användarupplevelser (UX) att omfatta komponenter i flera tjänster. I Microsoft 365 är ett enkelt exempel "[moderna bilagor](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)" där bifogade filer till e-post lagras i SharePoint Online eller OneDrive för företag. 

:::image type="content" source="../media/solutions-architecture-center/modern-attachments.png" alt-text="bifoga en fil i ett e-postmeddelande":::


Om du tittar på Outlook-klienten kan du se många tjänster som är "anslutna" som en del av den här upplevelsen, inte bara Exchange. Detta inkluderar Azure AD-, Microsoft-sökning-, app-, profil-, efterlevnads- och Office 365-grupper. 

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png" alt-text="Outlook-gränssnitt med bildtexter":::

Läs om [Microsoft Fluid Framework](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) för förhandsgranskning av kommande funktioner. I förhandsversion nu kan jag läsa och svara på Teams-konversationer direkt i Outlook. Faktum är att [Teams-klienten](https://products.office.com/microsoft-teams/download-app) är ett av de mer framträdande exemplen på denna strategi. 

Totalt sett blir det svårare att dra en tydlig linje mellan Office 365 och andra tjänster i Microsoft-moln. Jag ser det som en stor fördel för kunderna eftersom de kan dra nytta av total innovation över allt vi gör även om de använder en komponent. Ganska cool och har långtgående konsekvenser för många kunder.

Idag tycker jag att många kund-IT-grupper är uppbyggda kring "produkter". Det är logiskt för en lokal värld eftersom du behöver en expert för varje specifik produkt. Men jag är helt glad att jag inte behöver felsöka en Active Directory eller Exchange-databas någonsin igen eftersom dessa tjänster har flyttat till molnet. Automation (som moln typ av är) tar bort vissa repetitiva manuella jobb (se vad som hände med fabriker). Dessa ersätts dock med mer komplexa krav för att förstå interaktion mellan tjänster, effekter, affärsbehov etc. Om du är villig att [lära dig](https://docs.microsoft.com/learn/)finns det stora möjligheter som aktiveras av molnomvandling. Innan jag hoppar in i tekniken pratar jag ofta med kunder om att hantera förändringar i IT-kompetens och teamstrukturer.

Om du vill ha alla SharePoint-fan-people och utvecklare kan du sluta fråga "Hur kan jag göra XYZ i SharePoint online?" Använd [Power Automate](https://docs.microsoft.com/power-automate/) (aka Flow) för arbetsflöde, det är en mycket mer kraftfull plattform. Använd [Azure Bot Framework](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0) för att skapa en bättre UX för din 500K-objektlista. Börja använda [Microsoft Graph](https://developer.microsoft.com/graph/) i stället för CSOM. [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) innehåller SharePoint men också en värld mer. Det finns många andra exempel jag kan lista. Det finns ett stort och underbart universum där ute. Öppna dörren och [börja utforska](https://docs.microsoft.com).

Den andra gemensamma effekten är på området för efterlevnad. Denna strategi för tvärtjänster verkar helt förvirra många efterlevnadspolicyer. Jag ser organisationer som säger, "Jag måste journal alla e-postkommunikation till ett eDiscovery system." Vad betyder detta egentligen när e-post inte längre bara är e-post utan ett fönster till andra tjänster? Office 365 har en övergripande metod för [efterlevnad](https://docs.microsoft.com/microsoft-365/compliance/), men det är ofta mycket svårare att ändra personer och processer än teknik.

Det finns många andra människor och processkonsekvenser. Jag anser att detta är ett kritiskt och underdiskuterat område. Kanske mer i en annan artikel.

## <a name="tenant-structure-options"></a>Alternativ för hyresgäststruktur

### <a name="single-tenant-vs-multi-tenant"></a>En klient kontra flera innehavare

I allmänhet bör de flesta kunder bara ha en produktionsklient. Det finns många anledningar till varför flera hyresgäster är utmanande (ge det en [Bing-sökning)](https://www.bing.com/search?q=office%20365%20multiple%20tenants)eller läs detta [vitbok](https://aka.ms/multi-tenant-user). Samtidigt har många företagskunder jag arbetar med en annan (liten) hyresgäst för IT-lärande, testning och experiment. Azure [Lighthouse](https://azure.microsoft.com/services/azure-lighthouse/)med flera innehavare . Office 365 och många andra SaaS-tjänster har gränser för scenarier mellan innehavare. Det finns mycket att tänka på i [Azure AD B2B-scenarier.](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)

Många kunder hamnar med flera produktionshyresgäster efter en sammanslagning och förvärv (M&A) och vill konsolidera. Idag är det inte enkelt och skulle kräva Microsoft Consulting Services (MCS) eller en partner plus programvara från tredje part. Det pågår ett ingenjörsarbete för att hantera olika scenarier med kunder med flera innehavare i framtiden. 

Vissa kunder väljer att gå med mer än en klient. Detta bör vara ett mycket noggrant beslut och nästan alltid affärsmässiga skäl driven! Några exempel är följande:
- En holdingtyp företagsstruktur där enkelt samarbete mellan olika enheter inte krävs och det finns starka administrativa och andra isoleringsbehov.
- Efter ett förvärv fattas ett affärsbeslut för att hålla två enheter åtskilda.
- Simulering av en kunds miljö som inte ändrar kundens produktionsmiljö. 
- Utveckling av mjukvara för kunder.

I dessa scenarier för flera innehavare vill kunderna ofta behålla vissa konfigurationer på samma sätt mellan klienter eller rapportera om konfigurationsändringar och drifts. Detta innebär ofta att gå från manuella ändringar till konfiguration som kod. Microsoft Premiere-supporten erbjuder en workshop för dessa [https://Microsoft365dsc.com](https://Microsoft365dsc.com)typer av krav baserat på den här offentliga IP:et: .


### <a name="multi-geo"></a>Multi-Geo 

Till [Multi-Geo](https://docs.microsoft.com/office365/enterprise/office-365-multi-geo) eller inte till Multi-Geo, det är frågan. Med Office 365 Multi-Geo kan du etablera och lagra data i vila på de geografiska platser som du har valt för att uppfylla kraven på [databestämmelse.](https://docs.microsoft.com/office365/enterprise/o365-data-locations) Det finns många missuppfattningar om denna förmåga. Tänk på följande: 
- Det ger inte prestandafördelar. Det kan göra prestanda sämre om [nätverksdesignen](https://aka.ms/office365networking) inte är korrekt. Få enheter "nära" till Microsoft-nätverket, inte nödvändigtvis till dina data.
- Det är inte en lösning för [GDPR-efterlevnad.](https://www.microsoft.com/trust-center/privacy/gdpr-overview) GDPR fokuserar inte på datasuveränitet eller lagringsplatser. Det finns andra ramar för efterlevnad för detta.
- Den löser inte delegering av administration (se nedan) eller [informationshinder](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).
- Det är inte samma sak som flera innehavare och kräver ytterligare [arbetsflöden för användaretablering.](https:/docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation)
- Den flyttar inte [din klient (din](https://docs.microsoft.com/office365/enterprise/moving-data-to-new-datacenter-geos) Azure AD) till en annan geografi. 

## <a name="delegation-of-administration"></a>Delegation av administration

I de flesta stora organisationer är åtskillnad av arbetsuppgifter och rollbaserad åtkomstkontroll (RBAC) en nödvändig verklighet. Jag ska be om ursäkt i förväg. Detta är inte så enkelt som vissa kunder vill att det ska vara. Kund, juridik, efterlevnad och andra krav är olika och ibland motstridiga runt om i världen. Enkelhet och flexibilitet är ofta på motsatta sidor av varandra. Missförstå mig inte, vi kan göra ett bättre jobb med det här. Det har skett (och kommer att bli) betydande förbättringar över tiden. Besök ditt lokala [Microsoft Technology Center](https://www.microsoft.com/mtc) för att räkna ut den modell som passar dina affärskrav utan att läsa 379230-dokument! Här ska jag fokusera på vad du ska tänka på och inte varför det är så här. Nedan finns fem olika områden att planera för och några av de vanligaste frågorna jag har stött på.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD- och Microsoft 365-administrationscenter

Det finns en lång och växande lista över [inbyggda roller](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Varje roll består av en lista över rollbehörigheter grupperade tillsammans för att tillåta att specifika åtgärder utförs. Du kan se dessa behörigheter på fliken "Beskrivning" i varje roll. Alternativt kan du se en mer läsbar version av dessa i Microsoft 365 Admin Center. Definitionerna för inbyggda roller kan inte ändras. Jag i allmänhet, gruppera dessa i tre kategorier:

- **Global administratör** – Den här "alla kraftfulla" roll bör vara [mycket skyddad](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) precis som du skulle i andra system. Typiska rekommendationer är: ingen permanent tilldelning och använda Azure AD Privileged Identity Management (PIM); stark autentisering; Etc. Intressant nog ger den här rollen dig inte tillgång till allt som standard. Vanligtvis ser jag förvirring om efterlevnadsåtkomst och Azure-åtkomst, som beskrivs senare. Den här rollen kan dock alltid tilldela åtkomst till andra tjänster i klienten. 
- **Specifika tjänstadministratörer** – Vissa tjänster (Exchange, SharePoint, Power BI osv.) använder administrationsroller på hög nivå från Azure AD. Detta är inte konsekvent för alla tjänster och det finns fler tjänstspecifika roller som diskuteras senare.
- **Funktionell** - Det finns en lång (och växande) lista över roller med fokus på specifika operationer (gäst inbjudna, etc.). Periodvis läggs fler av dessa till baserat på kundernas behov.

Det är inte möjligt att delegera allt (även om gapet minskar), vilket innebär att den globala administratörsrollen skulle behöva användas ibland. Konfiguration som kod och automatisering bör övervägas i stället för personer som är medlemmar i den här rollen.

**Microsoft**365-administrationscentret har ett mer användarvänligt gränssnitt men har en delmängd av funktioner jämfört med Azure AD-administratörsupplevelsen. Båda portalerna använder samma Azure AD-roller, så ändringar sker på samma plats. Om du vill ha ett administratörsgränssnitt för identitetshantering [https://aad.portal.azure.com](https://aad.portal.azure.com)utan all Azure-röran använder du . 

Vad heter det? Gör inte antaganden från namnet på rollen. Språket är inte ett mycket exakt verktyg. Målet bör vara att definiera åtgärder som måste delegeras innan du tittar på vilka roller som behövs. Att lägga till någon i rollen "Säkerhetsläsare" gör inte att de ser säkerhetsinställningar över allt. 

Möjligheten att skapa [anpassade roller](https://docs.microsoft.com/azure/active-directory/users-groups-roles/roles-custom-overview) är en vanlig fråga. Detta är begränsat i Azure AD idag (se nedan) men kommer att växa i funktioner över tiden. Jag tänker på dessa som tillämpliga på funktioner i Azure AD och kanske inte spänner över "nedåt" hierarkimodellen (diskuteras ovan). När jag tar itu med "anpassade", jag tenderar att gå tillbaka till min huvudman för "enkel är bättre."

En annan vanlig fråga är möjligheten att begränsa roller till en delmängd av en katalog. Ett exempel är något i stil med "Helpdesk-administratör för användare i EU". [Administrativa enheter](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-administrative-units) (AU) är avsedda att ta itu med detta. Som ovan tänker jag på dessa som tillämpliga på funktioner i Azure AD och kanske inte sträcker sig "nedåt". Naturligtvis är vissa roller inte meningsfullt att omfattning (globala administratörer, administratörer tjänst, etc.)

Idag kräver alla dessa roller direkt medlemskap (eller dynamisk tilldelning om du använder [Azure AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/)). Det innebär att kunder måste hantera dessa direkt i Azure AD och dessa kan inte baseras på ett medlemskap i säkerhetsgruppen. Jag är inte ett av att skapa skript för att hantera dessa eftersom det skulle behöva köras med förhöjda rättigheter. Jag rekommenderar i allmänhet API-integrering med processsystem som ServiceNow eller med partnerstyrningsverktyg som Saviynt. Det pågår ingenjörsarbete för att ta itu med detta över tid.

Jag nämnde [Azure AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) ett par gånger. Det finns en motsvarande PAM-lösning (Microsoft Identity Manager) [för](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) lokala kontroller. Du kanske också vill titta på arbetsstationer för [privilegierad åtkomst](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) och [Azure AD Identity Governance](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview). Det finns en mängd olika verktyg från tredje part som också kan aktivera just-in-time, just-enough och dynamisk rollhöjd. Detta är vanligtvis en del av en större diskussion för att säkra en miljö. 

Ibland kräver scenarier för att lägga till en extern användare i en roll (se avsnittet flera innehavare ovan). Den här arbeten rättvis böter. [Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/) är ett annat stort och roligt ämne att gå igenom kunder, kanske i en annan artikel.

### <a name="security-and-compliance-center-scc"></a>Säkerhets- och efterlevnadscenter (SCC)

[Behörigheter i Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) är en samling "rollgrupper" som är separata och skiljer sig från Azure AD-roller. Detta kan vara förvirrande eftersom vissa av dessa rollgrupper har samma namn som Azure AD-roller (till exempel Säkerhetsläsare), men de kan ha olika medlemskap. Jag föredrar användningen av Azure AD-roller. Varje rollgrupp består av en eller flera "roller" (se vad jag menar med att återanvända samma ord?) och har medlemmar från Azure AD som är e-postaktiverade objekt. Du kan också skapa en rollgrupp med samma namn som en roll som kanske eller kanske inte innehåller den rollen (undvik den förvirringen).

På sätt och vis är detta en utveckling av exchange-förebilden. Exchange Online har dock ett eget gränssnitt för [hantering av rollgrupper.](https://docs.microsoft.com/exchange/permissions-exo) Vissa rollgrupper i Exchange Online är låsta och hanterade från Azure AD eller Security & Compliance Center, men andra kan ha samma eller liknande namn och hanteras i Exchange Online (lägga till förvirring). Jag rekommenderar att du undviker att använda Exchange Online-användargränssnittet om du inte behöver utrymme för Exchange-hantering.

Du kan inte skapa anpassade roller. Roller definieras av tjänster som skapats av Microsoft och kommer att växa när nya tjänster introduceras. Detta liknar i konceptet [med roller som definierats av program](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) i Azure AD. När nya tjänster är aktiverade måste ofta nya rollgrupper skapas för att ge eller delegera åtkomst till dessa (till exempel [insiderriskhantering).](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management)

Dessa rollgrupper kräver också direkt medlemskap och kan inte innehålla Azure AD-grupper. Tyvärr stöds inte dessa rollgrupper i dag av Azure AD PIM. Precis som Azure AD-roller rekommenderar jag hantering av dessa via API:er eller en partnerstyrningsprodukt som Saviynt eller andra.

Säkerhetsroller & Compliance Center-roller sträcker sig över Microsoft 365 och du kan inte begränsa dessa rollgrupper till en delmängd av miljön (som du kan med administrativa enheter i Azure AD). Många kunder frågar hur de kan delegera under. Till exempel "skapa en DLP-policy endast för EU-användare." Idag, om du har rättigheter till en specifik funktion i Security & Compliance Center, har du rättigheter till allt som omfattas av den här funktionen i klienten. Många principer har dock funktioner för att rikta in sig på en delmängd av miljön (till exempel "gör dessa [etiketter](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy) tillgängliga endast för dessa användare"). Korrekt styrning och kommunikation är en viktig komponent för att undvika konflikter. Vissa kunder väljer att implementera en metod för konfiguration som kod för att hantera underdelegering i Security & Compliance Center. Vissa särskilda tjänster stöder underdelegering (se nedan). 

Det är värt att notera att kontroller som för närvarande hanteras via Security & Compliance Center (protection.office.com) håller på att migreras till två separata administratörsportaler: security.microsoft.com och compliance.microsoft.com. Förändring är den enda konstanten!

### <a name="service-specific"></a>Tjänstespecifika

Som tidigare nämnts, många kunder är ute efter att uppnå en mer detaljerad delegering modell. Ett vanligt exempel: "Hantera XYZ-tjänsten endast för Division X-användare och platser" (eller någon annan dimension). Möjligheten att göra detta beror på varje tjänst och är inte konsekvent mellan tjänster och funktioner. Dessutom kan varje tjänst ha en separat och unik RBAC-modell. Istället för att diskutera alla dessa (det kommer att ta evigheter), jag lägger till relevanta länkar för varje tjänst. Detta är inte en fullständig lista, men det kommer att komma igång.

- **Byt online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators) 
- **Microsoft-team**  -  [ https://docs.microsoft.com/microsoftteams/itadmin-readiness](https://docs.microsoft.com/microsoftteams/itadmin-readiness )
- **Ediscovery** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](https://docs.microsoft.com/microsoft-365/compliance/) 
  + **Filtrering av**  -  [ https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search behörighet](https://docs.microsoft.com/microsoft-365/compliance/)
  + **Efterlevnadsgränser**  -  [ https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries )
  + **Avancerad eDiscovery**  -  [ https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 )
- **Yammer (yammer)** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins) 
- **Multi-geo** - [https://docs.microsoft.com/office365/enterprise/add-a-sharepoint-geo-admin](https://docs.microsoft.com/office365/enterprise/add-a-sharepoint-geo-admin) 
- **Dynamics 365** –[https://docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/) <br>
  Den här länken är till dokumentationens rot. Det finns flera typer av tjänster med variationer i administratörs-/delegeringsmodellen.
- **Power Platform** -  [ Kraftplattformhttps://docs.microsoft.com/power-platform/admin/admin-documentation](https://docs.microsoft.com/power-platform/admin/admin-documentation )
  + **Power-appar**  -  [ https://docs.microsoft.com/power-platform/admin/wp-security](https://docs.microsoft.com/power-platform/admin/wp-security ) <br>
    Det finns flera typer med variationer i administratörs-/delegeringsmodellerna.
  + **Power Automate** -  [ Strömautomathttps://docs.microsoft.com/power-automate/environments-overview-admin](https://docs.microsoft.com/power-automate/environments-overview-admin )
  + **PowerBI (på andra)**  -  [ https://docs.microsoft.com/power-bi/service-admin-governance](https://docs.microsoft.com/power-bi/service-admin-governance ) <br>
Säkerhet och delegering av dataplattformar (vilken Power BI är en komponent) är ett komplext område.
- **MEM/Intune**  -  [ https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control )
- **Microsoft Defender ATP**  -  [ https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles )
- **Microsofts hotskydd** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions)
- **Säkerhet i Microsoft Cloud-appar** - [https://docs.microsoft.com/cloud-app-security/manage-admins](https://docs.microsoft.com/cloud-app-security/manage-admins)
- **Stream** -  [ Strömmahttps://docs.microsoft.com/stream/assign-administrator-user-role](https://docs.microsoft.com/stream/assign-administrator-user-role )
- **Informationshinder**  -  [ https://docs.microsoft.com/microsoft-365/compliance/information-barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers )

För övrigt har sökning i Docs varit [https://docs.microsoft.com/](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)riktigt bra på sistone - . 


### <a name="activity-logs"></a>Aktivitetsloggar
Office 365 har en [enhetlig granskningslogg](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance). Det är en mycket [detaljerad logg,](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)men läs inte för mycket i namnet. Den kanske inte innehåller allt du vill ha eller behöver för dina säkerhets- och efterlevnadsbehov. Dessutom är vissa kunder verkligen intresserade av [Avancerad granskning](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit). 

Exempel på Microsoft 365-loggar som nås via andra API:er är följande:
- [Azure AD](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) (aktiviteter som inte är relaterade till Office 365)
- [Spårning av exchange-meddelanden](https://docs.microsoft.com/powershell/module/exchange/mail-flow/get-messagetrace?view=exchange-ps)
- Hot/UEBA-system som beskrivs ovan (till exempel Azure AD Identity Protection, Microsoft Cloud App Security, Microsoft Defender ATP, etc.)
- [Microsofts informationsskydd](https://docs.microsoft.com/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide)
- [Microsoft Defender Avancerat skydd.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft-diagram](https://graph.microsoft.com)

Det är viktigt att först identifiera alla loggkällor som behövs för ett säkerhets- och efterlevnadsprogram. Observera också att olika loggar har olika online-kvarhållningsgränser. 

Ur administratörsdelegeringsperspektivet har de flesta microsoft 365-aktivitetsloggar ingen inbyggd RBAC-modell. Om du har behörighet att se en logg kan du se allt i den. Ett vanligt exempel på ett kundkrav är: "Jag vill bara kunna fråga aktivitet för EU-användare" (eller någon annan dimension). För att uppnå detta krav måste vi överföra loggar till en annan tjänst. I Microsoft-molnet rekommenderar vi att du överför det till [antingen Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview) eller Log [Analytics](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace). 

Diagram på hög nivå:

![diagram över loggflödet på hög nivå](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

Diagrammet ovan representerar inbyggda funktioner för att skicka loggar till Event Hub och/eller Azure Storage och/eller Azure Log Analytics. Inte alla system inkluderar denna out-of-the-box ännu. Men det finns andra metoder för att skicka dessa loggar till samma databas. Se Till exempel [Skydda dina team med Azure Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761).

Kombinera alla loggar till en lagringsplats inkluderar extra nytta, såsom korskorrelationer, anpassade lagringstider, utöka med data som behövs för att stödja RBAC-modellen, etc. När data finns i det här lagringssystemet kan du skapa en PowerBI-instrumentpanel (eller en annan typ av visualisering) med en lämplig RBAC-modell.

Loggar behöver inte endast dirigeras till ett ställe. Det kan också vara fördelaktigt att integrera [Office 365-loggar med Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) eller en anpassad RBAC-modell i Power [BI](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics?view=o365-worldwide). Olika databaser har olika fördelar och målgrupper.

Det är värt att nämna att det finns ett mycket rikt inbyggt analyssystem för säkerhet, hot, sårbarheter, etc. i en tjänst som heter [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide).

Många stora kunder vill överföra dessa loggdata till ett tredjepartssystem (till exempel SIEM). Det finns olika metoder för detta, men i allmänhet [Azure Event Hub](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) och [Graph](https://docs.microsoft.com/graph/security-integration) är bra utgångspunkter.


### <a name="azure"></a>Azure 
Jag får ofta frågan om det finns ett sätt att skilja hög behörighet roller mellan Azure AD, Azure och SaaS (t.ex.: Global Administratör för Office 365 men inte Azure).  Inte riktigt.  Arkitektur med flera innehavare behövs om fullständig administrativ separation krävs, men det ger betydande [komplexitet](https://aka.ms/multi-tenant-user) (se ovan). Alla dessa tjänster är en del av samma säkerhets-/identitetsgräns (titta på hierarkimodellen ovan).  

Det är viktigt att förstå relationer mellan olika tjänster i samma klient. Jag arbetar med många kunder som bygger affärslösningar som spänner över Azure, Office 365 och Power Platform (och ofta även lokala och tredje parts molntjänster). Ett vanligt exempel: 
-   Jag vill samarbeta i en uppsättning dokument/bilder/etc (Office 365)
-   skicka var och en av dem genom en godkännandeprocess (Power Platform)
-   När alla komponenter har godkänts, montera dessa i en enhetlig slutprodukt (s) (Azure) [Microsoft Graph API](https://docs.microsoft.com/azure/active-directory/develop/microsoft-graph-intro) är din bästa vän för dessa.  Inte omöjligt, men betydligt mer komplicerat att utforma en lösning som spänner över [flera klienter](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).

Azure Role-Based Access Control (RBAC) möjliggör finkornig åtkomsthantering för Azure. Med hjälp av RBAC kan du hantera åtkomst till resurser genom att ge användarna minst behörighet som behövs för att utföra sina jobb. Information är utanför omfånget för det här dokumentet, men mer information om RBAC finns [i Vad är rollbaserad åtkomstkontroll (RBAC) i Azure?](https://docs.microsoft.com/azure/role-based-access-control/overview) RBAC är viktigt men bara en del av styrningsövervägandena för Azure. [Cloud Adoption Framework](https://docs.microsoft.com/azure/cloud-adoption-framework/govern/) är en bra utgångspunkt för att lära dig mer. Jag gillar hur min vän, Andres Ravinet går kunder steg för steg men olika komponenter för att besluta om metoden. Hög nivå vy för olika element (inte lika bra som processen för att komma till faktiska kundmodell) är ungefär så här:

:::image type="content" source="../media/solutions-architecture-center/identity-beyond-illustration-5.png" alt-text="vy på hög nivå av Azure-komponenter för delegerad administration":::

Som du kan se ovan bör många andra tjänster betraktas som en del av designen (t.ex.: [Azure-principer,](https://docs.microsoft.com/azure/governance/policy/overview) [Asure Blueprints](https://docs.microsoft.com/azure/governance/blueprints/overview), [Hanteringsgrupper,](https://docs.microsoft.com/azure/governance/management-groups/)etc.)

## <a name="conclusion"></a>Sammanfattning
Började som en kort sammanfattning, hamnade längre än jag väntat.  Jag hoppas att du nu är redo att ge sig in i en djup se att skapa delegering modell för din organisation.  Denna konversation är mycket vanligt med kunder. Det finns ingen modell som fungerar för alla. Väntar på några planerade förbättringar från Microsoft engineering innan du dokumenterar vanliga mönster som vi ser bland kunder. Under tiden kan du arbeta med ditt Microsoft-kontoteam för att ordna ett besök på närmaste [Microsoft Technology Center](https://www.microsoft.com/mtc).  Vi ses där!


