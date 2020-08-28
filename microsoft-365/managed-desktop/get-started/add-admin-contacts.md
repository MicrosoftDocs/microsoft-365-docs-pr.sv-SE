---
title: Lägga till och verifiera administratörskontakter i administratörsportalen
description: Berätta för oss vem du ska kontakta för varje fokus område.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8b287200b1c94ff350f7ba00cf0c4e6bc1b4a71f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289267"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Lägga till och verifiera administratörskontakter i administratörsportalen

Det finns flera sätt som Microsoft Managed Desktop Service kommunicerar med kunder. För att effektivisera kommunikationen och kontrol lera att vi håller på att kontrol lera med rätt personer måste du ange en uppsättning administratörs kontakter. Microsoft Managed Desktop den här personen kontaktar de här personerna för att få hjälp med fel söknings problem för din klient organisation.

> [!IMPORTANT]
> Du kanske redan har lagt till dessa kontakter i administrations portalen. Om så är fallet, ta ett tag nu för att kontrol lera att kontakt listan stämmer, eftersom Microsoft Managed Desktop **måste** kunna nå dem om en allvarlig olycka inträffar.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Åtkomst för Azure Active Directory-portalen för Microsoft Managed Desktop-administratörer

Administrations portalen för Microsoft Managed Desktop kräver att personer som använder portalen har en av dessa Azure Active Directory (AD)-roller:
- Global administratör
- Intune tjänst administratör
- Global läsare
- Support administratör för tjänsten

Den globala administratören måste vara den som ska registrera din organisation på Microsoft Managed Desktop. Alla fem roller har samma åtkomst i administrations portalen för att initiera och Visa aktiviteter. Mer information om hur du tilldelar dessa roller i Azure AD finns i [behörigheter för administratörs roller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). 

## <a name="admin-contact-areas-of-focus"></a>Administrations kontakt områden i fokus

Administratörs kontakterna bör vara den bästa personen eller gruppen som kan besvara frågor och fatta beslut för olika fokus områden. **Microsoft Managed Station ära datorer kontaktar dessa administratörs kontakter för frågor som berör support ärenden som skickas av kunden.** Dessa administratörs kontakter får aviseringar om uppdateringar och nya meddelanden om supportinformation. Dessa områden inkluderar:

Fokus område | Om du har frågor om
--- | ---
Program packning | Felsöka programpaket
Anordningar | Enhets hälsa, fel sökning med Microsoft hanterade Station ära enheter
Säkerhet | Felsöka säkerhets problem med Microsoft hanterade Station ära enheter
IT-support | i de fall vår support personal händer över användar biljetter utanför Microsoft Managed Desktop support-områden 
Annat | För problem som inte täcks av andra områden

**Den du väljer för dessa kontakter måste ha kunskap och behörighet för att fatta beslut för din Microsoft-hanterade Skriv bords miljö.** När du har en Microsoft Managed Desktop-miljö uppmanas du att lägga till kontakter för ditt lokala helpdesk och din säkerhet. 

Administratörs kontakter krävs när du [skickar in en supportbegäran](../service-description/support.md). Du måste ha en administratörs kontakt för att fokusera på support förfrågan. 

**Lägga till administratörs kontakter**

1.  Logga in på [administrations portalen för Microsoft Managed Desktop](https://aka.ms/mwaasportal). 

2.  Välj **admin-kontakter**under **support**. 

    ![Menyn support, administratörs kontakter nära det markerade överst](../../media/admincontacts.png)

3. Välj **Lägg till**.

    ![Administrations portalen, knappen Lägg till, till vänster om exportera och uppdatera](../../media/adminadd.png)

4.  Markera ett **område med fokus** och ange informationen för kontakten. 

    ![listan med fokus områden, till exempel andra, appar och säkerhet](../../media/areaoffocus.png)

5. Upprepa för varje fokus område. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Managed Desktop

1. Lägga till och verifiera administratörs kontakter i administrations portalen (det här avsnittet)
2. [Justera villkorsstyrd åtkomst](conditional-access.md)
3. [Koppla licenser](assign-licenses.md)
4. [Installera Intune-företagsportal på enheter](company-portal.md)
5. [Aktivera Enterprise State Roaming](enterprise-state-roaming.md)
6. [Konfigurera Microsoft Hanterat skrivbord enheter](set-up-devices.md)
7. [Få dina användare redo att använda enheter](get-started-devices.md)
8. [Distribuera appar till enheter](deploy-apps.md)
