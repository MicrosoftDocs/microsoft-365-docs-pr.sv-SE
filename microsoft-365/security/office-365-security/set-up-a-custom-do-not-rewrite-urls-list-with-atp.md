---
title: Konfigurera en anpassad lista över do-not-rewrite-url:er med hjälp av Office 365 ATP-säkra länkar
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
description: När du konfigurerar dina åtkomst- och tv-säkerhetslänkprinciper kan du inkludera en lista över webbadresser som inte skrivs om så att vissa personer i organisationen kan besöka webbplatser som du tar med i listan.
ms.openlocfilehash: 1983e0ff2ea85092af483d4f7a563681a6441152
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812952"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>Konfigurera en anpassad lista över do-not-rewrite-url:er med hjälp av Office 365 ATP-säkra länkar

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Advanced Threat Protection](office-365-atp.md). Om du är hemanvändare som letar efter information om säkra länkar i Outlook läser du [Avancerad Outlook.com säkerhet](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

Med [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan din organisation ha en anpassad [blockerad webbadresser](set-up-a-custom-blocked-urls-list-wtih-atp.md), så att när personer klickar på webbadresser (URL: er) i e-postmeddelanden eller vissa Office-dokument, de hindras från att gå till dessa webbadresser. Din organisation kan också ha anpassade listor "skriv inte om" för specifika grupper i organisationen. En "skriv inte om" med listan gör att vissa personer kan besöka webbadresser som annars blockeras av [ATP-säkra länkar i Office 365](atp-safe-links.md).

I den här artikeln beskrivs hur du anger en lista över webbadresser som är undantagna från atp-skanning för säkra länkar och några viktiga punkter att tänka på.

## <a name="set-up-a-do-not-rewrite-list"></a>Ställ in en "skriv inte om" lista

ATP Safe Links-skydd använder flera listor, inklusive organisationens blockerade webbadresser och listorna "skriv inte om" för undantag. Om du har de behörigheter som krävs kan du ställa in dina anpassade listor "skriv inte om inte". Du gör detta när du lägger till eller redigerar principer för säkra länkar som gäller för specifika mottagare i organisationen.

Om du vill redigera (eller definiera) ATP-principer måste du tilldelas en lämplig roll. Följande tabell innehåller några exempel. Mer information finns [i Behörigheter i Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

|Roll  |Var/hur tilldelad  |
|---------|---------|
|Global administratör för Office 365 |Personen som registrerar sig för att köpa Office 365 är som standard en global administratör. (Se [Om Office 365-administratörsroller](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) att lära sig mer.)         |
|Säkerhetsadministratör |Administrationscenter för[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory ( )|
|Exchange Online Organisation Management |Administrationscenter[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)för Exchange ( ) <br>eller <br>  PowerShell-cmdlets (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

> [!TIP]
> Mer information om roller och behörigheter finns [i Behörigheter i Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>Så här visar eller redigerar du en anpassad "skriv inte om" webbadresser

1. Gå [https://protection.office.com](https://protection.office.com) till och logga in med ditt arbets- eller skolkonto.

2. I den vänstra navigeringen, under **Hot hantering** \> **Princip** \> **Säkra länkar**.

3. I avsnittet **Principer som gäller för specifika mottagare** väljer du **Ny** (knappen Nytt liknar ett plustecken ()) **+** för att skapa en ny princip. (Alternativt kan du redigera en befintlig princip.)<br/>![Välj Ny om du vill lägga till en princip för säkra länkar för specifika e-postmottagare](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. Ange ett namn och en beskrivning för principen.

5. Markera rutan **Ange en giltig URL** i avsnittet Skriv inte om följande **webbadresser** och skriv sedan en URL och välj sedan plustecknet (+).

6. Välj **Mottagaren i**avsnittet **Tillämpad på** och välj sedan de grupper som du vill ta med i principen. Välj **Lägg till**och välj sedan **OK**.

7. När du är klar med webbadresserna väljer du **Spara**i det nedre högra hörnet av skärmen.

> [!NOTE]
> Se till att granska organisationens anpassade lista över blockerade webbadresser. Se [Konfigurera en anpassad lista över blockerade webbadresser med hjälp av ATP-säkra länkar](set-up-a-custom-blocked-urls-list-wtih-atp.md).

## <a name="important-points-to-keep-in-mind"></a>Viktiga punkter att tänka på

- Alla webbadresser som du anger i listan "skriv inte om" är undantagna från ATP Safe Links-sökning efter de mottagare som du anger.

- Om du redan har en lista över webbadresser i listan "skriv inte om" kontrollerar du att du granskar listan och lägger till jokertecken efter behov. Om din befintliga lista till exempel `https://contoso.com/a` har en post som `https://contoso.com/a/b` och du vill inkludera undersökvägar som `https://contoso.com/a/*`i principen lägger du till ett jokertecken i posten så att den ser ut .

- När du anger en "skriv inte om" för en ATP Safe Links-princip kan\*du inkludera upp till tre jokerteckenasterisker ( ). Jokertecken\*( ) används för att uttryckligen inkludera prefix eller underdomäner. Posten `contoso.com` är inte samma `*.contoso.com/*`sak `*.contoso.com/*` som, eftersom det gör att personer kan besöka underdomäner och sökvägar i den angivna domänen.

I följande tabell visas exempel på vad du kan ange och vilken effekt dessa poster har.

|**Exempel på post**|**Vad den gör**|
|:-----|:-----|
|`contoso.com`|Tillåter mottagarna att besöka `https://contoso.com` en webbplats som men inte underdomäner eller sökvägar.|
|`*.contoso.com/*`|Gör det möjligt för mottagare att besöka en domän, `https://www.contoso.com` `https://www.contoso.com`underdomäner och sökvägar, till exempel , , `https://maps.contoso.com`eller `https://www.contoso.com/a`. <br/><br/> Den här posten är `*contoso.com*`i sig bättre än , eftersom `https://www.falsecontoso.com` den inte innehåller potentiellt bedrägliga webbplatser, som eller`https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Tillåter specifika mottagare att besöka `https://contoso.com/a`en webbplats som , men inte underbanor som`https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Gör att specifika mottagare kan `https://contoso.com/a` besöka en webbplats som och underbanor som`https://contoso.com/a/b`|
