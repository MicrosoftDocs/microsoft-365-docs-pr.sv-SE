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
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26982659"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business

Om organisationen använder Windows Server Active Directory på lokaler, kan du ställa in Microsoft 365 Business att skydda din Windows 10-enheter, men fortfarande åtkomst till lokala resurser som kräver autentisering med lokala. Du kan ställa in detta genom att första synkronisera Active Directory med Azure Active Directory, följt av registrera Windows 10 enheter med Azure AD och registrera dem för hantering av mobila enheter med Microsoft 365 Business.
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Ställ in domänanslutna enheter som ska hanteras av Microsoft 365 Business

Om du vill konfigurera domänanslutna enheter i din organisation att utnyttja möjligheterna hos Azure Active Directory förutom lokal Active Directory kan du implementera **Hybrid Azure AD anslutna enheter**. Dessa är enheter som är ansluten både till lokal Active Directory och Azure Active Directory. Hybrid Azure AD anslutna enheter kan skyddas och hanteras av Microsoft 365 Business... 
  
Följ instruktionerna nedan för att göra Windows 10 enheter Hybrid Azure AD ansluten och hanteras av Microsoft 365 Business.
  
1. Om du vill synkronisera dina användare, grupper och kontakter från lokal Active Directory till Azure Active Directory, kör du guiden för Directory-synkroniseringen och Azure Active Directory ansluta som beskrivs i [Konfigurera katalogsynkronisering för Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
    > [!NOTE]
    > Stegen är exakt densamma för Microsoft 365 Business. 
  
2. Innan du slutför steg 3 för att aktivera Windows 10 enheter ska vara Hybrid Azure AD ansluten måste du kontrollera att du uppfyller följande krav:
    
   - Du kör den senaste versionen av Azure AD ansluta.
    
   - Azure AD ansluta har synkroniserats datorobjekt för de enheter som du vill ska vara hybrid Azure AD ansluten. Anslut även om datorobjekt tillhör specifika organisationsenheter (OU) och sedan kontrollera dessa organisationsenheter som är inställda för synkronisering i Azure AD.
    
3. Registrera befintliga domänanslutna Windows 10 enheter hybrid Azure AD-ansluten och registrera dem för hantering av mobila enheter med Intune (Microsoft 365 Business):
    
4. Följ steg-för-steg-instruktioner i [hur du konfigurerar hybrid Azure Active Directory anslutna enheter](https://go.microsoft.com/fwlink/p/?linkid=872870). Detta kommer att aktivera synkronisering av Active Directory lokaler anslutna datorer som Windows 10 och gör dem redo för moln.
    
5. För att registrera en Windows 10-enhet för hantering av mobila enheter finns i [registrera en Windows 10-enhet med Intune med hjälp av en grupprincip](https://go.microsoft.com/fwlink/p/?linkid=872871) för instruktioner. Du kan ange grupprincip på en lokal dator eller för massåtgärder, du kan skapa den här grupprincipinställningen på din Domänkontrollantservern. 
    

