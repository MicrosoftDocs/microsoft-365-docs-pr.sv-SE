---
title: Konfigurera samling med virtuella certifikat – Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Administratörer kan läsa hur du skapar en virtuell certifikat samling som används för att validera S/MIME-certifikat i Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16c6d38882a69feb46aa3e8fadccd6e005426304
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825143"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Konfigurera ett virtuellt certifikat i Exchange Online för att verifiera S/MIME

Som administratör måste du konfigurera en samling med virtuella certifikat i Exchange Online som används för att validera S/MIME-certifikat. Den här virtuella certifikat samlingen är konfigurerad som ett certifikat Arkiv med ett SST-filnamnstillägg. Filen SST innehåller alla rot-och mellanliggande certifikat som används vid verifiering av ett S/MIME-certifikat.

## <a name="create-and-save-an-sst"></a>Skapa och spara en SST

Du kan skapa den här filen för SST-certifikatarkiv genom att exportera certifikaten från en betrodd dator med hjälp av cmdleten för **export-certifikat** i Windows PowerShell och ange _typ_ svärdet som SST. Anvisningar finns i [Exportera-certifikat](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).

När du har en SST-arkivfil kan du använda följande syntax i Exchange Online PowerShell för att spara innehållet i filen SST i det virtuella certifikat arkivet för Exchange Online. Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

I det här exemplet importeras filen C:\Mina Documents\Exported certifikat arkiv. SST.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Detaljerad information om syntax och parametrar finns i [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).

## <a name="ensuring-a-certificate-is-valid"></a>Att kontrol lera att ett certifikat är giltigt

I Exchange Online används bara SST för certifikat verifiering.

## <a name="more-information"></a>Mer information

[S/MIME för signering och kryptering av meddelanden](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
