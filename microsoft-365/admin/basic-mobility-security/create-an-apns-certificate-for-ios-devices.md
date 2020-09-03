---
title: Skapa ett APN-certifikat för iOS-enheter
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Hantera iOS-enheter i grundläggande mobilitet och säkerhet.
ms.openlocfilehash: 8b41c1c6c891a5d6cb98a6a381c65aa0310a1761
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337137"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="961ce-103">Skapa ett APN-certifikat för iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="961ce-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="961ce-104">Skapa ett APN-certifikat för att hantera iOS-enheter som iPad och iPhone i grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="961ce-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="961ce-105">Logga in på Microsoft 365 med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="961ce-105">Sign in to Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="961ce-106">Skriv i webbläsaren  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="961ce-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>
    
3. <span data-ttu-id="961ce-107">Välj  **Hantera data förlust**   >  **Device management**och välj **APNs-certifikat för iOS-enheter**.</span><span class="sxs-lookup"><span data-stu-id="961ce-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>    

4. <span data-ttu-id="961ce-108">På sidan Inställningar för Apple Push Notification-certifikat väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="961ce-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>
    
5. <span data-ttu-id="961ce-109">Välj Ladda ned din CSR-fil och spara begäran om certifikat signering någonstans på din dator som du kommer ihåg.</span><span class="sxs-lookup"><span data-stu-id="961ce-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="961ce-110">Välj  **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="961ce-110">Select  **Next**.</span></span>
    
6. <span data-ttu-id="961ce-111">På sidan Skapa ett APN-certifikat:</span><span class="sxs-lookup"><span data-stu-id="961ce-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="961ce-112">Välj Apple-APN-portalen för att öppna Apple Push certificates-portalen.</span><span class="sxs-lookup"><span data-stu-id="961ce-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
    
    2. <span data-ttu-id="961ce-113">Logga in med ett Apple-ID.</span><span class="sxs-lookup"><span data-stu-id="961ce-113">Sign in with an Apple ID.</span></span>   

    >[!IMPORTANT]
    ><span data-ttu-id="961ce-114">Använd ett Apple-ID för företag som är kopplat till ett e-postkonto som kommer att fortsätta med din organisation även om den användare som hanterar kontot lämnar.</span><span class="sxs-lookup"><span data-stu-id="961ce-114">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves.</span></span> <span data-ttu-id="961ce-115">Spara detta ID eftersom du måste använda samma ID när det är dags att förnya certifikatet.</span><span class="sxs-lookup"><span data-stu-id="961ce-115">Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="961ce-116">Välj  **skapa ett certifikat**   och godkänn användnings villkoren.</span><span class="sxs-lookup"><span data-stu-id="961ce-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>
    
    4. <span data-ttu-id="961ce-117">Bläddra till den begäran om certifikat signering som du hämtade till datorn från Microsoft 365 och välj **Ladda upp**.</span><span class="sxs-lookup"><span data-stu-id="961ce-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>
    
        <span data-ttu-id="961ce-118">Ladda ned APN-certifikatet som skapades av Apple Push Certificate-portalen till datorn.</span><span class="sxs-lookup"><span data-stu-id="961ce-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>
    
       >[!TIP]
       ><span data-ttu-id="961ce-119">Om du har problem med att ladda ner certifikatet kan du uppdatera webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="961ce-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="961ce-120">Gå tillbaka till Microsoft 365 och välj **Nästa**   för att gå till sidan  **upload Certification**   .</span><span class="sxs-lookup"><span data-stu-id="961ce-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>
    
8. <span data-ttu-id="961ce-121">Bläddra till det APN-certifikat som du laddade ned från Apple Push certificates-portalen.</span><span class="sxs-lookup"><span data-stu-id="961ce-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
9. <span data-ttu-id="961ce-122">Välj  **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="961ce-122">Select  **Finish**.</span></span>
    
<span data-ttu-id="961ce-123">För att slutföra installationen går du tillbaka till säkerhets & Compliance Center > **Security policies**   >  **Device management**   >  **Hantera inställningar**för hantering av säkerhets principer.</span><span class="sxs-lookup"><span data-stu-id="961ce-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
