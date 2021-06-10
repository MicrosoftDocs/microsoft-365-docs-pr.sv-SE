---
title: Bedömningsverktyg för beredskap
description: Förklarar de två verktygen, kontrollerna de kör och vad resultatet betyder
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: caf9274284548a179e088131930ae832c098b521
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579404"
---
# <a name="readiness-assessment-tools"></a>Bedömningsverktyg för beredskap

För att upplevelsen ska gå så smidigt som möjligt när du registrerar dig i Microsoft Hanterat skrivbord finns det inställningar och andra parametrar som du måste ange i förväg, och vissa enhets- och nätverkskrav för att uppfylla. Ett verktyg, som du öppnar Microsoft Hanterat skrivbord administrationsportalen, kontrollerar hanteringsrelaterade inställningar. Ett annat verktyg, som kan laddas ned, kontrollerar enskilda enhetskrav och nätverksinställningar. Du kan använda de här verktygen för att kontrollera inställningarna och få detaljerade anvisningar för hur du åtgärdar fel personer som inte är rätt.

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>Hämtningsbar bedömningskontrollen för enheter och nätverk

Mer information om hur du använder den nedladdningsbara beredskapsutvärderingskontrollen finns i [Hämtningsbar beredskapsutvärderingskontroll.](readiness-assessment-downloadable.md)

## <a name="online-readiness-assessment-tool-for-management-settings"></a>Utvärderingsverktyg för onlineberedskap för hanteringsinställningar

