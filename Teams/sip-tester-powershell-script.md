---
title: 測試直接路由會話邊界控制器連接的 PowerShell 腳本
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本範例來測試直接路由會話邊界控制器Microsoft Teams。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1258f85219e5ce6c00f8db5dac3a5233ce2c0717
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627095"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>測試直接路由會話邊界控制器連接的 PowerShell 腳本

SIP 測試程式用戶端是一個範例 PowerShell 腳本，可用於測試直接路由會話邊界控制器 (SBC) 連接Microsoft Teams。 此腳本會使用直接路由測試由客戶配對的會話初始通訊協定 (SIP) 主幹的基本功能。

腳本會提交 SIP 測試給測試執行者、等待結果，然後以可讀取的格式呈現。 您可以使用此腳本來測試下列案例：

- 外發和傳入通話
- 同時響鈴
- 媒體升級
- 諮詢轉移

## <a name="download-the-script-and-documentation"></a>下載腳本和檔

下載 [SIP 測試程式用戶端腳本和檔](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。

  > [!NOTE]
  > SIP 測試程式用戶端腳本僅 adal.ps 版本 3.19.8.1。 如果使用較新版本的版本，就會 adal.ps 錯誤。
  
  
