---
title: Lync Server 2013：在虛擬機器上登入和使用 Lync 2013
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
ms.openlocfilehash: 40c5c18c4e991c3b53e37e090e7f2d960a32f71c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>在虛擬機器上登入和使用 Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

啟用 VDI 外掛程式之後，當使用者登入 Lync 2013 時，會發生下列步驟。

1.  使用者在虛擬機器上執行的 Lync 2013 用戶端輸入其認證。

2.  Lync 偵測到 VDI 外掛程式的可用性之後，Lync 會提示使用者重新輸入其認證。 在這個對話方塊中，我們建議使用者選取 [**儲存我的密碼**] 核取方塊，以便在進行後續登入時，系統不會要求您輸入認證。

3.  Lync 會從 VDI 外掛程式開始配對。 配對完成之前，用戶端會在 Lync 狀態列中顯示兩個圖示。 左下角的圖示表示沒有可用的音訊裝置，右下方的閃爍圖示則表示正在進行 VDI 配對，如下所示：
    
    ![顯示成功配對的 Lync VDI 圖示](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "顯示成功配對的 Lync VDI 圖示")  

4.  在已成功進行 VDI 配對之後，圖示會變更，以指出將用於通話的音訊裝置和 VDI 配對成功：
    
    ![顯示成功的 Lync VDI 配對圖示](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "顯示成功的 Lync VDI 配對圖示")  

5.  在 Lync 對使用 VDI 外掛程式之後，使用者可以在連線至本機電腦的 Lync 相容裝置上看到他或她的目前狀態。 使用者現在可以照常進行呼叫並接聽通話。

</div>

<span> </span>

</div>

</div>

</div>

