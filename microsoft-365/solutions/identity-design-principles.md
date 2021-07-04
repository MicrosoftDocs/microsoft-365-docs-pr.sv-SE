---
title: Microsoft 365 planering av företagsresurser – säkerhetsarkitektur
description: Läs mer om de viktigaste designstrategierna för Microsoft Enterprise-arkitekturen från Alex Shteynberg, Technical Principal Architect på Microsoft.
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
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: b22a3b8fc73ca1825f07dda5b84c85e2d2a68805
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289745"
---
# <a name="to-identity-and-beyondone-architects-viewpoint"></a>För identitet och vidarestöld – En arkitekts byggnad

I den här artikeln [beskriver Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/), Principal Technical Architect på Microsoft de bästa designstrategierna för företag som inför Microsoft 365 och andra Microsoft-molntjänster.

## <a name="about-the-author"></a>Om författaren

![Alex Shteynberg-foto](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

Jag är principal Technical Architect på [Microsoft Technology Center i New](https://www.microsoft.com/mtc?rtc=1)York. Jag arbetar oftast med stora kunder och komplexa krav. Min familj och mina åsikter baseras på dessa interaktioner och gäller kanske inte i alla situationer. Men om vi kan hjälpa kunder med de mest komplexa utmaningarna kan vi hjälpa alla kunder.

Jag arbetar normalt med fler än 100 kunder per år. Varje organisation har unika egenskaper, men det är intressant att se trender och vanliga behov. En trend är till exempel branschledande intresse för många kunder. En bankkontor kan ju också vara ett café och ett community center.

I min roll fokuserar jag på att hjälpa kunder att ta fram den bästa tekniska lösningen för att hantera sina unika affärsmål. Officiellt fokuserar jag på identitet, säkerhet, sekretess och efterlevnad. Jag gillar att dessa rör vid allt vi gör. Det ger mig möjlighet att vara engagerad i de flesta projekt. Det håller mig upptagen och gillar den här rollen.

Jag bor i New York (den bästa!) och tycker om dess kultur, mat och människor (inte trafik). Jag älskar att resa när jag kan och hoppas att se det mesta av världen under min livslängd. Jag letar just nu efter en resa till Afrika för att lära mig mer om djurliv.

## <a name="guiding-principles"></a>Vägledande principer

- **Enkelt är ofta bättre:** Du kan göra (nästan) allt med teknik, men det betyder inte att du ska göra det. Särskilt när det gäller säkerhetsutrymmet är det många kunder som överengineerarlösningar. Jag gillar [den här videon](https://www.youtube.com/watch?v=SOQgABDSYZE) från Googles Stripe-konferens till att understryka det här.
- **Personer, processer, teknik:** [Design för att förbättra](https://en.wikipedia.org/wiki/Human-centered_design) processen, inte tech först. Det finns inga "perfekta" lösningar. Vi behöver balansera olika riskfaktorer och beslut kommer att vara olika för varje företag. För många kunder utformar en metod som deras användare senare undviker.
- **Fokusera på "varför" först och "hur"** senare: Var den irriterande 7-åring som har en miljon frågor. Vi kan inte få fram rätt svar om vi inte känner till rätt frågor att ställa. Många kunder gör antaganden om hur det måste fungera i stället för att definiera affärsproblemet. Det finns alltid flera sökvägar som kan användas.
- **Long tail of past best practices**: Recognize that best practices are changing at light speed. Om du har tittat på Azure AD för mer än tre månader sedan är du förmodligen in gammal. Allt här kan komma att ändras efter publicering. Alternativet "Bäst" idag kanske inte är samma för sex månader från och med nu.

## <a name="baseline-concepts"></a>Grundbegrepp

Hoppa inte över det här avsnittet. Jag tycker ofta att jag måste gå tillbaka till de här avsnitten, även för kunder som har använt molntjänster i många år.
Språket är tyvärr inte ett exakt verktyg. Vi använder ofta samma ord för att betyda olika begrepp eller olika ord för att betyda samma koncept. I det här diagrammet nedan använder jag ofta terminologi och hierarkimodell.
<br><br>

![Illustration av klientorganisation, prenumeration, tjänst och data](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)

<br>

När du lär dig att simning är det bättre att börja i poolen och inte mitt på havet. Jag försöker inte vara tekniskt exakt med det här diagrammet. Det är en modell för att diskutera några grundläggande begrepp.

I diagrammet:

- Klientorganisation = en instans av Azure AD. Den är högst upp i en hierarki eller på Nivå 1 i diagrammet. Vi kan betrakta det som[den](/azure/active-directory/users-groups-roles/licensing-directory-independence)" gräns " där allt annat förekommer[(undan Azure AD B2B).](/azure/active-directory/b2b/what-is-b2b) Alla Microsoft Enterprise-molntjänster ingår i någon av dessa klientorganisationar. Konsumenttjänsterna är separata. "Klient" visas i dokumentationen som Office 365, Azure-klientorganisation, WVD-klientorganisation och så vidare. Jag tycker ofta att de här varianterna är förvirrande för kunderna.
- Tjänster/prenumerationer, nivå 2 i diagrammet, tillhör en och bara en klientorganisation. De flesta SaaS-tjänster är 1:1 och kan inte flytta utan migrering. Azure är annorlunda, du kan [flytta fakturering och/eller](/azure/cost-management-billing/manage/billing-subscription-transfer) en [prenumeration till en](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) annan klientorganisation. Det finns många kunder som behöver flytta Azure-prenumerationer. Det här har sina olika konsekvenser. Objekt som finns utanför prenumerationen flyttas inte (till exempel rollbaserad åtkomstkontroll eller Azure RBAC och Azure AD-objekt, inklusive grupper, appar, principer och så vidare). Dessutom en del tjänster (till exempel Azure-nyckelvalv, Data brickor och så vidare). Migrera inte tjänster utan att ha behov av bra affärer. Vissa skript som kan vara användbara för migreringen [delas på GitHub](https://github.com/lwajswaj/azure-tenant-migration).
- En viss tjänst har vanligtvis någon typ av "undernivågräns" eller nivå 3 (L3). Det är användbart för att separering av säkerhet, policyer, styrning och så vidare. Tyvärr finns det inget enhetligt namn som jag känner till. Namnen på L3 är till exempel: Azure-prenumeration = [resurs](/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [instans](/dynamics365/admin/new-instance-management); Power BI = [arbetsyta](/power-bi/service-create-the-new-workspaces); Power Apps = [miljö](/power-platform/admin/environments-overview); och så vidare.
- På nivå 4 finns de verkliga data. Det här "dataplan" är ett komplext ämne. Vissa tjänster använder Azure AD för RBAC, andra använder inte tjänsten. Jag ska diskutera det lite när vi kommer till delegeringsavsnitt.

Några ytterligare begrepp som jag tycker att många kunder (och Microsoft-anställda) är förvirrade över eller har frågor om är bland annat följande:

- Alla kan [skapa](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) flera klientorganisationar [utan kostnad.](https://azure.microsoft.com/pricing/details/active-directory/) Du behöver inte tillhandahålla en tjänst i den. Jag har många. Varje klientorganisations namn är unikt i Microsofts globala molntjänst (med andra ord kan inte två klientorganisationar ha samma namn). Alla har samma format som TenantName.onmicrosoft.com. Det finns även processer som skapar klientorganisation automatiskt[(ohanterade klientorganisationar).](/azure/active-directory/users-groups-roles/directory-self-service-signup) Det här kan till exempel inträffa när en användare registrerar sig för en företagstjänst med en e-postdomän som inte finns i någon annan klientorganisation.
- I en hanterad klientorganisation kan [många DNS-domäner](/azure/active-directory/fundamentals/add-custom-domain) registreras i den. Detta ändrar inte det ursprungliga klientnamnet. Det finns för närvarande inget enkelt sätt att byta namn på en klientorganisation (förutom migrering). Även om innehavarnamnet tekniskt sett inte är kritiskt i dessa dagar kan vissa se det som begränsat.
- Du bör reservera ett klientnamn för organisationen även om du ännu inte planerar att distribuera några tjänster. Annars kan någon ta det från dig och det finns ingen enkel process för att ta tillbaka den (samma problem som DNS-namn). Jag hör det här sättet för ofta från kunder. Namnet på din innehavare bör vara en ämnesartikel.
- Om du har DNS-namnområden ska du lägga till alla dessa i klientorganisationen. Annars kan en [ohanterad klientorganisation med det](/azure/active-directory/users-groups-roles/directory-self-service-signup) här namnet skapa störningar, vilket skulle kunna göra att den [hanteras.](/azure/active-directory/users-groups-roles/domains-admin-takeover)
- DNS-namnområdet (till exempel contoso.com) kan tillhöra en och endast en innehavare. Detta har sina konsekvenser för olika scenarier (t.ex. delning av en e-postdomän vid samgående eller förvärv och så vidare). Det finns ett sätt att registrera en DNS-under (till exempel div.contoso.com) i en annan klientorganisation, men det bör undvikas. Genom att registrera ett toppnivådomännamn antas alla underdomäner tillhöra samma klientorganisation. I scenarier med flera innehavare (se nedan) rekommenderar jag normalt att du använder ett annat domännamn på den översta nivån (till exempel contoso.ch eller ch-contoso.com).
- Vem ska "äga" en klientorganisation? Jag ser ofta kunder som inte vet vem som för närvarande äger deras klientorganisation. Det här är en stor röd flagga. Kontakta Microsoft support så fort som möjligt. Lika problematiskt är när en tjänstägare (ofta en Exchange administratör) är utsedd att hantera en klientorganisation. Klientorganisationen kommer att innehålla alla tjänster som du kanske vill använda i framtiden. Klientorganisationens ägare bör vara en grupp som kan fatta beslut om att aktivera alla molntjänster i en organisation. Ett annat problem är när en innehavarägaregrupp ombeds att hantera alla tjänster. Det här ska inte skalas för stora organisationer.
- Det finns inget koncept för en under-/superklientorganisation. Av någon anledning upprepas den här myten hela tiden. Det här gäller [även Azure AD B2C-klientorganisationen.](/azure/active-directory-b2c/) Jag hör för många gånger "Min B2C-miljö är i min XYZ-klient" eller "Hur flyttar jag min Azure-klientorganisation till min Office 365 klient?"
- Det här dokumentet fokuserar huvudsakligen på det kommersiella globala molnet eftersom det är det som de flesta kunder använder. Ibland kan det vara bra att känna [till moln i en suverän del](/azure/active-directory/develop/authentication-national-cloud). Självständig moln har ytterligare konsekvenser för att diskutera vilka som inte kan diskuteras i den här diskussionen.

## <a name="baseline-identity-topics"></a>Grundläggande identitetsavsnitt

Det finns mycket dokumentation om Microsofts identitetsplattform – Azure Active Directory (Azure AD). För dem som precis har börjat känns det ofta överväldigande. Det kan vara svårt att hålla dig upp med konstanta innovationer och förändringar även efter att du har lärt dig mer om det. I mina kundinteraktion tycker jag ofta att jag fungerar som "översättare" mellan affärsmål och "Bra, bättre, bäst" metoder för att hantera dessa (och mänskliga "klippanteckningar" för dessa ämnen). Det finns sällan ett perfekt svar och "rätt" beslut är en balans mellan olika riskfaktorer. Nedan följer några vanliga frågor och förvirringsområden som jag brukar diskutera med kunder.

### <a name="provisioning"></a>Etablering

Azure AD löser inte brist på styrning i din identitets värld! [Identitetsstyrning](/azure/active-directory/governance/identity-governance-overview) bör vara ett viktigt element oberoende av eventuella molnbeslut. Styrningskraven ändras med tiden, vilket är anledningen till att det är ett program och inte ett verktyg.

[Azure AD Anslut](/azure/active-directory/hybrid/whatis-azure-ad-connect) jämfört [med Microsoft Identity Manager](/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) jämfört med något annat (tredje part eller anpassat)? Nu och i framtiden kan du få problem med Azure AD Anslut. Det finns alla slags smartar i det här verktyget för att hantera kundkonfigurationer och kontinuerliga innovationer.

Vissa gränsfall som kan vara på väg mot en mer komplex arkitektur:

- Jag har flera AD-skogar utan nätverksanslutning mellan dessa. Det finns ett nytt alternativ som [kallas molnetablering.](/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)
- Jag har inte Active Directory, och jag vill inte heller installera det. Azure AD Anslut kan konfigureras för [synkronisering från LDAP](/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (partner kan krävas).
- Jag behöver etablera samma objekt för flera klientorganisationar. Det här stöds inte tekniskt men beror på definitionen av "samma".

Ska jag anpassa standardsynkroniseringsregler[(filtrera objekt,](/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering) [ändra attribut,](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) [alternativa inloggnings-ID](/azure/active-directory/hybrid/plan-connect-userprincipalname)och så vidare)? Undvik det! En identitetsplattform är lika värdefull som de tjänster som använder den. Du kan göra alla slags nyttiga konfigurationer, men för att besvara den här frågan måste du titta på hur programmen påverkas. Om du filtrerar e-postaktiverade objekt kommer gal-adress för onlinetjänster att vara ofullständig. om programmet använder specifika attribut kan filtrering av dem ha oförutsägbar effekt. och så vidare. Det är inte ett identitetsteams beslut.

XYZ SaaS har stöd för JIT-etablering (Just-in-Time), varför behöver jag synkronisera? Se ovan. Många program behöver profilinformation för funktioner. Du kan inte ha en GAL om alla e-postaktiverade objekt inte är tillgängliga. Detsamma gäller [användaretablering i](/azure/active-directory/app-provisioning/user-provisioning) program som är integrerade med Azure AD.

### <a name="authentication"></a>Autentisering

[Synkronisering av](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) lösenordshashar (PHS) jämfört med [direktautentisering](/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) jämfört med [federation](/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

Det finns oftast en starkt engagerade [diskussioner](/azure/active-directory/hybrid/choose-ad-authn) kring federation. Enklare är oftast bättre och därför bör du använda PHS om du inte har goda skäl att inte göra det. Det går även att konfigurera olika autentiseringsmetoder för olika DNS-domäner i samma klientorganisation.

Vissa kunder aktiverar federation + PHS huvudsakligen för:

- Ett alternativ för [återställning](/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) till (för katastrofåterställning) om federationstjänsten inte är tillgänglig.
- Ytterligare funktioner (till exempel: [Azure AD DS](/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)) och säkerhetstjänster (t.ex.: [läckta autentiseringsuppgifter](/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials))
- Stöd för tjänster i Azure som inte förstår federerad autentisering (till exempel [Azure-filer).](/azure/storage/files/storage-files-active-directory-overview)

Jag leder ofta kunder genom kundautentiseringsflödet för att förtydliga vissa missuppfattanden. Resultatet ser ut som i bilden nedan, vilket inte är lika bra som den interaktiva processen att komma dit.

![Exempel på whiteboard-konversation](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

Den här typen av whiteboard-ritning visar var säkerhetsprinciper tillämpas i flödet av en autentiseringsbegäran. I det här exemplet tillämpas principer som tillämpas via AD FS (Active Directory Federation Service) på den första tjänstbegäran, men inte efterföljande tjänstförfrågningar. Det här är minst en anledning till att flytta säkerhetskontroller till molnet så mycket som möjligt.

Vi har jagat drömn om [enkel](/azure/active-directory/manage-apps/what-is-single-sign-on) inloggning (SSO) så länge jag kan komma ihåg. Vissa kunder tror att de kan uppnå detta genom att välja rätt federationsleverantör (STS). Azure AD kan hjälpa dig att [avsevärt aktivera SSO-funktioner,](/azure/active-directory/manage-apps/plan-sso-deployment) men ingen STS är magiska. Det finns för många "äldre" autentiseringsmetoder som fortfarande används för viktiga program. Många av de scenarierna [kan åtgärdas om du](/azure/active-directory/saas-apps/tutorial-list) utökar Azure AD med partnerlösningar. SSO är en strategi och en resa. Du kan inte komma dit utan att gå över till [standarder för program.](/azure/active-directory/develop/v2-app-types) Relaterat till det här avsnittet är en resa mot [lösenordslös](/azure/active-directory/authentication/concept-authentication-passwordless) autentisering, som också inte har ett magiska svar.

[Multifaktorautentisering](/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) är nödvändigt idag[(här för](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) mer information). Lägg till [användarbeteendeanalyser och du](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) har en lösning som förhindrar de vanligaste cyberattackerna. Även konsumenttjänsterna flyttas och kräver MFA. Men jag har fortfarande ett möte med många kunder som inte vill gå över till [moderna autentiseringsmetoder.](../enterprise/hybrid-modern-auth-overview.md) Det viktigaste argumentet jag hör är att det påverkar användare och äldre program. Ibland kan en bra start hjälpa kunderna att flytta på sig – Exchange Online [meddelade ändringarna](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282). Nu finns det [många](/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) Azure AD-rapporter som kan hjälpa kunderna med övergången.

### <a name="authorization"></a>Auktorisering

Per [Wikipedia](https://en.wikipedia.org/wiki/Authorization)"att auktorisera" är att definiera en åtkomstprincip. Många ser det som möjligheten att definiera åtkomstkontroller till ett objekt (fil, tjänst och så vidare). I den nuvarande världen med cyberhot utvecklas det här begreppet snabbt till en dynamisk princip som kan reagera på olika hotvektorer och snabbt justera åtkomstkontroller som svar på dessa. Om jag till exempel öppnar mitt bankkonto från en ovanlig plats får jag ytterligare bekräftelsesteg. För att kunna ta hand om det behöver vi inte bara överväga själva principen utan även ekosystemet för identifiering av hot och signalrelationsmetoder.

Principmotorn i Azure AD implementeras med hjälp av [villkorsstyrda åtkomstprinciper.](/azure/active-directory/conditional-access/overview) Det här systemet är beroende av information från andra identifieringssystem för hot för att kunna fatta dynamiska beslut. En enkel vy skulle se ut ungefär så här:

![Principmotor i Azure AD](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

Om du kombinerar alla dessa signaler möjliggörs dynamiska principer som dessa:

- Om ett hot upptäcks på din enhet kommer din åtkomst till data begränsas till webben utan att du kan ladda ned den.
- Om du laddar ned en ovanligt stor mängd data krypteras och begränsas allt du laddar ned.
- Om du använder en tjänst från en ohanterad enhet blockeras du från mycket känsliga data men får tillgång till icke-begränsade data utan möjlighet att kopiera dem till en annan plats.

Om du godkänner denna utökade auktoriseringsdefinition måste du implementera ytterligare lösningar. Vilka lösningar du implementerar beror på hur dynamiskt du vill att principen ska vara och vilka hot du vill prioritera. Några exempel på sådana system är:

- [Azure AD Identity Protection](/azure/active-directory/identity-protection/)
- [Microsoft Defender for Identity](/azure-advanced-threat-protection/)
- [Microsoft Defender för Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender för Office 365](../security/office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security](/cloud-app-security/) (MCAS)
- [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md)
- [Microsoft Intune](/mem/intune/)
- [Microsoft Information Protection](../compliance/information-protection.md) (MIP)
- [Azure Sentinel](/azure/sentinel/)

Utöver Azure AD har naturligtvis olika tjänster och program egna specifika auktoriseringsmodeller. En del av dem tas upp senare i delegeringsavsnittet.

### <a name="audit"></a>Granskning

Azure AD har detaljerade [funktioner för granskning och](/azure/active-directory/reports-monitoring/) rapportering. Det är dock oftast inte den enda informationskällan som behövs för att fatta säkerhetsbeslut. Mer information finns i delegeringsavsnittet.

## <a name="theres-no-exchange"></a>Det finns inga Exchange

Ingen panik! Det innebär inte Exchange (eller föråldrade SharePoint och så vidare). Det är fortfarande en kärntjänst. Det jag menar är att teknikleverantörer under en längre tid har gått över användarupplevelser (UX) till att omfatta komponenter i flera tjänster. I Microsoft 365 är ett enkelt exempel "[moderna](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)bifogade filer " där bifogade filer i e-postmeddelanden lagras i SharePoint Online eller OneDrive för företag.

![Bifoga en fil i ett e-postmeddelande](../media/solutions-architecture-center/modern-attachments.png)

När du tittar på Outlook kan du se många tjänster som är "anslutna" som en del av den här upplevelsen, inte bara Exchange. Det inkluderar Azure AD, Microsoft Search, appar, profil, efterlevnad och Office 365 grupper.

![Outlook gränssnitt med bildtext](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

Läs mer [Microsoft Fluid Framework](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) om hur du förhandsgranskar kommande funktioner. I förhandsgranskningsläge nu kan jag läsa och svara på Teams direkt i Outlook. Faktum är att [Teams är ett](https://products.office.com/microsoft-teams/download-app) av de mest framträdande exemplen på den här strategi.

Generellt sett blir det svårare att rita en tydlig linje mellan Office 365 och andra tjänster i Microsoft-moln. Jag ser det som en stor fördel för kunderna eftersom de kan dra nytta av den totala innovationen i allt vi gör även om de använder en komponent. Ganska coolt och har betydande konsekvenser för många kunder.

Idag tycker jag att många kund-IT-grupper är strukturerade kring "produkter". Det är logiskt för en lokal värld eftersom du behöver en expert för varje specifik produkt. Men jag är helt nöjd över att jag inte behöver felsöka en Active Directory- eller Exchange-databas igen när de här tjänsterna har flyttats till molnet. Automation (vilken molnlösning det är) tar bort vissa återkommande manuella jobb (se vad som har hänt med faktorn). De ersätts dock med mer komplexa krav för att förstå interaktion mellan tjänster, påverkan, affärsbehov och så vidare. Om du vill lära dig [finns](/learn/)det stora möjligheter som kan aktiveras genom molnomvandling. Innan jag hoppar in i teknik pratar jag ofta med kunderna om att hantera förändring av IT-kunskaper och teamstrukturer.

Sluta fråga SharePoint "Hur gör jag med XYZ i SharePoint online?" till alla som gillar personer och utvecklare. Använd [Power Automate](/power-automate/) (eller Flow) för arbetsflödet, det är en mycket mer kraftfull plattform. Använd [Azure Bot Framework för](/azure/bot-service/) att skapa en bättre UX för objektlistan på 500 K. Börja använda [Microsoft Graph](https://developer.microsoft.com/graph/) i stället för CSOM. [Microsoft Teams](/MicrosoftTeams/Teams-overview) innehåller SharePoint men även en värld mer. Det finns många andra exempel som jag kan ta med. Det finns ett enormt och fantastiskt universum. Öppna dörren och [börja utforska]().

Andra vanliga konsekvenser ligger i efterlevnadsområdet. Den här metoden för tvärtjänster verkar totalt förvirra många efterlevnadsprinciper. Organisationer med statusen "Jag behöver journalför all e-postkommunikation till ett e-dataidentifieringssystem". Vad innebär detta egentligen när e-post inte längre bara är e-post utan ett fönster in i andra tjänster? Office 365 har en omfattande metod för [efterlevnad,](../compliance/index.yml)men det är ofta mycket svårare än teknik att ändra personer och processer.

Det finns många andra personer och processkonsekvenser. Enligt min mening är det här ett kritiskt och under diskuteras område. Kanske mer i en annan artikel.

## <a name="tenant-structure-options"></a>Alternativ för klientorganisationsstruktur

### <a name="single-tenant-vs-multi-tenant"></a>Enskild klientorganisation kontra flera innehavare

I allmänhet bör de flesta kunder bara ha en produktionsklient. Det finns många anledningar till varför flera klientorganisationar är svåra (ge det [en Bing sökning)](https://www.bing.com/search?q=office%20365%20multiple%20tenants)eller [läs det här informationsbladet.](https://aka.ms/multi-tenant-user) Samtidigt har många företagskunder som jag arbetar med en annan (liten) klientorganisation för IT-utbildning, testning och experimentarbete. Azure-åtkomst mellan klientorganisationen blir enklare med [Azure-fyren.](https://azure.microsoft.com/services/azure-lighthouse/) Office 365 och många andra SaaS-tjänster har begränsningar för scenarier mellan klientorganisationen. Det finns mycket att tänka på i [Azure AD B2B-scenarier.](/azure/active-directory/b2b/what-is-b2b)

Många kunder får flera produktionsklienter efter en sammanslagning och förvärv (M&A) och vill konsolidera. I dag är det inte enkelt och skulle kräva Microsoft Consulting Services (MCS) eller en partner plus programvara från tredje part. Det finns pågående teknikarbete för att hantera olika scenarier med kunder med flera innehavare i framtiden.

Vissa kunder väljer att använda fler än en klientorganisation. Det bör vara ett mycket noga beslut och nästan alltid verksamhetsberoende! Några exempel är följande:

- En företagsstruktur av typen holding där enkelt samarbete mellan olika enheter inte krävs och det finns starka behov av administrativ och annan avgränsning.
- Efter ett företagsköp görs ett beslut om att hålla två enheter separerade.
- Simulering av en kundmiljö som inte ändrar kundens produktionsmiljö.
- Utveckling av programvara för kunder.

I de här scenarierna med flera innehavare vill kunder ofta behålla samma konfiguration för flera klientorganisationener eller rapportera om konfigurationsändringar och drift. Det innebär ofta att flytta från manuella ändringar till konfiguration som kod. Microsoft Premier-supporten erbjuder en utgångspunkt för de här typerna av krav som baseras på denna offentliga IP: <https://Microsoft365dsc.com> .

### <a name="multi-geo"></a>Multi-Geo

Om [du vill använda Multi-Geo](../enterprise/microsoft-365-multi-geo.md) eller inte Multi-Geo är det frågan. Med Office 365 Multi-Geo kan du tillhandahålla och lagra data i vila på de geoplatser som du har valt att uppfylla krav för [datalagring.](../enterprise/o365-data-locations.md) Det finns många missuppfattningar om den här funktionen. Tänk på följande:

- Den ger inte några prestandafördelar. Det kan leda till sämre prestanda om [inte nätverksdesignen](https://aka.ms/office365networking) fungerar som den ska. Hämta enheter "stäng" till Microsoft-nätverket, inte nödvändigtvis dina data.
- Det är inte en lösning för [GDPR:s efterlevnad.](https://www.microsoft.com/trust-center/privacy/gdpr-overview) GDPR fokuserar inte på data eller lagringsplatser. Det finns andra ramverk för efterlevnad för detta.
- Den löser inte delegering av administration (se nedan) eller [informationsbarriärer.](../compliance/information-barriers.md)
- Det är inte detsamma som flerklientorganisationen och kräver ytterligare [arbetsflöden för användaretablering.](https://github.com/MicrosoftDocs/azure-docs-pr/blob/master/articles/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation.md)
- Din klientorganisation [(din](../enterprise/moving-data-to-new-datacenter-geos.md) Azure AD) flyttas inte till en annan geografi.

## <a name="delegation-of-administration"></a>Delegering av administration

I de flesta stora organisationer är avgränsningen av uppgifter och rollbaserad åtkomstkontroll (RBAC) nödvändig. Jag ska be om ursäkt i förväg. Det är inte så enkelt som vissa kunder vill att det ska vara. Kund-, juridiska krav, efterlevnadskrav och andra krav är olika och kan ibland vara i konflikt över hela världen. Enkelhet och flexibilitet är ofta på motsatt sidor av varandra. Det går inte att få mig att tro att vi kan göra ett bättre jobb. Det har gjorts (och kommer att) betydande förbättringar med tiden. Besök ditt lokala [Microsoft Technology Center för](https://www.microsoft.com/mtc) att ta fram den modell som passar dina företagskrav utan att läsa 379230-dokument! Här fokuserar jag på vad du ska tänka på och inte varför det är så här. Nedan finns fem olika områden att planera för och några av de vanligaste frågorna som jag har stött på.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD och Microsoft 365 administrationscenter

Det finns en lång och växande lista [med inbyggda roller.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Varje roll består av en lista över rollbehörigheter som grupperats för att tillåta att särskilda åtgärder utförs. De här behörigheterna visas på fliken Beskrivning i varje roll. Alternativt kan du se en mer läsbar version av dessa i Microsoft 365 Admin Center. Definitionerna för inbyggda roller kan inte ändras. I allmänhet grupperar jag dessa i tre kategorier:

- **Global administratör:** Den här "all kraftfulla" rollen bör [skyddas i hög grad](../enterprise/protect-your-global-administrator-accounts.md) på samma sätt som i andra system. Vanliga rekommendationer är: ingen permanent tilldelning och användning av Azure AD Privileged Identity Management (PIM); stark autentisering; och så vidare. På ett intressant sätt ger den här rollen dig inte tillgång till allt som standard. Jag brukar se förvirring vad gäller åtkomst till efterlevnad och Azure-åtkomst, vilket diskuteras senare. Den här rollen kan dock alltid tilldela åtkomst till andra tjänster i klientorganisationen.
- **Specifika tjänstadministratörer:** Vissa tjänster (Exchange, SharePoint, Power BI och så vidare) använder administratörsroller på hög nivå från Azure AD. Det är inte konsekvent i alla tjänster och det finns fler tjänstespecifika roller som diskuteras senare.
- **Funktionellt:** Det finns en lång (och växande) lista med roller som fokuserar på specifika åtgärder (gäst inbjudna och så vidare). Med jämna mellanrum läggs fler av dem till utifrån kundens behov.

Det går inte att delegera allt (även om mellanrummet minskar), vilket innebär att den globala administratörsrollen ibland skulle behöva användas. Konfiguration som kod och automatisering bör övervägas i stället för att personer ska vara medlemmar i den här rollen.

**Obs!** Administrationscenter för Microsoft 365 har ett mer användarvänligt gränssnitt men har en delmängd funktioner jämfört med administrationsupplevelsen i Azure AD. Båda portalerna använder samma Azure AD-roller, så ändringar sker på samma plats. Tips: Om du vill ha ett användargränssnitt med identitetshantering som är fokuserad administratör utan all Azure-röra kan du använda <https://aad.portal.azure.com> .

Vad finns i namnet? Gör inte antaganden från namnet på rollen. Språket är inte ett mycket exakt verktyg. Målet bör vara att definiera åtgärder som ska delegeras innan du ser vilka roller som behövs. Om du lägger till någon i rollen "Säkerhetsläsare" ser de inte säkerhetsinställningar i allt.

Möjligheten att skapa [anpassade roller](/azure/active-directory/users-groups-roles/roles-custom-overview) är en vanlig fråga. Det är begränsat i Azure AD idag (se nedan) men kommer att växa med tiden. Jag ser dem som tillämpliga på funktioner i Azure AD och kanske inte omfattar hierarkimodellen (diskuteras ovan). När jag tar itu med "anpassad" brukar jag gå tillbaka till mitt huvudnamn , "enkelt är bättre".

En annan vanlig fråga är möjligheten att begränsa roller till en delmängd av en katalog. Ett exempel är "Supportadministratör för endast användare inom EU". [Administrativa enheter](/azure/active-directory/users-groups-roles/directory-administrative-units) (AU) är avsedda att åtgärda detta. Som ovan ser jag dessa som tillämpliga funktioner i Azure AD och kanske inte spänner över "nedåt". Vissa roller är förstås inte meningsfulla att använda (globala administratörer, tjänstadministratörer och så vidare).

I dag kräver alla de här rollerna direkt medlemskap (eller dynamisk tilldelning om du använder [Azure AD PIM).](/azure/active-directory/privileged-identity-management/) Det innebär att kunder måste hantera dessa direkt i Azure AD och dessa kan inte baseras på ett medlemskap i säkerhetsgrupper. Jag gillar inte att skapa skript för att hantera dem eftersom det skulle behöva köras med förhöjda rättigheter. Jag rekommenderar api-integrering med processsystem som ServiceNow eller partnerstyrningsverktyg som Saviynt. Teknikarbetet kommer att åtgärdas med tiden.

Jag nämnde [Azure AD PIM](/azure/active-directory/privileged-identity-management/) några gånger. Det finns en Microsoft Identity Manager (MIM) [privileged access Management](/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) (PAM) för lokala kontroller. Du kanske också vill titta på [Paws (Privileged Access Arbetsstationer)](/windows-server/identity/securing-privileged-access/privileged-access-workstations) och Azure [AD-identitetsstyrning.](/azure/active-directory/governance/identity-governance-overview) Det finns även olika verktyg från tredje part som kan aktivera precis i tid, precis tillräckligt många och dynamisk rollhöjd. Det här är vanligtvis en del av en större diskussion om att skydda en miljö.

Ibland anropas scenarier för att lägga till en extern användare till en roll (se avsnittet med flera innehavare ovan). Det här fungerar alldeles utmärkt. [Azure AD B2B är](/azure/active-directory/b2b/) ett annat stort och roligt ämne som kunderna kan gå igenom, kanske i en annan artikel.

### <a name="security-and-compliance-center-scc"></a>Säkerhets- och efterlevnadscenter (SCC)

[Behörigheter i säkerhets- Office 365 säkerhets- &](../security/office-365-security/permissions-in-the-security-and-compliance-center.md) är en samling "rollgrupper", som är separata och skiljer sig från Azure AD-roller. Det kan vara förvirrande eftersom vissa av dessa rollgrupper har samma namn som Azure AD-roller (till exempel Säkerhetsläsare), men de kan ha olika medlemskap. Jag föredrar användningen av Azure AD-roller. Varje rollgrupp består av en eller flera "roller" (se vad jag menar med att återanvända samma ord?) och har medlemmar från Azure AD, som är e-postaktiverade objekt. Du kan också skapa en rollgrupp med samma namn som en roll, som kanske innehåller eller inte innehåller den rollen (undvik den här förvirringen).

Det här är i en mening en vidareutveckling Exchange modell för rollgrupper. Men Exchange Online har ett eget gränssnitt [för grupphantering.](/exchange/permissions-exo) Vissa rollgrupper i Exchange Online är låsta och hanteras från Azure AD eller Säkerhets- och efterlevnadscenter för &, men andra kan ha samma eller liknande namn och hanteras i Exchange Online (som en del av den förvirringen). Jag rekommenderar att du undviker att Exchange Online användargränssnittet såvida du inte behöver omfattningar för Exchange hantering.

Du kan inte skapa anpassade roller. Roller definieras av tjänster som skapas av Microsoft och växer i och med att nya tjänster införs. Det här fungerar ungefär som roller [som definieras av program](/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) i Azure AD. När nya tjänster är aktiverade behöver ofta nya rollgrupper skapas för att bevilja eller delegera åtkomst till dessa (till exempel [insiderriskhantering).](../compliance/insider-risk-management-configure.md)

De här rollgrupperna kräver direkt medlemskap och får inte innehålla Azure AD-grupper. Idag stöds tyvärr inte de här rollgrupperna av Azure AD PIM. Precis som med Azure AD-roller brukar jag rekommendera hantering av dessa via API:er eller en produkt för partnerstyrning, till exempel Saviynt.

Roller & kompatibilitetscenter omfattar Microsoft 365 och du kan inte begränsa rollgrupperna till en delmängd av miljön (som med administrativa enheter i Azure AD). Många kunder frågar hur de kan underta bort. Till exempel "skapa en DLP-princip endast för EU-användare". Om du i dag har rättigheter till en specifik funktion i Säkerhets- och & efterlevnadscenter har du rättigheter till allt som omfattas av den här funktionen i klientorganisationen. Men många principer har funktioner för att rikta en delmängd av miljön (till exempel "gör de här [etiketterna endast](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) tillgängliga för dessa användare"). Korrekt styrning och kommunikation är en viktig komponent för att undvika konflikter. Vissa kunder väljer att implementera en metod som "konfiguration som kod" för att hantera underdelegering i säkerhets- & efterlevnadscenter. Vissa specifika tjänster stöder underdelegering (se nedan).

Det är värt att notera att kontroller som hanteras via säkerhets- och efterlevnadscentret för & (protection.office.com) håller på att migreras till två separata administrationsportaler: security.microsoft.com och compliance.microsoft.com. Ändra är den enda konstanten!

### <a name="service-specific"></a>Tjänstspecifik

Som vi nämnt tidigare vill många kunder uppnå en mer detaljerad delegeringsmodell. Ett vanligt exempel: "Hantera XYZ-tjänsten endast för Division X-användare och -platser" (eller någon annan dimension). Möjligheten att göra detta beror på varje tjänst och är inte konsekvent för alla tjänster och funktioner. Dessutom kan varje tjänst ha en separat och unik RBAC-modell. I stället för att diskutera allt detta (det tar evigheter) lägger jag till relevanta länkar för varje tjänst. Det här är inte en fullständig lista, men det hjälper dig att komma igång.

- **Exchange Online** – (/exchange/permissions-exo/permissions-exo)
- **SharePoint Online** – (/sharepoint/manage-site-collection-administrators)
- **Microsoft Teams** – (/microsoftteams/itadmin-readiness)
- **eDiscovery** – (.. /compliance/index.yml)
  - **Behörighetsfiltrering** – (.. /compliance/index.yml)
  - **Efterlevnadsgränser** – (.. /compliance/set-up-compliance-boundaries.md)
  - **Advanced eDiscovery** - (.. /compliance/overview-ediscovery-20.md)
- **Yammer** - (/yammer/manage-yammer-users/manage-yammer-admins)
- **Multi-geo** - (.. /enterprise/add-a-sharepoint-geo-admin.md)
- **Dynamics 365** – (/dynamics365/)

  Obs! Den här länken finns i roten till dokumentationen. Det finns flera typer av tjänster med variationer i modellen för administratörer/delegering.

- **Power Platform** – (/power-platform/admin/admin-documentation)
  - **Power Apps** – (/power-platform/admin/wp-security)

    Obs! Det finns flera typer med variationer i modeller för administratörer/delegering.

  - **Power Automate** - (/power-automate/environments-overview-admin)
  - **Power BI** – (/power-bi/service-admin-governance)

    Obs! Säkerhet och delegering av dataplattform (som Power BI en komponent) är ett komplext område.

- **MEM/Intune** - (/mem/intune/fundamentals/role-based-access-control)
- **Microsoft Defender för slutpunkt** – (/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- **Microsoft 365 Defender** – (.. /security/defender/m365d-permissions.md)
- **Microsoft Cloud App Security** - (/cloud-app-security/manage-admins)
- **Stream** – (/stream/assign-administrator-user-role)
- **Informationsbarriärer** – (.. /compliance/information-barriers.md)

I övrigt har sökningen i Docs varit riktigt bra den senaste tiden – <https://docs.microsoft.com/> .

### <a name="activity-logs"></a>Aktivitetsloggar

Office 365 har en [enhetlig granskningslogg](../compliance/search-the-audit-log-in-security-and-compliance.md). Det är en mycket [detaljerad logg](/office/office-365-management-api/office-365-management-activity-api-schema), men läs inte för mycket i namnet. Den kanske inte innehåller allt du behöver eller behöver för dina säkerhets- och efterlevnadsbehov. Dessutom är vissa kunder mycket intresserade av [Avancerad granskning.](../compliance/advanced-audit.md)

Exempel på Microsoft 365 loggar som används via andra API:er är bland annat följande:

- [Azure AD](/azure/azure-monitor/platform/diagnostic-settings) (aktiviteter som inte är relaterade till Office 365)
- [Exchange Meddelandespårning](/powershell/module/exchange/get-messagetrace)
- Hot/UEBA-system som nämns ovan (till exempel Azure AD Identity Protection, Microsoft Cloud App Security, Microsoft Defender för Endpoint och så vidare)
- [Microsofts informationsskydd](../compliance/data-classification-activity-explorer.md)
- [Microsoft Defender för Endpoint](/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

Det är viktigt att först identifiera alla loggkällor som behövs för ett säkerhets- och efterlevnadsprogram. Observera även att olika loggar har olika begränsningar för lagring på rad.

Ur administratörsdelegeringsperspektiv har Microsoft 365 de flesta aktivitetsloggar inte en inbyggd RBAC-modell. Om du har behörighet att se en logg kan du se allt i den. Ett vanligt exempel på ett kundkrav är: "Jag vill kunna fråga aktivitet endast för EU-användare" (eller någon annan dimension). För att uppnå det här kravet måste vi överföra loggar till en annan tjänst. I Microsoft-molnet rekommenderar vi att du överför den till [antingen Azure Sentinel](/azure/sentinel/overview) eller [Log Analytics.](/azure/azure-monitor/learn/quick-create-workspace)

Översiktsdiagram:

![Diagram över loggkällor för ett säkerhets- och efterlevnadsprogram](../media/solutions-architecture-center/identity-beyond-illustration-4.png)

Diagrammet ovan representerar inbyggda funktioner för att skicka loggar till Händelsehubben och/eller Azure Storage och/eller Azure Log Analytics. Alla system har inte den här inbyggda ännu. Men det finns andra sätt att skicka loggarna till samma lagringsplats. Se till exempel Skydda [din Teams med Azure Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761).

Om du kombinerar alla loggar till en lagringsplats innebär det ytterligare fördelar, till exempel korskorrelationer, anpassade kvarhållningstider, utfyllning med data som behövs för att stödja RBAC-modellen och så vidare. När data finns i det här lagringssystemet kan du skapa en Power BI instrumentpanel (eller en annan typ av visualisering) med en lämplig RBAC-modell.

Loggar behöver inte dirigeras till en enda plats. Det kan också vara bra att integrera [Office 365 loggar med Microsoft Cloud App Security](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) eller en anpassad RBAC-modell i [Power BI](../admin/usage-analytics/usage-analytics.md). Olika lagringsplatsen har olika fördelar och målgrupper.

Det är värt att nämna att det finns ett mycket omfattande inbyggt analyssystem för säkerhet, hot, svagheter och så vidare i en tjänst som kallas [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md).

Många stora kunder vill överföra dessa loggdata till ett tredjepartssystem (till exempel SIEM). Det finns olika metoder för detta, men i allmänhet [är Azure Event Hub](/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) [Graph](/graph/security-integration) en bra utgångspunkt.

### <a name="azure"></a>Azure

Jag blir ofta tillfrågad om det finns något sätt att separera roller med hög behörighet mellan Azure AD, Azure och SaaS (till exempel: Global administratör för Office 365 men inte Azure).  Inte riktigt.  Arkitektur med flera klientorganisationar krävs om fullständig administrativ avgränsning krävs, men det ökar [komplexiteten](https://aka.ms/multi-tenant-user) (se ovan). Alla dessa tjänster är en del av samma säkerhets- och identitetsgräns (titta på hierarkimodellen ovan).

Det är viktigt att förstå relationer mellan olika tjänster i samma klientorganisation. Jag arbetar med många kunder som bygger affärslösningar som spänner över Azure, Office 365 och Power Platform (och ofta även lokala och tredjepartsmolntjänster). Ett vanligt exempel:

1. Jag vill samarbeta i en uppsättning dokument/bilder/osv.(Office 365)
2. Skicka var och en av dem genom en godkännandeprocess (Power Platform)
3. När alla komponenter har godkänts sätter du ihop dem till en enhetlig slutbar produkt (Azure) [Microsoft Graph API](/azure/active-directory/develop/microsoft-graph-intro) är din bästa vän för dessa.  Inte omöjligt, men betydligt mer komplicerat med att utforma en lösning som spänner [över flera klientorganisationar.](/azure/active-directory/develop/single-and-multi-tenant-apps)

Azure Role-Based Access Control (RBAC) ger enkel åtkomsthantering för Azure. Med RBAC kan du hantera åtkomst till resurser genom att bevilja användare de längsta behörigheterna som behövs för att utföra deras jobb. Informationen är inte begränsad till det här dokumentet, men mer information om RBAC finns i Vad är rollbaserad åtkomstkontroll [(RBAC) i Azure?](/azure/role-based-access-control/overview) RBAC är viktigt men bara en del av hanteringsöverväganden för Azure. [Cloud Adoption Framework](/azure/cloud-adoption-framework/govern/) är en bra utgångspunkt för mer information. Jag gillar hur min vän Andres Hansson vägkar kunderna steg för steg, men olika komponenter för att bestämma vilken metod jag ska välja. Vyn på hög nivå för olika element (inte lika bra som processen för att komma åt faktiska kundmodeller) ser ut ungefär så här:

![Vy på hög nivå av Azure-komponenter för delegerad administration](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

Som du ser ovanifrån bör många andra tjänster ses som en [](/azure/governance/policy/overview)del av designen (till exempel: Azure-principer, [Azure Blueprints,](/azure/governance/blueprints/overview) [Hanteringsgrupper](/azure/governance/management-groups/)och så vidare).

## <a name="conclusion"></a>Sammanfattning

Från början som en kort sammanfattning, avslutades längre än förväntat.  Jag hoppas att du nu är redo att ta dig in i en djup förståelse av hur du skapar delegeringsmodeller för din organisation.  Den här konversationen är mycket vanlig med kunder. Det finns ingen modell som fungerar för alla. Väntar på några planerade förbättringar från Microsoft Engineering innan vi dokumenterar vanliga mönster som vi ser för kunder. Under tiden kan du samarbeta med Microsoft-kontoteamet och ordna ett besök på närmaste [Microsoft Technology Center.](https://www.microsoft.com/mtc)  Vi ser dig!
