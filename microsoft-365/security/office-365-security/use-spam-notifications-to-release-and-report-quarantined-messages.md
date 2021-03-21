---
title: Skräppost-aviseringar för slutanvändare i Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om skräppost-aviseringar för slutanvändare för meddelanden i karantän i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 617ff9b6325ac2d5d95d8bc591b9e4ebb7f5434d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921126"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="eaaa8-103">Använda skräppost-aviseringar för användare för att släppa och rapportera meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="eaaa8-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eaaa8-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="eaaa8-104">**Applies to**</span></span>
- [<span data-ttu-id="eaaa8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="eaaa8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="eaaa8-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="eaaa8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="eaaa8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eaaa8-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="eaaa8-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="eaaa8-109">Mer information finns i [Meddelanden i karantän i EOP.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="eaaa8-109">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="eaaa8-110">Som standard är skräppost-aviseringar för slutanvändare inaktiverade i principerna för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-110">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="eaaa8-111">När en administratör aktiverar [skräppost-aviseringar](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)för slutanvändare får mottagare (inklusive delade postlådor med automatisk mappning aktiverat) periodiska aviseringar om meddelanden som har satts i karantän som skräppost, massutskick eller (från och med april 2020) nätfiske.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-111">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="eaaa8-112">För delade postlådor stöds skräppost-aviseringar för slutanvändare endast för användare som får behörigheten FullAccess till den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-112">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="eaaa8-113">Mer information finns i Använda [EAC för att redigera delegering av delad postlåda.](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)</span><span class="sxs-lookup"><span data-stu-id="eaaa8-113">For more information, see [Use the EAC to edit shared mailbox delegation](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="eaaa8-114">Skräppost-avisering för slutanvändare stöds inte för grupper.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-114">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="eaaa8-115">Meddelanden som har satts i karantän som nätfiske, skadlig kod eller genom e-postflödesregler (kallas även transportregler) är bara tillgängliga för administratörer.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-115">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="eaaa8-116">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="eaaa8-116">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="eaaa8-117">En skräppost-avisering för slutanvändaren innehåller följande information för varje meddelande i karantän:</span><span class="sxs-lookup"><span data-stu-id="eaaa8-117">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="eaaa8-118">**Avsändare**: Skicka meddelandets namn och e-postadress.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-118">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="eaaa8-119">**Ämne**: Ämnesraden i det i karantän-meddelandet.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-119">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="eaaa8-120">**Datum:** Datum och tid (i UTC) då meddelandet satt i karantän.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-120">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="eaaa8-121">**Spärra avsändare:** Klicka på den här länken om du vill lägga till avsändaren i listan Spärrade avsändare.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-121">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="eaaa8-122">Mer information finns i Spärra [en e-postavsändare.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)</span><span class="sxs-lookup"><span data-stu-id="eaaa8-122">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="eaaa8-123">**Version:** För skräppost (inte nätfiske) kan du släppa meddelandet här utan att gå till karantänen för & säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-123">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="eaaa8-124">**Granska**&: Klicka på den här länken för att gå till karantän i säkerhets- och efterlevnadscentret, där du kan visa , släppa, ta bort eller rapportera dina meddelanden i karantän (beroende på varför meddelandet satt i karantän).</span><span class="sxs-lookup"><span data-stu-id="eaaa8-124">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="eaaa8-125">Mer information finns i [Hitta och släppa meddelanden i karantän som en användare i EOP.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="eaaa8-125">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Exempel på skräppost-avisering för slutanvändare](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="eaaa8-127">Spärrade avsändare kan fortfarande skicka e-post till dig.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-127">A blocked sender can still send you mail.</span></span> <span data-ttu-id="eaaa8-128">Alla meddelanden från den här avsändaren som skickar dem till din postlåda flyttas omedelbart till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-128">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="eaaa8-129">Framtida meddelanden från den här avsändaren hamnar i mappen Skräppost eller till slutanvändares karantän.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-129">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="eaaa8-130">Om du vill ta bort dessa meddelanden vid ankomst i stället för att kvartiler kan du använda e-postflödesregler [(kallas](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) även transportregler) för att ta bort meddelandena när de anländer.</span><span class="sxs-lookup"><span data-stu-id="eaaa8-130">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>