---
title: Skydd mot nätfiske i Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
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
description: I den här artikeln introduceras tillgängliga onlineresurser som kan användas för att lära sig mer om och implementera alternativ och strategier mot nätfiske i Microsoft 365.
ms.openlocfilehash: 09d384376b1e44989987c40ef3c7860e4fac6167
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033768"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="d26b7-103">Skydd mot nätfiske i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d26b7-103">Anti-phishing protection in Microsoft 365</span></span>

<span data-ttu-id="d26b7-104">*Nätfiske* en e-postattack som försöker stjäla känslig information i meddelanden som verkar vara från legitima eller betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="d26b7-104">*Phishing* an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="d26b7-105">Det finns specifika kategorier av nätfiske.</span><span class="sxs-lookup"><span data-stu-id="d26b7-105">There are specific categories of phishing.</span></span> <span data-ttu-id="d26b7-106">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="d26b7-106">For example:</span></span>

- <span data-ttu-id="d26b7-107">**Spear phishing** använder mycket fokuserat och anpassat innehåll som är särskilt anpassat till de riktade mottagarna (vanligtvis efter spaning på mottagarna av angriparen).</span><span class="sxs-lookup"><span data-stu-id="d26b7-107">**Spear phishing** uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="d26b7-108">**Valfångst** riktas mot chefer eller andra högt värderade mål inom en organisation för maximal effekt.</span><span class="sxs-lookup"><span data-stu-id="d26b7-108">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="d26b7-109">**Business email compromise (BEC)** använder förfalskade betrodda avsändare (ekonomiansvariga, kunder, betrodda partner, etc.) i ett försök att lura mottagaren att godkänna betalningar, överföra pengar eller avslöja kunddata.</span><span class="sxs-lookup"><span data-stu-id="d26b7-109">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) in an effort to trick the recipient into approving payments, transferring funds, or disclosing customer data.</span></span>

