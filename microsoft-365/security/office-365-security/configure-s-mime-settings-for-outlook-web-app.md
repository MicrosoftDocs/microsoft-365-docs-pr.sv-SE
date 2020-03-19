---
title: Konfigurera S/MIME-inställningar i Exchange Online för Outlook på webben
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
ms.openlocfilehash: 354b247c2b0e0e610e6cb0626f4a404b582db717
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "42805659"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Konfigurera S/MIME-inställningar i Exchange Online för Outlook på webben

Som administratör för Exchange Online kan du konfigurera Outlook på webben (tidigare känt som Outlook Web App) så att du kan skicka och ta emot S/MIME-skyddade meddelanden. Använd **cmdlets-cmdlets get-SmimeConfig** och **Set-SmimeConfig** för att visa och hantera den här funktionen i Exchange Online PowerShell. Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

Detaljerad syntax- och parameterinformation finns i [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) och [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Överväganden för nya Microsoft Edge (Krom-baserade)

Om du vill använda S/MIME i Outlook på webben i den nya [webbläsaren Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) måste du (eller en annan administratör) ange och konfigurera webbläsarpolicyn för Microsoft Edge med namnet **ExtensionInstallForcelist** för att installera microsofts/MIME-tillägget i nya Microsoft Edge. Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`. Och observera att tillämpa den här principen kräver domänanslutna datorer, så med hjälp av S / MIME i den nya Microsoft Edge webbläsare effektivt kräver domänanslutna datorer.

Mer information om principen **ExtensionInstallForcelist** finns i [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Det här steget är en förutsättning för att använda nya Microsoft Edge. Den ersätter inte S/MIME-kontrollen som är installerad av användare. Användare uppmanas att hämta och installera S/MIME-kontrollen i Outlook på webben under den första användningen av S/MIME. Eller så kan användarna proaktivt gå till **S/MIME** i sina Outlook på webbinställningarna för att hämta länken för kontrollen.

## <a name="considerations-for-chrome"></a>Överväganden för Chrome

Om du vill använda S/MIME i Outlook på webben i webbläsaren Google Chrome måste du (eller en annan administratör) ange och konfigurera kromprincipen **ExtensionInstallForcelist** för att installera microsofts/MIME-tillägget i Chrome. Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`. Och observera att tillämpa den här principen kräver domänanslutna datorer, så med hjälp av S / MIME i Chrome effektivt kräver domänanslutna datorer.

Mer information om principen **ExtensionInstallForcelist** finns i [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Det här steget är en förutsättning för att använda Chrome. Den ersätter inte S/MIME-kontrollen som är installerad av användare. Användare uppmanas att hämta och installera S/MIME-kontrollen i Outlook på webben under den första användningen av S/MIME. Eller så kan användarna proaktivt gå till **S/MIME** i sina Outlook på webbinställningarna för att hämta länken för kontrollen.

## <a name="for-more-information"></a>Mer information

[S/MIME för meddelandesignering och kryptering](s-mime-for-message-signing-and-encryption.md)
