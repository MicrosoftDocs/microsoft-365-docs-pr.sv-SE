---
title: Microsoft OneDrive
description: Hur Microsoft Managed Desktop uppsättningar av OneDrive för registrerade enheter
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation, appar, verksamhetsbaserade appar, LOB-appar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 6cd2c993e0ca9d4c456a2914b866b65b59799afa
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233953"
---
# <a name="microsoft-onedrive"></a><span data-ttu-id="4c0d0-104">Microsoft OneDrive</span><span class="sxs-lookup"><span data-stu-id="4c0d0-104">Microsoft OneDrive</span></span>

<span data-ttu-id="4c0d0-105">Microsoft Hanterat skrivbord använder [OneDrive för företag](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) som en molnlagringstjänst för alla Microsoft-enheter som hanteras av Microsoft för att säkerställa att enheterna är så tillståndslösa som möjligt.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-105">Microsoft Managed Desktop uses [OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) as a cloud storage service for all Microsoft Managed Desktop devices to ensure that the devices are as stateless as possible.</span></span> <span data-ttu-id="4c0d0-106">Användaren kan hitta sina filer oavsett vilken enhet de loggar in på.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-106">User will be able to find their files no matter which device they sign into.</span></span> <span data-ttu-id="4c0d0-107">Om du till exempel ersätter en Microsoft Managed Desktop-enhet med en ny synkroniseras filer automatiskt till den nya enheten.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-107">For example, if you replace a Microsoft Managed Desktop device with a new one, files will automatically sync to the new device.</span></span>

<span data-ttu-id="4c0d0-108">Vi konfigurerar automatiskt de här inställningarna som standard på Microsoft-hanterade enheter:</span><span class="sxs-lookup"><span data-stu-id="4c0d0-108">We automatically configure these settings by default on Microsoft Managed Devices:</span></span>

- <span data-ttu-id="4c0d0-109">OneDrive är tyst konfigurerad med användarkontot och loggas automatiskt in (utan interaktion med användaren) på det användarkonto som användes för att logga in i Windows.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-109">OneDrive is silently configured with the user account and automatically signed in (without user interaction) to the user account that was used to sign into Windows.</span></span> <span data-ttu-id="4c0d0-110">Mer information finns i [Tyst konfiguration av användarkonton – OneDrive](https://docs.microsoft.com/onedrive/use-silent-account-configuration)</span><span class="sxs-lookup"><span data-stu-id="4c0d0-110">For more information, see [Silently configure user accounts - OneDrive](https://docs.microsoft.com/onedrive/use-silent-account-configuration)</span></span>

- <span data-ttu-id="4c0d0-111">Funktionen Filer på begäran är aktiverad så att användarna kan komma åt filer från sin molnlagring i OneDrive utan att behöva använda diskutrymmet i onödan.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-111">The Files-On-Demand feature is enabled so that users can access files from their cloud storage in OneDrive without having to use disk space unnecessarily.</span></span> <span data-ttu-id="4c0d0-112">Mer information finns i Spara diskutrymme med Filer på begäran [i OneDrive för Windows 10.](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)</span><span class="sxs-lookup"><span data-stu-id="4c0d0-112">For more information, see [Save disk space with OneDrive Files On-Demand for Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e).</span></span>

- <span data-ttu-id="4c0d0-113">Funktionen Flytta känd mapp aktiveras tyst för att backa upp användarnas data i molnet, vilket ger dem åtkomst till deras filer från valfri enhet.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-113">The Known Folder Move feature is enabled silently to back up users’ data in the cloud, which gives them access to their files from any device.</span></span> <span data-ttu-id="4c0d0-114">Mer information finns i [Back up your Documents, Pictures, and Desktop folders with OneDrive.](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)</span><span class="sxs-lookup"><span data-stu-id="4c0d0-114">For more information, see [Back up your Documents, Pictures, and Desktop folders with OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).</span></span>

- <span data-ttu-id="4c0d0-115">Användare kan inte inaktivera funktionen Flytta känd mapp eller ändra platsen för kända mappar för att säkerställa en enhetlig upplevelse på Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-115">Users cannot disable the Known Folder Move feature or change the location of known folders to ensure a consistent experience across Microsoft Managed Desktop devices.</span></span>

## <a name="user-experience"></a><span data-ttu-id="4c0d0-116">Användarupplevelse</span><span class="sxs-lookup"><span data-stu-id="4c0d0-116">User experience</span></span>

<span data-ttu-id="4c0d0-117">När Microsoft Managed Desktop-användare får en ny enhet får de en första körningsupplevelse genom att ange sina Azure-autentiseringsuppgifter när de konfigurerar enheten.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-117">When Microsoft Managed Desktop users receive a new device, they go through a first-run experience by entering their Azure credentials while setting up the device.</span></span> <span data-ttu-id="4c0d0-118">När den här processen är slutförd kan de komma åt skrivbordet och använda OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-118">After this process is completed, they can access their desktop and have the OneDrive experience.</span></span>

