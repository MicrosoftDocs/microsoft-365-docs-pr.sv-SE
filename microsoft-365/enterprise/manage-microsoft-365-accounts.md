---
title: Verktyg för att hantera Microsoft 365-användarkonton
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
description: Lär dig mer om vilka verktyg som ska användas och hur du hanterar Microsoft 365-konton.
ms.openlocfilehash: 205c61c0cff896f93069d225c84dc3086ca30eb5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694811"
---
# <a name="tools-to-manage-microsoft-365-user-accounts"></a>Verktyg för att hantera Microsoft 365-användarkonton

Du kan hantera Microsoft 365-användare på flera olika sätt, beroende på konfigurationen. Du kan hantera användare i [administrations centret för Microsoft 365](https://admin.microsoft.com), Windows PowerShell, i AD DS (Active Directory Domain Services) eller i administrations portalen för Azure Active Directory (Azure AD). 

Så fort du köper Microsoft 365 kan administrations centret och Windows PowerShell användas för att hantera konton. När du hanterar moln identiteter har alla i organisationen ett separat användar-ID och lösen ord för Microsoft 365. Om du vill integrera med din lokala infrastruktur och ha användar konton synkroniserade med Microsoft 365 kan du använda Azure AD Connect för att tillhandahålla synkronisering av identiteter och lösen ord för enkel inloggning.
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Planera var och hur du ska hantera dina användar konton

Var och hur du kan hantera dina användar konton beror på vilken identitets modell du vill använda för Microsoft 365. De två övergripande modellerna är Cloud-inloggningsautentisering och federerad verifikation.
  
### <a name="cloud-authentication"></a>Cloud-auktorisering

- Cloud-inloggningsautentisering-skapa och hantera användare i administrations centret för Microsoft 365. Du kan också använda Windows PowerShell eller Azure AD. 
    
- Lösenordsskyddade lösen ord (PHS) med sömlös enkel inloggning-det enklaste sättet att aktivera Active Directory DS-objekt i Azure AD. Med PHS synkroniserar du dina AD DS-objekt med Microsoft 365 och hanterar användarna lokalt. 
    
- Direktautentisering (PTA) med enkel inloggning-tillhandahåller enkel lösen ords verifiering för Azure AD-autentiseringstjänst med en program varu agent som körs på en eller flera lokala servrar för att verifiera användare direkt med AD DS. 
    
### <a name="federated-authentication"></a>Federerad autentisering

- Alternativ för federerade användare – i huvudsak för stora företags organisationer med mer komplexa autentiseringskrav, synkroniseras AD DS-objekt med Microsoft 365-och användar konton hanteras lokalt. 
    
- [Tredjeparts-och identitets leverantörer](about-microsoft-365-identity.md) – AD DS-objekt kan synkroniseras med Microsoft 365 och åtkomst till moln resurser hanteras främst av en tredjeparts identitets leverantör (IdP). 
    
## <a name="managing-accounts"></a>Hantera konton

Tänk på följande om du bestämmer vilket sätt din organisation ska skapa och hantera konton:
  
- Programmet för katalog synkronisering måste vara installerat på servrar i den lokala miljön för att du ska kunna ansluta identiteterna mellan Microsoft 365 och din AD DS.
    
- Alla alternativ för Katalogduplicering, inklusive SSO-alternativ, kräver att AD DS-attributen uppfyller standarder. Information om vilka attribut som används i katalogen och vilken rensning (om någon) behövs beskrivs i [förbereda för att tillhandahålla användare via katalog synkronisering till Microsoft 365](prepare-for-directory-synchronization.md). 
    
- Planera hur du ska skapa Microsoft 365-konton.
    
    I följande tabell visas de olika verktygen för konto hantering.
    
|**Alternativ**|**Kommentarer**|
|:-----|:-----|
|Administrations Center  <br/> |[Lägga till användare individuellt eller i bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  Tillhandahåller ett enkelt webb gränssnitt för att lägga till och ändra användar konton.  <br/>  Kan inte användas för att ändra användare om Active Directory-synkronisering är aktiverat (plats och tilldelning av licenser kan ställas in).  <br/>  Kan inte användas med SSO-alternativ.  <br/> |
|Windows PowerShell  <br/> |[Hantera Microsoft 365 med Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  Gör att du kan lägga till användare i gruppanvändare med ett Windows PowerShell-skript.  <br/>  Kan användas för att tilldela platser och licenser till konton, oavsett hur kontona skapas.  <br/> |
|Mass import  <br/> |[Lägga till flera användare samtidigt](add-several-users-at-the-same-time.md) <br/>  Låter dig importera en CSV-fil för att lägga till en grupp användare i Microsoft 365.  <br/>  Kan inte användas med SSO-alternativ.  <br/> |
|Azure AD  <br/> |Du får en gratis version av Azure AD med ditt Microsoft 365-abonnemang. Du kan utföra funktioner som automatisk återställning av lösen ord för moln användare och anpassning av sidorna för inloggnings-och åtkomst panelen genom att använda den kostnads fria versionen. För att få utökade funktioner kan du uppgradera till Basic Edition, Azure AD Premium P1 eller Azure AD Premium P2. Se [Azure AD-utgåvor](https://go.microsoft.com/fwlink/p/?LinkId=698465) för en lista med funktioner som stöds.  <br/> |
|Katalog-synkronisering  <br/> |[Integrera dina lokala identiteter med Azure AD](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  För Active Directory-synkronisering med eller utan Lösenordssynkronisering använder du [Azure AD Connect med Express-inställningar](https://go.microsoft.com/fwlink/p/?LinkID=698537).  <br/>  För flera skogar och SSO-alternativ använder du [anpassad installation av Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).  <br/>  Tillhandahåller den infrastruktur som behövs för att aktivera SSO.  <br/>  Krävs för många hybrid scenarier:  <br/>  Stegvis migrering  <br/>  Hybrid Exchange  <br/>  Synkroniserar grupper av säkerhets-och e-postaktivitet från AD DS.  <br/> |
   
- Oavsett hur du tänker lägga till användar konton i Microsoft 365, måste du hantera flera konto funktioner, till exempel tilldela licenser, ange plats och så vidare. De här funktionerna kan hanteras på lång sikt från administrations centret eller också kan du [skapa användar konton med PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=717083).
    
    Om du väljer att lägga till och hantera alla användare via administrations centret anger du platsen och tilldelar licenser samtidigt som du skapar Microsoft 365-kontot. Därför behövs inte någon planering.
    
    > [!IMPORTANT]
    > Att skapa konton i Microsoft 365 utan att tilldela en licens (till exempel till SharePoint Online) innebär att konto ägaren kan visa Microsoft 365-Center men inte komma åt några av tjänsterna i ditt företags abonnemang. När du har tilldelat en plats och en licens replikeras kontot till den tjänst eller de tjänster som du har tilldelat. Användaren kan logga in på sitt konto och använda de tjänster som du har tilldelat dem. 
  
## <a name="next-steps"></a>Nästa steg

[Microsoft 365-integrering med lokala miljöer](microsoft-365-integration.md)
  
## <a name="see-also"></a>Se även

[Hantera användare och grupper i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users)
  
