---
title: Hantera Microsoft 365 användarkonton
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Lär dig hur du Microsoft 365 användarkonton.
ms.openlocfilehash: c0387bf50228e0eeb763b4807b15c8d57e02eeac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909568"
---
# <a name="manage-microsoft-365-user-accounts"></a>Hantera Microsoft 365 användarkonton

Du kan hantera Microsoft 365-postkonton på flera olika sätt, beroende på din konfiguration. Du kan hantera användarkonton i [administrationscentret för Microsoft 365](../admin/add-users/index.yml), [PowerShell,](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)i AD DS (Active Directory Domain Services) eller i administrationsportalen för Azure Active Directory (Azure AD). 

När du köper Microsoft 365 kan Microsoft 365 och PowerShell användas för att hantera konton. När du hanterar molnidentiteter har varje person i organisationen ett separat användarnamn och lösenord. Om du vill integrera med den lokala infrastrukturen och synkronisera användarkonton med Microsoft 365 kan du använda Azure AD Anslut för att tillhandahålla synkronisering av identiteter och lösenord för enkel inloggning (SSO).
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Planera för var och hur du ska hantera användarkonton

Var och hur du kan hantera användarkonton beror på vilken identitetsmodell du vill använda för ditt Microsoft 365. De två övergripande modellerna är enbart moln- och hybridmodeller.
  
### <a name="cloud-only"></a>Endast molnet

Du skapar och hanterar användare i Microsoft 365 administrationscenter. Du kan också använda PowerShell eller administrationscentret för Azure AD. 
    
### <a name="hybrid"></a>Hybrid

Användarkonton synkroniseras med Microsoft 365 ad ds, så du måste använda lokala AD DS-verktyg för att hantera användarkonton. 
    
## <a name="managing-accounts"></a>Hantera konton

När du ska bestämma hur organisationen ska skapa och hantera konton bör du tänka på följande krav:
  
- Katalogsynkroniseringsprogramvaran måste installeras på servrar i den lokala miljön för att ansluta identiteter mellan Microsoft 365 och AD DS.
    
- För alla alternativ för katalogsynkronisering, inklusive SSO-alternativ, krävs att dina AD DS-attribut uppfyller standarder. Närmare information om vilka attribut som används i katalogen och vilken rensning (om någon) som krävs beskrivs i Förbereda katalogsynkronisering [för att Microsoft 365](prepare-for-directory-synchronization.md). 
    
- Planera hur du ska skapa Microsoft 365 konton.
    
I följande tabell visas de olika verktygen för kontohantering.
    
|Verktyg|Kommentar|
|:-----|:-----|
|Administrationscentret för Microsoft 365  <br/> |[Lägga till användare individuellt eller flera samtidigt](../admin/add-users/add-users.md) <br/>  Ett enkelt webbgränssnitt för att lägga till och ändra användarkonton.  <br/>  Kan inte användas för att ändra användare om katalogsynkronisering är aktiverad (plats- och licenstilldelning kan ställas in).  <br/>  Kan inte användas med SSO-alternativ.  <br/> |
|Windows PowerShell  <br/> |[Hantera Microsoft 365 med Windows PowerShell](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  Gör att du kan lägga till användare i grupp med hjälp av Windows PowerShell skript.  <br/>  Kan användas för att tilldela plats och licenser till konton, oavsett hur kontona skapas.  <br/> |
|Massimport  <br/> |[Lägga till flera användare samtidigt](add-several-users-at-the-same-time.md) <br/>  Med det här alternativet kan du importera en CSV-fil och lägga till en grupp användare Microsoft 365.  <br/>  Kan inte användas med SSO-alternativ.  <br/> |
|Azure AD  <br/> |Du får en kostnadsfri utgåva av Azure AD med din Microsoft 365 prenumeration. Med den kostnadsfria utgåvan kan du utföra funktioner som lösenordsåterställning via självbetjäning för användare i molnet och anpassa sidorna för inloggning och åtkomstpanel. För att få förbättrade funktioner kan du uppgradera till Basic-utgåvan, Azure AD Premium P1 eller Azure AD Premium P2. Se [Azure AD-utgåvor](/azure/active-directory/fundamentals/active-directory-whatis) för en lista över funktioner som stöds.  <br/> |
|Katalogsynkronisering:  <br/> |[Integrera lokala identiteter med Azure AD](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  För katalogsynkronisering med eller utan lösenordssynkronisering [använder du Azure AD Anslut med standardinställningar.](/azure/active-directory/hybrid/how-to-connect-install-express)  <br/>  För flera skogar och SSO-alternativ använder [du Anpassad installation av Azure AD Anslut](/azure/active-directory/hybrid/how-to-connect-install-custom).  <br/>  Tillhandahåller den infrastruktur som behövs för att aktivera enkel inloggning.  <br/>  Krävs för många hybridscenarier, till exempel staged migrering och Exchange  <br/>  Synkroniserar säkerhets- och e-postaktiverade grupper från din AD DS.  <br/> |
|||
   
- Oavsett hur du tänker lägga till användarkonton i Microsoft 365 måste du hantera flera kontofunktioner, till exempel tilldela licenser, ange plats osv. De här funktionerna kan hanteras långsiktigt från administrationscentret Microsoft 365 eller så kan du [skapa användarkonton med PowerShell.](./create-user-accounts-with-microsoft-365-powershell.md)
    
    Om du väljer att lägga till och hantera alla dina användare via administrationscentret anger du plats och tilldelar licenser samtidigt som du skapar Microsoft 365 konto. Därför krävs inte särskilt mycket planering.
    
    > [!IMPORTANT]
    > Att skapa konton i Microsoft 365 utan att tilldela en licens (t.ex. till SharePoint Online) innebär att kontoinnehavaren kan visa Microsoft 365-centret men kan inte komma åt några av tjänsterna i företagets prenumeration. När du har tilldelat en plats och licensen replikeras kontot till tjänsten eller tjänsterna som du har tilldelat. Användaren kan logga in på sitt konto och använda de tjänster som du har tilldelat dem. 
  
## <a name="see-also"></a>Se även

[Administrationscentret för Microsoft 365](../admin/add-users/index.yml)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)