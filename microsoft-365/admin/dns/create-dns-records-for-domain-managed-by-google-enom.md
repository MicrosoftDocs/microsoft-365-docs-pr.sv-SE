---
title: Skapa DNS-poster när din domän hanteras av Google (eNom)
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Lär dig att komma åt eNom och skapa DNS via sidan Google Domains.
ms.openlocfilehash: 8fc13ea2ccc7dfee510ef7abb72f88030d048943
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210664"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a><span data-ttu-id="51fa5-103">Skapa DNS-poster när din domän hanteras av Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="51fa5-103">Create DNS records when your domain is managed by Google (eNom)</span></span>

 <span data-ttu-id="51fa5-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="51fa5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="51fa5-105">För att kunna migrera e-postkonton till Office 365 måste du skapa en DNS-post hos din domänregistrator.</span><span class="sxs-lookup"><span data-stu-id="51fa5-105">To migrate your mail accounts to Office 365, you need to create a DNS record at your domain registrar.</span></span>
  
<span data-ttu-id="51fa5-106">Om du köpte domänen via Google när du registrerade dig för ditt **Google Apps for Work-konto** hanteras dina DNS-poster av Google men registreras hos eNom.</span><span class="sxs-lookup"><span data-stu-id="51fa5-106">If you purchased your domain through Google while signing up for your **Google Apps for Work** account, your DNS records are managed by Google but registered with eNom.</span></span> 
  
<span data-ttu-id="51fa5-107">Du kan komma åt eNom och skapa DNS via sidan Google **Domäner.**</span><span class="sxs-lookup"><span data-stu-id="51fa5-107">You can access eNom, and create DNS, through the Google **Domains** page.</span></span> <span data-ttu-id="51fa5-108">Följ bara anvisningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="51fa5-108">Just follow the steps in this article.</span></span> 
  
## <a name="create-the-dns-record"></a><span data-ttu-id="51fa5-109">Skapa DNS-posten</span><span class="sxs-lookup"><span data-stu-id="51fa5-109">Create the DNS record</span></span>

