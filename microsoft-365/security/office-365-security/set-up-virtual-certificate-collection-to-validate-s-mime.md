---
title: Konfigurera virtuell certifikatsamling - Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Administratörer kan lära sig hur du skapar en virtuell certifikatsamling som ska användas för att validera S/MIME-certifikat i Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5bd453383a263fdb2c0c7e2ce0014ad205e5fdc2
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352175"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Konfigurera virtuell certifikatsamling i Exchange Online för att validera S/MIME

Som administratör måste du konfigurera en virtuell certifikatsamling i Exchange Online som ska användas för att validera S/MIME-certifikat. Den här virtuella certifikatsamlingen har konfigurerats som ett certifikatarkiv med filnamnstillägget SST. SST-filen innehåller alla rot- och mellanliggande certifikat som används när ett S/MIME-certifikat valideras.

## <a name="create-and-save-an-sst"></a>Skapa och spara en SST

Du kan skapa den här SST-certifikatarkivfilen genom att exportera certifikaten från en betrodd dator med cmdlet **exportcertifikat** i Windows PowerShell och ange _typvärdet_ som SST. Instruktioner finns i [Exportera-certifikat](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).

När du har filen SST-certifikatarkiv använder du följande syntax i Exchange Online PowerShell för att spara SST-filinnehållet i det virtuella Exchange Online-certifikatarkivet. Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

I det här exemplet importeras SST-filen C:\Mina dokument\Exporterat certifikatarkiv.sst.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Detaljerad syntax- och parameterinformation finns i [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).

## <a name="ensuring-a-certificate-is-valid"></a>Se till att ett certifikat är giltigt

I Exchange Online används endast SST för certifikatvalidering.

## <a name="more-information"></a>Mer information

[S/MIME för signering och kryptering av meddelanden](s-mime-for-message-signing-and-encryption.md)

[Få-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
