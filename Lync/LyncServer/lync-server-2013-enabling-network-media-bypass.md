---
title: Lync Server 2013：啟用網路媒體旁路
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
ms.openlocfilehash: 4e0b5e7b060d056a785e80fdf29ded718d120bc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中啟用網路媒體旁路

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在 Microsoft Lync Server 2013 部署中，媒體旁路設定會全域運用。 [旁路媒體] 允許呼叫繞過中繼伺服器。 如需有關何時使用媒體旁路的詳細資料，請參閱規劃區段中的[Lync Server 2013 中的媒體旁路規劃](lync-server-2013-planning-for-media-bypass.md)。

您可以從 Lync Server [控制台] 啟用和設定 [媒體旁路]。

<div>

## <a name="to-enable-and-configure-media-bypass"></a>啟用和設定媒體旁路

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**全域**]。

4.  在 [**全域**] 頁面上，按一下 [**全域**配置]。 永遠只有一個設定，且永遠會將它命名為 Global。

5.  按一下 [**編輯**] 功能表上的 [**查看詳細資料**]。

6.  在 [**編輯全域設定**] 頁面上，按一下 [**啟用旁路媒體**] 核取方塊。

7.  選取下列其中一個選項：
    
      - **[永遠略過**   ] 選取此選項，即可在所有通話中嘗試媒體旁路。 如果啟用 [通話許可控制（CAC）]，此選項將無法使用。 如果未啟用 CAC，請在下列情況下選取此選項：
        
          - 您不需要頻寬控制。
        
          - 不需要精確的設定來判斷何時應發生旁路。
        
          - 閘道與用戶端之間有完整的連線能力。
    
      - **** 如果啟用了 CAC，請使用網站和地區設定，預設會選取此選項，且無法進行變更。    選取此選項時，系統會使用網路設定網站和區域來判斷何時可能會略過媒體。 如果您選取此選項，您可以選擇針對未對應的網站啟用 [旁路]。 如果您的一個或多個大型網站與不具備頻寬限制（例如大型中央網站）的同一個區域相關聯，且您還有一些與有頻寬限制的同一個區域相關聯的分支網站，請按一下 [為未**對應的網站啟用旁路**] 核取方塊。 當您針對未對應的網站啟用 [旁路] 時，系統會簡化配置，因為您只需指定與分支網站相關聯的子網，而不需要指定所有與所有網站相關聯的子網。 如果啟用 CAC，我們建議您不要選取 [**啟用旁路未對應的網站**] 核取方塊。

8.  按一下 [**認可**]，儲存您的變更。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中停用網路媒體旁路](lync-server-2013-disabling-network-media-bypass.md)  


[Lync Server 2013 中的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md)  


[在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

