---
title: Allmänna vanliga frågor och svar om EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Få svar på de vanligaste allmänna frågorna om tjänsten För molnbaserad e-postfiltrering av Exchange Online Protection (EOP).
ms.openlocfilehash: 0908fd5cf3a799f5a253122efac2b4d56d80ee76
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617036"
---
# <a name="eop-general-faq"></a>Allmänna vanliga frågor och svar om EOP

Här svarar vi på de vanligaste allmänna frågorna om EOP-molnfiltreringstjänsten (Exchange Online Protection). Mer information om vanliga frågor och svar finns i följande länkar:

- [Vanliga frågor och svar om köade, uppskjutna och studsade meddelanden i EOP](eop-queued-deferred-and-bounced-messages-faq.md)

- [Vanliga frågor och svar om delegerad administration](delegated-administration-faq.md)

- [Vanliga frågor om skydd mot skräppost](anti-spam-protection-faq.md)

- [Vanliga frågor och svar om karantän](quarantine-faq.md)

- [Vanliga frågor och svar om skydd mot skadlig kod](anti-malware-protection-faq-eop.md)

- [Vanliga frågor och svar om meddelandespårning](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>Vad är EOP?

EOP är en molnbaserad e-postfiltreringstjänst som är byggd för att skydda kunder från skräppost och skadlig kod och för att implementera anpassade principregler. EOP ingår i alla Microsoft 365-prenumerationer som innehåller Exchange Online-postlådor. EOP finns också som ett fristående erbjudande för att skydda lokala e-postmiljöer.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>Hur registrerar jag mig för en EOP-utvärderingsversion eller köper EOP?

Registrera dig för en EOP-utvärderingsversion eller köp EOP via webben på [Exchange Online Protection hemsida](https://products.office.com/exchange/exchange-email-security-spam-protection). Observera att funktionerna för ett provköp är desamma som för en betald prenumeration, men även de ytterligare funktioner som medföljer [Exchange Enterprise CAL med tjänster](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) prenumerationsplan.

## <a name="how-is-eop-priced"></a>Hur är EOP prissatt?

EOP är licensierat av användaren. Den senaste prisinformationen finns på [startsidan för Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection).

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>Hur lång tid tar det att sätta EOP i produktion?

När du ändrar MX-posten, enligt stegen i [Konfigurera din EOP-tjänst](set-up-your-eop-service.md)och din e-post flödar via EOP, börjar filtrningen omedelbart. MX-posten kan ta upp till 24-48 timmar att sprida via DNS. Du kan finjustera dina skyddsinställningar när som helst under den här processen.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>Måste jag använda alla funktioner i Microsoft 365 för att använda EOP? Tänk om jag bara vill ha EOP-skydd och det är allt?

Du kan använda EOP för att skydda dina lokala postlådor utan att använda några andra funktioner i Microsoft 365. Detta kallas en fristående prenumeration. En lista över EOP-funktioner finns i beskrivningen av [Exchange Online Protection Service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>Varför behöver jag en Microsoft 365-klient när jag registrerar mig för e-postfiltrering via EOP?

Microsoft 365 är namnet på en samling produkter och tjänster som kan nås via en Microsoft 365-klientorganisation. Tänk på Microsoft 365-klienten som utgångspunkt som du kan lägga till licenser för e-postfiltrering.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>Har EOP en kommunikationsportal där jag kan ta reda på kända problem och förväntade lösningar? Hur är det med nya funktioner?

Microsoft 365 admin center kommer att ha en del av denna information. Om du påverkas av en servicenivåhändelse bör du se en kommunikationsavisering (vanligtvis tillsammans med en klockikon) efter att du har loggat in på Microsoft 365-administrationscentret. Vi rekommenderar att du läser och agerar på alla objekt som är lämpliga.

När det gäller nya EOP-funktioner är [Microsoft 365 för företag en](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) bra resurs för att ta reda på information om kommande nya funktioner. Vi kommer också att publicera blogg artiklar om nya funktioner till [Microsoft 365 Bloggar](https://www.microsoft.com/microsoft-365/blog/) webbplats.

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>Fungerar tjänsten med äldre Exchange-versioner (till exempel Exchange Server 2010) och miljöer som inte är Exchange?

Ja, tjänsten är serveroberoende och kan användas med valfri SMTP-postöverföringsagent.

## <a name="what-size-organization-can-use-the-service"></a>Vilken storlek organisation kan använda tjänsten?

Vilken storlek som helst. EOP-nätverket har tillräcklig kapacitet för att tillgodose din tillväxt, oavsett hur snabbt din organisation växer.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>Vilka behörigheter behöver jag för att konfigurera EOP?

För att konfigurera EOP måste du vara global administratör eller exchange-företagsadministratör (rollgruppen Organisationshantering).

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>Hur vet jag att mina data och privata uppgifter är säkra?

Om du vill veta mer om de åtgärder vi har vidtagit för att säkerställa säkerheten för dina data och privat information, inklusive information om servicenivåavtal , går du till [Office 365 Trust Center](https://www.microsoft.com/trust-center).

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>Finns det några gränser som jag bör vara medveten om, till exempel begränsningar för meddelandestorlek?

Ja. Mer information om begränsningar i EOP finns i [Exchange Online Protection Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="does-eop-support-powershell"></a>Stöder EOP PowerShell?

Ja, fullständig EOP-funktionalitet är tillgänglig via PowerShell: Exchange Online PowerShell för organisationer med Exchange Online-postlådor; fristående EOP PowerShell för fristående EOP-organisationer. Mer information finns i [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) och [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell).
