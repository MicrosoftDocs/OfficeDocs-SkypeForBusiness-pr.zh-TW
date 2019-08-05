---
title: Microsoft 團隊聊天室的管理概述
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Microsoft 團隊聊天室的管理概覽。
ms.openlocfilehash: 01b2550c1a0ad691acf48c58f6c13a37f2b4b7e6
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2019
ms.locfileid: "36184278"
---
# <a name="management-overview"></a>管理概覽 

您必須開發並執行日常維護與作業, 以確保您的使用者可以使用 Microsoft 團隊聊天室系統, 並提供良好的使用者體驗。 

## <a name="monitoring"></a>監控程式 

[監視 Microsoft 團隊室系統] 是由兩個主要活動組成:

-  裝置、應用程式和週邊裝置監控

-  品質與可靠性監控 (CQD)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Microsoft 團隊聊天室裝置、應用程式和週邊裝置監控

若要確保使用者能夠使用 Microsoft 團隊會議室單元, 單位必須是 [開啟], 並聯機至網路, 且已正確設定 Microsoft [小組聊天室] 應用程式, 且已連接至正常運作的週邊裝置。 


Microsoft [團隊聊天室] 應用程式和已連接週邊裝置狀態的相關資訊, 由 Microsoft 團隊聊天室應用程式寫入 Windows 事件記錄, 並在[瞭解記錄專案](azure-monitor-manage.md#understand-the-log-entries)中記錄。 

|**正在**|**讓**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1  <br/> |可讓 Microsoft 團隊聊天室啟動  <br/> |
|電源管理-\>在 AC 上, 10 分鐘後關閉螢幕  <br/> 電源管理-\>在交流電上, 請勿將系統置於睡眠狀態  <br/> |讓 Microsoft 團隊聊天室關閉附加的顯示, 並自動喚醒  <br/> |
|淨帳戶/maxpwage: 無限制  <br/> 或同等的方式, 在本機帳戶上停用密碼過期。 如果不這麼做, 最終會導致 Skype 帳戶無法針對過期密碼登入。 請注意, 這會影響電腦上的所有本機帳戶, 因此無法設定這種情況, 也會導致盒上的系統管理帳戶最終過期。  <br/> |讓 Skype 帳戶永遠登入  <br/> |
   
使用群組原則來傳送檔案將在 [[設定檔案專案](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)] 中討論。
  
## <a name="remote-management-using-powershell"></a>使用 PowerShell 進行遠端系統管理
<a name="RemotePS"> </a>

建議您使用 Microsoft Operations Manager Suite 來監視 Microsoft 團隊聊天室系統。 如需有關如何設定監視及基本通知的指導方針, 請參閱[使用 Azure 監視器部署 Microsoft 團隊聊天室管理](azure-monitor-deploy.md)。 

使用本指導方針, 您可以建立一個便於使用的儀表板, 以找出您的 Microsoft 團隊會議室在整個部署中的任何問題。 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>確認您使用的是作業管理 Suite 來監視 Microsoft 團隊會議室部署。</li><li>決定您要用來傳送電子郵件通知的目標通訊群組清單。</li></ul>|
|![](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>定義您的品質與可靠性監視方法。</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>品質與可靠性監控 (CQD)

我們建議您在部署中執行持續運作品質與可靠性監視程式, 以監控通話趨勢與會議品質與可靠性, 找出任何需要考慮的事項, 並努力解決問題。 

當您將建築物資訊上傳到 CQD 時, 您可以在每個建築物層面上調查通話品質與可靠性趨勢, 這可讓您輕鬆比較建築物, 並將注意力集中在特定問題上。

我們建議您複習並遵循 [[體驗品質檢查] 指南](https://aka.ms/qerguide)來找出品質與可靠性趨勢, 並建立行動方案來解決問題。 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>更新 Microsoft 團隊會議室 OS 和 Microsoft 團隊聊天室應用程式

我們建議您更新 Microsoft 團隊會議室 OS 和 Microsoft 團隊聊天室應用程式, 以享受產品更新與改進的好處。 如需詳細指導方針, 請參閱[管理 Microsoft 團隊聊天室](room-systems-v2-operations.md#software-updates)。 

## <a name="windows-updates"></a>Windows 更新

Microsoft 團隊聊天室會在 Windows 10 企業版 IoT 或 Windows 10 企業版 (VL) 上執行, 並以標準桌面接收相同的 Windows 更新與 OS 組建。 如需詳細資訊, 請參閱[管理 Windows 更新](updates.md)。


## <a name="troubleshooting"></a>疑難排解

我們建議您按照上述章節所述, 設定運營管理套件的警示, 讓您的操作小組和技術人員收到任何 Microsoft 團隊聊天室問題的警告。 在[使用 powershell 的遠端系統管理](room-systems-v2-operations.md#remote-management-using-powershell)中, 將說明您在 powershell 遠端系統管理中擁有的選項。 當週邊裝置中斷連線時, 您可能需要依賴本機「智慧型手」或 IT 支援來調查並重新連接裝置。 

如需疑難排解及系統管理模式的詳細資訊, 請參閱[管理 Microsoft 團隊聊天室](room-systems-v2-operations.md#admin-mode-and-device-management)。 


## <a name="see-also"></a>另請參閱

[Microsoft 團隊聊天室說明](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[規劃 Microsoft 團隊聊天室](skype-room-systems-v2-0.md)

[部署 Microsoft 團隊聊天室](room-systems-v2.md)

[設定 Microsoft 團隊聊天室主控台](console.md)

[使用 XML 設定檔遠端系統管理 Microsoft 團隊聊天室的主控台設定](xml-config-file.md)
