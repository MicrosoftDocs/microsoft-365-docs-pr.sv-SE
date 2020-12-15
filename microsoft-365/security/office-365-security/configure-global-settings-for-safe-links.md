---
title: Konfigurera globala inställningar för inställningar för säkra länkar i Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om hur du visar och konfigurerar globala inställningar (Blockera följande webb adresser lista och skydd för Office 365-appar) för säkra länkar i Microsoft Defender för Office 365.
ms.openlocfilehash: bc44432d4d9478e4c6a2414a70acc785c5b2c005
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682912"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Konfigurera globala inställningar för säkra länkar i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](office-365-atp.md). Om du är hem användare letar efter information om Safelinks i Outlook kan du läsa mer i [avancerad Outlook.com-säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Säkra länkar är en funktion i [Microsoft Defender för Office 365](office-365-atp.md) som tillhandahåller URL-genomsökning av inkommande e-postmeddelanden i e-postflöde och när du klickar på verifiering av URL-adresser och länkar i e-postmeddelanden och på andra platser. Mer information finns i [säkra länkar i Microsoft Defender för Office 365](atp-safe-links.md).

Du konfigurerar de flesta säkra länkar-inställningar i principer för säkra länkar. Anvisningar finns i [Konfigurera principer för säkra länkar i Microsoft Defender för Office 365](set-up-atp-safe-links-policies.md).

Men, säkra länkar använder dessutom globala inställningar som gäller för alla användare som ingår i alla aktiva principer för säker länkar. Följande globala inställningar:

- Listan **Blockera följande URL: er** . Mer information finns i ["Blockera följande URL-adresser" för säkra länkar](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Säkra länkar skyddar mot Office 365-appar. Mer information finns i [Inställningar för säkra Länkar för Office 365-appar](atp-safe-links.md#safe-links-settings-for-office-365-apps).

Du kan konfigurera inställningarna för global Safe Links i säkerhets & Compliance Center eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med post lådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Microsoft Defender för Office 365 tilläggs prenumerationer).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- De funktioner som tillhandahålls av globala inställningar för säkra länkar tillämpas bara på användare som ingår i principer för aktiva säkra länkar. Det finns inga inbyggda eller standard principer för säkra länkar, så du behöver skapa minst en princip för säkra Länkar för att dessa globala inställningar ska vara aktiva. Anvisningar finns i [Konfigurera principer för säkra länkar i Microsoft Defender för Office 365](set-up-atp-safe-links-policies.md).

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till sidan **Safe Links** använder du <https://protection.office.com/safelinksv2> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - För att konfigurera globala inställningar för säkra länkar måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** .
  - Om du vill ha skrivskyddad åtkomst till de globala inställningarna för säkra länkar måste du vara medlem i rollen **global läsare** eller **säkerhets läsare** .

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  **Anmärkningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- För våra rekommenderade värden för globala inställningar för säkra länkar, se [Inställningar för säkra anslutningar](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).

- Tillåt upp till 30 minuter för att en ny eller uppdaterad princip ska tillämpas.

- [Nya funktioner läggs hela tiden till i Microsoft Defender för Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365). När nya funktioner läggs till kan du behöva justera dina befintliga principer för säker länkar.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Konfigurera listan "Blockera följande URL-adresser" i säkerhets & Compliance Center

I rutan **Blockera följande URL: er** visas länkar som alltid ska blockeras av sökning efter säkra länkar i program som stöds. Mer information finns i ["Blockera följande URL-adresser" för säkra länkar](atp-safe-links.md#block-the-following-urls-list-for-safe-links).

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> och klickar sedan på **globala inställningar**.

2. I **principen Safe Links för din organisation** flyger ut som visas går du till rutan **Blockera följande URL: er** .

3. Konfigurera en eller flera poster enligt [syntaxen för listan Blockera följande URL: er](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

   Klicka på **Spara** när du är klar.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Konfigurera listan "Blockera följande URL-adresser" i PowerShell

Information om syntaxen finns i [syntaxen för listan "Blockera följande URL-adresser"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

Du kan använda cmdleten **Get-AtpPolicyForO365** för att visa befintliga poster i egenskapen _BlockURLs_ .

- Om du vill lägga till värden som ersätter befintliga poster kan du använda följande syntax i Exchange Online PowerShell eller Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  I det här exemplet läggs följande poster till i listan:

  - Blockera domänen, under domäner och sökvägar för fabrikam.com.
  - Blockera under domänens Research, men inte den överordnade domänen eller andra under domäner i tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Använd följande syntax för att lägga till eller ta bort värden utan att påverka andra befintliga poster:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  I det här exemplet läggs en ny post för adatum.com till, och posten för fabrikam.com tas bort.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Konfigurera skydd för säkra Länkar för Office 365-appar i säkerhets & Compliance Center

Säkra länkar skydd för Office 365-appar gäller för dokument i Office-skrivbord, mobiler och webb program som stöds. Mer information finns i [Inställningar för säkra Länkar för Office 365-appar](atp-safe-links.md#safe-links-settings-for-office-365-apps).

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> och klickar sedan på **globala inställningar**.

2. I **principen Safe Links för din organisation** flyger ut som visas konfigurerar du följande inställningar i inställningarna för **innehåll utom e-post** :

   - **Office 365-program**: kontrol lera att växlings knappen är till höger för att aktivera säkra Länkar för Office 365-appar som stöds: ![ slå på ](../../media/scc-toggle-on.png) .

   - **Spåra inte när användare klickar på säkra länkar**: flytta växlings knappen till vänster för att hålla reda på användare klickar på relaterade till blockerade URL: er i Office 365-appar som stöds ![ ](../../media/scc-toggle-off.png) .

   - **Tillåt inte att användare klickar via säkra länkar till den ursprungliga webb adressen**: kontrol lera att växlings knappen är till höger för att förhindra användare från att klicka dig fram till den ursprungliga blockerade webb adressen i Office 365-appar som stöds och ![ aktivera ](../../media/scc-toggle-on.png) .

   Klicka på **Spara** när du är klar.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Konfigurera skydd för säkra Länkar för Office 365-appar i PowerShell

Om du hellre vill använda PowerShell för att konfigurera skydd för säkra Länkar för Office 365-appar kan du använda följande syntax i Exchange Online PowerShell eller Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

I det här exemplet konfigureras följande inställningar för skydd för säkra länkar i Office 365-appar:

- Säkra Länkar för Office 365-appar är aktiverade (vi använder inte parametern _EnableSafeLinksForO365Clients_ och standardvärdet är $true).
- Användaren klickar på relaterade till blockerade URL: er i Office 365-program som stöds och spåras.
- Användare får inte klicka här via _till den ursprungliga_ blockerade webb adressen i Office 365-appar som stöds, och standardvärdet är $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Detaljerad information om syntax och parametrar finns i [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Gör något av följande för att kontrol lera att du har konfigurerat de globala inställningarna för säkra länkar ( **Blockera följande webb adress** lista och Office 365 App Protection-inställningar):

- I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> - **säkra länkar**, klickar på **globala inställningar** och kontrollerar inställningarna i rutan Lägg på.

- Kör följande kommando i Exchange Online PowerShell eller Exchange Online Protection PowerShell och kontrol lera inställningarna:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Detaljerad information om syntax och parametrar finns i [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).
