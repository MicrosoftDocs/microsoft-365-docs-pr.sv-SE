---
title: Skapa och hantera enhetstaggar
description: Använd enhetstaggar för att gruppera enheter för att samla kontext och möjliggöra dynamiskt listskapande som en del av ett incident
keywords: taggar, enhetstaggar, enhetsgrupper, grupper, åtgärd, nivå, regler, aad-grupp, roll, tilldela, rangordna
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4a64d3242a34ec8bf6d5646513170aa35dd3a94c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076929"
---
# <a name="create-and-manage-device-tags"></a>Skapa och hantera enhetstaggar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Lägg till taggar på enheter för att skapa logiskt grupp samarbete. Enhetstaggar stöder korrekt mappning av nätverket, så att du kan bifoga olika taggar för att fånga sammanhang och möjliggöra skapande av dynamiska listor som en del av ett problem. Taggar kan användas som ett filter i **listvyn Enheter** eller för att gruppera enheter. Mer information om enhetsgruppering finns i [Skapa och hantera enhetsgrupper.](machine-groups.md)

Du kan lägga till taggar på enheter på följande sätt:

- Med hjälp av portalen
- Ange ett registernyckelvärde

> [!NOTE]
> Det kan finnas viss svarstid mellan det att en tagg läggs till på en enhet och dess tillgänglighet i listan enheter och på sidan enhet.  

Information om hur du lägger till enhetstaggar med API finns [i Lägga till eller ta bort API för enhetstaggar.](add-or-remove-machine-tags.md)

## <a name="add-and-manage-device-tags-using-the-portal"></a>Lägga till och hantera enhetstaggar via portalen

1. Välj den enhet där du vill hantera taggar. Du kan välja eller söka efter en enhet i någon av följande vyer:

   - **Instrumentpanel för** säkerhetsåtgärder – Välj enhetens namn i avsnittet Populära enheter med aktiva aviseringar.
   - **Telefonaviseringar** – Välj enhetsnamnet bredvid enhetsikonen från aviseringskön.
   - **Listan Enheter** – Välj enhetsnamnet i listan över enheter.
   - **Sökruta** – Välj enhet i listrutan och ange enhetens namn.

     Du kan också gå till aviseringssidan via filen och IP-vyerna.

2. Välj **Hantera taggar** i raden med svarsåtgärder.

    ![Bild på knappen Hantera taggar](images/manage-tags.png)

3. Skriv för att hitta eller skapa taggar

    ![Bild av att lägga till taggar på en enhet1](images/new-tags.png)

Taggar läggs till i enhetsvyn och visas även i **listvyn** Enheter. Sedan kan du använda **filtret Taggar** för att se den relevanta listan över enheter.

>[!NOTE]
> Filtrering kanske inte fungerar på taggnamn som innehåller parenteser.<br>
> När du skapar en ny tagg visas en lista med befintliga taggar. I listan visas bara taggar som skapats via portalen. Befintliga taggar som skapats från klientenheter visas inte.

Du kan också ta bort taggar från den här vyn.

![Bild av att lägga till taggar på en enhet2](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a>Lägga till enhetstaggar genom att ange ett registernyckelvärde

>[!NOTE]
> Endast tillämpligt på följande enheter:
>- Windows 10, version 1709 eller senare
>- Windows Server, version 1803 eller senare
>- Windows Server 2016
>- Windows Server 2012 R2
>- Windows Server 2008 R2 SP1
>- Windows 8.1
>- Windows 7 SP1

> [!NOTE] 
> Det maximala antalet tecken som kan anges i en tagg är 200.

Enheter med liknande taggar kan vara praktiska när du behöver tillämpa sammanhangsberoende åtgärder på en viss lista med enheter.

Använd följande registernyckelpost för att lägga till en tagg på en enhet:

- Registernyckel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`
- Registernyckelvärde (REG_SZ): `Group`
- Registernyckeldata: `Name of the tag you want to set`

>[!NOTE]
>Enhetstaggen är en del av enhetsinformationsrapporten som genereras en gång om dagen. Alternativt kan du välja att starta om slutpunkten som överför en ny enhetsinformationsrapport.
> 
> Om du behöver ta bort en tagg som lagts till med ovanstående registernyckel rensar du innehållet i registernyckeldata i stället för att ta bort gruppnyckeln.
