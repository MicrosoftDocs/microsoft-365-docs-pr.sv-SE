---
title: Vad kommer i Microsoft Secure Score?
description: I artikeln beskrivs Microsoft Secure Score i Microsoft 365-säkerhetscentret, hur information beräknas och vilka säkerhetsadministratörer som kan förvänta sig.
keywords: säkerhet, skadlig kod, Microsoft 365, M365, säker poäng, säkerhetscenter, förbättringsåtgärder
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
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42807253"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="f7abc-104">Vad kommer i Microsoft Secure Score?</span><span class="sxs-lookup"><span data-stu-id="f7abc-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="f7abc-105">För att göra Microsoft Secure Score till en bättre representant för din säkerhetsposition och förbättra användbarheten gör vi vissa ändringar inom en snar framtid.</span><span class="sxs-lookup"><span data-stu-id="f7abc-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="f7abc-106">Din poäng och högsta möjliga poäng kommer att förändras.</span><span class="sxs-lookup"><span data-stu-id="f7abc-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="f7abc-107">Detta innebär dock inte en förändring i din säkerhet hållning.</span><span class="sxs-lookup"><span data-stu-id="f7abc-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="f7abc-108">Mer information om de senaste ändringarna finns [i Nyheter i Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="f7abc-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="f7abc-109">16 mars 2020</span><span class="sxs-lookup"><span data-stu-id="f7abc-109">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="f7abc-110">Ta bort förbättringsåtgärder som inte uppfyller förväntningarna på tillförlitlig mätning eller inte ger en användbar representation av säkerhetshållning</span><span class="sxs-lookup"><span data-stu-id="f7abc-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="f7abc-111">För att säkerställa att Microsoft Secure Score är meningsfull och att varje förbättringsåtgärd är mätbar och tillförlitlig tar vi bort följande förbättringsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="f7abc-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="f7abc-112">Lagra användardokument i OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="f7abc-112">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="f7abc-113">Konfigurera principer för säker bifogad fil i Office 365</span><span class="sxs-lookup"><span data-stu-id="f7abc-113">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="f7abc-114">Konfigurera Office 365-säkra länkar för att verifiera webbadresser</span><span class="sxs-lookup"><span data-stu-id="f7abc-114">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="f7abc-115">Tillåt inte postlådedelegering</span><span class="sxs-lookup"><span data-stu-id="f7abc-115">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="f7abc-116">Tillåt anonyma gästdelningslänkar för webbplatser och dokument</span><span class="sxs-lookup"><span data-stu-id="f7abc-116">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="f7abc-117">Aktivera säkerhetskonsolen för molnappar</span><span class="sxs-lookup"><span data-stu-id="f7abc-117">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="f7abc-118">Konfigurera förfallotid för externa delningslänkar</span><span class="sxs-lookup"><span data-stu-id="f7abc-118">Configure expiration time for external sharing links</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="f7abc-119">Stöd för säkerhetsstandardvärden för Azure AD-förbättringsåtgärder</span><span class="sxs-lookup"><span data-stu-id="f7abc-119">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="f7abc-120">Microsoft Secure Score uppdaterar förbättringsåtgärder för att stödja [säkerhetsstandardvärden i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), vilket gör det enklare att skydda din organisation med förkonfigurerade säkerhetsinställningar för vanliga attacker.</span><span class="sxs-lookup"><span data-stu-id="f7abc-120">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="f7abc-121">Det kommer att påverka följande förbättringsåtgärder:</span><span class="sxs-lookup"><span data-stu-id="f7abc-121">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="f7abc-122">Se till att alla användare kan slutföra multifaktorautentisering för säker åtkomst</span><span class="sxs-lookup"><span data-stu-id="f7abc-122">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="f7abc-123">Kräv MFA för administrativa roller</span><span class="sxs-lookup"><span data-stu-id="f7abc-123">Require MFA for administrative roles</span></span>
- <span data-ttu-id="f7abc-124">Aktivera princip för att blockera äldre autentisering</span><span class="sxs-lookup"><span data-stu-id="f7abc-124">Enable policy to block legacy authentication</span></span>
