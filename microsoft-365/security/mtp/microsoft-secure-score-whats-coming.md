---
title: Vad kommer i Microsoft Secure Score?
description: I artikeln beskrivs Microsoft Secure Score i säkerhetscentret Microsoft 365, hur information beräknas och vilka säkerhetsadministratörer som kan förvänta sig.
keywords: säkerhet, malware, Microsoft 365, M365, säker poäng, säkerhetscenter, förbättringsåtgärder
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 1a5c5ae702f16bbf47be83837cf244cdd64278cd
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541113"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="f19e4-104">Vad kommer i Microsoft Secure Score?</span><span class="sxs-lookup"><span data-stu-id="f19e4-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="f19e4-105">För att göra Microsoft Secure Score till en bättre representant för din säkerhetsposition och förbättra användbarheten gör vi vissa ändringar inom en snar framtid.</span><span class="sxs-lookup"><span data-stu-id="f19e4-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="f19e4-106">Din poäng och högsta möjliga poäng kommer att förändras.</span><span class="sxs-lookup"><span data-stu-id="f19e4-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="f19e4-107">Detta innebär dock inte en förändring i din säkerhetsposition.</span><span class="sxs-lookup"><span data-stu-id="f19e4-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="f19e4-108">Mer information om de senaste ändringarna finns [i Vad är nytt i Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="f19e4-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="f19e4-109">21 april 2020</span><span class="sxs-lookup"><span data-stu-id="f19e4-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="f19e4-110">Ta bort förbättringsåtgärder som inte uppfyller förväntningarna för tillförlitlig mätning eller inte ger en användbar representation av säkerhetshållning</span><span class="sxs-lookup"><span data-stu-id="f19e4-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="f19e4-111">För att säkerställa att Microsoft Secure Score är meningsfull och att varje förbättringsåtgärd är mätbar och tillförlitlig tar vi bort följande förbättringsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="f19e4-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="f19e4-112">Använda IRM-skydd på dokument</span><span class="sxs-lookup"><span data-stu-id="f19e4-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="f19e4-113">Tillämpa principer för förebyggande av dataförlust</span><span class="sxs-lookup"><span data-stu-id="f19e4-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-in-the-preview-version"></a><span data-ttu-id="f19e4-114">Lägga till Azure AD-förbättringsåtgärd i förhandsversionen</span><span class="sxs-lookup"><span data-stu-id="f19e4-114">Adding Azure AD improvement action in the preview version</span></span>

- <span data-ttu-id="f19e4-115">Tillåt inte användare att bevilja samtycke till ohanterada program (finns för närvarande i släppt version)</span><span class="sxs-lookup"><span data-stu-id="f19e4-115">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-in-the-preview-version"></a><span data-ttu-id="f19e4-116">Lägga till Azure ATP-förbättringsåtgärder i förhandsversionen</span><span class="sxs-lookup"><span data-stu-id="f19e4-116">Adding Azure ATP improvement actions in the preview version</span></span>

- <span data-ttu-id="f19e4-117">Inaktivera tjänsten Utskriftshanteraren på domänkontrollanter</span><span class="sxs-lookup"><span data-stu-id="f19e4-117">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="f19e4-118">Ändra osäkra Kerberos-delegationer för att förhindra personifiering</span><span class="sxs-lookup"><span data-stu-id="f19e4-118">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="f19e4-119">Skydda och hantera lokala administratörslösenord med Microsoft LAPS</span><span class="sxs-lookup"><span data-stu-id="f19e4-119">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="f19e4-120">Minska risken för lateral rörelsebana för känsliga enheter</span><span class="sxs-lookup"><span data-stu-id="f19e4-120">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="f19e4-121">Ta bort vilande konton från känsliga grupper</span><span class="sxs-lookup"><span data-stu-id="f19e4-121">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="f19e4-122">Ta bort oskyddade SID-historikattribut från entiteter</span><span class="sxs-lookup"><span data-stu-id="f19e4-122">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="f19e4-123">Lösa oskyddade kontoattribut</span><span class="sxs-lookup"><span data-stu-id="f19e4-123">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="f19e4-124">Stoppa exponering för rensa textuppgifter</span><span class="sxs-lookup"><span data-stu-id="f19e4-124">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="f19e4-125">Stoppa äldre protokollkommunikation</span><span class="sxs-lookup"><span data-stu-id="f19e4-125">Stop legacy protocols communication</span></span>
- <span data-ttu-id="f19e4-126">Stoppa svag chifferanvändning</span><span class="sxs-lookup"><span data-stu-id="f19e4-126">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-the-preview-version"></a><span data-ttu-id="f19e4-127">Stöd för säkerhetsrekommendationer för Microsoft Defender ATP Threat & Vulnerability Management (TVM) i förhandsversionen</span><span class="sxs-lookup"><span data-stu-id="f19e4-127">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in the preview version</span></span>

- <span data-ttu-id="f19e4-128">Alla utgivna säkerhetsrekommendationer från TVM kommer nu också att finnas tillgängliga i Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="f19e4-128">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