1. <span data-ttu-id="4c0d0-119">Systemet meddelar användarna att OneDrive har konfigurerats och att de automatiskt har loggats in på OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-119">The system tells users that OneDrive has been configured and that they have been automatically signed into OneDrive.</span></span>

:::image type="content" source="media/onedrive-sync.png" alt-text="Avisering om att du synkroniserar OneDrive och du kan redigera filer i OneDrive. klicka här för att visa dina filer":::

2. <span data-ttu-id="4c0d0-121">Systemet meddelar användarna att Den kända mappflyttningen i OneDrive har konfigurerats för dem.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-121">The system tells users that OneDrive Known Folder Move has been configured for them.</span></span>

:::image type="content" source="media/onedrive-folders.png" alt-text="Meddelande om att IT-avdelningen har säkerhetskopierat viktiga mappar. Mapparna säkerhetskopieras nu till OneDrive och är tillgängliga från andra enheter":::

3. <span data-ttu-id="4c0d0-123">För att förhindra att dubbla ikoner på skrivbordet när enheter återställs eller återskapas, tar systemet automatiskt bort Microsoft Edge- och Microsoft Teams-ikoner från OneDrive-synkroniseringen, som visas i den här vyn i Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-123">To prevent duplicate icons on the desktop when devices are being reset or reimaged, the system automatically removes Microsoft Edge and Microsoft Teams icons from the OneDrive sync, as shown in this view in File Explorer.</span></span>

:::image type="content" source="media/onedrive-teams.png" alt-text="Utforskaren med Teams- och Edge-listor med avmarkerade kryssrutor och hovringstext som läser Undantagen från synkronisering.":::


## <a name="onedrive-sync-restrictions"></a><span data-ttu-id="4c0d0-125">Synkroniseringsbegränsningar för OneDrive</span><span class="sxs-lookup"><span data-stu-id="4c0d0-125">OneDrive sync restrictions</span></span>

<span data-ttu-id="4c0d0-126">Om du behöver begränsa OneDrive-synkronisering rekommenderar vi att du styr åtkomsten med en villkorsbaserad åtkomstprincip i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-126">If you need to restrict OneDrive sync, we recommend that you control access with an Azure Active Directory conditional access policy.</span></span> <span data-ttu-id="4c0d0-127">Mer information finns i Aktivera [stöd för villkorsstyrd åtkomst i OneDrive-synkroniseringsprogrammet.](https://docs.microsoft.com/onedrive/enable-conditional-access)</span><span class="sxs-lookup"><span data-stu-id="4c0d0-127">For more information, see [Enable conditional access support in the OneDrive sync app](https://docs.microsoft.com/onedrive/enable-conditional-access).</span></span>

<span data-ttu-id="4c0d0-128">Om du inte kan använda en villkorsbaserad åtkomstprincip för Azure AD i organisationen ska IT-administratören följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="4c0d0-128">If you can't use an Azure AD conditional access policy in your organization, your IT Admin should follow these steps:</span></span>

1. <span data-ttu-id="4c0d0-129">Om du inte redan vet det, slå upp ditt klientorganisations-ID enligt beskrivningen i Hitta [ditt klientorganisations-ID för Microsoft 365.](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)</span><span class="sxs-lookup"><span data-stu-id="4c0d0-129">If you don't already know it, look up your tenant ID, as described in [Find your Microsoft 365 tenant ID](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id).</span></span>
2. <span data-ttu-id="4c0d0-130">Logga in på administrationscentret för OneDrive och välj **sedan Synkronisera** i den vänstra rutan.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-130">Sign in to the OneDrive admin center, and then select **Sync** in the left pane.</span></span> <span data-ttu-id="4c0d0-131">Markera kryssrutan **Tillåt synkronisering endast på datorer med särskilda** domäner och lägg sedan till klientorganisations-ID:t i listan med domäner.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-131">Select the **Allow syncing only on PCs joined to specific domains** check box, and then add the tenant ID to the list of domains.</span></span> <span data-ttu-id="4c0d0-132">Mer information finns i Tillåta [synkronisering endast på datorer som är ansluten till vissa domäner.](https://docs.microsoft.com/onedrive/allow-syncing-only-on-specific-domains)</span><span class="sxs-lookup"><span data-stu-id="4c0d0-132">For more information, see [Allow syncing only on computers joined to specific domains](https://docs.microsoft.com/onedrive/allow-syncing-only-on-specific-domains).</span></span>

> [!NOTE]
> <span data-ttu-id="4c0d0-133">Den här vägledningen gäller endast för klienter i Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-133">This guidance applies only to tenants in Microsoft Managed Desktop.</span></span> <span data-ttu-id="4c0d0-134">Det finns andra inställningar som inte diskuteras i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="4c0d0-134">There are other settings in use that aren't discussed in this article.</span></span>
