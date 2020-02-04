---
title: 設定 Lync Server 2013 案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 789c3ee8c18b5fb0e92ef9a520152644bebbdde1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a>設定 Lync Server 2013 案例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-12-28_

若要執行 Lync Server 2013 應力和效能工具（LyncPerfTool），必須先針對要執行的案例設定 Lync Server 2013 拓撲。 如果未設定 Lync Server 2013 或未正確設定，則在大多數情況下，負載模擬將會失敗。 使用 Lync Server 2013 應力和效能工具，我們提供了範例 Lync Server 管理命令介面腳本和基本資源檔案，可做為開始進行 Lync Server 2013 的起點。 本主題描述提供的 Windows PowerShell 範例。 請注意，這不是本主題的目標，說明如何在一般情況下設定 Lync Server 2013。 如需在 Lync Server 2013 中使用 Windows PowerShell 的詳細資料，請參閱 Lync Server 管理命令<https://technet.microsoft.com/en-us/library/gg398474.aspx>介面檔，網址為。

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>關於執行 Lync Server 管理命令介面腳本

我們已提供可用於準備執行負載模擬的 Lync Server 管理命令介面腳本範例。 因為腳本是用來進行負載模擬，所以它們很簡單且便於使用，因此可能不適合生產。 所有腳本都是範例，而且在某些情況下，您必須經過修改，才能反映您的拓撲。 至少，我們預期需要修改回應群組服務（RGS）案例，以指定指派給代理群組的代理程式。 不過，您可以選擇不要模擬這項載入。

<div>


> [!WARNING]  
> 在審查及瞭解所提供的範例時請小心。 腳本會覆寫拓撲中任何現有的設定。



</div>

<div>


> [!NOTE]  
> 如需使用 Windows PowerShell 和 Lync Server 管理命令介面的詳細資訊，請參閱 Lync Server 2013 的 Windows <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>PowerShell 博客。



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>壓力與效能工具用戶端版本名字物件

如果您已變更預設值的設定，您可能需要設定用戶端版本檢查原則。 如需詳細資訊，請參閱「配置支援的<https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>用戶端版本」。 Lync Server 2013 的應力和效能工具預設會在與 Lync Server 2013 通訊時使用下列使用者代理版本：

  - LSPT/15.0.0.0 （Lync Server 2013 應力和效能工具）

  - OCPHONE/.0.522

這些適用于 LyncPerfTool 中的行動（UCWA）用戶端：

  - Ucwa Perf 工具/Web 會議

  - Ucwa Perf 工具/行動裝置

</div>

</div>

<span> </span>

</div>

</div>

</div>

