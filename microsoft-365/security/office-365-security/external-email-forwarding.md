---
title: Konfigurera och kontrol lera extern e-postvidarekoppling, automatisk vidarebefordran, 5.7.520 åtkomst nekad, inaktivera extern vidarebefordran, administratören har inaktiverat extern vidarebefordran, utgående princip för skräp post
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: c0a3849d330b508630eb60c7ee24cd8b498a32b8
ms.sourcegitcommit: 260c69fa31a898428d51cfdbd762c5f0213c403c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "48417229"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="25a61-103">Konfigurera extern vidarebefordran av e-post i Office 365</span><span class="sxs-lookup"><span data-stu-id="25a61-103">Configuring external email forwarding in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="25a61-104">Extern vidarebefordran styrs av *principen för utgående skräp post* och omfattning för användare baserat på den konfigurerade inställningen.</span><span class="sxs-lookup"><span data-stu-id="25a61-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="25a61-105">För närvarande finns det stöd för tre inställningar:</span><span class="sxs-lookup"><span data-stu-id="25a61-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="25a61-106">**Automatisk** – det här är systemstyrt: utgående skräp post filtrering för automatisk överföring av externa e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="25a61-106">**Automatic** – This is system-controlled: It allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="25a61-107">Detta är standardinställningen.</span><span class="sxs-lookup"><span data-stu-id="25a61-107">This is the default setting.</span></span>

- <span data-ttu-id="25a61-108">**På** – automatisk extern vidarebefordran är tillåten och inte begränsad.</span><span class="sxs-lookup"><span data-stu-id="25a61-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="25a61-109">**Av** – automatisk extern vidarekoppling är inaktiverat och resulterar i en rapport om utebliven leverans (NDR) för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="25a61-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="25a61-110">Mer information om hur du konfigurerar dessa inställningar finns i [Konfigurera filtrering för utgående e-post i EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) .</span><span class="sxs-lookup"><span data-stu-id="25a61-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) for more information on how to configure these settings.</span></span>

> [!NOTE]
> <span data-ttu-id="25a61-111">Om du inaktiverar automatisk vidarebefordran inaktive ras även regler för Inkorgen som omdirigerar meddelanden till externa adresser.</span><span class="sxs-lookup"><span data-stu-id="25a61-111">Disabling automatic forwarding will also disable Inbox rules that redirect messages to external addresses.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="25a61-112">Styra extern e-postvidarebefordran</span><span class="sxs-lookup"><span data-stu-id="25a61-112">Controlling external email forwarding</span></span>

<span data-ttu-id="25a61-113">Som administratör för en organisation kan du ha företags krav för att begränsa eller kontrol lera vem som kan vidarebefordra e-postmeddelanden med hjälp av regler för Inkorgen, eller SMTP-vidarekoppling utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="25a61-113">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="25a61-114">Vidarebefordran av e-post kan vara en användbar funktion, men du kan också skapa en risk genom att informationen avslöjas, även genom att tillhandahålla information till angripare som kan utnyttja organisationen eller dess partners.</span><span class="sxs-lookup"><span data-stu-id="25a61-114">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="25a61-115">Office 365 tillåter inte automatisk extern vidarebefordran av antingen Inkorgshanteraren eller konfiguration av e-postlåda, vilket ger en säker standard princip.</span><span class="sxs-lookup"><span data-stu-id="25a61-115">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="25a61-116">Administratören kan dock ändra dessa inställningar för alla eller vissa användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="25a61-116">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="25a61-117">Vidarebefordrade meddelanden mellan interna användare påverkas inte av en sådan modifiering.</span><span class="sxs-lookup"><span data-stu-id="25a61-117">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="25a61-118">Det går inte att inaktivera automatisk vidarebefordran till externa adresser i Office 365 i faser med uppgifter som kommunicerats via [meddelanden i meddelande Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) .</span><span class="sxs-lookup"><span data-stu-id="25a61-118">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="25a61-119">För att administratörer ska kunna förbereda sig för dessa ändringar har de ändrat principer i förväg för att säkerställa att användarna inte störs.</span><span class="sxs-lookup"><span data-stu-id="25a61-119">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="25a61-120">Mer information om användare som använder automatisk vidarebefordran (regler för Inkorgen eller SMTP-vidarekoppling) i din organisation finns i [rapporten automatisk vidarebefordrade meddelanden](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="25a61-120">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span></span>

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a><span data-ttu-id="25a61-121">Hur fungerar den här principen med andra kontroller för vidarekoppling av automatiskt</span><span class="sxs-lookup"><span data-stu-id="25a61-121">How does this policy work with other automatic forwarding controls</span></span>

<span data-ttu-id="25a61-122">Som administratör kan du ha andra typer av kontroller på plats, så blockering av automatisk vidarebefordran i [fjärrdomäner](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) och användning av en Exchange-Exchange.</span><span class="sxs-lookup"><span data-stu-id="25a61-122">As an admin, you may already have other types of controls in place, such blocking automatic forwarding in [remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) and the use of an Exchange Transport Rule (ETR).</span></span> <span data-ttu-id="25a61-123">Båda de här kontrollerna är oberoende av den här funktionen, till exempel om du tillåter automatisk vidarebefordran av en fjärrdomän, men blockerar automatisk vidarebefordran via den skräp post princip som visas, blir det automatiskt vidarebefordrade meddelandet blockerat.</span><span class="sxs-lookup"><span data-stu-id="25a61-123">Both of these controls are independent of this particular feature, for example if you allow automatic forwarding for a remote domain, but block automatic forwarding via the outbound spam policy the result will be that the automatically forwarded message is blocked.</span></span> <span data-ttu-id="25a61-124">Om du tillåter automatisk vidarebefordran i principen för utgående skräp post men blockerar den i en Exchange eller fjärrdomän blockeras meddelandet av någon av dessa kontroller.</span><span class="sxs-lookup"><span data-stu-id="25a61-124">Similarly if you allow automatic forwarding in the outbound spam policy but block it in an ETR or remote domain then the message will be blocked by either of these controls.</span></span> <span data-ttu-id="25a61-125">Då kan du till exempel tillåta automatisk vidarebefordran i principen för utgående skräp post och använda fjärrdomäner för att styra domänerna som användarna kan vidarekoppla meddelanden automatiskt till.</span><span class="sxs-lookup"><span data-stu-id="25a61-125">This allows you to, for example, allow automatic forwarding in the outbound spam policy and utilize remote domains to control the domains that users can automatic forward messages to.</span></span>


## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="25a61-126">Meddelande om blockerad e-post</span><span class="sxs-lookup"><span data-stu-id="25a61-126">The blocked email forwarding message</span></span>

<span data-ttu-id="25a61-127">När ett meddelande identifieras som automatiskt vidarebefordrat och organisations princip *blocken* som **aktivitet kommer att** genereras tillbaka till slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="25a61-127">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="25a61-128">Rapporten indikerar att meddelandet inte har levererats.</span><span class="sxs-lookup"><span data-stu-id="25a61-128">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="25a61-129">NDR har följande format:</span><span class="sxs-lookup"><span data-stu-id="25a61-129">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
