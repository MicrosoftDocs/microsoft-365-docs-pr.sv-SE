---
title: Konfigurera testlabbeta för Microsoft Threat Protection
description: Öppna Microsoft 365 Security Center och konfigurera sedan testlabbeta Microsoft Threat Protection
keywords: Testinställning för Microsoft Threat Protection, prova microsoft threat protection, microsoft threat protection utvärdering lab setup
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 50557b0824999f0220af4d12b906b0274db4471e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049621"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="537f9-104">Konfigurera testlabbeta för Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="537f9-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="537f9-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="537f9-105">**Applies to:**</span></span>
- <span data-ttu-id="537f9-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="537f9-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="537f9-107">Att skapa en testlabbmiljö för Microsoft Threat Protection och distribuera den är en trefasprocess:</span><span class="sxs-lookup"><span data-stu-id="537f9-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Förbered utvärderingslabbet för Microsoft Threat Protection" />
      <br/><span data-ttu-id="537f9-109">Fas 1: Förbered</a></span><span class="sxs-lookup"><span data-stu-id="537f9-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Konfigurera microsofts utvärderingslabb för hotskydd" />
      <br/><span data-ttu-id="537f9-111">Fas 2: Installation</a></span><span class="sxs-lookup"><span data-stu-id="537f9-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Konfigurera varje Microsoft Threat Protection-pelare för testlabbmiljön för Microsoft Threat Protection och dina slutpunkter" />
      <br/><span data-ttu-id="537f9-113">Fas 3: Konfigurera & ombord</a></span><span class="sxs-lookup"><span data-stu-id="537f9-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="537f9-114">Du befinner dig för närvarande i ställningsfasen.</span><span class="sxs-lookup"><span data-stu-id="537f9-114">You are currently in the set up phase.</span></span> <span data-ttu-id="537f9-115">Gör de första stegen för att komma åt Microsoft 365 Security Center och konfigurera sedan testlabbets miljö.</span><span class="sxs-lookup"><span data-stu-id="537f9-115">Take the initial steps to access Microsoft 365 Security Center then setup your trial lab environment.</span></span>

<span data-ttu-id="537f9-116">Registrera dig för en Office 365- eller Azure Active Directory-prenumeration för att generera en *.onmicrosoft.com-klient* som du kan använda för att registrera dig för din Microsoft 365 E5-licens.</span><span class="sxs-lookup"><span data-stu-id="537f9-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="537f9-117">Om du redan har en befintlig Office 365- eller Azure Active Directory-prenumeration kan du hoppa över stegen för att skapa utvärderingsversionen av Office 365 E5-utvärderingsversionen av klientversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av</span><span class="sxs-lookup"><span data-stu-id="537f9-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

