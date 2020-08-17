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
description: 'Sammanfattning: Använd PowerShell för Microsoft 365 om du vill hantera principer för Skype för företag – Online, principer för användare och mötesinställningar.'
ms.openlocfilehash: aea78d135a5d7ffbb5d8480c549d0fdee88f7d51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694773"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="9180b-103">Hantera Skype för företag – Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9180b-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="9180b-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9180b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9180b-105">En av de viktigaste aktiviteterna i valfri Skype för företag – Online-administratör är hantering av principer.</span><span class="sxs-lookup"><span data-stu-id="9180b-105">One of the primary tasks of any Skype for Business Online administrator is managing policies.</span></span> <span data-ttu-id="9180b-106">Även om du kan utföra vissa av de här uppgifterna i administrationscentret för Microsoft 365, kan andra uppgifter vara mycket snabbare och enklare i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9180b-106">Although you can accomplish some of these tasks in the Microsoft 365 admin center, other tasks are much quicker and easier in PowerShell.</span></span> 

## <a name="before-you-start"></a><span data-ttu-id="9180b-107">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="9180b-107">Before you start</span></span>

<span data-ttu-id="9180b-108">Ladda ned och installera [ Anslutningsmodulen för Skype för företag – Online](https://www.microsoft.com/download/details.aspx?id=39366)och starta om datorn.</span><span class="sxs-lookup"><span data-stu-id="9180b-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer.</span></span>


## <a name="connect-using-a-skype-for-business-online-administrator-account-name-and-password"></a><span data-ttu-id="9180b-109">Ansluta med namnet och lösenordet för ditt administratörskonto för Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="9180b-109">Connect using a Skype for Business Online administrator account name and password</span></span>

1. <span data-ttu-id="9180b-110">Öppna en Windows PowerShell kommandotolk och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="9180b-110">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="9180b-111">I dialogrutan **Begäran om autentiseringsuppgifter för Windows PowerShell** anger du användarnamnet och lösenordet för ditt administratörskonto för Skype för företag – Online och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9180b-111">In the **Windows PowerShell Credential Request** dialog box, type your Skype for Business Online administrator account name and password, and then click **OK**.</span></span>


## <a name="connect-using-a-skype-for-business-online-administrator-account-with-multi-factor-authentication"></a><span data-ttu-id="9180b-112">Ansluta med ett namnet och lösenordet för ditt administratörskonto för Skype för företag – Online med multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="9180b-112">Connect using a Skype for Business Online administrator account with multi-factor authentication</span></span>

1. <span data-ttu-id="9180b-113">Öppna en Windows PowerShell kommandotolk och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="9180b-113">Open a Windows PowerShell command prompt and run the following commands:</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="9180b-114">Skriv användarnamnet för ditt administratörskonto för Skype för företag – Online när du uppmanas av kommandot **New-CsOnlineSession**.</span><span class="sxs-lookup"><span data-stu-id="9180b-114">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="9180b-115">I dialogrutan **Logga in på ditt konto** skriver du ditt lösenordet för ditt administratörskonto för Skype för företag – Online och klickar sedan på **logga in**.</span><span class="sxs-lookup"><span data-stu-id="9180b-115">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password, and then click **Sign in**.</span></span>

4. <span data-ttu-id="9180b-116">Följ anvisningarna i dialogrutan **Logga in på ditt konto** för att ange ytterligare autentiseringsinformation, till exempel en verifieringskod, och klicka sedan på **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="9180b-116">Follow the instructions in the **Sign in to your account** dialog box to provide additional authentication information, such as a verification code, and then click **Verify**.</span></span>

<span data-ttu-id="9180b-117">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="9180b-117">For more information, see the following topics:</span></span>
  
- [<span data-ttu-id="9180b-118">Hantera Skype för företag – Onlineprinciper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9180b-118">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="9180b-119">Tilldela per användare Skype för företag – Onlineprinciper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9180b-119">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="9180b-120">Se även</span><span class="sxs-lookup"><span data-stu-id="9180b-120">See also</span></span>

[<span data-ttu-id="9180b-121">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9180b-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9180b-122">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9180b-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="9180b-123">PowerShell cmdlet-referenser för Skype för företag</span><span class="sxs-lookup"><span data-stu-id="9180b-123">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)

