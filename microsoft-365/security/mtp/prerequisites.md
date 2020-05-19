---
title: Förutsättningar för Microsoft Threat Protection
description: Lär dig mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för Microsoft Threat Protection
keywords: krav, krav, hårdvara, mjukvara, webbläsare, MTP, M365, licens, E5, A5, EMS, köp
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 71e7b532e046015dd64e51fd422d276433d65b3a
ms.sourcegitcommit: 6ea9a910a8106a5f1aa589c55d166bfa67fd12a8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280540"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Förutsättningar för Microsoft Threat Protection

**Gäller:**
- Microsoft Hotskydd

Lär dig mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för att etablera och använda Microsoft Threat Protection.

## <a name="licensing-requirements"></a>Licenskrav

>[!IMPORTANT]
>Från och med den 12 maj 2020 kommer Microsoft gradvis att lansera nya, optimerade upplevelser kring licenskrav och [aktivera Microsoft Threat Protection](mtp-enable.md). Under flera veckor under denna period kommer vissa kunder att börja se ändringar i sina portalupplevelser. Information om de nya upplevelserna markeras **Ny upplevelse** i den här artikeln.

Om du vill använda Microsoft Threat Protection behöver du antingen en enda licens eller en kombination av licenser. Dessa licenser eller licenskombinationer ger dig tillgång till Microsoft Threat Protection-funktioner utan extra kostnad.

### <a name="single-license"></a>Enkel licens
Du kan använda *någon* av följande licenser:

- Microsoft 365 E5 eller A5
- Microsoft 365 E5 Security eller A5 Security

### <a name="combination-of-licenses"></a>Kombination av licenser
Du kan också använda en kombination av licenser för E5- eller A5-prenumerationer på Office 365, *Enterprise Mobility + Security (EMS)* och Windows. Licenskombinationen måste innehålla *alla* dessa licenser:

- Office 365 E5 eller A5
- *Företagsmobilitet + säkerhet (EMS)* E5 eller A5
- Windows 10 Enterprise E5 eller A5

Mer information [finns i Microsoft 365 Enterprise-tjänstplanerna](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> Har du inte licens än? [Prova eller köp en Microsoft 365-prenumeration](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


**Ny erfarenhet:** Från och med den 12 maj 2020 kommer kunderna gradvis att få ändringar i den här upplevelsen. För dem med den nya upplevelsen är möjligheten att aktivera Microsoft Threat Protection tillgänglig för *alla* kunder med någon av följande licenser:

- Microsoft 365 E5 eller A5
- Microsoft 365 E5 Security eller A5 Security
- Windows 10 Enterprise E5 eller A5
- Enterprise Mobility + Security (EMS) E5 eller A5 
- Office 365 E5 eller A5
- Microsoft Defender Avancerat skydd 
- Azure Advanced Threat Protection 
- Microsoft Cloud App Security 
- Avancerat skydd mot Office 365 (plan 2) 

### <a name="check-your-existing--licenses"></a>Kontrollera dina befintliga licenser
Gå till Microsoft 365 administrationscenter ([admin.microsoft.com](https://admin.microsoft.com/)) för att visa dina befintliga licenser. Gå till **Billing**  >  **Faktureringslicenser i administrationscentret**.

>[!NOTE]
> Du måste tilldelas rollen **Faktureringsadministratör** eller **Global läsare** [i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licensinformation. Om du stöter på åtkomstproblem kontaktar du en global administratör.

## <a name="browser-requirements"></a>Krav på webbläsare
Få tillgång till Microsoft Threat Protection i Microsoft 365-säkerhetscentret med Microsoft Edge, Internet Explorer 11 eller valfri HTML 5-kompatibel webbläsare.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Tillgänglighet till amerikanska GCC, GCC High och andra amerikanska statliga institutioner
Microsoft Threat Protection är för närvarande *inte* tillgängligt för:
- Moln för usa:s myndighetsgemenskap (GCC)
- Us-regeringgemenskap moln kick (GCC kick)
- Usa:s försvarsdepartement
- Alla amerikanska statliga institutioner med kommersiella licenser

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över Microsofts hotskydd](microsoft-threat-protection.md)
- [Aktivera Microsoft Hotskydd](mtp-enable.md)
