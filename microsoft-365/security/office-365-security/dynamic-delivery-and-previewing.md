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
# <a name="dynamic-delivery-and-previewing-with-atp-safe-attachments"></a><span data-ttu-id="b4c71-103">Dynamisk leverans och förhands granskning med säkra filer för ATP</span><span class="sxs-lookup"><span data-stu-id="b4c71-103">Dynamic Delivery and previewing with ATP Safe Attachments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-dynamic-delivery"></a><span data-ttu-id="b4c71-104">Grundläggande funktioner för dynamisk leverans</span><span class="sxs-lookup"><span data-stu-id="b4c71-104">Basic features of Dynamic Delivery</span></span>

<span data-ttu-id="b4c71-105">Dynamisk leverans är ett alternativ som kan väljas för [säkra filer för ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="b4c71-105">Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="b4c71-106">Läs den här artikeln om du vill lära dig mer om funktionerna för förhands granskning av dynamisk leverans och för hands versioner i [Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="b4c71-106">Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="b4c71-107">När [ATP-principer för säker åtkomst är inställda](set-up-atp-safe-attachments-policies.md) för din organisation finns det flera alternativ för hur bifogade filer hanteras.</span><span class="sxs-lookup"><span data-stu-id="b4c71-107">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled.</span></span> <span data-ttu-id="b4c71-108">Här ingår **blockering**, **ersättning**och **dynamisk leverans**.</span><span class="sxs-lookup"><span data-stu-id="b4c71-108">These include **Block**, **Replace**, and **Dynamic Delivery**.</span></span> <span data-ttu-id="b4c71-109">Beroende på hur du konfigurerar principer för säker åtkomst till bifogade filer kan e-postmottagarna få en mindre fördröjning i e-postleveransen medan deras bilagor genomsöks.</span><span class="sxs-lookup"><span data-stu-id="b4c71-109">Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned.</span></span> <span data-ttu-id="b4c71-110">För att undvika fördröjningar av meddelanden väljer du **dynamisk leverans**.</span><span class="sxs-lookup"><span data-stu-id="b4c71-110">To avoid message delays, choose **Dynamic Delivery**.</span></span>

## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="b4c71-111">Så fungerar dynamisk leverans</span><span class="sxs-lookup"><span data-stu-id="b4c71-111">How Dynamic Delivery works</span></span>

<span data-ttu-id="b4c71-112">Dynamisk leverans eliminerar e-postfördröjningar genom att skicka bröd texten i ett e-postmeddelande till mottagaren med en plats hållare för varje bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="b4c71-112">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment.</span></span> <span data-ttu-id="b4c71-113">Plats hållaren fortsätter tills en kopia av den bifogade filen har skannats och bedöms vara säker av [säkra filer för säkerhet per ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="b4c71-113">The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

- <span data-ttu-id="b4c71-114">När alla bifogade filer är avmarkerade kan de öppna eller ladda ner.</span><span class="sxs-lookup"><span data-stu-id="b4c71-114">As each attachment is cleared, it is available to open or download.</span></span>

- <span data-ttu-id="b4c71-115">Om en bifogad fil bedöms vara skadlig, skickas den till karantän, där någon i organisationens säkerhets team (till exempel en global administratör eller säkerhets administratör) kan [Hantera meddelanden i karantän i Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="b4c71-115">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as a global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="b4c71-116">De flesta PDF-filer och Office-dokument kan förhandsgranskas i fel säkert läge medan genomsökning av ATP pågår.</span><span class="sxs-lookup"><span data-stu-id="b4c71-116">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway.</span></span> <span data-ttu-id="b4c71-117">Om en bifogad fil inte är kompatibel med förhands granskning för dynamisk leverans ser e-postmottagarna en bilage plats hållare tills ATP Safe Attachment scanning är klar.</span><span class="sxs-lookup"><span data-stu-id="b4c71-117">If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="b4c71-118">Om du använder en mobil enhet och PDF-filer inte återges i förhands granskning av dynamisk leverans först kan du försöka logga in med din mobil.</span><span class="sxs-lookup"><span data-stu-id="b4c71-118">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing in using your mobile browser.</span></span>

<span data-ttu-id="b4c71-119">Med dynamisk leverans kan användarna läsa och svara på deras e-postmeddelanden direkt medan deras bifogade filer analyseras.</span><span class="sxs-lookup"><span data-stu-id="b4c71-119">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span>

<span data-ttu-id="b4c71-120">ATP Safe Attachments scanning sker i samma region där dina Microsoft 365-data finns.</span><span class="sxs-lookup"><span data-stu-id="b4c71-120">ATP Safe Attachments scanning takes place in the same region where your Microsoft 365 data resides.</span></span> <span data-ttu-id="b4c71-121">Mer information om data Center geografi finns i [var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="b4c71-121">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span>

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="b4c71-122">Vad händer när någon vidarebefordrar ett e-postmeddelande som innehåller en bifogad fil?</span><span class="sxs-lookup"><span data-stu-id="b4c71-122">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="b4c71-123">Anta att en organisation använder dynamisk leverans för att få en [policy för säkerhets](set-up-atp-safe-attachments-policies.md)skull med ATP och någon får ett e-postmeddelande som innehåller en bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="b4c71-123">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment.</span></span> <span data-ttu-id="b4c71-124">Antag att personen vidarebefordrar e-postmeddelandet till någon annan.</span><span class="sxs-lookup"><span data-stu-id="b4c71-124">Now suppose that person forwards the email message to someone else.</span></span> <span data-ttu-id="b4c71-125">Vad händer?</span><span class="sxs-lookup"><span data-stu-id="b4c71-125">What happens?</span></span> <span data-ttu-id="b4c71-126">Det beror på om de ytterligare mottagarna ingår i principer för säkra bifogade filer via ATP.</span><span class="sxs-lookup"><span data-stu-id="b4c71-126">It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>

- <span data-ttu-id="b4c71-127">Om en mottagare täcks av en policy för säker användning av ATP med alternativet dynamisk leverans ser mottagaren plats hållaren och kan förhandsgranska kompatibla filer.</span><span class="sxs-lookup"><span data-stu-id="b4c71-127">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>

- <span data-ttu-id="b4c71-128">Om en mottagare inte täcks av en policy för säker e-postanvändning för ATP kommer e-postmeddelandet och bilagan att gå igenom, utan några extra säkerhets sökningar eller plats hållare för bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="b4c71-128">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without any ATP Safe Attachments scanning or attachment placeholders.</span></span>

## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="b4c71-129">Vad krävs för att dynamisk leverans ska fungera?</span><span class="sxs-lookup"><span data-stu-id="b4c71-129">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="b4c71-130">Din organisation måste ha [Office 365 Avancerat skydd](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="b4c71-130">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>

- <span data-ttu-id="b4c71-131">Principer måste definieras för säkra filer för ATP med alternativet dynamisk leverans (mer information finns i [Konfigurera principer för säkra bifogade säkerhets brev i Office 365](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="b4c71-131">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>

- <span data-ttu-id="b4c71-132">Din organisations e-postadress måste finnas med i Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4c71-132">Your organization's email must be hosted in Office 365.</span></span> <span data-ttu-id="b4c71-133">Trots att [Office 365 Avancerat skydd för e-post kan användas med valfri SMTP-överförings agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (till exempel Exchange Server) kräver alternativet för dynamisk leverans för säkerhets skull med ATP att organisationens e-postadress finns i Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4c71-133">Although [Office 365 Advanced Threat Protection can be used with any SMTP mail transfer agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (such as Exchange Server), the Dynamic Delivery option for ATP Safe Attachments requires that your organization's email be hosted in Office 365.</span></span> <span data-ttu-id="b4c71-134">Om e-postmeddelandet inte finns i Office 365 väljer du ett annat [princip alternativ](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), till exempel **blockera**.</span><span class="sxs-lookup"><span data-stu-id="b4c71-134">If your email is not hosted in Office 365, choose a different [ATP Safe Attachments policy option](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), such as **Block**.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="b4c71-135">Ytterligare överväganden</span><span class="sxs-lookup"><span data-stu-id="b4c71-135">Additional considerations</span></span>

<span data-ttu-id="b4c71-136">Det finns vissa scenarier där säkra bilagor (inklusive dynamisk leverans stöds inte).</span><span class="sxs-lookup"><span data-stu-id="b4c71-136">There are certain scenarios in which Safe Attachments (including Dynamic Delivery is not supported).</span></span> <span data-ttu-id="b4c71-137">De omfattar:</span><span class="sxs-lookup"><span data-stu-id="b4c71-137">These include:</span></span>

- <span data-ttu-id="b4c71-138">E-postmeddelanden i gemensamma mappar.</span><span class="sxs-lookup"><span data-stu-id="b4c71-138">Email messages that are in public folders.</span></span>

- <span data-ttu-id="b4c71-139">E-postmeddelanden som omdirigeras från och sedan tillbaka till användarens post låda med anpassade regler.</span><span class="sxs-lookup"><span data-stu-id="b4c71-139">Email messages that are routed out of and then back into the user's mailbox using custom rules.</span></span>

- <span data-ttu-id="b4c71-140">E-postmeddelanden som flyttas (automatiskt eller manuellt) från den värdbaserade post lådan och till andra platser, inklusive arkivmappar.</span><span class="sxs-lookup"><span data-stu-id="b4c71-140">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders.</span></span>

- <span data-ttu-id="b4c71-141">E-postmeddelanden som tas bort.</span><span class="sxs-lookup"><span data-stu-id="b4c71-141">Email messages that are deleted.</span></span>

- <span data-ttu-id="b4c71-142">En användares sökmapp i post lådan är i fel tillstånd.</span><span class="sxs-lookup"><span data-stu-id="b4c71-142">A user's mailbox search folder that is in an error state.</span></span>

- <span data-ttu-id="b4c71-143">Miljöer där en Exchange Online-administratör har aktiverat Exclaimer.</span><span class="sxs-lookup"><span data-stu-id="b4c71-143">Environments in which an Exchange Online admin has enabled Exclaimer.</span></span> <span data-ttu-id="b4c71-144">För att lösa det här kan du läsa [meddelanden med bifogade filer levereras inte när du använder ATP-dynamisk leverans och Exclaimer](https://support.microsoft.com/help/4014438).</span><span class="sxs-lookup"><span data-stu-id="b4c71-144">To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438).</span></span>

- <span data-ttu-id="b4c71-145">Meddelanden krypterade med [S/MIME (Secure Multipurpose Internet Mail Extensions](s-mime-for-message-signing-and-encryption.md))).</span><span class="sxs-lookup"><span data-stu-id="b4c71-145">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md)).</span></span>

- <span data-ttu-id="b4c71-146">Om det inte finns stöd för dynamisk leverans genomsöks inte e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="b4c71-146">In cases where Dynamic Delivery is not supported, Safe Attachments will not scan email messages.</span></span> <span data-ttu-id="b4c71-147">E-postmeddelanden med bifogade filer som innehåller URL: er kommer att kontrol leras, beroende på hur du har konfigurerat [principerna för Safet ATP-länkar](set-up-atp-safe-links-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="b4c71-147">However, delivering email messages with attachments that contain URLs will be checked, depending on how your [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured.</span></span> <span data-ttu-id="b4c71-148">I de här fallen är URL-adresser i e-postmeddelanden och Office-filer markerade.</span><span class="sxs-lookup"><span data-stu-id="b4c71-148">In these cases, URLs in email messages and Office files are checked.</span></span>
