---
title: Migrering från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster i de nya tyska Data Center-regionerna
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 07/09/2020
audience: ITPro
ms.topic: hub-page
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
ms.openlocfilehash: cfbd3b7406f7c7824f736633e3a4dba6fa5c4bff
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694748"
---
# <a name="migration-from-microsoft-cloud-germany-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migrering från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster i de nya tyska Data Center-regionerna


>[!Note]
>Den här artikeln gäller endast för kvalificerade Microsoft Cloud Germany/Deutschland-kunder.
>

## <a name="cloud-service-offerings-in-germany"></a>Moln tjänsts tjänster i Tyskland

I augusti 2018 presenterade vi vår avsikt att leverera hela Microsoft Cloud – Azure, Office 365, Dynamics 365 och Power Platform – från nya moln regioner i Tyskland för att bättre kunna aktivera den digitala omvandlingen av våra kunder. I augusti 2019 tillkännagede vi att vi nu håller på att öppna de nya moln regionerna i Tyskland. Vi meddelade att Azure i augusti och att Office 365 blev tillgänglig i december.  Dynamics 365 och Power Platform förväntas bli tillgängliga under det första kvartalet av 2020.  

De nya regionerna är utformade för att hantera de föränderliga behoven hos tyska kunder med den mest flexibla, senaste intelligenta moln tjänsten och fullständig anslutning till vårt globalt moln nätverk samt kund data de i Tyskland.

## <a name="moving-to-the-new-german-regions"></a>Flytta till de nya tyska regionerna

