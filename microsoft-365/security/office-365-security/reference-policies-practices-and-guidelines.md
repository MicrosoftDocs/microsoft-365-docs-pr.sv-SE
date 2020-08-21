---
title: Referens policy, praxis och rikt linjer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft har utvecklat olika policyer, procedurer och infört flera metod tips för att skydda våra användare mot grova och oönskade e-postmeddelanden.
ms.openlocfilehash: 13bc62f8be25a21f5ed2d1c2c2f4208a56d28bf0
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826523"
---
# <a name="reference-policies-practices-and-guidelines"></a>Referens: principer, övningar och riktlinjer

Microsoft värnar om att tillhandahålla den mest betrodda användar upplevelsen på webben. Därför har Microsoft utvecklat olika policyer, procedurer och infört flera metod tips för att skydda våra användare mot grova, oönskade och illasinnade e-postmeddelanden. Avsändare försöker skicka e-post till användarna så att de förstår och följer vägledningen i den här artikeln för att hjälpa till med att undvika potentiella leverans problem.

Om du inte uppfyller dessa principer och rikt linjer kan det vara omöjligt för vårt support team att hjälpa dig. Om du följer de rikt linjer, den praxis och de principer som visas i den här artikeln och fortfarande har problem med leveranserna baserat på din IP-adress, följer du anvisningarna för att skicka en begäran om registrering. Anvisningar finns i [använda List Portal för att ta bort dig själv från listan Spärrade avsändare](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="general-microsoft-policies"></a>Allmänna Microsoft-principer

E-post som skickas till Microsoft 365-användare måste uppfylla alla Microsoft-principer för e-postöverföring och användning av Microsoft 365.

- Villkor avseende tjänster som gäller för Microsoft 365; förbudet mot att använda tjänsten för att skicka skräp post eller distribuera skadlig program vara.

- [Villkor för Microsoft-tjänster](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Statliga bestämmelser

E-post som skickas till Microsoft 365-användare måste följa alla tillämpliga lagar och bestämmelser för e-postkommunikation under den tillämpliga jurisdiktionen.

- [KAN-skräp post Act: en guide för regelefterlevnad för företag](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- ["Ta bort mig"-svar och ansvars områden: e-marketers måste uppfylla "unsubscribe"-anspråk](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)

## <a name="technical-guidelines"></a>Tekniska rikt linjer

E-post som skickas till Microsoft 365 bör uppfylla rekommendationerna i följande dokument nedan (vissa länkar är bara tillgängliga på engelska).

- [RFC 2505: rekommendationer mot skräp post för SMTP MTAs](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP tjänst tillägg för kommando ledning](https://www.ietf.org/rfc/rfc2920.txt)

Dessutom måste e-postservrar som ansluter till Microsoft 365 uppfylla följande krav:

- Avsändaren förväntas uppfylla alla tekniska standarder för överföring av Internet-e-post, som publiceras av Internet samhällets Internet Engineering Task Force (IETF), inklusive RFC 5321, RFC 5322 och andra.

- Efter att ha fått en numerisk kod för en SMTP-felkod mellan 500 och 599 (kallas även för ett permanent icke-leverans svar eller NDR), får avsändaren inte försöka överföra meddelandet till den mottagaren.

- Efter flera svar som inte är leverans måste avsändaren upphöra med att skicka e-post till mottagaren.

- Meddelanden får inte överföras via ej säkra e-postrelän eller proxyservrar.

- Mekanismen för att avsluta prenumerationen, antingen från enskilda listor eller alla listor som hanteras av avsändaren, måste vara tydligt dokumenterad och lätt att hitta och använda.

- Anslutningar från dynamiskt IP-utrymme kanske inte accepteras.

- E-postservrar måste ha giltiga omvända DNS-poster.

## <a name="reputation-management"></a>Ryktes hantering

Avsändare, ISP och andra tjänste leverantörer bör aktivt hantera dina utgående IP-adresser.

## <a name="microsoft-365-limits"></a>Microsoft 365-begränsningar

Avsändare måste följa Microsoft 365-begränsningar i begränsningar för [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="email-delivery-resources-and-organizations"></a>Leverans resurser för e-post och organisationer

Microsoft aktivt samarbetar med bransch organ och tjänste leverantörer för att förbättra Internet-och e-postekoen. Dessa organisationer har publicerat metod dokument som vi stöder och rekommenderar att avsändare följer. Detta förbättrar möjligheten att skicka e-post till flera e-postleverantörer världen över.

- [Arbets grupp med skadlig program vara mobil anti-missbruk](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.otalliance.org/resources)

- [E-Coalition för & leverantör](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Rapportering av missbruk och skräp post

För att rapportera olagligt, skadligt, oönskat och skadligt e-postmeddelande, se [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md). Att skicka dessa typer av kommunikation är en överträdelse av Microsofts policy och lämplig åtgärd kommer att vidtas för bekräftade rapporter.

## <a name="law-enforcement"></a>Juridisk tillämpning

Om du är medlem i laglig användning och vill ha Microsoft Corporation med juridisk dokumentation om Office 365, eller om du har frågor om juridisk dokumentation som du har skickat till Microsoft, ringer du (1) (425) 722-1299.
