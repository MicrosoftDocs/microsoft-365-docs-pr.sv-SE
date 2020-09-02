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
description: Lär dig hur du lägger till och minskar fil lagringen i Microsoft 365-prenumerationen. Med extra fil lagring kan du lagra mer innehåll i SharePoint Online och OneDrive.
ms.date: ''
ms.openlocfilehash: 7f9973054bfe97beae36e28b73a3eb2025a13e73
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324474"
---
# <a name="add-storage-space-for-your-subscription"></a>Lägga till lagringsutrymme för din prenumeration

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Om du börjar få slut på lagringsutrymme för webbplatssamlingar i SharePoint Online kan du lägga till lagringsutrymme för din prenumeration om prenumerationen är berättigad till det. Om du inte ser **Office 365 extra File Storage** i listan med tillgängliga tillägg innebär det att din plan inte är berättigad. Mer information finns i finns [Min plan-kvalificerare?](#is-my-plan-eligible-for-office-365-extra-file-storage)

> [!NOTE]
> Om du har köpt ditt abonnemang via volym licensiering eller en KRYPTOGRAFIPROVIDER kan du inte köpa **Office 365 extra fil lagring** för organisationen direkt från Microsoft. Kontakta din representant eller partner för hjälp.

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara global eller SharePoint-administratör för att utföra åtgärderna i den här artikeln. Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).

## <a name="view-available-storage"></a>Visa tillgängligt lagrings utrymme

::: moniker range="o365-worldwide"

1. Gå till sidan <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">aktiva webbplatser</a> i administrations centret för SharePoint och logga in med ett konto som har [Administratörs behörigheter](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) för din organisation.

