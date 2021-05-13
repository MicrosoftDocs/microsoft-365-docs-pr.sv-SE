---
title: Hantera prenumerationer på självbetjäning
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Lär dig hur du hanterar kostnadsfria registreringsprenumerationer för självbetjäning för din organisation.
ms.date: 03/17/2021
ms.openlocfilehash: 9c29d36ff28e312fa3782b60f89fa755d4df9bf3
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345136"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Hantera prenumerationer på självbetjäning

## <a name="what-are-self-service-sign-up-subscriptions"></a>Vad är självbetjäning för registrering av prenumerationer?

Det finns ett begränsat antal kostnadsfria registreringsprenumerationer på självbetjäning som användarna i organisationen kan registrera sig för. En användare kan bara registrera sig själv och använda en självbetjäningsprenumeration. Du hanterar prenumerationer på registrering via självbetjäning genom att blockera användare från att registrera sig och genom att ta bort kostnadsfria prenumerationer som användare har registrerat sig för. Mer information om självbetjäning för registrering och tillgängliga prenumerationer finns i Registrera [dig med självbetjäning i din organisation.](../../admin/misc/self-service-sign-up.md)

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>Visa en lista över självbetjäning för registrering av prenumerationer

1. I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.
2. På fliken **Produkter** väljer du filterikonen och sedan **Gratis**. En lista med alla prenumerationer på självbetjäning visas.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>Hur skiljer sig de här prenumerationerna från prenumerationer på självbetjäning?

Självbetjäning för registrering av prenumerationer är kostnadsfria och är tillgängliga för en större lista med produkter än prenumerationer för självbetjäning. När en användare registrerar sig för en prenumeration på självbetjäning är de ansvariga för att betala för den. Prenumerationer på självbetjäning är endast tillgängliga för Power Platform-produkter (Power BI, Power Apps och Power Automate), Project och Visio. Mer information finns i Vanliga frågor [och svar om självbetjäning för köp.](self-service-purchase-faq.md)

## <a name="block-users-from-signing-up"></a>Blockera användare från att registrera sig

Du använder cmdleten [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) med parametern **AllowAdHocSubscriptions** för att styra om användare kan registrera sig för självbetjäningsprenumerationer. Mer information finns i [Hur styr jag självbetjäningsuppgifter?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Ta bort en prenumeration med självbetjäning

> [!IMPORTANT]
> När du tar bort en prenumeration på självbetjäning blockerar du alla användare från att komma åt sina data och sin e-post och ta bort alla data och e-post.

1. I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.
2. På fliken **Produkter** väljer du filterikonen och sedan **Gratis**.
3. Välj den självbetjäning för registrering av prenumeration som du vill ta bort. 
4. Välj Ta bort prenumeration i avsnittet Prenumerationer **och betalningsinställningar på** sidan **prenumerationsinformation.**
5. I fönstret **Ta bort** prenumeration markerar du kryssrutan och väljer sedan Ta **bort prenumeration.**

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Jag har en prenumeration med självbetjäning som blockerar katalogborttagning

Självbetjäning för registrering av produkter som enskilda användare kan registrera sig för skapar även en gästanvändare för autentisering i din Azure AD-katalog. För att undvika dataförlust blockerar dessa självbetjäningsprodukter katalogborttagningar tills de helt tas bort från katalogen. De kan bara tas bort av Azure AD-administratören. Mer information finns i Ta [bort en katalog i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).
