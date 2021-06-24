---
title: Meddelandespårning i Microsoft 365 Defender portalen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan använda länken för meddelandespårning i e Microsoft 365 Defender portalen för att ta reda på vad som har hänt med meddelandena.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108133"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="db320-103">Meddelandespårning i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="db320-103">Message trace in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="db320-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="db320-104">**Applies to**</span></span>
- [<span data-ttu-id="db320-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="db320-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="db320-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="db320-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="db320-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db320-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="db320-108">Meddelandespårning i Microsoft 365 Defender e-postmeddelanden när de färdas genom din Exchange Online organisation.</span><span class="sxs-lookup"><span data-stu-id="db320-108">Message trace in the Microsoft 365 Defender portal follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="db320-109">Du kan avgöra om ett meddelande har tagits emot, avvisats, skjutits upp eller levererats av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="db320-109">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="db320-110">Det visar också vilka åtgärder som har vidtagits för meddelandet innan det nått sin slutgiltiga status.</span><span class="sxs-lookup"><span data-stu-id="db320-110">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="db320-111">Du kan använda informationen från meddelandespårning för att effektivt svara på användarfrågor om vad som har hänt med meddelanden, felsöka problem i e-postflödet och verifiera principändringar.</span><span class="sxs-lookup"><span data-stu-id="db320-111">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
> <span data-ttu-id="db320-112">Meddelandespårning i Microsoft 365 Defender-portalen går bara vidare till Meddelandespårning i Exchange administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="db320-112">Message trace in the Microsoft 365 Defender portal is just a pass through to Message trace in the Exchange admin center.</span></span> <span data-ttu-id="db320-113">Mer information finns i [Meddelandespårning i det moderna Exchange administrationscentret.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="db320-113">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="db320-114">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="db320-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="db320-115">Du måste vara medlem i rollgrupperna **Organisationshantering,** Efterlevnadshantering eller Supportavdelning i Exchange Online **använda** meddelandespårning.  </span><span class="sxs-lookup"><span data-stu-id="db320-115">You need to be a member of the **Organization Management**, **Compliance Management** or **Help Desk** role groups in **Exchange Online** to use message trace.</span></span> <span data-ttu-id="db320-116">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="db320-116">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="db320-117">**Kommentarer:** Medlemskap i motsvarande Azure Active Directory roll i Administrationscenter för Microsoft 365 ger användarna  nödvändiga behörigheter och behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db320-117">**Notes**: Membership in the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="db320-118">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="db320-118">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="db320-119">Det maximala antalet meddelanden som visas i resultatet av en meddelandespårning beror på vilken rapporttyp du valde (mer information finns i avsnittet [Välj](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) rapporttyp).</span><span class="sxs-lookup"><span data-stu-id="db320-119">The maximum number of messages that are displayed in the results of a message trace depends on the report type you selected (see the [Choose report type](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) section for details).</span></span> <span data-ttu-id="db320-120">[Cmdlet:en Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) i Exchange Online PowerShell eller fristående EOP PowerShell returnerar alla meddelanden i resultatet.</span><span class="sxs-lookup"><span data-stu-id="db320-120">The [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="db320-121">Öppna meddelandespårning</span><span class="sxs-lookup"><span data-stu-id="db320-121">Open message trace</span></span>

<span data-ttu-id="db320-122">I portalen Microsoft 365 Defender ( <https://security.microsoft.com> ) går du till Skicka **e-& samarbete** \> **Exchange meddelandespårning**.</span><span class="sxs-lookup"><span data-stu-id="db320-122">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration** \> **Exchange message trace**.</span></span> <span data-ttu-id="db320-123">Du kan också använda för att gå direkt till sidan <https://admin.exchange.microsoft.com/#/messagetrace> Meddelandespårning.</span><span class="sxs-lookup"><span data-stu-id="db320-123">Or, to go directly to the message trace page, use <https://admin.exchange.microsoft.com/#/messagetrace>.</span></span>

<span data-ttu-id="db320-124">I det här läget öppnas meddelandespårning i EAC.</span><span class="sxs-lookup"><span data-stu-id="db320-124">At this point, message trace in the EAC opens.</span></span> <span data-ttu-id="db320-125">Mer information finns i [Meddelandespårning i det moderna Exchange administrationscentret.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="db320-125">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>
