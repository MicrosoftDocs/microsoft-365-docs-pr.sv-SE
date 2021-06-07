---
title: Migrering från Microsoft Cloud Deutschland till Office 365 i de nya tyska datacenterområdena
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
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
description: Sammanfattning Förstå migreringen från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365 i den nya tyska datacenterområdet.
ms.openlocfilehash: 4162e51164120cecaa431ad6883d3ee112ad4880
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796012"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migrering från Microsoft Cloud Deutschland till Office 365 i de nya tyska datacenterområdena

> [!NOTE]
> Den här artikeln gäller endast för berättigade Microsoft Cloud Deutschland-kunder.

I augusti 2018 meddelade Microsoft vår avsikt att tillhandahålla hela Microsoft-molnet – Azure, Office 365, Dynamics 365 och Power Platform – från nya molnområden i Tyskland för att bättre möjliggöra en digital omvandling av våra kunder. I augusti 2019 meddelade vi att vi nu håller på att öppna de nya molnområdena i Tyskland. Vi har sedan meddela om tillgängligheten för Azure, Office 365, Dynamics 365 och Power Platform.

De nya regionerna är utformade för att tillgodose de föränderliga behoven hos tyska kunder i större utsträckning, de senaste intelligenta molntjänsterna och fullständig anslutning till våra molnnätverk med Microsoft 365-tjänster samt kunddata som finns i Tyskland.

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>Migrera till de nya tyska datacenterområdena

Befintliga Microsoft Cloud Deutschland-kunder kan nu börja migrera sina Office 365-, Dynamics 365 Customer Engagement- och Power Platform-kunder. Det första steget är att [registrera dig för en Microsoft-ledd migrering till](./ms-cloud-germany-migration-opt-in.md) våra nya tyska datacenterområden.

För organisationer som väljer att använda Microsoft-drivna metoder förväntas migreringar inledas i början av 2021 och slutföras senast den 29 oktober 2021. På grund av migreringen flyttas basdata från kunder och prenumerationer till de nya tyska regionerna.

Den här artikeln innehåller en översikt över Den Microsoft-drivna metoden för migrering, information om upplevelser för både användare och administratörer under och efter migreringen och åtgärder som kan krävas för kunder baserat på vilka arbetsbelastningar du använder.

Följande tjänster migreras som en del av den Microsoft-drivna metoden:

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive för företag
- Skype för företag Online\*\*
- Grupper i Office 365
- Dynamics 365 / Power Platform\*\*\*

\*\*Under migreringen från Microsoft Cloud Deutschland till de tyska datacenterområdena kommer befintliga Skype för företag Online-kunder att övergå till Microsoft Teams. Mer [information finns i Microsoft Teams med din uppgradering.](/microsoftteams/upgrade-start-here)

\*\*\*Krav och påverkan på migreringen för dessa tjänster beskrivs i [artikeln Dynamics 365 Customer engagement.](/dynamics365/get-started/migrate-data-german-region)

