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
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur Exchange Online Protection (EOP) kan skydda din lokala e-postorganisation i fristående och hybridmiljöer.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8e3d44cb39e3569179d4155e32a8c11e0a5be56
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286891"
---
# <a name="exchange-online-protection-overview"></a>Översikt över Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

EOP (Exchange Online Protection) är den molnbaserade filtreringstjänsten som hjälper dig att skydda organisationen mot skräppost och skadlig programvara. EOP ingår i alla Microsoft 365-organisationer med Exchange Online-postlådor. EOP är dock även tillgängligt i följande lokala scenarier:

- **I ett fristående scenario:** EOP ger molnbaserat e-postskydd för din lokala Exchange-organisation eller någon annan lokal SMTP-e-postlösning.

- **I en hybriddistribution** kan EOP konfigureras för att skydda din e-postmiljö och styra e-postdirigeringen när du har en blandning av lokala postlådor och molnbaserade postlådor.

I de här scenarierna kan EOP förenkla hanteringen av e-postmiljön och förenkla många av de kostnader som följer med underhåll av lokal maskinvara och programvara.

I resten av det här avsnittet förklaras hur EOP fungerar i fristående miljöer och hybridmiljöer.

## <a name="how-eop-works"></a>Så här fungerar EOP

För att förstå hur EOP fungerar hjälper det dig att se hur det bearbetar inkommande e-post:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Bild av e-post från antingen Internet- eller kundfeedback som skickas till EOP och via anslutning, skadlig programvara, snedstrecksprincipfiltrering och innehållsfiltrering, innan de kan fastställa antingen skräppost eller karantän eller e-postleverans för slutanvändaren.":::

- När ett inkommande meddelande kommer in via EOP går det först igenom anslutningsfiltrering, vilket kontrollerar avsändarens rykte. Majoriteten av skräpposten stoppas nu och avvisas av EOP. Mer information finns i [konfigurera anslutningsfilter](configure-the-connection-filter-policy.md).

- Sedan kontrolleras meddelandet om det finns tecken på skadlig programvara. Om skadlig programvara hittas i meddelandet eller de bifogade filarna dirigeras meddelandet till en administratörs enda lagringslager i karantän. Här kan du läsa mer om hur du konfigurerar skydd mot [skadlig programvara.](configure-anti-malware-policies.md)

- Meddelanden fortsätter genom principfiltrering, där de utvärderas mot anpassade e-postflödesregler (kallas även transportregler) som du skapar eller tillämpar från en mall. Du kan till exempel ha en regel som skickar ett meddelande till en chef när e-post tas emot från en viss avsändare. DLP-kontroller (Data Loss Prevention) utförs också i det här läget (Exchange Enterprise CAL med Services).

- Sedan går meddelandet igenom innehållsfiltreringen (kallas även skräppostskydd). Ett meddelande som filtret fastställer är *skräppost* eller nätfiske kan bland annat skickas till karantän eller en användares skräppostmapp. Mer information finns i [Konfigurera principer för skydd mot skräppost och](configure-your-spam-filter-policies.md) Konfigurera principer för skydd mot [nätfiske.](configure-anti-phishing-policies-eop.md)

Alla meddelanden som skickar alla dessa skyddslager korrekt levereras till mottagaren.

Mer information finns i Ordning [och prioritet för e-postskydd.](how-policies-and-protections-are-combined.md)

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>EOP-abonnemang och funktioner för lokala e-postorganisationer

De tillgängliga EOP-abonnemangen är:

- **EOP fristående:** Du registrerar dig i EOP för att skydda din lokala e-postorganisation.

- **EOP-funktioner i Exchange Online:** Alla prenumerationer som innehåller Exchange Online (fristående eller som en del av Microsoft 365) använder EOP för att skydda dina Exchange Online-postlådor.

- **Exchange Enterprise CAL med Tjänster:** Om du har en lokal Exchange-organisation där du har köpt ytterligare Exchange Enterprise CAL med services-licenser är EOP en del av de tjänster som ingår.

