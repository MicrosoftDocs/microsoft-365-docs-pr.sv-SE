---
title: Sekretess och personliga data
description: Information om data som samlas in, lagras och används av tjänsten
keywords: GDPR, bevarande, borttagning, lagring, kvarhållning, bearbetning, säkerhet, granskning
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
ms.openlocfilehash: e98d42e79ac270e6ccce46e88e3b8ff00f8bfc0a
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712312"
---
# <a name="privacy-and-personal-data"></a>Sekretess och personliga data

Användare kan ta emot, överföra och lagra data på enheter som hanteras av Microsoft Managed Desktop. De litar på att datas integritet skyddas och bara används på ett sätt som stämmer överens med deras förväntningar. I den här artikeln förklaras hur Microsoft Hanterat skrivbord samlar in, lagrar, bevarar, bearbetar, säkrar, delar, granskar och exporterar personuppgifter. Du får också lära dig hur en administratör kan visa, korrigera och ta bort personliga data.

Microsoft Hanterade skrivbord använder inga personliga data som samlas in för att tillhandahålla tjänsten för profilering, reklam eller marknadsföring.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Datainsamling av Microsoft Managed Desktop

När användare registrerar företagsenheter i Microsoft Managed Desktop hanteras datainsamling – på det tekniska lagret – med hjälp av Windows och Microsoft Intune. Dessa källor samlar in personlig information om användarnas enheter, till exempel enhetsnamn för Microsoft Managed Desktop för att kunna identifiera enheten som ska hanteras och tillhandahållas med Microsoft Managed Desktop-upplevelserna.

