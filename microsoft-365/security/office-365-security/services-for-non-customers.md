---
title: Tjänster för icke-kunder som skickar e-post till Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/2/2016
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: För att upprätthålla användarnas förtroende för användningen av e-post har Microsoft infört olika policyer och tekniker för att skydda våra användare.
ms.openlocfilehash: 2d8de601fd24f30c342768b8b27e44248f05b5fe
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638398"
---
# <a name="services-for-non-customers-sending-mail-to-office-365"></a><span data-ttu-id="26791-103">Tjänster för icke-kunder som skickar e-post till Office 365</span><span class="sxs-lookup"><span data-stu-id="26791-103">Services for non-customers sending mail to Office 365</span></span>

<span data-ttu-id="26791-104">E-postmissbruk, skräppost och bedrägliga e-postmeddelanden (nätfiske) fortsätter att belasta hela e-postekosystemet.</span><span class="sxs-lookup"><span data-stu-id="26791-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="26791-105">För att upprätthålla användarnas förtroende för användningen av e-post har Microsoft infört olika policyer och tekniker för att skydda våra användare.</span><span class="sxs-lookup"><span data-stu-id="26791-105">To help maintain user trust in the use of email, Microsoft has put in place various policies and technologies to help protect our users.</span></span> <span data-ttu-id="26791-106">Microsoft förstår dock att legitim e-post inte bör påverkas negativt.</span><span class="sxs-lookup"><span data-stu-id="26791-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="26791-107">Därför har vi etablerat en uppsättning tjänster som hjälper avsändare att förbättra sin förmåga att leverera e-post till Microsoft 365-användare genom att proaktivt hantera deras sändningsrykte.</span><span class="sxs-lookup"><span data-stu-id="26791-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="26791-108">Den här översikten innehåller information om fördelar som vi ger din organisation även om du inte är kund.</span><span class="sxs-lookup"><span data-stu-id="26791-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="26791-109">Avsändare lösningar</span><span class="sxs-lookup"><span data-stu-id="26791-109">Sender solutions</span></span>

