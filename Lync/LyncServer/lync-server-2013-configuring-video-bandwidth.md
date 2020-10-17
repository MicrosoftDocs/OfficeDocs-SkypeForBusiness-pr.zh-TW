---
title: Lync Server 2013：設定影片頻寬
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3e1c4b0dab165c43e873c49039896f0af80f7f3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516980"
---
# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>在 Lync Server 2013 中設定影片頻寬

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

Lync Server 2013 包含數個設定，用來管理兩方通話和多方會議的影片。 當您部署 Lync Server 2013 時，應評估預設設定是否適合您的組織，並視需要加以修改。

本節所述的參數適用於雙方通話和多方會議。請使用下列其中一個 Cmdlet 來檢視或修改這些設定：

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

在您的會議原則中確認下列設定：

  - **VideoBitRateKb**    此設定指定由使用者所傳送之影片的最高每秒 (kbps) 的影片位元速率。 預設值為 50000 kbps。 有效的值為0到50000。
    
    這個設定分別套用至主要視訊和全景視訊。
    
    範例：如果您指定 2000 kbps，Lync Server 可以傳送 2000 kbps 的主要影片資料流程，以及全景影片資料流程的 2000 kbps。
    
    <div>
    

    > [!NOTE]  
    > Lync 2013 端點的最大視頻網路頻寬是 8000 kbps 的主要影片及全景影片的 2500 kbps。 只有當接收或傳送多個視訊時，才會達到上述最大值。 如需詳細資訊，請參閱 <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013 中媒體流量的網路頻寬需求</A>中的「媒體流量網路使用量」一節。 這一節列出所有支援的解析度的最大及一般視訊資料流頻寬。

    
    </div>

  - **TotalReceiveVideoBitRateKb**    此設定是 Lync Server 2013 中的新功能，指定用戶端所收到之所有影片的最大位元速率 (，單位為每秒千位) 。 也就是說，它會指定用戶端可以接收的所有影片資料流程（除了全景影片資料流程以外）的合併總計。 例如，如果您指定 1500 kbps，則用戶端最多可以接收 1500 kbps 的影片，其可能是由多個影片資料流程或單一的視頻資料流程所組成。 此設定僅適用于 Lync Server 2013 用戶端。
    
    **TotalReceiveVideoBitRateKb** 的預設值為 50000 kbps。如果「圖庫檢視」的 **EnableMultiviewJoin** 設定為 True，**TotalReceiveVideoBitRateKb** 的設定就不得低於 420 kbps。如果「圖庫檢視」的 **EnableMultiviewJoin** 設定為 False，**TotalReceiveVideoBitRateKb** 的設定就不得低於 100 kbps。如果 **EnableMultiviewJoin** 設定為 True，但您將值設定為低於 420 kbps，該值將會預設為臨界值。這個臨界值有助於防止意外的錯誤設定，避免造成不佳的使用者體驗。
    
    <div>
    

    > [!NOTE]  
    > 如需 <STRONG>EnableMultiviewJoin</STRONG> 設定的詳細資訊，請參閱 <A href="lync-server-2013-configuring-gallery-view.md">在 Lync Server 2013 中設定圖庫 View</A>。

    
    </div>

  - **MaxVideoConferencingResolution**    此參數不再用於 Lync Server 2013 會議中的 Lync Server 2013 用戶端。 Lync Server 2013 會議使用本節先前所述的位元速率控制。 此設定仍用於加入 Lync Server 2013 會議的舊版用戶端。 此參數會決定舊版用戶端對於以 Lync Server 2013 為宿主之使用者所組織的會議中所允許的最大解決方法。 也就是說，舊版用戶端的處理方式與舊版本的 Lync Server 或 Office 通訊伺服器相同。

除了套用至使用者的會議原則設定，也要評估媒體組態設定。請使用下列其中一個 Cmdlet 來檢視或修改這些設定：

  - **Get-CsMediaConfiguration**

  - **CsMediaConfiguration**

  - **新 CsMediaConfiguration**

確認下列設定：

  - **MaxVideoRateAllowed**    這個每個集區設定會指定在用戶端端點傳輸的視訊訊號的最大速率。 它只適用于舊版的 Lync Server 用戶端。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 用戶端忽略此設定，而改用會議原則中的 [TotalReceiveVideoBitRateKb] 設定。

    
    </div>
    
    預設值為 HD720P。有效值為 HD720p15M、VGA600K 和 CIF250K。
    
    範例：如果您指定 1500 kbps，則集區中所有舊版用戶端在雙方或多方會議中都可以接收高達 1500 kbps 的視訊。

下列程式是使用 Lync Server 管理命令介面來修改本節所述設定的範例。

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>修改視訊設定的會議原則

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列上執行下列 Cmdlet 以編輯會議原則：
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>修改舊版用戶端的媒體組態

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列上執行下列 Cmdlet 以編輯媒體組態：
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

