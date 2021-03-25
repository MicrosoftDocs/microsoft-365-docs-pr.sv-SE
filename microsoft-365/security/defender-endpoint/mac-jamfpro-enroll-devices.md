---
title: Registrera Microsoft Defender ATP för macOS-enheter i Jamf Pro
description: Registrera Microsoft Defender ATP för macOS-enheter i Jamf Pro
keywords: microsoft, defender, atp, mac, installation, distribuera, avinstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ef6e387d4e945afb71f1fa6ecef9d78ba2d74a55
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185689"
---
# <a name="enroll-microsoft-defender-for-endpoint-for-macos-devices-into-jamf-pro"></a><span data-ttu-id="96834-104">Registrera Microsoft Defender för Endpoint för macOS-enheter i Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="96834-104">Enroll Microsoft Defender for Endpoint for macOS devices into Jamf Pro</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="96834-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="96834-105">**Applies to:**</span></span>
- [<span data-ttu-id="96834-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="96834-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="96834-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96834-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="96834-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="96834-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="96834-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="96834-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a><span data-ttu-id="96834-110">Registrera macOS-enheter</span><span class="sxs-lookup"><span data-stu-id="96834-110">Enroll macOS devices</span></span>

<span data-ttu-id="96834-111">Det finns flera sätt att registrera sig till JamF.</span><span class="sxs-lookup"><span data-stu-id="96834-111">There are multiple methods of getting enrolled to JamF.</span></span>

<span data-ttu-id="96834-112">I den här artikeln får du vägledning om två metoder:</span><span class="sxs-lookup"><span data-stu-id="96834-112">This article will guide you on two methods:</span></span>

- [<span data-ttu-id="96834-113">Metod 1: Registreringsinbjudningar</span><span class="sxs-lookup"><span data-stu-id="96834-113">Method 1:  Enrollment Invitations</span></span>](#enrollment-method-1-enrollment-invitations)
- [<span data-ttu-id="96834-114">Metod 2: Prestage-registrering</span><span class="sxs-lookup"><span data-stu-id="96834-114">Method 2:  Prestage Enrollments</span></span>](#enrollment-method-2-prestage-enrollments)

<span data-ttu-id="96834-115">En fullständig lista finns i [Om datorregistrering.](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)</span><span class="sxs-lookup"><span data-stu-id="96834-115">For a complete list, see [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).</span></span>


## <a name="enrollment-method-1-enrollment-invitations"></a><span data-ttu-id="96834-116">Registreringsmetod 1: Registreringsinbjudningar</span><span class="sxs-lookup"><span data-stu-id="96834-116">Enrollment Method 1: Enrollment Invitations</span></span>

1. <span data-ttu-id="96834-117">Gå till Registreringsinbjudningar på **instrumentpanelen** Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="96834-117">In the Jamf Pro dashboard, navigate to **Enrollment invitations**.</span></span>

    ![Bild av konfigurationsinställningar1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. <span data-ttu-id="96834-119">Välj **+ Ny.**</span><span class="sxs-lookup"><span data-stu-id="96834-119">Select **+ New**.</span></span>

    ![En när bild på en logotypbeskrivning skapas automatiskt](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. <span data-ttu-id="96834-121">I **Ange mottagare för >** under  E-postadresser anger du mottagarnas e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="96834-121">In **Specify Recipients for the Invitation** > under **Email Addresses** enter the e-mail address(es) of the recipients.</span></span>

    ![Bild på konfigurationsinställningar2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![Bild på konfigurationsinställningar3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    <span data-ttu-id="96834-124">Till exempel: janedoe@contoso.com</span><span class="sxs-lookup"><span data-stu-id="96834-124">For example: janedoe@contoso.com</span></span>

    ![Bild på konfigurationsinställningar4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. <span data-ttu-id="96834-126">Konfigurera meddelandet för inbjudan.</span><span class="sxs-lookup"><span data-stu-id="96834-126">Configure the message for the invitation.</span></span>

    ![Bild på konfigurationsinställningar5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![Bild på konfigurationsinställningar6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![Bild på konfigurationsinställningar7](images/3ced5383a6be788486d89d407d042f28.png)

    ![Bild på konfigurationsinställningar8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a><span data-ttu-id="96834-131">Registreringsmetod 2: Prestage-registrering</span><span class="sxs-lookup"><span data-stu-id="96834-131">Enrollment Method 2: Prestage Enrollments</span></span>

1. <span data-ttu-id="96834-132">Gå till **Prestage-registrering** i instrumentpanelen Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="96834-132">In the Jamf Pro dashboard, navigate to **Prestage enrollments**.</span></span>

    ![Bild på konfigurationsinställningar9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. <span data-ttu-id="96834-134">Följ anvisningarna i [Datorns prestage-registrering.](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html)</span><span class="sxs-lookup"><span data-stu-id="96834-134">Follow the instructions in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span></span>

## <a name="enroll-macos-device"></a><span data-ttu-id="96834-135">Registrera macOS-enhet</span><span class="sxs-lookup"><span data-stu-id="96834-135">Enroll macOS device</span></span>

1. <span data-ttu-id="96834-136">Välj **Fortsätt** och installera certifikatutfärdaren i fönstret **Systeminställningar.**</span><span class="sxs-lookup"><span data-stu-id="96834-136">Select **Continue** and install the CA certificate from a **System Preferences** window.</span></span>

    ![Bild på Jamf Pro-registrering1](images/jamfpro-ca-certificate.png)

2. <span data-ttu-id="96834-138">När CA-certifikat har installerats går du tillbaka till webbläsarfönstret **och väljer Fortsätt** och installera MDM-profilen.</span><span class="sxs-lookup"><span data-stu-id="96834-138">Once CA certificate is installed, return to the browser window and select **Continue** and install the MDM profile.</span></span> 

    ![Bild på Jamf Pro-registrering2](images/jamfpro-install-mdm-profile.png)

3. <span data-ttu-id="96834-140">Välj **Tillåt** för hämtningar från JAMF.</span><span class="sxs-lookup"><span data-stu-id="96834-140">Select **Allow** to downloads from JAMF.</span></span>

    ![Bild på Jamf Pro-registrering3](images/jamfpro-download.png)

4. <span data-ttu-id="96834-142">Välj **Fortsätt för** att fortsätta med installationen av MDM-profilen.</span><span class="sxs-lookup"><span data-stu-id="96834-142">Select **Continue** to proceed with the MDM Profile installation.</span></span> 

    ![Bild på Jamf Pro-registrering4](images/jamfpro-install-mdm.png)

5. <span data-ttu-id="96834-144">Välj **Fortsätt** för att installera MDM-profilen.</span><span class="sxs-lookup"><span data-stu-id="96834-144">Select **Continue** to install the MDM Profile.</span></span>

    ![Bild på Jamf Pro-registrering5](images/jamfpro-mdm-unverified.png)

6. <span data-ttu-id="96834-146">Välj **Fortsätt**  för att slutföra konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="96834-146">Select **Continue**  to complete the configuration.</span></span> 

    ![Bild på Jamf Pro-registrering6](images/jamfpro-mdm-profile.png)