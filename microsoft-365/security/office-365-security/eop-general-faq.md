---
title: Allmänna vanliga frågor och svar om EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Få svar på de vanligaste allmänna frågorna om e-postfiltreringstjänsten med Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04246b7c0a241c672328febd1584a56aa11becf2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207484"
---
# <a name="eop-general-faq"></a>Allmänna vanliga frågor och svar om EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
-  [Exchange Online Protection fristående](exchange-online-protection-overview.md)

Här svarar vi på de vanligaste allmänna frågorna om EOP (Exchange Online Protection) molnbaserad e-postfiltreringstjänst. Om du vill ha fler vanliga frågor och svar går du till följande länkar:

- [Vanliga frågor och svar om köade, uppskjutna och studsade meddelanden i EOP](eop-queued-deferred-and-bounced-messages-faq.md)

- [Vanliga frågor och svar om delegerad administration](delegated-administration-faq.md)

- [Vanliga frågor och svar om skydd mot skräppost](anti-spam-protection-faq.md)

- [Vanliga frågor och svar om karantän](quarantine-faq.md)

- [Vanliga frågor och svar om skydd mot skadlig kod](anti-malware-protection-faq-eop.md)

- [Vanliga frågor och svar om meddelandespårning](/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>Vad är EOP?

EOP är en molnbaserad tjänst för e-postfiltrering som är skapad för att skydda kunderna mot skräppost och skadlig programvara samt för att implementera regler för anpassade policyer. EOP ingår i alla Microsoft 365-prenumerationer som innehåller Exchange Online-postlådor. EOP finns även som fristående erbjudande för att skydda lokala e-postmiljöer.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>Hur registrerar jag mig för en utvärderingsversion av EOP eller köper EOP?

Registrera dig för en utvärderingsversion av EOP eller köp EOP via webben på startsidan för [Exchange Online Protection.](https://products.office.com/exchange/exchange-email-security-spam-protection) Observera att funktionerna för ett köp av utvärderingsversion är desamma som för en betald prenumeration, men även de ytterligare funktionerna som medföljer [Exchange Enterprise CAL med Services-abonnemanget.](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview)

## <a name="how-is-eop-priced"></a>Hur kostar EOP priset?

EOP licensieras av användaren. Den senaste prisinformationen finns på startsidan [för Exchange Online Protection.](https://products.office.com/exchange/exchange-email-security-spam-protection)

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>Hur lång tid tar det att sätta in EOP i produktion?

När du ändrar MX-posten enligt stegen som beskrivs i Konfigurera [din EOP-tjänst](set-up-your-eop-service.md), och e-postflöden via EOP, börjar filtreringen omedelbart. MX-posten kan ta upp till 24–48 timmar att spridas via DNS. Du kan finjustera skyddsinställningarna när som helst under den här processen.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>Måste jag använda alla funktioner i Microsoft 365 för att använda EOP? Vad gör jag om jag bara vill ha EOP-skydd?

Du kan använda EOP för att skydda dina lokala postlådor utan att använda andra funktioner i Microsoft 365. Det här kallas för en fristående prenumeration. En lista med EOP-funktioner finns i Tjänstbeskrivning för [Exchange Online Protection.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>Varför behöver jag en Microsoft 365-klientorganisation när jag registrerar mig för e-postfiltrering via EOP?

Microsoft 365 är namnet på en samling produkter och tjänster som kan kommas åt via en Microsoft 365-klientorganisation. Tänk på Microsoft 365-klientorganisationen som utgångspunkt för när du kan lägga till licenser för e-postfiltrering.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>Har EOP en kommunikationsportal där jag kan ta reda på kända problem och förväntade lösningar? Vad gäller för nya funktioner?

I administrationscentret för Microsoft 365 finns en del av den här informationen. Om en tjänstnivåhändelse påverkar dig bör du se en kommunikationsavisering (vanligtvis åtföljd av en klockikon) när du har loggat in på administrationscentret för Microsoft 365. Vi rekommenderar att du läser och agerar på eventuella objekt efter behov.

När det gäller nya EOP-funktioner är översikten över [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) för företag en bra resurs för att ta reda på information om kommande nya funktioner. Vi kommer även att publicera bloggartiklar om nya funktioner på [webbplatsen Microsoft 365-bloggar.](https://www.microsoft.com/microsoft-365/blog/)

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>Fungerar tjänsten med äldre Exchange-versioner (till exempel Exchange Server 2010) och icke-Exchange-miljöer?

Ja, tjänsten är server agnostic och kan användas med alla SMTP-ombud för e-postöverföring.

## <a name="what-size-organization-can-use-the-service"></a>Vilken storlek kan organisationen använda tjänsten?

Valfri storlek. EOP-nätverket har tillräcklig kapacitet för att klara tillväxten, oavsett hur snabbt organisationen växer.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>Vilka behörigheter behöver jag för att konfigurera EOP?

För att kunna konfigurera EOP måste du vara global administratör eller Exchange-företagsadministratör (rollgruppen Organisationshantering).

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>Hur vet jag att mina data och min privata information är säkra?

Om du vill ha mer information om de åtgärder vi har vidtagit för att säkerställa säkerheten för dina data och privat information, inklusive information om tjänstenivåavtal (SLAs), går du till [Office 365 Säkerhetscenter.](https://www.microsoft.com/trust-center)

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>Finns det några begränsningar som jag bör känna till, till exempel storleksbegränsningar för meddelanden?

Ja. Mer information om begränsningar i EOP finns i Begränsningar för [Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="does-eop-support-powershell"></a>Stöder EOP PowerShell?

Ja, fullständiga EOP-funktioner är tillgängliga via PowerShell: Exchange Online PowerShell för organisationer med Exchange Online-postlådor. fristående EOP PowerShell för fristående EOP-organisationer. Mer information finns i [Exchange Online PowerShell och](/powershell/exchange/exchange-online-powershell) Exchange Online Protection [PowerShell.](/powershell/exchange/exchange-online-protection-powershell)