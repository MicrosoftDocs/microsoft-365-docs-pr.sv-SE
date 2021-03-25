---
title: Konfigurera S/MIME-inställningar – Exchange Online för Outlook på webben
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: En kort beskrivning av vad Exchange Online-administratörer behöver göra för att visa och konfigurera S/MIME-inställningar i Outlook på webben i Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6eacc6a264682474054d0d3546b831039bee9a0c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207006"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Konfigurera S/MIME-inställningar i Exchange Online för Outlook på webben

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Som administratör för Exchange Online kan du konfigurera Outlook på webben (kallades tidigare för Outlook Web App) så att du kan skicka och ta emot S/MIME-skyddade meddelanden. Använd **cmdletarna Get-SmimeConfig** och **Set-SmimeConfig** för att visa och hantera den här funktionen i Exchange Online PowerShell. Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

Detaljerad information om syntax och parametrar finns i [Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) och [Set-SmimeConfig.](/powershell/module/exchange/set-smimeconfig)

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Att tänka på för nya Microsoft Edge (Chromium-baserad)

Om du vill använda S/MIME i Outlook på webben i den nya [Webbläsaren Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) måste du (eller en annan administratör) konfigurera webbläsarprincipen för Microsoft Edge med namnet **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i den nya Microsoft Edge. Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Observera att användning av den här principen kräver domän-anslutna eller Azure AD-anslutna enheter, så användning av S/MIME i den nya webbläsaren Microsoft Edge kräver effektivt domän-anslutna eller Azure AD-anslutna enheter.

Mer information om **principen ExtensionInstallForcelist** finns i [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Det här steget krävs för att använda nya Microsoft Edge. Den ersätter inte den S/MIME-kontroll som installeras av användare. Användarna uppmanas att ladda ned och installera S/MIME-kontrollen i Outlook på webben vid första användningen av S/MIME. Eller så kan användare proaktivt gå till **S/MIME** i sina Outlook på webben-inställningar för att få nedladdningslänken för kontrollen.

## <a name="considerations-for-chrome"></a>Att tänka på för Chrome

Om du vill använda S/MIME i Outlook på webben i Google Chrome-webbläsaren måste du (eller en annan administratör) konfigurera Chromium-principen med namnet **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i Chrome. Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Observera att det krävs domänbaserade datorer för att kunna använda den här principen, så det krävs att du verkligen använder domänbaserade datorer i Chrome.

Mer information om **principen ExtensionInstallForcelist** finns i [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Det här steget krävs för att använda Chrome. Den ersätter inte den S/MIME-kontroll som installeras av användare. Användarna uppmanas att ladda ned och installera S/MIME-kontrollen i Outlook på webben vid första användningen av S/MIME. Eller så kan användare proaktivt gå till **S/MIME** i sina Outlook på webben-inställningar för att få nedladdningslänken för kontrollen.

## <a name="for-more-information"></a>Mer information

[S/MIME för signering och kryptering av meddelanden](s-mime-for-message-signing-and-encryption.md)