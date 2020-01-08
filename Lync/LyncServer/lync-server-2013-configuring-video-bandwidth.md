---
title: Lync Server 2013：設定影片頻寬
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ee374be85bc9427135ff89f3eb75acefd1cf5a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>在 Lync Server 2013 中設定影片頻寬

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

Lync Server 2013 包含數個設定，可用於管理雙方通話和多方會議的影片。 當您部署 Lync Server 2013 時，您應該評估預設設定是否適合您的組織，並視需要加以修改。

本節所述的參數同時適用于雙方通話和多方會議。 使用下列其中一個 Cmdlet 來查看或修改這些設定：

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

驗證會議原則中的下列設定：

  - **VideoBitRateKb**   此設定會指定使用者所傳送之影片的最大視頻位元速率，以千位數/秒（kbps）為單位。 預設值為 50000 kbps。 有效值為0至50000。
    
    此設定會分別適用于主要影片和全景影片。
    
    範例：如果您指定 2000 kbps，Lync Server 可以傳送 2000 kbps 的主要影片資料流程，以及全景視頻資料流程的 2000 kbps。
    
    <div>
    

    > [!NOTE]  
    > Lync 2013 端點的 [最大視頻網路頻寬] 是 8000 kbps 的，用於全景影片的主要影片和 2500 kbps。 只有在收到或傳送多個視頻時，才會達到這些最大值。 如需詳細資訊，請參閱<A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013 中的媒體流量需求網路頻寬需求</A>中的「媒體流量網路使用量」一節。 本節列出所有受支援之解析度的最大及典型視頻資料流程頻寬。

    
    </div>

  - **TotalReceiveVideoBitRateKb**   [Lync Server 2013] 中的 [新增] 這項設定，指定用戶端收到的所有影片串流的最大使用率（以千位/秒為單位）。 也就是說，它會為用戶端可以接收的所有視頻資料流程（除了全景視頻資料流程）指定合併總計。 例如，如果您指定 1500 kbps，用戶端最多可以接收 1500 kbps 的視頻，可能由多個視頻資料流程或單一的視頻資料流程所組成。 此設定僅適用于 Lync Server 2013 用戶端。
    
    **TotalReceiveVideoBitRateKb**的預設值為 50000 kbps。 如果圖庫視圖的 [ **EnableMultiviewJoin** ] 設定設為 True，則**TotalReceiveVideoBitRateKb**不得將低於 420 kbps。 如果圖庫視圖的**EnableMultiviewJoin**設定設為 False， **TotalReceiveVideoBitRateKb**不得將低於 100 kbps。 如果**EnableMultiviewJoin**設定為 True，且您設定的值低於 420 kbps，則這些值將會預設為 [閾值] 值。 這個閾值可協助防止意外的錯誤配置，可能會導致不佳的使用者體驗。
    
    <div>
    

    > [!NOTE]  
    > 如需<STRONG>EnableMultiviewJoin</STRONG>設定的詳細資訊，請參閱<A href="lync-server-2013-configuring-gallery-view.md">在 Lync Server 2013 中設定圖庫視圖</A>。

    
    </div>

  - **MaxVideoConferencingResolution**   此參數已不再用於 lync server 2013 會議中的 lync server 2013 用戶端。 Lync Server 2013 會議使用本節前面所述的位元速率控制。 此設定仍用於加入 Lync Server 2013 會議的舊版用戶端。 這個參數決定由駐留在 Lync Server 2013 的使用者所組織之會議中的舊版用戶端所允許的最大解析度。 也就是說，舊用戶端的處理方式與舊版 Lync Server 或 Office 通訊伺服器相同。

除了適用于使用者的會議原則設定之外，評估媒體設定。 使用下列其中一個 Cmdlet 來查看或修改這些設定：

  - **CsMediaConfiguration**

  - **Set-CsMediaConfiguration**

  - **新-CsMediaConfiguration**

確認下列設定：

  - **MaxVideoRateAllowed**   [此每個池] 設定會指定要在用戶端端點傳送視訊訊號的最大速度。 它只適用于舊版的 Lync Server 用戶端。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 用戶端會忽略此設定，而改為使用會議原則中的 [TotalReceiveVideoBitRateKb] 設定。

    
    </div>
    
    預設值為 HD720P。 有效值為 HD720p15M、VGA600K 和 CIF250K。
    
    範例：如果您指定 1500 kbps，則所有舊版用戶端都可以在兩方或多方會議中接收最多 1500 kbps 的影片。

下列程式是使用 Lync Server 管理命令介面來修改本節所述設定的範例。

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>修改影片設定的會議原則

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列上，執行下列 Cmdlet 來編輯會議原則：
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>若要修改舊版用戶端的媒體配置

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列上，執行下列 Cmdlet 來編輯媒體設定：
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

