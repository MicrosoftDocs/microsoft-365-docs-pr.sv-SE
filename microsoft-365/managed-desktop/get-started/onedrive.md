---
title: Microsoft OneDrive
description: Hur Microsoft Hanterat skrivbord uppsättningar OneDrive för registrerade enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation, appar, verksamhetsbaserade appar, verksamhetsbaserade appar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a26500c1671afffc7b70d509a4242914631b937c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904846"
---
# <a name="microsoft-onedrive"></a><span data-ttu-id="c68a1-104">Microsoft OneDrive</span><span class="sxs-lookup"><span data-stu-id="c68a1-104">Microsoft OneDrive</span></span>

<span data-ttu-id="c68a1-105">Microsoft Hanterat skrivbord använder [OneDrive för företag](/onedrive/plan-onedrive-enterprise) som en molnlagringstjänst för alla Microsoft Hanterat skrivbord-enheter för att säkerställa att enheterna är så stateless som möjligt.</span><span class="sxs-lookup"><span data-stu-id="c68a1-105">Microsoft Managed Desktop uses [OneDrive for Business](/onedrive/plan-onedrive-enterprise) as a cloud storage service for all Microsoft Managed Desktop devices to ensure that the devices are as stateless as possible.</span></span> <span data-ttu-id="c68a1-106">Användaren kan hitta sina filer oavsett vilken enhet de loggar in på.</span><span class="sxs-lookup"><span data-stu-id="c68a1-106">User will be able to find their files no matter which device they sign into.</span></span> <span data-ttu-id="c68a1-107">Om du till exempel ersätter en Microsoft Hanterat skrivbord enhet med en ny synkroniseras filer automatiskt till den nya enheten.</span><span class="sxs-lookup"><span data-stu-id="c68a1-107">For example, if you replace a Microsoft Managed Desktop device with a new one, files will automatically sync to the new device.</span></span>

<span data-ttu-id="c68a1-108">Vi konfigurerar automatiskt de här inställningarna som standard på Microsoft Hanterade enheter:</span><span class="sxs-lookup"><span data-stu-id="c68a1-108">We automatically configure these settings by default on Microsoft Managed Devices:</span></span>

- <span data-ttu-id="c68a1-109">OneDrive är tyst konfigurerad med användarkontot och loggas automatiskt in (utan interaktion med användaren) på det användarkonto som användes för att logga in på Windows.</span><span class="sxs-lookup"><span data-stu-id="c68a1-109">OneDrive is silently configured with the user account and automatically signed in (without user interaction) to the user account that was used to sign into Windows.</span></span> <span data-ttu-id="c68a1-110">Mer information finns i [Använda tyst konfiguration av användarkonton – OneDrive](/onedrive/use-silent-account-configuration)</span><span class="sxs-lookup"><span data-stu-id="c68a1-110">For more information, see [Silently configure user accounts - OneDrive](/onedrive/use-silent-account-configuration)</span></span>

- <span data-ttu-id="c68a1-111">Funktionen Filer på begäran är aktiverad så att användarna kan komma åt filer från sin molnlagring i OneDrive utan att behöva använda diskutrymmet i onödan.</span><span class="sxs-lookup"><span data-stu-id="c68a1-111">The Files-On-Demand feature is enabled so that users can access files from their cloud storage in OneDrive without having to use disk space unnecessarily.</span></span> <span data-ttu-id="c68a1-112">Mer information finns i [Spara diskutrymme med OneDrive i Filer](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)på begäran för Windows 10 .</span><span class="sxs-lookup"><span data-stu-id="c68a1-112">For more information, see [Save disk space with OneDrive Files On-Demand for Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e).</span></span>

- <span data-ttu-id="c68a1-113">Funktionen Flytta känd mapp aktiveras utan att du har aktiverat den för att backa upp användarnas data i molnet, vilket ger dem åtkomst till deras filer från valfri enhet.</span><span class="sxs-lookup"><span data-stu-id="c68a1-113">The Known Folder Move feature is enabled silently to back up users’ data in the cloud, which gives them access to their files from any device.</span></span> <span data-ttu-id="c68a1-114">Mer information finns i [Backa upp dina dokument, bilder och skrivbordsmappar med OneDrive.](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)</span><span class="sxs-lookup"><span data-stu-id="c68a1-114">For more information, see [Back up your Documents, Pictures, and Desktop folders with OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).</span></span>

- <span data-ttu-id="c68a1-115">Användare kan inte inaktivera funktionen För känd mappflyttning eller ändra platsen för kända mappar för att säkerställa en enhetlig upplevelse på Microsoft Hanterat skrivbord enheter.</span><span class="sxs-lookup"><span data-stu-id="c68a1-115">Users cannot disable the Known Folder Move feature or change the location of known folders to ensure a consistent experience across Microsoft Managed Desktop devices.</span></span>

## <a name="user-experience"></a><span data-ttu-id="c68a1-116">Användarupplevelse</span><span class="sxs-lookup"><span data-stu-id="c68a1-116">User experience</span></span>

