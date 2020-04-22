---
title: Utgående och inkommande e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 8/7/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Administratörer kan lära sig mer om widgeten Utgående och inkommande e-postflöde i instrumentpanelen för e-postflödet i Säkerhets- & Compliance Center.
ms.openlocfilehash: a1070783f60edf2de62d78c3094e9c20e3dd26f3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635202"
---
# <a name="outbound-and-inbound-mail-flow"></a>Utgående och inkommande e-postflöde

Widgeten **Utgående och inkommande e-postflöde** kombinerar informationen från **anslutningsrapporten** och den tidigare **TLS-översiktsrapporten** på ett ställe.

![Rapporten Flöde för utgående och inkommande e-post i instrumentpanelen för e-postflödet i Säkerhets- & Compliance Center](../../media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

Informationen i widgeten är relaterad till anslutningsappar och TLS-meddelandeskydd i Office 365. Mer information finns i följande avsnitt:

- [Konfigurera e-postflöde med kopplingar i Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

- [Så här använder Exchange Online TLS för att skydda e-postanslutningar i Office 365](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)

## <a name="message-protected-in-transit-by-tls"></a>Meddelande skyddat under transport (av TLS)

Widgeten **Utgående och inkommande e-postflöde** visar den TLS-kryptering som används för anslutningen när meddelanden levereras till och från din organisation. De anslutningar som upprättas med andra e-posttjänster krypteras av TLS när TLS erbjuds av båda sidor. Widgeten erbjuder en ögonblicksbild av den sista veckan av e-postflöde. När du klickar på **Visa information**visas TLS-skyddet för meddelanden **som skyddas under överföring (av TLS)** tls-skydd för meddelanden som kommer in och ut ur organisationen.

![De meddelanden som skyddas under överföring (av TLS) utfällbara i Security & Compliance Center](../../media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

För närvarande är TLS 1.2 den säkraste versionen av TLS som erbjuds av Office 365. Ofta måste du känna till TLS-krypteringen som används för efterlevnadsgranskningar. Du har förmodligen inte en direkt relation med de flesta av källan och destination e-postservrar (du inte äger dem, och inte heller Microsoft), så du inte har många alternativ för att förbättra TLS kryptering som används av dessa servrar.

Men du kan använda [anslutningsappar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) för att säkerställa bästa tillgängliga TLS-skydd för meddelanden som skickas mellan dina e-postservrar och Office 365. E-postflödet mellan Microsoft 365 och dina egna e-postservrar eller servrar som tillhör dina partner är ofta viktigare och känsligare än vanliga meddelanden, så du vill tillämpa extra säkerhet och vaksamhet på dessa meddelanden. Du kan uppgradera eller fixa dina egna e-postservrar för att förbättra TLS-krypteringen som används, eller nå ut till dina partner för att göra detsamma. **I Anslutningsrapporten** visas både e-postflödesvolym och TLS-kryptering för meddelanden som använder dina Microsoft 365-kopplingar.

## <a name="connector-report"></a>Rapport över koppling

När du klickar på länken **Anslutningsrapport** från det **utfällbara meddelandet (av TLS)** visas information om meddelanden som levereras till och från din organisation med hjälp av kopplingar. Du använder kopplingar mellan dina egna e-postservrar och Microsoft 365 eller din partners servrar och Office 365. Meddelandevolymen för varje anslutningsapp och TLS-kryptering för anslutningen är tillgänglig. Dessutom kan du också visa data för meddelanden som har skickats eller tagits emot i Microsoft 365 utan att använda en anslutningsapp.

Vyn **E-postflöde** visar volymen av meddelanden via kopplingen för den senaste veckan. Du kan ändra datumintervallet genom att välja **Filter** där du kan öka intervallet till högst 30 dagar. Vyn **Alla e-postmeddelanden visar** allt e-postflöde till och från organisationen via alla kopplingar. Du kan välja en specifik koppling efter namn i den nedrullningsbara menyn.

Du kan välja **TLS-användningsvyn** från listrutan för att se fördelningen av TLS-skydd för meddelanden via kopplingen. Precis som med rapporten **Överblicksrapport för TLS** visar den här vyn procentandelen av de olika TLS-versionerna. För TLS 1.0-anslutningar måste du verkligen få din e-postserver eller partnerns server uppgraderad eller fast för att undvika problem när TLS 1.0-stöd så småningom är inaktuellt i Office 365. Mer information finns [i Teknisk referensinformation om kryptering i Office 365](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption).

Insikter pekar på kopplingar för att uppmärksamma dig på potentiella TLS-krypteringsproblem för anslutningen. Insikterna är: **Ingen TLS är över 25%** eller **TLS 1,0 är över 50%**. Om du ser dessa insikter måste du undersöka dina e-postservrar som är kopplade till anslutningsappen eller nå ut till din partnerorganisation.

## <a name="see-also"></a>Snabbreferens

Mer information om andra insikter om e-postflöde i instrumentpanelen för e-postflödet finns [i Insikterna för e-postflöde i Security & Compliance Center](mail-flow-insights-v2.md).
