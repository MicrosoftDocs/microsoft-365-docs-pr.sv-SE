---
title: Sekretess och personlig information
description: Information om data som samlas in, lagras och används av tjänsten
keywords: GDPR, bevarande, borttagning, lagring, lagring, bearbetning, säkerhet, granskning
ms.service: m365-md
ms.sitesec: library
author: jaimeo
manager: laurawi
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: normal
ms.openlocfilehash: 0ee214cf7ff5d5998a7fa35688574a23f8b082f0
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229605"
---
# <a name="overview"></a>Översikt

Microsoft Hanterat skrivbord är en ITaaS-tjänst (IT-as-a-Service) för kunder i företagsmoln som utformats för att hålla anställdas anställda Windows distribuerade och uppdaterade. Den förser även IT-tjänstehantering och -drift, övervakar säkerhets- och incidentåtgärder samt ger support. I den här dokumentationen finns mer information om dataplattformen och sekretessefterlevnad för Microsoft Hanterat skrivbord.

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Microsoft Hanterat skrivbord och syfte med datakällor

Microsoft Hanterat skrivbord tillhandahåller sin tjänst till företagskunder och administrerar korrekt kundernas registrerade enheter genom att använda data från olika källor. De här källorna, Azure Active Directory, Microsoft Intune, Microsoft Windows 10 och Microsoft Defender för Endpoint, ger en omfattande vy över de enheter Microsoft Hanterat skrivbord hanterar. Tjänsten använder också följande Microsoft-tjänster för att Microsoft Hanterat skrivbord att tillhandahålla ITaaS-funktioner:

- [Microsoft Windows 10 Enterprise](/windows/windows-10/) – för hantering av enhetskonfiguration, hantering av anslutningar till andra tjänster och driftstöd för IT-proffs.
- [Windows för företag – använder](/windows/deployment/update/waas-manage-updates-wufb) en Windows 10 Enterprise för att ge ytterligare information vid Windows 10 uppdatering. 
- [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) – för enhetshantering och för att skydda dina data.
  - [Microsoft Azure Active Directory](/azure/active-directory/) – för autentisering och identifiering av alla användarkonton. 
  - [Microsoft Intune](/mem/intune/) – används för att distribuera enhetskonfigurationer, enhetshantering och programhantering.
  - [Slutpunktsanalys](/mem/analytics/overview) – för analys av enhets- och appanvändning.
  - [Windows Autopilot](/microsoft-365/windows/windows-autopilot) – för enhetsetablering och distribution.
  - [Microsoft Defender för slutpunkt](/microsoft-365/security/defender-endpoint/) – tillhandahåller säkerhetstjänster som övervakning av enhetssäkerhet och säkerhetsintelligensdata.
