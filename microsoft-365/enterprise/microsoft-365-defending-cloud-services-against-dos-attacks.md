---
title: Försvara Microsoft 365-moln tjänster mot DOS-attacker (Denial-of-Service)
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: I den här artikeln lär du dig hur Microsoft skyddar sina moln tjänster mot DoS-attacker (Denial-of-Service).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 21b38950ec06874f8c1d959eeb6a8b60179636e3
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332502"
---
# <a name="defending-microsoft-365-cloud-services-against-denial-of-service-attacks"></a>Försvara Microsoft 365-moln tjänster mot DOS-attacker (Denial-of-Service)

Microsoft datacentren skyddas av säkerhets skydd som inkluderar perimeter-och video kameror, säkerhets personal och säkra ingångar som använder biometri, smartkort och multifaktorautentisering. Skydd mot försvar fortsätter via alla områden i anläggningen och till varje fysisk server-enhet. [Microsoft Cloud Infrastructure and Operations Group](https://www.microsoft.com/cloud-platform/global-datacenters) har grundläggande infrastruktur och grundläggande teknik för våra moln tjänster. Våra data Center uppfyller bransch standarden för fysisk säkerhet och pålitlighet och hanteras, övervakas och administreras av Microsoft Operations personal.

För att skydda våra moln tjänster erbjuder Microsoft ett system för DDoS försvar som är en del av Microsoft Azure-kontinuerlig övervakning och inträngande test processer. Azure DDoS försvar-systemet är utformat för att inte bara motstå attacker från utsidan, utan även från andra Azure-innehavare. Azure använder standard funktioner för identifiering och begränsning som SYN-cookies, hastighets begränsning och anslutnings begränsningar för att skydda mot DDoS attacker.

Microsofts moln tjänster är föremål för angrepp från flera källor. För att minska och skydda mot de olika DoS-hoten är ett högskalbart och dynamiskt Azure-baserat system för identifiering av hot och begränsning för att skydda den underliggande infrastrukturen från DoS-attacker och att förhindra tjänst avbrott för moln tjänst kunder. Azure DoS-minsknings systemet skyddar inkommande, utgående och region-till-region-trafik.

De flesta DoS-attacker lanseras mot mål i Network (L3) och transport (L4) i den öppna modellen för [system Interconnection](https://docs.microsoft.com/windows-hardware/drivers/network/windows-network-architecture-and-the-osi-model) (OSI). Attacker riktade mot ett L3-och L4-lager är avsedda att överbelasta ett nätverks gränssnitt eller en tjänst med angrepps trafik till trånga resurser och förhindra möjligheten att reagera på legitim trafik. Särskilt är L3-och L4-angrepp ett försök att antingen Saturate kapacitet för nätverks länkar, enheter eller tjänster eller överbelasta servrarnas eller virtuella datorers processor användning.

För att skydda mot L3-och L4-attacker har Microsoft utformat, utvecklat och distribuerat en lösning som riktar sig till specifikt för att skydda infrastrukturen och kund målen som kommer under angrepp genom att skydda dessa lager. Genom att skydda infrastrukturen ser du till att attack trafik som är avsedd för en kund inte leder till mindre skador eller försämrad nätverks kvalitet för andra kunder. Lösningen använder trafik data från data Center-routrar. Dessa data analyseras av en nätverks övervaknings tjänst för att upptäcka attacker. När en attack upptäcks, kan funktioner för automatisk försvar vara på.

## <a name="application-level-defenses"></a>Försvar på program nivå
Microsoft Engineering Teams följer de rigorösa standarder som är inställda av [Microsofts operativa säkerhets säkra](https://www.microsoft.com/SDL/OperationalSecurityAssurance) för att skydda kunddata. Microsofts moln tjänster är avsiktligt utformade för att stödja en mycket hög belastning samt för att skydda och begränsa mot DoS-attacker på program nivå. Vi har implementerat en skalad arkitektur där tjänsterna distribueras i flera globala data Center med regionala isolerings-och begränsnings funktioner i vissa av arbets belastningarna.

Varje kunds land eller region som kundens administratör identifierar under den första konfigurationen av tjänsterna bestämmer den primära lagrings platsen för kundens data. Kunddata replikeras mellan överflödiga data Center enligt en primär/säkerhets kopierings strategi. Ett primärt Data Center lagrar program program varan tillsammans med alla primära kunddata som körs på program varan. Ett säkerhets kopierings Data Center ger automatisk redundans. Om det primära data centret upphör att fungera, kommer förfrågningar att omdirigeras till kopian av program varan och kund data i säkerhets kopie data centret. Vid en given tidpunkt kan kund uppgifter bearbetas antingen i det primära eller säkerhets kopie data centret. Om du distribuerar data i flera data Center minskar den berörda ytan om ett Data Center attackeras. Dessutom kan tjänsterna i det berörda data centret snabbt omdirigeras till det sekundära data centret som en av återställnings mekanismerna och vice versa (omdirigerade till det primära data centret när tjänsten återställs).

Enskilda arbets belastningar inkluderar inbyggda funktioner som hanterar resursutnyttjande. Till exempel kan mekanismerna för begränsning i Exchange Online och SharePoint Online vara en del av ett multi-lager-tillvägagångs sätt att försvara mot DoS-attacker. Begränsning för Exchange Online-användare baseras på den nivå av resurser som används av slutanvändaren, oavsett om resurserna finns i Active Directory, i informations arkivet för Exchange Online eller på annan plats. En budget tilldelas till varje klient för att begränsa resurserna som används av en användare. Exchange Online-begränsning för användar aktivitet och system komponenter baseras på [hantering av arbets belastning](https://technet.microsoft.com/library/jj150503(v=exchg.150).aspx). En Exchange Online-belastning är en Exchange Online-funktion, ett protokoll eller en tjänst som uttryckligen har definierats för system resurs hantering i Exchange Online. För varje Exchange Online-arbetsbelastning krävs system resurser som CPU, Mailbox databas Operations eller Active Directory-begäranden för att utföra användar förfrågningar eller bakgrunds arbete. Exempel på arbets belastning för Exchange Online inkluderar Outlook på webben, Exchange ActiveSync, Mailbox migration och post lådor. Klient organisationer kan hantera begränsnings inställningar för arbets belastnings hantering för användare med Exchange Management Shell. Det finns olika former av begränsning som har implementerats i Exchange Online, till exempel PowerShell, Exchange Web Services och POP och IMAP, Exchange ActiveSync, mobila enheter, anslutningar, med mera. Administratörer av lokala Exchange-installationer kan konfigurera begränsnings principer, men administratörer kan inte konfigurera begränsnings principer för Exchange Online.

Den vanligaste utlösaren för begränsning i SharePoint Online är CSOM-koden på klient sidan som utför för många åtgärder på ett alltför högt sätt. Med CSOM kan många åtgärder utföras med en enda begäran som kan överskrida användnings gränserna och orsaka varje användares begränsning.

Oberoende av vilken aktivitet som kan leda till begränsning när en användare överskrider användnings gränserna begränsas alla eventuella förfrågningar från det användar kontot, vanligt vis under en kort period. När en användares begränsning används begränsas alla åtgärder från den användaren tills begränsningen upphör, enligt följande kriterier:
- För förfrågningar som utförs av användaren direkt i en webbläsare omdirigerar SharePoint Online till sidan med begränsnings information och begäran Miss lyckas.
- För alla andra förfrågningar, inklusive CSOM-samtal, returnerar SharePoint Online HTTP-statuskod 429 ("för många begär Anden") och begäran Miss lyckas.

Om den felaktiga processen fortsätter att överskrida användnings gränserna kan SharePoint Online helt blockera processen och returnera HTTP-statuskod 503 ("tjänsten är inte tillgänglig").

## <a name="vulnerability-and-penetration-testing"></a>Säkerhets problem och inträngda test
Microsoft använder många [säkerhets tekniker och-metoder](https://www.microsoft.com/trustcenter/security/threatmanagement) för att [skydda moln infrastrukturen](https://blogs.technet.microsoft.com/hybridcloud/2015/05/05/protecting-your-datacenter-and-cloud-from-emerging-threats/) och lokala nätverk mot moderna, sofistikerade hot, inklusive användning av program mot skadlig kod och tjänster för moln tjänster, virtuella maskiner och andra system. Avancerad Threat Analytics, som övervakar vanliga användnings mönster för nätverk, system och användare och använder maskin inlärning för att flagga alla funktioner som ligger utanför det vanliga och vanliga inträngda test.

Förutom våra egna test och att erbjuda våra kunder ett [Microsoft Cloud Unified-testprogram för inträngning](https://technet.microsoft.com/mt784683), kan vi också samar beta med utomstående leverantörers säkerhetsutövare som regelbundet utför utvärdering av och tränga in på våra moln tjänster. Vi gör rapporterna från följande utvärderings versioner av tredje part som kan hämtas från [tjänst förtroendet](https://aka.ms/STP) och [service Assurance-](https://aka.ms/ServiceAssurance) portalerna.
