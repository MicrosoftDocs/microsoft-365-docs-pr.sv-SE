---
title: Fästa appar i användarnas start program
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
description: Som global administratör kan du fästa upp till tre program i användarnas start program.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310881"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Fästa appar i användarnas start program

Du kan använda kontroller i Azure Active Directory-portalen för att fästa upp till tre appar till Office.com och Start programmet för alla användare i organisationen. Du kan också ordna program grupper. Alla appar du lägger till kan senare avgränsas av användaren när som helst. För att fästa en app för användarna måste du vara ett moln programs administratör eller program administratör i Azure Active Directory eller en global administratör i Office 365. Mer information om administratörs roller finns i [Administratörs roller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) -och [Administratörs roller i Microsoft 365](../add-users/about-admin-roles.md). 

Mer information om start ikonen och Office.com finns i [uppfylla start-startprogrammet](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) och [uppdateringar till office.com och Office 365-programmet starta](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blogg inlägg.

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Använda Azure Active Directory-portalen för att fästa appar

1. Gå till administrations centret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .
2. I det vänstra navigerings fältet väljer du **Visa alla**och under **administrations Center**väljer du **Azure Active Directory**.
3. I **Azure Active Directory**väljer du inställningar för **företags program**  >  **User settings**.
4. I avsnittet **Inställningar för Office 365** väljer du **Lägg till program**.
5. Välj de program som du vill fästa i användarnas start program och välj sedan **Lägg till**.

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365-inställningar för att fästa appar.":::

### <a name="pin-a-custom-app"></a>Fäst en egen app

> [!NOTE]
> Användar gränssnittet anger om du behöver köpa fler Azure AD-licenser för att använda den här funktionen. Mer information finns i [Azure Active Directory-priser](https://azure.microsoft.com/pricing/details/active-directory/).

1. I **Azure Active Directory**väljer du **företags program**  >  **nytt program** högst upp på sidan **alla program** .
2. På sidan **Lägg till ett program** väljer du **icke-galleriprogram** eller **skapar ett eget program** om du befinner dig i för hands versionen av Azure Active Directory. 
3. Ange ett namn för programmet och sedan tilldela användare på fliken **användare och grupper** .
4. Använd fliken **Egenskaper** för att ladda upp en ikon för appen.
5. Om du vill tilldela en URL till programmet går du till fliken **enkel inloggning** och väljer **länkat** och anger sedan en URL.
6. Välj **Save**.

## <a name="create-application-collections"></a>Skapa program samlingar

Du kan också skapa program samlingar för användarna i organisationen. Instruktioner finns i [skapa samlingar på portalen mina program i Azure-portalen](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).