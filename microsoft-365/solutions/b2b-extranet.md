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
description: Lär dig hur du skapar en B2B-extranätwebbplats eller ett B2B-team med hanterade gäster från en partnerorganisation.
ms.openlocfilehash: f9b8d9326f302233ed85c9d168fdf6f343dc6cbf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904762"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>Skapa ett B2B-extranät med hanterade gäster

Du kan använda [Azure Active Directory berättigandeshantering](/azure/active-directory/governance/entitlement-management-overview) för att skapa ett B2B-extranät för att samarbeta med en partnerorganisation som använder Azure Active Directory. På så sätt kan användarna registrera sig själva på extranätwebbplatsen eller i teamet och få åtkomst via ett arbetsflöde för godkännande.

Med den här metoden för att dela resurser för samarbete kan partnerorganisationen hjälpa till att underhålla och godkänna gästerna på slutet, vilket minskar IT-avdelningens belastning och gör att de som känner till samarbetsavtalet kan hantera användaråtkomst.

Den här artikeln går igenom stegen för att skapa ett resurspaket (i det här fallet en webbplats eller ett team) som du kan dela med en partnerorganisation via en självbetjäning för åtkomstregistrering. 

Innan du börjar skapar du den webbplats eller det team som du vill dela med partnerorganisationen och aktiverar den för gästdelning. Mer information [finns i Samarbeta med gäster](collaborate-in-site.md) på en webbplats eller Samarbeta med [gäster](collaborate-as-team.md) i ett team. Vi rekommenderar även [](create-secure-guest-sharing-environment.md) att du går igenom Skapa en säker gästdelningsmiljö för information om säkerhets- och efterlevnadsfunktioner som du kan använda för att bevara dina styrningsprinciper när du samarbetar med gäster.

## <a name="license-requirements"></a>Licenskrav

Om du använder den här funktionen krävs en Azure AD Premium P2-licens. 

Specialiserade moln, till exempel Azure Germany och Azure China 21Vianet, är för närvarande inte tillgängliga för användning.

## <a name="video-demonstration"></a>Videodemonstration

Den här videon visar hur man går till i den här artikeln.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>Anslut partnerorganisationen

Om du vill bjuda in gäster från en partnerorganisation måste du lägga till partnerdomänen som en ansluten organisation i Azure Active Directory.

