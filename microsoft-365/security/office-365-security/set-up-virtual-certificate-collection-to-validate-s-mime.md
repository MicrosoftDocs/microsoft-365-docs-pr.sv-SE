---
title: Konfigurera insamling av virtuella certifikat – Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Administratörer kan lära sig hur man skapar en virtuell certifikatsamling som används för att verifiera S/MIME-certifikat i Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4537ecfa6d800294af9572e462ce18491ce2c441
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "50290483"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Konfigurera insamling av virtuella certifikat i Exchange Online för att verifiera S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Som administratör måste du konfigurera en virtuell certifikatsamling i Exchange Online som ska användas för att verifiera S/MIME-certifikat. Den här virtuella certifikatsamlingen är konfigurerad som ett certifikatarkiv med filnamnstillägget SST. SST-filen innehåller alla rotcertifikat och mellanliggande certifikat som används vid validering av ett S/MIME-certifikat.

## <a name="create-and-save-an-sst"></a>Skapa och spara en SST

Du kan skapa den här SST-certifikatarkivfilen genom att exportera certifikaten från en betrodd dator  med cmdleten **Export-Certificate** i Windows PowerShell och ange typvärdet som SST. Instruktioner finns i [Export-Certificate.](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)

När du har SST-certifikatarkivfilen använder du följande syntax i Exchange Online PowerShell för att spara SST-filens innehåll i det virtuella Certifikatarkivet i Exchange Online. Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

I det här exemplet importeras SST-filen C:\Mina dokument\Exporterat certifikatarkiv.sst.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Detaljerad information om syntax och parametrar finns [i Set-SmimeConfig.](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)

## <a name="ensuring-a-certificate-is-valid"></a>Säkerställa att ett certifikat är giltigt

I Exchange Online används endast SST-programmet för certifikatverifiering.

## <a name="more-information"></a>Mer information

[S/MIME för signering och kryptering av meddelanden](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
