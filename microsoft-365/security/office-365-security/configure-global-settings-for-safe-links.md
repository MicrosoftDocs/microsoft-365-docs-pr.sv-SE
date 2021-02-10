---
title: Konfigurera globala inställningar för inställningarna för Säkra länkar i Defender för Office 365
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
description: Administratörer kan ta reda på hur de visar och konfigurerar globala inställningar (listan Blockera följande URL:er och skydd för Office 365-program) för säkra länkar i Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 885fe6a06cce054bea6d6f20c24c5c1f2a159c07
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165733"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Konfigurera globala inställningar för Säkra länkar i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](office-365-atp.md). Om du är hemanvändare och vill ha information om säkra länkar i Outlook kan du [läsa Mer Outlook.com säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Säkra länkar är en funktion i Microsoft Defender för [Office 365](office-365-atp.md) som ger URL-genomsökning av inkommande e-postmeddelanden i e-postflödet och tidpunkten för klickverifiering av URL:er och länkar i e-postmeddelanden och på andra platser. Mer information finns i [Säkra länkar i Microsoft Defender för Office 365.](atp-safe-links.md)

Du konfigurerar de flesta inställningarna för Säkra länkar i principer för säkra länkar. Instruktioner finns i Konfigurera [principer för säkra länkar i Microsoft Defender för Office 365.](set-up-atp-safe-links-policies.md)

Men Säkra länkar använder även globala inställningar som gäller för alla användare som ingår i aktiva principer för säkra länkar. Följande globala inställningsområde:

- Listan **Blockera följande URL-adresser.** Mer information finns i [listan "Blockera följande URL:er" för Säkra länkar](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Skydd mot säkra länkar för Office 365-appar. Mer information finns i inställningarna [för Säkra länkar för Office 365-appar.](atp-safe-links.md#safe-links-settings-for-office-365-apps)

Du kan konfigurera globala inställningar för säkra länkar i Säkerhets- & och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Microsoft Defender för Office 365-tilläggsprenumerationer).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- De funktioner som tillhandahålls av globala inställningar för säkra länkar tillämpas endast på användare som ingår i aktiva principer för säkra länkar. Det finns ingen inbyggd eller standardprincip för säkra länkar, så du måste skapa minst en princip för säkra länkar för att dessa globala inställningar ska vara aktiva. Instruktioner finns i Konfigurera [principer för säkra länkar i Microsoft Defender för Office 365.](set-up-atp-safe-links-policies.md)

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt **till sidan Säkra** länkar använder du <https://protection.office.com/safelinksv2> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill konfigurera globala inställningar för Säkra länkar måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till globala inställningar för säkra länkar måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  **Anmärkningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- Våra rekommenderade värden för de globala inställningarna för Säkra länkar finns i [inställningarna för Säkra länkar.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)

- Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.

- [Nya funktioner läggs kontinuerligt till i Microsoft Defender för Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365) När nya funktioner läggs till kan du behöva justera dina befintliga principer för säkra länkar.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Konfigurera listan "Blockera följande URL:er" i Säkerhets- & Efterlevnadscenter

I **listan Blockera följande URL:er** identifieras de länkar som alltid ska blockeras genom genomsökning av Säkra länkar i appar som stöds. Mer information finns i [listan "Blockera följande URL:er" för Säkra länkar.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)

1. I Säkerhets- & Säkerhets- och  efterlevnadscenter går du till ATP – säkra länkar för hanteringspolicy och \>  \> klickar sedan **på Globala inställningar.**

2. I principen **för säkra länkar i organisationen** som visas går du till rutan Blockera följande **URL:er.**

3. Konfigurera en eller flera poster enligt beskrivningen i [Postsyntax för listan "Blockera följande URL:er".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Klicka på **Spara** när du är klar.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Konfigurera listan "Blockera följande URL:er" i PowerShell

Mer information om postsyntaxen [finns i Postsyntax för listan Blockera följande URL:er.](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

Du kan använda cmdleten **Get-AtpPolicyForO365** till att visa befintliga poster i egenskapen _BlockURLs._

- Om du vill lägga till värden som ersätter befintliga poster ska du använda följande syntax i Exchange Online PowerShell eller Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  I det här exemplet läggs följande poster till i listan:

  - Blockera domän, underdomäner och sökvägar för fabrikam.com.
  - Blockera underdomänsforskningen, men inte den överordnade domänen eller andra underdomäner i tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Om du vill lägga till eller ta bort värden utan att påverka andra befintliga poster använder du följande syntax:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  Det här exemplet lägger till en adatum.com post och tar bort posten för fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Konfigurera skydd mot säkra länkar för Office 365-appar i Säkerhets- & Efterlevnadscenter

Skydd mot säkra länkar för Office 365-program gäller dokument i Office-skrivbords-, mobil- och webbprogram som stöds. Mer information finns i inställningarna [för Säkra länkar för Office 365-appar.](atp-safe-links.md#safe-links-settings-for-office-365-apps)

1. I Säkerhets- & Säkerhets- och  efterlevnadscenter går du till ATP – säkra länkar för hanteringspolicy och \>  \> klickar sedan **på Globala inställningar.**

2. I principen **För säkra länkar i organisationen** som visas konfigurerar du följande inställningar i inställningarna som gäller för innehåll utom **e-postavsnittet:**

   - **Office 365-program:** Kontrollera att reglaget är till höger för att aktivera Säkra länkar för Office 365-program som stöds: ![ Aktivera ](../../media/scc-toggle-on.png) .

   - **Spåra inte när användare** klickar på Säkra länkar: Flytta växlingsknappen åt vänster för att spåra användarklick som är relaterade till blockerade URL:er i Office 365-appar som stöds: ![ ](../../media/scc-toggle-off.png) Inaktivera.

   - **Låt inte användare** klicka genom Säkra länkar till den ursprungliga URL:en: Kontrollera att reglaget är till höger för att hindra användare från att klicka till den ursprungliga blockerade URL:en i Office 365-appar som stöds: Slå ![ ](../../media/scc-toggle-on.png) på.

   Klicka på **Spara** när du är klar.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Konfigurera skydd mot säkra länkar för Office 365-appar i PowerShell

Om du hellre vill använda PowerShell för att konfigurera skydd mot säkra länkar för Office 365-program använder du följande syntax i Exchange Online PowerShell eller Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

Det här exemplet konfigurerar följande inställningar för skydd mot säkra länkar i Office 365-program:

- Säkra länkar för Office 365-appar är aktiverat (vi använder inte parametern _EnableSafeLinksForO365Clients_ och standardvärdet är $true).
- Användarklick som är relaterade till blockerade URL:er i Office 365-program spåras.
- Användare får inte klicka till den ursprungliga blockerade URL:en i Office 365-program som stöds (parametern _AllowClickThrough_ används inte och standardvärdet är $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Detaljerad information om syntax och parametrar finns [i Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Kontrollera att du har konfigurerat de globala inställningarna för  säkra länkar (listan Blockera följande URL-adresser och skyddsinställningarna för Office 365-appen) genom att göra något av följande:

- I Säkerhets- & Efterlevnadscenter går  du till ATP – säkra länkar för hanteringspolicy, klickar på Globala inställningar och kontrollerar inställningarna i flyg \>  \> ut som visas. 

- Kör följande kommando i Exchange Online PowerShell eller Exchange Online Protection PowerShell och kontrollera inställningarna:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Detaljerad information om syntax och parametrar finns i [Get-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)