Så här lägger du till en ansluten organisation
1. Klicka [på Identitetsstyrning](https://aad.portal.azure.com)i Azure Active **Directory.**
2. Klicka **på Anslutna organisationer.**
4. Klicka **på Lägg till ansluten organisation.**
5. Skriv ett namn och en beskrivning för organisationen och klicka sedan på **Nästa: Katalog + domän.**
6. Klicka **på Lägg till katalog + domän.**
7. Ange domänen för den organisation som du vill ansluta till och klicka sedan på Lägg **till**.
8. Klicka **på Anslut** och sedan på **Nästa: Sponsorer.**
9. Lägg till personer från organisationen eller organisationen som du ansluter till som du vill godkänna åtkomst för gäster.
10. Klicka **Nästa: Granska + Skapa**.
11. Granska de inställningar som du har valt och klicka sedan på **Skapa**.

    ![Skärmbild av sidan anslutna organisationer i Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>Välj resurser att dela

Det första steget när du väljer resurser att dela med en partnerorganisation är att skapa en katalog för att innehålla dem.

Så här skapar du en katalog
1. Klicka [på Identitetsstyrning](https://aad.portal.azure.com)i Azure Active **Directory.**
2. Klicka **på Kataloger.**
3. Klicka **på Ny katalog**.
4. Ange ett namn och en beskrivning för katalogen och kontrollera att **Både Aktiverad** och Aktiverad för **externa användare** är inställda på **Ja.**
5. Klicka på **Skapa**.

   ![Skärmbild av katalogsidan i Azure Active Directory-identitetsstyrning](../media/identity-governance-catalogs.png)

När katalogen har skapats lägger du till den SharePoint-webbplats eller det team som du vill dela med partnerorganisationen.

Lägga till resurser i en katalog
1. I Azure AD-identitetsstyrning **klickar du på Kataloger** och sedan på den katalog där du vill lägga till resurser.
2. Klicka **på Resurser** och sedan på Lägg till **resurser.**
3. Välj de team eller SharePoint-webbplatser som du vill inkludera i extranätet och klicka sedan på Lägg **till**.

   ![Skärmbild av sidan Katalogresurser i Azure Active Directory-identitetsstyrning](../media/identity-governance-catalog-resource.png)

När du har definierat vilka resurser du vill dela är nästa steg att skapa ett åtkomstpaket, som definierar vilken typ av åtkomst som partneranvändare beviljas och godkännandeprocessen för nya partneranvändare som begär åtkomst.

Skapa ett åtkomstpaket
1. I Azure AD-identitetsstyrning **klickar du på Kataloger** och sedan på den katalog där du vill skapa ett åtkomstpaket.
2. Klicka **på Access-paket** och klicka sedan på **Nytt åtkomstpaket**.
3. Skriv ett namn och en beskrivning för åtkomstpaketet och klicka sedan på **Nästa: Resursroller**.
4. Välj resurserna i katalogen som du vill använda för extranätet.
5. För varje resurs, i **kolumnen** Roll, väljer du den användarroll som du vill tilldela till gästerna som använder extranätet.
6. Klicka **på Nästa: Begäranden**.
7. Under **Användare som kan begära åtkomst** väljer du För användare som inte finns i **katalogen.**
8. Kontrollera att alternativet **Specifika anslutna organisationer** är markerat och klicka sedan på Lägg till **kataloger.**
9. Välj den anslutna organisationen du lägger till tidigare och klicka sedan på **Välj**
10. Under **Godkännande** väljer du **Ja för** **Kräv godkännande.**
11. Under **Förste godkännare** väljer du en av de huvudsponsorer som du lagt till tidigare eller väljer en viss användare.
12. Klicka **på Lägg till reserv** och välj en reserv godkännare.
13. Välj **Ja** under **Aktivera.**
14. Klicka **på Nästa: Livscykel.**
15. Välj inställningar för förfallotid och åtkomstgranskning som du vill använda och klicka sedan på **Nästa: Granska + Skapa.**
16. Granska inställningarna och klicka sedan på **Skapa**.

    ![Skärmbild av skärmen åtkomstpaket i Azure Active Directory-identitetsstyrning](../media/identity-governance-access-packages.png)

Om du samarbetar med en stor organisation kanske du vill dölja åtkomstpaketet. Om paketet är dolt kommer användare i partnerorganisationen inte att se paketet på Min *Access-portalen.* I stället måste de skickas en direktlänk för att registrera sig för paketet. Genom att dölja åtkomstpaketet kan du minska antalet olämpliga åtkomstförfrågningar och även hålla tillgängliga åtkomstpaket organiserade i partnerorganisationens portal.

Så här anger du att ett åtkomstpaket ska vara dolt
1. I Azure AD Identity Governance klickar du **på Access-paket** och sedan på ditt åtkomstpaket.
2. Klicka på **Redigera** på sidan **Översikt.**
3. Under **Egenskaper** väljer du **Ja** för **Dolda** och klickar sedan på **Spara**.

   ![Skärmbild av skärmen med egenskaper för redigering av åtkomstpaket](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>Bjud in partneranvändare

Om du ställer in åtkomstpaketet på dolt måste du skicka en direktlänk till partnerorganisationen så att de kan begära åtkomst till din webbplats eller ditt team.

Så här hittar du länken till åtkomstportalen
1. I Azure AD Identity Governance klickar du **på Access-paket** och sedan på ditt åtkomstpaket.
2. På sidan **Översikt** klickar du på **Kopiera till Urklipp-länken** för länken **Min Access-portal.**

   ![Skärmbild av egenskaper för åtkomstpaket med länken till åtkomstportalen](../media/identity-governance-access-portal-link.png)

När du har kopierat länken kan du dela den med din kontakt på partnerorganisationen och de kan skicka den till användarna i deras samarbetsgrupp.

## <a name="see-also"></a>Se även

[Skapa en säker miljö för gästdelning](create-secure-guest-sharing-environment.md)