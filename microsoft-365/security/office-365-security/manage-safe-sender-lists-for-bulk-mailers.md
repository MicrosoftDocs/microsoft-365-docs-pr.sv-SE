---
title: Hantera säkra avsändarlistor för massutskick
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 'Om du vill använda listor över betrodda avsändare bör du veta att Exchange Online Protection (EOP) och Outlook hanterar bearbetningen på olika sätt. Tjänsten respekterar betrodda avsändare och domäner genom att granska RFC 5321.MailFrom-adressen och RFC 5322.From-adressen, medan Outlook lägger till RFC 5322.From-adressen till en användares säkra avsändarelista. (Obs: Tjänsten inspekterar både 5321.MailFrom-adressen och 5322.From-adressen för blockerade avsändare och domäner.)'
ms.openlocfilehash: aaede7cab2e640603c20804f4015e19f61b6c2f3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812604"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>Hantera säkra avsändarlistor för massutskick

Om du vill använda listor över betrodda avsändare bör du veta att Exchange Online Protection (EOP) och Outlook hanterar bearbetningen på olika sätt. Office 365-tjänsten respekterar betrodda avsändare och `RFC 5321.MailFrom` domäner `RFC 5322.From` genom att granska `RFC 5322.From` adressen och adressen, medan Outlook lägger till adressen i en användares säkra avsändare. (Obs: Tjänsten inspekterar `5321.MailFrom` både `5322.From` adress och adress för blockerade avsändare och domäner.)

Adressen, `SMTP MAIL FROM` även känd `RFC 5321.MailFrom address`som , är den e-postadress som används för att utföra SPF-kontroller, och om e-postmeddelandet inte kan levereras, sökvägen som det studsade meddelandet levereras till. Det är den här e-postadressen `Return-Path` som placeras i meddelanderubrikerna som standard, men det är `Return-Path` möjligt för avsändaren att ange en annan adress.

Adressen `From:` i meddelanderubrikerna, även känd `RFC 5322.From` som adressen, är den e-postadress som visas i e-postklienten, till exempel Outlook.

Mycket av tiden, `5321.MailFrom` `5322.From` och adresser är desamma. Detta är typiskt för person-till-person kommunikation. Men när e-post skickas på uppdrag av någon annan, är adresserna ofta olika. Detta händer oftast oftast för massmeddelanden.

Anta till exempel att Blue Yonder Airlines har anlitat Margie's Travel för att skicka ut sin e-postreklam. Du får sedan ett meddelande i inkorgen från avsändare blueyonder@news.blueyonderairlines.com. I det här exemplet:

- Adressen `5321.MailFrom` är blueyonder.airlines@margiestravel.com.

- Adressen `5322.From` är blueyonder@news.blueyonderairlines.com, vilket är vad du ser i Outlook.

Om du vill förhindra att det här meddelandet filtreras kan du:

- **Som användare**: `RFC 5322.From` Lägg till adressen som en säker avsändare i Outlook.

- **Som administratör**: Ställ in en [regel för e-postflöde](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (kallas även transportregel).
