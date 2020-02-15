---
title: 'Lync Server 2013: Lync PreCall 診斷工具'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a63743c634c9e87c743928d7641609ce12c464cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Lync Server 2013 中的 Lync PreCall 診斷工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-11-04_

Lync PreCall 診斷工具 (PCD) 是網路的用戶端為基礎的應用程式，可讓您查看您的目前狀態可能會如何影響中即將來臨的企業語音通話的音訊品質。

PCD 是最適合用在網路的最後一個躍點可能是最弱 （例如，具有公用 WiFi 網路或隸屬使用者上的膝上型電腦） 的情況。 PCD 建立周遊網路此最終 leg 小型的封包資料流。 此工具然後分析來評估抖動和沿著此 leg 遺失可能會影響通話品質的封包資料流，然後將報表。 您可以 PCD 持續在用戶端，同時也可以執行所在的呼叫。 封包資料流沒有頻寬重大影響。

**最新版的 PCD，版本 1.1 中，包含下列增強功能：**

  - 支援較長的密碼，現在可達 127 個字元

  - 驗證登入問題的其他診斷

  - 進一步支援 Lync 混合式部署

  - 更新認證選擇器

  - 穩定性增強功能

我們歡迎任何意見反應。 請將所有支援問題都傳送給在[PCD 意見反應](mailto:pcdfb@microsoft.com)別名<pcdfb@microsoft.com>。

本主題包含下列各節：

  - Lync PCD 版本

  - Lync PCD 系統需求

  - Lync PCD 功能

  - 執行 Lync PCD

  - 解除安裝 Lync PCD

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Lync PCD 版本

本主題說明工具，可供免費下載的下列的版本：

  - Windows 桌面應用程式 ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Lync PCD 系統需求

<div>


> [!NOTE]  
> PCD 需要 Unified Communications Web API (UCWA) 是安裝和設定 Lync Server 部署中支援行動用戶端。 使用 Lync Server 安裝 ucwa 的參考。



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Windows 桌面應用程式需求

  - 任何版本的 Windows 7 或 Windows 8 作業系統

  - Microsoft.NET Framework 4.5 可在[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Lync PCD 功能

Lync PCD 包含下列功能：

  - 執行預設的隨選 （2 分鐘激增）

  - Always On 中執行 （最多 24 小時貼齊] 檢視中） 模式

  - 您在測試回合的歷史檢視

  - 診斷登入失敗 (僅限 Windows 8 的 Lync PCD)

![Lync PCD 功能登入進度螢幕擷取畫面](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD 功能登入進度螢幕擷取畫面")

  - 圖形網路計量 – 網路 MOS、 封包遺失和 Interarrival 抖動在全螢幕] 和 [貼齊的檢視的檢視。

**全螢幕檢視**

![PreCall 診斷工具測試結果圖形](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 診斷工具測試結果圖形")

**貼齊的檢視**

![PreCall 診斷工具使用率測試結果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 診斷工具使用率測試結果")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>執行 Lync PCD

<div>

## <a name="running-windows-desktop-app"></a>執行 Windows 桌面應用程式

1.  若要 PCD 系統上啟動 Windows 7，請從 [**開始**] 功能表中選取**PreCall 診斷**。
    
    若要在 Windows 8 的系統上啟動 PCD，選取 [開始] 畫面中或搜尋 「 PreCall 診斷。 」 上的圖示
    
    ![PreCall 診斷工具圖示](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 診斷工具圖示")

2.  工具開始時，選取您偏好的方法，提供認證和選取網路作業系統模式**PreCall 診斷工具選項**] 對話方塊中，然後選取 **[確定]**:

3.  選取 [**開始測試**] 按鈕，開始執行診斷。
    
    如果您選取 [**使用的網路認證**] 選項，會立即開始測試。
    
    如果您選取 [**讓我輸入我的認證**] 選項，會開啟 [ **Windows 安全性**] 對話方塊。 輸入您的認證之後，測試便會啟動。

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>解除安裝 Lync PCD

若要移除 Lync PCD，請依照下列程序適用於您作業系統：

  - 在 Windows 7 系統上，開啟 [**控制台**]，選取 [**程式和功能**]，按兩下 [ **Lync 2013 PreCall 診斷**。

  - 在 Windows 8 系統上，PCD 磚上按一下滑鼠右鍵，並在 [開始] 畫面底部的 [應用程式] 列中按一下 [**解除安裝**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

