---
title: Exempel på meddelande när en avsändare blockeras när utgående skräppost skickas
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: 'När en avsändare blockeras från tjänsten på grund av att utgående skräppost skickas får domänadministratören när du konfigurerar principen om utgående skräppost ett e-postmeddelande som liknar följande:'
ms.openlocfilehash: 537e97fe952ad9a5b2ca854c44fe6c53b642e3ac
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806048"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a><span data-ttu-id="6c333-103">Exempel på meddelande när en avsändare blockeras när utgående skräppost skickas</span><span class="sxs-lookup"><span data-stu-id="6c333-103">Sample notification when a sender is blocked sending outbound spam</span></span>

<span data-ttu-id="6c333-104">När en avsändare blockeras från tjänsten på grund av att utgående skräppost skickas får domänadministratören när du [konfigurerar principen om utgående skräppost](configure-the-outbound-spam-policy.md) ett e-postmeddelande som liknar följande:</span><span class="sxs-lookup"><span data-stu-id="6c333-104">When a sender is blocked from the service due to sending outbound spam, the domain admin specified when you [Configure the outbound spam policy](configure-the-outbound-spam-policy.md) will receive a notification email similar to the following:</span></span> 
  
 <span data-ttu-id="6c333-105">**Avsändaradress:** spamalerts@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6c333-105">**Sender address:** spamalerts@microsoft.com</span></span> 
  
 <span data-ttu-id="6c333-106">**Angående:** Meddelande om skräppost \<utanför dejd – *kontonamnet* \> blockerats från att skicka utgående e-post    </span><span class="sxs-lookup"><span data-stu-id="6c333-106">**Subject:** Outbound spam notification - \<  *account name*  \> blocked from sending outbound mail</span></span> 
  
 <span data-ttu-id="6c333-107">**Kropp:** Detta är ett automatiskt svar från Exchange Online Protection Spam Analysis System.</span><span class="sxs-lookup"><span data-stu-id="6c333-107">**Body:** This is an automated reply from the Exchange Online Protection Spam Analysis System.</span></span> 
  
<span data-ttu-id="6c333-108">Du kontaktas eftersom vi har upptäckt stora mängder e-post som markerats som skräppost eller annat misstänkt beteende som kommer från din organisation.</span><span class="sxs-lookup"><span data-stu-id="6c333-108">You are being contacted because we have detected high volumes of email marked as spam, or other suspicious behavior, originating from your organization.</span></span> <span data-ttu-id="6c333-109">Följande e-postkonton har blockerats från att skicka e-post (de kan fortfarande ta emot e-post):</span><span class="sxs-lookup"><span data-stu-id="6c333-109">The following email accounts have been blocked from sending email (they can still receive email):</span></span>
  
<span data-ttu-id="6c333-110">\<*kontonamn*  \></span><span class="sxs-lookup"><span data-stu-id="6c333-110">\< *account name*  \></span></span> 
  
<span data-ttu-id="6c333-111">Det är troligt att det här e-postkontot har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="6c333-111">It is likely that this email account has been compromised.</span></span> <span data-ttu-id="6c333-112">Följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="6c333-112">Please follow these steps:</span></span>
  
1. <span data-ttu-id="6c333-113">Lös problemet på din sida genom att:</span><span class="sxs-lookup"><span data-stu-id="6c333-113">Resolve this issue on your side by:</span></span>
    
  - <span data-ttu-id="6c333-114">Ändra lösenordet för kontot.</span><span class="sxs-lookup"><span data-stu-id="6c333-114">Changing the password of the account.</span></span>
    
  - <span data-ttu-id="6c333-115">Bestämma hur kontot komprometterades.</span><span class="sxs-lookup"><span data-stu-id="6c333-115">Determining how the account was compromised.</span></span>
    
  - <span data-ttu-id="6c333-116">Försiktighetsåtgärder för att säkerställa att denna sårbarhet inte kommer att utnyttjas igen.</span><span class="sxs-lookup"><span data-stu-id="6c333-116">Taking precautions to ensure that this vulnerability will not be exploited again.</span></span>
    
  - <span data-ttu-id="6c333-117">Bekräftar att din utgående e-postkö har rensats från alla stötande meddelanden.</span><span class="sxs-lookup"><span data-stu-id="6c333-117">Confirming that your outbound mail queue has been cleared of all offending messages.</span></span>
    
2. <span data-ttu-id="6c333-118">Kontakta Microsoft-supporten med hjälp av din vanliga kontaktkanal.</span><span class="sxs-lookup"><span data-stu-id="6c333-118">Contact Microsoft support by using your regular contact channel.</span></span>
    
3. <span data-ttu-id="6c333-119">Förklara att du har en användare som är blockerad från att skicka e-post och att problemet har åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="6c333-119">Explain that you have a user that is blocked from sending mail and that the problem has been dealt with.</span></span>
    
4. <span data-ttu-id="6c333-120">Agenten skapar en supportbiljett med den information som du anger och eskalerar den för att få e-postadressen eller domänen avblockerad.</span><span class="sxs-lookup"><span data-stu-id="6c333-120">The agent will create a support ticket with the information that you provide and escalate it to have the email address or domain unblocked.</span></span>
    
5. <span data-ttu-id="6c333-121">När adressen har avblockerats och inte i avvaktan på några andra problem kommer du att kontaktas och aviseras till avblockeringen.</span><span class="sxs-lookup"><span data-stu-id="6c333-121">After the address has been unblocked, and pending no other issues, you will be contacted and alerted to the unblocking.</span></span>
    
<span data-ttu-id="6c333-122">Tack för att du hjälper oss att kontrollera oönskad e-post.</span><span class="sxs-lookup"><span data-stu-id="6c333-122">Thank you for assisting us in controlling unwanted email.</span></span>
  
<span data-ttu-id="6c333-123">Exchange Online Skydd.</span><span class="sxs-lookup"><span data-stu-id="6c333-123">Exchange Online Protection.</span></span>
  
<span data-ttu-id="6c333-124">\*\*OBS - Svara inte på detta e-postmeddelande eftersom det skickas från en oövervakad adress\*\*</span><span class="sxs-lookup"><span data-stu-id="6c333-124">\*\*NOTE - Please do not respond to this email as it is sent from an unmonitored address\*\*</span></span>
  
> [!TIP]
> <span data-ttu-id="6c333-125">Du kan också kontakta supporten via de alternativ som dokumenteras på [Hjälp och support för EOP](help-and-support-for-eop.md).</span><span class="sxs-lookup"><span data-stu-id="6c333-125">You can also contact support via the options documented at [Help and support for EOP](help-and-support-for-eop.md).</span></span> 
  

