---
title: Lync Server 2013：啟用網路媒體旁路
description: Lync Server 2013：啟用網路媒體旁路。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1218376903aa42e1ea55205e3a9e8d16aade9a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546549"
---
# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中啟用網路媒體旁路

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

媒體旁路設定會在 Microsoft Lync Server 2013 部署中全域套用。 媒體旁路允許來電略過轉送伺服器。 如需有關何時使用媒體旁路的詳細資訊，請參閱規劃區段中的在 [Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md) 。

您可以從 Lync Server [控制台] 啟用和設定媒體旁路。

<div>

## <a name="to-enable-and-configure-media-bypass"></a>啟用及設定媒體旁路

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[網路設定]**，然後按一下 **[全域]**。

4.  在 **[全域]** 頁面上，按一下 **[全域]** 設定。 永遠只有一個設定，而且永遠稱為 Global。

5.  在 [ **編輯** ] 功能表上，按一下 [ **查看詳細資料**]。

6.  在 [ **編輯通用設定** ] 頁面上，按一下 [ **啟用媒體旁路** ] 核取方塊。

7.  請選取下列任一選項：
    
      - **永遠略過**    選取此選項，可在所有呼叫時嘗試媒體旁路。 如果已啟用 (CAC) 的通話許可控制，此選項將無法使用。 如果未啟用 CAC，請在下列情況下選取此選項：
        
          - 不需要頻寬控制。
        
          - 不需要微調設定，就能決定何時應該應該發生旁路。
        
          - 閘道和用戶端之間有完整的連線能力。
    
      - **使用網站與地區**     設定如果啟用 CAC，預設會選取此選項，而且無法變更。 選取此選項時，會使用網路設定網站和區域來決定何時可以進行媒體旁路。 如果您選取此選項，您可以針對未對應的網站，選擇啟用旁路。 只有當您有一個或多個大型網站與沒有頻寬限制的相同區域相關聯時，才會按一下 [為 **未對應的網站啟用旁路** ] 核取方塊 (例如，大型中央網站) ，而且您也有一些分支網站與具有頻寬限制的相同地區相關聯。 當您為未對應的網站啟用旁路時，將會簡化設定，因為您只會指定與分支網站相關聯的子網，而不需要指定所有網站相關聯的所有子網。 如果啟用 CAC，建議您不要選取 [為 **未對應的網站啟用旁路** ] 核取方塊。

8.  按一下 [ **認可** ] 以儲存變更。

</div>

<div>

## <a name="see-also"></a>另請參閱


[停用 Lync Server 2013 中的網路媒體旁路](lync-server-2013-disabling-network-media-bypass.md)  


[Lync Server 2013 中的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md)  


[在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

