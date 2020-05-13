---
title: Referenspolicyer, praxis och riktlinjer
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
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft har utvecklat olika policyer, procedurer och antagit flera metodtips för branschen för att skydda våra användare från stötande, oönskad eller skadlig e-post.
ms.openlocfilehash: 9684453503329e955c21051885c5d93e8c927c48
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208216"
---
# <a name="reference-policies-practices-and-guidelines"></a>Referens: principer, övningar och riktlinjer

Microsoft är dedikerade till att ge den mest betrodda användarupplevelsen på webben. Därför har Microsoft utvecklat olika policyer, procedurer och antagit flera branschtips för att skydda våra användare från stötande, oönskade eller skadliga e-postmeddelanden. Avsändare som försöker skicka e-post till användare bör se till att de förstår och följer anvisningarna i den här artikeln för att hjälpa till i den här insatsen och för att undvika potentiella leveransproblem.

Om du inte följer dessa policyer och riktlinjer kanske det inte är möjligt för vårt supportteam att hjälpa dig. Om du följer riktlinjerna, metoderna och policyerna som presenteras i den här artikeln och fortfarande har leveransproblem baserat på din sändande IP-adress följer du stegen för att skicka en begäran om avnotering. Instruktioner finns i [Använda avlistningsportalen för att ta bort dig själv från listan blockerade avsändare](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="general-microsoft-policies"></a>Allmänna Microsoft-policyer

E-post som skickas till Microsoft 365-användare måste följa alla Microsoft-policyer som styr e-postöverföring och användning av Microsoft 365.

- Villkor för tjänster som gäller för Microsoft 365; i synnerhet förbudet mot att använda tjänsten för att spamma eller distribuera skadlig kod.

- [Avtal om Microsoft-tjänster](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Statliga föreskrifter

E-post som skickas till Microsoft 365-användare måste följa alla tillämpliga lagar och förordningar som styr e-postkommunikation i tillämplig jurisdiktion.

- [CAN-SPAM Act: En efterlevnadsguide för företag](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- ["Ta bort mig" Svar och ansvar: E Marknadsförare måste Honor "Avsluta prenumerationen" Fordringar](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)

## <a name="technical-guidelines"></a>Tekniska riktlinjer

E-post som skickas till Microsoft 365 bör följa de tillämpliga rekommendationerna i dokumenten nedan (vissa länkar finns endast på engelska).

- [RFC 2505: Anti-Spam rekommendationer för SMTP MTAs](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP-tjänsttillägg för kommando pipelining](https://www.ietf.org/rfc/rfc2920.txt)

Dessutom måste e-postservrar som ansluter till Microsoft 365 uppfylla följande krav:

- Avsändaren förväntas uppfylla alla tekniska standarder för överföring av e-post på Internet, som publiceras av The Internet Society's Internet Engineering Task Force (IETF), inklusive RFC 5321, RFC 5322 och andra.

- Efter att ha gett en numerisk SMTP-felsvarskod mellan 500 och 599 (kallas även ett permanent svar än leverans eller NDR) får avsändaren inte försöka skicka meddelandet vidare till mottagaren.

- Efter flera svar som inte har levererats måste avsändaren upphöra med ytterligare försök att skicka e-post till mottagaren.

- Meddelanden får inte överföras via osäkra e-postrelä- eller proxyservrar.

- Mekanismen för avskrivning, antingen från enskilda listor eller alla listor som avsändaren hyser, måste vara tydligt dokumenterad och enkel för mottagarna att hitta och använda.

- Anslutningar från dynamiskt IP-utrymme kanske inte accepteras.

- E-postservrar måste ha giltiga omvända DNS-poster.

## <a name="reputation-management"></a>Hantering av anseende

Avsändare, Internet-leverantörer och andra tjänsteleverantörer bör aktivt hantera ryktet för dina utgående IP-adresser.

## <a name="microsoft-365-limits"></a>Microsoft 365-gränser

Avsändare måste följa Microsoft 365-gränser som anges i [Exchange Online Protection Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="email-delivery-resources-and-organizations"></a>Resurser och organisationer för e-postleverans

Microsoft arbetar aktivt med branschorgan och tjänsteleverantörer för att förbättra internet- och e-postekosystemet. Dessa organisationer har publicerat dokument med bästa praxis som vi stöder och rekommenderar avsändare att följa. Detta förbättrar din förmåga att leverera e-post bland flera e-postleverantörer runt om i världen.

- [Messaging Malware Mobile Anti-Abuse Arbetsgrupp](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.otalliance.org/resources)

- [E-postavsändare & Provider Coalition](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Rapportering av missbruk och skräppost

Om du vill rapportera olaglig, stötande, oönskad eller skadlig e-post läser du [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md). Att skicka dessa typer av kommunikation är ett brott mot Microsofts policy, och lämpliga åtgärder kommer att vidtas på bekräftade rapporter.

## <a name="law-enforcement"></a>Brottsbekämpande

Om du är medlem i polisen och vill betjäna Microsoft Corporation med juridisk dokumentation om Office 365, eller om du har frågor om juridisk dokumentation som du har skickat till Microsoft, ring (1) (425) 722-1299.
