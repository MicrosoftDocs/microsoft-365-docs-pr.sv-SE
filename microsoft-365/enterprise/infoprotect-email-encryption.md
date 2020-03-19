---
title: 'Steg 6: Konfigurera e-postkryptering'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Förstå och konfigurera hantering av privilegierad åtkomst för Office 365.
ms.openlocfilehash: d678c109f42901be2413c2b33e362d6796be96b7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805644"
---
# <a name="step-6-configure-email-encryption"></a><span data-ttu-id="ec207-103">Steg 6: Konfigurera e-postkryptering</span><span class="sxs-lookup"><span data-stu-id="ec207-103">Step 6: Configure email encryption</span></span>

<span data-ttu-id="ec207-104">*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="ec207-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="ec207-106">Det finns tre typer av e-postkryptering i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec207-106">There are three types of email encryption in Microsoft 365.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="ec207-107">Kryptering av Office-meddelanden (OME)</span><span class="sxs-lookup"><span data-stu-id="ec207-107">Office Message Encryption (OME)</span></span> | <span data-ttu-id="ec207-108">Kryptering för Exchange Online-e-post som skickas utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="ec207-108">Encryption for Exchange Online email sent outside your organization.</span></span> |
| <span data-ttu-id="ec207-109">Hantering av informationsrättigheter (IRM)</span><span class="sxs-lookup"><span data-stu-id="ec207-109">Information Rights Management (IRM)</span></span> | <span data-ttu-id="ec207-110">Kryptering och behörigheter som reser med e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="ec207-110">Encryption and permissions that travel with the email.</span></span> |
| <span data-ttu-id="ec207-111">Säkra/multifunktionella Internet-e-posttillägg (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="ec207-111">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span> | <span data-ttu-id="ec207-112">E-postskydd med kryptering och digitala signaturer.</span><span class="sxs-lookup"><span data-stu-id="ec207-112">Email protection with encryption and digital signatures.</span></span> |
|||

## <a name="office-365-message-encryption"></a><span data-ttu-id="ec207-113">Kryptering av Office 365-meddelanden</span><span class="sxs-lookup"><span data-stu-id="ec207-113">Office 365 Message Encryption</span></span>

<span data-ttu-id="ec207-114">Med OME kan din organisation skicka och ta emot krypterade e-postmeddelanden mellan personer inom och utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="ec207-114">With OME, your organization can send and receive encrypted email messages between people inside and outside your organization.</span></span> <span data-ttu-id="ec207-115">OME fungerar med Outlook.com, Yahoo!, Gmail och andra e-posttjänster.</span><span class="sxs-lookup"><span data-stu-id="ec207-115">OME works with Outlook.com, Yahoo!, Gmail, and other email services.</span></span> <span data-ttu-id="ec207-116">Kryptering av e-postmeddelanden säkerställer att endast avsedda mottagare kan visa meddelandet.</span><span class="sxs-lookup"><span data-stu-id="ec207-116">Email message encryption helps ensure that only intended recipients can view the message.</span></span>

![OME-kryptering av e-postmeddelanden](../media/infoprotect-email-encryption/ome-encryption.png)

<span data-ttu-id="ec207-118">Du ställer in transportregler som definierar villkoren för kryptering.</span><span class="sxs-lookup"><span data-stu-id="ec207-118">You set up transport rules that define the conditions for encryption.</span></span> <span data-ttu-id="ec207-119">När en användare skickar ett meddelande som matchar en regel tillämpas kryptering automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ec207-119">When a user sends a message that matches a rule, encryption is applied automatically.</span></span>

<span data-ttu-id="ec207-120">Om du vill visa krypterade meddelanden kan mottagarna antingen få en engångslösenkod, logga in med ett Microsoft-konto eller logga in med ett arbets- eller skolkonto som är kopplat till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec207-120">To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Microsoft 365.</span></span> <span data-ttu-id="ec207-121">Mottagarna kan också skicka krypterade svar.</span><span class="sxs-lookup"><span data-stu-id="ec207-121">Recipients can also send encrypted replies.</span></span> <span data-ttu-id="ec207-122">De behöver inte en egen Microsoft 365-prenumeration för att visa krypterade meddelanden eller skicka krypterade svar.</span><span class="sxs-lookup"><span data-stu-id="ec207-122">They don't need their own Microsoft 365 subscription to view encrypted messages or send encrypted replies.</span></span>

<span data-ttu-id="ec207-123">Mer information finns i [Office 365 Message Encryption](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span><span class="sxs-lookup"><span data-stu-id="ec207-123">For more information, see [Office 365 Message Encryption](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span></span>

## <a name="irm"></a><span data-ttu-id="ec207-124">Irm</span><span class="sxs-lookup"><span data-stu-id="ec207-124">IRM</span></span>

<span data-ttu-id="ec207-125">IRM i Microsoft 365 hjälper dig att skydda din information med ytterligare kryptering och genom att tillämpa en intelligent princip som anger vem som har åtkomst till vad de kan göra.</span><span class="sxs-lookup"><span data-stu-id="ec207-125">IRM in Microsoft 365 helps you secure your information with additional encryption and by applying an intelligent policy that specifies who has access what they can do.</span></span> <span data-ttu-id="ec207-126">För e-postmeddelanden kan du använda IRM för kryptering och tillämpa användningsbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="ec207-126">For email messages, you can use IRM for encryption and to apply usage restrictions.</span></span> <span data-ttu-id="ec207-127">Du kan till exempel ange att vissa mottagare har alla funktioner för att hantera e-postmeddelandet och vissa inte har möjlighet att skriva ut eller vidarebefordra e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="ec207-127">For example, you can specify that some recipients have all abilities to manage the email and some do not have the ability to print or forward the email.</span></span> 

<span data-ttu-id="ec207-128">IRM-principer konfigureras i Microsoft 365 och kan tillämpas på dokument i SharePoint Online och e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="ec207-128">IRM policies are configured within Microsoft 365 and can apply to documents in SharePoint Online and email messages.</span></span> <span data-ttu-id="ec207-129">Ett IRM-skyddat e-postmeddelande innehåller de tillämpade principinställningarna som tillämpas och reser med det.</span><span class="sxs-lookup"><span data-stu-id="ec207-129">An IRM-protected email includes the applied policy settings applied and travel with it.</span></span> 

![IRM-skydd av e-postmeddelanden](../media/infoprotect-email-encryption/irm-protection.png)

<span data-ttu-id="ec207-131">När mottagaren öppnar e-postmeddelandet med den medföljande principen används principinställningarna för att dekryptera meddelandet och bestämma vad mottagaren kan göra med det.</span><span class="sxs-lookup"><span data-stu-id="ec207-131">When the recipient opens the email with the included policy, the policy settings are used to decrypt the message and determine what the recipient can do with it.</span></span> 

<span data-ttu-id="ec207-132">Mer information finns [i Information Rights Management i Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="ec207-132">For more information, see [Information Rights Management in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span></span>

## <a name="smime"></a><span data-ttu-id="ec207-133">S/MIME</span><span class="sxs-lookup"><span data-stu-id="ec207-133">S/MIME</span></span>

<span data-ttu-id="ec207-134">S/MIME är en digital certifikatbaserad e-postbaserad skyddslösning som gör att du både kan kryptera och signera ett meddelande digitalt.</span><span class="sxs-lookup"><span data-stu-id="ec207-134">S/MIME is a digital certificate-based email-based protection solution that allows you to both encrypt and digitally sign a message.</span></span> <span data-ttu-id="ec207-135">Meddelandekrypteringen säkerställer att endast den avsedda mottagaren kan öppna och läsa meddelandet.</span><span class="sxs-lookup"><span data-stu-id="ec207-135">The message encryption helps ensure that only the intended recipient can open and read the message.</span></span> <span data-ttu-id="ec207-136">En digital signatur hjälper mottagaren att verifiera avsändarens identitet och fastställa att endast avsändaren kan ha skickat den.</span><span class="sxs-lookup"><span data-stu-id="ec207-136">A digital signature helps the recipient validate the identity of the sender and determine that only the sender could have sent it.</span></span>

![S/MIME-skydd av e-postmeddelanden](../media/infoprotect-email-encryption/smime-protection.png)

<span data-ttu-id="ec207-138">S/MIME kan användas för e-post till andra postlådor i din Microsoft 365-prenumeration eller till externa användare.</span><span class="sxs-lookup"><span data-stu-id="ec207-138">S/MIME can be used for email to other mailboxes in your Microsoft 365 subscription or to external users.</span></span>
<span data-ttu-id="ec207-139">Både meddelandekryptering och digitala signaturer möjliggörs med hjälp av digitala certifikat som innehåller offentliga och privata nycklar för att kryptera eller dekryptera meddelanden och skapa och verifiera digitala signaturer.</span><span class="sxs-lookup"><span data-stu-id="ec207-139">Both message encryption and digital signatures are made possible through the use of digital certificates that contain the public and private keys for encrypting or decrypting messages and creating and verifying digital signatures.</span></span>
<span data-ttu-id="ec207-140">Om du vill använda S/MIME måste du ha de offentliga nycklarna för varje mottagare.</span><span class="sxs-lookup"><span data-stu-id="ec207-140">To use S/MIME, you must have the public keys for each recipient.</span></span> <span data-ttu-id="ec207-141">Mottagarna behåller sina egna privata nycklar, som måste förbli säkra.</span><span class="sxs-lookup"><span data-stu-id="ec207-141">Recipients maintain their own private keys, which must remain secure.</span></span> <span data-ttu-id="ec207-142">Om din privata nyckel äventyras måste du skaffa ett nytt digitalt certifikat och distribuera offentliga nycklar till alla potentiella avsändare.</span><span class="sxs-lookup"><span data-stu-id="ec207-142">If your private key is compromised, you need to get a new digital certificate and redistribute public keys to all potential senders.</span></span>

<span data-ttu-id="ec207-143">Mer information finns i [S/MIME för meddelandesignering och kryptering](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span><span class="sxs-lookup"><span data-stu-id="ec207-143">For more information, see [S/MIME for message signing and encryption](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span></span>


<span data-ttu-id="ec207-144">Som en interimskontrollpunkt, se [exitkriterier som](infoprotect-exit-criteria.md#crit-infoprotect-step6) motsvarar detta steg.</span><span class="sxs-lookup"><span data-stu-id="ec207-144">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="ec207-145">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ec207-145">Next step</span></span>

|||
|:-------|:-----|
|![Steg 7](../media/stepnumbers/Step7.png)|[<span data-ttu-id="ec207-147">Konfigurera hantering av privilegierad åtkomst för Office 365</span><span class="sxs-lookup"><span data-stu-id="ec207-147">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
