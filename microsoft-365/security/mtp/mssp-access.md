---
title: Microsoft Defender för slutpunkt i Säkerhetscenter för Microsoft 365
description: Läs mer om ändringar från Microsoft Defender Säkerhetscenter till Microsoft 365 Säkerhetscenter
keywords: Komma igång med Microsoft 365 säkerhetscenter, OATP, MDATP, MDO, MDE, en fönsterruta, konvergerad portal, säkerhetsportal, defender säkerhetsportal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: 96d5a3bdbd0acbf428f01cc3bb5afefaa95950b4
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242985"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>Ge åtkomst för hanterad tjänstprovider (MSSP) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gäller för:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

Så här implementerar du en delegerad åtkomstlösning med flera klientorganisationer:

1. Aktivera [rollbaserad åtkomstkontroll](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) i Defender för slutpunkt i Microsoft 365 säkerhetscenter och anslut med Azure Active Directory (Azure AD) grupper.

2. Konfigurera [åtkomstpaket för](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) styrning för åtkomstbegäran och etablering.

3. Hantera åtkomstförfrågningar och granskningar i [Microsoft Myaccess.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve)

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a>Aktivera rollbaserade åtkomstkontroller i Microsoft Defender för Slutpunkt i Microsoft 365 säkerhetscenter

1. **Skapa åtkomstgrupper för MSSP-resurser i Kund AAD: Grupper**

    De här grupperna länkas till de roller som du skapar i Defender för Slutpunkt i Microsoft 365 säkerhetscenter. Det gör du genom att skapa tre grupper i kundens AD-klientorganisation. I vår exempel tillvägagångssätt skapar vi följande grupper:

    - Nivå 1-analytiker 
    - Tier 2-analytiker 
    - MSSP Analyst Approvers  


2. Skapa Defender för slutpunktsroller för lämpliga åtkomstnivåer i Customer Defender för Slutpunkt i Roller och grupper i Säkerhetscenter i Microsoft 365.

    Åtkomstbehörigheter **> Slutpunktsroller** i microsoft 365-säkerhetscentret för kunder & grupper > Roller med ett användarkonto med behörigheten Global administratör eller Säkerhetsadministratör.

    ![Bild på MSSP-åtkomst](../../media/mssp-access.png)

    Skapa sedan RBAC-roller för att uppfylla MSSP SOC-nivåbehov. Länka de här rollerna till de användargrupper som skapats via "Tilldelade användargrupper".

    Två möjliga roller:

    - **Nivå 1-analytiker** <br>
      Utför alla åtgärder utom livesvar och hantera säkerhetsinställningar.

    - **Nivå 2-analytiker** <br>
      Nivå 1-funktioner med tillägg till [livesvar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)

    Mer information finns i [Använda rollbaserad åtkomstkontroll.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)



## <a name="configure-governance-access-packages"></a>Konfigurera åtkomstpaket för styrning

1.  **Lägg till MSSP som ansluten organisation i kund AAD: identitetsstyrning**
    
    Om du lägger till MSSP som en ansluten organisation kan MSSP begära åtkomst och tillhandahålla åtkomst. 

    Det gör du genom att använda identitetsstyrning i kundens AD-klientorganisation: Ansluten organisation. Lägg till en ny organisation och sök efter din MSSP-analytiker via klientorganisations-ID eller domän. Vi föreslår att du skapar en separat AD-klientorganisation för dina MSSP-analytiker.

2. **Skapa en resurskatalog i Kund AAD: Identitetsstyrning**

    Resurskataloger är en logisk samling åtkomstpaket som skapats i kundens AD-klientorganisation.

    Det gör du genom att öppna identitetsstyrning i kundens AD-klientorganisation: Kataloger och lägga till **ny katalog.** I vårt exempel kallar vi det **MSSP-åtkomst.** 

    ![Bild på ny katalog](../../media/goverance-catalog.png)

    Mer information finns i [Skapa en resurskatalog.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)


3. **Skapa åtkomstpaket för MSSP-resurser Kund AAD: Identitetsstyrning**

    Åtkomstpaket är den samling av rättigheter och åtkomst som en begärare beviljas vid godkännande. 

    Det gör du genom att komma åt identitetsstyrning i kund-AD-klientorganisationen: Åtkomstpaket och lägga till **nytt åtkomstpaket.** Skapa ett åtkomstpaket för MSSP-godkännare och varje analytiker. Följande nivå 1-analytiker-konfiguration skapar till exempel ett åtkomstpaket som:

    - Kräver att en medlem i AD-gruppens **MSSP-analytiker godkänner att** auktorisera nya begäranden
    - Har årliga åtkomstgranskningar, där SOC-analytiker kan begära ett åtkomsttillägg
    - Kan endast begäras av användare i MSSP SOC-klientorganisationen
    - Access upphör automatiskt efter 365 dagar

    ![Bild av nytt åtkomstpaket](../../media/new-access-package.png)

    Mer information finns i Skapa [ett nytt åtkomstpaket.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)


4. **Länken Ange åtkomstbegäran till MSSP-resurser från kund AAD: identitetsstyrning**

    Länken Min Åtkomst-portalen används av MSSP SOC-analytiker för att begära åtkomst via åtkomstpaketen som skapats. Länken är beständiga, vilket innebär att samma länk kan användas med tiden för nya analytiker. Analytikerbegäran hamnar i en kö för godkännande av **MSSP-analytikernas godkännare.**


    ![Bild av åtkomstegenskaper](../../media/access-properties.png)

    Länken finns på översiktssidan för varje åtkomstpaket.

## <a name="manage-access"></a>Hantera åtkomst 

1. Granska och auktorisera åtkomstförfrågningar i Customer and/or MSSP myaccess.

    Åtkomstförfrågningar hanteras i min åtkomst för kunden av medlemmar i gruppen analyschefer för MSSP.

    Det gör du genom att komma åt kundens myaccess med hjälp av:  `https://myaccess.microsoft.com/@<Customer Domain >` . 

    Exempel:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. Godkänna eller neka begäranden i **avsnittet Godkännanden** i användargränssnittet.

     I det här läget har analysåtkomst etablerats och varje analytiker bör kunna komma åt kundens Microsoft 365 Säkerhetscenter: 

    `https://security.microsoft.com/?tid=<CustomerTenantId>` med de behörigheter och roller som de har tilldelats.

> [!IMPORTANT]
> Delegerad åtkomst till Microsoft Defender för Slutpunkt i Säkerhetscenter för Microsoft 365 ger för närvarande tillgång till en enda innehavare per webbläsarfönster. 