---
title: Kom igång med Attack simuleringsträning
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig att använda angrepps simulerings utbildning för att köra simulerade nätfiske och lösen ords attacker i sina Microsoft 365 E5-eller Microsoft Defender för Office 365 plan 2-organisationer.
ms.openlocfilehash: 2c00fb27748887c6b8e2fa1458b10f0c3405eef7
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877170"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="bbda7-103">Kom igång med Attack simuleringsträning</span><span class="sxs-lookup"><span data-stu-id="bbda7-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bbda7-104">Om din organisation har Microsoft 365 E5 eller Microsoft Defender för Office 365 abonnemang 2, som innehåller [hot undersöknings-och svars funktioner](office-365-ti.md), kan du använda funktionen för simulering av attacker i Microsoft säkerhets Center för att köra realistiska angrepp i din organisation.</span><span class="sxs-lookup"><span data-stu-id="bbda7-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="bbda7-105">Dessa simulerade attacker kan hjälpa dig att identifiera och hitta sårbara användare innan en verklig attack påverkar din botten linje.</span><span class="sxs-lookup"><span data-stu-id="bbda7-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="bbda7-106">Läs den här artikeln om du vill veta mer.</span><span class="sxs-lookup"><span data-stu-id="bbda7-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="bbda7-107">Utbildning för utskrivning av attacker ersätter den gamla attack Simulator v1-upplevelsen som beskrivs i [angrepps simulatorn i Microsoft Defender för Office 365](attack-simulator.md).</span><span class="sxs-lookup"><span data-stu-id="bbda7-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bbda7-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="bbda7-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bbda7-109">Öppna säkerhets Center genom att gå till <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="bbda7-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="bbda7-110">Utbildning för att simulering av attacker är tillgängligt på utbildning om **e-post och samarbete** \> .</span><span class="sxs-lookup"><span data-stu-id="bbda7-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="bbda7-111">Gå direkt till utbildning för angrepps simulering genom att öppna <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="bbda7-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="bbda7-112">Mer information om hur du får till gång till utbildning för utskrivning i olika Microsoft 365-abonnemang finns i [Beskrivning av Microsoft Defender för Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="bbda7-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="bbda7-113">Du måste tilldelas behörigheter i säkerhets & efterföljandekrav eller i Azure Active Directory innan du kan göra det i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="bbda7-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="bbda7-114">Specifikt måste du vara medlem i **organisations hantering**, **säkerhets administratör** eller någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="bbda7-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="bbda7-115">**Administratörer för angrepps Simulator**: skapa och hantera alla aspekter av kampanjer för utsättning av attacker.</span><span class="sxs-lookup"><span data-stu-id="bbda7-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="bbda7-116">**Nytto lastare för angrepps Simulator**: skapa nytto laster som en administratör kan initiera senare.</span><span class="sxs-lookup"><span data-stu-id="bbda7-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="bbda7-117">Mer information finns i [behörigheter i avsnittet säkerhets & efterlevnad](permissions-in-the-security-and-compliance-center.md) eller [om administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="bbda7-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="bbda7-118">Det finns inga motsvarande PowerShell-cmdlets för utbildning för att simulera attacker.</span><span class="sxs-lookup"><span data-stu-id="bbda7-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="bbda7-119">Information om attack simulering och utbildning relaterade data lagras med andra kunddata för Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="bbda7-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="bbda7-120">Mer information finns i [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span><span class="sxs-lookup"><span data-stu-id="bbda7-120">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="bbda7-121">Simulering av attacker är för närvarande inte tillgängligt i följande regioner: SGP, Förenade Arabemiraten, ZAF, ty, BRA och CHE.</span><span class="sxs-lookup"><span data-stu-id="bbda7-121">Attack simulation is currently not available in the following regions: SGP, NOR, UAE, ZAF, GER, BRA, and CHE.</span></span>

## <a name="simulations"></a><span data-ttu-id="bbda7-122">Simuleringar</span><span class="sxs-lookup"><span data-stu-id="bbda7-122">Simulations</span></span>

<span data-ttu-id="bbda7-123">*Nätfiske* är en generisk term för e-postattacker som försöker stjäla känslig information i meddelanden som verkar vara från legitima eller betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="bbda7-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="bbda7-124">*Nätfiske* är en del av en delmängd teknik som vi klassificerar som _social teknik_.</span><span class="sxs-lookup"><span data-stu-id="bbda7-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="bbda7-125">I utbildning för att simulera attacker är flera typer av social teknik teknik tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="bbda7-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="bbda7-126">**Skörd för autentiseringsuppgifter**: en angripare skickar mottagaren ett meddelande som innehåller en URL.</span><span class="sxs-lookup"><span data-stu-id="bbda7-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="bbda7-127">När mottagaren klickar på URL-adressen tas de till en webbplats som normalt visar en dialog ruta där användaren uppmanas att uppge användar namn och lösen ord.</span><span class="sxs-lookup"><span data-stu-id="bbda7-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="bbda7-128">Vanligt vis är målsidan ett tema som representerar en välkänd webbplats för att bygga förtroende för användaren.</span><span class="sxs-lookup"><span data-stu-id="bbda7-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="bbda7-129">**Bifogad fil med skadlig kod**: en angripare skickar mottagaren ett meddelande som innehåller en bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="bbda7-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="bbda7-130">När mottagaren öppnar den bifogade filen körs valfri kod (till exempel ett makro) på användarens enhet så att angriparen kan installera ytterligare kod eller entrench sig själva.</span><span class="sxs-lookup"><span data-stu-id="bbda7-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="bbda7-131">**Länk i bilaga**: det här är en hybrid av en skörd för uppgifter.</span><span class="sxs-lookup"><span data-stu-id="bbda7-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="bbda7-132">En angripare skickar mottagaren ett meddelande som innehåller en URL-adress i en bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="bbda7-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="bbda7-133">När mottagaren öppnar den bifogade filen och klickar på URL-adressen, tas de till en webbplats som visar en dialog ruta där användaren uppmanas att uppge användar namn och lösen ord.</span><span class="sxs-lookup"><span data-stu-id="bbda7-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="bbda7-134">Vanligt vis är målsidan ett tema som representerar en välkänd webbplats för att bygga förtroende för användaren.</span><span class="sxs-lookup"><span data-stu-id="bbda7-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="bbda7-135">**Länk till skadlig program vara**: angriparen skickar ett meddelande till mottagaren med en länk till en bifogad fil på en välkänd fildelnings webbplats (till exempel SharePoint Online eller Dropbox).</span><span class="sxs-lookup"><span data-stu-id="bbda7-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="bbda7-136">När mottagaren klickar på URL-adressen öppnas den bifogade filen och valfri kod (till exempel ett makro) körs på användarens enhet så att angriparen kan installera ytterligare kod eller entrench sig själva.</span><span class="sxs-lookup"><span data-stu-id="bbda7-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="bbda7-137">**Drive-by-URL**: en angripare skickar ett meddelande med en URL till mottagaren.</span><span class="sxs-lookup"><span data-stu-id="bbda7-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="bbda7-138">När mottagaren klickar på URL-adressen tas de till en webbplats där bakgrunds koden körs.</span><span class="sxs-lookup"><span data-stu-id="bbda7-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="bbda7-139">Den här bakgrunds koden försöker samla in information om mottagaren eller distribuera valfri kod på sina enheter.</span><span class="sxs-lookup"><span data-stu-id="bbda7-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="bbda7-140">Vanligt vis är mål webbplatsen en välkänd webbplats som har komprometterats eller en klon av en välkänd webbplats.</span><span class="sxs-lookup"><span data-stu-id="bbda7-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="bbda7-141">Bekant med webbplatsen gör det möjligt för användaren att klicka på länken.</span><span class="sxs-lookup"><span data-stu-id="bbda7-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="bbda7-142">Den här tekniken kallas också ett hål för att _attackera_ ett problem.</span><span class="sxs-lookup"><span data-stu-id="bbda7-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="bbda7-143">Kontrol lera tillgängligheten för den simulerade nät fiske URL-adressen i webbläsare som stöds innan du använder URL-adressen i en nätfiske-kampanj.</span><span class="sxs-lookup"><span data-stu-id="bbda7-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="bbda7-144">Medan vi arbetar med många URL-ryktes leverantörer för att alltid tillåta dessa simulerings-URL: er har vi inte alltid full täckning (till exempel Google Safe Internet).</span><span class="sxs-lookup"><span data-stu-id="bbda7-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="bbda7-145">De flesta leverantörer tillhandahåller vägledning som gör att du alltid kan tillåta specifika webb adresser (till exempel <https://support.google.com/chrome/a/answer/7532419> ).</span><span class="sxs-lookup"><span data-stu-id="bbda7-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="bbda7-146">URL-adresserna som används för utbildning av angrepps simulering beskrivs i följande lista:</span><span class="sxs-lookup"><span data-stu-id="bbda7-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="bbda7-147">Skapa en simulering</span><span class="sxs-lookup"><span data-stu-id="bbda7-147">Create a simulation</span></span>

<span data-ttu-id="bbda7-148">Steg för steg-instruktioner om hur du skapar och skickar en ny simulering finns i [simulera en nätfiske-attack](attack-simulation-training.md).</span><span class="sxs-lookup"><span data-stu-id="bbda7-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="bbda7-149">Skapa en nytto Last</span><span class="sxs-lookup"><span data-stu-id="bbda7-149">Create a payload</span></span>

<span data-ttu-id="bbda7-150">Mer information om hur du skapar en nytto last för användning i en simulering finns i [skapa en anpassad nytto last för utbildning för attack simulering](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="bbda7-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="bbda7-151">Få insikter</span><span class="sxs-lookup"><span data-stu-id="bbda7-151">Gaining insights</span></span>

<span data-ttu-id="bbda7-152">Steg för steg-instruktioner om hur du får insikter med rapportering finns i [få insikter genom att öva på att simulera attacker](attack-simulation-training-insights.md).</span><span class="sxs-lookup"><span data-stu-id="bbda7-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>