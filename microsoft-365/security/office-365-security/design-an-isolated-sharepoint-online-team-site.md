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
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Utforma isolerade SharePoint Online-gruppwebbplatser, inklusive att fastställa behörighetsnivåer, tilldela behörigheter till användare med åtkomstgrupper och kapslade Azure AD-grupper.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0f92a925948dbf6c8c5c1beb6b9c709f508c4b3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165517"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Utforma en isolerad SharePoint Online-gruppwebbplats

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


 **Sammanfattning:** Stega igenom designprocessen för isolerade SharePoint Online-gruppwebbplatser.

Den här artikeln tar dig genom de viktigaste designbesluten du måste fatta innan du skapar en isolerad SharePoint Online-gruppwebbplats.

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Fas 1: Ta reda på dina SharePoint-grupper och behörighetsnivåer

Alla SharePoint Online-gruppwebbplatser skapas som standard med följande SharePoint-grupper:

- \<site name> Medlemmar

- \<site name> Besökare

- \<site name> Ägare

De här grupperna är separata från Microsoft 365- och Azure Active Directory-grupper (AD) och utgör grunden för tilldelning av behörigheter för webbplatsens resurser.

Den uppsättning specifika behörigheter som bestämmer vad en medlem i en SharePoint-grupp kan göra på en webbplats är en behörighetsnivå. Det finns tre behörighetsnivåer som standard för en SharePoint Online-gruppwebbplats: Redigera, Läsa och Fullständig behörighet. I följande tabell visas standardkorrelationen för SharePoint-grupper och tilldelade behörighetsnivåer:

****

|SharePoint-grupp|Behörighetsnivå|
|---|---|
|\<site name> Medlemmar|Redigera|
|\<site name> Besökare|Läsa|
|\<site name> Ägare|Fullständig kontroll|
|

 **Metod bäst:** Du kan skapa ytterligare SharePoint-grupper och behörighetsnivåer. Vi rekommenderar dock att du använder standardgrupperna och behörighetsnivåerna för SharePoint Online-webbplatsen.

Här är standardgrupperna och behörighetsnivåerna i SharePoint.

