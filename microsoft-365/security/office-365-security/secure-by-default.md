---
title: Säker som standard i Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Läs mer om den säkra inställningen som standard i Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a507abce8c18657794b56570241570e5048b89d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288519"
---
# <a name="secure-by-default-in-office-365"></a>Säker som standard i Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

"Säker som standard" är en term som används för att definiera vilka standardinställningar som är säkrast som möjligt.

Säkerheten måste dock balanseras med produktiviteten. Detta kan innefatta balans mellan:

- **Användbarhet:** Inställningar bör inte vara i vägen för användarnas produktivitet.
- **Risk:** Säkerheten kan blockera viktiga aktiviteter.
- **Äldre inställningar:** Vissa konfigurationer för äldre produkter och funktioner kan behöva underhållas av företagsskäl, även om nya, moderna inställningar förbättras.

Microsoft 365-organisationer med postlådor i Exchange Online skyddas av Exchange Online Protection (EOP). Skyddet omfattar:

- E-post med misstänkt skadlig programvara sätts automatiskt i karantän och mottagare meddelas. Se [Konfigurera principer för skydd mot skadlig programvara i EOP.](configure-anti-malware-policies.md)
- E-post som identifieras som nätfiske hanteras i enlighet med policyåtgärden mot skräppost. Se [Konfigurera principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)

Mer information om EOP finns i [Översikt över Exchange Online Protection.](exchange-online-protection-overview.md)

Eftersom Microsoft vill att våra kunder ska vara säkra som standard tillämpas inte vissa åsidosättningar av klientorganisationen för skadlig programvara eller nätfiske med hög konfidens. Dessa åsidosättningar omfattar:

- Tillåtna avsändarlistor eller listor över tillåtna domäner (principer för skydd mot skräppost)
- Betrodda avsändare i Outlook
- IP-lista över tillåtna (anslutningsfiltrering)

Mer information om dessa åsidosättningar finns i skapa [listor över betrodda avsändare.](create-safe-sender-lists-in-office-365.md)

> [!NOTE]
> Vi håller på att ta bort  åtgärden Flytta meddelandet till mappen  Skräppost för nätfiskeuttryck i EOP:s principer för skräppost. Principer för skydd mot skräppost som använder den här åtgärden för nätfiskemeddelanden med hög förtroende konverteras till **karantänmeddelande.** Åtgärden **Omdirigera meddelande till e-postadress** för nätfiskemeddelanden med hög konfidens påverkas inte.

Säker är som standard inte en inställning som kan aktiveras eller inaktiveras, men det är så filtreringen fungerar för att hålla potentiellt skadliga eller oönskade meddelanden borta från dina postlådor. Skadlig programvara och nätfiskemeddelanden med hög konfidens ska ha karantän. Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig kod eller nätfiske och de kan också rapportera falska positiva meddelanden till Microsoft därifrån. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Mer information om varför vi gör det här

Andan för att vara säker som standard är att vi vidtar samma åtgärd för meddelandet du skulle vidta om du visste att meddelandet var skadligt, även om ett konfigurerat undantag annars skulle tillåta att meddelandet levereras. Det här är samma metod som vi alltid använt för skadlig programvara, och nu utökar vi den här funktionen till nätfiskemeddelanden med hög säkerhet.

Våra data anger att en användare är 30 gånger mer sannolikt att klicka på en skadlig länk i meddelanden i mappen Skräppost kontra karantän. Våra data visar också att den falska positiva hastigheten (bra meddelanden som markerats som dåliga) för nätfiskemeddelanden med hög förtroende är mycket låg och administratörer kan lösa alla falska positiva resultat med administratörsinskickningar.

Vi kom också fram till att listorna för tillåtna avsändare och tillåtna domäner i principerna för skräppostskydd och Betrodda avsändare i Outlook var för breda och orsakade mer skada än nytta.

För att uttrycka det på ett annat sätt: som en säkerhetstjänst arbetar vi för att förhindra att dina användare komprometteras. 

## <a name="exceptions"></a>Undantag

Den enda åsidosättningen som tillåter nätfiskemeddelanden att kringgå filtrering är Exchange-e-postflödesregler (kallas även transportregler). Information om hur du använder e-postflödesregler för att kringgå filtrering finns i Använda [e-postflödesregler för att ange SCL i meddelanden.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

Du bör endast överväga att använda åsidosättningar i följande scenarier:

- Nätfiskebedrägerier: Simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar organisationen.
- Säkerhet/SecOps-postlådor: Dedikerade postlådor som används av säkerhetsgrupper för att få ofiltrerade meddelanden (både bra och dåliga). Teams kan sedan granska dem för att se om de innehåller skadligt innehåll.
- Filter från tredje part: Säker som standard gäller inte när domänens MX-post inte pekar på Office 365.
- Falska positiva resultat: Du kanske tillfälligt vill tillåta vissa meddelanden som fortfarande analyseras av Microsoft [via administratörsinskickningar.](admin-submission.md) Precis som med alla åsidosättningar rekommenderar vi att de är tillfälliga.
