---
title: Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Lär dig mer om hur du aktiverar Microsoft 365 att skydda lokala AD ansluten Windows 10 enheter.
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982659"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="e0c4e-103">Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="e0c4e-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="e0c4e-p101">Om organisationen använder Windows Server Active Directory på lokaler, kan du ställa in Microsoft 365 Business att skydda din Windows 10-enheter, men fortfarande åtkomst till lokala resurser som kräver autentisering med lokala. Du kan ställa in detta genom att första synkronisera Active Directory med Azure Active Directory, följt av registrera Windows 10 enheter med Azure AD och registrera dem för hantering av mobila enheter med Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="e0c4e-p101">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication. You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="e0c4e-106">Ställ in domänanslutna enheter som ska hanteras av Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="e0c4e-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="e0c4e-p102">Om du vill konfigurera domänanslutna enheter i din organisation att utnyttja möjligheterna hos Azure Active Directory förutom lokal Active Directory kan du implementera **Hybrid Azure AD anslutna enheter**. Dessa är enheter som är ansluten både till lokal Active Directory och Azure Active Directory. Hybrid Azure AD anslutna enheter kan skyddas och hanteras av Microsoft 365 Business...</span><span class="sxs-lookup"><span data-stu-id="e0c4e-p102">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**. These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory. Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business..</span></span> 
  
<span data-ttu-id="e0c4e-110">Följ instruktionerna nedan för att göra Windows 10 enheter Hybrid Azure AD ansluten och hanteras av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="e0c4e-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="e0c4e-111">Om du vill synkronisera dina användare, grupper och kontakter från lokal Active Directory till Azure Active Directory, kör du guiden för Directory-synkroniseringen och Azure Active Directory ansluta som beskrivs i [Konfigurera katalogsynkronisering för Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="e0c4e-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e0c4e-112">Stegen är exakt densamma för Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="e0c4e-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="e0c4e-113">Innan du slutför steg 3 för att aktivera Windows 10 enheter ska vara Hybrid Azure AD ansluten måste du kontrollera att du uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="e0c4e-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>
    
   - <span data-ttu-id="e0c4e-114">Du kör den senaste versionen av Azure AD ansluta.</span><span class="sxs-lookup"><span data-stu-id="e0c4e-114">You are running the latest version of Azure AD connect.</span></span>
    
   - <span data-ttu-id="e0c4e-p103">Azure AD ansluta har synkroniserats datorobjekt för de enheter som du vill ska vara hybrid Azure AD ansluten. Anslut även om datorobjekt tillhör specifika organisationsenheter (OU) och sedan kontrollera dessa organisationsenheter som är inställda för synkronisering i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e0c4e-p103">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined. If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="e0c4e-117">Registrera befintliga domänanslutna Windows 10 enheter hybrid Azure AD-ansluten och registrera dem för hantering av mobila enheter med Intune (Microsoft 365 Business):</span><span class="sxs-lookup"><span data-stu-id="e0c4e-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="e0c4e-p104">Följ steg-för-steg-instruktioner i [hur du konfigurerar hybrid Azure Active Directory anslutna enheter](https://go.microsoft.com/fwlink/p/?linkid=872870). Detta kommer att aktivera synkronisering av Active Directory lokaler anslutna datorer som Windows 10 och gör dem redo för moln.</span><span class="sxs-lookup"><span data-stu-id="e0c4e-p104">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870). This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="e0c4e-p105">För att registrera en Windows 10-enhet för hantering av mobila enheter finns i [registrera en Windows 10-enhet med Intune med hjälp av en grupprincip](https://go.microsoft.com/fwlink/p/?linkid=872871) för instruktioner. Du kan ange grupprincip på en lokal dator eller för massåtgärder, du kan skapa den här grupprincipinställningen på din Domänkontrollantservern.</span><span class="sxs-lookup"><span data-stu-id="e0c4e-p105">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions. You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span> 
    

