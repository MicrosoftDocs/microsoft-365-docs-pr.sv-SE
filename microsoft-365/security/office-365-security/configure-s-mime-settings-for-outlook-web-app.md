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
ms.openlocfilehash: a81db5ec933f1d0d6e2944103be53c0169dde62f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165685"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Konfigurera S/MIME-inställningar i Exchange Online för Outlook på webben

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Som administratör för Exchange Online kan du konfigurera Outlook på webben (tidigare Outlook Web App) så att s/MIME-skyddade meddelanden kan skickas och tas emot. Använd **cmdletarna Get-SmimeConfig** och **Set-SmimeConfig** för att visa och hantera den här funktionen i Exchange Online PowerShell. Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Detaljerad information om syntax och parametrar finns i [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) och [Set-SmimeConfig.](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Att tänka på för nya Microsoft Edge (Chromium-baserad)

Om du vill använda S/MIME i Outlook på webben i den nya [webbläsaren Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) måste du (eller en annan administratör) ange och konfigurera Microsoft Edge-webbläsarprincipen med namnet **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i den nya Microsoft Edge. Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Observera att det krävs domän anslutna eller Azure AD-anslutna enheter för att kunna använda den här principen, så att du måste använda S/MIME i den nya Webbläsaren Microsoft Edge på ett effektivt sätt för domän anslutna eller Azure AD-anslutna enheter.

Mer information om **policyn ExtensionInstallForcelist** finns [i ExtensionInstallForcelist.](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)

Det här steget är en förutsättning för att du ska kunna använda nya Microsoft Edge. Den ersätter inte den S/MIME-kontroll som installeras av användare. Användare uppmanas att ladda ned och installera S/MIME-kontrollen i Outlook på webben vid första användningen av S/MIME. Användare kan också proaktivt gå till **S/MIME** i sina Outlook på webben-inställningar för att få nedladdningslänken för kontrollen.

## <a name="considerations-for-chrome"></a>Att tänka på när det gäller Chrome

Om du vill använda S/MIME i Outlook på webben i webbläsaren Google Chrome måste du (eller någon annan administratör) ange och konfigurera Chromium-principen med namnet **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i Chrome. Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Observera också att det krävs domänbaserade datorer för att kunna använda den här principen, så att du måste använda S/MIME i Chrome på ett effektivt sätt.

Mer information om **policyn ExtensionInstallForcelist** finns [i ExtensionInstallForcelist.](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)

Det här steget krävs för att använda Chrome. Den ersätter inte den S/MIME-kontroll som installeras av användare. Användare uppmanas att ladda ned och installera S/MIME-kontrollen i Outlook på webben vid första användningen av S/MIME. Användare kan också proaktivt gå till **S/MIME** i sina Outlook på webben-inställningar för att få nedladdningslänken för kontrollen.

## <a name="for-more-information"></a>Mer information

[S/MIME för signering och kryptering av meddelanden](s-mime-for-message-signing-and-encryption.md)
