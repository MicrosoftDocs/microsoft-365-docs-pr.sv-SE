---
title: Simulera en nätfiskeattack med Microsoft Defender för Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan lära sig hur de kan simulera nätfiskeattacker och träna sina användare mot nätfiskeskydd med hjälp av utbildning för attackbedrägerier i Microsoft Defender för Office 365.
ms.technology: mdo
ms.openlocfilehash: 27279f927a15ea94ae84112ffdc23d88ea42d2ff
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509344"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="49ab5-103">Simulera en nätfiskeattack</span><span class="sxs-lookup"><span data-stu-id="49ab5-103">Simulate a phishing attack</span></span>

<span data-ttu-id="49ab5-104">Med hjälp av simuleringsutbildning för attacker i Microsoft Defender för Office 365 kan du köra simuleringar av cyberattacker på din organisation för att testa säkerhetsprinciper och säkerhetsmetoder, samt utbilda de anställda att öka medvetenheten och minska deras känslighet för attacker.</span><span class="sxs-lookup"><span data-stu-id="49ab5-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="49ab5-105">I den här artikeln får du hjälp med att skapa en simulerad nätfiskeattack med hjälp av utbildning om attackbedrägerier.</span><span class="sxs-lookup"><span data-stu-id="49ab5-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="49ab5-106">Information om att simulera attacker finns i Komma igång med att [använda attackerssimuleringsutbildning.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="49ab5-106">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="49ab5-107">Om du vill starta en simulerad nätfiskeattack öppnar du Säkerhetscenter för [Microsoft 365,](https://security.microsoft.com/)går till E-post&-utbildning för samarbetsattack och växlar till  \>  [**fliken Simuleringar.**](https://security.microsoft.com/attacksimulator?viewid=simulations)</span><span class="sxs-lookup"><span data-stu-id="49ab5-107">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="49ab5-108">Under **Simuleringar** väljer du **+ Starta en simulering.**</span><span class="sxs-lookup"><span data-stu-id="49ab5-108">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Starta en simuleringsknapp i Microsoft 365 säkerhetscenter](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="49ab5-110">När som helst under simuleringen kan du spara och stänga för att fortsätta konfigurera simuleringen vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="49ab5-110">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="49ab5-111">Välja en social engineering-teknik</span><span class="sxs-lookup"><span data-stu-id="49ab5-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="49ab5-112">Välj bland fyra olika tekniker, utvalda från [MITRE ATT&CK® framework.](https://attack.mitre.org/techniques/enterprise/)</span><span class="sxs-lookup"><span data-stu-id="49ab5-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="49ab5-113">Olika nyttolaster är tillgängliga för olika tekniker:</span><span class="sxs-lookup"><span data-stu-id="49ab5-113">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="49ab5-114">**Autentiseringsuppgifter försöker samla** in autentiseringsuppgifter genom att ta användare till en känd webbplats med inmatningsrutor för att skicka ett användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="49ab5-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="49ab5-115">**Bifogade filer från skadlig** programvara lägger till en skadlig bilaga i ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="49ab5-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="49ab5-116">När användaren öppnar den bifogade filen körs godtycklig kod som hjälper attackeraren att kompromettera målets enhet.</span><span class="sxs-lookup"><span data-stu-id="49ab5-116">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="49ab5-117">**Länk i bifogad** fil är en typ av hybrid för autentiseringsuppgifter för att samla information.</span><span class="sxs-lookup"><span data-stu-id="49ab5-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="49ab5-118">En attack infogar en URL i en e-postbilaga.</span><span class="sxs-lookup"><span data-stu-id="49ab5-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="49ab5-119">URL:en i den bifogade filen följer samma teknik som för den autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="49ab5-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="49ab5-120">**Länk till skadlig** programvara kör skadlig kod från en fil som finns på en känd fildelningstjänst.</span><span class="sxs-lookup"><span data-stu-id="49ab5-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="49ab5-121">Meddelandet som skickas till användaren innehåller en länk till filen.</span><span class="sxs-lookup"><span data-stu-id="49ab5-121">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="49ab5-122">Öppna filen och hjälp attackeraren att kompromettera målets enhet.</span><span class="sxs-lookup"><span data-stu-id="49ab5-122">Opening the file and help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="49ab5-123">**Drive-by URL** är den plats där den skadliga URL:en i meddelandet tar användaren till en välbekant webbplats som körs tyst och/eller installerar kodkod på användarens enhet.</span><span class="sxs-lookup"><span data-stu-id="49ab5-123">**Drive-by URL** is where the malicious URL in the message takes the user to a familiar-looking website that silently runs and/or installs code code on the user's device.</span></span>

> [!TIP]
> <span data-ttu-id="49ab5-124">Om du **klickar på** Visa information i beskrivningen av varje teknik visas ytterligare information och simuleringsstegen för tekniken.</span><span class="sxs-lookup"><span data-stu-id="49ab5-124">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Simuleringssteg för att samla in autentiseringsuppgifter i attacksimuleringsutbildning i Microsoft 365 säkerhetscenter](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="49ab5-126">När du har valt metoden och klickat på **Nästa ger du** din simulering ett namn och en beskrivning om du vill.</span><span class="sxs-lookup"><span data-stu-id="49ab5-126">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="49ab5-127">Välja ett nyttolast</span><span class="sxs-lookup"><span data-stu-id="49ab5-127">Selecting a payload</span></span>

<span data-ttu-id="49ab5-128">Därefter måste du antingen välja en nyttolast från den befintliga nyttolastkatalogen.</span><span class="sxs-lookup"><span data-stu-id="49ab5-128">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="49ab5-129">Nyttolaster har ett antal datapunkter som hjälper dig att välja:</span><span class="sxs-lookup"><span data-stu-id="49ab5-129">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="49ab5-130">**Click rate counts** how many people clicked this payload.</span><span class="sxs-lookup"><span data-stu-id="49ab5-130">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="49ab5-131">**Förutsagd** komprometterad ränta förutsäger den procentandel av personer som kommer att bli komprometterad av den här nyttolasten baserat på historiska data för nyttolasten i Microsoft Defender för Office 365-kunder.</span><span class="sxs-lookup"><span data-stu-id="49ab5-131">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="49ab5-132">**Vid beräkningar som startas** räknas antalet gånger som den här nyttolasten har använts i andra simuleringar.</span><span class="sxs-lookup"><span data-stu-id="49ab5-132">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="49ab5-133">**Komplexitet,** som är tillgänglig **via** filter, beräknas baserat på antalet indikatorer i nyttolasten som tyder på att det är en attack.</span><span class="sxs-lookup"><span data-stu-id="49ab5-133">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="49ab5-134">Fler indikatorer leder till lägre komplexitet.</span><span class="sxs-lookup"><span data-stu-id="49ab5-134">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="49ab5-135">**Källa,** som är tillgänglig **via** filter, anger om nyttolasten skapades i klientorganisationen eller är en del av Microsofts befintliga nyttolastkatalog (global).</span><span class="sxs-lookup"><span data-stu-id="49ab5-135">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Vald nyttolast inom attacksimuleringsutbildning i Microsoft 365 säkerhetscenter](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="49ab5-137">Välj en nyttolast i listan om du vill se en förhandsgranskning av nyttolasten med ytterligare information om den.</span><span class="sxs-lookup"><span data-stu-id="49ab5-137">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="49ab5-138">Om du vill skapa en egen nyttolast kan du läsa om att [skapa en nyttolast för att simulera attacker.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="49ab5-138">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="49ab5-139">Målgruppsanpassning</span><span class="sxs-lookup"><span data-stu-id="49ab5-139">Audience targeting</span></span>

<span data-ttu-id="49ab5-140">Nu är det dags att välja den här simuleringens målgrupp.</span><span class="sxs-lookup"><span data-stu-id="49ab5-140">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="49ab5-141">Du kan välja att **ta med alla användare i organisationen eller** att endast inkludera vissa användare och **grupper.**</span><span class="sxs-lookup"><span data-stu-id="49ab5-141">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="49ab5-142">När du väljer att **endast inkludera vissa användare och grupper kan** du antingen:</span><span class="sxs-lookup"><span data-stu-id="49ab5-142">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="49ab5-143">**Lägg till** användare, så att du kan utnyttja sökning för klientorganisationen, samt avancerade sök- och filtreringsfunktioner, till exempel rikta användare som inte har riktats av en simulering under de senaste 3 månaderna.</span><span class="sxs-lookup"><span data-stu-id="49ab5-143">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="49ab5-144">![Användarfiltrering i utbildning om attacksimulering i Microsoft 365 säkerhetscenter](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="49ab5-144">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="49ab5-145">**Med import från CSV** kan du importera en fördefinierad uppsättning användare för den här simuleringen.</span><span class="sxs-lookup"><span data-stu-id="49ab5-145">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="49ab5-146">Tilldela utbildning</span><span class="sxs-lookup"><span data-stu-id="49ab5-146">Assigning training</span></span>

<span data-ttu-id="49ab5-147">Vi rekommenderar att du tilldelar utbildning för varje simulering eftersom anställda som går på utbildningar är mindre känsliga för liknande attacker.</span><span class="sxs-lookup"><span data-stu-id="49ab5-147">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="49ab5-148">Du kan antingen välja att själv tilldela utbildning till dig eller välja själv kurser och moduler.</span><span class="sxs-lookup"><span data-stu-id="49ab5-148">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="49ab5-149">Välj förfallodatum **för utbildningen så** att de anställda slutför sin utbildning i tid.</span><span class="sxs-lookup"><span data-stu-id="49ab5-149">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="49ab5-150">Om du väljer att själv välja kurser och moduler kan du fortfarande se det rekommenderade innehållet samt alla tillgängliga kurser och moduler.</span><span class="sxs-lookup"><span data-stu-id="49ab5-150">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Lägga till rekommenderad utbildning inom attacksimuleringsutbildning i Microsoft 365 säkerhetscenter](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="49ab5-152">I nästa steg måste du lägga till utbildningar **om** du valt att själv välja det och anpassa startsidan för utbildningen.</span><span class="sxs-lookup"><span data-stu-id="49ab5-152">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="49ab5-153">Du kommer att kunna förhandsgranska startsidan för utbildningen samt ändra sidhuvudet och brödtexten.</span><span class="sxs-lookup"><span data-stu-id="49ab5-153">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="49ab5-154">Starta information och granska</span><span class="sxs-lookup"><span data-stu-id="49ab5-154">Launch details and review</span></span>

<span data-ttu-id="49ab5-155">Nu när allt är konfigurerat kan du starta den här simuleringen direkt eller schemalägga den till ett senare datum.</span><span class="sxs-lookup"><span data-stu-id="49ab5-155">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="49ab5-156">Du måste också välja när du vill avsluta den här simuleringen.</span><span class="sxs-lookup"><span data-stu-id="49ab5-156">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="49ab5-157">Vi slutar fånga interaktionen med den här simuleringen efter den valda tiden.</span><span class="sxs-lookup"><span data-stu-id="49ab5-157">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="49ab5-158">**Aktivera regionmedveten tidszonsleverans** för att leverera simulerade attackmeddelanden till dina anställda under deras arbetstider baserat på deras region.</span><span class="sxs-lookup"><span data-stu-id="49ab5-158">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="49ab5-159">När du är klar klickar du på **Nästa och** granskar detaljerna i din simulering.</span><span class="sxs-lookup"><span data-stu-id="49ab5-159">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="49ab5-160">Klicka på **Redigera** på någon av delarna för att gå tillbaka och ändra information som behöver ändras.</span><span class="sxs-lookup"><span data-stu-id="49ab5-160">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="49ab5-161">Klicka på Skicka när du **är klar.**</span><span class="sxs-lookup"><span data-stu-id="49ab5-161">Once done, click **Submit**.</span></span>
