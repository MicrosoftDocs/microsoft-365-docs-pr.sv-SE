---
title: Växla till EOP från en annan skyddstjänst
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du byter till Exchange Online Protection (EOP) från en lokal e-postinstallation eller en molnbaserad skyddstjänst.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0cb946fbb60393657aab21195bc4dd723458f16e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290195"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Byta till EOP från Google Postini, Barracuda Spam and Virus Firewall eller Cisco IronPort

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

 Syftet med det här avsnittet är att hjälpa dig att förstå processen för att byta till Exchange Online Protection (EOP) från en lokal e-postlösning eller molnbaserad skyddstjänst och sedan ge dig hjälpresurser för att komma igång. Det finns många skräppostfiltreringslösningar, men i de flesta fall är processen för att byta till EOP liknande.

Om du inte har börjat använda EOP tidigare och vill läsa en översikt över funktionerna innan du bestämmer dig för att byta börjar du med [översiktsavsnittet](exchange-online-protection-overview.md) för Exchange Online Protection.

Innan du byter till EOP är det viktigt att tänka efter om du vill lagra dina EOP-skyddade postlådor i molnet, med Exchange Online, lokalt eller i ett hybridscenario. (Hybrid innebär att du har några postlådor lokalt och en annan del med Exchange Online.) Var och en av dessa värdscenarier: molnet, lokalt och hybrid är möjligt, men konfigurationsstegen kan variera. Här är några saker du bör tänka på när du väljer rätt distribution:

- **EOP-skydd** med lokala postlådor: Det här scenariot är lämpligt om du har befintlig e-postvärdinfrastruktur som du vill använda, eller om du har företagskrav för att behålla postlådorna lokalt och du vill använda EOP som ditt molnbaserade e-postskydd. [Om du byter till fristående EOP](#switch-to-eop-standalone) beskrivs det här scenariot mer i detalj.

- **EOP-skydd med Exchange** Online-postlådor: Det här scenariot är lämpligt om du vill ha EOP-skydd och alla dina postlådor i molnet. Det kan hjälpa dig att minska komplexiteten eftersom du inte behöver ha lokala meddelandeservrar. [Byt till Exchange Online](#switch-to-exchange-online) beskriver det här scenariot.

- **EOP-skydd med hybridpostlådor:** Du kanske vill ha molnpostlådor, men du måste ha postlådor för vissa användare lokalt. Välj det här scenariot om du vill ha några postlådor lokalt och en annan del med Exchange Online som värd. [När du byter till en hybridlösning](#switch-to-a-hybrid-solution) beskrivs det här scenariot.

## <a name="switch-to-eop-standalone"></a>Byt till EOP fristående

Om du för närvarande är värd för dina postlådor lokalt och använder ett lokalt skydd eller en tjänst för molnmeddelandeskydd kan du byta till EOP för att dra nytta av dess skyddsfunktioner och tillgänglighet. Om du vill konfigurera EOP i ett fristående scenario, vilket innebär att du har dina postlådor lokalt och använder EOP för att skydda e-posten, kan du följa stegen som beskrivs i Konfigurera [EOP-tjänsten.](set-up-your-eop-service.md) I det här avsnittet beskrivs stegen för att konfigurera EOP-skydd, som omfattar registrering, lägga till din domän och konfigurera e-postflöde med kopplingar.

## <a name="switch-to-exchange-online"></a>Byt till Exchange Online

Du kanske har lokala postlådor som skyddas av en lokal utrustning och vill gå till molnbaserade postlådor och EOP-skydd i Exchange Online för att kunna dra nytta av funktionerna för molnmeddelanden och skydd i Microsoft 365. För att komma igång kan du registrera dig för Microsoft 365 och lägga till din domän. I det här scenariot behöver du inte konfigurera kopplingar, eftersom det inte finns någon routning till lokala postlådor. Börja på [Skaffa de senaste avancerade funktionerna med Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) för att registrera dig och bekanta dig med funktionerna.

Under installationen av Microsoft 365 skapar du dina molnbaserade postlådeanvändare.

## <a name="switch-to-a-hybrid-solution"></a>Byt till en hybridlösning

På grund av affärskrav eller regelöverväganden kanske du bara vill flytta en del av dina postlådor till molnet. När du distribuerar ett hybridscenario kan du flytta postlådor till molnet allt eftersom företagskraven kräver det. Att migrera till ett hybridscenario med EOP-skydd är mer komplicerat än att flytta till ett scenario med hela molnet, men Microsoft har fullt hybridstöd och tillräckligt med resurser för att göra flytten till hybrid enklare.

Det bästa sättet att börja på om du överväger en hybriddistribution är [att Exchange Server hybriddistributioner.](https://docs.microsoft.com/exchange/exchange-hybrid) Det finns dessutom några olika sätt att dirigera e-post i ett hybridscenario som är viktigt att förstå. [Transportdirigering i Exchange-hybriddistributioner](https://docs.microsoft.com/exchange/transport-routing) förklarar varje typ, så du kan välja det bästa dirigeringsscenariot utifrån dina affärskrav.

## <a name="migration-planning"></a>Migreringsplanering

När du väljer att byta till EOP bör du särskilt beakta följande områden:

- **Anpassade filtreringsregler:** Om du har anpassade filtrerings- eller affärsprincipregler som fångar upp särskild skräppost rekommenderar vi att du provar EOP med standardinställningarna under en viss tidsperiod innan du migrerar dina regler. EOP ger skräppostskydd på företagsnivå med standardinställningarna, men det kan hända att du inte behöver migrera vissa av dina regler till EOP. Om du har regler som tillämpar särskilda anpassade affärsprinciper kan du naturligtvis skapa dem. [E-postflödesregler (transportregler) i Exchange Online Protection ger](mail-flow-rules-transport-rules-0.md) detaljerade instruktioner för hur du skapar e-postflödesregler i EOP.

- **Tillåtna IP-listor** och IP-blockeringslistor: Om du har tillåtna listor och blockeringslistor per användare kan du få lite tid att kopiera listorna till EOP som en del av installationen. Mer information om listan över tillåtna IP-adresser och IP-blockeringslistan finns i [Konfigurera principen för anslutningsfilter.](configure-the-connection-filter-policy.md)

- **Säker kommunikation:** Om du har en partner som kräver krypterade meddelanden rekommenderar vi att du krypterar detta i administrationscentret för Exchange. Information om hur du konfigurerar det här scenariot finns i [Konfigurera kopplingar för säkert e-postflöde med en partnerorganisation.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

> [!TIP]
> När du växlar från en lokal utrustning till EOP kan du låta utrustningen eller en server vara på plats och utföra affärsregelkontroller. Om din enhet till exempel utför anpassad filtrering på utgående e-post och du vill att det ska fortsätta kan du konfigurera EOP så att e-post skickas direkt till utrustningen för ytterligare filtrering, innan den dirigeras till Internet.
