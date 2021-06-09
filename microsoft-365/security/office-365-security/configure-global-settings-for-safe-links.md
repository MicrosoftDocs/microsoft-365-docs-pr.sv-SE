---
title: Konfigurera globala inställningar för Valv Länkar i Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur de visar och konfigurerar globala inställningar (listan "Blockera följande URL:er" och skydd för Office 365-appar) för Valv-länkar i Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4e77373657d3167ca8f5bafa544923ab3a2320ce
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821991"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Konfigurera globala inställningar för Valv Länkar i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](defender-for-office-365.md). Om du är hemanvändare och vill ha information om säkra länkar i Outlook kan du läsa [Mer Outlook.com-säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Valv Länkar är en funktion i [Microsoft Defender](defender-for-office-365.md) för Office 365 som ger URL-skanning av inkommande e-postmeddelanden i e-postflödet och tidpunkten för klickverifiering av URL:er och länkar i e-postmeddelanden och på andra platser. Mer information finns i artikeln [Valv i Microsoft Defender för Office 365](safe-links.md).

Du konfigurerar Valv inställningar för länkar Valv principer. Instruktioner finns i Konfigurera [principer Valv länkar i Microsoft Defender för Office 365.](set-up-safe-links-policies.md)

Men Valv länkar använder också följande globala inställningar som du konfigurerar utanför Valv själva principerna:

