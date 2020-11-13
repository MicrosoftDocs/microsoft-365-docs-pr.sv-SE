---
title: Tjänster för ej kunder som skickar e-post till Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: För att det ska vara lätt att skydda användar förtroendet för användning av e-post har Microsoft infört olika principer och teknologier som hjälper våra användare att hjälpa dig.
ms.openlocfilehash: 478f94d2ed1a03253168486d48fb2b2df57a6a5e
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49021031"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="39903-103">Tjänster för ej kunder som skickar e-post till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="39903-103">Services for non-customers sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="39903-104">E-POSTMISSBRUK, skräp post och bedräglig e-post (phishing) fortsätter att belasta hela e-postekoet.</span><span class="sxs-lookup"><span data-stu-id="39903-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="39903-105">Microsoft har ett flertal principer och teknologier för att skydda våra användare för att under lätta användar förtroendet för användning av e-post.</span><span class="sxs-lookup"><span data-stu-id="39903-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="39903-106">Microsoft förstår att legitim e-post inte bör påverkas negativt.</span><span class="sxs-lookup"><span data-stu-id="39903-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="39903-107">Därför har vi fastställt en svit med tjänster för att hjälpa avsändarna att kunna skicka e-post till Microsoft 365-användare genom att proaktivt hantera sitt sändnings rykte.</span><span class="sxs-lookup"><span data-stu-id="39903-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="39903-108">Den här översikten innehåller information om fördelarna som vi tillhandahåller din organisation även om du inte är kund.</span><span class="sxs-lookup"><span data-stu-id="39903-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="39903-109">Avsändare</span><span class="sxs-lookup"><span data-stu-id="39903-109">Sender solutions</span></span>

****

|<span data-ttu-id="39903-110">Tjänst</span><span class="sxs-lookup"><span data-stu-id="39903-110">Service</span></span>|<span data-ttu-id="39903-111">Intäkter</span><span class="sxs-lookup"><span data-stu-id="39903-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="39903-112">Detta online-hjälp innehåll</span><span class="sxs-lookup"><span data-stu-id="39903-112">This online help content</span></span>|<span data-ttu-id="39903-113">Gång</span><span class="sxs-lookup"><span data-stu-id="39903-113">Provides:</span></span> <ul><li><span data-ttu-id="39903-114">En utgångs punkt för eventuella frågor om att leverera kommunikation till EOP användare.</span><span class="sxs-lookup"><span data-stu-id="39903-114">A starting point for any questions related to delivering communications to EOP users.</span></span></li><li><span data-ttu-id="39903-115">Innehåller en enkel onlineguiden med våra principer och krav.</span><span class="sxs-lookup"><span data-stu-id="39903-115">Includes a simple online guide with our policies and requirements.</span></span></li><li><span data-ttu-id="39903-116">En översikt över skräp post filter och verifieringsmetoder som används av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39903-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span></li><ul>|
|[<span data-ttu-id="39903-117">Microsoft-Support</span><span class="sxs-lookup"><span data-stu-id="39903-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="39903-118">Tillhandahåller självhjälps-och eskaleringshantering för leverans problem.</span><span class="sxs-lookup"><span data-stu-id="39903-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="39903-119">IP-portalwebbplats för skräp post</span><span class="sxs-lookup"><span data-stu-id="39903-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="39903-120">Ett verktyg för att skicka en begäran om IP-registrering.</span><span class="sxs-lookup"><span data-stu-id="39903-120">A tool to submit IP delist request.</span></span> <span data-ttu-id="39903-121">Innan det här meddelandet skickas är det ansvarigt för att säkerställa att all e-post som härstammar från undersöknings tjänsten är olämplig eller skadlig.</span><span class="sxs-lookup"><span data-stu-id="39903-121">Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="39903-122">Missbruk och spam rapportering för skräp post från Exchange Online</span><span class="sxs-lookup"><span data-stu-id="39903-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="39903-123">Håller skräp posten och annan oönskad e-post från Exchange Online och fyller på Internet och ditt e-postsystem.</span><span class="sxs-lookup"><span data-stu-id="39903-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="39903-124">Microsoft-Support</span><span class="sxs-lookup"><span data-stu-id="39903-124">Microsoft support</span></span>

<span data-ttu-id="39903-125">Microsoft erbjuder flera support alternativ för att det ska gå att skicka e-post till Microsoft 365-mottagare.</span><span class="sxs-lookup"><span data-stu-id="39903-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="39903-126">Vi rekommenderar att du:</span><span class="sxs-lookup"><span data-stu-id="39903-126">We recommend that you:</span></span>

- <span data-ttu-id="39903-127">Följ instruktionerna i en rapport om utebliven leverans som du får.</span><span class="sxs-lookup"><span data-stu-id="39903-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="39903-128">Kolla de vanligaste problemen som icke-kunder stöter på vid [fel sökning av e-post som skickas till Office 365](troubleshooting-mail-sent-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="39903-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="39903-129">Använd [Microsoft 365-portalen](https://sender.office.com) för att skicka en begäran om att få din IP-adress bort från listan Spärrade avsändare.</span><span class="sxs-lookup"><span data-stu-id="39903-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="39903-130">Läs [Microsofts community-forum](https://community.office365.com/f/).</span><span class="sxs-lookup"><span data-stu-id="39903-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="39903-131">Kontakta kunden du försöker skicka via e-post med en annan metod och be dem kontakta Microsoft support och öppna ett support ärende åt dig.</span><span class="sxs-lookup"><span data-stu-id="39903-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="39903-132">I vissa fall måste Microsofts support kommunicera direkt med avsändaren som äger det IP-utrymme som blockeras.</span><span class="sxs-lookup"><span data-stu-id="39903-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="39903-133">Icke-kunder kan vanligt vis inte öppna support biljetter.</span><span class="sxs-lookup"><span data-stu-id="39903-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="39903-134">Mer information om Microsoft Technical Support för Office 365 finns i [support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span><span class="sxs-lookup"><span data-stu-id="39903-134">For more information about Microsoft Technical support for Office 365, see [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="39903-135">IP-portalwebbplats för skräp post</span><span class="sxs-lookup"><span data-stu-id="39903-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="39903-136">Det här är en självbetjänings portal som du kan använda för att ta bort dig själv från listan med spärrade avsändare i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="39903-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="39903-137">Använd den här portalen om du får ett fel meddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Microsoft 365 och du inte tycker att du ska vara.</span><span class="sxs-lookup"><span data-stu-id="39903-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="39903-138">Mer information finns i [använda List Portal för att ta bort dig själv från listan Spärrade avsändare](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="39903-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="39903-139">Missbruk och spam rapportering för skräp post från Exchange Online</span><span class="sxs-lookup"><span data-stu-id="39903-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="39903-140">Ibland används Microsoft365 av tredje part för att skicka skräp post, i strid mot våra villkor avseende användning och policy.</span><span class="sxs-lookup"><span data-stu-id="39903-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="39903-141">Om du får skräp post från Office 365 kan du rapportera dessa meddelanden till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39903-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="39903-142">Anvisningar finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="39903-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>
