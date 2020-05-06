---
title: Dynamisk leverans och förhandsgranskning med ATP-säkra bilagor
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
description: När du ställer in principerna för betrodda bilagor i ATP väljer du Dynamisk leverans för att undvika meddelandefördröjningar och gör det möjligt för personer att förhandsgranska bifogade filer som genomsöks.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7c30803efd2dafedd6d988de5374f08bd61f7d2a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034798"
---
# <a name="dynamic-delivery-and-previewing-with-atp-safe-attachments"></a>Dynamisk leverans och förhandsgranskning med ATP-säkra bilagor

## <a name="overview"></a>Översikt

Dynamisk leverans är ett alternativ som kan väljas för [ATP Säkra bilagor](atp-safe-attachments.md). Läs den här artikeln om du vill veta mer om förhandsgranskningsfunktioner för dynamisk leverans och förhandsgranskning av bifogade filer i [ATP-säkra bilagor i Office 365](atp-safe-attachments.md).

När [ATP-principer](set-up-atp-safe-attachments-policies.md) för säkra bilagor har ställts in för din organisation finns det flera alternativ för hur e-postbilagor hanteras. Dessa inkluderar **Block,** **Ersätt**och **Dynamisk leverans**. Beroende på hur principer för betrodda bilagor konfigureras kan e-postmottagare uppleva en mindre fördröjning i e-postleveransen medan deras bilagor genomsöks. Om du vill undvika meddelandefördröjningar väljer du **Dynamisk leverans**.

## <a name="how-dynamic-delivery-works"></a>Så här fungerar dynamisk leverans

Dynamisk leverans eliminerar e-postförseningar genom att skicka brödtexten i ett e-postmeddelande till mottagaren med en platshållare för varje e-postbilaga. Platshållaren finns kvar tills en kopia av bilagan skannas och bedöms vara säker av [ATP Safe Attachments](atp-safe-attachments.md).

- När varje bifogad fil är avmarkerad kan den öppnas eller hämtas.

- Om en bifogad fil bedöms vara skadlig skickas den till karantän, där någon i organisationens säkerhetsteam (till exempel en global administratör eller säkerhetsadministratör) kan [hantera meddelanden i karantän i Office 365](manage-quarantined-messages-and-files.md).

De flesta PDF-filer och Office-dokument kan förhandsgranskas i felsäkert läge medan ATP-skanning pågår. Om en bifogad fil inte är kompatibel med förhandsgranskningen av dynamisk leverans ser e-postmottagare en platshållare för bifogade filer tills ATP-skanningen av säkra bilagor är klar.

> [!TIP]
> Om du använder en mobil enhet och PDF-filer inte återges i förhandsgranskning av dynamisk leverans först kan du prova att logga in med din mobila webbläsare.

Med dynamisk leverans kan användarna läsa och svara på sina e-postmeddelanden direkt, medan deras bilagor analyseras.

ATP-skanning av säkra bilagor sker i samma region där dina Microsoft 365-data finns. Mer information om datacentergeografi finns i [Var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All)

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>Vad händer när någon vidarebefordrar ett e-postmeddelande som innehåller en bifogad fil?

Anta att en organisation använder dynamisk leverans för sin [ATP-princip för säkra bilagor](set-up-atp-safe-attachments-policies.md)och att någon får ett e-postmeddelande som innehåller en bifogad fil. Anta nu att personen vidarebefordrar e-postmeddelandet till någon annan. Vad händer? Det beror på om ytterligare mottagare ingår i ATP:s principer för säkra bilagor.

- Om en mottagare omfattas av en ATP-princip för säkra bilagor med alternativet Dynamisk leverans ser mottagaren platshållaren med möjlighet att förhandsgranska kompatibla filer.

- Om en mottagare inte omfattas av en ATP Safe Attachments-policy går e-post- och bilagan igenom, utan att några platshållare för ATP-säkra bilagor skanning eller platshållare för bifogade filer.

## <a name="whats-required-for-dynamic-delivery-to-work"></a>Vad krävs för att dynamisk leverans ska fungera?

- Din organisation måste ha [avancerat hotskydd för Office 365](office-365-atp.md)

- Principer måste definieras för ATP-säkra bilagor med alternativet Dynamisk leverans (se [Konfigurera ATP-principer för säkra bilagor i Office 365](set-up-atp-safe-attachments-policies.md))

- Organisationens e-post måste finnas i Office 365. Även om [office 365 Advanced Threat Protection kan användas med alla SMTP-e-postöverföringsagenter](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (till exempel Exchange Server), kräver alternativet Dynamisk leverans för ATP-säkra bilagor att organisationens e-post finns i Office 365. Om din e-post inte finns i Office 365 väljer du ett annat [atp-principalternativ för säkra bilagor,](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options)till exempel **Blockera**.

## <a name="additional-considerations"></a>Ytterligare överväganden

Det finns vissa scenarier där dynamisk leverans inte stöds. Dessa inkluderar följande:

- E-postmeddelanden som finns i gemensamma mappar

- E-postmeddelanden som dirigeras ut ur och sedan tillbaka till användarens postlåda med hjälp av anpassade regler

- E-postmeddelanden som flyttas (automatiskt eller manuellt) från den värdbaserade postlådan och till andra platser, inklusive arkivmappar

- E-postmeddelanden som tas bort

- En användares sökmapp för postlådan som är i feltillstånd

- Miljöer där en Exchange Online-administratör har aktiverat Exclaimer. LÃ¶s problemet genom att se [Meddelanden med bifogade filer inte levereras nÃ¤r ATP Dynamic Delivery and Exclaimer](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)

- Meddelanden krypterade med [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))

- I de fall dynamisk leverans inte stöds kommer ATP Safe Attachments inte att skanna e-postmeddelanden. Att leverera e-postmeddelanden med bifogade filer som innehåller webbadresser kommer dock att kontrolleras, beroende på hur [principerna för ATP Safe Links](set-up-atp-safe-links-policies.md) är konfigurerade. I dessa fall kontrolleras webbadresser i e-postmeddelanden och Office-filer.