Office 365 Videon dras tillbaka den 1 mars 2021. Om du väljer att migrera Office 365-klientorganisationen till de nya tyska datacenterområdena stöds inte Office 365 Video när SharePoint Online-migreringen är klar. Mer information finns i [tidslinjen för Microsoft Cloud Deutschland.](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-is-the-migration-organized"></a>Hur organiseras migreringen?

I den här bilden visas de tio faserna av migreringen till de nya tyska datacenteren.

:::image type="content" alt-text="De tio migreringsfaserna till de nya Tyskland-datacenter" source="../media/ms-cloud-germany-migration-opt-in/migration-organization.png" lightbox="../media/ms-cloud-germany-migration-opt-in/migration-organization.png":::

De här faserna startar [när du väljer att migrera.](./ms-cloud-germany-migration-opt-in.md) De flesta av migreringsfaserna körs som serviceåtgärder på backend med minimal kundinteraktion som krävs och körs en fas efter den andra. Start för ytterligare kundledda uppgifter och den övergripande migreringsstatusen meddelas via meddelandecentret i Microsoft 365 administrationscenter under migreringsprocessen. Exempel på uppgifter kan vara DNS-uppdateringar som hanteras av kunder, omkonfigurering av hybridkonfiguration Exchange hybridkunder eller Azure-migrering.

Migreringen påbörjas inte direkt när anmälning sker. Organisationen läggs till i listan över klientorganisationar som är schemalagda för senare migrering. Du kan börja faserna för arbetet nu eftersom de är kritiska för att säkerställa en lyckad migrering och användning vid slutförande:

- [Åtgärder och påverkan i migreringsfaser](ms-cloud-germany-transition-phases.md)
- [Ytterligare arbete](ms-cloud-germany-transition-add-pre-work.md)

En vecka innan klientorganisationens migrering startar visas ett meddelande i meddelandecentertjänsten som en sista varning om att alla krav måste vara slutförda.

Migreringen flyttar Azure AD-klientorganisationen från den suveräna Tyskland Azure AD-tjänsten till Office 365-tjänstinstansen av Azure AD i EU-regionen.

Nästa steg är migreringen av klientorganisationens&#39;och användarlicenser från Tyskland-specifika produkter till globala produkter.

När alla steg har slutförts, inklusive Azure-kundmigrering, slutförs klientorganisationen i Office 365 tjänst och migrering har markerats som slutförd. I det här läget får du den slutliga uppdateringen av Meddelandecenter. Klientorganisationen är nu en helt global Office 365 organisation.

Du får ett meddelande om migreringsförloppet med inlägg i Meddelandecenter. Inläggen kommer att ske vid specifika milstolpar och kommer att ge vägledning om ett stegs förlopp samt viktig information som kunderna kan agera på utifrån processkraven. Meddelanden i Meddelandecenter tillhandahålls vid följande milstolpar:

- Migreringens start (5 arbetsdagar innan Azure AD-migreringen påbörjas)
- Azure AD-migrering slutförd
- Prenumerations- och licensmigrering slutförd
- SharePoint slutförd migrering
- Exchange slutförd migrering
- Skype för företag slutförd
- Dynamics är klar
- Power BI slutförd
- Den slutliga tjänstefasen är slutförd

Efter den slutliga övergången av Azure AD till den globala tjänsten förväntas alla klienter och program fullständigt övergå till att använda rätt slutpunkter. Det finns ett 30-dagarsfönster efter den slutliga övergången där det kan vara möjligt att fortsätta hämta Azure AD-tokens från Microsoft Cloud Deutschland-tjänsten. När 30-dagarsfönstret går ut kan klienter och program inte längre komma åt Azure AD-slutpunkterna för Microsoft Cloud Deutschland. I det här läget går det inte att använda program eller användaråtkomst. Du måste se till att alla användare och program migreras till rätt slutpunkter innan det här fönstret stängs. 

## <a name="moving-to-the-new-german-datacenter-regions"></a>Flytta till de nya tyska datacenterområdena

Befintliga Microsoft Cloud Deutschland-kunder kan nu börja migrera sina Office 365- och Dynamics 365 Customer Engagement- och Power Platform-tjänster. Det första steget är att [registrera dig för en Microsoft-ledd migrering till](./ms-cloud-germany-migration-opt-in.md) våra nya tyska datacenterområden. När du förnyar prenumerationen anmäler du dig automatiskt till en Microsoft-assisterad migrering. Microsoft informerar administratörerna för klientorganisationen med e-post och i meddelandecentret i Microsoft 365 när detta har hänt. Om du föredrar att starta processen nu kan du anmäla [dig](./ms-cloud-germany-migration-opt-in.md) direkt i Microsoft 365 administrationscenter. Migreringarna beräknas starta i början av 2021 och slutförs senast den 29 oktober 2021. 

På grund av migreringen flyttas basdata från kunder och prenumerationer till de nya tyska datacenterområdena.

> [!NOTE]
> Den här artikeln innehåller endast vägledning för Office 365 migrering av tjänster. Om du kör ytterligare Azure-arbetsbelastningar i Microsoft Cloud Deutschland finns mer information i [Migreringsvägledning för Azure Germany.](/azure/germany/germany-migration-main)

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Så här förbereder du en migrering Office 365 tjänster i de nya tyska datacenterområdena

Det första steget är att meddela Microsoft så att vi har ditt tillstånd att migrera din prenumeration och data från Microsoft Cloud Deutschland till Office 365-tjänster i nya tyska datacenterområden. Se processen för [att registrera dig för instruktioner](./ms-cloud-germany-migration-opt-in.md) och observera att:

- Alla kunder som migrerar måste kontrollera om de är Office 365 Services [Office 365 URL:er](urls-and-ip-address-ranges.md)och IP-adresser, vilket inkluderar de nya tyska datacenterområdena. Inaction kan resultera i tjänst- och klientfel.
- Granska listan med aktiviteter [före arbetet för](ms-cloud-germany-transition-add-pre-work.md) att säkerställa att organisationen är informerad och förberedd på ändringarna.
- Läs beskrivningen av Office 365-plattformen för att förstå vilka funktioner och tjänster som blir tillgängliga för din organisation efter migreringen till den tyska regionen.
- Utvärderingsprenumerationer migreras inte och blockerar migreringen av alla betalda prenumerationer. Du måste avbryta utvärderingsversioner eller konvertera till betalda prenumerationer innan migreringen påbörjas.

## <a name="where-do-i-go-from-here"></a>Vart går jag härifrån?

Läs igenom avsnittet Vanliga frågor och svar.

## <a name="frequently-asked-questions"></a>Vanliga frågor

### <a name="is-migration-required"></a>Krävs migrering?

Microsoft erbjuder Office 365 klientorganisationsmigrering från Microsoft Cloud Deutschland Office 365 tjänster i de nya tyska datacenterområdena utan extra kostnad. Vi rekommenderar starkt att du väljer att migrera till de nya tyska datacenterområdena, men vi kommer att fortsätta att tillhandahålla de säkerhetsuppdateringar som krävs för Microsoft Cloud Deutschland-regionen.

Office 365 i de nya tyska datacenterområdena:

- Erbjuda konkurrenskraftigt pris på [marknaden för Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/)och [Power BI.](https://powerbi.microsoft.com/pricing/)
- Är anslutna till Microsoft&#39;globala nätverk, med hundratals nätverks edge-webbplatser, peeringplatser och utgående punkter för att ge en robust användarupplevelse var som helst i världen.
- Hjälper dig att uppfylla lokala krav för kundens data som lagras i Tyskland.
- Leverera våra fullständiga, globala molntjänster med de senaste versionerna av våra tjänster och nya funktioner som Microsoft Teams och Multi-Geo i Office 365. Jämför produkter efter region [för Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md)och [Dynamics 365.](/dynamics365/get-started/availability)
- Erbjuder fullständiga funktioner, säkerhet i företagsklass och omfattande funktioner som hjälper kunder att uppfylla efterlevnads- och regelkrav.
- Är tillgängliga via befintliga onlinetjänstavtal.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Vad är tjänstens tillgänglighet mellan de olika Office 365 molntjänsterbjudandena?
<h2 id="serv-avail"></h2>

Följande 15 tjänster finns tillgängliga i Microsoft Cloud Deutschland-molntjänsterbjudandet. Vi lägger inte till nya tjänster i Microsoft Cloud Deutschland.

1. Exchange Online
2. Customer Lockbox (Exchange Online)
3. Grupper (moderna grupper)
4. Delve Profil
5. Exchange Online Protection
6. Defender förr Office 365
7. Advanced eDiscovery
8. Avancerad datastyrning
9. SharePoint Online
10. Customer Lockbox (SharePoint Online)
11. OneDrive för företag
12. Skype för företag – Online
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 Pro Plus
15. Outlook Mobil

Det finns för närvarande 39 tillgängliga tjänster som en del Office 365 tjänster i de nya tyska datacenterområdena. Nya funktioner och tjänster kommer att finnas tillgängliga Office 365 kontinuerligt med globala tjänster.

1. Exchange Online
2. Customer Lockbox för Exchange Online
3. Microsoft 365-grupper
4. Delve Profil
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Defender förr Office 365
9. Advanced eDiscovery
10. Avancerad säkerhetshantering
11. Informationsskydd för Office 365 
12. Avancerad datastyrning
13. SharePoint Online
14. Customer Lockbox för SharePoint Online
15. OneDrive för företag
16. Microsoft Stream
17. Skype för företag (migreras till Microsoft Teams under migreringen)
18. Cloud PBX
19. PSTN-konferens
20. PSTN-samtal
21. Microsoft Teams
22. Admin-rapporter/användningsrapporter
23. Office på webben
24. Planner
25. Sway
26. Microsoft 365-applikationer
27. Outlook Mobil
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, Intune och Rights Management Service)
29. Yammer Enterprise
30. Microsoft Forms
31. Power Automate för Office 365
32. Power Virtual Agents för Office 365
33. PowerApps för Office 365
34. Microsoft Bookings
35. To-Do
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. Listor

### <a name="when-will-migration-happen"></a>När sker migreringen?

**Azure**

Om du bara är Azure-kund kan du börja [migrera dina Azure-resurser](/azure/germany/germany-migration-main) till en annan region idag. 

Om du har Azure med Office 365, Dynamics 365 eller Power BI måste du följa migreringsprocessen för Office 365-tjänster först för att säkerställa en lyckad migrering av Azure AD innan du kan påbörja den självbetjänade Azure-migreringen. Du måste slutföra Azure-migreringen innan du slutför klientorganisationens migrering för att kunna upprätthålla dina Azure-arbetsbelastningar med Azure AD Office 365 organisation. Mer information [finns i Åtgärder och effekter för migreringen från Microsoft Cloud Deutschland.](ms-cloud-germany-transition-phases.md)

**Office 365**

[Välj att delta i](./ms-cloud-germany-migration-opt-in.md) den Microsoft-drivna migreringen idag. När vi är redo att starta migreringen meddelar vi dig via Meddelandecenter Microsoft 365 administrationscentret.

**Dynamics 365 och Power BI**

Registrera dig för den Microsoft-drivna migreringen [av Dynamics 365 Customer Engagement](/dynamics365/get-started/migrate-data-german-region) och [Power BI](/power-bi/admin/service-admin-migrate-data-germany) idag. När vi är redo att starta migreringen meddelar vi dig via Meddelandecenter Microsoft 365 administrationscentret.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>Ändras priset för de Office 365 jag använder?

Ja. Priser i Microsoft&#39;globala molnområden (inklusive de nya datacenterområdena) är generellt lägre.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Vilka SKU:er och licenser kommer att tillämpas på min organisation och mina användare under prenumerationsmigrering?

Under migreringen från Microsoft Cloud Deutschland till Office 365-tjänsterna ersätts de tjänstspecifika Tyskland-SKU:er med globala versioner av samma eller liknande SKU. I de flesta fall är SKU:n i Office 365 samma men det finns få ersättningar där SKU:n i Tyskland inte längre är tillgänglig i Office 365. Om du vill uppdatera den SKU som tilldelats organisationen efter migreringen kontaktar du din säljare för att lägga till eller ändra de tjänster som har tilldelats.

| Microsoft Cloud Deutschland – Produkt-SKU (DE) | Microsoft Cloud Global – Produkt-SKU (WW) |
| --- | --- |
| Customer Lockbox \_ DE (LOCKBOX \_ DE) | Customer Lockbox (LOCKBOX) |
| Dynamics 365 Enterprise Edition – Ytterligare Storage \_ DE (CRMSTORAGE \_ DE) | Dynamics 365 Enterprise Edition – Ytterligare Storage (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition – Ytterligare instansen \_ DE (CRMTESTINSTANCE \_ DE) | Dynamics 365 Enterprise Edition – ytterligare icke-produktionsinstans (CRMTESTINSTANCE) |
| Dynamics 365 för kundtjänst Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE CUSTOMER SERVICE \_ \_ \_ DE) | Dynamics 365 för Enterprise Edition (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE) |
| Dynamics 365 for Sales Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE SALES \_ \_ DE) | Dynamics 365 for Sales Enterprise Edition (DYN365 \_ ENTERPRISE \_ SALES) |
| Dynamics 365 för teammedlemmar Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE TEAM MEMBERS \_ \_ \_ DE) | Dynamics 365 för teammedlemmar Enterprise Edition (DYN365 \_ ENTERPRISE \_ \_ TEAM-MEDLEMMAR) |
| Dynamics 365 abonnemang 1 Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365 abonnemang 1 Enterprise Edition (DYN365 \_ ENTERPRISE \_ ABONNEMANG1) |
| \_ECAL Services (EOA, EOP, DLP) DE (ECAL \_ SERVICES \_ DE) | ECAL Services (EOA, EOP, DLP) (ECAL \_ SERVICES) |
| \_Enterprise Mobility + Security E3 DE (EMS \_ DE) | Enterprise Mobility + Security E3 (EMS) |
| \_Exchange Online (alternativ 1) DE (EXCHANGESTANDARD \_ DE) | Exchange Online (alternativ 1) (EXCHANGESTANDARD) |
| \_Exchange Online (alternativ 2) DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online (alternativ 2) (EXCHANGEENTERPRISE) |
| \_Exchange Online Archiving för Exchange Online DE (EXCHANGEARCHIVE \_ ADDON \_ DE) | Exchange Online Archiving för Exchange Online (EXCHANGEARCHIVE \_ ADDON) |
| \_Exchange Online Archiving för Exchange Server DE (EXCHANGEARCHIVE \_ DE) | Exchange Online Archiving för Exchange Server (EXCHANGEARCHIVE) |
| \_Exchange Online Essentials DE (EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Exchange Online Essentials (EXCHANGE \_ S \_ ESSENTIALS) |
| \_Exchange Online – kiosk DE (EXCHANGEDESKLESS \_ DE) | Exchange Online – kiosk (EXCHANGEDESKLESS) |
| \_Exchange Online Protection DE (EOP \_ ENTERPRISE \_ DE) | Exchange Online Protection (EOP \_ ENTERPRISE) |
| Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| Microsoft Dynamics CRM Online Instance \_ DE (CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online Instans (CRMINSTANCE) |
| Office 365 A1 för faculty \_ DE (STANDARDWOFFPACK \_ FACULTY \_ DE) | Office 365 A1 för lärare och personal (STANDARDWOFFPACK \_ FACULTY) |
| Office 365 A1 för studenter \_ DE (STANDARDWOFFPACK \_ STUDENT \_ DE) | Office 365 A1 för elever (STANDARDWOFFPACK \_ STUDENT) |
| \_Office 365 Advanced Compliance DE (EQUIVIO \_ ANALYTICS \_ DE) | Microsoft 365 E5 Compliance \_ \_ (INFORMATIONSSKYDDSEFTERLEVNAD) |
|Microsoft Defender för Office 365 (abonnemang 1) \_ DE (ATP \_ ENTERPRISE \_ DE) |Microsoft Defender för Office 365 (abonnemang 1) (ATP \_ ENTERPRISE) |
| \_Office 365 Business Essentials DE (O365 \_ BUSINESS \_ ESSENTIALS \_ DE) | Microsoft 365 Business Basic (O365 \_ BUSINESS \_ ESSENTIALS) |
| \_Office 365 Business Premium DE (O365 \_ BUSINESS \_ PREMIUM \_ DE) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| \_Office 365 Business DE (O365 \_ BUSINESS \_ DE) | Microsoft 365-applikationer för affärsverksamhet (O365 \_ BUSINESS) |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 utan ProPlus \_ DE (ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | Office 365 E3 utan ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ DE (STANDARDPACK \_ DE) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| \_Office 365 extra fillagring DE (SHAREPOINTSTORAGE \_ DE) | Office 365 extra fillagring (SHAREPOINTSTORAGE) |
| \_Office 365 F1 DE (DESKLESSPACK \_ DE) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus för Faculty \_ DE (OFFICESUBSCRIPTION \_ FACULTY \_ DE) | Office 365 ProPlus för lärare och andra (OFFICESUBSCRIPTION \_ FACULTY) |
| Office 365 ProPlus för Students \_ DE (OFFICESUBSCRIPTION \_ STUDENT \_ DE) | Office 365 ProPlus för studenter (OFFICESUBSCRIPTION \_ STUDENT) |
| \_Office 365 ProPlus DE (OFFICESUBSCRIPTION \_ DE) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| \_OneDrive för företag (abonnemang 1) DE (WACONEDRIVESTANDARD \_ DE) | OneDrive för företag (abonnemang 1) (WACONEDRIVESTANDARD) |
| \_OneDrive för företag (abonnemang 2) DE (WACONEDRIVEENTERPRISE \_ DE) | OneDrive för företag (abonnemang 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro för lärare \_ DE (POWER \_ BI \_ PRO \_ FACULTY \_ DE) | Power BI Pro för lärare och andra lärare (POWER \_ BI \_ \_ PRO) |
| \_Power BI Pro DE (POWER \_ BI \_ PRO \_ DE) | Power BI Pro (POWER \_ BI \_ PRO) |
| \_Project Online Essentials DE (PROJECTESSENTIALS \_ DE) | Project Online Essentials (PROJECTESSENTIALS) |
| \_Project Online Premium DE (PROJECTPREMIUM \_ DE) | Project Online Premium (PROJECTPREMIUM) |
| \_Project Online Professional DE (PROJECTPROFESSIONAL \_ DE) | Project Online Professional (PROJECTPROFESSIONAL) |
| \_Project Abonnemang 3 DE (PROJECTPROFESSIONAL \_ DE) | Project Abonnemang 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ DE (ENTERPRISEWITHSCAL \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| \_SharePoint Online (alternativ 1) DE (SHAREPOINTSTANDARD \_ DE) | SharePoint Online (alternativ 1) (SHAREPOINTSTANDARD) |
| \_SharePoint Online (alternativ 2) DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online (alternativ 2) (SHAREPOINTENTERPRISE) |
| Skype för företag Online (abonnemang 1) \_ DE (MCOIMP \_ DE) | Office 365 E1 (STANDARDPACK) |
| Skype för företag Online (abonnemang 1) \_ DE (MCOIMP \_ DE) | Skype för företag Online (abonnemang 1) (MCOIMP) |
| Skype för företag Online (abonnemang 2) \_ DE (MCOSTANDARD \_ DE) | Skype för företag Online (abonnemang 2) (MCOSTANDARD) |
| Skype för företag Plus CAL \_ DE (MCOPLUSCAL \_ DE) | Skype för företag Plus CAL (MCOPLUSCAL) |
| Visio Onlineabonnemang 1 för lärare \_ DE (VISIOONLINE \_ ABONNEMANG1 \_ FAC \_ DE) | Visio Onlineabonnemang 1 för lärare (VISIOONLINE \_ ABONNEMANG1 \_ FAC) |
| Visio Online abonnemang 1 \_ DE (VISIOONLINE \_ ABONNEMANG1 \_ DE) | Visio Onlineabonnemang 1 \_ (VISIOONLINE-ABONNEMANG1) |
| Visio Onlineabonnemang 2 för fakultet \_ DE (VISIOCLIENT \_ FACULTY \_ DE) | Visio Onlineabonnemang 2 för lärare och personal (VISIOCLIENT \_ FACULTY) |
| Visio Online abonnemang 2 \_ DE (VISIOCLIENT \_ DE) | Visio Onlineabonnemang 2 (VISIOCLIENT) |
| \_Visio Abonnemang 1 DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Abonnemang 1 \_ (VISIOONLINE-ABONNEMANG1) |
| \_Visio Abonnemang 2 DE (VISIOCLIENT \_ DE) | Visio Abonnemang 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Hur får jag hjälp från Microsoft att migrera till en ny region eller få svar på supportfrågor?

Om du har frågor kan du kontakta oss eller din partner:

- För Azure kan du skicka in [nya supportbegäranden](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) i Azure Portal.
- För Office 365 frågor kan du skicka frågor med hjälp av länken Behöver du &quot; &quot; hjälp? Microsoft 365 [administrationscentret](https://portal.office.de/).
- Om du är Dynamics 365 Customer Engagement och Power BI kund och även har Office 365 kan du skicka frågor med hjälp av länken Behöver du hjälp? Microsoft 365 &quot; &quot; [administrationscentret.](https://portal.office.de/) Dynamics 365 Kundsupportalternativ finns [här.](/dynamics365/get-started/support/) Power BI finns [här](https://powerbi.microsoft.com/support/).

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>Min kund har redan en M365-klientorganisation i det globala Microsoft-molnet utöver en Microsoft Cloud Deutschland-klientorganisation. Kan de här två klientorganisationen slås ihop till en som en del av migreringen?

Nej, det finns ingen möjlighet att koppla klientorganisation. Klientorganisationen förblir separat och unik eftersom varje innehavare har ett eget namnområde och ett unikt ID. Microsoft migrerar en Microsoft Cloud Deutschland-klientorganisation till det globala molnet om så önskar, annars kan kunden avbryta och avbryta den.


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>Vilka åtgärder krävs för de flesta slutanvändare som en del av migreringen?
Migreringen har utformats för att ha minimal påverkan på slutanvändare/kunder.
- Kontrollera att Office kör de senaste tillgängliga versionerna. 
- Kunder som Skype för företag går över till Teams som en del av migreringen och kan behöva ladda ned och [installera Teams](/deployoffice/teams-install) på enheter.
- Slutanvändarna kan behöva logga ut från Office-programmen och logga in igen när migreringen är klar. 
- Kunder som kör OneDrive-synkroniseringsklienten måste logga ut från sin arbetsstation och logga in igen så att OneDrive-synkroniseringsklienten kan logga in på den globala Azure Active Directory-tjänsten.
- När migreringen är klar är det viktigt att du känner till de nya globala webbadresserna, Outlook Web Access (exempel: använd outlook.office365.com). SharePoint Onlineklienter fortsätter att ansluta till MCD-namnområdet med hjälp av den befintliga URL-adressen (exempel: contoso.sharepoint.de).


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>Vilka kunder påverkas av Azure Active Directory migreringen? 

Alla kunder till Office 365 är beroende av Azure Active Directory för att autentisera och lagra viktiga tjänstkomponenter som behövs för att Microsofts värdtjänster ska kunna driftas. 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>Hur påverkas Azure Active Directory migreringen?

Den första migreringen Azure Active Directory i den tidiga fasen påverkar inte kundupplevelsen. Efter den sista migreringen finns alla tjänster för kundens klientorganisation helt i den globala tjänsten. Efter det sista steget kan Azure Active Directory-tjänsten i Microsoft Cloud Deutschland inte längre godkänna auktoriseringsförfrågningar eller tillhandahålla åtkomsttoken för Office tjänster.


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>Vad innebär det att säkerställa nätverksanslutning till [e Office 365 och IP-adresser för tjänster?](./urls-and-ip-address-ranges.md)

I den här artikeln beskrivs de URL:er och IP-adresser som krävs för att den globala tjänsten ska fungera korrekt för att säkerställa en bra kundupplevelse. I relativt sällsynta fall försöker vissa kunder konfigurera perimetersäkerhet på ett sätt som minimerar trafikflöden och har begränsad åtkomst till tjänster till dem bara som en del av Microsoft Cloud Deutschland-tjänst-IP-intervallen.


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>Hur hanterar jag DNS-ändringarna för Exchange Online så att e-post fortsätter att flöda?

Microsoft-hanterade IP-intervall och DNS-zoner migreras under och som en del av migreringen till den globala tjänsten. 

Kundens hanterade DNS-zoner, till exempel anpassade domän-MX-poster, ansvarar dock för att förenkla den här migreringen som den kundhanterade MX-posten pekar på en Office 365-tjänstslutpunkt i office.de-zonen och Microsoft hanterar migreringen av den här tjänsteslutpunkten automatiskt.


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>Hur hanterar jag DNS-ändringar för Skype för företag? 
 
Alla Skype För företag-kunder går över till Microsoft Teams. Migreringen av Skype AV DNS-zoner krävs inte under migreringen till Teams. Kunder kommer att kunna logga in på Teams omedelbart med alla funktioner efter migreringen.
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>Fungerar Outlook för iOS och Android efter migreringen? 

Ja. Microsofts rekommendation är att alla kunder kör de senaste tillgängliga versionerna av Office-klienter, bland annat Outlook för iOS- och Android-klienter. När migreringen till den globala Office 365-tjänsten är slutförd måste alla Office-klienter logga ut och logga in igen för att erhålla en ny Azure Active Directory-åtkomsttoken från den globala tjänsten. 



## <a name="next-step"></a>Nästa steg

[Anmäl dig för migrering](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>Mer information

Komma igång:

- [Migreringshjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du in för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kundupplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom övergången:

- [Åtgärder och påverkan i migreringsfaser](ms-cloud-germany-transition-phases.md)
- [Ytterligare arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Molnappar:

- [Information om Dynamics 365-migreringsprogram](/dynamics365/get-started/migrate-data-german-region)
- [Power BI i migreringsprogrammet](/power-bi/admin/service-admin-migrate-data-germany)
- [Komma igång med din Microsoft Teams uppgradering](/microsoftteams/upgrade-start-here)
