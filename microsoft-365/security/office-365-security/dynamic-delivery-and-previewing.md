---
title: Dynamisk leverans och förhandsgranskning med Office 365 ATP-säkra bilagor
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
description: När du konfigurerar dina principer för betrodda bifogade filer i ATP väljer du Dynamisk leverans för att undvika fördröjningar i meddelandet och gör det möjligt för personer att förhandsgranska bifogade filer som genomsöks.
ms.openlocfilehash: 755a5a317710946a3a03004482a6b48c8947c1a7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42809347"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>Dynamisk leverans och förhandsgranskning med Office 365 ATP-säkra bilagor

## <a name="overview"></a>Översikt

Dynamisk leverans är ett alternativ som kan väljas för [ATP-säkra bilagor](atp-safe-attachments.md). Läs den här artikeln om du vill veta mer om förhandsgranskning av dynamiska leverans- och bifogade filer i [ATP-säkra bilagor i Office 365](atp-safe-attachments.md).

När [principer för betrodda bifogade filer för ATP har konfigurerats](set-up-atp-safe-attachments-policies.md) för din organisation finns det flera alternativ för hur e-postbilagor hanteras. Dessa inkluderar **Block,** **Ersätt**och **dynamisk leverans**. Beroende på hur principer för a-postbilagor konfigureras kan e-postmottagare uppleva en mindre fördröjning i e-postleveransen medan deras bilagor skannas. Om du vill undvika fördröjningar i meddelandet väljer du **Dynamisk leverans**.

## <a name="how-dynamic-delivery-works"></a>Så här fungerar dynamisk leverans

Dynamisk leverans eliminerar e-postfördröjningar genom att skicka brödtexten i ett e-postmeddelande till mottagaren med en platshållare för varje e-postbilaga. Platshållaren förblir tills en kopia av tillbehöret skannas och bestäms vara säker av [ATP Safe Attachments](atp-safe-attachments.md).

- Eftersom varje bifogad fil rensas är den tillgänglig för att öppna eller hämta.

- Om en bifogad fil bedöms vara skadlig skickas den till karantän, där någon i organisationens säkerhetsteam (till exempel en global Office 365-administratör eller säkerhetsadministratör) kan [hantera meddelanden i karantän i Office 365](manage-quarantined-messages-and-files.md).

De flesta PDF-filer och Office-dokument kan förhandsgranskas i felsäkert läge medan ATP-skanning pågår. Om en bifogad fil inte är kompatibel med förhandsgranskningen av dynamisk leverans ser e-postmottagarna en platshållare för bifogade filer tills ATP Safe Attachments-skanningen är klar.

> [!TIP]
> Om du använder en mobil enhet och PDF-filer inte återges i förhandsgranskningen av dynamisk leverans först kan du prova att logga in på Office 365 med hjälp av din mobila webbläsare.

Med dynamisk leverans kan andra läsa och svara på sina e-postmeddelanden direkt, medan deras bilagor analyseras.

Sökning av betrodda bifogade filer på ATP sker i samma region där dina Office 365-data finns. Mer information om datacentergeografi finns i [Var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All)

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>Vad händer när någon vidarebefordrar ett e-postmeddelande som innehåller en bifogad fil?

Anta att en organisation använder dynamisk leverans för sin [ATP Safe Attachments-princip](set-up-atp-safe-attachments-policies.md)och att någon får ett e-postmeddelande som innehåller en bifogad fil. Anta nu att personen vidarebefordrar e-postmeddelandet till någon annan. Vad händer? Det beror på om de ytterligare mottagarna ingår i ATP Safe Attachments-principer.

- Om en mottagare omfattas av en ATP-princip för säkra bilagor med alternativet Dynamisk leverans ser mottagaren platshållaren, med möjlighet att förhandsgranska kompatibla filer.

- Om en mottagare inte omfattas av en ATP Safe Attachments-policy kommer e-postmeddelandet och bilagan att gå igenom, utan att någon PLATShållare för betrodda bifogade filer eller tillbehör skannas eller tillbehörsplatshållare.

## <a name="whats-required-for-dynamic-delivery-to-work"></a>Vad krävs för att dynamisk leverans ska fungera?

- Din organisation måste ha [Office 365 Advanced Threat Protection](office-365-atp.md)

- Principer måste definieras för ATP-säkra bilagor med alternativet Dynamisk leverans (se [Konfigurera principer för betrodda bifogade filer i ATP i Office 365](set-up-atp-safe-attachments-policies.md))

- Organisationens e-post måste finnas i Office 365. Även om [Office 365 Advanced Threat Protection kan användas med alla SMTP-e-postöverföringsagenter](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (till exempel Exchange Server), kräver alternativet Dynamisk leverans för ATP-säkra bilagor att organisationens e-post finns i Office 365. Om din e-post inte finns i Office 365 väljer du ett annat [principalternativ för BETRODDa bifogade filer på ATP,](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options)till exempel **Blockera**.

## <a name="additional-considerations"></a>Ytterligare överväganden

Det finns vissa scenarier där dynamisk leverans inte stöds. Dessa inkluderar följande:

- E-postmeddelanden som finns i gemensamma mappar

- E-postmeddelanden som dirigeras ut ur och sedan tillbaka till användarens postlåda med hjälp av anpassade regler

- E-postmeddelanden som flyttas (automatiskt eller manuellt) från den värdbaserade postlådan och till andra platser, inklusive arkivmappar

- E-postmeddelanden som tas bort

- En användares sökmapp för postlådan som är i feltillstånd

- Miljöer där en Exchange Online-administratör har aktiverat Utropsmål. LÃ¶s problemet genom att se [Meddelanden med bifogade filer inte levereras när ATP Dynamic Delivery and Exclaimer används](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)

- Meddelanden krypterade med [tillägg till säker/mångsidig internetpost (S/MIME)](s-mime-for-message-signing-and-encryption.md))

- Om dynamisk leverans inte stöds söker inte ATP-säkra bilagor igenom e-postmeddelanden. Leverera e-postmeddelanden med bifogade filer som innehåller webbadresser kontrolleras dock, beroende på hur [dina ATP-principer för säkra länkar](set-up-atp-safe-links-policies.md) konfigureras. I dessa fall kontrolleras webbadresser i e-postmeddelanden och Office-filer.
