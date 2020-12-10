---
title: Simulera nätfiske-attack med Microsoft Defender för
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Lär dig hur man simulerar nät fiske attacker och kan utbilda dina användare om nätfiske-förebyggande med utbildning för attack simulering i Microsoft Defender för Office 365.
ms.openlocfilehash: 8f5f457f60c81fe961282f33bb8c37f4d9e27aab
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616110"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="13bfa-103">Simulera nätfiske-attack</span><span class="sxs-lookup"><span data-stu-id="13bfa-103">Simulate a phishing attack</span></span>

<span data-ttu-id="13bfa-104">Med utbildning för angrepps Simulator via Microsoft Defender för Office 365 kan du köra säkra cyberterrorism-attacker på din organisation för att testa dina säkerhets principer och-rutiner, samt träna de anställda i organisationen att öka sin medvetenhet och minska deras känslighet för angrepp.</span><span class="sxs-lookup"><span data-stu-id="13bfa-104">Attack simulator training through Microsoft Defender for Office 365 lets you run benign cyber attack simulations on your organization to test your security policies and practices, as well as train the employees of your organization to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="13bfa-105">Här får du hjälp med att simulera en nätfiske-attack genom att använda en angrepps Simulator utbildning.</span><span class="sxs-lookup"><span data-stu-id="13bfa-105">The following walks you through simulating a phishing attack using attack simulator training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="13bfa-106">För att starta en simulerad nätfiske-attack navigerar du till [Microsoft 365 säkerhets Center](https://security.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="13bfa-106">To launch a simulated phishing attack, navigate to the [Microsoft 365 security center](https://security.microsoft.com/).</span></span> <span data-ttu-id="13bfa-107">Under **e-post& samarbete** klickar du på **angrepps Simulator** och växlar till fliken [**simuleringar**](https://security.microsoft.com/attacksimulator?viewid=simulations) .</span><span class="sxs-lookup"><span data-stu-id="13bfa-107">Under **Email & collaboration** click on **Attack simulator** and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="13bfa-108">Välj **+ starta en simulering** under **simuleringar** .</span><span class="sxs-lookup"><span data-stu-id="13bfa-108">Under **Simulations** select **+ Launch a simulation**.</span></span>

![Starta en simulerings knapp i Microsoft 365 säkerhets Center](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="13bfa-110">När som helst under simuleringen kan du spara och stänga för att fortsätta att konfigurera simuleringen senare.</span><span class="sxs-lookup"><span data-stu-id="13bfa-110">At any point during simulation creation you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="13bfa-111">Välja en social teknik teknik</span><span class="sxs-lookup"><span data-stu-id="13bfa-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="13bfa-112">Välj bland fyra olika tekniker som kan granskas från [Mitre to&CK® Framework](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="13bfa-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="13bfa-113">Det finns olika nytto laster för olika tekniker.</span><span class="sxs-lookup"><span data-stu-id="13bfa-113">Different payloads are available for different techniques.</span></span>

- <span data-ttu-id="13bfa-114">**Skörde** uppgifter för att samla in autentiseringsuppgifter från anställda genom att ta dem till en välkänd webbplats där du kan skicka ett användar namn och lösen ord.</span><span class="sxs-lookup"><span data-stu-id="13bfa-114">**Credential harvest** attempts to collect credentials from employees by taking them to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="13bfa-115">**Bifogad fil med skadlig kod** lägger till en skadlig bifogad fil i ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="13bfa-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="13bfa-116">När den här bifogade filen öppnas körs en kod som gör att angriparen kan kompromissa med mål enheten.</span><span class="sxs-lookup"><span data-stu-id="13bfa-116">When opened, this attachment will run some arbitrary code that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="13bfa-117">**Länk i bilaga** är en typ av certifiering skörde hybrid.</span><span class="sxs-lookup"><span data-stu-id="13bfa-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="13bfa-118">En angripare infogar en URL i en e-postbilaga.</span><span class="sxs-lookup"><span data-stu-id="13bfa-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="13bfa-119">URL-adressen i den bifogade filen följer samma teknik som skörd för autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="13bfa-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="13bfa-120">**Länk till malware kör skadlig** kod från en fil som finns på en välkänd fildelnings webbplats.</span><span class="sxs-lookup"><span data-stu-id="13bfa-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file-sharing site.</span></span> <span data-ttu-id="13bfa-121">En länk till den här skadliga filen läggs till i meddelandet som skickas till målet och klicka på den kör filen och gör det lättare för angriparen att kompromissa med mål enheten.</span><span class="sxs-lookup"><span data-stu-id="13bfa-121">A link to this malicious file is added to the message sent to the target and clicking it will run the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="13bfa-122">Om du klickar på **Visa information** inom beskrivningen av varje teknik visas ytterligare information om tekniken samt simulerings stegen för den metoden.</span><span class="sxs-lookup"><span data-stu-id="13bfa-122">Clicking on **View details** within the description of each technique will display further information about the technique as well as the simulation steps for that technique.</span></span>
>
> ![Simulerings steg för certifiering skörd inom utbildning för simulering av attacker i Microsoft 365 säkerhets Center](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="13bfa-124">När du har valt en teknik och klickat på **Nästa** får du ett namn och eventuellt en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="13bfa-124">Once you've selected the technique and clicked on **Next** give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="13bfa-125">Välja en nytto Last</span><span class="sxs-lookup"><span data-stu-id="13bfa-125">Selecting a payload</span></span>

<span data-ttu-id="13bfa-126">Sedan måste du antingen välja en nytto Last från en befintlig nytto Last katalog.</span><span class="sxs-lookup"><span data-stu-id="13bfa-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="13bfa-127">Det finns många data punkter som du kan använda för att välja:</span><span class="sxs-lookup"><span data-stu-id="13bfa-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="13bfa-128">**Klicka på Rate** räknas hur många personer som klickade på denna nytto Last.</span><span class="sxs-lookup"><span data-stu-id="13bfa-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="13bfa-129">**Förväntad kompromiss frekvens** förväntar sig procent av personer som kommer att bli utsatt för denna nytto Last baserat på historiska data för denna nytto Last i Microsoft Defender för Office 365-kunder.</span><span class="sxs-lookup"><span data-stu-id="13bfa-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historic data for this payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="13bfa-130">**Simuleringar startas** antal gånger denna nytto Last användes i andra simuleringar.</span><span class="sxs-lookup"><span data-stu-id="13bfa-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="13bfa-131">**Komplexitet**, tillgängliga genom **filter**, beräknas baserat på antalet indikatorer inom nytto lasten som led trådar till att det är en attack.</span><span class="sxs-lookup"><span data-stu-id="13bfa-131">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="13bfa-132">Fler indikatorer kan leda till lägre komplexitet.</span><span class="sxs-lookup"><span data-stu-id="13bfa-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="13bfa-133">**Källa**, som är tillgänglig via **filter**, anger om nytto lasten skapades på din klient organisation eller är en del av Microsofts förvalda nytto fil katalog (global).</span><span class="sxs-lookup"><span data-stu-id="13bfa-133">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Vald nytto Last i utbildning för attack simulering i Microsoft 365 säkerhets Center](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="13bfa-135">Välj en nytto Last i listan för att se en förhands granskning av nytto lasten med ytterligare information om den.</span><span class="sxs-lookup"><span data-stu-id="13bfa-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="13bfa-136">Om du vill skapa en egen nytto Last läser du [skapa en nytto last för utbildning för utskrivning](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="13bfa-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="13bfa-137">Mål grupps anpassning</span><span class="sxs-lookup"><span data-stu-id="13bfa-137">Audience targeting</span></span>

<span data-ttu-id="13bfa-138">Nu är det dags att välja simuleringens mål grupp.</span><span class="sxs-lookup"><span data-stu-id="13bfa-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="13bfa-139">Du kan välja att **ta med alla användare i organisationen** eller **bara ta med specifika användare och grupper**.</span><span class="sxs-lookup"><span data-stu-id="13bfa-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="13bfa-140">Om du väljer att **bara inkludera specifika användare och grupper** kan du antingen:</span><span class="sxs-lookup"><span data-stu-id="13bfa-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="13bfa-141">**Lägg till användare**, som gör att du kan använda Sök funktionen för din klient organisation, samt avancerade funktioner för sökning och filtrering, som mål för användare som inte har riktat mot en simulering under de senaste 3 månaderna.</span><span class="sxs-lookup"><span data-stu-id="13bfa-141">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="13bfa-142">![Användar filter i utbildning för attack simulering i Microsoft 365 Security Center](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="13bfa-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="13bfa-143">**Importera från CSV** låter dig importera en fördefinierad uppsättning användare för den här simuleringen.</span><span class="sxs-lookup"><span data-stu-id="13bfa-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="13bfa-144">Tilldela utbildning</span><span class="sxs-lookup"><span data-stu-id="13bfa-144">Assigning training</span></span>

<span data-ttu-id="13bfa-145">Vi rekommenderar att du tilldelar utbildning för varje simulering, eftersom anställda som deltar i utbildningen är mindre utsatta för liknande attacker.</span><span class="sxs-lookup"><span data-stu-id="13bfa-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="13bfa-146">Du kan antingen välja att ha utbildning tilldelat åt dig eller välja kurser och moduler själv.</span><span class="sxs-lookup"><span data-stu-id="13bfa-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="13bfa-147">Välj **förfallo datum för utbildning** för att se till att anställda avslutar sin utbildning i god tid.</span><span class="sxs-lookup"><span data-stu-id="13bfa-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="13bfa-148">Om du väljer att välja kurser och moduler själv kan du fortfarande se det rekommenderade innehållet och alla tillgängliga kurser och moduler.</span><span class="sxs-lookup"><span data-stu-id="13bfa-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Lägga till Rekommenderad utbildning i utbildning för attack simulering i Microsoft 365 Security Center](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="13bfa-150">I nästa steg måste du **lägga till utbildningar** om du väljer det själv och anpassar din utbildning.</span><span class="sxs-lookup"><span data-stu-id="13bfa-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="13bfa-151">Du kan förhandsgranska övnings sidan för utbildning och även ändra sidhuvud och brödtext.</span><span class="sxs-lookup"><span data-stu-id="13bfa-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="13bfa-152">Starta detaljer och granska</span><span class="sxs-lookup"><span data-stu-id="13bfa-152">Launch details and review</span></span>

<span data-ttu-id="13bfa-153">Nu när allt är konfigurerat kan du starta simuleringen direkt eller schemalägga det för ett senare datum.</span><span class="sxs-lookup"><span data-stu-id="13bfa-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="13bfa-154">Du måste också välja när simuleringen ska avslutas.</span><span class="sxs-lookup"><span data-stu-id="13bfa-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="13bfa-155">Vi slutar samla in interaktionen med den här simuleringen tidigare den valda tiden.</span><span class="sxs-lookup"><span data-stu-id="13bfa-155">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="13bfa-156">**Aktivera region medveten leverans** för att leverera simulerade attack meddelanden till dina anställda under deras arbets tid baserat på deras region.</span><span class="sxs-lookup"><span data-stu-id="13bfa-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="13bfa-157">När du är klar klickar du på **Nästa** och läser informationen för simuleringen.</span><span class="sxs-lookup"><span data-stu-id="13bfa-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="13bfa-158">Klicka på **Redigera** på någon av delarna för att gå tillbaka och ändra eventuell information som behövs.</span><span class="sxs-lookup"><span data-stu-id="13bfa-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="13bfa-159">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="13bfa-159">Once done, click **Submit**.</span></span>
