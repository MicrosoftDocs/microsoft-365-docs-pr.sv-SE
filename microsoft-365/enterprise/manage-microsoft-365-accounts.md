---
title: Hantera Microsoft 365-användarkonton
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
description: Lär dig hur du hanterar Microsoft 365-användarkonton.
ms.openlocfilehash: a7b6d89a0f66605dde168b85d74fcd8e513afc15
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327765"
---
# <a name="manage-microsoft-365-user-accounts"></a>Hantera Microsoft 365-användarkonton

Du kan hantera Microsoft 365-användarkonton på flera olika sätt, beroende på konfigurationen. Du kan hantera användar konton i [administrations centret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/), [POWERSHELL](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), i AD DS (Active Directory Domain Services) eller i administratörs portalen för Azure Active Directory (Azure AD). 

Så fort du köper Microsoft 365 kan administrations centret för Microsoft 365 användas för att hantera konton. När du hanterar moln identiteter har alla i organisationen ett separat användar konto namn och lösen ord. Om du vill integrera med en lokal infrastruktur och ha användar konton synkroniserade med Microsoft 365 kan du använda Azure AD Connect för att tillhandahålla synkronisering av identiteter och lösen ord för enkel inloggning (SSO).
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Planera var och hur du ska hantera dina användar konton

Var och hur du kan hantera dina användar konton beror på vilken identitets modell du vill använda för Microsoft 365. De två övergripande modellerna är endast molnbaserade och hybrid.
  
### <a name="cloud-only"></a>Endast molnet

Du skapar och hanterar användare i administrations centret för Microsoft 365. Du kan också använda PowerShell eller administrations centret för Azure AD. 
    
### <a name="hybrid"></a>Hybrid

Användar konton synkroniseras med Microsoft 365 från AD DS, så du måste använda lokala AD DS-verktyg för att hantera användar konton. 
    
## <a name="managing-accounts"></a>Hantera konton

Tänk på följande om du bestämmer vilket sätt din organisation ska skapa och hantera konton:
  
- Programmet för katalog synkronisering måste vara installerat på servrar i den lokala miljön för att du ska kunna ansluta identiteterna mellan Microsoft 365 och din AD DS.
    
- Alla alternativ för Katalogduplicering, inklusive SSO-alternativ, kräver att AD DS-attributen uppfyller standarder. Information om vilka attribut som används i katalogen och vilken rensning (om en sådan finns) är i avsnittet [förbereda för katalog synkronisering till Microsoft 365](prepare-for-directory-synchronization.md). 
    
- Planera hur du ska skapa Microsoft 365-konton.
    
I följande tabell visas de olika verktygen för konto hantering.
    
|Sysprep|Kommentarer|
|:-----|:-----|
|Administrationscenter för Microsoft 365  <br/> |[Lägga till användare individuellt eller i bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  Tillhandahåller ett enkelt webb gränssnitt för att lägga till och ändra användar konton.  <br/>  Kan inte användas för att ändra användare om Active Directory-synkronisering är aktiverat (plats och tilldelning av licenser kan ställas in).  <br/>  Kan inte användas med SSO-alternativ.  <br/> |
|Windows PowerShell  <br/> |[Hantera Microsoft 365 med Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  Gör att du kan lägga till användare i gruppanvändare med ett Windows PowerShell-skript.  <br/>  Kan användas för att tilldela platser och licenser till konton, oavsett hur kontona skapas.  <br/> |
|Mass import  <br/> |[Lägga till flera användare samtidigt](add-several-users-at-the-same-time.md) <br/>  Låter dig importera en CSV-fil för att lägga till en grupp användare i Microsoft 365.  <br/>  Kan inte användas med SSO-alternativ.  <br/> |
|Azure AD  <br/> |Du får en gratis version av Azure AD med ditt Microsoft 365-abonnemang. Du kan utföra funktioner som automatisk återställning av lösen ord för moln användare och anpassning av sidorna för inloggnings-och åtkomst panelen genom att använda den kostnads fria versionen. För att få utökade funktioner kan du uppgradera till Basic Edition, Azure AD Premium P1 eller Azure AD Premium P2. Se [Azure AD-utgåvor](https://go.microsoft.com/fwlink/p/?LinkId=698465) för en lista med funktioner som stöds.  <br/> |
|Katalogsynkronisering:  <br/> |[Integrera dina lokala identiteter med Azure AD](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  För Active Directory-synkronisering med eller utan Lösenordssynkronisering använder du [Azure AD Connect med Express-inställningar](https://go.microsoft.com/fwlink/p/?LinkID=698537).  <br/>  För flera skogar och SSO-alternativ använder du [anpassad installation av Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).  <br/>  Tillhandahåller den infrastruktur som behövs för att aktivera SSO.  <br/>  Krävs för många hybrid scenarier som stegvis migrering och hybrid Exchange  <br/>  Synkroniserar grupper av säkerhets-och e-postaktivitet från AD DS.  <br/> |
|||
   
- Oavsett hur du tänker lägga till användar konton i Microsoft 365, måste du hantera flera konto funktioner, till exempel tilldela licenser, ange plats och så vidare. De här funktionerna kan hanteras längre från Microsoft 365 Admin Center eller också kan du [skapa användar konton med PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=717083).
    
    Om du väljer att lägga till och hantera alla användare via administrations centret anger du platsen och tilldelar licenser samtidigt som du skapar Microsoft 365-kontot. Därför behövs inte någon planering.
    
    > [!IMPORTANT]
    > Att skapa konton i Microsoft 365 utan att tilldela en licens (till exempel till SharePoint Online) innebär att konto ägaren kan visa Microsoft 365-Center men inte komma åt några av tjänsterna i ditt företags abonnemang. När du har tilldelat en plats och en licens replikeras kontot till den tjänst eller de tjänster som du har tilldelat. Användaren kan logga in på sitt konto och använda de tjänster som du har tilldelat dem. 
  
## <a name="see-also"></a>Se även

[Administrationscenter för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)  
