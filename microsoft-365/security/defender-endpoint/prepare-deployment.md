---
title: Förbereda Microsoft Defender för distribution av Endpoint
description: Förbereda godkännanden från intressenter, tidslinjer, miljööverväganden och införandeordning för distribution av Microsoft Defender för Slutpunkt
keywords: distribuera, förbereda, intressenter, tidslinje, miljö, slutpunkt, server, hantering, införande
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7841197594941354b21bd2104cd27ef37a1a25c9
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964602"
---
# <a name="prepare-microsoft-defender-for-endpoint-deployment"></a>Förbereda Microsoft Defender för distribution av Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Distribution av Defender för Endpoint är en process i tre steg:

| ![distributionsfas – förbereda](images/phase-diagrams/prepare.png)<br>Fas 1: Förbereda | [![distributionsfas – konfiguration](images/phase-diagrams/setup.png)](production-deployment.md)<br>[Fas 2: Installation](production-deployment.md) | [![distributionsfas – onboard](images/phase-diagrams/onboard.png)](onboarding.md)<br>[Fas 3: Introduktion](onboarding.md) |
| ----- | ----- | ----- |
|*Du är här!* | ||


Du håller på att förbereda dig.


Förberedelse är avgörande för en lyckad distribution. I den här artikeln får du vägledning i de punkter du behöver tänka på när du förbereder distributionen av Defender för Slutpunkt.


## <a name="stakeholders-and-approval"></a>Intressenter och godkännande
Följande avsnitt fungerar för att identifiera alla intressenter som är inblandade i projektet och måste godkänna, granska eller hålla sig informerad.

Lägg till intressenter i tabellen nedan efter behov för din organisation.

-   SO = Godkänn projekt

-   R = Granska det här projektet och ge input

-   I = Informeras om projektet

| Namn                 | Roll                                                                                                                                                                                                          | Åtgärd |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Ange namn och e-postadress | **CISO (Chief Information Security Officer)** En chef som fungerar som *sponsor inom organisationen för den nya teknikdistributionen.*                                                  | SO     |
| Ange namn och e-postadress | **Chef för Cyber Defense Operations Center (CDOC)** En representant från *CDOC-teamet* som ansvarar för att definiera hur ändringen justeras mot processerna i kundens säkerhetsoperationsteam.       | SO     |
| Ange namn och e-postadress | **Säkerhetsarkitekt** En representant för säkerhetsgruppen som ansvarar för att definiera hur ändringen överensstämmer med organisationens *kärnarkitektur inom säkerhet.*                         | R      |
| Ange namn och e-postadress | **Arbetsplatsarkitekt** *En representant för IT-teamet* som ansvarar för att definiera hur förändringen är i linje med organisationens kärnarkitektur på arbetsplatsen.                             | R      |
| Ange namn och e-postadress | **Säkerhetsanalytiker En** representant för CDOC-teamet som kan bidra med information om identifieringsfunktioner, användarupplevelse och den övergripande användbarheten för denna ändring ur ett *säkerhetsperspektiv.* | I      |


## <a name="environment"></a>Miljö 


Det här avsnittet används för att säkerställa att din miljö är helt förståd av intressenter, som kommer att hjälpa till att identifiera potentiella beroenden och/eller ändringar som krävs i tekniker eller processer.

| Vad                                  | Beskrivning |
|---------------------------------------|-------------|
| Antal slutpunkter                        |    Totalt antal slutpunkter per operativsystem.         |
| Antal servrar                          |    Totalt antal servrar efter operativsystemsversion.    |
| Hanteringsmotor                     |    Namn och version för hanteringsmotorn (till exempel System Center Configuration Manager Current Branch 1803).         |
| CDOC-fördelning                     |    Hög nivå CDOC-struktur (t.ex. Tier 1-outsourcing till Contoso, Tier 2 och Tier 3 internt fördelat över Europa och Asien).         |
| Säkerhetsinformation och händelse (SIEM) |    SIEM-teknik som används.         |


## <a name="role-based-access-control"></a>Rollbaserad åtkomstkontroll

