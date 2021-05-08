---
title: Schemaläggare för Microsoft 365 vanliga frågor och svar
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Schemaläggare för Microsoft 365 vanliga frågor och svar
ms.openlocfilehash: 12c2c00761b9a10fac6c62bc4d7ff5909ac935a7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286267"
---
# <a name="scheduler-for-microsoft-365-faqs"></a>Schemaläggare för Microsoft 365 vanliga frågor och svar

**Fråga:** Hur integrerar Scheduler med andra Cortana-funktioner, till exempel Cortana för *Windows,* *daglig* genomgång av e-post och *Spela upp mina e-postmeddelanden?*</br>
Scheduler är en oberoende tjänst från andra Cortana-funktioner. Andra Cortana-funktioner kan inaktiveras på klientorganisationsnivå, och Scheduler kan fortfarande aktiveras med hjälp av cortana@yourdomain.com postadressen. För närvarande kan användare bara interagera med Scheduler via e-post.

**Fråga:** Fungerar det bara med Outlook? Stöds andra e-postprodukter?</br>
Så länge du har en licens, Förutom de tre kraven ovan, kan användare skicka e-cortana@yourdomain.com från valfri e-postklient på valfri enhet.

**Fråga:** Kan kontakter finnas i en personlig kontaktlista i en Outlook eller motsvarande i företaget?</br>
Mötesdelidarna kan vara vem som helst med en e-postadress i eller utanför företaget. Schemaläggaren kan tyvärr inte automatiskt översätta namn till e-postadresser/alias genom att leta upp det i GAL i dag.

**Fråga:** Kan jag använda Scheduler med min installerade (lokala) version av Outlook?</br>
Schemaläggaren kräver Exchange Online. Fungerar inte med Exchange Server (prem). Fungerar med valfri e-postklient, Outlook, OWA, iOS, android, gmail och så vidare.

**Fråga:** Måste Outlook vara öppen i bakgrunden?</br>
Outlook behöver inte vara öppen i bakgrunden. Allt du behöver göra är att skicka ett e-postmeddelande till Cortana och förlita dig på att det gör mycket av arbetet.

## <a name="frequently-asked-trust-and-privacy-questions"></a>Vanliga frågor och svar om förtroende och sekretess

**Fråga:** Hur fungerar Scheduler?</br>
Scheduler använder AI (Scheduling Intelligence) som utökas med mänskliga assistenter. Om AI-modeller genererar ett behov av stöd i det naturliga språket för kommunikation med Cortana eskalerar mötesförfrågan till en person för granskning och slutförande.

**Fråga:** Vem människor som granskar eskalerade förfrågningar? </br>
Schemaläggarassistenter är Microsofts SSPA-certifierade (Supplier Security and Privacy Assurance) för personlig och mycket konfidentiell information. 

**Fråga:** Vad kan SSPA-assistenterna visa?</br>
Schemaläggaren och SSPA-assistenterna kan visa e-postmeddelanden som är adresserade till Cortana. I ett trådat e-postutbyte bearbetas bara de e-postmeddelanden som innehåller Cortanas e-postadress, inte de tidigare e-postmeddelandena i tråden innan Cortana lades till.   

**Fråga:** Behålls kunddata i Schemaläggarens data Flow? </br>
Schemaläggaren lagrar allt kundinnehåll inom klientorganisationens gränser och behåller data enligt GDPR:s riktlinjer, Microsoft 365 Trust & Sekretesspolicy och klientorganisationens e-postpolicyer.

**Fråga:** Hur bearbetas data om ledig/upptagen-information för interna deltagare i Scheduler? </br>
Scheduler's automation använder *tjänsten findMeetingTimes* för att identifiera tider som är ömsesidigt tillgängliga för deltagarna och organisatören. Den här tjänsten driver Outlook funktioner, till *exempel Föreslagna tider* i Outlook mötesformuläret. Deltagarinformation om ledig/upptagen används inte uttryckligen som block för ledig/upptagen tid. 

**Fråga:** Följer Scheduler GDPR kraven? </br>
Ja.

**Fråga:** Vem till Cortana-postlådan? </br>
Schemaläggaren bearbetar mötesförfrågningar och tillhörande e-postmeddelanden som skickas till din klientorganisations Cortana-postlåda. Microsoft har ingen annan åtkomst till Cortana-postlådan utom genom Lockbox-godkännande på begäran av innehavaradministratören.  

**Fråga:** Används kunddata för utbildning av AI-modeller?</br>
Inget kundinnehåll från Scheduler för Microsoft 365 användas för datautbildningsuppsättningar. Allt kundinnehåll finns i kundklientorganisationen.  

**Fråga:** Kommer Schemaläggaren att bearbeta krypterad e-post?</br>
Nej, krypterad e-post avvisas av Schemaläggaren-arbetsflödet. 




