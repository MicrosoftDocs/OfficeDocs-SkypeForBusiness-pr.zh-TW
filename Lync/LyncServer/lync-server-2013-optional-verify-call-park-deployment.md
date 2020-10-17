---
title: Lync Server 2013： (選用) 驗證通話駐留部署
description: Lync Server 2013： (選用) 驗證通話駐留部署。
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
ms.openlocfilehash: 772392a3a791ed57c3220d80e9bd510d8803debb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541929"
---
# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a> (選用) 在 Lync Server 2013 中驗證通話駐留部署

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-11_

安裝及設定通話駐留後，您必須確認設定，以確定停車場和取回通話如預期般地運作。 請至少確認下列項目：

  - 呼叫已啟用通話駐留且使用者寄存通話的使用者。
    
    <div>
    

    > [!NOTE]  
    > 如果您在執行此測試之前，在語音原則中啟用通話駐留，則寄存通話的使用者需要登出 Lync Server，然後再重新登入，才能在轉接通話清單中看到通話駐留選項。

    
    </div>

  - 撥打軌道號碼以取得通話。

  - 寄存另一次通話，讓寄存通話超時，但不要挑選回電。 確認已超時呼叫已正確路由傳送至 **OnTimeoutURI**所指定的回退目的地。

</div>

<span> </span>

</div>

</div>

</div>

