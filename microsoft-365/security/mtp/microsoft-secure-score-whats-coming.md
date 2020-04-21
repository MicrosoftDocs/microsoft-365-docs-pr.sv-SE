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
ms.openlocfilehash: 234ae17ab31d56d1bbd65f1aa8ed29475e9cd155
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583721"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="698b3-104">Vad kommer i Microsoft Secure Score?</span><span class="sxs-lookup"><span data-stu-id="698b3-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="698b3-105">För att göra [Microsoft Secure Score](microsoft-secure-score.md) till en bättre representant för din säkerhetsposition och förbättra användbarheten gör vi vissa ändringar inom en snar framtid.</span><span class="sxs-lookup"><span data-stu-id="698b3-105">To make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="698b3-106">Din poäng och högsta möjliga poäng kommer att förändras.</span><span class="sxs-lookup"><span data-stu-id="698b3-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="698b3-107">Detta innebär dock inte en förändring i din säkerhetsposition.</span><span class="sxs-lookup"><span data-stu-id="698b3-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="698b3-108">Mer information om de senaste ändringarna finns [i Vad är nytt i Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="698b3-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="698b3-109">21 april 2020</span><span class="sxs-lookup"><span data-stu-id="698b3-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="698b3-110">Ta bort förbättringsåtgärder som inte uppfyller förväntningarna för tillförlitlig mätning eller inte ger en användbar representation av säkerhetshållning</span><span class="sxs-lookup"><span data-stu-id="698b3-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="698b3-111">För att säkerställa att Microsoft Secure Score är meningsfull och att varje förbättringsåtgärd är mätbar och tillförlitlig tar vi bort följande förbättringsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="698b3-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="698b3-112">Använda IRM-skydd på dokument</span><span class="sxs-lookup"><span data-stu-id="698b3-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="698b3-113">Tillämpa principer för förebyggande av dataförlust</span><span class="sxs-lookup"><span data-stu-id="698b3-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-to-preview"></a><span data-ttu-id="698b3-114">Lägga till Azure AD-förbättringsåtgärd i förhandsversionen</span><span class="sxs-lookup"><span data-stu-id="698b3-114">Adding Azure AD improvement action to preview</span></span>

<span data-ttu-id="698b3-115">Lägga till följande förbättringsåtgärd för Azure Active Directory i [förhandsversionen av Microsoft Secure Score:](microsoft-secure-score-preview.md)</span><span class="sxs-lookup"><span data-stu-id="698b3-115">Adding the following Azure Active Directory improvement action to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="698b3-116">Tillåt inte användare att bevilja samtycke till ohanterada program (finns för närvarande i släppt version)</span><span class="sxs-lookup"><span data-stu-id="698b3-116">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-to-preview"></a><span data-ttu-id="698b3-117">Lägga till Azure ATP-förbättringsåtgärder i förhandsversionen</span><span class="sxs-lookup"><span data-stu-id="698b3-117">Adding Azure ATP improvement actions to preview</span></span>

<span data-ttu-id="698b3-118">Lägga till följande azure advanced threat protection improvement actions i [förhandsversionen av Microsoft Secure Score:](microsoft-secure-score-preview.md)</span><span class="sxs-lookup"><span data-stu-id="698b3-118">Adding the following Azure Advanced Threat Protection improvement actions to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="698b3-119">Inaktivera tjänsten Utskriftshanteraren på domänkontrollanter</span><span class="sxs-lookup"><span data-stu-id="698b3-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="698b3-120">Ändra osäkra Kerberos-delegationer för att förhindra personifiering</span><span class="sxs-lookup"><span data-stu-id="698b3-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="698b3-121">Skydda och hantera lokala administratörslösenord med Microsoft LAPS</span><span class="sxs-lookup"><span data-stu-id="698b3-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="698b3-122">Minska risken för lateral rörelsebana för känsliga enheter</span><span class="sxs-lookup"><span data-stu-id="698b3-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="698b3-123">Ta bort vilande konton från känsliga grupper</span><span class="sxs-lookup"><span data-stu-id="698b3-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="698b3-124">Ta bort oskyddade SID-historikattribut från entiteter</span><span class="sxs-lookup"><span data-stu-id="698b3-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="698b3-125">Lösa oskyddade kontoattribut</span><span class="sxs-lookup"><span data-stu-id="698b3-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="698b3-126">Stoppa exponering för rensa textuppgifter</span><span class="sxs-lookup"><span data-stu-id="698b3-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="698b3-127">Stoppa äldre protokollkommunikation</span><span class="sxs-lookup"><span data-stu-id="698b3-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="698b3-128">Stoppa svag chifferanvändning</span><span class="sxs-lookup"><span data-stu-id="698b3-128">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-preview"></a><span data-ttu-id="698b3-129">Stöd för säkerhetsrekommendationer för Microsoft Defender ATP Threat & Vulnerability Management (TVM) i förhandsversionen</span><span class="sxs-lookup"><span data-stu-id="698b3-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in preview</span></span>

<span data-ttu-id="698b3-130">Alla utgivna säkerhetsrekommendationer som tillhandahålls av TVM kommer nu också att vara tillgängliga [förhandsgranskningsversionen av Microsoft Secure Score](microsoft-secure-score-preview.md).</span><span class="sxs-lookup"><span data-stu-id="698b3-130">All released security recommendations supplied by TVM will now also be available the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md).</span></span>
