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
ms.openlocfilehash: d50f35d7d5e81622eb8dfc3bbf8328a8c43e9676
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430040"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="b9952-103">Hantera Skype för företag – Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9952-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="b9952-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b9952-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b9952-105">Administratörer av Skype för företag – Online ansvarar för hantering av principer.</span><span class="sxs-lookup"><span data-stu-id="b9952-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="b9952-106">Även om du kan utföra vissa av de här uppgifterna i administrationscentret för Microsoft 365, kan andra uppgifter vara enklare i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9952-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="b9952-107">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="b9952-107">Before you start</span></span>

<span data-ttu-id="b9952-108">Ladda ned och installera [ Windows PowerShellmodulen för Skype för företag – Online](https://www.microsoft.com/download/details.aspx?id=39366)och starta om datorn.</span><span class="sxs-lookup"><span data-stu-id="b9952-108">Download and install the [Skype for Business Online Windows PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer.</span></span>


## <a name="connect-using-skype-for-business-online-admin-credentials"></a><span data-ttu-id="b9952-109">Ansluta med inloggningsuppgifter för Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="b9952-109">Connect using Skype for Business Online admin credentials</span></span>

1. <span data-ttu-id="b9952-110">Öppna en Windows PowerShell kommandotolk och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="b9952-110">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="b9952-111">I dialogrutan **Begäran om autentiseringsuppgifter för Windows PowerShell** anger du användarnamnet och lösenordet för ditt administratörskonto för Skype för företag – Online och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9952-111">In the **Windows PowerShell Credential Request** dialog box, type your Skype for Business Online administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="b9952-112">Ansluta med ett administratörskonto med multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="b9952-112">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="b9952-113">Öppna en Windows PowerShell kommandotolk och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="b9952-113">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="b9952-114">Skriv användarnamnet för ditt administratörskonto för Skype för företag – Online när du uppmanas av kommandot **New-CsOnlineSession**.</span><span class="sxs-lookup"><span data-stu-id="b9952-114">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="b9952-115">I dialogrutan **Logga in på ditt konto** skriver du ditt lösenordet för ditt administratörskonto för Skype för företag – Online och välj sedan **logga in**.</span><span class="sxs-lookup"><span data-stu-id="b9952-115">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="b9952-116">I dialogrutan **Logga in på ditt konto** följ anvisningarna för att lägga till autentiseringsinformation, till exempel en verifieringskod, och välj sedan **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="b9952-116">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="b9952-117">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="b9952-117">For more information, see:</span></span>
  
- [<span data-ttu-id="b9952-118">Hantera Skype för företag – Onlineprinciper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9952-118">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="b9952-119">Tilldela per användare Skype för företag – Onlineprinciper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9952-119">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="b9952-120">Se även</span><span class="sxs-lookup"><span data-stu-id="b9952-120">See also</span></span>

[<span data-ttu-id="b9952-121">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9952-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b9952-122">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b9952-122">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="b9952-123">PowerShell cmdlet-referenser för Skype för företag</span><span class="sxs-lookup"><span data-stu-id="b9952-123">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