2. I det övre högra hörnet på sidan kan du se hur mycket lagrings utrymme som används för alla webbplatser och det totala lagrings utrymmet för din prenumeration. Om organisationen har konfigurerat multi-geo i Office 365, visar fältet även mängden lagrings utrymme som används för alla geo-platser.

   ![Fältet lagring på sidan aktiva webbplatser](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > Det lagrings utrymme som används inkluderar inte ändringar gjorda inom de senaste 24-48 timmarna.

::: moniker-end

::: moniker range="o365-germany"

1. Logga in på https://portal.office.de som global eller SharePoint-administratör och välj sedan administratörs panelen för att öppna administrations centret. Om du ser ett meddelande om att du inte har behörighet att komma åt sidan innebär det att du inte har Microsoft 365-administratörs behörighet i organisationen.

2. I det vänstra fönstret, under **administrations Center**, väljer du **SharePoint**. Om det klassiska administrations centret för SharePoint visas väljer du **öppna det nu** högst upp på sidan för att öppna det nya administrations centret för SharePoint.

3. I det vänstra fönstret i det nya administrations centret för SharePoint väljer du **aktiva webbplatser**.

4. I det övre högra hörnet på sidan kan du se hur mycket lagrings utrymme som används för alla webbplatser och det totala lagrings utrymmet för din prenumeration.

   ![Fältet lagring på sidan aktiva webbplatser](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > Det lagrings utrymme som används inkluderar inte ändringar gjorda inom de senaste 24-48 timmarna.

::: moniker-end

::: moniker range="o365-21vianet"

1. Logga in på https://login.partner.microsoftonline.cn/ som global eller SharePoint-administratör och välj sedan administratörs panelen för att öppna administrations centret. (Om du ser ett meddelande om att du inte har behörighet att komma åt sidan innebär det att du inte har Microsoft 365-administratörs behörighet i organisationen.

2. I det vänstra fönstret, under **administrations Center**, väljer du **SharePoint**. Om det klassiska administrations centret för SharePoint visas väljer du **öppna det nu** högst upp på sidan för att öppna det nya administrations centret för SharePoint.

3. I det vänstra fönstret i det nya administrations centret för SharePoint väljer du **aktiva webbplatser**.

4. I det övre högra hörnet på sidan kan du se hur mycket lagrings utrymme som används för alla webbplatser och det totala lagrings utrymmet för din prenumeration.  

   ![Fältet lagring på sidan aktiva webbplatser](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > Det lagrings utrymme som används inkluderar inte ändringar gjorda inom de senaste 24-48 timmarna.

::: moniker-end

När du har fastställt hur mycket lagringsutrymme du använder kan du lägga till eller ta bort lagringsutrymme för din prenumeration. Följ stegen i den här artikeln om du vill ta reda på hur mycket det kostar att lägga till lagringsutrymme och kontrollera prisinformationen innan köpet.
  
Information om hur du anger lagringsgränser för webbplatssamlingar finns i [Hantera lagringsgränser för webbplatssamlingar](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).
  
## <a name="add-storage-to-your-subscription"></a>Lägga till lagrings utrymme i din prenumeration

Om du ännu inte har köpt ett extra lagrings utrymme för din prenumeration kan du göra det.

::: moniker range="o365-worldwide"

1. Gå till sidan fakturering i administrations centret **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> .
2. Välj **tillägg**längst ned på sidan **Köp tjänster** .
3. Välj **Office 365 extra fil lagring**.
4. På sidan **Office 365 extra File Storage** , om visas väljer du bas abonnemang och anger sedan det antal gigabyte av lagrings utrymme som du vill lägga till.
5. Välj **kolla ut nu**.
6. Kontrol lera hur många GB lagrings utrymme du har valt på sidan **Hur ser det ut?** **.**
7. På sidan **Complete order** kontrollerar du summan. Om du behöver göra några ändringar väljer du **Redigera order**. Om ordern kräver en kredit kontroll markerar du kryss rutan. När du är klar väljer du **Placera order** \> **gå till administratörens start sida**.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan **faktura** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">prenumerationer</a> i administrations centret.  

2. På sidan **prenumerationer** väljer du den prenumeration där du vill lägga till lagrings utrymme och väljer sedan **tillägg**.

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Om du inte ser **tillägg**och prenumerationen har köpts via en partner väljer du **Volume Licensing Service Center (VLSC)**.
  
3. Välj **köp tillägg**.

    ![Länken Köp tilläggs komponenter på sidan prenumerationer i administrations centret.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. På sidan **Köp tjänster** pekar du på eller trycker på **Office 365 extra fil lagring**och väljer sedan **Köp nu**.
  
5. Ange antalet användar licenser du behöver och välj en bas prenumeration om det visas. Välj **kolla ut nu**.
  
6. Kontrol lera hur många GB lagrings utrymme du har valt på sidan **Hur ser det ut?** **.**

7. På sidan **Complete order** väljer du **Lägg order**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.

2. På sidan **prenumerationer** väljer du den prenumeration där du vill lägga till lagrings utrymme och väljer sedan **tillägg**.

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Om du inte ser **tillägg**och prenumerationen har köpts via en partner väljer du **Volume Licensing Service Center (VLSC)**.
  
3. Välj **köp tillägg**.

    ![Länken Köp tilläggs komponenter på sidan prenumerationer i administrations centret.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. På sidan **Köp tjänster** pekar du på eller trycker på **Office 365 extra fil lagring**och väljer sedan **Köp nu**.
  
5. Ange antalet användar licenser du behöver och välj en bas prenumeration om det visas. Välj **kolla ut nu**.
  
6. Kontrol lera hur många GB lagrings utrymme du har valt på sidan **Hur ser det ut?** **.**

7. På sidan **Complete order** väljer du **Lägg order**.

::: moniker-end

## <a name="increase-or-decrease-storage"></a>Öka eller minska lagringsutrymme

Om du redan har köpt extra fil lagrings utrymme via **Office 365 extra File Storage** -tillägget kan du öka eller minska det extra lagrings utrymmet för ditt abonnemang genom att använda de här stegen. Du kan minska lagrings utrymmet till så lite som 1 gigabyte. [Kontakta supporten](../admin/contact-support-for-business-products.md)om du vill ta bort allt extra lagrings utrymme.

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.
2. På fliken **produkter** väljer du den prenumeration som innehåller tillägget **Office 365 extra fil lagring** .
3. På sidan Product details går du **till avsnittet tillägg** och väljer **Hantera tillägg**.
4. I fönstret **Hantera tillägg** väljer du **Office 365 extra fil lagring**i listan **tillägg** .
5. I text rutan **kvantitet** anger du antalet GBS som du vill använda för abonnemanget.
6. Välj **Spara**.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.

2. Välj **tillägg**på sidan **prenumerationer** .

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Om du inte ser **tillägg**och prenumerationen har köpts via en partner väljer du **Volume Licensing Service Center (VLSC)**.
  
3. Under **Office 365 extra fil lagring**väljer du **ändra antal**.

    ![Länken Ändra antal.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. I det högra fönstret anger du det totala antalet gigabyte du behöver och väljer sedan **Skicka**.

    Om du för närvarande till exempel har 200 GB extra lagringsutrymme men bara behöver 100 GB ska du ange **100** i rutan.

5. Välj **Stäng**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.

2. Välj **tillägg**på sidan **prenumerationer** .

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Om du inte ser **tillägg**och prenumerationen har köpts via en partner väljer du **Volume Licensing Service Center (VLSC)**.
  
3. Under **Office 365 extra fil lagring**väljer du **ändra antal**.

    ![Länken Ändra antal.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. I det högra fönstret anger du det totala antalet gigabyte du behöver och väljer sedan **Skicka**.

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
> Office 365 extra fil lagring är också tillgängligt för GCC-, GCC-och DOD-abonnemang.

## <a name="related-content"></a>Relaterat innehåll

[Hantera lagrings gränser för webbplatser](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (artikel) \
[Ange standard lagrings utrymme för OneDrive-användare](https://docs.microsoft.com/onedrive/set-default-storage-space)(artikel)