Befintliga Microsoft Cloud Germany (Microsoft Cloud Deutschland) kunder kan nu börja migrera sin Office 365-, Dynamics 365-kund engagemang och Power Platform BI-kunder.  Det första steget är att [välja ett Microsoft-LED-migrering](https://aka.ms/office365germanymoveoptin) till våra nya tyska Data Center områden.

För organisationer som väljer Microsoft-drivna tillvägagångs sätt förväntas migreringarna i 2020. Som ett resultat av migreringen flyttas grundläggande kund uppgifter och abonnemang till de nya tyska regionerna. 

Följande tjänster migreras som en del av Microsoft-driven-metoden:

- Azure Active Directory
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive för företag
- Skype för företag – Online

Under migreringen från Microsoft Cloud Tyskland till de tyska Data Center-regionerna kommer befintliga Skype för företag – Online-kunder över till Microsoft Teams. Mer information finns i [komma igång med Microsoft Teams-uppgraderingen](https://aka.ms/SkypeToTeams-Home) .

- Grupper i Office 365
- Dynamics 365/Power Platform

Förutsättningar och konsekvenserna av migrering för dessa tjänster beskrivs i artikeln om [kund engagemang i Dynamics 365](https://aka.ms/d365ceoptin) .

Office 365 Video dras tillbaka den 1 mars 2021. Om du väljer att migrera din Office 365-klient till de nya tyska Data Center-regionerna kommer Office 365-videon inte att stödjas efter att SharePoint Online-migreringen är klar. [Läs mer](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Förbereda för migrering till Office 365-tjänster i de nya tyska Data Center-regionerna

Det första steget är att meddela Microsoft så att vi har din tillåtelse att migrera ditt abonnemang och data från Microsoft Cloud Tyskland/Deutschland till Office 365-tjänster i de nya tyska Data Center-områdena.  Anvisningar finns [i för dig](ms-cloud-germany-migration-opt-in.md) .

- Alla som migrerar kunder måste kontrol lera anslutningen till [URL-adressen och IP-adresserna i den globala Office-365](urls-and-ip-address-ranges.md), som innehåller de nya tyska Data Center-regionerna
- Kontrol lera beskrivningen av Office 365 Platform service för att förstå vilka funktioner och tjänster som blir tillgängliga i din organisation efter det att du har slutfört den tyska regionen. 
- Migreringen kommer överens om betalda abonnemang.  Vi kan inte migrera utvärderings abonnemang.

Migrering av klient organisationer utförs som backend-tjänster med minsta möjliga kund interaktion.  Eventuella ytterligare kund LED-uppgifter och status för fullständig migrering kommer att meddelas via meddelande Center under migreringen.  Exempel på uppgifter kan inkludera Kundhanterade DNS-uppdateringar eller omkonfigurering av hybrid inställningar för Exchange-hybrider.

## <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Kund upplevelse under migreringen till Office 365-tjänster i de nya tyska Data Center-regionerna

Migrering av klient organisationer har utformats för att få minimala konsekvenser för slutanvändare och administratörer.  Men det finns faktorer för varje arbets belastning.  

### <a name="azure-active-directory"></a>Azure Active Directory

Office/Dynamics-abonnemang från Microsoft Cloud Tyskland övergår till det tyska området med Azure Active Directory (Azure AD)-omplaceringen. Organisationen uppdateras sedan för att återspegla nya abonnemang på hela världen. Under den korta abonnemangs överförings processen blockeras ändringar av abonnemang.

### <a name="exchange-online"></a>Exchange Online

Exchange Online-kunder måste köra hybrid konfigurations guiden igen för att uppdatera lokal konfiguration mot Microsoft Cloud Tyskland innan över gången och omexekveringen av HCW vid rensning mot hela världen. Ytterligare DNS-uppdateringar kan krävas för kunder med anpassade domäner.

Post lådor migreras som en server del, användare i din organisation kan vara i antingen Microsoft Cloud Tyskland eller tysk region under över gången och ingår i samma Exchange-organisation (GAL)

### <a name="exchange-online-protection"></a>Exchange Online Protection

Exchange Online Protection-funktioner kopieras till det nya Tyskland

### <a name="sharepoint-online"></a>SharePoint Online

När SharePoint Online-migreringen har slutförts till tyska-regionen återskapas data indexet. Funktioner som är beroende av Sök index kan påverkas när Omindexering är klar.

Befintliga sharepoint.de-URL: er bevaras för över gångs organisationer.

### <a name="onedrive-for-business"></a>OneDrive för företag

När migreringen av OneDrive för företag har genomförts till det tyska området återskapas data indexet. Funktioner som är beroende av Sök index kan påverkas när Omindexering är klar.

### <a name="skype-for-business-online"></a>Skype för företag – Online

Befintliga kunder i Skype för företag – online över gång till Microsoft Teams. Mer [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) information finns i.

### <a name="office-365-video"></a>Office 365 Video
Innehåll från Office 365-videon migreras som en del av SharePoint Online-migreringen. Office 365-videon avvecklas och Office 365-Video kommer inte att användas när SharePoint Online-migreringen till de nya tyska Data Center-regionerna är klar. Videoklipp i Office 365-video spelas inte upp i Office 365-gränssnittet efter migreringen av SharePoint.

Microsoft Stream kommer inte att distribueras till Microsoft Deutschland och vi har för närvarande ingen tids linje för att distribuera Microsoft Stream i de nya tyska Data Center-regionerna. Därför kommer det inte att finnas några migreringsåtgärder i det här området för Office 365 Video till Microsoft Stream. Om du vill behålla innehållet måste du hämta eller flytta innehållet manuellt innan den 1 mars 2021. [Läs mer](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)


## <a name="key-differences-between-microsoft-cloud-germany-microsoft-cloud-deutschland-and-office-365-services-in-the-new-german-datacenter-regions"></a>Viktiga skillnader mellan Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) och Office 365-tjänsterna i de nya tyska Data Center-regionerna


|| Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) | Office 365-tjänster i de nya tyska Data Center-områdena |
|:-------|:-----|:-----|
| Microsoft 365-tjänster som är tillgängliga för abonnemang med bara en Office 365-klient organisation | 15 tjänster (se REF) | 29 tjänster (se REF) |
| Nya funktioner | Det finns inga nya funktioner. | Nya funktioner blir tillgängliga i enlighet med globala Office 365-tjänster. |
| Data förvaltare | Ja | Nej |
| Samarbete mellan innehavare med globala Office 365-klient organisationer | Nej | Ja |
| De för kund data | Kunddata lagras bara i tyska Data Center. | Microsoft lagrar följande kunddata på rest i Tyskland: Exchange Online-postlådearkiv (e-postmeddelande, kalender poster och innehållet i e-postbilagor), SharePoint Online-webbplatsens innehåll och filer som lagras på webbplatsen och filer som laddats upp till OneDrive för företag. |
| Tillämpliga villkor | [Villkor för online tjänster](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) med [tillägg](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Villkor för online tjänster](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="frequently-asked-questions"></a>Vanliga frågor

### <a name="is-migration-required"></a>Krävs migrering?

Microsoft erbjuder Office 365-innehavaradministration från Microsoft Cloud Tyskland till Office 365-tjänsterna i de nya tyska Data Center-regionerna utan extra kostnad.  Även om vi rekommenderar att du väljer att migrera till de nya tyska Data Center-regionerna fortsätter vi att tillhandahålla de säkerhets uppdateringar som behövs till Microsofts moln för Tyskland.  

Office 365-tjänsterna i de nya tyska Data Center-regionerna har ytterligare fördelar:

- Ge marknads konkurrens kraftiga priser för [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 kund engagemang](https://dynamics.microsoft.com/pricing/)och [Power BI](https://powerbi.microsoft.com/pricing/). 
- Är ansluten till Microsoft globalt nätverk och erbjuder hundratals webbplatser för nätverks kant, peering-placering och utgångs punkter för att tillhandahålla en robust användar upplevelse överallt i världen. 
- Hjälp med att möta lokala kund uppgifter de krav i Tyskland. 
- Leverera vårt fullt utvalda globala moln erbjudande inklusive den senaste versionen av våra tjänster och nya funktioner, bland annat Microsoft Teams och multi-geo i Office 365. Jämför produkter efter region för [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md)och [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- Ge full funktionalitet, säkerhet på företags nivå och omfattande funktioner som hjälper kunder att uppfylla efterlevnad och myndighets krav. 
- Är tillgängliga via befintliga Online Services-kontrakt.

#### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Vad är tjänst tillgänglighet mellan de olika Office 365 Cloud Service-tjänsterna?

Följande 15 tjänster är tillgängliga i det utbud av moln tjänster för Microsoft Cloud Tyskland (Microsoft Cloud Deutschland).  Vi lägger inte till nya tjänster i Microsoft Cloud Tyskland.

1. Exchange Online
2. Kund lås (Exchange Online)
3. Grupper (moderna grupper)
4. Delve-profil
5. Exchange Online Protection
6. Avancerat skydd (ATP)
7. Advanced eDiscovery
8. Data styrning
9. SharePoint Online
10. Kund lås (SharePoint Online)
11. OneDrive för företag
12. Skype för företag
13. Word Online, Excel Online, PowerPoint, OneNote, Visio online
14. Office 365 Pro plus
15. Outlook Mobile

Det finns för närvarande 29 tjänster tillgängliga som en del av Office 365-tjänsterna i de nya tyska Data Center-regionerna.  Nya funktioner och tjänster kommer att vara tillgängliga konsekvent med globala Office 365-tjänster.

1. Exchange Online
2. Kund lås (Exchange Online)
3. Grupper (moderna grupper)
4. Delve-profil
5. MyAnalytics
6. Arbets plats analys
7. Exchange Online Protection
8. Avancerat skydd (ATP)
9. Advanced eDiscovery
10. Avancerad säkerhets hantering
11. Information Rights Management
12. Data styrning
13. SharePoint Online
14. Kund lås (SharePoint Online)
15. OneDrive för företag
16. Microsoft Stream
17. Skype för företag (övergå till Microsoft Teams under migreringen)
18. Cloud PBX
19. PSTN-konferens
20. PSTN-samtal
21. Microsoft Teams
22. Rapporter om administratör/användning
23. Word Online, Excel Online, PowerPoint, OneNote och Visio online
24. Planner
25. Sway
26. Office 365 Pro plus
27. Outlook Mobile
28. EMS E3 (Azure Active Directory Premium P1 + Intune + Rights Management Service)
29. Yammer online

### <a name="when-will-migration-happen"></a>När sker migrering?

#### <a name="azure"></a>Azure 

Du kan börja [migrera](https://docs.microsoft.com/azure/germany/germany-migration-main) dina Azure-resurser till en annan region idag. Om du har Azure med Office 365, Dynamics 365 och/eller Power BI följer du stegen nedan.

#### <a name="office-365"></a>Office 365

[Anmäl](https://aka.ms/office365germanymoveoptin) dig till Microsoft-driven migration idag. När vi är redo att påbörja migreringen meddelar vi dig via [meddelande Center](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) i administrations centret för Microsoft 365.

#### <a name="dynamics-365-and-power-bi"></a>Dynamics 365 och Power BI

Anmäl dig till Microsoft-driven migration för [Dynamics 365 kund engagemang](https://aka.ms/D365ceOptIn) och [Power BI idag](https://aka.ms/PBIOptIn). När vi är redo att påbörja migreringen meddelar vi dig via [meddelande Center](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) i administrations centret för Microsoft 365.

### <a name="will-the-price-change-for-the-office-services-that-i-use"></a>Kommer priset att ändras för de Office-tjänster som jag använder?

Ja, priserna i Microsofts globala moln regioner (inklusive de nya data Center områdena) är allmänt lägre.

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Hur får jag hjälp från Microsoft att migrera till ett nytt område eller besvara support frågor?

Om du har frågor kan du kontakta oss på följande sätt eller via din partner:

- För Azure kan du skicka [nya support förfrågningar](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) i Azure-portalen.
- För Office 365 kan du skicka frågor med hjälp av "behöver du hjälp?" länk till [administrations centret för Microsoft 365](https://portal.office.de/).
- För Dynamics 365 Customer Engagement och Power BI-kunder som också har Office 365 kan du skicka frågor med hjälp av "behöver du hjälp?" länk till [administrations centret för Microsoft 365](https://portal.office.de/). Dynamics 365 support alternativ för kund åtagande finns [här](https://docs.microsoft.com/dynamics365/get-started/support/). Support alternativen för Power BI finns [här](https://powerbi.microsoft.com/support/).

## <a name="more-information"></a>Mer information

- [Hjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du för migrering](https://aka.ms/office365germanymoveoptin)
- [Information om programmet för Dynamics 365 migration](https://aka.ms/d365ceoptin)
- [Information om datamigreringshanteraren för Power BI](https://aka.ms/pbioptin)
- [URL-adresser och IP-adressintervall för Office 365](https://aka.ms/o365endpoints)
- [Office 365 Hybrid konfigurations guide](https://aka.ms/HybridWizard)
- [Komma igång med din uppgradering av Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
