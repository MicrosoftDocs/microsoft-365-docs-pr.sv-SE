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
description: Administratörer kan lära sig hur de kan simulera nätfiskeattacker och träna sina användare på nätfiskeskydd med hjälp av utbildning om attackbedrägerier i Microsoft Defender för Office 365.
ms.technology: mdo
ms.openlocfilehash: d82e7544e6795e4514cf1949645107c53fc69c61
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878370"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="d26df-103">Simulera en nätfiskeattack</span><span class="sxs-lookup"><span data-stu-id="d26df-103">Simulate a phishing attack</span></span>

<span data-ttu-id="d26df-104">**Gäller för** [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="d26df-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="d26df-105">Med utbildning av attack simulering i Microsoft Defender för Office 365 kan du köra simuleringar av cyberattacker på din organisation för att testa säkerhetsprinciper och metoder, samt utbilda dina anställda att öka deras medvetenhet och minska deras känslighet för attacker.</span><span class="sxs-lookup"><span data-stu-id="d26df-105">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="d26df-106">Den här artikeln beskriver hur du skapar en simulerad nätfiskeattack med hjälp av utbildning om attackbedrägerier.</span><span class="sxs-lookup"><span data-stu-id="d26df-106">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="d26df-107">Information om attack simuleringsutbildning för att komma igång finns i [Komma igång med simulering av attack .](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="d26df-107">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="d26df-108">Om du vill starta en simulerad nätfiskeattack öppnar du Microsoft 365 Defender-portalen ( ), går till E-&-utbildning för samarbete attackattack och växlar till <https://security.microsoft.com/>  \>  **[fliken Simuleringar.](https://security.microsoft.com/attacksimulator?viewid=simulations)**</span><span class="sxs-lookup"><span data-stu-id="d26df-108">To launch a simulated phishing attack, open the Microsoft 365 Defender portal (<https://security.microsoft.com/>), go to **Email & collaboration** \> **Attack simulation training**, and switch to the **[Simulations](https://security.microsoft.com/attacksimulator?viewid=simulations)** tab.</span></span>

<span data-ttu-id="d26df-109">Under **Simuleringar** väljer du **+ Starta en simulering**.</span><span class="sxs-lookup"><span data-stu-id="d26df-109">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Starta en simuleringsknapp i Microsoft 365 Defender-portalen](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="d26df-111">När som helst under simuleringen kan du spara och stänga för att fortsätta konfigurera simuleringen vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="d26df-111">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="d26df-112">Välja en social engineering teknik</span><span class="sxs-lookup"><span data-stu-id="d26df-112">Selecting a social engineering technique</span></span>

<span data-ttu-id="d26df-113">Välj bland fyra olika tekniker som används i [MITRE ATT&CK® framework.](https://attack.mitre.org/techniques/enterprise/)</span><span class="sxs-lookup"><span data-stu-id="d26df-113">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="d26df-114">Olika nyttolaster är tillgängliga för olika tekniker:</span><span class="sxs-lookup"><span data-stu-id="d26df-114">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="d26df-115">**Autentiseringsuppgifter försöker samla** in autentiseringsuppgifter genom att ta användare till en känd webbplats med inmatningsrutor för att skicka ett användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="d26df-115">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="d26df-116">**Bifogade filer från skadlig** programvara lägger till en skadlig bilaga i ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="d26df-116">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="d26df-117">När användaren öppnar den bifogade filen körs godtycklig kod som hjälper attackeraren att kompromettera målets enhet.</span><span class="sxs-lookup"><span data-stu-id="d26df-117">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="d26df-118">**Länk i bifogad** fil är en typ av hybrid för autentiseringsuppgifter för hybrid av autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d26df-118">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="d26df-119">En attack infogar en URL i en e-postbilaga.</span><span class="sxs-lookup"><span data-stu-id="d26df-119">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="d26df-120">URL:en i den bifogade filen följer samma teknik som autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d26df-120">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="d26df-121">**Länk till skadlig** programvara kör skadlig kod från en fil som finns på en känd fildelningstjänst.</span><span class="sxs-lookup"><span data-stu-id="d26df-121">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="d26df-122">Meddelandet som skickas till användaren innehåller en länk till den här skadliga filen.</span><span class="sxs-lookup"><span data-stu-id="d26df-122">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="d26df-123">Öppna filen och hjälpa attackerare att kompromettera målets enhet.</span><span class="sxs-lookup"><span data-stu-id="d26df-123">Opening the file and help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="d26df-124">**Drive-by URL** är den plats där den skadliga URL-adressen i meddelandet tar användaren till en välbekant webbplats som tyst kör och/eller installerar kodkod på användarens enhet.</span><span class="sxs-lookup"><span data-stu-id="d26df-124">**Drive-by URL** is where the malicious URL in the message takes the user to a familiar-looking website that silently runs and/or installs code code on the user's device.</span></span>

> [!TIP]
> <span data-ttu-id="d26df-125">Om du **klickar på** Visa information i beskrivningen av varje teknik visas ytterligare information och simuleringsstegen för tekniken.</span><span class="sxs-lookup"><span data-stu-id="d26df-125">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Simuleringssteg för credential-skörd i attack simuleringsutbildning i Microsoft 365 Defender-portalen](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="d26df-127">När du har valt tekniken och klickat på Nästa **ger** du simuleringen ett namn och en beskrivning om du vill.</span><span class="sxs-lookup"><span data-stu-id="d26df-127">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="d26df-128">Välja en nyttolast</span><span class="sxs-lookup"><span data-stu-id="d26df-128">Selecting a payload</span></span>

<span data-ttu-id="d26df-129">Därefter måste du antingen välja en nyttolast från den befintliga nyttokatalogen.</span><span class="sxs-lookup"><span data-stu-id="d26df-129">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="d26df-130">Nyttolaster har ett antal datapunkter som du kan använda för att välja:</span><span class="sxs-lookup"><span data-stu-id="d26df-130">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="d26df-131">**Click rate counts** how many people clicked this payload.</span><span class="sxs-lookup"><span data-stu-id="d26df-131">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="d26df-132">**Förutsagd komprometterad** ränta förutsäger den procentandel av personer som kommer att bli komprometterad av den här nyttolasten baserat på historiska data för nyttolasten i Microsoft Defender för Office 365 kunder.</span><span class="sxs-lookup"><span data-stu-id="d26df-132">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="d26df-133">**Simuleringar som startas** räknar antalet gånger den här nyttolasten användes i andra simuleringar.</span><span class="sxs-lookup"><span data-stu-id="d26df-133">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="d26df-134">**Komplexitet ,** som är tillgänglig **via** filter, beräknas baserat på antalet indikatorer i den nyttolast som ledtråden pekar på är en attack.</span><span class="sxs-lookup"><span data-stu-id="d26df-134">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="d26df-135">Fler indikatorer ger lägre komplexitet.</span><span class="sxs-lookup"><span data-stu-id="d26df-135">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="d26df-136">**Källa,** som **är** tillgänglig via filter, anger om nyttolasten skapades i klientorganisationen eller är en del av Microsofts befintliga nyttolastkatalog (global).</span><span class="sxs-lookup"><span data-stu-id="d26df-136">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Vald nyttolast inom attack simuleringsutbildning i Microsoft 365 Defender-portalen](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="d26df-138">Välj en nyttolast i listan om du vill se en förhandsgranskning av nyttolasten med ytterligare information om den.</span><span class="sxs-lookup"><span data-stu-id="d26df-138">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="d26df-139">Om du vill skapa en egen nyttolast kan du läsa skapa [en nyttolast för attack simuleringsutbildning](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="d26df-139">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="d26df-140">Målgruppsanpassning</span><span class="sxs-lookup"><span data-stu-id="d26df-140">Audience targeting</span></span>

<span data-ttu-id="d26df-141">Nu är det dags att välja den här simuleringspubliken.</span><span class="sxs-lookup"><span data-stu-id="d26df-141">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="d26df-142">Du kan välja att **inkludera alla användare i organisationen eller** att endast ta med specifika användare och **grupper.**</span><span class="sxs-lookup"><span data-stu-id="d26df-142">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="d26df-143">När du väljer att **endast inkludera vissa användare och grupper kan** du antingen:</span><span class="sxs-lookup"><span data-stu-id="d26df-143">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="d26df-144">**Lägg till** användare , så att du kan utnyttja sökning för din klientorganisation, samt avancerade sök- och filtreringsfunktioner, till exempel rikta användare som inte har riktats av en simulering under de senaste 3 månaderna.</span><span class="sxs-lookup"><span data-stu-id="d26df-144">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>

  ![Utbildning av användarfiltrering i simulering av attack i Microsoft 365 Defender-portalen](../../media/attack-sim-preview-user-targeting.png)

- <span data-ttu-id="d26df-146">**Med Import från CSV** kan du importera en fördefinierad uppsättning användare för den här simuleringen.</span><span class="sxs-lookup"><span data-stu-id="d26df-146">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="d26df-147">Tilldela utbildning</span><span class="sxs-lookup"><span data-stu-id="d26df-147">Assigning training</span></span>

<span data-ttu-id="d26df-148">Vi rekommenderar att du tilldelar utbildning för varje simulering eftersom anställda som går igenom utbildning inte är lika känsliga för liknande attacker.</span><span class="sxs-lookup"><span data-stu-id="d26df-148">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="d26df-149">Du kan antingen välja att själv tilldela utbildning eller välja utbildningar och moduler.</span><span class="sxs-lookup"><span data-stu-id="d26df-149">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="d26df-150">Välj förfallodatum **för utbildning för** att se till att anställda slutför sin utbildning i tid.</span><span class="sxs-lookup"><span data-stu-id="d26df-150">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="d26df-151">Om du väljer att själv välja kurser och moduler kan du fortfarande se det rekommenderade innehållet samt alla tillgängliga kurser och moduler.</span><span class="sxs-lookup"><span data-stu-id="d26df-151">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Lägga till rekommenderad utbildning i simuleringsutbildning för attacker i Microsoft 365 Defender-portalen](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="d26df-153">I nästa steg måste du  Lägga till utbildningar om du valt att välja det själv och anpassa startsidan för utbildningen.</span><span class="sxs-lookup"><span data-stu-id="d26df-153">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="d26df-154">Du kommer att kunna förhandsgranska startsidan för utbildningen samt ändra sidhuvud och brödtext i den.</span><span class="sxs-lookup"><span data-stu-id="d26df-154">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="d26df-155">Starta information och granska</span><span class="sxs-lookup"><span data-stu-id="d26df-155">Launch details and review</span></span>

<span data-ttu-id="d26df-156">Nu när allt är konfigurerat kan du starta den här simuleringen direkt eller schemalägga den till ett senare datum.</span><span class="sxs-lookup"><span data-stu-id="d26df-156">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="d26df-157">Du måste också välja när du vill avsluta den här simuleringen.</span><span class="sxs-lookup"><span data-stu-id="d26df-157">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="d26df-158">Vi slutar samla in interaktionen med den här simuleringen efter den valda tiden.</span><span class="sxs-lookup"><span data-stu-id="d26df-158">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="d26df-159">**Aktivera regionmedveten leverans av tidszoner** för att leverera simulerade attackmeddelanden till dina anställda under arbetstid baserat på deras region.</span><span class="sxs-lookup"><span data-stu-id="d26df-159">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="d26df-160">När du är klar klickar du på **Nästa och** granskar detaljerna i din simulering.</span><span class="sxs-lookup"><span data-stu-id="d26df-160">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="d26df-161">Klicka på **Redigera** på någon av delarna för att gå tillbaka och ändra information som behöver ändras.</span><span class="sxs-lookup"><span data-stu-id="d26df-161">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="d26df-162">Klicka på Skicka när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="d26df-162">Once done, click **Submit**.</span></span>
