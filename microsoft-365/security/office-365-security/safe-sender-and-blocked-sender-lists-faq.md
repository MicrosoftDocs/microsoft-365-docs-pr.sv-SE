---
title: Betrodd avsändare och blockerade avsändarlistor i Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Som eop-administratör (Exchange Online eller Exchange Online Protection) kan du se till att ett e-postmeddelande som färdas via tjänsten inte markeras som skräppost. Ett sätt att göra detta är att skapa en säker avsändare och blockerade avsändarlistor för personerna i organisationen.
ms.openlocfilehash: 959af558c32e71e5a4cede2aff7bbcd1dbb092e2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806049"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="7df32-104">Betrodd avsändare och blockerade avsändarlistor i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7df32-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="7df32-105">Som eop-administratör (Exchange Online eller Exchange Online Protection) kan du se till att ett e-postmeddelande som färdas via tjänsten inte markeras som skräppost.</span><span class="sxs-lookup"><span data-stu-id="7df32-105">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam.</span></span> <span data-ttu-id="7df32-106">Ett sätt att göra detta är att skapa en säker avsändare och blockerade avsändarlistor för personerna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="7df32-106">One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span>

<span data-ttu-id="7df32-107">*Se den uppdaterade versionen av tipsen och procedurerna för hur du arbetar med dessa listor som administratör i* Så här förhindrar du att bra [e-post markeras som skräppost i Office 365](prevent-email-from-being-marked-as-spam.md).</span><span class="sxs-lookup"><span data-stu-id="7df32-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [How to prevent good email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md).</span></span>

<span data-ttu-id="7df32-108">Om du inte är administratör och bara vill hantera din egen skräppost i Outlook med hjälp av en lista över betrodda avsändare kan du läsa stegen i[översikten över skräppostfiltret](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span><span class="sxs-lookup"><span data-stu-id="7df32-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in the[Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="7df32-109">Vilka är de säkra och blockerade avsändargränserna i Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="7df32-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="7df32-110">De säkra och blockerade avsändargränserna i Exchange Online skiljer sig från Active Directory- och Outlook-gränserna.</span><span class="sxs-lookup"><span data-stu-id="7df32-110">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits.</span></span> <span data-ttu-id="7df32-111">De är:</span><span class="sxs-lookup"><span data-stu-id="7df32-111">They are:</span></span>

- <span data-ttu-id="7df32-112">Säker avsändare gräns: 1.024</span><span class="sxs-lookup"><span data-stu-id="7df32-112">Safe sender limit: 1,024</span></span>

- <span data-ttu-id="7df32-113">Spärrad avsändaregräns: 500</span><span class="sxs-lookup"><span data-stu-id="7df32-113">Blocked sender limit: 500</span></span>

<span data-ttu-id="7df32-114">Obs!</span><span class="sxs-lookup"><span data-stu-id="7df32-114">Note:</span></span>

<span data-ttu-id="7df32-115">Felet som beskrivs i [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)kan uppstå.</span><span class="sxs-lookup"><span data-stu-id="7df32-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="7df32-116">LÃ¶s problemet genom att avmarkera kryssrutan "Betrodda e-postmeddelanden frÃ¥n mina kontakter".</span><span class="sxs-lookup"><span data-stu-id="7df32-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="7df32-117">Du kan också minska mängden e-postadresser som finns i standardmappen Kontakter för att få den inom den högsta tillåtna gränsen på 1024 i Exchange Online som är inställt för attributet "MaxSafeSenders".</span><span class="sxs-lookup"><span data-stu-id="7df32-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="7df32-118">Mer information om det här attributet och cmdleten Ange postlåda finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="7df32-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>

[<span data-ttu-id="7df32-119">Ange postlåda</span><span class="sxs-lookup"><span data-stu-id="7df32-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a><span data-ttu-id="7df32-120">Se även</span><span class="sxs-lookup"><span data-stu-id="7df32-120">See also</span></span>

[<span data-ttu-id="7df32-121">Avsändaresfiltrering i Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7df32-121">Sender filtering in Exchange Server</span></span>](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
