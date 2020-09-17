---
title: Integritets-och person uppgifter
description: Information om vilka data som samlas in, lagras och används av tjänsten
keywords: GDPR, bevarande, borttagning, lagring, bevarande, bearbetning, säkerhet, granskning
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 33a2bf0b85b9b8561a5dcf32eae6e4cd0cb53765
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950490"
---
# <a name="privacy-and-personal-data"></a>Integritets-och person uppgifter

Användare kan ta emot, överföra och lagra data på enheter som hanteras av Microsoft Managed Desktop. De litar på att data integriteten skyddas och används endast på ett sätt som överensstämmer med deras förväntningar. I den här artikeln beskrivs hur Microsoft Managed Desktop samlar in, lagrar, bevarar, bearbetar, skyddar, delar, granskar och exporterar person uppgifter. Du får också lära dig hur en administratör kan visa, korrigera och ta bort person uppgifter.

Microsoft Managed Desktop använder inte några person uppgifter som samlas in som en del av att tillhandahålla tjänsten för profilering, reklam och marknadsföring.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Data insamling av Microsoft Managed Desktop

När användare registrerar företags enheter på Microsoft Managed Desktop hanteras data insamling – på det tekniska lagret – med hjälp av Windows och Microsoft Intune. Dessa källor samlar in person uppgifter om användarnas enheter, till exempel enhets namn för Microsoft Managed Desktop för att identifiera vilken enhet som ska hanteras och tillhandahålls med Microsofts hanterade Skriv bords upplevelser.

