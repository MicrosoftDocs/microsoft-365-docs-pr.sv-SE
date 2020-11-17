---
title: Skapa och använda en mall för att lägga till användare
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ms.openlocfilehash: aef5085da603c38b37544b76c5336c9bfe4edd24
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123423"
---
# <a name="create-and-use-a-template-to-add-users"></a>Skapa och använda en mall för att lägga till användare

Du kan skapa och använda en mall för att spara tid och standardisera inställningar när du lägger till flera användare. Mallar är särskilt användbara om du har användare som delar många vanliga egenskaper, till exempel personer som har samma roll och som har samma program vara. Du kanske till exempel har ett team med support tekniker som arbetar i samma kontor.  

## <a name="create-a-template"></a>Skapa en mall

Det är enkelt att skapa mallar och &mdash; välja **användare**  >  **aktiva** användare användarmallar  >  **User templates** och sedan välja **Lägg till en mall** från List rutan, eller så kan du lägga till en ny användare och när du är klar har du möjlighet att spara posten som en mall.

När du skapar en mall när du har lagt till en användare sparas värdena som du väljer för följande inställningar i mallen:

- Domännamn
- Alternativ för lösen ords inställningar: du kan välja att skapa lösen ord eller automatiskt generera dem
- Lösen ords val för enskilda samtidigt: du kan kräva att användaren skapar ett nytt lösen ord efter att ha loggat in
- Licens plats
- Licens val
- Program alternativ
- Roll
- De flesta profil uppgifter, till exempel **jobb profil**, **avdelning**, **kontor**, **kontors telefon** och **gatuadress** 

Följande information är användarspecifik och sparas inte i mallen:

- För-och efter namn
- Visningsnamn
- Användar namn
- Alternativ för att skicka lösen ordet i e-post och vem som skickar e-postmeddelandet till
- Mobiltelefon nummer

Om du väljer att inte ange information för en inställning inom ett avsnitt kommer det värdet att vara tomt och inställningen visas inte i mallen. Om du till **exempel lämnar befattningen** tom visas inte **jobb namnet** alls när du granskar mallen och när du använder mallen. Om du låter alla inställningar för **profil** avsnitt vara tomma visas inte **profil** **avsnittet i den** slutliga mallen.

När du skapar en mall genom att välja alternativet **Lägg till en mall** kan du välja vilka värden som ska slutföras. Allting som lämnas tomt visas som ej **angivet** i mallen.

## <a name="use-a-template-to-add-a-user"></a>Använda en mall för att lägga till en användare

Så här använder du en befintlig mall för att lägga till en användare:

1. Välj **användare**  >  **aktiva användare** i administrations centret.

2. Välj **användarmallar** och välj sedan en mall i list rutan. (Listan kommer bara att innehålla de mallar som du har skapat, inte de som skapats av andra administratörer.)

   > [!NOTE]
   > Du kan också använda en mall för att lägga till en användare genom **att välja användarmallar**  >  **Hantera mallar**, välja en mall och sedan välja **Använd mall**.

3. Följ stegen för att skapa en användare från mallen som du har valt.

   > [!NOTE]
   > Om du inte har tillräckligt med licenser tillgängliga för en användare som du lägger till och din betalnings information är tillgänglig försöker vi köpa en annan licens med din befintliga betalnings information. Om din betalnings information inte är tillgänglig skapas användaren som en olicensierad användare.

## <a name="manage-templates"></a>Hantera mallar

Du kan bara ta bort mallar som du inte längre behöver och lägga till nya. Så här tar du bort en mall:

1. Välj **användare**  >  **aktiva användare** i administrations centret.

2. Välj **mallar** och sedan **Hantera mallar** i list rutan.

3. En lista med mallar visas. Du kan ta bort en mall genom att göra något av följande:
    - Välj en eller flera mallar och välj sedan **ta bort**. 
    - Markera de tre punkterna till höger om mallnamnet och välj sedan **ta bort**.
    - Välj mallnamnet. Välj **ta bort mall** när mal detaljer visas till höger på skärmen.

## <a name="related-articles"></a>Relaterade artiklar

[Lägga till användare och tilldela licenser samtidigt](add-users.md)

[Ta bort en tidigare anställd från Microsoft 365](remove-former-employee.md)
  
