---
title: Växla till EOP från en annan skydds tjänst
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du växlar till Exchange Online Protection (EOP) från en lokal server för e-posthygien eller Cloud-baserad skydd.
ms.openlocfilehash: a6405411a130abf8369b312f553060caf0bf3855
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827803"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Byta till EOP från Google Postini, Barracuda Spam and Virus Firewall eller Cisco IronPort

 Syftet med det här avsnittet är att hjälpa dig att förstå processen för att växla till Exchange Online Protection (EOP) från en lokal server för e-posthygien eller Cloud-baserad skydds tjänst, och sedan tillhandahålla hjälp resurser för att komma igång. Det finns många lösningar för skräp post filtrering, men processen för att växla till EOP är i de flesta fall.

Om du är nybörjare i EOP och vill läsa en översikt över dess funktioner innan du bestämmer dig för att byta, börjar du med avsnittet [Exchange Online Protection Overview](exchange-online-protection-overview.md) .

Innan du växlar till EOP är det viktigt att tänka på om du vill ha dina EOP-skyddade post lådor i molnet, med Exchange Online, lokalt eller i ett hybrid scenario. (Hybrid innebär att du har vissa post lådor som hanteras lokalt och en annan del som är värd för Exchange Online.) Var och en av de här värd scenarierna: molnet, lokala och Hybrid är möjligt, men konfigurations stegen kan variera. Här är några saker som hjälper dig att välja lämplig installation:

- **EOP skydd med lokala post lådor**: det här scenariot är lämpligt om du har befintlig e-postvärd infrastruktur som du vill använda, eller om du har företags krav för att behålla post lådor lokalt, och du vill använda EOP som ditt molnbaserade e-postskydd. [Växla till EOP fristående](#switch-to-eop-standalone) beskriver det här scenariot mer detaljerat.

- **EOP skydd med Exchange Online-postlådor**: det här scenariot är lämpligt om du vill ha EOP skydd och alla dina post lådor i molnet. Den kan hjälpa dig att minska komplexiteten, eftersom du inte behöver underhålla lokala meddelande servrar. [Växla till Exchange Online](#switch-to-exchange-online) beskriver det här scenariot.

- **EOP skydd med hybrid post lådor**: kanske du vill lägga till en post låda för vissa användare lokalt. Välj det här scenariot om du vill att vissa post lådor ska vara lokalt och en annan del med Exchange Online. [Byt till en hybrid lösning](#switch-to-a-hybrid-solution) beskriver det här scenariot.

## <a name="switch-to-eop-standalone"></a>Växla till EOP fristående

Om du för närvarande är värd för dina post lådor på lokala enheter och använder en lokal skydds apparat eller ett moln meddelande skydds tjänst kan du växla till EOP och dra nytta av dess skydds funktioner och tillgänglighet. Om du vill konfigurera EOP i ett fristående scenario, vilket innebär att du är värd för dina post lådor lokalt och använder EOP för att tillhandahålla e-postskydd kan du följa stegen som beskrivs i [Konfigurera din EOP-tjänst](set-up-your-eop-service.md). I det här avsnittet beskrivs hur du konfigurerar EOP-skydd, som inkluderar registreringen, lägger till din domän och hur du konfigurerar e-postflöde med kopplingar.

## <a name="switch-to-exchange-online"></a>Växla till Exchange Online

Kanske har du lokala post lådor som skyddas av en lokal enhet och du vill hoppa till Exchange Online-postköer och EOP skydd för att utnyttja Microsoft 365 Cloud Messaging och skydds funktioner. För att komma igång kan du registrera dig för Microsoft 365 och lägga till din domän. I det här scenariot behöver du inte konfigurera kopplingar, eftersom det inte finns någon routning på lokala post lådor. Börja med att [Skaffa de senaste avancerade funktionerna med Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) för att registrera dig och få bekanta med dess funktioner.

Under installationen av Microsoft 365 skapar du dina molnbaserade användare av post lådor.

## <a name="switch-to-a-hybrid-solution"></a>Växla till en hybrid lösning

Du kanske vill flytta bara en del av dina post lådor till molnet på grund av företagets krav. När du distribuerar ett hybrid scenario kan du flytta post lådor till molnet allteftersom dina affärs krav gäller. Att migrera till ett hybrid scenario med EOP skydd är mer komplicerat än att flytta till ett allt-moln-scenario, men Microsoft tillhandahåller fullt hybrid stöd och gott om resurser för att det ska bli enklare att flytta till hybrid.

Det bästa stället att börja om du använder en hybrid distribution är [Exchange Server hybrid distributioner](https://docs.microsoft.com/exchange/exchange-hybrid). Dessutom finns det några olika sätt att dirigera e-post i ett hybrid scenario som är viktigt att förstå. [Transport dirigering i Exchange hybrid distributioner](https://docs.microsoft.com/exchange/transport-routing) förklarar varje typ, så att du kan välja scenariot för bästa routning baserat på ditt företags behov.

## <a name="migration-planning"></a>Planering för migrering

När du bestämmer dig för att växla till EOP bör du tänka på följande:

- **Anpassade filtrerings regler**: om du har anpassade filtrerings-eller affärs princip regler för att fånga särskilda skräp post rekommenderar vi att du testar EOP med standardinställningarna för en viss tids period innan du migrerar dina regler. EOP erbjuder skräp post skydd på företags nivå med standardinställningarna, det kan hända att du inte behöver migrera vissa av dina regler till EOP. Om du har regler som gäller för vissa anpassade affärs principer kan du naturligtvis skapa dem. [Regler för e-postflöde (transport regler) i Exchange Online Protection](mail-flow-rules-transport-rules-0.md) innehåller detaljerade anvisningar för hur du skapar e-postflödes regler i EOP.

- Listor med **IP-adresser och IP-blockerare**: om du har listor och blockerade listor per användare tillåter det att du kan kopiera listorna till EOP som en del av din konfigurations process. Mer information om listan över tillåtna IP-adresser och IP-blockeringslistan finns i [Konfigurera principen för anslutnings filter](configure-the-connection-filter-policy.md).

- **Säker kommunikation**: om du har en partner som kräver krypterade meddelanden rekommenderar vi att du konfigurerar detta i administrations centret för Exchange. Om du vill konfigurera det här scenariot läser du [Konfigurera kopplingar för säkert e-postflöde med en partner organisation](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).

> [!TIP]
> När du växlar från en lokal apparat till EOP är det möjligt att lämna din apparat eller en server som utför affärs regel kontroller. Om din enhet till exempel utför anpassad filtrering för utgående e-post och du vill att den ska fortsätta gör du så kan du konfigurera EOP för att skicka e-post direkt till apparaten för ytterligare filtrering innan den dirigeras till Internet.
