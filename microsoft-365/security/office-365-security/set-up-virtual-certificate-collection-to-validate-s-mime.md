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
ms.openlocfilehash: aabd234f344778b2bfad34a7046bb51c55ed4b3d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197207"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="708bf-103">Konfigurera ett virtuellt certifikat i Exchange Online för att verifiera S/MIME</span><span class="sxs-lookup"><span data-stu-id="708bf-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="708bf-104">Som administratör måste du konfigurera en samling med virtuella certifikat i Exchange Online som används för att validera S/MIME-certifikat.</span><span class="sxs-lookup"><span data-stu-id="708bf-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="708bf-105">Den här virtuella certifikat samlingen är konfigurerad som ett certifikat Arkiv med ett SST-filnamnstillägg.</span><span class="sxs-lookup"><span data-stu-id="708bf-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="708bf-106">Filen SST innehåller alla rot-och mellanliggande certifikat som används vid verifiering av ett S/MIME-certifikat.</span><span class="sxs-lookup"><span data-stu-id="708bf-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="708bf-107">Skapa och spara en SST</span><span class="sxs-lookup"><span data-stu-id="708bf-107">Create and save an SST</span></span>

<span data-ttu-id="708bf-108">Du kan skapa den här filen för SST-certifikatarkiv genom att exportera certifikaten från en betrodd dator med hjälp av cmdleten för **export-certifikat** i Windows PowerShell och ange _typ_ svärdet som SST.</span><span class="sxs-lookup"><span data-stu-id="708bf-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="708bf-109">Anvisningar finns i [Exportera-certifikat](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span><span class="sxs-lookup"><span data-stu-id="708bf-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="708bf-110">När du har en SST-arkivfil kan du använda följande syntax i Exchange Online PowerShell för att spara innehållet i filen SST i det virtuella certifikat arkivet för Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="708bf-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="708bf-111">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="708bf-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="708bf-112">I det här exemplet importeras filen C:\Mina Documents\Exported certifikat arkiv. SST.</span><span class="sxs-lookup"><span data-stu-id="708bf-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="708bf-113">Detaljerad information om syntax och parametrar finns i [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="708bf-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="708bf-114">Att kontrol lera att ett certifikat är giltigt</span><span class="sxs-lookup"><span data-stu-id="708bf-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="708bf-115">I Exchange Online används bara SST för certifikat verifiering.</span><span class="sxs-lookup"><span data-stu-id="708bf-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="708bf-116">Mer information</span><span class="sxs-lookup"><span data-stu-id="708bf-116">More Information</span></span>

[<span data-ttu-id="708bf-117">S/MIME för signering och kryptering av meddelanden</span><span class="sxs-lookup"><span data-stu-id="708bf-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="708bf-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="708bf-118">Get-SmimeConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
