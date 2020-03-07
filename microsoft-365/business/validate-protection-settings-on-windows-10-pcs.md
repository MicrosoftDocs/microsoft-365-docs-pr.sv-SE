---
title: Bekräfta programskyddsinställningar på PC-datorer med Windows 10
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Validera Microsoft 365 Business-appskyddsinställningar på Windows 10-enheter och verifiera att användarna inte kan kopiera företagsdata till personliga filer eller appar som inte hanteras.
ms.openlocfilehash: 5b798e0335188543fc308553f71085bcde8b7752
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560849"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="483e2-103">Bekräfta programskyddsinställningar på PC-datorer med Windows 10</span><span class="sxs-lookup"><span data-stu-id="483e2-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="483e2-104">Kontrollera att användarna inte kan kopiera företagsdata till personliga filer på företagets enheter</span><span class="sxs-lookup"><span data-stu-id="483e2-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="483e2-105">När du [ställt in principer för programskydd](protection-settings-for-windows-10-devices.md) kan det ta några timmar innan principen börjar gälla på användarnas enheter.</span><span class="sxs-lookup"><span data-stu-id="483e2-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="483e2-106">Om du har **aktiverat Förhindra** att **användare kopierar företagsdata till personliga filer och tvingar dem att spara arbetsfiler till OneDrive för företag** för företagsägda enheter kan du kontrollera detta på användarens enhet när de har anslutit till Azure AD och loggat in.</span><span class="sxs-lookup"><span data-stu-id="483e2-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="483e2-107">**Kontrollera anslutningsinställningar**</span><span class="sxs-lookup"><span data-stu-id="483e2-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="483e2-p102">När du har loggat in med Microsoft 365 Business-autentiseringsuppgifter och anslutit till Azure AD enligt beskrivningen i [Konfigurera Windows-enheter för Microsoft 365 Business-användare](set-up-windows-devices.md) går du till **Windows-inställningar** \> **Konton** \> **Åtkomst till arbete eller skola**. Välj **Ansluten till \<innehavarnamn\> Azure AD** och välj sedan **Info**.</span><span class="sxs-lookup"><span data-stu-id="483e2-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="483e2-111">På sidan **Hanterat efter** \<\> klientnamn kan du se **anslutningsinformationen** som innehåller en **hanteringsserveradress** som den som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="483e2-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="483e2-113">**Kontrollera att du inte kan klistra in företagsdata i en icke-hanterad app**</span><span class="sxs-lookup"><span data-stu-id="483e2-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="483e2-114">Öppna Outlook 2016 som installerades av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="483e2-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="483e2-115">Öppna ett e-postmeddelande och kopiera visst innehåll från det.</span><span class="sxs-lookup"><span data-stu-id="483e2-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="483e2-116">Öppna Anteckningar och försök att klistra in innehållet där.</span><span class="sxs-lookup"><span data-stu-id="483e2-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="483e2-117">Du får ett felmeddelande om att appen inte kan komma åt innehåll.</span><span class="sxs-lookup"><span data-stu-id="483e2-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="483e2-119">Du kan dock klistra in samma innehåll i Word 2016.</span><span class="sxs-lookup"><span data-stu-id="483e2-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="483e2-120">Kontrollera att användarna inte kan kopiera företagsdata till personliga filer på personliga enheter</span><span class="sxs-lookup"><span data-stu-id="483e2-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="483e2-121">**Kontrollera anslutningsinställningar**</span><span class="sxs-lookup"><span data-stu-id="483e2-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="483e2-122">På din personliga Windows 10-enhet där du är inloggad som lokal användare går du till **Windows-inställningar**och trycker på eller trycker på **Konton** \> **Åtkomst arbete eller skola**.</span><span class="sxs-lookup"><span data-stu-id="483e2-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="483e2-123">Välj **Anslut** under **Åtkomst till arbete eller skola**.</span><span class="sxs-lookup"><span data-stu-id="483e2-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="483e2-124">Ange dina Microsoft 365 Business-autentiseringsuppgifter i dialogrutan **Konfigurera ett arbets- eller skolkonto** \> **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="483e2-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="483e2-125">På sidan **Åtkomst till arbetet eller skolan** väljer du **Arbets- eller skolkonto** och väljer sedan **Info**.</span><span class="sxs-lookup"><span data-stu-id="483e2-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Klicka eller tryck på Info i dialogrutan Arbete eller skolkonto.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="483e2-127">På sidan **Access-arbete eller skola** kan du se **anslutningsinformationen** som innehåller en **hanteringsserveradress** som den som visas i följande bild och innehåller orden *som raderar* och *mam* inuti.</span><span class="sxs-lookup"><span data-stu-id="483e2-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="483e2-129">**Kontrollera att du inte kan klistra in företagsdata i en icke-hanterad app**</span><span class="sxs-lookup"><span data-stu-id="483e2-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="483e2-130">Öppna Outlook 2016 och lägg till ditt Microsoft 365 Business-konto om det behövs, och logga in med dina Microsoft 365 Business-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="483e2-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="483e2-131">Öppna ett e-postmeddelande och kopiera visst innehåll från det.</span><span class="sxs-lookup"><span data-stu-id="483e2-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="483e2-132">Öppna Anteckningar och försök att klistra in innehållet där.</span><span class="sxs-lookup"><span data-stu-id="483e2-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="483e2-133">Du får ett felmeddelande om att Appen inte kan komma åt innehåll.</span><span class="sxs-lookup"><span data-stu-id="483e2-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="483e2-135">Du kan dock klistra in samma innehåll i Word 2016.</span><span class="sxs-lookup"><span data-stu-id="483e2-135">You can, however, paste the same content into Word 2016.</span></span>
    

