---
title: 測試直接路由會話邊界控制器連線的 PowerShell 腳本
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本範例來測試 Microsoft 團隊中的直接路由會話框線控制器連線。
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6df8ee654696ceef89c36a354d943c97139bf8b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37639314"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>測試直接路由會話邊界控制器連線的 PowerShell 腳本

SIP 測試者用戶端是一個範例 PowerShell 腳本，您可以用來測試 Microsoft 團隊中的直接路由會話邊界控制器（SBC）連線。 此腳本會利用直接路由來測試客戶配對會話初始通訊協定（SIP）幹線的基本功能。

此腳本會將 SIP 測試提交至測試回合程式，等待結果，然後以易於閱讀的格式呈現。 您可以使用此腳本來測試下列案例：

- 輸出和撥出通話
- 同時撥打
- 媒體升級
- 顧問式轉接

## <a name="download-the-script-and-documentation"></a>下載腳本與檔

下載[SIP 測試程式用戶端腳本及檔](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。