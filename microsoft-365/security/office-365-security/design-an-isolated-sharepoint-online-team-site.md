---
title: Utforma en isolerad SharePoint Online-gruppwebbplats
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 'Sammanfattning: Steg genom designprocessen för isolerade SharePoint Online-gruppwebbplatser.'
ms.openlocfilehash: 5efd5fb0501d88fda37f1530ef62e4c5110e4da2
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638518"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Utforma en isolerad SharePoint Online-gruppwebbplats

 **Sammanfattning:** Stega igenom designprocessen för isolerade SharePoint Online-gruppwebbplatser.
  
Den här artikeln tar dig igenom de viktiga designbeslut du måste fatta innan du skapar en isolerad SharePoint Online-gruppwebbplats.
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Fas 1: Bestäm dina SharePoint-grupper och behörighetsnivåer

Varje SharePoint Online-gruppwebbplats skapas som standard med följande SharePoint-grupper:
  
- \<webbplatsnamn> medlemmar
    
- \<webbplatsnamn> besökare
    
- \<webbplatsnamn> ägare
    
Dessa grupper är separata från Microsoft 365- och Azure Active Directory-grupper (AD) och ligger till grund för tilldelning av behörigheter för resurserna på webbplatsen.
  
Den uppsättning specifika behörigheter som avgör vad en medlem i en SharePoint-grupp kan göra på en webbplats är en behörighetsnivå. Det finns tre behörighetsnivåer som standard för en SharePoint Online-gruppwebbplats: Redigera, Läsa och Fullständig kontroll. I följande tabell visas standardkorrelationen för SharePoint-grupper och tilldelade behörighetsnivåer:
  
|**SharePoint-grupp**|**Behörighetsnivå**|
|:-----|:-----|
|\<webbplatsnamn> medlemmar  <br/> |Redigera  <br/> |
|\<webbplatsnamn> besökare  <br/> |Läsa  <br/> |
|\<webbplatsnamn> ägare  <br/> |Fullständig kontroll  <br/> |
   
 **Bästa praxis:** Du kan skapa ytterligare SharePoint-grupper och behörighetsnivåer. Vi rekommenderar dock att du använder standarddelningsgrupperna och behörighetsnivåerna för din isolerade SharePoint Online-webbplats.
  
Här är standardgrupperna och behörighetsnivåerna för SharePoint.
  
