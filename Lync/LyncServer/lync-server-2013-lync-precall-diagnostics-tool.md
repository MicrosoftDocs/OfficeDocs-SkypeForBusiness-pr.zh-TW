---
title: Lync Server 2013： Lync PreCall 診斷工具
description: Lync Server 2013： Lync PreCall 診斷工具。
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
ms.openlocfilehash: 17c2c51551fe0991eb354a628b1d4660baa1532b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571989"
---
# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Lync Server 2013 中的 lync PreCall 診斷工具

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-11-04_

Lync PreCall Diagnostics Tool (.PCD) 是一種用戶端應用程式，可讓您查看網路目前的狀態如何影響即將到來的 Enterprise Voice 通話中的音訊品質。

在網路的最後一個躍點可能是最弱的 (，例如，在公用 WiFi 網路或家用使用者) 上的膝上型電腦上，.PCD 非常有用。 .PCD 建立一個小型的封包資料流程，以流經這段網路的最後一個腿。 然後，該工具會分析封包資料流程，以估計沿著此腳的抖動和遺失可能會影響通話品質的方式，然後提供報告。 您可以在用戶端持續地執行 .PCD，甚至在撥打通話時也一樣。 封包資料流程對頻寬的影響不大。

**.PCD 版本1.1 的最新版本包含下列增強功能：**

  - 支援較長的密碼，現在可達127個字元

  - 驗證登入問題的其他診斷

  - 更好支援 Lync 混合式部署

  - 更新憑證選擇器

  - 穩定性改進

感謝您的意見反應。 請將所有支援問題或問題傳送至中的 [.Pcd 意見](mailto:pcdfb@microsoft.com) 反應別名 <pcdfb@microsoft.com> 。

本主題包含下列各節：

  - Lync .PCD 版本

  - Lync .PCD 系統需求

  - Lync .PCD 功能

  - 執行 Lync .PCD

  - 卸載 Lync .PCD

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Lync .PCD 版本

本主題說明下列工具版本，可供免費下載：

  - Windows Desktop App ([https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914)) 

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Lync .PCD 系統需求

<div>


> [!NOTE]  
> .PCD 需要安裝並設定整合通訊網頁 API () UCWA，以支援 Lync Server 部署中的行動用戶端。 UCWA 與 Lync Server 一起安裝。



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Windows 桌面應用程式需求

  - 任何版本的 Windows 7 或 Windows 8 作業系統

  - Microsoft .NET Framework 4.5 可于 [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Lync .PCD 功能

Lync .PCD 包含下列功能：

  - 在預設按需要執行 (2 分鐘的猝量) 

  - 在對齊模式) 模式中，以 Always On (于24小時內執行

  - 測試執行的歷史視圖

  - 在僅限 Windows 8 的 Lync .PCD 中診斷登入失敗 () 

![Lync .PCD 功能登入進度螢幕擷取畫面](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync .PCD 功能登入進度螢幕擷取畫面")

  - 網路計量的圖形化視圖，以全屏和貼齊模式顯示網路 MOS、封包遺失和 Interarrival 抖動。

**全螢幕視圖**

![PreCall 診斷工具測試結果圖形](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 診斷工具測試結果圖形")

**貼齊視圖**

![PreCall 診斷工具利用率測試結果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 診斷工具利用率測試結果")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>執行 Lync .PCD

<div>

## <a name="running-windows-desktop-app"></a>執行 Windows 桌面應用程式

1.  若要在 Windows 7 系統上啟動 .PCD，請從 [**開始**] 功能表中選取 [ **PreCall 診斷**]。
    
    若要在 Windows 8 系統上啟動 .PCD，請在 [開始] 畫面上選取圖示，或搜尋「PreCall 診斷」。
    
    ![PreCall 診斷工具圖示](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 診斷工具圖示")

2.  當工具開始時，請選取您要提供認證的慣用方法，並在 [ **PreCall 診斷工具選項** ] 對話方塊中選取 [網路] 工作模式，然後選取 [ **確定]**：

3.  選取 [ **開始測試** ] 按鈕開始執行診斷。
    
    如果您選取 [ **使用網路認證** ] 選項，測試會立即開始。
    
    如果您選取 [ **讓我輸入我的認證** ] 選項，則會開啟 [ **Windows 安全性** ] 對話方塊。 在您輸入認證之後，就會開始測試。

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>卸載 Lync .PCD

若要移除 Lync .PCD，請遵循作業系統的程式：

  - 在 Windows 7 系統上，開啟 [ **控制台**]，選取 [ **程式和功能**]，然後按兩下 [ **Lync 2013 PreCall 診斷**]。

  - 在 Windows 8 系統上，以滑鼠右鍵按一下 [.PCD] 磚，然後按一下 [開始] 畫面底部的 [應用程式] 欄中的 [ **卸載** ]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

