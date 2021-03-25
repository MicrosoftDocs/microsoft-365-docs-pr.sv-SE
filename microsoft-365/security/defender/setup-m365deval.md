---
title: Konfigurera utvärderingslabb eller pilotmiljö med Microsoft 365 Defender
description: Gå till Microsoft 365 Säkerhetscenter och konfigurera sedan testlabbmiljön i Microsoft 365 Defender
keywords: Utvärderingsversion av Microsoft Threat Protection, pilotkonfiguration av Microsoft Threat Protection, prova Microsoft Threat Protection, utvärderingslabbkonfiguration av Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 976f6a1ec010348e8a281c251064acdd7a26748b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074777"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="c57b6-104">Konfigurera utvärderingslabbmiljön i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c57b6-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c57b6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c57b6-105">**Applies to:**</span></span>
- <span data-ttu-id="c57b6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c57b6-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="c57b6-107">Det är en process i tre steg att skapa en provlabb eller pilotmiljö med Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="c57b6-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="c57b6-108">[![Fas 1: Förbereda](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="c57b6-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="c57b6-109">Fas 1: Förbereda</span><span class="sxs-lookup"><span data-stu-id="c57b6-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |![Fas 2: Konfigurera](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="c57b6-111">Fas 2: Konfigurera</span><span class="sxs-lookup"><span data-stu-id="c57b6-111">Phase 2: Set up</span></span> |<span data-ttu-id="c57b6-112">[![Fas 3: Introduktion](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="c57b6-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span></span><br/>[<span data-ttu-id="c57b6-113">Fas 3: Introduktion</span><span class="sxs-lookup"><span data-stu-id="c57b6-113">Phase 3: Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="c57b6-114">[![Tillbaka till pilottestning](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="c57b6-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="c57b6-115">Tillbaka till pilotspelboken</span><span class="sxs-lookup"><span data-stu-id="c57b6-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="c57b6-116">*Du är här!*</span><span class="sxs-lookup"><span data-stu-id="c57b6-116">*You are here!*</span></span>  | | |


<span data-ttu-id="c57b6-117">Du befinner dig för närvarande i ställ in fas.</span><span class="sxs-lookup"><span data-stu-id="c57b6-117">You're currently in the set up phase.</span></span> <span data-ttu-id="c57b6-118">Gör de första stegen för att komma åt Microsoft 365 Säkerhetscenter och konfigurera sedan testlabb eller pilotmiljö.</span><span class="sxs-lookup"><span data-stu-id="c57b6-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="c57b6-119">Registrera dig för en Office 365- eller Azure Active Directory-prenumeration om du vill generera en *.onmicrosoft.com-klientorganisation* som du kan använda för att registrera dig för din Microsoft 365 E5-licens.</span><span class="sxs-lookup"><span data-stu-id="c57b6-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="c57b6-120">Om du redan har en befintlig Office 365- eller Azure Active Directory-prenumeration kan du hoppa över stegen för att skapa klientorganisation eller utvärderingsversionen av Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c57b6-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="c57b6-121">I den här fasen får du vägledning genom att:</span><span class="sxs-lookup"><span data-stu-id="c57b6-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="c57b6-122">Skapa en utvärderingsversion av Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="c57b6-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="c57b6-123">Aktivera utvärderingsprenumeration på Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c57b6-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="c57b6-124">Skapa en utvärderingsversion av Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="c57b6-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="c57b6-125">Om du redan har en befintlig Office 365- eller Azure Active Directory-prenumeration kan du hoppa över stegen för att skapa klientorganisationens klientorganisation i Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c57b6-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="c57b6-126">Gå till Office [365 E5-produktportalen och](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) välj **Kostnadsfri utvärderingsversion**.</span><span class="sxs-lookup"><span data-stu-id="c57b6-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Bild of_Office utvärderingsversion av 365 E5 kostnadsfritt](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="c57b6-128">Slutför utvärderingsversionen genom att ange din e-postadress (personlig eller företagsadress).</span><span class="sxs-lookup"><span data-stu-id="c57b6-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="c57b6-129">Klicka **på Konfigurera konto.**</span><span class="sxs-lookup"><span data-stu-id="c57b6-129">Click **Set up account**.</span></span>

   ![Bild of_Office registreringsinställningar för utvärderingsversionen av 365 E5](../../media/mtp-eval-10.png)

3. <span data-ttu-id="c57b6-131">Fyll i ditt förnamn, efternamn, telefonnummer, företagsnamn, företagsstorlek och land eller region.</span><span class="sxs-lookup"><span data-stu-id="c57b6-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Bild of_Office 365 E5 sida för registrering av utvärderingsversion där du uppmanas att ange namn, telefonnummer och företagsinformation](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="c57b6-133">Landet eller regionen du anger här bestämmer vilken datacenterregion som Office 365 kommer att vara värd för.</span><span class="sxs-lookup"><span data-stu-id="c57b6-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="c57b6-134">Välj verifieringsinställning: via ett sms eller samtal.</span><span class="sxs-lookup"><span data-stu-id="c57b6-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="c57b6-135">Klicka **på Skicka verifieringskod**.</span><span class="sxs-lookup"><span data-stu-id="c57b6-135">Click **Send Verification Code**.</span></span> 

   ![Bild of_Office 365 E5 utvärderingsversion av registreringskonfiguration som frågar om verifieringsinställning](../../media/mtp-eval-12.png)

5. <span data-ttu-id="c57b6-137">Ange eget domännamn för klientorganisationen och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="c57b6-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Bild of_Office registreringskonfigurationssidan för utvärderingsversionen av 365 E5 där du kan konfigurera ditt domännamn](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="c57b6-139">Konfigurera den första identiteten, som blir global administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="c57b6-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="c57b6-140">Fyll i **Namn** och **Lösenord.**</span><span class="sxs-lookup"><span data-stu-id="c57b6-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="c57b6-141">Klicka **på Registrera dig.**</span><span class="sxs-lookup"><span data-stu-id="c57b6-141">Click **Sign up**.</span></span>

   ![Bild of_Office 365 E5 utvärderingsversionsinstallationssida där du kan ange din företagsidentitet](../../media/mtp-eval-14.png)

7. <span data-ttu-id="c57b6-143">Klicka **på Gå till installationsprogrammet** för att slutföra klientorganisationsetablering för Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c57b6-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Bild av registreringsinstallationssidan för Office 365 E5 med uppmaning om att klicka på knappen Gå till installation](../../media/mtp-eval-15.png)

8. <span data-ttu-id="c57b6-145">Anslut företagsdomänen till Office 365-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="c57b6-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="c57b6-146">[Valfritt] Välj **Anslut en domän som du redan äger** och skriv in domännamnet.</span><span class="sxs-lookup"><span data-stu-id="c57b6-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="c57b6-147">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="c57b6-147">Click **Next**.</span></span>

   ![Bild of_Office konfigurationssidan i 365 E5 där du bör anpassa din inloggning och e-post](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="c57b6-149">Lägg till en TXT- eller MX-post för att verifiera domänägarskapet.</span><span class="sxs-lookup"><span data-stu-id="c57b6-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="c57b6-150">När du har lagt till TXT- eller MX-posten i din domän väljer du **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="c57b6-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Bild of_Office 365 E5-konfigurationssidan där du bör lägga till en TXT av MX-post för att verifiera din domän](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="c57b6-152">[Valfritt] Skapa fler användarkonton för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="c57b6-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="c57b6-153">Du kan hoppa över det här steget genom att klicka **på Nästa.**</span><span class="sxs-lookup"><span data-stu-id="c57b6-153">You can skip this step by clicking **Next**.</span></span>

    ![Bild of_Office 365 E5-konfigurationssidan där du kan lägga till fler användare](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="c57b6-155">[Valfritt] Ladda ned Office-appar.</span><span class="sxs-lookup"><span data-stu-id="c57b6-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="c57b6-156">Hoppa **över det här** steget genom att klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="c57b6-156">Click **Next** to skip this step.</span></span> 

    ![Bild of_Office 365 E5 där du kan installera Office-programmen](../../media/mtp-eval-19.png)

12. <span data-ttu-id="c57b6-158">[Valfritt] Migrera e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="c57b6-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="c57b6-159">Du kan hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="c57b6-159">Again, you can skip this step.</span></span>

    ![Bild of_Office 365 E5 där du kan ange om du vill migrera e-postmeddelanden eller inte](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="c57b6-161">Välj onlinetjänster.</span><span class="sxs-lookup"><span data-stu-id="c57b6-161">Choose online services.</span></span> <span data-ttu-id="c57b6-162">Välj **Exchange** och klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="c57b6-162">Select **Exchange** and click **Next**.</span></span> 

    ![Bild of_Office 365 E5 där du kan välja onlinetjänster](../../media/mtp-eval-21.png)

14. <span data-ttu-id="c57b6-164">Lägg till MX-, CNAME- och TXT-poster i din domän.</span><span class="sxs-lookup"><span data-stu-id="c57b6-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="c57b6-165">När det är klart väljer **du Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="c57b6-165">When completed, select **Verify**.</span></span>

    ![Bild of_Office 365 E5 här kan du lägga till dina DNS-poster](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="c57b6-167">Grattis! Du har slutfört etableringen av din Office 365-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="c57b6-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Bild of_Office konfigurationsbekräftelse för E5 i 365](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="c57b6-169">Aktivera utvärderingsprenumeration på Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c57b6-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="c57b6-170">När du registrerar dig för en utvärderingsversion får du 25 användarlicenser att använda under en månad.</span><span class="sxs-lookup"><span data-stu-id="c57b6-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="c57b6-171">Mer [information finns i Prova eller köpa en M365-prenumeration.](../../commerce/try-or-buy-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="c57b6-171">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="c57b6-172">I [administrationscentret för Microsoft 365 klickar](https://admin.microsoft.com/)du **på Fakturering** och går sedan till **Köp tjänster.**</span><span class="sxs-lookup"><span data-stu-id="c57b6-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="c57b6-173">Välj **Microsoft 365 E5 och** klicka på Starta kostnadsfri **utvärderingsversion**.</span><span class="sxs-lookup"><span data-stu-id="c57b6-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Bild of_Microsoft 365 E5 Starta kostnadsfri utvärderingsversion](../../media/mtp-eval-24.png)

3. <span data-ttu-id="c57b6-175">Välj verifieringsinställning: via ett sms eller samtal.</span><span class="sxs-lookup"><span data-stu-id="c57b6-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="c57b6-176">När du har bestämt dig anger du telefonnumret och väljer **Skicka sms eller** Ring **mig** beroende på ditt val.</span><span class="sxs-lookup"><span data-stu-id="c57b6-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Bild of_Microsoft 365 E5 Starta kostnadsfri utvärderingsversion och fråga efter kontaktuppgifter för att skicka kod för att bevisa att du inte är en robot](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="c57b6-178">Ange verifieringskoden och klicka på **Starta den kostnadsfria utvärderingsversionen**.</span><span class="sxs-lookup"><span data-stu-id="c57b6-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Bild of_Microsoft 365 E5 Starta kostnadsfri utvärderingsversion där du kan fylla i verifieringskoden som systemet har skickat för att bevisa att du inte är en robot](../../media/mtp-eval-26.png)

5. <span data-ttu-id="c57b6-180">Klicka **på Prova nu** för att bekräfta utvärderingsversionen av Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c57b6-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Bild of_Microsoft 365 E5 Starta kostnadsfri utvärderingsversion där du ska klocka knappen Prova nu för att starta](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="c57b6-182">Gå till Microsoft **365 Admin Center Användare**  >    >  **aktiva användare.**</span><span class="sxs-lookup"><span data-stu-id="c57b6-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="c57b6-183">Välj ditt användarkonto, välj **Hantera produktlicenser och** byt sedan licensen från Office 365 E5 till **Microsoft 365 E5.**</span><span class="sxs-lookup"><span data-stu-id="c57b6-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="c57b6-184">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c57b6-184">Click **Save**.</span></span>

   ![Bild of_Microsoft 365 Admin Center-sida där du kan välja Microsoft 365 E5-licens](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="c57b6-186">Välj det globala administratörskontot igen och klicka sedan **på Hantera användarnamn**.</span><span class="sxs-lookup"><span data-stu-id="c57b6-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Bild of_Microsoft 365 Admin Center-sida där du kan välja Konto och sedan Hantera användarnamn](../../media/mtp-eval-29.png)

8. <span data-ttu-id="c57b6-188">[Valfritt] Ändra domänen från *onmicrosoft.com* till din egen domän, beroende på vad du valde i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="c57b6-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="c57b6-189">Klicka på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="c57b6-189">Click **Save changes**.</span></span>

   ![Bild of_Microsoft 365 Administrationscenter där du kan ändra domäninställningarna](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="c57b6-191">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c57b6-191">Next step</span></span>
|[<span data-ttu-id="c57b6-192">Fas 3: Konfigurera & onboard</span><span class="sxs-lookup"><span data-stu-id="c57b6-192">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="c57b6-193">Konfigurera varje Microsoft 365 Defender-pilotversion för provlabb eller pilotmiljö med Microsoft 365 Defender och registrera slutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="c57b6-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
