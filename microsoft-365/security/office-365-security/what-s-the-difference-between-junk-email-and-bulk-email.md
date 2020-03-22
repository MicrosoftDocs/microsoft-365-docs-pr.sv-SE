---
title: Vad är skillnaden mellan skräppost och massutskick av e-post?
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/7/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: Kunderna frågar iblandvad är skillnaden mellan skräppost och massmeddelanden? Syftet med det här avsnittet är att förklara skillnaden och att ge information om de olika alternativ som är tillgängliga för både Exchange Online och Exchange Online Protection (EOP).
ms.openlocfilehash: 55924ac5e83ca109fd66d1723cdb7c5f43f20df6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895041"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a><span data-ttu-id="a4fdc-103">Vad är skillnaden mellan skräppost och massutskick av e-post?</span><span class="sxs-lookup"><span data-stu-id="a4fdc-103">What's the difference between junk email and bulk email?</span></span>

<span data-ttu-id="a4fdc-104">Kunderna frågar ibland "vad är skillnaden mellan skräppost och massmeddelanden?"</span><span class="sxs-lookup"><span data-stu-id="a4fdc-104">Customers sometimes ask "what's the difference between junk email and bulk email messages?"</span></span> <span data-ttu-id="a4fdc-105">Syftet med det här avsnittet är att förklara skillnaden och att ge information om de olika alternativ som är tillgängliga för både Exchange Online och Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="a4fdc-105">The purpose of this topic is to explain the difference and to provide information about the different options that are available for both in Exchange Online and Exchange Online Protection (EOP).</span></span>
  
 <span data-ttu-id="a4fdc-106">**Vad är skräppost?**</span><span class="sxs-lookup"><span data-stu-id="a4fdc-106">**What's junk email?**</span></span>
  
