---
title: Säker som standard i Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Läs mer om inställningen säker som standard i Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c737647202e82af0fc217c0eadb3e2573d13a9b1
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177651"
---
# <a name="secure-by-default-in-office-365"></a>Säker som standard i Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

"Säker som standard" är en term som används för att definiera de standardinställningar som är säkrast möjliga.

Säkerheten måste dock balanseras med produktiviteten. Det kan till exempel vara balansering över:

- **Användbarhet:** Inställningar bör inte vara i vägen för användarnas produktivitet.
- **Risk:** Säkerheten kan blockera viktiga aktiviteter.
- **Äldre inställningar:** Vissa konfigurationer för äldre produkter och funktioner kan behöva underhållas av företagsskäl, även om nya, moderna inställningar har förbättrats.

Microsoft 365 organisationer med postlådor i Exchange Online skyddas av Exchange Online Protection (EOP). Det här skyddet omfattar:

- E-post med misstänkt skadlig programvara sätts automatiskt i karantän och mottagare meddelas. Se [Konfigurera principer för skydd mot skadlig programvara i EOP.](configure-anti-malware-policies.md)
- E-post som identifieras som nätfiske hanteras i enlighet med policyåtgärden mot skräppost. Se [Konfigurera principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)

Mer information om EOP finns i Exchange Online Protection [översikt.](exchange-online-protection-overview.md)

Eftersom Microsoft vill att våra kunder ska vara säkra som standard används inte vissa klientorganisations åsidosättningar för skadlig programvara eller nätfiske med hög säkerhet. Dessa åsidosättningar omfattar:

- Listor över tillåtna avsändare eller tillåtna domäner (principer som skydda mot skräppost)
- Outlook Valv avsändare
- Lista över tillåtna IP-adresser (anslutningsfiltrering)

Mer information om dessa åsidosättningar finns i Skapa [listor över betrodda avsändare.](create-safe-sender-lists-in-office-365.md)

> [!NOTE]
> Vi har tagit bort  åtgärden Flytta meddelandet till  mappen Skräppost för nätfiskeuttryck i EOP:s policy för skräppost. Principer för skydd mot skräppost som använder den här åtgärden för nätfiskemeddelanden med hög säkerhet konverteras till **karantänmeddelanden.** Åtgärden **Omdirigera meddelandet till e-postadress** för nätfiskemeddelanden med hög säkerhet påverkas inte.

Säker som standard är inte en inställning som kan aktiveras eller inaktiveras, men är det sätt som vår filtrering fungerar för att hålla potentiellt skadliga eller oönskade meddelanden från dina postlådor. Skadlig programvara och nätfiskemeddelanden med hög konfidens bör ha satts i karantän. Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig kod eller nätfiske med hög konfidens, och de kan också rapportera falska positiva meddelanden till Microsoft därifrån. Mer information finns i [Hantera meddelanden i karantän och filer som administratör i EOP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Mer information om varför vi gör detta

Andan med att vara säker som standard är: vi vidtar samma åtgärd för meddelandet som du skulle vidta om du visste att meddelandet var skadligt, även om ett konfigurerat undantag annars skulle tillåta att meddelandet levereras. Det här är samma metod som vi alltid har använt när vi använder skadlig programvara, och nu utökar vi denna funktion till att ge nätfiskemeddelanden med hög säkerhet.

Våra data anger att en användare är 30 gånger mer trolig att klicka på en skadlig länk i meddelanden i mappen Skräppost kontra Karantän. Våra data anger också att den falska positiva hastigheten (bra meddelanden som markerats som dåliga) för nätfiskemeddelanden är mycket låg och administratörer kan lösa alla falska positiva resultat med administratörsinskick.

Vi har också fastställt att listorna med tillåtna avsändare och tillåtna domäner i principer för skräppostskydd och Valv-avsändare i Outlook var för breda och orsakar mer skada än nytta.

Till att uttrycka det på ett annat sätt: som en säkerhetstjänst arbetar vi åt dig för att förhindra att dina användare komprometteras.

## <a name="exceptions"></a>Undantag

> [!NOTE]
> I augusti 2021 utökas säkerhet som standard till Exchange e-postflödesregler (kallas även transportregler). Om du använder e-postflödesregler för att tillåta nätfiskebedrägerier eller ofiltrerad leverans till postlådor för [](configure-advanced-delivery.md) säkerhetsåtgärd måste du så småningom eliminera dessa regler och byta till att använda den avancerade leveransprincipen när funktionen är tillgänglig för _dig._

Den enda åsidosättningen som tillåter nätfiskemeddelande med hög säkerhet att kringgå filtrering är e-postflödesregler. Information om hur du använder e-postflödesregler för att kringgå filtrering finns i [Använda e-postflödesregler för att ange SCL i meddelanden.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)

Du bör endast använda åsidosättningar i följande fall:

- Nätfiskebedrägerier: Simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar din organisation.
- Säkerhet/SecOps-postlådor: Dedikerade postlådor som används av säkerhetsteam för att få ofiltrerade meddelanden (både bra och dåliga). Teams kan sedan granska för att se om de innehåller skadligt innehåll.
- Filter från tredje part: Säker som standard gäller inte när domänens MX-post inte pekar på Office 365.
- Falska positiva resultat: Du kanske tillfälligt vill tillåta vissa meddelanden som fortfarande analyseras av Microsoft [via administratörsinskick.](admin-submission.md) Som med alla åsidosättningar rekommenderar vi att de är tillfälliga.
