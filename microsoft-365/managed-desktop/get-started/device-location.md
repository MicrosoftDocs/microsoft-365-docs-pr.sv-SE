---
title: Positioneringstjänst i Windows 10
description: Så här Windows du aktiverat platstjänster för dina enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929527"
---
# <a name="windows-10-location-service"></a>Positioneringstjänst i Windows 10

Enheter i Microsoft Hanterat skrivbord registreras med hjälp av Windows Autopilot. Med den här processen kan vi hantera dem Azure Active Directory och Microsoft Intune. Som standard är positionstjänsten Windows 10 inaktiverad när en enhet aktiveras för första gången om inte den här funktionen är aktiverad i sekretessinställningarna under "in box". De här inställningarna är dolda under Autopilot-registrering i Microsoft Hanterat skrivbord. Mer information om hur Autopilot är konfigurerad finns i [First-run-upplevelsen med Autopilot och registreringsstatussidan.](esp-first-run.md)

Därför kan Microsoft Hanterat skrivbord få sin enhets position, vilket begränsar funktionaliteten i flera Windows, till exempel tidszoner. Mer information om Windows 10 platstjänst finns i Windows 10 [platstjänst och sekretess.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

Du behöver inte använda platstjänsten för att kunna delta i Microsoft Hanterat skrivbord, men användarupplevelsen är begränsad. Enheter kan till exempel inte automatiskt ta reda på vilken tidszon de är i när användarna arbetar i en annan tidszon.

## <a name="enable-the-location-service"></a>Aktivera platstjänsten

Du kan välja att använda platstjänsten när du registrerar enheter i Microsoft Hanterat skrivbord eller så kan du aktivera eller inaktivera tjänsten efter registreringen.

### <a name="opt-in-during-enrollment"></a>Registrera dig under registrering

Du kan låta Microsoft Hanterat skrivbord aktivera platstjänsten. Under registreringsprocessen uppmanas du att välja om du vill tillåta att Windows 10 för plats på enheter.

### <a name="control-the-location-service-after-enrollment"></a>Kontrollera platstjänsten efter registrering

Du kan få platstjänsten aktiverad (eller inaktiverad) när som helst genom att skicka en [supportbegäran](../working-with-managed-desktop/admin-support.md) via [administratörsportalen.](access-admin-portal.md)

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>Hur Microsoft Hanterat skrivbord konfigurerar Windows 10 platstjänst

Om du väljer att använda platstjänsten använder vi de minsta nödvändiga inställningarna utan att påverka användarnas sekretess. Mer information finns i Windows 10 [platstjänst och sekretess.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

Microsoft Hanterat skrivbord av **sekretessinställningen för Plats** i Windows **till Tillåt** åtkomst till plats på den **här enheten.** Användargränssnittet ser ut så här:

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Platsinställningar i Windows inställningar":::

> [!NOTE]
> Om du väljer att använda platstjänsten gäller detta endast Windows operativsystemet. Appar får inte använda platstjänster. Varje användare kan välja om de vill tillåta att appar kommer åt sin plats.