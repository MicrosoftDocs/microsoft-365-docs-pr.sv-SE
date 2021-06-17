---
title: Lägga till och verifiera administratörskontakter i administratörsportalen
description: Berätta vem vi ska kontakta för varje fokusområde.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 65d7647e9000152d2eeb8d6bf36e8d45a0d4fa90
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984706"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Lägga till och verifiera administratörskontakter i administratörsportalen

Det finns flera sätt Microsoft Hanterat skrivbord kommunicerar med kunder. För att effektivisera kommunikationen och se till att vi kontrollerar med rätt personer, måste du tillhandahålla en uppsättning administratörskontakter. Microsoft Hanterat skrivbord IT-åtgärder kontaktar dessa personer för att få hjälp med att felsöka problem för klientorganisationen.

> [!IMPORTANT]
> Du kanske redan har lagt till de här kontakterna i administrationsportalen. I så fall bör du kontrollera att kontaktlistan är korrekt, eftersom  Microsoft Hanterat skrivbord måste kunna nå dem om det inträffar en allvarlig händelse.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory åtkomst Microsoft Hanterat skrivbord administrationsportalen

Microsoft Hanterat skrivbord Administratörsportalen kräver att personer som har åtkomst till portalen har någon av Azure Active Directory-roller (AD):
- Global administratör
- Intune-tjänstadministratör
- Global läsare
- Tjänstsupportadministratör

Den globala administratören måste vara den som registrerar din organisation i Microsoft Hanterat skrivbord. Alla fem rollerna har samma åtkomst i administrationsportalen för att initiera och visa uppgifter. Mer information om hur du tilldelar de här rollerna i Azure AD finns i [Behörigheter för administratörsroller i Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 

## <a name="admin-contact-areas-of-focus"></a>Administratörskontaktområden i fokus

Administratörskontakter bör vara den bästa personen eller gruppen som kan besvara frågor och fatta beslut inom olika fokusområden. **Microsoft Hanterat skrivbord Åtgärder kommer att kontakta dessa administratörskontakter för frågor som rör supportbegäranden som har lämnats in av kunden.** De här administratörskontakterna får aviseringar om uppdateringar av supportbegäran och nya meddelanden. Dessa områden omfattar:

Fokusområde | För frågor om
--- | ---
Appförpackning | Felsökning av appförpackningar
Enheter | Enhetens hälsa, felsökning med Microsoft Hanterat skrivbord enheter
Säkerhet | Felsöka säkerhetsproblem med Microsoft Hanterat skrivbord enheter
It-supportavdelningen | i fall där vår supportpersonal ger över användarärenden utanför Microsoft Hanterat skrivbord supportområden 
Annat | För problem som inte omfattas av andra områden

**De som du väljer för dessa kontakter måste ha kunskap och behörighet att fatta beslut i din Microsoft Hanterat skrivbord miljö.** När du onboard your Microsoft Hanterat skrivbord environment, you're prompted to add contacts for your local Helpdesk and Security. 

Administratörskontakter krävs när du [skickar en supportbegäran.](../service-description/support.md) Du måste ha en administratörskontakt för fokusområdet i supportbegäran. 

**Lägga till administratörskontakter**

1.  Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com). 

2.  Titta **efter avsnittet** för klientorganisationsadministration **Microsoft Hanterat skrivbord** välj sedan **Administratörskontakter**. 

3. Välj **Lägg till**.

4.  Välj **ett område med fokus** och ange information om kontakten. 

    ![listan över fokusområden, till exempel Andra, Appar och Säkerhet](../../media/areaoffocus.png)

5. Upprepa detta för varje fokusområde. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Hanterat skrivbord

1. Lägga till och verifiera administratörskontakter i administrationsportalen (det här avsnittet)
2. [Justera villkorsstyrd åtkomst](conditional-access.md)
3. [Koppla licenser](assign-licenses.md)
4. [Installera Intune-företagsportal på enheter](company-portal.md)
5. [Aktivera Enterprise State Roaming](enterprise-state-roaming.md)
6. [Konfigurera Microsoft Hanterat skrivbord enheter](set-up-devices.md)
7. [Få dina användare redo att använda enheter](get-started-devices.md)
8. [Distribuera appar till enheter](deploy-apps.md)
