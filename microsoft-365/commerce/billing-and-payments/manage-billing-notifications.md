---
title: Hantera faktureringsaviseringar och fakturabilagor
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: prkalid, guyb
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
search.appverid:
- MET150
description: Lär dig hur du hanterar vilka som får e-postmeddelanden om faktureringsaviseringar och fakturabilagor.
ms.date: 03/17/2021
ms.openlocfilehash: d4083dc5a9d70eb8c20b4107389ec5fec65749ad
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332144"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a>Hantera faktureringsaviseringar och fakturabilagor

På **sidan Faktureringsaviseringar** kan du hantera vilka som får e-postmeddelanden om faktureringsaviseringar för din organisation. På sidan finns också alternativet för att få [din organisations fakturor som e-postbilagor.](#receive-your-organizations-invoices-as-email-attachments)

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara global administratör för att kunna göra det som beskrivs i den här artikeln. Faktureringsadministratörer kan göra en del av dessa ändringar, som nämnts i avsnitten nedan. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="change-the-language-you-receive-email-in"></a>Ändra det språk som du får e-post på

> [!NOTE]
> Faktureringsadministratörer kan också följa anvisningarna i det här avsnittet.

E-postmeddelanden om faktureringsaviseringar skickas på organisationens föredragna språk. Använd följande steg om du vill ändra önskat språk.

1. I Microsoft 365 administrationscenter går du till sidan   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Faktureringsfaktureringsaviseringar.</a>
2. Välj Redigera **aviseringsinställningar** i **avsnittet Inställningar för faktureringsaviseringar.**
3. I fönstret Inställningar för faktureringsaviseringar under **Önskat** språk väljer du det språk du vill använda och väljer sedan **Spara**. 

## <a name="change-who-receives-billing-notifications"></a>Ändra vem som får faktureringsaviseringar

Din organisations faktureringsaviseringar skickas till den primära och alternativa e-postadressen för varje global administratör och faktureringsadministratör. Gör så här om du vill ändra vilka användare som har rollen Global administratör eller Faktureringsadministratör.

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a>Tilldela administratörsroller med hjälp av sidan Faktureringsaviseringar

1. Gå till sidan **Fakturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Faktureringsmeddelanden</a> i administrationscentret.
2. I avsnittet Administratörer som tar emot faktureringsaviseringar väljer du **länken** **Faktureringsadministratör** eller **Global** administratör i beskrivningstexten.
3. På fliken Tilldelade administratörer i den **högra rutan väljer** du Lägg **till**.
4. I fönstret **Lägg till** administratörer skriver du in användarens visningsnamn eller användarnamn och väljer användaren i listan med förslag.
5. Lägg till flera användare tills du är klar.
6. Välj **Spara**. Användaren läggs till i listan över tilldelade administratörer.

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a>Ta bort administratörsroller med hjälp av sidan Faktureringsaviseringar

1. Gå till sidan **Fakturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Faktureringsmeddelanden</a> i administrationscentret.
2. I avsnittet Administratörer som tar emot faktureringsaviseringar väljer du **länken** **Faktureringsadministratör** eller **Global** administratör i beskrivningstexten.
3. I den högra rutan, på **fliken Tilldelade administratörer, väljer** du de användare du vill ta bort från rollen och väljer sedan Ta **bort.**
4. Välj Ta bort i **bekräftelserutan.** Användaren tas bort från listan med tilldelade administratörer.

## <a name="change-the-email-addresses-for-admins"></a>Ändra administratörers e-postadresser

Gör så här om du vill ändra den primära och alternativa e-postadressen till andra administratörer i organisationen:

> [!NOTE]
> Faktureringsadministratörer kan ändra sina egna primära och alternativa e-postadresser, men inte för andra administratörer.

1. Gå till sidan **Fakturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Faktureringsmeddelanden</a> i administrationscentret.
2. Välj **ett namn i avsnittet Administratörer som** tar emot faktureringsaviseringar.
3. I det högra fönstret lägger du till eller uppdaterar den primära och alternativa e-postadressen efter behov och väljer **sedan Spara**.

## <a name="change-your-organizations-contact-email"></a>Ändra organisationens kontakt-e-postadress

Förutom dina globala administratörer och faktureringsadministratörer skickar vi faktureringsaviseringar till din organisations kontakt-e-postadress. Använd följande steg om du vill ändra e-postadressen.

1. Gå till sidan **Fakturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Faktureringsmeddelanden</a> i administrationscentret.
2. Under **Organisationskontakt som tar emot faktureringsaviseringar** väljer du organisationskontakten.
3. I det högra fönstret skriver du den e-postadress som du vill använda och väljer sedan **Spara**.

## <a name="receive-your-organizations-invoices-as-email-attachments"></a>Ta emot din organisations fakturor som e-postbilagor

> [!NOTE]
> Faktureringsadministratörer kan också följa anvisningarna i det här avsnittet.

Du kan bifoga en kopia av organisationens faktura som en PDF-fil för att få fakturaaviseringar via e-post när en ny faktura är klar. Använd följande steg för att ta emot fakturor som bifogade filer.

1. Gå till sidan **Fakturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Faktureringsmeddelanden</a> i administrationscentret.
2. Under **Inställningar för faktureringsavisering** väljer **du Redigera aviseringsinställningar**.
3. I fönstret **Inställningar för faktureringsaviseringar,** under Bifoga en **PDF-fil** till dina fakturameddelanden, markerar du kryssrutan och väljer sedan **Spara**.

Om du inte vill ta emot fakturans bifogade fil när som helst följer du stegen ovan och avmarkerar kryssrutan Bifoga en **PDF-fil** till dina fakturameddelanden i steg 3.

## <a name="what-if-i-have-a-billing-profile"></a>Vad händer om jag har en faktureringsprofil?

Om du har en faktureringsprofil kan vissa av stegen som beskrivs i den här artikeln vara lite annorlunda för vissa av dina prenumerationer. I det här avsnittet beskrivs skillnaderna. [Hur vet jag om jag har en faktureringsprofil?](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a>Vem faktureringsaviseringar?

E-postmeddelanden om faktureringsaviseringar skickas till de primära och alternativa e-postadresserna för användare som har tilldelats någon av följande roller:

- Faktureringsprofilägare
- Deltagare i faktureringsprofil
- Fakturaansvarig

Mer information om faktureringsprofilroller och hur du hanterar dem finns i Förstå [administrativa roller i Microsoft Customer Agreement i Azure.](/azure/cost-management-billing/manage/understand-mca-roles)

Om du vill ändra vem som får organisationens faktureringsaviseringar använder du följande steg för att ändra de roller som användare tilldelats.

1. I administrationscentret går du till sidan  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Faktureringsfakturor & betalningar.</a>
2. Välj **en faktureringsprofil** på fliken Faktureringsprofil.
3. I avsnittet **Faktureringsprofilroller** tilldelar eller tar du bort roller för **faktureringsprofilägare,** **faktureringsprofilsdeltagare** eller **fakturahanterare.**

### <a name="receive-invoices-as-email-attachments"></a>Ta emot fakturor som e-postbilagor

Om du vill få dina fakturor som bifogade filer i dina fakturaaviseringar använder du följande steg för att aktivera den här inställningen för en viss faktureringsprofil.

1. I administrationscentret går du till sidan  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Faktureringsfakturor & betalningar.</a>
2. Välj fliken **Faktureringsprofiler** och välj sedan en faktureringsprofil i listan.
3. På sidan med faktureringsprofilinformation under **Hämta fakturor i e-postbilagor** ändrar du växlingsknappen till **På**.

## <a name="related-content"></a>Relaterat innehåll

[Visa din räkning eller faktura](view-your-bill-or-invoice.md) (artikel)\
[Förstå din faktura för Microsoft 365 för företag](understand-your-invoice2.md) (artikel)\
[Lägga till användare och tilldela licenser samtidigt](../../admin/add-users/add-users.md) (artikel)
