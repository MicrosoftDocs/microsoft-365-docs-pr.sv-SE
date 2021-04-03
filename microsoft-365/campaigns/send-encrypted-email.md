---
title: Skicka krypterad e-post
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Lär dig hur du skickar krypterade e-postmeddelanden med Outlook.
ms.openlocfilehash: 209734bd52d1d97278d5632f035723758fe2e016
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51576979"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="fe55b-103">Kryptera eller märk dina konfidentiella e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="fe55b-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="fe55b-104">Data och kampanjinformation är viktig och ofta konfidentiell.</span><span class="sxs-lookup"><span data-stu-id="fe55b-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="fe55b-105">Skydda den här känsliga informationen genom att använda kryptering och känslighetsetiketter så att du och dina e-postmottagare behandlar informationen med den känslighet som krävs.</span><span class="sxs-lookup"><span data-stu-id="fe55b-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>

## <a name="best-practices"></a><span data-ttu-id="fe55b-106">Metodtips</span><span class="sxs-lookup"><span data-stu-id="fe55b-106">Best practices</span></span>

<span data-ttu-id="fe55b-107">Innan du skickar e-post med konfidentiell eller känslig information bör du överväga att aktivera:</span><span class="sxs-lookup"><span data-stu-id="fe55b-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="fe55b-108">**Kryptering:** Du kan kryptera din e-post för att skydda informationen i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="fe55b-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="fe55b-109">När du krypterar ett e-postmeddelande konverteras det från läsbar oformaterad text till kodad cyphertext.</span><span class="sxs-lookup"><span data-stu-id="fe55b-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="fe55b-110">Endast mottagaren som har den privata nyckeln som matchar den offentliga nyckeln som används för att kryptera meddelandet kan dechiffrera meddelandet för läsning.</span><span class="sxs-lookup"><span data-stu-id="fe55b-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="fe55b-111">Alla mottagare utan motsvarande privat nyckel ser däremot ochiffrbar text.</span><span class="sxs-lookup"><span data-stu-id="fe55b-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="fe55b-112">Administratören kan definiera regler för att automatiskt kryptera meddelanden som uppfyller vissa villkor.</span><span class="sxs-lookup"><span data-stu-id="fe55b-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="fe55b-113">Din administratör kan till exempel skapa en regel som krypterar alla meddelanden som skickas utanför organisationen eller alla meddelanden som nämner specifika ord eller fraser.</span><span class="sxs-lookup"><span data-stu-id="fe55b-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="fe55b-114">Eventuella krypteringsregler tillämpas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="fe55b-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="fe55b-115">**Känslighetsetiketter:** Din kampanj kan också konfigurera känslighetsetiketter som du kan använda för dina filer och e-post för att hålla dem kompatibla med informationsskyddsprinciperna för din kampanj.</span><span class="sxs-lookup"><span data-stu-id="fe55b-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="fe55b-116">När du anger en etikett beständiga etiketten med ditt e-postmeddelande, även när det skickas – till exempel genom att visas som ett sidhuvud i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="fe55b-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![Diagram över ett e-postmeddelande med bildtexter för etiketter och kryptering](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a><span data-ttu-id="fe55b-118">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="fe55b-118">Set it up</span></span>

<span data-ttu-id="fe55b-119">Om du vill kryptera ett meddelande som inte uppfyller en fördefinierad regel eller om administratören inte har angett några regler kan du använda en mängd olika krypteringsregler innan du skickar meddelandet.</span><span class="sxs-lookup"><span data-stu-id="fe55b-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="fe55b-120">Om du vill skicka ett krypterat meddelande från Outlook 2013 eller 2016 eller Outlook 2016 för Mac väljer du **Alternativ > Behörigheter** och sedan det skyddsalternativ du behöver.</span><span class="sxs-lookup"><span data-stu-id="fe55b-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="fe55b-121">Du kan också skicka ett krypterat meddelande genom att **välja knappen** Skydda i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="fe55b-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="fe55b-122">Mer information finns i [Skicka, visa och svara på krypterade meddelanden i Outlook för PC.](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)</span><span class="sxs-lookup"><span data-stu-id="fe55b-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="fe55b-123">Administratörsinställningar</span><span class="sxs-lookup"><span data-stu-id="fe55b-123">Admin settings</span></span>

<span data-ttu-id="fe55b-124">Du kan lära dig allt om att konfigurera e-postkryptering [i E-postkryptering i Microsoft 365.](../compliance/email-encryption.md)</span><span class="sxs-lookup"><span data-stu-id="fe55b-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](../compliance/email-encryption.md).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="fe55b-125">Kryptera e-postmeddelanden automatiskt</span><span class="sxs-lookup"><span data-stu-id="fe55b-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="fe55b-126">Administratörer kan skapa e-postflödesregler för att automatiskt skydda e-postmeddelanden som skickas och tas emot från kampanjen.</span><span class="sxs-lookup"><span data-stu-id="fe55b-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="fe55b-127">Konfigurera regler för att kryptera alla utgående e-postmeddelanden och ta bort kryptering från krypterade meddelanden från organisationen eller från svar på krypterade meddelanden som skickas från organisationen.</span><span class="sxs-lookup"><span data-stu-id="fe55b-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span>

<span data-ttu-id="fe55b-128">Du skapar e-postflödesregler för att kryptera e-postmeddelanden med de nya funktionerna i Meddelandekryptering i Office 365 (OME).</span><span class="sxs-lookup"><span data-stu-id="fe55b-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="fe55b-129">Definiera e-postflödesregler för att utlösa meddelandekryptering med de nya OME-funktionerna med hjälp av administrationscentret för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="fe55b-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="fe55b-130">Använd ett arbets- eller skolkonto som har beviljats global administratörsbehörighet i en webbläsare och logga in.</span><span class="sxs-lookup"><span data-stu-id="fe55b-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span>
2. <span data-ttu-id="fe55b-131">Välj panelen Admin.</span><span class="sxs-lookup"><span data-stu-id="fe55b-131">Choose the Admin tile.</span></span>
3. <span data-ttu-id="fe55b-132">I administrationscentret väljer du **Administrationscenter > Exchange.**</span><span class="sxs-lookup"><span data-stu-id="fe55b-132">In the admin center, choose **Admin centers > Exchange**.</span></span>

<span data-ttu-id="fe55b-133">Mer information finns i Definiera [e-postflödesregler för att kryptera e-postmeddelanden.](../compliance/define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="fe55b-133">For more information, see [Define mail flow rules to encrypt email messages](../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="fe55b-134">Profilera dina krypteringsmeddelanden</span><span class="sxs-lookup"><span data-stu-id="fe55b-134">Brand your encryption messages</span></span>

<span data-ttu-id="fe55b-135">Du kan också anpassa kampanjens varumärke om du vill anpassa utseendet och texten i e-postmeddelandena.</span><span class="sxs-lookup"><span data-stu-id="fe55b-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="fe55b-136">Mer information finns i [Lägga till företagets varumärke i krypterade meddelanden.](../compliance/email-encryption.md)</span><span class="sxs-lookup"><span data-stu-id="fe55b-136">For more information, see [Add your organization's brand to your encrypted messages](../compliance/email-encryption.md).</span></span>