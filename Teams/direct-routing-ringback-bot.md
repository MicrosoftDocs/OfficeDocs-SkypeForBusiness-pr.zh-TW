---
title: 設定直接路由的 Ringback bot
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: 瞭解如何使用 Ringback bot 進行直接路由，避免在建立通話時可能發生的意外 silences。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26738002ab333d2490ef0dac5674a1f7cdc19efd
ms.sourcegitcommit: 8974cd7a693bc879fed8222f551fd7ce3205dd65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420953"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>設定直接路由的 Ringback bot

本文將說明 Ringback bot，您可以用來協助避免在通話時間較長時可能會發生的意外 silences。 您可以在非媒體旁路模式中直接路由使用 Ringback bot。

有時，來自公開交換電話網絡的入站呼叫 (PSTN) 給團隊用戶端可能需要比預期更長的時間才能建立。 發生這種情況可能有多種原因。 在這種情況下，來電者可能不會聽到任何問題，小組用戶端就不會響鈴，而且有些電訊供應商可能會取消通話。

Ringback bot 可協助避免在此案例中可能發生的意外 silences。 對於從 PSTN 到團隊用戶端的撥入呼叫，Ringback bot 會在來電者中播放獨特的音訊信號，表示小組正在進行通話的過程。

> [!NOTE]
> Ringback bot 會產生來自團隊後端的早期媒體。 在某些國家和地區，您可能會在媒體開始流動時為通話付費。

## <a name="configure-the-ringback-bot"></a>設定 Ringback bot

使用 [CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) Cmdlet 來修改先前定義的會話邊界控制器 (SBC) 設定，或 CsOnlinePSTNGateway Cmdlet，以建立新 [的](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) SBC 配置，以及 **GenerateRingingWhileLocatingUser** 參數來設定 Ringback bot：

- 若要開啟 Ringback bot，請將 **GenerateRingingWhileLocatingUser** 參數設定為 [ **$True**]。 此為預設值。 

- 若要關閉 Ringback bot，請將 **GenerateRingingWhileLocatingUser** 參數設定為 [ **$False**]。 

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
