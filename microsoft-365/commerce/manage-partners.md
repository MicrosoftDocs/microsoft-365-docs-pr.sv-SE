---
title: Hantera partnerrelationer
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
- PPM_jmueller
ms.reviewer: tugu
search.appverid:
- MET150
description: Lär dig hur du arbetar med Microsoft-certifierade lösningsleverantörer (partners) för att köpa och hantera produkter och tjänster för din organisation eller skola.
ms.date: 04/13/2021
ms.openlocfilehash: e225fa0c525d484e8c5a3887b82277a1da5861b0
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107574"
---
# <a name="manage-partner-relationships"></a>Hantera partnerrelationer

Du kan samarbeta med Microsoft-certifierade lösningsleverantörer (partners) för att köpa och hantera produkter och tjänster för din organisation eller skola. Det ingår några steg i att konfigurera saker.

1. Administratörer hittar och kontaktar en partner med hjälp av formuläret på <a href="https://www.microsoft.com/solution-providers/home" target="_blank">https://www.microsoft.com/solution-providers/home</a> .
2. Partner skickar en e-postförfrågan till kunder för att upprätta en partnerrelation.
3. Kunderna accepterar inbjudan i Microsoft 365 administrationscenter och börjar arbeta med partnern.

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara antingen global administratör eller faktureringsadministratör för att kunna göra följande. Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).

## <a name="what-can-a-partner-do-for-my-organization-or-school"></a>Vad kan en partner göra för min organisation eller skola?

En partner kan arbeta med dig på flera olika sätt. Beroende på dina specifika affärsbehov väljer de någon av dessa typer när de skickar sin begäran att arbeta med dig.

| Partnertyp | Beskrivning |
| ------ | ------------------- |
| Återförsäljare | Partners som säljer Microsoft-produkter till din organisation eller skola. |
| Delegerad administratör | Partner som hanterar produkter och tjänster för din organisation eller skola. I Azure Active Directory (AD) är partnern global administratör för klientorganisationen. Med den här rollen kan de hantera tjänster som att skapa användarkonton, tilldela och hantera licenser och lösenordsåterställningar. |
| Återförsäljare & delegerad administratör | Partners som säljer och hanterar Microsofts produkter och tjänster till din organisation eller skola. |
| Partner | Du ger din partner ett användarkonto i klientorganisationen och de arbetar med andra Microsoft-tjänster åt dig. |
| Rådgivare | Partner kan återställa lösenord och hantera supportärenden för dig. |
| MPSA-& Products & Services Agreement (MPSA) | Om du har arbetat med flera partner via MPSA-programmet kan du låta dem se köp som gjorts av varandra. |
| LOB-partner | Partners kan utveckla, skicka in och hantera verksamhetsspecifika appar för din organisation eller skola. |

## <a name="find-a-partner"></a>Hitta en partner

1. Gå till <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.
2. Ange din plats, välj organisationens storlek, lägg till nyckelord för typen av tjänster du behöver och välj sedan **Gå**.
3. Välj en eller flera partner och välj sedan **Kontakta valda leverantörer.**
4. Fyll i formuläret för att beskriva dina affärsbehov och välj sedan **Skicka**.

Partnerkontakterna du och ger dig möjlighet att få mer information om dem. Om du bestämmer dig för att arbeta med dem skickar de en inbjudan via e-post för att upprätta en partnerrelation.

## <a name="review-and-accept-a-partner-relationship-and-microsoft-customer-agreement"></a>Granska och acceptera en partnerrelation och Microsofts kundavtal

När du har hittat en partner och bestämmer dig för att arbeta med partnern skickar de en e-postinbjudan till dig.

1. I e-postmeddelandet väljer du länken för att gå till Microsoft 365 administrationscenter.
2. På sidan **Acceptera avtal & partner,** väljer du länken till **Microsofts kundavtal** och läser dokumentet.
3. Markera rutan för att bekräfta att du läst avtalet.
4. Välj **Godkänn & Godkänn**.
5. Listan över partners som du arbetar med visas. Välj en partner för att se mer information.

## <a name="review-and-accept-a-microsoft-customer-agreement"></a>Granska och acceptera ett Microsoft-kundavtal

Om du redan har en partner, men ännu inte har signerat ett Microsoft-kundavtal, måste du acceptera avtalet innan de kan köpa eller hantera dina prenumerationer för din räkning.

1. Om du får ett e-postmeddelande från din partner väljer du länken för att gå Microsoft 365 administrationscentret eller gå till <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">sidan Acceptera</a> avtal.
2. Välj länken för **Microsofts kundavtal** och läs dokumentet.
3. Markera rutan för att bekräfta att du läst avtalet.
4. Välj **Acceptera**.
5. Listan över partners som du arbetar med visas. Välj en partner för att se mer information.

## <a name="remove-partner-admin-roles"></a>Ta bort partneradministratörsroller

När du accepterar inbjudan samtycker du till att ge partnern global administratörsroll och support,beroende på partnerns begäran. När du ger de här administratörsrollerna till en partner beviljar du dem automatiskt delegerade administratörsbehörigheter i Azure AD. Mer information finns i [Delegerade administratörsbehörigheter i Azure AD.](/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad)

Om du inte vill ge partnern administratörsroller avbryter du inbjudan i stället för att acceptera den.

Du kan när som helst ta bort administratörsroller från en partner. Partnerrelationen tas inte bort om du tar bort administratörsrollerna. De kan fortfarande arbeta med dig i en annan kapacitet, till exempel som återförsäljare. Om du bestämmer dig för att du inte längre vill arbeta med en partner kontaktar du din partner för att avsluta relationen.

1. I administrationscentret går du till sidan **Inställningar**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partnerrelationer.</a>
2. På sidan **Partnerrelationer** markerar du den rad som innehåller namnet på den partner som du vill ta bort.
3. Markera raden som innehåller namnet på partnern.
4. Välj Ta bort roller på **partnersidan.**
5. I dialogrutan **Ta bort roller?** väljer du **Ja.**