Onlineverktyget [kontrollerar](https://aka.ms/mmdart) inställningarna i Microsoft Endpoint Manager (särskilt Microsoft Intune), Azure Active Directory (Azure AD) och Microsoft 365 för att säkerställa att de fungerar med Microsoft Hanterat skrivbord. Microsoft Hanterat skrivbord behåller data som är associerade med dessa kontroller i 12 månader efter den senaste gången du kör en kontroll i Azure AD-organisationen (klientorganisation). Efter 12 månader behåller vi den i avde identifierat format. Du kan välja att ta bort de data vi samlar in.

Alla som har minst rollen Global Reader- eller Intune-administratör kan köra[](readiness-assessment-fix.md#conditional-access-policies) det här verktyget, men två av kontrollerna (villkorsbaserad åtkomstprincip och multifaktorautentisering kräver ytterligare behörigheter. [](readiness-assessment-fix.md#multifactor-authentication)
 
Utvärderingsverktyget kontrollerar följande objekt:

## <a name="microsoft-intune-settings"></a>Microsoft Intune inställningar

|Check  |Beskrivning  |
|---------|---------|
|Distributionsprofil för Autopilot     | Verifierar att tilldelning av Autopilot-distributionsprofilen inte gäller för alla enheter (profilen ska *inte* tilldelas till några Microsoft Hanterat skrivbord enheter.)       |
|Certifikatkopplingar     | Kontrollerar statusen för certifikatkopplingar för att säkerställa att de är aktiva   |
|Villkorlig åtkomst     | Verifierar att villkorsstyrda åtkomstprinciper inte har  tilldelats alla användare (villkorsstyrda åtkomstprinciper bör inte Microsoft Hanterat skrivbord till tjänstkonton.)    |
|Policyer för enhetsefterlevnad     | Kontrollerar att Intune-efterlevnadsprinciper inte tilldelas till alla användare (Principerna bör *inte* tilldelas till några Microsoft Hanterat skrivbord enheter.)    |
|Profiler för enhetskonfiguration     | Bekräftar att konfigurationsprofiler inte är tilldelade till alla  användare eller alla enheter (konfigurationsprofiler bör inte tilldelas till Microsoft Hanterat skrivbord enheter.)     |
|Begränsningar för enhetstyp     | Kontrollerar att Windows 10 enheter i organisationen tillåts registrera i Intune        |
|Statussida för registrering     | Bekräftar att registreringsstatussidan inte är aktiverad      |
|Intune-registrering     | Verifierar att Windows 10 enheter i din Azure AD-organisation automatiskt är registrerade i Intune         |
|Microsoft Store för företag     | Bekräftar att Microsoft Store för företag är aktiverat och synkroniserat med Intune        |
|Multifaktorautentisering | Verifierar att multifaktorautentisering inte tillämpas på Microsoft Hanterat skrivbord-tjänstkonton.
|PowerShell-skript     | Kontrollerar att Windows PowerShell skript inte *har tilldelats* på ett sätt som riktar Microsoft Hanterat skrivbord enheter    |
|Region     | Kontrollerar att din region stöds av Microsoft Hanterat skrivbord        |
|Säkerhetsbaslinjer     | Kontrollerar att säkerhetsbaslinjeprofilen inte riktar sig till alla användare eller alla enheter (principer för säkerhetsbaslinje *bör inte* ha några Microsoft Hanterat skrivbord enheter.)       |
|Windows appar     | Kontrollera vilka appar du vill tilldela till Microsoft Hanterat skrivbord enheter      |
|Windows Hello för företag     | Kontrollerar att Windows Hello för företag är aktiverat        |
|Windows 10 uppdateringsringen     | Kontrollerar att Intunes princip för Windows 10-uppdateringsringen inte riktar sig till alla  användare eller alla enheter (principen ska inte ha som mål Microsoft Hanterat skrivbord enheter.)     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory inställningar

|Check  |Beskrivning  |
|---------|---------|
|"Ad hoc"-abonnemang för Enterprise State Roaming     | Ger information om hur du kontrollerar en inställning som (om denna är inställd på "falskt") kan hindra Enterprise State Roaming från att fungera korrekt  |
|Enterprise State Roaming     | Råd om hur du kontrollerar att Roaming i företagstillstånd är aktiverat       |
|Licenser     | Kontrollerar att du har fått nödvändiga [licenser](prerequisites.md#more-about-licenses)         |
|Multifaktorautentisering     | Kontrollerar att multifaktorautentisering inte tillämpas på alla användare (Multifaktorautentisering får inte tillämpas av misstag Microsoft Hanterat skrivbord-tjänstkonton.)|
|Namn på säkerhetskonto   | Kontrollerar att inga användarnamn står i konflikt med Microsoft Hanterat skrivbord reserveras för eget bruk        |
|Säkerhetsadministratörsroller     | Bekräftar att användare med roller som säkerhetsläsare, säkerhetsoperator eller global läsare har tilldelats dessa roller i Microsoft Defender för slutpunkt         |
|Standardinställningar för säkerhet | Kontrollerar om Azure AD-organisationen har aktiverat säkerhetsstandarder i Azure Active Directory |
|Självbetjäning för återställning av lösenord     | Bekräftar att självbetjäning för återställning av lösenord är aktiverat        |
|Standardanvändarroll     | Verifierar att användare är standardanvändare och inte har lokala administratörsrättigheter         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365-appar för företag inställningar

|Check  |Beskrivning  |
|---------|---------|
|OneDrive för företag     | Kontrollerar om OneDrive för företag använder inställningar som inte stöds.        |


För varje kontroll rapporterar verktyget ett av fyra möjliga resultat:


|Resultat  |Betydelse  |
|---------|---------|
|Klar     | Ingen åtgärd krävs innan du slutför registreringen.        |
|Rådgivning    | Följ stegen i verktyget för att få den bästa upplevelsen med registrering och för användare. Du *kan* slutföra registreringen, men du måste åtgärda de här problemen innan du distribuerar din första enhet.        |
|Inte klar | *Registrering kommer att* misslyckas om du inte åtgärdar dessa problem. Följ stegen i verktyget för att lösa dem.        |
|Fel | Azure Active Director-rollen (AD) som du använder har inte tillräcklig behörighet för att köra den här kontrollen. |

## <a name="after-enrollment"></a>Efter registrering

När du har slutfört registreringen i Microsoft Hanterat skrivbord ska du komma ihåg att gå tillbaka och justera vissa Intune- och Azure AD-inställningar. Mer information finns i [Justera inställningar efter registrering.](../get-started/conditional-access.md)

## <a name="steps-to-get-ready"></a>Steg för att förbereda dig

1. Läs [Förutsättningar för Microsoft Hanterat skrivbord](prerequisites.md).
2. Använd [verktygen för beredskapsbedömning](readiness-assessment-tool.md). (Den här artikeln)
3. [Förutsättningar för gästkonton](guest-accounts.md)
4. [Nätverkskonfiguration för Microsoft Hanterat skrivbord](network.md)
5. [Förbereda certifikat och nätverksprofiler för Microsoft Hanterat skrivbord](certs-wifi-lan.md)
6. [Förbereda åtkomst till lokala resurser för Microsoft Hanterat skrivbord](authentication.md)
7. [Appar i Microsoft Hanterat skrivbord](apps.md)
8. [Förbereda mappade enheter för Microsoft Hanterat skrivbord](mapped-drives.md)
9. [Förbereda utskriftsresurser för Microsoft Hanterat skrivbord](printing.md)
