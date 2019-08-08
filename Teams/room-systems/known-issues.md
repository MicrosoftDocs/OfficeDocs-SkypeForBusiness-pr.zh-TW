---
title: 已知問題
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
description: 本文將討論 Microsoft 團隊聊天室的已知問題 (依功能區域)。
ms.openlocfilehash: fab004336d5a349bd0548479395ef0c25eb642c7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243429"
---
# <a name="known-issues"></a>已知問題 
 
本文列出 [Microsoft 團隊聊天室] 的已知問題 (依功能區域)。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>時更新 

| 問題標題 |  行為\/症狀 | 已知的解決方法 | 知識庫文章 |
|  ---        |      ---             |   ---            | --- |
|  App 已過期         |    Microsoft [團隊聊天室] 主控台顯示「系統組態已過期」錯誤。                |   [使用 Microsoft 團隊會議室恢復工具](recovery-tool.md)             |  無 |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>使用者介面 

| 問題標題 |  行為\/症狀 | 已知的解決方法 | 知識庫文章 |
|  ---        |      ---             |   ---            | --- |
|找不到虛擬鍵盤   | 當您需要在 Microsoft 團隊聊天室中輸入資訊時, 不會顯示虛擬鍵盤。 此問題會在 Windows 10 創意者更新 (版本 1703) 安裝于 Microsoft 團隊聊天室正在執行的 Surface Pro 4 上。 | 若要解決此問題, 請手動開啟虛擬鍵盤。 若要這樣做, 請執行下列步驟:<br><br> **1.** 敲擊並按住工作列, 然後按 [**顯示觸控式鍵盤**] 按鈕。 鍵盤圖示應該出現在工作列的右側。 <br><br> **2.** 輕觸鍵盤圖示以開啟虛擬鍵盤。 | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>硬體

| 問題標題 |  行為\/症狀 | 已知的解決方法 | 知識庫文章 |
|  ---        |      ---             |   ---            |   --- |
| 未偵測到監視器 | 當您在 Surface Pro (模型 2017) 裝置上執行 Microsoft 團隊聊天室時, 系統不會偵測到監視器。 |  按住 Surface Pro 電源按鈕20秒以上的時間。 當您這麼做時, 裝置會重新開機並清除圖形快取。 |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>限制與預期行為

***

Microsoft 團隊會議室不支援 HDCP 輸入, 但已觀察到可導致 HDMI 攝取功能 (影片、音訊) 的問題。 請務必小心, 確定連線至 Microsoft 團隊聊天室的交換器已關閉 HDCP 選項。 

***

用來做為會議室顯示幕正面的消費者電視必須支援 HDMI 的消費者電子產品控制 (CEC) 功能, 才能從待機模式自動切換到作用中的影片來源。 並非所有電視都支援這項功能。

***

請務必使用有線 1 Gbps 網路連線, 以確保您有所需的頻寬。 

***

如果您的 Microsoft 團隊聊天室裝置無法與網域失去信任, 您就無法在裝置上進行驗證, 也無法開啟 [設定]。 例如, 如果您在網域加入後從網域中移除 Microsoft 團隊聊天室, 信任就會遺失。 解決方法是使用本機管理員帳戶登入。 
***
Microsoft 團隊聊天室版本3.0.12.0 不再支援64位版本的 Windows 10 Enterprise 周年紀念日 (英文、版本 1607)。 
***
Microsoft [團隊會議室] 是一個多視窗應用程式, 且需要將房間顯示器正面連接到裝置的 HDMI 埠, 才能讓 app 正常運作。 如果您正在測試, 但尚未購買顯示器, 請確定您已連接 HDMI 顯示器, 或使用虛擬 HDMI 插頭。
***
<a name="See"> </a>  
## <a name="see-also"></a>另請參閱

[Microsoft 團隊聊天室說明](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft 團隊聊天室](skype-room-systems-v2.md)