1. <span data-ttu-id="51fa5-110">På [Google Admin-konsolen](https://www.google.com/work/apps/business)väljer du **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="51fa5-110">At the [Google Admin console](https://www.google.com/work/apps/business), select **Sign In**.</span></span>
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. <span data-ttu-id="51fa5-112">Ange ditt domännamn och välj sedan **Gå**.</span><span class="sxs-lookup"><span data-stu-id="51fa5-112">Enter your domain name, and then select **Go**.</span></span>
    
    ![Google Apps - Konfigurera-1-1-1](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. <span data-ttu-id="51fa5-114">Längst ned på sidan väljer du **Fler kontroller**.</span><span class="sxs-lookup"><span data-stu-id="51fa5-114">At the bottom of the page, select **More controls**.</span></span>
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. <span data-ttu-id="51fa5-116">Välj **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="51fa5-116">Select **Domains**.</span></span>
    
    ![Google Apps - Konfigurera-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. <span data-ttu-id="51fa5-118">På sidan **Domäner** väljer du **Lägg till/ta bort domäner**.</span><span class="sxs-lookup"><span data-stu-id="51fa5-118">On the **Domains** page, select **Add/remove domains**.</span></span>
    
    ![Google Apps - Konfigurera-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. <span data-ttu-id="51fa5-120">Välj **Avancerade DNS-inställningar på**sidan **Domäner** .</span><span class="sxs-lookup"><span data-stu-id="51fa5-120">On the **Domains** page, select **Advanced DNS settings**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="51fa5-121">Om du inte köpte ett domännamn via Google när du registrerade ditt **Google Apps for Work** -konto visas inte **Advanced DNS settings** på sidan **Domains**.</span><span class="sxs-lookup"><span data-stu-id="51fa5-121">If you didn't purchase a domain name through Google while signing up for your **Google Apps for Work** account, you won't have **Advanced DNS settings** on your **Domains** page.</span></span> <span data-ttu-id="51fa5-122">Då måste du i stället gå direkt till domänvärdens webbplats för att komma åt DNS-inställningarna och följa de här anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="51fa5-122">Instead, you must go directly to your domain host's web site to access your DNS settings and to perform this and the following steps.</span></span> <span data-ttu-id="51fa5-123">Mer information finns i [Komma åt domäninställningarna](https://support.google.com/a/answer/54693?hl=en) för G Suite.</span><span class="sxs-lookup"><span data-stu-id="51fa5-123">See [Access your G Suite domain settings](https://support.google.com/a/answer/54693?hl=en) for more information.</span></span> 
  
    ![Google-Apps-eNom-Konfigurera-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. <span data-ttu-id="51fa5-125">På sidan **Avancerade DNS-inställningar** väljer du **Logga in på DNS-konsolen**.</span><span class="sxs-lookup"><span data-stu-id="51fa5-125">On the **Advanced DNS settings** page, select **Sign in to DNS Console**.</span></span> <span data-ttu-id="51fa5-126">Skriv ned **inloggningsnamnet** och **lösenord**sinformationen.</span><span class="sxs-lookup"><span data-stu-id="51fa5-126">Note the **Sign-in name** and **Password** information.</span></span> <span data-ttu-id="51fa5-127">Du behöver det i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="51fa5-127">You'll need it in the next step.</span></span> 
    
    ![Google-Apps-eNom-Konfigurera-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. <span data-ttu-id="51fa5-129">Logga in på Google **Domain Manager** med **inloggningsnamnet** och **lösenordet** fån sidan **Advanced DNS settings**.</span><span class="sxs-lookup"><span data-stu-id="51fa5-129">Log in to the Google **Domain Manager** using the **Sign-in name** and **Password** from the **Advanced DNS settings** page.</span></span> 
    
    ![Google-Apps-eNom-Konfigurera-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. <span data-ttu-id="51fa5-131">Välj **Redigera**i avsnittet **Värdposter** på sidan ***domain_name*** .</span><span class="sxs-lookup"><span data-stu-id="51fa5-131">On the ***domain_name*** page, in the **Host Records** section, select **Edit**.</span></span>
    
    ![Google-Apps-eNom-Konfigurera-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. <span data-ttu-id="51fa5-133">Välj **Lägg till ny**i avsnittet **Värdposter** .</span><span class="sxs-lookup"><span data-stu-id="51fa5-133">In the **Host Records** section, select **Add New**.</span></span>
    
    ![Google-Apps-eNom-Konfigurera-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. <span data-ttu-id="51fa5-135">I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="51fa5-135">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="51fa5-136">**HOST (värd)**</span><span class="sxs-lookup"><span data-stu-id="51fa5-136">**HOST**</span></span>|<span data-ttu-id="51fa5-137">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="51fa5-137">**TXT VALUE**</span></span>|<span data-ttu-id="51fa5-138">**POSTTYP**</span><span class="sxs-lookup"><span data-stu-id="51fa5-138">**RECORD TYPE**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> ||<span data-ttu-id="51fa5-139">TXT</span><span class="sxs-lookup"><span data-stu-id="51fa5-139">TXT</span></span>  <br/> |

    > [!NOTE]
    > <span data-ttu-id="51fa5-140">Detta är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="51fa5-140">This is an example.</span></span> <span data-ttu-id="51fa5-141">Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="51fa5-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> 
  
    [<span data-ttu-id="51fa5-142">Hur hittar jag det här?</span><span class="sxs-lookup"><span data-stu-id="51fa5-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
  
12. <span data-ttu-id="51fa5-143">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="51fa5-143">Select **Save**.</span></span>
    
    ![Google-Apps-eNom-Configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. <span data-ttu-id="51fa5-145">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="51fa5-145">Select **Save Changes**.</span></span>
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  <span data-ttu-id="51fa5-p105">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="51fa5-p105">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
