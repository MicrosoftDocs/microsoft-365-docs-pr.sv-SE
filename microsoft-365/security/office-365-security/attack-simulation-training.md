---
title: Simulera nätfiske-attack med Microsoft Defender för Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan lära sig hur man simulerar nät fiske attacker och tränar användarna att förhindra nätfiske genom att använda utbildning för attack simulering i Microsoft Defender för Office 365.
ms.openlocfilehash: dfdd3c93afb1b0fb30cc5b5affc040a369c29447
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870973"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="cca8b-103">Simulera nätfiske-attack</span><span class="sxs-lookup"><span data-stu-id="cca8b-103">Simulate a phishing attack</span></span>

<span data-ttu-id="cca8b-104">Utbildning för angrepps simulering i Microsoft Defender för Office 365 kan du köra säkra cyberattack-simuleringar på din organisation för att testa din säkerhets policy och dina arbets rutiner, samt för att träna dina anställda att öka sin medvetenhet och minska deras känslighet för attacker.</span><span class="sxs-lookup"><span data-stu-id="cca8b-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="cca8b-105">I den här artikeln får du lära dig hur du skapar en simulerad nätfiske-attack med utbildning för att simulera attacker.</span><span class="sxs-lookup"><span data-stu-id="cca8b-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="cca8b-106">Information om hur du kommer igång med utbildning för att förbereda attacker finns i [komma igång med att använda funktionen för simulering av attacker](attack-simulation-training-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="cca8b-106">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="cca8b-107">För att starta en simulerad nätfiske-attack, öppna [Microsoft 365 Security Center](https://security.microsoft.com/), gå till **e-& samarbets** möjligheter för \> **simulering** och gå till fliken [**simuleringar**](https://security.microsoft.com/attacksimulator?viewid=simulations) .</span><span class="sxs-lookup"><span data-stu-id="cca8b-107">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="cca8b-108">Välj **+ starta en simulering** under **simuleringar**.</span><span class="sxs-lookup"><span data-stu-id="cca8b-108">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Starta en simulerings knapp i Microsoft 365 säkerhets Center](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="cca8b-110">När som helst under simuleringen kan du spara och stänga för att fortsätta att konfigurera simuleringen senare.</span><span class="sxs-lookup"><span data-stu-id="cca8b-110">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="cca8b-111">Välja en social teknik teknik</span><span class="sxs-lookup"><span data-stu-id="cca8b-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="cca8b-112">Välj bland fyra olika tekniker som kan granskas från [Mitre to&CK® Framework](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="cca8b-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="cca8b-113">Olika nytto laster är tillgängliga för olika tekniker:</span><span class="sxs-lookup"><span data-stu-id="cca8b-113">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="cca8b-114">När uppgifter **skördas** försöker insamling av autentiseringsuppgifter genom att användare till en välkänd webbplats med inmatnings rutor skickar ett användar namn och lösen ord.</span><span class="sxs-lookup"><span data-stu-id="cca8b-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="cca8b-115">**Bifogad fil med skadlig kod** lägger till en skadlig bifogad fil i ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="cca8b-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="cca8b-116">När användaren öppnar den bifogade filen körs valfri kod som gör att angriparen kan kompromissa med mål enheten.</span><span class="sxs-lookup"><span data-stu-id="cca8b-116">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="cca8b-117">**Länk i bilaga** är en typ av certifiering skörde hybrid.</span><span class="sxs-lookup"><span data-stu-id="cca8b-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="cca8b-118">En angripare infogar en URL i en e-postbilaga.</span><span class="sxs-lookup"><span data-stu-id="cca8b-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="cca8b-119">URL-adressen i den bifogade filen följer samma teknik som skörd för autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="cca8b-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="cca8b-120">**Länk till malware kör skadlig** kod från en fil som finns på en välkänd fildelnings tjänst.</span><span class="sxs-lookup"><span data-stu-id="cca8b-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="cca8b-121">Meddelandet som skickas till användaren innehåller en länk till den här skadliga filen.</span><span class="sxs-lookup"><span data-stu-id="cca8b-121">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="cca8b-122">Att öppna filen och göra det lättare för angriparen att kompromissa med mål enheten.</span><span class="sxs-lookup"><span data-stu-id="cca8b-122">Opening the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="cca8b-123">Om du klickar på **Visa information** inom beskrivningen av varje teknik visas ytterligare information och simulerings stegen för tekniken.</span><span class="sxs-lookup"><span data-stu-id="cca8b-123">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Simulerings steg för certifiering skörd inom utbildning för simulering av attacker i Microsoft 365 säkerhets Center](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="cca8b-125">När du har valt en teknik och klickat på **Nästa** ska du ge simuleringen ett namn och eventuellt en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="cca8b-125">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="cca8b-126">Välja en nytto Last</span><span class="sxs-lookup"><span data-stu-id="cca8b-126">Selecting a payload</span></span>

<span data-ttu-id="cca8b-127">Sedan måste du antingen välja en nytto Last från en befintlig nytto Last katalog.</span><span class="sxs-lookup"><span data-stu-id="cca8b-127">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="cca8b-128">Det finns många data punkter som du kan använda för att välja:</span><span class="sxs-lookup"><span data-stu-id="cca8b-128">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="cca8b-129">**Klicka på Rate** räknas hur många personer som klickade på denna nytto Last.</span><span class="sxs-lookup"><span data-stu-id="cca8b-129">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="cca8b-130">**Förväntad kompromiss frekvens** förväntar sig att procent andelen personer som kommer att bli utsatt för denna nytto Last baserat på historiska data för nytto lasten i Microsoft Defender för Office 365-kunder.</span><span class="sxs-lookup"><span data-stu-id="cca8b-130">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="cca8b-131">**Simuleringar startas** antal gånger denna nytto Last användes i andra simuleringar.</span><span class="sxs-lookup"><span data-stu-id="cca8b-131">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="cca8b-132">**Komplexitet**, tillgängliga genom **filter**, beräknas baserat på antalet indikatorer inom nytto lasten som led trådar till att det är en attack.</span><span class="sxs-lookup"><span data-stu-id="cca8b-132">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="cca8b-133">Fler indikatorer kan leda till lägre komplexitet.</span><span class="sxs-lookup"><span data-stu-id="cca8b-133">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="cca8b-134">**Källa**, som är tillgänglig via **filter**, anger om nytto lasten skapades på din klient organisation eller är en del av Microsofts förvalda nytto fil katalog (global).</span><span class="sxs-lookup"><span data-stu-id="cca8b-134">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Vald nytto Last i utbildning för attack simulering i Microsoft 365 säkerhets Center](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="cca8b-136">Välj en nytto Last i listan för att se en förhands granskning av nytto lasten med ytterligare information om den.</span><span class="sxs-lookup"><span data-stu-id="cca8b-136">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="cca8b-137">Om du vill skapa en egen nytto Last läser du [skapa en nytto last för utbildning för utskrivning](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="cca8b-137">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="cca8b-138">Mål grupps anpassning</span><span class="sxs-lookup"><span data-stu-id="cca8b-138">Audience targeting</span></span>

<span data-ttu-id="cca8b-139">Nu är det dags att välja simuleringens mål grupp.</span><span class="sxs-lookup"><span data-stu-id="cca8b-139">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="cca8b-140">Du kan välja att **ta med alla användare i organisationen** eller **bara ta med specifika användare och grupper**.</span><span class="sxs-lookup"><span data-stu-id="cca8b-140">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="cca8b-141">Om du väljer att **bara inkludera specifika användare och grupper** kan du antingen:</span><span class="sxs-lookup"><span data-stu-id="cca8b-141">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="cca8b-142">**Lägg till användare**, som gör att du kan använda Sök funktionen för din klient organisation, samt avancerade funktioner för sökning och filtrering, som mål för användare som inte har riktat mot en simulering under de senaste 3 månaderna.</span><span class="sxs-lookup"><span data-stu-id="cca8b-142">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="cca8b-143">![Användar filter i utbildning för attack simulering i Microsoft 365 Security Center](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="cca8b-143">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="cca8b-144">**Importera från CSV** låter dig importera en fördefinierad uppsättning användare för den här simuleringen.</span><span class="sxs-lookup"><span data-stu-id="cca8b-144">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="cca8b-145">Tilldela utbildning</span><span class="sxs-lookup"><span data-stu-id="cca8b-145">Assigning training</span></span>

<span data-ttu-id="cca8b-146">Vi rekommenderar att du tilldelar utbildning för varje simulering, eftersom anställda som deltar i utbildningen är mindre utsatta för liknande attacker.</span><span class="sxs-lookup"><span data-stu-id="cca8b-146">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="cca8b-147">Du kan antingen välja att ha utbildning tilldelat åt dig eller välja kurser och moduler själv.</span><span class="sxs-lookup"><span data-stu-id="cca8b-147">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="cca8b-148">Välj **förfallo datum för utbildning** för att se till att anställda avslutar sin utbildning i god tid.</span><span class="sxs-lookup"><span data-stu-id="cca8b-148">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="cca8b-149">Om du väljer att välja kurser och moduler själv kan du fortfarande se det rekommenderade innehållet och alla tillgängliga kurser och moduler.</span><span class="sxs-lookup"><span data-stu-id="cca8b-149">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Lägga till Rekommenderad utbildning i utbildning för attack simulering i Microsoft 365 Security Center](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="cca8b-151">I nästa steg måste du **lägga till utbildningar** om du väljer det själv och anpassar din utbildning.</span><span class="sxs-lookup"><span data-stu-id="cca8b-151">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="cca8b-152">Du kan förhandsgranska övnings sidan för utbildning och även ändra sidhuvud och brödtext.</span><span class="sxs-lookup"><span data-stu-id="cca8b-152">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="cca8b-153">Starta detaljer och granska</span><span class="sxs-lookup"><span data-stu-id="cca8b-153">Launch details and review</span></span>

<span data-ttu-id="cca8b-154">Nu när allt är konfigurerat kan du starta simuleringen direkt eller schemalägga det för ett senare datum.</span><span class="sxs-lookup"><span data-stu-id="cca8b-154">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="cca8b-155">Du måste också välja när simuleringen ska avslutas.</span><span class="sxs-lookup"><span data-stu-id="cca8b-155">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="cca8b-156">Vi slutar samla in interaktionen med den här simuleringen tidigare den valda tiden.</span><span class="sxs-lookup"><span data-stu-id="cca8b-156">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="cca8b-157">**Aktivera region medveten leverans** för att leverera simulerade attack meddelanden till dina anställda under deras arbets tid baserat på deras region.</span><span class="sxs-lookup"><span data-stu-id="cca8b-157">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="cca8b-158">När du är klar klickar du på **Nästa** och läser informationen för simuleringen.</span><span class="sxs-lookup"><span data-stu-id="cca8b-158">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="cca8b-159">Klicka på **Redigera** på någon av delarna för att gå tillbaka och ändra eventuell information som behövs.</span><span class="sxs-lookup"><span data-stu-id="cca8b-159">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="cca8b-160">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="cca8b-160">Once done, click **Submit**.</span></span>
