---
title: Beredskapsutvärderingsverktyg
description: Förklarar de två verktygen, kontrollerna de körs och vad resultatet betyder
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 9fbd24185288265d698288e0d5e63e8b3c2afd10
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921852"
---
# <a name="readiness-assessment-tools"></a>Beredskapsutvärderingsverktyg

För att upplevelsen ska bli så smidig som möjligt när du registrerar dig för Microsoft Managed Desktop finns det inställningar och andra parametrar som du måste ange i förväg och vissa enhets- och nätverkskrav för att uppfyllas. Ett verktyg, som används via Microsoft Managed Desktop Admin-portalen, kontrollerar hanteringsrelaterade inställningar. Ett annat verktyg, som kan laddas ned, kontrollerar enskilda enhetskrav och nätverksinställningar. Du kan använda dessa verktyg för att kontrollera dessa inställningar och få detaljerade anvisningar för att åtgärda fel som inte är rätt.

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>Nedladdningsbar beredskapsbedömning för enheter och nätverk

Mer information om hur du använder den nedladdningsbara beredskapsutvärderingskontrollen finns i [hämtningsberedskapsutvärderingskontrollen.](readiness-assessment-downloadable.md)

## <a name="online-readiness-assessment-tool-for-management-settings"></a>Utvärderingsverktyg för onlineberedskap för hanteringsinställningar

Onlineverktyget kontrollerar inställningarna i Microsoft Endpoint Manager (specifikt Microsoft Intune), Azure Active Directory (Azure AD) och Microsoft 365 för att säkerställa att de fungerar med Microsoft Managed Desktop. Microsoft Hanterat skrivbord behåller de data som är associerade med dessa kontroller i 12 månader efter den senaste kontrollen i Din Azure AD-organisation (klientorganisation). Efter 12 månader behåller vi den i avde identifierat format. Du kan välja att ta bort de data vi samlar in.

