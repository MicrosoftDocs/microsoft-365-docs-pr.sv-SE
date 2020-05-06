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
# <a name="dynamic-delivery-and-previewing-with-atp-safe-attachments"></a><span data-ttu-id="3cec8-103">Dynamisk leverans och förhandsgranskning med ATP-säkra bilagor</span><span class="sxs-lookup"><span data-stu-id="3cec8-103">Dynamic Delivery and previewing with ATP Safe Attachments</span></span>

## <a name="overview"></a><span data-ttu-id="3cec8-104">Översikt</span><span class="sxs-lookup"><span data-stu-id="3cec8-104">Overview</span></span>

<span data-ttu-id="3cec8-105">Dynamisk leverans är ett alternativ som kan väljas för [ATP Säkra bilagor](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="3cec8-105">Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="3cec8-106">Läs den här artikeln om du vill veta mer om förhandsgranskningsfunktioner för dynamisk leverans och förhandsgranskning av bifogade filer i [ATP-säkra bilagor i Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="3cec8-106">Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="3cec8-107">När [ATP-principer](set-up-atp-safe-attachments-policies.md) för säkra bilagor har ställts in för din organisation finns det flera alternativ för hur e-postbilagor hanteras.</span><span class="sxs-lookup"><span data-stu-id="3cec8-107">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled.</span></span> <span data-ttu-id="3cec8-108">Dessa inkluderar **Block,** **Ersätt**och **Dynamisk leverans**.</span><span class="sxs-lookup"><span data-stu-id="3cec8-108">These include **Block**, **Replace**, and **Dynamic Delivery**.</span></span> <span data-ttu-id="3cec8-109">Beroende på hur principer för betrodda bilagor konfigureras kan e-postmottagare uppleva en mindre fördröjning i e-postleveransen medan deras bilagor genomsöks.</span><span class="sxs-lookup"><span data-stu-id="3cec8-109">Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned.</span></span> <span data-ttu-id="3cec8-110">Om du vill undvika meddelandefördröjningar väljer du **Dynamisk leverans**.</span><span class="sxs-lookup"><span data-stu-id="3cec8-110">To avoid message delays, choose **Dynamic Delivery**.</span></span>

## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="3cec8-111">Så här fungerar dynamisk leverans</span><span class="sxs-lookup"><span data-stu-id="3cec8-111">How Dynamic Delivery works</span></span>

<span data-ttu-id="3cec8-112">Dynamisk leverans eliminerar e-postförseningar genom att skicka brödtexten i ett e-postmeddelande till mottagaren med en platshållare för varje e-postbilaga.</span><span class="sxs-lookup"><span data-stu-id="3cec8-112">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment.</span></span> <span data-ttu-id="3cec8-113">Platshållaren finns kvar tills en kopia av bilagan skannas och bedöms vara säker av [ATP Safe Attachments](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="3cec8-113">The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

- <span data-ttu-id="3cec8-114">När varje bifogad fil är avmarkerad kan den öppnas eller hämtas.</span><span class="sxs-lookup"><span data-stu-id="3cec8-114">As each attachment is cleared, it is available to open or download.</span></span>

- <span data-ttu-id="3cec8-115">Om en bifogad fil bedöms vara skadlig skickas den till karantän, där någon i organisationens säkerhetsteam (till exempel en global administratör eller säkerhetsadministratör) kan [hantera meddelanden i karantän i Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="3cec8-115">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as a global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="3cec8-116">De flesta PDF-filer och Office-dokument kan förhandsgranskas i felsäkert läge medan ATP-skanning pågår.</span><span class="sxs-lookup"><span data-stu-id="3cec8-116">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway.</span></span> <span data-ttu-id="3cec8-117">Om en bifogad fil inte är kompatibel med förhandsgranskningen av dynamisk leverans ser e-postmottagare en platshållare för bifogade filer tills ATP-skanningen av säkra bilagor är klar.</span><span class="sxs-lookup"><span data-stu-id="3cec8-117">If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="3cec8-118">Om du använder en mobil enhet och PDF-filer inte återges i förhandsgranskning av dynamisk leverans först kan du prova att logga in med din mobila webbläsare.</span><span class="sxs-lookup"><span data-stu-id="3cec8-118">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing in using your mobile browser.</span></span>

<span data-ttu-id="3cec8-119">Med dynamisk leverans kan användarna läsa och svara på sina e-postmeddelanden direkt, medan deras bilagor analyseras.</span><span class="sxs-lookup"><span data-stu-id="3cec8-119">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span>

<span data-ttu-id="3cec8-120">ATP-skanning av säkra bilagor sker i samma region där dina Microsoft 365-data finns.</span><span class="sxs-lookup"><span data-stu-id="3cec8-120">ATP Safe Attachments scanning takes place in the same region where your Microsoft 365 data resides.</span></span> <span data-ttu-id="3cec8-121">Mer information om datacentergeografi finns i [Var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="3cec8-121">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span>

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="3cec8-122">Vad händer när någon vidarebefordrar ett e-postmeddelande som innehåller en bifogad fil?</span><span class="sxs-lookup"><span data-stu-id="3cec8-122">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="3cec8-123">Anta att en organisation använder dynamisk leverans för sin [ATP-princip för säkra bilagor](set-up-atp-safe-attachments-policies.md)och att någon får ett e-postmeddelande som innehåller en bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="3cec8-123">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment.</span></span> <span data-ttu-id="3cec8-124">Anta nu att personen vidarebefordrar e-postmeddelandet till någon annan.</span><span class="sxs-lookup"><span data-stu-id="3cec8-124">Now suppose that person forwards the email message to someone else.</span></span> <span data-ttu-id="3cec8-125">Vad händer?</span><span class="sxs-lookup"><span data-stu-id="3cec8-125">What happens?</span></span> <span data-ttu-id="3cec8-126">Det beror på om ytterligare mottagare ingår i ATP:s principer för säkra bilagor.</span><span class="sxs-lookup"><span data-stu-id="3cec8-126">It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>

- <span data-ttu-id="3cec8-127">Om en mottagare omfattas av en ATP-princip för säkra bilagor med alternativet Dynamisk leverans ser mottagaren platshållaren med möjlighet att förhandsgranska kompatibla filer.</span><span class="sxs-lookup"><span data-stu-id="3cec8-127">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>

- <span data-ttu-id="3cec8-128">Om en mottagare inte omfattas av en ATP Safe Attachments-policy går e-post- och bilagan igenom, utan att några platshållare för ATP-säkra bilagor skanning eller platshållare för bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="3cec8-128">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without any ATP Safe Attachments scanning or attachment placeholders.</span></span>

## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="3cec8-129">Vad krävs för att dynamisk leverans ska fungera?</span><span class="sxs-lookup"><span data-stu-id="3cec8-129">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="3cec8-130">Din organisation måste ha [avancerat hotskydd för Office 365](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="3cec8-130">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>

- <span data-ttu-id="3cec8-131">Principer måste definieras för ATP-säkra bilagor med alternativet Dynamisk leverans (se [Konfigurera ATP-principer för säkra bilagor i Office 365](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="3cec8-131">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>

- <span data-ttu-id="3cec8-132">Organisationens e-post måste finnas i Office 365.</span><span class="sxs-lookup"><span data-stu-id="3cec8-132">Your organization's email must be hosted in Office 365.</span></span> <span data-ttu-id="3cec8-133">Även om [office 365 Advanced Threat Protection kan användas med alla SMTP-e-postöverföringsagenter](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (till exempel Exchange Server), kräver alternativet Dynamisk leverans för ATP-säkra bilagor att organisationens e-post finns i Office 365.</span><span class="sxs-lookup"><span data-stu-id="3cec8-133">Although [Office 365 Advanced Threat Protection can be used with any SMTP mail transfer agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (such as Exchange Server), the Dynamic Delivery option for ATP Safe Attachments requires that your organization's email be hosted in Office 365.</span></span> <span data-ttu-id="3cec8-134">Om din e-post inte finns i Office 365 väljer du ett annat [atp-principalternativ för säkra bilagor,](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options)till exempel **Blockera**.</span><span class="sxs-lookup"><span data-stu-id="3cec8-134">If your email is not hosted in Office 365, choose a different [ATP Safe Attachments policy option](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), such as **Block**.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="3cec8-135">Ytterligare överväganden</span><span class="sxs-lookup"><span data-stu-id="3cec8-135">Additional considerations</span></span>

<span data-ttu-id="3cec8-136">Det finns vissa scenarier där dynamisk leverans inte stöds.</span><span class="sxs-lookup"><span data-stu-id="3cec8-136">There are certain scenarios in which Dynamic Delivery is not supported.</span></span> <span data-ttu-id="3cec8-137">Dessa inkluderar följande:</span><span class="sxs-lookup"><span data-stu-id="3cec8-137">These include the following:</span></span>

- <span data-ttu-id="3cec8-138">E-postmeddelanden som finns i gemensamma mappar</span><span class="sxs-lookup"><span data-stu-id="3cec8-138">Email messages that are in public folders</span></span>

- <span data-ttu-id="3cec8-139">E-postmeddelanden som dirigeras ut ur och sedan tillbaka till användarens postlåda med hjälp av anpassade regler</span><span class="sxs-lookup"><span data-stu-id="3cec8-139">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>

- <span data-ttu-id="3cec8-140">E-postmeddelanden som flyttas (automatiskt eller manuellt) från den värdbaserade postlådan och till andra platser, inklusive arkivmappar</span><span class="sxs-lookup"><span data-stu-id="3cec8-140">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>

- <span data-ttu-id="3cec8-141">E-postmeddelanden som tas bort</span><span class="sxs-lookup"><span data-stu-id="3cec8-141">Email messages that are deleted</span></span>

- <span data-ttu-id="3cec8-142">En användares sökmapp för postlådan som är i feltillstånd</span><span class="sxs-lookup"><span data-stu-id="3cec8-142">A user's mailbox search folder that is in an error state</span></span>

- <span data-ttu-id="3cec8-143">Miljöer där en Exchange Online-administratör har aktiverat Exclaimer.</span><span class="sxs-lookup"><span data-stu-id="3cec8-143">Environments in which an Exchange Online admin has enabled Exclaimer.</span></span> <span data-ttu-id="3cec8-144">LÃ¶s problemet genom att se [Meddelanden med bifogade filer inte levereras nÃ¤r ATP Dynamic Delivery and Exclaimer](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span><span class="sxs-lookup"><span data-stu-id="3cec8-144">To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span></span>

- <span data-ttu-id="3cec8-145">Meddelanden krypterade med [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span><span class="sxs-lookup"><span data-stu-id="3cec8-145">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span></span>

- <span data-ttu-id="3cec8-146">I de fall dynamisk leverans inte stöds kommer ATP Safe Attachments inte att skanna e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="3cec8-146">In cases where Dynamic Delivery is not supported, ATP Safe Attachments will not scan email messages.</span></span> <span data-ttu-id="3cec8-147">Att leverera e-postmeddelanden med bifogade filer som innehåller webbadresser kommer dock att kontrolleras, beroende på hur [principerna för ATP Safe Links](set-up-atp-safe-links-policies.md) är konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="3cec8-147">However, delivering email messages with attachments that contain URLs will be checked, depending on how your [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured.</span></span> <span data-ttu-id="3cec8-148">I dessa fall kontrolleras webbadresser i e-postmeddelanden och Office-filer.</span><span class="sxs-lookup"><span data-stu-id="3cec8-148">In these cases, URLs in email messages and Office files are checked.</span></span>