<span data-ttu-id="a4fdc-107">Skräppostmeddelanden är "skräppost" meddelanden, som är oönskade (och vanligtvis oönskade) e-postmeddelanden som filtreras av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="a4fdc-107">Junk email messages are "spam" messages, which are unsolicited (and typically unwanted) email messages that are filtered by the service.</span></span> <span data-ttu-id="a4fdc-108">Som standard avvisar tjänsten skräppostmeddelandet baserat på ryktet om den sändande IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="a4fdc-108">By default, the service rejects the spam message based on the reputation of the sending IP address.</span></span> <span data-ttu-id="a4fdc-109">Men om det passerar IP-inspektion men klassificeras som skräppost av innehållsfiltren skickas meddelandet till mappen Skräppost för de avsedda mottagarna.</span><span class="sxs-lookup"><span data-stu-id="a4fdc-109">However, if it passes IP inspection but is classified as spam by the content filters, the message is sent to the Junk Email folder of the intended recipients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a4fdc-110">Åtgärden som utförs på innehållsfiltrerade meddelanden kan konfigureras via innehållsfilterprinciper i Administrationscenter för Exchange (EAC), enligt beskrivningen i [Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a4fdc-110">The action performed on content-filtered messages is configurable via content filter policies in the Exchange admin center (EAC), as described in [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="a4fdc-111">Om du inte håller med om skräppostklassificeringen kan du också rapportera meddelanden som du anser vara skräppost eller icke-skräppost till Microsoft på flera sätt, enligt beskrivningen i [Skicka in skräppost, icke-skräppost och meddelanden om nätfiske till Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="a4fdc-111">Also, if you disagree with the spam classification, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> 
  
 <span data-ttu-id="a4fdc-112">**Vad är massutskick av e-post?**</span><span class="sxs-lookup"><span data-stu-id="a4fdc-112">**What's bulk email?**</span></span>
  
<span data-ttu-id="a4fdc-113">Massutskick av e-post, även kallat grå e-post, är en typ av e-postmeddelande som är svårare att klassificera.</span><span class="sxs-lookup"><span data-stu-id="a4fdc-113">Bulk email, also referred to as gray mail, is a type of email message that's more difficult to classify.</span></span> <span data-ttu-id="a4fdc-114">Medan skräppost är ett ständigt hot, bulk e-post består vanligtvis av en annons eller marknadsföring meddelande som sannolikt inte kommer att få skickas upprepade gånger.</span><span class="sxs-lookup"><span data-stu-id="a4fdc-114">Whereas junk email is a constant threat, bulk email is typically comprised of an advertisement or marketing message that's not likely to get sent repeatedly.</span></span> <span data-ttu-id="a4fdc-115">Mass e-post är efterlyst av vissa användare, och i själva verket kan de ha medvetet registrerat sig för att ta emot dessa meddelanden, medan andra användare kan betrakta dessa typer av meddelanden som spam.</span><span class="sxs-lookup"><span data-stu-id="a4fdc-115">Bulk email is wanted by some users, and in fact they may have deliberately signed up to receive these messages, while other users may consider these types of messages to be spam.</span></span> <span data-ttu-id="a4fdc-116">Vissa användare vill till exempel ta emot e-postmeddelanden från Contoso Corporation eller inbjudningar till en kommande konferens om cybersäkerhet, medan andra användare anser att sådana e-postmeddelanden är skräppost.</span><span class="sxs-lookup"><span data-stu-id="a4fdc-116">For example, some users want to receive advertising emails from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider such emails to be spam.</span></span>
  
## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="a4fdc-117">Så här hanterar du massutskick av e-post</span><span class="sxs-lookup"><span data-stu-id="a4fdc-117">How to manage bulk email</span></span>

<span data-ttu-id="a4fdc-118">Hur man hanterar bulk e-post är inte en tydlig klippa beslut, för om alla bulk e-post klassificeras som spam, de användare som vill att det kan klaga och skicka in det som en falsk positiv (icke-spam) meddelande som felaktigt markerades som spam.</span><span class="sxs-lookup"><span data-stu-id="a4fdc-118">How to manage bulk email isn't a clear cut decision, because if all bulk email is classified as spam, the users that want it may complain and submit it as a false positive (non-spam) message that was wrongly marked as spam.</span></span> <span data-ttu-id="a4fdc-119">Å andra sidan, om alla bulk e-post är att släppa igenom, de användare som inte vill ha det kan klaga och skicka in det som en missad spam-meddelande (falskt negativ) som felaktigt kom i sin inkorg.</span><span class="sxs-lookup"><span data-stu-id="a4fdc-119">On the other hand, if all bulk email is let through, the users that don't want it may complain and submit it as a missed spam message (false negative) that wrongly arrived in their inbox.</span></span>
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a><span data-ttu-id="a4fdc-120">Aktivera masssynkänslighetskontroll för e-post i innehållsfilterprincipen</span><span class="sxs-lookup"><span data-stu-id="a4fdc-120">Enable bulk mail sensitivity control in the content filter policy</span></span>

<span data-ttu-id="a4fdc-121">Beroende på företagets policy för massmeddelanden kan administratörer välja ett tröskelvärde för att tilldela massmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="a4fdc-121">Depending on your company's policy on bulk email messages, admins can select a threshold to assign the bulk email.</span></span> <span data-ttu-id="a4fdc-122">Inställningen kan konfigureras via innehållsfilterprinciper i EAC.</span><span class="sxs-lookup"><span data-stu-id="a4fdc-122">The setting is configurable via content filter policies in the EAC.</span></span> <span data-ttu-id="a4fdc-123">Kolla in Konfigurera principer mot [skräppost i Office 365](configure-your-spam-filter-policies.md) för stegen.</span><span class="sxs-lookup"><span data-stu-id="a4fdc-123">Check out [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md) for the steps.</span></span> <span data-ttu-id="a4fdc-124">Du kan välja en tröskelinställning från 1-9, där 1 markerar de flesta mass-e-post som skräppost, och 9 tillåter de flesta bulk e-post som ska levereras.</span><span class="sxs-lookup"><span data-stu-id="a4fdc-124">You can choose a threshold setting from 1-9, where 1 marks most bulk email as spam, and 9 allows most bulk email to be delivered.</span></span> <span data-ttu-id="a4fdc-125">Tjänsten utför sedan den konfigurerade åtgärden, till exempel att skicka meddelandet till mottagarens skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="a4fdc-125">The service then performs the configured action, such as sending the message to the recipient's Junk Email folder.</span></span> 
  