Alla som har minst rollen Intune-administratör kan köra det här[](readiness-assessment-fix.md#conditional-access-policies) verktyget, men två av kontrollerna (villkorsstyrda åtkomstprinciper och multifaktorautentisering kräver ytterligare behörigheter. [](readiness-assessment-fix.md#multifactor-authentication)
 
Utvärderingsverktyget kontrollerar följande objekt:

## <a name="microsoft-intune-settings"></a>Microsoft Intune-inställningar

|Check  |Beskrivning  |
|---------|---------|
|Distributionsprofil för Autopilot     | Verifierar att tilldelning av Autopilot-distributionsprofilen inte gäller  för alla enheter (Profilen ska inte tilldelas till några Microsoft Managed Desktop-enheter.)       |
|Certifikatkopplingar     | Kontrollerar statusen för certifikatanslutningar för att säkerställa att de är aktiva   |
|Villkorlig åtkomst     | Verifierar att villkorsstyrda åtkomstprinciper inte har tilldelats till alla användare (villkorsstyrda åtkomstprinciper *bör* inte tilldelas Microsofts tjänstkonton för hanterad skrivbordsversionen.)    |
|Policyer för enhetsefterlevnad     | Kontrollerar att Intune-efterlevnadsprinciper inte har tilldelats till alla användare (principerna *bör* inte tilldelas några Microsoft Managed Desktop-enheter.)    |
|Enhetskonfigurationsprofiler     | Bekräftar att konfigurationsprofiler inte är tilldelade till alla  användare eller alla enheter (konfigurationsprofiler bör inte tilldelas några Microsoft Managed Desktop-enheter.)     |
|Begränsningar av enhetstyp     | Kontrollerar att Windows 10-enheter i organisationen tillåts registrera i Intune        |
|Statussida för registrering     | Bekräftar att statussidan för registrering inte är aktiverad      |
|Intune-registrering     | Verifierar att Windows 10-enheter i din Azure AD-organisation automatiskt registreras i Intune         |
|Microsoft Store för företag     | Bekräftar att Microsoft Store för företag är aktiverat och synkroniserat med Intune        |
|Multifaktorautentisering | Verifierar att multifaktorautentisering inte tillämpas på Microsoft-konton för hanterad skrivbordstjänst.
|PowerShell-skript     | Kontrollerar att Windows PowerShell-skript inte *har tilldelats* på ett sätt som riktar sig till Microsoft Managed Desktop-enheter    |
|Region     | Kontrollerar att din region stöds av Microsoft Managed Desktop        |
|Säkerhetsbaslinjer     | Kontrollerar att säkerhetsbaslinjeprofilen inte riktar sig till alla  användare eller alla enheter (principer för säkerhetsbaslinjer ska inte ha några Microsoft Managed Desktop-enheter som mål.)       |
|Windows-appar     | Kontrollera vilka appar du vill tilldela Microsoft Managed Desktop-enheter      |
|Windows Hello för företag     | Kontrollerar att Windows Hello för företag är aktiverat        |
|Uppdateringsringen i Windows 10     | Kontrollerar att Intunes princip för windows 10-uppdateringsringen inte riktar sig  till alla användare eller alla enheter (principen ska inte ha några Microsoft Managed Desktop-enheter som mål.)     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory-inställningar

|Check  |Beskrivning  |
|---------|---------|
|Ad hoc-abonnemang för Enterprise State Roaming     | Information om hur du kontrollerar en inställning som (om inställningen är "falskt") kan förhindra att Företagstillståndsroaming fungerar korrekt  |
|Enterprise State Roaming     | Information om hur du kontrollerar att Företagsroaming är aktiverat       |
|Licenser     | Kontrollerar att du har skaffat nödvändiga [licenser](prerequisites.md#more-about-licenses)         |
|Multifaktorautentisering     | Kontrollerar att multifaktorautentisering inte tillämpas på alla användare (Multifaktorautentisering får inte av misstag tillämpas på Microsofts tjänstkonton för hanterad stationär dator.)|
|Namn på säkerhetskonto   | Kontrollerar att inga användarnamn står i konflikt med sådana som Microsoft Hanterat skrivbord reserverar för eget bruk        |
|Säkerhetsadministratörsroller     | Bekräftar att användare med roller som Säkerhetsläsare, Säkerhetsoperator eller Global Läsare har tilldelats dessa roller i Microsoft Defender för slutpunkt         |
|Standardinställningar för säkerhet | Kontrollerar om Azure AD-organisationen har aktiverat säkerhetsstandarder i Azure Active Directory |
|Självbetjäning för återställning av lösenord     | Bekräftar att självbetjäning för återställning av lösenord är aktiverat        |
|Standardanvändarroll     | Verifierar att användare är standardanvändare och inte har lokala administratörsrättigheter         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365-program för företagsinställningar

|Check  |Beskrivning  |
|---------|---------|
|OneDrive för företag     | Kontrollerar om OneDrive för företag använder inställningar som inte stöds.        |


För varje kontroll rapporterar verktyget ett av fyra möjliga resultat:


|Resultat  |Betydelse  |
|---------|---------|
|Klar     | Ingen åtgärd krävs innan du slutför registreringen.        |
|Rådgivning    | Följ stegen i verktyget för att få den bästa upplevelsen med registrering och för användare. Du *kan* slutföra registreringen, men du måste åtgärda problemen innan du distribuerar din första enhet.        |
|Inte klar | *Registrering misslyckas om* du inte åtgärdar dessa problem. Följ stegen i verktyget för att lösa dem.        |
|Fel | Azure Active Director-rollen (AD) som du använder har inte tillräcklig behörighet för att köra den här kontrollen. |

## <a name="after-enrollment"></a>Efter registrering

När du har slutfört registreringen i Microsoft Managed Desktop ska du komma ihåg att gå tillbaka och justera vissa Intune- och Azure AD-inställningar. Mer information finns i [Justera inställningar efter registrering.](../get-started/conditional-access.md)
