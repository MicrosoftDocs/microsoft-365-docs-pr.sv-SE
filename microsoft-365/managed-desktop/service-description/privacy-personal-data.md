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
ms.openlocfilehash: 3de39e8d10f949856862095ebd204fac1a4d694e
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861689"
---
# <a name="privacy-and-personal-data"></a>Sekretess och personlig information

Användare kan ta emot, överföra och lagra data på enheter som hanteras av Microsoft Hanterat skrivbord. De litar på att datas integritet skyddas och används på ett sätt som stämmer överens med deras förväntningar. I den här artikeln förklaras Microsoft Hanterat skrivbord samlar in, lagrar, bevarar, bearbetar, säkrar, delar, granskar och exporterar personuppgifter. Du får också lära dig hur en administratör kan visa, korrigera och ta bort personliga data.

Microsoft Hanterat skrivbord några personliga data som samlas in för att tillhandahålla tjänsten i profilerings-, reklam- eller marknadsföringssyfte.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Datainsamling av Microsoft Hanterat skrivbord

När användare registrerar företagets enheter i Microsoft Hanterat skrivbord hanteras datainsamling – på det tekniska lagret – med hjälp av Windows och Microsoft Intune. Dessa källor samlar in personlig information om användarnas enheter, till exempel enhetsnamn för Microsoft Hanterat skrivbord för att kunna identifiera vilken enhet som ska hanteras och tillhandahållas med Microsoft Hanterat skrivbord funktioner.

