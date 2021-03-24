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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Administratörer kan läsa mer om funktionerna för skydd mot nätfiske i Exchange Online Protection (EOP) och Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0ca7a83e8e8d66bd58fddfc46f53df32f4f623c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073602"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="c2eac-103">Skydd mot nätfiske i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c2eac-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c2eac-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="c2eac-104">**Applies to**</span></span>
- [<span data-ttu-id="c2eac-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c2eac-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c2eac-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="c2eac-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c2eac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2eac-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c2eac-108">*Nätfiske* är en e-postattack som försöker stjäla känslig information i meddelanden som verkar vara från legitima eller betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="c2eac-108">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="c2eac-109">Det finns särskilda kategorier av nätfiske.</span><span class="sxs-lookup"><span data-stu-id="c2eac-109">There are specific categories of phishing.</span></span> <span data-ttu-id="c2eac-110">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="c2eac-110">For example:</span></span>

- <span data-ttu-id="c2eac-111">**Nätfiske** används med fokuserat, anpassat innehåll som är specifikt anpassat efter de riktade mottagarna (vanligtvis efter efterkontroll på mottagarna av attackeret).</span><span class="sxs-lookup"><span data-stu-id="c2eac-111">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="c2eac-112">**Whaling** riktar sig till chefer eller andra högvärdesmålen i en organisation för maximal effekt.</span><span class="sxs-lookup"><span data-stu-id="c2eac-112">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="c2eac-113">**BEC (Business Email Compromise)** använder förfalskade betrodda avsändare (finansansvariga, kunder, betrodda partner osv.) för att lura mottagare att godkänna betalningar, överföra pengar eller visa kunddata.</span><span class="sxs-lookup"><span data-stu-id="c2eac-113">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span>

- <span data-ttu-id="c2eac-114">**Utpressningstrojaner** som krypterar dina data och kräver betalning för att dekryptera dem börjar nästan alltid med nätfiskemeddelanden.</span><span class="sxs-lookup"><span data-stu-id="c2eac-114">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="c2eac-115">Skydd mot nätfiske kan inte hjälpa dig att dekryptera krypterade filer, men det kan hjälpa dig att identifiera de första nätfiskemeddelanden som är kopplade till utpressningstrojankampanjen.</span><span class="sxs-lookup"><span data-stu-id="c2eac-115">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="c2eac-116">Mer information om hur du återställer från en utpressningstrojanattack finns i [Återskapa från en utpressningstrojanattack i Microsoft 365.](recover-from-ransomware.md)</span><span class="sxs-lookup"><span data-stu-id="c2eac-116">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="c2eac-117">Med den växande komplexiteten på attacker är det ännu svårt för användare med utbildning att identifiera avancerade nätfiskemeddelanden.</span><span class="sxs-lookup"><span data-stu-id="c2eac-117">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="c2eac-118">Som tur är kan Exchange Online Protection (EOP) och de extra funktionerna i Microsoft Defender för Office 365 vara till hjälp.</span><span class="sxs-lookup"><span data-stu-id="c2eac-118">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="c2eac-119">Skydd mot nätfiske i EOP</span><span class="sxs-lookup"><span data-stu-id="c2eac-119">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="c2eac-120">EOP (d.v.s. Microsoft 365-organisationer utan Microsoft Defender för Office 365) innehåller funktioner som kan skydda organisationen mot nätfiskehot:</span><span class="sxs-lookup"><span data-stu-id="c2eac-120">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="c2eac-121">**Förfalskningsinformation**: granska falska meddelanden från avsändare i interna och externa domäner samt tillåt eller blockera avsändarna.</span><span class="sxs-lookup"><span data-stu-id="c2eac-121">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="c2eac-122">Mer information finns i [Konfigurera förfalskningsinformation i EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="c2eac-122">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="c2eac-123">Principer för skydd mot nätfiske i **EOP:** Aktivera eller inaktivera förfalskningsinformation, aktivera eller inaktivera oauthanterad avsändaridentifiering i Outlook och ange åtgärden för blockerade förfalskningsavsändare (flytta till mappen Skräppost eller karantän).</span><span class="sxs-lookup"><span data-stu-id="c2eac-123">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="c2eac-124">Mer information finns i Konfigurera [principer för skydd mot nätfiske i EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="c2eac-124">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="c2eac-125">**Implicit** e-postautentisering: EOP förbättrar vanliga e-postautentiseringskontroller för inkommande e-post [(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC)](use-dmarc-to-validate-email.md)med avsändarens rykte, avsändarhistorik, mottagarhistorik, beteendeanalys och andra avancerade tekniker som hjälper till att identifiera förfalskade avsändare.</span><span class="sxs-lookup"><span data-stu-id="c2eac-125">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="c2eac-126">Mer information finns i [E-postautentisering i Microsoft 365](email-validation-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="c2eac-126">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c2eac-127">Ytterligare skydd mot nätfiske i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="c2eac-127">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c2eac-128">Microsoft Defender för Office 365 innehåller ytterligare och mer avancerade funktioner mot nätfiske:</span><span class="sxs-lookup"><span data-stu-id="c2eac-128">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="c2eac-129">Principer för skydd mot nätfiske i Microsoft Defender för **Office 365:** Skapa nya anpassade principer, konfigurera inställningar för skydd mot personifiering (skydda användare och domäner från personifiering), postlådeintelligensinställningar och justerbara avancerade tröskelvärden för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="c2eac-129">**Anti-phishing policies in Microsoft Defender for Office 365**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="c2eac-130">Mer information finns i Konfigurera [principer för skydd mot nätfiske i Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c2eac-130">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="c2eac-131">Mer information om skillnaderna mellan principer för skydd mot nätfiske i EOP och principer för skydd mot nätfiske i Defender för Office 365 finns i Principer för skydd mot nätfiske i [Microsoft 365.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c2eac-131">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="c2eac-132">**Kampanjvyer:** Maskininlärning och annan heuristik identifierar och analyserar meddelanden som är inblandade i koordinerade nätfiskeattacker mot hela tjänsten och organisationen.</span><span class="sxs-lookup"><span data-stu-id="c2eac-132">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="c2eac-133">Mer information finns i [Kampanjvyer i Microsoft Defender för Office 365.](campaigns.md)</span><span class="sxs-lookup"><span data-stu-id="c2eac-133">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="c2eac-134">**Attackattack**: Administratörer kan skapa falska nätfiskemeddelanden och skicka dem till interna användare som ett utbildningsverktyg.</span><span class="sxs-lookup"><span data-stu-id="c2eac-134">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="c2eac-135">Mer information finns i [Attack Attack i Microsoft Defender för Office 365.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="c2eac-135">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="c2eac-136">Andra resurser mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="c2eac-136">Other anti-phishing resources</span></span>

- <span data-ttu-id="c2eac-137">För slutanvändare: Skydda [dig mot nätfiskeförsök och andra former av onlinebedrägerier.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)</span><span class="sxs-lookup"><span data-stu-id="c2eac-137">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="c2eac-138">[Hur Microsoft 365 verifierar Från-adressen för att förhindra nätfiske](how-office-365-validates-the-from-address.md).</span><span class="sxs-lookup"><span data-stu-id="c2eac-138">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