<span data-ttu-id="c68a1-117">När Microsoft Hanterat skrivbord får en ny enhet går de igenom första körningen genom att ange sina Azure-autentiseringsuppgifter när de inställningar för enheten.</span><span class="sxs-lookup"><span data-stu-id="c68a1-117">When Microsoft Managed Desktop users receive a new device, they go through a first-run experience by entering their Azure credentials while setting up the device.</span></span> <span data-ttu-id="c68a1-118">När den här processen är slutförd kan de komma åt sitt skrivbord och ha den OneDrive upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="c68a1-118">After this process is completed, they can access their desktop and have the OneDrive experience.</span></span>

1. <span data-ttu-id="c68a1-119">Systemet meddelar användarna att OneDrive har konfigurerats och att de har loggats in automatiskt i OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c68a1-119">The system tells users that OneDrive has been configured and that they have been automatically signed into OneDrive.</span></span>

:::image type="content" source="media/onedrive-sync.png" alt-text="Avisering om att du nu synkroniserar OneDrive och du kan redigera filer i OneDrive. klicka här för att visa dina filer":::

2. <span data-ttu-id="c68a1-121">Systemet meddelar användarna att OneDrive flytta känd mapp har konfigurerats för dem.</span><span class="sxs-lookup"><span data-stu-id="c68a1-121">The system tells users that OneDrive Known Folder Move has been configured for them.</span></span>

:::image type="content" source="media/onedrive-folders.png" alt-text="Meddelande som läser IT-avdelningen har säkerhetskopierat viktiga mappar. Mapparna säkerhetskopieras nu till enheten OneDrive är tillgängliga från andra enheter":::

3. <span data-ttu-id="c68a1-123">För att undvika att dubbla ikoner på skrivbordet när enheter återställs eller uppdateras tar systemet automatiskt bort Microsoft Edge- och Microsoft Teams-ikoner från OneDrive-synkroniseringen, som visas i den här vyn i Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="c68a1-123">To prevent duplicate icons on the desktop when devices are being reset or reimaged, the system automatically removes Microsoft Edge and Microsoft Teams icons from the OneDrive sync, as shown in this view in File Explorer.</span></span>

:::image type="content" source="media/onedrive-teams.png" alt-text="Utforskaren som visar Teams Och Edge-listor med avmarkerade kryssrutor och uppläsning av hovringstext som är undantagen från synkronisering.":::


## <a name="onedrive-sync-restrictions"></a><span data-ttu-id="c68a1-125">OneDrive för synkronisering</span><span class="sxs-lookup"><span data-stu-id="c68a1-125">OneDrive sync restrictions</span></span>

<span data-ttu-id="c68a1-126">Om du behöver begränsa OneDrive synkronisering rekommenderar vi att du kontrollerar åtkomsten med en Azure Active Directory princip för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="c68a1-126">If you need to restrict OneDrive sync, we recommend that you control access with an Azure Active Directory conditional access policy.</span></span> <span data-ttu-id="c68a1-127">Mer information finns i Aktivera [stöd för villkorsstyrd åtkomst i OneDrive synkroniseringsapp.](/onedrive/enable-conditional-access)</span><span class="sxs-lookup"><span data-stu-id="c68a1-127">For more information, see [Enable conditional access support in the OneDrive sync app](/onedrive/enable-conditional-access).</span></span>

<span data-ttu-id="c68a1-128">Om du inte kan använda en villkorsbaserad åtkomstprincip för Azure AD i organisationen ska DIN IT-administratör följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="c68a1-128">If you can't use an Azure AD conditional access policy in your organization, your IT Admin should follow these steps:</span></span>

1. <span data-ttu-id="c68a1-129">Om du inte redan känner till det letar du upp ditt klientorganisations-ID enligt beskrivningen i [Hitta ditt Microsoft 365 klientorganisations-ID](/onedrive/find-your-office-365-tenant-id).</span><span class="sxs-lookup"><span data-stu-id="c68a1-129">If you don't already know it, look up your tenant ID, as described in [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id).</span></span>
2. <span data-ttu-id="c68a1-130">Logga in på OneDrive och välj sedan **Synkronisera i** det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="c68a1-130">Sign in to the OneDrive admin center, and then select **Sync** in the left pane.</span></span> <span data-ttu-id="c68a1-131">Markera kryssrutan **Tillåt synkronisering endast på datorer som är ansluten** till vissa domäner och lägg sedan till klientorganisations-ID:t i listan över domäner.</span><span class="sxs-lookup"><span data-stu-id="c68a1-131">Select the **Allow syncing only on PCs joined to specific domains** check box, and then add the tenant ID to the list of domains.</span></span> <span data-ttu-id="c68a1-132">Mer information finns i Tillåt [synkronisering endast på datorer som är ansluten till vissa domäner.](/onedrive/allow-syncing-only-on-specific-domains)</span><span class="sxs-lookup"><span data-stu-id="c68a1-132">For more information, see [Allow syncing only on computers joined to specific domains](/onedrive/allow-syncing-only-on-specific-domains).</span></span>

> [!NOTE]
> <span data-ttu-id="c68a1-133">Den här vägledningen gäller endast för klientorganisationen i Microsoft Hanterat skrivbord.</span><span class="sxs-lookup"><span data-stu-id="c68a1-133">This guidance applies only to tenants in Microsoft Managed Desktop.</span></span> <span data-ttu-id="c68a1-134">Det finns andra inställningar som inte tas upp i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="c68a1-134">There are other settings in use that aren't discussed in this article.</span></span>