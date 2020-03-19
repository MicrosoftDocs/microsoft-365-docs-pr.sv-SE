---
title: Översikt över Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: Microsoft Exchange Online Protection (EOP) är en molnbaserad e-postfiltreringstjänst som hjälper till att skydda din organisation mot skräppost och skadlig kod och innehåller funktioner för att skydda din organisation från överträdelser av meddelandepolicyn.
ms.openlocfilehash: a87b9b40d1a95f7c4da194ffd2138aa9d1726032
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807943"
---
# <a name="exchange-online-protection-overview"></a>Översikt över Exchange Online Protection

Microsoft Exchange Online Protection (EOP) är en molnbaserad e-postfiltreringstjänst som hjälper till att skydda din organisation mot skräppost och skadlig kod och innehåller funktioner för att skydda din organisation från överträdelser av meddelandepolicyn. EOP kan förenkla hanteringen av din meddelandemiljö och lindra många av de bördor som följer med att upprätthålla lokal maskinvara och programvara.

I följande lista beskrivs hur du kan använda EOP för meddelandeskydd:

- **I ett fristående scenario**: EOP tillhandahåller molnbaserat e-postskydd för din lokala Exchange-organisation eller för någon annan lokal SMTP-e-postlösning.

- **Som en del av Exchange Online:** EOP är det inbyggda skyddet för molnbaserade postlådor i Exchange Online och Office 365. Se [Skydda mot hot](protect-against-threats.md) om du vill ha hjälp med att konfigurera dessa Exchange Online-funktioner.

- **I en hybriddistribution**: EOP kan konfigureras för att skydda meddelandemiljön och styra e-postroutningen när du har en blandning av lokala och molnpostlådor.

> [!NOTE]
> Dessa Exchange Online Protection-artiklar gäller för hybrid- och lokala miljöer.

## <a name="how-eop-works"></a>Så här fungerar EOP

För att förstå hur EOP fungerar hjälper det att se hur det bearbetar inkommande e-post:

![E-postprocessdiagram.](../../media/GitHubBugs/emailprocessingineop1.png)

Ett inkommande meddelande passerar inledningsvis genom anslutningsfiltrering, som kontrollerar avsändarens rykte och granskar meddelandet för skadlig kod. Majoriteten av spam stoppas vid denna punkt och tas bort av EOP. Meddelanden fortsätter genom principfiltrering, där meddelanden utvärderas mot anpassade regler för e-postflöde (kallas även transportregler) som du skapar eller framtvingar från en mall. Du kan till exempel ha en regel som skickar ett meddelande till en chef när e-post kommer från en viss avsändare. (Kontroller för förebyggande av dataförlust sker också i det här läget, om du har den funktionen, för information om funktionstillgänglighet, se [beskrivningen av Tjänsten Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).) Därefter skickar meddelanden genom innehållsfiltrering, där innehåll kontrolleras för terminologi eller egenskaper som är gemensamma för skräppost. Ett meddelande som bedöms vara skräppost av innehållsfiltret kan skickas till en användares skräppostmapp eller till karantänen, bland andra alternativ (inklusive Inkorg eller anpassad mapp), baserat på dina inställningar. När ett meddelande har skickat alla dessa skyddslager levereras det till mottagaren.

### <a name="eop-datacenters"></a>EOP datacenter

EOP körs i ett världsomspännande nätverk av datacenter som är utformade för att ge bästa tillgänglighet. Om ett datacenter till exempel blir otillgängligt dirigeras e-postmeddelanden automatiskt till ett annat datacenter utan avbrott i tjänsten. Servrar i varje datacenter accepterar meddelanden för din räkning, vilket ger ett lager av separation mellan din organisation och Internet, vilket minskar belastningen på dina servrar. Genom det här mycket tillgängliga nätverket kan Microsoft se till att e-post når din organisation i tid.

EOP utför belastningsutjämning mellan datacenter men bara inom en region. Om du är etablerad i en region kommer alla dina meddelanden att bearbetas med hjälp av e-postroutningen för den regionen. Följande lista visar hur regional e-postroutning fungerar för EOP-datacenter:

- I Europa, Mellanöstern och Afrika (EMEA) finns alla Exchange Online-postlådor i EMEA-datacenter och alla meddelanden dirigeras via EMEA-datacenter för EOP-filtrering.

- I Asien-Stillahavsområdet (APAC) finns alla Exchange Online-postlådor i APAC-datacenter och meddelanden dirigeras för närvarande via APAC-datacenter för EOP-filtrering.

- I Amerika finns alla Exchange Online-postlådor i amerikanska datacenter, med undantag för Sydamerika där datacenter i Brasilien och Chile används och i Kanada där datacenter i Kanada används. Alla e-postmeddelanden, inklusive meddelanden för kunder i Sydamerika och Kanada, dirigeras via lokala datacenter för EOP-filtrering. e-post i karantän lagras i det datacenter där klienten finns.

- För Government Community Cloud (GCC) finns alla Exchange Online-postlådor i amerikanska datacenter och alla meddelanden dirigeras via amerikanska datacenter för EOP-filtrering.

## <a name="eop-plans-and-features"></a>EOP planer och funktioner

De tillgängliga EOP-prenumerationsplanerna är:

- **EOP fristående:** Du registrerar dig i EOP för att skydda din lokala e-postorganisation.

- **EOP-funktioner i Exchange Online:** Alla prenumerationer som inkluderar Exchange Online (fristående eller som en del av Office 365) använder EOP för att skydda dina Exchange Online-postlådor.

- **Exchange Enterprise CAL med tjänster:** Om du har en lokal Exchange-organisation där du har köpt ytterligare Exchange Enterprise CAL med tjänster licenser, eop är en del av de medföljande tjänsterna.

Information om krav, viktiga gränser och funktionstillgänglighet för alla EOP-prenumerationsplaner finns i [beskrivningen av Tjänsten Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="setting-up-eop"></a>Ställa in EOP

Att konfigurera EOP kan vara enkelt, särskilt när det gäller en liten organisation med en handfull efterlevnadsregler. Men om du har en stor organisation med flera domäner, anpassade efterlevnadsregler eller hybridepostflöde kan det ta mer planering och tid att konfigurera.

Om du redan har köpt EOP läser du [Konfigurera EOP-tjänsten](set-up-your-eop-service.md) för att se till att du slutför alla nödvändiga steg för att konfigurera EOP för att skydda meddelandemiljön.

## <a name="for-more-information"></a>Mer information

[EOP-funktioner](eop-features.md)

[EOP allmänna FAQ](eop-general-faq.md)

[EOP köade, uppskjuten och studsade meddelanden FAQ](eop-queued-deferred-and-bounced-messages-faq.md)

[Vanliga frågor om delegerad administration](delegated-administration-faq.md)

[Flytta domäner och inställningar från en EOP-organisation till en annan EOP-organisation](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
