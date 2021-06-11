---
title: Tjänster för icke-kunder som skickar e-post till Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: För att upprätthålla användarnas förtroende för användningen av e-post har Microsoft utvecklat olika principer och tekniker som hjälper oss att skydda våra användare.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3213cae1b04b3f1a1b861e8f2cfc698576013546
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207369"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="3d063-103">Tjänster för icke-kunder som skickar e-post till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d063-103">Services for non-customers sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3d063-104">Missbruk av e-post, skräppost och bedrägliga e-postmeddelanden (nätfiske) fortsätter att belasta hela e-poste-ekosystemet.</span><span class="sxs-lookup"><span data-stu-id="3d063-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="3d063-105">För att upprätthålla användarnas förtroende för användningen av e-post har Microsoft lagt till olika principer och tekniker för att skydda våra användare.</span><span class="sxs-lookup"><span data-stu-id="3d063-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="3d063-106">Microsoft förstår dock att legitima e-postmeddelanden inte ska påverkas negativt.</span><span class="sxs-lookup"><span data-stu-id="3d063-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="3d063-107">Därför har vi upprättat en uppsättning tjänster för att hjälpa avsändare att förbättra sin förmåga att leverera e-Microsoft 365 till användare genom att proaktivt hantera sitt sändande rykte.</span><span class="sxs-lookup"><span data-stu-id="3d063-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="3d063-108">Den här översikten ger information om fördelar som vi ger din organisation även om du inte är kund.</span><span class="sxs-lookup"><span data-stu-id="3d063-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="3d063-109">Avsändarlösningar</span><span class="sxs-lookup"><span data-stu-id="3d063-109">Sender solutions</span></span>

****

|<span data-ttu-id="3d063-110">Tjänst</span><span class="sxs-lookup"><span data-stu-id="3d063-110">Service</span></span>|<span data-ttu-id="3d063-111">Förmåner</span><span class="sxs-lookup"><span data-stu-id="3d063-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="3d063-112">Det här onlinehjälpinnehållet</span><span class="sxs-lookup"><span data-stu-id="3d063-112">This online help content</span></span>|<span data-ttu-id="3d063-113">Ger:</span><span class="sxs-lookup"><span data-stu-id="3d063-113">Provides:</span></span> <ul><li><span data-ttu-id="3d063-114">En utgångspunkt för frågor som rör kommunikation till EOP-användare.</span><span class="sxs-lookup"><span data-stu-id="3d063-114">A starting point for any questions related to delivering communications to EOP users.</span></span></li><li><span data-ttu-id="3d063-115">Innehåller en enkel onlineguide med våra principer och krav.</span><span class="sxs-lookup"><span data-stu-id="3d063-115">Includes a simple online guide with our policies and requirements.</span></span></li><li><span data-ttu-id="3d063-116">En översikt över skräppostfilter och autentiseringstekniker som används av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d063-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span></li><ul>|
|[<span data-ttu-id="3d063-117">Microsoft Support</span><span class="sxs-lookup"><span data-stu-id="3d063-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="3d063-118">Ger stöd för självhjälp och eskalering för leveransproblem.</span><span class="sxs-lookup"><span data-stu-id="3d063-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="3d063-119">AVLIST-portalen för skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="3d063-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="3d063-120">Ett verktyg för att skicka in begäran om IP-avlistning.</span><span class="sxs-lookup"><span data-stu-id="3d063-120">A tool to submit IP delist request.</span></span> <span data-ttu-id="3d063-121">Innan denna begäran skickas är det avsändarens ansvar att säkerställa att all ytterligare e-post som kommer från ip-adressen i fråga inte är olämplig eller skadlig.</span><span class="sxs-lookup"><span data-stu-id="3d063-121">Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="3d063-122">Rapportering av missbruk och skräppost för skräppost som kommer från Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3d063-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="3d063-123">Hindrar skräppost och annan oönskad e-post från Exchange Online och gör att Internet och ditt e-postsystem blir rörigt.</span><span class="sxs-lookup"><span data-stu-id="3d063-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="3d063-124">Microsoft Support</span><span class="sxs-lookup"><span data-stu-id="3d063-124">Microsoft support</span></span>

<span data-ttu-id="3d063-125">Microsoft erbjuder flera supportalternativ för personer som har problem med att skicka e-post Microsoft 365 mottagare.</span><span class="sxs-lookup"><span data-stu-id="3d063-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="3d063-126">Vi rekommenderar att du:</span><span class="sxs-lookup"><span data-stu-id="3d063-126">We recommend that you:</span></span>

- <span data-ttu-id="3d063-127">Följ instruktionerna i alla rapporter om utebliven leverans som du får.</span><span class="sxs-lookup"><span data-stu-id="3d063-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="3d063-128">Kolla in de vanligaste problemen som icke-kunder stöter på i Felsökning av [e-post som skickas Office 365](troubleshooting-mail-sent-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="3d063-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="3d063-129">Använd Microsoft 365 [för att skicka](https://sender.office.com) en begäran om att få din IP borttagen från listan över spärrade avsändare.</span><span class="sxs-lookup"><span data-stu-id="3d063-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="3d063-130">Läs [Microsoft community-forumen](https://community.office365.com/f/).</span><span class="sxs-lookup"><span data-stu-id="3d063-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="3d063-131">Kontakta kunden som du försöker e-posta med en annan metod och be honom eller henne att kontakta Microsoft Support och öppna ett support ärende åt dig.</span><span class="sxs-lookup"><span data-stu-id="3d063-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="3d063-132">I vissa fall måste Microsoft Support, av juridiska skäl, kommunicera direkt med avsändaren som äger det IP-utrymme som blockeras.</span><span class="sxs-lookup"><span data-stu-id="3d063-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="3d063-133">Men icke-kunder kan vanligtvis inte öppna supportärenden.</span><span class="sxs-lookup"><span data-stu-id="3d063-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="3d063-134">Mer information om Microsofts tekniska support för Office 365 finns i [Support.](/office365/servicedescriptions/office-365-platform-service-description/support)</span><span class="sxs-lookup"><span data-stu-id="3d063-134">For more information about Microsoft Technical support for Office 365, see [Support](/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="3d063-135">AVLIST-portalen för skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="3d063-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="3d063-136">Det här är en självbetjäningsportal som du kan använda för Microsoft 365 bort dig själv från listan med spärrade avsändare.</span><span class="sxs-lookup"><span data-stu-id="3d063-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="3d063-137">Använd den här portalen om du får ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress ligger i Microsoft 365 och du inte tror att du bör vara det.</span><span class="sxs-lookup"><span data-stu-id="3d063-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="3d063-138">Mer information finns i Använda [delist-portalen för att ta bort dig själv från listan med spärrade avsändare.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)</span><span class="sxs-lookup"><span data-stu-id="3d063-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="3d063-139">Rapportering av missbruk och skräppost för skräppost som kommer från Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3d063-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="3d063-140">Ibland används Microsoft365 av tredje part för att skicka skräppost, i brott mot våra användningsvillkor och vår policy.</span><span class="sxs-lookup"><span data-stu-id="3d063-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="3d063-141">Om du får något skräppostmeddelande från Office 365 kan du rapportera dessa meddelanden till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d063-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="3d063-142">Anvisningar finns i [Artikeln om att rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="3d063-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>