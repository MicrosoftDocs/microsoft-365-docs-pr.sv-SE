---
title: Konfigurera och styra extern vidarebefordran av e-post, Automatisk vidarebefordran, 5.7.520 Åtkomst nekad, inaktivera extern vidarebefordran, Administratören har inaktiverat extern vidarebefordran, utgående policy mot skräppost
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
ms.openlocfilehash: 88c3dae4f5a6786fe4eddea0d5e1c61dda837a87
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080119"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="c8d9d-103">Konfigurera extern vidarebefordran av e-post i Office 365</span><span class="sxs-lookup"><span data-stu-id="c8d9d-103">Configuring external email forwarding in Office 365</span></span>

<span data-ttu-id="c8d9d-104">Extern vidarebefordran styrs av principen *om utgående skräppost* och begränsas till användare baserat på den konfigurerade inställningen.</span><span class="sxs-lookup"><span data-stu-id="c8d9d-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="c8d9d-105">För närvarande stöds 3 inställningar:</span><span class="sxs-lookup"><span data-stu-id="c8d9d-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="c8d9d-106">**Automatisk** – I det här läget är systemet ansvarigt för att avgöra om ett vidarebefordrat meddelande är tillåtet eller inte.</span><span class="sxs-lookup"><span data-stu-id="c8d9d-106">**Automatic** – In this mode the system is responsible for deciding if a forwarded message is allowed or not.</span></span>  <span data-ttu-id="c8d9d-107">Detta är standardläget och i det här läget blockerar systemet automatisk extern vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="c8d9d-107">This is the default mode and in this mode the system will block automatic external forwarding.</span></span>

- <span data-ttu-id="c8d9d-108">**På** – Automatisk extern vidarebefordran är tillåten och inte begränsad.</span><span class="sxs-lookup"><span data-stu-id="c8d9d-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="c8d9d-109">**Av** – Automatisk extern vidarebefordran är inaktiverad och resulterar i en rapport om utebliven leverans (NDR) till slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="c8d9d-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="c8d9d-110">Mer information om hur du konfigurerar dessa inställningar finns [i Konfigurera skräppostfiltrering i EOP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="c8d9d-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) for more information on how to configure these settings.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="c8d9d-111">Styra vidarebefordran av extern e-post</span><span class="sxs-lookup"><span data-stu-id="c8d9d-111">Controlling external email forwarding</span></span>

<span data-ttu-id="c8d9d-112">Som administratör för en organisation kan du ha företagskrav för att begränsa eller kontrollera vem som automatiskt kan vidarebefordra e-postmeddelanden med hjälp av inkorgsregler, eller SMTP-vidarebefordran, utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="c8d9d-112">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="c8d9d-113">Vidarebefordran av e-post kan vara en användbar funktion, men kan också utgöra en risk genom att eventuellt lämna ut information, även genom att tillhandahålla information till angripare som kan utnyttjas för att attackera organisationen eller dess partner.</span><span class="sxs-lookup"><span data-stu-id="c8d9d-113">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="c8d9d-114">Office 365 tillåter inte automatisk extern vidarekoppling av vare sig inkorgsregler eller e-postboxkonfiguration, vilket ger en säker standardprincip.</span><span class="sxs-lookup"><span data-stu-id="c8d9d-114">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="c8d9d-115">Administratören kan dock ändra dessa inställningar för alla eller vissa användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c8d9d-115">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="c8d9d-116">Vidarebefordra meddelanden mellan interna användare påverkas inte av en sådan ändring.</span><span class="sxs-lookup"><span data-stu-id="c8d9d-116">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="c8d9d-117">Inaktivera automatisk vidarebefordran till externa adresser i Office 365 rullas ut i faser med information som kommuniceras via [Message Center-inlägg.](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="c8d9d-117">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="c8d9d-118">För att hjälpa administratörer att förbereda sig för dessa ändringar får de ändra principer i förväg för att säkerställa att det inte finns några störningar för användarna.</span><span class="sxs-lookup"><span data-stu-id="c8d9d-118">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="c8d9d-119">Mer information om användare som använder automatisk vidarebefordran (inkorgsregler eller SMTP-vidarebefordran) i organisationen finns i [rapporten Automatiskt vidarebefordrade meddelanden](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="c8d9d-119">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="c8d9d-120">Meddelandet om vidarebefordran av e-post</span><span class="sxs-lookup"><span data-stu-id="c8d9d-120">The blocked email forwarding message</span></span>

<span data-ttu-id="c8d9d-121">När ett meddelande identifieras som automatiskt vidarebefordras och *organisationsprincipen blockerar* aktiviteten genereras en rapport **om utebliven leverans (NDR)** tillbaka till slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="c8d9d-121">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="c8d9d-122">Rapporten visar att meddelandet inte levererades.</span><span class="sxs-lookup"><span data-stu-id="c8d9d-122">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="c8d9d-123">NDR kommer att ha följande format:</span><span class="sxs-lookup"><span data-stu-id="c8d9d-123">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
