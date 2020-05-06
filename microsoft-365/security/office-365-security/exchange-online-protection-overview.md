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
ms.custom:
- seo-marvel-apr2020
description: Lär dig mer om Microsoft Exchange Online Protection (EOP) och hur det skyddar din organisation mot skräppost och skadlig kod.
ms.openlocfilehash: 4630c58bef49f13a1ae1536336afbac170418dcc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036530"
---
# <a name="exchange-online-protection-overview"></a>Översikt över Exchange Online Protection

Microsoft Exchange Online Protection (EOP) är en molnbaserad e-postfiltreringstjänst som hjälper till att skydda din organisation mot skräppost och skadlig kod och innehåller funktioner som skyddar din organisation från meddelandepolicyöverträdelser. EOP kan förenkla hanteringen av din meddelandemiljö och minska många av de bördor som följer med att underhålla lokal maskinvara och programvara.

I följande lista beskrivs hur du kan använda EOP för meddelandeskydd:

- **I ett fristående scenario:** EOP ger molnbaserat e-postskydd för din lokala Exchange-organisation eller för någon annan lokal SMTP-e-postlösning.

- **Som en del av Exchange Online:** EOP är det inbyggda skyddet för molnbaserade postlådor i Exchange Online och Office 365. Se [Skydda mot hot](protect-against-threats.md) om hjälp med att konfigurera dessa Exchange Online-funktioner.

- **I en hybriddistribution:** EOP kan konfigureras för att skydda din meddelandemiljö och styra e-postroutning när du har en blandning av lokala och molnpostlådor.

> [!NOTE]
> Dessa Exchange Online Protection-artiklar gäller hybrid- och lokala miljöer.

## <a name="how-eop-works"></a>Så här fungerar EOP

För att förstå hur EOP fungerar hjälper det att se hur det bearbetar inkommande e-post:

![E-postprocessdiagram.](../../media/GitHubBugs/emailprocessingineop1.png)

Ett inkommande meddelande passerar inledningsvis genom anslutningsfiltrering, som kontrollerar avsändarens rykte och kontrollerar meddelandet efter skadlig kod. Majoriteten av spam stoppas på denna punkt och tas bort av EOP. Meddelanden fortsätter genom principfiltrering, där meddelanden utvärderas mot anpassade regler för e-postflöde (kallas även transportregler) som du skapar eller tillämpar från en mall. Du kan till exempel ha en regel som skickar ett meddelande till en chef när e-post kommer från en viss avsändare. (Kontroller för att förhindra dataförluster sker också i det här läget, om du har [den](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)funktionen. Därefter passerar meddelanden genom innehållsfiltrering, där innehåll kontrolleras efter terminologi eller egenskaper som är gemensamma för skräppost. Ett meddelande som bedöms vara skräppost av innehållsfiltret kan skickas till en användares skräppostmapp eller till karantänen, bland andra alternativ (inklusive Inkorg eller anpassad mapp), baserat på dina inställningar. När ett meddelande har skickat alla dessa skyddslager har levererats det till mottagaren.

### <a name="eop-datacenters"></a>EOP-datacenter

EOP körs på ett världsomspännande nätverk av datacenter som är utformade för att ge den bästa tillgängligheten. Om ett datacenter till exempel blir otillgängligt dirigeras e-postmeddelanden automatiskt till ett annat datacenter utan avbrott i tjänsten. Servrar i varje datacenter accepterar meddelanden för din räkning, vilket ger ett lager av separation mellan din organisation och Internet, vilket minskar belastningen på dina servrar. Genom detta nätverk med högtillgänglig tillgång kan Microsoft se till att e-post når din organisation i tid.

EOP utför belastningsutjämning mellan datacenter men bara inom en region. Om du etableras i en region bearbetas alla dina meddelanden med hjälp av e-postroutning för den regionen. Följande lista visar hur regional e-postroutning fungerar för EOP-datacenter:

- I Europa, Mellanöstern och Afrika (EMEA) finns alla Exchange Online-postlådor i EMEA-datacenter och alla meddelanden dirigeras via EMEA-datacenter för EOP-filtrering.

- I Asien-Stillahavsområdet (APAC) finns alla Exchange Online-postlådor i APAC-datacenter och meddelanden dirigeras för närvarande via APAC-datacenter för EOP-filtrering.

- I Amerika finns alla Exchange Online-postlådor i amerikanska datacenter, med undantag för Sydamerika där datacenter i Brasilien och Chile används och i Kanada där datacenter i Kanada används. Alla e-postmeddelanden, inklusive meddelanden för kunder i Sydamerika och Kanada, dirigeras via lokala datacenter för EOP-filtrering. e-post i karantän lagras i det datacenter där klienten finns.

- För Government Community Cloud (GCC) finns alla Exchange Online-postlådor i amerikanska datacenter och alla meddelanden dirigeras via amerikanska datacenter för EOP-filtrering.

## <a name="eop-plans-and-features"></a>EOP-planer och funktioner

De tillgängliga EOP-prenumerationsplanerna är:

- **EOP fristående**: Du registrerar dig i EOP för att skydda din lokala e-postorganisation.

- **EOP-funktioner i Exchange Online**: Alla prenumerationer som inkluderar Exchange Online (fristående eller som en del av Office 365) använder EOP för att skydda dina Exchange Online-postlådor.

- **Exchange Enterprise CAL med tjänster**: Om du har en lokal Exchange-organisation där du har köpt ytterligare Exchange Enterprise CAL med tjänstelicenser är EOP en del av de inkluderade tjänsterna.

Information om krav, viktiga begränsningar och funktionstillgänglighet i alla EOP-prenumerationsplaner finns i [beskrivningen av Tjänsten Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="setting-up-eop"></a>Ställa in EOP

Det kan vara enkelt att konfigurera EOP, särskilt när det gäller en liten organisation med en handfull efterlevnadsregler. Men om du har en stor organisation med flera domäner, anpassade efterlevnadsregler eller hybridpostflöde kan det ta mer planering och tid.

Om du redan har köpt EOP läser du [Konfigurera din EOP-tjänst](set-up-your-eop-service.md) för att se till att du slutför alla nödvändiga steg för att konfigurera EOP för att skydda din meddelandemiljö.

## <a name="for-more-information"></a>Mer information

[Funktioner i EOP](eop-features.md)

[Allmänna vanliga frågor och svar om EOP](eop-general-faq.md)

[Vanliga frågor och svar om köade, uppskjutna och studsade meddelanden i EOP](eop-queued-deferred-and-bounced-messages-faq.md)

[Vanliga frågor och svar om delegerad administration](delegated-administration-faq.md)

[Flytta domäner och inställningar från en EOP-organisation till en annan EOP-organisation](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
