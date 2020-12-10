---
title: Skapa ett B2B-extranät med hanterade gäster
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Lär dig hur du skapar en webbplats eller ett B2B-team med hanterade gäster från en partner organisation.
ms.openlocfilehash: cfb7cc4310cb83f9ce7761c95f021724b7d75faf
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613602"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>Skapa ett B2B-extranät med hanterade gäster

Du kan använda [Azure Active Directory-hanteringen](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) för att skapa ett B2B-extra nät för att samar beta med en partner organisation som använder Azure Active Directory. Detta gör att användare själv kan registrera sig på extra nätet eller teamet och få åtkomst via ett arbets flöde för godkännande.

Med den här metoden för att dela resurser för samarbete kan partner organisationen hjälpa till att underhålla och godkänna gästerna, vilket minskar belastningen på IT-avdelningen och gör dem mest bekanta med samarbets avtalet för att hantera användar åtkomst.

Den här artikeln innehåller anvisningar för hur du skapar ett paket med resurser (i det här fallet en webbplats eller ett team) som du kan dela med en partner organisation via en självbetjänings registrerings modell. 

Innan du börjar ska du skapa en webbplats eller ett team som du vill dela med partner organisationen och aktivera den för gäst delning. Se [samar beta med gäster på en webbplats](collaborate-in-site.md) eller [samar beta med gäster i ett team](collaborate-as-team.md) för mer information. Vi rekommenderar också att du går igenom [skapa en säker gäst delnings miljö](create-secure-guest-sharing-environment.md) för information om säkerhets-och efterföljandekrav som du kan använda för att hjälpa till att underhålla dina styrnings principer när du samarbetar med gäster.

## <a name="license-requirements"></a>Licens krav

För att använda den här funktionen krävs en Azure AD Premium P2-licens. 

Specialiserade moln, till exempel Azure Germany och Azure Kina 21Vianet, är för närvarande inte tillgängliga för användning.

## <a name="video-demonstration"></a>Videodemonstration

Den här videon visar de procedurer som beskrivs i den här artikeln.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>Ansluta partner organisationen

För att kunna bjuda in gäster från en partner organisation måste du lägga till partners domän som ansluten organisation i Azure Active Directory.