- <span data-ttu-id="d26b7-110">**Ransomware** som krypterar dina data och kräver betalning för att dekryptera det nästan alltid börjar i phishing-meddelanden.</span><span class="sxs-lookup"><span data-stu-id="d26b7-110">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="d26b7-111">Skydd mot nätfiske kan inte hjälpa dig att dekryptera krypterade filer, men det kan hjälpa dig att identifiera de första nätfiskemeddelanden som är associerade med ransomware-kampanjen.</span><span class="sxs-lookup"><span data-stu-id="d26b7-111">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="d26b7-112">Mer information om hur du återställer från en ransomware-attack finns i [Återställ från en ransomware-attack i Microsoft 365](recover-from-ransomware.md).</span><span class="sxs-lookup"><span data-stu-id="d26b7-112">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="d26b7-113">Med den växande komplexiteten i attacker är det till och med svårt för utbildade användare att identifiera sofistikerade nätfiskemeddelanden.</span><span class="sxs-lookup"><span data-stu-id="d26b7-113">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="d26b7-114">Lyckligtvis kan Exchange Online Protection (EOP) och ytterligare funktioner i Microsoft 365 Advanced Threat Protection (ATP) hjälpa till.</span><span class="sxs-lookup"><span data-stu-id="d26b7-114">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft 365 Advanced Threat Protection (ATP) can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="d26b7-115">Skydd mot nätfiske i EOP</span><span class="sxs-lookup"><span data-stu-id="d26b7-115">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="d26b7-116">EOP (det vill säga Microsoft 365-organisationer utan ATP) innehåller funktioner som kan skydda din organisation från nätfiskehot:</span><span class="sxs-lookup"><span data-stu-id="d26b7-116">EOP (that is, Microsoft 365 organizations without ATP) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="d26b7-117">**Förfalskningsinformation**: granska falska meddelanden från avsändare i interna och externa domäner samt tillåt eller blockera avsändarna.</span><span class="sxs-lookup"><span data-stu-id="d26b7-117">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="d26b7-118">Mer information finns i [Konfigurera förfalskningsinformation i Microsoft 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="d26b7-118">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="d26b7-119">**Anti-phishing-principer i EOP:** Aktivera eller inaktivera falska underrättelser, aktivera eller inaktivera oautentiserade avsändande avsändare i Outlook och ange åtgärden för blockerade förfalskade avsändare (flytta till skräppostmapp eller karantän).</span><span class="sxs-lookup"><span data-stu-id="d26b7-119">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="d26b7-120">Mer information finns i [Konfigurera principer för nätfiske i EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="d26b7-120">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="d26b7-121">**Implicit e-postautentisering:** EOP förbättrar standardkontroller av e-postautentisering för inkommande e-post[(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC)](use-dmarc-to-validate-email.md)med avsändarens rykte, avsändarehistorik, mottagarhistorik, beteendeanalys och andra avancerade tekniker för att identifiera förfalskade avsändare.</span><span class="sxs-lookup"><span data-stu-id="d26b7-121">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="d26b7-122">Mer information finns i [E-postautentisering i Microsoft 365](email-validation-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d26b7-122">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a><span data-ttu-id="d26b7-123">Ytterligare skydd mot nätfiske i Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="d26b7-123">Additional anti-phishing protection in Office 365 ATP</span></span>

<span data-ttu-id="d26b7-124">Office 365 ATP innehåller ytterligare och mer avancerade funktioner mot nätfiske:</span><span class="sxs-lookup"><span data-stu-id="d26b7-124">Office 365 ATP contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="d26b7-125">**ATP:s principer för phishing:** Skapa nya anpassade principer, konfigurera inställningar för anti-personifiering (skydda användare och domäner från personifiering), inställningar för postlådans intelligens och justerbara avancerade tröskelvärden för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="d26b7-125">**ATP anti-phishing policies**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="d26b7-126">Mer information finns [i Konfigurera ATP-principer för nätfiske i Microsoft 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d26b7-126">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="d26b7-127">Mer information om skillnaderna mellan anti-phishing-policyer och ATP-principer för nätfiske finns [i policyer för nätfiske mot nätfiske i Microsoft 365](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d26b7-127">For more information about the differences between anti-phishing policies and ATP anti-phishing policies, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="d26b7-128">**Kampanjvyer**: Maskininlärning och andra heuristik identifierar och analyserar meddelanden som är involverade i samordnade nätfiskeattacker mot hela tjänsten och din organisation.</span><span class="sxs-lookup"><span data-stu-id="d26b7-128">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="d26b7-129">Mer information finns [i Kampanjvyer i Office 365 ATP](campaigns.md).</span><span class="sxs-lookup"><span data-stu-id="d26b7-129">For more information, see [Campaign Views in Office 365 ATP](campaigns.md).</span></span>

- <span data-ttu-id="d26b7-130">**Attack simulator:** Administratörer kan skapa falska nätfiskemeddelanden och skicka dem till interna användare som ett utbildningsverktyg.</span><span class="sxs-lookup"><span data-stu-id="d26b7-130">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="d26b7-131">Mer information finns [i Attack Simulator i Office 365 ATP](attack-simulator.md).</span><span class="sxs-lookup"><span data-stu-id="d26b7-131">For more information, see [Attack Simulator in Office 365 ATP](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="d26b7-132">Andra anti-phishing-resurser</span><span class="sxs-lookup"><span data-stu-id="d26b7-132">Other anti-phishing resources</span></span>

- <span data-ttu-id="d26b7-133">För slutanvändare: [Skydda dig mot nätfiske och andra former av onlinebedrägerier](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546).</span><span class="sxs-lookup"><span data-stu-id="d26b7-133">For end-users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546).</span></span>

- <span data-ttu-id="d26b7-134">[Så här validerar Microsoft 365 Från-adressen för att förhindra nätfiske](how-office-365-validates-the-from-address.md).</span><span class="sxs-lookup"><span data-stu-id="d26b7-134">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>