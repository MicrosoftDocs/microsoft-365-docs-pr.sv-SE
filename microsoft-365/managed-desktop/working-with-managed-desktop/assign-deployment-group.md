---
title: Tilldela enheter till en distributionsgrupp
description: Hur du anger vilken distributionsgrupp du vill att enheterna ska vara i
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 19465d2d2f077859490c106b9c01f08beb6e3906
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985642"
---
# <a name="assign-devices-to-a-deployment-group"></a>Tilldela enheter till en distributionsgrupp

Microsoft Hanterat skrivbord tilldelar enheter till de olika distributionsgrupper, men du kan ange eller ändra grupp som en enhet tilldelas till en enhet med hjälp av administrationsportalen. Du ändrar tilldelningen efter att en enhet har registrerats eller efter att en användare har registrerat sig.

> [!IMPORTANT]
> Om du ändrar tilldelningen tillämpas principer som är specifika för den gruppen på enheten. Ändringen kan installera den senaste versionen av Windows 10 (inklusive eventuella nya funktioner eller kvalitetsuppdateringar). Det är bäst att flytta bara några enheter i början och sedan kontrollera användarupplevelsen. Tänk på att vissa uppdateringar startar om enheten. Kontrollera att du har valt rätt enheter att tilldela. Det kan ta upp till 24 timmar innan uppgiften verkställs.

Följ de här stegen om du vill tilldela enheter till en distributionsgrupp. Upprepa de här stegen för varje grupp om du vill flytta separata enheter till olika grupper.

1. I Microsoft Endpoint Manager väljer du **Enheter** i det vänstra fönstret. I avsnittet **Microsoft Hanterat skrivbord** väljer du **Enheter**.
2. Välj de enheter som du vill tilldela. Alla valda enheter tilldelas till den grupp som du anger.
3. Välj **Enhetsåtgärder** på menyn.
4. Välj **Tilldela enhet till grupp**. Ett flyg in öppnas.
5. Använd den nedrullningsmenyn för att välja gruppen du vill flytta enheter till och välj sedan **Spara**. Gruppen **som tilldelats av** ändras till **Väntande.**

När uppgiften är klar ändras **gruppen** som tilldelats av till **Administratör** (anges som du gjorde ändringen) och den nya grupptilldelningen visas i kolumnen Grupp. 

> [!NOTE]
> Du kan inte flytta enheter till andra grupper om de har registreringstillståndet "fel" eller "väntande".
>
>Om en enhet inte har tagits bort korrekt kan den visa statusen "klar". Om du flyttar en sådan enhet är det möjligt att flyttningen inte kan slutföras. Om du inte  ser Gruppera tilldelad efter ändring till Väntande i steg 5 kontrollerar du att enheten är tillgänglig genom att söka efter den i Intune.  Mer information finns i [Visa enhetsinformation i Intune](/mem/intune/remote-actions/device-inventory).