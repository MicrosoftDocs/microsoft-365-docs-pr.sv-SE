---
title: Inaktivera skräppostrapportering i Outlook på webben
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: Som Office 365-administratör kan du inaktivera möjligheten för personer att rapportera e-post som skräppost.
ms.openlocfilehash: 0bca03786d0335c24e48340e588510f09d6f6a7e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811137"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="4debe-103">Inaktivera skräppostrapportering i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="4debe-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="4debe-104">Du kan skicka skräppost, skräppost och inte skräpmeddelanden till Microsoft för analys med hjälp av Outlook på webben (tidigare känt som Outlook Web App) skräprapporteringsalternativ, enligt beskrivningen i [Rapportera skräppost och nätfiskebedrägerier i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4debe-104">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web (formerly known as Outlook Web App) junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span> <span data-ttu-id="4debe-105">Om du inte vill använda dessa alternativ kan administratörer stänga av dem via cmdleten [Set-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="4debe-105">If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) cmdlet.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4debe-106">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="4debe-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="4debe-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="4debe-107"><a name="sectionSection0"> </a></span></span>

- <span data-ttu-id="4debe-108">Beräknad tid att slutföra: 5 minuter</span><span class="sxs-lookup"><span data-stu-id="4debe-108">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="4debe-109">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="4debe-109">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="4debe-110">Mer information om vilka behörigheter du behöver finns i posten "Outlook på webbpostlådeprinciperna" i [Exchange Online-behörigheter](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span><span class="sxs-lookup"><span data-stu-id="4debe-110">To see what permissions you need, see the "Outlook on the web mailbox policies" entry in [Exchange Online permissions](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span></span>

- <span data-ttu-id="4debe-111">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4debe-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="4debe-112">Inaktivera skräppost, nätfiske och inte skräppostrapportering till Microsoft</span><span class="sxs-lookup"><span data-stu-id="4debe-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="4debe-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="4debe-113"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="4debe-114">Kör först följande kommando för att hämta namnen på dina tillgängliga Outlook-principer för webbpostlådan:</span><span class="sxs-lookup"><span data-stu-id="4debe-114">First, run the following command to get the names of your available Outlook on the web mailbox policies:</span></span>

```
Get-OwaMailboxPolicy | Format-Table Name
```

<span data-ttu-id="4debe-115">Använd sedan följande syntax för att aktivera eller inaktivera skräppost och inte skräppostrapportering till Microsoft i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="4debe-115">Next, use the following syntax to enable or disable junk and not junk reporting to Microsoft in Outlook on the web:</span></span>

```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

<span data-ttu-id="4debe-116">I det här exemplet inaktiveras rapportering i standardprincipen för Outlook-webbappar:</span><span class="sxs-lookup"><span data-stu-id="4debe-116">This example turns off reporting in the default Outlook web app mailbox policy:</span></span>

```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

<span data-ttu-id="4debe-117">Detaljerad syntax- och parameterinformation finns i [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) och [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="4debe-117">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="4debe-118">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="4debe-118">How do you know this worked?</span></span>
<span data-ttu-id="4debe-119"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="4debe-119"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="4debe-120">Kör **Get-OWAMailboxPolicy** för att kontrollera parametervärdena och öppna sedan Outlook på webben för en berörd användare (som har principen Outlook på webbpostlådan som tillämpas på dem) och kontrollera att alternativen för att rapportera skräppost, nätfiske och inte skräppost inte är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="4debe-120">Run **Get-OWAMailboxPolicy** to check the parameter values, and then open Outlook on the web for an affected user (who has the Outlook on the web mailbox policy applied to them) and verify that the options to report junk, phishing, and not junk are not available.</span></span> <span data-ttu-id="4debe-121">Du kan fortfarande markera meddelanden som skräppost, nätfiske och inte skräp, men du kan inte rapportera dem.</span><span class="sxs-lookup"><span data-stu-id="4debe-121">You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span>
