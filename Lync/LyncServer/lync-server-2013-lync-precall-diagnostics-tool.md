---
title: Lync Server 2013： Lync PreCall 診斷工具
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
ms.openlocfilehash: 004d3b30dc2c2886eb7a2d8977f1da062277cc92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Lync Server 2013 中的 lync PreCall 診斷工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-11-04_

Lync PreCall 診斷工具（PCD）是一種用戶端的應用程式，可讓您查看網路目前狀態在未來的企業語音通話中可能會如何影響音訊品質。

在網路的最後一個躍點可能是最弱（例如，在公用 WiFi 網路或家用使用者上使用膝上型電腦）時，PCD 非常有用。 PCD 會建立一個可遍歷這個網路最後一個網段的小型資料包串流。 然後，該工具會分析資料包資料流程，以估計此腿的抖動與遺失對通話品質有何影響，然後提供報告。 您可以在用戶端連續執行 PCD，即使正在進行通話也一樣。 資料包資料流程在頻寬上不會有顯著的影響。

**PCD （版本1.1）最新版本包含下列增強功能：**

  - 支援較長的密碼，現在最多可以使用127個字元

  - 驗證登入問題的其他診斷資訊

  - 更好地支援 Lync 混合式部署

  - 認證選擇器的更新

  - 穩定性改善

我們感謝任何意見反應。 請將所有支援問題或問題傳送給[PCD 的意見](mailto:pcdfb@microsoft.com)反應<pcdfb@microsoft.com>別名。

本主題包含下列各節：

  - Lync PCD 版本

  - Lync PCD 系統需求

  - Lync PCD 功能

  - 執行 Lync PCD

  - 卸載 Lync PCD

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Lync PCD 版本

本主題描述下列工具版本，提供免費下載：

  - Windows 傳統型應用程式[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)（）

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Lync PCD 系統需求

<div>


> [!NOTE]  
> PCD 要求在 Lync Server 部署中安裝並設定整合通訊網頁 API （UCWA）以支援行動用戶端。 UCWA 是隨 Lync Server 一起安裝。



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Windows 桌面應用程式需求

  - 任何版本的 Windows 7 或 Windows 8 作業系統

  - Microsoft .NET Framework 4.5 可在[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Lync PCD 功能

Lync PCD 包括下列功能：

  - 根據需求預設執行（2分鐘突發）

  - [持續開啟] （在貼齊模式中最多24小時）

  - 測試執行的歷史視圖

  - 診斷登入失敗（僅適用于 Windows 8 的 Lync PCD）

![Lync PCD 功能登入進度螢幕擷取畫面](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD 功能登入進度螢幕擷取畫面")

  - 網路度量的圖形化視圖： [MOS]、[資料包遺失] 和 [Interarrival 抖動]，以全螢幕顯示及貼齊模式。

**全螢幕視圖**

![PreCall 診斷工具測試結果圖表](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 診斷工具測試結果圖表")

**貼齊視圖**

![PreCall 診斷工具使用率測試結果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 診斷工具使用率測試結果")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>執行 Lync PCD

<div>

## <a name="running-windows-desktop-app"></a>執行 Windows 桌面應用程式

1.  若要在 Windows 7 系統上啟動 PCD，請從 [**開始**] 功能表選取 [ **PreCall 診斷**]。
    
    若要在 Windows 8 系統上啟動 PCD，請選取 [開始] 畫面上的圖示，或搜尋「PreCall Diagnostics」。
    
    ![PreCall 診斷工具圖示](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 診斷工具圖示")

2.  當工具啟動時，請選取您要提供認證的慣用方法，然後選取 [ **PreCall 診斷工具選項**] 對話方塊中的 [網路] 工作模式，然後選取 **[確定]**：

3.  選取 [**開始測試**] 按鈕，即可開始執行診斷程式。
    
    如果您已選取 [**使用網路認證**] 選項，測試就會立即開始。
    
    如果您已選取 [**讓我輸入我的認證**] 選項，就會開啟 [ **Windows 安全性**] 對話方塊。 輸入認證之後，就會開始測試。

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>卸載 Lync PCD

若要移除 Lync PCD，請依照適用于您作業系統的程式進行：

  - 在 Windows 7 系統上，開啟 [**控制台**]，選取 [**程式和功能**]，然後按兩下 [ **Lync 2013 PreCall Diagnostics**]。

  - 在 Windows 8 系統上，以滑鼠右鍵按一下 [PCD] 磚，然後按一下 [開始] 畫面底部的應用程式行中的 [**卸載**]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

