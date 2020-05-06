---
title: Hantera registreringsprenumerationer för självbetjäning
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
search.appverid:
- MET150
description: Läs om hur du hanterar kostnadsfria registreringsprenumerationer för självbetjäning för din organisation.
ms.openlocfilehash: 46c77cb32fec4dfa1fb9c3d3f992bd842be1b969
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045267"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Hantera registreringsprenumerationer för självbetjäning

## <a name="what-are-self-service-sign-up-subscriptions"></a>Vad är självbetjäningsprenumerationer?

Det finns ett begränsat antal kostnadsfria registreringsprenumerationer för självbetjäning som användare i organisationen kan registrera sig för. En användare kan bara registrera sig för och använda en självbetjäningsprenumeration för sig själva. Dessa prenumerationer visas på sidan **Dina produkter,** markeras som **Kostnadsfria**och har en anteckning som säger: "Det här är en kostnadsfri prenumeration som aktiveras av användare i företaget." Du kan hantera självbetjäningsprenumerationer genom att blockera användare från att registrera sig och genom att ta bort kostnadsfria prenumerationer som användarna har registrerat sig för. Mer information om självbetjäningsanmäla och tillgängliga prenumerationer finns [i Använda självbetjäningsanmäla i organisationen](../../admin/misc/self-service-sign-up.md).

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>Hur skiljer sig dessa prenumerationer från självbetjäningsköpsprenumerationer?

Självbetjäningsprenumerationer är kostnadsfria och är tillgängliga för en större lista över produkter än självbetjäningsköpsprenumerationer. När en användare registrerar sig för en prenumeration på självbetjäningsköp ansvarar de för att betala för den. Prenumerationer på självbetjäningsköp är också endast tillgängliga för Power Platform-produkter (Power BI, Power Apps och Power Automate). Mer information finns i [Vanliga frågor och svar om självbetjäningsköp](self-service-purchase-faq.md).

## <a name="block-users-from-signing-up"></a>Blockera användare från att registrera sig

Du använder cmdleten [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) med parametern **AllowAdHocSubscriptions** för att styra om användare kan registrera sig för självbetjäningsanteckningsprenumerationer. Mer information finns i [Hur kontrollerar jag självbetjäningsinställningarna?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Ta bort en prenumeration på självbetjäningsanmälning

> [!IMPORTANT]
> När du tar bort en prenumeration för självbetjäningsanmälning blockerar du alla användare från att komma åt deras data och e-post och ta bort alla data och e-postmeddelanden.

1. Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Faktureringsprodukter</a> i administrationscentret. **Billing**
2. Hitta den självbetjäningsprenumeration som du vill ta bort. Välj **Ta bort prenumeration**i avsnittet Inställningar & **Åtgärder** .
3. Markera kryssrutan i fönstret **Ta bort prenumeration** och välj sedan Ta bort **prenumeration**.

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Jag har en självbetjäningsprenumeration som blockerar borttagning av katalog

De självbetjäningsannonsprodukter som enskilda användare kan registrera sig för skapar också en gästanvändare för autentisering i din Azure AD-katalog. För att undvika dataförlust blockerar dessa självbetjäningsprodukter katalogborttagningar tills de tas bort helt från katalogen. De kan bara tas bort av Azure AD-administratören. Mer information finns [i Ta bort en katalog i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).