Microsoft Managed Desktop samlar inte in data för sig själv för att tillhandahålla sin tjänst (med undantag för [IT-administratörers kontakt information](#it-admin-contact-information). I stället används data från Microsoft Managed Desktop som andra källor, till exempel Windows och Microsoft Intune, redan har samlat in. Microsoft Managed Desktop använder data de här tjänsterna samlar från registrerade enheter:

- Windows-diagnostikdata från enheter som hanteras av Microsoft Managed Desktop skickas till Microsofts Windows-diagnostikdata.
- Microsoft Managed Desktop använder [modern hantering](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) för att hantera registrerade enheter. Som en del av detta måste enheterna vara registrerade i klient organisationens Azure Active Directory.
- Microsoft Managed Desktop använder Microsoft Intune för att distribuera dess högoptimerade och säkra konfiguration till registrerade enheter.
- Microsoft Managed Desktop använder säkerhets information från Microsoft Defender Avancerat tråd skydd för de kunder som använder tjänsten.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Data lagring och källor på Microsoft Managed Desktop

När Microsoft Managed Desktop hämtar data måste de tillhandahålla sin tjänst, lagring och bearbetning av dessa data på följande sätt:

### <a name="storing-data-storage-location-and-data-retention"></a>Lagra data, lagrings plats och datakvarhållning

Microsoft Managed Desktop lagrar data i en eller flera av följande Microsoft-lagrings tjänster:

- Azure SQL
- Azure-lagring

Microsoft Managed Desktop lagrar data i USA. Person uppgifter behålls av Microsoft Managed Desktop i högst 30 dagar.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Data användning för Microsoft Managed Desktop

Microsoft Managed Desktop använder följande data:


| Data källor |Använda med Microsoft Managed Desktop  |
|---------|---------|
|Azure Active Directory-data     | Används i rapporter som har skapats för klient organisationer, vilka är tillgängliga på administrations portalen för Microsoft Managed Desktop.        |
|Intune-data     | Används i rapporter som har skapats för klient organisationer, vilka är tillgängliga på administrations portalen för Microsoft Managed Desktop.        |
|Microsoft Defender Avancerat skydd (ATP)     |  Används för adressering av säkerhetshoten som upptäckts på registrerade enheter av Microsoft Managed Desktops säkerhets åtgärds Center (SOC).  |
|Windows-diagnostikdata     |Används för att fastställa uppdaterings status för hanterade enheter samt för att tillhandahålla och förbättra Microsoft Managed Desktop-tjänsten IT-as-service (ITaaS).         |
|Administratörs kontakt data     | Används av Microsoft Managed Desktop för att kommunicera med klient organisationer.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Enheter som hanteras av Microsoft Managed Desktop

Microsoft Managed Desktop bearbetar dessa enheter för att tillhandahålla tjänsten:

- Enhets data
- Säkerhets inställningar för enhet
- Enhetens operativ system och maskin vara
- Aggregerad information om enhets hälsa
- Diagnostisk information om enheter
- Klient organisations data
- Azure Active Directory-resurser
- Princip-och konfigurations data
- Microsoft Defender ATP-metadata
- Windows-diagnostikdata
- Användnings data för produkt och tjänst

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Identitets data som används av Microsoft Managed Desktop lagras av Azure Active Directory på en geografisk plats baserat på den adress som tillhandahålls av organisationen när du prenumererar på en Microsoft Online-tjänst, till exempel Office 365 eller Azure. Se [Microsoft Azure – var finns mina kund data?](http://azuredatacentermap.azurewebsites.net/) för en karta som visar data centers för Azure Active Directory.

Mer information om regionerna Azure använder för data lagring finns i [Azure Active Directory – var finns dina data](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9).

### <a name="microsoft-intune"></a>Microsoft Intune

Intune-data kan lagras i några olika regioner, till exempel Europe Nord (Irland) och Europe West (Nederländerna). Din IT-administratör skapar ett klient konto och väljer det land där data ska lagras när de ursprungligen registrerar i Intune-tjänsterna. En lista med data Center-platser som används av Intune finns i [Microsoft Intune – var finns mina kund uppgifter?](http://intunedatacentermap.azurewebsites.net/). Mer information om data lagring och användning av Intune finns i [data insamling i Intune](https://docs.microsoft.com/intune/privacy-data-collect).

### <a name="microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Avancerat skydd

Microsoft Defender data för avancerat skydd (ATP) kan lagras i några olika regioner. Av den här anledningen fungerar Microsoft Defender ATP i Microsoft Azure-datacenters i Europeiska unionen, Storbritannien och USA, enligt vad som anges i [Microsoft Defender ATP – data lagrings platser](http://intunedatacentermap.azurewebsites.net/). Om du vill ha mer information om data lagring och användning av Microsoft Defender ATP kan du läsa [vilka data som har Microsoft Defender ATP?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Som angivits i [Microsofts integritets policy](https://privacy.microsoft.com/privacystatement)kan "person uppgifter som samlas in av Microsoft, lagras och bearbetas i din region, i USA och i alla andra länder där Microsoft eller dess dotter bolag, dotter bolag och tjänste leverantörer har lokaler. [...] Vanligt vis är den primära lagrings platsen i kundens region eller i USA, ofta med en säkerhets kopia till ett Data Center i en annan region. Lagrings plats (er) väljs för att fungera effektivt, för att förbättra prestanda och för att skapa redundanser för att skydda informationen om det uppstår avbrott eller andra problem. Vi vidtar åtgärder för att säkerställa att de uppgifter som vi samlar in under denna integritets policy behandlas enligt bestämmelserna i den här policyn och kraven i tillämplig lag var de finns. "

Mer information om diagnostikdata för Windows 10 finns i avsnittet ["där vi lagrar och bearbetar person uppgifter"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) i Microsofts sekretess policy.

## <a name="data-access-protection"></a>Data åtkomst skydd

Direkt åtkomst till Microsoft Managed Desktop ' s interna data lager är begränsat på flera olika sätt:

- Det kräver att du har ett godkännande på leadnivå.
- Både granskas och tidsbegränsade.
- Den kräver en lättillgänglig och begränsad arbets Station.
- Alla data är krypterade när den lagras.
- Det finns ingen ständig åtkomst.
- Åtkomst till Microsoft Managed Desktop ' s interna hanterings Portal kräver en starkt säker och begränsad arbets Station.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Bearbeta person uppgifter på ett kompatibelt sätt
Microsoft Managed Desktop bearbetar person uppgifter med ISO-certifierade system. Mer information finns i [överensstämmelse](../intro/compliance.md).

## <a name="profiling-and-marketing"></a>Profilering och marknadsföring

Microsoft Managed Desktop använder inte några person uppgifter som samlas in som en del av att tillhandahålla tjänsten för profilering, reklam och marknadsföring.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Data subjekt begär Anden för GDPR och CCPA

Europeiska unionens [allmänna data skydds förordning (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) ger rättigheter till personer (kända i förordningen som dataämnen) för att hantera de person uppgifter som har samlats av en arbetsgivare eller annan typ av agentur eller organisation (kallas datakontrollanten eller bara kontrollanten). Person uppgifter definieras väldigt brett under GDPR som alla data som är hänförliga till en identifierad eller identifierbar fysisk person. GDPR ger data som har särskilda rättigheter till person uppgifter; dessa rättigheter inkluderar att få kopior av person uppgifter och att begära korrigeringar av den, begränsa behandlingen av den, ta bort eller ta emot den i elektroniskt format så att den kan flyttas till en annan enhet. En formell begäran från en person som lyder under en kontrollant för att utföra en åtgärd på sina personliga uppgifter kallas för en begäran om data ämne eller DSR.

På samma sätt tillhandahåller California konsument integritets policyn för CCPA integritets rättigheter och skyldigheter till California-konsumenter, inklusive rättigheter som till exempel GDPRs rättigheter, såsom rätten att ta bort, komma åt och ta emot (portabilitet) sina person uppgifter. CCPA ger också till gång till vissa upplysningar, skydd mot diskriminering när det gäller att välja rättigheter och "opt-out" för vissa data transfereringar klassificerade som "försäljning". Försäljningen definieras brett för att omfatta delar av data för en värdefull räkning. Mer information om CCPA finns på [vanliga frågor och svar](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide)om sekretess [policy](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide) för användare av Kalifornien.

I följande avsnitt beskrivs hur Microsoft Managed Desktop hjälper styrenheterna att hitta, komma åt och agera med person uppgifter eller personlig information som används av Microsoft Managed Desktop.

> [!NOTE]
> Om du letar efter allmän information om GDPR kan du läsa [avsnittet GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) i service Trust Portal.

### <a name="it-admin-contact-information"></a>Kontakt information för IT-administratörer

En klient organisation kan visa, korrigera och ta bort sina egna person uppgifter (till exempel sin egen kontakt information) direkt i avsnittet administratörs kontakt på Microsoft Managed Desktop-portalen.

### <a name="user-related-personal-data"></a>Användar information

Bortsett från detta samlar Microsoft Managed Desktop inte in personlig information. I stället används person uppgifter som andra Microsoft Enterprise online-tjänster samlat in. IT-administratörer som vill svara på sina användar förfrågningar för att visa, korrigera och ta bort sina person uppgifter kan använda de respektive funktionerna för underliggande tjänster som Microsoft hanterar Skriv bordet beror på. Om du är intresse rad av att visa eller ta bort person uppgifter som används av de här tjänsterna kan du läsa den [GDPR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) artikeln först.

Använd dessutom följande vägledning för att använda DSRs för tjänsterna som hanteras av Microsoft, beror på insamling av person uppgifter:

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender Avancerat skydd](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