Microsoft rekommenderar att man använder minsta behörighetsbegreppet. Defender för Endpoint utnyttjar inbyggda roller i Azure Active Directory. Microsoft rekommenderar att [du granskar de olika roller som är tillgängliga](/azure/active-directory/active-directory-assign-admin-roles-azure-portal) och väljer rätt roll för att lösa dina behov för varje person i programmet. Vissa roller kan behöva tillämpas tillfälligt och tas bort när distributionen har slutförts.

| Personas                     | Roller | Azure AD-roll (vid behov) | Tilldela till |
|------------------------------|-------|-----------------------------|-----------|
| Säkerhetsadministratör       |       |                             |           |
| Säkerhetsanalytiker             |       |                             |           |
| Slutpunktsadministratör       |       |                             |           |
| Infrastrukturadministratör |       |                             |           |
| Företagsägare/intressent   |       |                             |           |

Microsoft rekommenderar att du [Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure) att hantera dina roller för att tillhandahålla ytterligare granskning, kontroll och åtkomstgranskning för användare med katalogbehörighet.

Defender för Endpoint har stöd för två sätt att hantera behörigheter:

-   **Grundläggande behörighetshantering:** Ange behörighet till antingen fullständig åtkomst eller skrivskydd. När det gäller användare av grundläggande behörighetshantering med rollen Global administratör eller Säkerhetsadministratör i Azure Active Directory ha fullständig åtkomst medan rollen Säkerhetsläsare har skrivskyddsåtkomst.

-   **Rollbaserad åtkomstkontroll (RBAC):** Ange detaljerade behörigheter genom att definiera roller, tilldela Azure AD-användargrupper till rollerna och ge användargrupper åtkomst till enhetsgrupper. Mer information. se [Hantera portalåtkomst med hjälp av rollbaserad åtkomstkontroll](rbac.md).

Microsoft rekommenderar att du utnyttjar RBAC för att säkerställa att endast användare som har ett företags justering kan komma åt Defender för Endpoint.

