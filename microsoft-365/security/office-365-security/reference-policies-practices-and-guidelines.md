---
title: Referensprinciper, metoder och riktlinjer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft har utvecklat olika policyer, metoder och använder flera branschtips för att skydda våra användare från olämplig, oönskad eller skadlig e-post.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f1a71b891829a2c9ea31502342c855db4126a6b5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207154"
---
# <a name="reference-policies-practices-and-guidelines"></a>Referens: principer, övningar och riktlinjer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft arbetar för att ge bästa sätt att använda användarna på webben. Därför har Microsoft utvecklat olika policyer, metoder och använder flera branschtips för att skydda användarna från olämplig, oönskad eller skadlig e-post. Avsändare som försöker skicka e-post till användare bör se till att de förstår allt och följer vägledning i den här artikeln för att bidra till detta arbete och för att undvika potentiella leveransproblem.

Om du inte följer dessa policyer och riktlinjer, kan det hända att vårt supportteam inte kan hjälpa dig. Om du följer riktlinjerna, metoderna och principerna som presenteras i den här artikeln och fortfarande har leveransproblem baserat på din avsändande IP-adress följer du anvisningarna för att skicka en avlistningsbegäran. Instruktioner finns i Använda [delist-portalen för att ta bort dig själv från listan med spärrade avsändare.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)

## <a name="general-microsoft-policies"></a>Allmänna Microsoft-policyer

E-post som Microsoft 365 till användare måste följa Microsofts policyer som reglerar e-postöverföring och användning av Microsoft 365.

- Villkor för tjänster som gäller Microsoft 365; i synnerhet att förbjuda användning av tjänsten för skräppost eller distribuera skadlig programvara.

- [Avtal för Microsoft-tjänster](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Statliga bestämmelser

E-post som Microsoft 365 till användare måste följa alla tillämpliga lagar och bestämmelser som gäller för e-postkommunikation i tillämplig jurisdiktion.

- [CAN-SPAM Act: En regelefterlevnadsguide för företag](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- ["Ta bort mig" Svar och ansvarsområden: E-postmarknadare måste avbryta prenumerationen](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>Tekniska riktlinjer

E-post som Microsoft 365-post bör följa de tillämpliga rekommendationer som anges i dokumenten nedan (vissa länkar är endast tillgängliga på engelska).

- [RFC 2505: skydd mot Rekommendationer för SMTP-MTAs](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP-tjänsttillägg för kommandoledning](https://www.ietf.org/rfc/rfc2920.txt)

Dessutom måste e-postservrar som ansluter Microsoft 365 måste följa följande krav:

- Sender is expected to comply with all technical standards for the transmission of Internet email, as published by The InternetLock's Internet Engineering Task Force (IETF), including RFC 5321, RFC 5322, and others.

- Efter att ha fått en numerisk SMTP-felsvarskod mellan 500 och 599 (kallas även permanent svar om utebliven leverans eller NDR), får avsändaren inte försöka att göra om meddelandet till mottagaren.

- När flera svar inte har levereras måste avsändaren upphöra med fler försök att skicka e-post till den mottagaren.

- Meddelanden får inte skickas via oskyddat e-postrelä eller proxyservrar.

- Mekanismen för att ta bort prenumerationen, antingen från enskilda listor eller alla listor hos avsändaren, måste vara tydligt dokumenterad och lätt att hitta och använda för mottagarna.

- Anslutningar från dynamiskt IP-utrymme kanske inte accepteras.

- E-postservrar måste ha giltiga omvända DNS-poster.

## <a name="reputation-management"></a>Rykteshantering

Avsändare, Internetleverantör och andra tjänsteleverantörer bör aktivt hantera ryktet för dina utgående IP-adresser.

## <a name="microsoft-365-limits"></a>Microsoft 365 begränsningar

Avsändarna måste följa de Microsoft 365 som anges i [Exchange Online Protection Begränsningar](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="email-delivery-resources-and-organizations"></a>Resurser för e-postleverans och organisationer

Microsoft samarbetar aktivt med branschorgan och tjänsteleverantörer för att förbättra internet- och e-poste-ekosystemet. Dessa organisationer har publicerat dokument med bästa praxis som vi ger support och rekommenderar avsändare följer. Det förbättrar möjligheten att leverera e-post mellan flera olika e-postleverantörer över hela världen.

- [Messaging Malware Mobile Anti-Abuse Working Group](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.internetsociety.org/ota/)

- [E-postavsändarpost & Provider Enl.](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Missbruks- och skräppostrapportering

Om du vill rapportera olagliga, olämpliga, oönskade eller skadliga e-postmeddelanden, [se Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md) Att skicka dessa typer av kommunikation är ett brott mot Microsofts policy och lämpliga åtgärder vidtas på bekräftade rapporter.

## <a name="law-enforcement"></a>Upprätthållande av rättslagstiftning

Om du är medlem i juridiken och vill tjäna Microsoft Corporation med juridisk dokumentation om Office 365, eller om du har frågor om juridisk dokumentation som du har skickat till Microsoft, kan du ringa (1) (425) 722-1299.