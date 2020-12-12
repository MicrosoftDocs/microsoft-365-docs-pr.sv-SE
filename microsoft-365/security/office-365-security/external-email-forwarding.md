---
title: Konfigurera och kontrol lera extern e-postvidarekoppling, automatisk vidarebefordran, 5.7.520 åtkomst nekad, inaktivera extern vidarebefordran, administratören har inaktiverat extern vidarebefordran, utgående princip för skräp post
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 76cd560c3b97bb67d25d2e4ff2c219669c3d4f0d
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658887"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Kontrol lera automatisk extern e-postvidarebefordran i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Som administratör kan du ha företags krav för att begränsa eller kontrol lera automatiskt vidarebefordrade meddelanden till externa mottagare (mottagare utanför organisationen). Vidarebefordran av e-post kan vara ett användbart, men kan också utgöra en säkerhets risk på grund av den potentiella informationen. Angripare kan använda den här informationen för att attackera din organisation eller dina partners.

Följande typer av automatisk vidarebefordran är tillgängliga i Microsoft 365:

- Användare kan konfigurera [regler för Inkorgen](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) för att automatiskt vidarebefordra meddelanden till externa avsändare (avsiktligt eller som ett resultat av ett komprometterat konto).

- Administratörer kan konfigurera [vidarebefordran av post lådor](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (kallas även för _SMTP-vidarekoppling_) för att automatiskt vidarebefordra meddelanden till externa mottagare. Administratören kan välja om du bara vill vidarekoppla meddelanden eller Spara kopior av vidarebefordrade meddelanden i post lådan.

Du kan använda filter principer för utgående e-post för att styra automatisk vidarebefordran till externa mottagare. Tre inställningar är tillgängliga:

- **Automatisk**: Automatisk extern vidarebefordran är blockerad. Intern automatisk vidarebefordran av meddelanden fortsätter att fungera. Detta är standardinställningen.
- **Den**: Automatisk extern vidarebefordran är tillåten och inte begränsad.
- **Av**: Automatisk extern vidarebefordran är inaktiverat och resulterar i en rapport om utebliven leverans (kallas även för ett NDR-eller studs meddelande) för avsändaren.

Anvisningar om hur du konfigurerar dessa inställningar finns i [Konfigurera utgående skräp post filtrering i EOP](configure-the-outbound-spam-policy.md).

> [!NOTE]
>
> - Om du inaktiverar automatisk vidarebefordring inaktive ras eventuella regler för Inkorgen (användare) eller vidarebefordran av post lådor som omdirigerar meddelanden till externa adresser.
>
> - Automatisk vidarebefordran av meddelanden mellan interna användare påverkas inte av inställningarna i principer för skräp post filter.
>
> - Du kan se information om användare som automatiskt vidarebefordrar meddelanden till externa mottagare i [rapporten för automatiskt vidarebefordrade meddelanden](mfi-auto-forwarded-messages-report.md).

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Så fungerar princip inställningarna för utgående skräp post med andra kontroller för automatisk e-postvidarekoppling

Som administratör kan du ha konfigurerat andra kontroller för att tillåta eller blockera automatisk vidarebefordran av e-post. Till exempel:

- [Fjärrdomäner](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) för att tillåta eller blockera automatisk vidarebefordran av e-post till vissa eller alla externa domäner.

- Villkor och åtgärder i regler för Exchange [-postflöde](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transport regler) för att identifiera och blockera automatiskt vidarebefordrade meddelanden till externa mottagare.

Inställningar för fjärrdomäner och e-postflöde är oberoende av inställningarna i principer för skräp post filter. Till exempel:

- Du tillåter automatisk vidarebefordring för en fjärran sluten domän, men du blockerar automatisk vidarebefordran i filter principer för utgående e-post. I det här exemplet blockeras automatiskt vidarebefordrade meddelanden.

- Du tillåter automatisk vidarebefordran i principer för skräp post filter, men du använder regler för e-post och domän inställningar för att blockera automatiskt vidarebefordrade e-postmeddelanden. I det här exemplet blockerar inställningarna för e-postflöden eller fjärrdomäner automatiskt vidarebefordrade meddelanden.

Med den här funktionen kan du (till exempel) tillåta automatisk vidarebefordran i filter principer för utgående e-post, men Använd fjärrdomäner för att styra vilka externa domäner användarna kan vidarekoppla meddelanden till.

## <a name="the-blocked-email-forwarding-message"></a>Meddelande om blockerad e-post

När ett meddelande identifieras som automatiskt vidarebefordrat och organisations principen *blockerar* den aktiviteten, returneras meddelandet till avsändaren i en NDR som innehåller följande information:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
