---
title: Lync Server 2013：退回 A/V Edge Server 設定資訊
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
ms.openlocfilehash: b73a6460b6045d5f1f2e35afcf91af0ebdd9e2b9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511380"
---
# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>傳回 Lync Server 2013 中 A/V Edge Server 設定資訊

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

A/V Edge 服務可讓內部使用者 (即已登入您組織網路的使用者) 將音訊和視訊共用給外部使用者 (即未登入您組織網路的使用者)。此服務主要是採用 A/V Edge 組態設定管理，可以在網站範圍或服務範圍裡完成這些設定 (亦即可以針對個別 A/V Edge 伺服器進行設定)。

若要傳回組織中使用之 A/V Edge 設定設定的相關資訊，您必須使用 Windows PowerShell 和 Get-CsAVEdgeConfiguration Cmdlet。 如需詳細資訊，請參閱 [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) Cmdlet 的 [說明] 主題。

從 Get-CsAVEdgeConfiguration Cmdlet 傳回的資訊看起來如下所示：

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>若要傳回所有 A/V Edge 設定設定的資訊

  - 下列命令會傳回組織目前所使用之所有 A/V Edge 設定設定的相關資訊：
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>若要傳回網站範圍的 A/V Edge 設定設定的資訊

  - 若要傳回特定 A/V Edge 設定設定集合的資訊，請在執行 Get-CsAVEdgeConfiguration Cmdlet 時，指定該集合的身分識別。 例如，下列命令只會傳回套用至 Redmond 網站之設定的資訊：
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>傳回服務範圍 A/V Edge 設定設定的資訊

  - 而且，此命令只會傳回套用特定 A/V Edge server 之設定的資訊：
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立或修改 A/V Edge Server 設定的集合](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[在 Lync Server 2013 中刪除現有的 A/V Edge Server 設定集合集合](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[在 Lync Server 2013 中 Audio/Video (A/V) Edge Server](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

