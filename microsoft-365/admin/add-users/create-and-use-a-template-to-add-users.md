---
title: Skapa och använda en mall för att lägga till användare
f1.keywords:
- NOCSH
ms.author: v-sharos
author: shars
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
ms.openlocfilehash: cbe61c87bec40196ffd7a8e9868ea4611e4c259e
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44431815"
---
# <a name="create-and-use-a-template-to-add-users"></a>Skapa och använda en mall för att lägga till användare

Du kan skapa och använda en mall för att spara tid och standardisera inställningar när du lägger till flera användare. Mallar är särskilt användbara om du har användare som delar många vanliga egenskaper, som de som har samma roll och arbetar på samma plats och de som behöver samma programvara. Du kan till exempel ha ett team med supporttekniker som arbetar på samma kontor.  

## <a name="create-a-template"></a>Skapa en mall

Mallar är enkla att &mdash; skapa, du kan välja **Användare**  >  **Aktiva användare**  >  **Användarmallar**, och välj sedan Lägg till en **mall** i listrutan, eller så kan du lägga till en ny användare och när du är klar har du möjlighet att spara posten som en mall.

När du skapar en mall när du har lagt till en användare sparas de värden du väljer för följande inställningar i mallen:

- Domännamn
- Val av lösenordsinställningar: du kan välja att skapa lösenord eller låta dem genereras automatiskt
- Engångslösenord: du kan kräva att användaren skapar ett nytt lösenord efter första inloggningen
- Licensplats
- Licensval
- Val av program
- Roll
- Mest profilinformation, till exempel **Jobbprofil,** **Avdelning,** **Office,** **Office-telefon**och **Gatuadress** 

Följande information är användarspecifik och sparas inte i mallen:

- För- och efternamn
- Visningsnamn
- Användarnamn
- Val att skicka lösenordet via e-post och vem lösenordet e-postmeddelandet skickas till
- Mobiltelefonnummer

Om du väljer att inte ange information för en inställning i ett avsnitt är det värdet tomt och den inställningen visas inte i mallen. Om du till exempel lämnar **befattningen** tom visas inte **befattningen jobbtitel** alls när du granskar mallen och när du använder mallen. Om du lämnar alla inställningar för **profilavsnittet** tomma visas **Ingen** i den slutliga mallen i avsnittet **Profil.**

När du skapar en mall genom att välja alternativet **Lägg till en mall** kan du välja vilka värden som ska slutföras. Allt som lämnas tomt visas som **Ingen i** mallen.

## <a name="use-a-template-to-add-a-user"></a>Använda en mall för att lägga till en användare

Så här använder du en befintlig mall för att lägga till en användare:

1. I administrationscentret väljer du **Aktiva**  >  **användare**.

2. Välj **Användarmallar**och välj sedan en mall i listrutan. (Listan innehåller bara de mallar som du har skapat, inte de som skapats av andra administratörer.)

 > [!NOTE]
 > Du kan också använda en mall för att lägga till en användare genom att välja **Användarmallar**  >  **Hantera mallar,** välja en mall och sedan välja **Använd mall**.

3. Följ stegen för att skapa en användare från den mall du valde.

> [!NOTE]
> Om du inte har tillräckliga licenser tillgängliga för en användare som du lägger till och din betalningsinformation är tillgänglig försöker vi köpa en annan licens med din befintliga betalningsinformation. Om din betalningsinformation inte är tillgänglig skapas användaren som en olicensierad användare.

## <a name="manage-templates"></a>Hantera mallar

Du kan enkelt ta bort mallar som du inte längre behöver och lägga till nya. Så här tar du bort en mall:

1. I administrationscentret väljer du **Aktiva**  >  **användare**.

2. Välj **Mallar**och välj sedan **Hantera mallar** i listrutan.

3. En lista med mallar visas. Du kan ta bort en mall genom att göra något av följande:
    - Markera en eller flera mallar och välj sedan **Ta bort**. 
    - Markera de tre punkterna till höger om mallnamnet och välj sedan **Ta bort**.
    - Välj mallnamnet. När mallinformationen visas till höger på skärmen väljer du **Ta bort mall**.

## <a name="related-articles"></a>Relaterade artiklar

[Lägga till användare individuellt eller i grupp i Microsoft 365](add-users.md)

[Ta bort en tidigare anställd från Microsoft 365](remove-former-employee.md)
  