Lägga till en ansluten organisation
1. Klicka på **identitets styrning** i [Azure Active Directory](https://aad.portal.azure.com).
2. Klicka på **anslutna organisationer**.
4. Klicka på **Lägg till ansluten organisation**.
5. Ange ett namn och en beskrivning för organisationen och klicka sedan på **Nästa: Katalog + domän**.
6. Klicka på **Lägg till katalog + domän**.
7. Skriv domänen för den organisation som du vill ansluta till och klicka sedan på **Lägg till**.
8. Klicka på **Anslut** och sedan på **Nästa: sponsorer**.
9. Lägg till personer från din organisation eller den organisation som du ansluter till och som du vill godkänna åtkomst för gäster.
10. Klicka på **Nästa: granska + skapa**.
11. Granska de inställningar du har valt och klicka sedan på **skapa**.

    ![Skärm bild av sidan anslutna organisationer i Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>Välj vilka resurser du vill dela

Det första steget när du väljer resurser som du vill dela med en partner organisation är att skapa en katalog som innehåller dem.

Skapa en katalog
1. Klicka på **identitets styrning** i [Azure Active Directory](https://aad.portal.azure.com).
2. Klicka på **kataloger**.
3. Klicka på **ny katalog**.
4. Ange ett namn och en beskrivning för katalogen och kontrol lera att **aktiverat** och **aktiverat för externa användare** båda är inställda på **Ja**.
5. Klicka på **Skapa**.

   ![Skärm bild av sidan kataloger i Azure Active Directory Identity styrelse](../media/identity-governance-catalogs.png)

När du har skapat katalogen lägger du till den SharePoint-webbplats eller det team som du vill dela med partner organisationen.

Lägga till resurser i en katalog
1. I Azure AD Identity styrelse klickar du på **kataloger** och sedan på den katalog där du vill lägga till resurser.
2. Klicka på **resurser** och sedan på **Lägg till resurser**.
3. Välj de team-eller SharePoint-webbplatser som du vill ta med i extra nätet och klicka sedan på **Lägg till**.

   ![Skärm bild av sidan katalog resurser i Azure Active Directory Identity styrelse](../media/identity-governance-catalog-resource.png)

När du har angett de resurser som du vill dela är nästa steg att skapa ett Access-paket, som definierar den typ av åtkomst som partner användare beviljar och godkännande processen för nya partner användare som begär åtkomst.

Så här skapar du ett Access-paket
1. I Azure AD Identity styrelse klickar du på **kataloger** och sedan på den katalog där du vill skapa ett Access-paket.
2. Klicka på **Access-paket** och sedan på **nytt Access-paket**.
3. Ange ett namn och en beskrivning för Access-paketet och klicka sedan på **Nästa: resurs roller**.
4. Välj de resurser från katalogen som du vill använda för extra nätet.
5. För varje resurs, i kolumnen **Role** , väljer du den användar roll du vill ge till gästerna som använder extra nätet.
6. Klicka på **Nästa: förfrågningar**.
7. Under **användare som kan begära åtkomst** väljer du **för användare som inte finns i katalogen**.
8. Kontrol lera att alternativet **specifika anslutna organisationer** är markerat och klicka sedan på **Lägg till kataloger**.
9. Välj den anslutna organisation du lägger till tidigare och klicka sedan på **Välj**
10. Under **godkännande** väljer du **Ja** för att **begära godkännande**.
11. Under den **första god kännaren** väljer du något av sponsorerna som du lade till tidigare eller väljer en specifik användare.
12. Klicka på **Lägg till reserv** och välj en reserv god kännare.
13. Under **Aktivera** väljer du **Ja**.
14. Klicka på **Nästa: livs cykel**.
15. Välj de inställningar för förfallo datum och åtkomst granskning du vill använda och klicka sedan på **Nästa: granska + skapa**.
16. Granska inställningarna och klicka sedan på **skapa**.

    ![Skärm bild av skärmen med åtkomst paket i Azure Active Directory-Identity styrelse](../media/identity-governance-access-packages.png)

Om du samarbetar med en stor organisation kanske du vill dölja Access-paketet. Om paketet är dolt kommer användare i partner organisationen inte att se paketet på sin *åtkomst* -Portal. I stället måste de skicka en direkt länk för att kunna registrera sig för paketet. Om du döljer Access-paketet kan du minska antalet olämpliga åtkomst begär Anden och du kan även hålla tillgängliga paket organiserade i partner organisationens Portal.

Så här anger du att ett Access-paket ska döljas
1. I Azure AD Identity styrelse klickar du på **Access-paket** och sedan på ditt Access-paket.
2. Klicka på **Redigera** på sidan **Översikt** .
3. Under **Egenskaper** väljer du **Ja** för **dold** och klickar sedan på **Spara**.

   ![Skärm bild av skärmen egenskaper för redigera Access-paket](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>Bjuda in partner användare

Om du anger att Access-paketet ska döljas måste du skicka en direkt länk till partner organisationen så att de kan begära åtkomst till webbplatsen eller teamet.

Så här hittar du Access Portal-länken
1. I Azure AD Identity styrelse klickar du på **Access-paket** och sedan på ditt Access-paket.
2. På sidan **Översikt** klickar du på **Kopiera till Urklipp** -länken för **länken My Access-portalen**.

   ![Skärm bild av egenskaper för Access-paket med åtkomst Portal länk](../media/identity-governance-access-portal-link.png)

När du har kopierat länken kan du dela den med din kontakt i partner organisationen och de kan skicka den till användarna i samarbets gruppen.

## <a name="see-also"></a>Se även

[Skapa en säker miljö för gästdelning](create-secure-guest-sharing-environment.md)
