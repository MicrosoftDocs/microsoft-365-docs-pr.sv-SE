---
title: Fästa appar i användarnas startprogram
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Som global administratör kan du fästa upp till tre program i användarnas startprogram.
ms.openlocfilehash: 965fcbbb3f0e22074e3f6c5476d65ade98fea94c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915224"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Fästa appar i användarnas startprogram

Du kan använda kontroller i Azure Active Directory-portalen för att fästa upp till tre program i Office.com och startprogrammet för alla användare i organisationen. Du kan också ordna grupper med program. Alla appar som du lägger till kan när som helst tas bort av användaren. Om du vill fästa ett program för användarna måste du vara molnprogramsadministratör eller programadministratör i Azure Active Directory eller global administratör i Office 365. Mer information om administratörsroller finns i [administratörsroller i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) och [administratörsroller i Microsoft 365.](../add-users/about-admin-roles.md) 

Mer information om startprogrammet och Office.com finns [](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) i möt startprogrammet och uppdateringar av office.com och bloggartikeln [om Office 365-startprogrammet.](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Fästa appar med Azure Active Directory-portalen

1. Gå till administrationscentret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .
2. I det vänstra navigeringsfältet **väljer du Visa alla** och under **Administratörscentra** väljer du **Azure Active Directory**.
3. Välj **Användarinställningar för** företagsprogram **i** Azure Active  >  **Directory**.
4. I avsnittet **Office 365-inställningar** väljer du Lägg **till program.**
5. Välj de program som du vill fästa i användarnas startprogram och välj sedan Lägg **till.**

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365-inställningar för att fästa appar.":::

### <a name="pin-a-custom-app"></a>Fästa ett anpassat program

> [!NOTE]
> Användargränssnittet anger om du behöver köpa ytterligare Azure AD-licenser för att använda den här funktionen. Mer information finns i [Azure Active Directory-priser.](https://azure.microsoft.com/pricing/details/active-directory/)

1. I **Azure Active Directory** väljer du   >  **Företagsprogram Nytt** program högst upp på **sidan Alla** program.
2. På sidan **Lägg till ett** program väljer  du Program som inte **finns** i galleriet eller Skapa ett eget program om du använder förhandsversionen av Azure Active Directory. 
3. Skriv ett namn för programmet och tilldela sedan användare på **fliken Användare och** grupper.
4. Använd fliken **Egenskaper** för att ladda upp en ikon för programmet.
5. Om du vill tilldela en URL till appen väljer **du Linked på** fliken Enkel inloggning och anger sedan en URL-adress. 
6. Välj **Spara**.

## <a name="create-application-collections"></a>Skapa programsamlingar

Du kan också skapa programsamlingar för användarna i organisationen. Instruktioner finns i [Skapa samlingar på portalen Mina appar i Azure Portal.](/azure/active-directory/manage-apps/access-panel-collections)