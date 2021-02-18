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
description: Microsoft har utvecklat olika policyer, metoder och använder flera branschrekommendationer för att skydda våra användare från olämplig, oönskad eller skadlig e-post.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1065fdef5f804214ca48f7ca54170e6e417490d7
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289215"
---
# <a name="reference-policies-practices-and-guidelines"></a>Referens: principer, övningar och riktlinjer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft arbetar för att tillhandahålla den mest betrodda användarupplevelsen på webben. Därför har Microsoft utvecklat olika policyer, metoder och använder flera branschrekommendationer för att skydda våra användare från olämplig, oönskad eller skadlig e-post. Avsändare som försöker skicka e-post till användare bör se till att de är helt förstådda och följer hjälpen i den här artikeln för att hjälpa till med detta och för att undvika potentiella leveransproblem.

Om du inte följer dessa policyer och riktlinjer kanske det inte är möjligt för vårt supportteam att hjälpa dig. Om du följer riktlinjerna, metoderna och principerna som beskrivs i den här artikeln och fortfarande har leveransproblem baserat på din avsändande IP-adress följer du anvisningarna för att skicka en begäran om avlistning. Instruktioner finns i Använda [avlisteportalen för att ta bort dig själv från listan spärrade avsändare.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)

## <a name="general-microsoft-policies"></a>Allmänna Principer för Microsoft

E-post som skickas till Microsoft 365-användare måste följa Microsofts policyer för e-postöverföring och användning av Microsoft 365.

- Villkor för tjänster som gäller För Microsoft 365; i synnerhet att förbjuda användning av tjänsten för skräppost eller distribuera skadlig programvara.

- [Avtal för Microsoft-tjänster](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Myndighetsföreskrifter

E-post som skickas till Microsoft 365-användare måste följa alla tillämpliga lagar och bestämmelser som gäller för e-postkommunikation i tillämplig jurisdiktion.

- [CAN-SPAM Act: En regelefterlevnadsguide för företag](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- ["Remove Me" Responses and Responsibilities: Email Marketers must Honor "Unsubscribe" Claims](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>Tekniska riktlinjer

E-post som skickas till Microsoft 365 måste följa de tillämpliga rekommendationer som listas i dokumenten nedan (vissa länkar är endast tillgängliga på engelska).

- [RFC 2505: Rekommendationer mot skräppost för SMTP MTAs](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP-tjänsttillägg för kommandoledning](https://www.ietf.org/rfc/rfc2920.txt)

Dessutom måste e-postservrar som ansluter till Microsoft 365 följa följande krav:

- Avsändaren förväntas följa alla tekniska standarder för överföring av internet-e-post, som publicerats av IETF (Internet Engineering Task Force, Internet Engineering Force), inklusive RFC 5321, RFC 5322 och andra.

- Efter ett givet numeriskt SMTP-felsvar mellan 500 och 599 (kallas även permanent svar vid utebliven leverans eller NDR) får avsändaren inte försöka att skicka meddelandet igen till mottagaren.

- Efter flera icke-leveranssvar måste avsändaren sluta att försöka skicka e-post till den mottagaren.

- Meddelanden får inte skickas via oskyddat e-postrelä eller proxyservrar.

- Mekanismen för att avsluta prenumerationen, antingen från enskilda listor eller alla listor hos avsändaren, måste vara tydligt dokumenterad och lätt att hitta och använda för mottagarna.

- Anslutningar från dynamiskt IP-blanksteg kanske inte accepteras.

- E-postservrar måste ha giltiga omvända DNS-poster.

## <a name="reputation-management"></a>Rykteshantering

Avsändare, Internetleverantörer och andra tjänsteleverantörer bör aktivt hantera ryktet för dina utgående IP-adresser.

## <a name="microsoft-365-limits"></a>Begränsningar för Microsoft 365

Avsändare måste följa microsoft 365-begränsningar som finns i Exchange [Online Protection Limits.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)

## <a name="email-delivery-resources-and-organizations"></a>Resurser för e-postleverans och organisationer

Microsoft arbetar aktivt med branschorgan och tjänsteleverantörer för att förbättra internet- och e-postesystemen. Dessa organisationer har publicerat dokument med bästa praxis som vi ger support och rekommenderar avsändare följer. Det förbättrar möjligheten att leverera e-post bland flera olika e-postleverantörer över hela världen.

- [Messaging Malware Mobile – anti abuse working group](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.otalliance.org/resources)

- [E-postavsändare & leverantörsavsändare](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Rapportering av missbruk och skräppost

Om du vill rapportera olagliga, olämpliga, oönskade eller skadliga e-postmeddelanden, se [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md) Att skicka den här typen av kommunikation är ett brott mot Microsoft-principen och lämpliga åtgärder vidtas på bekräftade rapporter.

## <a name="law-enforcement"></a>Upprätthållande av lagar

Om du är medlem i lagens verkställande och vill hjälpa Microsoft Corporation med juridisk dokumentation om Office 365, eller om du har frågor om juridisk dokumentation du har skickat till Microsoft, kan du ringa (1) (425) 722-1299.
