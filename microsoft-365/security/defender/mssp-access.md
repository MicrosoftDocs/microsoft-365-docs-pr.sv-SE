---
title: Tillhandahålla åtkomst för hanterad säkerhetstjänstleverantör (MSSP)
description: Läs mer om ändringar från Microsoft Defender Säkerhetscenter till Säkerhetscenter för Microsoft 365
keywords: Komma igång med Microsoft 365 Säkerhetscenter, OATP, MDATP, MDO, MDE, enda fönsterruta av glas, konvergerad portal, säkerhetsportal, Defender-säkerhetsportalen
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 4ea8c5a07016d3fe875d60501acee2cd46481489
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165735"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>Tillhandahålla åtkomst för hanterad säkerhetstjänstleverantör (MSSP) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gäller för:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Om du vill implementera en lösning med flera klientorganisationens delegerade åtkomst gör du följande:

1. Aktivera [rollbaserad åtkomstkontroll i](/windows/security/threat-protection/microsoft-defender-atp/rbac) Defender för slutpunkt i Microsoft 365 säkerhetscenter och anslut med Azure Active Directory-grupper (Azure AD).

2. Konfigurera [styrningsåtkomstpaket](/azure/active-directory/governance/identity-governance-overview) för åtkomstbegäran och etablering.

3. Hantera åtkomstförfrågningar och granskningar i [Microsoft Myaccess.](/azure/active-directory/governance/entitlement-management-request-approve)

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a>Aktivera rollbaserade åtkomstkontroller i Microsoft Defender för Slutpunkt i Microsoft 365 Säkerhetscenter

1. **Skapa åtkomstgrupper för MSSP-resurser i Kund-AAD: Grupper**

    De här grupperna länkas till de roller som du skapar i Defender för Slutpunkt i Microsoft 365 säkerhetscenter. Det gör du genom att skapa tre grupper i kundens AD-klientorganisation. Med den här metoden skapar vi följande grupper:

    - Analytiker på nivå 1 
    - Analytiker på nivå 2 
    - Mssp-analytikers godkännare  


2. Skapa Defender för slutpunktsroller för lämpliga åtkomstnivåer i Customer Defender för Endpoint i Roller och grupper i Säkerhetscenter i Microsoft 365.

    Åtkomstbehörigheter **> Slutpunktsroller &** grupper > Roller med ett användarkonto med behörigheten Global administratör eller Säkerhetsadministratör för att aktivera RBAC i Kundens Microsoft 365-säkerhetscenter.

    ![Bild av MSSP-åtkomst](../../media/mssp-access.png)

    Skapa sedan RBAC-roller för att uppfylla behoven på MSSP-nivån. Länka de här rollerna till de skapade användargrupperna via "Tilldelade användargrupper".

    Två möjliga roller:

    - **Nivå 1-analytiker** <br>
      Utför alla åtgärder utom live-svar och hantera säkerhetsinställningar.

    - **Nivå 2-analytiker** <br>
      Nivå 1-funktioner med tillägg till [live-svar](/windows/security/threat-protection/microsoft-defender-atp/live-response)

    Mer information finns i Använda [rollbaserad åtkomstkontroll.](/windows/security/threat-protection/microsoft-defender-atp/rbac)



## <a name="configure-governance-access-packages"></a>Konfigurera styrningsåtkomstpaket

1.  **Lägg till MSSP som ansluten organisation i kund AAD: identitetsstyrning**
    
    Om du lägger till MSSP som en ansluten organisation kan MSSP begära åtkomst och tillhandahålla åtkomst. 

    Det gör du genom att i kundens AD-klientorganisation få åtkomst till identitetsstyrning: Ansluten organisation. Lägg till en ny organisation och sök efter din MSSP-analytiker via klientorganisations-ID eller domän. Vi föreslår att du skapar en separat AD-klientorganisation för dina MSSP-analytiker.

2. **Skapa en resurskatalog i Kund AAD: Identitetsstyrning**

    Resurskataloger är en logisk samling åtkomstpaket som skapats i kundens AD-klientorganisation.

    Det gör du genom att i kundens AD-klientorganisation få åtkomst till identitetsstyrning: kataloger och lägga till **ny katalog.** I exemplet kallar vi det **MSSP Accesses.** 

    ![Bild av ny katalog](../../media/goverance-catalog.png)

    Mer information finns i [Skapa en resurskatalog.](/azure/active-directory/governance/entitlement-management-catalog-create)


3. **Skapa åtkomstpaket för MSSP-resurser Kund AAD: Identitetsstyrning**

    Åtkomstpaket är den samling av rättigheter och åtkomst som en begärare kommer att beviljas vid godkännande. 

    Det gör du genom att i kundens AD-klientorganisation få åtkomst till identitetsstyrning: Åtkomstpaket och lägga till **Nytt åtkomstpaket**. Skapa ett åtkomstpaket för MSSP-godkännare och varje analytiker. Följande analytikerkonfiguration på nivå 1 skapar till exempel ett åtkomstpaket som:

    - Kräver att en medlem i AD-gruppens **analytiker (MSSP) godkännare godkänner** nya begäranden
    - Har årliga åtkomstgranskningar, där SOC-analytiker kan begära ett åtkomsttillägg
    - Kan endast begäras av användare i MSSP-klientorganisationen
    - Access upphör automatiskt efter 365 dagar

    ![Bild på nytt åtkomstpaket](../../media/new-access-package.png)

    Mer information finns i [Skapa ett nytt åtkomstpaket.](/azure/active-directory/governance/entitlement-management-access-package-create)


4. **Länk för åtkomstbegäran till MSSP-resurser från kund AAD: identitetsstyrning**

    Länken Min åtkomstportal används av MSSP SOC-analytiker för att begära åtkomst via de åtkomstpaket som skapats. Länken är beständiga, vilket innebär att samma länk kan användas med tiden för nya analytiker. Analytikerbegäran går i en kö för godkännande av analytiker som godkänner **MSSP.**


    ![Bild av åtkomstegenskaper](../../media/access-properties.png)

    Länken finns på översiktssidan för varje åtkomstpaket.

## <a name="manage-access"></a>Hantera åtkomst 

1. Granska och auktorisera åtkomstförfrågningar i Customer and/or MSSP myaccess.

    Åtkomstförfrågningar hanteras i kundens My Access av medlemmar i gruppen Analysts godkännare för MSSP.

    Det gör du genom att använda kundens myaccess med hjälp av:  `https://myaccess.microsoft.com/@<Customer Domain >` . 

    Exempel:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. Godkänn eller neka förfrågningar i **avsnittet Godkännanden** i användargränssnittet.

     I det här läget har analytiker åtkomst till företaget etablerats och varje analytiker ska kunna komma åt kundens Microsoft 365 Säkerhetscenter: 

    `https://security.microsoft.com/?tid=<CustomerTenantId>` med de behörigheter och roller som de har tilldelats.

> [!IMPORTANT]
> Delegerad åtkomst till Microsoft Defender för Slutpunkt i Säkerhetscenter för Microsoft 365 ger för närvarande tillgång till en enda innehavare per webbläsarfönster.