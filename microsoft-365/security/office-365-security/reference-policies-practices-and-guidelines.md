---
title: Referensprinciper, praxis och riktlinjer
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft har utvecklat olika policyer, procedurer och antagit flera branschbästa metoder för att skydda våra användare från kränkande, oönskade eller skadliga e-postmeddelanden.
ms.openlocfilehash: e6e5565b032af656b2204ce448581014595013de
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807941"
---
# <a name="reference-policies-practices-and-guidelines"></a>Referens: Principer, praxis och riktlinjer

Microsoft är dedikerade till att ge den mest betrodda användarupplevelsen på webben. Därför har Microsoft utvecklat olika policyer, procedurer och antagit flera branschbästa metoder för att skydda våra användare från kränkande, oönskade eller skadliga e-postmeddelanden. Avsändare som försöker skicka e-post till Office 365-användare bör se till att de förstår och följer vägledningen i den här artikeln för att hjälpa till i den här insatsen och för att undvika potentiella leveransproblem.

Om du inte följer dessa policyer och riktlinjer kanske det inte är möjligt för vårt supportteam att hjälpa dig. Om du följer de riktlinjer, metoder och policyer som presenteras i den här artikeln och fortfarande har leveransproblem baserat på din sändande IP-adress följer du stegen för att skicka en begäran om avnotering. Instruktioner finns i [Använda avlistningsportalen för att ta bort dig själv från listan blockerade avsändare i Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="general-microsoft-policies"></a>Allmänna Microsoft-principer

E-post som skickas till Office 365-användare måste följa alla Microsoft-policyer som styr överföring och användning av Office 365.

- Användarvillkor som gäller för Office 365; i synnerhet förbudet mot att använda tjänsten för att spamma eller distribuera

- [Microsoft-tjänsteavtal](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Statliga föreskrifter

E-post som skickas till Office 365-användare måste följa alla tillämpliga lagar och förordningar som styr e-postkommunikation i tillämplig jurisdiktion.

- [CAN-SPAM Act: En efterlevnadguide för företag](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- ["Ta bort mig" Svar och ansvar: E Marknadsförare måste hedra "Unsubscribe" Fordringar](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)

## <a name="technical-guidelines"></a>Tekniska riktlinjer

E-post som skickas till Office 365 bör följa de tillämpliga rekommendationerna i dokumenten nedan (vissa länkar är endast tillgängliga på engelska).

- [RFC 2505: Anti-Spam rekommendationer för SMTP MTAs](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP-servicetillägg för kommandopipelining](https://www.ietf.org/rfc/rfc2920.txt)

Dessutom måste e-postservrar som ansluter till Office 365 följa följande krav:

- Avsändaren förväntas uppfylla alla tekniska standarder för överföring av E-post på Internet, som publiceras av Internet Society's Internet Engineering Task Force (IETF), inklusive RFC 5321, RFC 5322 och andra.

- Efter att ha fått en numerisk SMTP-felsvarskod mellan 500 och 599 (även känd som ett permanent svar utan leverans eller NDR) får avsändaren inte försöka överföra meddelandet till mottagaren igen.

- Efter flera svar som inte har skickats måste avsändaren upphöra med ytterligare försök att skicka e-post till mottagaren.

- Meddelanden får inte överföras via osäkra e-postrelä- eller proxyservrar.

- Mekanismen för att avprenumerera, antingen från enskilda listor eller alla listor som finns av avsändaren, måste dokumenteras tydligt och vara lätt för mottagarna att hitta och använda.

- Anslutningar från dynamiskt IP-utrymme kanske inte accepteras.

- E-postservrar måste ha giltiga omvänd DNS-poster.

## <a name="reputation-management"></a>Rykte förvaltning

Avsändare, Internetleverantörer och andra tjänsteleverantörer bör aktivt hantera ryktet om dina utgående IP-adresser.

## <a name="office-365-limits"></a>Office 365-gränser

Avsändare måste följa Office 365-gränser som anges i [Exchange Online Protection Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="email-delivery-resources-and-organizations"></a>E-postleveransresurser och organisationer

Microsoft samarbetar aktivt med branschorganisationer och tjänsteleverantörer för att förbättra internet- och e-postekosystemet. Dessa organisationer har publicerat dokument för bästa praxis som vi stöder och rekommenderar avsändare följer. Detta förbättrar din förmåga att leverera e-post bland flera e-postleverantörer runt om i världen.

- [Meddelande Malware Mobile Anti-Abuse Arbetsgrupp](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.otalliance.org/resources)

- [Koalitionen för &amp; e-postavsändare](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Missbruk och rapportering av skräppost

Om du vill anmäla olaglig, stötande, oönskad e-post eller skadlig e-post kan du [rapportera skräppost och nätfiskebedrägerier i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Att skicka dessa typer av kommunikation är ett brott mot Microsofts policy och lämpliga åtgärder kommer att vidtas i bekräftade rapporter.

## <a name="law-enforcement"></a>Brottsbekämpande

Om du är medlem i brottsbekämpande myndigheter och vill tjäna Microsoft Corporation med juridisk dokumentation om Office 365, eller om du har frågor om juridisk dokumentation som du har skickat till Microsoft, ring (1) (425) 722-1299.
