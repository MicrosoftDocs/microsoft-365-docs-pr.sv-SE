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
description: Hantera iOS-enheter i Basic Mobility and Security.
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877086"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="1a0d3-103">Skapa ett APN-certifikat för iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="1a0d3-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="1a0d3-104">Skapa ett APNs-certifikat för att hantera iOS-enheter som iPad och iPhone i Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="1a0d3-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="1a0d3-105">Logga in på Microsoft 365 ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="1a0d3-105">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="1a0d3-106">I webbläsaren skriver du  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="1a0d3-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="1a0d3-107">Välj  **Dataförlustskydd**   >  **Enhetshantering och** välj **APNs-certifikat för iOS-enheter.**</span><span class="sxs-lookup"><span data-stu-id="1a0d3-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="1a0d3-108">På sidan Apple Push Notification Certificate Inställningar väljer du **Next**.</span><span class="sxs-lookup"><span data-stu-id="1a0d3-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="1a0d3-109">Välj Ladda ned din CSR-fil och spara begäran om certifikatsignering någonstans på datorn som är så bra att du kommer ihåg den.</span><span class="sxs-lookup"><span data-stu-id="1a0d3-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="1a0d3-110">Välj  **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="1a0d3-110">Select  **Next**.</span></span>

6. <span data-ttu-id="1a0d3-111">På sidan Skapa ett APNs-certifikat:</span><span class="sxs-lookup"><span data-stu-id="1a0d3-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="1a0d3-112">Välj Apple APNS-portalen för att öppna Apple Push Certificates-portalen.</span><span class="sxs-lookup"><span data-stu-id="1a0d3-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>

    2. <span data-ttu-id="1a0d3-113">Logga in med ett Apple-ID.</span><span class="sxs-lookup"><span data-stu-id="1a0d3-113">Sign in with an Apple ID.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="1a0d3-114">Använd ett företags-Apple-ID som är kopplat till ett e-postkonto som kommer att finnas kvar i din organisation även om användaren som hanterar kontot slutar.</span><span class="sxs-lookup"><span data-stu-id="1a0d3-114">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves.</span></span> <span data-ttu-id="1a0d3-115">Spara detta ID eftersom du måste använda samma ID när det är dags att förnya certifikatet.</span><span class="sxs-lookup"><span data-stu-id="1a0d3-115">Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="1a0d3-116">Välj  **Skapa ett** certifikat och godkänn   användningsvillkoren.</span><span class="sxs-lookup"><span data-stu-id="1a0d3-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>

    4. <span data-ttu-id="1a0d3-117">Bläddra till den begäran om certifikatsignering som du laddade ned till datorn Microsoft 365 och välj **Upload**.</span><span class="sxs-lookup"><span data-stu-id="1a0d3-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>

        <span data-ttu-id="1a0d3-118">Ladda ned det APNs-certifikat som skapades av Apple Push Certificate-portalen till din dator.</span><span class="sxs-lookup"><span data-stu-id="1a0d3-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>

       >[!TIP]
       ><span data-ttu-id="1a0d3-119">Om du har problem med att ladda ned certifikatet kan du uppdatera webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="1a0d3-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="1a0d3-120">Gå tillbaka till Microsoft 365 och välj **Nästa för** att komma till sidan   Upload   **APNS-certifikat.**  </span><span class="sxs-lookup"><span data-stu-id="1a0d3-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>

8. <span data-ttu-id="1a0d3-121">Bläddra till det APN-certifikat som du laddade ned från Apple Push Certificates-portalen.</span><span class="sxs-lookup"><span data-stu-id="1a0d3-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="1a0d3-122">Välj  **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="1a0d3-122">Select  **Finish**.</span></span>

<span data-ttu-id="1a0d3-123">Slutför konfigurationen genom att gå tillbaka till Säkerhets- & Säkerhets- och > **Säkerhetsprinciper**   >  **Hantera**   >  **inställningar.**</span><span class="sxs-lookup"><span data-stu-id="1a0d3-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
