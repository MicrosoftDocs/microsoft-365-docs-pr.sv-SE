---
title: Admin-support för Microsoft Hanterat skrivbord
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 972430f5637f1160c330bed1558b79c8273171c5
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104588"
---
# <a name="admin-support-for-microsoft-managed-desktop"></a>Admin-support för Microsoft Hanterat skrivbord

Du kan skicka in support biljetter eller feedback till Microsoft via den administrativa portalen för Microsoft Managed Desktop. Supportfrågor prioriteras alltid för synpunkter från feedback. Support ärenden är triaged och hanteras enligt allvarlighets graden enligt beskrivningen i [tabellen allvarlighets grad](#sev). Feedback kontrol leras och ett svar som har begärts visas. 

>[!IMPORTANT]
>Se till att du [konfigurerar en administratörs kontakt](../get-started/add-admin-contacts.md) för programpaket, enheter, säkerhet och annan. Du kan inte skicka in en supportbegäran i något av dessa områden om en administratörs kontakt inte har kon figurer ATS.

**Så här skickar du en supportbegäran**
1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och navigera till **fel sökning + support** -menyn.
2. Leta efter avsnittet Microsoft Managed Desktop och välj **sevice Request**.
3. Välj **+ nytt support ärende**på **supportfrågor**.
4. Välj den **typ av support förfrågan** som matchar den hjälp du behöver. I tabellen nedan beskrivs alternativen. 
5. Välj **allvarlighets nivå**. Mer information finns i [support ärende – definitioner för allvarlighets grad](#sev). 

Typ av support förfrågan | När du ska använda
--- | ---
Händelse | Du måste ha Microsoft Managed Station ära datorer för att kunna undersöka, till exempel utbredd påverkan på ett ändrings-eller säkerhets tillbud.
Begäran om information | Du planerar en ändring för nätverk, proxykonfiguration, VPN-system, certifikat upphör ande eller behöver bara viss information om tjänsten. Ett svar från Microsoft Managed Desktop Operations team är starkt tillrådligt när du kommunicerar i din organisation.
Ändringsbegäran | Du måste ha Microsoft Managed Station ära datorer för att kunna göra ändringar, till exempel flytta enheter mellan uppdaterings grupper.

<span id="sev" />

## <a name="support-request-severity-definitions"></a>Support ärende definitioner för allvarlighets grad

Ursprunglig svars tid är den period från vilken du skickar in support förfrågan när en Microsoft-hanterad stationär ingenjör kontaktar dig och börjar arbeta på din support förfrågan. Den första svars tiden varierar beroende på hur mycket verksamheten har påverkats, baserat på begärans allvarlighets grad.

Allvarlighetsnivå  | Kund situation |  Ursprunglig responstid   | Förväntat kund svar
--- | --- | --- | ---
**Allvarlighets grad A – kritisk effekt** |  **Kritiskt företags påverkan**<br><br>Kundens företag har avsevärd förlust eller försämring av tjänster och kräver omedelbar uppmärksamhet.<br><br>**Stor inverkan på programkompatibilitet**<br><br>Hela företaget har ekonomisk påverkan på grund av en krasch eller förlust av kritiska funktioner | Initial: < 1 timme<br>Uppdatering: 60 minuter<br>tillgänglig dygnet runt | När du väljer allvarlighets grad bekräftar du att problemet har stor betydelse för verksamheten, med mycket förlust och försämring av tjänster. <br><br>Problemet är omedelbart uppfyllt och du åtar dig att svara kontinuerligt dygnet runt varje dag med Microsoft-teamet tills den är upplösningen, annars kan Microsoft till sin eget gottfinnande minska allvarlighets graden för nivå B.<br><br> Du ser också till att Microsoft har din korrekta kontakt information. 
**Allvarlighets grad B – måttlig påverkan** |  **Måttlig rörelse påverkan**<br><br>Kundens företag har en måttlig förlust eller försämring av tjänster, men arbetet kan rimligen kunna göras på ett syn sätt.<br><br>**Måttlig påverkan på programkompatibilitet**<br><br>En specifik företags grupp är inte längre produktiv, på grund av krasch beteende eller förlust av kritisk funktion. |  Initial: < 4 timmar<br>Uppdatera: 12 timmar<br>Kontors tid (dygnet runt) | När du väljer allvarlighets grad B bekräftar du att problemet har stor inverkan på ditt företag med förlust och försämring av tjänster, men lösningarna möjliggör rimlig, vår tillfälliga, affärs kontinuitet. <br><br>Problemet kräver ett brådskande svar. Om du valde dygnet runt när du skickar in support förfrågan, genomför du en ständig dygns åtgärd varje dag med Microsoft-teamet tills lösningen uppfylls, annars kanske Microsoft kan minska allvarlighets graden för nivå C. Om du valt support för företag när du skickar en allvarlighets grad B-incident kontaktar Microsoft dig bara under kontors tid.<br><br>Du ser också till att Microsoft har din korrekta kontakt information.
**Allvarlighets grad C – minimal påverkan** |   **Minsta rörelse påverkan**<br><br> Kundens företag fungerar med mindre hinder för tjänster.<br><br>**Mindre programkompatibilitet påverkas**<br><br>Potentiellt orelaterade användare upplever mindre kompatibilitetsproblem som inte hindrar produktivitet |    Initial: < 8 timmar<br>Uppdatera: 24 timmar<br>Kontors tid  | När du väljer allvarlighets grad C bekräftar du att problemet har minsta påverkan på verksamheten med mindre hinder för tjänsten.<br><br>För en allvarlighets grad C-olycka kontaktar Microsoft dig bara under kontors tid.<br><br>Du ser också till att Microsoft har din korrekta kontakt information

Ytterligare information:
- **Support språk** – all support tillhandahålls på engelska.
- **Ändringar på allvarlighets nivå** – Microsoft kan nedgradera allvarlighets graden om kunden inte kan tillhandahålla adekvata resurser eller svar för att Microsoft ska fortsätta med problemlösningen för problem. 
- **Kontors tid** – i de flesta länder är kontors tid det från 9:00 AM till 5:00 PM, Pacific, normal tid.
- **Programkompatibilitet** – för att få programkompatibilitetsproblem måste det finnas ett problem med program varan, med samma version av programmet, mellan den tidigare och den aktuella versionen av Windows eller Office. För att lösa problem med programkompatibilitet krävs en kund kontakt för att det ska fungera. Personen måste arbeta direkt med vårt snabb uppföljnings team för att undersöka och lösa problemet.
- **Svars tid för kunder** Om en kund inte kan uppfylla de förväntada svars kraven, nedgraderas begäran av en allvarlighets grad till ett minimum av allvarlighets grad C. Om en kund inte svarar på en begäran om att få en åtgärd kommer Microsoft att minska och stänga support förfrågan inom 48 timmar efter den senaste begäran.

## <a name="provide-feedback"></a>Ge feedback

Vi uppskattar din feedback och använder den för att förbättra support upplevelsen för administratörer.

När en biljett har **begränsats** eller **lösts** kan du dela med dig av dina synpunkter på din upplevelse med just det problemet. För att göra det går du till sidan **service begär Anden** i **fel sökning + support** -menyn i Mem-portalen. Välj den specifika biljetten. Biljett uppgifterna visas i den högra rutan, Välj fliken **feedback** och ange den information som krävs. Var försiktig så att du inte får med personlig information i feedback-formuläret. Mer information om sekretess finns i [Microsofts sekretess policy](https://privacy.microsoft.com/privacystatement).

![Feedback-formulär](../../media/feedback_form.png)



## <a name="additional-resources"></a>Ytterligare resurser
- [Användar stöd för Microsoft Managed Desktop](end-user-support.md). 
- [Stöd för Microsoft Managed Desktop](../service-description/support.md). 
- Om du redan prenumererar på Microsoft Managed Desktop kan du hitta detaljerade procedurer, process flöden, arbets instruktioner och vanliga frågor och svar i administratörs guiden för Microsoft- **Online resources** hanterade **Skriv bord på** **administrations** -menyn i Microsoft [slut punkts hanteraren](https://endpoint.microsoft.com/).
