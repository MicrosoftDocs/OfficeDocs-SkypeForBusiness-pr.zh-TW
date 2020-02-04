---
title: 刪除現有的 A/V 邊緣伺服器設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cc085cd6ac39c4712647795c5baf06eaa68f77a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>刪除 Lync Server 2013 中現有的 A/V 邊緣伺服器設定集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

A/V Edge 服務為內部使用者（登入組織網路的使用者）提供一種方式，與外部使用者（沒有登入組織網路的使用者）共用音訊和影片。 A/V Edge 服務主要是使用 A/V 邊緣設定設定來管理，設定可以在網站範圍或服務範圍（也就是針對個別的 A/V 邊緣伺服器進行設定）進行設定。

當您安裝 Lync Server 時，系統會為您建立 A/V 邊緣配置設定的全域集合。 無法刪除這個全域集合。 不過，您可以使用 Windows PowerShell 與 Remove CsAVEdgeConfiguration Cmdlet 來「重設」全域集合;這只代表全域集合中的所有屬性值都會重設為預設值。 例如，如果您已將 MaxTokenLifetime 屬性設定為16小時，該屬性將會重設為預設值8小時。

不過，您可以使用 CsAVEdgeConfiguration Cmdlet 來刪除您在網站範圍或服務範圍內建立的自訂設定集合。 如果您刪除 [網站設定]，該網站中的 A/V 邊緣伺服器將由全域設定來管理。 如果您刪除服務範圍設定，該伺服器將由其網站設定（如果有的話）來管理，或在沒有網站設定的情況下由全域設定來管理。

如需詳細資訊，請參閱[Remove CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) Cmdlet 的說明主題。

<div>

## <a name="to-reset-the-global-collection"></a>若要重設全域集合

  - 下列命令會重設 A/V 邊緣設定的全域集合：
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>若要從網站範圍中移除收藏

  - 這個命令會移除套用至雷蒙德網站的 A/V 邊緣設定：
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>從服務範圍移除集合

  - 這個命令會移除套用至 A/V 邊緣伺服器 atl-edge-001.litwareinc.com 的設定：
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中傳回 A/V 邊緣伺服器配置資訊](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[在 Lync Server 2013 中建立或修改 A/V 邊緣伺服器設定的集合](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013 中的音訊/視頻（A/V）邊緣伺服器](lync-server-2013-audio-video-a-v-edge-servers.md)  
[移除-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

