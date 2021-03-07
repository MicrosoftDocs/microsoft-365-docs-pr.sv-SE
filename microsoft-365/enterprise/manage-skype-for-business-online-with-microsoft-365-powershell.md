---
title: Hantera Skype för företag – Online med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Använd PowerShell för Microsoft 365 om du vill hantera principer för Skype för företag – Online, principer för användare och mötesinställningar.
ms.openlocfilehash: 1992edfb6d1c141c7ed4db22064960873b768865
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2021
ms.locfileid: "50514962"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="c719d-103">Hantera Skype för företag – Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="c719d-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="c719d-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c719d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c719d-105">Administratörer av Skype för företag – Online ansvarar för hantering av principer.</span><span class="sxs-lookup"><span data-stu-id="c719d-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="c719d-106">Även om du kan utföra vissa av de här uppgifterna i administrationscentret för Microsoft 365, kan andra uppgifter vara enklare i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c719d-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="c719d-107">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="c719d-107">Before you start</span></span>

  > [!Note]
   > <span data-ttu-id="c719d-108">Skype för företag – Online-Connector är för närvarande en del av den senaste versionen av Teams PowerShell-modul.</span><span class="sxs-lookup"><span data-stu-id="c719d-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="c719d-109">Om du använder den senaste versionen av Teams PowerShell, behöver du inte installera Skype för företag – Online-Connector.</span><span class="sxs-lookup"><span data-stu-id="c719d-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
<span data-ttu-id="c719d-110">Installera [Teams PowerShell-modul](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="c719d-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>


## <a name="connect-using-admin-credentials"></a><span data-ttu-id="c719d-111">Anslut med administratörsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="c719d-111">Connect using admin credentials</span></span>

1. <span data-ttu-id="c719d-112">Öppna en Windows PowerShell kommandotolk och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="c719d-112">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. <span data-ttu-id="c719d-113">I dialogrutan **Begäran om autentiseringsuppgifter för Windows PowerShell** anger du användarnamnet och lösenordet för ditt administratörskonto och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="c719d-113">In the **Windows PowerShell Credential Request** dialog box, type your administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="c719d-114">Ansluta med ett administratörskonto med multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="c719d-114">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="c719d-115">Öppna en Windows PowerShell kommandotolk och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="c719d-115">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. <span data-ttu-id="c719d-116">Skriv användarnamnet för ditt administratörskonto för Skype för företag – Online när du uppmanas.</span><span class="sxs-lookup"><span data-stu-id="c719d-116">When prompted enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="c719d-117">I dialogrutan **Logga in på ditt konto** skriver du ditt lösenordet för ditt administratörskonto för Skype för företag – Online och välj sedan **logga in**.</span><span class="sxs-lookup"><span data-stu-id="c719d-117">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="c719d-118">I dialogrutan **Logga in på ditt konto** följ anvisningarna för att lägga till autentiseringsinformation, till exempel en verifieringskod, och välj sedan **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="c719d-118">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="c719d-119">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="c719d-119">For more information, see:</span></span>
  
- [<span data-ttu-id="c719d-120">Hantera Skype för företag – Onlineprinciper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="c719d-120">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="c719d-121">Tilldela per användare Skype för företag – Onlineprinciper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="c719d-121">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="c719d-122">Se även</span><span class="sxs-lookup"><span data-stu-id="c719d-122">See also</span></span>

[<span data-ttu-id="c719d-123">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="c719d-123">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c719d-124">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c719d-124">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="c719d-125">PowerShell cmdlet-referenser för Skype för företag</span><span class="sxs-lookup"><span data-stu-id="c719d-125">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
