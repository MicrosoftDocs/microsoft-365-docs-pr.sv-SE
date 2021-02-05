---
title: Lägga till lagringsutrymme för din prenumeration
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
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Lär dig hur du lägger till och minskar fillagringen i Microsoft 365-prenumerationen. Med extra fillagring kan du lagra mer innehåll i SharePoint Online och OneDrive.
ms.date: ''
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114913"
---
# <a name="add-storage-space-for-your-subscription"></a>Lägga till lagringsutrymme för din prenumeration

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Om du börjar få slut på lagringsutrymme för webbplatssamlingar i SharePoint Online kan du lägga till lagringsutrymme för din prenumeration om prenumerationen är berättigad till det. Om du inte ser **Office 365 Extra** fillagring i listan med tillgängliga tillägg innebär det att ditt abonnemang inte är berättigande. Mer information finns i [Är mitt abonnemang berättigande?](#is-my-plan-eligible-for-office-365-extra-file-storage)

> [!NOTE]
> Om du har köpt prenumerationen via volymlicensiering eller en molntjänst kan du inte köpa **Office 365 extra** fillagring för din organisation direkt från Microsoft. Kontakta din representant eller partner för att få hjälp.

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara global administratör eller SharePoint-administratör för att kunna utföra uppgifterna i den här artikeln. Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).

## <a name="view-available-storage"></a>Visa tillgängligt lagringsutrymme

::: moniker range="o365-worldwide"

1. Gå till sidan Aktiva webbplatser <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank"></a> i administrationscentret för SharePoint och logga in med ett konto som har [administratörsbehörighet](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) för din organisation.

