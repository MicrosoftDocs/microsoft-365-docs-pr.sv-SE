---
title: Skapa och använda en mall för att lägga till användare
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
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Du kan skapa och använda en mall för att spara tid och standardisera inställningar när du lägger till flera användare.
ms.openlocfilehash: 3ce70f6d37036a2f71bdc2d41bfb5677a54b8db9
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579392"
---
# <a name="create-and-use-a-template-to-add-users"></a>Skapa och använda en mall för att lägga till användare

Du kan skapa och använda en mall för att spara tid och standardisera inställningar när du lägger till flera användare. Mallar är särskilt användbara om du har användare som delar många vanliga egenskaper, t.ex. de som har samma roll och arbetar på samma plats och de som behöver samma programvara. Du kan till exempel ha en grupp supporttekniker som arbetar på samma kontor.  

## <a name="create-a-template"></a>Skapa en mall

Mallar är lätta att skapa du kan välja Användare aktiva användare Användarmallar och sedan välja Lägg till en mall i listrutan, eller så kan du lägga till en ny användare. När du är klar har du möjlighet att spara posten som &mdash;   >    >  en mall. 

När du skapar en mall efter att ha lagt till en användare sparas de värden du väljer för följande inställningar i mallen:

- Domännamn
- Val av lösenordsinställningar: du kan välja att skapa lösenord eller att generera dem automatiskt
- Val av lösenord vid 1 tillfälle: du kan kräva att användaren skapar ett nytt lösenord efter första inloggningen
- Licensplats
- Licensalternativ
- Programalternativ
- Roll
- De flesta profiluppgifter, till **exempel jobbprofil,** **avdelning,** **Office,** **Office telefon** och **gatuadress** 

Följande information är användarspecifik och sparas inte i mallen:

- För- och efternamn
- Visningsnamn
- Användarnamn
- Välja att skicka lösenordet i ett e-postmeddelande och till vem som får e-postadressen med lösenordet
- Mobiltelefonnummer

Om du väljer att inte ange information för en inställning i ett avsnitt är det värdet tomt och inställningen visas inte i mallen. Om du till exempel lämnar **Befattning** tomt, när du granskar mallen och när du använder **mallen,** visas inte befattningen alls. Om du låter alla **profilavsnittsinställningar** vara tomma **visas** Inga **angivna i** den slutliga mallen i avsnittet Profil.

När du skapar en mall genom att välja **alternativet Lägg till en** mall kan du välja vilka värden som ska fyllas i. Allt som lämnas tomt visas som **Ingen tillhandahållet** i mallen.

## <a name="use-a-template-to-add-a-user"></a>Använda en mall för att lägga till en användare

Så här lägger du till en användare med en befintlig mall:

1. I administrationscentret väljer du **Användare**  >  **aktiva användare.**

2. Välj **Användarmallar** och välj sedan en mall i listrutan. (Listan innehåller bara de mallar som du har skapat, inte mallar som skapats av andra administratörer.)

   > [!NOTE]
   > Du kan också använda en mall för att lägga till en användare genom att välja Användarmallar Hantera mallar , välja en mall  >  och sedan välja **Använd mall.**

3. Följ anvisningarna för att skapa en användare från den valda mallen.

   > [!NOTE]
   > Om du har otillräckliga licenser tillgängliga för en användare som du lägger till och din betalningsinformation är tillgänglig försöker vi köpa en annan licens med hjälp av din befintliga betalningsinformation. Om din betalningsinformation inte är tillgänglig skapas användaren som en olicensierad användare.

## <a name="manage-templates"></a>Hantera mallar

Du kan bara ta bort mallar som du inte längre behöver och lägga till nya. Så här tar du bort en mall:

1. I administrationscentret väljer du **Användare**  >  **aktiva användare.**

2. Välj **Mallar** och välj **sedan Hantera mallar** i listrutan.

3. En lista med mallar visas. Du kan ta bort en mall genom att göra något av följande:
    - Markera en eller flera mallar och välj sedan Ta **bort**. 
    - Välj de tre punkterna till höger om mallnamnet och välj sedan Ta **bort**.
    - Välj mallnamnet. När mallinformationen visas till höger på skärmen väljer du Ta **bort mall**.

## <a name="related-articles"></a>Relaterade artiklar

[Lägga till användare och tilldela licenser samtidigt](add-users.md)

[Ta bort en tidigare anställd från Microsoft 365](remove-former-employee.md)
  
