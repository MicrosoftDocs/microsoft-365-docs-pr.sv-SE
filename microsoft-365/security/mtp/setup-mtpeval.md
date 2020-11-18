---
title: Konfigurera utvärderings labb eller pilot miljö för Microsoft 365 Defender
description: Gå till Microsoft 365 säkerhets Center och konfigurera utvärderings laboratorie miljön för Microsoft 365 Defender
keywords: Utvärderings version av Microsoft Threat Protection – Microsoft Threat Protection pilot-konfiguration
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
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 503b7a6a6b3ad6394293e9f70dbdd336f6bee9dd
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131315"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="9c6f2-104">Konfigurera utvärderings labb miljön för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c6f2-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9c6f2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9c6f2-105">**Applies to:**</span></span>
- <span data-ttu-id="9c6f2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c6f2-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="9c6f2-107">Att skapa en test labb-eller pilot miljö för Microsoft 365 Defender och distribuera det är en process i tre steg:</span><span class="sxs-lookup"><span data-stu-id="9c6f2-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="9c6f2-108">[![Fas 1: förbereda](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="9c6f2-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="9c6f2-109">Fas 1: förbereda</span><span class="sxs-lookup"><span data-stu-id="9c6f2-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |![Fas 2: Konfigurera](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="9c6f2-111">Fas 2: Konfigurera</span><span class="sxs-lookup"><span data-stu-id="9c6f2-111">Phase 2: Set up</span></span> |<span data-ttu-id="9c6f2-112">[![Fas 3: inbyggt](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="9c6f2-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span></span><br/>[<span data-ttu-id="9c6f2-113">Fas 3: inbyggt</span><span class="sxs-lookup"><span data-stu-id="9c6f2-113">Phase 3: Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="9c6f2-114">[![Tillbaka till piloten](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="9c6f2-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="9c6f2-115">Tillbaka till pilot Playbook</span><span class="sxs-lookup"><span data-stu-id="9c6f2-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="9c6f2-116">*Nu är det här!*</span><span class="sxs-lookup"><span data-stu-id="9c6f2-116">*You are here!*</span></span>  | | |


<span data-ttu-id="9c6f2-117">Du befinner dig i fasen inställning.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-117">You're currently in the set up phase.</span></span> <span data-ttu-id="9c6f2-118">Vidta de första stegen för att komma åt Microsoft 365 Security Center och konfigurera sedan utvärderings labbet eller pilot miljön.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="9c6f2-119">Registrera dig för en Office 365-eller Azure Active Directory-prenumeration och generera en *. onmicrosoft.com* -klient organisation som du kan använda för att registrera dig för din Microsoft 365 E5-licens.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="9c6f2-120">Om du redan har en prenumeration på Office 365 eller Azure Active Directory kan du hoppa över Office 365 E5-utvärderings-och pilot klient skapande anvisningar.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="9c6f2-121">I den här fasen vägleds du:</span><span class="sxs-lookup"><span data-stu-id="9c6f2-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="9c6f2-122">Skapa en Office 365 E5-prov klient</span><span class="sxs-lookup"><span data-stu-id="9c6f2-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="9c6f2-123">Aktivera utvärderings prenumeration för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9c6f2-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="9c6f2-124">Skapa en Office 365 E5-prov klient</span><span class="sxs-lookup"><span data-stu-id="9c6f2-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="9c6f2-125">Om du redan har en prenumeration på Office 365 eller Azure Active Directory kan du hoppa över stegen för att skapa ett Office 365 E5-prov.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="9c6f2-126">Gå till [produkt portalen för Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) och välj **gratis prov**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Bild of_Office 365 E5 gratis prov sida](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="9c6f2-128">Slutför utvärderings registreringen genom att ange din e-postadress (privat eller företag).</span><span class="sxs-lookup"><span data-stu-id="9c6f2-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="9c6f2-129">Klicka på **Konfigurera konto**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-129">Click **Set up account**.</span></span>

   ![Bild of_Office 365 E5 prov registrerings sida för utvärderings version](../../media/mtp-eval-10.png)

3. <span data-ttu-id="9c6f2-131">Fyll i ditt förnamn, efter namn, företags telefonnummer, företags namn, företags storlek och land eller region.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Bild of_Office 365 E5 utvärderings versionen av prov registrerings sidan som frågar efter namn, telefon och företagets uppgifter](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="9c6f2-133">Det land eller den region som du anger här bestämmer vilket område i data centret som Office 365 hanteras på.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="9c6f2-134">Välj verifierings inställningar: via SMS eller ett samtal.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="9c6f2-135">Klicka på **Skicka verifierings kod**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-135">Click **Send Verification Code**.</span></span> 

   ![Bild of_Office 365 E5 prov registrerings sida för utvärderings version](../../media/mtp-eval-12.png)

5. <span data-ttu-id="9c6f2-137">Ange det anpassade domän namnet för din klient organisation och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Bild of_Office 365 E5 prov registrerings sidan där du kan konfigurera ditt eget domän namn](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="9c6f2-139">Konfigurera den första identiteten, som är global administratör för klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="9c6f2-140">Fyll i **namn** och **lösen ord**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="9c6f2-141">Klicka på **Registrera dig**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-141">Click **Sign up**.</span></span>

   ![Bild of_Office 365 E5 prov registrerings sidan där du kan ställa in din företags identitet](../../media/mtp-eval-14.png)

7. <span data-ttu-id="9c6f2-143">Klicka på **gå till installations programmet** för att slutföra Office 365 E5-etableringen för utvärderings version.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Bild av Office 365 E5 prov registrerings sidan uppmana dig att klicka på knappen Kör inställningar](../../media/mtp-eval-15.png)

8. <span data-ttu-id="9c6f2-145">Anslut företags domänen till Office 365-klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="9c6f2-146">Skriver Välj **Anslut en domän som du redan äger** och skriv in ditt domän namn.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="9c6f2-147">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-147">Click **Next**.</span></span>

   ![Bild of_Office 365 E5 – installations sida där du bör anpassa inloggnings-och e-post](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="9c6f2-149">Lägga till en TXT-eller MX-post för att verifiera domänens ägarskap.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="9c6f2-150">När du har lagt till TXT-eller MX-posten i domänen väljer du **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Bild of_Office 365 E5-installationsfilen där du bör lägga till en TXT-post för att verifiera din domän](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="9c6f2-152">Skriver Skapa fler användar konton för din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="9c6f2-153">Du kan hoppa över det här steget genom att klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-153">You can skip this step by clicking **Next**.</span></span>

    ![Bild of_Office 365 E5-installationsfilen där du kan lägga till fler användare](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="9c6f2-155">Skriver Ladda ner Office-appar.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="9c6f2-156">Hoppa över det här steget genom att klicka på **Nästa** .</span><span class="sxs-lookup"><span data-stu-id="9c6f2-156">Click **Next** to skip this step.</span></span> 

    ![Bild of_Office 365 E5-sida där du kan installera Office-programmen](../../media/mtp-eval-19.png)

12. <span data-ttu-id="9c6f2-158">Skriver Migrera e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="9c6f2-159">Du kan hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-159">Again, you can skip this step.</span></span>

    ![Bild of_Office 365 E5 där du kan ange om du vill migrera e-postmeddelanden eller inte](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="9c6f2-161">Välj online tjänster.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-161">Choose online services.</span></span> <span data-ttu-id="9c6f2-162">Välj **Exchange** och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-162">Select **Exchange** and click **Next**.</span></span> 

    ![Bild of_Office 365 E5 där du kan välja online tjänster](../../media/mtp-eval-21.png)

14. <span data-ttu-id="9c6f2-164">Lägga till MX-, CNAME-och TXT-poster i din domän.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="9c6f2-165">När du är klar väljer du **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-165">When completed, select **Verify**.</span></span>

    ![Bild of_Office 365 E5 här kan du lägga till dina DNS-poster](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="9c6f2-167">Grattis, du har slutfört etableringen av din Office 365-klient.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Bild of_Office 365 E5-sidan för avslutning av installations programmet](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="9c6f2-169">Aktivera utvärderings prenumeration för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9c6f2-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="9c6f2-170">Om du registrerar dig för en utvärderings version får du 25 användar licenser att använda i en månad.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="9c6f2-171">Mer information finns i [prova eller köpa en M365-prenumeration](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) .</span><span class="sxs-lookup"><span data-stu-id="9c6f2-171">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="9c6f2-172">Från [Microsoft 365 administrations Center](https://admin.microsoft.com/)klickar du på **fakturering** och navigerar sedan till **inköps tjänster**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="9c6f2-173">Välj **Microsoft 365 E5** och klicka på **Starta gratis prov period**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Bild of_Microsoft 365 E5 gratis prov sida](../../media/mtp-eval-24.png)

3. <span data-ttu-id="9c6f2-175">Välj verifierings inställningar: via SMS eller ett samtal.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="9c6f2-176">När du har bestämt dig anger du telefonnumret, väljer **SMS** eller **Ring mig** beroende på ditt val.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Bild of_Microsoft 365 E5 gratis prov sida med förfrågan om kontakt information för att skicka kod som visar att du inte är en robot](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="9c6f2-178">Ange verifierings koden och klicka på **starta din gratis prov period**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Bild of_Microsoft 365 E5 gratis prov sida där du kan fylla i verifierings kod systemet skickade för att bevisa att du inte är en robot](../../media/mtp-eval-26.png)

5. <span data-ttu-id="9c6f2-180">Klicka på **prova nu** för att bekräfta utvärderings versionen av Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Bild of_Microsoft 365 E5 gratis prov sida där du bör stänga knappen prova nu för att starta](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="9c6f2-182">Gå till **administrations centret för Microsoft 365**-  >  **användare**  >  **Active users**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="9c6f2-183">Välj ditt användar konto, Välj **Hantera produkt licenser** och byt sedan licensen från Office 365 E5 till **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="9c6f2-184">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-184">Click **Save**.</span></span>

   ![Bild of_Microsoft 365 administrations Center sida där du kan välja Microsoft 365 E5-licens](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="9c6f2-186">Välj det globala administratörs kontot igen och klicka sedan på **hantera användar namn**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Bild of_Microsoft 365 administrations Center sida där du kan välja konto och sedan hantera användar namn](../../media/mtp-eval-29.png)

8. <span data-ttu-id="9c6f2-188">Skriver Ändra domänen från *onmicrosoft.com* till din egen domän, beroende på vad du valde i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="9c6f2-189">Klicka på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-189">Click **Save changes**.</span></span>

   ![Bild of_Microsoft 365 administrations Center sida där du kan ändra din domäns preferens](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="9c6f2-191">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9c6f2-191">Next step</span></span>
|[<span data-ttu-id="9c6f2-192">Steg 3: Konfigurera & inbyggt</span><span class="sxs-lookup"><span data-stu-id="9c6f2-192">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="9c6f2-193">Konfigurera varje Microsoft 365 Defender-pelare för utvärderings labb eller pilot miljö för Microsoft 365 Defender och få slut punkter.</span><span class="sxs-lookup"><span data-stu-id="9c6f2-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
