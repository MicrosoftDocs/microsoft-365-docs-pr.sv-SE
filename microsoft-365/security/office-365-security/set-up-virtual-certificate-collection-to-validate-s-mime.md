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
ms.openlocfilehash: 89061e3c07803d741e25846ffe8a3325a12668a4
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035302"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="37097-103">Konfigurera virtuell certifikatsamling i Exchange Online för att validera S/MIME</span><span class="sxs-lookup"><span data-stu-id="37097-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

<span data-ttu-id="37097-104">Som administratör måste du konfigurera en virtuell certifikatsamling i Exchange Online som ska användas för att validera S/MIME-certifikat.</span><span class="sxs-lookup"><span data-stu-id="37097-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="37097-105">Den här virtuella certifikatsamlingen har konfigurerats som ett certifikatarkiv med filnamnstillägget SST.</span><span class="sxs-lookup"><span data-stu-id="37097-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="37097-106">SST-filen innehåller alla rot- och mellanliggande certifikat som används när ett S/MIME-certifikat valideras.</span><span class="sxs-lookup"><span data-stu-id="37097-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="37097-107">Skapa och spara en SST</span><span class="sxs-lookup"><span data-stu-id="37097-107">Create and save an SST</span></span>

<span data-ttu-id="37097-108">Du kan skapa den här SST-certifikatarkivfilen genom att exportera certifikaten från en betrodd dator med cmdlet **exportcertifikat** i Windows PowerShell och ange _typvärdet_ som SST.</span><span class="sxs-lookup"><span data-stu-id="37097-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="37097-109">Instruktioner finns i [Exportera-certifikat](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span><span class="sxs-lookup"><span data-stu-id="37097-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="37097-110">När du har filen SST-certifikatarkiv använder du följande syntax i Exchange Online PowerShell för att spara SST-filinnehållet i det virtuella Exchange Online-certifikatarkivet.</span><span class="sxs-lookup"><span data-stu-id="37097-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="37097-111">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="37097-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="37097-112">I det här exemplet importeras SST-filen C:\Mina dokument\Exporterat certifikatarkiv.sst.</span><span class="sxs-lookup"><span data-stu-id="37097-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="37097-113">Detaljerad syntax- och parameterinformation finns i [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="37097-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="37097-114">Se till att ett certifikat är giltigt</span><span class="sxs-lookup"><span data-stu-id="37097-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="37097-115">I Exchange Online används endast SST för certifikatvalidering.</span><span class="sxs-lookup"><span data-stu-id="37097-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="37097-116">Läs mer</span><span class="sxs-lookup"><span data-stu-id="37097-116">More Information</span></span>

[<span data-ttu-id="37097-117">S/MIME för signering och kryptering av meddelanden</span><span class="sxs-lookup"><span data-stu-id="37097-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="37097-118">Få-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="37097-118">Get-SmimeConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig)
