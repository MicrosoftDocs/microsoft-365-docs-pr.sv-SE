---
title: Översikt över Exchange Online Protection (EOP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur Exchange Online Protection (EOP) hjälper till att skydda din lokala e-postorganisation i fristående och hybrid miljöer.
ms.openlocfilehash: 997f157432dced474ccc17bf47cf9af68f4b8c08
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356721"
---
# <a name="exchange-online-protection-overview"></a>Översikt över Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online Protection (EOP) är den molnbaserade filter tjänsten som hjälper dig att skydda din organisation mot skräp post och skadlig program vara. EOP ingår i alla Microsoft 365-organisationer med Exchange Online-postlådor. EOP är också tillgängligt i följande lokala scenarier:

- **I ett fristående scenario**: EOP tillhandahåller Cloud-baserad e-postskydd för din lokala Exchange-organisation eller för någon annan lokal SMTP-e-postlösning.

- **I en hybrid distribution**: EOP kan konfigureras för att skydda din e-postmiljö och styra e-postdirigering när du har en blandning av lokala och Cloud-postlådor.

I dessa scenarion kan EOP förenkla hanteringen av din e-postmiljö och för att minska antalet arbets bördar som medföljer underhåll av lokal maskin vara och program vara.

Resten av det här avsnittet förklarar hur EOP fungerar i fristående och hybrid miljöer.

## <a name="how-eop-works"></a>Så fungerar EOP

För att förstå hur EOP fungerar kan du se hur det behandlar inkommande e-post:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Bild av e-post från Internet eller en kund feedback som skickas till EOP och via anslutningen, antiskadligt, flödes regler med snedstreck – byte av filtrering och innehålls filtrering, innan Verdict av antingen skräp post eller karantän eller slutanvändarens e-postleverans.":::

- När ett inkommande meddelande kommer till EOP övergår det initialt genom anslutnings filtrering, vilket kontrollerar avsändarens rykte. Majoriteten av skräp posten har stoppats vid den här punkten och avvisas av EOP. Mer information finns i [konfigurera anslutningsfilter](configure-the-connection-filter-policy.md).

- Då kontrol leras meddelandet om att du har tecken på skadlig program vara. Om skadlig kod hittas i meddelandet eller bifogade filer skickas meddelandet till en administratörs karantän lagring. Du kan läsa mer om hur du konfigurerar anti-malware [här](configure-anti-malware-policies.md).

- Meddelanden fortsätter genom princip filtrering, där de utvärderas mot anpassade regler för e-postflöde (kallas även transport regler) som du skapar eller tillämpar från en mall. Du kan till exempel ha en regel som skickar ett meddelande till en chef när e-post kommer från en viss avsändare. Det sker även i den här punkten (Exchange Enterprise CAL med tjänster).

- Sedan passerar meddelandet upp genom innehålls filtrering (kallas även för skräp post). Ett meddelande om att det här filtret bestämmer sig för att vara skräp post *eller Phish* kan skickas till karantän eller till en annan mapp för skräp post. Mer information finns i [Konfigurera principer för skräp post](configure-your-spam-filter-policies.md) och [Konfigurera skydd mot nätfiske](configure-anti-phishing-policies-eop.md).

Alla meddelanden som klarar alla dessa skydds lager levereras till mottagaren.

Mer information finns i [order och prioriteringsordning för e-postskydd](how-policies-and-protections-are-combined.md).

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>EOP planer och funktioner för lokala e-postorganisationer

De tillgängliga EOP-abonnemangen är:

- **Fristående EOP**: du registrerar dig i EOP för att skydda din lokala e-postorganisation.

- **EOP funktioner i Exchange Online**: alla abonnemang som innehåller Exchange Online (fristående eller som en del av Microsoft 365) använder EOP för att skydda dina Exchange Online-postlådor.

- **Exchange Enterprise-klientåtkomstlicens med tjänster**: om du har en lokal Exchange-organisation där du har köpt ytterligare Exchange-klientåtkomstlicens för företag med tjänste licenser är EOP en del av de tjänster som ingår.

Information om krav, viktiga begränsningar och tillgängligheten för alla EOP-abonnemang finns i [beskrivningen av Exchange Online Protection Service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Konfigurera EOP för lokala e-postorganisationer

Det är enkelt att konfigurera EOP, särskilt när det gäller en liten organisation med en fåtal regler för efterlevnad. Om du har en stor organisation med flera domäner, anpassade efterföljandekrav eller ett hybridt e-postflöde kan du ställa in mer planering och tid.

Om du redan har köpt EOP läser du konfigurera [EOP-tjänsten](set-up-your-eop-service.md) för att se till att slutföra alla nödvändiga steg för att konfigurera EOP för att skydda din meddelande miljö.

### <a name="eop-datacenters"></a>EOP Data Center

EOP körs i ett världs omfattande nätverk av data Center som är utformade för att ge bästa möjliga tillgänglighet. Om till exempel ett Data Center inte är tillgängligt dirigeras e-postmeddelanden automatiskt till ett annat data Center utan avbrott i tjänsten. Servrar i varje data Center tar emot meddelanden åt dig, vilket ger en åtskillnad mellan din organisation och Internet, och därmed minskar belastningen på dina servrar. Tack vare det här tillgängliga nätverket kan Microsoft se till att e-post når din organisation i tid.

EOP utför belastnings fördelning mellan data centers men bara inom en region. Om du har etablerat en region kommer alla meddelanden att bearbetas med hjälp av e-postdirigering för det området. I följande lista visas hur regionala e-postroutning fungerar för EOP Data Center:

- I Europa, Mellanöstern och Afrika (EMEA) finns alla Exchange Online-postlådor i EMEA-Data Center och alla meddelanden routas genom EMEA-data för EOP filtrering.

- I Asia-Pacific (APAC) kommer alla Exchange Online-postlådor att finnas i APAC Data Center och meddelanden dirigeras för närvarande i APAC data centers för EOP-filtrering.

- I Amerika distribueras tjänsterna på följande platser:

  - Sydamerika: Exchange Online-postlådor finns i data centers i Brasilien och Chile. Alla meddelanden routas genom lokala data Center för EOP filtrering. Meddelanden i karantän lagras i data centret där klient organisationen finns.

  - Kanada: Exchange Online-postlådor finns i data centers i Kanada. Alla meddelanden routas genom lokala data Center för EOP filtrering. Meddelanden i karantän lagras i data centret där klient organisationen finns.

  - USA: Exchange Online-postlådor finns i amerikanska data Center. Alla meddelanden routas genom lokala data Center för EOP filtrering. Meddelanden i karantän lagras i data centret där klient organisationen finns.

- För det statliga community-molnet (GCC) finns alla Exchange Online-postlådor i amerikansk Data Center och alla meddelanden dirigeras via amerikanska data Center för EOP-filtrering.

## <a name="eop-help-for-admins"></a>EOP hjälp för administratörer

Hjälp innehållet för EOP-administratörer består av följande kategorier:

- [Konfigurera EOP, dag 1, för Microsoft Defender för Office 365-administratörer](protect-against-threats.md): Konfigurera EOP skydds-och identifierings verktyg i kärnan i Microsoft Defender för Office 365.

- [EOP funktioner](eop-features.md): innehåller en lista med funktioner som är tillgängliga i EOP.

- [Konfigurera EOP-tjänsten](set-up-your-eop-service.md): innehåller anvisningar för hur du konfigurerar en EOP-tjänst och länkar till ytterligare information.

- [Växla till EOP från Google Postini, Barracuda spam and virus Firewall eller Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): beskriver processen för att växla till EOP från en annan e-postskydds produkt.

- [Hantera mottagare i fristående EOP](manage-recipients-in-eop.md): Här beskrivs hur du hanterar e-postanvändare och grupper i EOP.

- [E-postflöde i EOP](mail-flow-in-eop.md): Här beskrivs hur du konfigurerar anpassade e-postflöden med hjälp av kopplingar, hur du hanterar domäner som är associerade med tjänsten och hur du aktiverar funktionen för katalogbaserade Edge-blockering (DBEB).

- [Metod tips för att konfigurera EOP](best-practices-for-configuring-eop.md): beskriver rekommenderade konfigurations inställningar och överväganden efter att du har konfigurerat och etablerat din tjänst.

- [Gransknings rapporter i fristående EOP](auditing-reports-in-eop.md): Här beskrivs hur du använder gransknings rapporter för att spåra konfigurations ändringar för tjänsten.

- [Skydd mot skräp post och mot skadlig program vara i EOP](anti-spam-and-anti-malware-protection.md): beskriver filtrering av skräp post och filter för skadlig program vara och visar hur du anpassar dem så att de passar bäst för din organisation. Dessutom beskrivs de uppgifter som administratörer och slutanvändare kan utföra på meddelanden i karantän.

- [Rapportering och meddelande spårning i Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): beskriver de rapporter och fel söknings verktyg som är tillgängliga.

- [Administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md): Här beskrivs hur du kommer åt och navigerar i administrations centret för Exchange (UK) för att hantera din EOP-tjänst.

- [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): ger information om Remote PowerShell, som du kan använda för att hantera din EOP-tjänst från kommando raden.

- [Hjälp och support för EOP](help-and-support-for-eop.md) Innehåller information om hur du får hjälp och teknisk support.
