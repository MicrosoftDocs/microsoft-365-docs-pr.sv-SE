---
title: Information om utgående och inkommande e-postflöde på instrumentpanelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Administratörer kan läsa mer om information om utgående och inkommande e-postflöde på instrumentpanelen för e-postflöde i säkerhets- & Efterlevnadscenter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fcce6981369217f21ace5fdf2abbf23ca8606569
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150814"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Information om utgående och inkommande e-postflöde i Säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Instrumentpanelen **för e-postflöde** i [](mail-flow-insights-v2.md) efterlevnadscentret för [& utgående](https://protection.office.com) och inkommande [](view-mail-flow-reports.md#connector-report) e-post i instrumentpanelen för e-postflöde kombinerar informationen från kopplingsrapporten och den tidigare **TLS-översiktsrapporten** på ett och samma ställe.

Widgeten visar den TLS-kryptering som används för anslutningen när meddelanden levereras till och från din organisation. Anslutningarna som upprättas med andra e-posttjänster krypteras av TLS när TLS erbjuds av båda sidor. Widgeten ger en ögonblicksbild av den senaste veckans e-postflöde.

![Widget för utgående och inkommande e-postflöde på instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

Informationen i widgeten är relaterad till kopplingar och TLS-meddelandeskydd i Microsoft 365. Mer information finns i följande avsnitt:

- [Konfigurera e-postflöde med kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Hur Exchange Online använder TLS för att skydda e-postanslutningar](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [Teknisk referensinformation om kryptering i Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a>Meddelande som skyddas under transport (av TLS)

När du klickar **på Visa** information på widgeten visas TLS-skyddet för meddelanden som matas in och lämnar organisationen i det meddelande som skyddas under överföring **(av TLS).**

![Meddelanden skyddade under överföring (av TLS) som visas när du klickar på Visa information på widgeten Utgående och inkommande e-post](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

För närvarande är TLS 1.2 den säkraste versionen av TLS som erbjuds av Microsoft 365. Ofta måste du känna till den TLS-kryptering som används för granskningar av efterlevnad. Du har förmodligen inte en direkt relation med de flesta käll- och mål-e-postservrarna (du äger dem inte och Microsoft har det inte), så du har inte många alternativ för att förbättra den TLS-kryptering som används av de servrarna.

Men du kan använda kopplingar [för](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) att säkerställa bästa tillgängliga TLS-skydd för meddelanden som skickas mellan dina e-postservrar och Microsoft 365. E-postflödet mellan Microsoft 365 och dina egna e-postservrar eller servrar som tillhör dina partner är ofta viktigare och känsligare än vanliga meddelanden, så du bör tillämpa extra säkerhet och uppmärksamhet på dessa meddelanden.

Du kan uppgradera eller åtgärda dina egna e-postservrar för att förbättra den TLS-kryptering som används, eller kontakta dina partners för att göra samma sak. I **anslutningsrapporten visas** både e-postflödesvolym och TLS-kryptering för meddelanden som använder dina Microsoft 365-kopplingar.

Du kan klicka på **kopplingens rapportlänk** för att gå till [kopplingsrapporten.](view-mail-flow-reports.md#connector-report) Följande information kan vara tillgänglig på sidan **med kopplingsrapporten** om det associerade villkoret har upptäckts:

- **Inkommande partneranslutning ser ett betydande TLS1.0-e-postflöde**
- **Inkommande OnPremises-koppling ser betydande TLS1.0-e-postflöde**

För TLS 1.0-anslutningar måste du få din e-postserver eller din partners server uppgraderad eller åtgärdad för att undvika problem när TLS 1.0-supporten så småningom är inaktuell i Microsoft 365.

## <a name="see-also"></a>Se även

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)