Mer information om behörighetsriktlinjer finns här: [Skapa roller och tilldela rollen till en Azure Active Directory grupp](/microsoft-365/security/defender-endpoint/user-roles#create-roles-and-assign-the-role-to-an-azure-active-directory-group).

Följande exempeltabell hjälper till att identifiera Cyber Defense Operations Center-strukturen i din miljö som hjälper dig att avgöra vilken RBAC-struktur som krävs för din miljö.

| Tier   | Beskrivning                                                                                                                                                                                                 | Behörighet krävs |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Nivå 1 | **Team/IT-team för lokala säkerhetsåtgärder**<br>Gruppen undersöker och undersöker vanligtvis aviseringar som finns inom deras geolokalisering och eskalerar till nivå 2 i fall där en aktiv åtgärd krävs.                                              |                     |
| Nivå 2 | **Teamet för regionala säkerhetsåtgärder**<br>Det här teamet kan se alla enheter i deras region och utföra åtgärder.                                                                                                                        |        Visa data               |
| Nivå 3 | **Teamet för globala säkerhetsåtgärder**<br>Det här teamet består av säkerhetsexperter och har behörighet att se och utföra alla åtgärder från portalen. | Visa data <br>  Undersökning av aviseringar Aktiv åtgärd <br> Undersökning av aviseringar Aktiv åtgärd <br> Hantera systeminställningar för portalsystem <br> Hantera säkerhetsinställningar |



## <a name="adoption-order"></a>Införandeordning
I många fall kommer organisationer att ha befintliga slutpunktssäkerhetsprodukter på plats. Lägsta antalet organisationer måste ha varit en antiviruslösning. Men i vissa fall kan en organisation också ha tagit bort en Identifiering och åtgärd på slutpunkt lösning redan.

Historiskt sett var det tidsintensivt och svårt att ersätta alla säkerhetslösningar på grund av de nära hakar i programlagret och beroenden av infrastrukturen. Men eftersom Defender för Endpoint är inbyggt i operativsystemet är det nu enkelt att byta ut lösningar från tredje part.

Välj komponenten i Defender för slutpunkt som ska användas och ta bort de som inte gäller. I tabellen nedan visas den ordning som Microsoft rekommenderar för hur slutpunktssäkerhetspaketet ska aktiveras.

| Komponent                               | Beskrivning                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rangordning för införandeordning |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Slutpunktsidentifiering & svar (Identifiering och åtgärd på slutpunkt)     | Defender för identifiering och åtgärd på slutpunkt tillhandahåller avancerade attackidentifieringar som är nästan i realtid och kan vidtas. Säkerhetsanalytiker kan effektivt prioritera varningar, få synlighet över helheten av ett intrång och vidta åtgärder för att åtgärda hot. <br> [Lära sig mer.](/windows/security/threat-protection/windows-defender-atp/overview-endpoint-detection-response)                                                                                                                                                                                                                                             | 1                   |
|Threat & Vulnerability Management (TVM)|Hot & Sårbarhetshantering är en komponent i Microsoft Defender för Endpoint och ger både säkerhetsadministratörer och säkerhetsoperationsteam ett unikt värde, inklusive: <br> -, identifiering och åtgärd på slutpunkt (Identifiering och åtgärd på slutpunkt) i realtid som är korrelerade med svagheter i slutpunkten <br> – ovärderliga enhetsbrister under incidentundersökningar <br> - Inbyggda åtgärdsprocesser via Microsoft Intune och Microsoft System Center Configuration Manager <br> [Mer information](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Introducing-a-risk-based-approach-to-threat-and-vulnerability/ba-p/377845).| 2 |
| Nästa generations skydd (NGP)        | Microsoft Defender Antivirus är en inbyggd antimalwarelösning som ger nästa generations skydd för stationära datorer, bärbara datorer och servrar. Microsoft Defender Antivirus omfattar: <br> -Moln levererat skydd för omedelbar identifiering och blockering av nya och nya hot. Tillsammans med maskininlärning och intelligent Graph är moln levererat skydd en del av nästa generations teknik som driver Microsoft Defender Antivirus.   <br> - Alltid-on-skanning med avancerad övervakning av fil- och processbeteenden och annan heuristics (kallas även "realtidsskydd"). <br> - Dedikerade skyddsuppdateringar baserade på maskininlärning, mänsklig och automatiserad analys av stora data, samt ingående forskning om ändliga hot. <br> [Mer information](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
| Minskning av attackytan (ASR)          | Funktioner för att minska attackytan i Microsoft Defender för Endpoint hjälper till att skydda enheter och program i organisationen från nya och nya hot. <br> [Lära sig mer.](/windows/security/threat-protection/windows-defender-atp/overview-attack-surface-reduction)                                                                                                                                                                                                                                                                                                                                                                                       | 4                   |
| Auto Investigation & Remediation (AIR)  | Microsoft Defender för Endpoint använder automatiska undersökningar för att avsevärt sänka mängden aviseringar som behöver undersökas individuellt. Funktionen Automatisk undersökning utnyttjar olika kontrollalgoritmer och processer som används av analytiker (till exempel spelböcker) för att undersöka aviseringar och vidta omedelbar åtgärd för att lösa överträdelser. Detta minskar meddelandevolymen avsevärt, vilket gör att experter på säkerhetsåtgärder kan fokusera på mer avancerade hot och andra initiativ med höga värden. <br>[Lära sig mer.](/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection) | Ej tillämpligt      |
| Microsoft Hotexperter (MTE)          | Microsoft Hotexperter är en hanterad säkerhetstjänst som tillhandahåller säkerhetscenter (SOCs) med övervakning och analys på expertnivå för att hjälpa dem att säkerställa att kritiska hot i deras unika miljöer inte missas. <br>[Lära sig mer.](/windows/security/threat-protection/windows-defender-atp/microsoft-threat-experts)                                                                                                                                                                                                                                                                                                                     | Ej tillämpligt      |

## <a name="next-step"></a>Nästa steg


![Fas 2: Installation](images/setup.png) <br>[Fas 2: Installation](production-deployment.md) 
 
Konfigurera Microsoft Defender för distribution av Slutpunkt 
