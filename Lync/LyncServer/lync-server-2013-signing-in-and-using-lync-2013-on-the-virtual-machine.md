---
title: Lync Server 2013： 登入和虛擬機器上使用 Lync 2013
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
ms.openlocfilehash: 56d34483e4fc01579e2ca6a94ac8059a8c816344
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>登入和虛擬機器上使用 Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-03_

啟用 VDI 外掛程式後，當使用者登入 Lync 2013 時，也會進行下列步驟。

1.  使用者輸入虛擬機器上執行 Lync 2013 用戶端中的他/她認證。

2.  Lync 偵測到的可用性 VDI 外掛程式後，Lync 會提示使用者重新輸入他/她的認證。 建議使用者在此對話方塊中選取 **[儲存我的密碼]** 核取方塊，這樣在後續的登入中就不需要輸入認證。

3.  Lync 開始與 VDI 外掛程式配對。 配對完畢之前，用戶端會在 Lync 狀態列中顯示兩個圖示。 左下方的圖示表示沒有音訊裝置可用，右下方閃爍的圖示表示 VDI 配對在進行中，如下圖所示：
    
    ![顯示成功配對的 Lync VDI 圖示](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "顯示成功配對的 Lync VDI 圖示")  

4.  VDI 配對成功後，圖示會變更為表示音訊裝置將用於通話，以及 VDI 配對成功：
    
    ![Lync VDI 配對圖示顯示成功](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI 配對圖示顯示成功")  

5.  Lync VDI 外掛程式配對之後，使用者可以在 Lync 相容的裝置連線至本機電腦上看到他/她的目前狀態。 現在使用者就可以正常撥打及接聽通話。

</div>

<span> </span>

</div>

</div>

</div>

