---
title: Kontrollera utgående skräppost i Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: Om din organisation skickar en hel del massutskick som är markerat som skräppost kan du blockeras från att skicka e-post med Office 365. Läs den här artikeln om du vill veta mer om varför detta händer och vad du kan göra åt det.
ms.openlocfilehash: e1b1e0f56398db774a9aabc56cdcde52ad17791a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42808620"
---
# <a name="control-outbound-spam-in-office-365"></a>Kontrollera utgående skräppost i Office 365

Vi tar hantera utgående spam på allvar eftersom vår är en delad tjänst.  Det finns många kunder bakom en delad pool av resurser, där om en kund skickar utgående spam, kan det försämra den utgående IP rykte tjänsten och påverkar den framgångsrika leveransbarheten av e-post för andra kunder.

> [!IMPORTANT]
> Meddelandet för när en avsändare är begränsad är nu en del av SCC-varningsplattformen (Security & Compliance Center). I stället för att använda metoder som beskrivs nedan för att skicka meddelanden, listan över användare att avisering kan hittas i **användaren begränsas från att skicka e-postavisering.** Börja använda [sidan varningsprinciper](https://sip.protection.office.com/alertpolicies) i Security & Compliance Center för att konfigurera aviseringen, eftersom den tidigare metoden kommer att tas bort i framtiden. Läs om den nya [ta bort en användare från portalen För begränsade användare efter att ha skickat skräppost."](removing-user-from-restricted-users-portal-after-spam.md)

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Vad administratörer kan göra för att kontrollera utgående spam

- **Aktivera meddelanden när ett konto skickar skräppost eller stängs av:** Administratörer kan få hemlig kopia när ett meddelande markeras som utgående skräppost och skickas via högriskpoolen. Genom att övervaka den här postlådan kan en administratör identifiera om de har ett komprometterat konto i sitt nätverk eller om skräppostfiltret av misstag markerar sin e-post som skräppost. Du hittar mer information om hur du ställer in den utgående skräppostpolicyn [här](configure-the-outbound-spam-policy.md).

- **Granska manuellt spam klagomål från 3: e parts e-postleverantörer:** Många 3: e parts e-posttjänster som Outlook.com, Yahoo och AOL ge en Feedback Loop där om någon användare i sin tjänst markerar ett e-postmeddelande från vår tjänst som spam, är meddelandet paketeras upp och skickas tillbaka till oss för granskning. Om du vill veta mer om support för avsändare för Outlook.com klickar du [här](https://sendersupport.olc.protection.outlook.com/pm/services.aspx).

## <a name="what-eop-does-to-control-outbound-spam"></a>Vad EOP gör för att kontrollera utgående spam

1. **Segregering av utgående trafik i separata pooler av IPs:** Varje meddelande som kunder skickar utgående via tjänsten genomsöks för spam. Om meddelandet är skräppost dirigeras det genom poolen Högriskleverans. Den här IP-poolen innehåller statusmeddelanden som inte kan levereras och skräppost. Leverans till den avsedda mottagaren garanteras inte eftersom många tredje parter inte accepterar e-post eftersom kvaliteten på e-post den avger.

   Dela trafiken på detta sätt säkerställer att lägre kvalitet e-post (spam, backscatter NDRs) inte drar ner rykte regelbundna utgående e-postpooler. Högriskpoolen har vanligtvis lågt rykte hos många mottagare runt Internet, även om detta inte är universellt.

2. **Övervakning av IP-rykte:** Office 365 frågar olika IP-blocklists från tredje part och genererar aviseringar om någon av våra utgående IP-adresser finns med på dem. Detta gör att vi kan reagera snabbt när spam har orsakat vårt rykte att försämras. När en avisering genereras har vi intern dokumentation som ligger bakom vilka åtgärder som ska vidtas för att avlistas.

3. **Inaktivera kränkande konton när de skickar för mycket e-post märkt som skräppost:** Även om vi segregera vår spam och icke-spam i två separata utgående IP-pooler, e-postkonton kan inte skicka spam på obestämd tid. Vi övervakar vilka konton som skickar skräppost och om det överskrider en hemlig gräns blockeras kontot från att skicka skräppost.

   Ett enda meddelande som markeras som skräppost kan vara en felklassificering av spammotorn och även känt som ett falskt positivt. Vi skickar den genom högriskpoolen för att ge den en chans att gå ut; Ett stort antal meddelanden på kort tid är dock ett tecken på ett problem och när det inträffar blockerar vi kontot från att skicka fler e-postmeddelanden. Det finns olika tröskelvärden som finns för enskilda e-postkonton samt sammanlagt för hela klienten.

4. **Inaktivera felande konton när de skickar för mycket e-post på för kort tid:** Förutom gränserna ovan som letar efter en andel meddelanden markerade som skräppost, det finns också gränser som blockerar konton när de når en övergripande gräns oavsett om meddelandena är markerade som spam. Anledningen till att denna gräns finns beror på att ett komprometterat konto kan skicka nolldagars skräppost som missas av spamfiltret. Eftersom det är svårt, om inte omöjligt, att ibland se skillnaden mellan en legitim massutskickkampanj och en massiv skräppostkampanj aktiveras dessa gränser för att begränsa eventuella skador.

> [!NOTE]
> För både #3 och #4 annonserar vi inte de exakta gränserna för att förhindra spammare från att spela systemet och för att säkerställa att vi kan ändra gränserna när vi behöver. Gränserna är tillräckligt höga så att en genomsnittlig affärsanvändare aldrig kommer att slå dem och tillräckligt låg för att den innehåller de flesta av de skador en spammare kan göra.

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a>Rekommenderade lösningar för kunder som vill skicka utgående en hel del e-post via EOP

Det är svårt att hitta en balans mellan kunder som vill skicka en stor mängd e-post kontra skydda tjänsten från komprometterade konton och masse e-postare med dålig praxis lista förvärv. Återigen är kostnaden för en utgående IP-landning på en 3: e parts blocklist högre än att blockera en kund från att skicka utgående e-post. Som beskrivs i [Exchange Online Service Description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), med EOP för att skicka bulk e-post är inte en stöds användning av tjänsten och är endast tillåtet på grundval av "bästa insats". För kunder som vill skicka massutskick rekommenderar vi följande:

1. **Skicka massmeddelandet via sina egna lokala e-postservrar:** Detta innebär att kunden måste behålla sin egen e-postinfrastruktur för den här typen av e-post.

2. **Använd en 3: e parts bulk e-postför att skicka masskommunikation:** Det finns flera 3: e parts bulk e-postörer vars enda verksamhet är att skicka bulk e-post. De kan arbeta med kunder för att säkerställa att de har bra e-postpraxis och de har resurser som är avsedda att genomdriva den.

The Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publicerar sin medlemslista [här](https://www.maawg.org/about/roster). Flera masse e-postleverantörer är på listan och är kända för att vara ansvarig Internet medborgare.

## <a name="for-more-information"></a>Mer information

[Exempel på meddelande när en avsändare blockeras skicka utgående skräppost](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[Office 365 email anti-spam protection](anti-spam-protection.md)

[Anti-förfalskningsskydd i Office 365](anti-spoofing-protection.md)

[Nivåer för förtroende för skräppost](spam-confidence-levels.md)
