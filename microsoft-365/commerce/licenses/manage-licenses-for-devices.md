---
title: Hantera licenser för enheter
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Lär dig hur du tilldelar licenser till grupper som du kan använda med enheter.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: 29bd56ccff01d8c21cc67d1188fa21e338fb4b7e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638189"
---
# <a name="manage-licenses-for-devices"></a>Hantera licenser för enheter

Om du har Microsoft 365-appar för Enterprise (enhet) eller Microsoft 365-appar för utbildning (enhet) kan du tilldela licenser till enheter med Azure AD Groups. När en enhet har en licens kan alla som använder enheten använda Microsoft 365-appar för företag (tidigare kallat Office 365 ProPlus). Låt oss säga att du har 20 bärbara datorer och surfplattor som används av personer i din organisation. När du tilldelar en licens till varje enhet använder varje person som loggar in på en av enheterna Microsoft 365-appar för företag utan att den egna licensen behövs.

> [!IMPORTANT]
> Enhets licenser för Microsoft 365-appar för företag är bara tillgänglig som en tilläggs licens för vissa kommersiella kunder och vissa utbildnings kunder. För kommersiella kunder är licensen *Microsoft 365-appar för Enterprise (enhet)* och är endast tillgänglig genom ett avtal för Enterprise-abonnemang. För utbildnings kunder är licensen *Microsoft 365-program för utbildning (enhet)* och är endast tillgänglig via registrering för utbildnings lösningar (EES). Mer information finns i blogg inlägget på [utbildning](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/). För att få en kommersiell tillgänglighet kontaktar du din Microsoft-representant.

Börja genom att skapa en grupp i administrations centret för Azure Active Directory och sedan tilldela enheter till gruppen. Om du vill veta mer om enhets licensiering, inklusive enhets krav, vilka typer av grupper du kan använda och hur du konfigurerar Microsoft 365-appar för företag att använda enhets licensiering, läser du [enhets licensiering för microsoft 365-program för företag](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!IMPORTANT]
> Du måste vara global administratör för att utföra åtgärderna i den här artikeln.

## <a name="assign-licenses-to-devices"></a>Tilldela licenser till enheter

När du tilldelar licenser till en grupp tilldelar du licenser till alla enheter i gruppen. Du kan bara tilldela en prenumeration till en enda grupp.

1. Gå till sidan för **fakturerings**licenser i administrations centret för Microsoft 365  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> .
2. På sidan **licenser** väljer du **Microsoft 365-appar för utbildning (enhet)** eller **Microsoft 365-appar för företag (enhet)**.
3. På nästa sida väljer du ett abonnemang och sedan **tilldela licenser**.
4. I fönstret **tilldela licenser i en grupp** börjar du skriva ett grupp namn och väljer det från resultaten för att lägga till det i listan.
5. Välj **tilldela**och sedan **Stäng**.

## <a name="unassign-licenses-from-devices"></a>Ta bort licenser från enheter

När du tilldelar licenser från en grupp tar du bort licenser från alla enheter i gruppen. Alla program och tillhör ande data är då skrivskyddade.

1. Gå till sidan för **fakturerings**licenser i administrations centret  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> .
2. På sidan **licenser** väljer du **Microsoft 365-appar för utbildning (enhet)** eller **Microsoft 365-appar för företag (enhet)**.
3. På nästa sida väljer du ett abonnemang, väljer **fler åtgärder**och väljer sedan **ta bort tilldelning av licenser**.
4. Välj **ta bort tilldelning**i dialog rutan **ta bort licenser** .