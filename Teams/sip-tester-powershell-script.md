---
title: 測試直接路由會話框線控制器連線的 PowerShell 腳本
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本範例來測試 Microsoft Teams 中的直接路由會話邊界控制器連線。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 215edfed535352004c960182bd649721131aedb0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564131"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>測試直接路由會話框線控制器連線的 PowerShell 腳本

SIP 測試人員用戶端是範例 PowerShell 腳本，您可以在 Microsoft Teams 中測試直接路由會話框線控制器 (SBC) 連線。 此腳本會測試客戶配對的會話初始通訊協定的基本功能 (SIP) 主幹搭配直接路由。

腳本會將 SIP 測試提交給測試的測試者，等待結果，然後以人為閱讀的格式呈現。 您可以使用此腳本來測試下列案例：

- 撥出和輸入通話
- 同時撥打
- 媒體升級
- 轉場轉移

## <a name="download-the-script-and-documentation"></a>下載腳本和檔

下載 [SIP 測試人員用戶端腳本和檔](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。

  > [!NOTE]
  > SIP 測試人員用戶端腳本僅支援 adal.ps 版本 3.19.8.1。 如果使用更新版本的 adal.ps，將會傳回錯誤。
  
  
