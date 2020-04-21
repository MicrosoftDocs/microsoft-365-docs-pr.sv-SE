---
title: Byt till EOP från Google Postini, Barracuda Spam and Virus Firewall eller Cisco IronPort
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
description: Syftet med det här avsnittet är att hjälpa dig att förstå processen för att byta till Exchange Online Protection (EOP) från en lokal e-posthygieninstallation eller molnbaserad skyddstjänst och sedan ge dig hjälpresurser för att komma igång.
ms.openlocfilehash: e6a25d6477741f5796dd08b5811d97e2d0c76b51
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631199"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Byt till EOP från Google Postini, Barracuda Spam and Virus Firewall eller Cisco IronPort

 Syftet med det här avsnittet är att hjälpa dig att förstå processen för att byta till Exchange Online Protection (EOP) från en lokal e-posthygieninstallation eller molnbaserad skyddstjänst och sedan ge dig hjälpresurser för att komma igång. Det finns många spam-filtreringslösningar, men processen för att byta till EOP är liknande i de flesta fall.

Om du inte har gjort det tidigare i EOP och vill läsa en översikt över dess funktioner innan du bestämmer dig för att byta börjar du med översiktsavsnittet [För Exchange Online Protection.](exchange-online-protection-overview.md)

Innan du växlar till EOP är det viktigt att tänka på om du vill vara värd för dina EOP-skyddade postlådor i molnet, med Exchange Online, lokalt eller i ett hybridscenario. (Hybrid innebär att du har några postlådor som finns lokalt och en annan del som finns i Exchange Online.) Var och en av dessa värdscenarier: moln, lokalt och hybrid, är möjligt, men installationsstegen kan variera. Här är några saker som hjälper dig att välja lämplig distribution:

- **EOP-skydd med lokala postlådor**: Det här scenariot är lämpligt om du har befintlig e-postvärdinfrastruktur som du vill använda, eller om du har affärskrav för att hålla postlådor lokalt och du vill använda EOP som ditt molnbaserade e-postskydd. [Växla till EOP fristående](#switch-to-eop-standalone) beskriver det här scenariot mer i detalj.

- **EOP-skydd med Exchange Online-postlådor**: Det här scenariot är lämpligt om du vill ha EOP-skydd och alla dina postlådor finns i molnet. Det kan hjälpa dig att minska komplexiteten, eftersom du inte behöver underhålla lokala meddelandeservrar. [Växla till Exchange Online](#switch-to-exchange-online) beskriver det här scenariot.

- **EOP-skydd med hybridpostlådor**: Kanske vill du ha molnpostlådor, men du måste behålla postlådor för vissa användare lokalt. Välj det här scenariot om du vill att vissa postlådor ska finnas lokalt och en annan del ska finnas med Exchange Online. [Växla till en hybridlösning](#switch-to-a-hybrid-solution) beskriver det här scenariot.

## <a name="switch-to-eop-standalone"></a>Växla till EOP fristående

Om du för närvarande är värd för dina postlådor lokalt och använder en lokal skyddsanordning eller en molnmeddelandeskyddstjänst kan du växla till EOP för att dra nytta av dess skyddsfunktioner och tillgänglighet. Om du vill konfigurera EOP i ett fristående scenario, vilket innebär att du är värd för dina postlådor lokalt och använder EOP för att tillhandahålla e-postskydd, kan du följa stegen i [Konfigurera din EOP-tjänst](set-up-your-eop-service.md). I avsnittet beskrivs stegen för att konfigurera EOP-skydd, som inkluderar registrering, lägger till din domän och konfigurerar e-postflöde med kopplingar.

## <a name="switch-to-exchange-online"></a>Växla till Exchange Online

Kanske har du lokala postlådor som skyddas av en lokal installation och du vill hoppa till Exchange Online-molnbaserade postlådor och EOP-skydd för att dra nytta av Microsoft 365 molnmeddelande- och skyddsfunktioner. För att komma igång kan du registrera dig för Microsoft 365 och lägga till din domän. Det här scenariot kräver inte att du konfigurerar kopplingar, eftersom det inte finns någon routning till lokala postlådor. Börja på [Få de senaste avancerade funktionerna med Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) för att registrera dig och bekanta dig med dess funktioner.

Under installationsprocessen för Microsoft 365 skapar du dina molnbaserade postlådeanvändare.

## <a name="switch-to-a-hybrid-solution"></a>Växla till en hybridlösning

Du kanske bara vill flytta en del av postlådorna till molnet på grund av affärskrav eller myndighetsskäl. När du distribuerar ett hybridscenario kan du flytta postlådor till molnet som dina affärskrav kräver. Att migrera till ett hybridscenario med EOP-skydd är mer komplicerat än att gå över till ett scenario med hela molnet, men Microsoft ger fullständigt hybridstöd och gott om resurser för att göra övergången till hybrid enklare.

Det bästa stället att börja, om du funderar på en hybriddistribution, är [Exchange Server hybriddistributioner](https://docs.microsoft.com/exchange/exchange-hybrid). Dessutom finns det några olika sätt att dirigera e-post i ett hybridscenario som är viktigt att förstå. [Transportroutning i Exchange-hybriddistributioner](https://docs.microsoft.com/exchange/transport-routing) förklarar varje typ, så att du kan välja det bästa routningsscenariot, baserat på dina affärsbehov.

## <a name="migration-planning"></a>Planering av migrering

När du bestämmer dig för att byta till EOP ska du ta särskild hänsyn till följande områden:

- **Anpassade filtreringsregler:** Om du har anpassade filtrerings- eller affärspolicyregler för att fånga upp specifik skräppost rekommenderar vi att du provar EOP med standardinställningarna för en period innan du migrerar reglerna. EOP erbjuder skräppostskydd på företagsnivå med standardinställningarna, det kan visa sig att du inte behöver migrera några av dina regler till EOP. Om du har regler som tillämpar specifika anpassade affärsprinciper kan du naturligtvis skapa dessa. [Regler för e-postflöde (transportregler) i Exchange Online Protection](mail-flow-rules-transport-rules-0.md) innehåller detaljerade instruktioner för hur du skapar regler för e-postflöde i EOP.

- **IP-tillåta listor och IP-blocklistor:** Om du har per användare tillåta listor och blocklistor, ge lite tid att kopiera listorna till EOP som en del av din installationsprocess. Mer information om IP-tillåta listor och IP-blockeringslistor finns i [Konfigurera princip för anslutningsfilter](configure-the-connection-filter-policy.md).

- **Säker kommunikation**: Om du har en partner som kräver krypterade meddelanden rekommenderar vi att du konfigurerar detta i administrationscentret för Exchange. Information om hur du konfigurerar det här scenariot finns i [Konfigurera kopplingar för säkert e-postflöde med en partnerorganisation](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).

> [!TIP]
> När du växlar från en lokal apparat till EOP är det möjligt att lämna din apparat eller en server på plats som utför affärsregelkontroller. Om din apparat till exempel utför anpassad filtrering på utgående e-post, och du vill att den ska fortsätta med det, kan du konfigurera EOP för att skicka e-post direkt till apparaten för ytterligare filtrering, innan den dirigeras till internet.