Microsoft Hanterat skrivbord samlar inte in data för sig själva för att tillhandahålla tjänsten (utom [kontaktinformation till IT-administratörer.](#it-admin-contact-information) I stället återanvänds data som andra källor, till exempel Windows och Microsoft Intune, redan har samlat in. Microsoft Managed Desktop använder data som samlas in från registrerade enheter:

- Windows-diagnostikdata från enheter som hanteras av Microsoft Managed Desktop skickas till Microsofts butiker för Windows-diagnostikdata.
- Microsoft Managed Desktop använder [modern hantering](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) för att hantera registrerade enheter. Som en del av "modern hantering" måste enheterna vara registrerade i klientorganisationens Azure Active Directory.
- Microsoft Managed Desktop använder Microsoft Intune för att distribuera sin optimerade och säkra konfiguration till registrerade enheter.
- Microsoft Managed Desktop använder säkerhetsinformation från Microsoft Defender Avancerat trådskydd för de kunder som använder den tjänsten.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Datalagring och källor i Microsoft Managed Desktop

När Microsoft Hanterat skrivbord hämtar data måste de tillhandahålla sin tjänst, lagring och bearbetning av dessa data följande:

### <a name="storing-data-storage-location-and-data-retention"></a>Lagra data, lagringsplats och datalagring

Microsoft Hanterade skrivbord lagrar sina data i en eller flera av följande Microsoft-lagringstjänster:

- Azure SQL
- Azure-lagring
- Dynamics 365

Microsoft Managed Desktop lagrar sina data i USA. Personliga data behålls av Microsoft Managed Desktop i högst 30 dagar, förutom aviseringsdata för Microsoft Managed Desktop-enheter som samlas in av Microsoft Defender för Endpoint. Faktiska aviseringsdata (som kan inkludera personuppgifter) lagras i 180 dagar. Aviseringsdata där personuppgifter tas bort lagras i upp till två år. I enlighet med dataskyddsförordningen (GDPR) och CCPA (California Consumer Privacy Act) följer Microsoft Managed Desktop data subject rights för alla personuppgifter som lagras i aviseringsdata.

### <a name="staff-location"></a>Personalplats

Microsoft Managed Desktop Operations och Security Operations teams finns i USA och Indien.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Dataanvändning av Microsoft Managed Desktop

Microsoft Hanterat skrivbord använder följande data:


| Datakällor |Använd med Microsoft Managed Desktop  |
|---------|---------|
|Azure Active Directory-data     | Används i rapporter som skapats för innehavaradministratörer, som är tillgängliga i Microsoft Managed Desktop Admin-portalen.        |
|Intune-data     | Används i rapporter som skapats för innehavaradministratörer, som är tillgängliga i Microsoft Managed Desktop Admin-portalen.        |
|Microsoft Defender för Endpoint     |  Används för att hantera säkerhetshot som upptäckts på registrerade enheter av Microsoft Managed Desktops Säkerhetsoperationscenter (SOC).  |
|Windows-diagnostikdata     |Används för att fastställa uppdateringsstatus för hanterade enheter och för att tillhandahålla och förbättra Microsoft Managed Desktops erbjudande om IT-as-a-Service (ITaaS).         |
|Administratörskontaktdata     | Används av Microsoft Hanterad dator för att kommunicera med innehavaradministratörer.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Enheter som bearbetas av Microsoft Managed Desktop

Microsoft Hanterat skrivbord bearbetar dessa enheter för att tillhandahålla tjänsten:

- Enhetsdata
- Säkerhetsinställningar för enheter
- Operativsystem och maskinvara för enheter
- Aggregerad information om enhetshälsa
- Enhetsdiagnostikinformation
- Klientorganisationsdata
- Azure Active Directory-resurser
- Princip- och konfigurationsdata
- Microsoft Defender för slutpunktens metadata och aviseringsdata
- Windows-diagnostikdata
- Användningsdata för produkter och tjänster

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Identitetsdata som används av Microsoft Managed Desktop lagras av Azure Active Directory på en geografisk plats baserat på den adress som tillhandahålls av organisationen när du prenumererar på en Microsoft-onlinetjänst som Office 365 eller Azure. Se [Microsoft Azure – Var finns mina kunddata?](http://azuredatacentermap.azurewebsites.net/) för en karta som visar datacenter för Azure Active Directory.

Mer information om de regioner som Azure använder för datalagring finns i [Azure Active Directory – var finns dina data.](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune

Intune-data kan lagras i några olika regioner, till exempel Europa Nord (Irland) och Europa väst (Nederländerna). IT-administratören skapar ett klientkonto och väljer det land där data ska lagras när de först registrerar sig i Intune-tjänster. En lista över datacenterplatser som används av Intune finns i [Microsoft Intune – Var finns mina kunddata?](http://intunedatacentermap.azurewebsites.net/). Mer information om datalagring och användning av Intune finns i [Datainsamling i Intune.](https://docs.microsoft.com/intune/privacy-data-collect)

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender för Endpoint

Microsoft Defender för slutpunktsdata kan lagras i några olika regioner. Av den anledningen fungerar Defender för Endpoint i Microsoft Azure-datacenter i EU, Storbritannien och USA, enligt vad som anges i Microsoft Defender för Endpoint – [Datalagringsplatser.](http://intunedatacentermap.azurewebsites.net/) Mer information om datalagring och användning av Defender för Endpoint finns i Vilka data samlar [Microsoft Defender för Endpoint in?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Enligt [Microsofts](https://privacy.microsoft.com/privacystatement)sekretesspolicy kan "personuppgifter som samlas in av Microsoft lagras och bearbetas i din region, i USA och i alla andra länder där Microsoft eller dess koncernbolag, dotterbolag eller tjänsteleverantörer bedriver verksamhet. [...] Vanligtvis finns den primära lagringsplatsen i kundens region eller i USA, ofta med en säkerhetskopia till ett datacenter i en annan region. Lagringsplatserna väljs för att fungera effektivt, för att förbättra prestandan och för att skapa redundans för att skydda data om det uppstår ett avbrott eller andra problem. Vi vidta åtgärder för att se till att de data vi samlar in enligt denna sekretesspolicy behandlas i enlighet med bestämmelserna i denna sekretesspolicy och kraven i tillämplig lag var data än finns."

Mer information om insamling av diagnostikdata i Windows 10 finns i avsnittet Var vi lagrar och [bearbetar personuppgifter i](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) Microsofts sekretesspolicy.

## <a name="data-access-protection"></a>Dataskydd

Direkt åtkomst till Microsoft Managed Desktops interna datakällor är begränsad på flera sätt:

- Det kräver godkännande av teknisk leadnivå.
- Den är både granskad och begränsad tid.
- Det kräver att en arbetsstation med hög säkerhet och begränsad användning krävs.
- Alla data krypteras medan de lagras.
- Det finns ingen stående åtkomst.
- Åtkomst till Microsoft Managed Desktops interna hanteringsportal kräver en skyddad och begränsad arbetsstation.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Bearbetning av personuppgifter på ett kompatibelt sätt
Microsoft Managed Desktop bearbetar personuppgifter med ISO-certifierade system. Mer information finns i [Efterlevnad.](../intro/compliance.md)

## <a name="profiling-and-marketing"></a>Profil och marknadsföring

Microsoft Hanterade skrivbord använder inga personliga data som samlas in för att tillhandahålla tjänsten för profilering, reklam eller marknadsföring.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Data Subject Requests för GDPR och CCPA

EU:s dataskyddsförordning [(GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) ger personer (som kallas i regeln dataämnen) rättigheter att hantera personuppgifter som har samlats in av en arbetsgivare eller annan typ av agentur eller organisation (kallas datakontrollant eller bara kontrollant). Personuppgifter definieras mycket allmänt i GDPR som data som relaterar till en identifierad eller identifierbar fysisk person. GDPR ger dataämnen specifika rättigheter till sina personuppgifter. Dessa rättigheter omfattar att skaffa kopior av personuppgifter, begära korrigeringar av dem, begränsa bearbetningen av dem, ta bort dem eller ta emot dem i ett elektroniskt format så att de kan flyttas till en annan handkontroll. En formell begäran från en dataansvarig om att vidta en åtgärd på deras personuppgifter kallas data subject request eller DSR.

PÅ samma sätt ger CCPA sekretessrättigheter och skyldigheter till konsumenter i Kalifornien, inklusive rättigheter som liknar GDPR:s rättigheter avseende data ämne, till exempel rätten att radera, komma åt och ta emot (porterbarhet) deras personliga information. CCPA innehåller även vissa villkor om avslöjande, skydd mot våld vid val av rättigheter och krav på avanmälning/avanmälning för vissa dataöverföringar som klassificeras som "försäljning". Försäljning definieras allmänt för att inkludera delning av data för en värdefull överväganden. Mer information om CCPA finns i California [Consumer Privacy Act och](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide) Vanliga frågor och svar om Consumer Privacy Act i [Kalifornien.](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide)

I följande avsnitt beskrivs hur Microsoft Hanterade skrivbord hjälper handkontroller att hitta, komma åt och agera på personuppgifter eller personlig information som används av Microsoft Managed Desktop.

> [!NOTE]
> Om du letar efter allmän information om GDPR kan du läsa avsnittet [GDPR på](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) Service Trust Portal.

### <a name="it-admin-contact-information"></a>Kontaktinformation för IT-administratörer

En innehavaradministratör kan visa, korrigera och ta bort sina egna personliga data (till exempel sin egen kontaktinformation) direkt i avsnittet Administratörskontakt i Microsoft Managed Desktop Portal.

## <a name="microsoft-defender-for-endpoint-alert-data"></a>Microsoft Defender för slutpunktsaviseringsdata

Säkerhetsadministratörer kan begära extrahering eller borttagning av personliga data som är relaterade till Microsoft Defender för slutpunktsaviseringar på en enhet som hanteras av Microsoft Hanterad dator i deras miljö. Säkerhetsadministratören bör logga in på Microsofts administrationsportal för [skrivbordet](https://aka.ms/memadmin) och skicka in en supportbegäran. Välj typ av   **ändringsförfrågan,** säkerhetskategori och underkategori för Annan, och ange sedan de relevanta enhetsnamnen i beskrivningen tillsammans med din begäran om extrahering eller borttagning av data. 

### <a name="user-related-personal-data"></a>Användarrelaterade personliga data

Utöver detta samlar Microsoft Managed Desktop inte in personliga data på egen hand. Den förlitar sig i stället på och använder personuppgifter som andra Microsoft Enterprise Online Services som samlas in. IT-administratörer som vill svara på sina användarförfrågningar om att visa, korrigera och ta bort sina personliga data kan använda respektive funktion i de underliggande tjänster som Microsoft Hanterat skrivbord är beroende av. Om du är intresserad av att visa eller ta bort personliga data som används av dessa tjänster, se [Azure Data Subject Requests för GDPR-artikeln](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) först.

Använd dessutom följande vägledning för att använda DSR för tjänsterna Microsoft Managed Desktop är beroende av för insamling av personliga data:

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender för Slutpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