|<span data-ttu-id="26791-110">**Tjänst**</span><span class="sxs-lookup"><span data-stu-id="26791-110">**Service**</span></span>|<span data-ttu-id="26791-111">**Fördelar**</span><span class="sxs-lookup"><span data-stu-id="26791-111">**Benefits**</span></span>|
|:-----|:-----|
|<span data-ttu-id="26791-112">Detta online-hjälpinnehåll</span><span class="sxs-lookup"><span data-stu-id="26791-112">This online help content</span></span>| <span data-ttu-id="26791-113">Ger:</span><span class="sxs-lookup"><span data-stu-id="26791-113">Provides:</span></span>  <br/>  <span data-ttu-id="26791-114">En utgångspunkt för alla frågor som rör leverans av kommunikation till EOP-användare</span><span class="sxs-lookup"><span data-stu-id="26791-114">A starting point for any questions related to delivering communications to EOP users</span></span>  <br/>  <span data-ttu-id="26791-115">Innehåller en enkel onlineguide med våra policyer och krav</span><span class="sxs-lookup"><span data-stu-id="26791-115">Includes a simple online guide with our policies and requirements</span></span>  <br/>  <span data-ttu-id="26791-116">En översikt över skräppostfilter och autentiseringstekniker som används av Microsoft</span><span class="sxs-lookup"><span data-stu-id="26791-116">An overview of the junk email filters and authentication technologies employed by Microsoft</span></span>|
|[<span data-ttu-id="26791-117">Microsoft-support</span><span class="sxs-lookup"><span data-stu-id="26791-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="26791-118">Ger självhjälp och eskaleringsstöd för leveransproblem.</span><span class="sxs-lookup"><span data-stu-id="26791-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="26791-119">Ip-portal för skräppost</span><span class="sxs-lookup"><span data-stu-id="26791-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="26791-120">Ett verktyg för att skicka IP-avlistningsbegäran.</span><span class="sxs-lookup"><span data-stu-id="26791-120">A tool to submit IP delist request.</span></span> <span data-ttu-id="26791-121">Innan denna begäran lämnas in är det avsändarens ansvar att se till att ytterligare post från ip-adressen i fråga inte är kränkande eller skadlig.</span><span class="sxs-lookup"><span data-stu-id="26791-121">Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="26791-122">Missbruks- och skräppostrapportering för skräppost från Exchange Online</span><span class="sxs-lookup"><span data-stu-id="26791-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="26791-123">Förhindrar att skräppost och annan oönskad e-post skickas från Exchange Online och belamar Internet och ditt e-postsystem.</span><span class="sxs-lookup"><span data-stu-id="26791-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the Internet and your mail system.</span></span>|

## <a name="microsoft-support"></a><span data-ttu-id="26791-124">Microsoft-support</span><span class="sxs-lookup"><span data-stu-id="26791-124">Microsoft support</span></span>

<span data-ttu-id="26791-125">Microsoft erbjuder flera supportalternativ för personer som har problem med att skicka e-post till Microsoft 365-inkorgar.</span><span class="sxs-lookup"><span data-stu-id="26791-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 inboxes.</span></span> <span data-ttu-id="26791-126">Vi rekommenderar att du:</span><span class="sxs-lookup"><span data-stu-id="26791-126">We recommend that you:</span></span>

- <span data-ttu-id="26791-127">Följ instruktionerna i alla rapporter om utebliven leverans som du får.</span><span class="sxs-lookup"><span data-stu-id="26791-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="26791-128">Ta reda på de vanligaste problemen som icke-kunder stöter på vid [Felsökning av e-post som skickas till Office 365](troubleshooting-mail-sent-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="26791-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="26791-129">Använd [Microsoft 365-avlistningsportalen](https://sender.office.com) för att skicka en begäran om att få din IP borttagen från den blockerade avsändarens lista.</span><span class="sxs-lookup"><span data-stu-id="26791-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="26791-130">Läs [Microsofts communityforum](https://community.office365.com/f/).</span><span class="sxs-lookup"><span data-stu-id="26791-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="26791-131">Kontakta kunden som du försöker skicka e-post med en annan metod och be dem kontakta Microsoft Support och öppna en supportbiljett för din räkning.</span><span class="sxs-lookup"><span data-stu-id="26791-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="26791-132">I vissa fall måste Microsoft Support av juridiska skäl kommunicera direkt med avsändaren som äger IP-utrymmet som blockeras.</span><span class="sxs-lookup"><span data-stu-id="26791-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="26791-133">Icke-kunder kan dock vanligtvis inte öppna supportbiljetter.</span><span class="sxs-lookup"><span data-stu-id="26791-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="26791-134">Mer information om Microsofts tekniska support för Office 365 finns i [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span><span class="sxs-lookup"><span data-stu-id="26791-134">For more information about Microsoft Technical support for Office 365, see [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="26791-135">Ip-portal för skräppost</span><span class="sxs-lookup"><span data-stu-id="26791-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="26791-136">Det här är en självbetjäningsportal som du kan använda för att ta bort dig själv från listan med blockerade avsändare från Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26791-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="26791-137">Använd den här portalen om du får ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Microsoft 365 och du inte tycker att du ska vara det.</span><span class="sxs-lookup"><span data-stu-id="26791-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="26791-138">Mer information finns i [Använda avlistningsportalen för att ta bort dig själv från listan blockerade avsändare](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="26791-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="26791-139">Missbruks- och skräppostrapportering för skräppost från Exchange Online</span><span class="sxs-lookup"><span data-stu-id="26791-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="26791-140">Ibland används Microsoft365 av tredje part för att skicka skräppost, i strid med våra användarvillkor och policyer.</span><span class="sxs-lookup"><span data-stu-id="26791-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="26791-141">Om du får skräppost från Office 365 kan du rapportera dessa meddelanden till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26791-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="26791-142">Instruktioner finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="26791-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>
