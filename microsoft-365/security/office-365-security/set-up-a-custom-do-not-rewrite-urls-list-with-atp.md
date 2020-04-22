---
title: Konfigurera en anpassad lista över webbadresser som inte skrivs om med hjälp av ATP Safe Links
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
description: När du ställer in principerna för betrodda länkar i ATP kan du inkludera en lista över webbadresser som inte skrivs om så att vissa personer i organisationen kan besöka webbplatser som du inkluderar i listan.
ms.openlocfilehash: 490fb3279f2c54bc6f2335510aa711866318e01d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638386"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a>Konfigurera en anpassad lista över webbadresser som inte skrivs om med hjälp av ATP Safe Links

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md). Om du är hemanvändare och letar efter information om säkra länkar i Outlook läser du [Avancerad Outlook.com säkerhet](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

Med [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan din organisation ha en anpassad blockerade [webbadresser,](set-up-a-custom-blocked-urls-list-wtih-atp.md)så att när personer klickar på webbadresser (webbadresser) i e-postmeddelanden eller vissa Office-dokument, hindras de från att gå till dessa webbadresser. Din organisation kan också ha anpassade listor "skriv inte om" för specifika grupper i organisationen. En lista över "skriv inte om" gör det möjligt för vissa personer att besöka webbadresser som annars blockeras av [ATP Safe Links i Office 365](atp-safe-links.md).

I den här artikeln beskrivs hur du anger en lista över webbadresser som är undantagna från ATP-skanning av säkra länkar och några viktiga punkter att tänka på.

## <a name="set-up-a-do-not-rewrite-list"></a>Skapa en lista över "skriv inte om"

ATP-skydd för säkra länkar använder flera listor, inklusive organisationens lista med blockerade webbadresser och listorna "skriv inte om" för undantag. Om du har de behörigheter som krävs kan du ställa in dina anpassade listor "skriv inte om". Du gör detta när du lägger till eller redigerar principer för säkra länkar som gäller för specifika mottagare i organisationen.

Om du vill redigera (eller definiera) ATP-principer måste du tilldelas en lämplig roll. Följande tabell innehåller några exempel. Mer information finns [i Behörigheter i Säkerhets- & Compliance Center](permissions-in-the-security-and-compliance-center.md).

|Roll  |Var/hur tilldelas  |
|---------|---------|
|global administratör |Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard. (Läs [mer om Microsoft 365-administratörsroller.)](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)         |
|Säkerhetsadministratör |Administrationscenter för[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory ( )|
|Hantering av Exchange Online-organisation |Administrationscenter[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)för Exchange ( ) <br>eller <br>  PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

> [!TIP]
> Mer information om roller och behörigheter finns [i Behörigheter i Säkerhets- & Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>Så här visar eller redigerar du en anpassad webbadresslista för "skriv inte om"

1. Gå [https://protection.office.com](https://protection.office.com) till och logga in med ditt arbets- eller skolkonto.

2. I den vänstra navigeringen, under **Hot management** \> **Policy** \> **Safe Links**.

3. I avsnittet **Principer som gäller för specifika mottagare** väljer du **Ny** (knappen Nytt liknar ett plustecken ( **+**)) för att skapa en ny princip. (Du kan också redigera en befintlig princip.)<br/>![Välj Ny om du vill lägga till en princip för säkra länkar för specifika e-postmottagare](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. Ange ett namn och en beskrivning för principen.

5. I avsnittet **Skriv inte om följande webbadresser** markerar du rutan Ange en giltig **URL** och skriver sedan en URL och väljer sedan plustecknet (+).

6. I avsnittet **Tillämpad på** väljer du **Mottagaren är medlem i**och väljer sedan den grupp(er) som du vill ta med i principen. Välj **Lägg till**och välj sedan **OK**.

7. När du har lagt till webbadresser väljer du **Spara**i det nedre högra hörnet av skärmen .

> [!NOTE]
> Se till att granska organisationens anpassade lista över blockerade webbadresser. Se [Konfigurera en anpassad lista med blockerade webbadresser med ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).

## <a name="important-points-to-keep-in-mind"></a>Viktiga punkter att tänka på

- Alla webbadresser som du anger i listan "skriv inte om" är undantagna från ATP Safe Links-sökning efter de mottagare som du anger.

- Om du redan har en lista med webbadresser i listan "Skriv inte om" kontrollerar du den listan och lägger till jokertecken efter behov. Om din befintliga lista till exempel `https://contoso.com/a` har en post som `https://contoso.com/a/b` och du vill inkludera underbanor som i `https://contoso.com/a/*`din princip, lägger du till ett jokertecken i posten så att det ser ut som .

- När du anger en lista "skriv inte om" för en ATP Safe Links-princip kan\*du inkludera upp till tre jokerteckenasterisker ( ). Jokertecken (\*) används för att uttryckligen inkludera prefix eller underdomäner. Posten `contoso.com` är inte samma `*.contoso.com/*`sak `*.contoso.com/*` som eftersom personer kan besöka underdomäner och sökvägar i den angivna domänen.

I följande tabell visas exempel på vad du kan ange och vilken effekt dessa poster har.

|**Exempel på post**|**Vad den gör**|
|:-----|:-----|
|`contoso.com`|Tillåter mottagare att besöka `https://contoso.com` en webbplats som men inte underdomäner eller sökvägar.|
|`*.contoso.com/*`|Tillåter mottagare att besöka en domän, underdomäner och `https://www.contoso.com` `https://www.contoso.com`sökvägar, till exempel , , `https://maps.contoso.com`eller `https://www.contoso.com/a`. <br/><br/> Den här posten är `*contoso.com*`till sin natur bättre än , `https://www.falsecontoso.com` eftersom den inte innehåller potentiellt bedrägliga webbplatser, gilla eller`https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Gör det möjligt för specifika `https://contoso.com/a`mottagare att besöka en webbplats som , men inte undersöker som`https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Gör det möjligt för specifika `https://contoso.com/a` mottagare att besöka en webbplats som och undervägar som`https://contoso.com/a/b`|
