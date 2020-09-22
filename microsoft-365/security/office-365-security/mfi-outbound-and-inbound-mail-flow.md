---
title: Utgående och inkommande e-postflöde i instrument panelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Administratörer kan lära sig mer om utgående och inkommande e-postflöde i instrument panelen för e-postflöde i säkerhets & Compliance Center.
ms.openlocfilehash: 33bfe3882c274fa655d17c80aba007e8d246b250
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199307"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Utgående och inkommande e-postflöde inblick i säkerhets-& Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Det **utgående och inkommande e-postflödet** inblickar i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i [säkerhets & Compliance Center](https://protection.office.com) kombinerar informationen från [kopplings rapporten](view-mail-flow-reports.md#connector-report) och den tidigare **TLS-översikten** på ett och samma ställe.

Widgeten visar TLS-kryptering som används för anslutningen när meddelanden levereras till och från din organisation. De anslutningar som upprättas med andra e-posttjänster krypteras av TLS när TLS erbjuds på båda sidor. Widgeten erbjuder en ögonblicks bild av den sista veckan i e-postflödet.

![Widget för utgående och inkommande e-post i instrument panelen för e-postflöde i säkerhets & Compliance Center](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

Informationen i widgeten är relaterad till kopplingar och skydd mot TLS-meddelanden i Microsoft 365. Mer information finns i följande avsnitt:

- [Konfigurera e-postflöde med kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Så här använder Exchange Online TLS för att skydda e-postanslutningar](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [Teknisk information om kryptering i Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a>Meddelande skyddat i transit (via TLS)

När du klickar på **Visa information** i widgeten visas TLS **-** skyddet för meddelanden som anger och lämnar din organisation.

![Meddelanden skyddade i transit (av TLS) utfällda som visas när du klickar på Visa information i widgeten utgående och inkommande e-post](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

För närvarande är TLS 1,2 den säkraste versionen av TLS som erbjuds av Microsoft 365. Du behöver ofta veta vilken TLS-kryptering som används för granskning av efterlevnad. Du har antagligen inget direkt förhållande till de flesta käll-och mål-e-postservrar (du inte äger dem och inte heller Microsoft), så du har inte många alternativ för att förbättra TLS-krypteringen som används av dessa servrar.

Men du kan använda [kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) för att se till att det bästa tillgängliga TLS-skyddet för meddelanden som skickas mellan dina e-postservrar och Microsoft 365. E-postflöde mellan Microsoft 365 och dina egna e-postservrar eller servrar som tillhör dina partners är ofta mer viktigare än vanliga meddelanden, så du bör tillämpa extra säkerhet och vaksamhet på dessa meddelanden.

Du kan uppgradera eller fixa dina egna e-postservrar för att förbättra den TLS-kryptering som används, eller nå dina partners för att göra det. I **kopplings rapporten** visas både mail flödes volym och TLS-kryptering för meddelanden som använder dina Microsoft 365-kopplingar.

Du kan klicka på **kopplings rapport** länken för att gå till [kopplings rapporten](view-mail-flow-reports.md#connector-report). Följande insikter kan vara tillgängliga på **kopplings rapport** sidan om det associerade villkoret har identifierats:

- **Inkommande partner Connector ser betydelsefullt TLS 1.0-e-postflöde**
- **Inkommande OnPremises-koppling som ser betydelsefullt TLS 1.0-e-postflöde**

För TLS 1,0-anslutningar måste du verkligen få e-postservern eller din partners server att uppgraderas eller åtgärdas för att undvika problem när stöd för TLS 1,0 är föråldrat i Microsoft 365.

## <a name="see-also"></a>Se även

Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).