![Standardgrupperna och behörighetsnivåerna för en SharePoint Online-webbplats.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Fas 2: Tilldela behörigheter till användare med åtkomstgrupper

Du kan tilldela behörigheter till användare genom att lägga till deras användarkonto, eller en Microsoft 365- eller Azure AD-grupp som användarkontot är medlem i, till SharePoint-grupperna. När användarkontona har lagts till tilldelas användarkontona, antingen direkt eller indirekt via medlemskap i en Microsoft 365- eller Azure AD-grupp, behörighetsnivån som är associerad med SharePoint-gruppen.
  
Använda standard-SharePoint-grupper som ett exempel:
  
- Medlemmar i ** \<webbplatsnamnet> Medlemmar** SharePoint-grupp, som kan innehålla både användarkonton och grupper, tilldelas **behörighetsnivån Redigera**
    
- Medlemmar i ** \<webbplatsnamnet> Visitors** SharePoint-grupp, som kan innehålla både användarkonton och grupper, tilldelas **behörighetsnivån Läs**
    
- Medlemmar i ** \<webbplatsnamnet> Ägare** SharePoint-grupp, som kan innehålla både användarkonton och grupper, tilldelas behörighetsnivån **Fullständig kontroll**
    
 **Bästa praxis:** Även om du kan hantera behörigheter via enskilda användarkonton rekommenderar vi att du använder en enda Azure AD-grupp, en så kallad åtkomstgrupp, i stället. Detta förenklar hanteringen av behörigheter via medlemskap i åtkomstgruppen, i stället för att hantera listan över användarkonton för varje SharePoint-grupp.
  
Azure AD-grupper för Microsoft 365 skiljer sig från Microsoft 365-grupper. Azure AD-grupper visas i Microsoft 365-administrationscentret med deras **typ** inställd på **Säkerhet** och har ingen e-postadress. Azure AD-grupper kan hanteras inom:
  
- Active Directory Domain Services (AD DS)
    
    Det här är grupper som har skapats i din lokala AD DS-infrastruktur och synkroniserats med din Microsoft 365-prenumeration. I administrationscentret för Microsoft 365 har dessa grupper **status** **för synkroniserad med active directory**.
    
- Office 365
    
    Det här är grupper som har skapats med hjälp av microsoft 365-administrationscentret, Azure-portalen eller Microsoft PowerShell. I administrationscentret för Microsoft 365 har dessa grupper status **för** **molnet**.
    
 **Bästa praxis:** Om du använder AD DS lokalt och synkroniserar med din Microsoft 365-prenumeration kan du utföra din användar- och grupphantering med AD DS.
  
För isolerade SharePoint Online-gruppwebbplatser ser den rekommenderade gruppstrukturen ut så här:
  
|**SharePoint-grupp**|**Azure AD-baserad åtkomstgrupp**|**Behörighetsnivå**|
|:-----|:-----|:-----|
|\<webbplatsnamn> medlemmar  <br/> |\<webbplatsnamn> medlemmar  <br/> |Redigera  <br/> |
|\<webbplatsnamn> besökare  <br/> |\<webbplatsnamn> Tittare  <br/> |Läsa  <br/> |
|\<webbplatsnamn> ägare  <br/> |\<webbplatsnamn> administratörer  <br/> |Fullständig kontroll  <br/> |
   
 **Bästa praxis:** Även om du kan använda microsoft 365- eller Azure AD-grupper som medlemmar i SharePoint-grupper rekommenderar vi att du använder Azure AD-grupper. Azure AD-grupper, som hanteras antingen via AD DS eller Microsoft 365, ger dig större flexibilitet att använda kapslade grupper för att tilldela behörigheter.
  
Här är standard-SharePoint-grupper som konfigurerats för att använda Azure AD-baserade åtkomstgrupper.
  
![Använda åtkomstgrupper som medlemmar i standardwebbplatsgrupper för SharePoint Online.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
När du utformar de tre åtkomstgrupperna bör du tänka på följande:
  
- Det bör bara finnas ett fåtal medlemmar i ** \<webbplatsnamnet> åtkomstgruppen administratörer,** vilket motsvarar ett litet antal SharePoint Online-administratörer som hanterar gruppwebbplatsen.
    
- De flesta av dina webbplatsmedlemmar finns i ** \<webbplatsnamnet> medlemmar** eller ** \<webbplatsnamn> Tittare** åtkomstgrupper. Eftersom webbplatsmedlemmar i ** \<webbplatsnamnet> medlemmars** åtkomstgrupp har möjlighet att ta bort eller ändra resurser på webbplatsen bör du noga överväga medlemskapet. När du är osäker lägger du till webbplatsmedlemmen i ** \<webbplatsnamnet>** tittaråtkomstgruppen.
    
Här är ett exempel på SharePoint-grupper och åtkomstgrupper för en isolerad webbplats med namnet ProjectX.
  
![Ett exempel på hur du använder åtkomstgrupper för en SharePoint Online-webbplats med namnet ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a>Fas 3: Använd kapslade Azure AD-grupper

För ett projekt som är begränsat till ett litet antal personer passar en enda nivå av Azure AD-baserade åtkomstgrupper som läggs till i SharePoint-grupperna på webbplatsen de flesta scenarier. Men om du har ett stort antal personer och dessa personer redan är medlemmar i etablerade Azure AD-grupper kan du enklare tilldela SharePoint-behörigheter med hjälp av kapslade grupper eller grupper som innehåller andra grupper som medlemmar.
  
Du vill till exempel skapa en isolerad SharePoint-onlinegruppwebbplats för samarbete mellan cheferna för försäljnings-, marknadsförings-, teknik-, juridiska och supportavdelningar och de avdelningar som redan är deras egna grupper med ett antal företagsprofiler. I stället för att skapa en ny grupp för de nya webbplatsmedlemmarna och placera alla enskilda verkställande användarkonton i den, placera de befintliga ledningsgrupperna för varje avdelning i den nya gruppen.
  
 Om du delar en Microsoft 365-prenumeration mellan flera organisationer kan det bli svårt att hantera en enda gruppmedlemskap för en isolerad webbplats för en organisation på grund av det stora antalet användarkonton. I det här fallet kan du använda kapslade Azure AD-grupper för varje organisation som innehåller grupperna inom deras organisationer för att hantera behörigheterna.
  
Så här använder du kapslade Azure AD-grupper:
  
1. Identifiera eller skapa Azure AD-grupper som ska innehålla användarkonton och lägga till lämpliga användarkonton som medlemmar.
    
2. Skapa behållaren Azure AD-baserad åtkomstgrupp som ska innehålla de andra Azure AD-grupperna och lägga till dessa grupper som medlemmar.
    
3.  Om du vill ha rätt åtkomstnivå för behållaråtkomstgruppen identifierar du SharePoint-gruppen och motsvarande behörighetsnivå.
    
> [!NOTE]
> Du kan inte använda kapslade Microsoft 365-grupper. 
  
Här är ett exempel på kapslade Azure AD-grupper för projectx-medlemsåtkomstgruppen.
  
![Ett exempel på hur du använder kapslade åtkomstgrupper för medlemsåtkomstgruppen för ProjectX-platsen.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
Eftersom alla användarkonton i teamen För forskning, teknik och projekt är avsedda att vara platsmedlemmar är det enklare att lägga till sina Azure AD-grupper i åtkomstgruppen För ProjectX-medlemmar.
  
## <a name="next-step"></a>Nästa steg

När du är redo att skapa och konfigurera en isolerad plats i produktion läser [du Distribuera en isolerad SharePoint Online-gruppwebbplats](deploy-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Se även

[Isolerade SharePoint Online-gruppwebbplatser](isolated-sharepoint-online-team-sites.md)
  
[Hantera en isolerad SharePoint Online-gruppwebbplats](manage-an-isolated-sharepoint-online-team-site.md)

[Distribuera en isolerad SharePoint Online-gruppwebbplats](deploy-an-isolated-sharepoint-online-team-site.md)



