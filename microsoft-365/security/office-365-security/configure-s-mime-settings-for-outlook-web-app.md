---
title: Konfigurera S/MIME-inställningar – Exchange Online för Outlook på webben
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: En kort beskrivning av vad Exchange Online-administratörer behöver göra för att visa och konfigurera S/MIME-inställningarna i Outlook på webben i Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c1496025124717688cc812e22e0d8fe3a441112
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616628"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Konfigurera S/MIME-inställningar i Exchange Online för Outlook på webben

Som administratör för Exchange Online kan du konfigurera Outlook på webben (tidigare kallat Outlook Web App) så att s/mime-skyddade meddelanden kan skickas och ta emot. Använd cmdletsna **Get-SmimeConfig** och **Set-SmimeConfig** för att visa och hantera den här funktionen i Exchange Online PowerShell. Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Detaljerad syntax- och parameterinformation finns i [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) och [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Överväganden för nya Microsoft Edge (Krom-baserade)

Om du vill använda S/MIME i Outlook på webben i den nya [Microsoft Edge-webbläsaren](https://www.microsoft.com/windows/microsoft-edge) måste du (eller en annan administratör) ange och konfigurera microsoft edge-webbläsarprincipen **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i nya Microsoft Edge. Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Och observera att tillämpa denna princip kräver domän-anslutna datorer, så att använda S / MIME i den nya Microsoft Edge webbläsare kräver effektivt domän-anslutna datorer.

Mer information om principen **ExtensionInstallForcelist** finns i [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Det här steget är en förutsättning för att använda nya Microsoft Edge. Den ersätter inte S/MIME-kontrollen som installeras av användare. Användare uppmanas att hämta och installera S/MIME-kontrollen i Outlook på webben under den första användningen av S/MIME. Eller så kan användare proaktivt gå till **S/MIME** i sina Outlook på webbinställningarna för att få nedladdningslänken för kontrollen.

## <a name="considerations-for-chrome"></a>Överväganden för Chrome

Om du vill använda S/MIME i Outlook på webben i webbläsaren Google Chrome måste du (eller en annan administratör) ange och konfigurera Chromium-principen **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i Chrome. Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Och observera att tillämpa den här principen kräver domänanslutna datorer, så att använda S/MIME i Chrome kräver effektivt domänanslutna datorer.

Mer information om principen **ExtensionInstallForcelist** finns i [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Det här steget är en förutsättning för att använda Chrome. Den ersätter inte S/MIME-kontrollen som installeras av användare. Användare uppmanas att hämta och installera S/MIME-kontrollen i Outlook på webben under den första användningen av S/MIME. Eller så kan användare proaktivt gå till **S/MIME** i sina Outlook på webbinställningarna för att få nedladdningslänken för kontrollen.

## <a name="for-more-information"></a>Mer information

[S/MIME för signering och kryptering av meddelanden](s-mime-for-message-signing-and-encryption.md)