![SharePoint-standardgrupper och behörighetsnivåer för en SharePoint Online-webbplats.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Steg 2: Tilldela behörigheter till användare med åtkomstgrupper

Du kan tilldela behörigheter till användare genom att lägga till deras användarkonto, eller en Microsoft 365- eller Azure AD-grupp där användarkontot är medlem, till SharePoint-grupperna. När användarkontona har lagts till tilldelas användarkontona, antingen direkt eller indirekt via medlemskap i en Microsoft 365- eller Azure AD-grupp, den behörighetsnivå som är kopplad till SharePoint-gruppen.

Använd SharePoint-standardgrupperna som exempel:

- Medlemmar i **\<site name> SharePoint-gruppen** Medlemmar, som kan innehålla både användarkonton och grupper, tilldelas **behörighetsnivån** Redigera

- Medlemmar i **\<site name> SharePoint-gruppen** Besökare, som kan innehålla både användarkonton och grupper, tilldelas **behörighetsnivån** Läsa

- Medlemmar i **\<site name> SharePoint-gruppen** Ägare, som kan innehålla både användarkonton och grupper, tilldelas **behörighetsnivån Fullständig** behörighet

 **Metod bäst:** Även om du kan hantera behörigheter via enskilda användarkonton rekommenderar vi att du använder en enda Azure AD-grupp, en så kallad åtkomstgrupp, i stället. Det gör det enklare att hantera behörigheter genom medlemskap i åtkomstgruppen, i stället för att hantera listan med användarkonton för varje SharePoint-grupp.

Azure AD-grupper för Microsoft 365 skiljer sig åt mellan Microsoft 365-grupper. Azure AD-grupper visas i administrationscentret för  Microsoft 365 med säkerhetstypen inställd på **säkerhet** och har ingen e-postadress. Azure AD-grupper kan hanteras i:

- Active Directory DS (AD DS)

    Det här är grupper som har skapats i din lokala AD DS infrastruktur och synkroniserats med din Microsoft 365-prenumeration. I administrationscentret för Microsoft 365 har de här grupperna **statusen Synkroniserad** **med Active Directory.**

- Office 365

    Det här är grupper som har skapats med hjälp av antingen Administrationscenter för Microsoft 365, Azure-portalen eller Microsoft PowerShell. I administrationscentret för Microsoft 365 har de här grupperna **molnstatus.** 

 **Metod bäst:** Om du använder AD DS och synkroniserar med Microsoft 365-prenumerationen utför du användar- och grupphanteringen med AD DS.

För isolerade SharePoint Online-gruppwebbplatser ser den rekommenderade gruppstrukturen ut så här:

****

|SharePoint-grupp|Azure AD-baserad åtkomstgrupp|Behörighetsnivå|
|---|---|---|
|\<site name> Medlemmar|\<site name> Medlemmar|Redigera|
|\<site name> Besökare|\<site name> Läsare|Läsa|
|\<site name> Ägare|\<site name> Administratörer|Fullständig kontroll|
|

 **Metod bäst:** Även om du kan använda antingen Microsoft 365 eller Azure AD-grupper som medlemmar i SharePoint-grupper rekommenderar vi att du använder Azure AD-grupper. Azure AD-grupper som hanteras antingen via AD DS eller Microsoft 365 ger dig mer flexibilitet att använda kapslade grupper för att tilldela behörigheter.

Här är de SharePoint-standardgrupper som konfigurerats för att använda Azure AD-baserade åtkomstgrupper.

![Använda åtkomstgrupper som medlemmar i standardwebbplatsgrupper i SharePoint Online.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

När du skapar de tre åtkomstgrupperna bör du tänka på följande:

- Det bör bara finnas ett **\<site name>** fåtal medlemmar i åtkomstgruppen Administratörer, vilket motsvarar ett litet antal SharePoint Online-administratörer som hanterar gruppwebbplatsen.

- De flesta av webbplatsmedlemmarna finns i **\<site name> åtkomstgrupperna Medlemmar** **eller \<site name>** Läsare. Eftersom medlemmar i gruppen **\<site name> Medlemmar har** möjlighet att ta bort eller ändra resurser på webbplatsen ska du noga överväga medlemskapet. Om du är osäker kan du lägga till webbplatsmedlemmen i **\<site name> åtkomstgruppen** Läsare.

Här är ett exempel på SharePoint-grupperna och åtkomstgrupperna för en isolerad webbplats med namnet ProjectX.

![Ett exempel på hur du använder åtkomstgrupper för en SharePoint Online-webbplats med namnet ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a>Fas 3: Använd kapslade Azure AD-grupper

För ett projekt som begränsas till ett litet antal personer kommer en enda nivå av Azure AD-baserade åtkomstgrupper som lagts till i SharePoint-grupperna på webbplatsen att passa de flesta scenarier. Men om du har ett stort antal personer och dessa personer redan är medlemmar i etablerade Azure AD-grupper kan du enklare tilldela SharePoint-behörigheter genom att använda kapslade grupper eller grupper som innehåller andra grupper som medlemmar.

Du vill till exempel skapa en isolerad SharePoint Online-gruppwebbplats för samarbete mellan chefer för sälj-, marknadsförings-, teknik-, juridik- och supportavdelningar och de avdelningarna har redan egna grupper med användarkontomedlemskap i ledningen. I stället för att skapa en ny grupp för de nya webbplatsmedlemmarna och placera alla enskilda chefers användarkonton i den, kan du placera befintliga ledningsgrupper för varje avdelning i den nya gruppen.

 Om du delar en Microsoft 365-prenumeration mellan flera organisationer kan det bli svårt att hantera en enstaka nivå av gruppmedlemskap för en isolerad webbplats i en organisation på grund av det stora antalet användarkonton. I det här fallet kan du använda kapslade Azure AD-grupper för varje organisation som innehåller grupper i sina organisationer för att hantera behörigheterna.

Så här använder du kapslade Azure AD-grupper:

1. Identifiera eller skapa Azure AD-grupperna som kommer att innehålla användarkonton och lägg till lämpliga användarkonton som medlemmar.

2. Skapa den Azure AD-baserade åtkomstgrupp för behållaren som innehåller de andra Azure AD-grupperna och lägg till de grupperna som medlemmar.

3. Identifiera SharePoint-gruppen och motsvarande behörighetsnivå för lämplig åtkomstnivå för behållarens åtkomstgrupp.

> [!NOTE]
> Du kan inte använda kapslade Microsoft 365-grupper.

Här är ett exempel på kapslade Azure AD-grupper för projectX-medlemsåtkomstgruppen.

![Ett exempel på hur du använder kapslade åtkomstgrupper för medlemmars åtkomstgrupp för ProjectX-webbplatsen.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

Eftersom alla användarkonton i grupperna Forskning, Teknik och Project är avsedda att vara webbplatsmedlemmar är det enklare att lägga till deras Azure AD-grupper i åtkomstgruppen För ProjectX-medlemmar.

## <a name="next-step"></a>Nästa steg

När du är redo att skapa och konfigurera en isolerad webbplats i produktionen kan du gå till [Distribuera en isolerad SharePoint Online-gruppwebbplats.](deploy-an-isolated-sharepoint-online-team-site.md)

## <a name="see-also"></a>Se även

[Isolerade SharePoint Online-gruppwebbplatser](isolated-sharepoint-online-team-sites.md)

[Hantera en isolerad SharePoint Online-gruppwebbplats](manage-an-isolated-sharepoint-online-team-site.md)

[Distribuera en isolerad SharePoint Online-gruppwebbplats](deploy-an-isolated-sharepoint-online-team-site.md)
