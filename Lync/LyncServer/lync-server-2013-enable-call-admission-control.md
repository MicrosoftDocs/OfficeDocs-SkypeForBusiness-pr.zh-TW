---
title: Lync Server 2013：啟用通話許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e129e109a62006d72b8b1db44c28effa8911e6c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528760"
---
# <a name="enable-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中啟用通話許可控制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

在設定通話許可控制部署的網路設定後，必須啟用 CAC，您的頻寬原則才能生效。

如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - [Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a>若要使用管理命令介面啟用通話許可控制

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 Set-CsNetworkConfiguration Cmdlet 以在您的網路中啟用 CAC。例如，執行：
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    如果您要在網路中停用 CAC，請執行下列命令：
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a>若要使用 Lync Server 控制台啟用通話許可控制

1.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左導覽列中，按一下 **[網路組態]**。

3.  按一下 **[通用]** 導覽按鈕。

4.  按一下清單中的 **[通用]**，然後選取 **[編輯]** 功能表上的 **[顯示詳細資料]**。

5.  在 **[編輯通用設定]** 頁面上，選取 **[啟用通話許可控制台]** 核取方塊。
    
    <div>
    

    > [!NOTE]  
    > 如果您要在整個部署中停用通話許可控制，請清除此核取方塊。

    
    </div>

6.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

