---
title: Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska datacenterområdena
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
description: 'Sammanfattning: Förstå migreringen från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterområdet.'
ms.openlocfilehash: d807637e9d5469131d3124d1ef8b6b1f874e81a1
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145421"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska datacenterområdena

> [!NOTE]
> Den här artikeln gäller endast för berättigade Microsoft Cloud Deutschland-kunder.

I augusti 2018 meddelade Microsoft vår avsikt att tillhandahålla ett komplett Microsoft-moln – Azure, Office 365, Dynamics 365 och Power Platform – från nya molnområden i Tyskland för att möjliggöra en digital omvandling av våra kunder. I augusti 2019 meddelade vi att vi nu håller på att öppna de nya molnområdena i Tyskland. Vi har sedan dess meddelat om tillgängligheten för Azure- och Office 365-, Dynamics 365- och Power-plattformen.

De nya regionerna är utformade för att tillgodose de föränderliga behoven hos tyska kunder med större behov, de senaste intelligenta molntjänsterna och fullständig anslutning till vårt molnnätverk för Microsoft 365-tjänster samt kunddata som finns i Tyskland.

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>Så här migrerar du till de nya tyska datacenterområdena

Befintliga Microsoft Cloud Deutschland-kunder kan nu börja migrera sina Office 365-, Dynamics 365 Customer Engagement- och Power Platform-kunder. Det första steget är att [registrera dig för en Microsoft-ledd migrering till](https://aka.ms/office365germanymoveoptin) våra nya tyska datacenterområden.

För organisationer som väljer den Microsoft-drivna metoden beräknas migreringar att starta i början av 2021 och slutföras senast den 29 oktober 2021. På grund av migreringen flyttas basdata för kunder och prenumerationer till de nya tyska regionerna.

Den här artikeln innehåller en översikt över den Microsoft-drivna migreringsprocessen, information om upplevelser för både användare och administratörer under och efter migreringen och åtgärder som kan krävas för kunder baserat på vilka arbetsbelastningar du använder.

Följande tjänster migreras som en del av den Microsoft-drivna metoden:

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive för företag

- Skype för företag – Online\*\*
- Grupper i Office 365
- Dynamics 365 / Power Platform\*\*\*

\*\*Under migreringen från Microsoft Cloud Deutschland till de tyska datacenterområdena går befintliga Skype för företag – Online-kunder över till Microsoft Teams. Mer information [finns i Komma igång med uppgraderingen till Microsoft Teams.](https://aka.ms/SkypeToTeams-Home)

\*\*\*Krav och påverkan på migreringen för de här tjänsterna beskrivs i [artikeln Dynamics 365 Customer engagement.](https://aka.ms/d365ceoptin)

Office 365 Video dras tillbaka den 1 mars 2021. Om du väljer att migrera Office 365-klienten till de nya tyska datacenterområdena stöds inte Office 365 Video när SharePoint Online-migreringen är klar. Mer information finns på [tidslinjen i Microsoft Cloud Deutschland.](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-is-the-migration-organized"></a>Hur organiseras migreringen?

I den här bilden visas de nio faserna av migreringen till de nya tyska datacenteren.

![De nio faserna av migreringen till de nya Tyskland-datacenter](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

De här faserna startar [när du väljer att migrera.](https://aka.ms/office365germanymoveoptin) De flesta av migreringsfaserna utförs som tjänståtgärder i backend med minimal kundinteraktion som krävs och körs en fas efter den andra. Start för ytterligare kundledda uppgifter och övergripande migreringsstatus meddelas via meddelandecentret i administrationscentret för Microsoft 365 under migreringsprocessen. Exempel på uppgifter kan vara DNS-uppdateringar som hanteras av kunder, konfiguration av hybridkonfiguration för Exchange-hybridkunder eller Azure-migrering.

Migreringen påbörjas inte direkt när anmälning sker. Organisationen läggs till i listan över klientorganisationar som är schemalagda för senare migrering. Du kan börja faserna före arbetet nu eftersom dessa är viktiga för att säkerställa en lyckad migrering och användning vid slutförande:

- [Åtgärder och påverkan i migreringsfaser](ms-cloud-germany-transition-phases.md)
- [Ytterligare förarbete](ms-cloud-germany-transition-add-pre-work.md)

En vecka innan klientorganisationens migrering startar visas ett meddelande i tjänsten Meddelandecenter som en sista varning om att alla krav måste vara slutförda.

Migreringen flyttar din Azure AD-klient från den suveräna Tyskland Azure AD-tjänsten till Office 365-tjänstinstansen av Azure AD i EU-regionen.

Nästa steg är migreringen av klientorganisationens&#39;och användarlicenser från Tyskland-specifika produkter till globala produkter.

När alla steg har slutförts, inklusive azure-kundmigrering, slutförs klientorganisationen i Office 365-tjänsttjänsten och migreringen har markerats som slutförd. I det här läget får du den slutliga uppdateringen av Meddelandecenter. Klientorganisationen är nu en helt global Office 365-organisation.

Du får ett meddelande om migreringens förlopp med inlägg i Meddelandecenter. Inläggen kommer att ske vid specifika milstolpar och kommer att ge vägledning när det gäller ett steg samt viktig information som kunderna kan agera utifrån processkraven. Meddelanden i Meddelandecenter tillhandahålls vid följande milstolpar:

- Migreringens start (5 arbetsdagar innan Azure AD-migreringen påbörjas)
- Azure AD-migrering slutförd
- Prenumerations- och licensmigrering slutförd
- SharePoint-migrering slutförd
- Exchange-migrering slutförd
- Skype för företag har slutförts
- Dynamics är klar
- Power BI har slutförts
- Den slutliga övergången av tjänster är slutförd

## <a name="moving-to-the-new-german-datacenter-regions"></a>Flytta till de nya tyska datacenterområdena

Befintliga Microsoft Cloud Deutschland-kunder kan nu börja migrera sina Office 365-, Dynamics 365 Customer Engagement- och Power-plattformstjänster. Det första steget är att [registrera dig för en Microsoft-ledd migrering till](https://aka.ms/office365germanymoveoptin) våra nya tyska datacenterområden. När du förnyar prenumerationen anmäler du dig automatiskt till en Microsoft-assisterad migrering. Microsoft meddelar kundens innehavaradministratörer via e-post och i meddelandecentret i administrationscentret för Microsoft 365 när detta har hänt. Men om du föredrar att starta processen nu kan du [anmäla dig](https://aka.ms/office365germanymoveoptin) direkt i administrationscentret för Microsoft 365 idag. Migreringarna beräknas starta i början av 2021 och slutförs senast den 29 oktober 2021. 

På grund av migreringen flyttas basdata och prenumerationer till de nya tyska datacenterområdena.

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Förbereda migrering till Office 365-tjänster i de nya tyska datacenterområdena

Det första steget är att meddela Microsoft så att vi har ditt tillstånd att migrera din prenumeration och dina data från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska datacenterområdena. Se processen för [att registrera dig för instruktioner](https://aka.ms/office365germanymoveoptin) och observera att:

- Alla migrerande kunder behöver verifiera anslutningen till Office 365 Services [Office 365-URL:er](urls-and-ip-address-ranges.md)och IP-adresser, som omfattar de nya tyska datacenterområdena. Inaction kan resultera i tjänst- och klientfel.
- Granska listan med [aktiviteter före arbetet för](ms-cloud-germany-transition-add-pre-work.md) att säkerställa att organisationen är informerad och redo för ändringarna.
- Läs tjänstbeskrivningen för Office 365-plattformen för att förstå vilka funktioner och tjänster som blir tillgängliga för din organisation efter migreringen till den tyska regionen.
- Utvärderingsprenumerationer migreras inte och blockerar migreringen av alla betalda prenumerationer. Du måste avbryta utvärderingsversioner eller konvertera till betalda prenumerationer innan migreringen påbörjas.

## <a name="where-do-i-go-from-here"></a>Vart tar jag vägen härifrån?

Gå igenom avsnittet Vanliga frågor och svar.

## <a name="frequently-asked-questions"></a>Vanliga frågor

### <a name="is-migration-required"></a>Krävs migrering?

Microsoft erbjuder Office 365-klientmigrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska datacenterområdena utan extra kostnad. Vi rekommenderar starkt att du väljer att migrera till de nya tyska datacenterområdena, men vi kommer att fortsätta att tillhandahålla de säkerhetsuppdateringar som krävs för Microsoft Cloud Deutschland..

Office 365-tjänster i de nya tyska datacenterområdena:

- Erbjuda marknadspriser för [Azure,](https://azure.microsoft.com/pricing/calculator/) [Office 365,](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/)och Power [BI.](https://powerbi.microsoft.com/pricing/)
- Är anslutna till Microsoft&#39;globala nätverk, med hundratals nätverks edge-webbplatser, peeringplatser och utgående punkter för att ge en robust användarupplevelse var som helst i världen.
- Hjälper dig att uppfylla lokala krav för kundens datalagring i Tyskland.
- Leverera våra fullständiga och globala molntjänster med de senaste versionerna av våra tjänster och nya funktioner, inklusive Microsoft Teams och Multi-Geo i Office 365. Jämför produkter efter region för [Azure,](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central) [Office 365](o365-data-locations.md)och [Dynamics 365.](https://docs.microsoft.com/dynamics365/get-started/availability)
- Erbjuder fullständiga funktioner, säkerhet i företagsklass och omfattande funktioner som hjälper kunderna att uppfylla efterlevnads- och regelkrav.
- Är tillgängliga genom befintliga onlinetjänster.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Vad är tjänstens tillgänglighet mellan de olika Office 365-molntjänsterbjudandena?
<h2 id="serv-avail"></h2>

Följande 15-tjänster finns tillgängliga i Microsoft Cloud Deutschland-molntjänsterbjudandet. Vi lägger inte till nya tjänster i Microsoft Cloud Deutschland.

1. Exchange Online
2. Customer Lockbox (Exchange Online)
3. Grupper (moderna grupper)
4. Delve-profil
5. Exchange Online Protection
6. Defender förr Office 365
7. Advanced eDiscovery
8. Datastyrning i förväg
9. SharePoint Online
10. Customer Lockbox (SharePoint Online)
11. OneDrive för företag
12. Skype för företag online
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 Pro Plus
15. Outlook Mobile

Det finns för närvarande 39 tjänster som är tillgängliga som en del av Office 365-tjänster i de nya tyska datacenterområdena. Nya funktioner och tjänster blir ständigt tillgängliga, konsekvent med globala Office 365-tjänster.

1. Exchange Online
2. Customer Lockbox för Exchange Online
3. Microsoft 365-grupper
4. Delve-profil
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Defender förr Office 365
9. Advanced eDiscovery
10. Avancerad säkerhetshantering
11. Informationsskydd för Office 365 
12. Datastyrning i förväg
13. SharePoint Online
14. Customer Lockbox för SharePoint Online
15. OneDrive för företag
16. Microsoft Stream
17. Skype för företag (migreras till Microsoft Teams under migreringen)
18. Cloud PBX
19. PSTN-konferenser
20. PSTN-samtal
21. Microsoft Teams
22. Administrativa rapporter/användningsrapporter
23. Office på webben
24. Planner
25. Sway
26. Microsoft 365-applikationer
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, Intune och Rights Management Service)
29. Yammer Enterprise
30. Microsoft Forms
31. Power Automate för Office 365
32. Virtuella poweragenter för Office 365
33. PowerApps för Office 365
34. Microsoft Bookings
35. To-Do
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. Listor

### <a name="when-will-migration-happen"></a>När sker migreringen?

**Azure**

Om du bara är Azure-kund kan du börja [migrera dina Azure-resurser](https://docs.microsoft.com/azure/germany/germany-migration-main) till en annan region idag. 

Om du har Azure med Office 365, Dynamics 365 eller Power BI måste du följa migreringsprocessen för att säkerställa lyckad migrering av AzureAD innan du påbörjar den självriktade Azure-migreringen. Du måste slutföra Azure-migreringen innan tjänsten stängs för att kunna upprätthålla dina Azure-arbetsbelastningar med din AzureAD- och Office 365-organisation.

**Office 365**

[Välj till den](https://aka.ms/office365germanymoveoptin) Microsoft-drivna migreringen idag. När vi är redo att starta migreringen meddelar vi dig via meddelandecentret i administrationscentret för Microsoft 365.

**Dynamics 365 och Power BI**

Välj till den Microsoft-drivna migreringen för [Dynamics 365 Customer Engagement](https://aka.ms/D365ceOptIn) och Power BI [idag.](https://aka.ms/PBIOptIn) När vi är redo att starta migreringen meddelar vi dig via meddelandecentret i administrationscentret för Microsoft 365.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>Ändras priset för Office 365-tjänsterna som jag använder?

Ja. Priserna i Microsoft&#39;globala molnområdena (inklusive de nya datacenterområdena) är i allmänhet lägre.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Vilka SKU:er och licenser kommer att tillämpas för min organisation och mina användare under prenumerationsmigrering?

Under migreringen från Microsoft Cloud Deutschland till Office 365-tjänsterna ersätts tjänstspecifika Tyskland-SKU:er med globala versioner av samma eller liknande SKU. I de flesta fall är SKU:n för Office 365-tjänster desamma, men det finns få ersättningstjänster där SKU i Tyskland inte längre är tillgänglig i Office 365-tjänsterna. Om du vill uppdatera den SKU som tilldelats din organisation efter migreringen kontaktar du din säljare för att lägga till eller ändra de tjänster som tilldelats.

| Microsoft Cloud Deutschland – Product SKU (DE) | Microsoft Cloud Global – Produkt-SKU (WW) |
| --- | --- |
| Customer Lockbox \_ DE (LOCKBOX \_ DE) | Customer Lockbox (LOCKBOX) |
| Dynamics 365 Enterprise Edition – Ytterligare databaslagring \_ DE (CRMSTORAGE \_ DE) | Dynamics 365 Enterprise Edition – Ytterligare databaslagring (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition – ytterligare icke-produktionsinstans \_ DE (CRMTESTINSTANCE \_ DE) | Dynamics 365 Enterprise Edition – ytterligare icke-produktionsinstans (CRMTESTINSTANCE) |
| Dynamics 365 for Customer Service Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE \_ DE) | Dynamics 365 for Customer Service Enterprise Edition (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE) |
| Dynamics 365 for Sales Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ SALES \_ DE) | Dynamics 365 for Sales Enterprise Edition (DYN365 \_ ENTERPRISE \_ SALES) |
| Dynamics 365 for Team Members Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS \_ DE) | Dynamics 365 for Team Members Enterprise Edition (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS) |
| Dynamics 365-abonnemang 1 Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365-abonnemang 1 Enterprise Edition (DYN365 \_ ENTERPRISE \_ PLAN1) |
| ECAL Services (EOA, EOP, DLP) \_ DE (ECAL \_ SERVICES \_ DE) | ECAL Services (EOA, EOP, DLP) (ECAL \_ SERVICES) |
| Enterprise Mobility + Security E3 \_ DE (EMS \_ DE) | Enterprise Mobility + Security E3 (EMS) |
| Exchange Online (abonnemang 1) \_ DE (EXCHANGESTANDARD \_ DE) | Exchange Online (abonnemang 1) (EXCHANGESTANDARD) |
| Exchange Online (abonnemang 2) \_ DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online (abonnemang 2) (EXCHANGEENTERPRISE) |
| Exchange Online Arkivering för Exchange Online \_ DE (EXCHANGEARCHIVE \_ ADDON \_ DE) | Exchange Online Arkivering för Exchange Online (EXCHANGEARCHIVE \_ ADDON) |
| Exchange Online – arkivering för Exchange Server \_ DE (EXCHANGEARCHIVE \_ DE) | Exchange Online – arkivering för Exchange Server (EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ DE (EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Exchange Online Essentials (EXCHANGE \_ S \_ ESSENTIALS) |
| Exchange Online Kiosk \_ DE (EXCHANGEDESKLESS \_ DE) | Exchange Online Kiosk (EXCHANGEDESKLESS) |
| Exchange Online Protection \_ DE (EOP \_ ENTERPRISE \_ DE) | Exchange Online Protection (EOP \_ ENTERPRISE) |
| Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| Microsoft Dynamics CRM Online Instance \_ DE (CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online-instans (CRMINSTANCE) |
| Office 365 A1 för lärare \_ och andra (STANDARDWOFFPACK \_ FACULTY \_ DE) | Office 365 A1 för lärare (STANDARDWOFFPACK \_ FACULTY) |
| Office 365 A1 för students \_ DE (STANDARDWOFFPACK \_ STUDENT \_ DE) | Office 365 A1 för studenter (STANDARDWOFFPACK \_ STUDENT) |
| Office 365 Advanced Compliance \_ DE (EQUIVIO \_ ANALYTICS \_ DE) | Microsoft 365 E5 efterlevnad \_ \_ (INFORMATIONSSKYDD) |
|Microsoft Defender för Office 365 (abonnemang 1) \_ DE (ATP \_ ENTERPRISE \_ DE) |Microsoft Defender för Office 365 (abonnemang 1) (ATP \_ ENTERPRISE) |
| Office 365 Business Essentials \_ DE (O365 \_ BUSINESS \_ ESSENTIALS \_ DE) | Microsoft 365 Business Basic (O365 \_ BUSINESS \_ ESSENTIALS) |
| Office 365 Business Premium \_ DE (O365 \_ BUSINESS \_ PREMIUM \_ DE) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| Office 365 Business \_ DE (O365 \_ BUSINESS \_ DE) | Microsoft 365-appar för företag (O365 \_ BUSINESS) |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 utan ProPlus \_ DE (ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | Office 365 E3 utan ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ DE (STANDARDPACK \_ DE) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Office 365 Extra Fillagring \_ DE (SHAREPOINTSTORAGE \_ DE) | Office 365 Extra fillagring (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ DE (DESKLESSPACK \_ DE) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus för lärare och andra \_ (OFFICESUBSCRIPTION \_ FACULTY \_ DE) | Office 365 ProPlus för lärare (OFFICESUBSCRIPTION \_ FACULTY) |
| Office 365 ProPlus för Studenter \_ DE (OFFICESUBSCRIPTION \_ STUDENT \_ DE) | Office 365 ProPlus för studenter (OFFICESUBSCRIPTION \_ STUDENT) |
| Office 365 ProPlus \_ DE (OFFICESUBSCRIPTION \_ DE) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| OneDrive för företag (abonnemang 1) \_ DE (WACONEDRIVESTANDARD \_ DE) | OneDrive för företag (abonnemang 1) (WACONEDRIVESTANDARD) |
| OneDrive för företag (abonnemang 2) \_ DE (WACONEDRIVEENTERPRISE \_ DE) | OneDrive för företag (abonnemang 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro för lärare \_ (POWER \_ BI PRO \_ \_ FACULTY \_ DE) | Power BI Pro för lärare (POWER \_ BI \_ PRO \_ FAKULTET) |
| Power BI Pro \_ DE (POWER \_ BI \_ PRO \_ DE) | Power BI Pro (POWER \_ BI \_ PRO) |
| Project Online Essentials \_ DE (PROJECTESSENTIALS \_ DE) | Project Online Essentials (PROJECTESSENTIALS) |
| Project Online Premium \_ DE (PROJECTPREMIUM \_ DE) | Project Online Premium (PROJECTPREMIUM) |
| Project Online Professional \_ DE (PROJECTPROFESSIONAL \_ DE) | Project Online Professional (PROJECTPROFESSIONAL) |
| Projektplan 3 \_ DE (PROJECTPROFESSIONAL \_ DE) | Projektplan 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ DE (ENTERPRISEWITHSCAL \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (abonnemang 1) \_ DE (SHAREPOINTSTANDARD \_ DE) | SharePoint Online (abonnemang 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (abonnemang 2) \_ DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online (abonnemang 2) (SHAREPOINTENTERPRISE) |
| Skype för företag – Online (abonnemang 1) \_ DE (MCOIMP \_ DE) | Office 365 E1 (STANDARDPACK) |
| Skype för företag – Online (abonnemang 1) \_ DE (MCOIMP \_ DE) | Skype för företag – Online (abonnemang 1) (MCOIMP) |
| Skype för företag – Online (abonnemang 2) \_ DE (MCOSTANDARD \_ DE) | Skype för företag – Online (abonnemang 2) (MCOSTANDARD) |
| Skype för företag Plus CAL \_ DE (MCOPLUSCAL \_ DE) | Skype för företag Plus CAL (MCOPLUSCAL) |
| Visio Online abonnemang 1 för lärare \_ (VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | Visio Online abonnemang 1 för lärare (VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio Online Plan 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Online abonnemang 1 (VISIOONLINE \_ PLAN1) |
| Visio Online abonnemang 2 för lärare \_ och andra personer (VISIOCLIENT \_ FACULTY \_ DE) | Visio Online abonnemang 2 för lärare (VISIOCLIENT \_ FACULTY) |
| Visio Online abonnemang 2 \_ DE (VISIOCLIENT \_ DE) | Visio Online abonnemang 2 (VISIOCLIENT) |
| Visio Plan 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Plan 1 (VISIOONLINE \_ PLAN1) |
| Visio Plan 2 \_ DE (VISIOCLIENT \_ DE) | Visio Abonnemang 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Hur får jag hjälp från Microsoft att migrera till en ny region eller besvara supportfrågor?

Om du har frågor kan du kontakta oss eller din partner:

- För Azure kan du skicka in [nya supportbegäranden](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) i Azure Portal.
- För Office 365 kan du skicka frågor med hjälp av länken Behöver du hjälp? i administrationscentret för &quot; &quot; Microsoft [365.](https://portal.office.de/)
- Om du är Dynamics 365 Customer Engagement- och Power BI-kund och även har Office 365 kan du skicka frågor med hjälp av länken Behöver du hjälp? i administrationscentret för &quot; &quot; Microsoft [365.](https://portal.office.de/) Supportalternativ för Dynamics 365 Kundsupport finns [här.](https://docs.microsoft.com/dynamics365/get-started/support/) Supportalternativ för Power BI finns [här.](https://powerbi.microsoft.com/support/)

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>Min kund har redan en M365-klientorganisation i det globala Microsoft-molnet utöver en Microsoft Cloud Deutschland-klientorganisation. Kan de här två innehavarna slås ihop till en som en del av migreringen?

Nej, det finns ingen möjlighet till sammanslagning av klientorganisationen. Klientorganisationen förblir separat och unik eftersom varje klientorganisation har ett eget namnområde och ett unikt ID. Microsoft migrerar en Microsoft Cloud Deutschland-klientorganisation till det globala molnet om så önskas eller så kan kunden avbryta och avbryta den.


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>Vilka åtgärder krävs för de flesta slutanvändare som en del av migreringen?
Migreringen har utformats för att ha minimal påverkan på slutanvändare/kunder.
- Kontrollera att Office-programmen kör de senaste tillgängliga versionerna. 
- Kunder som använder Skype för företag går över till Teams som en del av migreringen och kan behöva [ladda ned och installera Teams](https://docs.microsoft.com/deployoffice/teams-install) på enheter.
- Slutanvändarna kan behöva logga ut från Office-programmen och logga in igen när migreringen är klar. 
- Kunder som kör synkroniseringsklienten för OneDrive måste logga ut från sin arbetsstation och logga in igen för att oneDrive-synkroniseringsklienten ska kunna logga in på den globala Azure Active Directory-tjänsten.
- Var uppmärksam på nya globala URL:er när migreringen är slutförd, den största är outlook Web Access (exempel: använd outlook.office365.com). SharePoint Online-klienter fortsätter att ansluta till MCD-namnområdet med hjälp av den befintliga URL-adressen (exempel: contoso.sharepoint.de).


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>Vilka kunder påverkas av Azure Active Directory-migreringen? 

Alla Office365-kunder är beroende av Azure Active Directory för att autentisera och lagra viktiga tjänstkomponenter som behövs för att Microsofts värdtjänster ska kunna tillhandahållas. 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>Vilka blir effekterna av Azure Active Directory-migreringen?

Den första migreringen av Azure Active Directory i den tidiga fasen påverkar inte kundupplevelsen. Efter den sista migreringen är alla tjänster för kundens klientorganisation helt i den globala tjänsten. Efter den här sista fasen kan Azure Active Directory-tjänsten i Microsoft Cloud Deutschland inte längre acceptera auktoriseringsförfrågningar eller tillhandahålla åtkomsttoken till Office-tjänster.


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>Vad innebär det att säkerställa nätverksanslutning till URL-adresser och IP-adresser för [Office 365-tjänster?](https://aka.ms/o365urls)

I den här artikeln beskrivs de URL:er och IP-adresser som krävs för en korrekt funktion i den globala tjänsten för att säkerställa en bra kundupplevelse. I relativt sällsynta fall försöker vissa kunder konfigurera nätverkets perimetersäkerhet på ett sådant sätt att minimera trafikflöden och har begränsad åtkomst till tjänster till dem bara som en del av IP-adressintervallen för Microsoft Cloud Deutschland.


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>Hur hanterar jag DNS-ändringarna för Exchange Online så att e-post fortsätter att flöda?

Microsoft-hanterade IP-intervall och DNS-zoner migreras under och som en del av migreringen till den globala tjänsten. 

Kundhanterade DNS-zoner, till exempel anpassade domän-MX-poster, ansvarar däremot för att förenkla den här migreringen som den kundhanterade MX-posten pekar på en Slutpunkt för Office 365-tjänst i office.de-zonen och Microsoft hanterar migreringen av den här tjänstslutpunkten automatiskt.


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>Hur hanterar jag DNS-ändringarna för Skype för företag? 
 
Alla Skype för företag-kunder kommer att övergå till Microsoft Teams. Övergången av Skype DNS-zoner för kunder krävs inte vid migrering till Teams. Kunder kommer att kunna logga in i Teams omedelbart med alla funktioner efter migreringen.
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>Fungerar Outlook för iOS och Android efter migreringen? 

Ja. Microsofts rekommendation är att alla kunder kör de senaste tillgängliga versionerna av Office-klienter, inklusive Outlook för iOS- och Android-klienter. När migreringen till den globala Office 365-tjänsten är slutförd måste alla Office-klienter logga ut och logga in igen för att få en ny Azure Active Directory-åtkomsttoken från den globala tjänsten. 



## <a name="next-step"></a>Nästa steg

[Välj till migrering](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>Mer information

Komma igång:

- [Migreringshjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du in för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kundupplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom övergången:

- [Åtgärder och påverkan i migreringsfaser](ms-cloud-germany-transition-phases.md)
- [Ytterligare förarbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och AD [FS.](ms-cloud-germany-transition-add-adfs.md)

Molnappar:

- [Information om Dynamics 365-migreringsprogram](https://aka.ms/d365ceoptin)
- [Information om migreringsprogrammet för Power BI](https://aka.ms/pbioptin)
- [Komma igång med uppgraderingen till Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
