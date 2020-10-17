---
title: Lync Server 2013：在虛擬機器上登入和使用 Lync 2013
description: Lync Server 2013：在虛擬機器上登入和使用 Lync 2013。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad9a92d450fb9d60aed70617089d95280528892f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555679"
---
# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>在虛擬機器上登入和使用 Lync 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

在啟用 VDI 外掛程式之後，當使用者登入 Lync 2013 時，會執行下列步驟。

1.  使用者在虛擬機器上的 Lync 2013 用戶端中輸入其認證。

2.  Lync 偵測到 VDI 外掛程式的可用性後，Lync 會提示使用者重新輸入認證。 建議使用者在此對話方塊中選取 **[儲存我的密碼]** 核取方塊，這樣在後續的登入中就不需要輸入認證。

3.  Lync 開始配對與 VDI 外掛程式。 配對完成之前，用戶端會在 Lync 狀態列顯示兩個圖示。 左下方的圖示表示沒有音訊裝置可用，右下方閃爍的圖示表示 VDI 配對在進行中，如下圖所示：
    
    ![顯示成功配對的 Lync VDI 圖示](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "顯示成功配對的 Lync VDI 圖示")  

4.  VDI 配對成功後，圖示會變更為表示音訊裝置將用於通話，以及 VDI 配對成功：
    
    ![顯示成功的 Lync VDI 配對圖示](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "顯示成功的 Lync VDI 配對圖示")  

5.  使用 VDI 外掛程式的 Lync 配對後，使用者可以在連接至本機電腦的 Lync 相容裝置上看到其狀態。 現在使用者就可以正常撥打及接聽通話。

</div>

<span> </span>

</div>

</div>

</div>

