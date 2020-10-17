---
title: 設定 Lync Server 2013 案例
description: 設定 Lync Server 2013 案例。
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
ms.openlocfilehash: c4a5b7bd271191067779ac358807cc54918b16bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555459"
---
# <a name="configure-lync-server-2013-scenarios"></a>設定 Lync Server 2013 案例

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-12-28_

若要執行 Lync Server 2013 壓力和效能工具 (LyncPerfTool) ，必須先針對將要執行的案例，設定 Lync Server 2013 拓撲。 如果未設定 Lync Server 2013 或設定不正確，則在大多數情況下負載模擬都會失敗。 透過 Lync Server 2013 壓力和效能工具，我們提供了一些範例 Lync Server 管理命令介面腳本和基本資源檔案，可做為設定 Lync Server 2013 的起始點。 本主題說明所提供的 Windows PowerShell 範例。 請注意，這不是本主題的目標，說明一般會如何設定 Lync Server 2013。 如需在 Lync Server 2013 中使用 Windows PowerShell 的詳細資訊，請參閱 Lync Server 管理命令介面檔，網址為 <https://technet.microsoft.com/library/gg398474.aspx> 。

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>關於執行 Lync Server 管理命令介面腳本

我們已提供範例 Lync Server 管理命令介面腳本，可用於準備執行負載模擬。 因為這些腳本是用來進行負載模擬，所以它們很簡單且可供進行，因此可能不適合實際執行。 所有腳本都是範例，必須先加以檢查，而且在某些情況下，修改後才能反映您的拓撲。 在最低限度下，我們預計必須修改回應群組服務 (RGS) 案例，以指定指派給代理人群組的代理程式。 不過，您可以選擇不要模擬此負載。

<div>


> [!WARNING]  
> 請小心檢查和瞭解所提供的範例。 腳本會覆寫拓撲中的任何現有設定。



</div>

<div>


> [!NOTE]  
> 如需使用 Windows PowerShell 和 Lync Server 管理命令介面的詳細資訊，請參閱 Lync Server 2013 Windows PowerShell 博客，網址為 <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A> 。



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>應力和效能工具用戶端版本名字物件

如果您已變更預設值的設定，您可能需要設定用戶端版本檢查原則。 如需詳細資訊，請參閱《設定支援的用戶端版本》 <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx> 。 Lync Server 2013 應力和效能工具預設會使用下列使用者代理程式版本與 Lync Server 2013 通訊：

  - LSPT/15.0.0.0 (Lync Server 2013 壓力和效能工具) 

  - OCPHONE/.0.522

以下是 LyncPerfTool 中 (UCWA) 用戶端的行動性：

  - Ucwa Perf 工具/Web 會議

  - Ucwa Perf 工具/行動裝置

</div>

</div>

<span> </span>

</div>

</div>

</div>

