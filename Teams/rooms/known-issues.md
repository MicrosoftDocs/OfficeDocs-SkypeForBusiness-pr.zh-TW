---
title: 已知問題
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 本文將討論 Microsoft 團隊聊天室的已知問題（依功能區域）。
ms.openlocfilehash: e0b22d55de5fcf2fd49cf795497f2cb26c1952cf
ms.sourcegitcommit: 708270f1fecab6b7b44345d57a8e12bc36d19c8b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2020
ms.locfileid: "43102374"
---
# <a name="known-issues"></a>已知問題 
 
本文列出 [Microsoft 團隊聊天室] 的已知問題（依功能區域）。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>時更新 

| 問題標題 |  行為\/症狀 | 已知的因應措施 | 知識庫文章 |
|  ---        |      ---             |   ---            | --- |
|  App 已過期         |    Microsoft [團隊聊天室] 主控台顯示「系統組態已過期」錯誤。                |   [使用 Microsoft 團隊會議室恢復工具](recovery-tool.md)             |  無 |
|  裝置更新為不受支援的 Windows 10 版本   |    Windows 10 裝置從版本1803更新至不受支援的版本1809。 支援的版本為1903。 |   如果 DeferFeatureUpdatesPeriodinDays 設定的[群組原則或 MDM](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb)設定（可讓您將功能更新推遲至指定的天數），則會發生這種情況，將其設定為最大值365天。 <br><br> Microsoft 團隊聊天室不支援 Windows 10 版本1809，而版本1903則受支援。 不過，從2020年3月27日起，版本1809超過365天。 如果此設定未變更，Windows 會嘗試安裝版本1809，這可能會導致 Microsoft 團隊聊天室發生問題。<br><br>若要避免這種情況，請**移除**任何群組原則或任何推遲更新的 MDM 設定。 這可讓 Windows 更新到最新支援的 OS 版本。 <br><br>**重要**必須**移除**[群組原則] 或 [MDM] 設定（[保留未設定]），且**未設定為 0**。 如果原則設定為0，Windows 會採用可能不受支援的最新可用版本。 |  無 |

<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>使用者介面 

| 問題標題 |  行為\/症狀 | 已知的因應措施 | 知識庫文章 |
|  ---        |      ---             |   ---            | --- |
|找不到虛擬鍵盤   | 當您需要在 Microsoft 團隊聊天室中輸入資訊時，不會顯示虛擬鍵盤。 這個問題會發生在 Windows 10 版本1903。 | 透過 Windows 更新，為 Windows 10 （版本1903）安裝2020-04 累積更新。  | 無 | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>硬體

| 問題標題 |  行為\/症狀 | 已知的因應措施 | 知識庫文章 |
|  ---        |      ---             |   ---            |   --- |
| 未偵測到監視器 | 當您在 Surface Pro （模型2017）裝置上執行 Microsoft 團隊聊天室時，系統不會偵測到監視器。 |  按住 Surface Pro 電源按鈕20秒以上的時間。 當您這麼做時，裝置會重新開機並清除圖形快取。 |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>限制與預期行為

***

Microsoft 團隊會議室不支援 HDCP 輸入，但已觀察到可導致 HDMI 攝取功能（影片、音訊）的問題。 請務必小心，確定連線至 Microsoft 團隊聊天室的交換器已關閉 HDCP 選項。 

***

如果您希望在來源從待機模式喚醒時自動切換到活動影片來源（例如 MTR 主控台），必須符合某些條件。 此功能是選擇性的，但 Microsoft 團隊聊天室軟體支援，提供基礎硬體支援此功能。 在房間顯示中使用的消費者電視需要支援 HDMI 的消費電子產品控制（CEC）功能。  根據所選的 dock 或 console （可能不支援 CEC，請參閱製造商支援檔），您可能需要使用工作區控制器（例如[EXTRON HD CTL 100](https://www.extron.com/article/hdctl100ad) ）來啟用所需的行為。 

***

請務必使用有線 1 Gbps 網路連線，以確保您有所需的頻寬。 

***

如果您的 Microsoft 團隊聊天室裝置無法與網域失去信任，您就無法在裝置上進行驗證，也無法開啟 [設定]。 例如，如果您在網域加入後從網域中移除 Microsoft 團隊聊天室，信任就會遺失。 解決方法是使用本機管理員帳戶登入。 
***
Microsoft 團隊聊天室版本3.0.12.0 不再支援64位版本的 Windows 10 Enterprise 周年紀念日（英文、版本1607）。 
***
Microsoft [團隊會議室] 是一個多視窗應用程式，且需要將房間顯示器正面連接到裝置的 HDMI 埠，才能讓 app 正常運作。 如果您正在測試，但尚未購買顯示器，請確定您已連接 HDMI 顯示器，或使用虛擬 HDMI 插頭。
***
<a name="See"> </a>  
## <a name="see-also"></a>另請參閱

[Microsoft 團隊聊天室說明](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft 團隊聊天室](rooms-manage.md)
