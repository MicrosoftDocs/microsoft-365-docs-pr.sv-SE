---
title: Konfigurera och kontrollera extern vidarebefordran av e-post, automatisk vidarebefordran, 5.7.520 Åtkomst nekad, inaktivera extern vidarebefordran, Administratören har inaktiverat policyn för extern vidarebefordran och utgående skräppostskydd
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77f666e5eeceee3f5b324e5b9b6fac721c10e410
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286879"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Kontrollera automatisk vidarebefordran av extern e-post i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Som administratör kan du behöva begränsa eller styra automatiskt vidarebefordrade meddelanden till externa mottagare (mottagare utanför organisationen). Vidarebefordran av e-post kan vara användbart, men kan också utgöra en säkerhetsrisk på grund av potentiellt avslöjande av information. Attacker kan använda den här informationen för att attackerna mot organisationen eller partnern.


Följande typer av automatisk vidarebefordran är tillgängliga i Microsoft 365:

- Användare kan konfigurera [inkorgsregler](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) för att automatiskt vidarebefordra meddelanden till externa avsändare (avsiktligt eller som ett resultat av ett komprometterat konto).

- Administratörer kan konfigurera [vidarebefordran av postlådor](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (s.k. _SMTP-vidarebefordran)_ så att meddelanden vidarebefordras automatiskt till externa mottagare. Administratören kan välja om meddelanden bara ska vidarebefordras eller behålla kopior av vidarebefordrade meddelanden i postlådan.

Du kan använda principer för utgående skräppostfilter för att styra automatisk vidarebefordran till externa mottagare. Det finns tre inställningar:

- **Automatiskt:** Automatisk extern vidarebefordran blockeras. Internt automatisk vidarebefordran av meddelanden fortsätter att fungera. Detta är standardinställningen.
- **På:** Automatisk extern vidarebefordran är tillåtet och inte begränsat.
- **Av:** Automatisk extern vidarebefordran inaktiveras och resulterar i en rapport om utebliven leverans (kallas även NDR- eller icke-leveranskavstängningsmeddelande) till avsändaren.

Anvisningar om hur du konfigurerar de här inställningarna finns i [Konfigurera utgående skräppostfiltrering i EOP.](configure-the-outbound-spam-policy.md)

> [!NOTE]
>
> - Om du inaktiverar automatisk vidarebefordran inaktiveras alla inkorgsregler (användare) eller postlåde vidarebefordran (administratörer) som omdirigerar meddelanden till externa adresser.
>
> - Automatisk vidarebefordran av meddelanden mellan interna användare påverkas inte av inställningarna i principer för utgående skräppostfilter.
>
> - Du kan se information om användare som automatiskt vidarebefordrar meddelanden till externa mottagare i rapporten [Om automatiskt vidarebefordrade meddelanden.](mfi-auto-forwarded-messages-report.md)

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Så fungerar principinställningarna för utgående skräppostfilter med andra automatiska kontroller för vidarebefordran av e-post

Som administratör kanske du redan har konfigurerat andra kontroller för att tillåta eller blockera automatisk vidarebefordran av e-post. Till exempel:

- [Fjärrdomäner](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) för att tillåta eller blockera automatisk vidarebefordran av e-post till vissa eller alla externa domäner.

- Villkor och åtgärder i [Exchange-e-postflödesregler](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transportregler) för att identifiera och blockera automatiskt vidarebefordrade meddelanden till externa mottagare.

Fjärrdomäninställningar och e-postflödesregler är oberoende av inställningarna i principer för utgående skräppostfilter. Till exempel:

- Du tillåter automatisk vidarebefordran för en fjärrdomän, men du blockerar automatisk vidarebefordran i principer för utgående skräppostfilter. I det här exemplet blockeras automatiskt vidarebefordrade meddelanden.

- Du tillåter automatisk vidarebefordran i principer för utgående skräppostfilter, men du använder e-postflödesregler eller domäninställningar för fjärrdomäner för att blockera automatiskt vidarebefordrad e-post. I det här exemplet blockerar e-postflödesregler eller fjärrdomäninställningar automatiskt vidarebefordrade meddelanden.

Med det här funktionsoberoendet kan du (till exempel) tillåta automatisk vidarebefordran i principer för utgående skräppostfilter, men använda fjärrdomäner för att styra externa domäner som användare kan vidarebefordra meddelanden till.

## <a name="blocked-email-forwarding-messages"></a>Blockerade vidarebefordran av e-postmeddelanden

När ett meddelande identifieras som automatiskt vidarebefordrat och principen  för utgående skräppostfilter blockerar aktiviteten returneras meddelandet till avsändaren i en NDR som innehåller följande information: [](configure-the-outbound-spam-policy.md)

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
