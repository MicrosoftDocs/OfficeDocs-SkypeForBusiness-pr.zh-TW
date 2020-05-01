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
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43d1514eff811461ac8b6ad73f7c2a215205f4e3
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951258"
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

  > [!NOTE]
  > SIP 測試用戶端腳本只支援 adal.ps 版本3.19.8.1。 如果使用的是更新版本的 adal.ps，就會傳回錯誤。
  
  
