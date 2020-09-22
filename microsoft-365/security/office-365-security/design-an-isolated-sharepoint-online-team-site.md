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
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Designa isolerade SharePoint Online-gruppwebbplatser, inklusive att ange behörighets nivåer, tilldela behörigheter till användare med åtkomst grupper och kapslade Azure AD-grupper.
ms.openlocfilehash: 035952c1921443d86602eb94e3965acee86ae3e8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203125"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Utforma en isolerad SharePoint Online-gruppwebbplats

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 **Sammanfattning:** Stega genom design processen för isolerade SharePoint Online-gruppwebbplatser.

I den här artikeln får du hjälp med de viktiga design beslut som du måste göra innan du skapar en isolerad SharePoint Online-gruppwebbplats.

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Fas 1: Bestäm dina SharePoint-grupper och behörighets nivåer

Varje SharePoint Online-gruppwebbplats skapas som standard med följande SharePoint-grupper:

- \<site name> Gruppen

- \<site name> Besökare

- \<site name> Nmöjliga

Dessa grupper är åtskilda från Microsoft 365-och Azure Active Directory (AD)-grupper och är grunden för hur du tilldelar behörigheter för webbplatsen.

Uppsättningen med specifika behörigheter som avgör vad en medlem i en SharePoint-grupp kan göra på en webbplats är en behörighets nivå. Det finns tre behörighets nivåer som standard för en SharePoint Online-grupp webbplats: redigera, läsa och fullständig behörighet. I följande tabell visas standard korrelationen för SharePoint-grupper och tilldelade behörighets nivåer:

****

|SharePoint-grupp|Behörighets nivå|
|---|---|
|\<site name> Gruppen|Redigera|
|\<site name> Besökare|Läsa|
|\<site name> Nmöjliga|Fullständig behörighet|
|

 **Metod tips:** Du kan skapa ytterligare SharePoint-grupper och behörighets nivåer. Vi rekommenderar att du använder de SharePoint-standardgrupper och behörighets nivåer som är en SharePoint Online-webbplats.

Här är de SharePoint-standardgrupper och behörighets nivåer som är standard.

