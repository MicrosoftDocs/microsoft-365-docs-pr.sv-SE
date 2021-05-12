---
title: Hantera licenser för enheter
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: Läs om hur du tilldelar licenser till grupper för användning med enheter.
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: 67bd0734953c64f51390aac949a7da477914c7b4
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331664"
---
# <a name="manage-licenses-for-devices"></a>Hantera licenser för enheter

Om du har Microsoft 365-appar för företag (enhet) eller Microsoft 365-appar för utbildning (enhet) kan du tilldela licenser till enheter med hjälp av Azure AD-grupper. När en enhet har en licens kan alla som använder enheten använda Microsoft 365-appar för företag (kallades tidigare Office 365 ProPlus). Anta till exempel att du har 20 bärbara datorer och surfplattor som används av personer i organisationen. När du tilldelar en licens till varje enhet använder varje person som loggar in på någon av enheterna Microsoft 365-appar för företag utan att behöva ha en egen licens.

> [!IMPORTANT]
> Enhetsbaserad licensiering för Microsoft 365-appar för företag är endast tillgängligt som en tilläggslicens för vissa kommersiella kunder och vissa utbildningskunder. För kommersiella kunder är licensen *Microsoft 365-appar* för företag (enhet) och är endast tillgänglig via Enterprise Agreement/Enterprise Agreement-prenumeration. För utbildningskunder är licensen *Microsoft 365 Apps for Education (enhet)* och är endast tillgänglig via Enrollment for Education Solutions (EES). Mer information finns i blogginlägget om tillgänglighet [för utbildning.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education) Kontakta din Microsoft-kontorepresentant om du behöver kommersiell tillgänglighet.

Börja genom att skapa en grupp i administrationscentret för Azure Active Directory och sedan tilldela enheter till gruppen. Mer information om enhetslicensiering, bland annat enhetskrav, vilka typer av grupper du kan använda och hur du konfigurerar Microsoft 365-appar för företag för användning av enhetslicensiering finns i Enhetsbaserade licenser för [Microsoft 365-appar](/deployoffice/device-based-licensing)för företag.

> [!IMPORTANT]
> Du måste vara global administratör för att kunna utföra uppgifterna i den här artikeln.

## <a name="assign-licenses-to-devices"></a>Tilldela licenser till enheter

När du tilldelar licenser till en grupp tilldelar du licenser till alla enheter i gruppen. Du kan bara tilldela en prenumeration till en enskild grupp.

1. I administrationscentret för Microsoft 365 går du till **sidan**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser.</a>
2. På sidan **Licenser väljer** du **Microsoft 365-appar för utbildning (enhet)** eller Microsoft **365-appar för företag (enhet)**.
3. På nästa sida väljer du en prenumeration och sedan **Tilldela licenser.**
4. Börja skriva **ett gruppnamn i** fönstret Tilldela licenser till en grupp och välj sedan det från resultatet så att det kan läggas till i listan.
5. Välj **Tilldela** och välj sedan **Stäng.**

## <a name="unassign-licenses-from-devices"></a>Ta bort licenser från enheter

När du tar bort licenser från en grupp tar du bort licenserna från alla enheter i gruppen. Alla appar och tillhörande data är skrivskyddade.

1. I administrationscentret går du till sidan  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser.</a>
2. På sidan **Licenser väljer** du **Microsoft 365-appar för utbildning (enhet)** eller Microsoft **365-appar för företag (enhet)**.
3. På nästa sida väljer du en prenumeration, väljer **Fler åtgärder** och sedan Tilldela **licenser .**
4. I dialogrutan **Ta bort licenser** väljer du Ta bort **.**
