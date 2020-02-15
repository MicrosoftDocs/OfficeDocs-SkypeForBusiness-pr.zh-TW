---
title: 刪除現有集合的 A / V Edge Server 組態設定
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
ms.openlocfilehash: 901562812e7847a6c205f042922dca6383ad6254
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>刪除現有集合的 A / V Edge Server 組態設定 Lync Server 2013 中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

A/V Edge 服務可讓內部使用者 (即已登入您組織網路的使用者) 將音訊和視訊共用給外部使用者 (即未登入您組織網路的使用者)。此服務主要是採用 A/V Edge 組態設定管理，可以在網站範圍或服務範圍裡完成這些設定 (亦即可以針對個別 A/V Edge 伺服器進行設定)。

當您安裝 Lync Server，全域集合的 A / V Edge 組態設定會加以建立。 您無法刪除此全域集合。 不過，您可以使用 Windows PowerShell 和 Remove-csavedgeconfiguration cmdlet 」 重設 「 全域集合中;這只是表示全域集合中的所有屬性值，會重都設為其預設值。 例如，如果您已設定 MaxTokenLifetime 屬性 16 小時，該屬性將會重設為預設值為 8 小時。

然而，使用 Remove-CsAVEdgeConfiguration Cmdlet 可刪除在網站範圍或服務範圍建立的自訂設定集合。如果刪除網站設定，則該網站中的 A/V Edge Server 會由全域設定進行管理。如果刪除服務範圍設定，該伺服器就會由網站設定 (若存在) 或全域設定 (若無網站設定) 進行管理。

如需詳細資訊，請參閱[Remove-csavedgeconfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) cmdlet 的說明主題。

<div>

## <a name="to-reset-the-global-collection"></a>若要重設全域集合

  - 下列命令會重設 A/V Edge 組態設定的全域集合：
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>若要從網站範圍移除集合

  - 下列命令會移除套用至 Redmond 網站的 A/V Edge 組態設定：
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>若要從服務範圍移除集合

  - 下列命令會移除套用至 A/V Edge Server atl-edge-001.litwareinc.com 的設定：
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>另請參閱


[傳回 A / V Edge Server 在 Lync Server 2013 中的組態資訊](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[建立或修改一群 A / V Edge Server 組態設定 Lync Server 2013 中](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[音訊/視訊 (A / V) Lync Server 2013 中的 Edge Server](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-csavedgeconfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

