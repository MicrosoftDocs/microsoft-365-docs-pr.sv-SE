---
title: Hantera principer för automatiskt anspråk
f1.keywords:
- CSH
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
description: Lär dig hur du skapar och hanterar principer för automatiskt anspråk som automatiskt tilldelar användare licenser för vissa appar.
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
ms.openlocfilehash: bf3f79e425b3f7cd86f1a5ab95a337ef5127e345
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911478"
---
# <a name="manage-auto-claim-policies"></a>Hantera principer för automatiskt anspråk

Med principen för automatiskt anspråk kan användare automatiskt begära en licens för en produkt första gången de loggar in i en app. Som administratör tilldelar du vanligtvis licenser till användare antingen manuellt eller med gruppbaserad licensiering. Genom att använda principer för automatiskt anspråk hanterar du de produkter för vilka användare automatiskt kan begära licenser. Du kan också styra vilka produkter licenserna kommer från.

När du har skapat en princip för automatiskt anspråk kan du utföra följande uppgifter för att hantera principen:

- [Aktivera eller inaktivera principen](#turn-a-policy-on-or-off)
- [Redigera namnet på policyn](#edit-the-policy-friendly-name)
- [Lägga till eller ta bort säkerhetskopior](#add-or-remove-backup-products)
- [Hantera tilldelning av appar och tjänster](#change-the-assigning-apps-and-services)
- [Ändra tilldelningsordern](#change-the-assigning-order-for-backup-products)
- [Visa en principrapport](#view-an-auto-claim-policy-report)

> [!IMPORTANT]
> Policyer för automatiskt anspråk är för närvarande endast tillgängliga för Microsoft Teams. Fler produkter kommer att finnas tillgängliga att använda i framtiden.

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara global administratör för att skapa och hantera principer för automatiskt anspråk. Mer information finns i [Om Microsoft 365-administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="turn-the-auto-claim-policy-feature-on-or-off"></a>Aktivera eller inaktivera principen för automatiskt anspråk

Principen för automatiskt anspråk är inaktiverad som standard. Innan du kan använda funktionen måste du först aktivera den. När du har aktiverar funktionen kan du skapa en princip för automatiskt anspråk.

### <a name="turn-on-auto-claim-policies"></a>Aktivera principer för automatiskt anspråk

1. I administrationscentret går du  till sidan \> **Faktureringslicenser** och väljer sedan fliken <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Princip för automatiskt</a> anspråk.
2. I mitten av sidan väljer du **knappen Aktivera** inställning.

### <a name="turn-off-auto-claim-policies"></a>Inaktivera principer för automatiskt anspråk

1. I administrationscentret går du till sidan **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">för organisationen.</a>
2. Längst ned i tabellen väljer du **Användarägda appar och tjänster.**
3. I det högra fönstret avmarkerar du rutan för **Låt användare göra automatiskt anspråk på licenser första gången de loggar in.**

Om du redan har en aktiv princip, men inte vill att fler användare ska begära licenser, [inaktiverar du principen.](#turn-a-policy-on-or-off) När du inaktiverar en princip för automatiskt anspråk kan inga fler användare begära en licens från och med då. Användare som redan påstådda en licens förlorar inte sin licens.

## <a name="create-an-auto-claim-policy"></a>Skapa en princip för automatiskt anspråk

På <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">fliken Automatiskt anspråk finns</a> en lista med principer som du skapar. På den här fliken kan du se: namnet på principen, programmet som är kopplat till principen, den produkt som är tilldelad till principen, antalet tillgängliga licenser och status för principen.

När du skapar en princip för automatiskt anspråk kan du lägga till en produkt för säkerhetskopiering. Om den primära produkten har slut på licenser används säkerhetskopian för att tilldela licenser till användare. Du kan lägga till upp till fyra säkerhetskopior [och ändra i vilken ordning de används.](#change-the-assigning-order-for-backup-products) Mer information finns i Lägga [till eller ta bort säkerhetskopior.](#add-or-remove-backup-products)

> [!NOTE]
> För närvarande kan du bara skapa en princip för automatiskt anspråk. Antalet principer som du kan skapa ökar när fler produkter kan använda den här funktionen.

1. I administrationscentret går du  till sidan \> **Faktureringslicenser** och väljer sedan fliken <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Princip för automatiskt</a> anspråk.
2. Välj **Lägg till en princip**.
3. På sidan **Namnge principen för automatiskt anspråk** anger du ett namn på principen och väljer sedan **Nästa.**
4. På sidan **Ange ett automatiskt anspråk för app och produkt** väljer du en app och prenumerationen som du vill tilldela licenser från.
5. Om du vill lägga till en säkerhetskopia väljer du Lägg till en **säkerhetskopia i** den här principen och väljer sedan produkten i listan.
6. Välj **Nästa**.
7. Avmarkera **eller markera rutorna** för de appar som ska undantas eller inkluderas i licensen på sidan Välj appar och välj sedan **Nästa.**
8. Om du har lagt till en eller flera säkerhetskopior upprepar du steg 7 för varje produkt. Annars går du vidare till steg 9.
9. Kontrollera informationen **om den nya** principen på sidan Granska och slutför, gör nödvändiga ändringar och välj sedan Skapa **princip.**
10. Välj **Stäng**.

## <a name="turn-a-policy-on-or-off"></a>Aktivera eller inaktivera en princip

När du inaktiverar en princip kan inga fler användare begära licenser enligt den principen. Ändringen påverkar inte användare som redan har anspråk på licenser enligt den policyn.

1. I administrationscentret går du  till sidan \> **Faktureringslicenser** och väljer sedan fliken <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Princip för automatiskt</a> anspråk.
2. Markera den princip som du vill redigera.
3. Markera eller avmarkera kryssrutan under **Aktivera eller inaktivera den här** principen i informationsfönstret.
4. Välj **Spara** för att stänga informationsfönstret.

## <a name="edit-the-policy-friendly-name"></a>Redigera namnet på policyn

1. I administrationscentret går du  till sidan \> **Faktureringslicenser** och väljer sedan fliken <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Princip för automatiskt</a> anspråk.
2. Markera den princip som du vill redigera.
3. Välj Redigera i avsnittet **Principnamn** i **informationsfönstret.**
4. Ange ett nytt principnamn och välj sedan **Spara**.
5. Välj **Spara** för att stänga informationsfönstret.

## <a name="add-or-remove-backup-products"></a>Lägga till eller ta bort säkerhetskopior

När du skapar en princip lägger du till en produkt i den. Licenser tilldelas sedan automatiskt till användare från den licenspoolen. Du kan när som helst lägga till eller ta bort produkter för en princip för automatiskt anspråk. Om du redan har en produkt kopplad till principen betraktas de produkter som du lägger till som säkerhetskopior. När det tillgängliga antalet licenser från den första produkten används används nästa säkerhetskopia i listan för att tilldela licenser från i principen. Du [kan ändra ordning på produktlistan som](#change-the-assigning-apps-and-services) du vill.

När du tar bort en produkt för säkerhetskopiering används den inte längre för att tilldela licenser. Användare med en befintlig licens har fortfarande den licensen, men inga nya användare kan ta emot licenser för den produkten.

> [!NOTE]
> En princip för automatiskt anspråk måste innehålla minst en produkt. Du kan inte ta bort alla produkter från en princip. Om du inte längre vill tilldela licenser från en viss princip för automatiskt anspråk [inaktiverar du principen.](#view-an-auto-claim-policy-report)

### <a name="add-a-backup-product"></a>Lägga till en säkerhetskopia

1. I administrationscentret går du  till sidan \> **Faktureringslicenser** och väljer sedan fliken <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Princip för automatiskt</a> anspråk.
2. Markera den princip som du vill redigera.
3. Längst ned i informationsfönstret väljer du Lägg till en alternativ **produkt för säkerhetskopia i den här principen.**
    > [!NOTE]
    > Om du inte ser den här länken beror det på att du bara har en produkt kopplad till ditt konto.
4. I fönstret **Lägg till en** produkt använder du listrutan för att välja en produkt att lägga till i principen och väljer sedan Lägg **till**.
5. Välj **Spara** för att stänga informationsfönstret.

### <a name="remove-a-backup-product"></a>Ta bort en säkerhetskopia

1. I administrationscentret går du  till sidan \> **Faktureringslicenser** och väljer sedan fliken <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Princip för automatiskt</a> anspråk.
2. Markera den princip som du vill redigera.
3. Välj Ta bort en produkt längst ned i **informationsfönstret.**
4. I fönstret **Ta bort en produkt från principen** markerar du rutan för den princip du vill ta bort och väljer sedan **Spara**.
5. Stäng informationsfönstret.

## <a name="change-the-assigning-apps-and-services"></a>Ändra tilldelning av appar och tjänster

Varje produkt har en samling appar och tjänster som är kopplade till den.
För varje produkt i principen för automatiskt anspråk kan du ange vilka appar och tjänster som ska inkluderas när en användare automatiskt tilldelas en licens till produkten.

1. I administrationscentret går du  till sidan \> **Faktureringslicenser** och väljer sedan fliken <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Princip för automatiskt</a> anspråk.
2. Markera den princip som du vill redigera.
3. I informationsfönstret under Appar **och tjänster väljer** du **Redigera.**
4. I fönstret **Program och** tjänster väljer du **en enskild** produkt eller Alla produkter i listrutan **Produkt.**
5. Markera eller avmarkera kryssrutorna för program och tjänster som du vill att användarna ska ha tillgång till eller inte.
6. När du är klar väljer du **Spara** och stänger informationsfönstret.

## <a name="change-the-assigning-order-for-backup-products"></a>Ändra tilldelningsordern för säkerhetskopieringsprodukter

Om du har säkerhetskopiera produkter tilldelade till principen kan du ändra i vilken ordning de används för att tilldela licenser när användare loggar in i programmet.

1. I administrationscentret går du  till sidan \> **Faktureringslicenser** och väljer sedan fliken <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Princip för automatiskt</a> anspråk.
2. Markera den princip som du vill redigera.
3. I informationsfönstret, i **avsnittet** Produktlicenser, markerar du rutan bredvid den produkt som du vill flytta och väljer sedan **Flytta upp** eller Flytta **ned.**
4. Upprepa steg 3 för varje produkt som du vill beställa om.
5. När du är klar med beställningen av produkterna väljer du **Spara för** att stänga informationsfönstret.

## <a name="view-an-auto-claim-policy-report"></a>Visa en principrapport för automatiskt anspråk

1. I administrationscentret går du  till sidan \> **Faktureringslicenser** och väljer sedan fliken <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Princip för automatiskt</a> anspråk.
2. Välj **Visa rapport**. På **sidan Principrapport för automatiskt anspråk** visas alla licenser som tilldelats från varje princip under de senaste 90 dagarna. Som standard visas de senaste 90 dagarna på sidan.
3. Om du vill ändra tidsperioden som visas väljer du listrutan Senaste **30** dagarna. Du kan visa rapporter för de senaste 1, 7, 30 och 90 dagarna.

## <a name="next-steps"></a>Nästa steg

Du kan med jämna mellanrum gå tillbaka till **policyfliken Automatiskt** anspråk för att visa en lista över användare som har påstådda licenser enligt de principer du skapat.

## <a name="related-content"></a>Relaterat innehåll

[Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md) (artikel)\
[Köpa eller ta bort prenumerationslicenser](buy-licenses.md) (artikel)\
[Förstå prenumerationer och licenser](subscriptions-and-licenses.md) (artikel)