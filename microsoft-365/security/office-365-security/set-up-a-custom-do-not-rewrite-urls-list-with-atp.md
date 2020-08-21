---
title: Konfigurera en egen gör-inte omskrivning av URL-lista med säkra ATP-länkar
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
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 'Lär dig hur du konfigurerar anpassade blockerade URL: er för användare och gör om listan över URL: er för en grupp användare i Office 365-principer för säkra Länkar för säkerhets skull.'
ms.openlocfilehash: 9ec9c92e038aee33c716405916df009e3f4c60c5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825239"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a>Konfigurera en egen gör-inte omskrivning av URL-lista med säkra ATP-länkar

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md). Om du är hem användare letar efter information om säkra länkar i Outlook kan du läsa mer i [avancerad Outlook.com säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Med [Office 365 Avancerat skydd](office-365-atp.md) (ATP) kan organisationen ha [anpassade blockerade URL-adresser](set-up-a-custom-blocked-urls-list-atp.md), till exempel när personer klickar på webb adresser (URL: er) i e-postmeddelanden eller vissa Office-dokument, förhindras de från att gå till dessa URL-adresser. Din organisation kan också ha anpassade listor för "Skriv inte om" för specifika grupper i din organisation. En "Skriv inte in"-lista gör att vissa personer kan besöka URL: er som på annat sätt blockeras av [säkra Länkar för ATP i Office 365](atp-safe-links.md).

I den här artikeln beskrivs hur du anger en lista med URL-adresser som är undantagna från genomsökning av Safe Links för ATP och några viktiga punkter att hålla koll på.

> [!NOTE]
> Om din organisation använder principer för säkra länkar är listan "Skriv inte in" är den enda metod som stöds för nät fiske test.

## <a name="set-up-a-do-not-rewrite-list"></a>Konfigurera en "Skriv ej-lista"

Säkerhets antal säkra Länkar för ATP-skydd använder flera listor, inklusive din organisations blockerade URL-adresser och "Skriv inte om"-listor för undantag. Om du har nödvändig behörighet kan du ställa in dina anpassade "Skriv inte om"-listor. Du kan göra detta när du lägger till eller redigerar principer för säkra länkar som gäller för specifika mottagare i organisationen.

Om du vill redigera (eller definiera) ATP-principer måste du ha en lämplig roll. Följande tabell innehåller några exempel. Mer information finns i [behörigheter i säkerhets & Compliance Center](permissions-in-the-security-and-compliance-center.md).

|Roll|Där/hur kopplat|
|---|---|
|global administratör|Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard. (Mer information finns i [om administratörs roller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)|
|Säkerhets administratör|Azure Active Directory-administratörs Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Organisations hantering i Exchange Online|Administrations Center för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>eller <br>  PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

> [!TIP]
> Mer information om roller och behörigheter finns i [behörigheter i säkerhets & Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>Så här visar eller redigerar du en anpassad "URL-lista" skrivs inte över "

1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt arbets-eller skol konto.

2. I det vänstra navigerings fältet, **Threat management** under \> **Policy** \> **skyddade länkar**för hot Management policy.

3. I avsnittet **principer som gäller för specifika mottagare** väljer du **nytt** (den nya knappen ser ut som ett plus tecken ( **+** )) för att skapa en ny princip. (Du kan även redigera en befintlig princip.)<br/>![Välj nytt för att lägga till en policy för säkra Länkar för specifika e-postmottagare](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. Ange ett namn och en beskrivning för principen.

5. Aktivera URL-adresser **skrivs om och** kontrol leras med en lista över kända illasinnade länkar när användaren klickar på länken.

6. Markera rutan **Ange en giltig URL** , ange en URL-adress och välj sedan plus tecknet (+) i avsnittet **Skriv inte över följande URL-adresser** .

7. I avsnittet **används för** väljer du **mottagaren är medlem i**och väljer sedan de grupper som du vill ta med i policyn. Välj **Lägg till**och sedan **OK**.

8. När du är klar med att lägga till URL-adresser väljer du **Spara**längst ned till höger på skärmen.

> [!NOTE]
> Se till att granska din organisations anpassade lista med blockerade URL: er. Se [Konfigurera en anpassad lista över blockerade URL-adresser med säkerhet för ATP](set-up-a-custom-blocked-urls-list-atp.md).

## <a name="important-points-to-keep-in-mind"></a>Viktiga saker att tänka på

- Alla URL-adresser som du anger i listan "Skriv inte in" exkluderas från sökningar efter de mottagare som du anger.

- Överväg att lägga till vanliga interna URL-adresser i listan "Skriv inte in" för att förbättra användar upplevelsen. Om du till exempel har lokala tjänster, till exempel Skype för företag eller SharePoint, kan du lägga till deras URL-adresser i listan för att utesluta dem från genomsökningen.

- Om du redan har en lista med URL-adresser i listan "Skriv inga ändringar" bör du kontrol lera listan och lägga till jokertecken. Om din befintliga lista till exempel har en post som `https://contoso.com/a` och du vill ta med under Sök vägar `https://contoso.com/a/b` i policyn lägger du till ett jokertecken i posten så att den ser ut `https://contoso.com/a/*` .

- När du anger en policy för "Skriv inte in om" för en princip för säkerhet för ATP kan du ta med upp till tre jokertecken ( \* ). Jokertecken inkluderar uttryckligen prefix eller under domäner. Posten är till exempel `contoso.com` inte samma sak som `*.contoso.com/*` eftersom `*.contoso.com/*` tillåter personer att besöka under domäner och sökvägar i den angivna domänen.

I följande tabell visas exempel på vad du kan ange och vilken effekt de har.

****

|Exempel post|Vad det gör|
|---|---|
|`contoso.com`|Gör det möjligt för mottagarna att besöka en webbplats, till exempel `https://contoso.com` inte under domäner eller sökvägar.|
|`*.contoso.com/*`|Gör det möjligt för mottagarna att besöka en domän, under domäner och sökvägar, till exempel `https://www.contoso.com` ,, `https://www.contoso.com` `https://maps.contoso.com` eller `https://www.contoso.com/a` . <br/><br/> Den här posten är mycket bättre än `*contoso.com*` eftersom den inte innehåller potentiellt bedrägliga webbplatser, till exempel `https://www.falsecontoso.com` eller `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Gör att specifika mottagare kan besöka en webbplats `https://contoso.com/a` , till exempel inte under Sök vägar `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Gör att specifika mottagare kan besöka en webbplats `https://contoso.com/a` , till exempel och under Sök vägar, till exempel `https://contoso.com/a/b`|
|
