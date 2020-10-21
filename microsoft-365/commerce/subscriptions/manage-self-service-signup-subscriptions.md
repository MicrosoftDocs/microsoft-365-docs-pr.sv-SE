---
title: Hantera abonnemang för självbetjäning
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Lär dig hur du hanterar kostnads fria abonnemang för självbetjäning för din organisation.
ms.openlocfilehash: fb70d0c40d4358abc227c8f6ff4a0e0dce1a7265
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48647837"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Hantera abonnemang för självbetjäning

## <a name="what-are-self-service-sign-up-subscriptions"></a>Vad är självbetjänings abonnemang?

Det finns ett begränsat antal kostnads fria registrerings abonnemang för självbetjäning som användare i organisationen kan registrera sig för. En användare kan bara registrera sig för och använda ett själv registrerings abonnemang för sig själva. Dessa abonnemang visas på sidan **produkter** , markeras som **ledigt**och har en kommentar om att "det här är ett kostnads fritt abonnemang som har Aktiver ATS av användare i företaget." Du kan hantera självbetjänings abonnemang genom att hindra användare från att registrera sig och genom att ta bort kostnads fria abonnemang som användare har registrerat sig för. Mer information om själv registrering och tillgängliga prenumerationer finns i [använda självbetjänings registrering i din organisation](../../admin/misc/self-service-sign-up.md).

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>Hur skiljer sig abonnemangen från självbetjänings abonnemanget?

Självbetjänings prenumerationer är gratis och finns tillgängliga i en större lista över produkter än abonnemang för egen service. När en användare registrerar sig för ett abonnemang för självbetjänings köp är de ansvarig för att betala för det. Dessutom är självbetjänings-och inköps abonnemang endast tillgängliga för Power Platform-produkter (Power BI, Power app och Power automatiserat). Mer information finns i [vanliga frågor och svar om inköp](self-service-purchase-faq.md).

## <a name="block-users-from-signing-up"></a>Blockera användare från att registrera sig

Du använder cmdleten [**set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) med parametern **AllowAdHocSubscriptions** för att kontrol lera om användare ska kunna registrera sig för självbetjänings inloggnings prenumerationer. Mer information finns i [Hur styr jag självbetjänings inställningar?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Ta bort ett själv registrerings abonnemang

> [!IMPORTANT]
> När du tar bort ett själv registrerings abonnemang hindrar du alla användare från att komma åt sina data och e-postmeddelanden och ta bort alla data och e-postmeddelanden.

1. Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .
2. Hitta själv registrerings prenumerationen som du vill ta bort. Välj **ta bort prenumeration**i avsnittet **Settings & Actions** .
3. Markera kryss rutan i fönstret **ta bort prenumeration** och välj sedan **ta bort abonnemang**.

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Jag har ett självbetjänings abonnemang som hindrar borttagning av kataloger

Självbetjänings-och registrerings produkter som enskilda användare kan registrera sig för och skapa en gäst användare för att verifiera i din Azure AD-katalog. För att undvika data förlust tar du bort de här själv tjänst produkterna tills de tas bort helt från katalogen. De kan bara tas bort av Azure AD-administratören. Mer information finns i [ta bort en katalog i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).