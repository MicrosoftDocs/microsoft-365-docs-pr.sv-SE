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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Få svar på vanliga allmänna frågor om Exchange Online Protection (EOP)-Server för e-postfiltrering.
ms.openlocfilehash: 42162ea841f876fc5e958d67fab61dbe4bffe9de
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827767"
---
# <a name="eop-general-faq"></a>Allmänna vanliga frågor och svar om EOP

Här svarar de vanligaste allmänna frågorna om Exchange Online Protection (EOP)-Server för e-postfiltrering. Information om fler vanliga frågor och svar finns i följande länkar:

- [Vanliga frågor och svar om köade, uppskjutna och studsade meddelanden i EOP](eop-queued-deferred-and-bounced-messages-faq.md)

- [Vanliga frågor och svar om delegerad administration](delegated-administration-faq.md)

- [Vanliga frågor om skydd mot skräppost](anti-spam-protection-faq.md)

- [Vanliga frågor och svar om karantän](quarantine-faq.md)

- [Vanliga frågor och svar om skydd mot skadlig kod](anti-malware-protection-faq-eop.md)

- [Vanliga frågor om meddelande spårning](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>Vad är EOP?

EOP är en molnbaserad e-postfiltrerande tjänst som skyddar kunder mot skräp post och skadlig program vara, samt för att implementera anpassade policy regler. EOP ingår i alla Microsoft 365-abonnemang som innehåller Exchange Online-postlådor. EOP finns också som en fristående tjänst för att skydda lokala e-postmiljöer.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>Hur registrerar jag mig för en utvärderings version av EOP eller EOP?

Registrera dig för en EOP utvärderings version eller köp EOP via webben på [Start sidan för Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection). Observera att funktionerna för ett prov köp är desamma som för en betald prenumeration, men inkluderar också de ytterligare funktioner som tillhandahålls med [Exchange Enterprise CAL med abonnemang för tjänster](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) .

## <a name="how-is-eop-priced"></a>Hur kostar EOP?

EOP är licensierad av användare. Den senaste pris informationen finns på [Start sidan för Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection).

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>Hur lång tid tar det att sätta EOP i produktionen?

När du ändrar MX-posten, enligt anvisningarna i [Konfigurera EOP-tjänsten](set-up-your-eop-service.md)och dina e-postflöden genom EOP, börjar filtreringen omedelbart. MX-posten kan ta så lång tid som 24-48 timmar att spridas via DNS. Du kan när som helst finjustera dina skydds inställningar under den här processen.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>Måste jag använda alla funktioner i Microsoft 365 för att använda EOP? Vad gör jag om jag vill ha EOP skydd och det är allt?

Du kan använda EOP för att skydda dina lokala post lådor utan att använda några andra funktioner i Microsoft 365. Detta kallas för en fristående prenumeration. En lista med EOP-funktioner finns i beskrivningen av [Exchange Online Protection Service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>Varför behöver jag en Microsoft 365-klient för att registrera dig för e-postfiltrering via EOP?

Microsoft 365 är det namn som ges till en samling produkter och tjänster som kan nås via en Microsoft 365-klient organisation. Microsoft 365-klient organisationen som utgångs punkt för att lägga till licenser för e-postfiltrering.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>Har EOP en kommunikations portal där jag kan få veta mer om kända problem och uppskattade lösningar? Vad har du för funktioner?

Administrations centret för Microsoft 365 har viss information. Om du påverkas av en tjänst nivå händelse bör du se en kommunikations varning (som normalt åtföljs av en klock ikon) efter att du har loggat in på administrations centret för Microsoft 365. Vi rekommenderar att du läser och vidtar lämpliga objekt.

För nya EOP-funktioner är [Microsoft 365 för Business-översikt](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) en bra resurs för att få information om kommande nya funktioner. Vi kommer även att skicka blogg artiklar om nya funktioner till webbplatsen [Microsoft 365-Bloggar](https://www.microsoft.com/microsoft-365/blog/) .

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>Fungerar tjänsten med äldre Exchange-versioner (till exempel Exchange Server 2010) och miljöer utanför Exchange?

Ja, tjänsten är Server oberoende och kan användas med valfri SMTP-överförings agent.

## <a name="what-size-organization-can-use-the-service"></a>Vilken storlek organisationen kan använda tjänsten?

Valfri storlek. EOP-nätverket har tillräckligt med kapacitet för tillväxt, oavsett hur snabbt organisationen växer.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>Vilka behörigheter behöver jag för att konfigurera EOP?

För att kunna konfigurera EOP måste du vara global administratör eller administratör för Exchange-företag (roll gruppen organisations hantering).

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>Hur vet jag att min data och privata information är säker?

Om du vill veta mer om de åtgärder vi har fattat för att säkerställa säkerheten hos dina data och privata uppgifter, inklusive information om service nivå avtal (SLAs), går du till [Office 365 säkerhets Center](https://www.microsoft.com/trust-center).

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>Finns det några begränsningar Jag bör känna till, till exempel storleks begränsningar för meddelanden?

Ja. Mer information om begränsningar i EOP finns i [begränsningar för Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="does-eop-support-powershell"></a>Stöder EOP PowerShell?

Ja, fullständiga funktioner för EOP är tillgängliga via PowerShell: Exchange Online PowerShell för organisationer med Exchange Online-postlådor. fristående EOP PowerShell för fristående EOP-organisationer. Mer information finns i [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) och [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell).