<span data-ttu-id="537f9-118">I den här fasen guidas du till:</span><span class="sxs-lookup"><span data-stu-id="537f9-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="537f9-119">Skapa en office 365 E5-utvärderingsklient</span><span class="sxs-lookup"><span data-stu-id="537f9-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="537f9-120">Aktivera testprenumeration för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="537f9-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="537f9-121">Skapa en office 365 E5-utvärderingsklient</span><span class="sxs-lookup"><span data-stu-id="537f9-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="537f9-122">Om du redan har en befintlig Office 365- eller Azure Active Directory-prenumeration kan du hoppa över stegen för att skapa utvärderingsversionen av Office 365 E5-utvärderingsversionen av klientversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av</span><span class="sxs-lookup"><span data-stu-id="537f9-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="537f9-123">Gå till [produktportalen för Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) och välj **Kostnadsfri utvärderingsversion**.</span><span class="sxs-lookup"><span data-stu-id="537f9-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="537f9-124">![Bild of_page](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-124">![Image of_page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="537f9-125">Slutför provregistreringen genom att ange din e-postadress (personlig eller företagsadress).</span><span class="sxs-lookup"><span data-stu-id="537f9-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="537f9-126">Klicka på **Konfigurera konto**.</span><span class="sxs-lookup"><span data-stu-id="537f9-126">Click **Set up account**.</span></span>
<span data-ttu-id="537f9-127">![Bild of_page](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-127">![Image of_page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="537f9-128">Fyll i förnamn, efternamn, företagstelefonnummer, företagsnamn, företagsstorlek och land eller region.</span><span class="sxs-lookup"><span data-stu-id="537f9-128">Fill in your first name, last name, business phone number, company name, company size and country or region.</span></span>  
<br>![Bild of_page](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="537f9-130">Det land eller den region som du anger här avgör vilken datacenterregion ditt Office 365 ska vara värd för.</span><span class="sxs-lookup"><span data-stu-id="537f9-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="537f9-131">Välj din verifieringsinställning: via ett sms eller samtal.</span><span class="sxs-lookup"><span data-stu-id="537f9-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="537f9-132">Klicka på **Skicka verifieringskod**.</span><span class="sxs-lookup"><span data-stu-id="537f9-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="537f9-133">![Bild of_page](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-133">![Image of_page](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="537f9-134">Ange det anpassade domännamnet för din klient organisation och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="537f9-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="537f9-135">![Bild of_page](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-135">![Image of_page](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="537f9-136">Ställ in den första identiteten som kommer att vara en global administratör för klienten.</span><span class="sxs-lookup"><span data-stu-id="537f9-136">Set up the first identity which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="537f9-137">Fyll i **namn** och **lösenord**.</span><span class="sxs-lookup"><span data-stu-id="537f9-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="537f9-138">Klicka på **Registrera dig**.</span><span class="sxs-lookup"><span data-stu-id="537f9-138">Click **Sign up**.</span></span>
<span data-ttu-id="537f9-139">![Bild of_page](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-139">![Image of_page](../../media/mtp-eval-14.png)</span></span> <br>
<span data-ttu-id="537f9-140">C</span><span class="sxs-lookup"><span data-stu-id="537f9-140">c</span></span>
7. <span data-ttu-id="537f9-141">Klicka på **Gå till installationsprogrammet** för att slutföra utvärderingsversionen av Office 365 E5 E5-utvärderingsversionen av klientversionen.</span><span class="sxs-lookup"><span data-stu-id="537f9-141">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="537f9-142">![Bild of_page](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-142">![Image of_page](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="537f9-143">Anslut företagsdomänen till Office 365-klienten.</span><span class="sxs-lookup"><span data-stu-id="537f9-143">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="537f9-144">[Valfritt] Välj **Anslut en domän som du redan äger** och skriv in ditt domännamn.</span><span class="sxs-lookup"><span data-stu-id="537f9-144">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="537f9-145">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="537f9-145">Click **Next**.</span></span>
<br><span data-ttu-id="537f9-146">![Bild of_page](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-146">![Image of_page](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="537f9-147">Du måste lägga till en TXT- eller MX-post för att validera domänägarskapet.</span><span class="sxs-lookup"><span data-stu-id="537f9-147">You will need to add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="537f9-148">När du har lagt till TXT- eller MX-posten i domänen väljer du **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="537f9-148">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="537f9-149">![Bild of_page](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-149">![Image of_page](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="537f9-150">[Valfritt] Skapa fler användarkonton för din klient.</span><span class="sxs-lookup"><span data-stu-id="537f9-150">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="537f9-151">Du kan hoppa över det här steget genom att klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="537f9-151">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="537f9-152">![Bild of_page](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-152">![Image of_page](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="537f9-153">[Valfritt] Ladda ned Office-appar.</span><span class="sxs-lookup"><span data-stu-id="537f9-153">[Optional] Download Office apps.</span></span> <span data-ttu-id="537f9-154">Klicka på **Nästa** om du vill hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="537f9-154">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="537f9-155">![Bild of_page](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-155">![Image of_page](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="537f9-156">[Valfritt] Migrera e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="537f9-156">[Optional] Migrate email messages.</span></span> <span data-ttu-id="537f9-157">Återigen kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="537f9-157">Again, you can skip this step.</span></span>
<br><span data-ttu-id="537f9-158">![Bild of_page](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-158">![Image of_page](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="537f9-159">Välj onlinetjänster.</span><span class="sxs-lookup"><span data-stu-id="537f9-159">Choose online services.</span></span> <span data-ttu-id="537f9-160">Välj **Exchange** och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="537f9-160">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="537f9-161">![Bild of_page](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-161">![Image of_page](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="537f9-162">Lägg till MX-, CNAME- och TXT-poster i domänen.</span><span class="sxs-lookup"><span data-stu-id="537f9-162">Add MX, CNAME and TXT records to your domain.</span></span> <span data-ttu-id="537f9-163">När du är klar väljer du **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="537f9-163">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="537f9-164">![Bild of_page](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-164">![Image of_page](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="537f9-165">Grattis, du har slutfört etableringen av din Office 365-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="537f9-165">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="537f9-166">![Bild of_page](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-166">![Image of_page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="537f9-167">Aktivera testprenumeration för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="537f9-167">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="537f9-168">När du registrerar dig för en utvärderingsversion får du 25 användarlicenser att använda under en månad.</span><span class="sxs-lookup"><span data-stu-id="537f9-168">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="537f9-169">Mer information finns i [Prova eller köp en M365-prenumeration.](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1)</span><span class="sxs-lookup"><span data-stu-id="537f9-169">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="537f9-170">I [Administrationscenter för Microsoft 365](https://admin.microsoft.com/)klickar du på **Fakturering** och navigerar sedan till **Köptjänster**.</span><span class="sxs-lookup"><span data-stu-id="537f9-170">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="537f9-171">Välj **Microsoft 365 E5** och klicka på **Starta kostnadsfri utvärderingsversion**.</span><span class="sxs-lookup"><span data-stu-id="537f9-171">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="537f9-172">![Bild of_page](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-172">![Image of_page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="537f9-173">Välj din verifieringsinställning: via ett sms eller samtal.</span><span class="sxs-lookup"><span data-stu-id="537f9-173">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="537f9-174">När du har bestämt dig anger du telefonnumret, väljer **Sms:a mig** eller **Ring mig** beroende på ditt val.</span><span class="sxs-lookup"><span data-stu-id="537f9-174">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="537f9-175">![Bild of_page](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-175">![Image of_page](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="537f9-176">Ange verifieringskoden och klicka på **Starta din kostnadsfria utvärderingsversion**.</span><span class="sxs-lookup"><span data-stu-id="537f9-176">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="537f9-177">![Bild of_page](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-177">![Image of_page](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="537f9-178">Klicka på **Försök nu** om du vill bekräfta testversionen av Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="537f9-178">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="537f9-179">![Bild of_page](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-179">![Image of_page](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="537f9-180">Gå till **Microsoft 365 Admin Center** > **Användare** > Aktiva**användare**.</span><span class="sxs-lookup"><span data-stu-id="537f9-180">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="537f9-181">Välj ditt användarkonto, välj **Hantera produktlicenser**och byt sedan licensen från Office 365 E5 till **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="537f9-181">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="537f9-182">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="537f9-182">Click **Save**.</span></span>
<span data-ttu-id="537f9-183">![Bild of_page](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-183">![Image of_page](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="537f9-184">Välj det globala administratörskontot igen och klicka sedan på **Hantera användarnamn**.</span><span class="sxs-lookup"><span data-stu-id="537f9-184">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="537f9-185">![Bild of_page](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-185">![Image of_page](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="537f9-186">[Valfritt] Ändra domänen från *onmicrosoft.com* till din egen domän – beroende på vad du valde i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="537f9-186">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="537f9-187">Klicka på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="537f9-187">Click **Save changes**.</span></span>
<br><span data-ttu-id="537f9-188">![Bild of_page](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-188">![Image of_page](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="537f9-189">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="537f9-189">Next step</span></span>
<span data-ttu-id="537f9-190">||| |:-------|:-----|config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="537f9-190">||| |:-------|:-----|config-onboard.png)</span></span> <br><span data-ttu-id="537f9-191">[Fas 3: Konfigurera & ombord](config-mtpeval.md) | Konfigurera varje Microsoft Threat Protection-pelare för testlabbmiljön för Microsoft Threat Protection och dina slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="537f9-191">[Phase 3: Configure & Onboard](config-mtpeval.md) | Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints.</span></span>
