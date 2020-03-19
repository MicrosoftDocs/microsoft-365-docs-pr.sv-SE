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
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="3c5ad-103">Dynamisk leverans och förhandsgranskning med Office 365 ATP-säkra bilagor</span><span class="sxs-lookup"><span data-stu-id="3c5ad-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

## <a name="overview"></a><span data-ttu-id="3c5ad-104">Översikt</span><span class="sxs-lookup"><span data-stu-id="3c5ad-104">Overview</span></span>

<span data-ttu-id="3c5ad-105">Dynamisk leverans är ett alternativ som kan väljas för [ATP-säkra bilagor](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="3c5ad-105">Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="3c5ad-106">Läs den här artikeln om du vill veta mer om förhandsgranskning av dynamiska leverans- och bifogade filer i [ATP-säkra bilagor i Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="3c5ad-106">Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="3c5ad-107">När [principer för betrodda bifogade filer för ATP har konfigurerats](set-up-atp-safe-attachments-policies.md) för din organisation finns det flera alternativ för hur e-postbilagor hanteras.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-107">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled.</span></span> <span data-ttu-id="3c5ad-108">Dessa inkluderar **Block,** **Ersätt**och **dynamisk leverans**.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-108">These include **Block**, **Replace**, and **Dynamic Delivery**.</span></span> <span data-ttu-id="3c5ad-109">Beroende på hur principer för a-postbilagor konfigureras kan e-postmottagare uppleva en mindre fördröjning i e-postleveransen medan deras bilagor skannas.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-109">Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned.</span></span> <span data-ttu-id="3c5ad-110">Om du vill undvika fördröjningar i meddelandet väljer du **Dynamisk leverans**.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-110">To avoid message delays, choose **Dynamic Delivery**.</span></span>

## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="3c5ad-111">Så här fungerar dynamisk leverans</span><span class="sxs-lookup"><span data-stu-id="3c5ad-111">How Dynamic Delivery works</span></span>

<span data-ttu-id="3c5ad-112">Dynamisk leverans eliminerar e-postfördröjningar genom att skicka brödtexten i ett e-postmeddelande till mottagaren med en platshållare för varje e-postbilaga.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-112">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment.</span></span> <span data-ttu-id="3c5ad-113">Platshållaren förblir tills en kopia av tillbehöret skannas och bestäms vara säker av [ATP Safe Attachments](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="3c5ad-113">The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

- <span data-ttu-id="3c5ad-114">Eftersom varje bifogad fil rensas är den tillgänglig för att öppna eller hämta.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-114">As each attachment is cleared, it is available to open or download.</span></span>

- <span data-ttu-id="3c5ad-115">Om en bifogad fil bedöms vara skadlig skickas den till karantän, där någon i organisationens säkerhetsteam (till exempel en global Office 365-administratör eller säkerhetsadministratör) kan [hantera meddelanden i karantän i Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="3c5ad-115">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="3c5ad-116">De flesta PDF-filer och Office-dokument kan förhandsgranskas i felsäkert läge medan ATP-skanning pågår.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-116">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway.</span></span> <span data-ttu-id="3c5ad-117">Om en bifogad fil inte är kompatibel med förhandsgranskningen av dynamisk leverans ser e-postmottagarna en platshållare för bifogade filer tills ATP Safe Attachments-skanningen är klar.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-117">If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="3c5ad-118">Om du använder en mobil enhet och PDF-filer inte återges i förhandsgranskningen av dynamisk leverans först kan du prova att logga in på Office 365 med hjälp av din mobila webbläsare.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-118">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing into Office 365 using your mobile browser.</span></span>

<span data-ttu-id="3c5ad-119">Med dynamisk leverans kan andra läsa och svara på sina e-postmeddelanden direkt, medan deras bilagor analyseras.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-119">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span>

<span data-ttu-id="3c5ad-120">Sökning av betrodda bifogade filer på ATP sker i samma region där dina Office 365-data finns.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-120">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides.</span></span> <span data-ttu-id="3c5ad-121">Mer information om datacentergeografi finns i [Var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="3c5ad-121">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span>

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="3c5ad-122">Vad händer när någon vidarebefordrar ett e-postmeddelande som innehåller en bifogad fil?</span><span class="sxs-lookup"><span data-stu-id="3c5ad-122">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="3c5ad-123">Anta att en organisation använder dynamisk leverans för sin [ATP Safe Attachments-princip](set-up-atp-safe-attachments-policies.md)och att någon får ett e-postmeddelande som innehåller en bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-123">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment.</span></span> <span data-ttu-id="3c5ad-124">Anta nu att personen vidarebefordrar e-postmeddelandet till någon annan.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-124">Now suppose that person forwards the email message to someone else.</span></span> <span data-ttu-id="3c5ad-125">Vad händer?</span><span class="sxs-lookup"><span data-stu-id="3c5ad-125">What happens?</span></span> <span data-ttu-id="3c5ad-126">Det beror på om de ytterligare mottagarna ingår i ATP Safe Attachments-principer.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-126">It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>

- <span data-ttu-id="3c5ad-127">Om en mottagare omfattas av en ATP-princip för säkra bilagor med alternativet Dynamisk leverans ser mottagaren platshållaren, med möjlighet att förhandsgranska kompatibla filer.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-127">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>

- <span data-ttu-id="3c5ad-128">Om en mottagare inte omfattas av en ATP Safe Attachments-policy kommer e-postmeddelandet och bilagan att gå igenom, utan att någon PLATShållare för betrodda bifogade filer eller tillbehör skannas eller tillbehörsplatshållare.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-128">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without any ATP Safe Attachments scanning or attachment placeholders.</span></span>

## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="3c5ad-129">Vad krävs för att dynamisk leverans ska fungera?</span><span class="sxs-lookup"><span data-stu-id="3c5ad-129">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="3c5ad-130">Din organisation måste ha [Office 365 Advanced Threat Protection](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="3c5ad-130">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>

- <span data-ttu-id="3c5ad-131">Principer måste definieras för ATP-säkra bilagor med alternativet Dynamisk leverans (se [Konfigurera principer för betrodda bifogade filer i ATP i Office 365](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="3c5ad-131">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>

- <span data-ttu-id="3c5ad-132">Organisationens e-post måste finnas i Office 365.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-132">Your organization's email must be hosted in Office 365.</span></span> <span data-ttu-id="3c5ad-133">Även om [Office 365 Advanced Threat Protection kan användas med alla SMTP-e-postöverföringsagenter](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (till exempel Exchange Server), kräver alternativet Dynamisk leverans för ATP-säkra bilagor att organisationens e-post finns i Office 365.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-133">Although [Office 365 Advanced Threat Protection can be used with any SMTP mail transfer agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (such as Exchange Server), the Dynamic Delivery option for ATP Safe Attachments requires that your organization's email be hosted in Office 365.</span></span> <span data-ttu-id="3c5ad-134">Om din e-post inte finns i Office 365 väljer du ett annat [principalternativ för BETRODDa bifogade filer på ATP,](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options)till exempel **Blockera**.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-134">If your email is not hosted in Office 365, choose a different [ATP Safe Attachments policy option](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), such as **Block**.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="3c5ad-135">Ytterligare överväganden</span><span class="sxs-lookup"><span data-stu-id="3c5ad-135">Additional considerations</span></span>

<span data-ttu-id="3c5ad-136">Det finns vissa scenarier där dynamisk leverans inte stöds.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-136">There are certain scenarios in which Dynamic Delivery is not supported.</span></span> <span data-ttu-id="3c5ad-137">Dessa inkluderar följande:</span><span class="sxs-lookup"><span data-stu-id="3c5ad-137">These include the following:</span></span>

- <span data-ttu-id="3c5ad-138">E-postmeddelanden som finns i gemensamma mappar</span><span class="sxs-lookup"><span data-stu-id="3c5ad-138">Email messages that are in public folders</span></span>

- <span data-ttu-id="3c5ad-139">E-postmeddelanden som dirigeras ut ur och sedan tillbaka till användarens postlåda med hjälp av anpassade regler</span><span class="sxs-lookup"><span data-stu-id="3c5ad-139">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>

- <span data-ttu-id="3c5ad-140">E-postmeddelanden som flyttas (automatiskt eller manuellt) från den värdbaserade postlådan och till andra platser, inklusive arkivmappar</span><span class="sxs-lookup"><span data-stu-id="3c5ad-140">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>

- <span data-ttu-id="3c5ad-141">E-postmeddelanden som tas bort</span><span class="sxs-lookup"><span data-stu-id="3c5ad-141">Email messages that are deleted</span></span>

- <span data-ttu-id="3c5ad-142">En användares sökmapp för postlådan som är i feltillstånd</span><span class="sxs-lookup"><span data-stu-id="3c5ad-142">A user's mailbox search folder that is in an error state</span></span>

- <span data-ttu-id="3c5ad-143">Miljöer där en Exchange Online-administratör har aktiverat Utropsmål.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-143">Environments in which an Exchange Online admin has enabled Exclaimer.</span></span> <span data-ttu-id="3c5ad-144">LÃ¶s problemet genom att se [Meddelanden med bifogade filer inte levereras när ATP Dynamic Delivery and Exclaimer används](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span><span class="sxs-lookup"><span data-stu-id="3c5ad-144">To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span></span>

- <span data-ttu-id="3c5ad-145">Meddelanden krypterade med [tillägg till säker/mångsidig internetpost (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span><span class="sxs-lookup"><span data-stu-id="3c5ad-145">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span></span>

- <span data-ttu-id="3c5ad-146">Om dynamisk leverans inte stöds söker inte ATP-säkra bilagor igenom e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-146">In cases where Dynamic Delivery is not supported, ATP Safe Attachments will not scan email messages.</span></span> <span data-ttu-id="3c5ad-147">Leverera e-postmeddelanden med bifogade filer som innehåller webbadresser kontrolleras dock, beroende på hur [dina ATP-principer för säkra länkar](set-up-atp-safe-links-policies.md) konfigureras.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-147">However, delivering email messages with attachments that contain URLs will be checked, depending on how your [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured.</span></span> <span data-ttu-id="3c5ad-148">I dessa fall kontrolleras webbadresser i e-postmeddelanden och Office-filer.</span><span class="sxs-lookup"><span data-stu-id="3c5ad-148">In these cases, URLs in email messages and Office files are checked.</span></span>
