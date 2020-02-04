---
title: 建立或修改 A/V 邊緣伺服器設定的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c4b45b34b5c52d0eb138fbc16c37e5aaee7262b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改 A/V 邊緣伺服器設定的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

A/V Edge 服務為內部使用者（登入組織網路的使用者）提供一種方式，與外部使用者（沒有登入組織網路的使用者）共用音訊和影片。 A/V Edge 服務主要是使用 A/V 邊緣設定設定來管理，設定可以在網站範圍或服務範圍（也就是針對個別的 A/V 邊緣伺服器進行設定）進行設定。

當您安裝 Lync Server 時，系統會為您建立 A/V 邊緣配置設定的全域集合。 除此之外，您也可以使用 Windows PowerShell 和新的 CsAVEdgeConfiguration Cmdlet，在網站範圍或服務範圍（也就是個別 A/V 邊緣伺服器）建立新的設定。 如果您建立新的設定，請記住：

  - 在服務作用中設定的設定（也就是在個別伺服器上）會優先處理所有專案。

  - 在網站範圍設定的設定，會優先于在全域範圍內設定的設定。 不過，服務範圍設定也會取代網站範圍設定。

  - 只有在個別伺服器上沒有設定任何服務設定，而且該伺服器所在之網站沒有網站設定的情況下，全域作用中的設定才會使用。

然後，您就可以使用 CsAVEdgeConfiguration Cmdlet 來修改任何設定。 如需詳細資訊，請參閱[新-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))和[CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) Cmdlet 的說明主題。

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>在網站範圍中建立新的 A/V 邊緣配置設定

  - 下列命令會為雷德蒙的網站建立新的 A/V 邊緣配置設定集合：
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>在網站範圍中建立自訂的 A/V 邊緣配置設定

  - 由於沒有隨附其他參數，這些新設定將會使用 A/V 邊緣服務的預設值。 或者，您也可以新增其他參數和參數值來建立自訂集合。 例如，這個命令會將 MaxTokenLifetime 屬性設為4小時（04小時：00分：00秒）：
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>在服務範圍建立自訂的 A/V 邊緣配置設定

  - 這個命令會建立套用至 A/V 邊緣伺服器 atl-edge-001.litwareinc.com 的類似集合：
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>修改現有的 A/V 邊緣設定

  - 在這個範例中，CsAVEdgeConfiguration Cmdlet 是用來將雷德蒙者網站的最大權杖存留期變更為12個小時：
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中傳回 A/V 邊緣伺服器配置資訊](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[刪除 Lync Server 2013 中現有的 A/V 邊緣伺服器設定集合](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013 中的音訊/視頻（A/V）邊緣伺服器](lync-server-2013-audio-video-a-v-edge-servers.md)  
[新-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))  
[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

