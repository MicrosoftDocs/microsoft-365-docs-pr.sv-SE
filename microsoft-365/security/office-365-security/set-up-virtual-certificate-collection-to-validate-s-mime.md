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
description: Administratörer kan lära sig hur de skapar en virtuell certifikatsamling som används för att verifiera S/MIME-certifikat i Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a5dad897ce58b8496551535cc28e03c7a1fa964
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207485"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Konfigurera insamling av virtuella certifikat i Exchange Online för att verifiera S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Som administratör måste du konfigurera en virtuell certifikatsamling i Exchange Online som ska användas för att verifiera S/MIME-certifikat. Den här virtuella certifikatsamlingen är konfigurerad som ett certifikatarkiv med filnamnstillägget SST. SST-filen innehåller alla rot- och mellanliggande certifikat som används vid validering av ett S/MIME-certifikat.

## <a name="create-and-save-an-sst"></a>Skapa och spara en SST

Du kan skapa den här SST-certifikatarkivfilen genom att exportera certifikaten från en betrodd dator med hjälp av cmdleten **Export-Certificate** i Windows PowerShell och ange värdet _Type_ som SST. Instruktioner finns i [Exportera certifikat.](/powershell/module/pkiclient/export-certificate)

När du har SST-certifikatarkivfilen ska du använda följande syntax i Exchange Online PowerShell för att spara SST-filinnehållet i det virtuella certifikatarkivet för Exchange Online. Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

I det här exemplet importeras SST-filen C:\My Documents\Exported Certificate Store.sst.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Detaljerad information om syntax och parametrar finns i [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).

## <a name="ensuring-a-certificate-is-valid"></a>Kontrollera att ett certifikat är giltigt

I Exchange Online används endast SST för certifikatverifiering.

## <a name="more-information"></a>Mer information

[S/MIME för signering och kryptering av meddelanden](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig)