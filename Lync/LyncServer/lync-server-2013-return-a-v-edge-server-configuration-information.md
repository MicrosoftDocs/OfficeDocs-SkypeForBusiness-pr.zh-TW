---
title: Lync Server 2013：傳回 A/V 邊緣伺服器配置資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea7d7ed1ef74c092dac60ecfb2f009219564455
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>在 Lync Server 2013 中傳回 A/V 邊緣伺服器配置資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

A/V Edge 服務為內部使用者（登入組織網路的使用者）提供一種方式，與外部使用者（沒有登入組織網路的使用者）共用音訊和影片。 A/V Edge 服務主要是使用 A/V 邊緣設定設定來管理，設定可以在網站範圍或服務範圍（也就是針對個別的 A/V 邊緣伺服器進行設定）進行設定。

若要傳回在貴組織中使用之 A/V 邊緣設定的相關資訊，您必須使用 Windows PowerShell 及 CsAVEdgeConfiguration Cmdlet。 如需詳細資訊，請參閱[CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) Cmdlet 的說明主題。

從 CsAVEdgeConfiguration Cmdlet 傳回的資訊看起來會像這樣：

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>若要傳回所有 A/V 邊緣設定的資訊

  - 下列命令會傳回貴組織中目前使用的所有 A/V 邊緣設定資訊：
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>若要傳回網站範圍的 A/V 邊緣設定的資訊

  - 若要傳回特定的 A/V 邊緣配置設定集合的相關資訊，請在執行 CsAVEdgeConfiguration Cmdlet 時指定該集合的身分識別。 例如，這個命令只會傳回套用至雷德蒙者網站之設定的資訊：
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>返回服務範圍的 A/V 邊緣設定的資訊

  - 這個命令只會傳回已套用特定 A/V 邊緣伺服器之設定的資訊：
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立或修改 A/V 邊緣伺服器設定的集合](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[刪除 Lync Server 2013 中現有的 A/V 邊緣伺服器設定集合](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013 中的音訊/視頻（A/V）邊緣伺服器](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