![SharePoint-webbplatsens standard grupper och behörighets nivåer.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Fas 2: tilldela behörigheter till användare med Access-grupper

Du kan tilldela behörigheter till användare genom att lägga till deras användar konto eller en Microsoft 365-eller Azure AD-grupp som användar kontot är medlem i, till SharePoint-grupperna. När du har lagt till, tilldelas användar kontona, antingen direkt eller indirekt via medlemskap i en Microsoft 365-eller Azure AD-grupp, den behörighets nivå som är associerad med SharePoint-gruppen.

Använda SharePoint-standardgrupper som exempel:

- Medlemmar i SharePoint-gruppen ** \<site name> medlemmar** , som kan inkludera både användar konton och grupper, tilldelas behörighets nivån **Redigera**

- Medlemmar i SharePoint-gruppen ** \<site name> besökare** , som kan inkludera både användar konton och grupper, tilldelas behörighets nivån **läsa**

- Medlemmar i SharePoint-gruppen ** \<site name> ägare** , som kan inkludera både användar konton och grupper, tilldelas behörighets nivån **full kontroll**

 **Metod tips:** Även om du kan hantera behörigheter med enskilda användar konton rekommenderar vi att du använder en enda Azure AD-grupp, som kallas åtkomst grupp, i stället. Det gör det enklare att hantera behörigheter genom medlemskap i åtkomst gruppen, i stället för att hantera listan över användar konton för varje SharePoint-grupp.

Azure AD-grupper för Microsoft 365 är olika söker igenom med Microsoft 365-grupper. Azure AD-grupper visas i administrations centret för Microsoft 365 med deras **typ** inställda på **säkerhet** och ingen e-postadress. Azure AD-grupper kan hanteras i:

- AD DS (Active Directory Domain Services)

    Det här är grupper som har skapats i din lokala AD DS-infrastruktur och synkroniserats till din Microsoft 365-prenumeration. I administrations centret för Microsoft 365 har dessa grupper **statusen** **synkroniserad med Active Directory**.

- Office 365

    Det här är grupper som har skapats med hjälp av administrations centret för Microsoft 365, Azure Portal eller Microsoft PowerShell. I administrations centret för Microsoft 365 har dessa grupper **statusen** **moln**.

 **Metod tips:** Om du använder AD DS lokalt och synkroniserar med ditt Microsoft 365-abonnemang, kan du utföra användar-och grupp hanteringen med AD DS.

För isolerade SharePoint Online-gruppwebbplatser ser den rekommenderade grupp strukturen ut så här:

****

|SharePoint-grupp|Azure AD-baserad åtkomst grupp|Behörighets nivå|
|---|---|---|
|\<site name> Gruppen|\<site name> Gruppen|Redigera|
|\<site name> Besökare|\<site name> Läsare|Läsa|
|\<site name> Nmöjliga|\<site name> Administratörer|Fullständig behörighet|
|

 **Metod tips:** Även om du kan använda Microsoft 365-eller Azure AD-grupper som medlemmar i SharePoint-grupper rekommenderar vi att du använder Azure AD Groups. Azure AD-grupper, som hanteras antingen via AD DS eller Microsoft 365, ger dig större flexibilitet att använda kapslade grupper för att tilldela behörigheter.

Här är de SharePoint-standardgrupper som är konfigurerade för användning av Azure AD-baserade åtkomst grupper.

![Använda åtkomst grupper som medlemmar i standard webbplats grupper för SharePoint Online.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

Tänk på följande när du utformar de tre åtkomst grupperna:

- Det bör bara finnas några medlemmar i gruppen ** \<site name> Administratörer** , motsvarande ett litet antal SharePoint Online-administratörer som hanterar grupp webbplatsen.

- De flesta av dina webbplats medlemmar är i åtkomst grupperna ** \<site name> medlemmar** eller ** \<site name> läsare** . Eftersom webbplats medlemmar i gruppen ** \<site name> medlemmar** har möjlighet att ta bort eller ändra resurser på webbplatsen bör du noggrant överväga dess medlemskap. Om du är osäker kan du lägga till webbplats medlemmen i åtkomst gruppen ** \<site name> visnings program** .

Här är ett exempel på SharePoint-grupper och åtkomst grupper för en isolerad webbplats med namnet ProjectX.

![Ett exempel på hur du använder åtkomst grupper för en SharePoint Online-webbplats med namnet ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a>Fas 3: använda kapslade Azure AD-grupper

Ett projekt som är begränsat till ett fåtal personer är att en enda nivå av Azure AD-baserade åtkomst grupper läggs till i SharePoint-grupperna på webbplatsen för att passa de flesta scenarier. Men om du har ett stort antal personer och dessa personer redan är medlemmar i etablerade Azure AD-grupper kan du enkelt tilldela SharePoint-behörigheter genom att använda kapslade grupper eller grupper som innehåller andra grupper som medlemmar.

Du vill till exempel skapa en isolerad SharePoint Online-gruppwebbplats för samarbete mellan cheferna för avdelningarna försäljning, marknadsföring, teknik, juridik och support samt de avdelningar som redan har sina egna grupper med användar konto medlemskap för chefer. I stället för att skapa en ny grupp för de nya webbplats medlemmarna och placera alla enskilda användar konton i den, placerar du de befintliga chefs grupperna för varje avdelning i gruppen nytt.

 Om du delar en Microsoft 365-prenumeration mellan flera organisationer kan en enda grupp medlemskap för en isolerad webbplats för en organisation bli svår att hantera på grund av det skir antalet användar konton. I det här fallet kan du använda kapslade Azure AD-grupper för varje organisation som innehåller grupperna inom deras organisationer för att hantera behörigheterna.

Så här använder du kapslade Azure AD-grupper:

1. Identifiera eller skapa de Azure AD-grupper som ska innehålla användar konton och lägga till lämpliga användar konton som medlemmar.

2. Skapa en behållare för Azure AD-baserad åtkomst som kommer att innehålla de andra Azure AD-grupperna och lägga till dessa grupper som medlemmar.

3. För lämplig åtkomst nivå för gruppen behållar åtkomst identifierar du SharePoint-gruppen och motsvarande behörighets nivå.

> [!NOTE]
> Du kan inte använda kapslade Microsoft 365-grupper.

Här är ett exempel på kapslade Azure AD-grupper för gruppen ProjectX member Access.

![Ett exempel på hur kapslade åtkomst grupper används för gruppen medlemmar för ProjectX-webbplatsen.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

Eftersom alla användar konton i gruppen forsknings-, ingenjörs-och projekt ledare är avsedda att vara webbplats medlemmar är det enklare att lägga till deras Azure AD-grupper i ProjectX medlemmar.

## <a name="next-step"></a>Nästa steg

När du är redo att skapa och konfigurera en isolerad webbplats i produktion kan du läsa [distribuera en isolerad SharePoint Online-gruppwebbplats](deploy-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>Se även

[Isolerade SharePoint Online-gruppwebbplatser](isolated-sharepoint-online-team-sites.md)

[Hantera en isolerad SharePoint Online-gruppwebbplats](manage-an-isolated-sharepoint-online-team-site.md)

[Distribuera en isolerad SharePoint Online-gruppwebbplats](deploy-an-isolated-sharepoint-online-team-site.md)
