---
title: E-postmeddelanden i karantän
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om karantän i Exchange Online Protection (EOP) som kan vara skadlig eller oönskade meddelanden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b2a11f5f9e1e730a3b0cc09625ec8e8cb592d869
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333812"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="36ee4-103">E-postmeddelanden i karantän i EOP</span><span class="sxs-lookup"><span data-stu-id="36ee4-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="36ee4-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="36ee4-104">**Applies to**</span></span>
- [<span data-ttu-id="36ee4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="36ee4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="36ee4-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="36ee4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="36ee4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36ee4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="36ee4-108">I Microsoft 365 organisationer som har postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection Exchange Online) är karantän tillgänglig för potentiellt skadliga eller oönskade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="36ee4-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="36ee4-109">Principer för skydd mot skadlig programvara sätt automatiskt ett meddelande i karantän *om en* bifogad fil påträffas som innehåller skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="36ee4-109">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="36ee4-110">Mer information finns i Konfigurera [principer för skydd mot skadlig programvara i EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="36ee4-110">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="36ee4-111">Som standard sätts skräppostprinciper i karantän för nätfiskemeddelanden och skickar skräppost och massutskick till användarens skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="36ee4-111">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="36ee4-112">Men du kan också skapa och anpassa principer för skräppostskydd för att sätta skräppost i karantän och massutskick.</span><span class="sxs-lookup"><span data-stu-id="36ee4-112">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="36ee4-113">Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="36ee4-113">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="36ee4-114">Både användare och administratörer kan arbeta med meddelanden i karantän:</span><span class="sxs-lookup"><span data-stu-id="36ee4-114">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="36ee4-115">Administratörer kan arbeta med alla typer av meddelanden i karantän för alla användare.</span><span class="sxs-lookup"><span data-stu-id="36ee4-115">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="36ee4-116">Endast administratörer kan arbeta med meddelanden som har satts i karantän som skadlig kod, nätfiske med hög säkerhet eller som ett resultat av e-postflödesregler (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="36ee4-116">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="36ee4-117">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="36ee4-117">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="36ee4-118">Användare kan arbeta med meddelanden i karantän där de är mottagare om meddelandet satts i karantän som skräppost, massutskick eller nätfiske (från och med april 2020).</span><span class="sxs-lookup"><span data-stu-id="36ee4-118">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="36ee4-119">Mer information finns i [Hitta och släppa meddelanden i karantän som en användare i EOP.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="36ee4-119">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="36ee4-120">För att hindra användare från att hantera sina egna nätfiskemeddelanden  i karantän kan administratörer konfigurera en annan åtgärd för filtrering av nätfiske-e-postmeddelanden med filtrering av skräppost.</span><span class="sxs-lookup"><span data-stu-id="36ee4-120">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="36ee4-121">Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="36ee4-121">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="36ee4-122">Administratörer och användare kan rapportera falska positiva resultat till Microsoft i karantän.</span><span class="sxs-lookup"><span data-stu-id="36ee4-122">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="36ee4-123">Mer information om karantän finns i Vanliga frågor [och svar om karantän.](quarantine-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="36ee4-123">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.yml).</span></span>