- Listan **Blockera följande URL:er.** Den här inställningen gäller för alla användare som ingår i alla aktiva Valv-länkar. Mer information finns i [listan "Blockera följande URL:er" för Valv Länkar](safe-links.md#block-the-following-urls-list-for-safe-links)
- Valv Länkskydd för Office 365 appar. De här inställningarna gäller för alla användare i organisationen som är licensierade för Defender för Office 365, oavsett om användarna ingår i active Valv-länkar eller inte. Mer information finns i inställningar [Valv länkar för appar Office 365 .](safe-links.md#safe-links-settings-for-office-365-apps)

Du kan konfigurera de globala inställningarna för Valv-länkar i säkerhetscentret i Microsoft 365 eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med postlådor i Exchange Online– fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Microsoft Defender för Office 365-tilläggsprenumerationer).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Det finns ingen inbyggd eller standardprincip för Valv-länkar, så du måste skapa minst en Valv-länkprincip för att listan Blockera följande URL:er ska vara aktiv.  Instruktioner finns i Konfigurera [principer Valv länkar i Microsoft Defender för Office 365.](set-up-safe-links-policies.md)

- Öppna Microsoft 365 Säkerhetscenter på <https://security.microsoft.com>. Om du vill gå **direkt Valv sidan** Länkar använder du <https://security.microsoft.com/safelinksv2> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - För att konfigurera globala inställningar Valv länkar måste du vara medlem i rollgrupperna **Organisationshantering** **eller Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till globala inställningar för Valv länkar måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Anteckningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- Våra rekommenderade värden för de globala inställningarna för Valv finns i inställningar [Valv Länkar.](recommended-settings-for-eop-and-office365.md#safe-links-settings)

- Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.

- [Nya funktioner läggs kontinuerligt till i Microsoft Defender för Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365). När nya funktioner läggs till kan du behöva justera dina befintliga principer Valv Länkar.

## <a name="configure-the-block-the-following-urls-list-in-the-security-center"></a>Konfigurera listan "Blockera följande URL:er" i säkerhetscentret

I **listan Blockera följande URL:er** identifieras de länkar som alltid ska blockeras av Valv i program som stöds. Mer information finns i [listan "Blockera följande URL:er" för Valv Länkar.](safe-links.md#block-the-following-urls-list-for-safe-links)

1. I säkerhetscentret går du till avsnittet **E& för** samarbete & principer för \>  \> **hot mot** \> **regler** \> **Valv Länkar.**

2. På sidan **Valv klickar** du på **Globala inställningar**. I den **Valv princip för** länkar för organisationen som visas går du till rutan Blockera följande **URL:er.**

3. Konfigurera en eller flera poster enligt beskrivningen i [Postsyntax för listan "Blockera följande URL:er".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Klicka på **Spara** när du är klar.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Konfigurera listan "Blockera följande URL:er" i PowerShell

Mer information om postsyntaxen finns [i Postsyntax för listan "Blockera följande URL:er".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

Du kan använda cmdleten **Get-AtpPolicyForO365** till att visa befintliga poster i egenskapen _BlockURLs._

- Om du vill lägga till värden som ersätter befintliga poster använder du följande syntax i Exchange Online PowerShell Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  I det här exemplet läggs följande poster till i listan:

  - Blockera domän, underdomäner och sökvägar för fabrikam.com.
  - Blockera efterforskningar för underdomäner, men inte den överordnade domänen eller andra underdomäner i tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Om du vill lägga till eller ta bort värden utan att påverka andra befintliga poster använder du följande syntax:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  I det här exemplet läggs en ny adatum.com posten till och posten tas bort för fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security-center"></a>Konfigurera Valv för länkar Office 365-program i säkerhetscentret

Valv Länkskydd för Office 365-appar gäller för dokument i Office-, mobil- och webbappar som stöds. Mer information finns i inställningar [Valv länkar för appar Office 365 .](safe-links.md#safe-links-settings-for-office-365-apps)

1. I säkerhetscentret går du till avsnittet **E& för** samarbete & principer för \>  \> **hot mot** \> **regler** \> **Valv Länkar.**

2. På sidan **Valv klickar** du på **Globala inställningar**. I den **Valv-länkprincip** för organisationen som visas konfigurerar du följande inställningar i avsnittet Inställningar som gäller för innehåll i **Office 365-appar:**

   - **Använd Valv länkar i** Office 365-appar: Kontrollera att växlingsknappen är till höger för att aktivera Valv-länkar för Office 365-appar som stöds: ![ Aktivera ](../../media/scc-toggle-on.png) .

   - **Spåra inte när användare** klickar på skyddade länkar i Office 365-appar : Flytta reglaget till vänster för att spåra användarklick på blockerade URL:er i Office 365-appar: Inaktivera ![ ](../../media/scc-toggle-off.png) .

   - **Låt inte användare** klicka till den ursprungliga URL:en i Office 365-appar: Kontrollera att reglaget är till höger för att hindra användare från att klicka till den ursprungliga blockerade URL:en i Office 365-appar som stöds: Aktivera ![ ](../../media/scc-toggle-on.png) .

   Klicka på **Spara** när du är klar.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Konfigurera Valv för länkar för Office 365 i PowerShell

Om du hellre vill använda PowerShell för att konfigurera Valv Links protection för Office 365-appar använder du följande syntax i Exchange Online PowerShell eller Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

I det här exemplet konfigureras följande inställningar Valv skydd mot länkar i Office 365 appar:

- Valv Länkar till Office 365-appar är aktiverat (vi använder inte parametern _EnableSafeLinksForO365Clients_ och standardvärdet är $true).
- Användaren klickar på relaterade till blockerade URL:er i Office 365-program spåras.
- Användarna får inte klicka sig fram till den ursprungliga blockerade URL:en i Office 365-appar som stöds (parametern _AllowClickThrough_ används inte och standardvärdet är $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Detaljerad information om syntax och parametrar finns i [Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Kontrollera att du har konfigurerat de globala inställningarna för Valv-länkar (listan Blockera följande **URL:er** och Office 365-programskyddsinställningarna) genom att göra något av följande:

- I säkerhetscentret går du till **E-&** principer för samarbete & principer för regler och hot Valv Länkar klickar på Globala inställningar och kontrollerar inställningarna i flyg ut som \>  \>  \>  \>  \> visas. 

- I Exchange Online PowerShell Exchange Online Protection PowerShell kör du följande kommando och kontrollerar inställningarna:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Detaljerad information om syntax och parametrar finns i [Get-AtpPolicyForO365.](/powershell/module/exchange/get-atppolicyforo365)
