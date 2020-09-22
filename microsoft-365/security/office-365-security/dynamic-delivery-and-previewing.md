---
title: Dynamisk leverans och förhands granskning med säkra filer för ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: När du ställer in dina principer för Safe Attachments via ATP väljer du dynamisk leverans för att undvika meddelande fördröjningar och göra det möjligt för användare att förhandsgranska bifogade filer som söks igenom.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0b19317babbd433ba0914ca2385cf6c9b40d89b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203041"
---
# <a name="dynamic-delivery-and-previewing-with-atp-safe-attachments"></a>Dynamisk leverans och förhands granskning med säkra filer för ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-dynamic-delivery"></a>Grundläggande funktioner för dynamisk leverans

Dynamisk leverans är ett alternativ som kan väljas för [säkra filer för ATP](atp-safe-attachments.md). Läs den här artikeln om du vill lära dig mer om funktionerna för förhands granskning av dynamisk leverans och för hands versioner i [Office 365](atp-safe-attachments.md).

När [ATP-principer för säker åtkomst är inställda](set-up-atp-safe-attachments-policies.md) för din organisation finns det flera alternativ för hur bifogade filer hanteras. Här ingår **blockering**, **ersättning**och **dynamisk leverans**. Beroende på hur du konfigurerar principer för säker åtkomst till bifogade filer kan e-postmottagarna få en mindre fördröjning i e-postleveransen medan deras bilagor genomsöks. För att undvika fördröjningar av meddelanden väljer du **dynamisk leverans**.

## <a name="how-dynamic-delivery-works"></a>Så fungerar dynamisk leverans

Dynamisk leverans eliminerar e-postfördröjningar genom att skicka bröd texten i ett e-postmeddelande till mottagaren med en plats hållare för varje bifogad fil. Plats hållaren fortsätter tills en kopia av den bifogade filen har skannats och bedöms vara säker av [säkra filer för säkerhet per ATP](atp-safe-attachments.md).

- När alla bifogade filer är avmarkerade kan de öppna eller ladda ner.

- Om en bifogad fil bedöms vara skadlig, skickas den till karantän, där någon i organisationens säkerhets team (till exempel en global administratör eller säkerhets administratör) kan [Hantera meddelanden i karantän i Office 365](manage-quarantined-messages-and-files.md).

De flesta PDF-filer och Office-dokument kan förhandsgranskas i fel säkert läge medan genomsökning av ATP pågår. Om en bifogad fil inte är kompatibel med förhands granskning för dynamisk leverans ser e-postmottagarna en bilage plats hållare tills ATP Safe Attachment scanning är klar.

> [!TIP]
> Om du använder en mobil enhet och PDF-filer inte återges i förhands granskning av dynamisk leverans först kan du försöka logga in med din mobil.

Med dynamisk leverans kan användarna läsa och svara på deras e-postmeddelanden direkt medan deras bifogade filer analyseras.

ATP Safe Attachments scanning sker i samma region där dina Microsoft 365-data finns. Mer information om data Center geografi finns i [var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All)

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>Vad händer när någon vidarebefordrar ett e-postmeddelande som innehåller en bifogad fil?

Anta att en organisation använder dynamisk leverans för att få en [policy för säkerhets](set-up-atp-safe-attachments-policies.md)skull med ATP och någon får ett e-postmeddelande som innehåller en bifogad fil. Antag att personen vidarebefordrar e-postmeddelandet till någon annan. Vad händer? Det beror på om de ytterligare mottagarna ingår i principer för säkra bifogade filer via ATP.

- Om en mottagare täcks av en policy för säker användning av ATP med alternativet dynamisk leverans ser mottagaren plats hållaren och kan förhandsgranska kompatibla filer.

- Om en mottagare inte täcks av en policy för säker e-postanvändning för ATP kommer e-postmeddelandet och bilagan att gå igenom, utan några extra säkerhets sökningar eller plats hållare för bifogade filer.

## <a name="whats-required-for-dynamic-delivery-to-work"></a>Vad krävs för att dynamisk leverans ska fungera?

- Din organisation måste ha [Office 365 Avancerat skydd](office-365-atp.md)

- Principer måste definieras för säkra filer för ATP med alternativet dynamisk leverans (mer information finns i [Konfigurera principer för säkra bifogade säkerhets brev i Office 365](set-up-atp-safe-attachments-policies.md))

- Din organisations e-postadress måste finnas med i Office 365. Trots att [Office 365 Avancerat skydd för e-post kan användas med valfri SMTP-överförings agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (till exempel Exchange Server) kräver alternativet för dynamisk leverans för säkerhets skull med ATP att organisationens e-postadress finns i Office 365. Om e-postmeddelandet inte finns i Office 365 väljer du ett annat [princip alternativ](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), till exempel **blockera**.

## <a name="additional-considerations"></a>Ytterligare överväganden

Det finns vissa scenarier där säkra bilagor (inklusive dynamisk leverans stöds inte). De omfattar:

- E-postmeddelanden i gemensamma mappar.

- E-postmeddelanden som omdirigeras från och sedan tillbaka till användarens post låda med anpassade regler.

- E-postmeddelanden som flyttas (automatiskt eller manuellt) från den värdbaserade post lådan och till andra platser, inklusive arkivmappar.

- E-postmeddelanden som tas bort.

- En användares sökmapp i post lådan är i fel tillstånd.

- Miljöer där en Exchange Online-administratör har aktiverat Exclaimer. För att lösa det här kan du läsa [meddelanden med bifogade filer levereras inte när du använder ATP-dynamisk leverans och Exclaimer](https://support.microsoft.com/help/4014438).

- Meddelanden krypterade med [S/MIME (Secure Multipurpose Internet Mail Extensions](s-mime-for-message-signing-and-encryption.md))).

- Om det inte finns stöd för dynamisk leverans genomsöks inte e-postmeddelanden. E-postmeddelanden med bifogade filer som innehåller URL: er kommer att kontrol leras, beroende på hur du har konfigurerat [principerna för Safet ATP-länkar](set-up-atp-safe-links-policies.md) . I de här fallen är URL-adresser i e-postmeddelanden och Office-filer markerade.