- [Microsoft Hanterat skrivbord](https://endpoint.microsoft.com/#home) – Data som tillhandahålls av kunden eller genereras av tjänsten när tjänsten körs.
- [Microsoft 365 appar för företag](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1) – för hantering av Microsoft 365-applikationer.

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Microsoft Hanterat skrivbord dataprocess och lagring

Microsoft Hanterat skrivbord använder data från flera olika Microsoft-produkter och -tjänster för att tillhandahålla sina tjänster till företagskunder. För att uppnå målet för att skydda och underhålla registrerade enheter bearbetar och kopierar vi data från dessa tjänster till Microsoft Hanterat skrivbord. När vi bearbetar data följer vi de bedokumenterade anvisningarna som du anger i villkoren för onlinetjänster och Microsofts sekretesspolicy. När vi bearbetar data följer vi de bedokumenterade anvisningarna som du anger i villkoren [för onlinetjänster](https://www.microsoft.com/licensing/product-licensing/products) och [Microsofts sekretesspolicy.](https://privacy.microsoft.com/privacystatement) Microsoft Hanterat skrivbord processoruppgifter omfattar att säkerställa lämplig konfidentialitet, säkerhet och motståndskraft. Microsoft Hanterat skrivbord ytterligare sekretess- och säkerhetsåtgärder för att säkerställa korrekt hantering av personliga identifierbara data. 


## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Microsoft Hanterat skrivbord datalagring och personalplats

Microsoft Hanterat skrivbord lagras data i Azure-datacenter i USA. Personliga data som inhämtas Microsoft Hanterat skrivbord och andra tjänster krävs för att tjänsten ska fungera. Om en enhet tas bort från Microsoft Hanterat skrivbord behåller vi personuppgifter i högst 30 dagar, förutom aviseringsdata som samlas in av Microsoft Defender för Endpoint, som lagras i 180 dagar av säkerhetsskäl. Mer information om databevarande finns i [Datalagring, borttagning och bevarande av data i Microsoft 365.](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)

Microsoft Hanterat skrivbord Engineering Operations and Security Operations teams finns i USA och Indien. 

## <a name="microsoft-windows-10-diagnostic-data"></a>Microsoft Windows 10 för diagnostikdata

Microsoft Hanterat skrivbord använder [Windows 10 förbättrade diagnostikdata](/windows/privacy/windows-diagnostic-data) för att Windows att hålla dig säker, uppdaterad, felsöka problem och göra produktförbättringar. Den förbättrade inställningen för diagnostikdata innehåller mer detaljerad information om de enheter som är registrerade Microsoft Hanterat skrivbord deras inställningar, funktioner och enhetshälsa. När förbättrade diagnostikdata markeras samlas data, inklusive obligatoriska diagnostikdata, in. Mer [information Windows om inställningar för diagnostikdata](/windows/privacy/changes-to-windows-diagnostic-data-collection) och datainsamling Windows 10 ändringar av diagnostikdata.

Terminologin för diagnostikdata ändras i framtida versioner av Windows. Microsoft Hanterat skrivbord endast bearbeta de data som tjänsten behöver. Även om detta innebär att diagnostiknivån ändras till Valfri **så** kommer Microsoft Hanterat skrivbord att implementera begränsade diagnostikprinciper för att finjustera insamling av diagnostikdata som krävs för tjänsten. Mer information finns i Ändringar [av Windows insamling av diagnostikdata.](/windows/privacy/changes-to-windows-diagnostic-data-collection)

Microsoft Hanterat skrivbord endast processer och lagrar data på systemnivå från Windows 10 valfria diagnostikdata som kommer från registrerade enheter, till exempel program- och enhetstillförlitlighet och prestandainformation. Microsoft Hanterat skrivbord inte bearbetar och lagrar inte kundernas personuppgifter som chatt- och webbläsarhistorik, röst-, text- eller taldata. 

Mer information om insamling av diagnostikdata för Microsoft Windows 10 finns i avsnittet Var vi lagrar och [bearbetar personuppgifter](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) i Microsofts sekretesspolicy.

## <a name="microsoft-windows-update-for-business"></a>Microsoft Windows Update för företag
Microsoft Windows Update för företag använder data från Windows för att analysera uppdateringsstatus och fel. Microsoft Hanterat skrivbord utnyttjar dessa data och använder dem för att minimera och lösa problem för att säkerställa att alla registrerade enheter är uppdaterade baserat på ett fördefinierat uppdateringsfrekvens.

## <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory
Identifiering av data som används av Microsoft Hanterat skrivbord lagras av Azure Active Directory (Azure AD) på en geografisk plats baserat på den plats som tillhandahålls av organisationen när du prenumererar på Microsofts onlinetjänster, till exempel Microsoft Apps för företag och Azure. Identifiering av data som används av Microsoft Hanterat skrivbord lagras av Azure AD på en geografisk plats baserat på den plats som tillhandahålls av organisationen när du prenumererar på Microsofts onlinetjänster, till exempel Microsoft Apps för företag och Azure. Mer information om var dina Azure AD-data finns finns i Azure Active Directory [– Var finns dina data?](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

## <a name="microsoft-intune"></a>Microsoft Intune
Microsoft Intune samlar in, bearbetar och delar data i ett Microsoft Hanterat skrivbord för att stödja affärsverksamhet och tjänster. Mer information om data som samlas in i Intune finns i Datainsamling i [Intune.](/mem/intune/protect/privacy-data-collect) 

Mer information om Microsoft Intune dataplatser finns i [Var dina Microsoft 365 kunddata lagras](/microsoft-365/enterprise/o365-data-locations). Intune respekterar de lagringsplatser som administratören gjort för kunddata.

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender för Endpoint
Microsoft Defender för Endpoint samlar in och lagrar information för enheter som är registrerade Microsoft Hanterat skrivbord för administrations-, spårnings- och rapporteringssyften. Information som samlas in omfattar fildata (t.ex. filnamn, storlek och hash-filer), processdata (processer, hash-processer), registerdata, nätverksanslutningsdata och enhetsinformation (till exempel enhetsidentifierare, enhetsnamn och operativsystemsversionen). Se [Microsoft Defender för slutpunktens datalagring och](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) sekretess för mer information om Microsoft Defender för Endpoints datainsamlings- och lagringsplatser. 

## <a name="microsoft-365-apps-for-enterprise"></a> Microsoft 365 Apps för företag 
Microsoft 365-appar för företag samlar in och delar data med Microsoft Hanterat skrivbord för att säkerställa att apparna är uppdaterade med den senaste versionen baserat på fördefinierade uppdateringskanaler som hanteras av Microsoft Hanterat skrivbord. Se [Microsoft Defender för Slutpunktens datalagring och](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) sekretess för mer information Microsoft 365-applikationer information om datainsamling och lagringsplatser.

## <a name="major-data-change-notification"></a>Meddelande om större dataändring
Microsoft Hanterat skrivbord följer en ändringskontrollprocess enligt beskrivningen i vårt tjänstkommunikationsramverk. Vi meddelar kunderna via Microsoft 365 meddelandecenter och Microsoft Hanterat skrivbord administrationsportal om både säkerhetsincidenter och större ändringar av tjänsten. Ändringar av de typer av data som samlats och var de lagras betraktas som en materialändring. Vi kommer att meddela minst 30 dagar i förväg om den här ändringen enligt standard för Microsoft 365 produkter och tjänster. Mer information finns i [Tjänständringar och kommunikation.](/microsoft-365/managed-desktop/service-description/servicechanges)

## <a name="compliance"></a>Efterlevnad
Microsoft Hanterat skrivbord har genomgått externa granskningar och fått en omfattande uppsättning efterlevnadserbjudanden. Mer information finns i Microsoft Hanterat skrivbord [regelefterlevnad.](/microsoft-365/managed-desktop/intro/compliance) Granskningsrapporter finns tillgängliga för nedladdning på Microsoft [Service Trust Portal,](https://aka.ms/stp)som fungerar som en central lagringsplats för Microsoft Enterprise Online Services. (Microsoft Hanterat skrivbord i de här dokumenten under kategorin "Övervakning och hantering".) 

## <a name="legal"></a>Villkor
**Microsofts sekretesspolicy** för slutanvändare av produkter som tillhandahålls av organisationskunder – [Microsofts](https://privacy.microsoft.com/privacystatement) sekretesspolicy meddelar slutanvändarna att när de loggar in på Microsoft-produkter med ett arbetskonto, a) deras organisation kan kontrollera och administrera sina konton (inklusive kontrollera sekretessrelaterade inställningar) och åtkomst och bearbeta sina data, och b) Microsoft kan samla in och bearbeta data för att tillhandahålla tjänsten till organisationen och slutanvändarna.
