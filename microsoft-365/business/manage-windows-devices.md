---
title: Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business
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
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Läs om hur du aktiverar Microsoft 365 för att skydda lokala AD-anslutna Windows 10-enheter.
ms.openlocfilehash: 5cce4bc53f118560e31ad7e6048e4efcb49d662e
ms.sourcegitcommit: c0f769244d05ad019ea2307c38d5543d7b1e5afd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2019
ms.locfileid: "36992238"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="344bb-103">Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="344bb-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="344bb-104">Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.</span><span class="sxs-lookup"><span data-stu-id="344bb-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="344bb-105">Du kan ställa in detta genom att först synkronisera Active Directory med Azure Active Directory, följt av att registrera Windows 10-enheter med Azure AD och registrerar dem för hantering av mobila enheter av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="344bb-105">You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
<span data-ttu-id="344bb-106">I följande video beskrivs stegen för hur du ställer in detta för det vanligaste scenariot.</span><span class="sxs-lookup"><span data-stu-id="344bb-106">The following video details the steps for how to set this up for the most common scenario.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="344bb-107">Konfigurera domänanslutna enheter som ska hanteras av Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="344bb-107">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="344bb-108">Om du vill ställa in organisationens domänanslutna enheter att dra nytta av de funktioner som tillhandahålls av Azure Active Directory förutom lokal Active Directory, kan du implementera **hybrid Azure AD-anslutna enheter**.</span><span class="sxs-lookup"><span data-stu-id="344bb-108">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="344bb-109">Dessa är enheter som är anslutna både till din lokala Active Directory och Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="344bb-109">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span> <span data-ttu-id="344bb-110">Hybrid Azure AD-anslutna enheter kan skyddas och hanteras av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="344bb-110">Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business.</span></span> 
  
<span data-ttu-id="344bb-111">Slutför stegen nedan för att göra dina Windows 10-enheter hybrid Azure AD ansluten och hanteras av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="344bb-111">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="344bb-112">Om du vill synkronisera dina användare, grupper och kontakter från lokala Active Directory till Azure Active Directory, kör guiden katalogsynkronisering och Azure Active Directory Connect enligt beskrivningen i [Konfigurera katalogsynkronisering för Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="344bb-112">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="344bb-113">Stegen är exakt desamma för Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="344bb-113">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="344bb-114">Innan du Slutför steg 3 för att aktivera Windows 10-enheter som ska vara hybrid Azure AD-anslutna, måste du kontrollera att du uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="344bb-114">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="344bb-115">Du kör den senaste versionen av Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="344bb-115">You are running the latest version of Azure AD connect.</span></span>

   - <span data-ttu-id="344bb-116">Azure AD Connect har synkroniserat alla datorobjekten för de enheter som du vill ska vara hybrid Azure AD ansluten.</span><span class="sxs-lookup"><span data-stu-id="344bb-116">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="344bb-117">Om datorobjekten tillhör specifika organisationsenheter (OU), kontrollera att dessa organisationsenheter har angetts för synkronisering i Azure AD Connect samt.</span><span class="sxs-lookup"><span data-stu-id="344bb-117">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="344bb-118">Registrera befintliga domänanslutna Windows 10-enheter som ska vara hybrid Azure AD-anslutna och registrera dem för hantering av mobila enheter av Intune (Microsoft 365 Business):</span><span class="sxs-lookup"><span data-stu-id="344bb-118">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="344bb-119">Följ anvisningarna steg för steg i [så här konfigurerar du hybrid Azure Active Directory-anslutna enheter](https://go.microsoft.com/fwlink/p/?linkid=872870).</span><span class="sxs-lookup"><span data-stu-id="344bb-119">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870).</span></span> <span data-ttu-id="344bb-120">Detta gör att synkroniseringen av din lokala Active Directory-anslutna Windows 10-datorer och göra dem molnanpassade.</span><span class="sxs-lookup"><span data-stu-id="344bb-120">This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="344bb-121">För att registrera en Windows 10-enhet för hantering av mobila enheter, se [Registrera en Windows 10-enhet med Intune med hjälp av en grupprincip](https://go.microsoft.com/fwlink/p/?linkid=872871) för instruktioner.</span><span class="sxs-lookup"><span data-stu-id="344bb-121">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions.</span></span> <span data-ttu-id="344bb-122">Du kan ange grupprincipen på en lokal datornivå eller för massåtgärder, du kan skapa den här grupprincipinställningen på domänkontrollantens Server.</span><span class="sxs-lookup"><span data-stu-id="344bb-122">You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span>