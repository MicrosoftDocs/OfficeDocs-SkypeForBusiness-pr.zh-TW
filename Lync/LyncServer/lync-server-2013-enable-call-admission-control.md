---
title: Lync Server 2013：啟用呼叫許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 864de6f8ac456ad8a312b5c47af1f19124e7be3f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中啟用呼叫許可控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

在您設定 [通話許可控制] 部署的網路設定之後，您必須啟用 CAC，才能使您的頻寬原則生效。

如需詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：

  - [CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [移除-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a>使用管理命令介面啟用呼叫許可控制

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 CsNetworkConfiguration Cmdlet 以在您的網路中啟用 CAC。 例如，執行：
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    如果您想要在網路中停用 CAC，請執行下列動作：
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 啟用呼叫許可控制

1.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左側導覽列中，按一下 [**網路**設定]。

3.  按一下 [**全域**導覽] 按鈕。

4.  按一下清單中的 [**全域**]，然後選取 [**編輯**] 功能表上的 [**顯示詳細資料**]。

5.  在 [**編輯全域設定**] 頁面上，選取 [**啟用通話許可控制**] 核取方塊。
    
    <div>
    

    > [!NOTE]  
    > 如果您想要在整個部署中停用 [呼叫許可控制]，請清除此核取方塊。

    
    </div>

6.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

