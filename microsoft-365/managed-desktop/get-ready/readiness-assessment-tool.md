---
title: Verktyg för bedömning av beredskap
description: Förklarar vilka kontroller verktyget kör och innebörden av resultatet
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 347266f71dada3de1bbd9b1434cb1e6628249147
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931930"
---
# <a name="readiness-assessment-tool"></a>Verktyg för bedömning av beredskap

För att du ska få den bästa möjliga upplevelsen när du registrerar dig på Microsoft Managed Desktop finns det ett antal inställningar och andra parametrar som du måste ange i förväg. Du kan använda det här verktyget för att kontrol lera dessa inställningar och få detaljerade anvisningar för att åtgärda något som inte är rätt.

Verktyget kontrollerar inställningar i Microsoft slut punkts hanteraren (specifikt, Microsoft Intune), Azure Active Directory (Azure AD) och Microsoft 365 för att säkerställa att de fungerar med Microsoft Managed Desktop. Microsoft Managed Desktop behåller de data som är kopplade till dessa kontroller i 12 månader efter den senaste gången du kör en check i din Azure AD-organisation (klient organisationen). Efter 12 månader behåller vi det i det format som identifieras.  Du kan välja att ta bort de data som samlas in.

Alla som har minst rollen Intune-administratör kan köra det här verktyget, men två av kontrollerna ([certifikat kopplingar](readiness-assessment-fix.md#certificate-connectors) och [multifaktorautentisering](readiness-assessment-fix.md#multi-factor-authentication) kräver ytterligare behörigheter.
 
Utvärderings verktyget kontrollerar följande objekt:

## <a name="microsoft-intune-settings"></a>Microsoft Intune-inställningar

|Check  |Beskrivning  |
|---------|---------|
|Distributions profil för autopilot     | Verifiera att tilldelningen av profilen för autopilot-distribution inte gäller för alla enheter (profilen ska *inte* kopplas till någon hanterad Microsoft-enhet.)       |
|Certifikat anslutningar     | Kontrollerar statusen för certifikat anslutningar för att säkerställa att de är aktiva   |
|Villkorlig åtkomst     | Verifiera att principer för villkorlig åtkomst inte är tilldelade till alla användare (principer för villkorlig åtkomst ska *inte* tilldelas till Microsoft Managed Desktop Service-konton.)    |
|Principer för enhetskompatibilitet     | Kontrollerar att Intune-efterlevnadsprinciper inte är tilldelade till alla användare (policyn ska *inte* tilldelas till Microsoft Managed Station ära datorer).    |
|Profil profiler för enheter     | Bekräftar att konfigurations profilerna inte är tilldelade till alla användare eller alla enheter (konfigurations profiler ska *inte* tilldelas till Microsoft Managed Station ära datorer.)     |
|Begränsningar för enhets typer     | Kontrollerar att Windows 10-enheter i din organisation tillåts registrera i Intune        |
|Sidan registrerings status     | Bekräftar att registrerings status sidan inte är aktive rad      |
|Intune-registrering     | Verifierar att Windows 10-enheter i din Azure AD-organisation registreras automatiskt i Intune         |
|Microsoft Store för företag     | Bekräftar att Microsoft Store för företag är aktiverat och synkroniserat med Intune        |
|Multifaktorautentisering | Verifierar att multifaktorautentisering inte tillämpas på Microsoft Managed Desktop Service-konton.
|PowerShell-skript     | Kontrollerar att Windows PowerShell-skript *inte* är tilldelade på ett sätt som kan hantera Microsoft Managed Station ära enheter    |
|Region     | Kontrollerar att din region stöds av Microsoft Managed Desktop        |
|Säkerhets bas linjer     | Kontrollerar att säkerhets bas profilen inte uppfyller alla användare eller alla enheter (principer för säkerhets bas linje ska *inte* vara riktad till Microsoft Managed Station ära datorer).       |
|Windows-appar     | Granska vilka appar du vill tilldela Microsoft-hanterade Station ära enheter      |
|Windows Hello för företag     | Kontrollerar att Windows Hello för företag är aktiverat        |
|Windows 10-uppdatera ring     | Kontrollerar att Intune-principen "Windows 10 Update ring" inte riktar sig till alla användare eller alla enheter (principen ska *inte* vara riktad till Microsoft Managed Station ära enheter).     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory-inställningar

|Check  |Beskrivning  |
|---------|---------|
|"Ad hoc"-abonnemang för företags status-roaming     | Här förklaras hur du kontrollerar en inställning som (om värdet är "falskt") kan hindra företags tillstånd från att fungera korrekt  |
|Enterprise State Roaming     | Här får du information om hur du kontrollerar att nätverks tillstånd är aktiverat       |
|Licenser     | Kontrollerar att du har skaffat de [licenser](prerequisites.md#more-about-licenses) du behöver         |
|Multifaktorautentisering     | Kontrollerar att multifaktorautentisering inte används för alla användare (multifaktorautentisering får inte oavsiktligt användas på Microsoft Managed Desktop Service-konton.)|
|Namn på säkerhets konton   | Kontrollerar att inga användar namn är i konflikt med att Microsoft Managed Desktop reserver för eget bruk        |
|Säkerhets administratörs roller     | Bekräftar att användare med rollen säkerhets läsare, säkerhets ansvarig eller global läsare har tilldelats roller i Microsoft Defender för slut punkten         |
|Standardinställningar för säkerhet | Kontrollerar om din Azure AD-organisation har säkerhets standarder aktiverade i Azure Active Directory |
|Självbetjäning för återställning av lösenord     | Bekräftar att automatisk återställning av lösen ord är aktiverat        |
|Standard användar roll     | Verifierar att användare är standard användare och inte har lokal administratörs behörighet         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365-appar för företags inställningar

|Check  |Beskrivning  |
|---------|---------|
|OneDrive för företag     | Kontrollerar om OneDrive för företag använder inställningar som inte stöds.        |


För varje kontroll rapporteras ett av fyra möjliga resultat:


|Resultat  |Betydelse  |
|---------|---------|
|Förbereder     | Ingen åtgärd krävs innan du slutför registreringen.        |
|Rådgivare    | Följ stegen i verktyget för att få den bästa upplevelsen med registrering och för användare. Du *kan* slutföra registreringen, men du måste åtgärda dessa problem innan du distribuerar den första enheten.        |
|Inte klart | *Registreringen Miss lyckas* om du inte åtgärdar dessa problem. Följ stegen i verktyget för att åtgärda dem.        |
|Fel | Azure Active Director (AD)-rollen som du använder har inte tillräcklig behörighet för att köra den här kontrollen. |
