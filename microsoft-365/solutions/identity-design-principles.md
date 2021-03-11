---
title: Resursplanering för Microsoft 365 för företag – säkerhetsarkitektur
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
ms.openlocfilehash: b2ea85190aeda74efc25a7088a01365132caad30
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712516"
---
# <a name="to-identity-and-beyondone-architects-viewpoint"></a>Om du vill identitet och vidare – en arkitekts hus

I den här artikeln [beskriver Alex Shteynberg,](https://www.linkedin.com/in/alex-shteynberg/)Principal Technical Architect på Microsoft, de övre designstrategierna för företag som inför Microsoft 365 och andra Microsoft-molntjänster.

## <a name="about-the-author"></a>Om författaren

![Alex Shteynberg foto](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

Jag är principal Technical Architect på Microsoft [Technology Center i New](https://www.microsoft.com/mtc?rtc=1)York. Jag arbetar mest med stora kunder och komplexa krav. Min vän och mina åsikter baseras på dessa interaktioner och kanske inte gäller för alla situationer. Men om vi kan hjälpa kunder med de mest komplexa problemen kan vi hjälpa alla kunder.

Jag arbetar normalt med över 100 kunder per år. Även om alla organisationer har unika egenskaper är det intressant att se trender och orsaker. En trend är till exempel branschledande intresse för många kunder. En bank kan ju också vara ett café och ett communitycenter.

I min roll fokuserar jag på att hjälpa kunder att ta fram den bästa tekniska lösningen för att hantera sina unika affärsverksamhetsmål. Officiellt fokuserar jag på identitet, säkerhet, sekretess och efterlevnad. Jag tycker om att de rör vid allt vi gör. Det ger mig möjlighet att vara med i de flesta projekt. Det håller mig upptagen och gillar den här rollen.

Jag bor i New York City (den bästa!) och tycker om dess mångfald av kultur, mat och människor (inte trafik). Jag älskar att resa när jag kan och hoppas att se det mesta av världen under min livslängd. Jag letar just nu efter en resa till Afrika för att lära mig mer om djurliv.

## <a name="guiding-principles"></a>Vägledande principer

- **Det enkla är ofta bättre:** Du kan göra (nästan) allt med teknik, men det betyder inte att du ska göra det. Särskilt när det gäller säkerhetsutrymmet är det många kunder som använder överengineerlösningar. Jag gillar [den här videon](https://www.youtube.com/watch?v=SOQgABDSYZE) från Googles Stripe-konferens till att understryka det här.
- **Personer, processer, teknik:** [Design för att förbättra](https://en.wikipedia.org/wiki/Human-centered_design) processen, inte tekniskt först. Det finns inga "perfekta" lösningar. Vi behöver balansera olika riskfaktorer och beslut kommer att vara olika för varje företag. För många kunder utformar en metod som deras användare senare undviker.
- **Fokusera på "varför" först och "hur"** senare: Var den irriterande 7-åring som har en miljon frågor. Vi kan inte få fram rätt svar om vi inte känner till rätt frågor att ställa. Många kunder gör antaganden om hur saker måste fungera i stället för att definiera affärsproblemet. Det finns alltid flera sökvägar som kan användas.
- **Long tail of past best practices**: Recognize that best practices are changing at light speed. Om du har tittat på Azure AD för mer än tre månader sedan är du förmodligen in gammal. Allt här kan komma att ändras efter publicering. Alternativet "Bäst" i dag kanske inte är samma som för sex månader sedan.

## <a name="baseline-concepts"></a>Baslinjebegrepp

Hoppa inte över det här avsnittet. Jag tycker ofta att jag måste gå tillbaka till de här avsnitten, även för kunder som har använt molntjänster i många år.
Språket är tyvärr inte ett exakt verktyg. Vi använder ofta samma ord för att medelvärdet för olika begrepp eller olika ord för att betyda samma koncept. Jag använder ofta det här diagrammet nedan för att upprätta viss baslinjeterminologi och "hierarkimodell".
<br><br>

![Illustration av klientorganisation, prenumeration, tjänst och data](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

När du lär dig att simning är det bättre att börja i poolen och inte i mitten av oceanen. Jag försöker inte vara tekniskt korrekt med det här diagrammet. Det är en modell för att diskutera några grundläggande begrepp.

I diagrammet:

- Klientorganisation = en instans av Azure AD. Den är högst upp i en hierarki eller på Nivå 1 i diagrammet. Vi kan betrakta det som den "[gräns](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-directory-independence)" där allt annat förekommer (undan[Azure AD B2B).](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) Alla Microsoft Enterprise-molntjänster ingår i en av dessa klientorganisationar. Konsumenttjänsterna är separata. "Klientorganisation" visas i dokumentationen som Office 365-innehavare, Azure-klientorganisation, WVD-klientorganisation och så vidare. Jag tycker ofta att de här varianterna orsakar förvirring för kunderna.
- Tjänster/prenumerationer, nivå 2 i diagrammet, tillhör en och bara en klientorganisation. De flesta SaaS-tjänster är 1:1 och kan inte flytta utan migrering. Azure är annorlunda, du kan [flytta fakturering och/eller](https://docs.microsoft.com/azure/cost-management-billing/manage/billing-subscription-transfer) en [prenumeration till en](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) annan klientorganisation. Det finns många kunder som behöver flytta Azure-prenumerationer. Detta har olika konsekvenser. Objekt som finns utanför prenumerationen flyttas inte (till exempel rollbaserad åtkomstkontroll eller Azure RBAC och Azure AD-objekt, inklusive grupper, appar, principer och så vidare). Även vissa tjänster (till exempel Azure-nyckelvalv, data brickor och så vidare). Migrera inte tjänster utan att ha behov av bra affärer. Vissa skript som kan vara användbara för migreringen [delas på GitHub.](https://github.com/lwajswaj/azure-tenant-migration)
- En viss tjänst har vanligtvis någon typ av "undernivågräns" eller nivå 3 (L3). Det är användbart att förstå för separering av säkerhet, principer, styrning och så vidare. Det finns tyvärr inget enhetligt namn som jag känner till. Några exempelnamn för L3 är: Azure Subscription = [resource](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [instans](https://docs.microsoft.com/dynamics365/admin/new-instance-management); Power BI = [arbetsyta](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces); Power Apps = [miljö](https://docs.microsoft.com/power-platform/admin/environments-overview); och så vidare.
- På nivå 4 finns faktiska data. Det här "dataplan" är ett komplext ämne. Vissa tjänster använder Azure AD för RBAC, andra använder inte tjänsten. Jag ska diskutera det lite när vi kommer till delegeringsämnen.

Några ytterligare begrepp som jag tycker många kunder (och Microsoft-anställda) är förvirrade över eller har frågor om är bland annat följande:

- Alla kan [skapa](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) många klientorganisationar [utan kostnad.](https://azure.microsoft.com/pricing/details/active-directory/) Du behöver inte tillhandahålla en tjänst i tjänsten. Jag har många. Varje klientorganisationsnamn är unikt i Microsofts globala molntjänst (med andra ord kan inte två klientorganisationar ha samma namn). Alla har samma format som TenantName.onmicrosoft.com. Det finns även processer som skapar klientorganisation automatiskt[(ohanterade klientorganisationar).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) Detta kan till exempel inträffa när en användare registrerar sig för en företagstjänst med en e-postdomän som inte finns i någon annan klientorganisation.
- I en hanterad klientorganisation kan [många DNS-domäner](https://docs.microsoft.com/azure/active-directory/fundamentals/add-custom-domain) registreras i den. Detta ändrar inte det ursprungliga klientnamnet. Det finns för närvarande inget enkelt sätt att byta namn på en klientorganisation (förutom migrering). Klientorganisationens namn är tekniskt sett inte så viktigt i dessa dagar, men vissa kanske tycker att det är begränsat.
- Du bör reservera ett klientnamn för organisationen även om du ännu inte planerar att distribuera några tjänster. Annars kan någon ta det från dig och det finns ingen enkel process för att ta tillbaka den (samma problem som DNS-namn). Jag hör det här sättet för ofta från kunder. Namnet på klientorganisationen bör också vara ett diskuterande ämne.
- Om du har DNS-namnområden ska du lägga till alla dessa i klientorganisationen. Annars kan en [ohanterad klientorganisation](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) med det här namnet skapas, vilket gör att den hanteras utan [avbrott.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)
- DNS-namnområdet (till exempel contoso.com) kan tillhöra en och endast en klientorganisation. Det här påverkar olika scenarier (t.ex. delning av en e-postdomän vid en sammanslagning eller ett förvärv och så vidare). Det finns ett sätt att registrera en DNS-underorganisation (till exempel div.contoso.com) i en annan klientorganisation, men det bör undvikas. Genom att registrera ett domännamn på översta nivån antas alla underdomäner tillhöra samma klientorganisation. I scenarier med flera klientorganisationen (se nedan) rekommenderar jag normalt ett annat domännamn på den översta nivån (till exempel contoso.ch eller ch-contoso.com).
- Vem ska "äga" en klientorganisation? Jag ser ofta kunder som inte vet vem som för närvarande äger sin klientorganisation. Det här är en stor röd flagga. Ring Microsoft support ASAP. Lika problematiskt är när en tjänstägare (ofta en Exchange-administratör) utses till att hantera en klientorganisation. Klientorganisationen kommer att innehålla alla tjänster som du kanske vill använda i framtiden. Klientorganisationens ägare bör vara en grupp som kan fatta beslut om att aktivera alla molntjänster i en organisation. Ett annat problem är när en klientorganisationsägare uppmanas att hantera alla tjänster. Det här ska inte skalas för stora organisationer.
- Det finns inget koncept för en under-/superklientorganisation. Den här myten upprepas av någon anledning hela tiden. Det här gäller [även För Azure AD B2C-klientorganisationen.](https://docs.microsoft.com/azure/active-directory-b2c/) Jag hör för många gånger "Min B2C-miljö finns i min XYZ-klientorganisation" eller "Hur flyttar jag Azure-klientorganisationen till Office 365-klienten?"
- Det här dokumentet fokuserar mest på det kommersiella globala molnet eftersom det är det som de flesta kunder använder. Ibland kan det vara bra att känna [till moln i en suverän del.](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud) Självständig moln har ytterligare konsekvenser för att diskutera vilka som inte kan diskuteras i den här diskussionen.

## <a name="baseline-identity-topics"></a>Grundläggande identitetsavsnitt

Det finns mycket dokumentation om Microsofts identitetsplattform – Azure Active Directory (Azure AD). För dem som precis har börjat känns det ofta överväldigande. Det kan vara svårt att hålla dig upp till konstant innovation och förändring även efter att du har lärt dig det. I mina kundinteraktioner fungerar jag ofta som "översättare" mellan affärsmål och "Bra, bättre, bäst" metoder för att hantera dessa (och mänskliga "klippanteckningar" för dessa ämnen). Det finns sällan ett perfekt svar och "rätt" beslut är en balans mellan olika riskfaktorer. Nedan följer några vanliga frågor och förvirringsområden som jag brukar diskutera med kunder.

### <a name="provisioning"></a>Etablering

Azure AD löser inte brist på styrning i din identitets värld! [Identitetsstyrning](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) bör vara ett viktigt element oberoende av eventuella molnbeslut. Styrningskraven ändras med tiden, vilket är anledningen till att det är ett program och inte ett verktyg.

[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect) jämfört med [Microsoft Identity Manager](https://docs.microsoft.com/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) jämfört med något annat (tredje part eller anpassat)? Nu och i framtiden får du mycket problem med Azure AD Connect. Det finns alla typer av smarts i det här verktyget för att hantera kundkonfigurationer och pågående innovationer.

Vissa gränsfall som kan leda till en mer komplex arkitektur:

- Jag har flera AD-skogar utan nätverksanslutning mellan dem. Det finns ett nytt alternativ som kallas [molnetablering.](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)
- Jag har inte Active Directory, och jag vill inte heller installera det. Azure AD Connect kan konfigureras för [synkronisering från LDAP](https://docs.microsoft.com/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (partner kan krävas).
- Jag behöver etablera samma objekt för flera klientorganisationar. Det här stöds inte tekniskt men beror på definitionen av "samma".

Ska jag anpassa standardsynkroniseringsregler[(filtrera objekt,](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering) [ändra attribut,](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) [alternativa inloggnings-ID](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-userprincipalname)och så vidare)? Undvik det! En identitetsplattform är bara lika värdefull som de tjänster som använder den. Du kan göra alla typer av musrika konfigurationer, men för att besvara den här frågan måste du titta på hur programmen kommer att påverkas. Om du filtrerar e-postaktiverade objekt blir GAL för onlinetjänster ofullständig. om programmet använder specifika attribut kan filtrering av dessa ha oförutsägbar effekt. och så vidare. Det är inte ett identitetsgruppsbeslut.

XYZ SaaS har stöd för JIT-etablering (Just-in-Time), varför behöver jag synkronisera? Se ovan. Många program behöver profilinformation för funktionalitet. Du kan inte ha en GAL om alla e-postaktiverade objekt inte är tillgängliga. Samma sak gäller [användaretablering](https://docs.microsoft.com/azure/active-directory/app-provisioning/user-provisioning) i program som är integrerade med Azure AD.

### <a name="authentication"></a>Autentisering

[Synkronisering av lösenordshashar](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (PHS) jämfört med [direktautentisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) jämfört med [federation.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility)

Det finns vanligtvis en starkt [engagerande diskussion](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) kring federation. Enklare är oftast bättre och därför bör du använda PHS om du inte har goda skäl att inte göra det. Det går även att konfigurera olika autentiseringsmetoder för olika DNS-domäner i samma klientorganisation. 

Vissa kunder aktiverar federation + PHS huvudsakligen för:

- Ett alternativ för [att gå tillbaka](https://docs.microsoft.com/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) till (vid katastrofåterställning) om federationstjänsten inte är tillgänglig.
- Ytterligare funktioner (t.ex. [Azure AD DS)](https://docs.microsoft.com/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)och säkerhetstjänster (t.ex.: [läckta autentiseringsuppgifter)](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials)
- Stöd för tjänster i Azure som inte förstår federerad autentisering (till exempel [Azure-filer).](https://docs.microsoft.com/azure/storage/files/storage-files-active-directory-overview)

Jag vägleder ofta kunder genom kundautentiseringsflödet för att förtydliga vissa missuppfattningar. Resultatet ser ut som bilden nedan, vilket inte är lika bra som den interaktiva processen att komma dit.

![Exempel på whiteboard-konversation](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

Den här typen av whiteboard-ritning visar var säkerhetsprinciper tillämpas i flödet för en autentiseringsbegäran. I det här exemplet tillämpas principer via AD FS (Active Directory Federation Service) på den första tjänstbegäran, men inte efterföljande tjänstförfrågningar. Det här är minst en anledning till att flytta säkerhetskontroller till molnet så mycket som möjligt.

Vi har jagat dröm om [enkel inloggning](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) (SSO) så länge jag kan komma ihåg det. Vissa kunder tror att de kan uppnå detta genom att välja rätt federationsleverantör (STS). Azure AD kan hjälpa avsevärt till [att aktivera SSO-funktioner,](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-sso-deployment) men ingen STS är magiska. Det finns för många äldre autentiseringsmetoder som fortfarande används för kritiska program. Att utöka Azure AD med [partnerlösningar](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) kan hantera många av de här scenarierna. SSO är en strategi och en resa. Du kan inte komma dit utan att flytta till [standarder för program.](https://docs.microsoft.com/azure/active-directory/develop/v2-app-types) Relaterat till det här avsnittet är [en](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) resa mot lösenordslös autentisering, som också inte har ett magiska svar.

[Multifaktorautentisering](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) är viktigt idag[(här för](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) mer information). Lägg till [användarbeteendeanalyser och](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) du har en lösning som förhindrar de vanligaste cyberattackerna. Även konsumenttjänster flyttas till och med MFA krävs. Men jag har fortfarande ett möte med många kunder som inte vill gå över till [moderna autentiseringsmetoder.](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview) Det viktigaste argumentet jag hör är att det påverkar användare och äldre program. Ibland kan det hjälpa kunderna att komma igång – Exchange Online meddelade [ändringar.](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282) Det finns [](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) nu många Azure AD-rapporter som kan hjälpa kunderna med övergången.

### <a name="authorization"></a>Auktorisering

Per [Wikipedia](https://en.wikipedia.org/wiki/Authorization)är "att auktorisera" att definiera en åtkomstprincip. Många ser det som möjligheten att definiera åtkomstkontroller till ett objekt (fil, tjänst och så vidare). I den nuvarande världen med cyberhot utvecklas det här begreppet snabbt till en dynamisk princip som kan reagera på olika hotvektorer och snabbt justera åtkomstkontroller som svar på dessa. Om jag till exempel öppnar mitt bankkonto från en ovanlig plats får jag ytterligare bekräftelsesteg. För att kunna ta till oss det här behöver vi inte bara överväga själva principen utan hela ekosystemet för identifiering av hot och signalrelationsmetoder.

Principmotorn i Azure AD implementeras med hjälp av [villkorsstyrda åtkomstprinciper.](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) Det här systemet är beroende av information från andra system för identifiering av hot för att kunna fatta dynamiska beslut. En enkel vy skulle se ut ungefär så här:

![Principmotor i Azure AD](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

Om du kombinerar alla dessa signaler möjliggörs dynamiska principer som dessa:

- Om ett hot upptäcks på din enhet kommer din åtkomst till data att minskas till webben utan att du kan ladda ned.
- Om du laddar ned en ovanligt stor mängd data krypteras och begränsas allt du laddar ned.
- Om du använder en tjänst från en ohanterad enhet blockeras du från mycket känsliga data men får åtkomst till icke-begränsade data utan möjlighet att kopiera dem till en annan plats.

Om du godkänner den här utökade auktoriseringsdefinitionen måste du implementera ytterligare lösningar. Vilka lösningar du implementerar beror på hur dynamisk du vill att principen ska vara och vilka hot du vill prioritera. Några exempel på sådana system är:

- [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/) 
- [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/)
- [Microsoft Defender för Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) (MCAS)
- [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/mem/intune/)
- [Microsoft Information Protection](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) (MIP)
- [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/)

Utöver Azure AD har naturligtvis olika tjänster och program egna specifika auktoriseringsmodeller. En del av dem tas upp senare i delegeringsavsnittet.

### <a name="audit"></a>Granska

Azure AD har detaljerade [funktioner för granskning och](https://docs.microsoft.com/azure/active-directory/reports-monitoring/) rapportering. Det här är dock vanligtvis inte den enda informationskällan som behövs för att fatta säkerhetsbeslut. Mer information finns i delegeringsavsnittet.

## <a name="theres-no-exchange"></a>Det finns inget Exchange-byte

Få inte panik! Det innebär inte att Exchange är inaktuellt (eller SharePoint och så vidare). Det är fortfarande en kärntjänst. Det jag menar är att under ganska lång tid har teknikleverantörer gått över användarupplevelser (UX) till att omfatta komponenter i flera tjänster. I Microsoft 365 är ett enkelt exempel "[moderna](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)bifogade filer " där bifogade filer i e-post lagras i SharePoint Online eller OneDrive för företag.

![Bifoga en fil i ett e-postmeddelande](../media/solutions-architecture-center/modern-attachments.png)

När du tittar på Outlook-klienten kan du se många tjänster som är "anslutna" som en del av den här upplevelsen, inte bara Exchange. Det inkluderar Azure AD, Microsoft Search, Appar, Profil, efterlevnad och Office 365-grupper. 

![Outlook-gränssnitt med bildtext](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

Läs om [Microsoft Fluid Framework](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) för en förhandsgranskning av kommande funktioner. I förhandsgranskningsläge nu kan jag läsa och svara på Teams-konversationer direkt i Outlook. Faktum är att [Teams-klienten](https://products.office.com/microsoft-teams/download-app) är ett av de mer framträdande exemplen på den här strategi. 

Generellt sett blir det svårare att rita en tydlig linje mellan Office 365 och andra tjänster i Microsoft-moln. Jag ser det som en stor fördel för kunderna eftersom de kan dra nytta av den totala innovationen i allt vi gör även om de använder en komponent. Ganska coolt och har stora konsekvenser för många kunder.

Idag tycker jag att många kund-IT-grupper är strukturerade kring "produkter". Det är logiskt för en lokal värld eftersom du behöver en expert för varje specifik produkt. Men jag är helt nöjd med att jag aldrig behöver felsöka en Active Directory- eller Exchange-databas igen när de här tjänsterna har flyttats till molnet. Automation (vilken molnlösning) tar bort vissa återkommande manuella jobb (se vad som har hänt med faktorn). Dessa ersätts emellertid med mer komplexa krav för att förstå interaktion mellan tjänster, påverkan, affärsbehov och så vidare. Om du vill lära dig [finns](https://docs.microsoft.com/learn/)det goda möjligheter som kan tack vare molntransformering. Innan jag hoppar in på teknik pratar jag ofta med kunder om att hantera förändring av IT-kunskaper och teamstrukturer.

För alla SharePoint-fan-personer och utvecklare, sluta fråga "Hur kan jag göra XYZ i SharePoint online?" Använd [Power Automate](https://docs.microsoft.com/power-automate/) (eller Flow) för arbetsflödet, det är en mycket mer kraftfull plattform. Använd [Azure Bot Framework för](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0) att skapa en bättre UX för objektlistan på 500 K. Börja använda [Microsoft Graph i](https://developer.microsoft.com/graph/) stället för CSOM. [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) innehåller SharePoint men också en värld mer. Det finns många andra exempel som jag kan ta med. Det finns ett omfattande och fantastiskt universum. Öppna dörren och [börja utforska.](https://docs.microsoft.com)

Andra vanliga konsekvenser finns i efterlevnadsområdet. Den här metoden för flera tjänster verkar vara helt förvirrande för många efterlevnadsprinciper. Jag ser fortfarande organisationer som har statusen "Jag behöver journalföra all e-postkommunikation till ett eDiscovery-system". Vad innebär det egentligen när e-post inte längre bara är e-post utan ett fönster in i andra tjänster? Office 365 har en omfattande metod för [efterlevnad,](https://docs.microsoft.com/microsoft-365/compliance/)men det är ofta mycket svårare än teknik att ändra personer och processer.

Det finns många andra personer och processkonsekvenser. Enligt min mening är detta ett kritiskt och under diskuterat område. Kanske mer i en annan artikel.

## <a name="tenant-structure-options"></a>Alternativ för klientorganisationsstruktur

### <a name="single-tenant-vs-multi-tenant"></a>Enskild klientorganisation kontra flera innehavare

I allmänhet bör de flesta kunder bara ha en produktionsklientorganisation. Det finns många anledningar till varför flera klientorganisationar är svåra (ge det en [Bing-sökning)](https://www.bing.com/search?q=office%20365%20multiple%20tenants)eller läs [det här whitepaperet.](https://aka.ms/multi-tenant-user) Samtidigt har många företagskunder som jag arbetar med en annan (liten) klientorganisation för IT-utbildning, testning och experimentering. Azure-åtkomst mellan klientorganisationen blir enklare med [Azure Lighthouse.](https://azure.microsoft.com/services/azure-lighthouse/) Office 365 och många andra SaaS-tjänster har begränsningar för scenarier för flera innehavare. Det finns mycket att tänka på i [Azure AD B2B-scenarier.](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)

Många kunder får flera produktionsklienter efter en sammanslagning och ett förvärv (M&A) och vill konsolidera. I dag är det inte enkelt och skulle kräva Microsoft Consulting Services (MCS) eller en partner plus programvara från tredje part. Det finns pågående tekniskt arbete för att hantera olika scenarier med kunder med flera innehavare i framtiden.

Vissa kunder väljer att använda fler än en klientorganisation. Det bör vara ett mycket noga beslut och nästan alltid av skäl! Några exempel är följande:

- En företagsstruktur av typen holding där enkelt samarbete mellan olika enheter inte krävs och det finns starka behov av administrativ och annan avgränsning.
- Efter ett företagsköp görs ett beslut om att hålla två enheter separata.
- Simulering av en kunds miljö som inte ändrar kundens produktionsmiljö. 
- Utveckling av programvara för kunder.

I de här scenarierna för flera innehavare vill kunder ofta behålla samma konfiguration för alla klientorganisationen eller rapportera om konfigurationsändringar och drift. Det innebär ofta att flytta från manuella ändringar till konfiguration som kod. Microsoft Premier-supporten ger dig en utgångspunkt för de här typerna av krav utifrån den här offentliga IP-adressen: [https://Microsoft365dsc.com](https://Microsoft365dsc.com) .

### <a name="multi-geo"></a>Multi-Geo

Om [du vill använda Multi-Geo](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo) eller inte Multi-Geo är det frågan. Med Office 365 Multi-Geo kan du tillhandahålla och lagra data i vila på de geoplatser som du har valt att uppfylla krav för [datalagring.](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations) Det finns många missuppfattningar om den här funktionen. Tänk på följande:

- Den ger inte några prestandafördelar. Det kan leda till sämre prestanda om [nätverksdesignen](https://aka.ms/office365networking) inte är korrekt. Få enheter "nära" Microsoft-nätverket, inte nödvändigtvis dina data.
- Det är inte en lösning för [GDPRs efterlevnad.](https://www.microsoft.com/trust-center/privacy/gdpr-overview) GDPR fokuserar inte på data som är tillgängliga eller lagringsplatser. Det finns andra ramverk för efterlevnad för detta.
- Det löser inte delegering av administration (se nedan) eller [informationsbarriärer.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)
- Det är inte detsamma som flerklientsarbetsflöden och kräver ytterligare [arbetsflöden för användaretablering.](https://github.com/MicrosoftDocs/azure-docs-pr/blob/master/articles/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation.md)
- Din klientorganisation [(din](https://docs.microsoft.com/microsoft-365/enterprise/moving-data-to-new-datacenter-geos) Azure AD) flyttas inte till ett annat geografiskt område. 

## <a name="delegation-of-administration"></a>Delegering av administration

I de flesta stora organisationer är avgränsning av uppgifter och rollbaserad åtkomstkontroll (RBAC) nödvändig verklighet. Jag ber om ursäkt i förväg. Det är inte så enkelt som vissa kunder vill att det ska vara. Kund-, juridiska krav, efterlevnadskrav och andra krav är olika och kan ibland vara i konflikt över hela världen. Enkelhet och flexibilitet är ofta på motsatt sidor av varandra. Vi kan göra ett bättre jobb på det här. Det har gjorts (och kommer att) betydande förbättringar med tiden. Besök ditt lokala [Microsoft Technology Center för](https://www.microsoft.com/mtc) att ta fram den modell som passar dina affärskrav utan att läsa 379230-dokument! Här fokuserar jag på vad du ska tänka på och inte varför det är så här. Nedan finns fem olika områden att planera för och några av de vanligaste frågorna som jag har stött på.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Administrationscenter för Azure AD och Microsoft 365

Det finns en lång och växande lista [över inbyggda roller.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Varje roll består av en lista med rollbehörigheter som grupperats för att tillåta att särskilda åtgärder utförs. De här behörigheterna visas på fliken Beskrivning i varje roll. Alternativt kan du se en mer läsbar version av dessa i administrationscentret för Microsoft 365. Definitionerna för inbyggda roller kan inte ändras. I allmänhet grupperar jag dessa i tre kategorier:

- **Global administratör:** Den här "all kraftfulla" rollen [ska vara skyddad i hög grad](https://docs.microsoft.com/microsoft-365/enterprise/protect-your-global-administrator-accounts) precis som i andra system. Vanliga rekommendationer är: ingen permanent tilldelning och användning av azure AD Privileged Identity Management (PIM), stark autentisering och så vidare. Intressant nog ger den här rollen dig inte tillgång till allt som standard. Vanligtvis är jag förvirrad över efterlevnadsåtkomst och Azure-åtkomst, som diskuteras senare. Den här rollen kan dock alltid tilldela åtkomst till andra tjänster i klientorganisationen. 
- **Specifika tjänstadministratörer:** Vissa tjänster (Exchange, SharePoint, Power BI och så vidare) använder administrativa roller på hög nivå från Azure AD. Det är inte konsekvent i alla tjänster och det finns fler tjänstespecifika roller som diskuteras senare.
- **Funktionellt:** Det finns en lång (och växande) lista med roller som fokuserar på specifika åtgärder (gäst inbjudna och så vidare). Med jämna mellanrum läggs flera av dem till utifrån kundens behov.

Det går inte att delegera allt (även om mellanrummet minskar), vilket innebär att den globala administratörsrollen ibland måste användas. Konfiguration som kod och automatisering bör övervägas i stället för personer som medlemskap i den här rollen.

**Obs!** Administrationscentret för Microsoft 365 har ett mer användarvänligt gränssnitt, men har en delmängd funktioner jämfört med administrationscentret för Azure AD. Båda portalerna använder samma Azure AD-roller, så ändringar sker på samma plats. Tips! Om du vill ha ett användargränssnitt med identitetshanteringsfokuserad administratör utan all Azure-övrig e-post använder du [https://aad.portal.azure.com](https://aad.portal.azure.com) . 

Vad finns i namnet? Gör inte antaganden från namnet på rollen. Språket är inte ett mycket exakt verktyg. Målet bör vara att definiera åtgärder som måste delegeras innan du tittar på vilka roller som behövs. Om du lägger till någon i rollen "Säkerhetsläsare" ser de inte säkerhetsinställningar på allt.

Möjligheten att skapa [anpassade roller](https://docs.microsoft.com/azure/active-directory/users-groups-roles/roles-custom-overview) är en vanlig fråga. Det är begränsat i Azure AD idag (se nedan), men kommer att växa med tiden. Jag ser dem som tillämpliga funktioner i Azure AD och kanske inte omfattar "nedåt" hierarkimodellen (diskuteras ovan). När jag hanterar "anpassad" brukar jag gå tillbaka till mitt huvudnamn , "enkelt är bättre".

En annan vanlig fråga är möjligheten att begränsa roller till en delmängd av en katalog. Ett exempel är exempelvis "Supportadministratör för användare inom EU". [Administrativa enheter](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-administrative-units) (AU) är avsedda att åtgärda detta. Som ovan ser jag dessa som tillämpliga för funktioner i Azure AD och kanske inte omfattar "nedåt". Självklart är vissa roller inte meningsfulla för omfattning (globala administratörer, tjänstadministratörer och så vidare).

I dag kräver alla dessa roller direkt medlemskap (eller dynamisk tilldelning om du använder [Azure AD PIM).](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) Det innebär att kunder måste hantera dessa direkt i Azure AD och dessa kan inte baseras på ett säkerhetsgruppmedlemskap. Jag gillar inte att skapa skript för att hantera dem eftersom det skulle behöva köras med förhöjda rättigheter. Jag rekommenderar vanligtvis API-integrering med processsystem som ServiceNow eller att använda partnerstyrningsverktyg som Synynt. Det kommer tekniskt arbete att åtgärda det här med tiden.

Jag har [nämnt Azure AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) några gånger. Det finns en motsvarande MIM-lösning [(Microsoft](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) Identity Manager) Privileged Access Management (PAM) för lokala kontroller. Du kan också titta på [paws (privileged access arbetsstations)](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) och [Azure AD Identity Governance.](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) Det finns även olika verktyg från tredje part som kan aktivera "bara-in-time" och "precis enough" och dynamisk rollhöjning. Det här är vanligtvis en del av en större diskussion om att skydda en miljö. 

Ibland anropas scenarier för att lägga till en extern användare i en roll (se avsnittet för flera innehavare ovan). Det här fungerar alldeles utmärkt. [Azure AD B2B är](https://docs.microsoft.com/azure/active-directory/b2b/) ett annat stort och roligt ämne att gå igenom för kunderna, kanske i en annan artikel.

### <a name="security-and-compliance-center-scc"></a>Säkerhets- och efterlevnadscenter (SCC)

[Behörigheter i Säkerhets- och efterlevnadscenter & för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) är en samling "rollgrupper", som är separata och skiljer sig från Azure AD-roller. Det kan vara förvirrande eftersom vissa av dessa rollgrupper har samma namn som Azure AD-roller (till exempel Säkerhetsläsare), men de kan ha olika medlemskap. Jag föredrar användningen av Azure AD-roller. Varje rollgrupp består av en eller flera "roller" (se vad jag menar med att återanvända samma ord?) och har medlemmar från Azure AD, som är e-postaktiverade objekt. Du kan också skapa en rollgrupp med samma namn som en roll, som kanske inte innehåller den rollen (undvik den här förvirringen).

Det här är i en mening en utveckling av modellen för Exchange-rollgrupper. Exchange Online har dock ett eget gränssnitt [för hantering av rollgrupper.](https://docs.microsoft.com/exchange/permissions-exo) Vissa rollgrupper i Exchange Online är låsta och hanteras från Azure AD eller Säkerhets- & efterlevnadscenter, men andra kan ha samma eller liknande namn och hanteras i Exchange Online (för att göra det förvirrande). Jag rekommenderar att du undviker att använda användargränssnittet i Exchange Online om du inte behöver omfattningar för Exchange-hantering.

Du kan inte skapa anpassade roller. Roller definieras av tjänster som skapas av Microsoft och växer när nya tjänster införs. Detta begrepp liknar roller som [definieras av program i](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) Azure AD. När nya tjänster har aktiverats måste ofta nya rollgrupper skapas för att bevilja eller delegera åtkomst till dessa (till exempel [insider riskhantering).](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management)

De här rollgrupperna kräver direkt medlemskap och får inte innehålla Azure AD-grupper. Idag stöds inte de här rollgrupperna av Azure AD PIM. Precis som med Azure AD-roller rekommenderar jag en hantering av dessa via API:er eller en produkt för partnerstyrning som Synynt eller andra.

Roller & Efterlevnadscenter omfattar Microsoft 365 och du kan inte begränsa rollgrupperna till en delmängd i miljön (på samma sätt som med administrativa enheter i Azure AD). Många kunder frågar hur de kan välja att underdeportera. Till exempel "skapa en DLP-princip endast för EU-användare". Om du i dag har rättigheter till en viss funktion i Säkerhets- & Efterlevnadscenter har du rättigheter till allt som omfattas av den här funktionen i klientorganisationen. Många principer har emellertid funktioner för att rikta en delmängd av miljön (till exempel "gör de här [etiketterna endast](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy) tillgängliga för dessa användare"). Korrekt styrning och kommunikation är en viktig komponent för att undvika konflikter. Vissa kunder väljer att implementera en metod som kallas konfiguration som kod för att hantera underdelegering i säkerhets- & efterlevnadscenter. Vissa specifika tjänster har stöd för underdelegering (se nedan).

Det är värt att notera att kontroller som för närvarande hanteras via Säkerhets- & efterlevnadscenter (protection.office.com) håller på att migreras till två separata administrationsportaler: security.microsoft.com och compliance.microsoft.com. Förändring är den enda konstanten!

### <a name="service-specific"></a>Tjänstspecifik

Som vi nämnt tidigare vill många kunder uppnå en mer detaljerad delegeringsmodell. Ett vanligt exempel: "Hantera XYZ-tjänsten endast för division X-användare och -platser" (eller någon annan dimension). Möjligheten att göra detta beror på varje tjänst och är inte konsekvent mellan tjänster och funktioner. Dessutom kan varje tjänst ha en separat och unik RBAC-modell. I stället för att diskutera alla dessa (det tar evigheter) lägger jag till relevanta länkar för varje tjänst. Det här är inte en fullständig lista, men det hjälper dig att komma igång.

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators) 
- **Microsoft Teams**  -  [https://docs.microsoft.com/microsoftteams/itadmin-readiness](https://docs.microsoft.com/microsoftteams/itadmin-readiness )
- **eDiscovery** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](https://docs.microsoft.com/microsoft-365/compliance/) 
  + **Behörighetsfiltrering**  -  [https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search](https://docs.microsoft.com/microsoft-365/compliance/)
  + **Efterlevnadsgränser**  -  [https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries )
  + **Advanced eDiscovery**  -  [https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 )
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins) 
- **Multi-geo** - [https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin](https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin) 
- **Dynamics 365** – [https://docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/) <br>
  Obs! Den här länken finns i roten till dokumentationen. Det finns flera typer av tjänster med variationer i modellen för administration/delegering.
- **Power Platform**  -  [https://docs.microsoft.com/power-platform/admin/admin-documentation](https://docs.microsoft.com/power-platform/admin/admin-documentation )
  + **Power-appar**  -  [https://docs.microsoft.com/power-platform/admin/wp-security](https://docs.microsoft.com/power-platform/admin/wp-security ) <br>
    Obs! Det finns flera typer med variationer i modeller för administratörer och delegering.
  + **Power Automate**  -  [https://docs.microsoft.com/power-automate/environments-overview-admin](https://docs.microsoft.com/power-automate/environments-overview-admin )
  + **Power BI**  -  [https://docs.microsoft.com/power-bi/service-admin-governance](https://docs.microsoft.com/power-bi/service-admin-governance ) <br>
Obs! Säkerheten och delegering av dataplattformen (som Power BI är en komponent i) är ett komplext område.
- **MEM/Intune**  -  [https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control )
- **Microsoft Defender för Slutpunkt**  -  [https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles )
- **Microsoft 365 Defender** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions)
- **Microsoft Cloud App-säkerhet** - [https://docs.microsoft.com/cloud-app-security/manage-admins](https://docs.microsoft.com/cloud-app-security/manage-admins)
- **Streama**  -  [https://docs.microsoft.com/stream/assign-administrator-user-role](https://docs.microsoft.com/stream/assign-administrator-user-role )
- **Informationsbarriärer**  -  [https://docs.microsoft.com/microsoft-365/compliance/information-barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers )

För resten har sökning i Dokument varit riktigt bra på sistone - [https://docs.microsoft.com/](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) . 

### <a name="activity-logs"></a>Aktivitetsloggar

Office 365 har en [enhetlig granskningslogg.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) Det är en mycket [detaljerad logg,](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)men läs inte för mycket i namnet. Den kanske inte innehåller allt du vill ha eller behöver för dina säkerhets- och efterlevnadsbehov. Vissa kunder är också mycket intresserade av [Avancerad granskning.](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit)

Exempel på Microsoft 365-loggar som används via andra API:er är följande:

- [Azure AD](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) (aktiviteter som inte är relaterade till Office 365)
- [Spårning av Exchange-meddelanden](https://docs.microsoft.com/powershell/module/exchange/get-messagetrace)
- Hot/UEBA-system som nämns ovan (till exempel Azure AD Identity Protection, Microsoft Cloud App Security, Microsoft Defender för Endpoint och så vidare)
- [Informationsskydd från Microsoft](https://docs.microsoft.com/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide)
- [Microsoft Defender för Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

Det är viktigt att först identifiera alla loggkällor som behövs för ett säkerhets- och efterlevnadsprogram. Observera även att olika loggar har olika lagringsbegränsningar på rad. 

Ur administratörsdelegeringsperspektiv har de flesta Microsoft 365-aktivitetsloggar inte en inbyggd RBAC-modell. Om du har behörighet att se en logg kan du se allt i den. Ett vanligt exempel på ett kundkrav är: "Jag vill kunna fråga aktivitet endast för EU-användare" (eller någon annan dimension). För att kunna uppfylla det här kravet måste vi överföra loggar till en annan tjänst. I Microsoft-molnet rekommenderar vi att du överför det till [antingen Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview) eller [Log Analytics.](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) 

Översiktsdiagram:

![Diagram över loggkällor för ett säkerhets- och efterlevnadsprogram](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

Diagrammet ovan representerar inbyggda funktioner för att skicka loggar till Event Hub och/eller Azure Storage och/eller Azure Log Analytics. Alla system innehåller inte den här inbyggda datarutan ännu. Men det finns andra sätt att skicka loggarna till samma lagringsplats. Se till exempel [Skydda dina Teams med Azure Sentinel.](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761)

Om du kombinerar alla loggar till en lagringsplats innebär det ytterligare fördelar, till exempel korskorrelationer, anpassade bevarandetider, utökad med data som behövs för stöd för RBAC-modellen och så vidare. När data finns i det här lagringssystemet kan du skapa en Power BI-instrumentpanel (eller annan typ av visualisering) med en lämplig RBAC-modell.

Loggar behöver inte dirigeras till en enda plats. Det kan också vara bra att integrera [Office 365-loggar](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) med Microsoft Cloud App Security eller en anpassad RBAC-modell i [Power BI.](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics?view=o365-worldwide) Olika lagringsplatsen har olika fördelar och målgrupper.

Det är värt att nämna att det finns ett mycket omfattande inbyggt analyssystem för säkerhet, hot, svagheter och så vidare i en tjänst som kallas [Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)

Många stora kunder vill överföra dessa loggdata till ett tredjepartssystem (till exempel SIEM). Det finns olika metoder för detta, men i allmänhet [är Azure Event Hub](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) och [Graph](https://docs.microsoft.com/graph/security-integration) bra utgångspunkter.

### <a name="azure"></a>Azure

Jag blir ofta tillfrågad om det finns något sätt att separera roller med hög behörighet mellan Azure AD, Azure och SaaS (t.ex.: Global administratör för Office 365 men inte Azure).  Inte riktigt.  Arkitektur med flera klientorganisationer krävs om fullständig administrativ avgränsning krävs, men det ökar [komplexiteten](https://aka.ms/multi-tenant-user) (se ovan). Alla dessa tjänster är en del av samma säkerhets- och identitetsgräns (se hierarkimodellen ovan).  

Det är viktigt att förstå relationer mellan olika tjänster i samma klientorganisation. Jag arbetar med många kunder som bygger affärslösningar över Azure, Office 365 och Power-plattformen (och ofta även lokala och molnbaserade tjänster från tredje part). Ett vanligt exempel:

1. Jag vill samarbeta i en uppsättning dokument/bilder/etc.(Office 365)
2. Skicka var och en av dem via en godkännandeprocess (Power Platform)
3.  När alla komponenter har godkänts sätter du ihop dem till en enhetlig slutbar produkt (Azure) [Microsoft Graph API.](https://docs.microsoft.com/azure/active-directory/develop/microsoft-graph-intro)  Inte omöjligt, men betydligt mer komplext att utforma en lösning som spänner [över flera klientorganisationar.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)

Med Azure Role-Based Access Control (RBAC) kan du hantera enkel åtkomst för Azure. Med hjälp av RBAC kan du hantera åtkomst till resurser genom att bevilja användare de minsta behörigheterna som behövs för att utföra deras jobb. Informationen är inte omfångsbaserad för det här dokumentet, men mer information om RBAC finns i Vad är rollbaserad åtkomstkontroll [(RBAC) i Azure?](https://docs.microsoft.com/azure/role-based-access-control/overview) RBAC är viktigt, men endast en del av hanteringsöverväganden för Azure. [Cloud Adoption Framework](https://docs.microsoft.com/azure/cloud-adoption-framework/govern/) är en bra utgångspunkt för att lära dig mer. Jag gillar hur min vän Andres Ochres Ellert väg runt kunderna steg för steg går igenom olika komponenter för att avgöra vilken metod jag ska välja. Vyn på hög nivå för olika element (inte lika bra som processen för att komma till faktisk kundmodell) ser ut ungefär så här:

![Vy på hög nivå av Azure-komponenter för delegerad administration](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

Som du kan se ovanifrån bör många andra tjänster ses som [](https://docs.microsoft.com/azure/governance/policy/overview)en del av designen (t.ex. Azure-principer, [](https://docs.microsoft.com/azure/governance/management-groups/) [Azure-ritningar,](https://docs.microsoft.com/azure/governance/blueprints/overview)hanteringsgrupper och så vidare).

## <a name="conclusion"></a>Sammanfattning

Den startades som en kort sammanfattning längre än förväntat.  Jag hoppas att du nu är redo att ge dig in i en djup förståelse av hur du skapar delegeringsmodell för din organisation.  Den här konversationen är mycket vanlig med kunder. Det finns ingen modell som fungerar för alla. Väntar på några planerade förbättringar från Microsoft Engineering innan vi dokumenterar vanliga mönster som vi ser för kunder. Under tiden kan du samarbeta med ditt Microsoft-kontoteam för att ordna ett besök på närmaste [Microsoft Technology Center.](https://www.microsoft.com/mtc)  Vi ser dig!