2. Uppe till höger på sidan ser du hur mycket lagringsutrymme som används på alla webbplatser och det totala lagringsutrymmet för din prenumeration. Om organisationen har konfigurerat Multi-Geo i Office 365 visar fältet också hur mycket lagringsutrymme som används för alla geoplatser.

   ![Lagringsfält på sidan Aktiva webbplatser](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > Använt lagringsutrymme inkluderar inte ändringar som gjorts under de senaste 24–48 timmarna.

::: moniker-end

::: moniker range="o365-germany"

1. Logga in som https://portal.office.de global administratör eller SharePoint-administratör och välj sedan administratörspanelen för att öppna administrationscentret. Om ett meddelande visas om att du inte har behörighet att komma åt sidan betyder det att du inte har Administratörsbehörigheter för Microsoft 365 i din organisation.

2. Välj SharePoint i den **vänstra rutan under** **Administrationscenter.** Om det klassiska administrationscentret för  SharePoint visas väljer du Öppna nu högst upp på sidan för att öppna det nya administrationscentret för SharePoint.

3. Välj Aktiva webbplatser i den vänstra rutan i det nya administrationscentret **för** SharePoint.

4. Uppe till höger på sidan ser du hur mycket lagringsutrymme som används på alla webbplatser och det totala lagringsutrymmet för din prenumeration.

   ![Lagringsfält på sidan Aktiva webbplatser](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > Använt lagringsutrymme inkluderar inte ändringar som gjorts under de senaste 24–48 timmarna.

::: moniker-end

::: moniker range="o365-21vianet"

1. Logga in som https://login.partner.microsoftonline.cn/ global administratör eller SharePoint-administratör och välj sedan administratörspanelen för att öppna administrationscentret. (Om ett meddelande visas om att du inte har behörighet att komma åt sidan betyder det att du inte har Administratörsbehörigheter för Microsoft 365 i din organisation.

2. Välj SharePoint i den **vänstra rutan under** **Administrationscenter.** Om det klassiska administrationscentret för  SharePoint visas väljer du Öppna nu högst upp på sidan för att öppna det nya administrationscentret för SharePoint.

3. Välj Aktiva webbplatser i den vänstra rutan i det nya administrationscentret **för** SharePoint.

4. Uppe till höger på sidan ser du hur mycket lagringsutrymme som används på alla webbplatser och det totala lagringsutrymmet för din prenumeration.  

   ![Lagringsfält på sidan Aktiva webbplatser](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > Använt lagringsutrymme inkluderar inte ändringar som gjorts under de senaste 24–48 timmarna.

::: moniker-end

När du har fastställt hur mycket lagringsutrymme du använder kan du lägga till eller ta bort lagringsutrymme för din prenumeration. Följ stegen i den här artikeln om du vill ta reda på hur mycket det kostar att lägga till lagringsutrymme och kontrollera prisinformationen innan köpet.
  
Information om hur du anger lagringsgränser för webbplatssamlingar finns i [Hantera lagringsgränser för webbplatssamlingar](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).
  
## <a name="add-storage-to-your-subscription"></a>Lägga till lagring i din prenumeration

Om du ännu inte har köpt extra lagringsutrymme för prenumerationen kan du göra det.

::: moniker range="o365-worldwide"

1. Gå till sidan Faktureringsköpstjänster  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">i administrationscentret.</a>
2. Välj Tillägg **längst ned** på sidan **Köptjänster.**
3. Välj **Office 365 extra fillagring.**
4. På sidan Extra fillagring i **Office 365** väljer du basprenumerationen och anger sedan hur många GB lagringsutrymme du vill lägga till.
5. Välj **Gå till checka ut nu.**
6. På sidan **Hur ser det ut?** kontrollerar du antalet gigabyte lagringsutrymme du har valt, kontrollerar prisinformationen och väljer **sedan Nästa.**
7. Verifiera **summan på** sidan Slutför order. Om du behöver göra några ändringar väljer du **Redigera ordning.** Om ordern kräver en kreditkontroll markerar du kryssrutan. När du är klar väljer du Lägg **order gå** \> **till administrationscentrets start.**

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan Faktureringsprenumerationer  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">i administrationscentret.</a>  

2. På **sidan** Prenumerationer väljer du den prenumeration där du vill lägga till lagringsutrymme och väljer **sedan Tillägg.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Om inga tillägg visas och prenumerationen har **köpts** via en partner väljer du **Volume Licensing Service Center (VLSC).**
  
3. Välj **Köp tillägg.**

    ![Länken Köp tillägg på sidan Prenumerationer i administrationscentret.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. På sidan **Köptjänster** för du muspekaren över eller **trycker på Office 365 Extra** fillagring och väljer sedan Köp **nu.**
  
5. Ange antalet användarlicenser du behöver och, om det visas, välj en basprenumeration. Välj **Gå till checka ut nu.**
  
6. På sidan **Hur ser det ut?** kontrollerar du antalet gigabyte lagringsutrymme du har valt, kontrollerar prisinformationen och väljer **sedan Nästa.**

7. Välj **Lägg order på** sidan **Slutför order.**

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.

2. På **sidan** Prenumerationer väljer du den prenumeration där du vill lägga till lagringsutrymme och väljer **sedan Tillägg.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Om inga tillägg visas och prenumerationen har **köpts** via en partner väljer du **Volume Licensing Service Center (VLSC).**
  
3. Välj **Köp tillägg.**

    ![Länken Köp tillägg på sidan Prenumerationer i administrationscentret.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. På sidan **Köptjänster** för du muspekaren över eller **trycker på Office 365 Extra** fillagring och väljer sedan Köp **nu.**
  
5. Ange antalet användarlicenser du behöver och, om det visas, välj en basprenumeration. Välj **Gå till checka ut nu.**
  
6. På sidan **Hur ser det ut?** kontrollerar du antalet gigabyte lagringsutrymme du har valt, kontrollerar prisinformationen och väljer **sedan Nästa.**

7. Välj **Lägg order på** sidan **Slutför order.**

::: moniker-end

## <a name="increase-or-decrease-storage"></a>Öka eller minska lagringsutrymme

Om du redan har köpt extra lagringsutrymme via tillägget **Office 365 extra** fillagring kan du använda de här stegen till att öka eller minska det extra lagringsutrymmet för din prenumeration. Du kan minska lagringsutrymmet till så lite som 1 GIGABYTE. Kontakta support om du vill ta bort allt [extra lagringsutrymme.](../admin/contact-support-for-business-products.md)

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.
2. På fliken **Produkter** väljer du den prenumeration som innehåller **tillägget Office 365 extra fillagring.**
3. Välj Hantera tillägg i **avsnittet Tillägg på sidan** **Produktinformation.**
4. I fönstret **Hantera tillägg väljer** du  **Office 365 Extra fillagring i listan Tillägg.**
5. I **textrutan** Antal anger du antalet GBS lagringsutrymme som du vill använda för prenumerationen.
6. Välj **Spara**.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.

2. Välj  Tillägg på **sidan Prenumerationer.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Om inga tillägg visas och prenumerationen har **köpts** via en partner väljer du **Volume Licensing Service Center (VLSC).**
  
3. Välj **Ändra antal under Office 365 Extra** **fillagring.**

    ![Länken Ändra antal.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. I det högra fönstret anger du det totala antalet GIGABYTE du behöver och väljer sedan **Skicka.**

    Om du för närvarande till exempel har 200 GB extra lagringsutrymme men bara behöver 100 GB ska du ange **100** i rutan.

5. Välj **Stäng**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.

2. Välj **Tillägg** på **sidan Prenumerationer.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Om inga tillägg visas och prenumerationen har **köpts** via en partner väljer du **Volume Licensing Service Center (VLSC).**
  
3. Välj **Ändra antal under Office 365 Extra** **fillagring.**

    ![Länken Ändra antal.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. I det högra fönstret anger du det totala antalet GIGABYTE du behöver och väljer sedan **Skicka.**

    Om du för närvarande till exempel har 200 GB extra lagringsutrymme men bara behöver 100 GB ska du ange **100** i rutan.

5. Välj **Stäng**.

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a>Berättigar mitt abonnemang till Office 365 extra fillagring?

Office 365 extra fillagring är tillgängligt för följande prenumerationer:
  
- Office 365 Enterprise E1

- Office 365 Enterprise, E2

- Office 365 Enterprise, E3

- Office 365 Enterprise E4

- Office 365 Enterprise E5

- Office för webben med SharePoint abonnemang 1

- Office för webben med SharePoint abonnemang 2

- SharePoint Online (abonnemang 1)

- SharePoint Online (abonnemang 2)

- Microsoft 365 Business Basic

- Microsoft 365 Business Standard

- Microsoft 365 Business Premium

- Microsoft 365 E3

- Microsoft 365 E5

- Microsoft 365 F1

> [!NOTE]
> Office 365 Extra fillagring är också tillgängligt för GCC-, GCC High- och DOD-abonnemang.

## <a name="related-content"></a>Relaterat innehåll

[Hantera lagringsgränser för webbplatser](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (artikel)\
[Ange standardlagringsutrymme för OneDrive-användare](https://docs.microsoft.com/onedrive/set-default-storage-space)(artikel)
