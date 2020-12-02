---
title: Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska Data Center-regionerna
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 'Sammanfattning: förstå migrering från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster i det nya tyska data centret.'
ms.openlocfilehash: 37bf052739bf15c1a0d3712539779e9dff31d9e8
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551540"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska Data Center-regionerna

> [!NOTE]
> Den här artikeln gäller endast kvalificerade Microsoft Cloud Deutschland-kunder.

I augusti 2018 presenterade Microsoft vårt avsikt att leverera hela Microsoft Cloud – Azure, Office 365, Dynamics 365 och Power Platform – från nya moln regioner i Tyskland för att bättre kunna aktivera den digitala omvandlingen av våra kunder. I augusti 2019 tillkännagede vi att vi nu håller på att öppna de nya moln regionerna i Tyskland. Vi har sedan fått tillgänglighet för Azure, Office 365, Dynamics 365 och Power Platform.

De nya regionerna är utformade för att hantera de föränderliga behoven hos tyska kunder med mer flexibelt, de senaste intelligenta moln tjänsterna och fullständig anslutning till vårt Microsoft 365-tjänst moln nätverk samt kund data de i Tyskland.

## <a name="how-to-migrate-to-the-new-german-regions"></a>Så här migrerar du till de nya tyska regionerna

Befintliga Microsoft Cloud Deutschland-kunder kan nu börja migrera sin Office 365, Dynamics 365 kund engagemang och Power Platform-kunder. Det första steget är att [välja ett Microsoft-LED-migrering](https://aka.ms/office365germanymoveoptin) till våra nya tyska Data Center områden.

För organisationer som väljer Microsoft-drivna tillvägagångs sätt förväntas migreringarna från början i 2021 och kommer att slutföras senast den 29 oktober 2021. Som ett resultat av migreringen flyttas grundläggande kund uppgifter och abonnemang till de nya tyska regionerna.

Den här artikeln innehåller en översikt över Microsoft-drivna tillvägagångs sättet för migreringen, tydlighets upplevelsen för både användare och administratörer under och efter migreringen, och åtgärder som kan krävas för kunder baserat på vilka arbets uppgifter du använder.

Följande tjänster migreras som en del av Microsoft-driven-metoden:

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive för företag

- Skype för företag – Online\*\*
- Grupper i Office 365
- Dynamics 365/Power Platform\*\*\*

\*\*Under migreringen från Microsoft Cloud Deutschland till tyska Data Center-områdena övergår befintliga Skype för företag – Online-kunder till Microsoft Teams. Mer information finns i [komma igång med Microsoft Teams-uppgraderingen](https://aka.ms/SkypeToTeams-Home) .

\*\*\*Förutsättningar och konsekvenserna av migrering för dessa tjänster beskrivs i artikeln om [kund engagemang i Dynamics 365](https://aka.ms/d365ceoptin) .

Office 365 Video dras tillbaka den 1 mars 2021. Om du väljer att migrera din Office 365-klient till de nya tyska Data Center-regionerna kommer Office 365-videon inte att stödjas efter att SharePoint Online-migreringen är klar. Mer information finns i [Microsoft Cloud Deutschland Timeline](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).

## <a name="how-is-the-migration-organized"></a>Hur är migreringen organiserad?

Den här bilden visar de olika komponenterna i Office 365 och Dynamics 365 i migreringen till de nya tyska Data Center.

![Komponenter i Office 365 och Dynamics 365 i migreringen till de nya Tyskland](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Migrering utförs i faser som alla startar när du [väljer att migrera](https://aka.ms/office365germanymoveoptin). De flesta migrations faserna utförs som backend-tjänster med minsta möjliga kund interaktion och genomförs en fas efter den andra. Start för ytterligare kund LED-uppgifter och status för fullständig migrering meddelas via meddelande Center i administrations centret för Microsoft 365 under migreringen. Exempel på uppgifter kan inkludera Kundhanterade DNS-uppdateringar, omkonfigurering av hybrid inställningar för Exchange-hybridprodukter eller Azure migration.

Migreringen börjar inte när deltagande inträffar. Din organisation läggs till i listan över innehavare som är schemalagda för senare migrering. Du kan börja använda faserna nu eftersom det är viktigt att få en lyckad migrering och användning när den är klar:

- [Åtgärder och konsekvenser för migreringen](ms-cloud-germany-transition-phases.md)
- [Övrig för hands arbete](ms-cloud-germany-transition-add-pre-work.md)

En vecka innan klient organisationens början börjar, kommer du att få ett meddelande i Message Center-tjänsten som en slutgiltig varning om att alla förutsättningar måste vara klara.

Migreringen kommer att flytta din Azure AD-klient från den andra Tyskland Azure AD-tjänsten till Office 365 Services-instansen av Azure AD i EU-regionen.

Nästa steg är migreringen av klient organisationen&#39;s abonnemang och användar licenser från Tyskland-specifika produkter.

När alla steg är klara inklusive Azure migration för kunder är din klient för tillfället färdig i Office 365-tjänsterna och migreringen har marker ATS som slutförd. I det här läget tillhandahålls den senaste uppdateringen till meddelande Center. Klient organisationen är nu inte en helt global Office 365-organisation.

Du får ett meddelande om migrerings förlopp med inlägg i meddelande Center. Inläggen görs med specifika mil stolpar och ger vägledning om hur steget fortskrider samt viktig information för kunder att fungera baserat på process kraven. Meddelande Center-meddelanden tillhandahålls i följande mil stolpar:

- Början av migrering (fem arbets dagar innan Azure AD migration börjar)
- Azure AD migration färdig
- Migrering av abonnemang och licenser färdig
- SharePoint-migrering färdig
- Exchange-migrering slutförd
- Skype för företag-slutfört
- Dynamik klar
- Power BI färdigt
- Slutgiltig snabbmigrering av tjänsterna är färdig

## <a name="moving-to-the-new-german-regions"></a>Flytta till de nya tyska regionerna

Befintliga Microsoft Cloud Germany (Microsoft Cloud Deutschland) kunder kan nu börja migrera sina Office 365-, Dynamics 365-kund åtaganden och Power Platform-kunder. Det första steget är att [välja ett Microsoft-LED-migrering](https://aka.ms/office365germanymoveoptin) till våra nya tyska Data Center områden. När du förnyar prenumerationen ska du automatiskt välja ett Microsoft-kundbaserad migrering. Microsoft meddelar kundernas klient organisationer med e-post och i meddelande centret för Microsoft 365 Admin Center när det här inträffar. Men om du föredrar att starta processen nu kan du [välja](https://aka.ms/office365germanymoveoptin) direkt i Microsoft 365 Admin Center idag. Migreringar förväntas starta tidigt 2021 och kommer att slutföras senast den 29 oktober 2021. 

Som ett resultat av migreringen flyttas grundläggande kund uppgifter och abonnemang till de nya tyska regionerna.

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Förbereda för migrering till Office 365-tjänster i de nya tyska Data Center-regionerna

Det första steget är att meddela Microsoft så att vi har din tillåtelse att migrera ditt abonnemang och dina uppgifter från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska Data Center-områdena. Se vad du ska [säga](https://aka.ms/office365germanymoveoptin) för att få anvisningar och notera att:

- Alla som migrerar kunder måste kontrol lera anslutningen till Office 365 [-tjänsterna office 365-URL: er och IP-adresser](urls-and-ip-address-ranges.md), som innehåller de nya tyska Data Center-regionerna. Inåtgärd kan leda till tjänst-och klient fel.
- Granska listan över aktiviteter för [arbete](ms-cloud-germany-transition-add-pre-work.md) för att säkerställa att din organisation är informerad och försäkrad för ändringarna.
- Du bör läsa beskrivningen av Office 365 Platform service för att förstå vilka funktioner och tjänster som kommer att bli tillgängliga för din organisation efter migreringen till det tyska området.
- Utvärderings prenumerationer migreras inte och blockerar migrering av alla betalda abonnemang. Du måste annullera alla försök eller konvertera till betalda abonnemang innan migreringen påbörjas.

## <a name="where-do-i-go-from-here"></a>Var hamnar jag härifrån?

Läs följande vanliga frågor och svar.

## <a name="frequently-asked-questions"></a>Vanliga frågor

### <a name="is-migration-required"></a>Krävs migrering?

Microsoft erbjuder Office 365-innehavaradministration från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska Data Center-regionerna utan extra kostnad. Även om vi rekommenderar att du väljer att migrera till de nya tyska Data Center-regionerna fortsätter vi att tillhandahålla de nödvändiga säkerhets uppdateringarna till Microsoft Cloud Deutschland-regionen.

Office 365-tjänster i de nya tyska Data Center-områdena:

- Ge marknads konkurrens kraftiga priser för [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 kund engagemang](https://dynamics.microsoft.com/pricing/)och [Power BI](https://powerbi.microsoft.com/pricing/).
- Är ansluten till Microsoft&#39;s globala nätverk, erbjuder hundratals webbplatser för nätverks kant, peering-placering och utgångs punkter för att tillhandahålla en robust användar upplevelse överallt i världen.
- Hjälp med att möta lokala kund uppgifter de krav i Tyskland.
- Leverera vårt fullständiga globala moln erbjudande med de senaste versionerna av våra tjänster och nya funktioner, bland annat Microsoft Teams och multi-geo i Office 365. Jämför produkter efter region för [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md)och [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- Ge full funktionalitet, säkerhet på företags nivå och omfattande funktioner som hjälper kunder att uppfylla efterlevnad och myndighets krav.
- Är tillgängliga via befintliga Online Services-kontrakt.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Vad är tjänst tillgänglighet mellan de olika Office 365 Cloud Service-tjänsterna?
<h2 id="serv-avail"></h2>

Följande 15 tjänster är tillgängliga i tillägget Microsoft Cloud Deutschland Cloud service. Vi lägger inte till nya tjänster i Microsoft Cloud Deutschland.

1. Exchange Online
2. Kund lås (Exchange Online)
3. Grupper (moderna grupper)
4. Delve-profil
5. Exchange Online Protection
6. Defender för Office 365
7. Advanced eDiscovery
8. Data styrning
9. SharePoint Online
10. Kund lås (SharePoint Online)
11. OneDrive för företag
12. Skype för företag online
13. Word Online, Excel Online, PowerPoint, OneNote, Visio online
14. Office 365 Pro plus
15. Outlook Mobile

Det finns för närvarande 29 tjänster tillgängliga som en del av Office 365-tjänsterna i de nya tyska Data Center-regionerna. Nya funktioner och tjänster kommer att vara tillgängliga konsekvent med globala Office 365-tjänster.

1. Exchange Online
2. Kund lås för Exchange Online
3. Microsoft 365-grupper
4. Delve-profil
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Defender för Office 365
9. Advanced eDiscovery
10. Avancerad säkerhets hantering
11. Information Rights Management
12. Data styrning
13. SharePoint Online
14. Kund lås för SharePoint Online
15. OneDrive för företag
16. Microsoft Stream
17. Skype för företag (migreras till Microsoft Teams under migreringen)
18. Cloud PBX
19. PSTN-konferens
20. PSTN-samtal
21. Microsoft Teams
22. Rapporter om administratör/användning
23. Word Online, Excel Online, PowerPoint, OneNote och Visio online
24. Planner
25. Sway
26. Microsoft 365-applikationer
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, Intune och Rights Management Service)
29. Yammer online

### <a name="when-will-migration-happen"></a>När sker migrering?

**Azure**

Om du bara är en Azure-kund kan du börja [migrera](https://docs.microsoft.com/azure/germany/germany-migration-main) dina Azure-resurser till en annan region idag. 

Om du har Azure med Office 365, Dynamics 365 eller Power BI måste du följa migreringsprocessen för att säkerställa AzureAD innan du påbörjar den självgående Azure-migreringen. Du måste slutföra Azure migrationen innan tjänsten stängs för att behålla din Azure-arbets börda med din AzureAD och Office 365-organisationen.

**Office 365**

[Anmäl](https://aka.ms/office365germanymoveoptin) dig till Microsoft-driven migration idag. När vi är redo att påbörja migreringen meddelar vi dig via meddelande Center i administrations centret för Microsoft 365.

**Dynamics 365 och Power BI**

Anmäl dig till Microsoft-driven migration för [Dynamics 365 kund engagemang](https://aka.ms/D365ceOptIn) och [Power BI](https://aka.ms/PBIOptIn) idag. När vi är redo att påbörja migreringen meddelar vi dig via meddelande Center i administrations centret för Microsoft 365.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>Kommer priset att ändras för Office 365-tjänsterna som jag använder?

Ja. Priser i Microsoft&#39;s globala moln regioner (inklusive de nya data Center regionerna) är allmänt lägre.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Vilka SKU: er och licenser läggs till i organisationen och användarna?

Under migreringen från Microsoft Cloud Deutschland till Office 365-tjänsterna ersätts de Tyskland-specifika SKU: erna med globala versioner av samma eller liknande SKU. I de flesta fall finns SKU: er i Office 365-tjänster, men det finns bara några saker där SKU i Tyskland inte längre är tillgänglig i Office 365-tjänsterna. Om du vill uppdatera den SKU som har tilldelats till din organisation när migreringen har slutförts, kontaktar du säljaren för att lägga till eller ändra de tilldelade tjänsterna.

| Microsoft Cloud Deutschland – Product SKU (DE) | Microsoft Cloud global-produkt-SKU (WW) |
| --- | --- |
| Från vilken kund \_ de är (låst \_ de) | Kund lås (låst) |
| Dynamics 365 Enterprise Edition – ytterligare databas lagring \_ de (CRMSTORAGE \_ de) | Dynamics 365 Enterprise Edition-ytterligare databas lagring (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition-ytterligare icke-produktionsenhet \_ (CRMTESTINSTANCE \_ de) | Dynamics 365 Enterprise Edition-ytterligare icke-produktionsenhet (CRMTESTINSTANCE) |
| Dynamics 365 för kund tjänst Enterprise Edition \_ de (DYN365 \_ företags \_ kund \_ tjänst \_ de) | Dynamics 365 för kund tjänst Enterprise Edition (DYN365 \_ Enterprise \_ kund \_ Service) |
| Dynamics 365 för försäljning Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Sales \_ de) | Dynamics 365 för försäljning Enterprise Edition (DYN365 \_ Enterprise \_ Sales) |
| Dynamics 365 för team members Enterprise Edition \_ de (DYN365 \_ företags \_ grupp \_ medlemmar \_ de) | Dynamics 365 för team medlemmar Enterprise Edition (DYN365 \_ företags \_ grupp \_ medlemmar) |
| Dynamics 365 abonnemang 1 Enterprise Edition \_ de (DYN365 \_ Enterprise \_ PLAN1 \_ de) | Dynamics 365 abonnemang 1 Enterprise Edition (DYN365 \_ Enterprise \_ PLAN1) |
| ECAL Services (EOA, EOP, DLP) \_ de (ECAL \_ tjänster \_ de) | ECAL Services (EOA, EOP, DLP) (ECAL \_ -tjänster) |
| Företags mobilitet + säkerhet E3 \_ de (EMS \_ de) | Företags mobilitet + säkerhet E3 (EMS) |
| Exchange Online (abonnemang 1) \_ de (EXCHANGESTANDARD \_ de) | Exchange Online (abonnemang 1) (EXCHANGESTANDARD) |
| Exchange Online (abonnemang 2) \_ de (EXCHANGEENTERPRISE \_ de) | Exchange Online (abonnemang 2) (EXCHANGEENTERPRISE) |
| Exchange Online-arkivering för Exchange Online \_ de (EXCHANGEARCHIVE \_ addon \_ de) | Exchange Online-arkivering för Exchange Online (EXCHANGEARCHIVE \_ addon) |
| Exchange Online-arkivering för Exchange Server \_ de (EXCHANGEARCHIVE \_ de) | Exchange Online-arkivering för Exchange Server (EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ de (Exchange \_ S \_ Essentials \_ de) | Exchange Online Essentials (EXCHANGE \_ S \_ Essentials) |
| Exchange Online \_ -kiosk de (EXCHANGEDESKLESS \_ de) | Exchange Online-kiosk (EXCHANGEDESKLESS) |
| Exchange Online Protection \_ de (EOP \_ Enterprise \_ de) | Exchange Online Protection (EOP \_ Enterprise) |
| Microsoft 365 Business Standard (O365 \_ Business \_ Premium) | Microsoft 365 Business Standard (O365 \_ Business \_ Premium) |
| Microsoft Dynamics CRM Online instance \_ de (CRMINSTANCE \_ de) | Microsoft Dynamics CRM Online-instans (CRMINSTANCE) |
| Office 365 a1 för lärare \_ de (STANDARDWOFFPACK \_ fakulteten \_ de) | Office 365 a1 för lärare (STANDARDWOFFPACK \_ lärare) |
| Office 365 a1 för elever \_ de (STANDARDWOFFPACK \_ student \_ de) | Office 365 a1 för studenter (STANDARDWOFFPACK \_ student) |
| Office 365 avancerad efterlevnad \_ de (EQUIVIO \_ Analytics \_ de) | Microsoft 365 E5-efterlevnad (informations \_ skydd \_ ) |
|Microsoft Defender för Office 365 (abonnemang 1) \_ de (ATP \_ Enterprise \_ de) |Microsoft Defender för Office 365 (abonnemang 1) (ATP \_ Enterprise) |
| Office 365 Business Essentials \_ (O365 \_ Business \_ Essentials \_ de) | Microsoft 365 Business Basic (O365 \_ Business \_ Essentials) |
| Office 365 Business Premium \_ de (O365 \_ Business \_ Premium \_ de) | Microsoft 365 Business Standard (O365 \_ Business \_ Premium) |
| Office 365 Business \_ de (O365 \_ Business \_ de) | Microsoft 365-appar för företag (O365 \_ Business) |
| Office 365 E1 \_ de (STANDARDPACK \_ de) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 utan ProPlus \_ de (ENTERPRISEPACKWITHOUTPROPLUS \_ de) | Office 365 E3 utan ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ de (STANDARDPACK \_ de) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Office 365 extra File Storage \_ de (SHAREPOINTSTORAGE \_ de) | Office 365 extra fil lagring (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ de (DESKLESSPACK \_ de) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus för lärare \_ de (OFFICESUBSCRIPTION \_ fakulteten \_ de) | Office 365 ProPlus för lärare (OFFICESUBSCRIPTION \_ lärare) |
| Office 365 ProPlus för elever \_ de (OFFICESUBSCRIPTION \_ student \_ de) | Office 365 ProPlus för studenter (OFFICESUBSCRIPTION \_ student) |
| Office 365 ProPlus \_ de (OFFICESUBSCRIPTION \_ de) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| OneDrive för företag (abonnemang 1) \_ de (WACONEDRIVESTANDARD \_ de) | OneDrive för företag (abonnemang 1) (WACONEDRIVESTANDARD) |
| OneDrive för företag (abonnemang 2) \_ de (WACONEDRIVEENTERPRISE \_ de) | OneDrive för företag (abonnemang 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro för lärare \_ de (Power \_ bi \_ Pro \_ fakultet \_ de) | Power BI Pro för lärare (POWER \_ bi \_ Pro \_ -lärare) |
| Power BI Pro \_ de (Power \_ bi \_ Pro \_ de) | Power BI Pro (POWER \_ bi \_ Pro) |
| Project Online Essentials \_ de (PROJECTESSENTIALS \_ de) | Project Online Essentials (PROJECTESSENTIALS) |
| Project Online Premium \_ de (PROJECTPREMIUM \_ de) | Project Online Premium (PROJECTPREMIUM) |
| Project Online Professional \_ de (PROJECTPROFESSIONAL \_ de) | Project Online Professional (PROJECTPROFESSIONAL) |
| Project plan 3 \_ de (PROJECTPROFESSIONAL \_ de) | Project-plan 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ de (ENTERPRISEWITHSCAL \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (abonnemang 1) \_ de (SHAREPOINTSTANDARD \_ de) | SharePoint Online (abonnemang 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (abonnemang 2) \_ de (SHAREPOINTENTERPRISE \_ de) | SharePoint Online (abonnemang 2) (SHAREPOINTENTERPRISE) |
| Skype för företag – Online (abonnemang 1) \_ de (MCOIMP \_ de) | Office 365 E1 (STANDARDPACK) |
| Skype för företag – Online (abonnemang 1) \_ de (MCOIMP \_ de) | Skype för företag – Online (abonnemang 1) (MCOIMP) |
| Skype för företag – Online (abonnemang 2) \_ de (MCOSTANDARD \_ de) | Skype för företag – Online (abonnemang 2) (MCOSTANDARD) |
| Skype för företag Plus CAL \_ de (MCOPLUSCAL \_ de) | Skype för företag Plus CAL (MCOPLUSCAL) |
| Visio Online abonnemang 1 för lärare \_ (VISIOONLINE \_ PLAN1 \_ FAC \_ de) | Visio Online abonnemang 1 för lärare (VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio Online abonnemang 1 \_ de (VISIOONLINE \_ PLAN1 \_ de) | Visio Online-abonnemang 1 (VISIOONLINE \_ PLAN1) |
| Visio Online abonnemang 2 för lärare \_ (VISIOCLIENT \_ fakulteten \_ de) | Visio Online abonnemang 2 för lärare (VISIOCLIENT \_ lärare) |
| Visio Online abonnemang 2 \_ de (VISIOCLIENT \_ de) | Visio Online abonnemang 2 (VISIOCLIENT) |
| Visio abonnemang 1 \_ de (VISIOONLINE \_ PLAN1 \_ de) | Visio-abonnemang 1 (VISIOONLINE \_ PLAN1) |
| Visio-abonnemang 2 \_ de (VISIOCLIENT \_ de) | Visio-abonnemang 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Hur får jag hjälp från Microsoft att migrera till ett nytt område eller besvara support frågor?

Om du har frågor kan du kontakta oss eller din partner:

- För Azure kan du skicka [nya support förfrågningar](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) i Azure-portalen.
- För Office 365 kan du skicka frågor med hjälp av &quot; Hjälp? &quot; länken till [administrations centret för Microsoft 365](https://portal.office.de/).
- Om du är Dynamics 365 kund engagemang och Power BI-kund och även har Office 365 kan du skicka frågor med hjälp av &quot; Hjälp? &quot; länken till [Microsoft 365 Admin Center](https://portal.office.de/). Dynamics 365 support alternativ för kund åtagande finns [här](https://docs.microsoft.com/dynamics365/get-started/support/). Support alternativen för Power BI finns [här](https://powerbi.microsoft.com/support/).


## <a name="next-step"></a>Nästa steg

[Välj till migrering](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>Mer information

Komma igång:

- [Hjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kund upplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom över gången:

- [Åtgärder och konsekvenser för migreringen](ms-cloud-germany-transition-phases.md)
- [Övrig för hands arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information om [tjänster](ms-cloud-germany-transition-add-general.md), [enheter](ms-cloud-germany-transition-add-devices.md), [erfarenheter](ms-cloud-germany-transition-add-experience.md)och [AD FS](ms-cloud-germany-transition-add-adfs.md).

Molnappar:

- [Information om programmet för Dynamics 365 migration](https://aka.ms/d365ceoptin)
- [Information om datamigreringshanteraren för Power BI](https://aka.ms/pbioptin)
- [Komma igång med din uppgradering av Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
