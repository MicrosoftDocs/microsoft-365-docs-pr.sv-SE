---
title: Kom igång med Attack simuleringsträning
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig hur de använder utbildning av attack simulering för att köra simulerad nätfiske- och lösenordsattacker i sina Microsoft 365 E5 eller Microsoft Defender för Office 365 abonnemang 2 organisationer.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e344153ef433bc13b16136e584ec4da73fcef6a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207055"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="73395-103">Kom igång med Attack simuleringsträning</span><span class="sxs-lookup"><span data-stu-id="73395-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="73395-104">Om din organisation har Microsoft 365 E5 eller Microsoft Defender för Office 365 abonnemang 2, som omfattar funktioner för undersökning av hot och [svar,](office-365-ti.md)kan du använda utbildning av attack simulering i Microsoft Säkerhetscenter för att köra realistiska attackscenarier i din organisation.</span><span class="sxs-lookup"><span data-stu-id="73395-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="73395-105">Dessa simulerade attacker kan hjälpa dig att identifiera och hitta sårbara användare innan en verklig attack påverkar din nedersta linje.</span><span class="sxs-lookup"><span data-stu-id="73395-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="73395-106">Läs den här artikeln om du vill veta mer.</span><span class="sxs-lookup"><span data-stu-id="73395-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="73395-107">Utbildning av attack simulering ersätter den gamla attackteknik v1-upplevelsen som beskrivs i Attack Defender i [Microsoft Defender för Office 365.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="73395-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="73395-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="73395-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="73395-109">Öppna Microsoft Säkerhetscenter genom att gå till <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="73395-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="73395-110">Utbildning av attack simulering är tillgänglig på **E-post och** \> **samarbete Attack simulering utbildning**.</span><span class="sxs-lookup"><span data-stu-id="73395-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="73395-111">Om du vill gå direkt till simuleringsutbildningen för attack öppnar du <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="73395-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="73395-112">Mer information om tillgängligheten för simulering av attack i olika Microsoft 365-prenumerationer finns i Tjänstbeskrivning för Microsoft Defender för [Office 365.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="73395-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="73395-113">Du måste ha tilldelats behörigheter i säkerhets- & säkerhets- och efterlevnadscentret eller i Azure Active Directory innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="73395-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="73395-114">Du måste vara medlem i Organisationshantering, **Säkerhetsadministratör** eller någon av följande roller: </span><span class="sxs-lookup"><span data-stu-id="73395-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="73395-115">**Attack attackadministratörer:** Skapa och hantera alla aspekter av attack simuleringskampanjer.</span><span class="sxs-lookup"><span data-stu-id="73395-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="73395-116">**Författare av attack av nyttolast**: Skapa attack payloads som en administratör kan initiera senare.</span><span class="sxs-lookup"><span data-stu-id="73395-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="73395-117">Mer information finns i [Behörigheter i Säkerhets- & Kompatibilitetscenter](permissions-in-the-security-and-compliance-center.md) eller [Om administratörsroller.](../../admin/add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="73395-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="73395-118">Det finns inga Motsvarande PowerShell-cmdlets för simulering av attackattacker.</span><span class="sxs-lookup"><span data-stu-id="73395-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="73395-119">Attack simulering och utbildning relaterade data lagras med andra kunddata för Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="73395-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="73395-120">Mer information finns i [Microsoft 365-dataplatser.](../../enterprise/o365-data-locations.md)</span><span class="sxs-lookup"><span data-stu-id="73395-120">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="73395-121">Attack simulering är tillgänglig i följande regioner: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN och KOR.</span><span class="sxs-lookup"><span data-stu-id="73395-121">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

## <a name="simulations"></a><span data-ttu-id="73395-122">Simuleringar</span><span class="sxs-lookup"><span data-stu-id="73395-122">Simulations</span></span>

<span data-ttu-id="73395-123">*Nätfiske* är en allmän term för e-postattacker som försöker stjäla känslig information i meddelanden som verkar vara från legitima eller betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="73395-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="73395-124">*Nätfiske* är en del av en del av en uppsättning tekniker som vi klassificerar som _social engineering_.</span><span class="sxs-lookup"><span data-stu-id="73395-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="73395-125">I utbildning av attack simulering finns det flera typer av social engineering-tekniker:</span><span class="sxs-lookup"><span data-stu-id="73395-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="73395-126">**Credential credential harvest**: An attacker sends the recipient a message that contains a URL.</span><span class="sxs-lookup"><span data-stu-id="73395-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="73395-127">När mottagaren klickar på URL-adressen kommer de till en webbplats som vanligtvis visar en dialogruta där användaren uppmanas att ange sitt användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="73395-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="73395-128">Målsidan brukar motsvara en känd webbplats för att skapa förtroende för användaren.</span><span class="sxs-lookup"><span data-stu-id="73395-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="73395-129">**Bifogad fil från** skadlig programvara: En attackerare skickar ett meddelande till mottagaren som innehåller en bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="73395-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="73395-130">När mottagaren öppnar den bifogade filen körs godtycklig kod (till exempel ett makro) på användarens enhet för att hjälpa attackerare att installera ytterligare kod eller ytterligare entrencha sig själva.</span><span class="sxs-lookup"><span data-stu-id="73395-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="73395-131">**Länk i bifogad** fil: Det här är en hybrid av en credential-skörd.</span><span class="sxs-lookup"><span data-stu-id="73395-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="73395-132">En attackerare skickar ett meddelande till mottagaren som innehåller en URL-adress i en bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="73395-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="73395-133">När mottagaren öppnar den bifogade filen och klickar på URL-adressen kommer de till en webbplats som vanligtvis visar en dialogruta där användaren ombeds ange sitt användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="73395-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="73395-134">Målsidan brukar motsvara en känd webbplats för att skapa förtroende för användaren.</span><span class="sxs-lookup"><span data-stu-id="73395-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="73395-135">**Länk till skadlig** programvara: En attackerare skickar ett meddelande till mottagaren som innehåller en länk till en bifogad fil på en känd webbplats för fildelning (till exempel SharePoint Online eller Dropbox).</span><span class="sxs-lookup"><span data-stu-id="73395-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="73395-136">När mottagaren klickar på URL-adressen öppnas den bifogade filen och godtycklig kod (till exempel ett makro) körs på användarens enhet för att hjälpa attackeret att installera ytterligare kod eller ytterligare entrencha sig själva.</span><span class="sxs-lookup"><span data-stu-id="73395-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="73395-137">**Drive-by-url**: En attack skickar ett meddelande till mottagaren som innehåller en URL.</span><span class="sxs-lookup"><span data-stu-id="73395-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="73395-138">När mottagaren klickar på URL-adressen tas den till en webbplats som försöker köra bakgrundskod.</span><span class="sxs-lookup"><span data-stu-id="73395-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="73395-139">Den här bakgrundskoden försöker samla in information om mottagaren eller distribuera godtycklig kod på enheten.</span><span class="sxs-lookup"><span data-stu-id="73395-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="73395-140">Vanligtvis är målwebbplatsen en känd webbplats som har komprometterats eller en klona av en känd webbplats.</span><span class="sxs-lookup"><span data-stu-id="73395-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="73395-141">Webbplatsens bekanta med webbplatsen övertygar användaren om att länken är säker att klicka på.</span><span class="sxs-lookup"><span data-stu-id="73395-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="73395-142">Den här tekniken kallas även för en _watering hole-attack_.</span><span class="sxs-lookup"><span data-stu-id="73395-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="73395-143">Kontrollera om den simulerade nätfiske-URL:en är tillgänglig i dina webbläsare som stöds innan du använder URL:en i en nätfiskekampanj.</span><span class="sxs-lookup"><span data-stu-id="73395-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="73395-144">Medan vi arbetar med många URL-ryktesleverantörer för att alltid tillåta dessa simulerings-URL:er, har vi inte alltid fullständig täckning (till exempel Google Säker surfning).</span><span class="sxs-lookup"><span data-stu-id="73395-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="73395-145">De flesta leverantörer ger vägledning som gör att du alltid kan tillåta specifika URL:er (till <https://support.google.com/chrome/a/answer/7532419> exempel).</span><span class="sxs-lookup"><span data-stu-id="73395-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="73395-146">Url:erna som används av simuleringsutbildning för attack beskrivs i följande lista:</span><span class="sxs-lookup"><span data-stu-id="73395-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a><span data-ttu-id="73395-147">Skapa en simulering</span><span class="sxs-lookup"><span data-stu-id="73395-147">Create a simulation</span></span>

<span data-ttu-id="73395-148">Stegvisa instruktioner om hur du skapar och skickar en ny simulering finns i [Simulera en nätfiskeattack](attack-simulation-training.md).</span><span class="sxs-lookup"><span data-stu-id="73395-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="73395-149">Skapa en nyttolast</span><span class="sxs-lookup"><span data-stu-id="73395-149">Create a payload</span></span>

<span data-ttu-id="73395-150">Stegvisa instruktioner för hur du skapar en nyttolast för användning i en simulering finns i Skapa en anpassad [nyttolast för utbildning av attackattacker.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="73395-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="73395-151">Få insikter</span><span class="sxs-lookup"><span data-stu-id="73395-151">Gaining insights</span></span>

<span data-ttu-id="73395-152">Stegvisa instruktioner om hur du får insikter med rapporter finns i Få insikter [genom utbildning av attack simulering](attack-simulation-training-insights.md).</span><span class="sxs-lookup"><span data-stu-id="73395-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="73395-153">Attack Attack Attack använder Säkra länkar i Defender för Office 365 för att säkert spåra klickdata för URL-adressen i nyttolastmeddelandet som skickas till riktade mottagare av en nätfiskekampanj, även om inställningen Spåra inte **användarens** klickningar i principer för säkra länkar är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="73395-153">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>