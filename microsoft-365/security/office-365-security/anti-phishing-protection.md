---
title: Skydd mot nätfiske
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om skydd mot nätfiske-funktioner i Exchange Online Protection (EOP) och Office 365 Avancerat skydd (Office 365 ATP).
ms.openlocfilehash: 5607a3bf566fabccf3ae55726aca9eefcff9c062
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202417"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="6dd6c-103">Skydd mot nätfiske i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6dd6c-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6dd6c-104">*Nätfiske* är ett e-postangrepp som försöker stjäla känslig information i meddelanden som verkar vara från legitima eller betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="6dd6c-104">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="6dd6c-105">Det finns särskilda typer av nät fiske.</span><span class="sxs-lookup"><span data-stu-id="6dd6c-105">There are specific categories of phishing.</span></span> <span data-ttu-id="6dd6c-106">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="6dd6c-106">For example:</span></span>

- <span data-ttu-id="6dd6c-107">**Spear nätfiske** använder prioriterat, anpassat innehåll som är specifikt skräddarsydda för de riktade mottagarna (vanligt vis efter Reconnaissance på mottagarnas mottagare).</span><span class="sxs-lookup"><span data-stu-id="6dd6c-107">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="6dd6c-108">**Whaling** riktar sig till chefer eller andra mål inom en organisation för maximal effekt.</span><span class="sxs-lookup"><span data-stu-id="6dd6c-108">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="6dd6c-109">**Företags-e-postkompromisser (BEC)** använder förfalskade betrodda avsändare (finans tjänstemän, kunder, betrodda partners etc.) för att lura mottagarna att godkänna betalningar, överföra penning medel eller Visa kunddata.</span><span class="sxs-lookup"><span data-stu-id="6dd6c-109">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span>

