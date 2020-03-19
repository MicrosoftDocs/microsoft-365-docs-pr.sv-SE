---
title: Vad är EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: Detta inledande dokument hjälper dig att förstå Exchange Online Protection (EOP) och några viktiga terminologi. Detta gäller för Office 365-kunder som skyddar Exchange Online-molnbaserade postlådor och EOP-fristående kunder som skyddar lokala postlådor som Exchange Server 2016.
ms.openlocfilehash: b1a8e9360005b31cf03c5e9921e3285ff7119926
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811124"
---
# <a name="what-is-exchange-online-protection-eop"></a>Vad är Exchange Online Protection (EOP)

Exchange Online Protection (EOP) är en molnbaserad e-postfiltreringstjänst som hjälper till att skydda din organisation mot skräppost och skadlig kod. Om du har postlådor i Office 365 skyddas de automatiskt av EOP eftersom det är en del av tjänsten. Detta inkluderar organisationer som har postlådor i både Office 365 och lokalt, vilket brukar kallas ett hybridscenario. EOP fristående är också tillgängligt för kunder som inte har postlådor i molnet men vill skydda sina lokala postlådor.

EOP försöker filtrera bort skräp, hålla inkorgen borta från innehåll som användarna inte vill se. Normalt levereras skräppost till mappen Skräppost. Vissa användare gillar att kontrollera att filtrering gör vad de vill så skräppost mappen är ett enkelt sätt för användare att kontrollera på egen hand.  

> [!TIP]
> Det är en bra sak när skräp eller på annat sätt dålig e-post går in i skräppostmappen automatiskt. Tjänsten kommer att göra vad som är nödvändigt baserat på vad standard- eller anpassade administratörsinställningarna anger. Med andra ord bör användarna inte oroa sig för att se en hel del skräppost i skräppostmappen. Om administratörer föredrar att flytta allt skräp utom synhåll, bör karantänen konfigureras. Mer information finns [i e-postmeddelandena karantän i Office 365.](quarantine-email-messages.md)

## <a name="important-terms"></a>Viktiga termer

**Inkommande**: Meddelanden som kommer till Office 365.

**Utgående**: Meddelanden som kommer ut från Office 365.

**Internt**: Meddelanden som kommer från någon inom organisationen till någon inom organisationen. Detta inkluderar kunder som är i hybridscenarier och en postlåda kan vara lokalt och den andra postlådan finns i molnet.

**False Negative (FN)**: Spam och annat skräp som felaktigt skickas in i inkorgen.

**Falskt positivt (FP)**: Legitima meddelanden som felaktigt får markeras som skräppost och sätts in i mappen Skräppost eller Karantän.

**Spam, även känd som oönskad e-post:** Detta kommer i form av kommersiell reklam, kedjebrev, politiska utskick, etc. Detta är e-post som användare inte registrerar sig för och från spammare som försöker värva produkter eller försöker begå bedrägeri.

**Phish**: Phishing är en speciell typ av spam som är avsedd att lura dig att ge upp personlig information i syfte att begå identitetsstöld eller bedrägeri. Den här typen av meddelande innehåller vanligtvis en skadlig länk eller bifogad fil, men inte alltid.

**Spoof:** Spoofing är när spammare smida FRÅN-huvudet så att meddelanden verkar ha sitt ursprung från någon eller någon annan än den faktiska källan. Detta kan vara spam men oftast används för att phish användare.

**Personifiering:** Denna typ av spam är också ett sätt att förfalska avsändaradressen, men det görs genom att ändra en del av namnet eller domänen så att den ser ut som den verkliga källan. Till exempel Bi11@micr0s0ft.com, där "l" i Bill var faktiskt nummer elva och "o" i Microsoft ersattes med numret noll.

**Bulk**: Bulk post är oftast efterfrågas av användare, men ibland indirekt när företag säljer information till andra företag. Det är vanligt att användare avsiktligt registrera dig för massutskick (dvs. newletters) men glömma senare och tycker att det är spam. Massutskick blir skräppost när massutskick skickar mer än användare registrerar sig och klagomålsnivåerna blir för höga.