Mer information om krav, viktiga begränsningar och funktionstillgänglighet för alla EOP-abonnemang finns i tjänstbeskrivningen [för Exchange Online Protection.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Konfigurera EOP för lokala e-postorganisationer

Det kan vara enkelt att konfigurera EOP, särskilt för små organisationer med några få efterlevnadsregler. Men om du har en stor organisation med flera domäner, anpassade efterlevnadsregler eller hybrid-e-postflöde kan det ta längre tid att planera och ta tid att konfigurera.

Om du redan har köpt EOP kan du gå till Konfigurera [EOP-tjänsten](set-up-your-eop-service.md) för att säkerställa att du slutför alla steg som krävs för att konfigurera EOP för att skydda meddelandemiljön.

### <a name="eop-datacenters"></a>EOP-datacenter

EOP körs på ett globalt nätverk av datacenter som är utformade för att ge bästa tillgänglighet. Om till exempel ett datacenter blir otillgängligt, dirigeras e-postmeddelanden automatiskt till ett annat datacenter utan avbrott i tjänsten. Servrar i varje datacenter tar emot meddelanden åt dig, vilket gör att det finns en åtskillnad mellan organisationen och Internet, vilket minskar belastningen på servrarna. Genom detta tillgängliga nätverk kan Microsoft se till att e-post når din organisation i tid.

EOP utför belastningsutjämning mellan datacenter men bara i en region. Om du är etablerat i en region bearbetas alla meddelanden med e-postdirigering för det området. I följande lista visas hur regional e-postdirigering fungerar för EOP-datacenter:

- I Europa, Mellanöstern och Afrika (EMEA) finns alla Exchange Online-postlådor i EMEA-datacenter och alla meddelanden dirigeras via EMEA-datacenter för EOP-filtrering.

- I Asia-Pacific (APAC) finns alla Exchange Online-postlådor i APAC-datacenter och meddelanden dirigeras för närvarande via APAC-datacenter för EOP-filtrering.

- I Amerika distribueras tjänster på följande platser:

  - Sydamerika: Exchange Online-postlådor finns i datacenter i Brasilien och Chile. Alla meddelanden dirigeras genom lokala datacenter för EOP-filtrering. Meddelanden i karantän lagras i det datacenter där klientorganisationen finns.

  - Kanada: Exchange Online-postlådor finns i datacenter i Kanada. Alla meddelanden dirigeras genom lokala datacenter för EOP-filtrering. Meddelanden i karantän lagras i det datacenter där klientorganisationen finns.

  - USA: Exchange Online-postlådor finns i amerikanska datacenter. Alla meddelanden dirigeras genom lokala datacenter för EOP-filtrering. Meddelanden i karantän lagras i det datacenter där klientorganisationen finns.

- För Government Community Cloud (GCC) finns alla Exchange Online-postlådor i amerikanska datacenter och alla meddelanden dirigeras via amerikanska datacenter för EOP-filtrering.

## <a name="eop-help-for-admins"></a>EOP-hjälp för administratörer

Hjälpinnehållet för EOP-administratörer består av följande kategorier på den översta nivån:

- [Konfigurera EOP, dag 1,](protect-against-threats.md)för Microsoft Defender för Office 365-administratörer: Konfigurera EOP-skydds- och identifieringsverktygen i kärnan i Microsoft Defender för Office 365.

- [EOP-funktioner:](eop-features.md)Ger en lista över funktioner som är tillgängliga i EOP.

- [Konfigurera EOP-tjänsten:](set-up-your-eop-service.md)Innehåller instruktioner för att konfigurera EOP-tjänsten och länkar till ytterligare information.

- [Byt till EOP från Google Postini, Barracuda Spam and Virus Firewall eller Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Beskriver processen för att byta till EOP från ett annat e-postskyddsprodukt.

- [Hantera mottagare i fristående EOP:](manage-recipients-in-eop.md)Här beskrivs hur du hanterar e-postanvändare och grupper i EOP.

- [E-postflöde i EOP:](mail-flow-in-eop.md)Här beskrivs hur du konfigurerar scenarier för anpassade e-postflöden med kopplingar, hur du hanterar domäner som är kopplade till tjänsten och hur du aktiverar funktionen DBEB (Directory Based Edge Blocking).

- [Rekommendationer för konfigurering av EOP:](best-practices-for-configuring-eop.md)Beskriver rekommenderade konfigurationsinställningar och överväganden för när du har konfigurerat och etablerat tjänsten.

- [Granskningsrapporter i fristående EOP](auditing-reports-in-eop.md): Beskriver hur du använder granskningsrapporter för att spåra konfigurationsändringar för tjänsten.

- Skydd mot skräppost och skadlig programvara i [EOP:](anti-spam-and-anti-malware-protection.md)Här beskrivs filtrering av skräppost och filtrering av skadlig programvara och visar hur du kan anpassa dem så att de bäst uppfyller organisationens behov. Dessutom beskrivs uppgifter som administratörer och slutanvändare kan utföra på meddelanden i karantän.

- [Rapportering och meddelandespårning i Exchange Online Protection:](reporting-and-message-trace-in-exchange-online-protection.md)Beskriver de rapporter och felsökningsverktyg som är tillgängliga.

- [Administrationscenter för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md): Här beskrivs hur du kommer åt och navigerar i administrationsgränssnittet för Exchange -administrationscentret (EAC) för att hantera EOP-tjänsten.

- [Exchange Online Protection PowerShell:](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)Innehåller information om fjärr-PowerShell, som gör att du kan hantera EOP-tjänsten från kommandoraden.

- [Hjälp och support för EOP](help-and-support-for-eop.md) Innehåller information om hur du skaffar hjälp och teknisk support.