- <span data-ttu-id="6dd6c-110">**Utpressnings tro** vara som krypterar dina data och kräver betalning för att dekryptera det nästan alltid med nät fiske meddelanden.</span><span class="sxs-lookup"><span data-stu-id="6dd6c-110">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="6dd6c-111">Skydd mot nätfiske kan inte hjälpa dig att dekryptera krypterade filer, men det kan hjälpa till att identifiera de inledande nät fiske meddelandena som är kopplade till utpressnings bara kampanjen.</span><span class="sxs-lookup"><span data-stu-id="6dd6c-111">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="6dd6c-112">Mer information om hur du återställer från en utpressnings tro Jan attack finns i [återställa från en utpressnings tro Jan attack i Microsoft 365](recover-from-ransomware.md).</span><span class="sxs-lookup"><span data-stu-id="6dd6c-112">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="6dd6c-113">Det är ännu svårt för utbildade användare att identifiera avancerade nät fiske meddelanden.</span><span class="sxs-lookup"><span data-stu-id="6dd6c-113">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="6dd6c-114">Som tur är kan Exchange Online Protection (EOP) och ytterligare funktioner i Office 365 Avancerat skydd (Office 365 ATP) hjälpa dig.</span><span class="sxs-lookup"><span data-stu-id="6dd6c-114">Fortunately, Exchange Online Protection (EOP) and the additional features in Office 365 Advanced Threat Protection (Office 365 ATP) can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="6dd6c-115">Skydd mot nätfiske i EOP</span><span class="sxs-lookup"><span data-stu-id="6dd6c-115">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="6dd6c-116">EOP (det vill säga Microsoft 365-organisationer utan ATP) innehåller funktioner som kan skydda din organisation från nätfiske-hot:</span><span class="sxs-lookup"><span data-stu-id="6dd6c-116">EOP (that is, Microsoft 365 organizations without ATP) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="6dd6c-117">**Förfalskningsinformation**: granska falska meddelanden från avsändare i interna och externa domäner samt tillåt eller blockera avsändarna.</span><span class="sxs-lookup"><span data-stu-id="6dd6c-117">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="6dd6c-118">Mer information finns i [Konfigurera förfalsknings information i EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="6dd6c-118">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="6dd6c-119">**Anti-nätfiske-principer i EOP**: Aktivera eller inaktivera förfalsknings intelligens, Aktivera oautentiserad avsändare i Outlook på eller av och ange åtgärd för blockerade avsändare (flytta till mappen skräp post eller karantän).</span><span class="sxs-lookup"><span data-stu-id="6dd6c-119">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="6dd6c-120">Mer information finns i [Konfigurera principer för nätfiske i EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="6dd6c-120">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="6dd6c-121">**Implicit e-postauktorisering**: EOP förbättrar standardinställningarna för inkommande e-post ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC](use-dmarc-to-validate-email.md)) med avsändarens rykte, avsändarens historik, mottagar historik, beteende analys och andra avancerade tekniker som hjälper dig att identifiera förfalskade avsändare.</span><span class="sxs-lookup"><span data-stu-id="6dd6c-121">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="6dd6c-122">Mer information finns i [E-postautentisering i Microsoft 365](email-validation-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="6dd6c-122">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a><span data-ttu-id="6dd6c-123">Ytterligare skydd mot nätfiske i Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="6dd6c-123">Additional anti-phishing protection in Office 365 ATP</span></span>

<span data-ttu-id="6dd6c-124">Office 365 ATP innehåller fler och mer avancerade nät fiske funktioner:</span><span class="sxs-lookup"><span data-stu-id="6dd6c-124">Office 365 ATP contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="6dd6c-125">**AntiPhishing-principer för ATP**: skapa nya anpassade principer, konfigurera inställningar för skydd mot obehörig person (skydda användare och domäner från personifiering), inställningar för post låda och justerbara avancerade tröskelvärden för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="6dd6c-125">**ATP anti-phishing policies**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="6dd6c-126">Mer information finns i [Konfigurera AntiPhishing-principer för ATP i Microsoft 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6dd6c-126">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="6dd6c-127">Mer information om skillnaderna mellan anti-nätfiske-principer och Antivirus principer för ATP finns i [principer för nätfiske i Microsoft 365](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6dd6c-127">For more information about the differences between anti-phishing policies and ATP anti-phishing policies, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="6dd6c-128">**Kampanjmallar**: maskin inlärning och andra heuristik identifierar och analyserar meddelanden som ingår i koordinerade nätfiske-attacker mot hela tjänsten och din organisation.</span><span class="sxs-lookup"><span data-stu-id="6dd6c-128">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="6dd6c-129">Mer information finns [i vyn kampanjmallar i Office 365 ATP](campaigns.md).</span><span class="sxs-lookup"><span data-stu-id="6dd6c-129">For more information, see [Campaign Views in Office 365 ATP](campaigns.md).</span></span>

- <span data-ttu-id="6dd6c-130">**Angrepps Simulator**: administratörer kan skapa falska nät fiske meddelanden och skicka dem till interna användare som utbildnings verktyg.</span><span class="sxs-lookup"><span data-stu-id="6dd6c-130">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="6dd6c-131">Mer information finns i [angrepps Simulator i Office 365 ATP](attack-simulator.md).</span><span class="sxs-lookup"><span data-stu-id="6dd6c-131">For more information, see [Attack Simulator in Office 365 ATP](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="6dd6c-132">Andra AntiPhishing-resurser</span><span class="sxs-lookup"><span data-stu-id="6dd6c-132">Other anti-phishing resources</span></span>

- <span data-ttu-id="6dd6c-133">För slutanvändare: [skydda dig från nätfiske och andra former av bedrägerier online](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span><span class="sxs-lookup"><span data-stu-id="6dd6c-133">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="6dd6c-134">[Hur Microsoft 365 verifierar från-adressen för att förhindra nätfiske](how-office-365-validates-the-from-address.md).</span><span class="sxs-lookup"><span data-stu-id="6dd6c-134">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
