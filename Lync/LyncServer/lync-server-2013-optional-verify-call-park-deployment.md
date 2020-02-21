---
title: 'Lync Server 2013: （選用） 驗證通話保留部署'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1526c05245ea35f794664d8d64f90b60022b2be2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>（選用）確認 Lync Server 2013 中的通話駐留部署

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-11_

安裝並設定通話駐留之後，您需要確認若要確定駐留並擷取通話運作符合預期組態。 請至少確認下列項目：

  - 呼叫具有已啟用的通話駐留的使用者，並讓使用者駐留通話。
    
    <div>
    

    > [!NOTE]  
    > 如果您啟用語音原則中的通話駐留之前執行這項測試，則駐留通話的使用者必須登出 Lync Server]，然後再重新登入，無法看到 [通話駐留] 選項在傳送呼叫清單。

    
    </div>

  - 撥打軌道號碼以擷取通話。

  - 其他通話駐留，讓駐留的通話逾時，並不會收取回電。 確認逾時通話正確地路由傳送至指定的**OnTimeoutURI**後援目的地。

</div>

<span> </span>

</div>

</div>

</div>

