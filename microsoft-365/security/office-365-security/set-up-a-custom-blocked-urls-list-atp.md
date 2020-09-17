---
title: Konfigurera en egen lista med blockerade URL-adresser med säkerhet för ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du konfigurerar en lista över blockerade URL-adresser för organisationen med hjälp av Office 365 Avancerat skydd.
ms.openlocfilehash: f66d447b980cae4a4afbb706f26659c5976bdf37
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948096"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a>Konfigurera en egen lista med blockerade URL-adresser med säkerhet för ATP

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md). Om du är hem användare letar efter information om säkra länkar i Outlook kan du läsa mer i [avancerad Outlook.com säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Med [Office 365 Avancerat skydd](office-365-atp.md) (ATP) kan din organisation ha en anpassad lista med webb adresser (URL: er) som blockeras. När en URL blockeras, tas de som klickar på länkar till den blockerade URL-adressen till en [varnings sida](atp-safe-links-warning-pages.md) som ser ut så här:

![Den här webbplatsen är blockerad](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

Listan blockerade URL-adresser definieras av organisationens säkerhets team för Microsoft 365 för företag och den listan gäller för alla i organisationen som omfattas av principer för säkra Länkar för Office 365.

Läs den här artikeln för att få reda på hur du konfigurerar din organisations anpassade blockerade URL-adresser för [säkraste ATP-länkar i Office 365](atp-safe-links.md).

## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>Visa eller redigera en anpassad lista med blockerade URL: er

Med [ATP-säkra länkar i Office 365](atp-safe-links.md) används flera listor, till exempel organisationens anpassade blockerade URL-adresser. Om du har nödvändig behörighet kan du ställa in organisationens anpassade lista. Det gör du genom att redigera organisationens standard princip för säkra länkar.

Om du vill redigera (eller definiera) ATP-principer måste du ha en av de roller som beskrivs i följande tabell:

****

|Roll|Där/hur kopplat|
|---|---|
|global administratör|Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard. (Mer information finns i [om administratörs roller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)|
|Säkerhets administratör|Azure Active Directory-administratörs Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Organisations hantering i Exchange Online|Administrations Center för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>eller <br>  PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

> [!TIP]
> Mer information om roller och behörigheter finns i [behörigheter i säkerhets & Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>Visa eller redigera en anpassad lista över blockerade URL-adresser

1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt arbets-eller skol konto.

2. I det vänstra navigerings fältet, under **Threat Management**, väljer du **policy** \> **Safe Links**.

3. I de **principer som gäller för hela avsnittet organisation** väljer du **standard**och sedan **Redigera** (knappen Redigera påminner om en penna).<br/>![Klicka på Redigera om du vill redigera standard principen för skydd av säkra länkar](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>Det gör att du kan visa din lista med blockerade URL-adresser. För det första kanske du inte har några URL-adresser här.<br/>![Lista över blockerade URL-adresser i standard principen för säkra länkar](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)

4. Markera rutan **Ange en giltig URL** , Skriv en URL och välj sedan plus tecknet ( **+** ).

5. När du är klar med att lägga till URL-adresser väljer du **Spara**längst ned till höger på skärmen.

## <a name="a-few-things-to-keep-in-mind"></a>Ett par saker du bör tänka på

Tänk på följande när du lägger till URL-adresser i listan:

- Ta inte med snedstreck ( **/** ) i slutet av webb adressen. I stället för att ange `https://www.contoso.com/` skriver du in `https://www.contoso.com` .

- Du kan ange en domän-URL (till exempel `contoso.com` eller `tailspintoys.com` ). Då blockeras klickningar på alla URL-adresser som innehåller domänen.

- Du kan ange en under domän (gilla `toys.contoso.com*` ) utan att blockera en fullständig domän (som `contoso.com` ). Då raderas en URL som innehåller under domänen, men blockerar inte klickningar till en URL som innehåller den fullständiga domänen.

- Du kan ta med upp till tre asterisker ( \* ) per URL. I tabellen nedan visas några exempel på vad du kan ange och vilken effekt de har.

****

|Exempel post|Vad det gör|
|---|---|
|`contoso.com` respektive `*contoso.com*`|Blockerar domänen, under domäner och sökvägar, till exempel `https://www.contoso.com` , `https://sub.contoso.com` och `https://contoso.com/abc`|
|`https://contoso.com/a`|Blockerar en webbplats `https://contoso.com/a` men inte fler under Sök vägar `https://contoso.com/a/b`|
|`https://contoso.com/a*`|Blockerar en webbplats `https://contoso.com/a` och ytterligare under Sök vägar som `https://contoso.com/a/b`|
|`https://toys.contoso.com*`|Blockerar en under domän ("leksaker" i det här fallet) men tillåter klickningar till andra domän adresser (till exempel `https://contoso.com` eller `https://home.contoso.com` ).|
|

> [!NOTE]
> Som standard kan du bara lägga till 500-URL: er i listan blockerade URL-adresser i Office 365-standard för Safe Links. En enskild URL får inte överstiga 128 tecken. Hela den blockerade URL-listan får inte innehålla fler än 10 000 tecken.

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>Så här definierar du undantag för vissa användare i en organisation

Om du vill att vissa grupper ska kunna visa URL-adresser som kan ha blockerats av andra kan du ange en policy för Safet ATP-länkar som gäller för specifika mottagare. Se [Konfigurera en anpassad "URL-lista", Skriv inte över "med hjälp av säkerhet för ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
