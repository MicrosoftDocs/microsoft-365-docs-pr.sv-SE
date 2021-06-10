---
title: Fästa appar i användarnas startprogram
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Som global administratör kan du fästa upp till tre program i användarnas startprogram.
ms.openlocfilehash: 786368f1236c7a86a6fbd0dd863ad0296cb65fac
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579272"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Fästa appar i användarnas startprogram

Du kan använda kontroller i Azure Active Directory-portalen för att fästa upp till tre appar på Office.com och i startprogrammet för alla användare i organisationen. Du kan också ordna grupper med program. Alla appar som du lägger till kan när som helst tas bort av användaren. Om du vill fästa ett program för dina användare måste du vara molnprogramsadministratör eller programadministratör i Azure Active Directory eller global administratör i Office 365. Mer information om administratörsroller finns i [administratörsroller i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) [och administratörsroller i Microsoft 365](../add-users/about-admin-roles.md). 

Mer information om startprogrammet och Office.com finns [](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) i Möt startprogrammet och uppdateringar av [office.com och bloggartikeln om](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) Office 365-startprogrammet.

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Använda Azure Active Directory för att fästa appar

1. Gå till Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> administrationscenter.
2. I det vänstra navigeringsfältet **väljer du Visa** alla och under **Administrationscenter** väljer **du Azure Active Directory**.
3. I **Azure Active Directory** väljer du **Användarinställningar för**  >  **företagsprogram.**
4. I avsnittet **Office 365 Inställningar** du Lägg **till program**.
5. Välj de program som du vill fästa i användarnas startprogram och välj sedan Lägg **till.**

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365 för att fästa appar.":::

### <a name="pin-a-custom-app"></a>Fästa ett anpassat program

> [!NOTE]
> Användargränssnittet anger om du behöver köpa ytterligare Azure AD-licenser för att använda den här funktionen. Mer information finns i [Azure Active Directory priser.](https://azure.microsoft.com/pricing/details/active-directory/)

1. I **Azure Active Directory** väljer du   >  **Företagsprogram Nytt** program högst upp på **sidan Alla** program.
2. På sidan **Lägg till ett** program väljer du **Icke-galleriprogram** **eller** Skapa ett eget program om du är i förhandsgranskningsversionen av Azure Active Directory. 
3. Skriv ett namn för programmet och tilldela sedan användare på **fliken Användare och** grupper.
4. Använd fliken **Egenskaper** för att ladda upp en ikon för programmet.
5. Om du vill tilldela en URL till appen väljer **du Linked på** fliken Enkel inloggning och anger sedan en URL-adress. 
6. Välj **Spara**.

## <a name="create-application-collections"></a>Skapa programsamlingar

Du kan också skapa programsamlingar för användarna i organisationen. Instruktioner finns i [Skapa samlingar på portalen Mina appar i Azure Portal.](/azure/active-directory/manage-apps/access-panel-collections)