Microsoft Hanterat skrivbord samlar inte in data själva för att tillhandahålla tjänsten (utom [kontaktinformation för IT-administratörer.](#it-admin-contact-information) I stället Microsoft Hanterat skrivbord data som andra källor, till exempel Windows och Microsoft Intune, redan har samlat in. Microsoft Hanterat skrivbord använder data som samlas in från registrerade enheter:

- Windows av diagnostikdata från enheter som hanteras Microsoft Hanterat skrivbord skickas till Microsofts Windows för diagnostikdata.
- Microsoft Hanterat skrivbord använder [modern hantering](/learn/modules/introduction-to-modern-management-in-microsoft-365/) för att hantera registrerade enheter. Som en del av "modern hantering" måste enheterna vara registrerade i klientorganisationens Azure Active Directory.
- Om du vill distribuera en optimerad och säker konfiguration till registrerade enheter använder Microsoft Hanterat skrivbord den Microsoft Intune.
- Microsoft Hanterat skrivbord använder säkerhetsintelligensdata från Microsoft Defender Avancerat trådskydd för kunder som använder den tjänsten.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Datalagring och källor i Microsoft Hanterat skrivbord

När Microsoft Hanterat skrivbord hämtar data måste de tillhandahålla sin tjänst, lagring och bearbetning av dessa data på följande sätt:

### <a name="storing-data-storage-location-and-data-retention"></a>Lagra data, lagringsplats och datalagring

Microsoft Hanterat skrivbord lagras data i en eller flera av följande Microsoft-lagringstjänster:

- Azure-SQL
- Azure-lagring
- Dynamics 365

Microsoft Hanterat skrivbord lagras i USA. Personliga data sparas senast Microsoft Hanterat skrivbord i högst 30 dagar, förutom aviseringsdata för Microsoft Hanterat skrivbord-enheter som samlas in av Microsoft Defender för Endpoint. De faktiska aviseringsdata (som kan inkludera personuppgifter) lagras i 180 dagar. Aviseringsdata där personuppgifter tas bort lagras i upp till två år. I enlighet med dataskyddsförordningen (GDPR) och California Consumer Privacy Act (CCPA) följer Microsoft Hanterat skrivbord data omfattas av alla personuppgifter som lagras i aviseringsdata.

### <a name="staff-location"></a>Personalplats

Teamen Microsoft Hanterat skrivbord Operations and Security Operations är placerade i USA och Indien.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Dataanvändning av Microsoft Hanterat skrivbord

Microsoft Hanterat skrivbord använder följande data:


| Datakällor |Används med Microsoft Hanterat skrivbord  |
|---------|---------|
|Azure Active Directory data     | Används i rapporter som skapats för innehavaradministratörer, som är tillgängliga Microsoft Hanterat skrivbord administrationsportalen.        |
|Intune-data     | Används i rapporter som skapats för innehavaradministratörer, som är tillgängliga Microsoft Hanterat skrivbord administrationsportalen.        |
|Microsoft Defender för Endpoint     |  Används för att hantera säkerhetshot som upptäckts på registrerade enheter av Microsoft Hanterat skrivbord Säkerhetsoperationscenter (SOC).  |
|Windows diagnostikdata     |Används för att fastställa uppdateringsstatus för hanterade enheter och för att tillhandahålla Microsoft Hanterat skrivbord av ITaaS-erbjudande (IT-as-a-Service).         |
|Kontaktdata för administratör     | Används av Microsoft Hanterat skrivbord för att kommunicera med innehavaradministratörer.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Enheter som bearbetas av Microsoft Hanterat skrivbord

Microsoft Hanterat skrivbord bearbetar dessa enheter för att tillhandahålla tjänsten:

- Enhetsdata
- Säkerhetsinställningar för enheter
- Operativsystem och maskinvara för enheter
- Aggregerad information om enhetens hälsa
- Enhetsdiagnostikinformation
- Klientorganisationsdata
- Azure Active Directory resurser
- Policy- och konfigurationsdata
- Microsoft Defender för slutpunktens metadata och aviseringsdata
- Windows diagnostikdata
- Användningsdata för produkter och tjänster

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Identitetsdata som används av Microsoft Hanterat skrivbord lagras av Azure Active Directory på en geografisk plats baserat på den adress som tillhandahålls av organisationen när du prenumererar på en Microsoft-onlinetjänst som Office 365 eller Azure. Se [Microsoft Azure – Var finns mina kunddata? för](http://azuredatacentermap.azurewebsites.net/) en karta som visar datacenter för Azure Active Directory.

Mer information om de regioner som Används av Azure för datalagring finns [i Azure Active Directory – Var finns dina data.](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune

Intune-data kan lagras i några olika regioner, till exempel Europa nord (Irland) och Europa väst (Nederländerna). IT-administratören skapar ett klientkonto och väljer det land där data ska lagras när de först registrerar in Intune-tjänster. En lista över datacenterplatser som används av Intune finns i Microsoft Intune [– Var finns mina kunddata?](http://intunedatacentermap.azurewebsites.net/). Mer information om intune-datalagring och -användning finns i [Datainsamling i Intune.](/intune/privacy-data-collect)

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender för Endpoint

Microsoft Defender för slutpunktsdata kan lagras i några olika regioner. Av den anledningen fungerar Defender för Endpoint i Microsoft Azure-datacenter i EU, Storbritannien och USA, enligt Microsoft Defender för [Endpoint – Datalagringsplatser.](http://intunedatacentermap.azurewebsites.net/) Mer information om datalagring och användning av Defender för Endpoint finns i Vilka data samlar [Microsoft Defender för Slutpunkt in?](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Enligt [Microsofts](https://privacy.microsoft.com/privacystatement)sekretesspolicy kan "personuppgifter som samlas in av Microsoft lagras och bearbetas i din region, i USA och i alla andra länder där Microsoft eller dess koncernbolag, dotterbolag eller tjänsteleverantörer bedriver verksamhet. [...] Vanligtvis finns den primära lagringsplatsen i kundens region eller i USA, ofta med en säkerhetskopia till ett datacenter i en annan region. Lagringsplatserna väljs för att fungera effektivt, för att förbättra prestandan och för att skapa redundans för att skydda data vid avbrott eller andra problem. Vi vidta åtgärder för att se till att de data vi samlar in enligt denna sekretesspolicy bearbetas i enlighet med bestämmelserna i denna policy och kraven i tillämplig lag oavsett var informationen finns."

Mer information om insamling av diagnostikdata för Windows 10 i avsnittet "Var vi lagrar och [bearbetar personuppgifter"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) i Microsofts sekretesspolicy.

## <a name="data-access-protection"></a>Dataskydd

På flera sätt Microsoft Hanterat skrivbord direkt åtkomst till de interna datakällorna:

- Det kräver godkännande från teknisk lednivå.
- Den är tidsbunden och granskad.
- Alla data krypteras medan de lagras.
- Åtkomst till Microsoft Hanterat skrivbord interna hanteringsportal kräver en starkt skyddad och begränsad arbetsstation.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Bearbeta personuppgifter på ett kompatibelt sätt
Microsoft Hanterat skrivbord bearbetar personuppgifter med ISO-certifierade system. Mer information finns i [Efterlevnad](../intro/compliance.md).

## <a name="profiling-and-marketing"></a>Profil och marknadsföring

Microsoft Hanterat skrivbord några personliga data som samlas in för att tillhandahålla tjänsten i profilerings-, reklam- eller marknadsföringssyfte.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Data Subject Requests för GDPR och CCPA

EU:s dataskyddsförordning [(GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) ger personer (som kallas för dataämnen) rättigheter att hantera personliga data som har samlats in av en arbetsgivare eller någon annan typ av agentur eller organisation (kallas datakontrollant eller bara controller). Personuppgifter definieras mycket allmänt i GDPR som data som relaterar till en identifierad eller identifierbar naturlig person. GDPR ger data individer specifika rättigheter till sina personliga data; Dessa rättigheter omfattar att skaffa kopior av personuppgifter, begära korrigeringar av dem, begränsa bearbetningen, ta bort dem eller ta emot dem i ett elektroniskt format så att de kan flyttas till en annan kontrollant. En formell begäran från en data som är ämnesansvarig för en kontrollant att vidta en åtgärd på sina personliga data kallas Data Subject Request eller DSR.

På samma sätt tillhandahåller CCPA sekretessrättigheter och skyldigheter till kaliforniens konsumenter, inklusive rättigheter som liknar GDPR:s rättigheter i data subject rights, till exempel rätten att radera, få åtkomst till och ta emot (portabilitet) deras personliga information. CCPA tillhandahåller även vissa informationskällor, skydd mot undantag när man väljer att utöva rättigheter och krav för att avanmäla/välja bort för vissa dataöverföringar som klassificerats som "försäljning". Försäljning definieras allmänt för att inkludera delning av data för en värdefull hänsyn. Mer information om CCPA finns i California [Consumer Privacy Act och](/compliance/regulatory/offering-ccpa?view=o365-worldwide) Vanliga frågor och svar om California Consumer Privacy [Act.](/compliance/regulatory/ccpa-faq?view=o365-worldwide)

I följande avsnitt beskrivs hur Microsoft Hanterat skrivbord hjälper rörelsekontroller att hitta, komma åt och agera på personliga data eller personlig information som används av Microsoft Hanterat skrivbord.

> [!NOTE]
> Om du letar efter allmän information om GDPR, se avsnittet [GDPR på](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) Service Trust Portal.

### <a name="it-admin-contact-information"></a>Kontaktinformation för IT-administratörer

En innehavaradministratör kan visa, korrigera och ta bort sina egna personliga data (till exempel egen kontaktinformation) direkt i avsnittet Administratörskontakt i Microsoft Hanterat skrivbord portalen.

## <a name="microsoft-defender-for-endpoint-alert-data"></a>Aviseringsdata för Microsoft Defender för slutpunkt

Säkerhetsadministratörer kan begära extrahering eller borttagning av personliga data relaterade till Microsoft Defender för slutpunktsaviseringar på en Microsoft Hanterat skrivbord hanterad enhet i miljön. Säkerhetsadministratören bör logga in på [Microsoft Hanterat skrivbord-administrationsportalen](https://aka.ms/memadmin) och skicka en supportbegäran. Välj Typ **av supportbegäran** i   **Ändringsförfrågan,** Säkerhetskategori och Underkategori för Annan, och ange sedan de relevanta enhetsnamnen i beskrivningen tillsammans med din begäran om extrahering eller borttagning av data.  

### <a name="user-related-personal-data"></a>Användarrelaterade personliga data

Utöver det samlar Microsoft Hanterat skrivbord inte in personliga data på egen hand. I stället används de personuppgifter som andra Microsoft Enterprise Online Services har samlat in. IT-administratörer som vill svara på användarens förfrågningar om att visa, korrigera och ta bort sina personliga data kan använda respektive funktion i de underliggande tjänster som Microsoft Hanterat skrivbord är beroende av. Om du är intresserad av att visa eller ta bort personliga data som används av dessa tjänster, se [Azure Data Subject Requests för GDPR-artikeln](/compliance/regulatory/gdpr-dsr-Azure) först.

Använd dessutom följande vägledning för att använda DSR för de Microsoft Hanterat skrivbord är beroende av för insamling av personuppgifter:

- [Azure Active Directory](/compliance/regulatory/gdpr-dsr-Azure?view=o365-worldwide)
- [Microsoft Intune](/compliance/regulatory/gdpr-dsr-Intune?view=o365-worldwide)
- [Microsoft Defender för Slutpunkt](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](/windows/privacy/windows-10-and-privacy-compliance)
