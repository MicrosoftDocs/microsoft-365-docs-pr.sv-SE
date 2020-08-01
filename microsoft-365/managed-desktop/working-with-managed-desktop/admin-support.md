---
title: Admin-support för Microsoft Hanterat skrivbord
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a29fa11e43e9be5c8175118ad5b54817c463e929
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529905"
---
# <a name="admin-support-for-microsoft-managed-desktop"></a>Admin-support för Microsoft Hanterat skrivbord

Du kan skicka supportärenden eller feedbackförfrågningar till Microsoft med hjälp av Microsoft Managed Desktop Administrative Portal. Supportbegäranden prioriteras alltid framför feedbacköverföringar. Supportbegäranden triaged och hanteras efter allvarlighetsgrad enligt beskrivningen i [tabellen allvarlighetsgrad definition](#sev). Feedback granskas och ett svar ges där så önskas. 

>[!IMPORTANT]
>Se till att du [konfigurerar en administratörskontakt](../get-started/add-admin-contacts.md) för appförpackningar, enheter, säkerhet och annat. Du kan inte skicka en supportbegäran i något av dessa områden om en administratörskontakt inte är konfigurerad.

**Så här skickar du en supportbegäran**
1. Logga in på [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal). 
2. På **Supportförfrågningar**väljer du **+ Ny supportbiljett**.
3. Välj den **typ av supportbegäran** som matchar den hjälp du behöver. I tabellen nedan beskrivs alternativen. 
4. Välj **allvarlighetsgrad**. Mer information finns i [Allvarlighetsgraddefinitioner för supportbegäran](#sev). 

Typ av supportbegäran | När ska du använda
--- | ---
Incident | Du kräver att Microsoft Managed Desktop Operations Team undersöker, till exempel omfattande effekter av en ändring eller säkerhetsincident.
Begäran om information | Du planerar en ändring för nätverk, proxykonfiguration, VPN-system, certifikatets förfallodatum eller behöver bara lite information om tjänsten. Ett svar från Microsoft Managed Desktop Operations Team rekommenderas starkt när du kommunicerar en ändring inom organisationen.
Ändra begäran | Du måste göra en ändring av Microsoft Managed Desktop Operations Team, till exempel flytta enheter mellan uppdateringsgrupper.

<span id="sev" />

## <a name="support-request-severity-definitions"></a>Allvarlighetsgraddefinitioner för supportbegäran

Inledande svarstid är den period från den tidpunkt då du skickar din supportbegäran till när en Microsoft Managed Desktop-tekniker kontaktar dig och börjar arbeta med din supportbegäran. Den första svarstiden varierar med begärans inverkan på verksamheten, baserat på begärans allvarlighetsgrad.

Allvarlighetsnivå  | Kundens situation |  Inledande svarstid   | Förväntat kundsvar
--- | --- | --- | ---
**Allvarlighetsgrad A – Kritisk påverkan** |  **Kritisk inverkan på verksamheten**<br><br>Kundens verksamhet har betydande förlust eller försämring av tjänster och kräver omedelbar uppmärksamhet.<br><br>**Större inverkan på programkompatibilitet**<br><br>Kundens hela verksamhet har ekonomiska konsekvenser på grund av kraschning eller förlust av kritisk funktionalitet | Initial: < 1 timme<br>Uppdatering: 60 minuter<br>24x7 tillgänglig | När du väljer Allvarlighetsgrad A bekräftar du att problemet har en kritisk inverkan på verksamheten, med allvarlig förlust och försämring av tjänster. <br><br>Problemet kräver ett omedelbart svar, och du åtar dig att kontinuerlig 24x7-drift varje dag med Microsoft-teamet fram till lösning, annars kan Microsoft efter eget gottfinnande minska allvarlighetsgraden till nivå B.<br><br> Du ser också till att Microsoft har korrekt kontaktinformation. 
**Allvarlighetsgrad B – Måttlig effekt** |  **Måttlig inverkan på verksamheten**<br><br>Kundens verksamhet har måttlig förlust eller försämring av tjänster, men arbetet kan rimligen fortsätta på ett försämrat sätt.<br><br>**Måttlig påverkan på programkompatibilitet**<br><br>En viss affärsgrupp är inte längre produktiv på grund av kraschbeteende eller förlust av kritiska funktioner. |  Initial: < 4 timmar<br>Uppdatering: 12 timmar<br>Öppettider (24x7 tillgänglig) | När du väljer Allvarlighetsgrad B bekräftar du att problemet har måttlig inverkan på din verksamhet med förlust och försämring av tjänster, men lösningar möjliggör rimlig, om än tillfällig, affärskontinuitet. <br><br>Frågan kräver ett brådskande svar. Om du väljer 24x7 när du skickar supportbegäran åtar du dig en kontinuerlig 24x7-åtgärd varje dag med Microsoft-teamet fram till upplösningen, annars kan Microsoft efter eget gottfinnande minska allvarlighetsgraden till nivå C. Om du väljer support för kontorstid när du skickar in en allvarlighetsgrad B-incident kontaktar Microsoft dig endast under kontorstid.<br><br>Du ser också till att Microsoft har korrekt kontaktinformation.
**Allvarlighetsgrad C – Minimal påverkan** |   **Minsta påverkan på verksamheten**<br><br> Kundens verksamhet fungerar med mindre hinder för tjänster.<br><br>**Mindre påverkan på programkompatibilitet**<br><br>Potentiellt orelaterade användare upplever mindre kompatibilitetsproblem som inte förhindrar produktivitet |    Initial: < 8 timmar<br>Uppdatering: 24 timmar<br>Öppettider  | När du väljer Allvarlighetsgrad C bekräftar du att problemet har minimal påverkan på ditt företag med mindre hinder för tjänsten.<br><br>För en allvarlighetsgrad C-incident kontaktar Microsoft dig endast under kontorstid.<br><br>Du ser också till att Microsoft har din korrekta kontaktinformation

Ytterligare information:
- **Stödspråk** - All support ges på engelska.
- **Ändringar på allvarlighetsgrad** – Microsoft kan nedgradera allvarlighetsgraden om kunden inte kan tillhandahålla tillräckliga resurser eller svar så att Microsoft kan fortsätta med problemlösningsarbetet. 
- **Öppettider** - För de flesta länder är öppettiderna från 09:00 till 17:00, Pacific Standard Time.
- **Programkompatibilitet** - För att ett programkompatibilitetsproblem ska kunna beaktas måste det finnas ett reproducerbart fel, av samma version av programmet, mellan den tidigare och den aktuella versionen av Windows eller Office. För att lösa problem med programkompatibiliteten kräver Microsoft en kundkontaktpunkt att arbeta med. Individen måste arbeta direkt med vårt Fast Track-team för att undersöka och lösa problemet.
- **Kundens svarstid** Om en kund inte kan uppfylla de förväntade svarskraven nedgraderar Microsoft begäran med en allvarlighetsgrad till ett minimum av allvarlighetsgrad C. Om en kund inte svarar på begäran om åtgärder kommer Microsoft att minska och stänga supportbegäran inom 48 timmar efter den senaste begäran.

## <a name="provide-feedback"></a>Ge feedback

Vi uppskattar din feedback och använder den för att förbättra administratörssupportupplevelsen.

När en biljett är i **reducerade** eller **löst tillstånd** kan du dela din feedback på din upplevelse med just det problemet. Det gör du genom att gå till sidan **Supportbegäranden** i administratörsportalen. Välj den specifika biljetten. I förbiflygningen som visas på höger sida väljer du fliken **Feedback** och anger den begärda informationen. Var noga med att inte inkludera någon personlig information i feedbackformuläret. Mer information om sekretess finns i [Microsofts sekretesspolicy](https://privacy.microsoft.com/privacystatement).

![Formulär för feedback](../../media/feedback_form.png)



## <a name="additional-resources"></a>Ytterligare resurser
- [Stöd för slutanvändare för Microsoft Managed Desktop](end-user-support.md). 
- [Stöd för Microsoft Managed Desktop](../service-description/support.md). 
- Om du redan prenumererar på Microsoft Managed Desktop kan du hitta detaljerade procedurer, processflöden, arbetsinstruktioner och vanliga frågor i administratörshandboken för Microsoft Managed Desktop i avsnittet **Onlineresurser** i [Microsoft Managed Desktop Admin Portal](https://aka.ms/mwaasportal).
