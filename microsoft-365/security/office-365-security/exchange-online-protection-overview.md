---
title: Exchange Online Protection (EOP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Lär dig Exchange Online Protection (EOP) kan skydda din lokala e-postorganisation i fristående och hybridmiljöer.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce90f1429e2c54f413ae54172a6d2f663ef6a358
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624728"
---
# <a name="exchange-online-protection-overview"></a>Översikt över Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) är den molnbaserade filtreringstjänsten som hjälper dig att skydda organisationen mot skräppost, skadlig programvara och andra e-posthot. EOP ingår i alla Microsoft 365 med Exchange Online postlådor.

I resten av den här artikeln förklaras hur EOP fungerar.

> [!NOTE]
> EOP är också tillgängligt för sig själv för att skydda lokala postlådor och i hybridmiljöer för att skydda lokala Exchange postlådor. Mer information finns i [Fristående Exchange Online Protection](/exchange/standalone-eop/standaonline-eop).

## <a name="how-eop-works"></a>Så här fungerar EOP

För att förstå hur EOP fungerar hjälper det dig att se hur det bearbetar inkommande e-post:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Bild av e-post från Internet eller kundfeedback som passerar till EOP och via Anslutning, Skadlig programvara, Filtrering av e-postflödesregler och innehållsfiltrering, innan bedömning av antingen skräppost eller karantän, eller slutanvändarens e-postleverans.":::

- När ett inkommande meddelande kommer in i EOP passerar det först genom anslutningsfiltrering, som kontrollerar avsändarens rykte. Majoriteten av skräpposten stoppas nu och avvisas av EOP. Mer information finns i [konfigurera anslutningsfilter](configure-the-connection-filter-policy.md).

- Sedan kontrolleras meddelandet om det finns skadlig programvara. Om skadlig programvara finns i meddelandet eller i de bifogade filer, dirigeras meddelandet till en administratörs enda lagringslager i karantän. Mer information om skydd mot skadlig programvara finns [i Skydd mot skadlig programvara i EOP.](anti-malware-protection.md)

- Meddelanden fortsätter med principfiltrering, där de utvärderas mot anpassade e-postflödesregler (kallas även transportregler) som du skapar eller tillämpar från en mall. Du kan till exempel ha en regel som skickar ett meddelande till en chef när e-post tas emot från en viss avsändare. DLP-kontroller (Data Loss Prevention) utförs också i det här läget (Exchange Enterprise CAL med Services).

- Därefter passerar meddelandet skräppostfiltrering där meddelandet är sök efter skräppost, nätfiske eller massutskick. Upptäckta meddelanden kan skickas till karantän, eller till en användares skräppostmapp, bland annat. Mer information finns i [Konfigurera principer för skydd mot skräppost](configure-your-spam-filter-policies.md) och Konfigurera principer mot [nätfiske.](configure-anti-phishing-policies-eop.md)

Alla meddelanden som klarar alla dessa skyddslager levereras till mottagaren.

Mer information finns i [Ordning och prioritet för e-postskydd.](how-policies-and-protections-are-combined.md)

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>EOP-abonnemang och -funktioner för lokala e-postorganisationer

De tillgängliga EOP-abonnemangen är:

- **Fristående EOP:** Du registrerar dig i EOP för att skydda din lokala e-postorganisation.

- **EOP-funktioner i Exchange Online**: Alla prenumerationer som innehåller Exchange Online (fristående eller som en del av Microsoft 365) använder EOP för att skydda Exchange Online postlådor.

- **Exchange Enterprise CAL** med tjänster: Om du har en lokal Exchange-organisation där du har köpt ytterligare Exchange Enterprise CAL med services-licenser är EOP en del av tjänsterna som ingår.

Mer information om krav, viktiga begränsningar och funktionstillgänglighet för alla EOP-abonnemang finns [i Exchange Online Protection tjänstbeskrivning.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

> [!NOTE]
> Om du har en Microsoft 365- Office 365-prenumeration som omfattar Exchange Online postlådor har du EOP. Information om steg för att konfigurera EOP-säkerhetsfunktioner i din prenumeration och information om den extra säkerheten som en Microsoft Defender för Office 365-prenumeration kan ge dig finns i skydda [mot hot.](protect-against-threats.md) Rekommenderade inställningar för EOP-funktionen för konfiguration finns i Rekommenderade inställningar för EOP och [Microsoft Defender för Office 365 säkerhet.](recommended-settings-for-eop-and-office365.md)

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Konfigurera EOP för lokala e-postorganisationer

Det kan vara enkelt att konfigurera EOP, särskilt om det gäller en liten organisation med några få efterlevnadsregler. Men om du har en stor organisation med flera domäner, anpassade efterlevnadsregler eller hybrid-e-postflöde kan det ta längre tid att planera och ta tid att konfigurera.

Om du redan har köpt EOP kan du gå till Konfigurera [EOP-tjänsten](/exchange/standalone-eop/set-up-your-eop-service) och kontrollera att du har slutfört alla steg som krävs för att konfigurera EOP för att skydda meddelandemiljön.

### <a name="eop-datacenters"></a>EOP-datacenter

EOP körs i ett globalt nätverk av datacenter som är utformade för att ge bästa tillgänglighet. Om till exempel ett datacenter blir otillgängligt, dirigeras e-postmeddelanden automatiskt till ett annat datacenter utan avbrott i tjänsten. Servrar i varje datacenter tar emot meddelanden åt dig, vilket innebär en åtskillnad mellan organisationen och Internet, vilket minskar belastningen på servrarna. Genom detta tillgängliga nätverk kan Microsoft se till att e-post når din organisation i tid.

EOP utför belastningsutjämning mellan datacenter men bara i en region. Om du har etablerat dig i en region bearbetas alla meddelanden med e-postdirigeringen för den regionen. I följande lista visas hur regional e-postdirigering fungerar för EOP-datacenter:

- I Europa, Mellanöstern och Afrika (EMEA) finns alla Exchange Online-postlådor i EMEA-datacenter och alla meddelanden dirigeras via EMEA-datacenter för EOP-filtrering.
- I Asia-Pacific (APAC) finns alla Exchange Online-postlådor i APAC-datacenter och meddelandena dirigeras just nu via APAC-datacenter för EOP-filtrering.
- I Amerika distribueras tjänster på följande platser:
  - Sydamerika: Exchange Online finns i datacenter i Brasilien och Chile. Alla meddelanden dirigeras genom lokala datacenter för EOP-filtrering. Meddelanden i karantän lagras i det datacenter där klientorganisationen finns.
  - Kanada: Exchange Online finns i datacenter i Kanada. Alla meddelanden dirigeras genom lokala datacenter för EOP-filtrering. Meddelanden i karantän lagras i det datacenter där klientorganisationen finns.
  - USA: Exchange Online postlådor finns i datacenter i USA. Alla meddelanden dirigeras genom lokala datacenter för EOP-filtrering. Meddelanden i karantän lagras i det datacenter där klientorganisationen finns.
- För Government Community Cloud (GCC) finns alla Exchange Online-postlådor i USA:s datacenter och alla meddelanden dirigeras via usa-datacenter för EOP-filtrering.

## <a name="eop-help-for-admins"></a>EOP-hjälp för administratörer

Hjälpinnehållet för EOP-administratörer består av följande toppnivåkategorier:

- [Konfigurera EOP, dag 1,](protect-against-threats.md)för Microsoft Defender för Office 365-administratörer: Konfigurera skydds- och identifieringsverktygen i EOP i kärnan i Microsoft Defender för Office 365.

- [EOP-funktioner:](eop-features.md)Innehåller en lista över funktioner som är tillgängliga i EOP.

- [Konfigurera EOP-tjänsten:](/exchange/standalone-eop/set-up-your-eop-service)Innehåller anvisningar för hur du ställer in EOP-tjänsten och länkar till ytterligare information.

- [Byt till EOP från Google Postini, Barracuda Spam and Virus Firewall eller Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Beskriver processen för att byta till EOP från en annan e-postskyddsprodukt.

- [Hantera mottagare i fristående EOP](/exchange/standalone-eop/manage-recipients-in-eop): Beskriver hur du hanterar e-postanvändare och grupper i fristående EOP.

- [E-postflöde](mail-flow-in-eop.md)i EOP : Här beskrivs hur du konfigurerar scenarier för anpassade e-postflöden med kopplingar, hur du hanterar domäner som är kopplade till tjänsten och hur du aktiverar funktionen DBEB (Directory Based Edge Blocking).

- [Rekommenderade inställningar för EOP](recommended-settings-for-eop-and-office365.md)och Microsoft Defender för Office 365-säkerhet: Beskriver rekommenderade konfigurationsinställningar och överväganden för när du har installerat och etablerat tjänsten.

- [Granskningsrapporter i Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports): Beskriver hur du använder granskningsrapporter för att spåra konfigurationsändringar i tjänsten.

- Skydd mot skräppost och skadlig programvara i [EOP:](anti-spam-and-anti-malware-protection.md)Här beskrivs filtrering av skräppost och filtrering av skadlig programvara och hur du kan anpassa dem så att de bäst uppfyller organisationens behov. Dessutom beskrivs de uppgifter som administratörer och slutanvändare kan utföra på meddelanden i karantän.

- [Rapportering och meddelandespårning i Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Beskriver de rapporter och felsökningsverktyg som är tillgängliga.

- [Exchange](/exchange/exchange-admin-center) administrationscenter i Exchange Online eller Exchange administrationscenter i fristående [EOP](/exchange/standalone-eop/exchange-admin-center-eop): Beskriver hur du kommer åt och navigerar i administrationscentret för Exchange (EAC) för att kunna hantera relaterade EOP-funktioner.

- [Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell): Innehåller information om fjärr-PowerShell, där du kan hantera EOP-tjänsten från kommandoraden.

- [Hjälp och support för EOP](help-and-support-for-eop.md) Innehåller information om hur du skaffar hjälp och teknisk support.