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
ms.openlocfilehash: 18823db8ca8d4bfa82b8ab6265ee8a0902a13e79
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925898"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Lägga till och verifiera administratörskontakter i administratörsportalen

Tjänsten Microsoft Managed Desktop kommunicerar med kunder på flera olika sätt. För att effektivisera kommunikationen och se till att vi kontrollerar med rätt personer, måste du tillhandahålla en uppsättning administratörskontakter. Microsoft Managed Desktop IT Operations kontaktar dessa personer för att få hjälp med att felsöka problem för klientorganisationen.

> [!IMPORTANT]
> Du kanske redan har lagt till de här kontakterna i administrationsportalen. I så fall bör du kontrollera att kontaktlistan är korrekt, eftersom Microsoft Managed **Desktop** måste kunna nå dem om ett allvarligt problem inträffar.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory-åtkomst för Microsoft Managed Desktop Admin-portalen

Microsoft Managed Desktop Admin-portalen kräver att personer som har åtkomst till portalen har någon av dessa Azure Active Directory-roller (AD):
- Global administratör
- Intune-tjänstadministratör
- Global läsare
- Tjänstsupportadministratör

Den globala administratören måste vara den som registrerar din organisation i Microsoft Managed Desktop. Alla fem rollerna har samma åtkomst i administrationsportalen för att initiera och visa uppgifter. Mer information om hur du tilldelar de här rollerna i Azure AD finns i [Behörigheter för administratörsroll i Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 

## <a name="admin-contact-areas-of-focus"></a>Administratörskontaktområden i fokus

Administratörskontakter bör vara den bästa personen eller gruppen som kan besvara frågor och fatta beslut inom olika fokusområden. **Microsoft Managed Desktop Operations kommer att kontakta dessa administratörskontakter för frågor som rör supportbegäranden som lämnats in av kunden.** De här administratörskontakterna får aviseringar om uppdateringar av supportbegäran och nya meddelanden. Dessa områden omfattar:

Fokusområde | För frågor om
--- | ---
Appförpackning | Felsökning av appförpackningar
Enheter | Enhetens hälsa, felsökning med Microsoft Managed Desktop-enheter
Säkerhet | Felsöka säkerhetsproblem med Microsoft Managed Desktop-enheter
It-supportavdelningen | i fall där vår supportpersonal ger över användarärenden utanför supportområdena för Microsoft Managed Desktop 
Annat | För problem som inte omfattas av andra områden

**De som du väljer för dessa kontakter måste ha kunskaper och behörighet att fatta beslut om Microsoft Managed Desktop-miljön.** När du onboard your Microsoft Managed Desktop environment, you're prompted to add contacts for your local Helpdesk and Security. 

Administratörskontakter krävs när du [skickar en supportbegäran.](../service-description/support.md) Du måste ha en administratörskontakt för fokusområdet i supportbegäran. 

**Lägga till administratörskontakter**

1.  Logga in på [administrationsportalen för Microsoft Managed Desktop.](https://aka.ms/mwaasportal) 

2.  Under **Support** väljer du **Administratörskontakter**. 

    ![Supportmenyn, administratörskontakter nästan högst upp markerat](../../media/admincontacts.png)

3. Välj **Lägg till**.

    ![Administrationsportal, knappen Lägg till, till vänster om Exportera och uppdatera](../../media/adminadd.png)

4.  Välj **ett område med fokus** och ange information om kontakten. 

    ![listan över fokusområden, till exempel Andra, Appar och Säkerhet](../../media/areaoffocus.png)

5. Upprepa detta för varje fokusområde. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Managed Desktop

1. Lägga till och verifiera administratörskontakter i administrationsportalen (det här avsnittet)
2. [Justera villkorsstyrd åtkomst](conditional-access.md)
3. [Koppla licenser](assign-licenses.md)
4. [Installera Intune-företagsportal på enheter](company-portal.md)
5. [Aktivera Enterprise State Roaming](enterprise-state-roaming.md)
6. [Konfigurera Microsoft Hanterat skrivbord enheter](set-up-devices.md)
7. [Få dina användare redo att använda enheter](get-started-devices.md)
8. [Distribuera appar till enheter](deploy-apps.md)