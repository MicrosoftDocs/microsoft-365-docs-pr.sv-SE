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
description: I den här artikeln får du lära dig hur du byter till EOP (Exchange Online Protection) från en lokal e-postklienttjänst eller en molnbaserad skyddstjänst.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dfbbc44ebfed6cafb97e36b18a4fc34c91840d9b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624019"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Byta till EOP från Google Postini, Barracuda Spam and Virus Firewall eller Cisco IronPort

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 Syftet med det här avsnittet är att hjälpa dig förstå processen för att byta till Exchange Online Protection (EOP) från en lokal e-posttjänst eller molnbaserat skyddstjänst, och sedan ge dig hjälpresurser att komma igång. Det finns många skräppostfiltreringslösningar, men processen för att byta till EOP är i de flesta fall liknande.

Om du är nybörjare på EOP och vill läsa en översikt över funktionerna innan du vill byta börjar du med Exchange Online Protection [översiktsavsnittet.](exchange-online-protection-overview.md)

Innan du byter till EOP är det viktigt att tänka på om du vill lagra dina EOP-skyddade postlådor i molnet med Exchange Online, lokalt eller i ett hybridscenario. (Hybrid innebär att du har några postlådor lokalt och en annan del med Exchange Online.) Var och en av de här värdscenarierna: molnet, lokalt och hybrid kan vara möjligt, men konfigurationsstegen kan variera. Här är några saker du bör tänka på när du väljer rätt distribution:

- **EOP-skydd** med lokala postlådor: Det här scenariot är lämpligt om du har befintlig infrastruktur för e-postvärd som du vill använda, eller om du har företagskrav för att behålla postlådor lokalt, och du vill använda EOP som ditt molnbaserade e-postskydd. [Byt till fristående EOP](#switch-to-eop-standalone) beskriver det här scenariot mer detaljerat.

- **EOP-skydd Exchange Online** postlådor: Det här scenariot är lämpligt om du vill att EOP-skyddet och alla dina postlådor ska vara i molnet. Det kan hjälpa dig att minska komplexiteten eftersom du inte behöver underhålla lokala meddelandeservrar. [Växla till Exchange Online](#switch-to-exchange-online) beskriver det här scenariot.

- **EOP-skydd med hybridpostlådor**: Du kanske vill ha molnbaserade postlådor, men du behöver behålla postlådor för vissa användare lokalt. Välj det här scenariot om du vill att vissa postlådor ska ha lokalt och en annan del Exchange Online. [Byt till en hybridlösning](#switch-to-a-hybrid-solution) beskriver det här scenariot.

## <a name="switch-to-eop-standalone"></a>Byta till fristående EOP

Om du för närvarande är värd för dina postlådor lokalt och använder ett lokalt skydd eller en tjänst för molnmeddelandeskydd kan du byta till EOP för att dra nytta av dess skyddsfunktioner och tillgänglighet. Om du vill konfigurera EOP i ett fristående scenario, vilket innebär att du har dina postlådor lokalt och använder EOP för att skydda e-posten, kan du följa stegen som beskrivs i Konfigurera [EOP-tjänsten.](/exchange/standalone-eop/set-up-your-eop-service) I avsnittet beskrivs stegen för att konfigurera EOP-skydd, som omfattar registrering, lägga till din domän och konfigurera e-postflöde med kopplingar.

## <a name="switch-to-exchange-online"></a>Växla till Exchange Online

Du kanske har lokala postlådor skyddade av lokala program och vill gå till Exchange Online-molnbaserade postlådor och EOP-skyddet för att kunna dra nytta av Microsoft 365-molnmeddelanden och skyddsfunktioner. För att komma igång kan du registrera dig för Microsoft 365 och lägga till din domän. I det här scenariot behöver du inte konfigurera kopplingar, eftersom det inte finns någon routning till lokala postlådor. Börja på [Hämta de senaste avancerade funktionerna Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) registrera dig och bekanta dig med funktionerna.

Under Microsoft 365 skapar du dina molnbaserade postlådeanvändare.

## <a name="switch-to-a-hybrid-solution"></a>Byta till en hybridlösning

På grund av affärskrav eller regelöverväganden kanske du bara vill flytta en del av dina postlådor till molnet. När du distribuerar ett hybridscenario kan du flytta postlådor till molnet efter behov i verksamheten. Att migrera till ett hybridscenario med EOP-skydd är mer komplicerat än att flytta till ett scenario med hela molnet, men Microsoft har fullt hybridstöd och tillräckligt med resurser för att göra flytten till hybriden enklare.

Den bästa platsen att börja på om du överväger en hybriddistribution är [att Exchange Server hybriddistributioner.](/exchange/exchange-hybrid) Det finns dessutom några olika sätt att dirigera e-post i ett hybridscenario som är viktigt att förstå. [Transportdirigering i Exchange hybriddistributioner](/exchange/transport-routing) beskriver varje typ, så du kan välja bästa dirigeringsscenario, baserat på dina affärskrav.

## <a name="migration-planning"></a>Migreringsplanering

När du väljer att byta till EOP bör du särskilt överväga följande områden:

- **Anpassade filtreringsregler:** Om du har anpassade filterregler eller affärsprincipregler för att fånga upp specifik skräppost rekommenderar vi att du provar EOP med standardinställningarna under en viss tid innan du migrerar dina regler. EOP har skräppostskydd på företagsnivå med standardinställningarna. Det kan hända att du inte behöver migrera vissa av dina regler till EOP. Om du har regler som framtvingar särskilda anpassade affärspolicyer kan du naturligtvis skapa dessa. Mer information finns i [E-postflödesregler (transportregler) i Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

- **Tillåtna IP-listor** och IP-blockeringslistor: Om du har tillåtna listor per användare och blockeringslistor kan du ta lite tid att kopiera listorna till EOP som en del av konfigurationen. Mer information om listan över tillåtna IP-adresser och blockeringslistan för IP finns i [Konfigurera principen för anslutningsfilter.](configure-the-connection-filter-policy.md)

- **Säker kommunikation:** Om du har en partner som kräver krypterade meddelanden rekommenderar vi att du krypterar detta Exchange administrationscentret. Information om hur du konfigurerar det [här scenariot finns i Konfigurera kopplingar för säkert e-postflöde med en partnerorganisation.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

> [!TIP]
> När du växlar från en lokal miljö till EOP kan du låta program eller en server vara på plats där affärsregelkontroller utförs. Om dina program till exempel utför anpassad filtrering på utgående e-post och du vill att det ska fortsätta kan du konfigurera EOP att skicka e-post direkt till utrustningen för ytterligare filtrering innan den dirigeras till Internet.
