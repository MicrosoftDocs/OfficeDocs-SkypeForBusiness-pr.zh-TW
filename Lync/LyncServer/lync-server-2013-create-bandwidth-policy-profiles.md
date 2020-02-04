---
title: Lync Server 2013：建立頻寬原則設定檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d3eef3ea6dfb349f0f712c1127adb8310d90c27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a>在 Lync Server 2013 中建立頻寬原則設定檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

*頻寬原則*定義即時音訊與視頻形式的頻寬使用量限制。 頻寬原則會套用到*頻寬策略設定檔*，這可以套用到多個網路網站以進行呼叫許可控制。

如需在您的 CAC 部署中應該設定哪些頻寬限制的指導方針，請參閱在規劃檔中，在[Lync Server 2013 中定義您的通話許可控制需求](lync-server-2013-defining-your-requirements-for-call-admission-control.md)。

如需使用頻寬原則與原則設定檔的詳細資訊，請參閱 Lync Server 管理命令介面檔，瞭解下列 Cmdlet：

  - [新-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [移除-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

下列程式中建立的範例原則設定了整體音訊流量、個別音訊會話、整體影片流量，以及個別的視頻會話限制。 例如，5Mb\_連結頻寬原則設定檔會設定下列限制：

  - 音訊限制： 2000 kbps

  - 音訊會話限制： 200 kbps

  - 影片限制： 1400 kbps

  - 影片會話限制： 700 kbps

<div class=" ">


> [!NOTE]  
> 最小音訊會話限制值為 40 kbps。 最小的視頻會話限制值為 100 kbps。



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a>使用管理命令介面建立頻寬原則設定檔

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  針對您想要建立的每一個頻寬原則設定檔，執行新的 CsNetworkBandwidthPolicyProfile Cmdlet。 例如，執行：
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 建立頻寬原則設定檔

1.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左側導覽列中，按一下 [**網路**設定]。

3.  按一下 [**原則設定檔**] 導覽按鈕。

4.  按一下 [**新增**]。

5.  在 [**新增原則設定檔**] 頁面上，按一下 [**名稱**]，然後輸入頻寬原則設定檔的名稱。

6.  按一下 [**音訊限制**]，然後輸入允許所有音訊會話合併的最大 kbps 數。

7.  按一下 [**音訊會話限制**]，然後輸入每個個別音訊會話允許的最大 kbps 數。

8.  按一下 [**影片限制**]，然後輸入允許所有視頻會話合併的最大 kbps 數。

9.  按一下 [**視頻會話限制**]，然後輸入每個個別影片會話允許的最大 kbps 數。

10. 或者，按一下 [**描述**]，然後輸入其他資訊來描述此頻寬原則設定檔。

11. 按一下 [認可]****。

12. 若要完成建立拓撲的頻寬原則設定檔，請重複步驟4到11，以及其他頻寬策略設定檔的設定。

</div>

</div>

<span> </span>

</div>

</div>

</div>

